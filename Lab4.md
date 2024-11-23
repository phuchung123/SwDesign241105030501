# Thiết kế các ca sử dụng cho hệ thống "Payroll System"
## 1. Use case Login:

![](https://www.planttext.com/api/plantuml/png/X92n2i8m54NtVCKRxT0VS90wE0WEWkWgCNbj0sa2xqMbY5_cu2Vv2wOXYDI2cSBDEU5oNuzdnK5IE7TMI1KymPwH1A4AqZKMOIjxyjOUTpq7xE0c89w1WN81iurlZ2jIbkyfNhaG0KMeqGKZBMVaDq_u0SdK_GG_yG3bO2oLGcRWLAg0EQnhk4Xhz1zlr_eh896dB1dtfOr-_GXQSdloadIkDGeJc2Q92nhlOlkxgD3fEEeR003__mC0)

- Mô tả Use Case: Người dùng nhập thông tin đăng nhập, hệ thống xác thực và cho phép truy cập nếu hợp lệ.
- Tiền điều kiện:
  - Người dùng đã đăng ký tài khoản.
  - Kết nối internet.
- Luồng sự kiện chính:
  - Mở giao diện đăng nhập.
  - Nhập tên đăng nhập và mật khẩu.
  - Hệ thống kiểm tra thông tin:
    - Hợp lệ: Truy cập hệ thống.
    - Không hợp lệ: Hiển thị lỗi.
- Hậu điều kiện: Truy cập hệ thống hoặc thông báo lỗi.
- Lý do thiết kế:
  - Bảo mật: Chỉ người dùng hợp lệ truy cập.
  - Trải nghiệm: Giao diện đơn giản.
  - Hiệu quả: Truy cập nhanh chóng.
