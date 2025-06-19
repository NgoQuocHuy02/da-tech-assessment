---
title: report_a05_customer_onboarding_analytics
---

# Phân Tích Hành Trình Onboarding Khách Hàng (KYC/AML)

---
## Thuật Ngữ
---

<details>
<summary>Giải Nghĩa Các Thuật Ngữ Quan Trọng Trong Onboarding và KYC/AML</summary>

---

| **Thuật Ngữ**              | **Định Nghĩa** |
|----------------------------|----------------|
| **KYC**                    | Know Your Customer – Quy trình xác minh danh tính khách hàng theo quy định. |
| **AML**                    | Anti-Money Laundering – Chống rửa tiền, đảm bảo khách hàng không liên quan đến hoạt động tài chính phi pháp. |
| **Onboarding**             | Quá trình đưa người dùng mới từ đăng ký đến khi có thể sử dụng đầy đủ dịch vụ. |
| **Chuyển đổi (Conversion)**| Tỷ lệ người dùng hoàn tất một bước hoặc toàn bộ quá trình onboarding. |
| **Phễu Onboarding (Funnel)** | Chuỗi các bước người dùng cần thực hiện trong quá trình onboarding (ví dụ: đăng ký → gửi giấy tờ → kích hoạt). |
| **Điểm ma sát (Friction Point)** | Các bước hoặc yếu tố trong quy trình gây cản trở, khiến người dùng dễ rời bỏ. |
| **OCR**                   | Optical Character Recognition – Công nghệ đọc ký tự từ ảnh giấy tờ. |
| **Xác minh sinh trắc (Liveness Check)** | Kiểm tra khuôn mặt hoặc chuyển động để đảm bảo người thật đang thao tác. |
| **PEP**                   | Politically Exposed Person – Cá nhân có ảnh hưởng chính trị, cần giám sát chặt chẽ hơn. |
| **Tỷ lệ chấp thuận (Approval Rate)** | Tỷ lệ hồ sơ người dùng được duyệt qua các bước xác minh. |
| **Tỷ lệ từ chối (Rejection Rate)** | Tỷ lệ hồ sơ bị từ chối qua các bước KYC. |
| **Tỷ lệ rớt bước (Drop-off Rate)** | Phần trăm người dùng không hoàn thành một bước nào đó trong phễu onboarding. |
| **Chờ xử lý thủ công**      | Những hồ sơ cần nhân viên can thiệp, không thể xử lý tự động. |
| **user\_id**                   | Mã định danh duy nhất của người dùng                                 |
| **registration\_channel**      | Kênh mà người dùng bắt đầu đăng ký (Web, Mobile, Referral...)        |
| **ocr\_confidence**            | Mức độ tin cậy của kết quả nhận dạng ký tự từ giấy tờ                |
| **face\_match\_score**         | Điểm đo mức độ khớp giữa ảnh selfie và giấy tờ tùy thân              |
| **liveness\_check**            | Quy trình kiểm tra người dùng là người thật, không phải ảnh hoặc bot |
| **pep\_flag / sanction\_flag** | Cờ đánh dấu người dùng nằm trong danh sách chính trị hoặc bị cấm vận |
| **internal\_risk\_score**      | Điểm rủi ro nội bộ do hệ thống đánh giá dựa trên các chỉ báo         |
| **abandonment\_flag**          | Biến đánh dấu người dùng đã từ bỏ quy trình tại một bước nào đó      |
| **retry\_count**               | Số lần người dùng gửi lại giấy tờ xác minh                           |

---
</details>

## Tóm Tắt Tổng Quan
---
<details>
<summary>Tổng Quan Cao Cấp về Khung Phân Tích và Tác Động Kinh Doanh Chính</summary>

---

- Phần này cung cấp một bản tóm tắt ngắn gọn về vấn đề, giải pháp đề xuất và lợi ích mong đợi.
- Nó nêu bật các thành phần cốt lõi của khung phân tích cho quy trình `onboarding` khách hàng và `KYC/AML`.
- Tập trung vào giá trị chiến lược của dự án đối với các bên liên quan trong kinh doanh.

---

</details>

---

## 1. Phát Biểu Vấn Đề
---
<details>
<summary>Mô Tả Chi Tiết Thách Thức Kinh Doanh trong Quy Trình Onboarding Khách Hàng và KYC/AML</summary>

---

