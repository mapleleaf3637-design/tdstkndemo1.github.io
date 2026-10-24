# MẬT MÃ SẮC VIỆT — The Curator's Challenge

Đây là bản **prototype giáo dục**, thiết kế cho nhóm 2–4 người chơi sau khi tham quan một tuyến mỹ thuật dân gian. Bản này dùng **1 file `index.html`**, không cần backend hoặc bước build.

## Chơi thử

Mở `index.html` trong trình duyệt Chrome, Edge, Firefox hoặc Safari. Cần mạng để tải 5 hình ảnh tham khảo từ Wikimedia Commons và tải font Google. Nếu không có mạng, ảnh sẽ thay bằng thông báo dự phòng; trò chơi vẫn có thể mở nhưng các phần quan sát tranh sẽ không còn đầy đủ.

Đầu tiên, chọn `Demo Mode` nếu chơi ở lớp / ở nhà; chọn `Museum Mode` nếu vừa tham quan và muốn dùng hiện vật làm nguồn quan sát. Trên điện thoại, **chạm** tác phẩm và chạm nơi thả tương ứng thay cho kéo–thả.

## Đăng lên GitHub Pages

1. Tạo một repository trên GitHub, ví dụ `mat-ma-sac-viet`.
2. Upload file `index.html` vào **thư mục gốc** của nhánh `main`. Có thể upload thêm `README.md`.
3. Vào **Settings → Pages → Build and deployment → Deploy from a branch**.
4. Chọn `main` và `/(root)`, sau đó **Save**.
5. GitHub sẽ cung cấp một URL có dạng `https://ten-tai-khoan.github.io/mat-ma-sac-viet/`. URL này có thể dùng làm đích QR code.

Chỉ cần `index.html` để triển khai bản demo; `README.md` dùng để hướng dẫn nhóm.

## Cấu trúc và tùy chỉnh

Mở file `index.html` bằng VS Code. Tìm đến vùng `DATA` ở đầu đoạn `<script>`:

- `ARTWORKS`: ID, tên tranh, dòng tranh, link ảnh, link nguồn, credit và thẻ chủ đề.
- `LOOK_QUESTIONS`: chi tiết cần phóng to, vị trí crop `focusX`, `focusY`, độ phóng đại `scale`, vị trí vòng đánh dấu `ringX`, `ringY`, `ringW`, `ringH`, gợi ý và lời giải thích.
- `DECODE_QUESTIONS`: câu hỏi, loại tương tác `options` / `hotspot`, phương án trả lời, lời giải thích.
- `THEMES`: danh sách chủ đề ngẫu nhiên để chọn tranh triển lãm.
- `REASONS`: gợi ý câu giải thích cho giám tuyển trẻ.

**Đổi sang ảnh lưu trong dự án**: tạo `assets/artworks`, tải ảnh mà nhóm có quyền sử dụng và sửa trường `image` thành đường dẫn ví dụ `assets/artworks/dam-cuoi-chuot.jpg`. Trên GitHub nhớ upload cả thư mục `assets`.

Trong bản demo này, Stage 2 sử dụng kéo tác phẩm vào **hai nhóm dòng tranh**. Sau khảo sát, nhóm có thể đổi thành clue chủ đề, chất liệu hoặc công dụng theo nhãn thuyết minh thực tế.

## Logic và thang điểm

- Observation: 2 câu, mỗi câu tối đa 20 điểm (40).
- Connection: 4 tác phẩm phân loại, mỗi tác phẩm tối đa 7,5 điểm (30).
- Interpretation: 2 câu, mỗi câu tối đa 10 điểm (20).
- Curator bonus: đủ 3 tác phẩm, có tên và lời giải thích — 10 điểm.
- Chọn sai không bị trừ điểm; được thử lại.
- Nếu dùng gợi ý trước khi trả lời/đặt đúng thì câu/lượt phân loại chỉ nhận **50% điểm**.
- Các lựa chọn tác phẩm và diễn giải triển lãm cuối **không bị chấm theo nội dung đúng-sai**. Việc hoàn thành được thưởng 10 điểm.

## Nguồn ảnh và lưu ý nội dung

1. **Đám cưới chuột** — ảnh Daderot, CC0 1.0: https://commons.wikimedia.org/wiki/File:Mice%27s_wedding,_Dong_Ho_picture,_paper_-_Vietnam_National_Museum_of_Fine_Arts_-_Hanoi,_Vietnam_-_DSC05290.JPG
2. **Gà trống và gà mái** — ảnh Daderot, CC0 1.0: https://commons.wikimedia.org/wiki/File:Rooster_and_hen,_Dong_Ho_picture,_paper_-_Vietnam_National_Museum_of_Fine_Arts_-_Hanoi,_Vietnam_-_DSC05287.JPG
3. **Ngũ hổ** — ảnh Daderot, CC0 1.0: https://commons.wikimedia.org/wiki/File:Five_tigers,_Hang_Trong_painting,_Hanoi,_paper,_view_1_-_Vietnam_National_Museum_of_Fine_Arts_-_Hanoi,_Vietnam_-_DSC05281.JPG
4. **Tứ bình – Tố nữ** — ảnh tham khảo dòng tranh Hàng Trống, Commons ghi public domain. **Không khẳng định đây là bộ Tố nữ đang trưng bày tại Bảo tàng Mỹ thuật Việt Nam:** https://commons.wikimedia.org/wiki/File:Tu_binh.JPG
5. **Đánh ghen** — ảnh tham khảo Đông Hồ, public domain; chỉ là tranh bonus, **chưa xác nhận có trên tuyến tham quan:** https://commons.wikimedia.org/wiki/File:%C4%90%C3%A1nh_ghen.JPG

Trước khi đưa vào hoạt động chính thức ở bảo tàng, cần khảo sát hiện vật/trưng bày, xin chấp thuận đặt QR và điều chỉnh câu hỏi theo nguồn thuyết minh thực tế. Những câu suy luận trong bản demo dùng bằng chứng hình ảnh đơn giản, không được coi là diễn giải lịch sử chính thức.

## Giới hạn của prototype

Trò chơi không thu thập tên hoặc dữ liệu người chơi và không gửi điểm lên máy chủ. Thành tích hiện trên trang kết quả, có nút sao chép tóm tắt và in/lưu bản kết quả. **Chưa có** hệ thống lưu kết quả, bảng xếp hạng, tạo ảnh PNG tự động hoặc phân tích khảo sát người chơi. Ảnh nghệ thuật từ Commons vẫn cần Internet cho đến khi được thay bằng file local.
