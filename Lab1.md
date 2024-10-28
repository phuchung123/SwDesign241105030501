# Tài liệu hợp nhất phân tích hệ thống Payroll System

## 1. Kiến trúc đề xuất:

Kiến trúc 3 tầng (Three-Tier Architecture) là một mô hình phổ biến trong phát triển phần mềm, đặc biệt trong các hệ thống lớn như Payroll System. Kiến trúc này giúp phân tách nhiệm vụ giữa các thành phần, giúp hệ thống dễ bảo trì, dễ mở rộng, và dễ quản lý hơn. 

Các tầng trong hệ thống:
- Tầng giao diện (Presentation Layer): Đây là tầng mà nhân viên trực tiếp tương tác với hệ thống. Tầng này chịu trách nhiệm hiển thị thông tin, nhận đầu vào và xác minh dữ liệu từ nhân viên.
- Tầng xử lý nghiệp vụ (Business Logic Layer): Tầng này chịu trách nhiệm xử lý toàn bộ nghiệp vụ và logic của hệ thống. Nó sẽ xử lý các yêu cầu từ tầng giao diện, thực hiện các phép tính và xử lý logic liên quan đến tính lương, giờ làm, doanh số bán hàng, và quản lý thông tin nhân viên.
- Tầng dữ liệu (Data Layer): Tầng này quản lý việc lưu trữ và truy xuất dữ liệu, bao gồm thông tin nhân viên, thông tin dự án, thông tin lương, và các bảng dữ liệu liên quan.

Giải thích lý do lựa kiến trúc: 
- Khả năng mở rộng và bảo trì: Khi có sự thay đổi về giao diện nhân viên, hoặc khi cần cập nhật logic tính lương, hệ thống có thể dễ dàng sửa đổi mà không cần ảnh hưởng đến toàn bộ hệ thống.
- Tăng cường bảo mật: Việc tách biệt tầng giao diện với tầng xử lý nghiệp vụ và tầng dữ liệu giúp giảm nguy cơ bị tấn công, vì dữ liệu chỉ có thể được truy cập qua các lớp nghiệp vụ.
- Phân tách nhiệm vụ rõ ràng: Mỗi tầng đảm nhận một nhiệm vụ cụ thể, giảm sự phụ thuộc giữa các thành phần, giúp dễ bảo trì và cập nhật khi có thay đổi.

Ý nghĩa của từng thành phần trong kiến trúc: 
- Presentation Layer (Tầng giao diện): Tầng này sẽ bao gồm các form, bảng điều khiển, và giao diện báo cáo mà nhân viên có thể sử dụng để tương tác với hệ thống. Đồng thời, tầng này cũng giúp kiểm tra tính hợp lệ của dữ liệu trước khi gửi về tầng logic.
- Business Logic Layer (Tầng xử lý nghiệp vụ): Tầng này sẽ thực hiện các chức năng như kiểm tra thông tin thời gian làm việc, tính lương cho nhân viên theo từng loại (giờ công, lương cố định, có hoa hồng), tính các khoản thưởng hoặc phụ cấp, và tạo ra các báo cáo tài chính cho quản lý. Hệ thống cũng sẽ phải đảm bảo tính năng bảo mật để chỉ cho phép nhân viên truy cập vào thông tin của riêng họ.
- Data Layer (Tầng dữ liệu): Tầng này sẽ chứa các hoạt động tương tác với cơ sở dữ liệu, như lấy thông tin thời gian làm việc, chi tiết lương và đơn đặt hàng của nhân viên từ các bảng liên quan. Nó đảm bảo rằng tất cả các thông tin về nhân viên, lương, thời gian làm việc, và mã chi phí được lưu trữ an toàn và sẵn sàng cho việc truy xuất.

Biểu đồ kiến trúc của hệ thống Payroll System:

