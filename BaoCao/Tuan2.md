# 1. Domain
Trang quản trị Domain của Hostinger:
![image](https://github.com/user-attachments/assets/030c2cea-4a14-4c11-99ca-a4d0e04bed5d)
![image](https://github.com/user-attachments/assets/317e6575-4540-48f1-aed9-e759cf2a0136)

- Để trỏ domain vào hosting ta chỉnh sửa địa chỉ IP trong A record:
![image](https://github.com/user-attachments/assets/3c53b49f-fac5-4b24-92d3-6100481ec8a6)

Xem thông tin Domain:
![image](https://github.com/user-attachments/assets/d8f6addb-56a5-4f7e-a9e8-ed86a151acd4)

Các trạng thái cần có của Domain: 
- Server Status Code: addPeriod, autoRenewPeriod, inactive, ok, pendingCreate, pendingDelete, pendingRenew, pendingRestore, pendingTransfer, pendingUpdate, redemptionPeriod, renewPeriod, serverDeleteProhibited, serverHold, serverRenewProhibited, serverTransferProhibited, serverUpdateProhibited,  transferPeriod.
- Client Status Code: clientDeleteProhibited, clientHold, clientRenewProhibited, clientTransferProhibited, clientUpdateProhibited.
Các trạng thái gây ảnh hưởng tới việc truy cập website: inactive, pendingDelete, redemptionPeriod, serverHold, clientHold.
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

