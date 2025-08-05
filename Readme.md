# Bonkfun-bundler
https://x.com/0xmooncity
A Solana-based token bundler and transaction automation tool, designed for creating, distributing, and managing tokens and wallets at scale. Built with TypeScript and leveraging the Solana, Raydium, and Anchor SDKs.

## Features

- **Token Creation**: Automates the creation of new tokens on Solana, including metadata and launchpad setup.
- **Wallet Distribution**: Distributes SOL to multiple generated wallets for mass participation or airdrops.
- **Automated Buying**: Executes buy instructions across distributed wallets.
- **LUT (Address Lookup Table) Management**: Creates and manages Solana address lookup tables for efficient transaction batching.
- **Gathering & Closing**: Gathers tokens/SOL from distributed wallets and closes them, reclaiming rent.
- **Jito Fee Integration**: Supports Jito fee wallets for MEV-aware transaction execution.
- **Utility Scripts**: Includes scripts for closing LUTs, gathering funds, and checking status.

## Project Structure

- `index.ts`: Main entry point for token creation, distribution, and buy automation.
- `src/`: Core logic for token creation, transaction building, and utility functions.
- `gather.ts`: Script to gather tokens/SOL from distributed wallets and close them.
- `closeLut.ts`: Script to close address lookup tables.
- `status.ts`: Script to check the status of wallets and transactions.
- `constants/`: Environment variable management and project-wide constants.
- `executor/`: Transaction execution logic, including Jito and legacy support.
- `utils/`: Helper functions for file I/O, transaction building, and more.

## Getting Started

### Prerequisites

- Node.js (v18+ recommended)
- Yarn or npm
- Solana CLI (for wallet management)
- A funded Solana wallet

### Installation

```bash
yarn install
# or
npm install
```

### Environment Variables

Create a `.env` file in the project root with the following variables:

```
PRIVATE_KEY=...
RPC_ENDPOINT=...
RPC_WEBSOCKET_ENDPOINT=...
TOKEN_NAME=...
TOKEN_SYMBOL=...
DESCRIPTION=...
TOKEN_SHOW_NAME=...
TOKEN_CREATE_ON=...
TWITTER=...
TELEGRAM=...
WEBSITE=...
FILE=...
VANITY_MODE=false
SWAP_AMOUNT=0.01
DISTRIBUTION_WALLETNUM=10
JITO_FEE=0.001
BUYER_WALLET=...
BUYER_AMOUNT=...
```

> **Note:** See `constants/constants.ts` for all required variables.

### Usage

- **Start the bundler (main process):**
  ```bash
  yarn start
  # or
  npm run start
  ```

- **Gather funds and close wallets:**
  ```bash
  yarn gather
  # or
  npm run gather
  ```

- **Close LUTs:**
  ```bash
  yarn close
  # or
  npm run close
  ```

- **Check status:**
  ```bash
  yarn status
  # or
  npm run status
  ```

## Scripts

- `start`: Runs the main bundler process (`index.ts`)
- `gather`: Gathers funds and closes distributed wallets (`gather.ts`)
- `close`: Closes address lookup tables (`closeLut.ts`)
- `status`: Checks wallet and transaction status (`status.ts`)
- `test`: (If implemented) Runs tests

## Dependencies

- `@solana/web3.js`
- `@raydium-io/raydium-sdk` and `@raydium-io/raydium-sdk-v2`
- `@coral-xyz/anchor`
- `@solana/spl-token`
- `axios`, `dotenv`, `js-sha256`, `pino`, `typescript`, and more

See `package.json` for the full list.


