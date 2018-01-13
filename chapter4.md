# Control Flow: if, when, for, while

Các bài trước mới học cách biểu diễn dữ liệu lên trên Kotlin sử dụng các kiểu dữ liệu có sẵn của Kotlin. Với control flow, ta có thể xử lý logic, điều kiện, thực hiện lặp đi lặp lại các đoạn code.

## if

```kotlin
>>> var age = 18
>>> if (age < 18) {
...   println("Chưa đủ tuổi xem film")
...   println("Mời về")
... } else {
...   println("Đã đủ tuổi xem film")
...   println("Mời vào")
... }
Đã đủ tuổi xem film
Mời vào

```

Code chạy từ trên xuống
- nếu điều kiện trong if là `true` thì khối lệnh (block) trong if sẽ được chạy
- nếu điều kiện trong if trả về `false` thì khối lệnh (block) trong else sẽ được chạy.

Như vậy if/else giúp rẽ nhánh chương trình thành 2 nhánh (branch) khác nhau, một khi đã đi nhánh này là không đi nhánh khác nữa.

Trong khối lệnh bên trong if và else, có thể chứa tiếp if và else tùy ý:

```kotlin
>>> if (age < 18) {
...   print("Chưa đủ tuổi")
...   print("Mời về")
... } else {
...   if (age < 30) {
...     print("Bạn gái đâu?")
...   } else {
...   }
...   println("Mời vào")
... }
Bạn gái đâu?Mời vào
```

Có 2 cách sử dụng `if`:
- dùng như 1 biểu thức (expression), tức sau khi chạy xong trả về giá trị
- dùng như 1 câu lệnh (st
atement) - chạy xong không trả về gì cả.

Cách dùng như thấy ở trên là cách dùng theo kiểu câu lệnh - CHÚ Ý: if luôn phải có else đi kèm.

Khi dùng như expression, ta phải gán giá trị mà biểu thức if trả về, nó sẽ trả về giá trị cuối cùng mà nó xử lý:

```kotlin
>>> var result = if (5 > 4) {
...   50
... } else {
...   40
... }
>>> println(result)
50
```

## For, break, continue

Kotlin cho phép dùng for để duyệt qua bất cứ object nào có thể duyệt qua (iterable) - như Array, string...

`break` giúp thoái khỏi vòng lặp chứa nó, `continue` giúp bỏ qua 1 vòng lặp.

```kotlin
>>> for (i in 1..10) {
...   if (i < 5) continue
...   else {
...     if (i > 8) break
...     else {
...       println(i)
...     }
...   }
... }
5
6
7
8
```

## while

Lặp cho tới khi điều kiện trong `while` sai thì dừng lại

```kotlin
>>> var i = 0
>>> while (i < 5) {
...    println(i)
...    i += 1
... }
0
1
2
3
4

```

## when

Dùng để kiểm tra lần lượt các điều kiện từ trên xuống dưới, dừng lại khi có một điều kiện đúng. Thay thế cho `switch` hay `if/elif/else` trong các ngôn ngữ khác.

```kotlin
>>> var x = 1
>>> when (x) {
...   in 1..5 -> println("x is in the range")
...   1,2,3 -> println("x is 1 or 2 or 3")
...   else -> println("Otherwise")
... }
x is in the range
```

Sau `->` có thể là một khối lệnh (block) nằm trong `{  }`
