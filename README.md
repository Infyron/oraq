<div align="center">

![x402 Oracle Banner](./assets/x402-banner.png)

# x402 Oracle Infrastructure v5.0

**Built by ORAQ - Building Web2 APIs as Oracles to Make x402 Protocol More Robust on BASE Chain**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Solidity](https://img.shields.io/badge/Solidity-0.8.20-blue.svg)](https://soliditylang.org/)
[![BASE Chain](https://img.shields.io/badge/Chain-BASE_Mainnet-orange.svg)](https://www.basechain.org/)
[![npm](https://img.shields.io/badge/npm-@x402--oracle/sdk-red.svg)](https://www.npmjs.com/package/@x402-oracle/sdk)

**[🌐 Website](https://x402-oracle.xyz)** • **[𝕏 Twitter](https://x.com/x402Oracle)** • **[📖 Docs](./X402_ORACLE_TECHNICAL_SPECIFICATION.md)** • **[🔍 Contract](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)**

</div>

---

## 🚀 Live on BASE Chain Mainnet (Primary Base)

**x402 Oracle Infrastructure Contract:**  
[`0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3`](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)

✅ **Production Ready** • ✅ **Verified on BSCScan** • ✅ **Fully Functional** • ✅ **BASE Chain Native**

---

## 🎯 What is x402 Oracle Infrastructure?

x402 Oracle Infrastructure, built by **ORAQ**, is a **robust oracle system** that transforms Web2 APIs into reliable data sources for the **x402 protocol** micropayments. We're building the missing piece that makes the x402 protocol truly robust by providing verified, real-time data feeds from traditional web APIs with cryptographic verification and seamless integration.

### Key Features

✅ **Web2 API Integration** - Transform any REST API into a verified oracle  
✅ **x402 Protocol Micropayments** - HTTP 402 payments using USDC on BASE Chain  
✅ **BASE Chain Native** - Built specifically for BASE Chain ecosystem  
✅ **Multi-Wallet Parallelization** - 10x faster than sequential transactions  
✅ **23 Smart Contracts** - Production-ready oracle infrastructure  
✅ **TypeScript SDK** - React hooks for zero-boilerplate integration  
✅ **Mainnet Deployed** - Live on BASE Chain  
✅ **Cryptographic Verification** - TLS + SHA256 + IPFS verification  
✅ **AI-Powered Discovery** - Automatically discover and validate new APIs

---

## 🚀 Quick Start

### Install SDK

```bash
npm install @x402-oracle/sdk
```

### Create Your First x402 Protocol Oracle

```typescript
import { x402OracleSDK } from "@x402-oracle/sdk";

const sdk = new x402OracleSDK({
  chainId: 56, // BASE Chain Mainnet (Primary Base)
  rpcUrl: "https://bsc-dataseed.binance.org/",
  s402FacilitatorAddress: "0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3",
});

// Transform a Web2 API into an x402 protocol oracle
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

// Query the oracle with x402 protocol payment
const price = await oracle.query();
console.log(`BTC Price: $${price.value}`);
```

---

## 📦 Repository Structure

```
x402-oracle-sdk/
│
├── 📄 README.md                              # You are here
├── 📄 QUICK_START.md                         # 5-minute guide
├── 📄 CONTRIBUTING.md                        # Contribution guide
├── 📄 LICENSE                                # MIT License
├── 📄 package.json                           # v5.0.0
│
├── 📁 contracts/                             # 23 Smart Contracts
│   ├── x402Facilitator.sol                   # ⭐ x402 protocol payment settlement (DEPLOYED)
│   ├── x402Oracle.sol                        # Core oracle with bounties
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
│   ├── MultiWalletx402Pool.ts                # ⭐ 10x parallel speedup
│   ├── x402Client.ts                         # x402 protocol payment client
│   ├── x402-config.ts                        # Mainnet configuration
│   ├── x402OracleClient.ts                   # Oracle interactions
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
│   ├── x402-middleware.js                    # ⭐ Payment verification
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
│   ├── deploy-x402-mainnet.js                # ⭐ Mainnet deployment
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
    ├── X402_ORACLE_TECHNICAL_SPECIFICATION.md    # ⭐ Complete architecture
    ├── V5_PERMISSIONLESS_ORACLE_COMPLETE.md      # ⭐ Self-expanding agent
    ├── X402_VS_S402_COMPARISON.md                # ⭐ s402 protocol explained
    ├── USDC_USDT_BASE_CHAIN_IMPLEMENTATION.md     # s402 implementation
    ├── EIP_PAYMENT_STANDARDS_COMPARISON.md       # EIP-2612 vs EIP-3009
    └── EIP3009_LOOPHOLE_ANALYSIS.md              # Why EIP-3009 doesn't work
```

**⭐ = Core v5.0 features**

---

## 🏗️ Architecture

### v5.0: x402 Oracle Infrastructure

x402 Oracle Infrastructure v5.0, built by **ORAQ**, introduces **robust oracle infrastructure** that makes x402 protocol payments more reliable by integrating Web2 APIs:

```
Web2 API → Oracle Verification → x402 Protocol Payment → Data Response
   (REST)      (TLS+SHA256)      (USDC)        (Verified Data)
```

**Key Components:**

1. **x402Facilitator.sol** - Smart contract for x402 protocol payment settlement (1% platform fee)
2. **MultiWalletx402Pool** - 10 worker wallets for parallel transactions (10x speedup)
3. **x402-middleware.js** - Backend payment verification
4. **Web2 API Integration** - Transform any REST API into a verified oracle
5. **AI-Powered Discovery** - Automatically discover and validate new APIs

### Why x402 Oracle Infrastructure?

**Traditional x402 Protocol:**

- ✅ HTTP 402 micropayments
- ❌ Limited to basic data sources
- ❌ No verification mechanisms
- ❌ Single point of failure

**x402 Oracle Infrastructure (by ORAQ):**

- ✅ HTTP 402 protocol micropayments with Web2 API integration
- ✅ Cryptographic verification (TLS + SHA256 + IPFS)
- ✅ AI-powered API discovery and validation
- ✅ Multi-source consensus and redundancy
- ✅ Works on BASE Chain with EIP-2612

**[Read Full Comparison →](./X402_VS_S402_COMPARISON.md)**

---

## 💡 Use Cases

### 1. Real-Time Price Feeds

```typescript
// Transform CoinGecko API into verified x402 protocol oracle
const priceOracle = await sdk.createOracle({
  name: "CoinGecko BTC Price",
  apiEndpoint: "https://api.coingecko.com/api/v3/simple/price",
  parameters: { ids: "bitcoin", vs_currencies: "usd" },
  verification: "tls+sha256+ipfs",
});

// Query with x402 protocol payment
const price = await priceOracle.query();
console.log(`BTC: $${price.value} (verified: ${price.verified})`);
```

### 2. Weather Data APIs

```typescript
// Transform OpenWeatherMap into x402 protocol oracle
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
// Transform Alpha Vantage API into x402 protocol oracle
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

- **x402Oracle** - Question/answer oracle with bounties
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

**v5.0 - x402 Oracle Infrastructure:**

- **x402Facilitator** - x402 protocol payment settlement with 1% platform fee ([View on BSCScan](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3))

---

## 📊 Pricing

### x402 Protocol Oracle Operation Costs

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

### x402 Protocol Payment Security

- ✅ **EIP-712 Signatures** - Cryptographically secure payment authorizations
- ✅ **Replay Prevention** - Used payment tracking
- ✅ **Recipient Binding** - Payments cryptographically bound to recipient (prevents front-running)
- ✅ **Deadline Enforcement** - All payments have expiration times
- ✅ **Dual-Signature** - EIP-2612 permit + EIP-712 authorization

**[View Contract on BSCScan →](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)**

---

## 🌊 Gas Costs (BASE Chain)

| Operation               | Gas     | BASE (3 Gwei)  | USD ($600 BASE) |
| ----------------------- | ------- | -------------- | --------------- |
| Create Oracle           | ~200K   | ~0.0006 BASE   | ~$0.36          |
| Query Web2 API          | ~50K    | ~0.00015 BASE  | ~$0.09          |
| Verify Data             | ~45K    | ~0.000135 BASE | ~$0.08          |
| x402 Protocol Payment Settlement | ~180K   | ~0.00054 BASE  | ~$0.32          |
| Batch API Queries       | ~35K ea | ~0.000105 BASE | ~$0.06          |
| AI API Discovery        | ~100K   | ~0.0003 BASE   | ~$0.18          |

**Total Cost:** ~$0.50 to create oracle + query API with x402 protocol

---

## 🔗 Network Information

### BASE Chain Mainnet (Primary Base)

- **Chain ID:** 56
- **RPC:** https://bsc-dataseed.binance.org/
- **Explorer:** https://bscscan.com
- **x402 Oracle Contract:** [`0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3`](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)
- **USDC:** `0x8AC76a51cc950d9822D68b83fE1Ad97B32Cd580d` (Binance-Bridged, EIP-2612)
- **USDT:** `0x55d398326f99059fF775485246999027B3197955` (18 decimals!)
- **Status:** ✅ **Primary Base Chain** - Native x402 Oracle Infrastructure

### BASE Chain Testnet

- **Chain ID:** 97
- **RPC:** https://data-seed-prebsc-1-s1.binance.org:8545/
- **Explorer:** https://testnet.bscscan.com
- **Faucet:** https://testnet.basechain.org/faucet-smart

---

## 📖 Documentation

### Core Concepts

- **[X402_ORACLE_TECHNICAL_SPECIFICATION.md](./X402_ORACLE_TECHNICAL_SPECIFICATION.md)** - Complete architecture and design
- **[V5_PERMISSIONLESS_ORACLE_COMPLETE.md](./V5_PERMISSIONLESS_ORACLE_COMPLETE.md)** - How the permissionless oracle works
- **[USDC_USDT_BASE_CHAIN_IMPLEMENTATION.md](./USDC_USDT_BASE_CHAIN_IMPLEMENTATION.md)** - s402 payment implementation

### Comparison & Analysis

- **[X402_VS_S402_COMPARISON.md](./X402_VS_S402_COMPARISON.md)** - Why we built s402 instead of using x402
- **[EIP_PAYMENT_STANDARDS_COMPARISON.md](./EIP_PAYMENT_STANDARDS_COMPARISON.md)** - EIP-2612 vs EIP-3009 deep-dive
- **[EIP3009_LOOPHOLE_ANALYSIS.md](./EIP3009_LOOPHOLE_ANALYSIS.md)** - Why "EIP-3009 on BASE" claims are false

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
npx hardhat run scripts/deploy-x402.js --network bscTestnet
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
git clone https://github.com/YOUR_USERNAME/x402-oracle-sdk

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

**Built by ORAQ** - x402 Oracle Infrastructure enhances the **x402 protocol** with robust oracle capabilities.

### vs. Traditional x402 Protocol Implementations

| Feature                  | x402 Oracle Infrastructure (by ORAQ) | Basic x402              | Coinbase x402         |
| ------------------------ | -------------------------- | ----------------------- | --------------------- |
| **Web2 API Integration** | ✅ Any REST API            | ❌ Limited sources      | ❌ Limited sources    |
| **Verification**         | ✅ TLS+SHA256+IPFS         | ❌ No verification      | ❌ Basic verification |
| **AI Discovery**         | ✅ Auto API discovery      | ❌ Manual setup         | ❌ Manual setup       |
| **Multi-Source**         | ✅ Consensus mechanism     | ❌ Single source        | ❌ Single source      |
| **BASE Chain**           | ✅ Native support          | ❌ Not supported        | ❌ Base only          |
| **Robustness**           | ✅ Redundant & verified    | ❌ Single point failure | ⚠️ Limited redundancy |

### vs. Traditional Oracles (Chainlink, UMA)

| Feature              | x402 Oracle Infrastructure (by ORAQ) | Chainlink            | UMA             |
| -------------------- | -------------------------- | -------------------- | --------------- |
| **x402 Protocol Payments**    | ✅ Native HTTP 402         | ❌ LINK tokens       | ❌ UMA bonds    |
| **Web2 Integration** | ✅ Direct API access       | ⚠️ Node operators    | ⚠️ Limited      |
| **Permissionless**   | ✅ Anyone can add APIs     | ❌ Whitelisted nodes | ⚠️ Token voting |
| **AI-Powered**       | ✅ Auto discovery          | ❌ Manual            | ❌ Manual       |
| **Micropayments**    | ✅ $0.01-0.15              | ❌ High costs        | ❌ High costs   |
| **BASE Chain**       | ✅ Native support          | ✅ Supported         | ⚠️ Limited      |

---

## 💬 Support & Community

- **Website:** [x402-oracle.xyz](https://x402-oracle.xyz)
- **𝕏 Twitter:** [@x402Oracle](https://x.com/x402Oracle)
- **Email:** x402oracle@proton.me
- **GitHub Issues:** [Report bugs & request features](https://github.com/x402-oracle/x402-oracle-sdk/issues)
- **Contract:** [View on BSCScan](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)

---

<div align="center">

**x402 Oracle Infrastructure v5.0** - Built by **ORAQ** 🚀

Making the **x402 protocol** robust through Web2 API integration

✅ Web2 API Integration | ✅ x402 Protocol Micropayments | ✅ Cryptographic Verification | ✅ BASE Chain | ✅ Mainnet Live

**ORAQ** is building the missing piece that makes the x402 protocol truly robust with verified, real-time data feeds.

Transforming Web2 APIs into reliable oracles for the decentralized web 🌐

**[Get Started →](./QUICK_START.md)** • **[View Contract →](https://bscscan.com/address/0x605c5c8d83152bd98ecAc9B77a845349DA3c48a3)** • **[Follow on 𝕏 →](https://x.com/x402Oracle)**

</div>
