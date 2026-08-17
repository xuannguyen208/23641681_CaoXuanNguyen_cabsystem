# 23641681_CaoXuanNguyen_cabsystem

Câu 1:
a) Hệ thống hiện tại có những vấn đề gì?
- Việc phân công tài xế chủ yếu vẫn làm thủ công nên có thể mất nhiều thời gian.
- Khách hàng khó theo dõi được trạng thái chuyến đi của mình.
- Thông tin thanh toán chưa được quản lý tập trung.
- Bộ phận vận hành gặp khó khăn khi số lượng khách hàng và tài xế tăng lên.
- Khi tài xế đầu tiên không nhận chuyến thì việc tìm tài xế khác chưa được tự động hóa tốt.
- Khó theo dõi vị trí của tài xế để tìm tài xế gần khách hàng và dự đoán thời gian tài xế đến.
- Hệ thống hiện tại khó mở rộng thêm các chức năng mới trong tương lai.
b) Mục tiêu chính của hệ thống:
- Cho phép khách hàng đặt xe một cách dễ dàng.
- Tự động tìm và phân công tài xế phù hợp cho khách hàng.
- Cho khách hàng theo dõi được trạng thái chuyến đi.
- Cho phép tài xế nhận và cập nhật trạng thái chuyến.
- Hỗ trợ tính cước và thanh toán bằng tiền mặt hoặc thanh toán điện tử.
- Quản lý thông tin khách hàng, tài xế, phương tiện và chuyến đi tập trung.
- Gửi thông báo cho khách hàng và tài xế khi có các sự kiện quan trọng.
- Hỗ trợ nhân viên vận hành theo dõi và xử lý các chuyến đi.
- Có báo cáo về số lượng chuyến, doanh thu, tỷ lệ hoàn thành, tỷ lệ hủy và hiệu quả của tài xế.
- Hệ thống phải có khả năng mở rộng để sau này có thể thêm dịch vụ, phương thức thanh toán hoặc nhà cung cấp thông báo mới.
c) Vấn đề hiện tại là gì?
- Việc tìm và phân công tài xế mất nhiều thời gian.
- Khách hàng không biết chính xác chuyến xe đang ở trạng thái nào.
- Nhân viên vận hành khó quản lý khi số lượng chuyến tăng.
- Việc thanh toán và thông tin giao dịch chưa được quản lý tốt.
- Hệ thống khó mở rộng khi công ty muốn phát triển thêm.
d) Ai là người tham gia và sử dụng hệ thống?
d.1. Khách hàng
- Đăng ký và đăng nhập.
- Cập nhật thông tin cá nhân.
- Nhập điểm đón và điểm đến.
- Chọn loại xe.
- Đặt xe.
- Theo dõi trạng thái chuyến đi.
- Xem thông tin tài xế và thời gian dự kiến tài xế đến.
- Xem lịch sử chuyến đi.
- Xem số tiền cần thanh toán.
- Thanh toán.
- Đánh giá tài xế sau chuyến đi.
d.2. Tài xế
- Đăng ký tài khoản hoặc được nhân viên tạo tài khoản.
- Cập nhật thông tin cá nhân.
- Cập nhật thông tin phương tiện.
- Chuyển sang trạng thái sẵn sàng nhận chuyến.
- Nhận thông báo khi có chuyến mới.
- Chấp nhận hoặc từ chối chuyến.
- Cập nhật trạng thái chuyến như:
  - Đã đến điểm đón.
  - Đã đón khách.
  - Đang di chuyển.
  - Hoàn thành chuyến.
- Hệ thống cũng lưu vị trí của tài xế để hỗ trợ tìm tài xế gần khách hàng.
d.3. Nhân viên vận hành
- Quản lý khách hàng.
- Quản lý tài xế.
- Quản lý phương tiện.
- Quản lý các chuyến đi.
- Xem các chuyến đang diễn ra.
- Kiểm tra trạng thái của tài xế.
- Hỗ trợ xử lý các chuyến bị lỗi.
- Tra cứu lịch sử giao dịch.
- Theo dõi các báo cáo về hoạt động của hệ thống.
d.4. Ban giám đốc
- Theo dõi số lượng chuyến đi.
- Theo dõi doanh thu.
- Theo dõi tỷ lệ chuyến hoàn thành.
- Theo dõi tỷ lệ chuyến bị hủy.
- Theo dõi hiệu quả hoạt động của tài xế.
- Đưa ra các yêu cầu và định hướng phát triển hệ thống.
- Có thể mở rộng thêm các loại dịch vụ, phương thức thanh toán và các kênh thông báo trong tương lai.
d.5. Nhà cung cấp thanh toán
- Xử lý các giao dịch thanh toán điện tử của khách hàng.
- Trả kết quả thanh toán về cho hệ thống CAB.
- Hỗ trợ trường hợp thanh toán thành công hoặc thất bại.
- Hệ thống CAB không lưu trực tiếp các thông tin nhạy cảm của thẻ hoặc tài khoản thanh toán.
- Khi thanh toán thất bại, hệ thống cần thông báo cho khách hàng và cho phép xử lý lại theo chính sách của công ty.
d.6. Nhà cung cấp dịch vụ thông báo
- Gửi thông báo khi khách hàng tạo yêu cầu đặt xe.
- Thông báo khi có tài xế nhận chuyến.
- Thông báo khi tài xế đến điểm đón.
- Thông báo khi chuyến đi hoàn thành.
- Thông báo kết quả thanh toán.
Câu 2: 
| Tên                                                        | Vai trò                                                                                                                                         |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| Khách hàng (Customer)                                 | Đăng ký, đặt xe, theo dõi chuyến đi, thanh toán, xem lịch sử và đánh giá tài xế.                                                                |
| **Tài xế (Driver)**                                        | Nhận hoặc từ chối chuyến, cập nhật trạng thái chuyến, quản lý thông tin cá nhân và phương tiện, cung cấp vị trí để hệ thống tìm tài xế phù hợp. |
| **Nhân viên vận hành (Operation Staff)**                   | Quản lý khách hàng, tài xế, phương tiện và chuyến đi; theo dõi chuyến đang diễn ra, xử lý các trường hợp lỗi và tra cứu giao dịch.              |
| **Ban giám đốc (Management)**                              | Theo dõi số lượng chuyến, doanh thu, tỷ lệ hoàn thành/hủy và hiệu quả tài xế; đưa ra định hướng phát triển hệ thống.                            |
| **Nhà cung cấp thanh toán (Payment Provider)**             | Xử lý thanh toán điện tử và trả kết quả giao dịch về hệ thống CAB.                                                                              |
| **Nhà cung cấp dịch vụ thông báo (Notification Provider)** | Gửi các thông báo liên quan đến đặt xe, tài xế, chuyến đi và thanh toán cho khách hàng và tài xế.                                               |

