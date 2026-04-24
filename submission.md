# DOMIN-H Project - AI-Powered Personal Finance for Students

## 5. Checkpoints — Output yêu cầu

### 5.1 Checkpoint 1 — Scope Review Gate (MVP Boundary)
Sản phẩm tập trung giải quyết bài toán: **"Giảm rào cản ghi chép và tăng kỷ luật tiết kiệm cho sinh viên bằng AI."**

* **In-Scope (Tối đa 3 tính năng):**
    1. **AI OCR & Categorization:** Trích xuất thông tin hóa đơn và phân loại tự động vào các đầu mục (Ăn uống, Di chuyển, Học tập...) sử dụng Gemini Flash.
    2. **Smart Budgeting:** Cảnh báo chi tiêu dựa trên hạn mức đã thiết lập.
    3. **AI Savings Coach:** Gợi ý cắt giảm dựa trên hành vi chi tiêu thực tế (VD: "Bạn đã chi 500k cho trà sữa tuần này, bớt 2 ly sẽ đủ tiền mua sách").
* **Out-of-Scope:** Quản lý nợ, Liên kết ví điện tử/Ngân hàng, Quản lý tài sản đầu tư.
* **Non-Goals:** Tính năng mạng xã hội (Social Finance), Hệ thống đổi quà.

### 5.2 Checkpoint 2 — Clarity Review Gate (PRD Skeleton)

#### 6 Thành phần Standard:
1. **Context:** Sinh viên thường bỏ cuộc sau 3 ngày ghi chép thủ công vì quá lười và khó nhớ các khoản nhỏ.
2. **Goals:** 90% hóa đơn được phân loại đúng; User cảm thấy việc quản lý tiền "không còn là gánh nặng".
3. **User Stories:** * "Tôi muốn biết mình đã tiêu bao nhiêu cho ăn vặt chỉ bằng cách chụp ảnh, để cuối tháng không phải ăn mì tôm."
    * "Tôi muốn nhận cảnh báo khi sắp tiêu quá 80% ngân sách tuần." (Tránh kiểu viết: As a user I want AI to work).
4. **User Flow:** Splash -> Camera (Chụp hóa đơn) -> AI Processing -> Xác nhận thông tin -> Dashboard cập nhật.
5. **Analytics:** Tỷ lệ giữ chân (Retention) ngày 7, Độ chính xác của AI phân loại.
6. **Constraints:** Phụ thuộc vào chất lượng Camera và ánh sáng khi chụp hóa đơn.

#### 3 Thành phần AI-Specific:
7. **Model Selection:** **Gemini 1.5 Flash**.
    * *Lý do:* Tốc độ xử lý Multimodal cực nhanh, xử lý tiếng Việt tốt, chi phí API thấp phù hợp cho quy mô startup sinh viên.
    * *Trade-off:* Có thể nhầm lẫn giữa các hóa đơn có định dạng quá lạ (như hóa đơn viết tay chợ truyền thống).
8. **Data Source:** Dataset hóa đơn bán lẻ Việt Nam (hợp tác thu thập từ cộng đồng sinh viên) và Taxonomy tiêu dùng của General Statistics Office (GSO).
9. **Fallback UX:** Khi `confidence_score < 0.7`, hệ thống sẽ highlight vùng thông tin AI nghi ngờ và cho phép người dùng sửa nhanh bằng một chạm thay vì nhập lại từ đầu.

### 5.3 Final Checklist
- **Hypothesis:** 1 giả thuyết cho tính năng Coach: "Nếu gợi ý tiết kiệm được gửi vào khung giờ 19h (giờ đi chơi), tỷ lệ user dừng chi tiêu không cần thiết sẽ tăng 20%."
- **PMF Scorecard:**
    * **Aha Moment:** Khoảnh khắc user thấy biểu đồ chi tiêu tự nhảy số ngay sau khi chụp ảnh.
    * **Actionable Metric:** % người dùng thực hiện theo ít nhất 1 gợi ý của AI Coach trong tuần.
    * **PMF Method:** Khảo sát "Bạn sẽ cảm thấy thế nào nếu không thể sử dụng DOMIN-H nữa?" (Chỉ số thất vọng > 40%).

---
*Dự án được thực hiện bởi Jimala - Junior AI Engineer.*
