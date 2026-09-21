# Phân rã Domain lớn thành các Sub-domain theo DDD

## 1. Domain lớn

**CAB/JAM – Ride Booking Management Domain**

Domain lớn của hệ thống CAB/JAM là quản lý toàn bộ nghiệp vụ đặt và thực hiện chuyến xe, từ khi khách hàng tạo yêu cầu đặt xe cho đến khi chuyến đi hoàn thành, thanh toán và đánh giá.

Luồng nghiệp vụ cốt lõi:

```text
Booking
   ↓
Tìm tài xế
   ↓
Gán tài xế
   ↓
Thực hiện chuyến
   ↓
Hoàn thành
   ↓
Tính cước
   ↓
Thanh toán
   ↓
Đánh giá
```

---

## 2. Phân rã Domain thành các Sub-domain

```text
CAB/JAM Ride Booking Domain
│
├── 1. Identity & Access Management
├── 2. Customer Management
├── 3. Driver & Vehicle Management
├── 4. Booking Management
├── 5. Driver Discovery & Assignment
├── 6. Trip Management
├── 7. Location & Tracking
├── 8. Fare Management
├── 9. Payment Management
├── 10. Notification Management
├── 11. Review Management
├── 12. Operation & Incident Management
└── 13. Reporting & Analytics
```

---

## 3. Phân loại các Sub-domain

| STT | Sub-domain                      | Nghiệp vụ chính                | Loại       |
| --- | ------------------------------- | ------------------------------ | ---------- |
| 1   | Identity & Access Management    | Đăng ký, đăng nhập, phân quyền | Supporting |
| 2   | Customer Management             | Quản lý khách hàng             | Supporting |
| 3   | Driver & Vehicle Management     | Quản lý tài xế và phương tiện  | Core       |
| 4   | Booking Management              | Tạo, xác nhận, hủy đặt xe      | Core       |
| 5   | Driver Discovery & Assignment   | Tìm và gán tài xế              | Core       |
| 6   | Trip Management                 | Quản lý vòng đời chuyến đi     | Core       |
| 7   | Location & Tracking             | Vị trí và theo dõi chuyến      | Core       |
| 8   | Fare Management                 | Tính và quản lý giá cước       | Supporting |
| 9   | Payment Management              | Thanh toán và giao dịch        | Supporting |
| 10  | Notification Management         | Gửi thông báo                  | Supporting |
| 11  | Review Management               | Đánh giá chuyến đi và tài xế   | Supporting |
| 12  | Operation & Incident Management | Vận hành và xử lý sự cố        | Supporting |
| 13  | Reporting & Analytics           | Báo cáo và thống kê            | Supporting |

---

# 4. Chi tiết các Sub-domain

## 4.1. Identity & Access Management

### Mục đích

Quản lý danh tính người dùng và quyền truy cập vào hệ thống CAB/JAM.

### Chức năng

* Đăng ký tài khoản
* Đăng nhập
* Đăng xuất
* Xác thực tài khoản
* Quản lý thông tin tài khoản
* Quản lý vai trò
* Kiểm tra quyền truy cập

### Functional Requirements

* FR01 – User Management
* FR18 – Authorization

---

## 4.2. Customer Management

### Mục đích

Quản lý thông tin khách hàng và các dữ liệu liên quan đến hoạt động sử dụng dịch vụ.

### Chức năng

* Tạo khách hàng
* Cập nhật thông tin khách hàng
* Xem thông tin khách hàng
* Tìm kiếm khách hàng
* Xem lịch sử chuyến đi
* Xem lịch sử thanh toán

### Functional Requirements

* FR02 – Customer Management

---

## 4.3. Driver & Vehicle Management

### Mục đích

Quản lý tài xế, phương tiện và trạng thái hoạt động của tài xế.

### Chức năng

* Quản lý hồ sơ tài xế
* Cập nhật thông tin tài xế
* Quản lý trạng thái tài xế
* Quản lý phương tiện
* Quản lý loại phương tiện
* Gán phương tiện cho tài xế
* Thay đổi trạng thái phương tiện

### Functional Requirements

* FR03 – Driver Management
* FR04 – Vehicle Management

---

## 4.4. Booking Management

### Mục đích

Quản lý yêu cầu đặt xe của khách hàng từ khi tạo yêu cầu đến khi xác nhận hoặc hủy.

### Chức năng

* Nhập điểm đón
* Nhập điểm trả
* Chọn loại phương tiện
* Tạo yêu cầu đặt xe
* Kiểm tra thông tin đặt xe
* Xác nhận đặt xe
* Hủy đặt xe
* Theo dõi trạng thái booking

### Luồng nghiệp vụ

```text
Khách hàng
    ↓
Nhập thông tin chuyến
    ↓
Tạo Booking
    ↓
Kiểm tra thông tin
    ↓
Xác nhận Booking
    ↓
Tìm tài xế
```