- **Tình Hình Hiện Tại:**
  - Nhiều khách hàng tiềm năng bắt đầu quy trình đăng ký nhưng bỏ dở giữa chừng.
  - Tồn tại các `điểm ma sát` đáng kể, đặc biệt trong các bước xác minh `KYC/AML` phức tạp.
- **Hậu Quả:**
  - `Mất Khách Hàng Tiềm Năng`: Ảnh hưởng trực tiếp đến việc thu hút người dùng và tăng trưởng kinh doanh.
  - `Tăng Chi Phí Vận Hành`: Do hỗ trợ thủ công, xác minh thất bại và xử lý lại.
  - `Trải Nghiệm Khách Hàng Chưa Tối Ưu`: Dẫn đến sự khó chịu của người dùng và ấn tượng ban đầu tiêu cực.
  - `Rủi Ro Tuân Thủ`: Quy trình `KYC/AML` kém hiệu quả tiềm ẩn rủi ro pháp lý và tuân thủ.
- **Thách Thức Chung:** Chúng ta thiếu hiểu biết rõ ràng, dựa trên dữ liệu về hành trình `onboarding` của khách hàng để xác định chính xác các `điểm đau` và tối ưu hóa quy trình một cách hiệu quả, đồng thời duy trì tuân thủ.

---

</details>

---

## 2. Mục Tiêu Dự Án
---
<details>
<summary>Các Mục Tiêu Rõ Ràng và Kết Quả Mong Đợi của Sáng Kiến Phân Tích</summary>

---

- **Mục Tiêu Chính:**
  - Xây dựng một hệ thống phân tích mạnh mẽ để có cái nhìn sâu sắc về hành trình `onboarding` của khách hàng.
  - Hệ thống này sẽ cho phép tối ưu hóa quy trình, giảm tỷ lệ bỏ cuộc và nâng cao trải nghiệm người dùng.
  - Đồng thời, đảm bảo tuân thủ đầy đủ các quy định `KYC/AML`.
- **Các Câu Hỏi Chính Cần Trả Lời:**
  - `Bước nào` trong quy trình `onboarding` có tỷ lệ bỏ cuộc cao nhất?
  - `Tại sao` người dùng lại bỏ dở quy trình tại những điểm cụ thể đó?
  - `Mất bao lâu` để một khách hàng hoàn tất toàn bộ luồng `onboarding` và xác minh?
  - `Những cải tiến khả thi nào` có thể được thực hiện để tinh gọn và đơn giản hóa quy trình mà không ảnh hưởng đến bảo mật và tuân thủ?

---

</details>

---

## 3. Kế Hoạch và Các Giai Đoạn Dự Án
---
<details>
<summary>Chiến Lược Toàn Diện Từ Đầu Đến Cuối để Giải Quyết Vấn Đề Phân Tích Onboarding</summary>

---

