# BNB Passport MCP Toolkit

## ℹ️ Overview

The `@bnbpassport/mcp-toolkit` is a modular framework built around the Model Context Protocol (MCP). MCP standardizes AI agent interactions by providing a structured way to handle identity-related workflows. This toolkit enables AI agents to securely manage decentralized identities (DIDs), verifiable credentials, and trust registries, making it an essential component for AI-driven identity systems. This repository allows developers to configure and deploy an MCP server with the available toolkits.

## Prerequisites

- Node.js 20 or higher
- pnpm 8 or higher
- Basic knowledge of TypeScript and MCP

## 📦 Packages

### @bnbpassport/mcp-toolkit

The `@bnbpassport/mcp-toolkit` package allows you to configure and host an MCP (multi-party computation) server within an environment. It integrates with tools from this repository to provide a customizable infrastructure for managing identity-related operations.

Features:

- Configurable MCP server setup
- Integration with various tools from this repository

#### Usage with Claude Desktop or Cursor

Add the following configuration to your claude_desktop_config.json or .cursor/mcp.json:

##### npx

```json
{
    "mcpServers": {
        "bnbpassport": {
            "command": "npx",
            "args": [
                "-y",
                "@bnbpassport/mcp-toolkit-server"
            ],
            "env": {
                "TOOLS": "credo,<other available tools>",
                ...
            }
        }
    }
}
```

##### docker-compose

Use the `env.example` file and update the appropriate variables.

```json
{
  "mcpServers": {
    "bnbpassport-docker-compose": {
      "command": "docker",
      "args": [
        "compose",
        "-f",
        "/path/to/repo/mcp-toolkit/docker/docker-compose.yml",
        "run",
        "--rm",
        "-p", 
        "3000:3000",
        "--name",
        "faber",
        "-T",
        "mcp-server"
      ]
    }
  }
}
```

### @bnbpassport/mcp-toolkit-credo

The `@bnbpassport/mcp-toolkit-credo` package is one of the toolkits that integrate with @openwalletfoundation/credo-ts, allowing an AI agent to manage DIDs and verifiable credentials. It provides tools for:

- Issuing and revoking credentials
- Schema and credential definition management
- DID-based authentication

#### 🌍 Environment Variables

```bash
TOOLS="credo"
CREDO_PORT="3000"
CREDO_NAME="faber"
CREDO_CHEQD_TESTNET_MNEMONIC="your-mnemonic-phrase"
```

## Development Setup

### 1. Install pnpm

If you don't already have pnpm installed:

```bash
npm install -g pnpm
```

### 2. Clone the repository

```bash
git clone https://github.com/bnbpassport/mcp-toolkit.git
cd mcp-toolkit
```

### 3. Install dependencies

```bash
pnpm install
```

### 4. Build the packages

```bash
pnpm build
```


## 🙋 Find us elsewhere

[![Telegram](https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge\&logo=telegram\&logoColor=white)](https://https://t.me/BNB_Passport) [![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge\&logo=twitter\&logoColor=white)](https://twitter.com/intent/follow?screen\_name=BNBpassport_) 
