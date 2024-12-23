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
## II. Phân tích ca sử dụng Create Employee Report:
### 1. Mô tả ca sử dụng:
Ca sử dụng này cho phép nhân viên tạo các báo cáo bao gồm “Tổng số giờ làm việc,” “Tổng số giờ làm việc cho một dự án”, “Nghỉ phép/Nghỉ ốm,” hoặc “Tổng lương từ đầu năm đến nay”.
### 2. Các lớp phân tích:
- Boundary Class: EmployeeInterface.
- Control Class: ReportController, ReportSaveController.
- Entity Class: EmployeeReport, Project.
### 3. Biểu đồ Sequence:
![Sequence Diagram](https://www.planttext.com/api/plantuml/png/d5H1JiCm4Bpx5QkUuGCSK15Km0rH9CvRUqDDNJkiDqLz6mUUn1TO9Kr9I4jR8kKGspCxEvdrryVdE0koLCjWq4fYc2pBaDP4ninI5HtoUhjq7uMuG4l6fYYS0ZnIcLYkcwz0R2YAbnz4iz-kFd1w9Il6jDjmVZaaXmkbVQie2qW2ouH2m0tHy727GO5NUG65Dj4S1rcNT0PrWu3H0Udhb2uRWq7Wle3HKn8CS9Sgpl2SU46k9i1MxCY0FeS4JodeMIWRJBTy3zwJ_TkxJjyjZvqZln34QZaZpZNL0ALC6warWR2d5G6kq0US1VgBgyNj4oCLnrErx7BdnkSouFelgaC_TcDm3tbGGxEdw5kAn3ynWdSlywqQ7uka2NNzMEumHErQURSbSIJgSJQdAP3vDiodZ476rN-78EAIwlI7P55yYWVh_cfqFy6nUMuRw3H_b6lJFgZcASdwmbD7JJlBhTmaTJKtcDmT2ZMQ5jbrbGsYiCkYYTgX0RAKzIuPAqGlq6y0003__mC0)
### 4. Nhiệm vụ của các lớp phân tích:
Boundary Class:
- EmployeeInterface: Đóng vai trò là giao diện người dùng để nhận đầu vào từ nhân viên và hiển thị các thông tin cần thiết.

Control Class:
- ReportController: Quản lý và điều phối quy trình tạo báo cáo.
- ReportSaveController: Quản lý quy trình lưu báo cáo, bao gồm việc yêu cầu nhân viên cung cấp tên và vị trí để lưu báo cáo.

Entity Class:
- EmployeeReport: Đại diện cho báo cáo mà nhân viên tạo ra.
- Project: Đại diện cho dự án và các thông tin liên quan đến dự án (ví dụ: mã dự án).
### 5. Biểu đồ lớp:
![Class Diagram](https://www.planttext.com/api/plantuml/png/h5HBJiCm4Dtx5DxHIkq58bHLK2egLQXgAo6MLZ9fJHrFi2T54U9aB3WILy29apO_TcJXA3FZcVUUd_FpzJst90nbYMBiXYyWbXhu7MOw4YRdeHBMidBb3qcgC0TOQG8JYn3u1-F5O-0j0qjRID7G0aX8PKVZW9zHHhuYaZPL8lSL8rE-Waj37svj4FQqHBCJPnZk-ja0Uu-Q32gF5MgqVb-LKs1gi0VGO0H12yi-Jo7WEp9I7oQy56JXQW9Uh1CEEhf-Zhl0Mo9i3Bv2I2iTOm5sBItTLh6PBxGNKdy8CU6nLF0aaWOaXQ4WYRgED7HeqYq4wrE-JjpZqhN-dxaN_HyqISexyhTRLqYcVRLzd924UiJCs6Sq9uW2BZLrKyuGbPADz5buW6jm91jnAyDJDrQsseZy1OJPep_HMA6WGMVq9Aw6rrpIwgIZDfKgt9InRZze3byoyufkGPLix56cblKlt7Gwwnixu24cIQQbKm8iVvTqPBsYOcVdJ88BOpjSNnCEdBaTIZYxxXKz9sgCRD1qWvCA2rh6vkuckJ_DBm000F__0m00)

Giải thích biểu đồ lớp:
- EmployeeInterface (Boundary):
  - Chứa các phương thức như requestReportDetails() để yêu cầu nhân viên cung cấp thông tin báo cáo, displayReport() để hiển thị báo cáo, và askForSaveReportDetails() để yêu cầu lưu báo cáo.
- ReportController (Control):
  - Quản lý việc tạo báo cáo và yêu cầu thông tin từ các lớp khác. Các phương thức bao gồm:
    - generateReport(): Tạo báo cáo dựa trên loại báo cáo và thời gian.
    - requestProjectInfo(): Lấy thông tin về dự án nếu loại báo cáo yêu cầu.
    - saveReport(): Lưu báo cáo sau khi nhân viên xác nhận.
- ReportSaveController (Control):
  - Đảm nhận việc lưu báo cáo vào vị trí và tên được chỉ định. Phương thức duy nhất là saveReportToFile().
- EmployeeReport (Entity):
  - Đại diện cho báo cáo của nhân viên. Nó lưu trữ các thuộc tính như loại báo cáo, tổng số giờ làm, giờ làm cho dự án, phép nghỉ, nghỉ ốm, và tổng lương. Phương thức generateReport() để tạo báo cáo.
- Project (Entity):
  - Đại diện cho dự án và chứa thông tin về các dự án (như projectId, projectName). Phương thức getProjectInfo() trả về thông tin về các dự án.
## III. Phân tích ca sử dụng Maintain Employee Information:
### 1. Mô tả ca sử dụng:
Ca sử dụng này cho phép Quản trị viên lương (Payroll Administrator) duy trì thông tin nhân viên trong hệ thống. Công việc này bao gồm việc thêm, thay đổi, và xóa thông tin nhân viên khỏi hệ thống.
### 2. Các lớp phân tích:
- Boundary Class: Payroll Administrator Interface.
- Control Class: EmployeeController, EmployeeValidationController.
- Entity Class: Employee, EmployeeID.
### 3. Biểu đồ Sequence:
![Sequence Diagram](https://www.planttext.com/api/plantuml/png/n5JBRi8m4BpdArQSGABYpg420Qeu8A6YVe255zLgOgVE1fHlww6Vr5_enix3QHALIzLRafsTcPsD_VNnkSf8MCgJE19dCXOcHr5O4yUmbedIAYCh-FC4HEQ_HAX9KT7YJaL6c3Y0VsmGkoIDJO6uCPfAA7gQzhM7T7L-wHNssxgqtqQHCm8FZvKWBE4PttFC24oAx5SP3TErb8kNL0h2nHPZ99n55PmRFSCIZjOaAS651--spi7tpg5kxekUk7B-gGb2G-qwL6odviwDS07B6ZYTHK4zy5VFXHKGb6QlYPCRSCJZN9N45YwHX8gpm8UBaA5Fg4lR2BbMhD6sSC0UqysNSgixe0vbEPF5aaxZhPb_8F3JgxavJ4XrJxH-7MFfZkOroBxJn34F3zFVarSUNLMOaLLunUwoUZbjLPR6eWXs94WCc3mOgIx5BsHLAWt8ujbOEH0CUxuecq3k6kvAtF_u_v6uL_xZnCSpagNyy07hGB2dT13shPKfRvM6QrmkEAmLTeLQyety3G00__y30000)
### 4. Nhiệm vụ của các lớp phân tích:
Boundary Class:
- Payroll Administrator Interface: Cung cấp giao diện cho Quản trị viên lương nhập thông tin nhân viên, chọn thao tác (thêm, cập nhật, xóa).

Control Class:
- EmployeeController: Điều phối và thực thi các tác vụ nghiệp vụ theo luồng yêu cầu từ giao diện người dùng.
- EmployeeValidationController: Kiểm tra tính hợp lệ của thông tin nhập vào. Xử lý các tình huống ngoại lệ, ví dụ như thông báo lỗi khi không tìm thấy nhân viên khi cập nhật hoặc xóa.

Entity Class:
- Employee: Lưu trữ thông tin chi tiết của nhân viên, bao gồm các thuộc tính như tên, mã nhân viên, loại nhân viên, mức lương, số điện thoại, địa chỉ, v.v.
- EmployeeID: Chịu trách nhiệm tạo mã số nhân viên duy nhất khi thêm nhân viên mới vào hệ thống.
### 5. Biểu đồ lớp:
![Class Diagram](https://www.planttext.com/api/plantuml/png/Z5JBJkGm4BpdAomkm65-80S4oymXqcftnUlUs3qJQ_t8kcqWGdpP7lWaVW5xCex6aw0XXqZfgYwNs-Ly_7-_90_E1wsgwfJziC48S3sxLa1KyVHc9t-WTrOfTYMqD9Ay0syTQun7jmQE9-orOkbn-2yW-TyTHeQqvknyg6DYhdIdR8_OcBNDW93KAUZd86hjyxKrQ-bqrdfB3cFDHpE3GHmjPeaThD2Dha28Z6Rnq0dmU5WLg71QVG8bzzcD6AmSBFmmqABJ6GiJZRsDyXRvtmoiNk9uqN3CsrqPBtt_rMxp0WiSpTNirZjfDaFTWCQoafbtVNU0Q90gVbm9uP2enCXo2UeMUN3Hpg-W7z6L30ylInI1fmaSD5lVeliAx5fhS4wmjS6f_YPEhMPB6nuLxgo0YW4jQzngBOcY-fIVT7vABNszJUm6tIGM-yTHHgC8Qn6F7J8DGhCSZts39jq4l3SoNemKd76BsyEzGRLD3BMoe-huDLiiBkQJNZEPMC0ziMVfssgMLRId9Wq6DZ5LnzdpwQuP1wM8hQFDfv7n3Raqe_tcPfbdLVJFTb4SIlHSNQ8HyQ_r2G00__y30000)

Giải thích biểu đồ lớp:
- Payroll Administrator Interface: Là lớp giao diện (Boundary) tương tác với Quản trị viên lương. Lớp này cung cấp các phương thức để nhập thông tin nhân viên, yêu cầu thực hiện thao tác (thêm, cập nhật, xóa), và hiển thị kết quả.
- EmployeeController: Là lớp điều khiển (Control) chịu trách nhiệm thực hiện các tác vụ nghiệp vụ chính như thêm, cập nhật, xóa nhân viên. Nó kiểm tra tính hợp lệ của thông tin và điều phối các hành động tương ứng.
- EmployeeValidationController: Là lớp điều khiển kiểm tra tính hợp lệ của thông tin nhân viên (ví dụ: kiểm tra xem mã nhân viên có tồn tại không, dữ liệu có hợp lệ hay không).
- Employee: Là lớp thực thể (Entity) đại diện cho thông tin nhân viên. Lớp này lưu trữ các thuộc tính của nhân viên như tên, loại nhân viên, mức lương, và các thông tin khác, đồng thời cung cấp các phương thức để thêm, cập nhật và xóa thông tin.
- EmployeeID: Là lớp thực thể quản lý việc tạo mã nhân viên duy nhất. Nó cung cấp phương thức generateUniqueId() để tạo mã nhân viên mới khi thêm nhân viên vào hệ thống.
## IV. Phân tích ca sử dụng Run Payroll:
### 1. Mô tả ca sử dụng:
Ca sử dụng này mô tả cách thức trả lương được thực hiện tự động vào mỗi ngày thứ Sáu và vào ngày làm việc cuối cùng của tháng.
### 2. Các lớp phân tích:
- Boundary Class: PayrollScheduler, PaymentMethod.
- Control Class: PayrollProcessor, BankTransactionHandler.
- Entity Class: Employee, Payroll, BankTransaction.
### 3. Biểu đồ Sequence:
![Sequence Diagram](https://www.planttext.com/api/plantuml/png/X5D9RiCm3Bph5JosGFg17egWIO4UWomFe6Kc4I9B1YK7qDjww9FwXLAAcwLnO0C6R98pd26bdw_lQOZ8iMkiGXqzmoOGgrP2HfiMNOG59lRMhlIUwiuE9nViDONWRvCVJMjz8he9lgCxh1bTa7R6kqzqzN_INB9A8LAZL9O3BsztAk0LrcnsE_dgKz2BK7Ub5_XPfy1NsVSZyALGm7y-1BIao8QET8wD8cPeTMSnKcu5Jz4qf97hC86sOxt7GE2v9fP0G8kS9b2Hews94gd5GHbJU5PeYzg6P49LWjcUz461F2C25cm4qMBI1K4sq3NFt33f27DgVJ3n8U7msh8_fcmkv-6ge10z0FLqfnNdJP2hXmcovvBeQpSEZsWiLfPAVhp9eEQynGIuZVAN5rAuH8JAxv3xSWh5gvUnqccLDwTcAa2vGhy0003__mC0)
### 4. Nhiệm vụ của các lớp phân tích:
Boundary Class:
- PayrollScheduler: Lớp này quản lý lịch trình chạy bảng lương, cụ thể là việc tự động kích hoạt quá trình trả lương vào mỗi thứ Sáu và vào ngày làm việc cuối cùng của tháng.
- PaymentMethod: Lớp này chứa thông tin về phương thức thanh toán của nhân viên (ví dụ: chuyển khoản ngân hàng, trả qua thư, hoặc nhận trực tiếp).

Control Class:
- PayrollProcessor: Lớp này là trung tâm của quá trình tính toán bảng lương. Nó điều phối việc lấy thông tin về các nhân viên cần trả lương, tính toán các khoản thanh toán dựa trên các yếu tố như lương, thời gian làm việc, đơn mua hàng, quyền lợi và các khoản khấu trừ.
- BankTransactionHandler: Lớp này quản lý quá trình tạo và gửi giao dịch ngân hàng khi phương thức thanh toán là chuyển khoản.

Entity Class:
- Employee: Lớp này đại diện cho thông tin của một nhân viên trong hệ thống.
- Payroll: Lớp này đại diện cho bảng lương của một nhân viên trong một kỳ trả lương.
- BankTransaction: Lớp này đại diện cho một giao dịch ngân hàng khi thanh toán qua chuyển khoản.
### 5. Biểu đồ lớp:
![Class Diagram](https://www.planttext.com/api/plantuml/png/Z5HBJiCm4Dtd55d2eXU8K5MGa402LAcvW6jFWuK_aJsf525Ene8ZSGN6YPCwQLEnYz-ycNdpo-_tpyOZSzXebN75lC-th7LMgHr_1z4eSFbdbkSvEbbLuA9nwom7xszkiw_ivAR1u2lWknMzZ-w-oxQ6lCXt5C5K0VOGMS528GYgfj29dePF4jkegkwVqTZ7Sa2kS8H7NIlR0lWUvapnHZ448aV40JqVcFae7JEUSPJMf2NDJ4_CYB4VIyvTVKOaO6a3wwIjlP9jrte4FQbjWJrKrtEbe9P9W-7RC3thDrFCjGG9s-mL16WF1WuI_GGKDEykpnH6gO4p9mBw8ZtUbH5OnyaDKfxDmLwRNIyL1dOY6IqoHQp_o360SsP5rRX-ijtcDbfJmHUbp0OsxFO8fAgOjet1QT_8_PxpWByrUa_Ba3RwqiI8SBHI10LdXxLQhS_tkXXEpMTdjk0m3huODzsFJINf1tlPRtgVL1GWE2qDUTUzATxhPVU5MoZY8VYqYTa2UOWJjxpeBcNgELQNz2Oa6Owt4nl0UOxh8XtK3YWRJhDjA3_z-Fu0003__mC0)

Giải thích biểu đồ lớp:
- PayrollScheduler: Quản lý lịch trình và kích hoạt quá trình trả lương.
- PaymentMethod: Đại diện cho phương thức thanh toán của nhân viên, có thể là chuyển khoản ngân hàng, trả qua thư, hoặc nhận trực tiếp.
- PayrollProcessor: Xử lý toàn bộ quá trình trả lương, tính toán tiền lương và giao tiếp với các hệ thống như ngân hàng.
- BankTransactionHandler: Tạo giao dịch ngân hàng và gửi nó đến hệ thống ngân hàng. Nếu giao dịch thất bại, nó sẽ thử lại.
- BankSystem: Xử lý giao dịch ngân hàng.
- Employee: Chứa thông tin chi tiết của nhân viên như lương, quyền lợi, khấu trừ và thẻ chấm công.
- Payroll: Đại diện cho bảng lương của nhân viên trong hệ thống, chứa tổng tiền lương, các khoản khấu trừ và tiền thực nhận.
- BankTransaction: Đại diện cho giao dịch ngân hàng khi thực hiện thanh toán qua chuyển khoản.
## V. Phân tích ca sử dụng Select Payment Method:
### 1. Mô tả ca sử dụng:
Ca sử dụng này mô tả quá trình cho phép nhân viên chọn phương thức thanh toán.
### 2. Các lớp phân tích:
- Boundary Class: Employee Interface.
- Control Class: PaymentMethodController.
- Entity Class: Employee, PaymentMethod.
### 3. Biểu đồ Sequence:
![Sequence Diagram](https://www.planttext.com/api/plantuml/png/d5JDJi904BxlKqmuQG8lmC6G22OSC4JZ0mpT0JTiTylkzC2pUV2HV0LdjxHQg1ZjeOV9zpS_xSVR-omo1gvBgx1W7s1HLjOVYHGvDdo4KLk0fMCAMone11XXiLI5TnoyXT4QZwN0LyIlNjytLKiXuzQhhyA5PgFKbNiw9xPINO39dRZ259vJOeXagM3ZTb0rD2WpJmac8LlM5EOcLXQF7SvNRBoBS5EPOZ-fgp6KQEmOj0cY29eg7mtV3XXdos6_xtqAT8qndYAIFcVqi4bS20_6QQ3MqRYj3oMcd6en8Fz4N0VNnokq3EkcfSvQWJn3VeyUK6kJ7D1cFWGwr3A2dpalbKQcisw0FPm6gSX6WfKCynV_PMxXK5FaFFkqHKaJACPCk5ZX8jrU3_AdVCr-MtfEEM-MFM-M_OUy6tHxS5WIe6mCYyBNukNgSYC7VYLyvcbYYVAF3lgtEUwhaHkugPHPIbjpkYCHYn5tfFATTF6SPzXA2rSwRxyV2a5-4ArCCbKpUSk_unC00F__0m00)
### 4. Nhiệm vụ của các lớp phân tích:
Boundary Class:
- Employee Interface: Hiển thị các lựa chọn phương thức thanh toán (pick-up, mail, direct deposit) cho nhân viên.

Control Class:
- PaymentMethodController: Là lớp điều khiển chính. Nó tiếp nhận yêu cầu từ lớp biên giới và thực hiện logic.

Entity Class:
- Employee: Lưu trữ thông tin về nhân viên, bao gồm các thông tin cá nhân và thông tin về phương thức thanh toán.
- PaymentMethod: Lưu trữ thông tin về phương thức thanh toán mà nhân viên đã chọn (pick-up, mail, hoặc direct deposit).
### 5. Biểu đồ lớp:
![Class Diagram](https://www.planttext.com/api/plantuml/png/X9CzRiCm38LtdOB8v039qDLJ-ZTaQ5eWlO1YCObGMN8bkeLHz6GTUgHUeOej9vBZ89ijFfBV4wc_dz-58swfBXKh57SE7ijAcGOHlXZ07AJ8GMfglpKlCOSrMQbtxK75cn8rFI7jZTUznBzU0B13IWwpwPYghWGdJ8NbM4sV_M6aODyim2RHG4nDbL9o8Imwbvnjk7vR3UtmeZ2rfbLTRj16aTP7r-FL5p-OY68kYSNTUzoWkkquiW7FG7NdoHwGk5Gk6rBEnX7FhgMVuL8JsYqlkc422EagnPjmQyyLIQDT5WDuesjKM12Aiy55dYs-r-WEZkIX1bTBlJMHPdn0zqQJDKgX3JokRPKsmi2U7rt4VA7noQ1lssSikrMTdZAZxUgFhZMRmRNDEpwG-HmcDvF13kQmvuwT3s1C7Dr7IuwM5-JWKzAUNHA6EaU8FFXprpA6c7qQMw0M_ld_0m00__y30000)

Giải thích biểu đồ lớp:
- Employee: Lớp này chứa các thuộc tính của nhân viên (id, name, paymentMethod) và các phương thức để lấy và cập nhật phương thức thanh toán.
- PaymentMethod: Lớp này đại diện cho phương thức thanh toán của nhân viên, bao gồm các thuộc tính như loại phương thức thanh toán (type), địa chỉ nhận thư (address), tên ngân hàng và số tài khoản (bankName, accountNumber).
- EmployeeInterface: Lớp này cung cấp giao diện cho nhân viên để chọn phương thức thanh toán, yêu cầu thông tin bổ sung nếu cần và hiển thị các lựa chọn.
- PaymentMethodController: Lớp điều khiển này chịu trách nhiệm xử lý logic liên quan đến phương thức thanh toán, bao gồm việc yêu cầu thông tin nhân viên, chọn phương thức thanh toán và cập nhật thông tin nhân viên trong hệ thống.
# Code Java mô phỏng ca sử dụng Maintain Timecard
## 1. Timecard Class:
Lớp này sẽ đại diện cho thẻ chấm công của nhân viên, bao gồm các phương thức để thêm giờ làm, kiểm tra tính hợp lệ của giờ làm và nộp thẻ chấm công.

public class Timecard {

    private String employeeId;
    private String startDate;
    private String endDate;
    private Map<String, Integer> chargeNumbers; // chargeNumber -> hours worked
    private boolean submitted;

    public Timecard(String employeeId, String startDate, String endDate) {
        this.employeeId = employeeId;
        this.startDate = startDate;
        this.endDate = endDate;
        this.chargeNumbers = new HashMap<>();
        this.submitted = false;
    }

    public boolean addHours(String chargeNumber, int hours) {
        if (submitted) {
            System.out.println("Timecard already submitted, cannot modify hours.");
            return false;
        }
        if (hours < 0 || hours > 24) {
            System.out.println("Invalid hours entered, please enter a valid number of hours.");
            return false;
        }
        chargeNumbers.put(chargeNumber, hours);
        return true;
    }

    public boolean submitTimecard() {
        if (submitted) {
            System.out.println("Timecard has already been submitted.");
            return false;
        }
        submitted = true;
        System.out.println("Timecard submitted successfully.");
        return true;
    }

    public boolean isSubmitted() {
        return submitted;
    }

    public void printTimecard() {
        System.out.println("Timecard for Employee: " + employeeId);
        for (Map.Entry<String, Integer> entry : chargeNumbers.entrySet()) {
            System.out.println("Charge Number: " + entry.getKey() + ", Hours Worked: " + entry.getValue());
        }
    }
}

## 2. Employee Class:
Lớp này đại diện cho nhân viên, có thể tạo thẻ chấm công, thêm giờ làm và nộp thẻ chấm công.

public class Employee {

    private String employeeId;
    private Timecard currentTimecard;

    public Employee(String employeeId) {
        this.employeeId = employeeId;
    }

    public void createTimecard(String startDate, String endDate) {
        if (currentTimecard != null && !currentTimecard.isSubmitted()) {
            System.out.println("Cannot create a new timecard until the current one is submitted.");
        } else {
            currentTimecard = new Timecard(employeeId, startDate, endDate);
            System.out.println("New timecard created.");
        }
    }

    public boolean addHours(String chargeNumber, int hours) {
        if (currentTimecard == null) {
            System.out.println("No timecard available. Please create a timecard first.");
            return false;
        }
        return currentTimecard.addHours(chargeNumber, hours);
    }

    public boolean submitTimecard() {
        if (currentTimecard == null) {
            System.out.println("No timecard available to submit.");
            return false;
        }
        return currentTimecard.submitTimecard();
    }

    public void printTimecard() {
        if (currentTimecard != null) {
            currentTimecard.printTimecard();
        } else {
            System.out.println("No timecard available.");
        }
    }
}

## 3. Hàm Main:

public class Main {

    public static void main(String[] args) {
    
        // Tạo một đối tượng Scanner để đọc dữ liệu từ bàn phím
        Scanner scanner = new Scanner(System.in);

        // Tạo một nhân viên mới
        System.out.println("Enter employee ID:");
        String employeeId = scanner.nextLine();
        Employee employee = new Employee(employeeId);

        // Nhân viên tạo thẻ chấm công cho kỳ lương
        System.out.println("Enter start date for the timecard (YYYY-MM-DD):");
        String startDate = scanner.nextLine();
        System.out.println("Enter end date for the timecard (YYYY-MM-DD):");
        String endDate = scanner.nextLine();
        employee.createTimecard(startDate, endDate);

        // Nhân viên thêm giờ làm cho các dự án khác nhau
        while (true) {
            System.out.println("Do you want to enter hours for a project? (yes/no)");
            String choice = scanner.nextLine();
            if (choice.equalsIgnoreCase("no")) {
                break;
            }

            System.out.println("Enter charge number (e.g., P001):");
            String chargeNumber = scanner.nextLine();
            System.out.println("Enter hours worked for " + chargeNumber + ":");
            int hours = scanner.nextInt();
            scanner.nextLine();  // consume newline
            if (!employee.addHours(chargeNumber, hours)) {
                System.out.println("Invalid hours. Please try again.");
            }
        }

        // In thẻ chấm công trước khi nộp
        employee.printTimecard();

        // Nhân viên nộp thẻ chấm công
        System.out.println("Do you want to submit the timecard? (yes/no)");
        String submitChoice = scanner.nextLine();
        if (submitChoice.equalsIgnoreCase("yes")) {
            employee.submitTimecard();
        }

        // Cố gắng chỉnh sửa thẻ chấm công sau khi đã nộp
        System.out.println("Do you want to make any more changes after submission? (yes/no)");
        String changeChoice = scanner.nextLine();
        if (changeChoice.equalsIgnoreCase("yes")) {
            System.out.println("You cannot modify the timecard after it has been submitted.");
        }

        // In thẻ chấm công sau khi nộp
        employee.printTimecard();

        // Đóng scanner
        scanner.close();
    }
}
