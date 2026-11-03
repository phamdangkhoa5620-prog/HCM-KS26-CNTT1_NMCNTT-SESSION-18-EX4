## Phần 1. Phân tích

* Nhấn **F12 → Inspect Element** để chọn khung **Thông tin tài xế** trong DOM Tree.
* Mở tab **Computed** để xem kích thước và 4 lớp của CSS Box Model.
* Sơ đồ Box Model hiện tại:

```text
+----------------------+
|        MARGIN        |
|  +----------------+  |
|  |     BORDER     |  |
|  |  +----------+  |  |
|  |  | PADDING  |  |  |
|  |  | +------+ |  |  |
|  |  | |CONTENT| |  |  |
|  |  | +------+ |  |  |
|  |  +----------+  |  |
|  +----------------+  |
+----------------------+
```

* **Content:** Chứa nội dung thông tin tài xế.
* **Padding:** Khoảng cách giữa nội dung và viền.
* **Border:** Đường viền phần tử.
* **Margin:** Khoảng cách bên ngoài phần tử.

### Nút thắt cổ chai

* `Margin` quá nhỏ hoặc bằng `0`.
* `Position` (`absolute`/`fixed`) khiến hai khung chồng lên nhau.
* `Width` cộng thêm `Padding` vượt quá không gian hiển thị.

## Phần 2. Triển khai

Chỉ chỉnh trong tab **Styles** của DevTools.

### CSS đề xuất


Khung thông tin tài xế 
.driver-info{
    width:45%;
    padding:16px;
    margin:10px;
    border:1px solid #ccc;
    box-sizing:border-box;
    position:relative;

 Khung danh sách trạm 
.station-list{
    width:45%;
    padding:16px;
    margin:10px;
    border:1px solid #ccc;
    box-sizing:border-box;
    position:relative;

 Khung chứa 
.container{
    display:flex;
    gap:20px;

Thông số mới

* `width: 45%`
* `padding: 16px`
* `margin: 10px`
* `border: 1px solid #ccc`
* `box-sizing: border-box`
* `gap: 20px` giữa hai khung.

## Phần 3. Kiểm thử

Nếu thay đổi `margin` nhưng phần tử vẫn không di chuyển:

* Kiểm tra `position: absolute` hoặc `position: fixed`.
* Kiểm tra CSS có `!important` ghi đè.
* Kiểm tra phần tử cha dùng `display: flex`, `grid` hoặc `transform`.
* Kiểm tra **User Agent Stylesheet** (CSS mặc định của trình duyệt) trong tab **Styles**.
* Bật/tắt từng thuộc tính trong DevTools để xác định quy tắc đang ghi đè.

