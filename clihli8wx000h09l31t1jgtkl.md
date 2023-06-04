---
title: "Solidity 101: Understanding Storage, Memory, and Mappings"
datePublished: Sun Jun 04 2023 15:46:16 GMT+0000 (Coordinated Universal Time)
cuid: clihli8wx000h09l31t1jgtkl
slug: solidity-101-understanding-storage-memory-and-mappings
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1685893509694/f8a543d5-d58d-4b1d-a90c-166b8469d640.jpeg
tags: tutorial, beginners, blockchain, solidity, web3

---

Mastering Solidity requires a deep understanding of some of its unique features. This article goes into three of these features: ***storage, memory, and mappings.***

Hopefully, by the end of this post, you should have a good grasp of how these features work and how you can use them in your smart contracts.

## Storage vs. Memory

In Solidity, there are two locations where variables can be stored: storage and memory.

1. **Storage**: Variables stored in storage are persistent and saved on the blockchain. They stay in the contract's storage between function calls and even after the function in which they were declared ends. Storage is expensive in terms of gas costs due to the persistent nature of the Ethereum blockchain.
    

```solidity
contract StorageExample {
    uint public storageVar;  // This variable is in storage

    function setStorageVar(uint _value) public {
        storageVar = _value;  // Changes are persistent
    }
}
```

1. **Memory**: Variables stored in memory are temporary and exist only within the function call scope. Once the function call ends, they are erased. Memory is less expensive in terms of gas costs.
    

```solidity
contract MemoryExample {
    function calculate(uint _value) public pure returns (uint) {
        uint memoryVar = _value + 10;  // This variable is in memory
        return memoryVar;
    }
}
```

## Mappings

Mappings are a key-value store for storing and looking up data. In Solidity, mappings are declared with the `mapping` keyword.

Here's an example of a mapping in Solidity:

```solidity
contract MappingExample {
    mapping(address => uint) public balances;

    function updateBalance(address _user, uint _value) public {
        balances[_user] = _value;
    }
}
```

In the `MappingExample` contract, `balances` is a mapping where addresses (keys) are mapped to uints (values). The `updateBalance` function can be used to set the balance of a user.

A few things to note about mappings:

* Mappings can have any type as a value but only a limited number of types as a key: `address`, `uint`, `int`, `bytes`, and `bool`.
    
* Mappings do not have a length or a concept of a key or value being "set".
    
* It's not possible to iterate over a mapping or to retrieve a list of keys. If you need to perform these operations, you may need to store an extra array of keys.
    

## Conclusion

Solidity offers various storage mechanisms and data structures like storage, memory, and mappings.

**Understanding the differences between storage and memory is key to writing efficient contracts and managing gas costs.**

Mappings, on the other hand, provide a flexible and efficient way of managing relationships between data.

As you continue your journey into Solidity, remember that knowledge of these concepts will be invaluable in becoming a proficient smart contract developer.

Happy coding!