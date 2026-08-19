---
layout: default
title: Cài đặt
parent: 🛠️ Dev
grand_parent: Trang chủ
nav_order: 2
---

# Cài đặt

## Trạng thái nhanh

✅ **Không cần cài thủ công** trên bản Hermes Desktop mới — Bot Mode là plugin **bundled, bật mặc định**. Chỉ cần vào **Settings → Plugins** và bật **Hermes Bots** nếu chưa thấy.

Phần dưới đây dành cho bản cũ hoặc khi cần cài plugin thủ công.

## Yêu cầu (Requirements)

- Hermes **desktop app** có plugin SDK (bản mới).
- Duyệt session theo profile cần bản Desktop có `host.openSession(id, { profile })`.
- Các RPC `profiles.*` / `image.generate` có trong bản hermes-agent ≥ giữa 2026 (`hermes update`). Plugin **feature-detect** gateway cũ: roster hoạt động mọi nơi; chỉ Advanced editing và avatar generation cần RPC mới.

## ⚠️ Cài đúng chỗ

> Đây là **desktop plugin** — phải cài trên máy chạy **Hermes desktop app**, **không phải** trên gateway.

Desktop plugins nạp từ thư mục phía app: `~/.hermes/desktop-plugins/`. Nếu bạn dùng gateway remote/SSH, cài trên máy gateway **không có tác dụng**.

Ví dụ: gateway trên homelab, desktop app trên MacBook → cài trên **MacBook**.

## Các bước cài thủ công

```bash
# Cách 1: clone repo vào thư mục plugin
git clone https://github.com/NousResearch/Hermes-Bot-Mode ~/.hermes/desktop-plugins/hermes-bots
```

Hoặc chỉ cần tải file `plugin.js`:

```bash
mkdir -p ~/.hermes/desktop-plugins/hermes-bots
curl -o ~/.hermes/desktop-plugins/hermes-bots/plugin.js \
  https://raw.githubusercontent.com/NousResearch/Hermes-Bot-Mode/main/plugin.js
```

Sau đó nạp lại plugin:

- **Ctrl+K → "Reload desktop plugins"**, hoặc
- Khởi động lại app.

Kết quả: tab **Bots** xuất hiện cạnh tab Sessions, và ô **Routines** dock bên cạnh hội thoại.

## Kiểm tra cài thành công

- Tab **Bots** hiện ra trong desktop app.
- Tạo được bot mới (New Agent).
- Nếu các tính năng nâng cao (avatar AI, advanced edit) không sáng — gateway đang cũ, chạy `hermes update`.

> 💡 Hiểu cơ chế đằng sau → xem [Kiến trúc](kien-truc) và [Hermes profiles](hermes-profiles).