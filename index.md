---
layout: home
title: Trang chủ
nav_order: 1
permalink: /
---

# Hermes Bot Mode · Tài liệu kiến thức

**Hermes Bot Mode** là tính năng của [Hermes Agent](https://github.com/NousResearch/hermes-agent) — một hệ điều hành AI cá nhân chạy trên máy của bạn. Bot Mode biến các **agent profiles** (hồ sơ AI riêng biệt) thành một **đội bot** có tên tuổi, mỗi bot có chat riêng, avatar, cá tính và lịch làm việc riêng.

Ban đầu là một plugin mã nguồn mở ([NousResearch/Hermes-Bot-Mode](https://github.com/NousResearch/Hermes-Bot-Mode)), nay tính năng này đã được **tích hợp sẵn trong Hermes Desktop** — không cần cài thêm gì.

> 📦 Lưu ý: repo gốc đã được archive (17/08/2026) vì Bot Mode đã ship bundled trong Hermes Desktop. Phát triển tiếp tục trong tree của `hermes-agent`. Tài liệu này giải thích tính năng và cách dùng, không phụ thuộc repo gốc.

---

## Bạn đọc theo vai trò nào?

Tài liệu này được chia làm hai đường, theo đúng nhu cầu của hai tệp người đọc:

### 👔 Business-driven — hiểu giá trị, không cần code

Muốn biết **Bot Mode là gì, mang lại lợi ích gì, dùng khi nào**, mà không cần đụng tới kỹ thuật.

- [Bot Mode là gì?](business/tong-quan) — chức năng chính và giá trị cốt lõi
- [Các tình huống dùng thực tế](business/use-cases) — khi nào nên dùng, ví dụ cụ thể
- [Bắt đầu nhanh](business/bat-dau) — làm quen trong vài phút, không cần code

### 🛠️ Dev-driven — hiểu kiến trúc và mở rộng

Muốn biết **nó hoạt động ra sao bên trong, cài đặt thế nào, mở rộng được không**.

- [Kiến trúc tổng quan](dev/kien-truc) — bot = Hermes profile, không patch core
- [Cài đặt](dev/cai-dat) — yêu cầu và các bước cài đặt
- [Nền tảng: Hermes profiles](dev/hermes-profiles) — hiểu primitive đứng sau
- [Routines & cron](dev/routines-cron) — lịch làm việc của bot
- [Bot-to-bot messaging](dev/bot-messaging) — bot giao tiếp với nhau thế nào
- [Mở rộng & plugin SDK](dev/mo-rong) — đường phát triển tiếp theo

---

## Tóm tắt nhanh (30 giây)

| Câu hỏi | Trả lời |
|---|---|
| Nó là gì? | Biến các hồ sơ AI của Hermes thành một đội bot riêng biệt, mỗi bot có chat + avatar + lịch riêng |
| Cần cài gì? | Không — đã tích hợp sẵn trong Hermes Desktop |
| Bot là gì về mặt kỹ thuật? | Một Hermes profile (config, memory, skills, credentials riêng) |
| Bot nói chuyện với nhau được không? | Có — bot-to-bot messaging + @mention handoff |
| Có lịch làm việc không? | Có — Routines, chạy bằng Hermes cron |
| Có sửa core Hermes không? | Không — toàn bộ là UI trên surface có sẵn |

---

*Tài liệu tiếng Việt do MasuPhan biên soạn, dựa trên repo mã nguồn mở Hermes-Bot-Mode (MIT © Nous Research).*