### Functional Requirements

* FR05 – Booking Management

---

## 4.5. Driver Discovery & Assignment

### Mục đích

Tìm kiếm tài xế phù hợp và thực hiện gán tài xế cho yêu cầu đặt xe.

### Chức năng

* Tìm tài xế khả dụng
* Kiểm tra vị trí tài xế
* Kiểm tra khoảng cách
* Kiểm tra loại phương tiện
* Xác định tài xế phù hợp
* Gửi yêu cầu nhận chuyến
* Ghi nhận tài xế chấp nhận
* Ghi nhận tài xế từ chối
* Tìm tài xế khác khi bị từ chối hoặc không phản hồi
* Xác nhận gán tài xế

### Luồng nghiệp vụ

```text
Booking
   ↓
Tìm tài xế khả dụng
   ↓
Lọc theo vị trí + loại xe
   ↓
Gửi yêu cầu nhận chuyến
   ↓
Tài xế phản hồi
   │
   ├── Chấp nhận → Gán tài xế
   │
   └── Từ chối/Không phản hồi
              ↓
        Tìm tài xế khác
```

### Functional Requirements

* FR06 – Driver Search
* FR07 – Driver Assignment

---

## 4.6. Trip Management

### Mục đích

Quản lý toàn bộ vòng đời của chuyến đi sau khi tài xế được gán.

### Trạng thái chuyến

```text
booking
    ↓
searching_driver
    ↓
driver_assigned
    ↓
arriving_pickup
    ↓
arrived_pickup
    ↓
picked_up
    ↓
in_progress
    ↓
completed
```

Chuyến đi có thể chuyển sang trạng thái:

```text
cancelled
```

### Chức năng

* Tạo chuyến
* Gắn khách hàng với chuyến
* Gắn tài xế với chuyến
* Cập nhật trạng thái chuyến
* Theo dõi trạng thái chuyến
* Xác nhận tài xế đến điểm đón
* Xác nhận đã đón khách
* Cập nhật chuyến đang thực hiện
* Hoàn thành chuyến
* Hủy chuyến
* Xem lịch sử chuyến

### Functional Requirements

* FR08 – Trip Management

---

## 4.7. Location & Tracking

### Mục đích

Quản lý vị trí tài xế và cung cấp thông tin theo dõi chuyến đi.

### Chức năng

* Nhận vị trí tài xế
* Cập nhật vị trí tài xế
* Lưu vị trí
* Hiển thị vị trí
* Tính khoảng cách
* Ước tính thời gian đến (ETA)
* Theo dõi chuyến đi

### Functional Requirements

* FR09 – Driver Location

---

## 4.8. Fare Management

### Mục đích

Tính toán và quản lý giá cước của chuyến đi.

### Chức năng

* Xác định loại dịch vụ
* Thu thập thông tin chuyến
* Tính giá cước
* Hiển thị giá cước
* Lưu giá cước
* Liên kết giá cước với chuyến

### Functional Requirements

* FR10 – Fare Management

---

## 4.9. Payment Management

### Mục đích

Quản lý quá trình thanh toán và kết quả giao dịch của chuyến đi.

### Chức năng

* Hiển thị số tiền cần thanh toán
* Chọn phương thức thanh toán
* Thanh toán tiền mặt
* Thanh toán điện tử
* Tạo giao dịch
* Gửi yêu cầu đến Payment Provider
* Nhận kết quả thanh toán
* Cập nhật trạng thái giao dịch
* Tra cứu giao dịch
* Xử lý thanh toán thất bại
* Thực hiện thanh toán lại

### Luồng nghiệp vụ

```text
Trip Completed
      ↓
Tính giá cước
      ↓
Tạo Payment
      ↓
Chọn phương thức
      │
      ├── Tiền mặt
      │
      └── Thanh toán điện tử
                ↓
        Payment Provider
                ↓
        Kết quả giao dịch
```

### Functional Requirements

* FR11 – Payment
* FR12 – Payment Handling
* FR19 – Payment Provider Integration

---

## 4.10. Notification Management

### Mục đích

Quản lý việc gửi thông báo đến khách hàng, tài xế và các đối tượng liên quan.

### Chức năng

* Thông báo đặt xe
* Thông báo gán tài xế
* Thông báo tài xế đến
* Thông báo hoàn thành chuyến
* Thông báo thanh toán
* Thông báo thay đổi trạng thái
* Theo dõi trạng thái gửi thông báo

### Functional Requirements

* FR13 – Notification
* FR20 – Notification Provider Integration

---

## 4.11. Review Management

### Mục đích

Quản lý đánh giá của khách hàng sau khi chuyến đi hoàn thành.

### Chức năng

* Đánh giá chuyến đi
* Chấm điểm tài xế
* Lưu đánh giá
* Liên kết đánh giá với chuyến
* Liên kết đánh giá với tài xế
* Xem đánh giá của tài xế

