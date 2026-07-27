# Group Report — Day 02

## Thành viên nhóm

| STT | Họ và tên | Mã học viên | Vai trò trong nhóm |
|-----|-----------|-------------|--------------------|
| 1   | Sùng A Khua | 2A202601129 | Nhà đầu tư |
| 2   | Đoàn Vũ Hoàng | 20A202601727 | Thuyết trình |
| 3   | Lê Hoàng Long | 2A202601025 | Nhà đầu tư |
| 4   | Đàm Vinh Quang | 2A202601255 | Thành viên nhóm |

---

## 03 — Group Convergence: Nhật ký hội tụ (Từ candidates về 1 problem)

### 3.1 — Tổng hợp Candidates từ các cá nhân

| # | Candidate Problem | Người gặp vấn đề | Điểm nghẽn chính |
|---|---|---|---|
| 1 | **Lọc review sản phẩm online tránh seeding** | Người mua sắm online gia dụng, công nghệ | Đọc & tự phân biệt review thật vs. review seeding/ảo (Mất 90 phút) |
| 2 | Lên thực đơn 7 ngày & tối ưu thực phẩm tủ lạnh | Người nội trợ / Sống tự lập | Vắt óc suy nghĩ thực đơn thỏa mãn nhiều điều kiện cùng lúc |
| 3 | Khớp lịch rảnh chung để đặt lịch họp nhóm | Trưởng nhóm đồ án / PM | Phụ thuộc phản hồi chậm & dò ghép thủ công các khoảng lịch trống |
| 4 | Trích xuất quyết định & task từ tin nhắn nhóm chat | Team Leader / Quản lý CLB | Cuộn lướt hàng ngàn tin nhắn trôi mất quyết định chốt & phân công |

### 3.2 — Ma trận chấm điểm đồng thuận (Scoring Matrix)

| Candidate Problem | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Khả thi trong Lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **Lọc review sản phẩm online** | 5 | 5 | 5 | 5 | 5 | 5 | 5 | **35** |
| Lên thực đơn 7 ngày | 4 | 4 | 4 | 4 | 4 | 4 | 4 | **28** |
| Khớp lịch rảnh họp nhóm | 5 | 5 | 4 | 4 | 4 | 4 | 4 | **30** |
| Trích xuất task từ nhóm chat | 4 | 4 | 4 | 4 | 4 | 4 | 4 | **28** |

### 3.3 — Quyết định chọn của nhóm

