# **1. Tìm hiểu các dịch vụ cơ bản của Vietnix**
...
# **2.**
...
# **3. Cài đặt WHM và Cpanel trên VPS**
ssh vào VPS:
![image](https://github.com/user-attachments/assets/36ed480d-8079-46a9-9954-78eadc186880)

Để cài WHM và Cpanel, ta chạy lệnh `cd /home && curl -o latest -L https://securedownloads.cpanel.net/latest && sh latest`
![image](https://github.com/user-attachments/assets/683312f5-a1d8-48b9-a99c-bf17c45e36f8)

Dùng lệnh `whmlogin` và truy cập vào đường dẫn được tạo ra để trưy cập vào WHM trên web:
![image](https://github.com/user-attachments/assets/baba6672-5cd2-449d-a736-9d22de7146f1)

Click vào checkbox và nhấn Continue:
![image](https://github.com/user-attachments/assets/f7d5dc10-ee55-4834-822f-cde1c0cc55c5)

Ta có thể đăng nhập vào WHM bằng cách truy cập vào đường dẫn http://domain:2087 và nhập thông tin đăng nhập là user/password của VPS:
![image](https://github.com/user-attachments/assets/304363b0-5fc1-4b31-b9ba-dc73571cd8b8)

Giao diện chính của WHM:
![image](https://github.com/user-attachments/assets/74e93544-0877-4d76-a392-73713878a64f)

Để tạo account Cpanel, vào Account Functions, chọn Create a New Account:\
![image](https://github.com/user-attachments/assets/5efdee13-8a9c-4e97-ac40-c7c0b06ba176)

Điền các thông tin cần thiết và nhấn Create:
![image](https://github.com/user-attachments/assets/64b5a1c9-44a6-46f4-8ae8-9c5aa267d753)

Sau khi tạo thành công, nhấn Go to Cpanel:
![image](https://github.com/user-attachments/assets/92d07f0b-ae36-4250-b351-0cdfbf87488a)

Giao diện chính của Cpanel:
![image](https://github.com/user-attachments/assets/ca815e7c-5ff2-4323-ae55-637b86c595f5)

Như vậy ta đã cài đặt thành công WHM và Cpanel trên VPS.
