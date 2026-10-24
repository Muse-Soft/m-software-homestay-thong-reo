# Thiết kế giao diện — Trang homestay Thông Reo (Đà Lạt)

- **Task:** TEC-79 — Thiết kế giao diện trang homestay Thông Reo
- **Epic:** TEC-78 — Sprint 1, trang web giới thiệu homestay Thông Reo ở Đà Lạt
- **Nguồn yêu cầu:** MSR-12 (yêu cầu web: homestay 4 phòng tại Đà Lạt)
- **Repo:** Muse-Soft/m-software-homestay-thong-reo
- **Vai trò:** Designer — bản này là tài liệu bàn giao cho task Dev TEC-80.
- **Nguyên tắc:** mobile-first (thiết kế cho điện thoại trước, rồi mở rộng lên desktop),
  một trang duy nhất cuộn dọc, tông ấm áp — mộc mạc (gỗ, thông, ánh đèn vàng).

> ⚠️ **Placeholder — KHÔNG bịa nội dung thật:** nguồn yêu cầu (MSR-12) và các issue
> TEC-78/79/80 không cho tên phòng, giá/đêm, số điện thoại, link Zalo hay địa chỉ cụ
> thể. Mọi chỗ đó trong bản này đều ghi dạng `[PLACEHOLDER]` (xem mục 9).
> Dev (TEC-80) giữ nguyên khung, chỉ thay placeholder bằng nội dung thật do chủ
> homestay/PO cung cấp — tuyệt đối không tự điền số điện thoại hay giá.

## 1. Tổng quan trang (sơ đồ cuộn dọc)

Thứ tự các khối từ trên xuống dưới — đúng thứ tự này trên cả mobile và desktop:

1. Header cố định (sticky) — logo + menu + nút Đặt phòng
2. Hero — ảnh lớn + tên homestay + câu giới thiệu + 2 nút đặt phòng
3. Giới thiệu ngắn (3 điểm nhấn: nhà gỗ, sân vườn, gần trung tâm)
4. 4 phòng — lưới thẻ phòng (mobile: 1 cột; desktop: 2 cột)
5. Tiện ích chung — lưới icon: bếp, sân vườn, BBQ, thuê xe máy
6. Đánh giá khách — 3 thẻ đánh giá + điểm tổng
7. Điểm tham quan gần đó — danh sách kèm khoảng cách
8. Đặt phòng — khối chốt: gọi điện / Zalo + lưu ý giờ nhận–trả phòng
9. Footer — liên hệ, địa chỉ, giờ hoạt động
10. Thanh đặt phòng cố định cuối màn hình (chỉ mobile)

## 2. Bảng màu (ấm áp, mộc mạc)

| Vai trò | Tên | Mã màu | Dùng ở đâu |
|---|---|---|---|
| Nền chính | Kem giấy | `#FAF3E7` | Nền toàn trang |
| Nền khối xen kẽ | Kem đậm | `#F1E6D2` | Khối tiện ích, đánh giá |
| Màu chủ đạo | Nâu gỗ | `#6B4A2F` | Tiêu đề, header, footer |
| Màu nhấn (CTA) | Cam đất | `#C97B4A` | Nút Đặt phòng, giá, link |
| Màu phụ | Xanh lá thông | `#3E5C4B` | Nhãn, icon tiện ích, badge |
| Chữ chính | Nâu đen | `#3B2F2A` | Văn bản thường |
| Chữ phụ | Nâu xám | `#7A6A5E` | Chú thích, khoảng cách, ngày |
| Viền | Be viền | `#E3D5BF` | Viền thẻ, đường phân cách |

Quy tắc: nền sáng chiếm ~70%, nâu gỗ ~20%, cam đất + xanh thông ~10% (chỉ dùng
làm điểm nhấn, không phủ kín). Nút CTA luôn là cam đất `#C97B4A`, chữ trắng —
không đổi màu nút giữa các khối.

## 3. Typography (chữ)

Cả hai font đều hỗ trợ đầy đủ dấu tiếng Việt — Dev kiểm tra dấu (ơ, ư, đ, dấu
thanh) trước khi chốt, nếu font lỗi dấu thì đổi sang Be Vietnam Pro cho cả hai.

