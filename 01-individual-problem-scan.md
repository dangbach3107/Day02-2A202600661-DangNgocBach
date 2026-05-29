# 01 — Individual Problem Scan

**Tác giả:** Đặng Ngọc Bách  
**Ngày:** May 29, 2026  

## Scan rộng

Bách scan 10 problems, vượt mức tối thiểu 5.

| # | Lăng kính | Problem quan sát được | Ai đang đau? | Dấu hiệu thật |
|---|---|---|---|---|
| 1 | Tốn thời gian | Trích xuất thông số, so sánh khi đọc bài báo khoa học (Paper AI) | SV nghiên cứu, thực tập sinh | Mất khoảng 30-45 phút/paper |
| 2 | Lặp lại | Bẻ nhỏ task (WBS) và ước lượng thời gian chạy đồ án | Trưởng nhóm, sinh viên | Mất 2-3 tiếng/dự án, dễ bỏ sót việc |
| 3 | AI có thể tốt hơn | Bí ý tưởng khi nhắn tin bắt chuyện/tán tỉnh, sợ nhạt | Nam độc thân, người dùng | Mất 15-20 phút chỉ để nghĩ 1 tin nhắn |
| 4 | Tốn thời gian | Tự kẻ vẽ hỗ trợ/kháng cự và phân tích lực mua/bán (PTKT) | Nhà giao dịch, SV tài chính | 20 phút/biểu đồ, dễ bị cảm xúc chi phối |
| 5 | Lặp lại | Phải click đọc thủ công hàng chục Abstract từ email alert học thuật | SV nghiên cứu | 30-45 phút mỗi sáng, dễ bị mỏi mắt |
| 6 | Tốn thời gian | Tìm kiếm quyết định/link tài liệu cũ trong nhóm chat Zalo | Cả team | 10-15 phút/lần tìm, hay trôi tin |
| 7 | Lặp lại | Format trích dẫn chuẩn IEEE cho báo cáo đồ án | SV làm đồ án | 30 phút rà soát trước khi nộp |
| 8 | Pain từ người khác | Mentor phải chỉ lại cách cấu hình môi trường code | Thực tập sinh, mentor | Hỏi đi hỏi lại mỗi khi có mem mới |
| 9 | Tốn thời gian | Viết báo cáo tiến độ (Weekly update) thực tập | Thực tập sinh | Lặp lại mỗi cuối tuần |
| 10 | Pain từ người khác | Code bị lỗi syntax thư viện cũ, không biết sửa ở đâu | Developer | Mất hàng giờ tra StackOverflow |


## Top 5 Chọn Để Deep-Dive

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---|---|---|---|
| 1 | Lập WBS / Gantt | Workflow rõ, giải quyết pain thật khi chạy dự án nhóm | Agent hay Workflow là đủ |
| 2 | Đọc Paper AI | Trực tiếp hỗ trợ công việc thực tập/đồ án, metric tốt | AI tóm tắt có bị sót ý chính (hallucination) không |
| 3 | Tán gái + Nhắn tin | Siêu thú vị, dễ làm demo, dễ cảm nhận "nỗi đau" | Xử lý giọng văn (tone/voice) sao cho tự nhiên |
| 4 | Tóm tắt PTKT | Workflow tuyến tính, tận dụng Vision-Language model | Rủi ro AI nhận định sai dẫn đến mất tiền |
| 5 | Lọc Email Alert | Giảm tải việc lặp lại mỗi sáng cực kỳ rõ rệt | Bỏ lỡ paper quan trọng do AI chấm điểm sai |

---

## Problem Card #1 — Đọc Paper AI

**Problem 1 câu:** Tốn quá nhiều thời gian để trích xuất thông số kỹ thuật và so sánh phương pháp từ hàng chục bài báo khoa học (paper) về mô hình AI mới.

**Actor:** Sinh viên nghiên cứu / Thực tập sinh AI cần làm literature review.

**Thời điểm / bối cảnh:** Quá trình đọc tài liệu để chuẩn bị bảo vệ đồ án hoặc viết báo cáo.

**Current workflow:**
```text
1. Tải file PDF từ arXiv.
2. Đọc lướt Abstract & Conclusion.
3. Highlight các ý chính (dataset, loss function, accuracy).
4. Đưa các thông số vào bảng so sánh chung trên Sheets.
5. Phân tích khác biệt và viết lại tóm tắt.
```

**Bottleneck:** Bước 3 và 4 — việc dò tìm thông số và điền bảng đối chiếu tốn khoảng 30-45 phút/paper.

**Impact:** Mất hàng tuần chỉ để đọc và lọc tài liệu, làm chậm tiến độ bắt tay vào code thực nghiệm.

**Success metric:** Giảm thời gian trích xuất thông tin cốt lõi xuống dưới 5 phút/paper.

**Non-AI alternative:** Tạo template đọc chuẩn hóa, chia đều số lượng bài cho các thành viên review chéo.

**AI hypothesis:** Hệ thống AI (RAG/NotebookLM) tự động trích xuất thông số vào bảng theo tiêu chí định sẵn. Người dùng chỉ cần kiểm tra độ chính xác.

