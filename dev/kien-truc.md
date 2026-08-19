---
layout: default
title: Kiến trúc tổng quan
parent: 🛠️ Dev
grand_parent: Trang chủ
nav_order: 1
---

# Kiến trúc tổng quan

Hiểu Bot Mode hoạt động ra sao bên trong — điều quan trọng nhất cho developer.

## Nguyên lý cốt lõi

> **Một bot chính là một Hermes profile.**

Hermes lưu mỗi profile như một thư mục riêng biệt: `~/.hermes/profiles/<tên>/`, chứa config, bộ nhớ, kỹ năng, thông tin đăng nhập và lịch sử chat. Bot Mode **chỉ là một lớp giao diện (UI)** phía trên primitive này.

Hệ quả quan trọng:

- **Không patch core** — không sửa mã nguồn Hermes.
- **Không có daemon nền** — không có tiến trình chạy ngầm thêm.
- **Không lưu trữ phụ** — mọi thứ dùng surface có sẵn của Hermes.

## Các thành phần ghép nối

| Tính năng | Cơ chế bên dưới |
|---|---|
| Mở chat / duyệt session | Session navigation có nhận biết profile (`host.openSession(id, { profile })`) |
| Tạo / sửa bot | Gateway RPC `profiles.*` (`list`, `create`, `describe`, `configure`) |
| Tạo avatar bằng AI | RPC `image.generate` (hoạt động cả gateway local lẫn remote, trả về data URL) |
| Routines | Là các **cron job** Hermes thường, namespace `[bot:<tên>] <routine>` — cũng hiện trong `hermes cron list` và trang Cron |
| Bot-to-bot | Là **CLI handoff** thật: `hermes -p <bot> chat --in ~ -c "Bot Chat" -Q -q "..."` |

## Luồng dữ liệu cơ bản

```text
Hermes Desktop (plugin Bot Mode)
        │  UI trên profile primitive
        ▼
Hermes profile (~/.hermes/profiles/<tên>/)
        │  config · memory · skills · credentials · history
        ▼
Gateway RPCs (profiles.*, image.generate)
        ▼
Hermes cron (Routines) ──► CLI handoff (bot-to-bot)
```

## Ưu điểm của thiết kế này

1. **An toàn khi nâng cấp** — vì không đụng core, lên bản Hermes mới không vỡ.
2. **Tương thích ngược** — plugin feature-detect gateway cũ, degrade graceful (roster vẫn chạy; chỉ các tính năng nâng cao mới cần RPC mới).
3. **Minh bạch** — bot-to-bot và routines là các cơ chế Hermes chuẩn, nhìn được qua CLI.

## Trạng thái hiện tại

Repo gốc `Hermes-Bot-Mode` đã **archive** (17/08/2026). Tính năng giờ nằm trong tree `hermes-agent` tại `apps/desktop/src/plugins/hermes-bots/`, là plugin bundled mặc định. Mọi issue/PR nộp về `NousResearch/hermes-agent`.

> 💡 Muốn hiểu primitive đứng sau → xem [Hermes profiles](hermes-profiles).