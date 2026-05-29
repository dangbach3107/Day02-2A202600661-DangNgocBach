# 02 — Group Problem Statement

## Group convergence

Nhóm 3-4 người, mỗi người share top 3. Dưới đây là các problem tiêu biểu được tổng hợp lại từ các thành viên.

| Cluster | Candidate examples | Pattern chung |
| --- | --- | --- |
| Giao tiếp / Cá nhân hóa | Tán gái + Nhắn tin làm quen | Bị "blank brain", overthinking khi tạo nội dung giao tiếp, cần gợi ý theo ngữ cảnh. |
| Phân tích / Tối ưu hóa | Tối ưu CV theo JD tuyển dụng | Cần đối chiếu nội dung hiện tại với tiêu chuẩn mẫu (JD) để tìm ra điểm thiếu sót và sửa đổi. |
| Xử lý tài liệu / Ngôn ngữ | Dịch paper tiếng Anh giữ nguyên cấu trúc | Chuyển đổi ngôn ngữ tài liệu nhưng phải duy trì nghiêm ngặt format, bố cục và yếu tố kỹ thuật. |

## Shortlist và score

| Candidate | Actor rõ | Workflow rõ | Pain có evidence | Impact đo được | Làm trong lab | So sánh R/W/A được | Nhóm hiểu domain | Tổng |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Tán gái + Nhắn tin | 5 | 5 | 4 | 3 | 3 | 4 | 4 | 28 |
| Tối ưu CV theo JD | 5 | 4 | 5 | 5 | 5 | 5 | 5 | 34 |
| Dịch paper giữ cấu trúc | 5 | 4 | 5 | 4 | 5 | 4 | 5 | 32 |

Nhóm chọn: **Dịch paper tiếng Anh giữ nguyên cấu trúc** (Tuy Tối ưu CV điểm cao, nhưng Dịch paper là bài toán nặng về kỹ thuật xử lý tài liệu, rất phù hợp để ứng dụng AI giải quyết triệt để bottleneck về format).

Vì sao chọn:

* Actor (Sinh viên AI, người nghiên cứu) và pain point cực kỳ rõ ràng.
* Nỗi đau mất cấu trúc (bảng biểu, công thức) khi dịch thủ công chưa có tool phổ thông nào giải quyết trọn vẹn.
* Có thể đo lường impact trực tiếp qua thời gian đọc và mức độ giữ nguyên layout.
* Rất phù hợp để thực hành R/W/A với các mô hình AI xử lý PDF và ngôn ngữ.

Vì sao không chọn các bài khác:

* Tán gái + Nhắn tin: Workflow rõ nhưng impact mang tính cảm quan cá nhân, khó đo lường chính xác tỷ lệ thành công (reply rate) trong môi trường lab.
* Tối ưu CV theo JD: Là một bài toán tốt, nhưng dễ bị trùng lặp với quá nhiều tool tạo CV AI hiện có trên thị trường.

## Quick validation

Nhóm hỏi nhanh 3 bạn sinh viên/researcher.

| Nguồn | Số người | Tín hiệu xác nhận | Tín hiệu phản bác | Nhóm sửa problem thế nào |
| --- | --- | --- | --- | --- |
| Quick interview | 3 | 3/3 người đều than phiền việc dùng Google Translate phá nát các công thức toán và format chia 2 cột của paper. | 1 người dùng DeepL bản Pro thấy khá ổn, nhưng thỉnh thoảng vẫn lệch bảng biểu. | Thu hẹp problem: Tập trung xử lý các paper chuyên ngành kỹ thuật/AI có nhiều toán học, công thức và layout phức tạp. |
| Mini poll | 6 | 5/6 thừa nhận tốn gấp đôi thời gian để đối chiếu bản dịch và bản gốc để xem hình/công thức. | Có người bảo chỉ cần đọc Abstract và Conclusion, không cần dịch cả bài. | Thêm tính năng: Cho phép chọn dịch toàn bài hoặc chỉ dịch các section cụ thể giữ nguyên layout. |

Insight sau validation:

```text
Pain thật không chỉ nằm ở việc "không hiểu tiếng Anh". Pain lớn nhất là "sự đứt gãy mạch đọc" khi phải liên tục chuyển đổi giữa bản gốc (để xem hình/công thức) và bản dịch (để hiểu text) do các công cụ dịch hiện tại phá vỡ layout.

```

## Research giải pháp

Nhóm tìm các hướng đã có sẵn, không giả định phải tự build từ đầu.

