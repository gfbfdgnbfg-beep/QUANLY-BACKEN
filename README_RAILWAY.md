# License API A1 / A2 — Railway

Bản này được nâng cấp từ backend hiện tại, giữ nguyên ID + KEY, device binding, khóa tài khoản, reset KEY và gia hạn.

## Điểm mới

Mỗi account có `tool_access`:

- `A1` — chỉ Tool A1
- `A2` — chỉ Tool A2
- `A1+A2` — dùng chung một ID + KEY cho cả hai tool

`POST /api/license/login` trả thêm:

```json
{
  "tool_access": "A1+A2",
  "allowed_tools": ["A1", "A2"]
}
```

Có thể gửi thêm `tool_id: "A1"` hoặc `tool_id: "A2"`. Nếu KEY không có quyền cho tool đó, server trả `403` với `reason: "tool_not_allowed"`.

## Database cũ

Không cần xóa database/Volume. Khi server khởi động, nó tự thêm cột `tool_access` nếu database cũ chưa có. Mọi KEY cũ được giữ nguyên và mặc định quyền `A1`.

## Railway Variables

- `ADMIN_USER=admin`
- `ADMIN_PASSWORD=<mật khẩu admin mạnh>`
- `TOOL_NAME=A1 + A2`
- `ALLOWED_ORIGINS=https://lecongminhvuong31154-hash.github.io`
- `DB_PATH=/data/license_manager.db`

Không cần tự tạo `PORT`; Railway cung cấp biến này.

## Volume

Mount Volume tại `/data` để SQLite nằm ở `/data/license_manager.db`.

## Deploy

Upload toàn bộ file trong thư mục Railway lên repo/service Railway rồi redeploy. Sau deploy test:

`https://<domain>.up.railway.app/api/health`
