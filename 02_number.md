# Tính tiền với Kotlin

## Các kiểu dữ liệu số

Nếu so với Python, kiểu dữ liệu số trong Kotlin khá phức tạp và giới hạn.
Python3 chỉ có kiểu `integer` và `float`, thì Kotlin tuân theo truyền thống Java
với 5 kiểu:

```
Type - Bit width
Double 	64
Float 	32
Long 	64
Int 	32
Short 	16
```

Bit-width là độ "rộng" của mỗi kiểu, tính bằng đơn vị bit.

- Kiểu `Short` chứa được 16 bit. Tức biểu diễn được 2 mũ 16 giá trị.
- ...
- Kiểu `Long` chứa được 64 bits, biểu diễn được 2 mũ 64 giá trị, tức 18446744073709551616 giá trị. Giá trị này được chia điều 2 bên số 0, tức nằm trong đoạn [-9223372036854775807, 9223372036854775807]. Mọi giá trị nằm ngoài khoảng này khi gõ vào sẽ gặp lỗi.

  ```
  >>> 9223372036854775807
  9223372036854775807
  >>> 9223372036854775808
  error: the value is out of range
  9223372036854775808
  ^
  ```

  Hay hơn nữa (và nguy hiểm hơn), nếu đem tính mà kết quả vượt ra khỏi khoảng cho phép, kết quả sẽ bị "xoay vòng" về phía "bên kia".

  ```
  >>> 9223372036854775807 + 2
  -9223372036854775807
  >>> 9223372036854775807 + 3
  -9223372036854775806
  ```

## Các phép toán cơ bản

### Cộng

```kotlin
>>> 1000 + 1000
2000
```

### Trừ

```kotlin
>>> 1000 - 2000
-1000
```

### Nhân

Kiểu dữ liệu số trong Kotlin có độ lớn giới hạn (với Python là tùy ý),
vì vậy phép tính nhân với số lớn sẽ báo lỗi:


```kotlin
>>> 2 * 5
10

>>> 1000 * 1000000000009999999999999999999999999
error: the value is out of range
1000 * 1000000000009999999999999999999999999
       ^
```

Kể cả thêm chữ `L` xuống cuối để ám chỉ kiểu số `long`, vẫn lỗi:

```
>>> 1000 * 1000000000009999999999999999999999999L
error: the value is out of range
1000 * 1000000000009999999999999999999999999L
       ^
```

Số lớn quá mức xử lý mặc định của Kotlin, để tính số lớn tùy ý,
ta phải tìm giải pháp khác.

### Chia

```kotlin
>>> 10/3
3
```

Đáng buồn thay phép chia 2 số nguyên của Kotlin trả về số kiểu integer.
Tính năng này giống như Python2 - còn Python3 đã sửa lại luôn trả về kiểu float.

Để ám chỉ số là kiểu float, thêm chữ `f` ở đuôi hay dùng dấu `.` thập phân:

```kotlin
>>> 10/3f
3.3333333
>>> 10/3.0
3.3333333333333335
>>> 2 * 2.5
5.0
>>> .1 + .1
0.2
>>> .1 + .1 + .1
0.30000000000000004
```
Chú ý, kết quả phép cộng 3 số 0.1 (viết tắt là `.1`) trên không phải là lỗi của
Kotlin. Kiểu float trong Kotlin tuân theo chuẩn IEEE 754 và kết quả thu được giống như các ngôn ngữ lập trình phổ biến khác như C, Python, Java, Golang ... Xem chi tiết nguyên nhân tại http://pymi.vn/blog/why-not-float/.

Tất nhiên, chia cho `0` sẽ xảy ra Exception vì ta đâu thể trả về kết quả nào có nghĩa:

```kotlin
>>> 1 / 0
java.lang.ArithmeticException: / by zero

```

### Chia lấy dư
Dùng ký hiệu `%`:

```kotlin
>>> 5 % 4
1
>>> -2 % 5
-2
>>> -7 % 5
-2
>>> 2 % 2
0
```

## Các phép toán "cao cấp"

### Lũy thừa
Không có ký tự đăc biệt nào để tính lũy thừa (mũ) cả.
Người dùng phải tự tính hoặc sử dụng thư viện kotlin.math.

#### TODO example for this

## So sánh

Kotlin - như mọi ngôn ngữ khác, hỗ trợ các phép so sánh số học, kết quả của các phép toán này luôn là một trong hai giá trị `true` (đúng) hoặc `false` (sai)

```kotlin
>>> 5 > 4
true
>>> 5 < 4
false
>>> 5 == 4
false
>>> 5 == 5
true
>>> 3 <= 4
true
```

Không hỗ trợ so sánh kẹp giữa như Python:

```kotlin
>>> 3 <= 4 <= 5
error: the integer literal does not conform to the expected type Boolean
3 <= 4 <= 5
```

## Kiểm tra kiểu
Dùng `is`:

```kotlin
>>> "abc" is String
true
>>> 123 is Int
true
>>> true is Boolean
true
>>> false is String
error: incompatible types: String and Boolean
false is String
```


Tính toán trên Kotlin có vẻ không được vui cho lắm. Hãy chuyển sang xử lý string
ở bài tiếp theo.
