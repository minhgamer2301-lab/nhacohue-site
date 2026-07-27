# nhacohue.com

Trang tĩnh của **Nhà Cô Huệ** — Bún Đậu & Bánh Xèo, Cư xá Phú Lâm B, P. Phú Lâm, TP.HCM.
Một trang, không JavaScript, không phụ thuộc host ngoài (font tự chứa trong `fonts/`).

Host: Cloudflare Pages, gói free, deploy tự động mỗi lần push nhánh chính.

## ⚠️ Đừng sửa thẳng trong repo này

Toàn bộ nội dung được **sinh ra** từ vault Amadeus (repo private, khác repo này). Sửa ở đây thì
lần build sau sẽ ghi đè, và vault với web sẽ thành hai nguồn khác nhau.

| Muốn đổi gì | Sửa file nào trong vault |
|---|---|
| Giá, giờ mở, câu chữ | `_project/CoHue/website/content-v1.md` (SSOT chữ) rồi chép sang template |
| Bố cục, màu, CSS | `_project/CoHue/_brand/web/landing-template.html` (SSOT giao diện) |
| Ảnh nào lên trang | bảng `ANH` trong `_project/CoHue/_brand/web/build_site.py` |
| Tên miền, mô tả, JSON-LD | hằng số đầu `build_site.py` |

Rồi chạy trong vault:

```bash
python _project/CoHue/_brand/web/build_site.py
```

Script ghi đè `index.html`, `style.css`, `img/`, `fonts/`, favicon trong thư mục này. Xem lại
bằng `git diff`, ưng thì commit + push, Pages tự deploy.

## Có gì trong đây

```
index.html    trang chủ — sinh tự động
thuc-don.html bảng giá hai quán; món có ảnh thì bấm tên là ảnh mở ra (không JS)
chuyen-quan*  trang danh sách blog quán + một file cho mỗi bài
style.css     font brand + toàn bộ CSS — sinh tự động
img/          21 ảnh webp, đặt tên theo món
fonts/        6 subset woff2 (Be Vietnam Pro + Oswald, latin + vietnamese)
og-*.jpg      ảnh hiện khi chia sẻ link lên Facebook/Zalo (để JPEG, nhiều nơi không đọc webp)
favicon-*.png icon tab trình duyệt
```

## Blog quán

Đã mở 27/07 với bài đầu tiên (chữ nằm ở `website/blog/*.md` trong vault, không nằm trong HTML).
Khi kho bài dày lên **bốn năm bài** thì tính chuyện chuyển sang Astro —
cấu trúc hiện tại port sang được, `style.css` dùng lại nguyên, không phải viết lại chữ.
Blog quán do vai Marketer viết (bán hàng cho quán), khác blog hành trình Amadeus — hai thứ,
hai tên miền.
