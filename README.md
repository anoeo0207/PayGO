# 🪙 PayGO - Hệ thống Ví Điện Tử Thông Minh

![PayGO](image/PayGO)


## 📌 Tổng quan

**PayGO** là một hệ thống ví điện tử được xây dựng để phục vụ người dùng tại Việt Nam trong việc thực hiện các giao dịch tài chính hàng ngày một cách **nhanh chóng**, **an toàn** và **thuận tiện**. Hệ thống được phát triển bởi sinh viên Trường Đại học Công nghệ - ĐHQGHN, trong khuôn khổ môn học **Công nghệ phần mềm**.

PayGO không chỉ cung cấp các chức năng cơ bản như nạp/rút tiền, chuyển khoản mà còn tích hợp các dịch vụ như **thanh toán hóa đơn**, **mua vé tàu/xe/phim**, **nạp tiền điện thoại** và **hỗ trợ khách hàng 24/7**.

---

## 🎯 Mục tiêu & Phạm vi

- Phát triển hệ thống ví điện tử đa nền tảng (iOS & Android)
- Hướng tới trải nghiệm người dùng mượt mà, thân thiện
- Đảm bảo hiệu năng cao và bảo mật cấp doanh nghiệp
- Dễ dàng tích hợp với ngân hàng và nhà cung cấp dịch vụ

---

## ⚙️ Tính năng chính

### 🧑‍💼 Quản lý người dùng
- Đăng ký tài khoản (mật khẩu & sinh trắc học)
- Đăng nhập bằng mật khẩu hoặc vân tay/Face ID
- Cập nhật hồ sơ người dùng

### 💰 Quản lý ví
- Xem số dư tài khoản
- Xem lịch sử giao dịch (lọc theo ngày)
- Thống kê chi tiêu theo loại giao dịch

### 💸 Giao dịch tài chính
- Liên kết ngân hàng (Vietcombank, BIDV, MB...)
- Nạp tiền từ tài khoản ngân hàng
- Rút tiền về tài khoản ngân hàng
- Chuyển tiền tới ví PayGO khác (P2P)

### 🧾 Dịch vụ thanh toán
- Thanh toán hóa đơn: điện, nước, Internet
- Mua vé: tàu, xe khách, rạp chiếu phim
- Nạp tiền điện thoại

### 📞 Hỗ trợ khách hàng
- Hệ thống IVR tự động 24/7
- Gửi yêu cầu hỗ trợ trực tiếp qua app

---

## 🧠 Kiến trúc hệ thống

Hệ thống được xây dựng theo kiến trúc **Microservices** kết hợp **Domain-Driven Design**:

- **Mobile App** (Flutter): Giao diện người dùng iOS & Android
- **API Gateway**: Xác thực, định tuyến, giới hạn tốc độ
- **Core Services**:
  - IAM: Quản lý người dùng & xác thực
  - Wallet Engine: Quản lý số dư & giao dịch
  - Payment Service: Xử lý thanh toán hóa đơn/vé
  - Support Service: Tiếp nhận yêu cầu khách hàng
- **Integration Layer**:
  - Bank Gateway
  - Bill/Ticket Provider Gateway
  - Notification Service
- **Foundational Layer**:
  - Message Queue: Kafka/RabbitMQ
  - Cache: Redis
  - Monitoring: Prometheus + Grafana
  - Logging: ELK Stack
- **Database Layer**:
  - PostgreSQL/MongoDB

---

## 🧱 Cơ sở dữ liệu

### 🔗 Các bảng chính:
- `users`, `user_profiles`, `biometric_data`
- `wallets`, `transactions`
- `bank_accounts`
- `bills`, `tickets`, `service_providers`
- `support_tickets`, `notifications`
- `security_logs`

### 📋 Quan hệ:
- 1 user ↔ 1 wallet
- 1 wallet ↔ N transactions
- 1 user ↔ N support tickets, N notifications
- 1 user ↔ N bank accounts
- 1 bill/ticket ↔ 1 transaction ↔ 1 wallet

Tối ưu cho truy vấn nhanh & bảo mật cao bằng cách phân tách dữ liệu nhạy cảm và sử dụng chuẩn hóa 3NF.

---

## 🛡️ Bảo mật & Quy định

- **MFA**: Bảo mật đa lớp khi đăng nhập & xác thực giao dịch
- **Mã hóa AES-256 + TLS 1.3**: Cho dữ liệu lưu trữ & truyền tải
- **Firewall & SIEM**: Giám sát & ngăn chặn tấn công
- **Tuân thủ**: PCI-DSS, ISO 27001, GDPR (bảo vệ dữ liệu cá nhân)

---

## 📈 Yêu cầu phi chức năng

| Yêu cầu                        | Chi tiết |
|-------------------------------|----------|
| Hiệu năng                     | 10.000 giao dịch/giây, 95% trong 2 giây |
| Tính sẵn sàng                 | Uptime 99.99% (~5 phút/ngày) |
| Khả năng mở rộng              | Auto-scaling, hỗ trợ 10 triệu người dùng |
| Dịch vụ khách hàng            | Hỗ trợ 24/7, phản hồi trong 1 giờ |
| Tương thích thiết bị          | Android 8+, iOS 12+ |

---

## 🖼️ Giao diện người dùng (UI/UX)

Xem thiết kế Figma: 👉 [PayGO UI Prototype](https://www.figma.com/design/c1cS4apvMoKknq123ITiHI/SONIX?node-id=0-1&t=ESFkuWxjIqGdTs5p-1)

Giao diện trực quan, thao tác đơn giản, hỗ trợ tiếng Việt.

---

## 👨‍💻 Nhóm phát triển

- Nguyễn Hải An - 23020581
- Lê Hoàng Anh - 23020583
- Vũ Quốc Anh - 23020587
- Ngô Thị Thảo Linh - 23020620

---

## 📄 Giấy phép

Dự án phục vụ mục đích học tập tại Trường Đại học Công nghệ - ĐHQGHN.

---