| Vai trò | Font | Cỡ mobile → desktop | Độ đậm |
|---|---|---|---|
| Tiêu đề lớn (hero, tên trang) | Playfair Display, serif | 32px → 48px | 700 |
| Tiêu đề khối (H2) | Playfair Display, serif | 24px → 32px | 700 |
| Tên phòng, tiêu đề thẻ (H3) | Playfair Display, serif | 20px → 24px | 700 |
| Văn bản thường | Be Vietnam Pro, sans-serif | 16px → 17px | 400 |
| Chú thích, nhãn nhỏ | Be Vietnam Pro, sans-serif | 13px → 14px | 400 |
| Giá phòng, nút bấm | Be Vietnam Pro, sans-serif | 16px → 18px | 700 |

Dòng văn bản: chiều cao dòng 1,5 cho văn bản thường; tiêu đề 1,2. Không dùng
quá 2 họ font trên toàn trang.

## 4. Lưới, khoảng cách, thành phần chung

- **Mobile-first:** cột đơn, nội dung rộng tối đa 100% với lề 16px hai bên.
  Breakpoint: tablet ≥ 768px (2 cột cho phòng/tiện ích), desktop ≥ 1024px
  (nội dung tối đa 1100px, căn giữa).
- **Khoảng cách:** giữa các khối 48px (mobile) / 72px (desktop); trong thẻ 16px.
- **Thẻ (card):** bo góc 16px, viền 1px `#E3D5BF`, bóng nhẹ, ảnh bo góc trên.
- **Nút bấm:** bo góc 999px (dạng viên nang), cao tối thiểu 48px, vùng bấm tối
  thiểu 44×44px (ngón tay bấm được). Nút chính: nền cam đất, chữ trắng.
  Nút phụ: viền nâu gỗ, nền trong suốt, chữ nâu gỗ.
- **Ảnh:** tỉ lệ 4:3 cho ảnh phòng và tiện ích, 16:9 cho hero. Mọi ảnh phải có
  văn bản thay thế (alt) mô tả bằng tiếng Việt. Ảnh gợi ý: nhà gỗ, giường gỗ,
  sân vườn, bàn BBQ ngoài trời — tông ấm, ánh sáng vàng, không dùng ảnh
  lạnh/xanh dương làm ảnh chính.

## 5. Wireframe từng khối (mobile — cột đơn)

### 5.1. Header (sticky, luôn ở đầu màn hình khi cuộn)

```
┌────────────────────────────────────────┐
│ 🌲 THÔNG REO            [☰ Menu] [Đặt] │
└────────────────────────────────────────┘
```

- Trái: tên "Thông Reo" (Playfair Display, nâu gỗ) + dòng nhỏ "Homestay Đà Lạt".
- Phải: nút "Đặt phòng" (cam đất). Menu mobile dạng ☰ mở danh sách neo tới các
  khối: Phòng, Tiện ích, Đánh giá, Tham quan, Đặt phòng.
- Desktop: menu ngang đầy đủ, không dùng ☰.

### 5.2. Hero (ảnh toàn chiều rộng, chữ đè lên nền tối nhẹ)

```
┌────────────────────────────────────────┐
│  [Ảnh nhà gỗ / sân vườn Đà Lạt, 16:9]  │
│                                        │
│   THÔNG REO — Homestay Đà Lạt          │
│   Nhà gỗ ấm cúng giữa rừng thông,      │
│   sân vườn rộng, BBQ ngoài trời.       │
│                                        │
│   [📞 Gọi đặt phòng]  [💬 Zalo]        │
└────────────────────────────────────────┘
```

- Tiêu đề lớn nhất trang, 1 câu giới thiệu ≤ 2 dòng, không nhồi thông tin.
- 2 nút đặt phòng ngay trong hero (gọi điện + Zalo) — khách không cần cuộn
  mới đặt được.

### 5.3. Giới thiệu ngắn (3 điểm nhấn, 1 hàng ngang 3 ô trên mobile cuộn ngang)

