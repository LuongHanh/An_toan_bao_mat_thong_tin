# PHƯƠNG PHÁP MÃ HOÁ VIGENÈRE
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/17dba956-b58f-4bc1-8aa7-b09cbce6d7bd" />

## 1.Tên gọi: Vigenere Cipher
## 2.Thuật toán mã hoá, thuật toán giải mã
### a. Thuật toán mã hoá
Ý tưởng: Vigenère là dạng đa bảng (polyalphabetic). Thay vì dịch theo 1 khóa cố định (như Caesar), Vigenère dịch mỗi ký tự theo khóa lặp lại.

Ký hiệu:

P = P₁P₂...Pn: bản rõ

C = C₁C₂...Cn: bản mã

K = K₁K₂...Km: khóa (chuỗi ký tự, độ dài m)

N = 26 (chữ cái A–Z)

Công thức:

Ci = (Pi + K(i mod m)) mod N

Trong đó, Kj được hiểu là số dịch tương ứng ký tự khóa (A=0, B=1, …).
### b. Thuật toán giải mã
Ý tưởng: trừ ngược lại theo khóa.

Ci = (Pi - K(i mod m)) mod N

Nhưng để không bị xuất hiện số âm nên dùng:

Ci = (Pi - K(i mod m) + N) mod N

## 3.Không gian khóa
Với Caesar: 26 khóa.

Với Affine: 312 khóa.

Với Vigenère: không gian khóa tăng theo độ dài m.

Cụ thể:

Nếu khóa dài m ký tự, với bảng chữ cái N = 26 → có 26^m khả năng.

Ví dụ:

m=3 → 26³ = 17.576 khóa

m=5 → 26⁵ ≈ 11,8 triệu khóa

m=10 → 26¹⁰ ≈ 1,4 × 10¹⁴ khóa

Như vậy, Vigenère mạnh hơn nhiều so với Caesar và Affine nếu khóa dài.
## 4.Cách phá mã (mà không cần khoá)
Vẫn có thể phá khoá nếu m nhỏ bằng phương pháp vét cạn.
Nhưng nếu m lớn thì có thể dùng phương pháp phân tích tần suất. 
## 5.Cài đặt thuật toán mã hoá và giải mã bằng html+css+javascript
Đã cài đặt thuật toán mã hoá và giải mã trong file vigenere.html
<img width="1899" height="1013" alt="image" src="https://github.com/user-attachments/assets/cc07006a-0407-49e4-acb2-05ecfc4c4edb" />

