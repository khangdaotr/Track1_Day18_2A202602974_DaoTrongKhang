# Track 1 — Day 18

## 1. Thông tin cá nhân và nhóm

| Thông tin | Chi tiết |
|---|---|
| Mã học viên | 2A202602974 |
| Họ và tên | Đào Trọng Khang |
| Tên nhóm | ThreeWhites |
| Số thành viên | 3 |
| Thành viên 1 | Đào Trọng Khang — MHV: 2A202602974 |
| Thành viên 2 | Nguyễn Tiến Phát — MHV: 2A202602387 |
| Thành viên 3 | Đỗ Trọng Bình — MHV: 2A202602855 |
| Case đã chọn | Case A — AI Tutor: Diagnostic Refresher |

## 2. Hypothesis Problem
Khi đang học (trên lớp hoặc trực tuyến) và gặp phần chưa hiểu trong lúc bài giảng vẫn tiếp tục, học viên gặp khó khăn trong việc làm rõ phần đó ngay trong ngữ cảnh bài học vì phải rời luồng bài sang công cụ bên ngoài (chụp màn hình, chuyển tab, tự mô tả lại ngữ cảnh) hoặc ghi lại để xem sau. Quá trình này làm mất thêm thời gian và trì hoãn việc làm rõ, khiến những kiến thức chưa hiểu dần tích tụ, tạo thành các lỗ hổng kiến thức và lâu dài làm chậm tiến độ học các bài tiếp theo.
## 3. Three Solution Options

### Option A — Gợi ý mở rộng theo nhu cầu

Hệ thống cung cấp nút gợi ý để người học chủ động yêu cầu thêm ví dụ hoặc một cách diễn đạt khác. Nội dung chỉ được mở khi người học lựa chọn và được AI tạo dựa trên kiến thức, ngữ cảnh học tập có sẵn.

### Option B — Chẩn đoán khó khăn và hỗ trợ chủ động

AI nhận diện những nội dung mà người học dừng lại lâu hoặc có dấu hiệu gặp khó khăn, từ đó chủ động đưa ra câu hỏi gợi mở và đề xuất hỗ trợ phù hợp để giúp người học tiếp tục bài học.

### Option C — Giải thích nội dung do người học lựa chọn

Người học chủ động đánh dấu văn bản hoặc chụp ảnh màn hình phần chưa hiểu, sau đó yêu cầu AI giải thích. AI phân tích nội dung được chọn và trả lời câu hỏi theo đúng ngữ cảnh.

## 4. Đóng góp của tôi trong nhóm

Tôi phụ trách phát triển **Option B — Chẩn đoán khó khăn và hỗ trợ chủ động**. Các công việc chính gồm:

- Xây dựng ý tưởng để AI nhận diện dấu hiệu người học gặp khó khăn và chủ động hỗ trợ mà không yêu cầu người học rời khỏi bài giảng.
- Thiết kế ba biến thể tương tác gồm **B1 — Binary Check**, **B2 — Confidence Check** và **B3 — Guided Check** nhằm so sánh các cách đặt câu hỏi hỗ trợ.
- Xây dựng prototype mô phỏng luồng học: AI hiển thị câu hỏi kiểm tra sau một khoảng thời gian, xác định phần kiến thức người học chưa hiểu và cung cấp nội dung giải thích phù hợp.
- Hoàn thiện **B3 — Guided Check** thành phương án chính với giao diện toàn màn hình và nội dung minh họa về mô hình Double Diamond.
- Tham gia kiểm thử prototype, ghi nhận phản hồi của người dùng và đề xuất cải tiến thời điểm hiển thị thông báo cũng như cách loại bỏ các đáp án liên quan đến kiến thức người học đã nắm vững.

## 5. Prototype Feedback

### 5.1. Thông tin phiên kiểm thử

**Người trải nghiệm:** Linh  
**Mục tiêu:** So sánh ba phương án hỗ trợ người học khi gặp nội dung chưa hiểu trong bài giảng và xác định phương án mang lại trải nghiệm phù hợp nhất.

Linh lần lượt trải nghiệm Option A, B và C. Phản hồi được ghi nhận dựa trên nhận xét và hành vi quan sát trong phiên thử, không phải lời trích dẫn nguyên văn.

### 5.2. Kết quả quan sát

| Phương án | Điểm tích cực | Hạn chế được ghi nhận |
|---|---|---|
| **Option A — Gợi ý mở rộng theo nhu cầu** | Linh nhanh chóng hiểu thao tác cần thực hiện và không mất nhiều thời gian làm quen. | Một số nội dung lý thuyết chưa chính xác và cần được rà soát lại. |
| **Option B — Chẩn đoán khó khăn và hỗ trợ chủ động** | Câu hỏi dễ nắm bắt, có ghi chú kiến thức quan trọng và ví dụ trực quan. Linh tích cực thao tác và có biểu hiện đồng tình qua việc gật đầu. | Thông báo hỗ trợ xuất hiện khá sớm, có thể làm gián đoạn lúc người học vẫn đang đọc bài. |
| **Option C — Giải thích nội dung do người học lựa chọn** | Sau khi hiểu cách sử dụng, Linh nhận thấy thao tác khoanh vùng có thể đáp ứng nhu cầu chọn phần kiến thức cần hỏi. | Thao tác kéo, thả ban đầu khó làm quen; người học vẫn phải nhập nội dung muốn hỏi. Tương tác chủ yếu qua nút bấm, nội dung chưa được phân nhỏ và vùng lựa chọn còn giới hạn. |

