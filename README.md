# Day26_Track01_beecode · AI adoption change management

> **Tình huống lab giả định.** Chưa có log vận hành, MSSV của hai thành viên mẫu hay phản biện từ nhóm khác. Các nhận định về nội bộ là giả thuyết cần kiểm chứng; dashboard không dùng số liệu giả làm kết quả thực tế.

## 1. Thành viên và đóng góp

| Họ tên | MSSV | Phần phụ trách | Góp ý đã đưa cho nhóm bạn |
| :--- | :--- | :--- | :--- |
| Nguyễn Thành Tiến | 2A202603003 | Phạm vi, workflow, năng suất và memo | Chưa có thông tin nhóm phản biện ngoài. |
| Văn A | Chưa cung cấp | Gartner-Lite, ADKAR, sử dụng và bàn giao | Chưa có thông tin nhóm phản biện ngoài. |
| Ngyễn B | Chưa cung cấp | Mollick, QA nguồn và chất lượng | Chưa có thông tin nhóm phản biện ngoài. |

Hai góp ý cụ thể trong [memo](memo/memo_quyet_dinh.md) là **tự rà soát v1 theo bốn trục của đề**, không phải phản biện chéo đã diễn ra với nhóm khác.

## 2. Phạm vi

**Một sản phẩm:** trợ lý AI tra cứu tài liệu nội bộ. **Một nhóm người dùng chính:** nhân viên vận hành của một nhóm pilot. **Ba workflow:** tra cứu SOP để xử lý yêu cầu; đối chiếu phiên bản chính sách; trả lời câu hỏi nội bộ. Vấn đề cần đo: nhân viên vẫn quay lại tìm file hoặc hỏi đồng nghiệp sau khi có trợ lý AI.

## 3. Nguyên nhân gốc cần kiểm chứng

