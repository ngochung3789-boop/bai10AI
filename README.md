# AI Học Nhìn Ảnh — Tiết 9 • Lớp 7 • Mã 7.C4.1

App trình chiếu dạy bài **"Vấn đề đạo đức nảy sinh từ dữ liệu huấn luyện AI"** —
mở hộp đen ra xem máy học như thế nào. Chạy bằng Chrome, một file HTML duy nhất,
không cần cài đặt, không cần tài khoản.

Trang live: https://ngochung3789-boop.github.io/bai10AI/

## Bản đang chạy (live)

- **index.html — v10.4** (15/11/2026): trên nền v10.3, giữ nguyên 3 tab
  Hình ảnh / Âm thanh / Lệnh lớp học, lệnh giọng "đứng dậy" / "ngồi xuống",
  cửa kho báu mở bằng giọng "mở cửa", lưu IndexedDB, "Xem luồng chạy",
  "Mở hộp đen — xem nơ-ron".

### v10.4 sửa 2 việc thầy yêu cầu (15/11)

1. **Nhận diện đúng mặt thầy (face-api.js, cùng họ công nghệ như Google dùng):**
   mỗi ảnh mặt thầy (10 ảnh wizard + ảnh đã lưu IndexedDB) tính 1 vector đặc
   trưng 128 số; lúc xem trực tiếp, đo vector của mặt trong khung rồi so khoảng
   cách với các vector đã lưu — gần nhất < 0,6 thì "✅ ĐÂY LÀ THẦY HƯNG",
   mặt người khác (khoảng cách ≥ 0,6) thì "❌ KHÔNG PHẢI MẶT THẦY",
   không có mặt thì "🚫 Không thấy mặt trong khung hình" và không đoán.
   Vẽ khung mặt xanh quanh mặt thầy trên video xem trước.
   Vector lưu kèm ảnh trong IndexedDB nên lần sau mở ra vẫn nhận ra thầy.
   - Gắn cổng vào MỌI đường đoán: xem trước trực tiếp (vòng 500ms của wizard),
     thử 1 ảnh, đoán ảnh webcam ở slide, chụp ảnh, wizard — kể cả vòng xem
     trước 600ms cũ (đã gắn cổng phòng thủ; vòng này vốn không chạy vì không
     còn phần tử trVideo trong file).
   - Mất mạng (CDN không tải được) thì dùng FaceDetector rồi ngưỡng tương phản
     như v10.3, app hiện rõ đang dùng cách nào ("Nhận diện: face-api (Google)"
     / "Nhận diện: dự phòng").
2. **Sửa lỗi khôi phục ảnh đã lưu:** trước đây chỉ lưu (saveFace10) mà không
   tải lại nên mở app lại là mất ảnh; v10.4 gọi restoreFace10() khi mở app.

### Giữ nguyên bài học

- Bộ phân loại 2 con số (Độ sáng, Độ tương phản) và số liệu 98/64/51 → 97/86
  giữ nguyên cho phần thử ảnh mẫu trên slide — đó là minh họa "dữ liệu thiếu
  đa dạng thì máy đoán sai". Chỉ phần xem trực tiếp/chụp ảnh dùng nhận diện
  mặt thật. Trong app ghi rõ: "Xem trực tiếp: nhận diện đúng mặt thầy bằng
  đặc trưng khuôn mặt. Thử ảnh mẫu: máy chỉ đo 2 con số nên ảnh tối đoán sai —
  đó là bài học."
- Lần nhận diện đầu tiên trên máy yếu mất vài giây để tải model (~7 MB, lần
  sau trình duyệt nhớ sẵn). Máy thầy (i7) nhận diện trong ~1–3 giây.

## Kiểm chứng (Playwright, camera giả + ảnh mẫu, 15/11/2026)

- (a) Mặt trong khung → "ĐÂY LÀ THẦY HƯNG", khoảng cách 0,09, khung mặt hiện;
  mặt ra khỏi khung (tường sáng) → "Không thấy mặt trong khung hình", không đoán.
- (b) Mặt người khác → "KHÔNG PHẢI MẶT THẦY", khoảng cách 0,76.
- (c) Mặt thầy tối / rất tối → vẫn nhận ra (khoảng cách 0,10 / 0,12).
- (d) Số liệu slide mẫu 98/64/51 → 97/86 giữ nguyên.
- (e) Vector còn sau khi tải lại trang (IndexedDB): 6/6 ảnh có vector 128 số.
- (f) Chặn CDN → dự phòng chạy, app không vỡ, 0 lỗi console chết người.
- (g) Không tràn 1280×720 và 1920×1080.

## File trong repo

- `index.html` — v10.4 (bản live).
- `bai10AI-v10-3.html` — v10.3 (bản trước, giữ để đối chiếu).
