# PHƯƠNG PHÁP MÃ HOÁ AFFINE
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/6f25cf04-fd20-41cf-96d5-f4fbaa4e4a37" />

## 1.Tên gọi: Affine Cipher
## 2.Thuật toán mã hoá, thuật toán giải mã
### a. Thuật toán mã hoá
Ý tưởng: Affine cipher là phép biến đổi tuyến tính trên mỗi ký tự.

Với bảng chữ cái có kích thước N (thường N = 26), mỗi ký tự được ánh xạ thành số nguyên 0..N−1.

Công thức mã hóa:

Ci = (a.P + b) mod N

Trong đó:
  -Pi: giá trị số của ký tự bản rõ
  -Ci: giá trị số của ký tự bản mã
  -a, b: khoá, với điều kiện gcd(a, N) = 1 (để giải mã được), b tuỳ ý.

### b. Thuật toán giải mã
Để giải mã, cần tính nghịch đảo modular của a theo modulo N (gọi là a⁻¹).
Ta có a.a⁻¹ = 1 (mod N).
Công thức:

P = (c - b)/a = a⁻¹.(c - b)

## 3.Không gian khóa
Khóa gồm 2 phần: (a, b)

a: phải thỏa điều kiện gcd(a, N) = 1.

b: có thể là bất kỳ số từ 0 đến N−1.

Với N=26:
Các giá trị a khả dĩ = {1, 3, 5, 7, 9, 11, 15, 17, 19, 21, 23, 25} (tổng cộng 12 giá trị).

Các giá trị b = {0..25} (26 giá trị).

→ Không gian khóa = 12 × 26 = 312 khóa thực tế.

So với Caesar (26 khóa), Affine mạnh hơn nhiều, nhưng vẫn nhỏ so với máy tính hiện nay.
## 4.Cách phá mã (mà không cần khoá)
Với không gian khoá như vậy vẫn có thể áp dụng Brute-force(thử tất cả khoá). Nhưng sẽ lâu hơn Caeser 1 chút. Tuy nhiên vẫn nhanh.
## 5.Cài đặt thuật toán mã hoá và giải mã bằng html+css+javascript
Đã cài đặt thuật toán mã hoá và giải mã trong file affine.html
<img width="1886" height="1055" alt="image" src="https://github.com/user-attachments/assets/23cae856-03ea-4f18-9f65-4c3f34912f94" />