- Kế hoạch này phác thảo phương pháp tiếp cận 4 giai đoạn, tập trung vào việc biến dữ liệu thô thành thông tin chi tiết có thể hành động:

  ---

  #### Giai Đoạn 1: Thu Thập & Chuẩn Bị Dữ Liệu (Xây Dựng Nền Tảng)
  ---
  - **Những Gì Chúng Ta Sẽ Làm:**
    - Hợp tác với các nhóm kỹ thuật để xác định và thu thập tất cả dữ liệu liên quan đến đăng ký và xác minh khách hàng.
    - Ví dụ về dữ liệu:
      - `Thời điểm đăng ký của người dùng` (`timestamp`) (bắt đầu, hoàn thành từng bước).
      - `Các bước cụ thể đã hoàn thành` hoặc đã cố gắng thực hiện.
      - `Lỗi gặp phải` trong quá trình.
      - `Thời gian chờ đợi` cho mỗi bước xác minh.
      - `Kết quả xác minh` (thành công/thất bại, lý do thất bại).
      - `Nhật ký liên lạc` với người dùng (ví dụ: thông báo email/SMS).
    - Thiết kế một `sơ đồ dữ liệu` (`blueprint`) hoặc `schema` rõ ràng để dễ hiểu và sử dụng.
  - **Mục Tiêu:**
    - Đảm bảo có sẵn dữ liệu sạch, chính xác và có thể sử dụng được để phân tích.

  ---

  #### Giai Đoạn 2: Xây Dựng Khung Phân Tích (Vẽ Bức Tranh Toàn Cảnh)
  ---
  - **Những Gì Chúng Ta Sẽ Làm:**
    - Xây dựng các `phễu` (`funnels`) để trực quan hóa toàn bộ hành trình của khách hàng từ khi bắt đầu đăng ký đến khi kích hoạt tài khoản.
    - Định nghĩa các `chỉ số hiệu suất chính` (`KPIs`) như:
      - `Tỷ lệ chuyển đổi theo từng bước`.
      - `Thời gian trung bình để hoàn tất xác minh`.
      - `Tỷ lệ thất bại KYC` theo lý do.
      - `Chi phí trên mỗi lần onboarding thành công`.
    - Đề xuất các phương pháp `kiểm thử A/B` (`A/B testing`) cho các luồng `onboarding` khác nhau hoặc so sánh hiệu suất với các `benchmark`.
  - **Mục Tiêu:**
    - Xác định chính xác các bước gây tắc nghẽn và hiểu rõ tác động của chúng.

  ---

  #### Giai Đoạn 3: Phân Tích Chuyên Sâu & Xác Định Vấn Đề (Tìm Ra Gốc Rễ)
  ---
  - **Những Gì Chúng Ta Sẽ Làm:**
    - Thực hiện phân tích chuyên sâu để hiểu `tại sao` khách hàng bỏ cuộc.
    - Điều tra các yếu tố như:
      - Độ phức tạp của quy trình tải tài liệu.
      - Thời gian chờ đợi phản hồi.
      - Sự rõ ràng của hướng dẫn.
    - Phân tích các trường hợp `KYC/AML bị từ chối` để xác định các lý do phổ biến và đề xuất cải thiện quy trình tuân thủ.
  - **Mục Tiêu:**
    - Chỉ ra nguyên nhân gốc rễ của các vấn đề và các cơ hội cải thiện cụ thể.

  ---

  #### Giai Đoạn 4: Báo Cáo & Đề Xuất Giải Pháp (Biến Dữ Liệu Thành Hành Động)
  ---
  - **Những Gì Chúng Ta Sẽ Làm:**
    - Tổng hợp các phát hiện vào một báo cáo rõ ràng, dễ hiểu, tập trung vào các khuyến nghị có thể hành động.
    - Ví dụ về các khuyến nghị:
      - `Đơn giản hóa bước X` trong luồng.
      - `Tự động hóa kiểm tra Y`.
      - `Cải thiện thông báo cho người dùng` ở bước Z.
    - Phác thảo `Dashboard` (bảng điều khiển) để các nhóm liên quan có thể dễ dàng theo dõi hiệu suất theo thời gian thực.
  - **Mục Tiêu:**
    - Cung cấp thông tin chi tiết và giải pháp để các nhóm Sản phẩm, Marketing, Vận hành và Tuân thủ có thể cùng nhau hợp tác, nâng cao trải nghiệm khách hàng và hiệu quả kinh doanh.

  ---

- **Sử Dụng Công Cụ GenAI:**
  - Trong suốt tất cả các giai đoạn, các công cụ `GenAI` sẽ được tận dụng để tăng tốc độ phân tích, tạo báo cáo và đảm bảo độ chính xác, tối đa hóa hiệu quả và chất lượng đầu ra.

---

</details>

---
## 4. Nguồn Dữ Liệu và Thiết Kế Schema
---
<details>
<summary>Mô Tả Chi Tiết về Các Nguồn Dữ Liệu Thô và Mô Hình Dữ Liệu Đề Xuất</summary>

---