| Nguồn / tool / case | Link | Họ giải quyết phần nào? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
| --- | --- | --- | --- | --- | --- |
| DeepL Translate | [https://www.deepl.com](https://www.deepl.com) | Dịch file PDF/Word | Dịch ngữ cảnh tốt, tự nhiên | Hay bị lỗi font, lệch bảng biểu với file PDF 2 cột phức tạp. | Cần bóc tách text và layout riêng trước khi đưa qua engine dịch. |
| ChatPDF / SciSpace | [https://www.chatpdf.com](https://www.chatpdf.com) | Hỏi đáp trên tài liệu | Summarize và giải thích thuật ngữ cực tốt | Không output ra một file PDF hoàn chỉnh giữ nguyên layout ban đầu. | Trải nghiệm đọc liền mạch trên 1 file quan trọng hơn chat hỏi đáp tản mạn. |
| Google Translate (Documents) | [https://translate.google.com](https://translate.google.com) | Dịch toàn bộ file | Tốc độ nhanh, miễn phí | Dịch thuật ngữ chuyên ngành AI kém, format vỡ nát. | AI cần được mớm prompt ngữ cảnh học thuật/AI thay vì dịch word-by-word. |

Research takeaway:

```text
Không thể đưa thẳng PDF vào một mô hình dịch đơn thuần. Cần thiết kế một Workflow: Bóc tách cấu trúc (Heading, Text, Hình ảnh, Math) -> Chỉ đưa Text qua AI dịch thuật chuyên ngành -> Ráp lại theo cấu trúc ban đầu.

```

## Workflow before/after

Nội dung workflow:

```text
CURRENT STATE — 5 bước, 120 phút/paper

[1 Tìm và tải paper: 5']
→ [2 Đọc abstract (tự dịch/Google): 10']
→ [3 Copy từng đoạn text, bỏ qua hình/công thức: 30']  <-- bottleneck 1
→ [4 Paste qua công cụ dịch & đọc kết quả: 45']        <-- bottleneck 2
→ [5 Đối chiếu lại bản gốc để xem hình/công thức: 30']

FUTURE STATE — 4 bước, 60 phút/paper

[1 Tìm và tải PDF paper: 5']
→ [2 AI phân tích layout + dịch text + ráp lại PDF tiếng Việt: 5']  -- Workflow step
→ [3 Người dùng đọc bản PDF đã dịch với layout nguyên vẹn: 50']     -- Trải nghiệm đọc liền mạch
→ [4 Nhấn gửi/lưu trữ: 0']

Fallback:
AI dịch thuật ngữ chuyên ngành quá tối nghĩa → Người dùng trỏ chuột để xem nguyên bản tiếng Anh của câu đó.

Bottleneck mới:
AI parsing có thể nhận diện sai text trong hình ảnh hoặc công thức toán phức tạp. Cần có cơ chế fallback hiển thị bản gốc.

```

Before/after impact:

| Metric | Trước | Sau kỳ vọng | Ghi chú |
| --- | --- | --- | --- |
| Tổng thời gian đọc hiểu | 120 phút | Giảm 50% (còn ~60 phút) | Target chính |
| Số bước thao tác | 5 | 4 | Loại bỏ hoàn toàn thao tác copy/paste thủ công |
| Trải nghiệm đọc | Bị đứt đoạn, vỡ format | Liền mạch trên 1 file | Giữ nguyên heading, công thức |
| Bottleneck chính | Copy/paste và đối chiếu nguồn | Thời gian xử lý của AI | Cần tối ưu pipeline parse PDF |
| Risk mới | Không có | Dịch sai thuật ngữ chuyên ngành | Cần review/hover xem bản gốc |

## Problem Statement v0

| Field | Nội dung |
| --- | --- |
| **Actor** | Sinh viên, người nghiên cứu AI cần đọc nhiều tài liệu tiếng Anh. |
| **Workflow** | Tìm paper PDF, copy từng đoạn sang công cụ dịch, ghép kết quả, đối chiếu lại bản gốc để xem hình/công thức. |
| **Bottleneck** | Việc dịch thủ công tốn thời gian thao tác và các tool hiện tại phá vỡ hoàn toàn layout, bảng biểu, công thức của bài báo học thuật. |
| **Impact** | Tốc độ research chậm (giảm 50% hiệu suất), người học dễ nản và mất tập trung do mạch đọc bị đứt gãy liên tục. |
| **Success Metric** | Giảm 50% thời gian đọc/xử lý paper; file đầu ra giữ nguyên 90% cấu trúc layout (hình ảnh, công thức, 2 cột) của file gốc. |
| **Boundary** | Chỉ hỗ trợ dịch thuật ngữ/văn bản, không tự động tóm tắt làm sai lệch nội dung gốc. |

## Rule / Workflow / Agent

| Mức | Phương án | Khi nào đủ | Rủi ro | Chọn? |
| --- | --- | --- | --- | --- |
| **Rule** | Dùng Google Translate/DeepL API trực tiếp lên file | Đủ nếu format file đơn giản (Word text thuần) | Vỡ nát layout khi gặp PDF 2 cột, chứa toán học và hình ảnh | Không chọn |
| **Workflow** | Parser bóc tách cấu trúc -> AI Translate text theo văn cảnh -> Reconstructor ghép lại PDF | Hợp lý để giải quyết bài toán layout, các bước rõ ràng tuyến tính | Lỗi bóc tách PDF phức tạp | Chọn |
| **Agent** | Agent tự động đi tìm paper, tự tổng hợp, tự phân tích và sinh ra báo cáo tiếng Việt | Chỉ cần khi muốn AI thay mình làm research | Quá xa với problem ban đầu là "giữ cấu trúc bài báo" | Không chọn |

Mức chọn:

```text
Workflow.

```

Vì sao:

* Bài toán đòi hỏi sự can thiệp chia nhỏ các bước xử lý tài liệu (Parsing -> Translating -> Reconstructing).
* AI chỉ tập trung vào việc dịch nội dung text dựa trên ngữ cảnh chuyên ngành, các bước giữ layout có thể dùng logic phần mềm (Rule).
* Không cần Agent tự quyết định hành động, input và output cực kỳ rõ ràng (PDF in -> PDF out).

## Problem Statement v1

| Field | Nội dung |
| --- | --- |
| **Actor** | Sinh viên AI, nhà nghiên cứu cần tiếp thu nhanh kiến thức từ paper tiếng Anh. |
| **Workflow** | Upload PDF -> AI bóc tách layout -> AI dịch phần text -> Render file PDF tiếng Việt nguyên bản layout -> Người dùng đọc liền mạch. |
| **Bottleneck** | Quá trình đọc đứt gãy do phải tự dịch thủ công, các tool tự động thì phá vỡ công thức/layout. |
| **Impact** | Mất nhiều thời gian đối chiếu bản gốc - bản dịch, giảm tốc độ research đi 50%. |
| **Success Metric** | Giảm 50% thời gian hoàn thành đọc 1 paper; tỷ lệ giữ nguyên hình ảnh, bảng biểu và công thức toán học > 90%. |
| **Boundary** | Hệ thống không tóm tắt hay tự thêm bớt nội dung, tôn trọng 100% nội dung gốc của tác giả. |
| **AI intervention point** | Ở bước xử lý text đã được bóc tách từ PDF: Dịch nội dung theo ngữ cảnh chuyên ngành học thuật. |
| **Mức chọn** | Workflow: OCR/Parser tách layout, AI dịch text, Renderer ghép lại PDF. |
| **Rủi ro & người thật kiểm tra** | Risk: Dịch sai thuật ngữ mới sinh. Người thật kiểm tra: Tích hợp tính năng hover (rê chuột) vào đoạn văn tiếng Việt để xem lại câu tiếng Anh gốc. |

## Final decision

Decision:

```text
Go với scope nhỏ (Workflow).

```

Pilot nhỏ nhất:

* Dùng 3 paper mẫu chuyên ngành AI (có 2 cột, có công thức, có hình ảnh).
* Build workflow: Dùng thư viện bóc tách PDF (vd: Nougat/Marker) -> Đưa text qua Gemini/Claude API kèm prompt chuyên ngành -> Trả về kết quả song ngữ hoặc PDF mới.
* Sinh viên test trải nghiệm đọc trên file output.

Exit / rollback:

* Nếu tỷ lệ vỡ layout (đặc biệt là mất công thức toán) quá 30% trên các paper mẫu, chuyển hướng làm dạng "Song ngữ Side-by-Side" (một nửa màn hình là bản gốc, một nửa là text dịch) thay vì cố tạo ra một file PDF mới hoàn chỉnh.
* Nếu AI dịch quá chậm (> 10 phút cho 1 paper), sẽ phải pre-process và cache hoặc chuyển sang dịch từng trang theo yêu cầu (on-demand reading).

Decision rationale:

* Bài toán giải quyết nỗi đau có thật và cực kỳ phổ biến trong giới sinh viên/research.
* Giải pháp Workflow kết hợp giữa Rule (bóc tách file) và AI (dịch) là rất thực tế.
* Các metric đo lường sự thành công và điểm dừng (fallback) rõ ràng.