
# Deployment Guide

## Prerequisites

1. Install Node.js (v16 or higher)
2. Install MetaMask browser extension
3. Get some ETH for gas fees (testnet ETH for testing)

## Setup

1. Clone the repository and install dependencies:
```bash
npm install
```

2. Create a `.env` file based on `.env.example`:
```bash
cp .env.example .env
```

3. Configure your `.env` file with:
   - Alchemy or Infura RPC URLs
   - Your private key (for deployment)
   - Etherscan API key (for contract verification)

## Local Development

1. Start a local Hardhat node:
```bash
npx hardhat node
```

2. Deploy contracts to local network:
```bash
npx hardhat run scripts/deploy.js --network localhost
```

3. Update the contract address in `src/services/web3Service.ts`

4. Start the frontend:
```bash
npm run dev
```

## Testnet Deployment (Sepolia)

1. Get Sepolia ETH from faucet: https://sepoliafaucet.com/

2. Deploy to Sepolia:
```bash
npx hardhat run scripts/deploy.js --network sepolia
```

3. Update contract address in `src/services/web3Service.ts`

4. Verify contract on Etherscan:
```bash
npx hardhat verify --network sepolia DEPLOYED_CONTRACT_ADDRESS
```

## Production Deployment

1. Deploy contracts to mainnet:
```bash
npx hardhat run scripts/deploy.js --network mainnet
```

2. Update contract address in production build

3. Deploy frontend to your hosting platform

## Usage Instructions

### For Supervisors:
1. Connect MetaMask wallet
2. Ensure you have supervisor privileges (contact contract owner)
3. Create elections through the supervisor dashboard
4. Add candidates to elections
5. Monitor voting progress and results

### For Voters:
1. Connect MetaMask wallet
2. Ensure you're registered as a voter (contact supervisor)
3. Browse available elections
4. Cast your vote (one vote per election)
5. View live results

## Important Notes

- Each vote costs gas fees (usually $1-5 on mainnet)
- Votes are permanent and cannot be changed
- All votes are publicly visible on the blockchain
- Voter privacy is maintained through wallet addresses
- Smart contracts are immutable once deployed

## Troubleshooting

- If transactions fail, check gas prices and network congestion
- Ensure MetaMask is connected to the correct network
- Verify you have sufficient ETH for gas fees
- Check contract addresses are correctly configured
