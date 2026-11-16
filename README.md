# Dashboard theo dõi tồn kho

Báo cáo Power BI (`Tồn kho.pbix`) theo dõi tình hình tồn kho của chuỗi cửa hàng bán lẻ: lượng hàng đặt, bán, tồn theo thời gian; tốc độ quay vòng của từng sản phẩm; và cảnh báo các sản phẩm cần đặt thêm hàng.

## 1. Thông tin chung

| Hạng mục | Nội dung |
|----------|----------|
| Tệp báo cáo | `Tồn kho.pbix` |
| Nguồn dữ liệu | [Retail Store Inventory Forecasting Dataset (Kaggle)](https://www.kaggle.com/datasets/anirudhchauhan/retail-store-inventory-forecasting-dataset) |
| Công cụ | Power BI Desktop, Power Query, DAX |
| Số trang | 4 |
| Kích thước trang | 1920 × 1080 (Full HD, Fit to Page) |
| Giao diện | Theme Fluent 2, hiển thị tiếng Việt |
| Điều hướng | Cột nút bên trái, chuyển trang bằng cách bấm tên trang |

## 2. Tổng quan các trang

| # | Trang | Câu hỏi trả lời | Đối tượng dùng chính |
|---|-------|-----------------|----------------------|
| 1 | **Tổng quan** | Tình hình tồn kho chung hiện nay ra sao? | Quản lý, lãnh đạo |
| 2 | **Dòng chảy** | Hàng được đặt và bán ra thế nào theo thời gian? | Mua hàng, kế hoạch |
| 3 | **Cấu trúc** | Sản phẩm nào quay vòng nhanh, sản phẩm nào chậm? | Quản lý ngành hàng |
| 4 | **Cảnh báo** | Sản phẩm nào cần đặt gấp và đặt bao nhiêu? | Mua hàng, vận hành kho |

## 3. Chi tiết từng trang

### 3.1. Tổng quan

<img width="806" height="452" alt="Screenshot 2026-11-16 155104" src="https://github.com/user-attachments/assets/7e0bdbc3-8409-457d-94f5-f1bdeac14785" />


| Thành phần | Loại | Nội dung |
|------------|------|----------|
| Tồn kho hiện tại | Thẻ KPI | Current Stock |
| Số ngày tồn kho | Thẻ KPI | Days of Inventory |
| Vòng quay tồn kho | Thẻ KPI | Inventory Turnover |
| Giá trị tồn kho | Thẻ KPI | Stock Value |
| Cơ cấu tồn theo nhóm hàng | Biểu đồ donut | `Current Stock` theo `Category` |
| Bán và đặt hàng theo tháng | Biểu đồ đường | `Units Sold`, `Units Ordered` theo `YearMonth` |
| Top 5 sản phẩm tồn nhiều nhất | Biểu đồ thanh | `Current Stock` theo `Product ID` |
| Tồn cuối tháng | Biểu đồ cột | `Current Stock` theo `YearMonth` |

### 3.2. Dòng chảy

<img width="806" height="452" alt="dong-chay" src="https://github.com/user-attachments/assets/8ff433a8-7b27-46b7-bd46-83be7789b10c" />

| Thành phần | Loại | Nội dung |
|------------|------|----------|
| Tổng hàng đặt | Thẻ KPI | `Total Units Ordered` |
| Tổng bán | Thẻ KPI | `Total Units Sold` |
| Đặt trừ bán | Thẻ KPI | `Net Flow` |
| Tồn TB mỗi ngày | Thẻ KPI | `Avg Inventory` |
| Đặt hàng so với bán theo tháng | Biểu đồ cột | Đặt và bán theo `YearMonth` |
| Tồn trung bình mỗi ngày theo tháng | Biểu đồ đường | `Avg Inventory` theo `YearMonth` |
| Đặt hàng so với bán theo nhóm hàng | Biểu đồ thanh | Đặt và bán theo `Category` |
| Chênh lệch đặt và bán theo sản phẩm | Bảng | `Product ID`, đặt, bán, `Net Flow` |

### 3.3. Cấu trúc

<img width="804" height="450" alt="cau-truc" src="https://github.com/user-attachments/assets/b52c1da4-6872-4782-87b1-b517e51b6e61" />

| Thành phần | Loại | Nội dung |
|------------|------|----------|
| Vòng quay mỗi năm | Thẻ KPI | `Inventory Turnover` |
| Tồn TB mỗi ngày | Thẻ KPI | `Avg Inventory` |
| Giá trị tồn | Thẻ KPI | `Stock Value` |
| Vòng quay và tồn trung bình theo sản phẩm | Biểu đồ phân tán | Trục X: vòng quay; trục Y: tồn trung bình; kích thước bong bóng: giá trị tồn; đường kẻ ngang/dọc là mức trung bình |
| Giá trị tồn theo nhóm hàng | Biểu đồ cột | `Stock Value` theo `Category` |
| Xếp hạng sản phẩm theo vòng quay | Bảng | Vòng quay, số ngày tồn, giá trị tồn, phân loại **Quay nhanh / Quay chậm** |

### 3.4. Cảnh báo

<img width="808" height="454" alt="canh-bao" src="https://github.com/user-attachments/assets/909c8bff-182f-46a9-840b-040c292332c5" />

| Thành phần | Loại | Nội dung |
|------------|------|----------|
| Sản phẩm cần đặt gấp | Thẻ KPI | `Urgent SKU` |
| Tổng số lượng đề xuất | Thẻ KPI | `Suggested Order Qty` |
| Số ngày tồn | Thẻ KPI | `Days of Inventory` |
| Top 10 sản phẩm cần đặt nhiều nhất | Biểu đồ thanh | `Suggested Order Qty` theo `Product ID` |
| Tồn so với điểm đặt lại | Biểu đồ cột | `Current Stock` và `Reorder Point` theo `Category` |
| Đề xuất đặt hàng theo sản phẩm | Bảng | Tồn, số ngày tồn, điểm đặt lại, số lượng đề xuất, trạng thái **Cần đặt gấp / Ổn định / Tồn nhiều** |
| Lead Time | Thanh trượt | Kéo để thay đổi thời gian giao hàng, số lượng đề xuất tính lại theo |

## 4. Bộ lọc

| Bộ lọc | Dạng | Trang áp dụng | Ý nghĩa |
|--------|------|---------------|---------|
| `Category` | Dropdown | Cả 4 trang | Chọn nhóm hàng |
| `Store ID` | Dropdown | Cả 4 trang | Chọn cửa hàng |
| `Year` | Dropdown | Cả 4 trang | Chọn năm |
| `Lead Time` | Thanh trượt | Cảnh báo | Thay đổi thời gian giao hàng để tính lại số lượng đặt |

> Lưu ý: nếu một slicer đang chọn sẵn một giá trị (ví dụ `Category` = Clothing, `Store ID` = S001), toàn bộ visual chỉ hiển thị dữ liệu của giá trị đó. Chọn **Select all** để xem đầy đủ.

## 5. Nhận xét nhanh

Số liệu lấy từ ảnh chụp ở bộ lọc mặc định (tất cả nhóm hàng, tất cả cửa hàng, Lead Time = 9). Đây là dữ liệu tổng hợp (synthetic) nên các nhận xét chỉ mang tính minh họa cách đọc dashboard.

| Quan sát | Trang | Ý nghĩa |
|----------|-------|---------|
| Tồn hiện tại khoảng 26K, giá trị tồn khoảng 1.41M, số ngày tồn khoảng 1.94 | Tổng quan | Lượng hàng tồn chỉ đủ bán khoảng 2 ngày |
| Cơ cấu tồn khá đều giữa các nhóm: Electronics 24.75%, Toys 24.06%, Furniture 20.9%, Groceries 18.41%, Clothing 11.88% | Tổng quan | Clothing là nhóm có tồn thấp nhất |
| Tổng đặt khoảng 8M, tổng bán khoảng 9.98M, `Net Flow` khoảng -2M | Dòng chảy | Lượng đặt thấp hơn lượng bán, tồn không được bổ sung kịp |
| Vòng quay các sản phẩm nằm trong khoảng hẹp từ 178 đến 184 | Cấu trúc | Chênh lệch giữa các sản phẩm nhỏ, nhãn Quay nhanh / Quay chậm chỉ là so sánh tương đối với mức trung bình |
| Furniture và Electronics có giá trị tồn cao nhất, Clothing thấp nhất | Cấu trúc | Vốn nằm nhiều ở Furniture và Electronics |
| 20/20 sản phẩm ở trạng thái Cần đặt gấp, tổng đề xuất khoảng 196.98K | Cảnh báo | Tồn chỉ đủ bán khoảng 2 ngày trong khi lead time là 9 ngày, nên toàn bộ sản phẩm đều dưới điểm đặt lại. Giảm Lead Time để thấy số sản phẩm cần đặt gấp giảm theo |

## 6. Mô hình dữ liệu

### 6.1. Bảng

| Bảng | Vai trò |
|------|---------|
| `Fact_Inventory` | Bảng sự kiện chính, chứa các cột và measure của báo cáo |
| `Lead Time` | Bảng tham số cho thanh trượt Lead Time |

### 6.2. Cột chính của `Fact_Inventory`

| Cột | Ý nghĩa |
|-----|---------|
| `Date` | Ngày ghi nhận |
| `YearMonth` | Tháng, dùng cho trục thời gian |
| `Store ID` | Mã cửa hàng |
| `Product ID` | Mã sản phẩm |
| `Category` | Nhóm hàng |
| `Units Sold` | Số lượng bán |
| `Units Ordered` | Số lượng đặt |
| `Inventory Level` | Mức tồn kho ghi nhận theo ngày |
| `Price` | Đơn giá |

### 6.3. Danh sách measure

| Measure | Ý nghĩa | Dùng ở trang |
|---------|---------|--------------|
| `Current Stock` | Tồn kho tại ngày cuối cùng trong phạm vi đang lọc | Tổng quan, Cảnh báo |
| `Stock Value` | Giá trị tồn kho tại ngày cuối (tồn × đơn giá) | Tổng quan, Cấu trúc |
| `Avg Inventory` | Tồn kho trung bình theo ngày | Dòng chảy, Cấu trúc |
| `Total Units Ordered` | Tổng lượng đặt | Dòng chảy |
| `Total Units Sold` | Tổng lượng bán | Dòng chảy |
| `Net Flow` | Chênh lệch giữa lượng đặt và lượng bán | Dòng chảy |
| `Avg Daily Sales` | Lượng bán trung bình mỗi ngày | Cảnh báo (dùng để tính các measure khác) |
| `Inventory Turnover` | Vòng quay tồn kho | Tổng quan, Cấu trúc |
| `Days of Inventory` | Số ngày tồn kho | Tổng quan, Cấu trúc, Cảnh báo |
| `Turnover Class` | Phân loại quay nhanh / quay chậm | Cấu trúc |
| `Lead Time Value` | Giá trị lead time đang chọn ở thanh trượt | Cảnh báo |
| `Safety Stock` | Tồn kho an toàn | Cảnh báo |
| `Reorder Point` | Điểm đặt lại | Cảnh báo |
| `Stock Status` | Trạng thái tồn: Cần đặt gấp / Ổn định / Tồn nhiều | Cảnh báo |
| `Suggested Order Qty` | Số lượng đề xuất đặt thêm | Cảnh báo |
| `Urgent SKU` | Số SKU cần đặt gấp | Cảnh báo |

### 6.4. Công thức DAX

#### Nhóm 1: Tồn kho

```DAX
Current Stock =
VAR LastDate = MAX ( Fact_Inventory[Date] )
RETURN
    CALCULATE (
        SUM ( Fact_Inventory[Inventory Level] ),
        KEEPFILTERS ( Fact_Inventory[Date] = LastDate )
    )
```

```DAX
Stock Value =
VAR LastDate = MAX ( Fact_Inventory[Date] )
RETURN
    SUMX (
        FILTER ( Fact_Inventory, Fact_Inventory[Date] = LastDate ),
        Fact_Inventory[Inventory Level] * Fact_Inventory[Price]
    )
```

```DAX
Avg Inventory =
AVERAGEX (
    VALUES ( Fact_Inventory[Date] ),
    CALCULATE ( SUM ( Fact_Inventory[Inventory Level] ) )
)
```

#### Nhóm 2: Dòng chảy

```DAX
Total Units Sold = SUM ( Fact_Inventory[Units Sold] )
```

```DAX
Total Units Ordered = SUM ( Fact_Inventory[Units Ordered] )
```

```DAX
Net Flow = [Total Units Ordered] - [Total Units Sold]
```

```DAX
Avg Daily Sales =
DIVIDE ( [Total Units Sold], DISTINCTCOUNT ( Fact_Inventory[Date] ) )
```

#### Nhóm 3: Vòng quay

```DAX
Inventory Turnover =
DIVIDE ( [Total Units Sold], [Avg Inventory] )
```

```DAX
Days of Inventory =
DIVIDE ( [Avg Inventory], [Avg Daily Sales] )
```

```DAX
Turnover Class =
VAR AvgTurnover =
    CALCULATE (
        [Inventory Turnover],
        ALLSELECTED ( Fact_Inventory[Product ID] )
    )
RETURN
    IF ( [Inventory Turnover] >= AvgTurnover, "Quay nhanh", "Quay chậm" )
```

#### Nhóm 4: Cảnh báo và đặt hàng

Bảng tham số cho thanh trượt Lead Time (**Modeling → New table**):

```DAX
Lead Time = GENERATESERIES ( 1, 14, 1 )
```

```DAX
Lead Time Value =
SELECTEDVALUE ( 'Lead Time'[Lead Time], 3 )
```

```DAX
Safety Stock =
VAR Z = 1.65  -- mức phục vụ khoảng 95%
VAR StdDaily =
    STDEVX.P (
        VALUES ( Fact_Inventory[Date] ),
        CALCULATE ( SUM ( Fact_Inventory[Units Sold] ) )
    )
RETURN
    Z * StdDaily * SQRT ( [Lead Time Value] )
```

```DAX
Reorder Point =
[Avg Daily Sales] * [Lead Time Value] + [Safety Stock]
```

```DAX
Stock Status =
VAR Stock = [Current Stock]
VAR ROP = [Reorder Point]
RETURN
    SWITCH (
        TRUE (),
        Stock < ROP, "Cần đặt gấp",
        Stock > 2 * ROP, "Tồn nhiều",
        "Ổn định"
    )
```

```DAX
Suggested Order Qty =
SUMX (
    VALUES ( Fact_Inventory[Product ID] ),
    MAX ( 0, ROUNDUP ( [Reorder Point] - [Current Stock], 0 ) )
)
```

```DAX
Urgent SKU =
COUNTROWS (
    FILTER (
        VALUES ( Fact_Inventory[Product ID] ),
        [Current Stock] < [Reorder Point]
    )
)
```

#### Ghi chú về công thức

| Vấn đề | Giải thích |
|--------|------------|
| `Reorder Point` phải là measure | Nếu để là cột tính sẵn thì thanh trượt Lead Time sẽ không làm số liệu thay đổi |
| `Current Stock` lấy ngày cuối | Với trục tháng, đây chính là tồn cuối tháng; không cộng dồn tồn của nhiều ngày |
| `Days of Inventory` | Tồn trung bình chia cho lượng bán trung bình mỗi ngày, cho biết hàng đủ bán trong bao nhiêu ngày |
| Hệ số `Z = 1.65` và ngưỡng `2 * ROP` | Là giả định, có thể đổi theo chính sách tồn kho thực tế |

## 7. Hướng dẫn sử dụng

| Bước | Thao tác |
|------|----------|
| 1 | Tải `Tồn kho.pbix` về và mở bằng Power BI Desktop |
| 2 | Dùng bộ lọc bên trái để chọn nhóm hàng, cửa hàng, năm |
| 3 | Chuyển trang bằng các nút ở cột bên trái |
| 4 | Ở trang **Cảnh báo**, kéo thanh **Lead Time** để xem số lượng đề xuất đặt thay đổi |
| 5 | Muốn cập nhật dữ liệu: tải lại file CSV từ Kaggle, vào **Transform data → Data source settings** để trỏ đường dẫn về file trên máy, rồi bấm **Refresh** |

## 8. Gợi ý đọc nhanh

| Tín hiệu | Trang | Ý nghĩa | Hành động |
|----------|-------|---------|-----------|
| Vòng quay thấp, tồn trung bình cao | Cấu trúc | Hàng tồn đọng | Xem lại kế hoạch nhập, cân nhắc khuyến mãi |
| Tồn thấp hơn điểm đặt lại | Cảnh báo | Nguy cơ thiếu hàng | Ưu tiên đặt gấp |
| `Net Flow` âm kéo dài | Dòng chảy | Bán nhiều hơn đặt, tồn đang giảm | Tăng lượng đặt |
| `Net Flow` dương kéo dài | Dòng chảy | Đặt nhiều hơn bán, tồn đang tích lũy | Giảm lượng đặt |

## 9. Nguồn dữ liệu

| Hạng mục | Nội dung |
|----------|----------|
| Tên bộ dữ liệu | Retail Store Inventory Forecasting Dataset |
| Nền tảng | Kaggle |
| Tác giả | Anirudh Singh Chauhan |
| Đường dẫn | [Retail Store Inventory Forecasting Dataset](https://www.kaggle.com/datasets/anirudhchauhan/retail-store-inventory-forecasting-dataset) |
| Tính chất | Dữ liệu tổng hợp (synthetic), ghi nhận theo ngày, cửa hàng và sản phẩm |
| Giấy phép | Xem trên trang Kaggle của bộ dữ liệu trước khi dùng lại hoặc công khai |
| Ngày tải | `02/11/2026` |
