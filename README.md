🧩 1. Kiến trúc dự án

<img width="365" height="758" alt="image" src="https://github.com/user-attachments/assets/9b8d8385-528d-43fc-8e26-d0a0fad1c52a" />

Mô tả tổng thể Project:

Hệ thống áp dụng mô hình Microservices gồm 4 dịch vụ chính: Auth, Product, Order và API Gateway. 

Gateway nhận request từ client và định tuyến đến từng service.

Các service giao tiếp nội bộ qua REST và RabbitMQ, lưu dữ liệu trong MongoDB.

Hệ thống dùng các mẫu thiết kế như Microservices, MVC, Service Layer, Repository, Middleware và Gateway Pattern để tách biệt chức năng, tăng khả năng mở rộng và bảo trì.

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

🧩 4. Build Project lên docker test

- Tiến hành gõ lệnh sau vào terminal: docker compose up

- Sau đó project được push lên docker test với các container sau:

<img width="1542" height="506" alt="image" src="https://github.com/user-attachments/assets/f6568d4b-2f2b-47e1-a589-6b8499851c92" />

🧩 5. Kiểm tra trạng thái container

GÕ lệnh : docker compose ps

🧩 6. Test các API bằng Postman

Request: POST http://localhost:3003/auth/register → Đăng ký tài khoản

<img width="1264" height="903" alt="image" src="https://github.com/user-attachments/assets/facb3a41-2fce-4b20-91b7-34d8855e4728" />

Request: POST http://localhost:3003/auth/login → Đăng nhập và nhận Token

<img width="1624" height="901" alt="image" src="https://github.com/user-attachments/assets/272253f4-45e1-421b-aae1-ab3028507024" />

Request: POST http://localhost:3003/products/api/products → Xác thực Token và tiến hành nhập thông tin để thêm product

<img width="1175" height="904" alt="image" src="https://github.com/user-attachments/assets/544a51e8-58ce-4ac6-9534-6eba096f6e9e" />

Request: GET http://localhost:3003/products/api/products → Xác thực Token và nhấn send để xem danh sách tất cả product

<img width="1278" height="923" alt="image" src="https://github.com/user-attachments/assets/1fdd2b50-f0a3-471a-a2e0-a6dde5e17a1f" />

Request: POST http://localhost:3003/products/api/products/buy → Xác thực Token và tiến hành nhập id sản phẩm để tiến hành đặt hàng

<img width="1324" height="829" alt="image" src="https://github.com/user-attachments/assets/e2e5f21b-ad42-4c10-b58e-940aeece918f" />

🧩7. Thêm endpoint id 

- Trong productController.js

<img width="664" height="383" alt="image" src="https://github.com/user-attachments/assets/f0ea768e-6de0-4020-b5d7-06d37e395df9" />

- Trong productRoutes.js

  <img width="616" height="26" alt="image" src="https://github.com/user-attachments/assets/913d1f00-501e-452d-874d-879dd44136bc" />

- Test endpoint id sau khi thêm mã code vào 2 file trên:

Request: GET http://localhost:3003/products/api/products/.....(id) → Xác thực Token nhấn send để tìm sản phẩm theo id

<img width="1289" height="759" alt="image" src="https://github.com/user-attachments/assets/be20f168-7d96-4e68-8d71-2e3fe684b92a" />

