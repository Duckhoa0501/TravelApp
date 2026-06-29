Travel MVC - Hệ Thống Quản Lý Du Lịch
Đây là ứng dụng Website Quản lý và Đặt Tour Du Lịch được xây dựng dựa trên nền tảng ASP.NET Core MVC. Hệ thống cung cấp trải nghiệm đặt tour dễ dàng cho khách hàng và bộ công cụ quản trị (Dashboard) trực quan dành cho doanh nghiệp lữ hành.

🚀 Các tính năng nổi bật
👤 Dành cho Khách hàng (Client-side)
Tìm kiếm & Lọc Tour: Tìm kiếm điểm đến, lọc theo giá và sắp xếp tour dễ dàng.
Xem chi tiết: Hiển thị thông tin lịch trình, hình ảnh và giá cả minh bạch.
Đặt Tour (Booking): Giao diện đặt chỗ nhanh chóng, dễ thao tác.
Quản lý Tài khoản: Đăng ký, đăng nhập an toàn với mật khẩu mã hóa (BCrypt).
Quản lý Đơn hàng: Theo dõi lịch sử đặt tour cá nhân.
🛡 Dành cho Quản trị viên (Admin-side)
Bảng điều khiển (Dashboard): Thống kê doanh thu, đơn hàng, người dùng trực quan.
Quản lý Tour: Thêm, sửa, xóa, và ẩn/hiện các chuyến đi.
Quản lý Đơn hàng: Cập nhật trạng thái duyệt đơn.
Quản lý Người dùng: Phân quyền và theo dõi tài khoản khách hàng.
🛠 Công nghệ sử dụng (Tech Stack)
Backend: C# / ASP.NET Core MVC
Cơ sở dữ liệu: Microsoft SQL Server (tương tác qua Entity Framework Core - Code First)
Frontend: HTML5, CSS3, JavaScript
Bảo mật: Mã hóa mật khẩu chuẩn BCrypt
⚙️ Hướng dẫn cài đặt và Chạy dự án (Local Setup)
Yêu cầu hệ thống (Prerequisites)
Visual Studio 2022 (Khuyên dùng)
.NET Core SDK
SQL Server Management Studio (SSMS) hoặc SQL Server LocalDB.
Các bước cài đặt
Bước 1: Mở mã nguồn Giải nén thư mục dự án và mở tệp giải pháp (File có đuôi .sln) bằng Visual Studio.

Bước 2: Cấu hình chuỗi kết nối (Connection String) Mở file appsettings.json nằm ở thư mục gốc của dự án. Sửa đổi mục DefaultConnection sao cho trỏ đúng vào tên Server SQL trên máy của bạn:

json

"ConnectionStrings": {
  "DefaultConnection": "Server=TEN_SERVER_CUA_BAN;Database=TravelDB;Trusted_Connection=True;MultipleActiveResultSets=true;Encrypt=False"
}
(Nếu dùng LocalDB mặc định của Visual Studio, bạn có thể giữ nguyên).

Bước 3: Khởi tạo Cơ sở dữ liệu (Database Migration) Mở cửa sổ Package Manager Console (Vào Tools > NuGet Package Manager > Package Manager Console) và chạy lệnh sau để tự động tạo Database cùng các bảng dữ liệu:

powershell

Update-Database
Bước 4: Chạy ứng dụng Nhấn F5 hoặc nút Start (mũi tên xanh lá) trên thanh công cụ của Visual Studio để biên dịch và chạy dự án. Trình duyệt sẽ tự động mở trang chủ tại địa chỉ https://localhost:<port>.

📖 Hướng dẫn sử dụng luồng nghiệp vụ
Trải nghiệm khách hàng:
Tại trang chủ, bạn có thể gõ từ khóa vào thanh tìm kiếm để tìm điểm đến.
Nhấp vào bất kỳ Tour nào, đọc chi tiết lịch trình và chọn "Đặt ngay".
Bạn cần điền thông tin cá nhân và số lượng người đi để hoàn tất quy trình giả lập thanh toán.
Trải nghiệm Quản trị viên (Admin):
Truy cập đường dẫn /Admin hoặc bấm nút Đăng nhập nội bộ.
Sử dụng tài khoản có quyền Admin để vào xem Bảng điều khiển (Dashboard).
Tại đây bạn có thể kiểm duyệt các đơn mà khách vừa đặt hoặc thêm mới một tour du lịch để nó hiển thị ra ngoài trang chủ.
