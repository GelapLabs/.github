# Gelap

Introducing Gelap, the first confidential RWA Dark Pool and private execution layer built on the Mantle ecosystem. Gelap leverages a hybrid architecture combining Trusted Execution Environments (TEE) for real-time private matching with SP1 zkVM for verifiable correctness. This design allows users to utilize shielded vaults for depositing collateral, execute private swaps with zero MEV, and trade Real-World Assets (RWAs) like T-bills and private credit without exposing their positions or strategies on-chain. Gelap ensures market integrity by eliminating front-running and providing a compliance-ready infrastructure where institutional privacy meets decentralized settlement.broader Polkadot ecosystem.

## Why Built on Mantle?

- **Modular Architecture for Privacy**: Mantle’s modular design provides the high-performance, low-cost data availability required to process heavy cryptographic proofs (SP1 zkVM) and TEE execution traces without checking scalability.

- **Native RWA & Yield Alignment**: Mantle is a hub for yield-bearing assets (mETH) and RWAs (USDY). Gelap is built here to serve as the necessary privacy layer for these assets, allowing them to be traded securely and confidentially.

- **Institutional-Grade Reliability**: Leveraging Mantle’s robust finality and security inherited from Ethereum, Gelap can offer the secure settlement assurances required for high-value institutional trades.

## Why Gelap Matters for Mantle

- **Solving the Institutional Privacy Gap**: Institutions cannot trade RWAs on-chain if their net asset values (NAV) and order flows are visible. Mantle’s RWA-heavy ecosystem is the perfect environment for Gelap’s Dark Pool, which unlocks institutional capital by protecting trade secrecy.

- **Synergy with Native Yield**: Gelap complements Mantle’s economy by allowing users to hold and trade yield-bearing assets (like mETH) within a shielded pool. This ensures users maintain their privacy without forfeiting the native yield that makes Mantle unique.

- **The Zero-MEV Trading Experience**: In an ecosystem focused on efficiency, Gelap offers Mantle users a "Dark Pool" experience where sandwich attacks and MEV are impossible, creating the fairest execution environment on the network.

- **First-Mover Advantage**: As the first verifiable Confidential Dark Pool on Mantle, Gelap establishes itself as critical infrastructure, capturing early liquidity from privacy-conscious whales and institutions entering the ecosystem.

## Problem

#### Why does 50% of wall street trade in the dark, while DeFi forces everyone into the light?

![Bloomberg](bloomberg.png)

1. **The TradFi Standard**
   Wall Street demands privacy. Data shows that >50% of US Equity volume is executed "Off-Exchange" (Dark Pools) to prevent price slippage.

2. **The DeFi Reality**
   DeFi operates on <1% privacy. Every order is visible in the public mempool before it settles.

3. **The Disconnect**
   There is a fundamental mismatch between how institutions trade (privately) and how DeFi works (publicly).

_It makes transparency expensive_

1. **For Retail**
   Retail traders lose billions to MEV bots. When your order is visible, bots front-run and sandwich your trade, forcing you to buy at a higher price.

2. **For Institution**
   Institutions cannot trade RWAs (T-Bills, Private Credit) on-chain. Because a transparent ledger reveals their Net Asset Value (NAV) and trading strategies to competitors instantly.

**Thus, RWAs onchain is not usable if strategies are public**

## Solution

Gelap enable a complete privacy lifecycle that lets you submit invisible orders, match them privately, and settle verifiably on-chain.

1. **Shielded Entry (Submit)**
   Users deposit assets into "Shielded Balances," decoupling their identity from their funds. This ensures your wallet history and transaction context remain completely unlinkable from the start.

2. **Private Execution (Compute)**
   Transaction logic is executed off-chain using **Client-Side ZK Proving**. This ensures that trade intentions, amounts, and recipients are never exposed to the public mempool, effectively neutralizing MEV bots and preserving total privacy before the transaction is even sent.