| 🌲 Nhà gỗ ấm cúng | 🌿 Sân vườn rộng | 📍 Gần trung tâm Đà Lạt |
|---|---|---|
| Nội thất gỗ, ánh đèn vàng, ngủ ngon giữa thông reo. | Sân vườn, góc BBQ, chỗ ngồi ngoài trời. | [PLACEHOLDER: khoảng cách tới trung tâm/chợ Đà Lạt]. |

### 5.4. Phòng — 4 thẻ phòng (AC 1: "4 phòng")

Mobile 1 cột, tablet/desktop 2 cột. Mỗi thẻ giống hệt nhau về cấu trúc:

```
┌────────────────────────────────────────┐
│ [Ảnh phòng, tỉ lệ 4:3]   [Badge: 2 khách│
│                          / 4 khách...] │
│                                        │
│  [TÊN PHÒNG 1]                         │
│  👥 Sức chứa: [PLACEHOLDER: số khách]   │
│  🛏️ [PLACEHOLDER: loại giường]          │
│  [Chip tiện ích riêng: ...]            │
│                                        │
│  [GIÁ/ĐÊM — PLACEHOLDER]  [Đặt phòng →]│
└────────────────────────────────────────┘
```

- 4 thẻ: `[TÊN PHÒNG 1]` đến `[TÊN PHÒNG 4]` — tên, sức chứa, giá/đêm, tiện ích
  riêng của từng phòng đều là placeholder cho tới khi có nội dung thật.
- Chip tiện ích riêng: ví dụ điều hòa, ban công, view rừng thông — chỉ ghi chip
  nào có thật, không ghi chip chung chung cho cả 4 phòng.
- Nút "Đặt phòng →" trên mỗi thẻ cuộn thẳng xuống khối Đặt phòng (mục 5.7),
  kèm tên phòng được chọn (để khách gọi điện nói tên phòng cho nhanh).

### 5.5. Tiện ích chung (AC 1 — đúng 4 mục từ TEC-80)

Lưới 2 cột (mobile) / 4 cột (desktop), mỗi ô: icon + tên + 1 dòng mô tả ngắn.

| 🍳 Bếp chung | 🌿 Sân vườn | 🔥 BBQ ngoài trời | 🛵 Thuê xe máy |
|---|---|---|---|
| Nấu ăn chung, đủ đồ dùng cơ bản. | Ngồi chơi, đọc sách, chụp ảnh. | Khu nướng ngoài trời, đặt trước khi dùng. | [PLACEHOLDER: giá thuê/ngày, liên hệ]. |

### 5.6. Đánh giá khách (AC 1)

- Dòng tổng: ★ [PLACEHOLDER: điểm trung bình, ví dụ 4,9/5] — [PLACEHOLDER: số
  lượt đánh giá] đánh giá.
- 3 thẻ đánh giá, mỗi thẻ: tên khách `[PLACEHOLDER]`, sao, 2–3 câu trích dẫn
  ngắn, tháng/năm ở. Không bịa lời khen cụ thể — Dev chỉ đăng đánh giá thật
  do chủ homestay cung cấp.
- Mobile: 3 thẻ xếp dọc hoặc cuộn ngang; desktop: 3 cột.

### 5.7. Điểm tham quan gần đó (AC 1)

Danh sách dọc, mỗi dòng: tên điểm — khoảng cách — thời gian di chuyển. Toàn bộ
là placeholder cho tới khi có dữ liệu thật:

```
📍 [Tên điểm tham quan 1] — [x km] — [x phút đi xe]
📍 [Tên điểm tham quan 2] — [x km] — [x phút đi xe]
📍 [Tên điểm tham quan 3] — [x km] — [x phút đi xe]
```

- Không ghi tên điểm cụ thể nếu chưa kiểm chứng khoảng cách thật từ homestay.

### 5.8. Đặt phòng — khối chốt (AC 1: gọi điện / Zalo)

