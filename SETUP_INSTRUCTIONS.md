
# Complete Setup Instructions

## 🚀 Quick Start Guide

### Prerequisites
- Node.js v16+ installed
- MetaMask browser extension
- Git installed on your system

### 1. Download Project Locally

**From GitHub (Recommended):**
```bash
# Clone your repository
git clone https://github.com/yourusername/your-repo-name.git
cd your-repo-name

# Install dependencies
npm install
```

**Alternative - Download ZIP:**
1. Download project as ZIP from Lovable/GitHub
2. Extract to your desired folder
3. Open terminal in project folder
4. Run `npm install`

### 2. Environment Setup

Create `.env` file in project root using these details:
```bash
# Blockchain Configuration for Sepolia Testnet Only
SEPOLIA_URL=https://sepolia.infura.io/v3/c979ea163a5c43af8fc345e2dbdfc4d1
PRIVATE_KEY=98d38a21f39233bd3d14c390edd6c16cb046dfcf13748719cca924794a770825
ETHERSCAN_API_KEY=8C1YWR1ZKVJARXIU6261UCB6NJJSB9PB2T

# Contract Address (Update after deployment)
VITE_VOTING_CONTRACT_ADDRESS=0x0000000000000000000000000000000000000000
```

### 3. Get Required API Keys

You already have the necessary Infura, Private Key, and Etherscan API keys set above.

**MetaMask Private Key:**  
1. Open MetaMask  
2. Click account menu → Account Details  
3. Export Private Key (keep this secure!)

### 4. Deploy Smart Contracts

**Deploy to Sepolia Testnet**
```bash
# Get testnet ETH from https://sepoliafaucet.com/
# Deploy contract
npx hardhat run scripts/deploy.cjs --network sepolia

# Copy the deployed address and update src/services/web3Service.ts
```

*(No mainnet step: this project uses Sepolia testnet only)*

### 5. Update Contract Address

After deployment, update `src/services/web3Service.ts`:
```typescript
// Replace with your deployed contract address
const CONTRACT_ADDRESS = "0xYourDeployedContractAddressHere";
```

### 6. Start Application

```bash
# Start development server
npm run dev

# Open browser to http://localhost:5173
```

## 🔧 Development Workflow

### Daily Development
```bash
# Start local blockchain (Terminal 1)
npx hardhat node

# Start frontend (Terminal 2)
npm run dev

# Make changes and test in browser
```

### Smart Contract Changes
```bash
# Compile contracts
npx hardhat compile

# Redeploy after changes
npx hardhat run scripts/deploy.js --network sepolia

# Update contract address in frontend
```

### Demo Preparation
- Have test accounts ready (supervisor + voter)
- Pre-create sample election
- Test voting flow completely
- Verify results display correctly
- Prepare backup screenshots

## 🛠️ Troubleshooting

### Common Issues

**MetaMask Connection Issues:**
- Ensure MetaMask is installed and unlocked
- Switch to Sepolia testnet
- Refresh page after network changes

**Contract Deployment Fails:**
- Check you have enough Sepolia ETH for gas fees
- Verify private key is correct in .env
- Ensure Infura URL is working and project ID is correct

**Frontend Won't Start:**
- Run `npm install` to ensure dependencies
- Check Node.js version (needs v16+)
- Clear npm cache: `npm cache clean --force`

**Votes Not Working:**
- Verify contract address is updated
- Check MetaMask is connected to Sepolia
- Ensure voter is registered by supervisor

### Development Tips

**Reset Local Blockchain:**
```bash
# Stop hardhat node (Ctrl+C)
# Restart: npx hardhat node
# Redeploy contracts
```

**Clear Browser Data:**
- Clear localStorage in browser dev tools
- Disconnect and reconnect MetaMask
- Hard refresh page (Ctrl+Shift+R)

**Debug Smart Contracts:**
```bash
# Console logs in contracts
console.log("Debug message");

# View transaction details
npx hardhat verify --network sepolia ADDRESS
```

## 📱 Browser Setup

### Required Extensions
- MetaMask (essential for Web3 functionality)
- React Developer Tools (helpful for debugging)

### Browser Configuration
1. Install MetaMask extension
2. Create or import wallet
3. Add Sepolia testnet:
   - Network Name: Sepolia
   - RPC URL: https://sepolia.infura.io/v3/c979ea163a5c43af8fc345e2dbdfc4d1
   - Chain ID: 11155111
   - Symbol: ETH

## 🎯 Testing Checklist

- Smart contracts deployed successfully
- Frontend connects to MetaMask
- Can create elections as supervisor
- Can vote as registered voter
- Results update in real-time
- All navigation works properly
- Responsive design on different screens

---

*Follow these instructions step by step, and you'll have a fully functional decentralized voting system ready for your presentation!*

