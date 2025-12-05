# Bài tập lớn Học máy – Dữ liệu dạng bảng (Adult Income)

## 1. Thông tin chung

- Môn học: Học máy  
- Thông tin giảng viên hướng dẫn: Trương Vĩnh Lân
- Chủ đề: 4.1 – Học máy với dữ liệu dạng bảng (Tabular Data)  
- Dataset: Adult / Census Income (UCI Machine Learning Repository)  
- Bài toán: Dự đoán thu nhập cá nhân `<=50K` hay `>50K` dựa trên thông tin nhân khẩu học và công việc.  

## 2. Cấu trúc thư mục
```
├── data/
│ └── adult.data # Dữ liệu gốc (https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data)
├── notebooks/
│ └── adult_income_pipeline.ipynb # Notebook chính: EDA + tiền xử lý + mô hình
├── reports/
│ └── report_adult_income.pdf # Báo cáo bài tập lớn
└── README.md
```

## 3. Nội dung notebook chính

### 3.1. EDA (Exploratory Data Analysis)

- Thống kê mô tả dữ liệu, kiểm tra số lượng dòng/cột, kiểu dữ liệu.  
- Phân tích missing value cho các cột `workclass`, `occupation`, `native-country`, …  
- Trực quan hoá phân phối các biến số (`age`, `fnlwgt`, `education-num`, `capital-gain`, `capital-loss`, `hours-per-week`).  
- Phân tích quan hệ giữa một số đặc trưng và biến mục tiêu (`education vs income`, `hours-per-week vs income`, …).  
- Ma trận tương quan cho các biến số.

### 3.2. Tiền xử lý dữ liệu

- Điền giá trị thiếu:
  - Biến phân loại: điền bằng mode từng cột.  
  - Biến số: điền bằng median.  
- Mã hóa biến phân loại bằng `LabelEncoder`.  
- Chuẩn hóa các biến số bằng `StandardScaler`.  
- Chia dữ liệu thành tập train/test (ví dụ: 80% train, 20% test).

### 3.3. Mô hình học máy truyền thống

- **Logistic Regression**
  - Huấn luyện mô hình baseline.  
  - Đánh giá bằng Accuracy, Precision, Recall, F1-score, confusion matrix, ROC/AUC.  

- **Random Forest**
  - Huấn luyện mô hình ensemble trên cùng tập đặc trưng.  
  - Đánh giá bằng các chỉ số tương tự để so sánh với Logistic Regression.  

### 3.4. Mô hình Deep Learning (tf.keras)

- Xây dựng mạng nơ-ron nhiều lớp (MLP) với:
  - Các tầng Dense ẩn (ReLU) và Dropout.  
  - Tầng đầu ra sigmoid cho phân loại nhị phân.  
- Huấn luyện với optimizer Adam, loss binary cross-entropy.  
- Vẽ learning curve (loss, val_loss), confusion matrix và ROC/AUC.  

### 3.5. So sánh kết quả

- Bảng so sánh hiệu suất 3 mô hình: Logistic Regression, Random Forest, Tensorflow Keras.  
- Phân tích theo lớp `<=50K` và `>50K` dựa trên Precision, Recall, F1-score.  
- Nhận xét ảnh hưởng của mất cân bằng dữ liệu và ưu/nhược điểm của từng mô hình.

## 4. Cách chạy

1. Cài đặt môi trường Python (khuyến nghị: Google Colab hoặc môi trường có sẵn scikit-learn, pandas, matplotlib, seaborn, tensorflow).  
2. File đã được load sẵn trong notebook từ link công khai (https://archive.ics.uci.edu/ml/machine-learning-databases/adult/adult.data) 
3. Mở notebook `notebooks/adult_income_pipeline.ipynb`.  
4. Chạy `Run all` để thực hiện toàn bộ pipeline từ EDA, tiền xử lý đến huấn luyện và so sánh các mô hình.

## 5. Thành viên nhóm

- Mai Thanh Hải – 2033504 – 
  Nhiệm vụ chính:
  - Tìm kiếm và chuẩn bị dữ liệu Adult.
  - Thực hiện EDA: thống kê, vẽ biểu đồ, phân tích phân phối và tương quan.
  - Thiết kế và cài đặt pipeline tiền xử lý (missing value, mã hóa, chuẩn hóa, chia train/test).
  - Cài đặt và huấn luyện các mô hình: Logistic Regression, Random Forest
  - Viết các phần báo cáo: Giới thiệu, Mô tả dữ liệu, EDA, Tiền xử lý, Mô hình học máy truyền thống.


- Nguyễn Đức Việt – 2115274 –
  Nhiệm vụ chính:
  - Cài đặt và huấn luyện mô hình Tensorflow Keras.
  - Thực hiện đánh giá, vẽ confusion matrix, ROC, bảng so sánh chỉ số.
  - Phân tích kết quả, nhận xét về mất cân bằng dữ liệu, so sánh mô hình, viết kết luận.
  - Chuẩn bị README, chỉnh sửa format báo cáo, hoàn thiện cấu trúc thư mục, kiểm tra notebook chạy Run all.
  - Viết các phần báo cáo về mô hình: Mô hình Deep Learning (tf.keras), phân tích – so sánh kết quả, nhận xét về mất cân bằng dữ liệu và kết luận.



