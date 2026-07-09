# Dự đoán xu hướng giá của thị trường chứng khoán bằng thuật toán Linear Regression

## Tổng quan

Là 1 ứng dụng **Machine Learning** nhằm dự đoán xu hướng biến động giá của thị trường chứng khoán bằng thuật toán **Linear Regression**. Dữ liệu lịch sử được thu thập từ **Yahoo Finance**, sau đó được xử lý để tạo các đặc trưng (Lag Features) và huấn luyện mô hình dự đoán lợi nhuận (Log Return) của ngày giao dịch tiếp theo.

Ngoài việc xây dựng mô hình dự đoán, dự án còn mô phỏng một chiến lược giao dịch đơn giản dựa trên kết quả dự đoán và so sánh hiệu quả với chiến lược mua và nắm giữ (Buy & Hold).

---

# Mục tiêu

* Thu thập dữ liệu lịch sử của thị trường.
* Tiền xử lý và chuẩn hóa dữ liệu.
* Tính toán tỷ suất sinh lời theo Log Return.
* Xây dựng các đặc trưng Lag từ dữ liệu quá khứ.
* Huấn luyện mô hình Linear Regression.
* Dự đoán xu hướng biến động giá.
* Xây dựng chiến lược giao dịch dựa trên kết quả dự đoán.
* Đánh giá hiệu quả của mô hình và chiến lược giao dịch.

---

# Dữ liệu sử dụng

**Nguồn dữ liệu**

* Yahoo Finance

**Mã giao dịch**

```
Chọn mã bất kỳ ví dụ muốn dự đoán Bitcoin thì chọn BTC-USD
```

Dữ liệu bao gồm các thuộc tính:

* Open
* High
* Low
* Close
* Adjusted Close
* Volume

---

# Phương pháp thực hiện

## Bước 1. Thu thập dữ liệu

Dữ liệu lịch sử của Bitcoin được tải trực tiếp từ Yahoo Finance bằng thư viện **yfinance**.

---

## Bước 2. Tiền xử lý dữ liệu

Tính tỷ suất sinh lời theo công thức Log Return:

Giá trị này sẽ được sử dụng làm biến mục tiêu để huấn luyện mô hình.

---

## Bước 3. Xây dựng đặc trưng

Tạo 5 biến trễ (Lag Features):

* Lag_1
* Lag_2
* Lag_3
* Lag_4
* Lag_5

Sử dụng biến động của 5 ngày gần nhất để dự đoán biến động của ngày kế tiếp.

---

## Bước 4. Huấn luyện mô hình

Sử dụng thuật toán **Linear Regression** trong thư viện Scikit-learn.

Dữ liệu được chia thành:

* Tập huấn luyện (70%)
* Tập kiểm tra (30%)

Sau đó mô hình được huấn luyện trên tập Train và đánh giá trên tập Test.

---

## Bước 5. Dự đoán

Mô hình dự đoán giá trị Log Return của ngày tiếp theo.

Nếu:

* Prediction > 0 → Giá có xu hướng tăng
* Prediction < 0 → Giá có xu hướng giảm

---

## Bước 6. Mô phỏng chiến lược giao dịch

Từ kết quả dự đoán, hệ thống sinh tín hiệu giao dịch:

* Buy khi dự đoán tăng.
* Sell khi dự đoán giảm.

Lợi nhuận của chiến lược được tính và so sánh với lợi nhuận của thị trường.

---

# Thuật toán sử dụng

* Linear Regression
* Feature Engineering (Lag Features)
* Log Return
* Train/Test Split

---

# Công nghệ sử dụng

* Python
* Jupyter Notebook
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* yfinance

---

# Cài đặt

### 1. Clone dự án

```bash
git clone https://github.com/Phihungzz/StockMarket.git
```

### 2. Di chuyển vào thư mục dự án

```bash
cd StockMarket
```

### 3. Cài đặt thư viện

```bash
pip install -r requirements.txt
```

---

# Hướng dẫn sử dụng

Khởi động Jupyter Notebook:

```bash
jupyter notebook
```

Mở file:

```
Project pre.ipynb
```

Sau đó chạy lần lượt các ô lệnh từ trên xuống dưới.

---

# Quy trình thực hiện

```
  Thu thập dữ liệu
        │
        ▼
 Tiền xử lý dữ liệu
        │
        ▼
  Tính Log Return
        │
        ▼
  Tạo Lag Features
        │
        ▼
Huấn luyện Linear Regression
        │
        ▼
     Dự đoán
        │
        ▼
Sinh tín hiệu Buy/Sell
        │
        ▼
Đánh giá hiệu quả chiến lược
```

---

# Kết quả

Dự án đã xây dựng thành công mô hình dự đoán xu hướng biến động giá Bitcoin dựa trên dữ liệu lịch sử.

Kết quả dự đoán được sử dụng để mô phỏng chiến lược giao dịch và so sánh với chiến lược Buy & Hold nhằm đánh giá hiệu quả của mô hình.

---

