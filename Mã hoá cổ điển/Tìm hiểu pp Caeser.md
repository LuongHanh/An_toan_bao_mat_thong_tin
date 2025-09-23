# PHƯƠNG PHÁP MÃ HOÁ CAESER
<img width="346" height="146" alt="image" src="https://github.com/user-attachments/assets/6f1ee22d-835c-4fd7-94cf-50df3658ca04" />

## 1.Tên gọi: Caeser Cipher
## 2.Thuật toán mã hoá, thuật toán giải mã
### a. Thuật toán mã hoá
Ý tưởng: dịch mỗi ký tự trong bản rõ (plaintext) theo một số vị trí cố định k trong bảng chữ cái (ví dụ A→C nếu k=2). Đây là dạng shift cipher đơn giản nhất.

Ký hiệu:
  P = bản rõ (chuỗi ký tự)
  C = bản mã (chuỗi ký tự)
  k = khóa (số nguyên, 0 ≤ k < N)
  N = số chữ cái trong bảng (ví dụ N = 26 cho chữ Latin A–Z)

Công thức (với chữ cái được ánh xạ thành số 0..N−1):

  Ci = (Pi + k) mod N

### b. Thuật toán giải mã
Ý tưởng: dịch ngược lại từng ký tự theo khóa k (hoặc dịch tiến theo khóa N-k).

Công thức:

  Pi = (Ci - k) mod N

Nhưng để không bị giới hạn độ lớn số k nên dùng:

  Pi = (Ci - k + N) mod N
  
## 3.Không gian khóa
Không gian khóa là tập tất cả các khóa có thể: k từ 0 đến N−1.
Vậy nên phương pháp Caeser có không gian khoá nhỏ.
Ví dụ bảng chữ cái tiếng anh có 26 chữ cái ==> không gian khoá = 26
## 4.Cách phá mã (mà không cần khoá)
Vì phương pháp này có không gian khoá nhỏ nên ta có thể vét cạn dễ dàng.
Sử dụng Brute-force (thử tất cả khóa).
## 5.Cài đặt thuật toán mã hoá và giải mã bằng html+css+javascript
Đã cài đặt thuật toán mã hoá và giải mã trong file caeser.html
<img width="1896" height="949" alt="image" src="https://github.com/user-attachments/assets/fd3ea1ca-c70a-48ed-8384-5c7d1c662937" />

Phá mã không cần khoá:
<img width="1877" height="1076" alt="image" src="https://github.com/user-attachments/assets/203cf10d-f19c-4dc9-a227-dd6abfee3dbe" />
