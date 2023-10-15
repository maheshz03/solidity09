# Token Smart Contract README

## Overview

This is a Solidity smart contract written for creating and managing a basic token on the Ethereum blockchain. The contract provides functionality for minting new tokens, burning existing tokens, and checking the token balance of a user.

## Contract Details

- **Token Name**: "Mahesh Zabade"
- **Token Abbreviation**: "MZ"
- **Total Supply**: 500 tokens

## Functions

### Mint
The `Mint` function allows for the creation of new tokens and assigns them to a specified Ethereum address.

**Parameters**:
- `_receiver` (address): The Ethereum address to which tokens will be minted.
- `_value` (uint): The number of tokens to mint and assign to the given address.

**Description**:
- Increases the total supply by the specified `_value`.
- Increases the balance of the `_receiver` address by the specified `_value`.

### Burn
The `Burn` function allows for the destruction of tokens, reducing both the total supply and the balance of a user's address.

**Parameters**:
- `_receiver` (address): The Ethereum address from which tokens will be burned.
- `_value` (uint): The number of tokens to burn from the given address.

**Description**:
- Checks if the balance of the `_receiver` address is greater than or equal to the specified `_value`.
- If the balance is sufficient, deducts the specified `_value` from the total supply and the balance of the `_receiver` address.

### User Balance
You can check the token balance of any user by directly querying the `userBalance` mapping with the user's Ethereum address.

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract Token {
    string public tokenTitle = "Mahesh Zabade";
    string public tokenCode = "MZ";
    uint public totalAmount = 500;
    
    mapping(address => uint) public userBalance;
    
    function Mint(address _receiver, uint _value) public {
        totalAmount += _value;
        userBalance[_receiver] += _value;
    }
    
    function Burn(address _receiver, uint _value) public {
        if (userBalance[_receiver] >= _value) {
            totalAmount -= _value;
            userBalance[_receiver] -= _value;
        }
    }
}








## Getting Started

To interact with this smart contract, follow these steps:

1. Use an Ethereum development environment, such as Remix or Truffle, to deploy and interact with the contract on the Ethereum blockchain.

2. Deploy the contract to the blockchain.

3. Use the deployed contract to mint and burn tokens for specific addresses. Make sure you meet the conditions to prevent burning more tokens than a user holds.

4. To check a user's token balance, use the `userBalance` mapping.

## License

This project is licensed under the MIT License. See the LICENSE.md file for more details.

## Author

- Author: Mahesh Zabade
- Contact: [Your Email Address]
