# HƯỚNG DẪN CÀI ĐẶT WEBSITE BÁN LAPTOP

## 1. Yêu cầu môi trường

Trước khi chạy project, cần cài đặt các công cụ sau:

- **Visual Studio 2022**
- **.NET SDK** phù hợp với project ASP.NET Core MVC
- **SQL Server**
- **SQL Server Management Studio (SSMS)**

---

## 2. Clone source code

Tải project từ GitHub về máy bằng lệnh:

```bash
git clone <repository-url>
```

Sau đó mở thư mục project.

---

## 3. Mở project trong Visual Studio

- Vào thư mục `src/`
- Mở file solution:

```text
ecommerce-asp.sln
```

- Chờ Visual Studio restore các package cần thiết

---

## 4. Tạo cơ sở dữ liệu

Có 2 cách để tạo cơ sở dữ liệu:

### Cách 1: Chạy file SQL

Mở **SQL Server Management Studio (SSMS)** và thực hiện:

- Tạo database mới, ví dụ:

```sql
CREATE DATABASE LaptopStore;
```

- Chọn database vừa tạo
- Chạy các file SQL trong thư mục `setup/`, ví dụ:
  - `create-database.sql`
  - `sample-data.sql`

### Cách 2: Dùng Entity Framework Core Migration

Nếu project đã có migration, mở **Package Manager Console** và chạy:

```powershell
Update-Database
```

Nếu chưa có database, hệ thống sẽ tự tạo các bảng cần thiết.

---

## 5. Cấu hình chuỗi kết nối

Mở file:

```text
src/ecommerce-asp/appsettings.json
```

Tìm phần `ConnectionStrings` và chỉnh sửa lại cho phù hợp với máy của bạn:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=.;Database=LaptopStore;Trusted_Connection=True;TrustServerCertificate=True"
}
```

Trong đó:

- `Server=.` : dùng SQL Server trên máy cục bộ
- `Database=LaptopStore` : tên cơ sở dữ liệu
- `Trusted_Connection=True` : đăng nhập bằng tài khoản Windows
- `TrustServerCertificate=True` : bỏ qua cảnh báo chứng chỉ trong môi trường local

Nếu dùng SQL Server Authentication thì có thể sửa thành:

```json
"ConnectionStrings": {
  "DefaultConnection": "Server=.;Database=LaptopStore;User Id=sa;Password=your_password;TrustServerCertificate=True"
}
```

---

## 6. Chạy chương trình

Sau khi cấu hình xong:

- Nhấn **Ctrl + F5** hoặc **F5** trong Visual Studio
- Hệ thống sẽ chạy trên trình duyệt với địa chỉ localhost, ví dụ:

```text
https://localhost:xxxx
```

---

## 7. Tài khoản đăng nhập mẫu

### Tài khoản người dùng

Người dùng có thể tự đăng ký tài khoản mới trên website.

### Tài khoản quản trị

Có thể tạo tài khoản admin trực tiếp trong SQL Server bằng câu lệnh:

Sau đó đăng nhập với:

- **Email:** admin@gmail.com
- **Mật khẩu:** 123456

---

## 8. Cấu trúc thư mục liên quan

```text
setup/
├── huong-dan-cai-dat.md
├── database.sql
```

- `huong-dan-cai-dat.md`: tài liệu hướng dẫn cài đặt
- `database.sql`: file tạo bảng dữ liệu

---

## 9. Một số lỗi thường gặp

### Không kết nối được database

- Kiểm tra lại tên database trong `appsettings.json`
- Kiểm tra SQL Server đã chạy chưa
- Kiểm tra đúng tên server chưa

### Lỗi thiếu bảng dữ liệu

- Chạy lại file SQL tạo bảng
- Hoặc chạy lại lệnh:

```powershell
Update-Database
```

### Không đăng nhập được admin

- Kiểm tra tài khoản admin đã được thêm vào bảng `Customers` chưa
- Kiểm tra cột `Role` đã có giá trị `Admin` chưa

---

## 10. Kết luận

Sau khi thực hiện đầy đủ các bước trên, hệ thống website bán laptop có thể chạy được trên máy cục bộ, hỗ trợ các chức năng cơ bản dành cho người dùng và quản trị viên.
