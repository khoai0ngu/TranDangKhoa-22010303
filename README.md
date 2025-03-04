# Website Bán Điện Máy

## Giới thiệu
Dự án website bán điện máy được phát triển nhằm cung cấp nền tảng trực tuyến cho việc mua sắm các sản phẩm điện tử và gia dụng. Hệ thống bao gồm hai phần chính:
- **Trang người dùng:** Cho phép khách hàng xem sản phẩm, thêm vào giỏ hàng và thanh toán.
- **Trang quản trị:** Admin quản lý sản phẩm, đơn hàng, khách hàng và nội dung bài viết.

## Chức năng chính
### 1. Trang người dùng
- **Xem sản phẩm:** Danh sách sản phẩm theo danh mục, xem chi tiết sản phẩm.
- **Giỏ hàng và thanh toán:** Thêm sản phẩm vào giỏ hàng, kiểm tra và thanh toán.
- **Tìm kiếm:** Tìm kiếm sản phẩm theo tên, danh mục, khoảng giá.
- **Liên hệ và hỗ trợ:** Trang liên hệ và phần câu hỏi thường gặp
### 2. Trang quản trị
- **Quản lý sản phẩm:** Thêm, sửa, xóa sản phẩm.
- **Quản lý đơn hàng:** Xem và cập nhật trạng thái đơn hàng.
- **Quản lý khách hàng:** Xem và chỉnh sửa thông tin khách hàng.
- **Quản lý bài viết:** Quản lý nội dung tin tức, bài viết quảng cáo trên trang chủ.

## Cấu trúc thư mục
- `index.php`: Trang chính của người dùng.
- `admin/`: Thư mục chứa giao diện và chức năng của trang quản trị.
- `db/connect.php`: Kết nối cơ sở dữ liệu MySQL.
- `css/`, `js/`, `images/`, `uploads/`: Tài nguyên tĩnh cho giao diện.
- `bandienmay.sql`: Cơ sở dữ liệu mẫu.

## Cơ sở dữ liệu
- **Tệp `bandienmay.sql`**: Bao gồm các bảng chính như:
  - `sanpham`, `danhmuc`: Quản lý thông tin sản phẩm.
  - `khachhang`, `donhang`, `chitietdonhang`: Quản lý đơn hàng và khách hàng.
- **Quan hệ giữa các bảng:**
  - `danhmuc` liên kết với `sanpham`.
  - `donhang` liên kết với `khachhang` và `chitietdonhang`.

## Cài đặt và triển khai
1. **Yêu cầu hệ thống:**
   - XAMPP hoặc WAMP trên Windows.
   - PHP >= 7.4, MySQL.
2. **Các bước cài đặt:**
   - Tạo cơ sở dữ liệu `bandienmay` và import `bandienmay.sql`.
   - Cấu hình kết nối trong `db/connect.php`.
   - Chạy dự án bằng cách truy cập `http://localhost/bdm/`.

## Đánh giá bảo mật
- **Điểm mạnh:**
  - Sử dụng `$_SESSION` để quản lý phiên đăng nhập.
  - Phân quyền người dùng và quản trị viên.
- **Điểm yếu và cải tiến:**
  - **SQL Injection:** Cần sử dụng Prepared Statements.
  - **Mã hóa mật khẩu:** Sử dụng `password_hash()` và `password_verify()`.
  - **Xác thực và phân quyền:** Bổ sung kiểm tra `$_SESSION['role']`.
  - **CSRF:** Thêm CSRF token trên các form quan trọng.

## Đóng góp và phát triển
- Fork dự án, tạo nhánh mới để phát triển tính năng.
- Tạo pull request khi hoàn thành và được kiểm tra lại.

## Giấy phép
Dự án này được phát triển cho mục đích học tập và phi thương mại.

---

© 2025 - Tran Dang Khoa
