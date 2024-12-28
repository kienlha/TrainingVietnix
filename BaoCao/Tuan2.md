# 1. Domain
## Quản trị Domain trên cPanel:
Để vào giao diện quản lý domain, ta vào Tools, trong danh sách công cụ Domains ta chọn Domains:
![image](https://github.com/user-attachments/assets/cc07b692-4916-4133-a0ae-d6134004cd3c)

Giao diện quản lý Domain trong cPanel:
![image](https://github.com/user-attachments/assets/360896c8-5379-46e7-a5d6-1ca553ba29df)
- Tại đây ta có thể xem danh sách domain, thực hiện các cấu hình cho domain trong danh sách, tạo domain mới

Nhấn nút Create A New Domain để tạo 1 domain mới:
![image](https://github.com/user-attachments/assets/418c9169-1f03-4aa9-a671-ace3f527460f)

Nhập vào tên Domain, chọn Share document root nếu muốn tạo Alias domain, bỏ chọn nếu muốn tạo addon domain:
![image](https://github.com/user-attachments/assets/a028be50-0102-4306-aeee-3108a9a9a0a0)

Nhấn nút Submit để tạo. Domain mới sẽ được thêm vào danh sách:
![image](https://github.com/user-attachments/assets/013ed350-bd94-4c00-bbc7-7388d262d8c4)

Để xem và quản lý các record của các domain ta chọn Zone Editor trong Tools của Domain:\
![image](https://github.com/user-attachments/assets/7f399396-533e-4a2c-842b-f658dbfd532e)

Tại giao diện Zone Editor, trong mục Actions có các tùy chọn để thêm các Record, DNSSEC key và quản lý các Record:
![image](https://github.com/user-attachments/assets/e1ec6f35-fe3f-4b5a-becf-b81fee57b9ad)

Chọn Manage để vào giao diện xem, xóa, sửa các bản ghi của từng domain:
![image](https://github.com/user-attachments/assets/1c5804b8-10ac-47ff-ab6b-a65c86e6ff22)

Xem thông tin Domain bằng cách sử dụng công cụ LOOKUP của ICANN:
![image](https://github.com/user-attachments/assets/a5238446-930f-4678-837b-6e5f065c1c28)

Ta thấy tên miền kienlha.xyz có 2 trạng thái là: serverTransferProhibited(không được chuyển đổi tên miền từ nhà đăng ký tên miền này sang một nhà đăng ký tên miền khác) và clientTransferProhibited(khóa chuyển nhượng tên miền).

## Các trạng thái cần có của Domain: 
- Server Status Code: addPeriod, autoRenewPeriod, inactive, ok, pendingCreate, pendingDelete, pendingRenew, pendingRestore, pendingTransfer, pendingUpdate, redemptionPeriod, renewPeriod, serverDeleteProhibited, serverHold, serverRenewProhibited, serverTransferProhibited, serverUpdateProhibited,  transferPeriod.
- Client Status Code: clientDeleteProhibited, clientHold, clientRenewProhibited, clientTransferProhibited, clientUpdateProhibited.
  
## Các trạng thái gây ảnh hưởng tới việc truy cập website: 
inactive, pendingDelete, redemptionPeriod, serverHold, clientHold.
# 2. Đăng ký, cài đặt cấu hình hosting/vps
Hosting:
![image](https://github.com/user-attachments/assets/26f5d722-cdda-4bac-a490-d948481d8dbd)

VPS:
![image](https://github.com/user-attachments/assets/d95d88d3-5517-4cb9-b18c-5b08e419d793)

# 3. Cài đặt Cyberpanel trên VPS
Lệnh cài đặt Cyberpanel:
>`sh <(curl https://cyberpanel.net/install.sh || wget -O - https://cyberpanel.net/install.sh)`

Sau khi cài xong SSH lại vào VPS sẽ thấy hiển thị thông tin về Cyberpanel:
![image](https://github.com/user-attachments/assets/11f86d9a-1f34-4403-9593-e71dcb18392f)

Truy cập vào Cyberpanel bằng cách nhập kienlha.xyz:8090 vào thanh địa chỉ:
![image](https://github.com/user-attachments/assets/73806af9-6e6e-41bb-868b-3212a43fd8a4)

Sau khi đăng nhập thành công sẽ vào giao diện chính của Cyberpanel:
![image](https://github.com/user-attachments/assets/300aa4ac-e886-4a80-9994-c3c893255542)

Để tạo website, trong MAIN, chọn Website->Create Website và điền vào các thông tin cần thiết:
![image](https://github.com/user-attachments/assets/916c0459-ae24-4d51-a8b2-ee4bb01aeaea)

Để cài wordpress và tạo nội dung cho website, vào List Websites, chọn Manage:
![image](https://github.com/user-attachments/assets/098b8748-e931-42a3-9454-67c41471c25c)

Trong APPlICATION INSTALLER, chọn WP+LS CACHE:
![image](https://github.com/user-attachments/assets/05c491b0-d805-4384-873d-6c0d2d765fe1)

Nhập các thông tin cần thiết và nhấn Install Now:
![image](https://github.com/user-attachments/assets/8b8dc1c2-2b3a-40f6-88df-3cb52590cdd2)

Sau khi cài xong, khi truy cập vào tên miền kienlha.xyz ta sẽ vào được website đã tạo:
![image](https://github.com/user-attachments/assets/3b091c99-51b4-45e0-8baa-b3adfb94239e)

# 4. Chuyển dữ liệu website từ cPanel qua Cyberpanel
Tạo file backup trang web wordpress:
- Vào File Manager, nén tất cả các file trong thư mục lưu web (public_html), sau đó tải về máy
![image](https://github.com/user-attachments/assets/036bff02-c87e-409e-b527-6b90412ebd09)

- Vào Databases, chọn phpMyAdmin, chọn CSDL của trang web cần chuyển, chọn mục Export, sau đó nhấn nút Export ở dưới để tải CSDL về máy:
![image](https://github.com/user-attachments/assets/5a88c95c-5ba1-4d1a-949c-6f453e61db0a)

Upload và giải nén dữ liệu trang web vào trong thư mục public_html của Cyberpanel:
![image](https://github.com/user-attachments/assets/e75d6580-56a3-4e9a-a135-388e59dd1b0b)

Vào phpMyAdmin của Cyberpanel và import CSDL của trang web cũ vào CSDL của trang mới:
![image](https://github.com/user-attachments/assets/501b05bb-8629-4bba-953d-9dae89c33260)

Trong File Manager, chọn file wp-config.php và chọn Edit:
![image](https://github.com/user-attachments/assets/5aad3327-f791-4a3c-9297-54e7203d7565)

Sửa lại các thông tin cho đúng với CSDL bên Cyberpanel và lưu lại:
![image](https://github.com/user-attachments/assets/9148d425-0dbe-464f-8125-e63127b19764)

Vào trang quản lý tên miền trỏ vào IP của Cyberpanel, sau đó truy cập tên miền kienlha.xyz sẽ vào được trang web chuyển từ cPanel:
![image](https://github.com/user-attachments/assets/549af295-96cd-49e2-ad98-79401eaaab4d)

# 5. Cài đặt website Wordpress trên VPS
## Cài đặt PHP, Apache và các thư viện liên quan
![image](https://github.com/user-attachments/assets/1293445f-5892-4705-ab4f-7f2ceebf0a9a)

## Cài đặt Wordpress
Tạo thư mục cài đặt và tải file từ [WordPress.org](http://wordpress.org/)\
![image](https://github.com/user-attachments/assets/a410ab3d-676d-4f9f-a197-f4e83f0d2e44)
## Cấu hình Apache cho WordPress
Tạo trang Apache cho WordPress. Tạo file `/etc/apache2/sites-available/wordpress.conf` với nội dung như sau:
![image](https://github.com/user-attachments/assets/42437a58-7029-4462-9965-3017882df157)

Kích hoạt trang với lệnh `a2ensite wordpress`\
Kích hoạt URL rewriting với lệnh `a2enmod rewrite`\
Vô hiệu hóa trang mặc định với lệnh `a2dissite 000-default`\
Reload dịch vụ apache2 với lệnh `service apache2 reload`\
## Cấu hình cơ sở dữ liệu
Tạo CSDL MySQL với các lệnh:
![image](https://github.com/user-attachments/assets/62caf2c9-277e-4c7b-98df-a7b26021fde7)

## Cấu hình WordPress kết nối với CSDL:
Sao chép file cấu hình mẫu tới wp-config.php:
![image](https://github.com/user-attachments/assets/0a17a5c2-2680-4917-ad71-c75a9aa3370d)

Đặt thông tin đăng nhập CSDL vào trong file cấu hình:
![image](https://github.com/user-attachments/assets/f03fdd3d-2f40-4402-8749-d5d14186dd78)

Mở file cấu hình với lệnh: `sudo -u www-data nano /srv/www/wordpress/wp-config.php`
Xóa các dòng sau:
![image](https://github.com/user-attachments/assets/0cdfea8e-2c80-4975-838b-0990e114bd01)

Thay thế bằng:\
![image](https://github.com/user-attachments/assets/0ff32e43-9282-47cc-941d-4980b93fc6b5)

## Vào trang WordPress:
Truy cập vào IP của VPS:
![image](https://github.com/user-attachments/assets/433f289d-66eb-4de3-b115-eab342f9de16)

Nhập các thông tin cần thiết:
![image](https://github.com/user-attachments/assets/cb28ab8b-9926-42d4-82f3-c56410925b5c)

Đăng nhập váo WordPress:
![image](https://github.com/user-attachments/assets/883f5a50-c3f2-4fc7-b3d9-267850295a30)

Kết quả vào được Dashboard WordPress:
![image](https://github.com/user-attachments/assets/5708e561-bb77-4cb3-8346-21c54169bc8e)

## Cài đặt plugin cho WordPress:
Tại dashboard chọn Plugins ở thanh bên trái và nhấn Add New Plugin:
![image](https://github.com/user-attachments/assets/a571c7c7-c705-4dcb-b802-d89d92659d96)

Nhấn Install Now trên plugin cấn cài đặt:
![image](https://github.com/user-attachments/assets/5e19590e-df33-41b5-a712-8432c7fd91c5)

Sau khi cài xong nhấn Activate để kích hoạt Plugin:\
![image](https://github.com/user-attachments/assets/b535dddc-8abb-43d8-9fa5-5a1c2416117f)

# 6. Setup Mail Account, FTP Account trên cPanel
## Mail Account:
Các công cụ về Email trên cPanel:
![image](https://github.com/user-attachments/assets/52ac6ccc-785c-4cc8-97e4-017aa9dc3948)

Giao diện quản lý Email Accounts:
![image](https://github.com/user-attachments/assets/3538749d-54fe-4e06-ab34-ae70a92cd572)

Để tạo 1 Email mới ta nhấn nút Create trên giao diện Email Accounts, sau đó điền các thông tin cần thiết, cuối cùng nhấn Create để tạo:
![image](https://github.com/user-attachments/assets/a2e2d4d0-9289-4cd5-85b0-08c124a7243d)

Truy cập vào web mail bằng đường dẫn http://url:2096:
![image](https://github.com/user-attachments/assets/88ca7987-26ef-42eb-96b5-f9160e6f4d19)

Đăng nhập bằng tài khoản vừa tạo ta sẽ vào được giao diện webmail:
![image](https://github.com/user-attachments/assets/d070744b-1d9c-4287-965c-0adca154e53d)

Nhấn Open để vào Inbox của mail:
![image](https://github.com/user-attachments/assets/ebdeb826-68be-4e80-8c49-3c275239060f)

Tại đây ta có thể sử dụng các chức năng của Web Mail như gửi/nhận Email,...
![image](https://github.com/user-attachments/assets/a6e8aa22-206b-4ad3-aee4-4fa555df316b)

Quay về giao diện Email Accounts, nhấn nút Manage để thực hiện các tùy chỉnh đối với tài khoản Mail được chọn:
![image](https://github.com/user-attachments/assets/49b138de-9311-4dbe-8769-2d0737fa5c02)

Tại đây ta có thể đổi mật khẩu, cấp phát dung lượng lưu trữ, chọn các restriction, hoặc xóa tài khoản email:
![image](https://github.com/user-attachments/assets/c1efe3d6-3f8b-4eed-b8df-98b91115286e)

## FTP Account:
Trong Files, chọn FTP Accounts:
![image](https://github.com/user-attachments/assets/0238412a-5912-4304-89c6-dbc0abd542a0)

Nhập các thông tin cần thiết rồi nhấn Create FTP Account để tạo 1 tài khoản FTP:
![image](https://github.com/user-attachments/assets/fd7c9a10-637c-43ea-8962-b2b5a4e427e7)

Danh sách tài khoản FTP được tạo, tại đây ta có thể đổi password tài khoản, đặt giới hạn lưu trữ cũng như xóa tài khoản:
![image](https://github.com/user-attachments/assets/7572edb1-91ac-4dd2-a0cc-c2f59b54425f)

Danh sách tài khoản FTP đặc biệt được tạo mặc định:
![image](https://github.com/user-attachments/assets/dee02b46-541d-4765-88fd-dae1254ad5c4)

Sử dụng Filezilla để kiểm tra:
Nhập vào thông tin tài khoản FTP đã tạo:
![image](https://github.com/user-attachments/assets/1f25fa04-8b5d-4abf-826a-68c4eb99984a)

Nhấn Quickconnect ta thấy đăng nhập thành công:
![image](https://github.com/user-attachments/assets/5702d5de-e195-4519-9543-1e70254e1534)

Nhấn chuột phải vào 1 file và nhấn Upload:
![image](https://github.com/user-attachments/assets/46856b11-aa53-4489-8b6d-a32083e028e8)

Upload file thành công:
![image](https://github.com/user-attachments/assets/b5ab3669-01c8-4c4c-91c9-b9da118fa333)

# 7.Reverse Proxy
## Giới thiệu
Reverse Proxy là một loại máy chủ (Server) hoạt động như một trung gian giữa người dùng và các máy chủ Back-end (Backend Servers). Trong kiến trúc mạng, Reverse Proxy (hoặc còn gọi là Server đảo ngược) thường được đặt giữa người dùng và các máy chủ backend để thực hiện một số chức năng quan trọng.
![image](https://github.com/user-attachments/assets/6c21d1b5-7786-4246-bff1-bb154c68d9c2)

Một số lợi ích của Reverse Proxy: 
- Phân phối tải hiệu quả
- Tăng tốc độ tải trang
- Bảo mật tốt
- Giảm áp lực xử lý SSL trên máy chủ backend và cung cấp một lớp bảo mật tốt hơn
- Chuyển hướng linh hoạt
## Cài đặt Reverse Proxy cho cPanel
Trang web hiện tại của cPanel đang sử dụng web server là Apache:\
![image](https://github.com/user-attachments/assets/7f82891b-9f80-4c04-83b9-83cad3d2073a)

Cài đặt NGINX với lệnh `apt install --purge ea-nginx`
![image](https://github.com/user-attachments/assets/38242ee5-8244-4047-b7eb-cb8b7271cbaa)

Như vậy ta đã cài reverse proxy NGINX thành công, để kiểm tra, khi vào cPanel ta thấy trong cột General Information có thêm mục NGINX caching:\
![image](https://github.com/user-attachments/assets/90e17cae-960a-446f-8231-db6b1ea928d1)

Trên WHM, ta thấy xuất hiện các tùy chọn của NGINX Manager:
![image](https://github.com/user-attachments/assets/b4db4834-24e5-4f49-b456-9dcf6e7b5ca9)

Ta thấy web server lúc này đã chuyển sang nginx:
![image](https://github.com/user-attachments/assets/60cfc35d-e687-417b-a243-2b2ba17a3345)

## Cài đặt Reverse Proxy NGINX cho Webserver Apache
Cài đặt Apache và kiểm tra trạng thái của nó:\
![image](https://github.com/user-attachments/assets/d9280c84-9002-4db5-b75f-b85e62e8bb73)
![image](https://github.com/user-attachments/assets/4cec557d-4ee7-4a09-9d5f-a6c8f3d3b701)

Truy cập vào IP của VPS ta thấy đã cái Apache thành công:
![image](https://github.com/user-attachments/assets/3d1428c8-9d20-44ad-b1a3-35e130e068e9)

Để cấu hình NGINX làm reverse proxy, đâù tiên cần cài NGINX:\
![image](https://github.com/user-attachments/assets/2e39bf27-e153-4b8e-a39f-ce6f00eea563)

Sửa cấu hình của máy chủ Apache đang listen trên cổng 80 sang một cổng khác (ở đây là 8080):\
![image](https://github.com/user-attachments/assets/fb4d3065-bd02-410f-8a90-03cf7b74a6a6)
![image](https://github.com/user-attachments/assets/8aae5a82-2ffb-48f9-9404-d5a6040b9826)

Vì đã chuyển port của Apache sang cống khác nên chúng ta cũng phải cấu hình lại file 000-default.conf của apache sang port 8080 mà chúng ta mới sửa:\
![image](https://github.com/user-attachments/assets/7244a6d0-c784-4120-b4aa-38103db90631)
![image](https://github.com/user-attachments/assets/9542d880-f4b4-48c3-9fa8-2d57d61b013b)

Khởi động lại Apache để áp dụng cấu hình mới bằng lệnh: `systemctl restart apache2`\
Tạo file cấu hình cho reverse proxy:
![image](https://github.com/user-attachments/assets/8ab8c80f-a8d6-46a9-8d92-e9bd611b00b5)

Thêm vào các dòng sau:\
![image](https://github.com/user-attachments/assets/fe305a6a-d314-4cf5-bfc1-f2e46ebbbb0e)

* Giải thích ý nghĩa các dòng:
	+ listen: cổng mà nginx tiến hành lắng nghe ở đây là 80 mặc định là http
	+ server_name: khai báo tên miền, hoặc địa chỉ IP mà nginx sẽ chạy khi có yêu cầu đến  địa chỉ này
	+ proxy_pass: chuyển tiếp tất cả yêu cầu HTTP đến một backend server khác, do ở đây là cấu hình trên cùng máy chủ nên sẽ để là đỉa chỉ localhost với port 8080 nơi mà webserver nginx của chúng ta đang hoạt động
	+ proxy_set_header Host $host: thêm header Host vào yêu cầu gửi đi giúp backend server nhận được thông tin tên miền chính xác mà client đã yêu cầu
	+ proxy_set_header X-Real-IP $remote_addr: gửi địa chỉ IP của client yêu cầu đến máy chủ backend
  + proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for: gửi tất cả các proxy server mà gói tin client đã đi qua trước đó để đến backend server
  + proxy_set_header X-Forwarded-Proto $scheme: gửi cho Backend Server biết giao thức mà client đã sử dụng
Kích hoạt và liên kết đến thư mục sites-enabled:
![image](https://github.com/user-attachments/assets/026a6b33-0fc6-4c7b-892f-13c098419f90)

Kiểm tra xem cấu hình đã hoạt động hay chưa bằng lệnh `nginx -t`\
Ta thấy cấu hình mới đã hoạt động thành công:
![image](https://github.com/user-attachments/assets/c1e35264-2f1e-4006-8ba0-8e2818b30cb2)

Khởi động lại dịch vụ nginx với lệnh `systemctl restart nginx` và truy cập vào địa chỉ IP để kiểm tra kết quả:
![image](https://github.com/user-attachments/assets/69dbb622-b43d-4d48-95b7-e04804fd3e39)

Ta thấy nội dung trang web vẫn được hiển thị từ Apache nhưng Webserver của nó đang là nginx/1.18.0. Như vây ta đã cấu hình thành công Reverse Proxy bằng NGINX cho máy chủ Apache.
Thử sửa proxy_pass trong file reverse-proxy.conf thành google.com:\
![image](https://github.com/user-attachments/assets/d590bc63-fe94-490a-baf7-0a842a1149c7)

Khi truy cập vào IP của VPS, ta thấy nó có status 301 nghĩa là đã chuyển sang google.com vĩnh viễn:
![image](https://github.com/user-attachments/assets/27cfb841-d4b8-4eba-8f33-f013e439f6c6)
![image](https://github.com/user-attachments/assets/7fd1f207-1c3c-4954-8572-cdde59be8dd2)
![image](https://github.com/user-attachments/assets/63aa4f22-f1cd-4943-8bc3-bcd179f9033e)



