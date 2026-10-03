# Kịch bản kiểm thử VLSM Studio

Người phụ trách kiểm thử cần chạy từng case, chụp ảnh kết quả và điền **Đạt/Không đạt** cùng ghi chú vào bảng dưới. Các ảnh đó có thể đưa vào chương “Kiểm thử và đánh giá kết quả” của báo cáo.

| ID | Dữ liệu vào | Kết quả kỳ vọng | Trạng thái | Ghi chú / ảnh |
|---|---|---|---|---|
| TC-01 | `200.120.5.0/24`; B=50, A=40, D=30, C=20, E=F=G=2 | B `.0/26`; A `.64/26`; D `.128/27`; C `.160/27`; E `.192/30`; F `.196/30`; G `.200/30`; còn 52 địa chỉ | Chưa chạy | |
| TC-02 | `192.168.1.17/24`; 1 mạng 50 host | App chuẩn hóa mạng gốc thành `192.168.1.0/24`, cấp `/26` | Chưa chạy | |
| TC-03 | `10.0.0.0/30`; 1 mạng 50 host | Cảnh báo mạng gốc không đủ địa chỉ | Chưa chạy | |
| TC-04 | `192.168.1.0/24`; 1 mạng 1 host | Cấp `/30`, 2 host khả dụng (quy ước IPv4 truyền thống, có network + broadcast) | Chưa chạy | |
| TC-05 | `abc/24` hoặc `192.168.1.0/31` | Cảnh báo CIDR/IPv4 không hợp lệ | Chưa chạy | |
| TC-06 | Bài toán mẫu; chuyển “Bảng chi tiết” | 7 hàng khớp TC-01; mask và broadcast đúng | Chưa chạy | |
| TC-07 | Bài toán mẫu; chọn LAN D trên sơ đồ | Inspector hiển thị `.128/27`, mask `255.255.255.224`, host `.129-.158`, broadcast `.159` | Chưa chạy | |
| TC-08 | Bài toán mẫu; bấm “Xuất CSV” | Tải tệp `ket-qua-vlsm.csv`, gồm tiêu đề và 7 hàng | Chưa chạy | |

## Tiêu chí nghiệm thu

1. Không có subnet chồng lấn.
2. Mỗi subnet đáp ứng hoặc vượt số host yêu cầu tối thiểu.
3. Tất cả subnet thuộc mạng gốc.
4. Bảng chi tiết, sơ đồ và CSV cùng cho một kết quả.
5. Ghi phiên bản trình duyệt, ngày chạy test và ảnh minh chứng trong báo cáo.

