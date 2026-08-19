---
layout: default
title: Các tình huống dùng thực tế
parent: 👔 Business
grand_parent: Trang chủ
nav_order: 2
---

# Các tình huống dùng thực tế

Bot Mode phát huy sức mạnh khi bạn có **nhiều việc AI làm thường xuyên, độc lập, cần tách bạch**. Dưới đây là các mẫu tình huống phổ biến.

## 1. Đội ngũ nội dung tự động

Gom nhiều bot chuyên viết nội dung thành một nhóm:

- **Bot Nghiên cứu** — tìm chủ đề, thu thập dữ liệu.
- **Bot Viết** — soạn bài từ dữ liệu.
- **Bot Biên tập** — rà lỗi, chuẩn hóa giọng văn.
- **Bot Đăng bài** — đưa bài lên kênh theo lịch.

Mỗi bot có bộ nhớ riêng về phong cách và chủ đề của mình, không bị lẫn. Nhóm chat giúp chúng phối hợp: bot Nghiên cứu `@Viết` để giao dữ liệu, bot Viết `@Biên tập` để nhờ rà soát.

## 2. Giám sát & cảnh báo theo lịch

- Bot **Theo dõi tin tức** — mỗi sáng quét tin tức đối thủ, tóm tắt, gửi vào chat riêng.
- Bot **Báo cáo** — cuối tuần tổng hợp số liệu, soạn báo cáo.
- Bot **Nhắc việc** — nhắc deadline, nhắc lịch họp.

Các bot này chạy theo **Routines** (lịch định kỳ) mà không cần bạn thao tác. Bạn chỉ mở chat của bot để xem kết quả.

## 3. Trợ lý chuyên môn tách bạch

- Bot **Kế toán** — chỉ giữ dữ liệu tài chính, không trộn với việc khác.
- Bot **Pháp lý** — chỉ xử lý hợp đồng, quy định.
- Bot **Sáng tạo** — chỉ làm ý tưởng, hình ảnh.

Nhờ mỗi bot là một profile riêng (bộ nhớ, kỹ năng, quyền riêng), bạn **không lo lộn dữ liệu** giữa các lĩnh vực nhạy cảm.

## 4. Phòng ban AI phối hợp (nhóm chat)

Khi một việc cần nhiều chuyên môn, gom 2–6 bot vào một **phòng chat chung**:

- Bạn giao việc, các bot trong phòng lần lượt đóng góp.
- Bot kéo nhau vào bằng `@ten-bot`.
- Việc cần quyết định quan trọng, bot `@bạn` lên để bạn quyết — có huy hiệu "cần bạn".

Giới hạn chống lặp vô hạn (10 tin/turn, 3 vòng) giữ cho phòng không "quay vòng" mãi.

## 5. Thử nghiệm cá tính & quy trình

Vì tạo bot nhanh và **nhân bản** dễ, bạn có thể thử nhiều cách cấu hình (SOUL.md, kỹ năng, model) mà không ảnh hưởng bot đang chạy.

---

## Khi nào KHÔNG nên dùng

- Việc **một lần, đơn giản** — chỉ cần một bot, không cần đội.
- Việc **cần quyết định của con người ngay lập tức** — bot-to-bot giao tiếp theo kiểu "gửi vào inbox, bot xử lý khi chạy lần tới", chưa phải real-time.
- Khi bạn chỉ cần **một trợ lý tổng hợp** — Bot Mode tối ưu cho tách bạch, không phải gộp chung.