# Aletheia Solana Monorepo

> **Trustless, Privacy-Preserving Reputation Bridge from Ethereum to Solana**

This monorepo contains all components of the Aletheia system as git submodules.

## Components

| Component | Description | Repository |
|-----------|-------------|------------|
| **registry** | Solana smart contracts (Anchor) | [Registry](./registry) |
| **light_client** | ZK circuits for Ethereum consensus verification | [LightClient-Noir](./light_client) |
| **aletheia-sync** | User-facing privacy circuits & SDK | [Circuits-Aletheia](./aletheia-sync) |

## Architecture Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                        ALETHEIA SYSTEM                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────────┐    ┌─────────────────┐    ┌────────────┐  │
│  │  light_client   │    │  aletheia-sync  │    │  registry  │  │
│  │  (Trust Anchor) │    │  (Privacy Layer)│    │  (Shield)  │  │
│  └────────┬────────┘    └────────┬────────┘    └─────┬──────┘  │
│           │                      │                   │         │
│           │   Ethereum Data      │   User Proofs     │         │
│           ▼                      ▼                   ▼         │
│  ┌─────────────────────────────────────────────────────────┐   │
│  │                    Solana Blockchain                    │   │
│  │  PrimaryRegistry │ SatelliteRegistry │ ReputationPassport  │
│  └─────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

## Quick Start

### Clone with Submodules
```bash
git clone --recurse-submodules https://github.com/Aletheia-Sync/Solana-Monorepo.git
cd Solana-Monorepo
```

### Update Submodules
```bash
git submodule update --init --recursive
```

## Deployed Contracts (Devnet)

| Program | Address |
|---------|---------|
| Registry | `G6eHn1pbtTvFnBRynwtDHgM7xFdiDAqVZsibd8vs7FBT` |
| Verifier Consensus | `H4QKVpQTFGmN5xVWKHkbaixrNKhYqKudLBk78riqTikZ` |
| Verifier Execution | `Fx2DNegVVHkynHb1Zvjoh4NDFVRVdniu5gqY5L4KvqQe` |
| Verifier Identity | `9TQTyPtY1iVhyttBM3837wUvQ1VdGYAiNgf3e4VF7PvE` |

## Partners & Technology

- **QuickNode**: High-performance Ethereum RPC
- **Sunspot**: Noir ZK proof orchestration
- **Noir**: Zero-knowledge circuit language
- **Anchor**: Solana smart contract framework

## License

MIT
