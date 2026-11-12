# YÊU CẦU — Mini game "Đập Chuột"

> Tài liệu mô tả yêu cầu cho một mini game chạy trên trình duyệt. Chưa bao gồm code.

## 1. Tổng quan

| Mục | Nội dung |
|---|---|
| Tên game | Đập Chuột |
| Nền tảng | Trình duyệt web (máy tính và điện thoại) |
| Người chơi | 1 người |
| Bàn chơi | Lưới 3×3 (9 ô/hang) |
| Thời lượng một lượt | 30 giây |
| Mục tiêu | Đập trúng càng nhiều chuột càng tốt trong 30 giây |

## 2. Luật chơi

1. Người chơi bấm nút **Bắt đầu** để vào lượt chơi. Đồng hồ đếm ngược từ **30 giây**.
2. Trong lượt, chuột lần lượt **ngoi lên ngẫu nhiên** ở một trong 9 ô.
3. Mỗi thời điểm chỉ có **tối đa 1 con chuột** trên bàn.
4. Mỗi con chuột ở trên mặt đất trong một khoảng thời gian ngắn (gợi ý **0,6 – 1,2 giây**), sau đó tự lặn xuống.
5. Con chuột tiếp theo xuất hiện sau một khoảng nghỉ ngắn (gợi ý **0,2 – 0,5 giây**) và **không xuất hiện lại đúng ô vừa rồi** liên tiếp.
6. Người chơi **bấm/chạm vào ô có chuột** để đập.
   - Đập trúng: chuột bị "choáng" và biến mất ngay, con tiếp theo xuất hiện theo nhịp bình thường.
   - Bấm vào ô trống: không có tác dụng (không cộng, không trừ điểm).
7. Khi đồng hồ về **0**:
   - Chuột đang hiện biến mất ngay, mọi cú bấm sau thời điểm này **không được tính**.
   - Game chuyển sang màn hình **Kết thúc**.
8. Người chơi có thể bấm **Chơi lại** để bắt đầu lượt mới; điểm và đồng hồ được đặt lại từ đầu.

## 3. Cách tính điểm

| Hành động | Điểm |
|---|---|
| Đập trúng chuột | **+1** |
| Bấm vào ô trống | 0 |
| Để chuột lặn mất (không đập) | 0 |

Quy tắc bổ sung:

- Mỗi con chuột chỉ được tính **tối đa 1 điểm**, dù bấm nhiều lần liên tiếp vào nó.
- Điểm bắt đầu từ **0** ở mỗi lượt.
- **Điểm cao nhất** (kỷ lục) được lưu lại trên trình duyệt của người chơi và vẫn còn khi tải lại trang. Nếu không lưu được (ví dụ chế độ ẩn danh), game vẫn chạy bình thường, chỉ không giữ kỷ lục.

## 4. Màn hình

### 4.1. Màn hình Bắt đầu

- Tên game "Đập Chuột".
- Mô tả luật ngắn gọn (1–2 dòng), ví dụ: *"Đập trúng chuột để ghi điểm. Bạn có 30 giây!"*
- Hiển thị **Kỷ lục** hiện tại (nếu có).
- Nút **Bắt đầu**.

### 4.2. Màn hình Chơi

- **Thanh thông tin** phía trên lưới:
  - **Điểm**: số điểm hiện tại, cập nhật ngay khi đập trúng.
  - **Thời gian**: số giây còn lại (30 → 0). Khi còn ≤ 5 giây, đổi màu nổi bật (ví dụ đỏ) để cảnh báo.
- **Lưới 3×3**: 9 ô hình hang, kích thước bằng nhau, căn giữa màn hình.
  - Ô có chuột hiển thị hình chuột ngoi lên rõ ràng.
  - Khi đập trúng: có phản hồi tức thì (chuột đổi hình "choáng", hiệu ứng rung hoặc "+1" bay lên).
- Con trỏ chuột trên máy tính có thể đổi thành hình cây búa (không bắt buộc).

### 4.3. Màn hình Kết thúc

- Thông báo "Hết giờ!".
- **Điểm của lượt vừa chơi**.
- **Kỷ lục**; nếu lượt này phá kỷ lục, hiển thị thông báo "Kỷ lục mới!".
- Nút **Chơi lại**.

### 4.4. Yêu cầu chung về giao diện

- Hiển thị tốt trên màn hình điện thoại (chiều ngang từ 360px) đến máy tính, không bị cuộn ngang.
- Trên điện thoại: chạm vào ô hoạt động như bấm chuột, không bị phóng to/zoom khi chạm nhanh liên tục.
- Mỗi ô đủ lớn để chạm dễ dàng (tối thiểu khoảng 80×80px trên điện thoại).
- Chữ và số dễ đọc, độ tương phản tốt.

## 5. Ngoài phạm vi (chưa làm ở phiên bản này)

- Nhiều cấp độ khó, chuột tăng tốc theo thời gian.
- Chuột đặc biệt (cộng nhiều điểm, trừ điểm, bom…).
- Bảng xếp hạng online, đăng nhập tài khoản.
- Âm thanh, nhạc nền (có thể bổ sung sau).
- Chơi nhiều người.

## 6. Tiêu chí hoàn thành

Game được coi là hoàn thành khi **tất cả** các điểm dưới đây đều đạt:

**Luồng chơi**
- [ ] Mở trang thấy màn hình Bắt đầu, có nút Bắt đầu.
- [ ] Bấm Bắt đầu → vào màn hình Chơi, điểm = 0, thời gian = 30.
- [ ] Đồng hồ đếm ngược đúng 30 giây (sai lệch không quá ±0,5 giây so với đồng hồ thật).
- [ ] Hết giờ → tự chuyển sang màn hình Kết thúc, hiển thị đúng điểm.
- [ ] Bấm Chơi lại → bắt đầu lượt mới với điểm 0 và thời gian 30.

**Chuột và lưới**
- [ ] Lưới hiển thị đúng 3×3 = 9 ô.
- [ ] Mỗi lúc chỉ có tối đa 1 con chuột trên bàn.
- [ ] Chuột xuất hiện ngẫu nhiên, không lặp lại cùng một ô hai lần liền nhau.
- [ ] Chuột tự lặn xuống nếu không bị đập.

**Tính điểm**
- [ ] Đập trúng chuột → +1 điểm, hiển thị cập nhật ngay.
- [ ] Bấm nhiều lần vào cùng một con chuột chỉ được 1 điểm.
- [ ] Bấm ô trống không thay đổi điểm.
- [ ] Cú bấm sau khi hết giờ không được tính.
- [ ] Kỷ lục được lưu và hiển thị lại sau khi tải lại trang; thông báo "Kỷ lục mới!" xuất hiện đúng lúc.

**Thiết bị và hiệu năng**
- [ ] Chạy được trên bản mới nhất của Chrome, Safari, Firefox, Edge.
- [ ] Chơi được bằng chạm trên điện thoại (iOS Safari, Android Chrome), không bị zoom khi chạm nhanh.
- [ ] Không có lỗi trong console trình duyệt khi chơi trọn một lượt và chơi lại.
- [ ] Phản hồi khi đập trúng hiện ra ngay, không có độ trễ cảm nhận được.
