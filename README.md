# Java Backend Developer — Portfolio

Trang portfolio tĩnh (HTML + Tailwind CDN + JS thuần), không cần build, deploy thẳng lên GitHub Pages.

## Cấu trúc

```
portfolio/
├── index.html            # Toàn bộ nội dung (mỗi section có comment)
├── cv.pdf                # CV mẫu — thay bằng CV thật (giữ nguyên tên file)
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
- Thuộc tính `download="YourName_Java_Backend_CV.pdf"` trên nút Download CV → tên file khi tải về

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
