---
title: "Solidity 101: Understanding and Preventing Reentrancy Attacks"
datePublished: Sun Jun 04 2023 15:56:11 GMT+0000 (Coordinated Universal Time)
cuid: clihluzyr000009l5cvgo3ko9
slug: solidity-101-understanding-and-preventing-reentrancy-attacks
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/w7ZyuGYNpRQ/upload/45132bf019cd1cbfe60a2bd24740b8dc.jpeg
tags: tutorial, beginners, blockchain, solidity, web3

---

In this post, we will look into one of the most infamous vulnerabilities in smart contracts: reentrancy attacks.

This kind of attack was responsible for many of the attacks between 2016-2023 that resulted in a loss of over 1 billion in stolen funds across multiple reentrancy hacks.

## What is a Reentrancy Attack?

A reentrancy attack is a type of security vulnerability in which a function can be interrupted during execution and re-invoked before its execution is finished. This can result in state variables being modified unexpectedly, often leading to devastating consequences.

Consider the following contract:

```solidity
pragma solidity ^0.8.3;

contract Vulnerable {
    mapping (address => uint) private balances;
    
    function deposit() public payable {
        balances[msg.sender] += msg.value;
    }

    function withdraw() public {
        uint amount = balances[msg.sender];
        (bool success, ) = msg.sender.call{value: amount}("");
        require(success, "Transfer failed.");
        balances[msg.sender] = 0;
    }
}
```

In this contract, an attacker can re-enter the `withdraw` function via the `call` function before `balances[msg.sender] = 0;` is executed. As a result, they can drain the contract of more Ether than they are supposed to.

## How to Prevent Reentrancy Attacks

There are several ways to prevent reentrancy attacks:

### Checks-Effects-Interactions Pattern

This pattern suggests that you should make any state changes in your functions before interacting with other contracts. Here's an example:

```solidity
function withdraw() public {
    uint amount = balances[msg.sender];
    balances[msg.sender] = 0; // State change before calling another contract
    (bool success, ) = msg.sender.call{value: amount}("");
    require(success, "Transfer failed.");
}
```

### Reentrancy Guard

Another approach is to use a reentrancy guard, a simple boolean flag that prevents a function from being re-entered. OpenZeppelin's `ReentrancyGuard` is a commonly used solution:

```solidity
pragma solidity ^0.8.3;

import "@openzeppelin/contracts/security/ReentrancyGuard.sol";

contract Secure is ReentrancyGuard {
    mapping (address => uint) private balances;
    
    function deposit() public payable {
        balances[msg.sender] += msg.value;
    }

    function withdraw() public nonReentrant {
        uint amount = balances[msg.sender];
        balances[msg.sender] = 0;
        (bool success, ) = msg.sender.call{value: amount}("");
        require(success, "Transfer failed.");
    }
}
```

### Using `transfer` or `send`

In newer versions of Solidity (&gt;=0.4.22), the recommended way to send Ether is by using the `transfer` or `send` functions, which have a fixed gas limit and can prevent reentrancy attacks. However, this method is generally considered as less secure than using the checks-effects-interactions pattern or a reentrancy guard.

```solidity
function withdraw() public {
    uint amount = balances[msg.sender];
    balances[msg.sender] = 0;
    payable(msg.sender).transfer(amount);
}
```

## Conclusion

Reentrancy attacks pose a significant threat to smart contracts, but by following proper coding practices and security measures, you can protect your contracts from such attacks.

Remember to always follow the checks-effects-interactions pattern, consider using a reentrancy guard, and think carefully before using `transfer` or `send` for transferring Ether.

Always test your contracts thoroughly before deployment, and consider getting a security audit for any contract that will hold significant value.

And always, happy coding!

.