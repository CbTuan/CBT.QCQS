# Add-in CBT.QCQS (AddinQSQCCBT) — Cài đặt và tự cập nhật

Trang này chứa các bản phát hành của add-in Excel **CBT.QCQS** (file `AddinQSQCCBT.xlam`).

- Tải bản mới nhất: **[Releases → Latest](https://github.com/CbTuan/CBT.QCQS/releases/latest)** → file `AddinQSQCCBT.xlam`.
- Từ bản **20261122**, tên file add-in **cố định là `AddinQSQCCBT.xlam`**, không còn kèm năm (`AddinQSQCCBT2026.01.xlam` là tên cũ). Số phiên bản xem ở nút **Kiểm tra cập nhật** (tab CBT.QCQS → nhóm Cài đặt).
- Add-in **tự cập nhật**: không cần tải tay mỗi lần có bản mới.

---

## 1. Cài lần đầu bản `AddinQSQCCBT.xlam`

Làm 1 lần duy nhất, kể cả khi đang dùng bản cũ `AddinQSQCCBT2026.01.xlam`.

1. Tải file `AddinQSQCCBT.xlam` ở trang [Releases](https://github.com/CbTuan/CBT.QCQS/releases/latest).
2. **Bỏ chặn file tải từ Internet:** chuột phải file → **Properties** → tích **Unblock** (Bỏ chặn) → OK. Nếu không làm, Excel chặn macro và add-in không chạy.
3. Chép file vào **cùng thư mục với bản cũ** (thư mục đang có `AddinQSQCCBTKemTheo.xls` và `CBT_QCQS.bundle`). Thường là:
   `C:\Users\<tên>\AppData\Roaming\Microsoft\AddIns\`
   (gõ `%APPDATA%\Microsoft\AddIns` vào thanh địa chỉ File Explorer).
4. Mở Excel → **File → Options → Add-ins** → dòng *Manage: Excel Add-ins* bấm **Go…** → **Browse…** → chọn `AddinQSQCCBT.xlam` → **OK**. Đảm bảo có dấu tích ở **AddinQSQCCBT**.
   **Chưa bỏ tích bản cũ** ở bước này.
5. Khoảng 8 giây sau, add-in mới:
   - tự **chép mã kích hoạt và các thiết lập** (lề đã lưu, hệ số Cao dòng, màu, thiết lập form…) từ bản cũ — không phải nhập lại mã;
   - hỏi **"Gỡ bản cũ?"** → bấm **Yes**.
6. Đóng và mở lại Excel. Xong.

> Nếu đã gỡ bản cũ trước khi cài bản mới, add-in mới sẽ hỏi mã kích hoạt như lần đầu — nhập lại mã là dùng được.

## 2. Tự cập nhật hoạt động thế nào

| Lúc | Add-in làm gì |
|---|---|
| Mở Excel (mỗi ngày 1 lần) | Kiểm tra bản mới trên trang này. Mất mạng thì bỏ qua, không báo lỗi. |
| Có bản mới | Tự tải ngầm, kiểm tra mã SHA-256. Tên tab đổi thành **CBT.QCQS ★**, nhóm Cài đặt hiện nút **Có bản mới …** (rê chuột để xem nội dung thay đổi). Vẫn làm việc bình thường. |
| Đóng Excel | Tự thay file add-in bằng bản mới (bản cũ giữ lại thành `AddinQSQCCBT.xlam.bak`). |
| Mở Excel lần sau | Chạy bản mới, báo **"Đã cập nhật lên bản …"**. Mã kích hoạt và thiết lập được giữ nguyên. |

- Tắt máy ngay sau khi đóng Excel **không làm hỏng add-in**: hoặc đã thay xong, hoặc chưa thay gì (lần đóng Excel sau làm lại).
- Tên file add-in không đổi nên **link hàm tự tạo trong các file Excel không bị ảnh hưởng**.

## 3. Các nút liên quan (tab CBT.QCQS)

- **Cài đặt → Kiểm tra cập nhật**: kiểm tra ngay, báo kết quả (kể cả "đang là bản mới nhất" hoặc lỗi mạng).
- **Cài đặt → Có bản mới …** (chỉ hiện khi đã tải sẵn bản mới): xem nội dung thay đổi; chọn **No** để **bỏ qua bản này** (không cài, không nhắc lại cho tới bản sau).
- **Tác giả → Hỗ trợ → Hướng dẫn cập nhật**: mở trang này.

## 4. Link hàm tự tạo trong file Excel

Khi mở một file có công thức dùng hàm tự tạo của add-in nhưng link trỏ tới **bản cũ khác tên** (`AddinQSQCCBT2026.01.xlam`) hoặc **thư mục khác** (file từ máy khác), add-in **tự đổi link** sang add-in đang chạy. Lưu file để giữ thay đổi.

> Một chiều: file đã đổi link gửi cho người còn dùng bản cũ `AddinQSQCCBT2026.01.xlam` thì phía họ sẽ báo link hỏng — họ nên cài bản mới.

## 5. Xử lý sự cố

**Có bản mới nhưng mãi không tự cài** (máy công ty chặn PowerShell, phần mềm diệt virus chặn): bấm **Có bản mới …**, add-in mở thư mục chứa file và hướng dẫn cài tay:
1. Đóng hết Excel.
2. Xóa (hoặc đổi tên) `AddinQSQCCBT.xlam`.
3. Đổi tên `AddinQSQCCBT.xlam.new` thành `AddinQSQCCBT.xlam`.

**Thư mục add-in không ghi được** (cài trong Program Files…): add-in chỉ báo ★; bấm nút để mở trang tải về rồi chép đè tay (đóng Excel trước). Khuyên dùng thư mục `%APPDATA%\Microsoft\AddIns`.

**Muốn quay lại bản trước:** đóng hết Excel → trong thư mục add-in, đổi tên `AddinQSQCCBT.xlam` thành tên khác, rồi đổi tên `AddinQSQCCBT.xlam.bak` thành `AddinQSQCCBT.xlam`. Lần kiểm tra sau add-in sẽ tải lại bản mới: khi nút **Có bản mới …** hiện ra, bấm nút và chọn **No** để bỏ qua bản đó.

**Tắt tự cập nhật** (máy không muốn tự thay add-in): mở Command Prompt, chạy
```
reg add "HKCU\Software\VB and VBA Program Settings\CBT_QCQS\CapNhat" /v TatTuDong /t REG_SZ /d 1 /f
```
Bật lại: thay `/d 1` bằng `/d 0`. Nút **Kiểm tra cập nhật** vẫn dùng được.

**Không kết nối được GitHub** (mạng công ty chặn `github.com`): tải file ở máy khác, cài tay như mục 1 (bước 2–4, chép đè `AddinQSQCCBT.xlam` khi Excel đã đóng).

**Ribbon AutoCAD (tab CBT.QCQS trong AutoCAD):** add-in tự ghi lại đường dẫn mỗi lần mở Excel, không cần bấm lại "Cài Ribbon AutoCAD".

---

Hỗ trợ: nhóm Zalo / Youtube (tab CBT.QCQS → Tác giả → Hỗ trợ).
