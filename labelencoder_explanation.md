
# 📌 Tại sao dùng `fit_transform()` cho train và chỉ `transform()` cho test khi dùng LabelEncoder?

Trong quá trình xử lý dữ liệu phân loại với `LabelEncoder`, bạn thường có hai tập dữ liệu:
- **Train (huấn luyện)**
- **Test (kiểm tra)**

Việc sử dụng đúng `fit_transform()` và `transform()` là **rất quan trọng** để đảm bảo rằng mô hình học đúng và dự đoán chính xác.

---

## ✅ Quy trình đúng

```python
from sklearn.preprocessing import LabelEncoder

le = LabelEncoder()
train_labels_enc = le.fit_transform(train_labels)  # Học mapping + mã hóa train
test_labels_enc = le.transform(test_labels)        # Dùng lại mapping để mã hóa test
```

### ✅ Vì sao làm như vậy?
- `fit_transform()` vừa **học mapping** từ train data, vừa **mã hóa**.
- `transform()` chỉ **áp dụng lại mapping đã học** cho dữ liệu test.

> Điều này đảm bảo rằng **cùng một nhãn sẽ được mã hóa giống nhau** ở cả train và test.

---

## ❌ Nếu bạn `fit()` lại trên test

```python
test_labels_enc = le.fit_transform(test_labels)  # ❌ Sai!
```

### ❌ Điều gì sẽ xảy ra?
- `LabelEncoder` sẽ **học lại mapping mới** từ test data.
- Mapping này có thể **khác với train**, gây lỗi nghiêm trọng cho mô hình.

### 🔥 Hậu quả:
- Mô hình đã học dựa trên mapping A (từ train), nhưng khi dự đoán lại nhận dữ liệu đã mã hóa theo mapping B (từ test).
- Dẫn đến **kết quả sai lệch hoàn toàn**.

---

## 🧠 Kết luận

| Bước           | Dùng gì?            | Ghi chú |
|----------------|---------------------|--------|
| Train          | `fit_transform()`   | Học và mã hóa |
| Test / Predict | `transform()`       | Dùng lại mapping cũ |
| ❌ Sai         | `fit_transform()` trên test | Học sai mapping |

Hãy luôn nhớ:
> ❗ "Chỉ **fit** trên tập train, không bao giờ fit trên test!"

