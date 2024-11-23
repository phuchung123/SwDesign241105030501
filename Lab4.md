# Thiết kế các ca sử dụng cho hệ thống "Payroll System"
## 1. Login:

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

## 2. Maintain Timecard:

![](https://www.planttext.com/api/plantuml/png/X94n2i9G38RtdYAZ3bx0GGfQi9jGq3csh_BmlQIagV0GJ-RWaRo2RQs3KZLZllzB2BbVRt6jADfu5s6kB93uod4m9XAJAzB16TXW47Ok2xKQ3-S8sdh5OBQ0ITQDW1tB4TRSI0q9gOHf7_m6Up6bgdbZAPKi7jKo3VhFI3zaoLHQyO1KGDRilTL17G6zi4Ld2rGpicqK3JUoVBJda9Pmwen_yihMbSC0YGZB85fwgfSeDbIq3tW0003__mC0)

- Mô tả Use Case:
  - Nhập giờ làm việc vào hệ thống Payroll: Nhân viên nhập giờ làm việc và hệ thống xác thực, lưu trữ nếu hợp lệ.
- Tiền điều kiện:
  - Tài khoản nhân viên.
  - Kết nối internet.
- Luồng sự kiện chính:
  - Mở giao diện nhập giờ.
  - Nhập thông tin giờ làm việc.
  - Xác nhận và gửi.
- Kiểm tra:
  - Hợp lệ: Lưu trữ thông tin.
  - Không hợp lệ: Thông báo lỗi.
- Hậu điều kiện: Lưu trữ thành công hoặc thông báo lỗi.
- Lý do thiết kế:
  - Hiệu quả: Nhập thông tin nhanh chóng.
  - Độ chính xác: Xác thực trước khi lưu trữ.
  - Trải nghiệm: Giao diện dễ sử dụng.
  - Bảo mật: Chỉ nhân viên có quyền truy cập.

## 3. Run Payroll:

![](https://www.planttext.com/api/plantuml/png/V951Ri9034NtESKNArXmWIug49jMQgMA25XR4qEd39d8uu0YnCbOS2Ikm2GCg6fflVH_tz-opyVJA2Y9rXkNaL4lUAUILYoPi54gLuxH-w16l7F8cw2ywM6V8LO2CNn6FszdOE5bZHTVIy2ugiHloGqwz1-ziyyjxp1buwN0cmsQNB_QronsSJNa5Hkxj2O1jw37OcUSVB9POqxE5bQRPFZHxC3hSZp04rwNsBRQt_2Kls9YOctvZRwFQR5PLP0ouY6q3YdxPdsW7x8HbqNyoWK00F__0m00)

- Mô tả Use Case:
  - Phê duyệt giờ làm việc: Quản lý kiểm tra và phê duyệt giờ làm việc của nhân viên.
- Tiền điều kiện:
  - Tài khoản quản lý.
  - Kết nối internet.
- Luồng sự kiện chính:
  - Bắt đầu phê duyệt.
  - Xem danh sách bản ghi.
  - Chọn bản ghi.
  - Kiểm tra tính hợp lệ:
    - Hợp lệ: Phê duyệt và cập nhật trạng thái.
    - Không hợp lệ: Thông báo lỗi.
- Hậu điều kiện: Giờ làm việc được phê duyệt hoặc thông báo lỗi.
- Lý do thiết kế:
  - Hiệu quả: Phê duyệt nhanh chóng.
  - Trải nghiệm: Giao diện thân thiện.
  - Bảo mật: Chỉ quản lý có quyền.
