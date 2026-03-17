# Auto Garage Manager

[![.NET](https://img.shields.io/badge/.NET-10.0-blue.svg)](https://dotnet.microsoft.com/)
[![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-10.0-green.svg)](https://dotnet.microsoft.com/apps/aspnet)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 📋 Mô tả dự án

**Auto Garage Manager** là một hệ thống quản lý garage ô tô toàn diện được xây dựng bằng ASP.NET Core Razor Pages. Hệ thống giúp các garage quản lý hiệu quả các hoạt động hàng ngày như quản lý khách hàng, xe cộ, dịch vụ sửa chữa, kho phụ tùng, hóa đơn thanh toán và nhắc nhở bảo dưỡng định kỳ.

## ✨ Tính năng chính

### 👥 Quản lý người dùng và phân quyền
- **Đăng ký/Đăng nhập**: Hệ thống xác thực người dùng với ASP.NET Core Identity
- **Phân quyền**: 4 vai trò chính (Admin, Kế toán, Thợ sửa, Khách hàng)
- **Quản lý hồ sơ**: Cập nhật thông tin cá nhân

### 🚗 Quản lý xe cộ
- **Thêm/Sửa/Xóa xe**: Quản lý thông tin chi tiết xe (biển số, chủ sở hữu, model, năm sản xuất)
- **Lịch sử sửa chữa**: Theo dõi toàn bộ lịch sử bảo dưỡng và sửa chữa
- **Tra cứu nhanh**: Tìm kiếm xe theo biển số

### 🔧 Quản lý dịch vụ và phụ tùng
- **Danh mục dịch vụ**: Quản lý các loại dịch vụ sửa chữa
- **Kho phụ tùng**: Theo dõi tồn kho, cảnh báo khi hết hàng
- **Linh kiện thay thế**: Ghi nhận phụ tùng sử dụng trong mỗi lần sửa chữa

### 💰 Quản lý tài chính
- **Hóa đơn tự động**: Tạo hóa đơn chi tiết cho mỗi lần sửa chữa
- **Báo cáo doanh thu**: Thống kê theo tháng/quý/năm
- **Xuất báo cáo**: PDF và Excel

### 📅 Nhắc nhở bảo dưỡng
- **Cài đặt lịch bảo dưỡng**: Tự động nhắc nhở theo km hoặc thời gian
- **SMS thông báo**: Gửi tin nhắn nhắc nhở qua Twilio
- **Theo dõi trạng thái**: Đã gửi/Chưa gửi

### 📊 Dashboard và báo cáo
- **Thống kê tổng quan**: Số lượng xe, doanh thu, dịch vụ
- **Biểu đồ trực quan**: Sử dụng Chart.js
- **Báo cáo chi tiết**: Theo ngày/tháng/năm

## 🛠️ Công nghệ sử dụng

- **Backend**: ASP.NET Core 10.0 Razor Pages
- **Database**: Entity Framework Core với SQL Server
- **Authentication**: ASP.NET Core Identity
- **Frontend**: Bootstrap 5, Font Awesome 6, CSS3
- **JavaScript**: jQuery, Chart.js
- **SMS Service**: Twilio API
- **Deployment**: IIS/Windows Server

## 📁 Cấu trúc dự án

```
AutoGarageManager/
├── Data/
│   ├── ApplicationDbContext.cs          # Database context
│   ├── SeedData.cs                      # Dữ liệu mẫu
│   └── MaintenanceReminderService.cs    # Service nhắc nhở
├── Models/
│   ├── ApplicationDbContext.cs
│   ├── Customer.cs                      # Model khách hàng
│   ├── Vehicle.cs                       # Model xe cộ
│   ├── Service.cs                       # Model dịch vụ
│   ├── Part.cs                          # Model phụ tùng
│   ├── ServiceHistory.cs                # Model lịch sử sửa chữa
│   ├── MaintenanceReminder.cs           # Model nhắc nhở
│   ├── Settings.cs                      # Model cài đặt
│   └── SupportTicket.cs                 # Model ticket hỗ trợ
├── Pages/
│   ├── Index.cshtml                     # Trang chủ
│   ├── Login.cshtml                     # Đăng nhập
│   ├── Register.cshtml                  # Đăng ký
│   ├── Contact.cshtml                   # Liên hệ
│   ├── Admin/                           # Trang quản trị
│   ├── Accountant/                      # Trang kế toán
│   ├── Mechanic/                        # Trang thợ sửa
│   ├── Customer/                        # Trang khách hàng
│   └── Shared/                          # Layout và partial views
├── Services/
│   ├── ISmsService.cs                   # Interface SMS
│   └── TwilioSmsService.cs              # Implementation Twilio
├── wwwroot/
│   ├── css/
│   │   └── site-modern.css              # CSS tùy chỉnh
│   ├── js/
│   └── lib/                             # Thư viện frontend
├── Migrations/                          # EF Core migrations
├── Properties/
│   └── launchSettings.json
├── appsettings.json                     # Cấu hình ứng dụng
├── Program.cs                           # Entry point
└── AutoGarageManager.csproj             # Project file
```

## 🚀 Cài đặt và chạy

### Yêu cầu hệ thống
- .NET 10.0 SDK
- SQL Server (LocalDB hoặc SQL Server Express)
- Visual Studio 2022 hoặc VS Code
- Git

### Các bước cài đặt

1. **Clone repository**
   ```bash
   git clone https://github.com/LeTheDuy-hihi/AutoGarageManager.git
   cd AutoGarageManager
   ```

2. **Cài đặt dependencies**
   ```bash
   dotnet restore
   ```

3. **Cập nhật database**
   ```bash
   dotnet ef database update
   ```

4. **Chạy ứng dụng**
   ```bash
   dotnet run
   ```

5. **Truy cập ứng dụng**
   - Mở trình duyệt và truy cập: `https://localhost:5001`
   - Đăng ký tài khoản mới hoặc sử dụng tài khoản admin mặc định

### Tài khoản mặc định
- **Admin**: admin@autogarage.vn / Admin123!
- **Kế toán**: accountant@autogarage.vn / Accountant123!
- **Thợ sửa**: mechanic@autogarage.vn / Mechanic123!
- **Khách hàng**: customer@autogarage.vn / Customer123!

## ⚙️ Cấu hình

### Chuỗi kết nối database
Chỉnh sửa `appsettings.json`:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=AutoGarageManager;Trusted_Connection=True;MultipleActiveResultSets=true"
  }
}
```

### Cấu hình SMS (Twilio)
```json
{
  "Twilio": {
    "AccountSid": "your_account_sid",
    "AuthToken": "your_auth_token",
    "FromPhoneNumber": "+1234567890"
  }
}
```

### Cấu hình email (tùy chọn)
```json
{
  "EmailSettings": {
    "SmtpServer": "smtp.gmail.com",
    "Port": 587,
    "Username": "your_email@gmail.com",
    "Password": "your_app_password"
  }
}
```

## 📖 Hướng dẫn sử dụng

### Cho Admin
1. **Quản lý người dùng**: Thêm/sửa/xóa tài khoản, phân quyền
2. **Quản lý danh mục**: Dịch vụ, phụ tùng, cài đặt hệ thống
3. **Xem báo cáo**: Thống kê tổng quan, xuất báo cáo

### Cho Kế toán
1. **Quản lý hóa đơn**: Tạo và theo dõi hóa đơn
2. **Quản lý khách hàng**: Xem thông tin và lịch sử giao dịch
3. **Báo cáo tài chính**: Xuất báo cáo doanh thu

### Cho Thợ sửa
1. **Quản lý xe**: Thêm xe mới, cập nhật thông tin
2. **Ghi nhận dịch vụ**: Tạo lịch sử sửa chữa
3. **Xem nhắc nhở**: Danh sách xe cần bảo dưỡng

### Cho Khách hàng
1. **Quản lý xe cá nhân**: Thêm/sửa/xóa xe
2. **Xem lịch sử**: Lịch sử sửa chữa và hóa đơn
3. **Nhận thông báo**: Nhắc nhở bảo dưỡng qua SMS

## 🔧 Phát triển

### Chạy ở chế độ development
```bash
dotnet watch run
```

### Chạy migration
```bash
dotnet ef migrations add MigrationName
dotnet ef database update
```

### Build production
```bash
dotnet publish -c Release
```

## 🤝 Đóng góp

Chúng tôi hoan nghênh mọi đóng góp! Vui lòng:

1. Fork repository
2. Tạo branch feature: `git checkout -b feature/AmazingFeature`
3. Commit changes: `git commit -m 'Add some AmazingFeature'`
4. Push to branch: `git push origin feature/AmazingFeature`
5. Tạo Pull Request

## 📝 License

Dự án này được phân phối dưới giấy phép MIT. Xem file `LICENSE` để biết thêm chi tiết.

## 📞 Liên hệ

- **Tác giả**: LeTheDuy
- **Email**: lethduy@example.com
- **GitHub**: [LeTheDuy-hihi](https://github.com/LeTheDuy-hihi)

## 🙏 Lời cảm ơn

Cảm ơn các công nghệ và thư viện mã nguồn mở đã hỗ trợ phát triển dự án này:
- ASP.NET Core
- Entity Framework Core
- Bootstrap
- Font Awesome
- Twilio
- Chart.js

---

⭐ Nếu bạn thấy dự án hữu ích, hãy cho chúng tôi một ngôi sao trên GitHub!