# 1. Tổng quan về Email Hosting
## 1.1. Định nghĩa
Email hosting là một dịch vụ cung cấp khả năng tạo, gửi, nhận, lưu trữ email và quản lý email trên tên miền riêng, được tích hợp trực tiếp vào tài khoản hosting của bạn một cách an toàn và chuyên nghiệp mà không cần xây dựng hệ thống riêng. Thay vì sử dụng các dịch vụ email miễn phí như Gmail hay Yahoo với tên miền chung, Email Hosting cho phép doanh nghiệp hoặc cá nhân có địa chỉ email chuyên nghiệp.
- Email Hosting sẽ có định dạng như sau:✉️ abc@tenmiencuaban.com\
→ Với đặc điểm nổi bật là *tenmiencuaban*.
- Email Hosting có thể đáp ứng mọi nhu cầu của doanh nghiệp với sự đa dạng về cấu
hình.
## 1.2. Tính năng của Email Hosting Vietnix
- **Tăng tỷ lệ vào Inbox đến 99%**: Nhờ IP uy tín, hệ thống giám sát spam chặt chẽ, và điều kiện tên miền hoạt động tối thiểu 6 tháng.
- **Bảo mật cao - Chống Spam**: Sử dụng IP uy tín và hệ thống giảm thiểu spam nhằm bảo vệ uy tín của IP gửi email.
- **Hỗ trợ chuyển đổi từ Google Workspace và Office 365**: Chuyển email nhanh chóng, đảm bảo dữ liệu không bị ảnh hưởng.
- **Dễ dàng quản trị**: Giao diện quản lý trực quan, hỗ trợ thao tác toàn quyền với tài khoản email.
- **Backup hàng ngày**: Dữ liệu được sao lưu tự động mỗi ngày, lưu trữ trong 7 ngày để đảm bảo an toàn.
- **Sử dụng nhiều IP sạch**: Tự động thay đổi IP luân phiên để giảm rủi ro bị đánh dấu spam, giúp gửi nhận email thông suốt.
- **Hỗ trợ Email Relay**: Tích hợp với ứng dụng, website, hoặc máy chủ hiện tại để gửi email nhanh chóng.
- **Tư vấn cấu hình**: Hỗ trợ lựa chọn gói phù hợp và hỗ trợ sử dụng trong suốt quá trình vận hành.
# 2. Email Relay
Email Relay sẽ nhận email từ máy chủ thư này, sau đó thông qua một bên thứ ba để chuyển tiếp email sang cho một máy chủ thư khác. Email Relay giúp email tránh bị đánh dấu là spam do được gửi thông qua một server mail có IP sạch.

Các thành phần chính trong Mail Relay là: .
- Mail Relay Server: Một máy chủ email có thể được cấu hình để chuyển tiếp email đến một máy chủ email khác
- Smart Host: là một máy chủ email đóng vai trò là điểm trung gian cho việc chuyển tiếp email từ máy chủ nguồn đến máy chủ đích.

# 3. DKIM và SPF
## 3.1. DKIM
**Khái niệm:**
- DKIM (DomainKeys Identified Mail) là một tiêu chuẩn xác thực email giúp xác định tính hợp lệ của email và nguồn gốc của nó bằng cách sử dụng chữ ký số được gắn vào email (private - public key). 
- Điều này giúp ngăn chặn spam và email giả mạo, đảm bảo email đến từ tên miền được xác định và không bị sửa đổi trong quá trình truyền tải.
  
**Cách DKIM hoạt động:**
- Server Mail nhận trích xuất chữ ký trong Email Header
- Dùng thông tin về Domain Key (s=default) để lấy PK