### 5.3. Lựa chọn của người trải nghiệm

Linh lựa chọn **Option B — Chẩn đoán khó khăn và hỗ trợ chủ động**. Phương án này giúp người học tiếp cận hỗ trợ mà không cần tự hình thành một câu hỏi hoàn chỉnh ngay từ đầu. Câu hỏi ngắn, phần kiến thức trọng tâm và ví dụ minh họa cũng giúp quá trình tương tác dễ theo dõi hơn.

Biểu hiện tích cực của Linh cho thấy Option B tạo được sự hứng thú trong phiên thử. Tuy nhiên, việc gật đầu hoặc thao tác thuận lợi chưa đủ để khẳng định người học đã hiểu và ghi nhớ kiến thức.

### 5.4. Thay đổi ở vòng tiếp theo

Phiên bản tiếp theo sẽ ưu tiên điều chỉnh thời điểm can thiệp và làm cho chuỗi câu hỏi thích ứng với mức độ hiểu của người học:

1. Kéo dài thời gian chờ trước khi hiển thị thông báo và thử nghiệm nhiều mốc thời gian khác nhau.
2. Cho phép người học hoãn hoặc đóng thông báo nếu họ vẫn đang tập trung đọc bài.
3. Ghi nhận câu trả lời ở từng bước; khi người học xác nhận đã hiểu một phần kiến thức, hệ thống sẽ loại bỏ nội dung đó khỏi các lựa chọn tiếp theo.
4. Giữ cách trình bày câu hỏi ngắn, ghi chú kiến thức quan trọng và ví dụ trực quan.
5. Trong lần thử tiếp theo, ghi nhận thời gian phản hồi, số lần đóng thông báo và kết quả của một câu hỏi kiến thức ngắn sau khi người học nhận hỗ trợ.

### 5.5. Những điểm chưa được kiểm chứng

- Chưa xác định được thời điểm tối ưu để hệ thống chủ động hiển thị thông báo.
- Phản hồi của Linh chưa thể đại diện cho toàn bộ người học.
- Chưa có dữ liệu chứng minh Option B giúp người học hiểu bài hoặc ghi nhớ tốt hơn hai phương án còn lại.
- Hiệu quả của cơ chế loại bỏ những đáp án liên quan đến phần kiến thức đã hiểu cần được kiểm thử trong phiên bản tiếp theo.

## 6. AI Support Log

Trong quá trình thực hiện Option B, tôi sử dụng AI như một công cụ hỗ trợ ở các công việc sau:

| Công việc | Cách AI hỗ trợ | Kết quả và điều chỉnh của tôi |
|---|---|---|
| Phát triển ý tưởng | Gợi ý các cách AI có thể chủ động kiểm tra mức độ hiểu bài của người học. | Tôi lựa chọn và phát triển ba biến thể B1, B2 và B3 để kiểm thử. |
| Thiết kế luồng tương tác | Hỗ trợ xây dựng trình tự từ lúc người học xem bài, nhận câu hỏi kiểm tra đến khi được giải thích thêm. | Tôi điều chỉnh luồng để sự hỗ trợ diễn ra ngay trong bài học và không yêu cầu chuyển sang công cụ khác. |
| Xây dựng prototype | Hỗ trợ tạo cấu trúc giao diện, nội dung câu hỏi và logic hiển thị cửa sổ thông báo. | Tôi kiểm tra, chỉnh sửa nội dung, thời gian xuất hiện và hoàn thiện B3 thành prototype chính. |
| Chuẩn hóa nội dung | Hỗ trợ diễn đạt câu hỏi, phần giải thích và ghi chú kiến thức theo hướng ngắn gọn, dễ hiểu. | Tôi rà soát lại độ chính xác, ngữ cảnh và mức độ phù hợp với người học. |
| Tổng hợp phản hồi | Hỗ trợ nhóm các nhận xét sau kiểm thử và diễn đạt lại thành các điểm mạnh, hạn chế và hướng cải tiến. | Tôi lựa chọn các thay đổi ưu tiên cho phiên bản tiếp theo. |

AI chỉ đóng vai trò hỗ trợ đề xuất và diễn đạt. Tôi trực tiếp lựa chọn phương án, kiểm tra nội dung, điều chỉnh prototype và chịu trách nhiệm đối với sản phẩm cuối cùng.
