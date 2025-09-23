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
