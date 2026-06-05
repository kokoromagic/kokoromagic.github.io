# CẨM NANG SỬ DỤNG CÁC APP V2RAY VÀ MAGIC V2RAY

Chào mừng bạn đến với **Magic V2Ray** – Trạm điều khiển mạng bảo mật thế hệ mới dành cho thiết bị Android của bạn. 

Tài liệu này được viết ra để giải thích các tính năng phức tạp bằng ngôn ngữ đời sống dễ hiểu nhất, giúp bạn làm chủ 100% ứng dụng mà không cần phải là một chuyên gia về mạng hay công nghệ!

---

## 🧭 PHẦN 1: GIẢI THÍCH CÁC TÍNH NĂNG

### 1. Phân giải DNS Qua Proxy (Resolve DNS via Proxy)
> Một số app sẽ không có tùy chọn này
* **Giải thích bình dân:** Bình thường khi bạn gõ `facebook.com`, điện thoại sẽ hỏi "nhà mạng Việt Nam" xem địa chỉ nhà Facebook ở đâu rồi mới đi. Việc này dễ bị nhà mạng chặn hoặc theo dõi. Khi bật tính năng này, điện thoại sẽ bỏ qua nhà mạng, đóng gói câu hỏi lại bảo mật rồi gửi sang máy chủ nước ngoài (VPS) nhờ hỏi hộ.
* **Ưu điểm:** Vượt qua mọi tường lửa, chặn mạng của các nhà mạng tại Việt Nam một cách hoàn hảo. An toàn tuyệt đối.
* **Nhược điểm:** Bạn phải tốn thêm một chút thời gian chờ máy chủ nước ngoài trả lời, nên lúc mới bấm vào trang web sẽ có cảm giác hơi "khựng" nhẹ khoảng 0.5 giây đầu.

### 2. Bật Cơ Chế Fake DNS (Enable Fake DNS)
* **Giải thích bình dân:** Đây là "liều thuốc" trị chứng bệnh "khựng 0.5 giây" ở trên. Thay vì bắt trình duyệt ngồi đợi máy chủ nước ngoài tìm địa chỉ thật, ứng dụng sẽ **bịa ngay ra một địa chỉ ảo** (Fake IP) trên bộ nhớ máy và đưa cho trình duyệt chạy luôn lập tức. Trong lúc trình duyệt đang chạy, ứng dụng sẽ âm thầm dịch ngược lại ở phía sau.
* **Ưu điểm:** Mạng phản hồi nhanh "búng ngón tay là ăn ngay". Lướt web, mở ứng dụng cực mượt, tiết kiệm pin và băng thông.

### 3. Khử Nhiễu Dòng Tín Hiệu (Enable Sniffing & RouteOnly)
* **Giải thích bình dân:** Giống như một chú bưu tá thông minh đứng ở cổng. Chú sẽ "ngửi" xem gói tin bạn gửi đi là loại gì (đang lướt web, xem video hay chơi game) để dán nhãn phân loại chuẩn xác, giúp hệ thống định tuyến đi đúng đường, không bị đi lạc dòng dữ liệu.

### 4. Ưu Tiên IPv6 (Prefer IPv6)
* **Giải thích bình dân:** IPv6 là hệ thống đường cao tốc mới rộng hơn, thoáng hơn IPv4 cũ. Nếu máy chủ của bạn hỗ trợ, bật tính năng này sẽ ép dữ liệu di chuyển trên làn đường cao tốc mới này.
* **Lưu ý:** Chỉ nên bật nếu mạng 4G/Wifi và máy chủ của bạn có hỗ trợ IPv6, nếu không có thể gây mất kết nối một số trang web.

### 5. Ghim Chứng Chỉ Máy Chủ (Pinned Peer Cert SHA256)
> Các app sử dụng X-ray core cũ sẽ không có tùy chọn này
* **Giải thích bình dân:** Đây là tính năng bảo mật cấp cao nhất. Bạn cấp cho ứng dụng một mã "Hộ chiếu độc quyền" của máy chủ thật. Khi bạn ra quán cafe kết nối Wifi công cộng, nếu có hacker xấu tính cố tình giả mạo địa chỉ máy chủ để ăn trộm mật khẩu của bạn, ứng dụng quét mã thấy không khớp sẽ **ngay lập tức cắt đứt kết nối** để bảo vệ bạn.

### 6. Ghép Kênh Dữ Liệu - MUX (Multiplexing)
* **Giải thích bình dân:** Bình thường mỗi hình ảnh, mỗi dòng tin nhắn là một chiếc xe chạy riêng lẻ trên đường, gây tốn tài nguyên và dễ tắc đường. MUX sẽ gom tất cả các chiếc xe nhỏ đó lại, xếp gọn vào một chiếc "xe tải siêu trường siêu trọng" để chở đi một chuyến duy nhất sang máy chủ.
* **Ưu điểm:** Giảm tải cho điện thoại khi bạn mở quá nhiều tab hoặc nhiều ứng dụng cùng lúc.

