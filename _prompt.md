---
title: _prompt
---

# Prompts used for Task A05 – Customer Onboarding Journey Analytics (KYC/AML)

This file documents the GenAI prompts used during the execution of Task A05.  
Each prompt includes the original query, its purpose, and where it was applied in the report.

---

## Day 1 – Task Selection and Preparation

---

### Prompt 1 – Understanding the Assignment
<details>
<summary>Ask GenAI to help interpret the test document and summarize task structure</summary>

---

**Prompt:**
> Tôi mới nhận được thông báo vượt qua vòng duyệt CV cho vị trí DA, họ gửi kèm một bài test yêu cầu tôi làm trong 5 ngày. Tôi sẽ cung cấp bài test đó cho bạn, bạn hãy đọc và trình bày lại cho tôi nắm.

**Purpose:**
- Hiểu rõ yêu cầu bài test tổng thể và các nhiệm vụ trong List A và List B

**Used for:**
- Định hướng ban đầu để chọn task phù hợp

---
</details>

---

### Prompt 2 – Evaluate Task Options
<details>
<summary>Ask GenAI to help decide which task to focus on given time constraints</summary>

---

**Prompt:**
> Với các nhiệm vụ ở danh sách A, theo bạn trong thời gian cho phép chúng ta nên bắt đầu với dự án nào trước?

**Purpose:**
- So sánh các nhiệm vụ trong List A để chọn ra task phù hợp nhất với thời gian và kiến thức

**Decision:**
- Ban đầu chọn A01 → Sau đó chuyển sang A05 vì đơn giản hơn

---
</details>

---

### Prompt 3 – Confirm Markdown Style Rules
<details>
<summary>Ask GenAI to understand the formatting requirements from ctx_doc_style.md</summary>

---

**Prompt:**
> Trước khi chọn nhiệm vụ, tôi sẽ cung cấp file `.md` về quy tắc viết markdown cho bạn, bạn hãy ghi nhớ chuẩn này để viết báo cáo cho đúng.

**Purpose:**
- Đảm bảo toàn bộ nội dung sau này tuân thủ định dạng chuẩn của công ty

**Used in:**
- Tất cả các section trong `report_A05.md` sau này

---
</details>

---

### Prompt 4 – Review and Improve Prompt Documentation
<details>
<summary>Ask GenAI to review and reformat the prompt log for Task A05</summary>

---

**Prompt:**
> Đây là file prompt tôi viết:  
> ```
> ---
> title: _prompt 
> ---
> 
> # Prompts used for Task A05 – Customer Onboarding Journey Analytics (KYC/AML)
> ...
> ```
> chuyển về chuẩn giúp tôi

**Purpose:**
- Nhờ GenAI đánh giá và chỉnh sửa file prompt để đúng chuẩn định dạng và yêu cầu trong bài test
- Cải thiện tính rõ ràng, mạch lạc, và tuân thủ style `ctx_doc_style.md`

**Result:**
- File `report_A05_prompt.md` được tái cấu trúc lại theo format chính thức, bao gồm:
  - Tên file theo chuẩn YAML
  - Các prompt chia thành khối `<details>`
  - Có mục đích và vị trí sử dụng rõ ràng

**Used in:**
- Toàn bộ phần cấu trúc ngày đầu tiên trong file prompt chính thức

---
</details>

---

## Notes

- GenAI tool used: ChatGPT (GPT-4o)
- Các tài liệu sinh ra sẽ được format lại để phù hợp với `ctx_doc_style.md`
