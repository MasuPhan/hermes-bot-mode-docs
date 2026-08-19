---
layout: default
title: Bắt đầu nhanh
parent: 👔 Business
grand_parent: Trang chủ
nav_order: 3
---

# Bắt đầu nhanh

Hướng dẫn làm quen với Bot Mode trong vài phút — không cần kiến thức lập trình.

## Bước 0 — Kiểm tra sẵn sàng

Bot Mode **đã tích hợp sẵn** trong Hermes Desktop bản mới. Chỉ cần:

- Hermes Desktop bản mới nhất (có plugin SDK).
- Nếu chưa thấy, vào **Settings → Plugins** và bật **Hermes Bots**.

> Nếu bạn đang chạy bản cũ chưa tích hợp sẵn, xem hướng dẫn cài plugin thủ công ở nhánh [Dev-driven → Cài đặt](../dev/cai-dat).

## Bước 1 — Mở tab Bots

Trong Hermes Desktop, tìm tab **Bots** (cạnh tab Sessions). Một danh sách bot hiện ra — ban đầu có thể chỉ có bot mặc định của bạn.

## Bước 2 — Tạo bot đầu tiên

1. Bấm **New Agent** (Tạo bot mới).
2. Điền **tên** (ví dụ `nghien-cuu`), **tiêu đề** và **mô tả**.
3. Bấm tạo. Bot xuất hiện trong danh sách.

Muốn tùy chỉnh sâu (model, kỹ năng, cá tính), mở phần **Advanced** — nhưng để bắt đầu, không cần.

## Bước 3 — Trò chuyện với bot

Click vào bot để mở chat riêng của nó. Gõ tin nhắn như chat bình thường. Bot có bộ nhớ và bối cảnh riêng — không biết chuyện của bot khác.

## Bước 4 — Giao việc định kỳ (Routines)

Bên cạnh hội thoại có ô **Routines**. Tạo một việc lặp lại, ví dụ:

> "Tóm tắt inbox của tôi mỗi sáng 8h."

Bot sẽ tự chạy theo lịch và kết quả nằm trong chat riêng của nó.

## Bước 5 — Cho bot nói chuyện với nhau

- Trong chat của bot A, gõ `@ten-bot-B` để chuyển việc cho bot B.
- Hoặc tạo **nhóm chat** từ header của một nhóm (gom 2–6 bot) để chúng phối hợp.

## Mẹo nhanh

| Muốn làm gì | Làm thế nào |
|---|---|
| Đổi avatar | Click phải bot → **Edit Profile** → đổi avatar |
| Nhân bản bot | Click phải bot → **Duplicate** |
| Gom bot vào nhóm | Click phải bot → **Move to group** |
| Xem bot đang chạy | Nhìn vạch **Active now** phía trên danh sách |
| Xóa bot | Click phải bot → **Delete Profile** (không xóa được bot mặc định) |

---

> 💡 Hiểu sâu về cách nó hoạt động bên trong → sang nhánh [🛠️ Dev-driven](../dev/kien-truc).