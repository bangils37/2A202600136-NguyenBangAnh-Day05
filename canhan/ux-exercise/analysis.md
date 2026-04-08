# Ý tưởng sản phẩm

## Sản phẩm hướng tới

* **Quản lý tài chính cá nhân**
* **Tự động phân loại chi tiêu**
* **Chatbot trả lời / gợi ý dữ liệu**
* **Đặt mục tiêu ngân sách**
* **Tìm kiếm giao dịch**
* **Tìm khuyến mãi phù hợp**

---

# 2. Phân tích 4 paths vs Use case: Phân loại giao dịch

### Khi hệ thống phân loại **đúng**

* Hiển thị luôn kết quả phân loại cho người dùng.

### Khi hệ thống phân loại **sai**

* Hiển thị kết quả phân loại.
* Người dùng có thể **bấm vào để phân loại lại**.

Ví dụ:

* Nội dung giao dịch: `"đi ăn đê"`
* Hệ thống có thể phân loại nhầm sang **từ thiện** (theo rule).

### Trường hợp **không chắc chắn**

Hệ thống đề xuất phân loại dựa theo:

* Thời gian
* Số tiền
* Nội dung giao dịch
* Lịch sử giao dịch

---

### Vấn đề niềm tin của user

Nếu:

* User **mất niềm tin** vì hệ thống **phân loại sai liên tục**

Thì:

* User sẽ **không tin vào phân loại tự động nữa**
* Khó thuyết phục họ sử dụng lại

Mục tiêu:

* Làm cho việc sửa lại **dễ tìm, dễ thao tác**

---

# 3. Sketch Flow khi hệ thống không chắc chắn

## Cách hiện tại

```
Giao dịch user
      ↓
Tự động phân loại
      ↓
Hiển thị kết quả
      ↓
User có thể sửa lại
```

---

## Cách đề xuất (tốt hơn)

```
Giao dịch
     ↓
Hệ thống phân loại + tính xác suất từng loại
     ↓
Lấy 3 loại có xác suất cao nhất
     ↓
Hiển thị theo thứ tự xác suất (cao → thấp)
     ↓
User chọn loại phù hợp
     ↓
Hoặc chọn từ dropdown loại khác
```

### Kết quả

* User chọn → **cập nhật lại gợi ý**
* Hệ thống **chốt loại có xác suất cao nhất**

---

💡 **Ý tưởng cốt lõi:**
Thay vì chỉ **auto classify → sửa**, hệ thống nên **đưa ra nhiều lựa chọn có xác suất cao** để user chọn nhanh → tăng **độ tin tưởng + trải nghiệm tốt hơn**.
