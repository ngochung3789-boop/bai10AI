# AI Học Nhìn Ảnh — Tiết 9 • Lớp 7 • Mã 7.C4.1

App trình chiếu dạy bài **"Vấn đề đạo đức nảy sinh từ dữ liệu huấn luyện AI"** —
mở hộp đen ra xem máy học như thế nào. Chạy offline bằng Chrome, một file HTML duy nhất,
không cần cài đặt, không cần tài khoản.

Trang live: https://ngochung3789-boop.github.io/bai10AI/

## Bản đang chạy (live)

- **index.html — v7** (12/11/2026): 7 slide vừa màn hình TV + hệ thống huấn luyện
  3 cột kiểu Teachable Machine (tab Hình ảnh / Âm thanh).
  - **ĐƠN GIẢN HÓA — chỉ chụp mặt thầy:** lớp "Bàn ghế" đã nạp sẵn 6 ảnh mẫu
    ngay khi mở hệ thống huấn luyện (đúng 6 biến thể như slide 2), thầy không
    phải bấm gì ở lớp này. Nút "▶️ HUẤN LUYỆN" chỉ cần lớp "Mặt thầy" có ảnh
    là chạy (≥1 ảnh). Nếu chưa chụp mặt thì app chỉ báo 1 câu:
    "Chụp ảnh mặt thầy trước đã, rồi bấm Huấn luyện." — không còn câu
    "Cần ảnh ở cả 2 lớp mới huấn luyện được".
  - **Tên gọi theo ý thầy:** lớp 1 hiển thị "Mặt thầy", lớp 2 hiển thị
    "Không phải mặt thầy (bàn ghế — đã có sẵn)". Kết quả đoán hiện
    "Đây là mặt thầy" / "Không phải mặt thầy" + số %.
    Dòng hướng dẫn to ngay trên nút Huấn luyện: "Thầy chỉ cần chụp mặt thầy
    (6 ảnh) — lớp bên kia đã có sẵn rồi."
  - **🔍 Mở hộp đen — xem nơ-ron hoạt động (mới):** nút to trong hệ thống
    huấn luyện và ở slide 4. Khi thử 1 ảnh, hộp đen mở ra và chạy CHẬM,
    TỪNG BƯỚC, mỗi bước 1 việc, chữ to, hình nơ-ron to giữa màn hình:
    Bước 1 — ảnh vào thành 2 con số (Độ sáng, Độ tương phản);
    Bước 2 — tín hiệu chạy qua từng nơ-ron lớp ẩn, nơ-ron nào sáng lên thì
    sáng thật, kèm 1 câu ngắn bằng lời thường;
    Bước 3 — nơ-ron đầu ra sáng, máy đoán "Đây là mặt thầy" hay
    "Không phải mặt thầy" + số %;
    Bước 4 — 1 câu chốt: "Máy đoán theo 3 chấm gần nhất; mạng nơ-ron chỉ
    minh họa cách ghi nhận việc học".
    Mỗi bước có nút "Tiếp ›" và nút "▶ Chạy chậm tự động".
    Nếu sơ đồ nơ-ron minh họa cho kết quả khác với máy, bước 3 nói rõ luôn:
    máy trong app KHÔNG dùng nơ-ron để đoán.
  - **Camera/mic tự bật (từ v6):** bấm/giữ nút chụp là camera tự bật ngay,
    không phải bật ở chỗ khác trước. Bấm 1 cái vào nút "📸 Chụp 1 ảnh" cũng chụp
    được 1 ảnh; bấm vào chính khung ngắm cũng bật camera. Giữ thu giọng thì mic
    tự bật. Thả tay trong lúc đang chờ bật thì hủy, không chụp/thu ảnh rác.
    Nút "📸 Chụp 3 ảnh đủ sáng" / "🌑 Chụp 3 ảnh tối" ở slide 2 cũng tự bật camera.
  - **Báo lỗi rõ ràng:** bị chặn quyền thì app báo đỏ ngay tại chỗ —
    "Trình duyệt đang chặn camera cho trang này — bấm biểu tượng camera trên
    thanh địa chỉ → chọn Cho phép, rồi bấm lại." Không có camera thì báo
    "Máy này không tìm thấy camera — dùng Tải ảnh lên."
  - **Giữ để chụp / giữ để thu:** nút to, mỗi lớp có khung ngắm riêng
    (ảnh: video webcam; giọng: sóng âm chạy thật + độ to). Giữ là chụp/thu liên tiếp,
    thả ra là dừng; vòng tiến trình chạy, ảnh/mẫu bay vào lưới, số đếm tăng ngay.
  - **Mạng nơ-ron trong hộp đen:** sơ đồ 3 lớp (vào 2 → ẩn 4 → ra 2) ở slide 4
    và trong cột giữa hệ thống huấn luyện, cả hai tab Hình ảnh và Âm thanh.
    Trọng số tính thật từ dữ liệu (quy tắc delta: w mới = w cũ + 0,05 × tín hiệu vào
    × sai số), số trọng số hiện ngay trên đường nối.
  - **Ranh giới trung thực (ghi rõ trong app và trong kịch bản):**
    sơ đồ nơ-ron chỉ minh họa CÁCH mạng nơ-ron ghi nhận việc học.
    Máy trong app này đoán bằng cách đo khoảng cách 3 chấm gần nhất (k-NN, k=3)
    như đã kiểm chứng — AI thật dùng mạng nơ-ron với hàng triệu nơ-ron nên
    không mở ra xem từng cái được.
  - Số liệu đã đo trên app thật: ảnh đủ sáng 98% đúng; thiếu sáng 64% sai;
    rất tối 51% sai; bàn ghế 98% đúng. Sau khi thêm 3 ảnh tối: thiếu sáng 97% đúng,
    rất tối 86% đúng. (Số % là mức chắc chắn tính từ khoảng cách các chấm.)
    Lưu ý: 6 ảnh mẫu bàn ghế nạp sẵn phải đúng 6 biến thể như slide 2 mới giữ
    được các số này — đã kiểm chứng lại bằng predict() ở v7.
  - Ảnh lớp "Mặt thầy" hiện dùng ảnh mẫu (đã ghi nhãn trong app). Muốn dùng ảnh thật:
    thay 1 file `assets_v7/anh-thay-hung.jpg` (giữ đúng tên file) hoặc chụp bằng webcam
    trong app.

## Các bản lưu

- **bai10AI-v6.html** — v6 (12/11/2026): bấm/giữ chụp tự bật camera; vẫn bắt
  nạp ảnh cả 2 lớp mới huấn luyện được — đã đơn giản hóa ở v7.

## Kịch bản giải thích

`Kich_ban_giai_thich_hop_den_v5.md` (trong thư mục bài dạy, không có trong repo này) —
lời nói nguyên văn để thầy đọc theo, mỗi câu ≤ 12 chữ, có phần giải thích nơ-ron
và phần giữ chụp / giữ thu cho cả hai tab.
