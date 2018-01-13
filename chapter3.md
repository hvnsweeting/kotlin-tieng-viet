# Chữ và nghĩa

## Tạo string

Để biểu diễn các đoạn chữ lên Kotlin, ta dùng kiểu dữ liệu `String` để biểu diễn. Mỗi string được bao quanh bởi 1 cặp dấu double quote (`"`). CHÚ Ý: Single quote không dùng để biểu diễn string

```kotlin
>>> "ABC Kotlin"
ABC Kotlin
>>> 'ABC Kotlin'
error: too many characters in a character literal ''ABC Kotlin''
'ABC Kotlin'
^
```

Để tiện sử dụng, ta đặt gán một biến / giá trị bằng string này. Trong Kotlin có 2 loại:
- Giá trị: tức sau khi gán sẽ không đổi - hằng sô: ký hiệu là val (value)
- Biến: sau khi gán, có thể thay đổi giá trị khá, ký hiệu là var (variable).

```kotlin
>>> val number = 100
>>> number = number + 1
error: val cannot be reassigned
number = number + 1
^

>>> var number = 100
>>> number = number + 1
>>> number
101

```

Để gõ dấu `"` trong nôi dung string, cần phải đặt dấu `\` (backslash) trước nó, để kotlin hiểu rằng đây không phải là ký hiệu kết thúc string. Hành động này gọi là "escape".

```kotlin
>>> var s = "This is double quote \" - you see!"
>>> s
This is double quote " - you see!

```

Các ký hiệu đặc biệt như xuống dòng (newline), dấu tab cũng dùng escape để biểu diễn:

```kotlin
>>> var ss = "Trái đất này\nLà của chúng\tmình."
>>> ss
Trái đất này
Là của chúng	mình.

```

Quan sát bên trên có thể thấy Kotlin hỗ trợ UTF-8 (gõ được tiếng Việt) ngon lành.


## Indexing

Truy cập từng ký tự bằng index - số xuất phát từ 0, không có index âm (như Python):

```kotlin
>>> var s = "Kotlin"
>>> s[0]
K
>>> s[1]
o
>>> s[2]
t
>>> s[3]
l
>>> s[4]
i
>>> s[5]
n
>>> s[6]
java.lang.StringIndexOutOfBoundsException: String index out of range: 6
	at java.lang.String.charAt(String.java:658)
>>> s[-1]
java.lang.StringIndexOutOfBoundsException: String index out of range: -1
	at java.lang.String.charAt(String.java:658)
```

Thử thay đổi ký tự đầu tiên (chữ `K`) thành chữ `P`:

```kotlin
>>> s[0] = "P"
error: unresolved reference. None of the following candidates is applicable because of receiver type mismatch:
@InlineOnly public operator inline fun <K, V> MutableMap<Int, String>.set(key: Int, value: String): Unit defined in kotlin.collections
@InlineOnly public operator inline fun kotlin.text.StringBuilder /* = java.lang.StringBuilder */.set(index: Int, value: Char): Unit defined in kotlin.text
s[0] = "P"
^
error: no set method providing array access
s[0] = "P"
 ^

```

String trong Kotlin là kiểu dữ liệu không thay đổi được (immutable), một khi đã tạo ra thì không thay đổi được. Nếu muốn thay đổi nội dung, ta phải tạo ra một string mới.
Tính năng này giống hệt Python.

## Duyệt qua từng ký tự của string
Sử dụng vòng lặp `for`

```kotlin
>>> var s = "Kotlin"
>>> for (c in s) {
...   println(c)
... }
K
o
t
l
i
n
>>>
```

## Độ dài của một string

```kotlin
>>> var s = "Việt Nam"
>>> s.length
8
```

## Format string - string template
Một string có thể chứa "template expression", nó sẽ được xử lý với nội dung / giá trị tương ứng và đưa ra kết quả:


```kotlin
>>> var name = "PyMI"
>>> var age = 3
>>> var s = "Hello $name, you are $age years old"
>>> s
Hello PyMI, you are 3 years old
>>> var s2 = "Name: $name has length ${name.length}"
>>> s2
Name: PyMI has length 4
```

Tính năng này mới có trong Python 3.6.


## Kiểm tra phần tử

Dùng `in` và `!in`:

```kotlin
>>> "Ko" in "Kotlin"
true
>>> "KO" !in "Kotlin"
true
>>> "JAVA" in "Kotlin"
false
```

## TODO các function xử lý string

Tương tự như Python

```kotlin
>>> "Kotlin".startsWith("Kot")
true
>>> "Kotlin".endsWith("lin")
true
```
