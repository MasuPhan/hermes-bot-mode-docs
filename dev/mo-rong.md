---
layout: default
title: Mở rộng & plugin SDK
parent: 🛠️ Dev
grand_parent: Trang chủ
nav_order: 6
---

# Mở rộng & plugin SDK

Đường phát triển và cách mở rộng Bot Mode.

## Trạng thái upstream

Repo gốc `Hermes-Bot-Mode` đã **archive** (17/08/2026). Bot Mode giờ là plugin **bundled, bật mặc định** trong Hermes Desktop, phát triển tiếp trong tree:

```text
apps/desktop/src/plugins/hermes-bots/
```

Mọi **issue / PR** nộp về [`NousResearch/hermes-agent`](https://github.com/NousResearch/hermes-agent). Không cần cài thủ công trên bản Desktop mới.

## Mở rộng theo hướng nào

Vì Bot Mode chỉ là UI trên profile primitive, bạn có thể mở rộng bằng cách tận dụng các surface Hermes chuẩn:

### 1. Thêm kỹ năng (skills) cho bot

Mỗi bot có skills riêng. Gán kỹ năng phù hợp để bot chuyên sâu một lĩnh vực.

### 2. Tùy chỉnh SOUL.md

SOUL.md định nghĩa **cá tính và giao thức** của bot — gồm cả cách bot-to-bot trả lời. Đây là nơi bạn "đào tạo" hành vi bot.

### 3. Ghép thêm toolset / model

Pin model hoặc toolset riêng cho từng bot qua Advanced config — phù hợp khi bot cần model mạnh hơn hoặc quyền hạn khác.

### 4. Tận dụng cron & CLI

Routines và bot-to-bot đều là cơ chế Hermes chuẩn. Bạn có thể điều khiển bot từ CLI (`hermes -p <bot>`) ngoài UI.

## Viết plugin mới

Bot Mode là ví dụ điển hình về **desktop plugin** Hermes. Muốn viết plugin tương tự:

- Plugin nạp từ `~/.hermes/desktop-plugins/<tên>/plugin.js`.
- Dùng plugin SDK của Hermes Desktop.
- Feature-detect gateway RPC để degrade graceful.

## Lưu ý thiết kế khi mở rộng

- **Không patch core** — giữ nguyên nguyên tắc, tránh vỡ khi nâng cấp.
- **Tận dụng surface có sẵn** — profile, cron, CLI, RPC.
- **Feature-detect** — không giả định gateway có đủ RPC.
- **Bot-to-bot chưa real-time** — thiết kế quy trình chấp nhận độ trễ per-invocation.

---

## Tài liệu tham khảo chính thức

- [Hermes Agent](https://github.com/NousResearch/hermes-agent) — repo chính
- [Hermes-Bot-Mode (archive)](https://github.com/NousResearch/Hermes-Bot-Mode) — repo gốc
- [Docs Hermes Agent](https://hermes-agent.nousresearch.com/docs) — tài liệu chính thức