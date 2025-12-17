# CosmicGauge

Built for Base

CosmicGauge is a Base-aligned repository created to observe live network signals, validate RPC consistency, and confirm wallet connectivity using official Coinbase tooling.

The project is intentionally infrastructure-focused and optimized for repeatable Base environment checks.

## Purpose

CosmicGauge helps:
- Verify Base Mainnet and Base Sepolia availability
- Confirm chainId correctness (8453 / 84532)
- Validate wallet onboarding flows via OnchainKit
- Perform simple, deterministic onchain reads
- Cross-check results with Basescan

## Networks

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  
RPC: https://sepolia.base.org  

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  
RPC: https://mainnet.base.org  

## Application Flow

Primary file: app/cosmicGauge.ts

At runtime, the app:
- Initializes an OnchainKitProvider on the selected Base network
- Renders wallet connection UI
- Uses Viem to fetch:
  - RPC-reported chainId
  - latest block number
  - native ETH balance for a provided address
- Exposes Basescan links for manual verification

## Repository Structure

app/  
- cosmicGauge.ts  
  React entry component combining wallet UX with Base RPC reads.

Common companion files:
- package.json
- tsconfig.json
- index.html / main.tsx
- .env 

## Libraries

OnchainKit  
https://github.com/coinbase/onchainkit  

Viem  
EVM client for Base JSON-RPC reads  

## Installation and Usage

Requirements:
- Node.js 18+
- Browser environment with wallet support

Install dependencies using your preferred package manager and run the project with a standard React/Vite or Next.js development server.

Optional environment variables:
- VITE_BASE_RPC_URL
- VITE_BASE_SEPOLIA_RPC_URL

## Author

GitHub: https://github.com/PelayoElygelene

Public contact (email): squabs.grub.08@icloud.com

Public contact (X): https://x.com/komarovelyge

## License

MIT License

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract #1 address:  
0x495850be0f4616474bbefbb836ac88d4cca9fb95 

Deployment and verification:
- https://sepolia.basescan.org/address/0x495850be0f4616474bbefbb836ac88d4cca9fb95 
- https://sepolia.basescan.org/0x495850be0f4616474bbefbb836ac88d4cca9fb95/0#code  

Contract #2 address:  
0x9f8b85beeb92b39c0023c6ef859acd69fe9142ff 

Deployment and verification:
- https://sepolia.basescan.org/address/0x9f8b85beeb92b39c0023c6ef859acd69fe9142ff  
- https://sepolia.basescan.org/0x9f8b85beeb92b39c0023c6ef859acd69fe9142ff/0#code  

Contract #3 address:  
0x33e562280c7d95bf22b5f32fb539cc7c638042c0 

Deployment and verification:
- https://sepolia.basescan.org/address/0x33e562280c7d95bf22b5f32fb539cc7c638042c0 
- https://sepolia.basescan.org/0x33e562280c7d95bf22b5f32fb539cc7c638042c0/0#code 
These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.

