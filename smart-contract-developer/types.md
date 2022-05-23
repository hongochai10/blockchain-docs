---
description: Type of each variable - Kiểu của mỗi biến.
---

# Types

Solidity is a statically typed language, which means that the type of each variable (state and local) needs to be specified. Solidity provides several elementary types which can be combined to form complex types.

Solidity là một ngôn ngữ được định kiểu tĩnh, có nghĩa là kiểu của mỗi biến (trạng thái và cục bộ) cần được chỉ định. Solidity cung cấp một số kiểu cơ bản có thể được kết hợp để tạo thành các kiểu phức tạp.

## Value&#x20;

Value Types: Các kiểu sau đây còn được gọi là kiểu giá trị, vì các biến của kiểu này luôn được chuyển theo giá trị, tức là chúng luôn được sao chép khi chúng sử dụng làm đối số hàm hoặc trong phép gán.

### Booleans

`bool`: Các giá trị có thể là hằng số `true`và `false`.

Operators:

* `!`(phủ định lôgic)
* `&&`(kết hợp logic, “và”)
* `||`(sự liên kết hợp lý, “hoặc”)
* `==`(bình đẳng)
* `!=`(bất bình đẳng)

Operators `||`và `&&` áp dụng các quy tắc đoản mạch phổ biến. Điều này có nghĩa là trong biểu thức , nếu được đánh giá , sẽ không được đánh giá ngay cả khi nó có thể có tác dụng phụ.

`f(x) || g(y) f(x) true g(y)`

## Integers

`int`/ `uint`: Các số nguyên có dấu và không dấu có kích thước khác nhau. Từ khóa `uint8`đến `uint256`trong các bước `8`(không có dấu từ 8 đến 256 bit) và `int8`đến `int256`. `uint`và `int`là bí danh cho `uint256`và `int256`, tương ứng.

Operators:

* `<=`, `<`, `==`, `!=`, `>=`, `>` (evaluate to `bool`)
* Bit operators: `&`, `|`, `^` (bitwise exclusive or), `~` (bitwise negation)
* Shift operators: `<<` (left shift), `>>` (right shift)
* Arithmetic operators: `+`, `-`, unary `-` (only for signed integers), `*`, `/`, `%` (modulo), `**` (exponentiation)

Đối với kiểu số nguyên `X`, bạn có thể sử dụng `type(X).min`và `type(X).max`để truy cập giá trị tối thiểu và giá trị lớn nhất có thể biểu diễn theo kiểu.

## Addition, Subtraction and Multiplication

Phép cộng, phép trừ và phép nhân có ngữ nghĩa thông thường, với hai chế độ khác nhau liên quan đến dòng thừa và dòng dưới:

Theo mặc định, tất cả số học đều được kiểm tra thiếu hoặc thừa, nhưng điều này có thể bị vô hiệu hóa bằng cách sử dụng [khối không được kiểm tra](https://docs.soliditylang.org/en/v0.8.13/control-structures.html#unchecked), dẫn đến gói số học. Thông tin chi tiết có thể được tìm thấy trong phần đó.

## **Division**

Vì kiểu kết quả của một phép toán luôn là kiểu của một trong các toán hạng, nên phép chia trên số nguyên luôn cho kết quả là số nguyên. Trong Solidity, phép chia làm tròn về 0. Điều này có nghĩa là .`int256(-5) / int256(2) == int256(-2)`

\
\




**Tài liệu tham khảo:**

* Solidity: [https://docs.soliditylang.org/en/v0.8.13/types.html#](https://docs.soliditylang.org/en/v0.8.13/types.html)
