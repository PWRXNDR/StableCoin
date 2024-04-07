# Stablecoin Smart Contract

This Solidity smart contract provides a comprehensive solution for creating and managing a stablecoin, backed by Ethereum (ETH) as collateral. The contract integrates with various components such as an ERC20 token, an Oracle for price feeds, and a custom DepositorCoin for managing collateral. Below are the key features and functionalities of the contract:

## Features

### ERC20 Token Standard
- Implements an ERC20 token, providing standard functionalities such as transfer, balance tracking, and allowances.

### Collateral-Backed Stablecoin
- Allows users to mint and burn stablecoin tokens in exchange for ETH, maintaining a stable value pegged to the Oracle-provided price.

### Dynamic Fee Rate
- Implements a dynamic fee rate system for minting and burning operations, where fees are calculated as a percentage of the transaction amount.

### Initial Collateral Ratio
- Ensures a minimum initial collateral ratio, providing a safeguard against under-collateralization at the contract’s inception.

### Depositor Coin
- Issues a special Depositor Coin (DPC) for users who contribute excess collateral, representing their share in the surplus collateral pool.

### Oracle Integration
- Utilizes an external Oracle contract for fetching the current ETH price, critical for various calculations like minting, burning, and collateral management.

## Functionalities

### Minting Stablecoins
- Users can mint stablecoins by sending ETH to the contract. The minted amount is based on the current ETH price from the Oracle, minus a fee.

### Burning Stablecoins
- Users can burn stablecoins to withdraw their ETH collateral. The refund amount in ETH is calculated based on the current price, with a fee deduction.

### Deposit Collateral Buffer
- Users can deposit additional ETH as collateral. If the contract has a deficit, the ETH is used to cover it; otherwise, it contributes to a surplus.
- In case of surplus, the user receives Depositor Coins (DPC) proportional to their contribution.

### Withdraw Collateral Buffer
- Allows Depositor Coin (DPC) holders to withdraw their share of the collateral if there's a surplus in the contract.
- The withdrawal amount in ETH is calculated based on the user’s share in DPC and the current ETH price.

### Fee Calculation
- Fees for minting and burning are dynamically calculated as a percentage of the transaction value.

### Deficit/Surplus Calculation
- Internally calculates whether the contract is in a deficit or surplus state, crucial for managing collateral and DPC issuance.

### Error Handling
- Implements custom error messages for specific scenarios like failing to meet the initial collateral ratio.

## Getting Started

To deploy and interact with this contract:

1. Set up your Ethereum development environment with tools like Truffle or Hardhat.
2. Ensure you have a running Ethereum node or use services like Infura.
3. Deploy the Oracle contract and provide its address during the deployment of the Stablecoin contract.
4. Set the initial parameters like fee rate and initial collateral ratio upon deployment.

## Prerequisites

- An Oracle contract for ETH price feed
- Knowledge of ERC20 token standards


