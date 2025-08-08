
# So sánh AdaBoost, Gradient Boosting (GBM), và XGBoost

| **Tiêu chí**               | **AdaBoost**                              | **Gradient Boosting (GBM)**                          | **XGBoost**                                        |
|---------------------------|-------------------------------------------|-----------------------------------------------------|---------------------------------------------------|
| **Ý tưởng chính**         | Trọng số mẫu tăng cho mẫu sai             | Boosting với gradient descent                       | GBM cải tiến + tối ưu hiệu năng                   |
| **Tốc độ huấn luyện**     | Chậm với dữ liệu lớn                      | Trung bình                                          | Nhanh nhất (dùng song song, cache...)            |
| **Độ chính xác**          | Tốt trong dữ liệu nhiễu thấp              | Tốt                                                 | Thường tốt nhất                                   |
| **Chống overfitting**     | Trung bình                                | Trung bình                                          | Tốt hơn nhờ regularization (L1/L2)               |
| **Hỗ trợ GPU**            | ❌ Không                                   | ❌ Không                                             | ✅ Có (rất nhanh)                                 |
| **Xử lý missing values**  | ❌ Không tự động                           | ❌ Không tự động                                     | ✅ Tự động xử lý missing                          |
| **Regularization**        | ❌ Không                                   | ❌ Không                                             | ✅ Có (alpha, lambda)                             |
| **Tùy biến cao**          | Thấp                                      | Vừa                                                 | ✅ Rất cao                                        |
| **Triển khai sản phẩm**   | Dễ, nhẹ                                   | Vừa                                                 | Khá dễ, thư viện mạnh                             |
| **Thư viện chính**        | `sklearn.ensemble.AdaBoostClassifier`     | `sklearn.ensemble.GradientBoostingClassifier`       | `xgboost.XGBClassifier`                           |
