Dashboard theo dõi tồn kho

Báo cáo Power BI (Tồn_kho.pbix) theo dõi tình hình tồn kho của chuỗi cửa hàng bán lẻ: lượng hàng đặt – bán – tồn theo thời gian, tốc độ quay vòng của từng sản phẩm, và cảnh báo những sản phẩm cần đặt thêm hàng.

Nguồn dữ liệu: Retail Store Inventory
Kích thước trang: 1920 × 1080 (Full HD, chế độ Fit to Page)
Giao diện: theme Fluent 2, ngôn ngữ hiển thị tiếng Việt
Cấu trúc báo cáo

Báo cáo gồm 4 trang, chuyển qua lại bằng thanh điều hướng ở góc trên bên trái.

#	Trang	Câu hỏi trả lời
1	Tổng quan	Tình hình tồn kho chung hiện nay ra sao?
2	Dòng chảy	Hàng được đặt và bán ra như thế nào theo thời gian?
3	Cấu trúc	Sản phẩm nào quay vòng nhanh, sản phẩm nào chậm?
4	Cảnh báo	Sản phẩm nào cần đặt gấp và đặt bao nhiêu?
1. Tổng quan
Thẻ KPI: Tồn hiện tại, Số ngày tồn kho, Vòng quay tồn kho, Giá trị tồn kho
Cơ cấu tồn theo nhóm hàng (biểu đồ donut)
Top 5 sản phẩm tồn nhiều nhất
Bán và đặt hàng theo tháng (biểu đồ đường)
Tồn cuối tháng (biểu đồ cột)
2. Dòng chảy
Thẻ KPI: Tổng đặt hàng, Tổng bán ra, Chênh lệch ròng (Net Flow), Tồn trung bình
Đặt hàng so với bán theo tháng và theo nhóm hàng
Tồn trung bình mỗi ngày theo tháng
Bảng chênh lệch đặt và bán theo sản phẩm
3. Cấu trúc
Thẻ KPI: Vòng quay tồn kho, Tồn trung bình, Giá trị tồn kho
Biểu đồ phân tán: vòng quay và tồn trung bình theo sản phẩm (có đường trung bình để chia nhóm)
Giá trị tồn theo nhóm hàng
Bảng xếp hạng sản phẩm theo vòng quay, phân loại Quay nhanh / Quay chậm
4. Cảnh báo
Thẻ KPI: Số SKU khẩn cấp, Đề xuất đặt hàng, Số ngày tồn kho
Top 10 sản phẩm cần đặt nhiều nhất
Tồn so với điểm đặt lại (Reorder Point) theo nhóm hàng
Bảng đề xuất đặt hàng theo sản phẩm, trạng thái Cần đặt gấp / Ổn định / Tồn nhiều
Thanh trượt Lead time: kéo để xem số lượng cần đặt thay đổi theo thời gian giao hàng
Bộ lọc

Các trang đều có bộ lọc dạng dropdown ở thanh bên trái:

Store ID – cửa hàng
Category – nhóm hàng
Date – thời gian
Lead Time – chỉ có ở trang Cảnh báo
Mô hình dữ liệu
Bảng	Vai trò
Fact_Inventory	Bảng sự kiện chính, chứa các cột và measure của báo cáo
Lead Time	Bảng tham số cho thanh trượt Lead time

Cột chính: Date, YearMonth, Store ID, Product ID, Category, Units Sold, Units Ordered, Current Stock, Reorder Point

Measure chính:

Measure	Ý nghĩa
Current Stock	Tồn kho hiện tại
Stock Value	Giá trị tồn kho
Avg Inventory	Tồn kho trung bình
Inventory Turnover	Vòng quay tồn kho
Days of Inventory	Số ngày tồn kho
Total Units Ordered / Total Units Sold	Tổng lượng đặt / tổng lượng bán
Net Flow	Chênh lệch giữa lượng đặt và lượng bán
Turnover Class	Phân loại quay nhanh / quay chậm
Stock Status	Trạng thái tồn: Cần đặt gấp / Ổn định / Tồn nhiều
Suggested Order Qty	Số lượng đề xuất đặt thêm
Urgent SKU	Số SKU cần đặt gấp

Công thức DAX chi tiết của từng measure xem trong Power BI Desktop (mục Model view hoặc Data view). Phần mô tả trên dựa trên tên measure và cách chúng được dùng trong báo cáo.

Cách sử dụng
Mở Tồn_kho.pbix bằng Power BI Desktop (bản mới, hỗ trợ định dạng báo cáo PBIR).
Nếu có yêu cầu, chọn Refresh để cập nhật dữ liệu từ nguồn.
Dùng bộ lọc bên trái để chọn cửa hàng, nhóm hàng hoặc khoảng thời gian.
Vào trang Cảnh báo, kéo thanh Lead time để xem số lượng đề xuất đặt thay đổi.
Gợi ý đọc nhanh
Vòng quay thấp + tồn trung bình cao (góc trên bên phải ở trang Cấu trúc): hàng tồn đọng, cần xem lại kế hoạch nhập.
Tồn thấp hơn điểm đặt lại (trang Cảnh báo): nguy cơ thiếu hàng, ưu tiên đặt gấp.
Net Flow dương kéo dài (trang Dòng chảy): đặt nhiều hơn bán, tồn kho đang tích lũy.
