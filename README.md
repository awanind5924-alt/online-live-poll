# LivePoll

LivePoll is a mini end-to-end Stellar + Soroban dApp: a multi-wallet polling app backed by a deployed Soroban smart contract on Stellar Testnet, with real-time contract event sync, transaction progress feedback, basic caching, and a small automated test suite.

---

# Level 3 Submission Checklist

- Live demo link: https://online-live-poll-three.vercel.app/
- Test output screenshot (3+ passing tests): ✅ (see below)
- Public GitHub repo link: https://github.com/awanind5924-alt/online-live-poll

---

# Submission Overview

This project demonstrates:

- Multi-wallet integration with StellarWalletsKit
- Smart contract deployment on Stellar Testnet
- Contract reads and writes from the frontend
- Real-time event polling and state synchronization
- Visible transaction lifecycle feedback
- Wallet error handling for missing wallet, rejected request, and insufficient balance
- Loading states and progress indicators during reads/writes
- Basic caching of recently loaded poll data in localStorage
- Automated tests for core helper logic

---

# Key Features

- Connect with supported Stellar wallets including Freighter, xBull, Albedo, Rabet, Lobstr, Hana, Hot Wallet, and Klever
- Create, vote on, close, and delete polls through frontend contract calls
- Browse contract data in read-only mode even without a connected wallet
- See transaction phases in the UI:
  - preparing
  - awaiting-signature
  - pending
  - success
  - error
- Refresh poll state automatically from recent on-chain contract events

---

# Demo Screenshots

## 1. Multi-Wallet Integration

<img width="1920" height="1080" alt="Screenshot 2026-06-16 205135" src="https://github.com/user-attachments/assets/f0de5548-a001-42c2-8f3c-9fba572fed42" />




# Deployed Contract

- Network: Stellar Testnet
- Contract address:

```text
CCFNX337JTKZ6HJSD55NLN6LUU3VHIOWWJOHAU4J32M6QQIJ25K6A3ZU
```

- Contract explorer:

https://stellar.expert/explorer/testnet/contract/CCFNX337JTKZ6HJSD55NLN6LUU3VHIOWWJOHAU4J32M6QQIJ25K6A3ZU

---

# Verifiable Contract Calls

Deploy transaction:

```text
a5bf9f5a73bbef57e88aabb67d0fb2cf58186f810f687468e7cf6dfc6ea7fc99
```

Explorer:

https://stellar.expert/explorer/testnet/tx/a5bf9f5a73bbef57e88aabb67d0fb2cf58186f810f687468e7cf6dfc6ea7fc99

Sample create_poll transaction:

```text
a83d7d16603eadfded067152d073cd7f936f59e5d1dc3749582f7d3609dd1a7a
```

Explorer:

https://stellar.expert/explorer/testnet/tx/a83d7d16603eadfded067152d073cd7f936f59e5d1dc3749582f7d3609dd1a7a

---

# Live Demo

https://online-live-poll-three.vercel.app/

---

# Setup

Run all commands from the project directory.

## Install dependencies

```bash
npm install
```

## Build the Soroban contract

```bash
npm run contract:build
```

## Sync WASM

```bash
npm run wasm:sync
```

## Create local environment file

```powershell
Copy-Item .env.example .env.local
```

## Start development server

```bash
npm run dev
```

## Build production version

```bash
npm run build
```

---

# Tests

Run the automated tests:

```bash
npm test
```

Expected output:

```text
✓ cache helpers
✓ poll logic
✓ vote counting

3 passing
```

---

# Environment Variables

```env
VITE_STELLAR_RPC_URL=https://soroban-testnet.stellar.org
VITE_STELLAR_NETWORK_PASSPHRASE=Test SDF Network ; September 2015
VITE_STELLAR_CONTRACT_ID=CCFNX337JTKZ6HJSD55NLN6LUU3VHIOWWJOHAU4J32M6QQIJ25K6A3ZU
VITE_STELLAR_READ_ACCOUNT=
VITE_STELLAR_EXPLORER_URL=https://stellar.expert/explorer/testnet
VITE_POLL_CONTRACT_WASM_URL=/contracts/poll_contract.wasm
```

---

# Testnet Notes

- A connected wallet must be funded on Stellar Testnet before sending contract transactions.
- If the wallet does not exist on Testnet, fund it using Friendbot first.
- Poll data can still be read without a connected wallet.

---

# Scripts

```bash
npm run dev
npm run build
npm run lint
npm test
npm run contract:build
npm run wasm:sync
npm run contract:deploy
```

---

# Walkthrough

1. Open the deployed site.
2. View contract data in read-only mode.
3. Connect a supported wallet.
4. Create a poll.
5. Sign the transaction.
6. Vote on the poll.
7. Observe real-time event updates.
8. Open the transaction and contract on Stellar Expert.

---

# Project Structure

```text
src/
 ├── lib/
 │   ├── stellar.js
 │   ├── pollCache.js
 │   └── pollLogic.js
 ├── components/
 └── pages/

poll_contract/
scripts/
tests/
public/
```

---

# Additional Documentation

- Frontend Guide: FRONTEND.md
- Contract Guide: poll_contract/README.md

---

# Submission Notes

- GitHub Repository:
  https://github.com/awanind5924-alt/online-live-poll

- Contract deployed and verified on Stellar Testnet
- Multi-wallet support implemented
- Real-time event synchronization implemented
- Transaction lifecycle feedback implemented
- Automated tests included
- Frontend deployed on Vercel
