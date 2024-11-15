# Xác định các phần tử thiết kế của hệ thống “Payroll System”.
## 1. Subsystem context diagrams
### 1.1. BankSystem:

![](https://www.planttext.com/api/plantuml/png/h9512i8m44NtESNGLGNJwhQ855rr9tY2aAOOsYObcGf5FPaBZ-GLR5eggTswoGJ-dyV_pFlvIYqoWsrT4LunQ-74EgEhwgWLkYaCt0X078Df5JIZ6Ax8Wn2fK9Y2SG7PWQdot5aKzU3EHQEjn93rC7uHl4nW-gsXNzFEdu1xCrLeKpEKMWtGCSI_UPFRmtj6GfQbWqqKRGEWT3zhbq0kZU0uHR8mS2rS9IE-SNUdrAinqnpqc-XNM6HBXShxytm0003__mC0)

### 1.2. Giải thích:  
- Hệ thống con:
  - PayrollController:
    - Phương thức: run payroll()
    - Quan hệ: Có mối quan hệ 0..1 với IBankSystem, cho phép gửi tiền trực tiếp qua IBankSystem. 
  - BankSystem:
    - Phương thức: deposit(aPaycheck: Paycheck, intoBank: BankInformation)
    - Paycheck: Đại diện cho phiếu lương.
    - BankInformation: Đại diện cho thông tin ngân hàng.
- Interface của hệ thống con:
  - Interface IBankSystem định nghĩa phương thức deposit, là một điểm giao tiếp giữa hệ thống con quản lý lương (PayrollController) và hệ thống ngân hàng (BankSystem).

### 2.1. PrintService:

![](https://www.planttext.com/api/plantuml/png/l591QWCn3BplAtHi8Ca3J2cXxIMtG5xWhAV5eBMtabrOshmiXpwfNwZNxOPa2prM5o7DQ2G6VPu-DfgifDnnGoLQjggqiuD4veSOqfWXz5RH6eAN34s5e-pxcqL5ZarDFYJ8asr1svsKOWzvzQMw6E_7_ZIChkSu05jdQ9yAyhmajMnbCFGOyu6n90UNs-HZqActC7GV8yE6oztdqqVbdutNq7zVzDl6rUfkveoXhD1AlmPktzThcb5zEGuTGj8_z2S73BK2ct3crcvbp5Jrsm8uEWpD1i6LR_W2003__mC0)

### 2.2. Giải thích:
- Hệ thống con:
  - PayrollController:
    - Phương thức: requestPayslip()
    - Quan hệ: Sử dụng IPrintService, tạo Payslip.
  - PrintService:
    - Phương thức: printPayslip(employeeId: String, salary: Double, deductions: Double): Boolean
    - Quan hệ: Thực hiện IPrintService, in Payslip.
  - Payslip: Đại diện cho phiếu lương, được tạo bởi PayrollController và in bởi PrintService.
- Interface của hệ thống con:
  - Interface IPrintService định nghĩa phương thức printPayslip, là một điểm giao tiếp giữa hệ thống quản lý lương (PayrollController) và hệ thống in ấn (PrintService).
 
### 3.1. ProhectManagementDatabase subsystems:

![](https://www.planttext.com/api/plantuml/png/t5D1JiCm4Bpd5Jws4kq38eGgQ2LwGAh4WVFMMT9GnuwyQw48U1a7diGNS9mKhAHOdF75acTcPtPjVxv_h8Z1igjL9loI2eZ43bfhbBenchiThNW9Q5WbygPkb6aHTzOyeUGrCCpcFmpN5C0dyDOuImFwbeMjqeps4IIAxK2w0mqbrgX3hJqGZXnZ9npSjqKkxjbMkfpd8Y8aWqp55wBf2V7HeIC_67j4VxWsRg_GcrmRen1qtCimiF_HnlUzGjirSGxfFSuWqsdqbQTlQR6uIbryBXmX1Ms2TVcwN2R6dlUF32IJUAxua8WoQhhp3_EclsZw05u3KYATSe_XMEAvx7CTVsT6HOcgKbEsGbtu7_e5003__mC0)

### 3.2. Giải thích:
- Hệ thống con:
  - PayrollController:
    - Phương thức: getEmployeeProjectData(), updateProjectHours()
    - Quan hệ: Sử dụng IProjectManagementDatabase, cập nhật EmployeePayment, truy cập EmployeeProject.
  - ProjectManagementDatabase:
    - Phương thức: getProjectData(employeeId: String): ProjectData, updateProjectHours(employeeId: String, projectId: String, hoursWorked: Double): Boolean.
    - Quan hệ: Thực hiện các phương thức của IProjectManagementDatabase.
  - EmployeePayment: Đại diện cho thông tin thanh toán của nhân viên, được cập nhật bởi PayrollController.
  - EmployeeProject:
    - Quan hệ: Theo dõi thông tin Employee, gán Project.
  - Employee: Đại diện cho nhân viên trong hệ thống.
  - Project: Đại diện cho các dự án mà nhân viên tham gia.
- Interface của hệ thống con:
  - Interface IProjectManagementDatabase định nghĩa các phương thức getProjectData và updateProjectHours, là các điểm giao tiếp giữa PayrollController và ProjectManagementDatabase.

## 2. Analysis class to design element map

|  Analysis Class | Design Element |  
|-----------------|----------------|
| LoginForm | LoginForm|
| MaintainTimecardForm | MainEmployeeForm |
| TimecardController | TimecardController |
| PayrollController | PayrollController |
| PayCheck | PayCheck |
| SystemClock| SystemCLockInterface |
| PayPeriod | PayPeriodController |
| PaymentMethod | PaymentMethod |
| Timecard | TimecardEntity |
| PurchaseOrder | PurchaseOrderController |
| SalariedEmployee | SalariedEmployeeEntity |
| CommissionedEmployee | CommissionedEmployeeEntity |
| HourlyEmployee | Hourly EmployeeController |

## 3. Design element to owning package map

|  Design Element | "Owning" Package |  
|-----------------|----------------|
| LoginForm | Middleware::Security::GUIFramwork |
| MainEmployeeForm | Applications::Employee Activities |
| TimecardController | Applications::Employee Activities |
| SystemClockInterface | Applications::Payroll |
| PayrollController | Applications: Payroll |
| PayCheck | Business Services::Payroll Artifacts |
| PayPeriod | Business Services::Payroll Artifacts |
| PaymentMethod | Business Services::Payroll Artifacts |
| Timecard | Data Access::Employee Management |
| PurchaseOrder | Business Services::Payroll Artifacts |
| SalariedEmployee | Applications::Employee Activities |
| CommissionedEmployee | Applications::Employee Activities |
| HourlyEmployee | Applications::Employee Activities |

## 4. Architectural layers and their dependencies

