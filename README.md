# Transparent Funding Platform Using Blockchain

[![Blockchain](https://img.shields.io/badge/Blockchain-Ethereum-blue)](https://ethereum.org/)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.10-orange)](https://soliditylang.org/)
[![React](https://img.shields.io/badge/React-Next.js-blue)](https://nextjs.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A decentralized crowdfunding platform built on Ethereum blockchain that ensures complete transparency, security, and global accessibility for fundraising campaigns. This platform eliminates intermediaries, prevents fraud, and provides immutable transaction records through smart contracts.

## 🎯 Project Overview

Traditional crowdfunding platforms suffer from lack of transparency, security vulnerabilities, high fees, and restricted global access. This project addresses these critical issues by leveraging blockchain technology to create a trustless, transparent, and efficient fundraising ecosystem.

### Key Features

- **🔒 Complete Transparency**: All transactions recorded on blockchain with immutable ledger
- **🌍 Global Accessibility**: Anyone worldwide can create or contribute to campaigns
- **💰 Zero Intermediaries**: Direct peer-to-peer transactions with minimal fees
- **🛡️ Enhanced Security**: Smart contract automation prevents fraud and misuse of funds
- **📊 Real-time Tracking**: Monitor campaign progress and fund utilization instantly
- **🔐 Wallet Integration**: Seamless MetaMask integration for secure transactions
- **📁 IPFS Storage**: Decentralized storage for campaign images and documents via Pinata

## 🏗️ System Architecture

```
User Interface (Frontend)
         ↓
    Next.js + React
         ↓
    Web3 Integration (ethers.js)
         ↓
    Ethereum Blockchain
         ↓
Smart Contracts (Solidity)
    ├── CampaignFactory
    └── Campaign
         ↓
    IPFS (Pinata Cloud)
```

## 🛠️ Technology Stack

### Frontend
- **Next.js** - React framework for server-side rendering
- **React** - UI component library
- **Styled Components** - CSS-in-JS styling
- **ethers.js** - Ethereum blockchain interaction
- **Rainbow Kit** - Wallet connection management

### Blockchain
- **Solidity** - Smart contract development (v0.8.10)
- **Hardhat** - Ethereum development environment
- **Ganache** - Local blockchain for testing
- **MetaMask** - Cryptocurrency wallet integration

### Storage
- **Pinata Cloud** - IPFS hosting for decentralized file storage

### Development Tools
- **Node.js** - JavaScript runtime
- **Dotenv** - Environment variable management
- **Visual Studio Code** - Code editor

## 📋 Prerequisites

- Node.js (v14+ recommended)
- MetaMask browser extension
- Ganache (for local development)
- Minimum 8GB RAM
- Stable internet connection

## ⚙️ Installation & Setup

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/transparent-funding-platform.git
cd transparent-funding-platform
```

2. **Install dependencies**
```bash
npm install
```

3. **Configure environment variables**
Create a `.env` file in the root directory:
```env
NEXT_PUBLIC_RPC_URL=http://127.0.0.1:7545
NEXT_PUBLIC_ADDRESS=<Your_Deployed_Contract_Address>
PINATA_API_KEY=<Your_Pinata_API_Key>
PINATA_SECRET_KEY=<Your_Pinata_Secret_Key>
```

4. **Start Ganache**
- Open Ganache and create a new workspace
- Note the RPC Server URL (typically http://127.0.0.1:7545)

5. **Compile smart contracts**
```bash
npx hardhat compile
```

6. **Deploy smart contracts**
```bash
npx hardhat run scripts/deploy.js --network localhost
```

7. **Run the development server**
```bash
npm run dev
```

8. **Access the application**
Open [http://localhost:3000](http://localhost:3000) in your browser

## 🚀 Usage Guide

### Creating a Campaign

1. **Connect Wallet**: Click "Connect Wallet" and authorize MetaMask
2. **Navigate to Create Campaign**: Click the "Create Campaign" button
3. **Fill Campaign Details**:
   - Campaign Title
   - Required Amount (in MATIC)
   - Category (Education, Health, Animal Welfare, etc.)
   - Campaign Story
   - Upload Image
4. **Confirm Transaction**: Approve the transaction in MetaMask
5. **Campaign Created**: Your campaign is now live on the blockchain

### Donating to a Campaign

1. **Browse Campaigns**: View all active campaigns on the homepage
2. **Select Campaign**: Click on any campaign to view details
3. **Enter Donation Amount**: Input the amount you wish to donate
4. **Confirm Transaction**: Approve the transaction in MetaMask
5. **Donation Complete**: View your transaction in the donation history

### Tracking Donations

- **Recent Donations**: View all donations made to a campaign in real-time
- **My Donations**: Track your personal contribution history
- **Transaction History**: Complete audit trail of all transactions
- **Campaign Progress**: Monitor funding progress with visual indicators

## 📁 Project Structure

```
├── contracts/
│   └── Campaign.sol              # Smart contracts
├── components/
│   ├── Form.js                   # Campaign creation form
│   ├── Wallet.js                 # Wallet connection component
│   ├── Header.js                 # Navigation header
│   └── Layout.js                 # Page layout wrapper
├── pages/
│   ├── index.js                  # Homepage
│   ├── dashboard.js              # User dashboard
│   └── [address].js              # Campaign detail page
├── artifacts/                    # Compiled contracts
├── scripts/
│   └── deploy.js                 # Deployment script
├── hardhat.config.js             # Hardhat configuration
└── README.md
```

## 🔐 Smart Contract Details

### CampaignFactory Contract
- **Purpose**: Factory pattern for creating campaign instances
- **Key Functions**:
  - `createCampaign()`: Deploys new campaign contracts
  - Emits `campaignCreated` event with campaign details

### Campaign Contract
- **Purpose**: Individual campaign management
- **Key Functions**:
  - `donate()`: Accept donations from contributors
  - Automatically transfers funds to campaign owner
  - Emits `donated` event for transparency
- **State Variables**:
  - `title`: Campaign name
  - `requiredAmount`: Funding goal
  - `receivedAmount`: Current funds collected
  - `owner`: Campaign creator address

## 🧪 Testing

The platform includes comprehensive test cases:

### Test Case 1: Campaign Creation
- Create campaign for child education at mines
- Verify campaign appears on homepage and dashboard
- Validate campaign details display correctly

### Test Case 2: Donation Flow
- Connect wallet and select campaign
- Enter donation amount and confirm transaction
- Verify funds transfer and transaction recording

### Test Case 3: Multiple Campaigns
- Create campaigns for various causes (animal welfare, healthcare)
- Test concurrent campaign management
- Validate isolated fund tracking

Run tests:
```bash
npx hardhat test
```

## 🎨 Screenshots

*(Add screenshots showing):*
- Homepage with campaign listings
- Campaign creation form
- Donation interface
- Transaction history
- MetaMask integration

## 🌟 Key Achievements

- ✅ Eliminated fraud through blockchain transparency
- ✅ Reduced transaction costs by removing intermediaries
- ✅ Enabled global participation without geographical restrictions
- ✅ Automated fund management through smart contracts
- ✅ Immutable transaction records for complete accountability
- ✅ Real-time campaign tracking and analytics

## 🚧 Future Enhancements

- [ ] **Multi-blockchain Support**: Extend to Polygon, Binance Smart Chain
- [ ] **Advanced Analytics**: Comprehensive campaign performance metrics
- [ ] **Mobile Application**: Native iOS and Android apps
- [ ] **Decentralized Identity (DID)**: Enhanced KYC/verification
- [ ] **DAO Governance**: Community-driven platform decisions
- [ ] **NFT Rewards**: Contributor recognition system
- [ ] **Milestone-based Funding**: Gradual fund release upon goal completion
- [ ] **Multi-currency Support**: Accept various cryptocurrencies

## 👥 Team

- **Kannemolla Santhosh** 
- **Jatavath Jayanth** 

**Guide**: P. Subhashini, Assistant Professor, CSE Department

**Institution**: Maturi Venkata Subba Rao (MVSR) Engineering College

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Dr. Vijaya Gunturu (Principal, MVSREC)
- J. Prasanna Kumar (HOD, CSE Department)
- K. Murali Krishna (Project Coordinator)
- All faculty and lab staff who supported this project


## 📚 References

Complete list of academic papers and resources referenced in the development of this platform is available in the project report.

---

**Note**: This project was developed as part of the B.Tech final year major project (Academic Year 2023-24) at MVSR Engineering College, affiliated with Osmania University.

