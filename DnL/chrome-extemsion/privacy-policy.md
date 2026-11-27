# Chính sách Quyền riêng tư — Tiện ích D&L

Cập nhật lần cuối: 2026-11-26

Tiện ích D&L ("tiện ích") được thiết kế để hỗ trợ nhập mã CAPTCHA. Chúng tôi tôn trọng quyền riêng tư của bạn.

## 1. Dữ liệu được xử lý

Tiện ích xử lý các dữ liệu sau **trên thiết bị của bạn**:

- Nội dung CAPTCHA (mã `key` và hình SVG) do chính trang web tải về.
- Giá trị CAPTCHA đã giải, độ tin cậy và thời gian xử lý (tối đa 10 bản ghi gần đây).
- Cấu hình do bạn nhập: địa chỉ máy chủ backend, API KEY, danh sách domain và
  các tuỳ chọn giao diện.

## 2. Cách dữ liệu được lưu trữ

- Cấu hình và lịch sử CAPTCHA được lưu trong `chrome.storage.local` của trình
  duyệt, trên chính máy của bạn.
- Tiện ích **không** đồng bộ dữ liệu qua `chrome.storage.sync`.
- API KEY không được nhúng trong mã nguồn và không được ghi vào log.

## 3. Truyền dữ liệu

- Khi chế độ tự động được bật, nội dung CAPTCHA (`key`, SVG) được gửi tới
  **địa chỉ máy chủ backend do chính bạn cấu hình** trong trang Options
  (`POST /api/captcha/solve`).
- Tiện ích cũng gọi `GET /healthz` trên cùng máy chủ để hiển thị trạng thái.
- Ngoài máy chủ do bạn cấu hình, tiện ích **không gửi dữ liệu tới bên thứ ba
  nào**, không dùng dịch vụ phân tích, quảng cáo hay telemetry.

## 4. Quyền truy cập

- `storage`: lưu cấu hình và lịch sử cục bộ.
- `scripting`, `tabs`, `activeTab`: chèn mã vào các domain bạn phê duyệt để quan
  sát và điền CAPTCHA.
- `optional_host_permissions`: chỉ được cấp khi bạn bấm xác nhận trong Options.

## 5. Kiểm soát của người dùng

- Bạn có thể bật/tắt tự động giải trong popup hoặc Options.
- Bạn có thể xoá toàn bộ lịch sử CAPTCHA bằng nút **Xoá** trong popup.
- Bạn có thể gỡ cài đặt tiện ích bất kỳ lúc nào; dữ liệu trong `chrome.storage.local`
  sẽ bị xoá cùng tiện ích.

## 6. Liên hệ

Số điện thoại: +84903062754
Email liên hệ: zhaohaiyuan.2012@gmail.com