![Package Diagram](https://www.planttext.com/api/plantuml/png/UhzxlqDnIM9HIMbk3bT1Od9sOdggWbB8mrtByz8Lt3CJynLSCX_kRizJKgZcKW02k18aEGM_z6CR7kwUcwdWSdXdNhgIGcAnGa1HQd5gNabYIMP-dazYPMgHWerD3eYsi-EgvSAmAUBXxhKAFeVt0etA09bPe13sSFTI34jnAGDQw5HQd9cNMbpiav-UcKo4ZIuFTwzNy04PKefXJKXHQQM2yyDTQmjGbG6jSKaiISHYEXRlwkhQON4K5pPtWfJ23UPoICrB0SO60000__y30000)

## 2. Cơ chế phân tích:

Dưới đây là một vài cơ chế phân tích có thể áp dụng cho Payroll System là: 
- Authorization and access control: Để đảm bảo tính bảo mật, hệ thống cần có cơ chế phân quyền truy cập. nhân viên chỉ có thể xem và chỉnh sửa các thông tin cá nhân của mình.
- Multi-factor Authentication (MFA): Để tăng cường bảo mật, đặc biệt là cho dữ liệu nhạy cảm về tài chính, hệ thống nên áp dụng xác thực đa yếu tố. Điều này giúp ngăn chặn việc truy cập trái phép từ bên ngoài hoặc từ các nhân viên không có quyền.
- Backup and Recovery: Để đảm bảo tính liên tục của hệ thống, cần xây dựng cơ chế sao lưu tự động cho các bản ghi về giờ làm, đơn hàng và thông tin thanh toán. Các bản sao lưu cần được lưu trữ an toàn và có quy trình phục hồi dữ liệu để nhanh chóng khôi phục hệ thống trong trường hợp lỗi hoặc sự cố.
- Periodic inspection and maintenance: Một hệ thống kiểm tra và bảo trì định kỳ sẽ giúp hệ thống luôn được cập nhật và khắc phục lỗi kịp thời. Bảo trì định kỳ có thể bao gồm kiểm tra mã nguồn, rà soát bảo mật và nâng cấp các thành phần phần mềm để tối ưu hiệu suất và khả năng bảo mật của hệ thống. 
- Automatically run and pay periodically: Cơ chế này giúp hệ thống tự động chạy quy trình tính lương vào các ngày cố định (thứ Sáu hàng tuần và ngày làm việc cuối cùng trong tháng), đảm bảo tính lương đều đặn mà không cần sự can thiệp của con người.
- Data encryption: Dữ liệu nhạy cảm, bao gồm thông tin tài khoản ngân hàng, địa chỉ, và chi tiết cá nhân của nhân viên, cần được mã hóa cả khi lưu trữ và truyền tải.

## 3. Phân tích ca sử dụng Select Payment:

1. Mô tả ca sử dụng Select Payment:
- Tên ca sử dụng: Select Payment
- Mô tả: Ca sử dụng này cho phép nhân viên chọn phương thức thanh toán cho lương của họ. nhân viên có thể chọn giữa việc nhận séc trực tiếp, nhận qua bưu điện, hoặc nhận tiền chuyển khoản trực tiếp vào tài khoản ngân hàng đã chỉ định.

2. Các lớp phân tích:

Boundary Class: PaymentMethodSelectionUI
- Giao diện nhân viên cho phép nhân viên chọn phương thức thanh toán và nhập thông tin cần thiết.

Control Class: PaymentMethodController
- Chịu trách nhiệm xử lý luồng sự kiện, điều phối giữa lớp biên và lớp thực thể, xác thực thông tin và cập nhật dữ liệu.

Entity Class:
- Employee: Đại diện cho nhân viên trong hệ thống, chứa thông tin như tên, địa chỉ, và phương thức thanh toán đã chọn.
- PaymentMethod: Đại diện cho các phương thức thanh toán (nhận trực tiếp, bưu điện, chuyển khoản).

3. Biểu đồ Sequence:

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/h9J1Ji8m6CVlVOeldE3W2t0mX8L43n8IP-9rbcPT7EqokaFF7emn9lW6eZ564o8cNjmE74PuZpu1hs0x19mwH6Ith-r-t_V__zTDar6jAvnGH1qVELZm41gTmEUI47J28zPsGWajHtO84mT4KDu-93x1mkFiQ1zXpaJ8_Vm1QxRean3fDK_81R6HbGZDQzZPBMHNeQxYPm7ZQnK_H82fIguO17GodFIP2qBNZnWLlVsDl1og2Z9zqa23jTCtQMNaSWKLd5yz9FLKSiPipRZCmTRKE9FL-b1bPwBAfIPLyO2125NoWa5uAXu5fSfcOl_K0Jc-W9_s4EXdXK7vXAl6tK6GWSIQhOdV9L2V32ETkFRqdFtMijZKPRxZdix5CQ5SpDhgP0nspN0YvbeglW-ACDinvBFekH4MZQJviE2KSXNVRSKCcwQlkgl7ccvwo_RI6-PkPaSnQ3k6V1LlJ65jzEyBUfpsyIA_LPTfFcl-UcUgnpsJKv13ePeUJ_y_tm400F__0m00)

