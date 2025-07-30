## Kế hoạch triển khai Docker hóa ứng dụng

### Tuần 1: Chuẩn bị và Docker hóa cơ bản

#### Mục tiêu:

- **Hiểu rõ cấu trúc dự án hiện tại trên VPS.**
- **Cài đặt Docker và Docker Compose trên môi trường phát triển.**
- **Tạo Dockerfile cho từng thành phần (Frontend, Backend).**
- **Chạy thử các container riêng lẻ.**

#### Tìm hiểu kiến thức liên quan quan trọng:

- **Khái niệm cơ bản về Docker:** Nắm vững các thành phần cốt lõi như **Images**, **Containers**, **Volumes**, và **Networks** . Hiểu cách chúng hoạt động và tương tác với nhau.
- **Cú pháp Dockerfile:** Làm quen với các chỉ thị Dockerfile thiết yếu như `FROM` , `WORKDIR` , `COPY` , `RUN` , `EXPOSE` , và `CMD` .
- **Cơ chế hoạt động của Frontend (React) và Backend (Node.js):** Hiểu rõ cách ứng dụng React được build và phục vụ file tĩnh, cũng như cách Node.js Backend xử lý request và cung cấp API. Nắm được các phụ thuộc và cách chúng giao tiếp.

---

### Tuần 2: Docker Compose và Tích hợp MongoDB

#### Mục tiêu:

- **Sử dụng Docker Compose để định nghĩa và chạy tất cả các service cùng nhau (Frontend, Backend, MongoDB).**
- **Thiết lập kết nối giữa các service trong mạng Docker.**
- **Cấu hình môi trường (environment variables) cho ứng dụng.**

#### Tìm hiểu kiến thức liên quan quan trọng:

- **Cú pháp Docker Compose (`docker-compose.yml`):** Học cách định nghĩa nhiều service trong một file duy nhất, bao gồm `services`, `networks`, `volumes`, `environment`, và `depends_on`.
- **Mạng trong Docker:** Hiểu cách các container trong cùng một Docker Compose project có thể giao tiếp với nhau bằng **tên service** thông qua bridge network mặc định.
- **Quản lý dữ liệu với Docker Volumes:** Nắm được tầm quan trọng của Docker Volumes trong việc lưu trữ dữ liệu bền vững cho các database như MongoDB, tránh mất dữ liệu khi container bị xóa hoặc cập nhật.
- **Các biến môi trường trong Docker:** Tìm hiểu cách truyền các biến môi trường (ví dụ: thông tin kết nối database, khóa API) vào container một cách an toàn và linh hoạt.

---

### Tuần 3: Triển khai trên VPS và cấu hình Nginx Production

#### Mục tiêu:

- **Triển khai ứng dụng đã Docker hóa lên môi trường VPS Ubuntu.**
- **Cấu hình Nginx làm reverse proxy và quản lý tên miền.**
- **Cấu hình SSL/TLS với Certbot (Let's Encrypt).**

#### Tìm hiểu kiến thức liên quan quan trọng:

- **Lệnh cơ bản của Linux (Ubuntu):** Làm quen với các lệnh quản lý hệ thống như `sudo apt update`, `sudo apt upgrade` (cập nhật hệ thống), `sudo systemctl` (quản lý dịch vụ), và `sudo ufw` (quản lý tường lửa) để chuẩn bị môi trường VPS.
- **Khái niệm Reverse Proxy:** Hiểu vai trò của Nginx như một proxy ngược, định tuyến các yêu cầu từ internet đến các service Backend và Frontend đang chạy trong Docker.
- **Cấu hình Nginx cơ bản:** Học cách viết các cấu hình Nginx thông qua `server block` (khối máy chủ), `location block` (khối vị trí), và `proxy_pass` (chuyển tiếp yêu cầu) để xử lý tên miền và định tuyến lưu lượng.
- **Chứng chỉ SSL/TLS và HTTPS:** Nắm được tầm quan trọng của HTTPS trong việc bảo mật dữ liệu truyền tải và cách chứng chỉ SSL/TLS hoạt động.
- **Certbot và Let's Encrypt:** Tìm hiểu cách sử dụng Certbot để tự động hóa quá trình cấp phát và gia hạn chứng chỉ SSL/TLS miễn phí từ Let's Encrypt, giúp website của bạn an toàn hơn.
