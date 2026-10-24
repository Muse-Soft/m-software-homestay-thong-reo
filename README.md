# m-software-homestay-thong-reo

Trang web giới thiệu homestay Thông Reo tại Đà Lạt (Sprint 1 — Epic TEC-78).

## Trang chính

Mở `index.html` bằng trình duyệt (không cần build). Một trang duy nhất, mobile-first:

- Header cố định + hero (tên homestay, 2 nút đặt phòng)
- Giới thiệu ngắn: nhà gỗ, sân vườn, gần trung tâm
- 4 thẻ phòng (TEC-80): sức chứa, loại giường, tiện ích riêng, giá/đêm
- Tiện ích chung (TEC-80): bếp chung, sân vườn, BBQ, thuê xe máy
- Khối đặt phòng: gọi điện / Zalo + giờ nhận–trả phòng
- Footer + thanh đặt phòng cố định cuối màn hình (chỉ mobile)

Thiết kế: `docs/thiet-ke-homestay-thong-reo.md` (TEC-79) — bảng màu nâu gỗ
`#6B4A2F`, kem `#FAF3E7`, cam đất `#C97B4A`, xanh thông `#3E5C4B`;
font Playfair Display / Be Vietnam Pro (hỗ trợ tiếng Việt).

## Chưa thuộc phạm vi TEC-80

Đánh giá khách + điểm tham quan gần đó là task TEC-81 riêng — chưa có trong
trang này, không tự thêm trước khi TEC-81 làm.

## ⚠️ Placeholder — phải thay bằng nội dung thật trước khi launch

Nguồn yêu cầu MSR-12 không có tên phòng, giá, SĐT, link Zalo hay địa chỉ cụ
thể, nên trang hiện dùng `[PLACEHOLDER]` rõ ràng — tuyệt đối không bịa số liệu:

- [ ] Tên 4 phòng, sức chứa, loại giường, tiện ích riêng, giá/đêm từng phòng
- [ ] Số điện thoại + link Zalo: điền vào `CONTACT` ở đầu thẻ `<script>` trong
      `index.html` là mọi nút Gọi / Zalo (hero, thẻ phòng, khối đặt phòng,
      thanh mobile) tự động dùng link `tel:` / Zalo thật — hiện các nút hiển
      thị trạng thái "chưa cập nhật" và không gọi tới số giả nào
- [ ] Địa chỉ, khoảng cách tới trung tâm, giá thuê xe máy, giờ nhận/trả phòng,
      lưu ý đặt cọc/hủy phòng
- [ ] Ảnh thật của homestay (hiện là khối minh họa tạm)
