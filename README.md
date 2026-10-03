# VLSM Studio

Ứng dụng trực quan hóa phân chia mạng con theo kỹ thuật VLSM cho bài tập môn **Mạng máy tính và truyền số liệu**.

## Chức năng

- Nhập mạng gốc IPv4 theo CIDR; tự chuẩn hóa về địa chỉ network.
- Thêm, xóa và đổi tên các LAN/WAN; tự sắp xếp nhu cầu host giảm dần.
- Tự tính prefix, subnet mask, network address, dải host và broadcast.
- Báo lỗi CIDR sai hoặc mạng gốc không đủ địa chỉ.
- Xem kết quả bằng sơ đồ phân bổ địa chỉ hoặc bảng chi tiết.
- Chọn từng subnet để xem lý do chọn prefix và thông tin chi tiết.
- Xuất bảng kết quả dạng CSV; tự lưu nháp input trong trình duyệt.

## Chạy trên máy

```bash
npm install
npm run dev
```

Sau đó mở địa chỉ mà Vite hiển thị. Để tạo bản production:

```bash
npm run build
npm run test:sites
```

## Bài toán mẫu

`200.120.5.0/24` được chia cho LAN B (50), LAN A (40), LAN D (30), LAN C (20) và 3 WAN (2 host). Kết quả đúng: `/26, /26, /27, /27, /30, /30, /30`, còn dư 52 địa chỉ từ `200.120.5.204` đến `200.120.5.255`.

## Phân công gợi ý

- **Thành viên 1 - Xây dựng ứng dụng & UI:** thuật toán, giao diện React, animation GSAP, xuất CSV, tài liệu kỹ thuật.
- **Thành viên 2 - Kiểm thử & kết quả:** chạy các case trong `TESTING.md`, lưu ảnh màn hình/bảng kết quả, đối chiếu tính tay, ghi lỗi và kết luận vào báo cáo.

