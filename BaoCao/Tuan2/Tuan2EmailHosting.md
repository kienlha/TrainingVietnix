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

# 3. DKIM, SPF và PTR(RDNS)
## 3.1. DKIM
**Khái niệm:**
- DKIM (DomainKeys Identified Mail) là một tiêu chuẩn xác thực email giúp xác định tính hợp lệ của email và nguồn gốc của nó bằng cách sử dụng chữ ký số được gắn vào email (private - public key). 
- Điều này giúp ngăn chặn spam và email giả mạo, đảm bảo email đến từ tên miền được xác định và không bị sửa đổi trong quá trình truyền tải.
  
**Cách DKIM hoạt động:**
- Server Mail nhận trích xuất chữ ký trong Email Header
- Dùng thông tin về Domain Key (s=default) để lấy PK

## 3.2. SPF
SPF là viết tắt của "Sender Policy Framework" được sử dụng để bảo vệ và xác minh tính xác thực của email. SPF được sử dụng để ngăn chặn email giả mạo và gian lận.

Khi một máy chủ mail nhận một mail, nó sẽ kiểm tra xem tên miền này đã được cấu hình SPF hay chưa. SPF ghi rõ các IP được ủy quyền để gửi mail từ tên miền đó. Nếu mail được gửi từ một IP không có trong danh sách SPF thì mail này sẽ được đánh dấu nó là spam hoặc từ chối nhận.

Giải thích SPF record:\
`"v=spf1 +mx +a +ip4:103.200.23.160 ~all"`\
`“v=spf1 +mx +a include: _spf.mta.vietnix.com ~all”`
| Loại | Result Code | Giải thích                          |
|------|-------------|-------------------------------------|
| +    | Pass        | Cho phép                           |
| -    | Fail        | Từ chối                            |
| ~    | Soft Fail   | Đánh dấu là từ chối nhưng vẫn nhận |
| ?    | Neutral     | Không từ chối cũng không đồng ý (treo) |

| Loại    | Giải thích                                                                                   |
|---------|----------------------------------------------------------------------------------------------|
| +mx     | Accept nếu MX Server trùng với IP đang gửi mail                                              |
| +a      | Nếu IP gửi tới trùng với IP của domain thì accept                                            |
| +ip4    | Đây là IP của SMTP Outgoing SMTP Server                                                     |
| include | Khi mail server gặp giá trị include nó sẽ tìm record TXT của giá trị include như vậy ta có 2 record SPF lồng nhau |
| ~all    | Tất cả các nguyên tắc trên luôn được áp dụng                                                |

## 3.3. PTR(RDNS)
- Record PTR được sử dụng trong việc thực hiện xác minh đảm bảo rằng máy chủ gửi email là máy chủ hợp pháp của tên miền.
- Máy chủ email khi gửi mail thì cần có một bản ghi PTR tương ứng trong hệ thống DNS để xác minh rằng địa chỉ IP của máy chủ đó có liên quan đến tên miền. 
- Khi máy chủ email nhận một email từ một máy chủ khác, nó có thể kiểm tra bản ghi PTR của máy chủ gửi để đảm bảo tính hợp lệ của nguồn gốc. Nếu bản ghi PTR không khớp hoặc không tồn tại, email có thể bị xem xét như một email spam.
- Sử dụng bản ghi PTR cùng với các tiêu chuẩn xác thực email khác như DKIM và SPF giúp làm giảm khả năng email giả mạo và cải thiện tính hợp lệ của email trong hệ thống email.
