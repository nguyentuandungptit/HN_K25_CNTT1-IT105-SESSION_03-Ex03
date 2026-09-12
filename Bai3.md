# BÁO CÁO PHÂN TÍCH STAKEHOLDER & GIẢI QUYẾT XUNG ĐỘT BẢO MẬT HỒ SƠ EHR
**Khóa học:** Phân tích & Thiết kế Hệ thống (IT105)  
**Session:** 03 - Ma trận Stakeholder & Phân hệ Hồ sơ sức khỏe điện tử (EHR)  
**Vai trò thực hiện:** Lead System Analyst (Lead SA)

---

## PHẦN 1: THANH LỌC DANH SÁCH & LOẠI BỎ THỰC THỂ KỸ THUẬT

### 1. Phân định Thực thể Kỹ thuật và Stakeholder Thực thụ

| STT | Đối tượng khảo sát ban đầu | Phân loại | Giải thích lý do |
| :---: | :--- | :---: | :--- |
| **1** | **Bác sĩ điều trị trực tiếp** | **Stakeholder thực thụ** *(Giữ lại)* | Nhóm người trực tiếp sử dụng hệ thống để tra cứu, ghi nhận bệnh án và quyết định phác đồ điều trị cho bệnh nhân. |
| **2** | **Máy chủ cơ sở dữ liệu Oracle** | **Thực thể kỹ thuật** *(LOẠI BỎ)* | Là tài sản hạ tầng CNTT (phần cứng/phần mềm), không phải cá nhân hay tổ chức; không có hành vi, quyền lợi hay lợi ích xã hội để coi là Stakeholder. |
| **3** | **Ban Giám đốc Bệnh viện RikkeiCare** | **Stakeholder thực thụ** *(Giữ lại)* | Tổ chức/cá nhân nắm quyền lực cao nhất, phê duyệt ngân sách và quyết định chiến lược số hóa của bệnh viện. |
| **4** | **Bệnh nhân và Thân nhân người bệnh** | **Stakeholder thực thụ** *(Giữ lại)* | Nhóm người thụ hưởng trực tiếp dịch vụ khám chữa bệnh và là chủ sở hữu quyền riêng tư dữ liệu sức khỏe. |
| **5** | **Thanh tra Pháp chế & Bảo mật Y tế (Bộ Y tế)** | **Stakeholder thực thụ** *(Giữ lại)* | Cơ quan quản lý nhà nước ban hành quy định pháp lý, có quyền thanh tra, xử phạt và yêu cầu tuân thủ an toàn bảo mật. |

### 2. Phản biện đề xuất sai lệch từ nhóm cũ
- **Nhận định sai của nhóm cũ:** Xếp "Máy chủ cơ sở dữ liệu Oracle" vào nhóm *Manage Closely* vì giá trị đắt tiền.
- **Phản biện của Lead SA:** Đề xuất này sai bản chất nghiệp vụ. Máy chủ là đối tượng quản lý tài sản hạ tầng CNTT (IT Asset Management/Infrastructure), thuộc phạm vi thiết kế kiến trúc hạ tầng chứ không phải đối tượng tương tác truyền thông của dự án. Nhóm cần quản lý ở ô *Manage Closely* phải là các Stakeholder bằng con người/tổ chức có quyền lực và ảnh hưởng lớn đến sự thành bại của dự án.

---

## PHẦN 2: MA TRẬN STAKEHOLDER 4 Ô & GIẢI QUYẾT XUNG ĐỘT BẢO MẬT

### 1. Điền khuyết Ma trận Quyền lực - Mức độ quan tâm (Power-Interest Matrix)

| Nhóm chiến lược | Tiêu chí | Stakeholder | Hành động tương tác chủ chốt |
| :--- | :--- | :--- | :--- |
| **Quản lý chặt chẽ** *(Manage Closely)* | Quyền lực **Cao** - Quan tâm **Cao** | **Ban Giám đốc Bệnh viện** | Báo cáo tiến độ trực tiếp, tham gia mọi quyết định lớn và trình duyệt chiến lược triển khai. |
| **Giữ hài lòng** *(Keep Satisfied)* | Quyền lực **Cao** - Quan tâm **Thấp** | **Thanh tra Pháp chế & Bảo mật Y tế (Bộ Y tế)** | Tham vấn các tiêu chuẩn bảo mật/thông tư pháp lý y tế (như Luật KCB, quy định dữ liệu y tế), cam kết tuân thủ đầy đủ tiêu chuẩn mã hóa và audit log để không bị bác bỏ khi nghiệm thu/thanh tra. |
| **Giữ thông tin** *(Keep Informed)* | Quyền lực **Thấp** - Quan tâm **Cao** | **Bác sĩ điều trị trực tiếp** | Khảo sát sâu quy trình khám chữa bệnh thực tế, tổ chức đào tạo sử dụng hệ thống EHR, thu thập phản hồi về UI/UX và cập nhật liên tục các thay đổi về luồng thao tác. |
| **Giám sát tối thiểu** *(Monitor)* | Quyền lực **Thấp** - Quan tâm **Thấp** | **Bệnh nhân và Thân nhân người bệnh** *(ở cấp độ quản trị dự án)* | Thông báo định kỳ qua email/ứng dụng mobile về các tính năng sổ sức khỏe điện tử mới, hướng dẫn quản lý quyền riêng tư dữ liệu, không cần họp riêng. |

---

### 2. Đề xuất Giải pháp Dung hòa Xung đột Bảo mật (Tiện ích vs Bảo mật)

#### A. Phân tích Xung đột
- **Phía Bác sĩ:** Cần truy cập bệnh án tức thì để đưa ra quyết định cấp cứu/điều trị nhanh nhất (ưu tiên tính tiện ích & tính mạng bệnh nhân).
- **Phía Pháp chế:** Yêu cầu bệnh nhân xác nhận (Consent Mechanism) trước khi mở thông tin nhạy cảm để tuân thủ Luật Bảo vệ dữ liệu cá nhân & Bảo mật Y tế.

#### B. Giải pháp Dung hòa & Cơ chế Bẫy Khẩn cấp (Emergency Override)
*"Để dung hòa xung đột, hệ thống EHR triển khai **cơ chế xác thực mặc định bằng mã OTP/Consent từ ứng dụng của Bệnh nhân** trong điều kiện khám chữa bệnh thông thường; đồng thời xây dựng tính năng **Cấp quyền truy cập khẩn cấp (Emergency Override)** cho phép Bác sĩ điều trị trực tiếp kích hoạt mở hồ sơ tức thì mà không cần mã xác nhận khi bệnh nhân rơi vào tình trạng cấp cứu/hôn mê bất tỉnh, đi kèm điều kiện **bắt buộc ghi nhận vết nhật ký kiểm toán (Audit Log) không thể chỉnh sửa** (lưu danh tính Bác sĩ, thời gian, lý do kích hoạt, IP/thiết bị) và gửi thông báo cảnh báo ngay lập tức tới Cán bộ Pháp chế & Ban Giám đốc để hậu kiểm."*
