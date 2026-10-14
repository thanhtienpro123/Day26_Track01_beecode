# Memo quyết định · AI adoption

**Ngày lập:** 14/10/2026

**Sản phẩm:** trợ lý AI tra cứu tài liệu nội bộ

**Người dùng chính:** nhân viên vận hành của một nhóm pilot
**Quy trình:** tra cứu SOP; đối chiếu phiên bản chính sách; trả lời câu hỏi nội bộ.

## 1. Vấn đề và nguyên nhân gốc

Tình huống lab giả định nhân viên vẫn tìm file hoặc hỏi đồng nghiệp dù đã có trợ lý AI. Hai **giả thuyết nguyên nhân gốc**: (1) AI chưa gắn vào bước tra cứu có owner, kiểm nguồn và bàn giao; (2) câu trả lời chưa có nguồn/phiên bản đủ rõ để người dùng tin và kiểm chứng. “Ít sử dụng” là triệu chứng. Nguyễn Thành Tiến sẽ xác nhận hai giả thuyết qua 5–10 ca quan sát và log D1–D7.

## 2. Framework và bằng chứng

- **Gartner-Lite:** Direction đã khoá ở một sản phẩm, một nhóm và ba workflow. Readiness cần xác minh nguồn, quyền, lịch cập nhật; Absorption cần owner QA và vòng phản hồi.
- **Mollick:** AI tìm/tóm tắt; nhân viên kiểm nguồn và owner quy trình quyết định cuối. Chưa tự động phê duyệt chính sách. **ADKAR:** thiếu nguồn tác động Desire, thiếu hướng dẫn tại bước việc tác động Knowledge/Ability, thiếu phản hồi làm yếu Reinforcement.
- **Bằng chứng tham khảo:** [Morgan Stanley công bố trợ lý nội bộ dẫn đến tài liệu nguồn](https://www.morganstanley.com/press-releases/key-milestone-in-innovation-journey-with-openai); [OpenAI mô tả việc đánh giá với chuyên gia và cải thiện truy xuất](https://openai.com/index/morgan-stanley/). Đây là bài học thiết kế, không phải log của nhóm. Dấu hiệu trong đề là quay lại tìm file; cần kiểm chứng tại pilot.

## 3. Hai thay đổi sau rà soát bản v1

| Góp ý cụ thể khi tự rà soát theo khung phản biện của đề | V1 | V2 |
| :--- | :--- | :--- |
| Số câu hỏi là activity, không chứng minh độ tin cậy. | Product metric: ≥100 câu hỏi/tuần. | Product metric: ≥95% câu trả lời AI có nguồn hợp lệ; QA kiểm link, phiên bản, ngày và nội dung. |
| Phút tiết kiệm tự khai không đối chiếu được với tác vụ. | Workflow metric: ≥20 phút/ngày tự khai. | Phút xử lý TB/tác vụ SOP hoàn thành từ log gắn ID; mục tiêu ≤80% baseline ở gate 90. |

V2 bổ sung mẫu log, tỷ lệ chuyển người khi thiếu nguồn và gate chất lượng. **Chưa có phản biện chéo thực tế từ nhóm khác**; hai góp ý trên là rà soát mô phỏng và cần thay bằng biên bản góp ý thật nếu có.

## 4. Quyết định

**SỬA trong pilot, chưa mở rộng.** Chưa có baseline nội bộ và chưa xác nhận đầy đủ dữ liệu, quyền truy cập, owner nguồn và cơ chế QA. Không quyết định mở rộng chỉ từ lượt dùng công cụ.

## 5. Lý do, bước tiếp theo và owner

Trong 0–30 ngày, **Nguyễn Thành Tiến** ghi baseline D1–D7, quan sát ca thật và chốt data owner; **Văn A** kiểm danh mục nguồn, quyền và bàn giao. Gate 30 cần baseline và owner. Trong 31–60 ngày, **Ngyễn B** QA ít nhất 30 câu AI; gate 60 đòi nguồn hợp lệ ≥95%, người kiểm ≥90% và thiếu nguồn chuyển người 100%. Trong 61–90 ngày, Nguyễn Thành Tiến quyết định tiếp tục/sửa/dừng dựa vào gate 60, tỷ lệ SOP không QA làm lại ≥85%, thời gian ≤80% baseline và mức dùng SOP ≥70%. Nếu thiếu điều kiện, owner sửa nguyên nhân và đo lại trước khi mở rộng.

Xem [dashboard v2](../dashboard/dashboard_hanh_dong_v2.xlsx) để nhập dữ liệu thật và [dashboard v1](../v1/dashboard_hanh_dong_v1.xlsx) để đối chiếu.
