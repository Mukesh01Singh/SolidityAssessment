# MyToken Solidity Smart Contract

A simple ERC-20-like smart contract that allows the creation, minting, and burning of tokens.

## Description

`MyToken` is a Solidity smart contract designed to manage a basic token system. The contract provides functionalities to mint new tokens and burn existing ones, with checks in place to ensure sufficient balances for burning operations. It includes public variables to store token details such as the token name, abbreviation, and total supply, as well as a mapping to keep track of token balances for each address.

## Getting Started

### Installing

To get started with the `MyToken` smart contract, follow these steps:

1. Clone the repository from GitHub:
    ```sh
    git clone https://github.com/Mukesh01Singh/SolidityAssessment.git
    ```
2. Navigate to the project directory:
    ```sh
    cd Solidity
    ```

### Executing Program

To deploy and interact with the `MyToken` contract, use the following steps:

1. Open the Remix IDE (https://remix.ethereum.org/).
2. Create a new file named `MyToken.sol` and copy the contract code into it.
3. Compile the contract using the Solidity compiler.
4. Deploy the contract to a local or test Ethereum network.

#### Minting Tokens

To mint new tokens, use the `mint` function:

```solidity
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
```
Example:

1.Deploy the contract.
2.Call the mint function with the desired address and amount
```
mint('0xYourAddress', 1000)
```
### Burning Tokens
To burn existing tokens, use the burn function:
```
function burn(address _address, uint _value) public {
    require(balances[_address] >= _value, "Insufficient balance to burn");
    totalSupply -= _value;
    balances[_address] -= _value;
}
```
Example:

Ensure the address has a sufficient token balance.
Call the burn function with the address and amount to be burned:
```
burn('0xYourAddress', 500)
```
### Help
For any issues or common problems, refer to the following command to get helper information from the contract:

```
// Unfortunately, Solidity contracts do not typically include helper commands directly in the contract.
// However, detailed comments and documentation in the contract code can assist in troubleshooting.
```
### Authors
Name : Mukesh Singh
Metacrafterid: 22BCS14300
Email: msgzp2000@gmail.com
Loom Video Link: https://www.loom.com/share/fdf3b27de76f43f7a7ce7f611b1e0ada?sid=0fa6693d-c2d3-475e-b811-d562f827a39f


### License
This project is licensed under the MIT License - see the LICENSE file for details.