#### 4.1 – Nguồn Dữ Liệu Thô (Raw Data Sources)
---
- Để xây dựng khung phân tích hành trình `onboarding`, chúng ta cần thu thập dữ liệu từ nhiều hệ thống khác nhau trong quy trình đăng ký và xác minh.
- Dưới đây là các nhóm dữ liệu thô chính:

  ---

  ##### 🧾 Nhóm 1: Dữ Liệu Đăng Ký Người Dùng (User Registration Logs)
  ---
  - Bao gồm tất cả thông tin liên quan đến thời điểm người dùng bắt đầu quá trình đăng ký.
  - Trường dữ liệu quan trọng:
    - `user_id`: Mã định danh duy nhất
    - `registration_start_time`: Thời điểm bắt đầu đăng ký
    - `registration_channel`: Web / mobile / referral
    - `device_type`, `os_version`, `browser`: Dùng để phân tích hành vi thiết bị
    - `language`, `region`: Phục vụ phân tích theo địa lý

  ---

  ##### 🪪 Nhóm 2: Dữ Liệu Xác Minh Danh Tính (Identity Verification Logs)
  ---
  - Bao gồm thông tin giấy tờ người dùng cung cấp và quá trình xử lý `OCR`.
  - Trường dữ liệu chính:
    - `doc_type`: CMND / CCCD / Passport
    - `ocr_status`, `ocr_confidence`: Kết quả nhận dạng ký tự
    - `upload_time`, `verification_result`, `rejection_reason`
    - `retry_count`: Số lần thử lại (nếu có)

  ---

  ##### 🧠 Nhóm 3: Dữ Liệu Sinh Trắc (Biometric Verification)
  ---
  - Xác minh người thật (`liveness`) và đối chiếu khuôn mặt.
  - Trường dữ liệu:
    - `face_match_score`: Mức độ khớp khuôn mặt
    - `liveness_check_result`: true/false
    - `device_camera_quality`: chất lượng camera
    - `frame_blur_score`: đánh giá độ rõ ảnh
    - `action_prompt_passed`: có làm đúng yêu cầu (nhìn trái/phải...)

  ---

  ##### 🚦 Nhóm 4: Đánh Giá Rủi Ro & Tuân Thủ (Risk & Compliance)
  ---
  - Dữ liệu từ hệ thống chống rửa tiền (`AML`) và kiểm tra `PEP/sanction`.
  - Trường dữ liệu:
    - `pep_flag`, `sanction_flag`: Có nằm trong danh sách hay không
    - `internal_risk_score`: Điểm đánh giá nội bộ
    - `risk_decision`: approve / manual_review / reject
    - `manual_review_reason` (nếu có)

  ---

  ##### 💬 Nhóm 5: Nhật Ký Tương Tác & Giao Tiếp (User Communication Logs)
  ---
  - Ghi lại các lần gửi `email`, thông báo, chăm sóc người dùng.
  - Trường dữ liệu:
    - `email_sent`, `sms_sent`, `push_notification_sent`
    - `time_sent`, `user_response_time`
    - `support_ticket_opened`, `ticket_status`, `assigned_agent_id`

  ---

  ##### 📱 Nhóm 6: Hành Vi Ứng Dụng (App Event Logs)
  ---
  - Dữ liệu hành vi như mở `app`, thao tác ở từng bước `onboarding`.
  - Trường dữ liệu:
    - `screen_viewed`, `step_started`, `step_completed`
    - `timestamp`, `session_duration`, `abandonment_flag`

  ---

- Những nhóm dữ liệu này là nền tảng để thiết kế `schema`, xác định `funnel` và tính `KPI` trong các phần tiếp theo.

