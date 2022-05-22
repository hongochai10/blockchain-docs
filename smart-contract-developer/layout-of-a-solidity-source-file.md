---
description: Bố cục của một tập tin Solidity.
---

# Layout of a Solidity Source File

### Giấy phép

```
// SPDX-License-Identifier: MIT
```

Giá trị giấy phép đặc biệt: `UNLICENSED`

**Lưu ý rằng:** `UNLICENSED`(không được phép sử dụng, không có trong danh sách giấy phép SPDX) khác với `UNLICENSE`(cấp mọi quyền cho mọi người)

### Pragmas

Từ `pragma`khóa được sử dụng để kích hoạt các tính năng hoặc kiểm tra trình biên dịch nhất định. Một chỉ thị pragma luôn là cục bộ đối với một tệp nguồn, vì vậy bạn phải thêm pragma vào tất cả các tệp của mình nếu bạn muốn bật nó trong toàn bộ dự án của mình. Nếu bạn [nhập](https://docs.soliditylang.org/en/v0.8.14/layout-of-source-files.html#import) tệp khác, pragma từ tệp đó _không_ tự động áp dụng cho tệp nhập.

**Phiên bản Pragmas**

Phiên bản pragma được sử dụng như sau:

```
pragma solidity ^0.5.2;
pragma solidity >0.6.0;
pragma solidity >=0.4.0 <0.6.0;
```

### ABI Coder Pragmas

Bằng cách sử dụng hoặc bạn có thể chọn giữa hai cách triển khai của bộ mã hóa và giải mã ABI.

* `pragma abicoder v1`
* `pragma abicoder v2`

Nó sẽ được kích hoạt theo mặc định bắt đầu từ Solidity 0.8.0, nên có tùy chọn để chọn người viết mã cũ sử dụng.

Lên đến Solidity 0.7.4, có thể chọn bộ mã ABI v2 bằng cách sử dụng , nhưng không thể chọn bộ mã v1 một cách rõ ràng vì nó là mặc định. `pragma experimental ABIEncoderV2`

Bởi vì mã ABI v2 không được coi là thử nghiệm nữa, nó có thể được chọn thông qua (vui lòng xem ở trên) kể từ Solidity 0.7.4.`pragma abicoder v2`

### Nhập các tệp từ nguồn khác

```
import "filename";
import * as symbolName from "filename";
import "filename" as symbolName;
import {symbol1 as alias, symbol2} from "filename";
```

### Nhận xét

```
// This is a single-line comment.

/*
This is a
multi-line comment.
*/
```

**Tài liệu tham khảo:**

* Solidity: [https://docs.soliditylang.org/en/v0.8.14/layout-of-source-files.html](https://docs.soliditylang.org/en/v0.8.14/layout-of-source-files.html)
