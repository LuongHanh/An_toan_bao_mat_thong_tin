# BÀI TẬP 01 - AN TOÀN BẢO MẬT THÔNG TIN
# LƯỜNG VĂN HẠNH - K225480106013
### DEADLINE 28-09-2025
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

# PHƯƠNG PHÁP MÃ HOÁ PLAYFAIR
<img width="1752" height="712" alt="image" src="https://github.com/user-attachments/assets/ace3bf04-5fb9-4e1d-9262-a6b93472e45a" />

## 1.Tên gọi: Playfair Cipher
## 2.Thuật toán mã hoá, thuật toán giải mã
### a. Thuật toán mã hoá
Bước 1: Chọn một từ khóa và lập bảng 5x5 (Playfair Square).

Gồm 25 chữ cái (thường gộp I và J chung 1 ô).

Viết từ khóa trước, bỏ ký tự trùng, sau đó điền các chữ còn lại.

Ví dụ từ khóa: KEYWORD

Bảng:
<table class="playfair" aria-label="Playfair cipher square">
      <tr>
        <td>K</td><td>E</td><td>Y</td><td>W</td><td>O</td>
      </tr>
      <tr>
        <td>R</td><td>D</td><td>A</td><td>B</td><td>C</td>
      </tr>
      <tr>
        <td>F</td><td>G</td><td>H</td><td class="ij">I / J</td><td>L</td>
      </tr>
      <tr>
        <td>M</td><td>N</td><td>P</td><td>Q</td><td>S</td>
      </tr>
      <tr>
        <td>T</td><td>U</td><td>V</td><td>X</td><td>Z</td>
      </tr>
    </table>

Bước 2: Chia bản rõ thành cặp chữ cái (digraph).

Nếu gặp hai chữ giống nhau → chèn X giữa.

Nếu còn lẻ 1 chữ → thêm X cuối.

Ví dụ: HELLO → HE LX LO

Bước 3: Mã hóa từng cặp theo luật:

Cùng hàng → thay mỗi chữ bằng chữ bên phải nó (vòng tròn).

Cùng cột → thay mỗi chữ bằng chữ phía dưới (vòng tròn).

Khác hàng, khác cột → thay bằng chữ nằm ở giao điểm hàng của chữ này và cột của chữ kia (hình chữ nhật). Nói dẽ hiểu là lấy 2 đỉnh còn lại của hình chữ nhật, lấy theo hàng.

### b. Thuật toán giải mã
Ngược lại các quy tắc trên:

Cùng hàng → lấy chữ bên trái.

Cùng cột → lấy chữ phía trên.

Khác hàng/cột → lấy chữ ở góc đối diện còn lại.

## 3.Không gian khóa
Không gian khóa phụ thuộc vào số cách sắp xếp 25 chữ cái trong bảng 5x5.

Kích thước ≈ 25! (gần 2^83) – khá lớn so với Caesar/Affine/Vigenère.

## 4.Cách phá mã (mà không cần khoá)
Phân tích tần suất digraph (2-gram) thay vì đơn ký tự.

Các cặp chữ trong tiếng Anh/Việt có tần suất đặc trưng (TH, HE, NG, TR,...).

Với văn bản đủ dài, có thể suy ra cấu trúc bảng và khóa.

Tuy nhiên khó hơn nhiều so với Caesar/Affine/Vigenère vì Playfair che giấu tốt hơn tần suất chữ đơn.

## 5.Cài đặt thuật toán mã hoá và giải mã bằng html+css+javascript
Đã cài đặt thuật toán mã hoá và giải mã trong file playfair.html

Mã hoá:
<img width="1870" height="878" alt="image" src="https://github.com/user-attachments/assets/a1c5c072-3b7b-4159-b2c6-9d7a9ece090d" />

Giải mã:
<img width="1871" height="880" alt="image" src="https://github.com/user-attachments/assets/f19801ef-e13a-47b2-a3a8-45cca6ae35e8" />

# PHƯƠNG PHÁP MÃ HOÁ HOÁN VỊ
<img width="568" height="202" alt="image" src="https://github.com/user-attachments/assets/0a4f5092-05f8-4357-90f4-dc488dc0c6b5" />

## 1.Tên gọi: Transposition Cipher
## 2.Thuật toán mã hoá, thuật toán giải mã
### a. Thuật toán mã hoá
Chọn một khóa hoán vị π, tức là một thứ tự sắp xếp lại vị trí của các ký tự trong một khối có độ dài n.

