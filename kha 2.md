# BÁO CÁO PHÂN TÍCH TƯƠNG QUAN GIỎ HÀNG VÀ CƠ CẤU ĐỒ ĂN KÈM
**Doanh nghiệp:** Starbucks Vietnam  
**Người thực hiện:** Chuyên viên Cao cấp Phân tích Dữ liệu Thương mại (Commercial BI Analyst)  
**Mã học phần:** BI301 - S06

---

## PHẦN 1: TÍNH TOÁN TỶ LỆ FOOD ATTACHMENT RATE CHO TỪNG DÒNG SẢN PHẨM

Dựa trên dữ liệu đầu vào, Tỷ lệ gọi kèm đồ ăn (Food Attachment Rate - FAR) được tính theo công thức: 
**FAR = [Số hóa đơn có kèm bánh] / [Tổng số hóa đơn]**

### Bảng phân tích Tỷ lệ gọi kèm đồ ăn (FAR)

| Nhóm thức uống | Tổng số HĐ (Đơn) | Số HĐ có kèm bánh | Giá trị đồ uống TB | Doanh số đồ ăn kèm TB | Food Attachment Rate (FAR) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Cà phê truyền thống / Espresso** | 5,000 | 1,200 | 75,000 VNĐ | 45,000 VNĐ | **24.0%** |
| **Trà Teavana cao cấp** | 3,500 | 280 | 80,000 VNĐ | 50,000 VNĐ | **8.0%** |
| **Đồ đá xay Frappuccino** | 4,000 | 200 | 105,000 VNĐ | 40,000 VNĐ | **5.0%** |

### Đánh giá sự phân hóa mức độ gắn kết (Cà phê vs. Frappuccino)
Từ bảng dữ liệu, chúng ta thấy một sự chênh lệch rất lớn về mức độ gắn kết đồ ăn giữa nhóm uống Cà phê (24%) và nhóm uống Frappuccino (5%). Sự phân hóa này bắt nguồn từ hai yếu tố cốt lõi: đặc tính sản phẩm và hành vi tiêu dùng.

Thứ nhất, đối với nhóm Cà phê truyền thống/Espresso, đây thường là thức uống khởi đầu ngày mới. Hương vị đắng và đậm đà của cà phê tạo ra một sự cân bằng hoàn hảo về vị giác khi kết hợp cùng các loại bánh mì ngọt, bánh sừng bò (croissant) có chứa bơ sữa. Khách hàng mua cà phê thường có nhu cầu ăn sáng hoặc nạp năng lượng nhanh, do đó tỷ lệ mua kèm thức ăn rất cao (24%).

Ngược lại, dòng đồ đá xay Frappuccino vốn đã chứa lượng đường, sữa, kem tươi (whipped cream) và calo rất cao. Bản thân một ly Frappuccino đóng vai trò gần như một món tráng miệng (dessert) độc lập, mang lại cảm giác no nê cho khách hàng. Do đó, nhu cầu tiêu thụ thêm một phần bánh ngọt hay đồ ăn kèm bị sụt giảm mạnh, dẫn đến tỷ lệ FAR chạm đáy ở mức 5%.

---

## PHẦN 2: MÔ PHỎNG BÀI TOÁN TĂNG TRƯỞNG DOANH SỐ KHI TỐI ƯU HÓA TỶ LỆ BÁN KÈM

### 1. Tính toán doanh thu đồ ăn hiện tại
Doanh thu đồ ăn đóng góp từ mỗi nhóm thức uống = [Số hóa đơn có kèm bánh] x [Doanh số đồ ăn kèm TB].

*   **Nhóm Cà phê / Espresso:** 1,200 đơn x 45,000 VNĐ = 54,000,000 VNĐ
*   **Nhóm Trà Teavana:** 280 đơn x 50,000 VNĐ = 14,000,000 VNĐ
*   **Nhóm Frappuccino:** 200 đơn x 40,000 VNĐ = 8,000,000 VNĐ

**Tổng doanh thu đồ ăn hiện tại:** 54,000,000 + 14,000,000 + 8,000,000 = **76,000,000 VNĐ**

