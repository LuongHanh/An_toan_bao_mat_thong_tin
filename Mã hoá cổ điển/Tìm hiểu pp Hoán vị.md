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
