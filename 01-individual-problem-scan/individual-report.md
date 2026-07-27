# Phase 1: Individual scan

| # | Lăng kính | Problem quan sát được | Ai chịu ảnh hưởng? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Pain từ người khác | Nhiều sinh viên bị lỡ các thông tin quan trọng | Sinh viên, nhà trường | Nhiều bạn học không để ý email, không biết có các sự kiện quan trọng cần tham gia |
| 2 | Pain từ người khác, tốn thời gian | Nhiều sinh viên gặp khó khăn trong việc thực hiện các thủ tục hành chính | Sinh viên | Mỗi lần thực hiện thủ tục lại phải xem lại cách cách làm trên cổng trực tuyến |
| 3 | Pain từ người khác | Nhiều sinh viên có thắc mắc nhưng không biết phải hỏi ai | Sinh viên | Trên các nhóm có nhiều câu hỏi nhưng không nhận được câu trả lời thỏa đáng vì ít người gặp phải hay quan tâm |
| 4 | Pain từ người khác, AI có thể làm tốt hơn| Thông tin trực quan về ngành học, chương trình đào tạo còn mơ hồ, khó tiếp cận| Nhà trường | Mỗi mùa tuyển sinh lại có rất nhiều câu hỏi về ngành học trên các hội nhóm |
| 5 | Pain từ người khác | Cán bộ, giảng viên khó khăn trong việc nắm bắt nguyện vọng, mong muốn của sinh viên| Cán bộ, giảng viên | Ít hoạt động, sự kiện mà nhiều sinh viên nhiệt tình tham gia |

# Phase 2: Problem Cards + draft workflow 

## Chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Lỡ thông tin quan trọng | Nhiều người mắc phải | Khó metric hiệu quả |
| 2 | Thủ tục hành chính | Pain  thật | Không chắc sẽ cải thiện được quá nhiều |
| 3 | Trực quan ngành học, chương trình đào tạo| Nhiều người quan tâm | Phạm vi có thể hơi rộng |

## Problem card

```text
Problem 1 câu: Nhiều sinh viên gặp khó khăn và mất thời gian khi thực hiện các thủ tục hành chính trên cổng trực tuyến của nhà trường.

Actor: Sinh viên cần thực hiện các thủ tục hành chính.

Thời điểm / bối cảnh: Mọi lúc (vì thực hiện online nên sinh viên có thể vào làm tại mọi thời điểm).

Current workflow:
1. Kiểm tra xem thủ tục mình cần có thể thực hiện trực tuyến hay không.
2. Xem lại hướng dẫn cách khai báo và thực hiện (vì không phải ai cũng làm thường xuyên để có thể nhớ và nắm cách rõ cách thực hiện).
3. Khai báo thông tin, chuẩn bị các giấy tờ cần thiết.
4. Đợi kết quả (phải vào kiểm tra liên tục vì không biết lúc nào sẽ có kết quả),

Bottleneck: Bước 2 xem lại hướng dẫn thực hiện gây mất thời gian không cần thiết.

Impact: Tốn thời gian của nhiều sinh viên.

Success metric: Giảm thời gian thực hiện các thủ tục hành chính trực tuyến.

Non-AI alternative: Option dialog dựa trên rule.

AI hypothesis: AI dạng chatbot giúp hiểu yêu cầu và hướng dẫn sinh viên nhanh hơn.

Quick gut:
[ ] No AI / process fix
[ ] Rule
[X] Workflow
[ ] Agent
[ ] Chưa biết

Future workflow: Sinh viên tương tác trực tiếp với AI để đưa ra yêu cầu và AI sẽ đưa ra hướng dẫn và tự động điều hướng, thực hiện các bước trung gian không mang tính cá nhân. Sau khi thủ tục hoàn thành sẽ gửi email trực tiếp đến sinh viên.

Fall back: AI có thể hiểu sai ý sinh viên dẫn tới hướng dẫn sai -> sinh viên cần feedback lại nếu AI không hướng dẫn đúng như mong muốn và cán bộ phụ trách cũng cần thường xuyên kiểm tra lịch sử các lần thực hiện.
```