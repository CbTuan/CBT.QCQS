# Add-in CBT.QCQS (AddinQSQCCBT) — Cài đặt và cập nhật

Trang này chứa các bản phát hành của add-in Excel **CBT.QCQS** (file `AddinQSQCCBT.xlam`).

- Tải bản mới nhất: **[AddinQSQCCBT.xlam](https://github.com/CbTuan/CBT.QCQS/releases/latest/download/AddinQSQCCBT.xlam)** (hoặc trang [Releases → Latest](https://github.com/CbTuan/CBT.QCQS/releases/latest), mục *Assets*).
- Từ bản **20261122**, tên file add-in **cố định là `AddinQSQCCBT.xlam`**, không còn kèm năm (`AddinQSQCCBT2026.01.xlam` là tên cũ).
- Cập nhật bằng nút **Kiểm tra cập nhật** (tab CBT.QCQS → nhóm Tác giả → **Hỗ trợ**). Add-in không tự kiểm tra, không tự tải.

---

## 1. Cài lần đầu bản `AddinQSQCCBT.xlam`

Làm 1 lần duy nhất, kể cả khi đang dùng bản cũ `AddinQSQCCBT2026.01.xlam`.

1. Tải file [`AddinQSQCCBT.xlam`](https://github.com/CbTuan/CBT.QCQS/releases/latest/download/AddinQSQCCBT.xlam). Trình duyệt cảnh báo thì chọn **Keep / Giữ lại**.
2. **Bỏ chặn file tải từ Internet:** chuột phải file → **Properties** → tích **Unblock** (Bỏ chặn) → OK. Không thấy ô Unblock thì bỏ qua. Nếu không bỏ chặn, Excel chặn macro và add-in không chạy.
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

## 2. Cập nhật bản mới

Bấm **Kiểm tra cập nhật** (tab CBT.QCQS → Tác giả → Hỗ trợ):

| Bước | Màn hình |
|---|---|
| 1 | Đang dùng bản mới nhất → báo số bản đang dùng. Hết. |
| 2 | Có bản mới → cửa sổ **Cập nhật AddinQSQCCBT** hiện nội dung thay đổi, nút **Cập nhật ngay** / **Để sau**. |
| 3 | **Cập nhật ngay** → thanh tiến trình tải về (có nút **Hủy**). Tải xong add-in tự kiểm tra mã SHA-256. |
| 4 | **Đóng Excel và cài đặt** → Excel đóng (file chưa lưu được hỏi lưu như bình thường). Chọn **Để sau** thì bản mới tự cài ở lần đóng Excel kế tiếp. |
| 5 | Cửa sổ cài đặt: chờ Excel đóng hẳn → thay file add-in (bản cũ giữ lại thành `AddinQSQCCBT.xlam.bak`). |
| 6 | **Cập nhật xong** → bấm **Mở Excel**. Mã kích hoạt và thiết lập được giữ nguyên. |

- Tắt máy giữa chừng **không làm hỏng add-in**: hoặc đã thay xong, hoặc chưa thay gì.
- Tên file add-in không đổi nên **link hàm tự tạo trong các file Excel không bị ảnh hưởng**.

## 3. Link hàm tự tạo trong file Excel

Khi mở một file có công thức dùng hàm tự tạo của add-in nhưng link trỏ tới **bản cũ khác tên** (`AddinQSQCCBT2026.01.xlam`) hoặc **thư mục khác** (file từ máy khác), add-in **tự đổi link** sang add-in đang chạy. Lưu file để giữ thay đổi.

> Một chiều: file đã đổi link gửi cho người còn dùng bản cũ `AddinQSQCCBT2026.01.xlam` thì phía họ sẽ báo link hỏng — họ nên cài bản mới.

## 4. Xử lý sự cố

**Cửa sổ cài đặt báo "Đang chờ Excel đóng hẳn…" mãi:** Excel còn chạy ẩn (thường do AutoCAD / phần mềm Kata giữ Excel). Tắt chương trình đó, hoặc bấm **Hủy** — bản mới cài ở lần đóng Excel sau.

**Bấm Kiểm tra cập nhật không hiện cửa sổ cập nhật** (máy công ty chặn PowerShell, phần mềm diệt virus chặn): add-in hỏi mở trang tải về → tải file → **đóng hết Excel** → chép đè `AddinQSQCCBT.xlam` trong thư mục add-in (mục 1 bước 2–3).

**Đã tải nhưng cài khi đóng Excel thất bại nhiều lần:** bấm **Kiểm tra cập nhật**, add-in mở thư mục chứa file và hướng dẫn cài tay:
1. Đóng hết Excel.
2. Xóa (hoặc đổi tên) `AddinQSQCCBT.xlam`.
3. Đổi tên `AddinQSQCCBT.xlam.new` thành `AddinQSQCCBT.xlam`.

**Thư mục add-in không ghi được** (cài trong Program Files…): add-in hỏi mở trang tải về rồi chép đè tay (đóng Excel trước). Khuyên dùng thư mục `%APPDATA%\Microsoft\AddIns`.

**Muốn quay lại bản trước:** đóng hết Excel → trong thư mục add-in, đổi tên `AddinQSQCCBT.xlam` thành tên khác, rồi đổi tên `AddinQSQCCBT.xlam.bak` thành `AddinQSQCCBT.xlam`.

**Không kết nối được GitHub** (mạng công ty chặn `github.com`): tải file ở máy khác, cài tay như mục 1 (bước 2–4, chép đè `AddinQSQCCBT.xlam` khi Excel đã đóng).

**Ribbon AutoCAD (tab CBT.QCQS trong AutoCAD):** add-in tự ghi lại đường dẫn mỗi lần mở Excel, không cần bấm lại "Cài Ribbon AutoCAD".

---

Hỗ trợ: nhóm Zalo / Youtube (tab CBT.QCQS → Tác giả → Hỗ trợ).
