# Hướng dẫn cài web commission có trang chỉnh sửa (/admin)

Làm 1 lần trên máy tính (khoảng 30-60 phút). Sau đó sửa giá/up ảnh bằng điện thoại ở `ten-web.netlify.app/admin`.
Tên các mục trong GitHub/Netlify có thể khác chút so với bên dưới vì họ hay đổi giao diện.

## Bước 1: Đưa code lên GitHub
1. Tạo tài khoản github.com (nếu chưa có).
2. Bấm New repository, đặt tên (ví dụ `commission-web`), chọn Public hoặc Private, bấm Create.
3. Bấm "uploading an existing file", giải nén file zip rồi kéo thả TOÀN BỘ thư mục/tệp bên trong (index.html, admin, content, images) vào. Bấm Commit changes.

## Bước 2: Sửa tên repo trong admin/config.yml
Mở file admin/config.yml trên GitHub, bấm biểu tượng cây bút, đổi dòng `repo:` thành `tên-github-của-bạn/tên-repo`, rồi Commit.

## Bước 3: Đưa web lên Netlify
1. Vào netlify.com, đăng ký bằng tài khoản GitHub.
2. Add new site > Import an existing project > GitHub > chọn repo.
3. Build command để trống, Publish directory để trống hoặc `.`, bấm Deploy. Xong sẽ có link `xxx.netlify.app`.

## Bước 4: Cho phép đăng nhập admin bằng GitHub
1. GitHub > Settings > Developer settings > OAuth Apps > New OAuth App.
   - Homepage URL: link Netlify của bạn.
   - Authorization callback URL: `https://api.netlify.com/auth/done`
2. Tạo xong, copy Client ID, bấm Generate a new client secret và copy secret.
3. Netlify > site của bạn > Site configuration > Access control > OAuth (Authentication providers) > Install provider > GitHub, dán Client ID và Secret.

## Bước 5: Dùng
Vào `link-netlify/admin`, bấm Login with GitHub, chọn "Bảng giá" hoặc "Gallery sample", sửa rồi bấm Publish. Khoảng 1 phút sau web tự cập nhật.
- Chỉ người có quyền ghi repo (tức bạn) mới đăng nhập được.
- Nên nén ảnh còn khoảng 300-800 KB trước khi up.

## Muốn sửa chữ (giới thiệu, ToS)
Phần này nằm trong index.html, nhờ Claude sửa rồi thay file trên GitHub (Add file > Upload files, upload đè).
