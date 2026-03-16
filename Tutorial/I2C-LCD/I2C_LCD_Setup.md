# Hướng dẫn cấu hình Module MKE-M07 LCD1602 I2C

Module **MKE-M07 LCD1602 I2C** được thiết kế tối ưu cho hệ sinh thái MakerEdu, hỗ trợ tốt cho Arduino Uno, ESP32 và các vi điều khiển khác. Điểm đặc biệt của module này là tích hợp sẵn nút **Setup** trên mạch, cho phép cấu hình trực tiếp các thông số phần cứng mà không cần nạp lại code.

---

## 1. Thay đổi địa chỉ I2C (I2C Address)

Sử dụng khi bạn cần kết nối nhiều thiết bị I2C trên cùng một bus và muốn tránh trùng lặp địa chỉ.

1.  **Vào chế độ:** Cấp nguồn cho module, nhấn và giữ nút **Setup** cho đến khi màn hình hiển thị chế độ thiết lập địa chỉ.
2.  **Thay đổi:** Nhấn thả (**Click**) nút Setup để thay đổi địa chỉ. Giá trị sẽ thay đổi tuần hoàn: 
    * `0x20` → `0x21` → `0x22` → `0x23` → `0x24` → `0x25` → `0x26` → `0x27` (quay lại `0x20`).
3.  **Lưu cài đặt:** Nhấn và giữ nút **Setup** cho đến khi màn hình hiện thông báo: **"I2C ADDR SAVED!"**.
4.  **Hoàn tất:** Ngắt điện và cấp nguồn lại để module nhận địa chỉ mới.

---

## 2. Tùy chỉnh độ sáng đèn nền (Brightness)

Module hỗ trợ 5 mức độ sáng để phù hợp với các điều kiện môi trường khác nhau.

1.  **Vào chế độ:** Cấp nguồn, nhấn giữ nút **Setup** để vào chế độ set địa chỉ trước.
2.  **Chuyển mode:** Nhấn nhanh 2 lần liên tiếp (**Double Click**) vào nút Setup để chuyển sang chế độ **"Setup Brightness"**.
3.  **Thay đổi:** Nhấn thả (**Click**) để thay đổi độ sáng (có 5 mức từ 1 đến 5).
4.  **Lưu cài đặt:** Nhấn và giữ nút **Setup** cho đến khi màn hình hiển thị: **"Shut down PWR Pls!"**.
5.  **Hoàn tất:** Tắt nguồn và khởi động lại.

---

## 3. Khôi phục cài đặt gốc (Factory Reset)

Nếu bạn muốn đưa mọi thiết lập về trạng thái mặc định của nhà sản xuất.

* **Thao tác:** Nhấn giữ nút **Setup** đồng thời trong lúc vừa cấp nguồn cho module.
* **Trình tự hiển thị:** Màn hình sẽ hiện lần lượt: `I2C Address` -> **`FACTORY RESET`**.
* **Thông số sau Reset:** * Địa chỉ I2C: `0x27`
    * Độ sáng: `5/5` (Mức cao nhất)

---

## Tóm tắt thao tác nút Setup

| Thao tác | Trạng thái | Chức năng |
| :--- | :--- | :--- |
| **Nhấn giữ** | Đang hoạt động | Truy cập Menu Setup |
| **Nhấn giữ** | Khi cấp nguồn | **Factory Reset** |
| **Click (Nhấn thả)** | Trong Menu | Thay đổi giá trị (Địa chỉ/Độ sáng) |
| **Double Click** | Trong Menu | Chuyển đổi giữa Set I2C và Set Brightness |
| **Nhấn giữ** | Trong Menu | **Lưu cài đặt** và thoát |

> **Lưu ý:** Luôn ngắt nguồn và cấp lại (Re-power) sau khi lưu cài đặt để các thay đổi có hiệu lực hoàn toàn.