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
- ReportRequestForm: Lớp này đại diện cho giao diện người dùng, nơi Quản trị viên Bảng lương nhập tiêu chí báo cáo, như loại báo cáo, ngày bắt đầu và kết thúc, tên nhân viên, v.v.
- ReportDisplay: Lớp này đại diện cho giao diện hiển thị báo cáo cho Quản trị viên Bảng lương.
- ReportSaveDialog: Lớp này đại diện cho hộp thoại lưu báo cáo, nơi Quản trị viên Bảng lương nhập tên và vị trí lưu.
