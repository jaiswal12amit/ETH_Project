# JANGO Token Smart Contract

## Overview

This is a simple smart contract implemented in Solidity for a token named "JANGO" with the abbreviation "JGO". The contract includes functionalities to mint and burn tokens, manage balances, and keep track of the total supply. 

## Contract Details

### Variables

- `token__name`: Public variable storing the name of the token ("JANGO").
- `token__abbr`: Public variable storing the abbreviation of the token ("JGO").
- `total__supply`: Public variable storing the total supply of tokens.
- `balance`: Public mapping variable that maps addresses to their respective balances.

### Functions

#### `mint(address addr, uint value)`

This function mints new tokens.
- Parameters:
  - `addr`: The address to which the minted tokens will be assigned.
  - `value`: The number of tokens to be minted.
- Behavior:
  - Increases the `total__supply` by the specified `value`.
  - Increases the balance of the specified address by the specified `value`.

#### `burn(address addr, uint value)`

This function burns tokens, effectively reducing the total supply.
- Parameters:
  - `addr`: The address from which the tokens will be burned.
  - `value`: The number of tokens to be burned.
- Behavior:
  - Checks if the balance of the specified address is greater than or equal to the `value`.
  - If the balance is sufficient, decreases the `total__supply` by the specified `value`.
  - Decreases the balance of the specified address by the specified `value`.

## Requirements

1. **Token Details**: The contract has public variables that store the details about the token (Token Name, Token Abbrv., Total Supply).
2. **Address Balances**: The contract has a mapping of addresses to balances (`mapping(address => uint)`).
3. **Mint Function**: 
   - Takes an address and a value as parameters.
   - Increases the total supply by the specified value.
   - Increases the balance of the specified address by the specified value.
4. **Burn Function**:
   - Takes an address and a value as parameters.
   - Decreases the total supply by the specified value.
   - Decreases the balance of the specified address by the specified value.
   - Includes a condition to ensure the balance of the specified address is greater than or equal to the amount to be burned.

### burning tokens :
Ensure the address has a sufficient balance to cover the burn amount. The function will only execute if the balance of the specified address is greater than or equal to the amount to be burned.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Getting Started

### Prerequisites

To compile and deploy this smart contract, you'll need the following:

- Solidity compiler version 0.8.18.
- An Ethereum wallet (such as MetaMask) and some test Ether.
- A development environment like Remix IDE or Truffle.

### Deployment

1. Open the Solidity file in your preferred development environment.
2. Compile the contract using the Solidity compiler (version 0.8.18).
3. Deploy the contract to the Ethereum network (or a local test network).

### Example

Below is an example of how you can interact with the contract after deployment:

```solidity
// Initialize the contract
Token token = new Token();

// Mint 1000 tokens to an address
token.mint(0xYourAddress, 1000);

// Burn 500 tokens from an address
token.burn(0xYourAddress, 500);
```

Replace `0xYourAddress` with the actual Ethereum address you want to interact with.

## Authors

- [Amit Jaiswal](https://github.com/jaiswal12amit)
