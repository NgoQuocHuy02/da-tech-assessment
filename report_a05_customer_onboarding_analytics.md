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