4. Nhiệm vụ của từng lớp phân tích:

PaymentMethodSelectionUI: 
- Cung cấp giao diện nhân viên để nhân viên tương tác với hệ thống.
- Thông báo cho nhân viên về kết quả của quá trình chọn phương thức thanh toán, bao gồm cả thông điệp xác nhận.

PaymentMethodController: 
- Xử lý luồng sự kiện từ giao diện nhân viên và tương tác với các lớp thực thể.
- Quản lý logic cho việc lựa chọn phương thức thanh toán của nhân viên.
- Xác định và thực hiện các hành động cần thiết dựa trên lựa chọn của nhân viên, bao gồm yêu cầu thông tin bổ sung nếu cần.
- Cập nhật thông tin phương thức thanh toán của nhân viên trong hệ thống.

EmployeeEntity: 
- Lưu trữ và quản lý dữ liệu liên quan đến nhân viên.
- Thực hiện các thao tác cần thiết để cập nhật thông tin phương thức thanh toán khi được yêu cầu từ lớp điều khiển.

PaymentMethod: 
- Lưu trữ thông tin liên quan đến từng phương thức thanh toán.
- Cung cấp thông tin cho lớp điều khiển để thực hiện cập nhật phương thức thanh toán cho nhân viên.

5. Biểu đồ lớp:

