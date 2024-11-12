# Phân tích tất cả các ca sử dụng còn lại trong hệ thống Payroll System
## I. Phân tích ca sử dụng Create Administrative Report:
### 1. Mô tả ca sử dụng:
Ca sử dụng này cho phép Quản trị viên tạo báo cáo về "Tổng số giờ làm việc" hoặc "Lương tích lũy theo năm".
### 2. Các lớp phân tích:
- Boundary Class: ReportRequestForm, ReportDisplay, ReportSaveDialog.
- Control Class: ReportController, SaveReportControl.
- Entity Class: Report, Employee.
### 3. Biểu đồ Sequence:

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/Z9DBJiCm48RtFiLSW0jaWLfHmROg4liX7YfBZbt6arOz6mkEn1MmqwHnx1QHbJsFRnw_y_FrlGg2B7rd5RRY6RPuPc_jMdV6cI2CoOW1jckbjcjuU8GT7JpBZZvx2lBikMjWl81uQ9bG27W8IanpJFSgIQdADCEVl9FK1N4J6mfXn4Mu4MA39NUEdx2pPQOsy4AEU6uFtZ6G1k_kWYVSxTPs93qxs8zKFKsjwGxcLbSR4muMpmsCXt_WyZKMhX6orEfQuitGwIxrcefMu1MFLn4XVZak-JO6hTylb0z5Ie6VizJWBgs9dswBJKNvsH-DfWlT-XR5HBtGQN3OqR9GbNwfL9dp9v4DEWnneDPycBZygTQ0o9PL5oa2gd791ahgjiWwNz1VBxK89wTLhLZ-x5Sn9Fx5lm000F__0m00)

### 4. Nhiệm vụ của các lớp phân tích:
Boundary Class:
- ReportRequestForm: Lớp này đại diện cho giao diện người dùng, nơi Quản trị viên nhập tiêu chí báo cáo, như loại báo cáo, ngày bắt đầu và kết thúc, tên nhân viên, v.v.
- ReportDisplay: Lớp này đại diện cho giao diện hiển thị báo cáo cho Quản trị viên.
- ReportSaveDialog: Lớp này đại diện cho hộp thoại lưu báo cáo, nơi Quản trị viên nhập tên và vị trí lưu.

Control Class:
- ReportController: Lớp này quản lý các quy trình tạo báo cáo, bao gồm việc xử lý tiêu chí báo cáo, tạo báo cáo theo yêu cầu, và lưu báo cáo vào hệ thống.
- SaveReportControl: Lớp này đảm bảo rằng báo cáo được lưu ở vị trí và tên do Quản trị viên chỉ định, đồng thời xác nhận quyết định lưu từ người dùng.

Entity Class:
- Report: Lớp này lưu trữ thông tin của báo cáo, bao gồm loại báo cáo, khoảng thời gian, tên nhân viên, và dữ liệu tổng hợp tương ứng.
- Employee: Lớp này đại diện cho thông tin nhân viên, bao gồm tên nhân viên và thông tin cần thiết khác để tạo báo cáo.

### 5. Biểu đồ lớp:

![Class Diagram](https://www.planttext.com/api/plantuml/png/d5HBRkCm3Dth54GspG3D1OoYw4oT0GfqKJIzW60nAG5PSYKvXL7qPBEO8_KAew_Zn6aMuuKDK--HZy-al_xylREE6zUtah4hg75B2i6z8lpIlHBS3D18RYrQ5f_mZ9qsxXdVUhJkjpOjV328bqcn1BWto1rfjMmCEJJ4AoW7wVr71NjD8dC5sKxouK5rVKowBCUVxAXkdN1ZpSnBXqiJ7wNIDoasV8yrSQbtfyh3oQDkakvZVOrMMp9jv693TehuF37kNYjdj3phMpwJQCRYJN0ASmSNt4g1GzyDD-9YtmbflUIpi6kGkTSADiwGsbs3uYsMjvbzcp5JwV1ZKkD5ZzRzTvqZ6zVAaJi_VRdm2jpGZNboA4vpxHsj8Dnp59MOnzfEwW7naQmN6-utwnowpOtjKA7nZFau5kGePTfI3f4u2eHqhl1gT9oa3OapPDg_GHaTiw_KMJPVkTNgTZvG5Iow82tP3sMK5co6FD3BFdbkNgMnPv4J5Nw11l8J7qAgdw8bvNtpS1thxmdVJsYJTGlC-H05sKRlIM2S8n39cGMRGm-w0okYdGRR-OtSaXTS1krYou5QUWGlEw_IYUn863-ofv1gPEyrbga1mPttbjtvqV8_pty0003__mC0)

Giải thích biểu đồ lớp:
- ReportRequestForm, ReportDisplay, và ReportSaveDialog là các lớp Boundary để xử lý tương tác với người dùng.
- ReportController và SaveReportControl là các lớp Control để quản lý quy trình tạo và lưu báo cáo.
- Report và Employee là các lớp Entity, lưu trữ dữ liệu báo cáo và thông tin nhân viên.
- Quan hệ giữa các lớp được chỉ định với vai trò và phương thức của từng lớp để thực hiện luồng sự kiện trong ca sử dụng.
