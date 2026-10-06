# BÀI TẬP VỀ NHÀ BI301 S06
## Phân tích đa chiều Slice và Dice tại Starbucks Vietnam

### 1. Bối cảnh và vai trò

**Doanh nghiệp:** Starbucks Vietnam  
**Vai trò:** Chuyên viên Phân tích Báo cáo Đa chiều (OLAP Reporting Analyst)

Dữ liệu kinh doanh được tổ chức dưới dạng **Data Cube** với các chiều gồm: Thời gian, Địa điểm cửa hàng, Danh mục sản phẩm và Kích cỡ đồ uống. Hai thao tác **Slice** và **Dice** được sử dụng để lọc và phân tích dữ liệu theo các chiều khác nhau, từ đó hỗ trợ nhà quản lý đánh giá tình hình kinh doanh.

---

# Phần 1: Thao tác Cắt lát (Slice)

### 1.1. Điều kiện Slice

Thực hiện thao tác **Slice** bằng cách cố định một chiều:

> **Thành phố = "Hà Nội"**

Từ bảng dữ liệu đầu vào, các bản ghi thuộc Hà Nội gồm SB-HN01 và SB-HN02.

| Mã cửa hàng | Thành phố | Dòng sản phẩm | Kích cỡ | Khung giờ | Doanh số (VNĐ) | Số ly bán |
|---|---|---|---|---|---:|---:|
| SB-HN01 | Hà Nội | Frappuccino | Grande | Chiều | 18.500.000 | 185 |
| SB-HN01 | Hà Nội | Espresso | Tall | Sáng | 12.000.000 | 160 |
| SB-HN02 | Hà Nội | Frappuccino | Grande | Chiều | 15.000.000 | 150 |
| **Tổng** | **Hà Nội** | | | | **45.500.000** | **495** |

### 1.2. Kết quả và ý nghĩa nghiệp vụ

**Tổng doanh số tại Hà Nội:**

> 18.500.000 + 12.000.000 + 15.000.000 = **45.500.000 VNĐ**

**Tổng số ly bán ra tại Hà Nội:**

> 185 + 160 + 150 = **495 ly**

Thao tác Slice giúp Giám đốc Bán lẻ **tách riêng toàn bộ dữ liệu của thị trường Hà Nội** khỏi Data Cube để đánh giá sức tiêu thụ tại khu vực này. Kết quả cho thấy Hà Nội tạo ra **45,5 triệu VNĐ doanh số từ 495 ly** trong các bản ghi được cung cấp. Đây là cơ sở để nhà quản lý tiếp tục phân tích sâu hơn theo dòng sản phẩm, kích cỡ hoặc khung giờ.

---

# Phần 2: Thao tác Xúc xắc (Dice)

### 2.1. Điều kiện Dice

Thực hiện **Dice** đồng thời với 3 điều kiện:

- **Thành phố = Hà Nội**
- **Dòng sản phẩm = Frappuccino**
- **Khung giờ = Chiều (13h–17h)**

Sau khi lọc, còn lại 2 bản ghi:

| Mã cửa hàng | Thành phố | Dòng sản phẩm | Kích cỡ | Khung giờ | Doanh số (VNĐ) | Số ly bán |
|---|---|---|---|---|---:|---:|
| SB-HN01 | Hà Nội | Frappuccino | Grande | Chiều | 18.500.000 | 185 |
| SB-HN02 | Hà Nội | Frappuccino | Grande | Chiều | 15.000.000 | 150 |
| **Tổng** | **Hà Nội** | **Frappuccino** | **Grande** | **Chiều** | **33.500.000** | **335** |

### 2.2. Tính giá bán bình quân

Công thức:

> **Giá bán bình quân = Tổng doanh số / Tổng số ly**

Thay số:

> **33.500.000 / 335 = 100.000 VNĐ/ly**

Vậy **giá bán bình quân của Frappuccino cỡ Grande bán vào buổi chiều tại Hà Nội là 100.000 VNĐ/ly**.

### 2.3. Ý nghĩa nghiệp vụ

Thao tác Dice cho phép nhà quản lý **khoanh vùng đồng thời nhiều chiều dữ liệu** để phân tích một phân khúc cụ thể. Trong trường hợp này, kết quả cho thấy Frappuccino Grande vào khung giờ chiều tại Hà Nội đạt **33,5 triệu VNĐ doanh số với 335 ly**, tương ứng giá bán bình quân **100.000 VNĐ/ly**.

Thông tin này có thể hỗ trợ Starbucks Vietnam đánh giá **sức tiêu thụ của Frappuccino tại khu vực trung tâm Hà Nội**, từ đó đưa ra quyết định về phân bổ hàng hóa, nhân sự và các chương trình bán hàng trong khung giờ chiều.
