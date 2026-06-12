cat > README.md <<'EOF'
# CustodyChain: Decentralized Logistics Escrow Protocol

A decentralized accountability suite designed to solve real-world logistics and supply chain disputes. Built from over a decade of direct operational experience in high-volume logistics (FedEx, Amazon), this protocol eliminates false claims and ensures deterministic dispute resolution using cryptographic delivery proofs and collateral-based incentives.

## Architecture & Design Patterns

CustodyChain consolidates patterns developed across a three-contract suite, bringing together separate infrastructural concepts into a single orchestration layer:

* **SpawnLedger:** Established the deadline enforcement and automatic state resolution patterns reused here to manage deterministic queue movements.
* **MultisigVault:** Established the threshold consensus model that informs the multi-party arbitration system during escrow deadlocks.

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
EOF

---

### Guardar los cambios en GitHub

Ahora que el archivo local está actualizado, ejecuta el ciclo de Git para subirlo a la nube. Como hace un momento tuvimos el problema del `rejected` debido al historial desalineado, esta vez usaremos la bandera `--force` para asegurarnos de que tu Mac mande la versión definitiva y limpie cualquier conflicto que haya quedado con los bots de GitHub:

```bash
git add README.md
git commit -m "docs: refine README architecture description for technical accuracy"
git push origin main --force