3. **Verifiable Settlement (Finalize)**
   We utilize **SP1 zkVM** to mathematically prove the validity of the state transition. The protocol settles these proofs on-chain, confirming that the transaction was honest and followed all rules without ever revealing the underlying sensitive data to the public ledger.

## Products

- Private Swap
  - A privacy-first AMM that conceals trade amounts and identities, protecting users from MEV bots and front-running attacks.
- Shielded Vault
  - Private yield-bearing pools where users can deposit assets to earn returns without revealing their total holdings or strategies.
- Confidential RWA
  - A secure framework for tokenizing real-world assets that keeps ownership details and asset values hidden from public view.
- Compliance Ready
  - An opt-in regulatory layer enabling institutions to cryptographically prove compliance to auditors without exposing their full transaction history.

## How Gelap Works

Gelap is built on a set of core privacy modules that work together to deliver confidential DeFi operations on EVM chains.

- Main Interface: Gelap is accessible through its privacy-first dashboard on Mantle, where users can shield assets, execute private swaps, and manage compliance proofs in one unified view.
- Shielded Pool Module: Users deposit ERC-20 tokens into a shared anonymity set (Merkle Tree), effectively decoupling their public identity from their funds and enabling truly private ownership.

- Private Transaction Module: Users can transfer assets and execute swaps internally without generating any on-chain transaction history, ensuring that amounts, senders, and receivers remain completely invisible.

- Client-Side Proving Module: Gelap utilizes SP1 technology to generate zero-knowledge proofs directly on the user's device, ensuring that sensitive data never leaves the local environment while still proving validity to the network.

- Compliance Module: This opt-in layer allows institutions to selectively disclose specific transaction details or proofs of innocence to regulators and auditors, bridging the gap between total privacy and regulatory requirements.

- Verifier & Settlement: The on-chain contract verifies the ZK proofs submitted by users and settles the state changes (nullifying spent notes and creating new ones) without ever learning the private inputs.

## Deployments

### Mantle

|             Contract | Address                                                                                                                         |
| -------------------: | :------------------------------------------------------------------------------------------------------------------------------ |
| GelapShieldedAccount | [0x54EC23CBCE1A9d33F05C4d3d79Ec28Aff3c8ce8D](https://sepolia.mantlescan.xyz/address/0x54EC23CBCE1A9d33F05C4d3d79Ec28Aff3c8ce8D) |
|      MockSP1Verifier | [0x79117dbB5A08B03cD796d06EdeEC6e0f2c554f4B](https://sepolia.mantlescan.xyz/address/0x79117dbB5A08B03cD796d06EdeEC6e0f2c554f4B) |

## Others

- Github repo

  - Front End: [https://github.com/GelapLabs/gelap-privacy](https://github.com/GelapLabs/gelap-privacy)
  - Back End: [https://github.com/GelapLabs/gelap-cryptography](https://github.com/GelapLabs/gelap-cryptography)
  - Smart Contract: [https://github.com/GelapLabs/gelap-contracts](https://github.com/GelapLabs/gelap-contracts)

- X (Twitter): [https://x.com/gelapmantle](https://x.com/gelapmantle)
- Docs: [https://gelaps-mantle.gitbook.io/](https://gelaps-mantle.gitbook.io/)
- Demo Video:
- Pitch Deck: [![Pitch Deck](https://img.shields.io/badge/Pitch%20Deck-View%20on%20Canva-00C4CC?style=for-the-badge&logo=canva&logoColor=white)](https://www.canva.com/design/DAG6zfwMtCU/YRAIpzi0i6A-kuRJ3sWYUw/view?utm_content=DAG6zfwMtCU&utm_campaign=designshare&utm_medium=link2&utm_source=uniquelinks&utlId=h9dda6ec850)

[Gelap Docs](https://gelaps-mantle.gitbook.io/docs)

[Website](https://gelapprivacy.vercel.app/)
