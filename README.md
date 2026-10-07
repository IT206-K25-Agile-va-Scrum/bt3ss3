# [Vận dụng chuyên sâu] THIẾT KẾ BACKLOG CHO TÍNH NĂNG FLASH SALE - PHÂN RÃ FEATURE GHÉP KHÁCH CÙNG TUYẾN THÀNH USER STORY

> 👤 **Học viên:** Đỗ Hoàng Sơn | **Mã SV:** PTIT-HCM-066
> 🏫 **Môn học:** IT206-K25-Agile-va-Scrum

---

## Phần 1 - Phân tích

Trong buổi Backlog Refinement của Sprint, đội ngũ phát triển cùng Product Owner Đức đã tiến hành mổ xẻ yêu cầu thô về tính năng ghép chuyến để chuẩn bị cho các Sprint tiếp theo.

- Vai trò 'Khách hàng (Hành khách)': Nhu cầu chính là nhanh chóng tìm được người đi chung tuyến, tự động chia tiền cước và thanh toán ví điện tử tích hợp chỉ trong một thao tác bấm duy nhất để tiết kiệm chi phí.
- Vai trò 'Tài xe (Tài xế công nghệ)': Nhu cầu chính là nhận được cuốc xe ghép tối đa 3 khách cùng hướng một cách tối ưu trên hệ thống để tăng doanh thu mà không cần tự tính toán chia tiền thủ công.

## Phần 2 - Phân rã

Dựa trên yêu cầu nghiệp vụ và tiêu chí INVEST, đội ngũ đã tách Feature lớn thành 3 User Story cụ thể sau đây:

- User Story 1: As a passenger, I want to request a shared ride with electronic wallet payment so that I can split the fare and pay in a single tap.
- Giải thích độ Small của US 1: User story này chỉ tập trung vào việc tạo yêu cầu ghép chuyến và xử lý thanh toán ví điện tử cơ bản, hoàn toàn có thể hoàn thành trong 2 ngày phát triển.
- User Story 2: As a system, I want to automatically match up to 3 passengers traveling in the same direction within 5 minutes so that the shared ride vehicle is fully optimized.
- Giải thích độ Small của US 2: Thuật toán quét và gom nhóm giới hạn chặt chẽ ở con số 3 khách, phạm vi code xử lý logic ngắn gọn, kiểm thử trong 2 ngày của Sprint.
- User Story 3: As a passenger, I want the system to handle timeout or vehicle capacity limits so that I can choose to ride solo or cancel for free if no match is found.
- Giải thích độ Small của US 3: Xử lý riêng biệt các ngoại lệ khi hết giờ chờ hoặc xe đã đủ chỗ, mã nguồn xử lý sự kiện đơn giản, hoàn thành nhanh trong vòng 1-2 ngày.

## Phần 3 - Nghiệm thu

Dưới đây là bộ Acceptance Criteria được viết theo định dạng Given - When - Then cho User Story tìm kiếm khách ghép nhằm kiểm thử cả luồng thành công lẫn các bẫy dữ liệu (Edge Cases):

| Kịch bản (Scenario) | Given (Bối cảnh) | When (Hành động) | Then (Kết quả mong đợi) |
| --- | --- | --- | --- |
| 1. Tìm thấy khách ghép trong thời hạn quy định | Khách hàng đã bấm đặt chuyến ghép tuyến và thanh toán ví điện tử thành công | Hệ thống thực hiện tìm kiếm hành khách cùng tuyến trong vòng 5 phút và đủ 3 khách | Hệ thống ghép nhóm thành công, xác nhận chuyến đi và thông báo cho tài xế bắt đầu đón khách |
| 2. Quá 5 phút không tìm đủ khách ghép (Ngoại lệ) | Khách hàng đã tạo yêu cầu đặt chuyến ghép và hệ thống bắt đầu đếm ngược thời gian 5 phút | Đã hết thời gian 5 phút nhưng hệ thống không tìm được đủ khách đi chung tuyến | Hệ thống hiển thị lựa chọn cho phép khách chuyển sang đi riêng với giá cước thông thường hoặc hủy chuyến hoàn toàn miễn phí |

---

## 📁 Danh sách tệp tin nộp bài trong Repository
- 📝 `bt3.docx`: Báo cáo tài liệu phân tích nghiệp vụ hoàn chỉnh.
