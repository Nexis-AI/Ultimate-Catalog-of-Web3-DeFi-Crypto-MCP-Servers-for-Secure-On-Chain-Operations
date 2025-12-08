# Ultimate Catalog of Web3 & DeFi MCP Servers

Welcome to the **Ultimate Catalog of Web3, DeFi, and Crypto MCP Servers**. This repository serves as the central source of truth for safe, verified, and high-performance Model Context Protocol (MCP) servers tailored for on-chain operations.

## 🚀 What is this?

This Registry connects standard AI Agents (using MCP) to the world of Web3. By adding this registry to your MCP-compliant host (like Nex-T1, Claude Desktop, or Docker Desktop), you gain instant access to tools for:

- **DeFi**: Swapping on Uniswap, checking Aave positions.
- **Wallet**: Managing keys via secure enclaves.
- **Analytics**: Querying Dune, Etherscan, and graph nodes.

## 📦 How to Use

### For Users

Configure your MCP Host to consume this registry manifest.

**Manifest URL**:
`https://raw.githubusercontent.com/Nexis-AI/Ultimate-Catalog-of-Web3-DeFi-Crypto-MCP-Servers-for-Secure-On-Chain-Operations/main/registry.json`

### For Developers

To add your own MCP server to this catalog, please see [CONTRIBUTING.md](./CONTRIBUTING.md).

## 🏆 Featured Categories

| Category     | Description                                             |
| ------------ | ------------------------------------------------------- |
| **DeFi**     | DEX aggregators, Lending protocols, Yield farming tools |
| **Wallets**  | EVM, Solana, and Bitcoin wallet management              |
| **Infra**    | Node providers, RPCs, Indexers                          |
| **Security** | Smart contract auditors, Token sniffers                 |

## 🐳 Docker Deployment

We provide **Generic Runners** to containerize any Git-based MCP server instantly.

1.  Navigate to `docker/`.
2.  Edit `docker-compose.yml` to uncomment the servers you want.
3.  Run:
    ```bash
    docker-compose up -d --build
    ```

## 🔐 Secure Wallet Integration (Human-in-the-Loop)

**CRITICAL**: Do NOT use your main wallet's private key in `env` variables for production agents.

### The "Transaction Builder" Pattern

To use these servers with your **In-App Wallet** (e.g., Nexis Wallet, Metamask, Phantom):

1.  **Configure Servers as "Builders"**: Most trading servers (like `jupiter-mcp`) support a mode where they return an **Unsigned Transaction** object instead of executing the trade.
2.  **Handling the Response**:
    - **Agent**: Calls `swap_jupiter(token: "SOL", amount: 1)`.
    - **MCP Server**: Returns `{ "type": "transaction", "data": "<base64_unsigned_tx>", "network": "solana" }`.
    - **Nex-T1 App**: Intercepts this JSON.
    - **UI**: Pops up a "Sign Transaction" modal for the user.
    - **User**: Approves via In-App Wallet.
    - **App**: Broadcasts the signed tx.

This ensures **User Custody** is never compromised. The Agent _intends_, the User _approves_.

## 🛡️ Verification

All servers listed here undergo a basic verification process to ensure they conform to the MCP standard and do not contain malicious defaults. However, **ALWAYS review the code and permissions** of any server you grant access to your wallet.

---

_Maintained by Nexis AI_
