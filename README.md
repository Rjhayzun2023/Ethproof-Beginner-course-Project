# MyToken Smart Contract

This is a simple Solidity smart contract called **MyToken** that implements basic functionalities for creating and managing a custom token. The contract includes features like minting new tokens and burning existing tokens.

## Table of Contents

- [Requirements](#requirements)
- [Contract Overview](#contract-overview)
- [Usage](#usage)
- [Authors](#authors)
- [License](#license)

## Requirements

Before diving into the details of this smart contract, let's recap the requirements:

1. The contract should have public variables that store the details about the coin (Token Name, Token Abbreviation, Total Supply).
2. It should maintain a mapping of addresses to balances (address => uint).
3. The contract must have a **mint** function that takes two parameters: an address and a value. The function increases the total supply by that value and also increases the balance of the sender's address by the same amount.
4. A **burn** function is required, which works in the opposite way of the mint function. It should destroy tokens by deducting the specified value from the total supply and the balance of the sender's address.
5. The burn function should include conditionals to ensure that the sender's balance is greater than or equal to the amount to be burned.

## Code Overview

This Solidity smart contract, named **MyToken**, fulfills the requirements outlined above. Here's an overview of the contract:

- Public variables:
  - `name`: A string representing the name of the token.
  - `abbrv`: A string representing the abbreviation of the token.
  - `totalSupply`: An unsigned integer representing the total supply of the token.
  
- Events:
  - `LogMessage(string message)`: An event used for logging messages, particularly for insufficient balance checks in the burn function.

- Mapping:
  - `balances`: A mapping that associates Ethereum addresses with their token balances.

- Constructor:
  - The constructor initializes the contract with the token name, abbreviation, and an initial supply. It assigns the initial supply to the creator's address.

- **mint** function:
  - This function increases the total supply by the specified value and increases the balance of the provided address by the same amount.

- **burn** function:
  - This function destroys tokens by deducting the specified value from the total supply and the balance of the provided address.
  - It includes conditional checks to ensure that the sender's balance is sufficient for the requested burn.

## Usage

To use this contract:

1. Deploy it to the Ethereum blockchain with the constructor parameters (`name`, `abbrv`, `initialSupply`) to create your custom token.

2. Interact with the contract using Ethereum wallets or applications to mint and burn tokens as needed.

## Authors

Metacrafter Randel Jason B. Espiritu

## License

This contract is released under the MIT License. You can find the license information in the contract source code.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;
