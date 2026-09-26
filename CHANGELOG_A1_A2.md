# THAY ĐỔI A1/A2

- Thêm `tool_access` cho mỗi ID/KEY: `A1`, `A2`, `A1+A2`.
- Database cũ tự migrate; KEY cũ mặc định A1.
- API login trả `tool_access` + `allowed_tools`.
- API login hỗ trợ `tool_id` tùy chọn để server chặn tool không được cấp quyền.
- Web tạo ID có lựa chọn quyền tool.
- Web có thể đổi quyền của ID đang tồn tại mà không reset KEY.
- Chưa thay đổi logic thời hạn theo tháng ở bước này.