```
┌────────────────────────────────────────┐
│  ĐẶT PHÒNG                             │
│  Gọi điện hoặc nhắn Zalo — chủ nhà     │
│  xác nhận phòng trống trong ngày.      │
│                                        │
│  [📞 Gọi: PLACEHOLDER SĐT]             │
│  [💬 Nhắn Zalo: PLACEHOLDER LINK]      │
│                                        │
│  Giờ nhận phòng: [PLACEHOLDER]         │
│  Giờ trả phòng: [PLACEHOLDER]         │
│  Lưu ý: [PLACEHOLDER: đặt cọc/hủy...]  │
└────────────────────────────────────────┘
```

- **Không có form đặt phòng online** — theo yêu cầu, đặt phòng chỉ qua gọi
  điện/Zalo. Nút gọi dùng link `tel:[SĐT]`; nút Zalo dùng link Zalo thật khi có.
- Thanh đặt phòng cố định cuối màn hình (chỉ mobile): 2 nút chia đôi —
  [📞 Gọi] | [💬 Zalo] — luôn thấy khi cuộn, trừ khi khối Đặt phòng đang hiển thị.

### 5.9. Footer

- Tên homestay, địa chỉ `[PLACEHOLDER: địa chỉ Đà Lạt]`, số điện thoại
  `[PLACEHOLDER]`, Zalo `[PLACEHOLDER]`, giờ hoạt động `[PLACEHOLDER]`.
- Dòng cuối: "© [PLACEHOLDER: năm] Homestay Thông Reo".

## 6. Trạng thái và khả năng tiếp cận

- Nút khi bấm: đổi màu tối hơn 10% trong 150ms (phản hồi bấm rõ ràng).
- Tương phản chữ/nền: chữ nâu đen `#3B2F2A` trên nền kem `#FAF3E7` đạt tương
  phản cao; không dùng chữ cam đất cỡ nhỏ trên nền kem (khó đọc).
- Mọi nút/link đều tới được bằng bàn phím, có viền focus thấy rõ.
- Không dùng màu làm cách duy nhất để truyền thông tin (giá, trạng thái phòng
  luôn có chữ kèm theo, không chỉ màu).

## 7. Đối chiếu Acceptance Criteria (TEC-79)

| AC | Đáp ứng ở |
|---|---|
| Bố cục: hero | Mục 5.2 |
| Bố cục: 4 phòng | Mục 5.4 (4 thẻ, cùng cấu trúc) |
| Bố cục: tiện ích chung | Mục 5.5 (bếp, sân vườn, BBQ, thuê xe máy) |
| Bố cục: đánh giá khách | Mục 5.6 |
| Bố cục: đặt phòng (gọi điện/Zalo) | Mục 5.2, 5.4, 5.8 + thanh mobile |
| Bố cục: điểm tham quan gần đó | Mục 5.7 |
| Bảng màu + typography ấm áp, mộc mạc, nhất quán | Mục 2, 3, 4 (một bảng màu, hai font, một kiểu nút toàn trang) |
| Responsive mobile-first | Mục 4 (cột đơn → 2 cột → 1100px) |

## 8. Bàn giao cho Dev (TEC-80)

- Triển khai đúng thứ tự khối ở mục 1; không tự thêm khối mới (ví dụ blog,
  form đặt phòng) nếu PO không yêu cầu.
- Đưa bảng màu mục 2 thành biến CSS (ví dụ `--color-wood: #6B4A2F;`) và dùng
  xuyên suốt, không hard-code mã màu rải rác.
- Ảnh: dùng ảnh thật của homestay khi có; ảnh minh họa tạm chỉ để demo, ghi rõ
  là ảnh tạm và thay trước khi bàn giao khách.

## 9. Checklist placeholder phải thay bằng nội dung thật trước khi launch

- [ ] Tên 4 phòng, sức chứa, loại giường, tiện ích riêng, giá/đêm từng phòng
- [ ] Số điện thoại (link `tel:`) và link Zalo
- [ ] Địa chỉ homestay, khoảng cách tới trung tâm Đà Lạt
- [ ] Giá thuê xe máy, giờ nhận/trả phòng, lưu ý đặt cọc/hủy phòng
- [ ] Đánh giá khách thật (tên, sao, trích dẫn, thời gian ở)
- [ ] Tên + khoảng cách thật của các điểm tham quan gần đó
- [ ] Ảnh thật của homestay (hero, 4 phòng, sân vườn, BBQ)