Ví dụ: với n = 6, khóa π = (3,1,4,6,2,5) nghĩa là vị trí 1 → 3, 2 → 1, 3 → 4, 4 → 6, 5 → 2, 6 → 5.

Chia bản rõ thành các khối độ dài n. Nếu khối cuối không đủ thì thêm ký tự đệm (padding, thường là X).

Trong mỗi khối, sắp xếp lại các ký tự theo thứ tự hoán vị π để được bản mã.

### b. Thuật toán giải mã
Dùng nghịch đảo của hoán vị π.

Nếu π = (3,1,4,6,2,5) thì π⁻¹ = (2,5,1,3,6,4).

Áp dụng lên bản mã sẽ thu được bản rõ.

Tuy nhiên trong file cài đặt của thuật toán này, em đang giải mã theo cách suy ngược các bước. Chưa đúng với tinh thần của bài toán. Phần này em sẽ chỉnh sửa sau.
## 3.Không gian khóa
Không gian khoá của phương pháp này cực lớn với không gian khoá = n!.

Với việc hoán bị bảng chữ cái 26 ký tự ta thu được không gian khoá ≈ 4.03×10^26.
## 4.Cách phá mã (mà không cần khoá)
Nếu độ dài khối nhỏ → có thể thử toàn bộ không gian khóa (brute force).

Nếu bản mã đủ dài → dùng phân tích tần suất theo vị trí.

Ví dụ: trong tiếng Việt/Anh, chữ "E" hay "A" thường xuất hiện nhiều → từ đó suy ra cách sắp xếp.

Phương pháp cribs (đoán trước một số từ trong bản rõ) rất hiệu quả với mật mã hoán vị.

## 5.Cài đặt thuật toán mã hoá và giải mã bằng html+css+javascript
Đã cài đặt thuật toán mã hoá và giải mã trong file hoanvi.html

Trong phương pháp này em cài đặt chương trình với 4 loại khoá: Khoá chữ cái, khoá dãy số, hoán vị kép, hoán vị bảng chữ cái.

**a. Khóa chữ cái**

Ý tưởng: dùng một từ khóa gồm các chữ cái để xác định thứ tự hoán vị.

Ví dụ: từ khóa “SECRET”

Sắp xếp chữ cái theo thứ tự alphabet → C E R S T

Từ đó sinh ra hoán vị cho các cột hoặc hàng khi mã hóa.

Ưu điểm: dễ nhớ, gọn.

**b. Khóa dãy số**

Khóa được cho dưới dạng một dãy số chỉ rõ thứ tự hoán vị.

Ví dụ: khóa (3,1,4,2) → ký tự ở vị trí 1 chuyển sang 3, vị trí 2 chuyển sang 1, vị trí 3 chuyển sang 4, vị trí 4 chuyển sang 2.

Đây là cách trực tiếp nhất để biểu diễn khóa hoán vị.

**c. Hoán vị kép**

Thực hiện 2 lần hoán vị liên tiếp (thường theo hàng và cột của một bảng).

Bước 1: sắp xếp ký tự theo thứ tự khóa hàng.

Bước 2: sắp xếp tiếp theo khóa cột.

Ví dụ: viết bản rõ theo dạng bảng (matrix), sau đó hoán vị theo hàng và theo cột dựa trên 2 khóa khác nhau.

Ưu điểm: tăng độ an toàn so với chỉ hoán vị một lần.

**d. Hoán vị bảng chữ cái**

Hoán vị trên toàn bộ bảng chữ cái (26 chữ cái hoặc 29 chữ cái tiếng Việt).

Ví dụ: thay đổi thứ tự của bảng A–Z thành một thứ tự bất kỳ, sau đó dùng bảng đó để mã hóa.

Về bản chất, giống như một phép thay thế đơn bảng (monoalphabetic substitution), nhưng có thể xem như dạng đặc biệt của hoán vị.

Không gian khóa rất lớn: với 26 chữ cái → 26! ≈ 4.03 × 10^26 khóa.

**Dưới đây là demo:**

Mã hoá:
<img width="1890" height="755" alt="image" src="https://github.com/user-attachments/assets/265d11b0-373f-44de-aa8a-47f307a738ad" />
<img width="1877" height="843" alt="image" src="https://github.com/user-attachments/assets/638a5da3-acf7-4467-abdb-a028a22e2774" />

Giải mã:
<img width="1875" height="757" alt="image" src="https://github.com/user-attachments/assets/b7c038e7-f821-4671-a5a1-3316869872e3" />
<img width="1877" height="841" alt="image" src="https://github.com/user-attachments/assets/64313945-8be6-4749-bebf-5dafc0eea0ba" />
