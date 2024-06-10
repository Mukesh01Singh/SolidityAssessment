# MyToken Solidity Smart Contract

This repository contains the code for the `MyToken` smart contract, implemented in Solidity. The contract provides basic functionalities for minting and burning tokens.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Contract Details](#contract-details)
- [Functions](#functions)
  - [mint](#mint)
  - [burn](#burn)
- [Usage](#usage)
- [License](#license)

## Overview

`MyToken` is a simple ERC-20-like smart contract that allows the creation, minting, and burning of tokens. It includes:

- Public variables to store token details (name, abbreviation, total supply).
- A mapping to keep track of token balances for each address.
- Functions to mint and burn tokens.

## Requirements

1. Public variables to store:
   - Token Name
   - Token Abbreviation
   - Total Supply
2. A mapping to track balances of addresses.
3. A `mint` function to increase total supply and balance of a specified address.
4. A `burn` function to decrease total supply and balance of a specified address, with checks to ensure sufficient balance.

## Contract Details

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // Mapping of address to balance
    mapping (address => uint) public balances;
    
    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```
## Functions
mint
The mint function increases the total supply of the token and the balance of a specified address.

```
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
```
## Parameters:

_address: The address of the recipient.
_value: The number of tokens to mint.
burn
The burn function decreases the total supply of the token and the balance of a specified address. It ensures that the balance is sufficient before burning.

```
function burn(address _address, uint _value) public {
    require(balances[_address] >= _value, "Insufficient balance to burn");
    totalSupply -= _value;
    balances[_address] -= _value;
}
```
##  Parameters:

_address: The address of the token holder.
_value: The number of tokens to burn.
## Usage
Deploy the Contract: Deploy the MyToken contract to your preferred Ethereum network using Remix, Truffle, or another deployment tool.
Mint Tokens: Use the mint function to increase the token balance for a specific address.
Burn Tokens: Use the burn function to decrease the token balance for a specific address, ensuring sufficient balance is available.
## License
This project is licensed under the MIT License. See the LICENSE file for details.
