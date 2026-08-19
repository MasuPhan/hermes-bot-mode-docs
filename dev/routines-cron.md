---
layout: default
title: Routines & cron
parent: 🛠️ Dev
grand_parent: Trang chủ
nav_order: 4
---

# Routines & cron

Routines (lịch làm việc của bot) thực chất là **Hermes cron jobs** — không có cơ chế mới.

## Nguyên lý

Một routine được đặt tên theo namespace:

```text
[bot:<tên-bot>] <mô tả routine>
```

Ví dụ:

```text
[bot:nghien-cuu] Tóm tắt tin tức đối thủ mỗi sáng 8h
```

Vì là cron job Hermes chuẩn, routine:

- Hiện trong `hermes cron list`.
- Hiện trong trang **Cron** của Hermes Desktop.
- Chạy đúng theo lịch cron.

## Luồng hoạt động

1. Bạn tạo routine trong ô **Routines** của bot.
2. Hermes đăng ký một cron job, namespace theo tên bot.
3. Đến giờ, cron chạy — bot thực thi việc.
4. Kết quả (output) nằm trong **chat riêng của bot** (lịch sử session của bot đó).

## Vì sao dùng cron chuẩn?

- **Minh bạch** — nhìn được qua CLI, không ẩn.
- **Quản lý tập trung** — cùng hệ thống cron của Hermes.
- **Không cần daemon riêng** — tận dụng hạ tầng có sẵn.

## Lưu ý

- Routine gắn với **profile** của bot — phạm vi theo bot, không lẫn.
- Tạm dừng / lỗi routine xử lý qua cơ chế cron của Hermes.
- Muốn quản lý cron ở mức hệ thống, dùng `hermes cron` CLI.

> 💡 Hiểu cách bot giao tiếp → xem [Bot-to-bot messaging](bot-messaging).