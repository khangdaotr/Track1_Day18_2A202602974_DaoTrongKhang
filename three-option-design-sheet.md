# Three Option Design Sheet — Day 19

## 1. Bối cảnh thiết kế

Người học đang theo dõi bài giảng bằng slide nhưng gặp một phần kiến thức chưa hiểu. Nếu phải chuyển sang công cụ khác, chụp màn hình hoặc tự mô tả lại toàn bộ ngữ cảnh, luồng học sẽ bị gián đoạn. Ba prototype dưới đây cùng hướng đến việc hỗ trợ người học ngay trong bài giảng, nhưng khác nhau về người khởi tạo hỗ trợ và cách xác định nội dung cần giải thích.

## 2. Tổng quan ba phương án

| Phương án | Người phụ trách | Cơ chế chính | Người khởi tạo hỗ trợ |
|---|---|---|---|
| **Option A — Gợi ý mở rộng theo nhu cầu** | Nguyễn Tiến Phát | Bấm trực tiếp vào thuật ngữ hoặc phần chữ trên slide để mở giải thích. | Người học |
| **Option B — Chẩn đoán khó khăn và hỗ trợ chủ động** | Đào Trọng Khang | Hệ thống tự hiển thị câu hỏi kiểm tra và đưa ra hỗ trợ dựa trên lựa chọn của người học. | AI/hệ thống |
| **Option C — Giải thích nội dung do người học lựa chọn (C2)** | Đỗ Trọng Bình | Kéo chuột khoanh vùng nội dung, xem trước vùng chọn và yêu cầu AI giải thích. | Người học |

## 3. Mô tả chi tiết

### Option A — Gợi ý mở rộng theo nhu cầu

**Ý tưởng**

Người học chủ động chọn một thuật ngữ hoặc phần nội dung chưa rõ ngay trên slide. Những vị trí có thể tương tác được thể hiện qua hiệu ứng khi di chuột. Khi bấm vào nội dung, một cửa sổ nhỏ xuất hiện gần vị trí đã chọn và cung cấp phần giải thích liên quan.

**Luồng tương tác**

1. Người học đọc slide và di chuột qua các nội dung.
2. Hệ thống làm nổi bật thuật ngữ có thể tương tác.
3. Người học bấm vào phần muốn tìm hiểu thêm.
4. Cửa sổ giải thích hiển thị nội dung liên quan ngay trên slide.
5. Người học đóng cửa sổ hoặc chọn thuật ngữ khác để tiếp tục.

**Giá trị chính**

- Thao tác đơn giản và dễ làm quen.
- Nội dung hỗ trợ xuất hiện đúng vị trí người học đang chú ý.
- Người học quyết định khi nào cần mở thêm thông tin nên ít bị gián đoạn ngoài ý muốn.

**Đánh đổi**

- Người học phải tự nhận ra mình chưa hiểu phần nào và chủ động bấm vào đúng nội dung.
- Chỉ những vị trí đã được thiết kế sẵn mới có thể mở giải thích.
- Nội dung lý thuyết cần được rà soát kỹ để tránh cung cấp giải thích chưa chính xác.

**Prototype:** [option-a.html](prototypes/prototype_phat/prototype/option-a.html)

### Option B — Chẩn đoán khó khăn và hỗ trợ chủ động

**Ý tưởng**

Hệ thống theo dõi thời gian người học dừng tại nội dung và chủ động hiển thị câu hỏi kiểm tra. Thay vì yêu cầu người học tự viết câu hỏi, AI đưa ra các lựa chọn ngắn để xác định mức độ hiểu hoặc phần kiến thức còn chưa rõ, sau đó mở nội dung giải thích phù hợp.

**Ba biến thể đã thiết kế**

- **B1 — Binary Check:** hỏi người học đã hiểu hay chưa.
- **B2 — Confidence Check:** hỏi mức độ chắc chắn gồm hiểu rõ, chưa chắc và chưa hiểu.
- **B3 — Guided Check:** cho người học chọn cụ thể phần kiến thức mình chưa hiểu. Đây là biến thể chính được sử dụng trong prototype.

**Luồng tương tác của B3**

1. Người học đọc slide Double Diamond.
2. Sau một khoảng thời gian chờ, popup Guided Check tự động xuất hiện.
3. Người học chọn trạng thái hiểu bài hoặc phần kiến thức chưa rõ.
4. Nếu người học chọn chưa hiểu hoặc chưa chắc, hệ thống hiển thị phần giải thích tương ứng.
5. Người học xác nhận đã hiểu và tiếp tục bài học.

**Giá trị chính**

