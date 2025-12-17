Chuo-Vote: Blockchain Voting System for Tanzanian Higher Education 🇹🇿
A secure, transparent voting platform built specifically for universities and colleges in Tanzania.

https://img.shields.io/badge/Status-Active_Development-yellow
https://img.shields.io/badge/License-MIT-blue
https://img.shields.io/badge/Made_for-Tanzania-green

Overview
Chuo-Vote is a decentralized voting platform designed to address election integrity challenges in Tanzanian higher education institutions. Born from the need for transparent student government elections and academic decision-making processes, this system leverages blockchain technology to create immutable, verifiable voting records.

Why Blockchain for Tanzanian Universities?

Transparency: Every vote is recorded on-chain, preventing tampering

Accessibility: Students can vote securely from multiple campuses

Auditability: Election results can be independently verified

Cost-effective: Reduces physical ballot costs and logistics

📋 Project Background
This project started in late 2024 after witnessing congestions during elections periods at Institute Of Finance Management (IFM). The goal was to create a system that could scale across Tanzania's 50+ higher education institutions while maintaining cultural and administrative relevance.


🚀 Getting Started
Prerequisites
Make sure you have these installed:

Node.js 18+ (I'm using v18.16.0 personally)

npm 

MetaMask wallet (for testing)

Basic understanding of blockchain concepts

Installation
Clone the repository

bash
git clone https://github.com/yourusername/chuo-vote.git
cd chuo-vote
Install dependencies

bash
npm install
# Had some issues with web3.js v1.x vs v4.x - stick with what's in package.json
Set up environment variables

bash
cp .env.example .env
# Fill in your values - contact me for testnet RPC URLs
Start development server

bash
npm run dev
# Sometimes runs on 5173, sometimes 3000 - check terminal output


Project Structure
text
chuo-vote/
├── src/
│   ├── components/     # React components
│   ├── contracts/      # Solidity smart contracts
│   ├── hooks/          # Custom React hooks
│   ├── lib/            # Utilities and config
│   ├── pages/          # Next.js pages (or React Router)
│   └── styles/         # Tailwind/CSS
├── contracts/          # Hardhat/Truffle project (if separate)
├── docs/               # Documentation
└── tests/              # Test files



🔧 Technologies Used
Frontend:

React 18 with TypeScript - For type safety and modern React features

Vite - Faster builds than Create React App (switched from CRA last month)

Tailwind CSS - Utility-first styling

shadcn/ui - Consistent component library

Web3.js/Ethers.js - Blockchain interaction

Blockchain:

Solidity - Smart contract development

Hardhat - Local development and testing

IPFS - For storing ballot metadata

Backend :

Node.js/Express


🎯 Key Features
Implemented:
✅ Student identity verification using institutional emails

✅ Secure wallet connection with MetaMask

✅ Basic voting smart contract deployment

✅ Real-time vote counting

✅ Audit trail for each ballot

In Progress:
🔄 Multi-institution support (UDOM, UDSM, MU, etc.)

🔄 SMS verification fallback (for areas with poor internet)

🔄 Offline vote queuing system

Planned:
📋 Integration with NECTA/TCU student databases

📋 Biometric verification options

📋 Swahili language interface


🧑‍💻 Development Notes

Challenges Encountered:
Network Connectivity: Tanzanian campuses have varying internet quality

Digital Literacy: Some students are new to crypto wallets

Regulatory Compliance: Working with university legal teams

Gas Fees: Exploring Layer 2 solutions for cost reduction


Design Decisions:
Used React over Angular for faster iteration (student devs know React better)

Chose Tailwind for rapid UI development

Implementing gradual wallet onboarding (start with simple email/password)


🤝 Contributing
We welcome contributions from Tanzanian developers and students! Please read our Contributing Guidelines first.

Areas needing help:

Swahili language localization

Mobile app development

Security audit of smart contracts


📄 License
MIT License - see LICENSE file for details.

🙏 Acknowledgments
Institute of Finance Management for pilot program feedback

Open-source blockchain community

Local developers who've provided testing feedback



For Tanzanian institutions interested in piloting Chuo-Vote, please reach out directly. We're particularly looking for universities with active computer science departments who can help with real-world testing.

Note: This project is independently developed and not officially affiliated with any Tanzanian government body. We're working with institutions on a voluntary pilot basis.

Last updated: [Current Date] - Working on the admin dashboard this week!