---
#### 4.2 – Thiết Kế Schema Dữ Liệu Đề Xuất (Proposed Data Schema)
---
- Để hỗ trợ phân tích hành trình `onboarding` khách hàng và `KYC/AML`, chúng ta đề xuất một mô hình dữ liệu tập trung, bao gồm các bảng được thiết kế để thu thập và tổ chức thông tin từ các nguồn dữ liệu thô khác nhau.
- Mục tiêu là tạo ra một `schema` rõ ràng, dễ truy vấn, giúp tính toán các chỉ số `KPI` và xây dựng `phễu` (`funnel`) một cách hiệu quả.
- Các bảng chính trong `schema` đề xuất của chúng ta bao gồm:

  ---

  ##### 📊 Bảng: `dim_users` (Thông tin Người Dùng)
  ---
  - **Mục đích:** Chứa các thông tin cơ bản và thuộc tính tĩnh của người dùng.
  - **Mối quan hệ:** Liên kết với tất cả các bảng khác thông qua `user_id`.
  - **Cấu trúc bảng:**

    | Tên Trường (Field Name) | Kiểu Dữ Liệu (Data Type) | Mô Tả (Description) |
    | :---------------------- | :----------------------- | :------------------ |
    | `user_id`               | `STRING`                 | `Khóa chính` (`Primary Key`), mã định danh duy nhất của người dùng. |
    | `registration_start_time` | `TIMESTAMP`              | Thời điểm khách hàng bắt đầu quá trình đăng ký tài khoản. |
    | `registration_channel`  | `STRING`                 | Kênh đăng ký ban đầu (ví dụ: `Web`, `Mobile App`, `Referral`, `Partnership`). |
    | `device_type`           | `STRING`                 | Loại thiết bị được sử dụng để đăng ký (`Mobile`, `Tablet`, `Desktop`). |
    | `os_version`            | `STRING`                 | Phiên bản hệ điều hành (`iOS 17`, `Android 13`, `Windows 10`). |
    | `browser_type`          | `STRING`                 | Loại trình duyệt (`Chrome`, `Safari`, `Firefox`). |
    | `language_preference`   | `STRING`                 | Ngôn ngữ mà người dùng đã chọn hoặc hệ thống phát hiện. |
    | `geo_country`           | `STRING`                 | Quốc gia của người dùng dựa trên IP hoặc thông tin đăng ký ban đầu. |
    | `email`                 | `STRING`                 | Địa chỉ email được sử dụng khi đăng ký (có thể được mã hóa/băm để bảo mật). |
    | `phone_number`          | `STRING`                 | Số điện thoại được sử dụng (có thể được mã hóa/băm). |
    | `account_status`        | `STRING`                 | Trạng thái tài khoản hiện tại (`Pending`, `Verified`, `Rejected`, `Suspended`). |
    | `registration_completion_time` | `TIMESTAMP`         | Thời điểm người dùng hoàn tất quá trình đăng ký cơ bản. |

  ---

  ##### 📈 Bảng: `fact_onboarding_events` (Các Sự Kiện Hành Trình Onboarding)
  ---
  - **Mục đích:** Ghi lại từng sự kiện hoặc bước mà người dùng thực hiện trong quá trình `onboarding`. Đây là bảng chính để xây dựng `phễu` (`funnel`).
  - **Mối quan hệ:** Liên kết với `dim_users` qua `user_id`.
  - **Cấu trúc bảng:**

    | Tên Trường (Field Name) | Kiểu Dữ Liệu (Data Type) | Mô Tả (Description) |
    | :---------------------- | :----------------------- | :------------------ |
    | `event_id`              | `STRING`                 | `Khóa chính`, mã định danh duy nhất cho mỗi sự kiện. |
    | `user_id`               | `STRING`                 | `Khóa ngoại` (`Foreign Key`), liên kết đến `dim_users`. |
    | `event_timestamp`       | `TIMESTAMP`              | Thời điểm chính xác xảy ra sự kiện. |
    | `event_name`            | `STRING`                 | Tên của sự kiện (`KYC_STARTED`, `ID_DOCUMENT_UPLOADED`, `LIVENESS_CHECK_FAILED`, `ACCOUNT_ACTIVATED`). |
    | `onboarding_step`       | `INT`                    | Số thứ tự của bước trong hành trình `onboarding` (ví dụ: `1` cho đăng ký, `2` cho tải giấy tờ). |
    | `step_description`      | `STRING`                 | Mô tả chi tiết về bước `onboarding`. |
    | `event_status`          | `STRING`                 | Trạng thái của sự kiện (`SUCCESS`, `FAILURE`, `PENDING`, `RETRY`). |
    | `error_code`            | `STRING`                 | Mã lỗi (nếu có) khi sự kiện thất bại. |
    | `error_message`         | `STRING`                 | Mô tả lỗi dễ hiểu (nếu có). |
    | `session_id`            | `STRING`                 | `ID` của phiên làm việc mà sự kiện xảy ra. |
    | `duration_in_step_seconds` | `INT`                 | Thời gian người dùng ở lại trong bước này trước khi chuyển tiếp hoặc thoát. |

  ---

  ##### 📋 Bảng: `fact_kyc_verification_details` (Chi Tiết Xác Minh KYC)
  ---
  - **Mục đích:** Lưu trữ thông tin chi tiết về từng lần nộp/xác minh giấy tờ và sinh trắc học.
  - **Mối quan hệ:** Liên kết với `dim_users` qua `user_id`.
  - **Cấu trúc bảng:**

    | Tên Trường (Field Name) | Kiểu Dữ Liệu (Data Type) | Mô Tả (Description) |
    | :---------------------- | :----------------------- | :------------------ |
    | `kyc_submission_id`     | `STRING`                 | `Khóa chính`, mã định danh duy nhất cho mỗi lần nộp `KYC`. |
    | `user_id`               | `STRING`                 | `Khóa ngoại`, liên kết đến `dim_users`. |
    | `submission_timestamp`  | `TIMESTAMP`              | Thời điểm người dùng gửi thông tin `KYC`. |
    | `document_type`         | `STRING`                 | Loại giấy tờ được nộp (`Passport`, `National ID`, `Driver's License`). |
    | `ocr_status`            | `STRING`                 | Trạng thái nhận dạng `OCR` (`Success`, `Failure`, `Partial`). |
    | `ocr_confidence_score`  | `FLOAT`                  | Điểm tin cậy của kết quả `OCR` (0.0 - 1.0). |
    | `face_match_score`      | `FLOAT`                  | Điểm khớp khuôn mặt từ ảnh giấy tờ và ảnh `liveness` (0.0 - 1.0). |
    | `liveness_check_result` | `BOOLEAN`                | Kết quả kiểm tra người thật (`true` nếu là người thật). |
    | `kyc_result`            | `STRING`                 | Kết quả xác minh cuối cùng (`Approved`, `Rejected`, `Under Review`, `Retry Needed`). |
    | `rejection_reason`      | `ARRAY<STRING>`          | Danh sách các lý do từ chối (ví dụ: `Blurred Document`, `Face Mismatch`, `Document Expired`). |
    | `processing_time_seconds` | `INT`                  | Thời gian xử lý `KYC` tự động/thủ công. |
    | `agent_id`              | `STRING`                 | `ID` của nhân viên xử lý thủ công (nếu có). |
    | `number_of_retries`     | `INT`                    | Số lần người dùng phải nộp lại `KYC` cho lần này. |

  ---

  ##### 🚨 Bảng: `fact_risk_assessments` (Đánh Giá Rủi Ro)
  ---
  - **Mục đích:** Ghi lại kết quả các đánh giá rủi ro `AML`/`PEP`/`Sanction` cho người dùng.
  - **Mối quan hệ:** Liên kết với `dim_users` qua `user_id`.
  - **Cấu trúc bảng:**

    | Tên Trường (Field Name) | Kiểu Dữ Liệu (Data Type) | Mô Tả (Description) |
    | :---------------------- | :----------------------- | :------------------ |
    | `risk_assessment_id`    | `STRING`                 | `Khóa chính`, mã định danh duy nhất cho mỗi lần đánh giá rủi ro. |
    | `user_id`               | `STRING`                 | `Khóa ngoại`, liên kết đến `dim_users`. |
    | `assessment_timestamp`  | `TIMESTAMP`              | Thời điểm đánh giá rủi ro được thực hiện. |
    | `risk_score`            | `INT`                    | Điểm rủi ro tổng thể của người dùng (ví dụ: 1-100). |
    | `pep_flag`              | `BOOLEAN`                | `True` nếu người dùng được xác định là `PEP` (Người có ảnh hưởng chính trị). |
    | `sanction_flag`         | `BOOLEAN`                | `True` nếu người dùng nằm trong danh sách trừng phạt. |
    | `aml_status`            | `STRING`                 | Trạng thái kiểm tra `AML` (`Clear`, `Match Found`, `Under Investigation`). |
    | `final_risk_decision`   | `STRING`                 | Quyết định rủi ro cuối cùng (`Approved`, `Manual Review`, `Rejected`). |
    | `decision_reason`       | `ARRAY<STRING>`          | Các lý do cụ thể cho quyết định rủi ro. |

  ---

  ##### 📧 Bảng: `fact_user_communications` (Tương Tác & Giao Tiếp Người Dùng)
  ---
  - **Mục đích:** Ghi lại tất cả các thông điệp hệ thống hoặc từ bộ phận hỗ trợ gửi đến người dùng trong quá trình `onboarding`.
  - **Mối quan hệ:** Liên kết với `dim_users` qua `user_id`.
  - **Cấu trúc bảng:**

    | Tên Trường (Field Name) | Kiểu Dữ Liệu (Data Type) | Mô Tả (Description) |
    | :---------------------- | :----------------------- | :------------------ |
    | `communication_id`      | `STRING`                 | `Khóa chính`, mã định danh duy nhất cho mỗi lần giao tiếp. |
    | `user_id`               | `STRING`                 | `Khóa ngoại`, liên kết đến `dim_users`. |
    | `communication_timestamp` | `TIMESTAMP`            | Thời điểm gửi tin nhắn/thông báo. |
    | `communication_type`    | `STRING`                 | Loại giao tiếp (`Email`, `SMS`, `Push Notification`, `In-App Message`). |
    | `message_content`       | `STRING`                 | Nội dung chính của tin nhắn (có thể cắt ngắn hoặc mã hóa). |
    | `delivery_status`       | `STRING`                 | Trạng thái gửi (`Sent`, `Delivered`, `Failed`, `Opened`). |
    | `user_interaction_status` | `STRING`               | Trạng thái tương tác của người dùng (`Clicked`, `Ignored`, `Responded`). |
    | `support_ticket_id`     | `STRING`                 | `ID` của `ticket` hỗ trợ liên quan (nếu có). |

  ---
  ##### 📄 Bảng: `fact_manual_review_logs` (Nhật Ký Duyệt Thủ Công)
  ---
  - **Mục đích:** Ghi lại thông tin chi tiết về quá trình duyệt `KYC` thủ công bởi nhân viên.
  - **Mối quan hệ:** Liên kết với `dim_users` qua `user_id` và có thể liên kết với `fact_kyc_verification_details` qua `kyc_submission_id`.
  - **Cấu trúc bảng:**

    | Tên Trường (Field Name) | Kiểu Dữ Liệu (Data Type) | Mô Tả (Description) |
    | :---------------------- | :----------------------- | :------------------ |
    | `review_id`             | `STRING`                 | `Khóa chính`, mã định danh duy nhất cho mỗi lần duyệt thủ công. |
    | `user_id`               | `STRING`                 | `Khóa ngoại`, liên kết đến `dim_users`. |
    | `kyc_submission_id`     | `STRING`                 | `Khóa ngoại`, liên kết đến `fact_kyc_verification_details`. |
    | `review_start_time`     | `TIMESTAMP`              | Thời điểm bắt đầu quá trình duyệt. |
    | `review_end_time`       | `TIMESTAMP`              | Thời điểm kết thúc quá trình duyệt. |
    | `review_result`         | `STRING`                 | Kết quả duyệt (`Approved`, `Rejected`, `Needs More Info`). |
    | `review_notes`          | `STRING`                 | Ghi chú của người duyệt về trường hợp này. |
    | `reviewer_id`           | `STRING`                 | `ID` của nhân viên thực hiện duyệt. |

  ---

  ##### 📊 Sơ đồ quan hệ giữa các bảng (ERD)
  ---

  ```mermaid
  erDiagram
      dim_users ||--o{ fact_onboarding_events : has
      dim_users ||--o{ fact_kyc_verification_details : has
      dim_users ||--o{ fact_risk_assessments : has
      dim_users ||--o{ fact_user_communications : has
      dim_users ||--o{ fact_manual_review_logs : has
      fact_kyc_verification_details ||--o{ fact_manual_review_logs : triggers
  ```
