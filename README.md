# IPL Token Smart Contract

## Overview

The IPL Token (PL) is an ERC-20 compliant smart contract deployed on Ethereum. This token is designed for use within a specific ecosystem, leveraging Ethereum blockchain technology to ensure security, transparency, and wide compatibility. This smart contract includes functionalities for minting, burning, and transferring tokens.

## Features

- **ERC-20 Standard**: Adheres to the widely-adopted ERC-20 standard, ensuring compatibility with various Ethereum wallets and other smart contracts.
- **Ownership Management**: Only the owner of the contract (set at deployment) can mint new tokens, offering a controlled supply mechanism.
- **Burn Function**: Users can decrease the total supply by burning tokens they own.
- **Mint Function**: The contract owner can increase the supply by minting new tokens to a specified address.

## Contract Functions

### Constructor

- `constructor(address initialOwner)`
  - Initializes the token with the name "IPL" and symbol "PL".
  - Sets the initial owner of the contract.

### Mint

- `function mint(address to, uint256 amount) external onlyOwner`
  - Allows the contract owner to mint new tokens to a specified address.
  - **Parameters**:
    - `to`: Address of the recipient to receive the newly minted tokens.
    - `amount`: Amount of tokens to be minted.

### Burn

- `function burn(uint256 amount) external`
  - Allows any token holder to burn their tokens, reducing the total supply.
  - **Parameters**:
    - `amount`: Amount of tokens to be burned.

### Transfer

- `function transfer(address recipient, uint256 amount) public override returns (bool)`
  - Transfers tokens from the caller's address to the specified recipient.
  - **Parameters**:
    - `recipient`: Address of the recipient.
    - `amount`: Amount of tokens to transfer.

## Setup and Deployment

### Prerequisites

- Node.js and npm
- Truffle Suite or Hardhat for deployment
- An Ethereum wallet with Ether for deploying the contract

### Installation

1. Clone the repository or download the source code.
2. Install dependencies via npm:

    ```bash
    npm install @openzeppelin/contracts
    ```

3. Compile the smart contract using Truffle or Hardhat:

    ```bash
    truffle compile
    ```

    or

    ```bash
    hardhat compile
    ```

### Deployment

Use Truffle or Hardhat to deploy the contract to an Ethereum testnet or mainnet:

- Using Truffle:

    ```bash
    truffle migrate --network mainnet
    ```

- Using Hardhat:

    ```bash
    npx hardhat run scripts/deploy.js --network mainnet
    ```

Replace `mainnet` with your preferred network (e.g., `ropsten`, `rinkeby`, etc.).

