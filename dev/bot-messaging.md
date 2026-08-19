---
layout: default
title: Bot-to-bot messaging
parent: 🛠️ Dev
grand_parent: Trang chủ
nav_order: 5
---

# Bot-to-bot messaging

Cách các bot nhắn tin cho nhau — và cách @mention chuyển việc.

## Nguyên lý: CLI handoff

Bot-to-bot không phải một kênh ẩn riêng. Nó là **CLI handoff thật** của Hermes:

```bash
hermes -p <bot-nhận> chat --in ~ -c "Bot Chat" -Q -q \
  "Message from 🤖 <bot-gửi> (@<bot-gửi>): ..."
```

Nghĩa là: bot gửi chạy lệnh Hermes CLI với profile của bot nhận, ghi tin nhắn vào chat "Bot Chat" của bot nhận, kèm attribution rõ ai gửi.

## Mỗi bot có một "Bot Chat" bền vững

Mỗi bot có một hội thoại **Bot Chat** cố định. Tin nhắn giữa các bot đều đổ vào đây, có ghi rõ:

```text
Message from 🤖 researcher (@researcher): ...
```

SOUL.md của bot dạy chúng giao thức này — bao gồm cả cách trả lời.

![Agent to Agent — bot nhắn tin cho bot]({{ site.baseurl }}/assets/img/agent-to-agent.png){: width="640"}

## @mention handoff

Trong bất kỳ chat nào, gõ:

```text
@researcher have a look at this
```

Bot đang hoạt động sẽ:

1. Chuyển tin nhắn cho bot `researcher`.
2. **Chờ** phản hồi.
3. **Báo lại** kết quả cho bạn.

## Giới hạn hiện tại

> ⚠️ **Bot-to-bot delivery là per-invocation.**

Bot nhận **thấy tin nhắn trong inbox khi nó chạy lần tới** — không phải real-time interrupt. Việc ngắt giữa chừng một bot đang hội thoại là **upstream future work** (chưa có ở thời điểm repo archive).

Nếu quy trình của bạn cần bot phản hồi ngay lập tức, đây là điểm cần lưu ý thiết kế.

## Avatar & tùy chỉnh

Avatar / pet customization lưu trong **plugin storage**, không làm bẩn profile. Profile của bot vẫn sạch sẽ.

> 💡 Muốn biết đường phát triển → xem [Mở rộng & plugin SDK](mo-rong).