### Functional Requirements

* FR14 – Review

---

## 4.12. Operation & Incident Management

### Mục đích

Hỗ trợ nhân viên vận hành giám sát chuyến đi và xử lý các sự cố phát sinh.

### Chức năng

* Theo dõi chuyến đang thực hiện
* Kiểm tra trạng thái tài xế
* Kiểm tra trạng thái chuyến
* Tra cứu giao dịch
* Ghi nhận sự cố
* Kiểm tra sự cố
* Cập nhật trạng thái xử lý
* Hỗ trợ xử lý chuyến có vấn đề
* Xem lịch sử xử lý

### Functional Requirements

* FR15 – Operation
* FR16 – Incident Handling

---

## 4.13. Reporting & Analytics

### Mục đích

Cung cấp thông tin thống kê và báo cáo phục vụ quản lý.

### Chức năng

* Báo cáo số lượng chuyến
* Báo cáo doanh thu
* Báo cáo tỷ lệ hoàn thành
* Báo cáo tỷ lệ hủy
* Báo cáo hiệu quả tài xế
* Lọc báo cáo theo thời gian
* Xem báo cáo

### Functional Requirements

* FR17 – Reports

---

# 5. Core Domain và Supporting Sub-domain

## 5.1. Core Domain

Các nghiệp vụ tạo ra giá trị cốt lõi cho hệ thống đặt xe:

```text
Booking Management
        ↓
Driver Discovery & Assignment
        ↓
Trip Management
        ↓
Location & Tracking
```

### Core Domain gồm:

1. **Booking Management**
2. **Driver Discovery & Assignment**
3. **Trip Management**
4. **Location & Tracking**

Đây là chuỗi nghiệp vụ trực tiếp tạo nên dịch vụ đặt và thực hiện chuyến xe.

---

## 5.2. Supporting Sub-domain

Các nghiệp vụ hỗ trợ cho Core Domain:

```text
Identity & Access
Customer Management
Driver & Vehicle Management
Fare Management
Payment Management
Notification Management
Review Management
Operation & Incident Management
Reporting & Analytics
```

Các sub-domain này hỗ trợ hệ thống vận hành đầy đủ nhưng không phải toàn bộ giá trị cốt lõi của quy trình đặt chuyến.

---

# 6. Mối quan hệ giữa các Sub-domain

```text
                    Identity & Access
                           │
                           ↓
Customer ───────→ Booking Management
                       │
                       ↓
             Driver Discovery
                       │
                       ↓
              Driver Assignment
                       │
                       ↓
                Trip Management
                  │           │
                  │           └────────→ Location & Tracking
                  │
                  ↓
              Fare Management
                  │
                  ↓
             Payment Management
                  │
                  ↓
          Notification Management
                  │
                  ↓
            Review Management


Operation & Incident Management
              │
              └────→ Giám sát các nghiệp vụ


Reporting & Analytics
              ↑
              └────→ Dữ liệu từ các nghiệp vụ
```

---

# 7. Bảng tổng hợp Domain – Sub-domain – FR

| Domain  | Sub-domain                      | FR liên quan     |
| ------- | ------------------------------- | ---------------- |
| CAB/JAM | Identity & Access Management    | FR01, FR18       |
| CAB/JAM | Customer Management             | FR02             |
| CAB/JAM | Driver & Vehicle Management     | FR03, FR04       |
| CAB/JAM | Booking Management              | FR05             |
| CAB/JAM | Driver Discovery & Assignment   | FR06, FR07       |
| CAB/JAM | Trip Management                 | FR08             |
| CAB/JAM | Location & Tracking             | FR09             |
| CAB/JAM | Fare Management                 | FR10             |
| CAB/JAM | Payment Management              | FR11, FR12, FR19 |
| CAB/JAM | Notification Management         | FR13, FR20       |
| CAB/JAM | Review Management               | FR14             |
| CAB/JAM | Operation & Incident Management | FR15, FR16       |
| CAB/JAM | Reporting & Analytics           | FR17             |

---

# 8. Kết luận

Theo DDD, Domain lớn **CAB/JAM – Ride Booking Management** được phân rã thành các Sub-domain có phạm vi nghiệp vụ tương đối độc lập.

Trong đó, **Booking Management, Driver Discovery & Assignment, Trip Management và Location & Tracking** tạo thành nhóm nghiệp vụ cốt lõi của hệ thống.

Các Sub-domain còn lại như **Identity & Access, Customer, Driver & Vehicle, Fare, Payment, Notification, Review, Operation & Incident và Reporting** đóng vai trò hỗ trợ cho quá trình vận hành Core Domain.

Việc phân rã này giúp xác định rõ ranh giới nghiệp vụ, trách nhiệm của từng Sub-domain và tạo cơ sở cho các bước tiếp theo của DDD như xác định **Bounded Context, Entity, Value Object, Aggregate và Domain Service**.