- Hỗ trợ cả khi người học chưa biết cách đặt câu hỏi.
- Câu hỏi ngắn giúp xác định nhanh nội dung cần giải thích.
- Ghi chú kiến thức và ví dụ trực quan có thể giúp người học tiếp tục bài học mà không chuyển sang công cụ khác.

**Đánh đổi**

- Popup xuất hiện không đúng thời điểm có thể làm gián đoạn sự tập trung.
- Người học có thể mong muốn tự gọi hỗ trợ thay vì chờ hệ thống.
- Cơ chế chẩn đoán cần ghi nhớ phần kiến thức đã hiểu để tránh hỏi lặp lại.

**Prototype:** [prototype_khang.html](prototypes/prototype_khang.html) · [Bản trực tuyến](https://option-b-ai-tutor-khang.daotrongkhang072.chatgpt.site)

### Option C — Giải thích nội dung do người học lựa chọn, biến thể C2

**Ý tưởng**

Người học tự xác định chính xác nội dung chưa hiểu bằng cách kéo chuột khoanh vùng trên slide. Hệ thống tạo ảnh xem trước của vùng đã chọn; người học có thể nhập thêm câu hỏi hoặc gửi ngay để nhận phần giải thích chung.

**Luồng tương tác**

1. Người học kéo chuột để tạo khung quanh phần sơ đồ hoặc nội dung cần hỏi.
2. Panel trợ lý hiển thị ảnh xem trước của vùng đã khoanh.
3. Người học kiểm tra vùng chọn và có thể nhập thêm yêu cầu, chẳng hạn xin ví dụ hoặc hỏi sâu về một giai đoạn.
4. Người học bấm **Giải thích phần đã chọn**.
5. Hệ thống hiển thị phần giải thích, ví dụ và ý chính; người học có thể sửa yêu cầu, đổi vùng chọn hoặc tiếp tục bài học.

**Giá trị chính**

- Người học kiểm soát chính xác phạm vi cần giải thích.
- Có thể sử dụng với sơ đồ, hình ảnh hoặc bảng mà thao tác chọn văn bản không xử lý tốt.
- Cho phép đặt câu hỏi chi tiết hoặc nhận giải thích chung nếu không nhập thêm nội dung.

**Đánh đổi**

- Kéo và khoanh vùng cần nhiều thao tác hơn, có thể khó làm quen ở lần đầu.
- Vùng chọn trong prototype còn giới hạn và có thể không bao phủ toàn bộ hình ảnh mong muốn.
- Người học phải chủ động xác định nội dung; việc nhập thêm câu hỏi làm tăng công sức tương tác.
- Prototype dùng câu trả lời dựng sẵn, chưa thực hiện OCR hoặc phân tích ảnh thật.

**Prototype:** [prototype-c2-region.html](prototypes/prototype_binh/prototype-c2-region.html)

## 4. So sánh thiết kế

| Tiêu chí | Option A | Option B | Option C2 |
|---|---|---|---|
| **Thời điểm hỗ trợ** | Khi người học bấm vào nội dung | Hệ thống chủ động sau một khoảng chờ | Khi người học hoàn tất chọn vùng |
| **Cách xác định nội dung** | Chọn thuật ngữ đã được gắn tương tác | Trả lời câu hỏi chẩn đoán | Tự khoanh vùng và có thể nhập câu hỏi |
| **Mức độ chủ động của người học** | Cao | Trung bình | Rất cao |
| **Số thao tác ban đầu** | Ít | Ít, nhưng phải chờ popup | Nhiều hơn |
| **Khả năng xử lý hình ảnh/sơ đồ** | Hạn chế ở nội dung được gắn sẵn | Dựa trên các lựa chọn chẩn đoán có sẵn | Phù hợp nhất trong ba phương án |
| **Rủi ro chính** | Người học không nhận ra vùng có thể bấm | Can thiệp sai thời điểm | Khó thao tác và chọn vùng chưa chính xác |

## 5. Giả thuyết cần kiểm thử

- **Option A:** Nếu nội dung tương tác dễ nhận biết, người học có thể tự mở giải thích nhanh mà không bị gián đoạn.
- **Option B:** Nếu hệ thống hỏi đúng lúc và loại bỏ những phần người học đã hiểu, hỗ trợ chủ động sẽ giúp người học tiếp tục bài học mà không cần tự soạn câu hỏi.
- **Option C2:** Nếu thao tác khoanh vùng chính xác và dễ sử dụng, người học sẽ chấp nhận thêm thao tác để đổi lấy quyền kiểm soát phạm vi cần giải thích.