---
- Việc thiết kế `schema` này đảm bảo tính toàn vẹn dữ liệu, hiệu quả truy vấn và khả năng mở rộng, là nền tảng vững chắc cho việc phân tích chuyên sâu ở các giai đoạn tiếp theo.

---

</details>

---

## 5. Logic Chuyển Đổi Dữ Liệu
---
<details>
<summary>Mô Tả Các Quy Trình Làm Sạch, Chuẩn Hóa và Tổng Hợp Dữ Liệu</summary>

---

- Phần này sẽ phác thảo các bước để chuyển đổi dữ liệu thô thành định dạng có thể sử dụng được để phân tích.

---

</details>

---

## 6. Khung Phân Tích và Các KPIs
---
<details>
<summary>Định Nghĩa Các Chỉ Số Hiệu Suất Chính và Các Phương Pháp Phân Tích</summary>

---

- Phần này sẽ trình bày chi tiết phương pháp phân tích `phễu` (`funnel analysis`), định nghĩa tỷ lệ `chuyển đổi` (`conversion rates`) và các chỉ số liên quan khác.

---

</details>

---

## 7. Chiến Lược Báo Cáo và Dashboard
---
<details>
<summary>Các Hình Ảnh Trực Quan và Cấu Trúc Báo Cáo Đề Xuất cho Các Bên Liên Quan</summary>

---

- Phần này sẽ đề cập đến cách các thông tin chi tiết sẽ được trình bày và các `dashboard` sẽ được thiết kế.

---

</details>

---

## 8. Tác Động Kinh Doanh và Khuyến Nghị
---
<details>
<summary>Các Khuyến Nghị Cụ Thể và Kết Quả Mong Đợi để Cải Thiện Kinh Doanh</summary>

---

- Phần này sẽ tóm tắt các lời khuyên có thể hành động và những tác động tích cực dự kiến đến kinh doanh.

---

</details>