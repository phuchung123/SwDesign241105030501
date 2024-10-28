# Tài liệu hợp nhất phân tích hệ thống Payroll System

## 1. Kiến trúc đề xuất:

Kiến trúc 3 tầng (Three-Tier Architecture) là một mô hình phổ biến trong phát triển phần mềm, đặc biệt trong các hệ thống lớn như Payroll System. Kiến trúc này giúp phân tách nhiệm vụ giữa các thành phần, giúp hệ thống dễ bảo trì, dễ mở rộng, và dễ quản lý hơn. 

Các tầng trong hệ thống:
- Tầng giao diện (Presentation Layer): Đây là tầng mà người dùng trực tiếp tương tác với hệ thống. Tầng này chịu trách nhiệm hiển thị thông tin, nhận đầu vào và xác minh dữ liệu từ người dùng.
- Tầng xử lý nghiệp vụ (Business Logic Layer): Tầng này chịu trách nhiệm xử lý toàn bộ nghiệp vụ và logic của hệ thống. Nó sẽ xử lý các yêu cầu từ tầng giao diện, thực hiện các phép tính và xử lý logic liên quan đến tính lương, giờ làm, doanh số bán hàng, và quản lý thông tin nhân viên.
- Tầng dữ liệu (Data Layer): Tầng này quản lý việc lưu trữ và truy xuất dữ liệu, bao gồm thông tin nhân viên, thông tin dự án, thông tin lương, và các bảng dữ liệu liên quan.

Giải thích lý do lựa kiến trúc: 
- Khả năng mở rộng và bảo trì: Khi có sự thay đổi về giao diện người dùng, hoặc khi cần cập nhật logic tính lương, hệ thống có thể dễ dàng sửa đổi mà không cần ảnh hưởng đến toàn bộ hệ thống.
- Tăng cường bảo mật: Việc tách biệt tầng giao diện với tầng xử lý nghiệp vụ và tầng dữ liệu giúp giảm nguy cơ bị tấn công, vì dữ liệu chỉ có thể được truy cập qua các lớp nghiệp vụ.
- Phân tách nhiệm vụ rõ ràng: Mỗi tầng đảm nhận một nhiệm vụ cụ thể, giảm sự phụ thuộc giữa các thành phần, giúp dễ bảo trì và cập nhật khi có thay đổi.

Ý nghĩa của từng thành phần trong kiến trúc: 
- Presentation Layer (Tầng giao diện): Tầng này sẽ bao gồm các form, bảng điều khiển, và giao diện báo cáo mà nhân viên có thể sử dụng để tương tác với hệ thống. Đồng thời, tầng này cũng giúp kiểm tra tính hợp lệ của dữ liệu trước khi gửi về tầng logic.
- Business Logic Layer (Tầng xử lý nghiệp vụ): Tầng này sẽ thực hiện các chức năng như kiểm tra thông tin thời gian làm việc, tính lương cho nhân viên theo từng loại (giờ công, lương cố định, có hoa hồng), tính các khoản thưởng hoặc phụ cấp, và tạo ra các báo cáo tài chính cho quản lý. Hệ thống cũng sẽ phải đảm bảo tính năng bảo mật để chỉ cho phép nhân viên truy cập vào thông tin của riêng họ.
- Data Layer (Tầng dữ liệu): Tầng này sẽ chứa các hoạt động tương tác với cơ sở dữ liệu, như lấy thông tin thời gian làm việc, chi tiết lương và đơn đặt hàng của nhân viên từ các bảng liên quan. Nó đảm bảo rằng tất cả các thông tin về nhân viên, lương, thời gian làm việc, và mã chi phí được lưu trữ an toàn và sẵn sàng cho việc truy xuất.

Biểu đồ kiến trúc của hệ thống Payroll System:

![Package Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWbB8mrtByz8Lt3CJynLSCX_kRizJKgZcKW02k18aEGM_z6CR7kwUcwdWSdXdNhgIGcAnGa1HQd5gNabYIMP-dazYPMgHWerD3eYsi-EgvSAmAUBXxhKAFeVt0etA09bPe13sSFTI34jnAGDQw5HQd9cNMbpiav-UcKo4ZIuFTwzNy04PKefXJKXHQQM2yyDTQmjGbG6jSKaiISHYEXRlwkhQON4K5pPtWfJ23UPoICrB0SO60000__y30000)



