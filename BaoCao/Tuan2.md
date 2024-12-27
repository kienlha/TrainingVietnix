# 1. Domain
## Trang quản trị Domain của Hostinger:
![image](https://github.com/user-attachments/assets/030c2cea-4a14-4c11-99ca-a4d0e04bed5d)
![image](https://github.com/user-attachments/assets/317e6575-4540-48f1-aed9-e759cf2a0136)

- Để trỏ domain vào hosting ta chỉnh sửa địa chỉ IP trong A record:
![image](https://github.com/user-attachments/assets/3c53b49f-fac5-4b24-92d3-6100481ec8a6)

Xem thông tin Domain bằng cách sử dụng công cụ LOOKUP của ICANN:
![image](https://github.com/user-attachments/assets/a5238446-930f-4678-837b-6e5f065c1c28)

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

# 4. Chuyển dữ liệu website từ Cpanel qua Cyberpanel
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

Vào trang quản lý tên miền trỏ vào IP của Cyberpanel, sau đó truy cập tên miền kienlha.xyz sẽ vào được trang web chuyển từ Cpanel:
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

Thay thế bằng:
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



