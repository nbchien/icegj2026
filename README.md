# ICEGJ 2026 - Website Hội thảo & Triển lãm Quốc tế về Việc làm Xanh

Website chính thức của **The 1st International Conference and Exhibition on Green Jobs for a Net Zero Future (ICEGJ 2026)**.

- **Thời gian:** 26 – 28 tháng 10 năm 2026
- **Địa điểm:** Đại học Bách khoa Hà Nội (HUST), Hà Nội, Việt Nam
- **Tên miền chính thức:** [www.icegj.org](https://www.icegj.org)

---

## 📌 Tổng quan dự án

Trang web được xây dựng dưới dạng **Static Website (HTML/CSS/JavaScript thuần)**, tối ưu cho tốc độ tải trang cao, tính tương thích di động hoàn hảo và khả năng lưu trữ miễn phí thông qua **GitHub Pages** (kết hợp custom domain).

### Công nghệ sử dụng
- **HTML5 & CSS3** hiện đại, chuẩn ngữ nghĩa (semantic tags).
- **Tailwind CSS (CDN)**: Quản lý giao diện, bố cục responsive và hệ thống màu sắc nhận diện thương hiệu.
- **Font Awesome 6.0**: Bộ icon trực quan.
- **Google Fonts**: Phông chữ `Montserrat` (tiêu đề/heading) và `Poppins` (nội dung/body).
- **Vanilla JavaScript**: Xử lý logic chuyển đổi menu trên thiết bị di động (Mobile responsive hamburger menu).

---

## 📂 Cấu trúc thư mục

```text
icegj2026/
├── index.html                     # Trang chủ (Giới thiệu, Diễn giả, Ban tổ chức, Chủ đề, Địa điểm, Đối tác)
├── exhibition/
│   └── index.html                 # Trang Triển lãm (Thông tin gian hàng, sơ đồ mặt bằng, bảng giá, đăng ký)
├── important-information/
│   └── index.html                 # Trang Mốc thời gian quan trọng (Deadlines nộp bài, thông báo, địa điểm)
├── submissions/
│   └── index.html                 # Trang Hướng dẫn nộp bài (Quy định, mẫu template, cổng nộp EasyChair)
├── registration/
│   └── index.html                 # Trang Đăng ký tham dự (Biểu phí, đối tượng tham dự, tài khoản ngân hàng)
├── program/
│   └── index.html                 # Trang Chương trình hội thảo (Lịch trình chi tiết 3 ngày, phiên báo cáo)
├── directions/
│   └── index.html                 # [Legacy] Trang chỉ dẫn đường đi
├── assets/
│   ├── main.css                   # Tùy biến CSS bổ sung
│   ├── banner.jpg, banner1...     # Hình ảnh banner và hình nền
│   ├── hust.png, sme.png...       # Logo các trường đại học, ban ngành, nhà tài trợ
│   ├── fee.png, topics.png...     # Hình ảnh minh họa bảng phí, chủ đề
│   ├── speakers/                  # Ảnh chân dung các diễn giả chính (Keynote Speakers)
│   │   ├── Ms_ThuyTien.png
│   │   ├── Prof_Byoung.png
│   │   └── ...
│   └── template/                  # Tài liệu mẫu cho tác giả nộp bài
│       ├── Abstract Template.docx # Mẫu tóm tắt bài báo (Abstract)
│       └── Paper Template.docx    # Mẫu bài báo đầy đủ (Full Paper)
├── CNAME                          # Cấu hình Custom Domain (www.icegj.org) cho GitHub Pages
├── sitemap.xml                    # Sơ đồ website phục vụ SEO và Google Search Console
└── README.md                      # Tài liệu hướng dẫn quản trị và phát triển website
```

---

## 💻 Hướng dẫn chạy và xem thử cục bộ (Local Development)

Vì đây là trang web tĩnh, bạn không cần cài đặt các framework phức tạp (như Node.js/PHP/Ruby) để chạy:

### Cách 1: Sử dụng Extension "Live Server" trên Visual Studio Code (Khuyên dùng)
1. Mở thư mục dự án trong VS Code.
2. Cài đặt extension **Live Server** (tác giả *Ritwick Dey*).
3. Nhấp chuột phải vào tệp `index.html` và chọn **Open with Live Server** (hoặc bấm nút `Go Live` ở góc dưới bên phải).

### Cách 2: Sử dụng Python
Nếu máy tính đã cài đặt Python:
```bash
# Di chuyển vào thư mục dự án
cd icegj2026

# Khởi chạy server nội bộ (port 8000)
python -m http.server 8000
```
Mở trình duyệt và truy cập `http://localhost:8000`.

### Cách 3: Sử dụng Node.js (`npx serve`)
```bash
npx serve .
```

---

## 🛠 Hướng dẫn chỉnh sửa & Cập nhật nội dung

### 1. Bảng màu thương hiệu (Brand Theme)
Các trang đều thống nhất cấu hình Tailwind CSS trong thẻ `<script>` ở phần `<head>`:
```javascript
tailwind.config = {
    theme: {
        extend: {
            fontFamily: {
                sans: ['Poppins', 'sans-serif'],
                heading: ['Montserrat', 'sans-serif'],
            },
            colors: {
                brand: {
                    blue: '#1e3a8a',  /* Xanh dương đậm chủ đạo */
                    teal: '#2dd4bf',  /* Xanh ngọc / Mint điểm nhấn */
                    dark: '#0f172a',  /* Xanh đen nền */
                    light: '#f8fafc', /* Trắng xám */
                }
            }
        }
    }
}
```
Nếu muốn thay đổi màu sắc nhận diện, hãy điều chỉnh mã HEX tương ứng trên các trang.

### 2. Cập nhật mốc thời gian quan trọng (Important Dates)
- Mở tệp `important-information/index.html` và phần "Important Dates" trên `index.html`.
- Chỉnh sửa các mốc:
  - Hạn nộp tóm tắt (Abstract Submission)
  - Thông báo chấp nhận (Notification of Acceptance)
  - Hạn nộp bài hoàn chỉnh (Full Paper Deadline)
  - Hạn đăng ký sớm (Early Bird Registration)
  - Ngày diễn ra hội thảo (Conference Dates: 26 - 28/10/2026)

### 3. Cập nhật thông tin diễn giả (Keynote Speakers)
1. Thêm ảnh chân dung vào thư mục `assets/speakers/` (khuyến nghị ảnh vuông, định dạng `.png` hoặc `.jpg`).
2. Mở `index.html`, tìm đến khối `Keynote Speakers`.
3. Cập nhật thông tin: Ảnh, Họ tên, Học hàm/Học vị, Đơn vị công tác, và Tên bài trình bày (Keynote Title).

### 4. Cập nhật biểu phí và tài khoản đăng ký
- Mở tệp `registration/index.html`.
- Cập nhật bảng giá cho từng đối tượng (Tác giả quốc tế/trong nước, Người tham dự, Sinh viên, Early bird vs Regular).
- Cập nhật số tài khoản ngân hàng, tên chủ tài khoản, mã QR chuyển khoản và cú pháp thanh toán.

### 5. Cập nhật tài liệu mẫu nộp bài (Templates)
- Khi có mẫu định dạng bài báo mới, sao chép tệp `.docx` vào thư mục `assets/template/`.
- Kiểm tra đường dẫn liên kết tải xuống tại `submissions/index.html`.

---

## 🚀 Hướng dẫn triển khai (Deployment)

### Triển khai trên GitHub Pages với Custom Domain (`www.icegj.org`)
1. Đẩy mã nguồn lên kho lưu trữ (repository) trên GitHub (nhánh `main` hoặc `master`).
2. Vào **Settings** > **Pages** của repository:
   - **Source:** Chọn `Deploy from a branch`.
   - **Branch:** Chọn `main` (hoặc `master`) và thư mục `/(root)`. Nhấn **Save**.
3. Tại mục **Custom domain**:
   - Nhập `www.icegj.org`.
   - Bật tùy chọn **Enforce HTTPS** (sau khi chứng chỉ SSL được cấp phát xong).
4. Tệp `CNAME` ở thư mục gốc của repository phải chứa đúng dòng:
   ```text
   www.icegj.org
   ```

### Cấu hình DNS tại nhà cung cấp tên miền
- **Bản ghi CNAME**:
  - `Host`: `www`
  - `Points to`: `<your-github-username>.github.io`
- **Bản ghi A (Apex domain cho icegj.org nếu cần chuyển hướng về www)**:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`

---

## 📞 Liên hệ Ban tổ chức

- **Đơn vị chủ trì:** Đại học Bách khoa Hà Nội (HUST)
- **Hỗ trợ kỹ thuật & nội dung:** Ban Thư ký Hội thảo ICEGJ 2026
- **Website:** [https://www.icegj.org](https://www.icegj.org)

## Bản quyền
- MIT