**Quick gut:** Workflow.

### Draft current workflow
```text
CURRENT STATE — 45 phút/paper

[1 Tải PDF: 2']
→ [2 Đọc lướt Abstract: 5']
→ [3 Dò tìm & highlight: 15']
→ [4 Điền bảng Sheets: 15']  <-- bottleneck
→ [5 Phân tích: 8']
```

### Draft future workflow
```text
FUTURE STATE — 14 phút/paper

[1 Tải PDF: 2']
→ [2 Upload hệ thống: 1']
→ [3 AI trích xuất + điền bảng: 1']
→ [4 SV rà soát + verify số liệu: 5']  <-- human boundary
→ [5 Phân tích: 5']

Fallback: AI trích xuất thiếu → SV đọc dò lại thủ công.
```

---

## Problem Card #2 — Lập WBS / Gantt Chart

**Problem 1 câu:** Việc bẻ nhỏ công việc (WBS) và ước lượng thời gian từ Project Charter thường bị thiếu sót task nhỏ hoặc tốn quá nhiều thời gian họp nhóm.

**Actor:** Trưởng nhóm dự án / Sinh viên quản lý dự án.

**Thời điểm / bối cảnh:** Giai đoạn lập kế hoạch đầu kỳ để chạy đồ án.

**Current workflow:**
```text
1. Đọc chốt mục tiêu từ Project Charter.
2. Họp brainstorm chia dự án thành các Phases.
3. Tự nghĩ và bẻ nhỏ Phase thành task con.
4. Ước lượng thời gian/nguồn lực cho từng task.
5. Nhập liệu để vẽ Gantt chart.
```

**Bottleneck:** Bước 3 và 4 — "mù" ý tưởng, dễ bỏ sót hidden tasks, tốn hàng giờ cãi nhau chốt tiến độ.

**Impact:** Mất nhiều buổi họp, dự án chạy thực tế bị vỡ kế hoạch do phát sinh việc chưa lường trước.

**Success metric:** Rút ngắn thời gian draft WBS từ 3 tiếng xuống 15 phút, độ bao phủ công việc đạt >80%.

**Non-AI alternative:** Tìm kiếm và tái sử dụng template WBS của các khóa trước.

**AI hypothesis:** AI đóng vai chuyên gia PM, nhận Project Charter và đề xuất draft WBS chi tiết kèm estimate thời gian.

**Quick gut:** Workflow.

### Draft current workflow
```text
CURRENT STATE — 180 phút

[1 Đọc Charter: 15']
→ [2 Brainstorm: 30']
→ [3 Bẻ nhỏ WBS: 60']  <-- bottleneck
→ [4 Ước lượng thời gian: 45']
→ [5 Vẽ Gantt: 30']
```

### Draft future workflow
```text
FUTURE STATE — 29 phút

[1 Input Charter vào prompt: 2']
→ [2 AI draft WBS + Estimate: 2']
→ [3 Trưởng nhóm review + edit: 20']  <-- human boundary
→ [4 Export Data Gantt: 5']

Fallback: AI ảo tưởng task → Trưởng nhóm họp chốt tay như cũ.
```

---

## Problem Card #3 — Tán gái + Nhắn tin

**Problem 1 câu:** Bị "blank brain" và đắn đo suy nghĩ quá lâu khi nhắn tin làm quen, dẫn đến trả lời nhạt hoặc đánh mất cơ hội.

**Actor:** Nam giới độc thân ngại giao tiếp hoặc sợ nói hớ.

**Thời điểm / bối cảnh:** Nhận được tin nhắn của đối phương và cần reply sao cho mặn mà.

**Current workflow:**
```text
1. Đọc tin nhắn đối phương.
2. Gõ nháp phương án 1 (xóa vì sợ nhạt).
3. Gõ nháp phương án 2 (xóa vì thấy sai).
4. Tìm kiếm Google/TikTok để có meme chữa cháy.
5. Chốt gửi tin nhắn an toàn kèm emoji.
```

**Bottleneck:** Bước 2, 3 và 4 — overthink khiến việc soạn tin mất 20 phút mà chất lượng lại thấp.

**Impact:** Cuộc trò chuyện đi vào ngõ cụt (dead air), mất cơ hội phát triển mối quan hệ.

**Success metric:** Rút ngắn thời gian chốt tin nhắn xuống dưới 2 phút, tỷ lệ được phản hồi (reply rate) cao.

**Non-AI alternative:** Chụp màn hình gửi bạn bè nhờ quân sư (mất thời gian đợi).

**AI hypothesis:** Hệ thống AI đọc ngữ cảnh, gợi ý 3 phương án (Hài hước, Tinh tế, An toàn) kèm meme. Người dùng duyệt và gửi.

**Quick gut:** Agent.

### Draft current workflow
```text
CURRENT STATE — 22 phút/tin

[1 Đọc tin: 1']
→ [2 Nháp 1: 5']
→ [3 Nháp 2: 5']
→ [4 Tìm meme/ảnh: 10']  <-- bottleneck
→ [5 Gửi tin chung chung: 1']
```

