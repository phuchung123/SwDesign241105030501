# Tài liệu hợp nhất phân tích hệ thống Payroll System

## 1. Kiến trúc đề xuất:

Kiến trúc 3 tầng (Three-Tier Architecture) là một lựa chọn phù hợp cho hệ thống tính lương (Payroll System) vì nó cung cấp sự phân tách rõ ràng giữa các thành phần, giúp dễ dàng bảo trì, mở rộng và bảo mật.

Các tầng trong hệ thống:
- Tầng giao diện (Presentation Layer): Đây là tầng mà người dùng trực tiếp tương tác với hệ thống. Trong Payroll System, tầng giao diện sẽ là ứng dụng Windows-based desktop cho phép nhân viên nhập thông tin thẻ chấm công, tạo đơn đặt hàng, thay đổi tùy chọn thanh toán, và tạo các báo cáo.
- Tầng xử lý nghiệp vụ (Business Logic Layer): Tầng này chứa toàn bộ logic nghiệp vụ của hệ thống, xử lý các quy tắc liên quan đến tính lương, tính hoa hồng, quản lý các loại nhân viên (theo giờ, hưởng lương cố định, có hoa hồng), và tạo các báo cáo.
- Tầng dữ liệu (Data Layer): Tầng dữ liệu chịu trách nhiệm lưu trữ và quản lý dữ liệu của hệ thống, bao gồm thông tin nhân viên, thông tin chấm công, thông tin thanh toán và dữ liệu bán hàng.
