<div align="center">

![Sora Oracle Banner](./assets/sora-banner.png)

# x402 Oracle Infrastructure v5.0

**Building Web2 APIs as Oracles to Make x402 More Robust on BNB Chain**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.20-blue.svg)](https://soliditylang.org/)
[![BNB Chain](https://img.shields.io/badge/Chain-BNB_Mainnet-orange.svg)](https://www.bnbchain.org/)
[![npm](https://img.shields.io/badge/npm-@sora--oracle/sdk-red.svg)](https://www.npmjs.com/package/@sora-oracle/sdk)

**[🌐 Website](https://sora-oracle.xyz)** • **[𝕏 Twitter](https://x.com/SoraOracle)** • **[📖 Docs](./SORA_ORACLE_TECHNICAL_SPECIFICATION.md)** • **[🔍 Contract](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)**

</div>

---

## 🚀 Live on BNB Chain Mainnet

**S402Facilitator Contract:**  
[`0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3`](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)

✅ **Production Ready** • ✅ **Verified on BSCScan** • ✅ **Fully Functional**

---

## 🎯 What is x402 Oracle Infrastructure?

x402 Oracle Infrastructure is a **robust oracle system** that transforms Web2 APIs into reliable data sources for x402 micropayments. We're building the missing piece that makes x402 truly robust by providing verified, real-time data feeds from traditional web APIs with cryptographic verification and seamless integration.

### Key Features

✅ **Web2 API Integration** - Transform any REST API into a verified oracle  
✅ **x402 Micropayments** - HTTP 402 payments using USDC on BNB Chain  
✅ **Multi-Wallet Parallelization** - 10x faster than sequential transactions  
✅ **23 Smart Contracts** - Production-ready oracle infrastructure  
✅ **TypeScript SDK** - React hooks for zero-boilerplate integration  
✅ **Mainnet Deployed** - Live on BNB Chain  
✅ **Cryptographic Verification** - TLS + SHA256 + IPFS verification  
✅ **AI-Powered Discovery** - Automatically discover and validate new APIs

---

## 🚀 Quick Start

### Install SDK

```bash
npm install @sora-oracle/sdk
```

### Create Your First x402 Oracle

```typescript
import { x402OracleSDK } from "@sora-oracle/sdk";

const sdk = new x402OracleSDK({
  chainId: 56, // BNB Chain Mainnet
  rpcUrl: "https://bsc-dataseed.binance.org/",
  s402FacilitatorAddress: "0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3",
});

// Transform a Web2 API into an x402 oracle
const oracle = await sdk.createOracle({
  name: "CoinGecko Price Oracle",
  apiEndpoint: "https://api.coingecko.com/api/v3/simple/price",
  parameters: {
    ids: "bitcoin",
    vs_currencies: "usd",
  },
  payment: {
    token: "USDC",
    amount: "0.01", // $0.01 USDC per query
  },
});

// Query the oracle with x402 payment
const price = await oracle.query();
console.log(`BTC Price: $${price.value}`);
```

---

## 📦 Repository Structure

```
sora-oracle-sdk/
│
├── 📄 README.md                              # You are here
├── 📄 QUICK_START.md                         # 5-minute guide
├── 📄 CONTRIBUTING.md                        # Contribution guide
├── 📄 LICENSE                                # MIT License
├── 📄 package.json                           # v5.0.0
│
├── 📁 contracts/                             # 23 Smart Contracts
│   ├── S402Facilitator.sol                   # ⭐ s402 payment settlement (DEPLOYED)
│   ├── SoraOracle.sol                        # Core oracle with bounties
│   ├── SimplePredictionMarket.sol            # Binary (yes/no) markets
│   ├── MultiOutcomeMarket.sol                # 2-10 outcome markets
│   ├── OrderBookMarket.sol                   # Limit order book trading
│   ├── AMMPredictionMarket.sol               # AMM-style liquidity pools
│   ├── ConditionalMarket.sol                 # Markets with linked outcomes
│   ├── RangeBettingMarket.sol                # Bet on price ranges
│   ├── TimeSeriesMarket.sol                  # Statistical predictions
│   ├── PancakeTWAPOracle.sol                 # Manipulation-resistant TWAP
│   ├── BatchOracleOperations.sol             # Batch 20 questions (30% gas savings)
│   ├── OracleReputationTracker.sol           # Provider performance tracking
│   ├── DisputeResolution.sol                 # Stake-based challenges
│   ├── AutomatedMarketResolver.sol           # AI-powered settlement
│   ├── BatchPayoutDistributor.sol            # Efficient winner payouts
│   ├── MarketFactory.sol                     # Market registry
│   ├── ReferralRewards.sol                   # Viral growth (5% rewards)
│   ├── LiquidityIncentives.sol               # Bootstrap new markets
│   ├── AggregatedOracle.sol                  # Multi-source consensus
│   ├── ScheduledFeeds.sol                    # Automated updates
│   ├── CrossChainBridge.sol                  # Multi-chain data
│   ├── DAOGovernance.sol                     # Community voting
│   ├── OracleStaking.sol                     # Reputation staking
│   └── SlashingMechanism.sol                 # Penalty system
│
├── 📁 src/sdk/                               # TypeScript SDK
│   ├── MultiWalletS402Pool.ts                # ⭐ 10x parallel speedup
│   ├── S402Client.ts                         # s402 payment client
│   ├── s402-config.ts                        # Mainnet configuration
│   ├── SoraOracleClient.ts                   # Oracle interactions
│   ├── PredictionMarketClient.ts             # Market interactions
│   └── MultiOutcomeMarketClient.ts           # Multi-outcome markets
│
├── 📁 src/ai/                                # Permissionless Oracle
│   ├── SelfExpandingResearchAgent.ts         # ⭐ AI-powered API discovery
│   ├── APIDiscoveryAgent.ts                  # Automatic API finding
│   ├── DataSourceRouter.ts                   # Intelligent routing
│   ├── TLSVerifier.ts                        # Certificate verification
│   └── IPFSClient.ts                         # Decentralized storage
│
├── 📁 server/                                # Backend Examples
│   ├── s402-middleware.js                    # ⭐ Payment verification
│   ├── index.js                              # Blockchain indexer
│   └── storage.ts                            # Database layer
│
├── 📁 frontend/                              # React UI Example
│   ├── src/
│   │   ├── components/                       # React components
│   │   ├── pages/                            # App pages
│   │   ├── config.ts                         # Contract addresses
│   │   └── App.tsx                           # Main app
│   └── package.json
│
├── 📁 scripts/                               # Deployment & Utils
│   ├── deploy-s402-mainnet.js                # ⭐ Mainnet deployment
│   ├── ai-oracle-settler.js                  # AI-powered settlement
│   ├── fund-workers.js                       # Fund worker wallets
│   ├── check-worker-balances.js              # Monitor balances
│   └── [15+ more utility scripts]
│
├── 📁 test/                                  # Test Suite
│   ├── S402Facilitator.test.js
│   ├── MultiOutcomeMarket.test.js
│   └── [comprehensive test coverage]
│
├── 📁 examples/                              # SDK Usage Examples
│   ├── sdk-usage.ts                          # Basic SDK usage
│   ├── multi-wallet-demo.ts                  # Parallel payments
│   └── self-expanding-demo.ts                # Permissionless oracle
│
└── 📁 docs/                                  # Documentation
    ├── SORA_ORACLE_TECHNICAL_SPECIFICATION.md    # ⭐ Complete architecture
    ├── V5_PERMISSIONLESS_ORACLE_COMPLETE.md      # ⭐ Self-expanding agent
    ├── X402_VS_S402_COMPARISON.md                # ⭐ s402 protocol explained
    ├── USDC_USDT_BNB_CHAIN_IMPLEMENTATION.md     # s402 implementation
    ├── EIP_PAYMENT_STANDARDS_COMPARISON.md       # EIP-2612 vs EIP-3009
    └── EIP3009_LOOPHOLE_ANALYSIS.md              # Why EIP-3009 doesn't work
```

**⭐ = Core v5.0 features**

---

## 🏗️ Architecture

### v5.0: x402 Oracle Infrastructure

x402 Oracle Infrastructure v5.0 introduces **robust oracle infrastructure** that makes x402 payments more reliable by integrating Web2 APIs:

```
Web2 API → Oracle Verification → x402 Payment → Data Response
   (REST)      (TLS+SHA256)      (USDC)        (Verified Data)
```

**Key Components:**

1. **S402Facilitator.sol** - Smart contract for x402 payment settlement (1% platform fee)
2. **MultiWalletS402Pool** - 10 worker wallets for parallel transactions (10x speedup)
3. **s402-middleware.js** - Backend payment verification
4. **Web2 API Integration** - Transform any REST API into a verified oracle
5. **AI-Powered Discovery** - Automatically discover and validate new APIs

### Why x402 Oracle Infrastructure?

**Traditional x402:**

- ✅ HTTP 402 micropayments
- ❌ Limited to basic data sources
- ❌ No verification mechanisms
- ❌ Single point of failure

**x402 Oracle Infrastructure:**

- ✅ HTTP 402 micropayments with Web2 API integration
- ✅ Cryptographic verification (TLS + SHA256 + IPFS)
- ✅ AI-powered API discovery and validation
- ✅ Multi-source consensus and redundancy
- ✅ Works on BNB Chain with EIP-2612

**[Read Full Comparison →](./X402_VS_S402_COMPARISON.md)**

---

## 💡 Use Cases

### 1. Real-Time Price Feeds

```typescript
// Transform CoinGecko API into verified x402 oracle
const priceOracle = await sdk.createOracle({
  name: "CoinGecko BTC Price",
  apiEndpoint: "https://api.coingecko.com/api/v3/simple/price",
  parameters: { ids: "bitcoin", vs_currencies: "usd" },
  verification: "tls+sha256+ipfs",
});

// Query with x402 payment
const price = await priceOracle.query();
console.log(`BTC: $${price.value} (verified: ${price.verified})`);
```

### 2. Weather Data APIs

```typescript
// Transform OpenWeatherMap into x402 oracle
const weatherOracle = await sdk.createOracle({
  name: "OpenWeatherMap Current Weather",
  apiEndpoint: "https://api.openweathermap.org/data/2.5/weather",
  parameters: { q: "London", appid: "YOUR_API_KEY" },
  payment: { token: "USDC", amount: "0.02" },
});

// Get weather data with micropayment
const weather = await weatherOracle.query();
console.log(`London: ${weather.main.temp}°C`);
```

### 3. Financial Data Integration

```typescript
// Transform Alpha Vantage API into x402 oracle
const stockOracle = await sdk.createOracle({
  name: "Alpha Vantage Stock Price",
  apiEndpoint: "https://www.alphavantage.co/query",
  parameters: {
    function: "GLOBAL_QUOTE",
    symbol: "AAPL",
    apikey: "YOUR_API_KEY",
  },
  payment: { token: "USDC", amount: "0.03" },
});

// Get stock data with verified payment
const stock = await stockOracle.query();
console.log(`AAPL: $${stock.price}`);
```

---

## 🛠️ Smart Contracts

### 23 Production-Ready Contracts

**Core Oracle (v3):**

- **SoraOracle** - Question/answer oracle with bounties
- **PancakeTWAPOracle** - Manipulation-resistant TWAP pricing

**Market Types (v3-v4):**

- **SimplePredictionMarket** - Binary (yes/no) markets
- **MultiOutcomeMarket** - 2-10 outcome markets
- **OrderBookMarket** - Limit order book (institutional-grade)
- **AMMPredictionMarket** - AMM-style liquidity pools
- **ConditionalMarket** - Markets with linked outcomes
- **RangeBettingMarket** - Bet on price ranges
- **TimeSeriesMarket** - Statistical predictions

**Automation (v4):**

- **AutomatedMarketResolver** - AI-powered settlement
- **AggregatedOracle** - Multi-source consensus
- **ScheduledFeeds** - Automated oracle updates
- **CrossChainBridge** - Multi-chain oracle data

**Operations:**

- **BatchOracleOperations** - Batch 20 questions (30% gas savings)
- **BatchPayoutDistributor** - Efficient winner payouts
- **DisputeResolution** - Stake-based challenges
- **OracleReputationTracker** - Provider performance

**Governance:**

- **DAOGovernance** - Community voting
- **OracleStaking** - Reputation and rewards
- **SlashingMechanism** - Penalty system

**Growth:**

- **ReferralRewards** - Viral growth (5% fee sharing)
- **MarketFactory** - Market registry with categories
- **LiquidityIncentives** - Bootstrap new markets

**v5.0 - s402 Payments:**

- **S402Facilitator** - Payment settlement with 1% platform fee ([View on BSCScan](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3))

---

## 📊 Pricing

### x402 Oracle Operation Costs

| Operation              | Price (USDC) | Description                         |
| ---------------------- | ------------ | ----------------------------------- |
| Web2 API Query         | $0.01        | Single API data request             |
| Verified Data Feed     | $0.03        | Cryptographically verified data     |
| Multi-Source Consensus | $0.05        | Multiple API sources + consensus    |
| AI API Discovery       | $0.02        | Auto-discover and validate new APIs |
| Batch API Queries      | $0.05        | Multiple API requests               |
| Real-Time Data Stream  | $0.10        | Continuous data feed                |

**Platform Fee:** 1% of all transactions (adjustable by owner, max 10%)

---

## 🔒 Security

### Smart Contract Security

- ✅ **OpenZeppelin v5** - Battle-tested libraries
- ✅ **ReentrancyGuard** - All withdrawal functions protected
- ✅ **Pausable** - Emergency stop mechanism
- ✅ **Access Control** - Role-based permissions
- ✅ **Input Validation** - All user inputs sanitized

### s402 Payment Security

- ✅ **EIP-712 Signatures** - Cryptographically secure payment authorizations
- ✅ **Replay Prevention** - Used payment tracking
- ✅ **Recipient Binding** - Payments cryptographically bound to recipient (prevents front-running)
- ✅ **Deadline Enforcement** - All payments have expiration times
- ✅ **Dual-Signature** - EIP-2612 permit + EIP-712 authorization

**[View Contract on BSCScan →](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)**

---

## 🌊 Gas Costs (BNB Chain)

| Operation               | Gas     | BNB (3 Gwei)  | USD ($600 BNB) |
| ----------------------- | ------- | ------------- | -------------- |
| Create Oracle           | ~200K   | ~0.0006 BNB   | ~$0.36         |
| Query Web2 API          | ~50K    | ~0.00015 BNB  | ~$0.09         |
| Verify Data             | ~45K    | ~0.000135 BNB | ~$0.08         |
| x402 Payment Settlement | ~180K   | ~0.00054 BNB  | ~$0.32         |
| Batch API Queries       | ~35K ea | ~0.000105 BNB | ~$0.06         |
| AI API Discovery        | ~100K   | ~0.0003 BNB   | ~$0.18         |

**Total Cost:** ~$0.50 to create oracle + query API with x402

---

## 🔗 Network Information

### BNB Chain Mainnet

- **Chain ID:** 56
- **RPC:** https://bsc-dataseed.binance.org/
- **Explorer:** https://bscscan.com
- **S402 Contract:** [`0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3`](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)
- **USDC:** `0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d` (Binance-Bridged, EIP-2612)
- **USDT:** `0x55d398326f99059fF775485246999027B3197955` (18 decimals!)

### BNB Chain Testnet

- **Chain ID:** 97
- **RPC:** https://data-seed-prebsc-1-s1.binance.org:8545/
- **Explorer:** https://testnet.bscscan.com
- **Faucet:** https://testnet.bnbchain.org/faucet-smart

---

## 📖 Documentation

### Core Concepts

- **[SORA_ORACLE_TECHNICAL_SPECIFICATION.md](./SORA_ORACLE_TECHNICAL_SPECIFICATION.md)** - Complete architecture and design
- **[V5_PERMISSIONLESS_ORACLE_COMPLETE.md](./V5_PERMISSIONLESS_ORACLE_COMPLETE.md)** - How the permissionless oracle works
- **[USDC_USDT_BNB_CHAIN_IMPLEMENTATION.md](./USDC_USDT_BNB_CHAIN_IMPLEMENTATION.md)** - s402 payment implementation

### Comparison & Analysis

- **[X402_VS_S402_COMPARISON.md](./X402_VS_S402_COMPARISON.md)** - Why we built s402 instead of using x402
- **[EIP_PAYMENT_STANDARDS_COMPARISON.md](./EIP_PAYMENT_STANDARDS_COMPARISON.md)** - EIP-2612 vs EIP-3009 deep-dive
- **[EIP3009_LOOPHOLE_ANALYSIS.md](./EIP3009_LOOPHOLE_ANALYSIS.md)** - Why "EIP-3009 on BNB" claims are false

### Getting Started

- **[QUICK_START.md](./QUICK_START.md)** - Get started in 5 minutes
- **[CONTRIBUTING.md](./CONTRIBUTING.md)** - How to contribute

---

## 🧪 Development

### Setup

```bash
# Install dependencies
npm install

# Compile contracts
npx hardhat compile

# Run tests
npx hardhat test

# Deploy to testnet
npx hardhat run scripts/deploy-s402.js --network bscTestnet
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Access at: http://localhost:5000

---

## 🤝 Contributing

We welcome contributions! This is open-source MIT licensed software.

```bash
# Fork and clone
git clone https://github.com/YOUR_USERNAME/sora-oracle-sdk

# Install and test
npm install && npx hardhat test

# Create feature branch
git checkout -b feature/amazing-feature

# Submit PR
```

**See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed guidelines.**

---

## 📄 License

**MIT License** - See [LICENSE](./LICENSE) for details.

Use it, fork it, modify it, sell it - whatever you want! All smart contracts are fully permissionless and open source.

---

## 🌟 Why x402 Oracle Infrastructure?

### vs. Traditional x402 Implementations

| Feature                  | x402 Oracle Infrastructure | Basic x402              | Coinbase x402         |
| ------------------------ | -------------------------- | ----------------------- | --------------------- |
| **Web2 API Integration** | ✅ Any REST API            | ❌ Limited sources      | ❌ Limited sources    |
| **Verification**         | ✅ TLS+SHA256+IPFS         | ❌ No verification      | ❌ Basic verification |
| **AI Discovery**         | ✅ Auto API discovery      | ❌ Manual setup         | ❌ Manual setup       |
| **Multi-Source**         | ✅ Consensus mechanism     | ❌ Single source        | ❌ Single source      |
| **BNB Chain**            | ✅ Native support          | ❌ Not supported        | ❌ Base only          |
| **Robustness**           | ✅ Redundant & verified    | ❌ Single point failure | ⚠️ Limited redundancy |

### vs. Traditional Oracles (Chainlink, UMA)

| Feature              | x402 Oracle Infrastructure | Chainlink            | UMA             |
| -------------------- | -------------------------- | -------------------- | --------------- |
| **x402 Payments**    | ✅ Native HTTP 402         | ❌ LINK tokens       | ❌ UMA bonds    |
| **Web2 Integration** | ✅ Direct API access       | ⚠️ Node operators    | ⚠️ Limited      |
| **Permissionless**   | ✅ Anyone can add APIs     | ❌ Whitelisted nodes | ⚠️ Token voting |
| **AI-Powered**       | ✅ Auto discovery          | ❌ Manual            | ❌ Manual       |
| **Micropayments**    | ✅ $0.01-0.15              | ❌ High costs        | ❌ High costs   |
| **BNB Chain**        | ✅ Native support          | ✅ Supported         | ⚠️ Limited      |

---

## 💬 Support & Community

- **Website:** [sora-oracle.xyz](https://sora-oracle.xyz)
- **𝕏 Twitter:** [@SoraOracle](https://x.com/SoraOracle)
- **Email:** soraoracle@proton.me
- **GitHub Issues:** [Report bugs & request features](https://github.com/sora-oracle/sora-oracle-sdk/issues)
- **Contract:** [View on BSCScan](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)

---

<div align="center">

**x402 Oracle Infrastructure v5.0** - Making x402 robust through Web2 API integration 🚀

✅ Web2 API Integration | ✅ x402 Micropayments | ✅ Cryptographic Verification | ✅ BNB Chain | ✅ Mainnet Live

Building the missing piece that makes x402 truly robust with verified, real-time data feeds.

Transforming Web2 APIs into reliable oracles for the decentralized web 🌐

**[Get Started →](./QUICK_START.md)** • **[View Contract →](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)** • **[Follow on 𝕏 →](https://x.com/SoraOracle)**

</div>
