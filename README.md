# Xe Home

Màn hình chính mới cho box **Carlinkit Tbox Ultra** (Android): miễn phí, không quảng cáo, không cần tài khoản.

Xe Home **không thay launcher** của box. Dock bên trái và ô Google Maps vẫn giữ nguyên; app chỉ phủ thêm một cột thông tin bên phải.

> Đã chạy ổn trên Carlinkit Tbox Ultra 5G (Android 15), màn 1920×720 của Lexus RX350 2023. Với box hoặc màn hình khác, có thể phải chỉnh vị trí lớp phủ trong phần **Căn chỉnh** của app.

## Tải về

**[⬇ Tải Xe Home (bản mới nhất)](https://github.com/hoanganh1987vn/xe-home-app/releases/latest/download/xe-home.apk)**

Danh sách phiên bản, nội dung thay đổi và mã kiểm tra SHA-256 của từng bản: [trang Releases](https://github.com/hoanganh1987vn/xe-home-app/releases).

## Tính năng

**Màn hình chính mới**
- Giờ to, thứ ngày và ngày âm lịch (tính đúng múi giờ Việt Nam).
- Lịch tháng âm – dương, có đánh dấu ngày lễ.
- Ô nhạc cho Zing MP3, Spotify, YouTube…: tên bài, ảnh bìa, nút lùi / phát / tiếp, và nút thích bài ngay trên ô (Spotify dấu +, Zing MP3 trái tim).
- 9 app hay dùng (nhấn giữ một ô để đổi app khác).
- Thời tiết theo vị trí xe: nhiệt độ, cao/thấp, khả năng mưa, dự báo 5 giờ tới, tên phường/tỉnh.

**Tiện ích khác**
- **Tất cả ứng dụng gọn gàng:** đang ở màn chính, bấm nút Home tròn ở dock là mở ngay. Cả kho app nằm trong 1 trang, tìm không cần gõ dấu, ẩn được app ít dùng.
- **Chia đôi màn hình 2 chạm:** đang mở một app (vd YouTube) → bấm Chia đôi → chạm app thứ hai (vd Maps). Nếu đang ở màn chính thì chọn lần lượt 2 app.
- **Chụp màn hình hẹn giờ:** chụp ngay hoặc sau 3–30 giây; ảnh lưu trong Thư viện, thư mục XeHome.
- **Nút nổi Xe Home** dùng được ở mọi màn: Quay lại · Màn chính · Chụp màn hình · Chia đôi · Cài đặt.
- **Tự bật lại sau khi tắt máy xe** (cần cấp quyền 1 lần bằng laptop, xem bước 5).

## Quyền riêng tư

- Không tài khoản, không quảng cáo, không thu thập dữ liệu.
- Thứ duy nhất app gửi ra ngoài là **toạ độ đã làm tròn khoảng 1 km**:
  - gửi [Open-Meteo](https://open-meteo.com/) để lấy thời tiết, tối đa 30 phút một lần;
  - gửi dịch vụ địa chỉ có sẵn của Android (Google) để hiện tên phường/tỉnh, chỉ khi xe đi sang khu khác.
- Quyền Trợ năng chỉ dùng để nhận biết màn hình chính, xử lý nút Home, chia đôi và chụp màn hình. App không đọc nội dung các app khác.

## Cách cài (box Android 10 trở lên)

1. **Tải file APK** bằng nút ở trên (mở bằng trình duyệt ngay trên box, hoặc chép file vào box qua USB).
2. **Cài đặt:** mở file trên box. Nếu box hỏi, cho phép cài app từ nguồn này.
3. **Cấp quyền:** mở app Xe Home → mục 1 → cấp 3 quyền:
   - **Trợ năng** (bắt buộc);
   - **Truy cập thông báo** (để hiện bài đang phát);
   - **Vị trí** (để có thời tiết).

   Nếu nút bật Trợ năng bị mờ hoặc báo "cài đặt bị hạn chế": vào Cài đặt → Ứng dụng → Xe Home → bấm ⋮ ở góc trên → **Cho phép cài đặt bị hạn chế** → quay lại bật.
4. **Nút nổi Xe Home:** trong trang Trợ năng của Xe Home, bật phím tắt bằng nút hỗ trợ tiếp cận (tên mục có thể hơi khác tuỳ box).
5. **Tự bật lại sau khi tắt máy xe** (nên làm, cần laptop Windows). Box tự tắt Trợ năng của app ngoài mỗi lần khởi động, nên cần cấp quyền 1 lần để Xe Home tự bật lại:
   - Trên box: Cài đặt → Hệ thống → Tuỳ chọn cho nhà phát triển → bật **Gỡ lỗi qua Wi-Fi**. Nếu chưa thấy mục này, chạm 7 lần vào "Số bản dựng" trong phần thông tin thiết bị.
   - Cho laptop và box vào chung một mạng Wi-Fi (vd điểm phát của điện thoại).
   - Tải [scrcpy cho Windows](https://github.com/Genymobile/scrcpy/releases) (file `scrcpy-win64-…zip`, đã kèm adb) rồi giải nén.
   - Mở thư mục vừa giải nén → chuột phải vào chỗ trống → **Mở trong Terminal**, rồi chạy lần lượt 3 lệnh:
     ```
     .\adb.exe pair IP:CỔNG_GHÉP MÃ_GHÉP
     .\adb.exe connect IP:CỔNG
     .\adb.exe shell pm grant vn.harry.xehome android.permission.WRITE_SECURE_SETTINGS
     ```
     `IP:CỔNG_GHÉP` và `MÃ_GHÉP` lấy ở mục "Ghép nối thiết bị bằng mã ghép nối" trên box; `IP:CỔNG` lấy ở dòng "Địa chỉ IP và cổng".
   - Làm xong thì tắt Gỡ lỗi qua Wi-Fi.

**Cập nhật bản mới:** tải file mới và cài đè lên. Cấu hình và quyền đã cấp vẫn được giữ.

## Lưu ý

- **Vào cài đặt Xe Home:** bấm nút "Cài đặt Xe Home" trong màn Tất cả ứng dụng, hoặc chọn ô Xe Home trong menu nút nổi.
- **Tắt lớp phủ:** Cài đặt Xe Home → mục 2. Muốn gỡ thì gỡ như app bình thường.
- **Phụ thuộc box:** nút Home và chia đôi dựa vào launcher của box Carlinkit. Phiên bản firmware khác có thể chạy khác.
- App cá nhân, phi thương mại, **không liên quan hãng Carlinkit**. Mọi người tự cân nhắc khi cài. Chỉ thao tác khi xe đã dừng.

## Nguồn dữ liệu

- Thời tiết: [Open-Meteo](https://open-meteo.com/), giấy phép CC BY 4.0.
- Lịch âm: thuật toán của Hồ Ngọc Đức (múi giờ +7).