1. **AI chưa nằm trong quy trình có owner và bàn giao.** Gartner-Lite gợi ý thiếu Absorption; Mollick chỉ ra bước kiểm nguồn và phê duyệt cuối chưa được giao rõ. Dấu hiệu của tình huống lab là người dùng quay lại tìm file; cần quan sát 5–10 ca thật ở ngày 1–7.
2. **Câu trả lời chưa đủ căn cứ để tin.** Gartner-Lite đặt câu hỏi về Readiness của tài liệu và quyền truy cập; ADKAR dự đoán nghẽn Desire/Ability khi không thấy nguồn hoặc không biết cách kiểm. [Morgan Stanley gắn câu trả lời với tài liệu nguồn](https://www.morganstanley.com/press-releases/key-milestone-in-innovation-journey-with-openai) và [dùng đánh giá với chuyên gia trước khi mở rộng](https://openai.com/index/morgan-stanley/). Đây là bằng chứng tham khảo về thiết kế, **không chứng minh** nguyên nhân tại nhóm giả định.

## 4. Cách làm mới

| AS-IS | TO-BE · owner và kiểm soát |
| :--- | :--- |
| Tìm nhiều thư mục, hỏi đồng nghiệp rồi tự chọn file. | Hỏi AI trong tác vụ có ID, chọn một trong ba workflow. |
| Có thể không rõ bản tài liệu đang dùng. | AI tìm/tóm tắt tài liệu được phép truy cập; hiện link nguồn, phiên bản và ngày cập nhật. |
| Không có bước kiểm chứng hoặc báo lỗi thống nhất. | Nhân viên mở nguồn và đối chiếu; owner quy trình chịu trách nhiệm kết quả cuối. Thiếu nguồn/xung đột phiên bản thì **chuyển người**, không dùng câu trả lời AI. |
| Sai sót chỉ nằm trong trao đổi cá nhân. | QA kiểm mẫu và ghi lỗi theo ID; data owner sửa tài liệu, AI owner sửa truy xuất rồi kiểm lại. |

**Mollick:** người giữ quyền phê duyệt, ngoại lệ và trách nhiệm; AI hỗ trợ tìm/tóm tắt; chưa tự động phê duyệt hoặc phát hành chính sách. **Chuỗi tin cậy:** nguồn → trích nguồn → QA mẫu → chuyển người → phản hồi. Trong mô hình lab, Nguyễn Thành Tiến là workflow/data owner, Văn A là AI owner, Ngyễn B là QA owner.

## 5. Chỉ số ra quyết định

Chi tiết năm tầng đo và mẫu log ở [dashboard v2](dashboard/dashboard_hanh_dong_v2.xlsx); [v1](v1/dashboard_hanh_dong_v1.xlsx) giữ để đối chiếu. Baseline chưa có; nhập log giai đoạn Baseline trong D1–D7, rồi chốt mục tiêu đề xuất tại gate 30.

| Cấp | Chỉ số | Baseline | Target đề xuất | Nguồn | Owner | Khi xấu |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| Product | Tỷ lệ câu trả lời AI có nguồn hợp lệ | Đo D1–D7 từ log + QA mẫu | ≥95% ở gate 60 | Log AI, link nguồn, phiếu QA | Ngyễn B | Khoá nguồn lỗi, tăng QA, sửa truy xuất. |
| Workflow · tra cứu SOP | Phút xử lý TB/tác vụ hoàn thành | Đo D1–D7 từ log tác vụ | ≤80% baseline ở gate 90 | Log tác vụ gắn ID | Nguyễn Thành Tiến | Phân tích bước chờ, ca ngoại lệ và sửa quy trình. |

Dashboard còn đo mức dùng theo workflow, kiểm nguồn của người dùng, tỷ lệ không phải QA làm lại và chuyển người khi thiếu nguồn. Một dòng log cho một tác vụ; chỉ số thiếu mẫu số hiện “Chưa đo”, không bị biến thành 0.

## 6. Quyết định

**SỬA trong pilot, chưa mở rộng:** chưa có baseline nội bộ; owner tài liệu và kiểm soát nguồn cần xác nhận. Hai sửa đổi v1 → v2: (1) số câu hỏi thành tỷ lệ câu trả lời có nguồn hợp lệ ở cấp product; (2) thời gian tự khai thành thời gian từ log tác vụ. V2 còn thêm log bàn giao và gate chất lượng.

## Phân tích và lộ trình 30–60–90

| Giai đoạn / gate | Việc kiểm chứng và thay đổi | Owner | Dấu hiệu hoàn thành để qua gate |
| :--- | :--- | :--- | :--- |
| **0–30 ngày · chứng minh vấn đề** | Quan sát 5–10 ca; vẽ AS-IS; xác nhận workflow, owner, lịch cập nhật và quyền; thu baseline D1–D7. | Nguyễn Thành Tiến (workflow/data), Văn A (AI) | Có baseline có mẫu số, ID tác vụ, danh mục nguồn và owner; nhóm xác nhận mục tiêu. Thiếu thì sửa readiness. |
| **31–60 ngày · chứng minh chất lượng** | Bật trích nguồn/ngày cập nhật, hướng dẫn kiểm nguồn tại tác vụ, QA ít nhất 30 câu AI, xử lý lỗi và bàn giao. | Ngyễn B (QA), Văn A (AI) | Nguồn hợp lệ ≥95%, có người kiểm ≥90%, ca thiếu nguồn chuyển người 100%; không đạt thì chưa mở rộng. |
| **61–90 ngày · quyết định mở rộng** | So sánh cùng loại tác vụ với baseline; rà governance, hỗ trợ, chi phí và ca lỗi tồn. | Nguyễn Thành Tiến (quyết định), Ngyễn B (QA) | Ngoài gate 60: SOP không QA làm lại ≥85%, thời gian TB ≤80% baseline, tỷ lệ SOP dùng AI ≥70%; chỉ mở rộng nếu toàn bộ đạt. |

**ADKAR:** giải thích loại câu hỏi nên dùng AI (Awareness); trích nguồn để tăng niềm tin (Desire); hướng dẫn hỏi/kiểm (Knowledge); kèm ca thật và hỗ trợ tại chỗ (Ability); xem log, QA và phản hồi lỗi hàng tuần (Reinforcement). **Gartner-Lite:** Direction đã rõ; Readiness và Absorption chỉ coi là đạt sau gate 30–60. Không dùng lượt login hay số câu hỏi để quyết định mở rộng.

## Tự kiểm trước khi nộp

| Hạng mục | Trạng thái |
| :--- | :--- |
| Đúng tên repo, nhánh main; có README, dashboard v1/v2 và memo | Đã chuẩn bị trong repo. |
| Phạm vi, framework, workflow, owner, gate 30–60–90, chỉ số và quyết định | Có trong README, dashboard và memo. |
| Hai thay đổi v1 → v2 có thể đối chiếu | Có; xem hai file dashboard và memo. |
| Baseline, MSSV của hai tên mẫu, phản biện chéo thực tế | Chưa được cung cấp; cần dữ liệu/hoạt động thật nếu giảng viên yêu cầu minh chứng thực tế. |
| Public và mở được khi không đăng nhập | Đã xác nhận trang repo công khai; kiểm tra lại nội dung sau khi đẩy. |
| Các thành viên cùng dán link Vlearn | Chỉ mỗi thành viên có thể hoàn tất trên tài khoản Vlearn của mình. |

Không đưa dữ liệu nội bộ nhạy cảm vào mẫu log. Repo chứa phương án và biểu mẫu đo, chưa phải báo cáo kết quả pilot đã diễn ra.