### 7. Phân Mảnh Gói Tin (Fragment)
* **Giải thích bình dân:** Khi bạn đi qua các hàng rào kiểm duyệt gắt gao của nhà mạng (DPI), các gói tin lớn dễ bị soi mói và bóp băng thông. Tính năng này sẽ "chặt nhỏ" gói tin ra thành từng mảnh liti như hạt cát, khiến hệ thống quét của nhà mạng không thể nhận diện được đây là dữ liệu gì, từ đó thoải mái vượt qua vòng kiểm duyệt.

---

## ⚡ PHẦN 2: CÁC THIẾT LẬP TỐI ƯU SẴN (CHỈ CẦN CHỈNH THEO)

Tùy thuộc vào nhu cầu hằng ngày của bạn, hãy chọn một trong các chế độ cấu hình mẫu dưới đây để điền vào phần **Traffic Settings** trên giao diện Board điều khiển:

### 🎮 Chế độ 1: ƯU TIÊN GAMING (Yêu cầu Ping thấp, Không giật lag)
*Mục tiêu: Giảm thiểu tối đa độ trễ tín hiệu, giúp các pha combo trong game không bị delay.*
* **Phân Giải DNS Qua Proxy:** ❌ **TẮT** (Để DNS phân giải trực tiếp trong nước cho gần, giảm Ping).
* **Bật Cơ Chế Fake DNS:** ❌ **TẮT** (Tránh xung đột IP ảo với một số tựa game nghiêm ngặt).
* **Ghép Kênh MUX:** ❌ **TẮT** (MUX làm tăng độ trễ xử lý lệnh, chơi game tuyệt đối không bật).
* **Phân Mảnh Fragment:** ❌ **TẮT**.
* **Mức Ghi Log (LogLevel):** Chọn `none` hoặc `warning` (Giảm tải cho CPU điện thoại).

### 📱 Chế độ 2: ƯU TIÊN DUYỆT WEB / MẠNG XÃ HỘI (TikTok, Facebook, YouTube)
*Mục tiêu: Mở ứng dụng là load video ngay lập tức, cuộn tin tức không bị khựng.*
* **Phân Giải DNS Qua Proxy:** **BẬT**.
* **Bật Cơ Chế Fake DNS:** **BẬT** *(Bắt buộc bật để tối ưu tốc độ mở trang).*
* **Khử Nhiễu Sniffing:** **BẬT** (Chọn thêm `RouteOnly` để lọc luồng dữ liệu sạch).
* **Ghép Kênh MUX:** **BẬT** (Đặt số kết nối `Concurrency` là `8` để tải nhiều ảnh/video cùng lúc mượt mà).
* **Phân Mảnh Fragment:** ❌ **TẮT** (Trừ khi mạng bị nhà mạng chặn quá gắt).

### 📥 Chế độ 3: ƯU TIÊN TẢI FILE NẶNG (Download Phim, Update Game, Torrent)
*Mục tiêu: Tận dụng tối đa băng thông đường truyền, kéo tốc độ lên kịch sàn.*
* **Phân Giải DNS Qua Proxy:** **BẬT**.
* **Bật Cơ Chế Fake DNS:** **BẬT**.
* **Ghép Kênh MUX:** ❌ **TẮT** (Khi tải file nặng, bật MUX sẽ làm nghẽn cổ chai CPU, tắt đi để đạt tốc độ tối đa).
* **Kích Thước Gói Tối Đa (MTU):** Nâng lên `1400` hoặc giữ nguyên `1350` (Giúp mỗi gói tin chở được nhiều dữ liệu hơn).

### ⚖️ Chế độ 4: CÂN BẰNG HOÀN HẢO (Gaming & Duyệt Web & Tải File)
*Cấu hình khuyên dùng cho 90% người dùng phổ thông, bật một lần dùng cho mọi nhu cầu hằng ngày.*
* **Phân Giải DNS Qua Proxy:** **BẬT** (Bảo mật vượt chặn).
* **Bật Cơ Chế Fake DNS:** **BẬT** (Tăng tốc load web).
* **Khử Nhiễu Sniffing:** **BẬT** (Tắt `RouteOnly`).
* **Ghép Kênh MUX:** ❌ **TẮT** (Để vừa chơi được game mượt, vừa tải file không bị thắt nút cổ chai).
* **Phân Mảnh Fragment:** ❌ **TẮT** (Chỉ bật thủ công khi thấy mạng có dấu hiệu bị bóp băng thông).
* **Mức Ghi Log (LogLevel):** Chọn `error` (Chỉ ghi nhận khi có lỗi lớn, giúp máy chạy nhẹ nhàng).
