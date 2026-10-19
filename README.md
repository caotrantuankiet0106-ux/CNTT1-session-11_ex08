# Phần 1: Phân tích lỗi
Các lỗi vi phạm Database & Hậu quả với AutoFilter:

Tiêu đề gộp & hàng trống trên đầu (Vi phạm Quy tắc 1 & 4): Làm AutoFilter nhận nhầm vị trí header, cắt đứt vùng dữ liệu.

Dòng Tổng kết nằm giữa bảng (Vi phạm Quy tắc 4 & 5): Làm AutoFilter hiểu đây là kết thúc bảng, bỏ qua toàn bộ dữ liệu phía dưới.

Hàng trống giữa dữ liệu (Vi phạm Quy tắc 4): Ngắt quãng vùng dữ liệu khiến bộ lọc không quét được hết bảng.

Cơ chế so sánh chuỗi của Filter: Bộ lọc so sánh chính xác từng ký tự (theo mã ASCII). "Trần Thị Bình" khác hoàn toàn với chuỗi có thêm khoảng trắng thừa ở đuôi như "Trần Thị Bình  ", dẫn đến việc bị loại bỏ khi lọc.

# Phần 2: Sửa lỗi & Nghiệm thu
Cấu trúc bảng chuẩn Database: Xóa bỏ dòng tiêu đề gộp và dòng tổng chèn giữa; đưa hàng tiêu đề lên sát trên cùng; chuyển dòng tổng số lượng xuống dưới cùng của bảng.

Làm sạch dữ liệu & Thao tác lọc:

Dùng hàm =TRIM(B2) để xóa khoảng trắng thừa cho cột Họ và Tên.

Thao tác lọc: Bật AutoFilter (Ctrl + Shift + L) 
→
→ Cột Khoa/Viện chọn CNTT 
→
→ Cột Điểm Xét Duyệt chọn lọc điều kiện 
≥
8.0
≥8.0.
