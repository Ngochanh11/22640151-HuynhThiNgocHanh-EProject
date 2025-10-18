🧩 1. Kiến trúc dự án

<img width="365" height="758" alt="image" src="https://github.com/user-attachments/assets/9b8d8385-528d-43fc-8e26-d0a0fad1c52a" />

Mô tả tổng thể:

Dự án được xây dựng theo kiến trúc microservices, gồm 4 dịch vụ chính:

api-gateway: Cổng giao tiếp trung tâm, định tuyến request đến các service.

auth: Xử lý xác thực người dùng (login, register, JWT, v.v.)

product: Quản lý thông tin sản phẩm.

order: Xử lý đơn hàng, kết nối với auth và product.

utils: Chứa các hàm tiện ích dùng chung giữa các service (như middleware isAuthenticated.js).

Dự án có tệp docker-compose.yml, cho phép chạy toàn bộ hệ thống bằng Docker, dễ dàng triển khai và quản lý container cho từng service.

⚙️ 2. Công nghệ sử dụng

<img width="817" height="471" alt="image" src="https://github.com/user-attachments/assets/6eb1081d-e56a-490c-89c3-1f7b9561c25a" />

🧩3. Tạo các file .env

+ auth service

<img width="544" height="110" alt="image" src="https://github.com/user-attachments/assets/7945cb64-c073-4fa7-93a5-c03fec2fbc5b" />

+ order service

<img width="636" height="170" alt="image" src="https://github.com/user-attachments/assets/19f87bee-a258-4fa5-8b8f-c446a5e37a59" />

+ product service

<img width="636" height="207" alt="image" src="https://github.com/user-attachments/assets/0ae4b982-7b67-48c9-9b0d-08591528b6f6" />

+ .env cho thư mục gốc

<img width="380" height="90" alt="image" src="https://github.com/user-attachments/assets/fd9dc43c-921e-4615-b167-aaf6dfb2246c" />

🧩 4. Kiểm tra trạng thái container

GÕ lệnh : docker compose ps

🧩 5. Test các API bằng Postman

Request: POST http://localhost:3003/auth/register → Đăng ký tài khoản

Request: POST http://localhost:3003/auth/login → Đăng nhập và nhận Token
