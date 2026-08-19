---
layout: default
title: "Nền tảng: Hermes profiles"
parent: 🛠️ Dev
grand_parent: Trang chủ
nav_order: 3
---

# Nền tảng: Hermes profiles

Để hiểu Bot Mode, phải hiểu **profile** — primitive mà nó dựng lên.

## Profile là gì?

Một Hermes profile là một **thực thể AI độc lập hoàn toàn**, lưu trong thư mục riêng:

```text
~/.hermes/profiles/<tên>/
├── config          # cấu hình riêng
├── memory          # bộ nhớ riêng
├── skills          # kỹ năng riêng
├── credentials     # thông tin đăng nhập riêng
└── history         # lịch sử chat riêng
```

Mỗi profile **không chia sẻ** bộ nhớ, kỹ năng, hay bối cảnh với profile khác. Đây chính là nguồn gốc tính "tách bạch" của Bot Mode.

## Vì sao thiết kế này quan trọng

1. **Cô lập dữ liệu** — bot kế toán không thấy dữ liệu bot sáng tạo.
2. **Tùy chỉnh sâu** — mỗi bot có thể có model, kỹ năng, SOUL.md riêng.
3. **Di động** — profile là thư mục, dễ backup, clone, di chuyển.

## Các RPC liên quan

Bot Mode dùng gateway RPC `profiles.*`:

| RPC | Chức năng |
|---|---|
| `profiles.list` | Liệt kê các profile (bot) |
| `profiles.create` | Tạo profile mới |
| `profiles.describe` | Xem chi tiết một profile |
| `profiles.configure` | Chỉnh cấu hình profile |

Kèm theo đó, `image.generate` dùng để tạo avatar bằng AI (trả về data URL, hoạt động cả gateway local lẫn remote).

Phần **Advanced** khi tạo/sửa bot cho phép tùy chỉnh sâu profile: model, kỹ năng, SOUL.md:

![Tạo agent — phần cấu hình nâng cao](/assets/img/new-agent-advanced.png){: width="440"}

## Feature-detect & degrade graceful

Plugin **không giả định** gateway có đủ RPC mới. Nó kiểm tra và giảm chức năng:

- Gateway cũ → roster (danh sách bot) vẫn hoạt động.
- Gateway mới → Advanced editing + avatar generation sáng lên.

Điều này giúp plugin chạy được trên nhiều phiên bản Hermes mà không vỡ.

## Liên hệ với Bot Mode

| Khái niệm Hermes | Trong Bot Mode |
|---|---|
| Profile | Bot |
| `~/.hermes/profiles/<tên>/` | Thư mục dữ liệu của bot |
| `profiles.*` RPC | Tạo / sửa / xóa bot |
| Cron job | Routine của bot |
| CLI `hermes -p <bot>` | Bot-to-bot messaging |

> 💡 Xem tiếp [Routines & cron](routines-cron) và [Bot-to-bot messaging](bot-messaging).