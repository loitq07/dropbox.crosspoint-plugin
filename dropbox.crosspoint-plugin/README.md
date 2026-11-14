# Dropbox Plugin for CrossPoint (reTerminal Sticky)

Browse and download books and documents directly from your Dropbox to your e-reader.

## Features
- **Hierarchical Folder Navigation:** Tap any folder to open, press Back to navigate to parent folder.
- **Smart Book Filtering:** Shows only supported book files (`.epub`, `.pdf`, `.txt`, `.mobi`, `.cbz`) and folders.
- **Cursor-based Pagination:** Smooth browsing across large libraries.
- **Silent Token Refresh:** Automatically refreshes access tokens without interrupting your reading.
- **Direct SD Download:** Books are saved to `/books/Dropbox/`.

---

## Cấu hình / Configuration

### 1. Lấy Access Token / Refresh Token (Dropbox App Console)
1. Truy cập [Dropbox App Console](https://www.dropbox.com/developers/apps).
2. Nhấn **Create app**:
   - Chọn **Scoped access**.
   - Chọn **Full Dropbox** (hoặc **App folder** nếu chỉ cần chia sẻ một thư mục riêng).
   - Đặt tên app (ví dụ: `MyStickyReader-YourName`).
3. Vào tab **Permissions**:
   - Bật: `files.metadata.read` và `files.content.read`.
   - Nhấn **Submit**.
4. Vào tab **Settings**:
   - Bạn sẽ thấy **App key** (`client_id`) và **App secret** (`client_secret`).
   - Trong mục **OAuth 2**, nhấn **Generate access token** để lấy token dùng ngay.

### 2. Thiết lập trên thẻ SD
Tạo hoặc sửa file `/.crosspoint/plugins/dropbox/token.json`:
```json
{
  "access_token": "YOUR_DROPBOX_ACCESS_TOKEN",
  "refresh_token": "YOUR_REFRESH_TOKEN_IF_ANY"
}
```

Nếu muốn tự động refresh token, điền App key và App secret vào `config.json`:
```json
{
  "client_id": "YOUR_APP_KEY",
  "client_secret": "YOUR_APP_SECRET"
}
```

---

## Hướng dẫn sử dụng
1. Bật Wi-Fi trên máy đọc sách.
2. Từ màn hình chính, vào **Plugins** > chọn **Dropbox**.
3. Danh sách thư mục và sách sẽ hiển thị, chọn sách cần đọc để tải về.
