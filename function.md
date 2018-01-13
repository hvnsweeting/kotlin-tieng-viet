## Dùng lại code - Function.

Function (hàm) là một cơ chế giúp dùng lại code. Thay vì copy lại 1 đoạn code nhiều lần và (có thể) thay đổi một chút, ta viết nó thành function, với những thứ thay đổi được cho vào làm argument (tham số).

Thay vì tính chu vi của các hình chữ nhật nhiều lần:

```kotlin
>>> var w = 3
>>> var h = 5
>>> var perimeter = (w + h) * 2
>>> println(perimeter)
16

>>> var w = 4
>>> var h = 6
>>> var perimeter = (w + h) * 2
>>> println(perimeter)
20
```
Ta định nghĩa function với tên `perimeter` (chu vi), với argument là w và h, trả về kết quả là giá trị tính toán được:

```kotlin
>>> fun perimeter(w: Int, h: Int): Int {
...   return (w + h) * 2
... }
>>> perimeter(3, 5)
16
>>> perimeter(4, 6)
20
```

Code khi sử dụng function vừa ngắn gọn hơn, vừa có tên rõ ràng nhìn vào tên là hiểu, vừa dễ dàng thay đổi tại 1 chỗ duy nhất nếu một ngày nào đó công thức tính chu vi phải nhân 4 lần mới thỏa mãn lòng tham.

CHÚ Ý: các giá trị argument hay kết quả function đều có ghi rõ kiều của nó. Nếu đưa vào sai kiểu, code sẽ không compile được và báo lỗi ngay:

```kotlin
>>> perimeter(2.0, 3)
error: the floating-point literal does not conform to the expected type Int
perimeter(2.0, 3)
```

## Default argument

Các tham số có thể có giá trị mặc định, giá trị đó sẽ thay đổi khi người dùng chỉ định cụ thể.

```kotlin
>>> fun printHello(name: String, upper: Boolean = true) {
...   if (upper == true) println("Hello ${name.toUpperCase()}")
...   else println("Hello $name")
... }
>>> printHello("world")
Hello WORLD
>>> printHello("world", upper=false)
Hello world
>>> printHello("world", false)
Hello world

```

Khi một function không chỉ định return gì, nó sẽ return `Unit`. `Unit` là kiểu dữ liệu chỉ có 1 giá trị : `Unit` - Giống `None` trong Python.


## TODO varargs