### Draft future workflow
```text
FUTURE STATE — 4 phút/tin

[1 Nhận tin: 1']
→ [2 AI phân tích + gợi ý 3 replies + meme: 1']
→ [3 Chọn + chỉnh sửa theo tone: 2']  <-- human boundary
→ [4 Nhấn gửi: 0']

Fallback: AI gợi ý quá "máy móc" → Người dùng tự gõ reply.
```

---

## Problem Card #4 — Tóm tắt PTKT

**Problem 1 câu:** Tốn nhiều thời gian và dễ bị cảm xúc chi phối khi tự vẽ hỗ trợ/kháng cự và phân tích lực mua/bán trên biểu đồ chứng khoán.

**Actor:** Nhà giao dịch cá nhân / Sinh viên tìm hiểu thị trường tài chính.

**Thời điểm / bối cảnh:** Trước phiên giao dịch, cần soi biểu đồ để đưa ra quyết định vào lệnh.

**Current workflow:**
```text
1. Mở TradingView xem biểu đồ.
2. Kẻ vẽ đường xu hướng, vùng cản quan trọng.
3. Đối chiếu Volume đánh giá lực thị trường.
4. Tổng hợp tin tức cơ bản.
5. Ra quyết định mua/bán.
```

**Bottleneck:** Bước 2 và 3 — phân tích thủ công mất 15-20 phút và dễ bị thiên kiến xác nhận (bias).

**Impact:** Lỡ mất điểm vào lệnh đẹp hoặc chịu rủi ro vì phân tích sai lệch.

**Success metric:** Rút ngắn thời gian tóm tắt tín hiệu kỹ thuật xuống dưới 3 phút/biểu đồ.

**Non-AI alternative:** Dùng rule-based indicator có sẵn hoặc mua tín hiệu từ group.

**AI hypothesis:** Người dùng cung cấp ảnh biểu đồ, Vision AI nhận diện vùng giá, tóm tắt diễn biến và lực cung/cầu.

**Quick gut:** Workflow.

### Draft current workflow
```text
CURRENT STATE — 25 phút

[1 Mở biểu đồ: 2']
→ [2 Kẻ vẽ vùng cản: 10']  <-- bottleneck
→ [3 Soi Volume: 5']
→ [4 Đọc tin tức: 5']
→ [5 Chốt quyết định: 3']
```

### Draft future workflow
```text
FUTURE STATE — 8 phút

[1 Chụp màn hình gửi AI: 1']
→ [2 AI Vision phân tích + tổng hợp: 2']
→ [3 Đọc report tóm tắt: 3']  <-- human boundary
→ [4 Tự quyết định mua/bán: 2']

Fallback: AI nhận diện sai nến/vùng giá → User bắt buộc phân tích lại thủ công.
```

---

## Problem Card #5 — Lọc Email Alert Nghiên cứu

**Problem 1 câu:** Mỗi sáng phải click đọc thủ công hàng chục Abstract từ các email alert bài báo khoa học, gây quá tải và lỡ thông tin.

**Actor:** Sinh viên nghiên cứu / Kỹ sư AI cần theo dõi tiến bộ công nghệ.

**Thời điểm / bối cảnh:** Mỗi sáng mở hộp mail kiểm tra thông báo từ Google Scholar/arXiv.

**Current workflow:**
```text
1. Mở email tổng hợp.
2. Đọc lướt tiêu đề bài báo.
3. Click mở link đọc Abstract của bài tiềm năng.
4. Lưu link vào Notion nếu hữu ích.
5. Lặp lại chu trình.
```

**Bottleneck:** Bước 2 và 3 — tiêu đề không nói rõ phương pháp, việc click và đọc thủ công rất mỏi mắt và tốn thì giờ.

**Impact:** Dễ bị nản, dần dần bấm "Mark as read" toàn bộ và lỡ mất kiến thức trọng tâm.

**Success metric:** Thời gian lọc thư mỗi sáng dưới 5 phút, không bỏ sót bài báo theo keyword trọng điểm.

**Non-AI alternative:** Cài filter rules Gmail chặt chẽ hơn (dễ bị sót) hoặc dùng RSS reader.

**AI hypothesis:** AI workflow tự bắt mail, chấm điểm liên quan (relevance score), tóm tắt 2 dòng và đẩy báo cáo ngắn gọn.

**Quick gut:** Workflow.

### Draft current workflow
```text
CURRENT STATE — 34 phút

[1 Mở list mail: 2']
→ [2 Đọc tiêu đề: 5']
→ [3 Đọc Abstract từng bài: 20']  <-- bottleneck
→ [4 Lưu link: 5']
→ [5 Đóng thư: 2']
```

### Draft future workflow
```text
FUTURE STATE — 6 phút

[1 Auto-catch email: 0']
→ [2 AI chấm điểm + tóm tắt: 1']
→ [3 Đọc daily report: 4']  <-- human boundary
→ [4 Auto-push lên Notion: 1']

Fallback: AI tóm tắt sai bối cảnh → Mở link gốc tự đọc Abstract.
```