* **Bài toán được chọn:** **Lọc review sản phẩm online tránh seeding** (Candidate #1 - Điểm cao nhất 35/35).
* **Vì sao chọn:**
  - Pain point rất thật và phổ biến đối với bất kỳ ai mua sắm thương mại điện tử (Shopee, TikTok Shop, Lazada).
  - Workflow hiện tại có baseline thời gian rất rõ ràng (120 phút/sản phẩm) và điểm nghẽn thủ công lớn.
  - Có thể áp dụng giải pháp Workflow AI (cào dữ liệu + LLM phân loại seeding + tóm tắt ưu/nhược điểm).
  - Kết quả có thể kiểm chứng ngay bằng cách so sánh bài tóm tắt AI với review thực tế trên sàn.
* **Vì sao không chọn bài khác:**
  - *Khớp lịch họp*: Đã có nhiều tool quy trình (Calendly/Google Calendar) giải quyết khá tốt mà không bắt buộc cần AI.
  - *Lên thực đơn*: Độ biến thiên khẩu vị cá nhân quá lớn, khó chuẩn hóa success metric trong thời gian lab.

---

## 04 — Quick Validation & Research giải pháp

### 4.1 — Kiểm chứng nhanh (Validation)

* **Khảo sát nhanh (Quick Interview)**: Phỏng vấn 5 người bạn thường xuyên mua hàng online (>500k/đơn).
  - *Kết quả*: 5/5 người đều mất ít nhất 1–2 tiếng lướt review trước khi bấm mua; 4/5 người từng mua phải hàng dỏm do tin vào review 5 sao ảo/seeding của shop.
* **Tín hiệu xác nhận (Insight)**: Pain thật không nằm ở việc "không có review", mà nằm ở chỗ **quá nhiều review rác/seeding** khiến người mua bị quá tải thông tin và mất niềm tin.

### 4.2 — Research giải pháp đã có trên thị trường

| Nguồn / Tool / Case | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / Rủi ro | Bài học cho nhóm |
|---|---|---|---|---|
| **Fakespot / ReviewMeta** | Phân tích review giả lập trên Amazon/eBay | Thuật toán nhận diện spam/seeding rất tốt | Không hỗ trợ tiếng Việt và chưa kết nối sàn Shopee/TikTok/Lazada | Áp dụng pattern nhận diện seeding (lặp từ khóa, tài khoản mới, đánh giá chung chung) |
| **Bộ lọc 1–3 sao trên Shopee** | Lọc xem các đánh giá thấp | Nhanh, có sẵn trên ứng dụng | Lẫn nhiều review tiêu cực do bên vận chuyển chứ không phải chất lượng SP | Cần dùng AI để phân loại đúng feedback về chất lượng SP vs. vận chuyển |
| **ChatGPT / Claude thủ công** | Tóm tắt text review dán vào | Khả năng tổng hợp Pros/Cons xuất sắc | Người dùng phải tự cào text dán tay vào chat, rất mất công | Cần xây dựng Workflow tự động cào dữ liệu qua Link URL |

---

## 05 — Current & Future Workflow bản nhóm

### 5.1 — Current Workflow (Trước khi tối ưu)

```text
CURRENT STATE — 5 bước, 120 phút

[1 Tìm kiếm sản phẩm trên sàn: 10']
→ [2 Cuộn lướt xem 200+ review: 20']
→ [3 Đọc & lọc review thật vs. seeding thủ công: 70']  <-- BOTTLENECK
→ [4 So sánh ưu/nhược điểm trong đầu: 15']
→ [5 Quyết định bấm chốt mua / bỏ qua: 5']
```

### 5.2 — Future Workflow (Sau khi tối ưu)

```text
FUTURE STATE — 4 bước, 13 phút

[1 Paste link sản phẩm vào công cụ: 1']  -- Script/Extension
→ [2 Auto-scrape & AI lọc seeding + tổng hợp Pros/Cons: 1']  -- AI Workflow Step
→ [3 Người dùng đọc bản summary & đánh giá rủi ro: 10']  -- HUMAN BOUNDARY
→ [4 Bấm chốt mua / chọn SP khác: 1']

Fallback: 
AI tổng hợp mơ hồ hoặc thiếu lượng review -> Hệ thống báo lỗi và gợi ý người dùng chuyển sang đọc lọc bộ 1-3 sao thủ công trên sàn.

Bottleneck mới: 
Người dùng đọc và đánh giá bản summary (10 phút). Đây là điểm kiểm soát chất lượng (Human Boundary) hoàn toàn chấp nhận được.
```

### 5.3 — Bảng so sánh Before / After Impact

| Metric | Trước | Sau kỳ vọng | Ghi chú |
|---|---:|---:|---|
| **Tổng thời gian nghiên cứu** | 120 phút | 13 phút | Giảm ~89% thời gian |
| **Số bước thực hiện** | 5 bước | 4 bước | Tự động hóa khâu đọc và lọc |
| **Số bước thủ công** | 5/5 bước | 2/4 bước | Người dùng chỉ nhập Link và đọc Kết quả |
| **Tỷ lệ mua đúng sản phẩm ưng ý** | ~80% | >95% | Loại bỏ rủi ro tin nhầm review seeding |
| **Risk mới** | Tốn thời gian & mua nhầm đồ kém | AI phân loại sai hoặc thiếu data | Cần giữ Human Boundary ở bước chốt mua |

---

## 06 — Rule / Workflow / Agent & Quyết định cuối

### 6.1 — So sánh phương án Rule / Workflow / Agent

| Mức | Phương án cho bài toán nhóm | Khi nào đủ | Rủi ro | Chọn? |
|---|---|---|---|---|
| **Rule** | Lọc theo số sao (1–3 sao) hoặc lọc từ khóa cố định | Đủ nếu chỉ cần xem đánh giá xấu nhất | Bỏ sót các bài viết seeding ẩn dưới dạng 5 sao hoặc review khen ảo | Không chọn làm toàn bộ |
| **Workflow** | Extension cào data -> LLM lọc seeding -> LLM tóm tắt Pros/Cons -> User đọc & mua | Hợp lý vì quy trình tuyến tính, AI xử lý dữ liệu ngôn ngữ rất tốt | AI phân loại nhầm review thật thành seeding | **CHỌN** |
| **Agent** | Agent tự động đọc review, tự cầm tiền bấm mua luôn cho user | Chỉ cần nếu muốn tự động hóa 100% khâu mua sắm | Quá rủi ro tài chính, người dùng luôn muốn tự quyết định mua hàng | Không chọn |

* **Mức chọn chính thức:** **Workflow**.
* **Lý do:** Khâu cào dữ liệu dùng Rule/Script; khâu phân tích cảm xúc & tóm tắt dùng AI; người dùng giữ vai trò quyết định mua sắm cuối cùng (Human-in-the-loop).

---

### 6.2 — Problem Statement v1

| Trường thông tin | Nội dung chi tiết |
|---|---|
| **Actor** | Người mua sắm online đồ gia dụng, thiết bị công nghệ cá nhân/gia đình. |
| **Workflow** | Paste Link SP -> Auto-scrape Review -> AI lọc Seeding & tổng hợp Pros/Cons -> Người dùng đọc tóm tắt -> Chốt mua. |
| **Bottleneck** | Khâu đọc và tự phân biệt review thật vs. review seeding/ảo (Mất 70–90 phút/sản phẩm). |
| **Impact** | Tốn 120 phút/lần mua sắm; tỷ lệ mua nhầm đồ kém chất lượng ~20% gây lãng phí tiền bạc. |
| **Success Metric** | Giảm tổng thời gian nghiên cứu từ 120 phút xuống dưới 15 phút/sản phẩm; Tỷ lệ mua đúng đồ ưng ý >95%. |
| **Boundary** | AI không tự động bấm mua hàng, không thay đổi giá sản phẩm; người dùng tự chịu trách nhiệm quyết định mua cuối cùng. |
| **AI Intervention Point** | Ngay sau khi cào xong toàn bộ dữ liệu review thô từ sàn, trước bước người dùng đọc tóm tắt. |
| **Mức chọn** | **Workflow** (Auto Scraper + LLM Classifier/Summarizer + Human Review). |
| **Rủi ro & Kiểm tra** | Rủi ro AI lọc nhầm review thật hoặc tổng hợp mơ hồ -> Người dùng kiểm tra lại các đoạn trích dẫn review gốc đính kèm trong bản summary. |

---

### 6.3 — Quyết định cuối cùng (Final Decision)

* **Decision:** **GO** (Tiến hành xây dựng phiên bản Pilot nhỏ).
* **Pilot nhỏ nhất (MVP):** Một Chrome Extension hoặc Web App đơn giản: Người dùng dán Link Shopee/TikTok Shop -> Trả về bản tóm tắt Ưu/Nhược điểm & Điểm uy tín (Seeding Score) trong 60 giây.
