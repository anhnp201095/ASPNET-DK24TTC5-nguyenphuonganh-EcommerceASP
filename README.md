# XÂY DỰNG WEBSITE BÁN LAPTOP - ASP.NET CORE MVC

## Thông tin sinh viên

- **Họ và tên:** Nguyễn Phương Anh
- **MSSV:** 170124503
- **Lớp:** DK24TTC5
- **Email:** nguyenphuonganh130421@gmail.com
- **Số điện thoại:** 0966032884

---

## 1. Giới thiệu đề tài

Đây là đồ án xây dựng **website bán laptop** sử dụng **ASP.NET Core MVC** kết hợp với **Entity Framework Core** và **SQL Server**.  
Hệ thống được xây dựng nhằm hỗ trợ khách hàng tìm kiếm, xem thông tin sản phẩm, thêm vào danh sách yêu thích, thêm vào giỏ hàng, đặt hàng trực tuyến, đồng thời hỗ trợ quản trị viên quản lý sản phẩm, khách hàng và đơn hàng.

Đề tài hướng đến việc áp dụng các kiến thức đã học về:

- Lập trình web với ASP.NET Core MVC
- Kết nối và thao tác cơ sở dữ liệu bằng Entity Framework Core
- Thiết kế giao diện website bán hàng
- Xây dựng chức năng tìm kiếm, lọc và phân trang dữ liệu
- Phân quyền giữa người dùng và quản trị viên

---

## 2. Mục tiêu của đề tài

- Xây dựng một website bán laptop có giao diện thân thiện, dễ sử dụng
- Hiển thị danh sách laptop từ cơ sở dữ liệu
- Phân loại sản phẩm theo **danh mục** và **thương hiệu**
- Tìm kiếm sản phẩm theo từ khóa
- Phân trang sản phẩm ở trang chủ
- Xem chi tiết sản phẩm
- Xây dựng chức năng **wishlist**
- Xây dựng chức năng **giỏ hàng**
- Hỗ trợ đặt hàng và quản lý đơn hàng cơ bản
- Xây dựng khu vực **quản trị riêng cho admin**

---

## 3. Công nghệ sử dụng

- **Ngôn ngữ lập trình:** C#
- **Framework:** ASP.NET Core MVC
- **Cơ sở dữ liệu:** SQL Server
- **ORM:** Entity Framework Core
- **Front-end:** HTML, CSS, Bootstrap, Razor View Engine
- **IDE:** Visual Studio 2022

---

## 4. Chức năng chính của website

### 4.1 Người dùng

- Xem danh sách laptop
- Xem chi tiết từng sản phẩm
- Tìm kiếm laptop theo tên
- Lọc sản phẩm theo danh mục
- Lọc sản phẩm theo thương hiệu
- Kết hợp lọc theo nhiều điều kiện
- Thêm sản phẩm vào danh sách yêu thích
- Xem danh sách yêu thích
- Thêm sản phẩm vào giỏ hàng
- Cập nhật số lượng sản phẩm trong giỏ hàng
- Đặt hàng
- Xem đơn hàng của mình
- Xem chi tiết đơn hàng

### 4.2 Quản trị viên

- Đăng nhập vào trang quản trị
- Xem tổng quan hệ thống
- Quản lý sản phẩm
- Thêm sản phẩm mới
- Chỉnh sửa thông tin sản phẩm
- Xóa sản phẩm
- Quản lý đơn hàng
- Xem chi tiết đơn hàng
- Cập nhật trạng thái đơn hàng
- Quản lý khách hàng

### 4.3 Hệ thống

- Lấy dữ liệu sản phẩm từ cơ sở dữ liệu
- Hiển thị phân trang, mỗi trang 6 sản phẩm
- Quản lý thông tin thương hiệu, danh mục, khách hàng, giỏ hàng, yêu thích và đơn hàng
- Phân quyền tài khoản giữa **người dùng** và **quản trị viên**

---

## 5. Cấu trúc dữ liệu chính

Hệ thống sử dụng các bảng chính sau:

- **Brand**: lưu thông tin thương hiệu laptop  
  Ví dụ: Dell, Asus, HP, Lenovo, Acer, MacBook

- **Category**: lưu danh mục sản phẩm  
  Ví dụ: Laptop Gaming, Laptop Văn Phòng, Laptop Sinh Viên, MacBook

- **Laptop**: lưu thông tin sản phẩm laptop

- **Customer**: lưu thông tin khách hàng và quyền tài khoản

- **CartItem**: lưu thông tin giỏ hàng của từng khách hàng

- **Wishlist**: lưu danh sách sản phẩm yêu thích của khách hàng

- **Order**: lưu thông tin đơn hàng

- **OrderDetail**: lưu chi tiết từng sản phẩm trong đơn hàng

---

## 6. Giao diện và hoạt động của website

Website được thiết kế theo mô hình cửa hàng bán laptop trực tuyến.  
Trang chủ hiển thị danh sách laptop lấy từ cơ sở dữ liệu, mỗi trang hiển thị 6 sản phẩm. Người dùng có thể:

- bấm vào danh mục để lọc sản phẩm
- bấm vào thương hiệu để lọc sản phẩm
- tìm kiếm laptop theo tên
- chuyển qua các trang tiếp theo để xem thêm sản phẩm
- xem chi tiết từng laptop
- thêm sản phẩm vào giỏ hàng
- thêm sản phẩm vào danh sách yêu thích
- đặt hàng và theo dõi đơn hàng

Ngoài ra, website còn có các khu vực chức năng như:

- **Wishlist** để lưu sản phẩm yêu thích
- **Giỏ hàng**
- **Thông tin đơn hàng**
- **Trang quản trị riêng cho admin**

Trang quản trị được thiết kế tách biệt với giao diện người dùng.  
Admin đăng nhập bằng tài khoản có quyền quản trị để truy cập vào hệ thống quản lý. Tại đây, admin có thể:

- xem tổng quan hệ thống
- quản lý danh sách sản phẩm
- thêm, sửa, xóa sản phẩm
- quản lý đơn hàng
- cập nhật trạng thái đơn hàng
- quản lý danh sách khách hàng

---

## 7. Cấu trúc thư mục repository

```text
│── README.md
├── src/
│   ├── ecommerce-asp.sln
│   └── ecommerce-asp/
│       ├── Controllers/
│       ├── Models/
│       ├── Views/
│       ├── wwwroot/
│       ├── Properties/
│       ├── appsettings.json
│       ├── Program.cs
│       └── ecommerce-asp.csproj
│
├── setup/
│   ├── huong-dan-cai-dat.md
│   ├── database.sql
│
├── progress-report/
│   ├── progress-week1.docx
│   ├── progress-week2.docx
│   ├── progress-week3.docx
│   └── progress-week4.docx
│
├── thesis/
│   ├── doc/
│   ├── pdf/
│   └── refs/
```
