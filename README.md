# Tổng hợp số liệu Phòng Y tế — V6.6.0

Phiên bản V6.6.0 giữ nguyên kiến trúc:

- GitHub Pages làm khung PWA.
- Google Apps Script xử lý giao diện và nghiệp vụ.
- Google Sheet lưu dữ liệu tập trung.

## Thay đổi chính

- Trang Nhập liệu chỉ còn 3 cột: **Chỉ tiêu – Số liệu hiện tại – Thao tác**.
- Bỏ hoàn toàn các ô **Số bổ sung**, **Ghi chú**, **Sau khi lưu** và thanh lưu cuối trang.
- Chỉ dùng một luồng cập nhật trực tiếp: chọn **Chỉnh sửa**, nhập tổng đúng rồi lưu.
- Cho phép nhập giá trị mới lớn hơn, nhỏ hơn hoặc bằng `0`.
- Chỉ tiêu chưa có bản ghi cũng có thể được ghi nhận lần đầu, kể cả giá trị `0`.
- Khi bấm lưu, nút đổi ngay thành **Đang lưu...**, có vòng quay và khóa toàn bộ thao tác trong cửa sổ để chống bấm nhiều lần.
- Sau khi Apps Script trả kết quả, cửa sổ tự đóng, bảng cập nhật ngay và dữ liệu Tổng quan đồng bộ nền.
- Không yêu cầu nhập ghi chú; hệ thống tự lưu lịch sử giá trị trước–sau và người thực hiện.

## Cập nhật Apps Script

1. Sao lưu `Code.gs` hiện tại.
2. Sao chép toàn bộ `apps-script/Code.gs` trong gói này.
3. Dán đè toàn bộ mã cũ và lưu.
4. Triển khai **phiên bản mới** trên deployment hiện tại để giữ URL `/exec`.

Không cần chạy lại `initializeApplication()` nếu Google Sheet đang hoạt động ổn định.

## Cập nhật GitHub Pages

1. Đưa toàn bộ tệp trong thư mục này lên thư mục gốc repository.
2. Ghi đè tệp cũ và commit.
3. Chờ GitHub Pages hoàn tất.
4. Nhấn `Ctrl + F5` hoặc đóng/mở lại PWA để nhận cache V6.6.0.

## An toàn dữ liệu

- Không xóa sheet, cột hoặc bản ghi hiện hữu.
- Dữ liệu cùng ngày và mã chỉ tiêu được cập nhật tại dòng hiện hữu.
- Mọi thay đổi vẫn ghi vào `LỊCH SỬ SỐ LIỆU` và `NHẬT KÝ` nội bộ.
