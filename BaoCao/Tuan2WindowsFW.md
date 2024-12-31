# 1. Giới thiệu về Windows Firewall
Windows Firewall là một tính năng bảo mật tích hợp trong hệ điều hành Windows của Microsoft, giúp bảo vệ máy tính khỏi các mối đe dọa từ mạng. Đây là một tường lửa lọc gói dữ liệu, kiểm soát luồng thông tin giữa thiết bị và internet hoặc mạng nội bộ.\
![image](https://github.com/user-attachments/assets/298fd55c-5b6d-49be-bbfe-670ed30fb208)

Chức năng chính:
- Chặn truy cập trái phép: Ngăn chặn các kết nối không mong muốn từ bên ngoài hoặc các phần mềm độc hại.
- Kiểm soát ứng dụng: Cho phép hoặc từ chối các chương trình cụ thể truy cập mạng dựa trên quy tắc do người dùng thiết lập.
- Quản lý kết nối mạng: Tùy chỉnh theo từng loại mạng như public, private hoặc domain.
# 2. Các chức năng cơ bản của Windows Firewall
Để sử dụng Windows Firewall, ta vào Server Manager->Local Server, rồi nhấn vào dòng chữ bên cạnh Windows Firewall
![image](https://github.com/user-attachments/assets/5f579398-3b31-402f-8d73-709a15894502)

Giao diện chính của Windows Firewall:
![image](https://github.com/user-attachments/assets/14aa10c1-5db3-44cc-ae8d-05cf985cbd4a)

Chọn Turn Windows Firewall on or off để bật/tắt firewall hoặc chặn tất cả truy cập vào trên private và public network:
![image](https://github.com/user-attachments/assets/2474bf0e-c7ab-46de-88a0-9a97904e0ccc)

Chọn Allow an app or feature throught Windows Firewall để cho phép ứng dụng nào đó đi qua:
![image](https://github.com/user-attachments/assets/fc9f2b2a-bd6b-426a-b045-6d6c6f85bd1a)Windows Firewall là một tính năng bảo mật tích hợp trong hệ điều hành Windows của Microsoft, giúp bảo vệ máy tính khỏi các mối đe dọa từ mạng. Đây là một tường lửa lọc gói dữ liệu, kiểm soát luồng thông tin giữa thiết bị và internet hoặc mạng nội bộ.

Chức năng chính:
Chặn truy cập trái phép: Ngăn chặn các kết nối không mong muốn từ bên ngoài hoặc các phần mềm độc hại.
Kiểm soát ứng dụng: Cho phép hoặc từ chối các chương trình cụ thể truy cập mạng dựa trên quy tắc do người dùng thiết lập.
Quản lý kết nối mạng: Tùy chỉnh theo từng loại mạng như mạng công cộng, mạng cá nhân hoặc mạng miền.

# 3. Các chức nâng nâng cao của Windows Firewall
## 3.1. Tổng quan
Để sử dụng các chức năng nâng cao, ta có thể chon Advanced Setting trên giao diện Windows Firewall hoặc tại Server Manager, chọn Tools->Windows Firewall with Advanced Security:
![image](https://github.com/user-attachments/assets/cc593573-d26f-455a-b93d-36c5e32bd264)

Giao diện chính của Windows Firewall with Advanced Security:mạng công cộng, mạng cá nhân hoặc mạng miền
![image](https://github.com/user-attachments/assets/c6fa689d-23ab-4c57-ac51-2cdfd93dcfe0)

Có 2 chức năng chính cần quan tâm là Inbound Rules và Outbound Rules:
- Inbound Rules: những quy tắc áp dụng khi kết nối từ bên ngoài vào server.
- Outbound Rules: những quy tắc áp dụng khi kết nối từ server ra ngoài.
![image](https://github.com/user-attachments/assets/5ae6d998-9060-4433-944c-064110e443fc)
  + Cột bên trái là nơi ta chọn các tùy chọn bảo mật chính cần sử dụng
  + Cột giữa là danh sách và thông tin liên quan của các Rule
  + Cột phải là các tùy chọn để tạo rule mới, lọc rule cãn tìm, tùy chỉnh các mục để xem, tải lại, xuất danh sách rule, xóa rule,...
## 3.2. Tạo Rule mới
### VD1: Chặn port 22
Ở Inbound Rules, chọn New Rule... để thêm quy tắc cho việc truy cập từ bên ngoài vào
![image](https://github.com/user-attachments/assets/78c2c3ee-6da1-444c-81e2-4446522716b5)
Tại cửa sổ New Inbound Rule Wizard, ở Rule Type có các lựa chọn:
- Program: kiểm soát kết nối tới 1 chương trình
- Port: kiểm soát kết nối tới 1 port nào đó
- Predefined: chọn các quy tắc được Windows thiết lập sẵn
- Custom: có các tùy chọn cụ thể hơn trong việc thiết lập các rule
Chọn Port và nhấn Next

Tại Protocol and Ports, ta chọn giao thức được áp dụng (TCP hoặc UDP) và nhập 1 port hoặc 1 dãy các port. Ở đây chọn TCP và port 22 rồi nhấn Next
![image](https://github.com/user-attachments/assets/2ba5c339-ac73-4317-a182-ce5b816c5c4b)

Trong mục Actions ta thấy có 3 tùy chọn là 
+ Allow the connection: Cho phép kết nối.
+ Allow the connection if it is secure: chỉ có phép các kết nối đã được bảo mật hoặc xác thực bằng IPSec.
+ Block the connection: chặn tất cả các kết nối đến.
Để chặn kết nối thì ta chọn Block the connection rồi nhấn Next:
![image](https://github.com/user-attachments/assets/59d80200-0130-40ee-b2db-81fd07c6acc4)

Chọn phạm vi áp dụng trong mục Profile với các lựa chọn là Domain(trong cùng 1 miền), Private(trong 1 mạng riêng), Public(trong mạng công cộng) rồi nhấn Next
![image](https://github.com/user-attachments/assets/8a9d3e54-1650-4d84-9329-856b7da204f0)

Tại mục Name ta đặt tên cho Rule rồi nhấn Finish để hoàn tất:
![image](https://github.com/user-attachments/assets/555ca219-7c01-43b9-bc6e-857c5ecc7d5c)

Ta thấy trong danh sách Inbound Rules đã xuất hiện Rule vửa tạo là "Block port 22"
![image](https://github.com/user-attachments/assets/b14843fe-eeaf-4eeb-b8cf-3d6a728f88d8)

### VD2: Tạo Rule cho phép ping từ ngoài vào 
IP của máy Windows Server là 14.225.206.52:
![image](https://github.com/user-attachments/assets/4f283c4a-0f45-436f-a970-131442863e75)

Ping từ máy Linux tới IP của máy Windows Server ta thấy không nhận được phản hồi:
![image](https://github.com/user-attachments/assets/2060d2ad-6c70-4680-8dda-92a2bce7d5fc)

Tại Inbound Rules, nhấn New Rule, trong Rule Type chọn Custom rồi nhấn Next:
![image](https://github.com/user-attachments/assets/8821abd9-38c8-4bcc-9d09-87533daae76b)

Trong Program chọn All programs rồi nhấn Next:
![image](https://github.com/user-attachments/assets/835c1bc7-bbc8-4d5c-9e62-bb3a92b219da)

Chọn ICMPv4 trong Protocol Type rồi nhấn Next:
![image](https://github.com/user-attachments/assets/9c7242c8-e148-4fd5-8160-81ba1402ab7d)

Trong Scope chọn Any IP address cho cả 2 lựa chọn rồi nhấn Next:
![image](https://github.com/user-attachments/assets/be5ed33b-f47f-4a9e-a7f4-685c3ef1efb7)

Chọn Allow the connection rồi nhấn Next:
![image](https://github.com/user-attachments/assets/b94c80ab-695e-421a-915b-ce3b9a3845fa)

Chọn hết để áp dụng lến toàn bộ rồi nhấn Next:
![image](https://github.com/user-attachments/assets/c38a397b-1614-4b84-ac6b-21152118df5f)

Đặt tên rồi nhấn Finish để hoàn thành:
![image](https://github.com/user-attachments/assets/3bec2aa7-e5d7-4722-88bf-05a205b41494)

Trên máy Linux thực hiện ping tới IP của máy Windows Server:
![image](https://github.com/user-attachments/assets/d4e93900-e809-4af9-a77a-871b016917a5)

### VD3: Chặn kết nối HTTP
Đầu tiên ở Outbound Rules, chọn New Rule. Tiếp theo trong Rule Type chọn Port:
![image](https://github.com/user-attachments/assets/e58a7a0d-1f9b-4eef-89c4-92c2bc3c4c88)

Chọn giao thức là TCP và port là 80:
![image](https://github.com/user-attachments/assets/04271651-381e-497c-bbeb-3c85b6cc5673)

Tiếp theo chọn Block the connection. Các bước còn lại cũng tương tự như trước là tạo thành công:
![image](https://github.com/user-attachments/assets/990ce4d8-6ef1-43d4-ad7d-c771b945421a)

Truy cập vào website http://stealmylogin.com ta thấy nó đã bị chặn:
![image](https://github.com/user-attachments/assets/8453d168-919a-42ef-b680-b38bfd88c7ab)