### 2. Mô phỏng bài toán tăng trưởng
*Giả định: Nâng tỷ lệ mua kèm (FAR) của nhóm Trà Teavana từ 8.0% lên bằng mức của nhóm Cà phê là 24.0%.*

*   Số hóa đơn có kèm bánh mục tiêu của nhóm Teavana = 3,500 đơn x 24% = **840 đơn**
*   Số đơn hàng bán kèm bánh tăng thêm = 840 - 280 = **560 đơn**
*   Doanh thu đồ ăn tăng thêm từ nhóm Teavana = 560 đơn x 50,000 VNĐ = **28,000,000 VNĐ**

**Kết luận mô phỏng:** Chỉ bằng việc đưa tỷ lệ bán kèm của một dòng thức uống (Teavana) lên mức tiệm cận với cà phê, doanh thu đồ ăn toàn chuỗi (trong tập dữ liệu này) sẽ **tăng thêm 28 triệu VNĐ (tương đương mức tăng trưởng gần 37% tổng doanh thu đồ ăn hiện tại)** mà không cần kéo thêm lượt khách mới (traffic) hay mở rộng mặt bằng.

---

## PHẦN 3: KHUYẾN NGHỊ CHIẾN LƯỢC GHÉP ĐÔI THỰC ĐƠN (PRODUCT PAIRING STRATEGY)

Để hiện thực hóa mục tiêu tăng trưởng Food Attachment Rate tại thị trường Việt Nam (từ 12% lên tiệm cận mức 28% của Thái Lan), tôi đề xuất 2 chiến lược Product Pairing đánh mạnh vào thời điểm tiêu dùng và quy luật bù trừ hương vị:

### Combo 1: "Morning Boost" - Bữa sáng Năng lượng
*   **Sản phẩm ghép đôi:** Cà phê (Americano nóng/đá hoặc Latte) + Bánh Sừng bò bơ (Butter Croissant) / Bánh mì kẹp thịt (Sandwich).
*   **Thời điểm áp dụng vàng:** 07:00 AM - 09:30 AM.
*   **Cơ sở đề xuất:** Nhóm khách hàng công sở (chiếm tỷ trọng lớn của Starbucks) có nhịp sống hối hả vào buổi sáng. Họ cần tính tiện lợi "grab-and-go". Vị đắng chát nhẹ của Espresso làm nền tuyệt vời để tôn lên vị béo ngậy của bơ trong bánh Croissant mà không gây ngán.
*   **Chiến thuật:** Trưng bày các khay bánh nướng nóng hổi ngay tại quầy thu ngân. Đào tạo Barista kỹ năng up-sell tự nhiên: *"Anh/chị dùng thêm một chiếc Croissant nóng dùng kèm Americano cho bữa sáng trọn vẹn nhé?"* và thiết lập mức giá Combo rẻ hơn 10-15% so với mua lẻ.

### Combo 2: "Afternoon Tea Chill" - Trà chiều Thanh tao
*   **Sản phẩm ghép đôi:** Trà Teavana (Hibiscus, Green Tea, Black Tea) + Bánh ngọt nhẹ (Cheesecake, Mousse, hoặc Macaron).
*   **Thời điểm áp dụng vàng:** 02:00 PM - 05:00 PM.
*   **Cơ sở đề xuất:** Khắc phục điểm yếu FAR thấp của nhóm Trà. Khách hàng uống Teavana thường có xu hướng tìm kiếm sự thanh mát, nhẹ nhàng. Các loại bánh ngọt có vị béo hoặc chua ngọt (như Passion Fruit Mousse hoặc New York Cheesecake) sẽ cân bằng hoàn hảo với độ thanh chát nhẹ của trà. Trà sẽ giúp "rửa trôi" cảm giác ngấy của bánh ngọt.
*   **Chiến thuật:** Đưa ra khái niệm "Trà Chiều" (Afternoon Tea Set) theo phong cách hiện đại. Chụp các bộ ảnh quảng bá trực quan sự kết hợp giữa màu sắc rực rỡ của trà Hibiscus và một lát bánh Mousse. Tung ưu đãi mua Trà size Grande/Venti được giảm 20% cho món bánh ngọt đi kèm vào khung giờ thấp điểm buổi chiều để kích cầu.
