# 03 — Individual Reflection Example

## Đóng góp của Bách trong nhóm

| Hoạt động | Bách đã làm gì? | Kết quả |
|---|---|---|
| Scan cá nhân | Đưa ra 10 problems đa dạng (học thuật, quản lý dự án, PTKT, đời sống) | Nhóm có nguồn ý tưởng phong phú để phân tích, đặc biệt là mảng học thuật |
| Pitch | Pitch bài toán "Đọc Paper AI" ở bước cá nhân | Bài toán được chọn làm nền tảng và sau đó phát triển, sắc nét hơn thành "Dịch paper giữ cấu trúc" |
| Challenge | Đặt vấn đề về việc AI tóm tắt dễ làm mất chi tiết và phá nát công thức toán/bảng biểu khi dịch PDF | Nhóm xác định đúng bottleneck cốt lõi không chỉ là dịch ngôn ngữ, mà là bảo toàn layout học thuật |
| Workflow | Vẽ current/future workflow cho bài toán đọc paper gốc | Nhóm làm rõ được "đứt gãy mạch đọc" nằm ở bước copy/paste và liên tục đối chiếu file gốc - file dịch |
| Research | Đánh giá trực tiếp các công cụ đang có như DeepL, ChatPDF, Google Translate | Chỉ ra khoảng trống thị trường: các tool này dịch tốt nhưng chưa giữ được format PDF 2 cột phức tạp |
| Rule / Workflow / Agent | Lập luận chia nhỏ giải pháp thành Workflow (Parser bóc tách -> AI Translate -> Reconstructor) | Nhóm thống nhất không làm Agent dư thừa, ưu tiên luồng xử lý tài liệu tuyến tính, rõ ràng |

## Bảng dùng AI trong reflection

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hời hợt ở đâu? | Tôi sửa gì |
|---|---|---|---|---|
| Scan | Nhờ AI gợi ý pain point thực tế của sinh viên/người làm nghiên cứu | Mở rộng góc nhìn về các thao tác lặp lại (ví dụ lọc email alert mỗi sáng) | Đề xuất giải pháp quá sớm (vd: "làm chatbot đọc paper") thay vì xoáy sâu vào problem | Gạt bỏ các ý tưởng thiên về solution, tập trung làm rõ actor và current workflow |
| Workflow | Phác thảo luồng thao tác của người dùng khi gặp file PDF ngoại ngữ | Liệt kê hệ thống các bước tải, đọc lướt, tra từ điển | AI gộp chung bước dịch và đối chiếu lại bản gốc làm một | Tự tách rõ bottleneck là quá trình copy/paste thủ công và đảo mắt giữa 2 văn bản |
| Research | Tìm các công cụ AI hỗ trợ dịch thuật tài liệu giữ nguyên định dạng | List ra được nhiều tool đa dạng ngoài thị trường như SciSpace | AI khen các tool này giữ format hoàn hảo theo quảng cáo | Tự đưa paper thực tế vào test và nhận ra bảng biểu, phương trình vẫn bị vỡ |
| Problem Statement | Tinh chỉnh lại các field cho gãy gọn, đúng văn phong PM | Viết phần Impact và Success Metric rất sắc sảo | Gợi ý đẩy scope lên thành "Agent tự động research và viết báo cáo" | Kéo lại scope về Workflow: cam kết chỉ dịch văn bản và giữ nguyên 100% nội dung gốc |

## Bài học của Bách

- Problem có giá trị nhất nhiều khi không phải là tạo ra một thứ gì đó quá vĩ mô, mà chỉ đơn giản là giải quyết triệt để những "việc chân tay số" (copy/paste, đối chiếu hai màn hình) gây đứt gãy sự tập trung của người dùng.
- Việc phân tách rõ ràng giữa Rule và AI là chìa khóa trong xử lý tài liệu. Bóc tách layout PDF (Heading, Image, Math) là nhiệm vụ của Rule/Parser; hiểu ngữ cảnh chuyên sâu để dịch mượt mà mới là vùng đất để AI (LLM) tỏa sáng.
- Metric thời gian (giảm từ 120 phút xuống 60 phút) bắt buộc phải đi kèm với metric chất lượng (giữ nguyên >90% layout). Nếu tốc độ nhanh mà nát format thì giải pháp trở nên vô dụng với dân kỹ thuật.

Nếu làm lại:
> Thay vì chỉ giả định bước bóc tách dữ liệu (Parser) sẽ hoạt động trơn tru, tôi sẽ lấy trực tiếp các paper có layout cực kỳ phức tạp — ví dụ như các bài báo nghiên cứu kiến trúc Mixture-of-Experts (MoE) hay các bài về Vision-Language Models phân tích ảnh Chest X-Ray — để test thử khả năng nhận diện công thức và hình ảnh ngay từ phase Research. Việc đối diện với dữ liệu khó từ sớm sẽ giúp pilot thực tế hơn và quản lý rủi ro tốt hơn.