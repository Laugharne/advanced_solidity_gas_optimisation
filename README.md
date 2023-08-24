### 📖 Table of Contents
<!-- TOC -->

- [📖 Table of Contents](#-table-of-contents)
- [📍 Overview](#-overview)
- [🌲 Repository Tree](#-repository-tree)

<!-- /TOC -->

----

### 📍 Overview

Ever been surprised by the gas costs in a smart contract? The Ethereum Virtual Machine calculates these costs deterministically, but understanding how is a bit obscure unless you want to comb through the dense yellowpaper! This course helps you understand where every last bit of gas is coming from and the gotchas that can make transactions surprisingly expensive.

----

### 🌲 Repository Tree
```bash
.
├── Section 1 : Overview of Gas Cost
│   ├── 01. Introduction
│   ├── 02. Lecture 2; Calculating The Cost of an Ethereum Transfer
│   ├── 03. Example Smart Contract Interactions Part 1
│   ├── 04. Example Smart contract Interactions Part 2
│   ├── 05. Example Smart contract Interactions Part 3
│   ├── 06. Heavy and Light Functions
│   ├── 07. Block Limit
│   ├── 08. Gas Efficient Chains
│   ├── 09. Prerequisite: Storage Slots
│   ├── 10. What are Opcodes
│   ├── 11. Opcode Gas Costs
│   ├── 12. Opcode Debugging Gas Cost
│   ├── 13. Function Selectors
│   ├── 14. Cost of Doing Nothing: Op Codes
│   ├── 15. Cost of Doing Nothing: Sum of Op Codes
│   ├── 16. Cost of Doing Nothing: Transaction Data
│   ├── 17. Cost of Doing Nothing: Memory Costs
│   ├── 18. Non-payable Functions
│   ├── 19. Unchecked Arithmetic Part 1
│   ├── 20. Unchecked Arithmetic Part 2
│   ├── 21. Gas Limit and More on 21,000 Gas
│   ├── 22. EIP 1559 Part 1
│   ├── 23. EIP 1559 Part 2
│   └── 24. Solidity Optimizer
├── Section 2 : Storage
│   ├── 25. Storage Overview
│   ├── 26. More on 5000 gas non-zero to non-zero
│   ├── 27. Smaller Integers
│   ├── 28. Unchanged Storage Values
│   ├── 29. Arrays
│   ├── 30. Refunds and Setting to Zero Part 1
│   ├── 31. Refunds and Setting to Zero Part 2
│   ├── 32. ERC20 Transfers
│   ├── 33. Storage Cost For Files
│   ├── 34. Structs and Strings Part 1
│   ├── 35. Variable Packing
│   └── 36. Array Length
├── Section 3 : Memory costs
│   ├── 37. Memory vs Calldata
│   ├── 38. Memory Explosion
│   └── 39. Memory is Never Cleared
├── Section 4 : Solidity Tricks
│   ├── 40. Function Names
│   ├── 41. Less Than vs Less Than or Equal To
│   ├── 42. Bit Shifting
│   ├── 43. Reverting Early
│   ├── 44. Short Circuiting
│   └── 45. Precomputing
└── Section 5 : Practice Problems
    └── 46. Gas Puzzles

51 directories, 333 files
```

----