# Học Kotlin một cách xì tin

Học lập trình Kotlin theo phong cách PyMi.vn - một phong cách trẻ trâu - một phong cách xì tin - và chuyên nghiệp :v


## Kotlin là gì?
Trên [trang chủ của Kotlin](https://kotlinlang.org/) có ghi

> Statically typed programming language for modern multiplatform applications 100% interoperable with Java™ and Android™

Kotlin là một ngôn ngữ lập trình, chạy trên nền tảng máy ảo Java (JVM),
tương thích hoàn toàn với Java và Android.

Dễ thấy nhất có thể dùng Kotlin để viết app chạy trên nền tảng Android
(hệ điều hành của các smartphone sản xuất bởi SamSung, Sony, HTC ...)

Theo dòng quảng cáo trên thì còn 2 điều đáng chú ý:
- multiplatform: chạy trên nhiều nền tảng - tức Android không phải là ứng dụng
duy nhất mà có thể dùng Kotlin - ta sẽ khám phá dần dần.
- Statically typed: một "tính năng" mà chỉ ai từng code mới quan tâm. Nếu chưa
code bao giờ, bạn sẽ cảm thấy nó giống một thủ tục rườm rà - nhưng trên thực tế,
tính năng này giúp viết code không bị các lỗi liên quan đến kiểu, phát hiện các
lỗi này trước khi chạy code (khi phát triển - dev), vì vậy khi đưa vào chạy Ithật
s không bao giờ làm phần mềm báo lỗi liên quan đến kiểu dữ liệu.

Kotlin là một ngôn ngữ lập trình mới, hiện tại ở phiên bản 1.2 (https://blog.jetbrains.com/kotlin/2017/11/kotlin-1-2-released/), nó xuất hiện vào năm
2010 và trở nên bùng nổ vào năm 2017 khi được Google công nhận là
ngôn ngữ chính thức được Android hỗ trợ.

Kotlin là một phần mềm mã nguồn mở (https://github.com/JetBrains/kotlin),
phát triển bởi công ty JetBrains - một công ty lừng danh với các IDE như
PyCharm, IntelliJ IDEA

### Kotlin để làm gì?
Vì Kotlin chạy trên máy ảo JVM, nên Java làm được cái gì thì Kotlin làm được
cái đó:

- Android App
- Web (server side)
- Web client với JavaScript hay JavaFX
- Desktop app

Vậy là quá đủ để gọi là "full-stack" rồi :v

Trích từ [FAQ của Kotlin](https://kotlinlang.org/docs/reference/faq.html) :

> Kotlin can be used for any kind of development, be it server-side, client-side web and Android. With Kotlin/Native currently in the works, support for other platforms such as embedded systems, macOS and iOS is coming. People are using Kotlin for mobile and server-side applications, client-side with JavaScript or JavaFX, and data science, just to name a few possibilities.

### Tại sao dùng kotlin
- Code Kotlin [ngắn hơn code Java ~ 40%](https://kotlinlang.org/docs/reference/faq.html#what-advantages-does-kotlin-give-me-over-the-java-programming-language).
- Tương thích 100% với Java - tức có thể sử dụng lượng thư viện Java đồ sộ đã
có
- Hỗ trợ cả OOP lẫn functional tận răng.
- Đây là chương trình hello world:

```kotlin
fun main(args: Array<String>) {
   println("Hello, PyMI.vn")
}
```

- Đây là bản Kotlin script của hello world:
```
println("Hello, PyMI")
```

Ngắn như Python:

```
print("Hello, PyMI")
```

- Có REPL (thường hay gọi là shell): gõ lệnh cái ra kết quả luôn:

```
$ kotlinc-jvm
Welcome to Kotlin version 1.2.10 (JRE 1.8.0_151-8u151-b12-0ubuntu0.16.04.2-b12)
Type :help for help, :quit for quit
>>> println("Hello, PyMI")
Hello, PyMI
>>> 2 + 2
4
```

