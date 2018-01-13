# Cài đặt và thiết lập môi trường dev
- Môi trường nào hỗ trợ dev Android thì hỗ trợ Kotlin - tức cả Linux, OSX, Windows...
- Cài đặt đơn giản, có nhiều cách để cài đặt ở trang chủ https://kotlinlang.org/. Người dùng Windows nên thao khảo cách cài đặt khác trên trang chủ. Còn với mục đích học tập, ở đây sẽ cài riêng `compiler` và sử dụng bất kỳ editor nào để code (notepad, sublimetext, VScode, ... vim)

## Cài đặt sử dụng SDKMAN! (Linux & OSX)

Theo https://kotlinlang.org/docs/tutorials/command-line.html

Gõ lệnh trên [terminal](http://www.familug.org/2012/03/ccgu-cli-can-ban.html):

```
curl -s https://get.sdkman.io | bash
```

Rồi mở terminal mới, gõ

```
sdk install kotlin
```

Cài xong sẽ xem được phiên bản kotlin

```
kotlin -version
# ra kết quả
Kotlin version 1.2.10 (JRE 1.8.0_151-8u151-b12-0ubuntu0.16.04.2-b12)
```

## Chạy hello world
Tạo file `hello.kt` với nội dung

```kotlin
fun main(args: Array<String>) {
   println("Hello, PyMI.vn")
}
```

Vào thư mục chứa file vừa tạo, gõ:

```
kotlinc hello.kt -include-runtime -d hello.jar
```

Chờ khoảng 5 giây, khi lệnh chạy xong, gõ:

```
java -jar hello.jar
# Màn hình hiện ra
Hello, PyMI.vn
```

Khi đã cài đặt xong môi trường, sẵn sàng để bước vào một hành trình mới
ở các bài tiếp theo.
