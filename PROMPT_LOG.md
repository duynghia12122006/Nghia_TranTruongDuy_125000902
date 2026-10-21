# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)

- **Họ và tên:** Trần Trương Duy Nghĩa
- **MSSV:** BỔ SUNG MSSV TRƯỚC KHI NỘP
- **Tên đề tài Website:** Portfolio cá nhân
- **Công cụ AI đã sử dụng:** ChatGPT

> **Lưu ý:** Bản nhật ký này được tổng hợp từ các yêu cầu trong quá trình xây dựng website. Trước khi nộp, hãy chỉnh sửa phần đánh giá cá nhân và bổ sung kết quả kiểm thử theo đúng những gì bạn đã tự thực hiện.

## 1. Yêu cầu ban đầu (Initial Prompt)

> Tạo website Portfolio cá nhân cho Trần Trương Duy Nghĩa, sinh viên ngành Công nghệ thông tin tại Đại học Lạc Hồng; email liên hệ là duynghia12122006@gmail.com. Website cần có phần giới thiệu, kỹ năng, dự án và liên hệ. Tuân thủ Semantic HTML5 (`header`, `nav`, `main`, `section`, `footer`), khai báo CSS Variables trong `:root`, sử dụng Flexbox hoặc CSS Grid, responsive cho điện thoại, tích hợp Animate.css và AOS, có hiệu ứng `:hover`/`:focus`. Không tự điền MSSV khi chưa được cung cấp.

**Kết quả AI tạo ra:** Phiên bản đầu gồm `index.html`, `style.css`, `PROMPT_LOG.md` và `README.md`. Bố cục đã có điều hướng, giới thiệu, kỹ năng, dự án và liên hệ.

**Nhận xét & tinh chỉnh:** Các dự án mẫu cần được ghi rõ là bài tập/ý tưởng thực hành cho đến khi có sản phẩm và liên kết demo thật.

## 2. Quá trình tinh chỉnh & giải quyết sự cố

### Lần 1: Rà soát yêu cầu JavaScript

- **Yêu cầu tinh chỉnh:** “Trong đề hình như không yêu cầu JS.”
- **Phản hồi và thay đổi:** Đối chiếu lại yêu cầu của đề; bỏ các chức năng JavaScript bổ sung không cần thiết và bỏ file `script.js` riêng. AOS vẫn cần một lệnh `AOS.init()` sau khi nạp thư viện để kích hoạt hiệu ứng cuộn, nên lệnh khởi tạo ngắn được đặt ở cuối `index.html`.
- **Nhận xét cần ghi sau khi kiểm tra:** Mở website và xác nhận các nội dung chính vẫn đọc được; kiểm tra AOS khi có Internet. Nếu không muốn dùng AOS, cần hỏi giảng viên trước khi bỏ vì đề có yêu cầu thư viện này.

### Lần 2: Cá nhân hóa bằng ảnh và phong cách tham khảo

- **Yêu cầu tinh chỉnh:** Sử dụng ảnh chân dung cá nhân, tạo phong cách trang web theo hình minh họa cổ điển công nghệ–thiên nhiên, đồng thời tạo thư mục `assets/` và thêm hình minh họa phù hợp.
- **Thay đổi trong mã nguồn:**
  - Đưa ảnh chân dung vào `assets/duy-nghia-portrait.jpg`.
  - Đưa hình tham khảo phong cảnh vào `assets/nature-tech-landscape.jpg`.
  - Thêm hai hình minh họa mới cho các dự án: `assets/portfolio-workspace.jpg` và `assets/database-notebook.jpg`.
  - Đổi giao diện sang nền giấy ngà, xanh rêu/xanh ngọc và vàng ấm; thêm khung ảnh, chi tiết kiểu in giấy và các thẻ dự án dùng ảnh.
- **Nhận xét & tinh chỉnh của sinh viên:** Kiểm tra ảnh, văn bản thay thế (`alt`), cách cắt ảnh và độ tương phản khi hiển thị trên desktop/điện thoại; có thể thay ảnh nếu muốn dùng tài nguyên khác.

### Lần 3: CSS Variables, Semantic HTML và responsive

- **Prompt tinh chỉnh:** “Rà soát các thẻ semantic, tập trung màu sắc/font/spacing vào CSS Variables, dùng Grid/Flexbox và bảo đảm website không tràn ngang trên màn hình nhỏ. Thêm trạng thái hover/focus dễ nhìn.”
- **Kết quả trong mã nguồn:** `index.html` sử dụng `header`, `nav`, `main`, `section`, `article`, `figure`, `footer`; `style.css` khai báo biến màu/font/khoảng cách trong `:root`, có các media query và trạng thái hover/focus.
- **Kiểm tra nên thực hiện:** Mở trang ở kích thước desktop và điện thoại; kiểm tra menu điều hướng, các nút, tiêu đề dài, thẻ dự án và việc ảnh có bị cắt mất chủ thể hay không.

### Lần 4: Animate.css và AOS

- **Prompt tinh chỉnh:** “Dùng Animate.css cho phần mở đầu, AOS cho các phần nội dung xuất hiện khi cuộn; hiệu ứng nhẹ, không làm cản trở khả năng đọc và hỗ trợ `prefers-reduced-motion`.”
- **Kết quả trong mã nguồn:** `index.html` liên kết Animate.css và AOS; tiêu đề mở đầu dùng các lớp `animate__...`, các section có `data-aos`, và cuối trang gọi `AOS.init()`.
- **Thách thức cần lưu ý:** Hai thư viện và Google Fonts được tải từ CDN, nên hiệu ứng/font có thể không hoạt động nếu thiết bị ngoại tuyến hoặc CDN không tải được. Nội dung chính và ảnh vẫn được lưu cục bộ trong dự án.
- **Cách debug khi AOS không chạy:** Kiểm tra kết nối Internet, đường dẫn AOS CSS/JS và vị trí `AOS.init()`; xác nhận các phần tử có `data-aos`. Không để nội dung chính phụ thuộc hoàn toàn vào hiệu ứng.

## 3. Đánh giá cá nhân về quá trình Vibe Coding

> Hãy sửa các câu dưới đây để thể hiện đúng trải nghiệm của bản thân trước khi nộp.

- **AI giúp tiết kiệm thời gian ở phần nào?** Gợi ý trả lời: AI hỗ trợ dựng bố cục, tạo biến CSS, viết media query và chuẩn bị hình minh họa đồng bộ phong cách. Tôi vẫn cần đọc mã, thử hiển thị và quyết định phần nào phù hợp với yêu cầu bài thi.
- **Bài học về cách viết prompt:** Prompt hiệu quả nên nói rõ mục tiêu, thông tin cá nhân được phép sử dụng, công nghệ bắt buộc, phong cách hình ảnh và giới hạn kỹ thuật. Sau mỗi lần tạo mã, cần kiểm tra kết quả thực tế rồi yêu cầu sửa từng vấn đề cụ thể.
- **Điều cần làm trước khi nộp:** Điền MSSV, tự kiểm tra website, cập nhật nhật ký theo thực tế và bổ sung đường dẫn tới những dự án có sản phẩm demo thật.
