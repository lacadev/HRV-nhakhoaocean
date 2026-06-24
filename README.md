# Hướng dẫn sử dụng Haravan CLI phát triển Theme local

Tài liệu này hướng dẫn chi tiết cách tải và đồng bộ giao diện (theme) Haravan về máy tính cá nhân bằng công cụ **Haravan CLI**.

---

## Các bước thiết lập và tải Theme

### Bước 1: Đăng nhập vào Haravan
Chạy lệnh đăng nhập sau trong terminal:
```bash
haravan login
```
*Trình duyệt web sẽ tự động mở trang đăng nhập để bạn xác thực tài khoản Haravan (yêu cầu tài khoản có quyền quản trị mục Giao diện của cửa hàng).*

### Bước 2: Kiểm tra và chọn Cửa hàng (Organization)
Sau khi đăng nhập thành công, quay lại Terminal kiểm tra danh sách các cửa hàng đã liên kết:
```bash
haravan whoiam
```
*(Lưu ý: Tên lệnh là `whoiam` chứ không phải `whoami`)*

Nếu bạn quản lý nhiều cửa hàng, hãy chọn đúng cửa hàng cần làm việc bằng lệnh:
```bash
haravan select [mã_org_id]
```
*(Ví dụ mã org id của Nhakhoaocean là: `200001188300`)*

### Bước 3: Tải toàn bộ file theme về máy local
Di chuyển terminal đến thư mục dự án trống và chạy lệnh:
```bash
haravan theme fetch [mã_theme_id]
```
*(Ví dụ mã theme id của Smile Clinic là: `1001496275`)*

CLI sẽ tự động tải song song toàn bộ mã nguồn về máy của bạn và sắp xếp theo cấu trúc tiêu chuẩn:
- `/layout`
- `/templates`
- `/snippets`
- `/assets`
- `/config`
- `/locales`

Đồng thời, hệ thống sẽ tự sinh ra file ẩn `.haravan-cli_local.json` dùng để cấu hình kết nối.

---

## Đồng bộ hóa trong quá trình phát triển (Mẹo lập trình)

Khi bắt đầu chỉnh sửa giao diện ở máy local (bằng VS Code...), hãy chạy lệnh:
```bash
haravan theme dev
```
CLI sẽ lắng nghe mọi sự thay đổi file ở local (watch), mỗi khi bạn lưu file (`Ctrl + S`), mã nguồn mới sẽ lập tức được tự động đồng bộ lên Haravan để bạn xem thử trực tiếp trên môi trường online.
