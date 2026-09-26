RAILWAY A1+A2 - WEEK STRICT V3

- API thời hạn chỉ dùng weeks.
- Tạo KEY: chỉ chấp nhận weeks: 1 => 7 ngày.
- Gia hạn: chỉ chấp nhận weeks: 1 => +7 ngày.
- Request cũ có months hoặc days sẽ trả HTTP 400, không âm thầm bỏ qua.
- Đã xóa helper add_months và import calendar khỏi backend.
- /api/health version: A1A2-WEEK-STRICT-V3
- Database/Volume cũ giữ nguyên.

Frontend GitHub hiện tại đã gửi weeks:1 nên tương thích trực tiếp.
