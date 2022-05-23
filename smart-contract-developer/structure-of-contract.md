---
description: Hợp đồng Solidity rất giống với lập trình hướng đối tượng.
---

# Structure Of Contract

## State Variables

State Variables: Các biến giá trị được lưu trữ vĩnh viễn trong contract.

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.0 <0.9.0;

contract SimpleStorage {
    uint storedData; // State variable
    // ...
}
```

## Functions

Các hàm là các chức năng được định nghĩa bên trong hợp đồng, có thể bên ngoài hợp đồng.

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.1 <0.9.0;

contract SimpleAuction {
    function bid() public payable { // Function
        // ...
    }
}

// Helper function defined outside of a contract
function helper(uint x) pure returns (uint) {
    return x * 2;
}
```

## Function Modifiers

Bổ nghĩa của hàm có thể sử dụng để làm thay đổi hàm theo cách khai báo.

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.22 <0.9.0;

contract Purchase {
    address public seller;

    modifier onlySeller() { // Modifier
        require(
            msg.sender == seller,
            "Only seller can call this."
        );
        _;
    }

    function abort() public view onlySeller { // Modifier usage
        // ...
    }
}
```

## Events

Events: Ghi nhật ký tương tác với EVM Logging Facilities

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.21 <0.9.0;

contract SimpleAuction {
    event HighestBidIncreased(address bidder, uint amount); // Event

    function bid() public payable {
        // ...
        emit HighestBidIncreased(msg.sender, msg.value); // Triggering event
    }
}
```

## Errors

Errors: Cho phép bạn xác định tên và dữ liệu mô tả cho các tình huống lỗi.

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity ^0.8.4;

/// Not enough funds for transfer. Requested `requested`,
/// but only `available` available.
error NotEnoughFunds(uint requested, uint available);

contract Token {
    mapping(address => uint) balances;
    function transfer(address to, uint amount) public {
        uint balance = balances[msg.sender];
        if (balance < amount)
            revert NotEnoughFunds(amount, balance);
        balances[msg.sender] -= amount;
        balances[to] += amount;
        // ...
    }
}

```

## Struct Types

Cấu trúc là các kiểu được xác định tuỳ chỉnh có thể nhóm chung một số biến.

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.0 <0.9.0;

contract Ballot {
    struct Voter { // Struct
        uint weight;
        bool voted;
        address delegate;
        uint vote;
    }
}
```

## Enum Types

Enums có thể được sử dụng để tạo các kiểu tuỳ chỉnh với một tập hợp hữu hạn các "Giá trị không thay đổi"

```
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.4.0 <0.9.0;

contract Purchase {
    enum State { Created, Locked, Inactive } // Enum
}
```

**Tài liệu tham khảo:**

* Solidity v0.8.0: [https://docs.soliditylang.org/en/v0.8.13/structure-of-a-contract.html](https://docs.soliditylang.org/en/v0.8.13/structure-of-a-contract.html)
