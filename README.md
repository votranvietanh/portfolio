# Java Backend Developer — Portfolio

Trang portfolio tĩnh (HTML + CSS + JS thuần, không framework), không cần build, deploy thẳng lên GitHub Pages.

## Cấu trúc

```
portfolio/
├── index.html            # Toàn bộ nội dung (mỗi section có comment)
├── cv.pdf                # CV (thay file này khi cập nhật, giữ nguyên tên)
├── .nojekyll             # Báo GitHub Pages không chạy Jekyll
└── assets/
    ├── css/styles.css    # Style component (card, project, tag...) + màu Light/Dark
    └── js/main.js        # Toggle theme, menu mobile, năm ở footer
```

## Chỉnh nội dung

Mở `index.html`, tìm các comment `HERO SECTION`, `ABOUT ME`, `CORE TECHNICAL EXPERTISE`, `KEY PROJECTS`, `FOOTER / CONTACT` và thay:

- `Your Name`, `your-name` → tên của bạn (cả trong `<title>` và `og:title`)
- `you@example.com`, `+84 900 000 000`, `your-username`, `your-profile` → thông tin liên hệ
- Số liệu trong khối About (`5+ yrs`, `3k TPS`...) và các dự án → số liệu thật
- Thêm dự án: copy một khối `<article class="project">…</article>`
- Sửa CSS xong thì tăng số `?v=` ở thẻ `<link ... styles.css?v=5>` trong `index.html` (vd. `v=6`) để trình duyệt tải file mới thay vì dùng bản cũ.
- Thuộc tính `download="YourName_Java_Backend_CV.pdf"` trên nút Download CV → tên file khi tải về

## Cập nhật CV

1. Chép file CV mới đè lên `cv.pdf` trong thư mục này (**giữ nguyên tên `cv.pdf`**).
2. Đẩy lên GitHub:

   ```bash
   git add cv.pdf
   git commit -m "Update CV"
   git push
   ```

3. Đợi ~1 phút để GitHub Pages build lại. Nếu vẫn tải về bản cũ thì do trình duyệt đang cache: nhấn `Ctrl + F5` hoặc thử cửa sổ ẩn danh.

## Thêm công ty / dự án vào timeline

Trong `index.html`, phần `EXPERIENCE TIMELINE`:
- Thêm công ty: copy một khối `<li class="tl-item">…</li>` (mới nhất đặt trên cùng; công ty hiện tại dùng `tl-dot--current`).
- Thêm dự án trong một công ty: copy một khối `<article class="tl-project">…</article>`.

## Chạy thử local

Mở trực tiếp `index.html` bằng trình duyệt, hoặc:

```bash
python -m http.server 8000
```

rồi vào http://localhost:8000

## Deploy lên GitHub Pages

1. Tạo repo **public** tên `<username>.github.io` (để có URL `https://<username>.github.io`).
   Dùng tên repo khác (vd. `portfolio`) thì URL sẽ là `https://<username>.github.io/portfolio`.
2. Push code:

   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin https://github.com/<username>/<username>.github.io.git
   git push -u origin main
   ```

3. Trên GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, chọn `main` / `/ (root)` → **Save**.
4. Đợi ~1 phút, trang sẽ có tại `https://<username>.github.io`.