![Class Diagram](https://www.planttext.com/api/plantuml/png/V99DJiCm48NtEOMNwI8No0ArG1Si2aWL1x3geRNm7vw9gWXnCXOSYIjWrqw4enflBBttFFEDxP-lxpKIzpHerHmKHsJFVDHWQ0Tqic8F2WuahNbvO1yDYqj8T8gFJoxAsAwIwk5z0AGTbseZX0TSEhVSlDq31Nzsy6JFTzQyIgzvB1Rqp-OQHGYHjqg1do1oqUkiS_sBaCnMNxQUxSbBSyo9mGbEK4dCB5ljb1q1jeOaZHcXCrp354uAJuENelkBM5YvUp537QA8JGmf_RWaOKV8mMYrgzaCrQhFstKtrLllsO20JSsEHnUNrEVf_ZzK3fMxD6im8lp7Nm000F__0m00)

Giải thích biểu đồ lớp:

- PaymentMethodSelectionUI: Đây là lớp giao diện nhân viên, nơi nhân viên tương tác để chọn phương thức thanh toán.
- PaymentMethodController: Đây là lớp điều khiển, chịu trách nhiệm xử lý logic cho quá trình chọn phương thức thanh toán.
- EmployeeEntity: Đây là lớp thực thể đại diện cho thông tin của nhân viên trong hệ thống.
- PaymentMethod: Đây là lớp thực thể đại diện cho các phương thức thanh toán có sẵn.

## 4. Phân tích ca sử dụng Maintain Timecard:
1. Mô tả ca sử dụng Maintain Timecard:
- Tên ca sử dụng: Maintain Timecard.
- Mô tả: Ca sử dụng "Maintain Timecard" cho phép nhân viên cập nhật và gửi thông tin thời gian làm việc. Nhân viên (cả theo giờ và theo lương) phải gửi thời gian làm việc hàng tuần, ghi lại tất cả số giờ đã làm trong tuần và dự án tương ứng.

2. Các lớp phân tích:

Boundary Class: 
- Employee Interface: Giao diện nhân viên cho nhân viên, nơi họ có thể nhập giờ làm việc và gửi thời gian làm việc.
- Timecard Display: Hiển thị thời gian làm việc hiện tại của nhân viên, bao gồm các số liệu về giờ làm việc và số dự án.
- Error Message Display: Hiển thị thông báo lỗi khi có sự cố xảy ra.

Control Class:
- TimecardController: Lớp này xử lý logic cho ca sử dụng, bao gồm việc lưu, gửi và xác thực thông tin thời gian làm việc của nhân viên.
- ValidationController: Lớp này đảm bảo rằng các dữ liệu được nhập vào là hợp lệ, kiểm tra số giờ và đảm bảo không vượt quá giới hạn cho phép.

Entity Class: 
- Timecard: Lớp này lưu trữ thông tin về thời gian làm việc, bao gồm số giờ làm việc cho từng dự án, trạng thái của thời gian làm việc (ví dụ: đã gửi hay chưa), và các thông tin liên quan khác.
- Project: Lớp này lưu trữ thông tin về các dự án có thể tính giờ, bao gồm số dự án và số hiệu charge.
- Employee: Lớp này đại diện cho nhân viên, lưu trữ thông tin cá nhân và quyền hạn của họ trong hệ thống.

3. Biểu đồ Sequence:

![Sequence Diagram](https://www.planttext.com/api/plantuml/png/l5H1Yjim5Dtx59_PzmA1bA6PORfeoYooQ9UA8cnrPDd8Si3hBePI2Wsbb58A2M4ej0pJGbVMOXOESm-TOAxGRzbkx2HDPjKiWlprtzTxJy--DxV7YIPAfw7m2DMHWjCm5b76c1TZcLCU4wdXQCH3HecQm22IMaL2C7K4987HO5tOZQZQweTkoxcANZ6gOKWayLd8i7P2D1cJX3dK-R1vxE9EbKAYGvOa28CJdiI2P0xXTkg2v_NxyCJcDnfMCvj_Iu4IIAovXearLzA7VjzhnCAZnnqfFNXPV4U0Wyd0vjSn-DoQho2AUUYrMnsqbjU3PpQ_oa07nMyyG7E9IqHn11Ffi13Wc4kistp1FIBqNp1Sr2XhFZJxWBz_7pR2dcZxXD2QBznZShB5SsremnJzc04DY48ZBr3diZR7CHjKTPc6OwOI85F21HaBjfDMOsKFdgB2rvNoj-q3F2OIjZbKHlhGuDQTRWolVHuNQ8EmvbDbM1lGPJP2r0zINQYi4QLFUtBmVFFoOLhCEwhsXE7kPzf6hcR5iawJ2-SPXf5ltz-qJ0XzS3pzdLFsq7fHBAZh_qNReIvl_6nD5lUNSUdHvO4KEfNIB-PPHUL0--gzDH-HhyBmbcaFYaN9lfZBe3Be8KC6GPgv72G4Pr2qzBPyoStdSctUkFKxMWMkfQb-mmv8-n-1EyP__ER-0G00__y30000)

4. Nhiệm vụ của từng lớp phân tích:

Employee Interface: 
- Cung cấp giao diện nhân viên cho nhân viên để nhập giờ làm việc, xem thông tin thời gian làm hiện tại và gửi thời gian làm. Lớp này xử lý các tương tác trực tiếp với nhân viên.

Timecard Display: 
- Hiển thị thông tin chi tiết về thời gian làm việc hiện tại, bao gồm số giờ làm, số charge, và trạng thái của thời gian làm (đã gửi hay chưa).

Error Message Display: 
- Hiển thị thông báo lỗi khi có sự cố xảy ra trong quá trình nhập liệu, chẳng hạn như số giờ không hợp lệ hoặc khi không thể truy cập số charge.

TimecardController: 
- Xử lý logic cho ca sử dụng, bao gồm việc lưu trữ, xác thực và gửi thông tin thời gian làm việc.

ValidationController: 
- Chịu trách nhiệm xác thực dữ liệu nhập vào, đảm bảo rằng số giờ làm và các thông tin khác là hợp lệ.

Timecard: 
- Lưu trữ thông tin về thời gian làm việc của nhân viên, bao gồm số giờ làm cho từng dự án, trạng thái của thời gian làm (đã gửi hay chưa), và các thông tin liên quan khác như ngày gửi.

Project: 
- Lưu trữ thông tin về các dự án mà nhân viên có thể tính giờ, bao gồm số hiệu charge và các thông tin liên quan khác về dự án.

Employee: 
- Đại diện cho thông tin cá nhân của nhân viên, bao gồm quyền hạn và thông tin liên quan đến tài khoản nhân viên trong hệ thống.

5. Biểu đồ lớp:

![Class Diagram](https://www.planttext.com/api/plantuml/png/b5IxRjim5Dtr5HUUtC8Eq5KeZ01EW6Q84I15EzFKXSIA8WsIiXiK7OgEdJfrxjgjw5OF6TmVyHVq5qg9r8jIXdgmx7lkuzp38_uzFbvgGvGf2nvHJhI6wsB7vGCYV8Z0VfR0aXZkZM8YzG512Wn2Il9X283Bz4RCdyMmbopnCHG6rIjPAXq0kjmMpBnc1LAYaXRy67bI3TAIgabV4MEdLjy-YY8PnR9gt5kfShHxt9BTomfRrByStmNSM5efgjMgQsvA7QpeA1eC9m2G974x9Iso09eHbUAcBBQecauBHoPk1WOQa3q6ikm9PrNJAhoLLcCYccGqztr2lTb1LvjOhpCVRZMI-4x9TqXDg_3K0XxQkTHDw0E05CswLrVn3l6xhhW7ZqvwBOMnhkAeF2C0XJONzxWkbR9EQjs2th5nwrtRjq5zBLLefTdWuR-g6ltTyHeFTcdZOndwUB9YAFiRDu99CR4npP3cTOPZCB9FCxrjTwsKLBUeDKdnYkaT9mzjDvt9GutF2vSGUi7RcUP27ZWcARhi7kVsSfYzcC5okRBFYuldi-xzZ86UVaNjto2jyLWCd9r-2CZFlnzDD77aNTsWzv-lx7pyL4AUsUTd4KsAzqJj-zDt2YOx7t_IQ4gb9yhSfBhm2_3pyHkBeajxpzWByny0003__mC0)

Giải thích biểu đồ lớp: 
- Employee: Hiển thị thông tin cá nhân của nhân viên.
- Timecard: Hiển thị thông tin chi tiết về thời gian làm việc hiện tại.
- Project: Lưu trữ thông tin về các dự án.
- TimecardController: Xử lý logic cho ca sử dụng.
- ValidationController: Chịu trách nhiệm xác thực dữ liệu nhập vào.
- Error Message Display: Hiển thị thông báo lỗi khi có sự cố xảy ra trong quá trình nhập liệu.

## 5. Hợp nhất kết quả phân tích:

Biểu đồ lớp

![Class Diagram](https://www.planttext.com/api/plantuml/png/b5F1IiD04BtdAuPwBgZ7KagrA7XG1FK3ficQBDtiXjcj9OeVKw4NGV3WoHuy1FeV_G9_eHERnfYc1G-1dVTcvhrzIRxdNtthaDmuLfuTIPqWOGmsmi1Cf0xX7fKL5KP9BLoQ233a8bCXV8NMmfC7S6wqky9OW8zA3aaMq8ry571qpDKf-gEGp5W70wCCmO6IOUHIePIPvBIXG5113SbCD8Cdn8Sch46jnDUIXzwpvoMiYQ60rYLAxVY1MnaB7obe_PY6ihwxW6vtcBj3IdkzFzo0bv9HIX3t-EkYriA4q4wwpUXPd2YJ2b77AtBjTgz9eGDsEN-3O3cVwN2NZUeiJxZ5-sBAhyrbKt_VIEcg0shvEKl1HTb7FiV1w2XxqV0WirVDoPN1NMCQymqsSHLbKre5jIUieiFLG_bTcflSthCToNRFVwwtUqFfi9OfVqfzeGF-NLO0003__mC0)

