# CustodyChain: Decentralized Logistics Escrow Protocol

An enterprise-grade accountability suite designed to solve real-world logistics and supply chain disputes. Built from over a decade of direct operational experience in high-volume logistics (FedEx, Amazon), this protocol eliminates false claims and ensures deterministic dispute resolution using cryptographic delivery proofs and collateral-based incentives.

## Architecture & Integration

CustodyChain acts as the primary orchestration layer of a three-contract accountability suite. Rather than keeping all logic in a monolithic contract, it integrates two external modules by design:

* **SpawnLedger:** Integrated to manage deterministic queue patterns and state transitions.
* **MultisigVault:** Integrated to handle threshold consensus for decentralized dispute arbitration.

## Technical Highlights

* **Cryptographic Delivery Proofs (EIP-191):** Implemented ECDSA signature verification to validate delivery and custody transfers off-chain before settling state on-chain.
* **Yul IR Memory Optimization:** Configured low-level compiler optimizations (`via_ir`) to restructure EVM memory layout, successfully bypassing "Stack too deep" limitations during complex state orchestration.
* **Chaos Engineering & Testing:** Backed by a strict Foundry test suite covering happy paths, security reverts, temporal manipulation constraints, and deliberate chaos testing.

## Tech Stack

* **Smart Contracts:** Solidity (0.8.34)
* **Framework & Testing:** Foundry (Forge/Cast)
* **Standards:** EIP-191, ECDSA

## Local Development & Testing

This project uses Foundry. Ensure you have it installed before proceeding.

### Build
Note: This project relies on the Yul IR optimizer. Ensure `via_ir = true` is present in your `foundry.toml`.
```bash
forge build
Test
Run the test suite with maximum verbosity to trace the Escrow state transitions:
Bash
forge test -vvv

**Para subir este README a tu GitHub**, solo tienes que ejecutar tu ciclo de envío regular:
```bash
git add README.md
git commit -m "docs: add comprehensive README explaining logistics architecture"
git push
