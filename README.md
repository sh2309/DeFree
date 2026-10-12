# DeFree — All-in-One Web3 Collaboration Platform

**DeFree** is a unified collaboration platform that brings freelancing, event management, and real-time community communication into one ecosystem. It combines traditional web technologies with blockchain-based payments and NFT ticketing to support collaboration between freelancers, clients, developers, startups, and communities.

<p align="center">
  <a href="https://defree.vercel.app/">
    <img src="https://img.shields.io/badge/Live-Demo-green?style=for-the-badge" alt="Live Demo">
  </a>
  <img src="https://img.shields.io/badge/Blockchain-Ethereum-blue?style=for-the-badge" alt="Ethereum">
  <img src="https://img.shields.io/badge/Smart%20Contracts-Solidity-purple?style=for-the-badge" alt="Solidity">
  <img src="https://img.shields.io/badge/Frontend-React-blue?style=for-the-badge" alt="React">
</p>

<p align="center">
  <a href="https://defree.vercel.app/">Live Demo</a> •
  <a href="#key-features">Features</a> •
  <a href="#technology-stack">Tech Stack</a> •
  <a href="#getting-started">Getting Started</a> •
  <a href="#screenshots">Screenshots</a>
</p>

---

## Table of Contents

* [Overview](#overview)
* [Key Features](#key-features)
* [Technology Stack](#technology-stack)
* [System Architecture](#system-architecture)
* [Getting Started](#getting-started)
* [Usage Workflows](#usage-workflows)
* [Demo and Screenshots](#demo-and-screenshots)
* [Security Considerations](#security-considerations)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Acknowledgements](#acknowledgements)

## Overview

DeFree brings three major capabilities together:

* **Freelancing Marketplace:** Enables clients to post gigs and freelancers to submit proposals, with blockchain-based escrow functionality.
* **Event Management:** Supports event creation, registration, and NFT-based ticketing.
* **Real-Time Community:** Provides communication through public and private channels, direct messages, and media sharing.

The platform combines a React-based frontend, a Node.js backend, MongoDB, Socket.IO, and Ethereum smart contracts to support both on-chain and off-chain interactions.

## Key Features

| Module                  | Features                                                                                  |
| ----------------------- | ----------------------------------------------------------------------------------------- |
| Freelancing Marketplace | Post gigs, browse opportunities, submit proposals, and track proposal status.             |
| Blockchain Payments     | Smart-contract-based escrow workflow for freelance transactions.                          |
| Event Management        | Create events, manage registrations, and issue NFT tickets using ERC-721.                 |
| Community Chat          | Real-time messaging, public and private channels, direct messages, and message history.   |
| Web3 Integration        | MetaMask wallet connectivity and blockchain interactions.                                 |
| User Profiles           | Manage user information and view relevant activity, subject to implemented functionality. |

## Technology Stack

| Layer                   | Technologies                                                      |
| ----------------------- | ----------------------------------------------------------------- |
| Frontend                | React, TypeScript, Tailwind CSS                                   |
| UI and Animations       | Framer Motion                                                     |
| Backend                 | Node.js, Express.js                                               |
| Database                | MongoDB, Mongoose                                                 |
| Real-Time Communication | Socket.IO, WebSockets                                             |
| Smart Contracts         | Solidity, Hardhat                                                 |
| Blockchain Integration  | Ethereum, Ethers.js, MetaMask, Alchemy                            |
| Deployment              | Vercel for the frontend; Render for the backend, where configured |
| Media Storage           | Cloudinary — planned, if not yet integrated                       |

## System Architecture

The platform is organized into frontend, backend, database, real-time communication, and blockchain components.

### Core Components

* **Frontend:** React single-page application built with TypeScript and Tailwind CSS.
* **Backend:** Express REST APIs for application functionality and server-side operations.
* **Database:** MongoDB for application data, including users, events, and related records.
* **Real-Time Layer:** Socket.IO for live messaging and communication.
* **Blockchain Layer:** Solidity smart contracts for escrow transactions and NFT ticketing.
* **Wallet Integration:** MetaMask for wallet connectivity and blockchain transactions.

## Getting Started

Follow these steps to set up the project locally. The commands below assume the repository contains `client`, `server`, and `smart-contracts` directories. Adjust them if your actual folder structure differs.

### Prerequisites

Install the following tools before proceeding:

* Node.js and npm
* Git
* MongoDB or an accessible MongoDB database
* MetaMask browser extension, for wallet-related features
* A compatible Ethereum RPC endpoint, for blockchain functionality

Check your installed versions:

```bash
node --version
npm --version
git --version
```

### 1. Clone the Repository

Replace the placeholder URL with the actual repository URL.

```bash
git clone <YOUR_REPOSITORY_URL>
cd DeFree
```

### 2. Install Dependencies

Install the frontend and backend dependencies:

```bash
cd client
npm install

cd ../server
npm install
```

If the smart contracts are maintained in a separate directory, install their dependencies there as well:

```bash
cd ../smart-contracts
npm install
```

### 3. Configure Environment Variables

Create the necessary `.env` files in the directories expected by the application. Use the project's example environment files as the source of truth.

Typical configuration variables may include:

**Server environment**

```dotenv
PORT=8080
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_strong_jwt_secret
CLIENT_URL=your_frontend_url
SEPOLIA_RPC_URL=your_testnet_rpc_url
NFT_CONTRACT_ADDRESS=your_nft_contract_address
```

**Client environment**

```dotenv
VITE_API_URL=your_backend_url
```

**Smart-contract deployment environment, if required**

```dotenv
SEPOLIA_RPC_URL=your_testnet_rpc_url
PRIVATE_KEY=your_deployment_wallet_private_key
```

Only add variables that are actually used by your code. Configure additional payment-provider or media-storage variables only if those integrations are implemented.

> **Security warning:** Never commit `.env` files, private keys, API secrets, or production credentials to GitHub. Keep local secrets out of notebook outputs, screenshots, and logs. Use a test wallet and testnet funds during development.

### 4. Start the Application

Start the backend in one terminal:

```bash
cd server
npm run dev
```

Start the frontend in a second terminal:

```bash
cd client
npm run dev
```

Run the blockchain event listener, if your project requires it, from the directory containing the listener script:

```bash
npx tsx events/listenMintEvents.ts
```

Confirm the listener's correct path and required environment variables before running this command.

### 5. Deploy Smart Contracts (Optional)

For local development, start a local Hardhat network if your deployment workflow requires one, then deploy the contracts using the project's configured script.

```bash
cd smart-contracts
npx hardhat run scripts/deploy.js --network localhost
```

Ensure the selected network, contract addresses, and RPC configuration match your local environment. Deployment scripts and filenames may differ by project version.

## Usage Workflows

### Freelancing Workflow

1. Connect a wallet using MetaMask.
2. Browse gigs or publish a new gig.
3. Submit a proposal for an opportunity.
4. Use the escrow workflow to deposit funds, where supported.
5. Complete the work and follow the configured payment-release process.

### Event Management Workflow

1. Create an event.
2. Register for an event.
3. Mint or obtain an NFT ticket, where supported.
4. View event information and manage attendee details.

### Community Workflow

1. Join a public or private channel.
2. Send and receive real-time messages.
3. Use direct messaging and media-sharing features where available.

## Demo and Screenshots

### Live Demo

Explore the deployed application:

**[Open DeFree](https://defree.vercel.app/)**

### Demo Video

Watch the project demonstration:

[View Demo Video](https://github.com/user-attachments/assets/cc042158-d2ca-4e0d-b470-fcf282571fea)

### Screenshots

<table>
  <tr>
    <td align="center" width="50%">
      <img src="https://github.com/user-attachments/assets/17a982d2-841d-44e7-b51e-f386fa15aa78" alt="DeFree onboarding page" width="100%">
      <br><strong>Onboarding</strong>
      <br>Wallet connection and authentication
    </td>
    <td align="center" width="50%">
      <img src="https://github.com/user-attachments/assets/29869cd7-7629-4422-9cfe-08ae59e6105e" alt="DeFree dashboard" width="100%">
      <br><strong>Dashboard</strong>
      <br>Access to freelancing, events, and community features
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <img src="https://github.com/user-attachments/assets/92e1a960-4fb3-47e9-bcab-a759449113fc" alt="DeFree freelancing marketplace" width="100%">
      <br><strong>Freelancing Marketplace</strong>
      <br>Gigs, proposals, and escrow workflow
    </td>
    <td align="center" width="50%">
      <img src="https://github.com/user-attachments/assets/017c7fd9-a1f0-4424-9106-baffb9f6cd98" alt="DeFree event management" width="100%">
      <br><strong>Event Management</strong>
      <br>Event creation and NFT ticketing
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <img src="https://github.com/user-attachments/assets/307a22cc-9cee-4713-b786-93fa46c0e959" alt="DeFree community chat" width="100%">
      <br><strong>Community Chat</strong>
      <br>Real-time community communication
    </td>
    <td align="center" width="50%">
      <img src="https://github.com/user-attachments/assets/3272e54a-d922-4751-bb38-bf9b48fceae6" alt="DeFree user profile page" width="100%">
      <br><strong>User Profile</strong>
      <br>User activity and profile information
    </td>
  </tr>
</table>

## Security Considerations

Security is an important consideration for a platform handling user accounts, payments, and blockchain interactions.

The project includes or is designed around the following security measures; verify each against the current implementation before treating it as complete:

* **Authentication:** JWT-based authentication.
* **Input Handling:** Input validation for application requests.
* **API Protection:** Rate limiting and CORS configuration, where implemented.
* **Smart Contracts:** OpenZeppelin-based components where applicable, with testing for contract behavior.
* **Secret Management:** Environment variables for sensitive configuration.
* **Wallet Security:** Private keys should remain outside the frontend and source control.

**Audit status:** An external smart-contract security audit was planned in the original project description. Do not describe the contracts as externally audited unless a completed audit report is available.

## Performance and Reliability

Potential areas for optimization and future improvement include:

* Frontend code splitting and lazy loading.
* Database indexing and query optimization.
* Appropriate caching strategies.
* Efficient blockchain event handling and RPC fallback configuration.
* Smart-contract gas optimization and transaction error handling.

These items should be marked as completed only after they have been implemented and tested.

## Roadmap

### Phase 1 — Core Platform

* [ ] Web3 wallet integration
* [ ] Freelancing marketplace foundation
* [ ] Event management and NFT ticketing foundation
* [ ] Real-time community chat foundation

### Phase 2 — Feature Enhancements

* [ ] User reputation system
* [ ] Advanced search and filtering
* [ ] Expanded administrative analytics
* [ ] Payment-provider integration, such as Stripe or Razorpay, if required

### Phase 3 — Future Expansion

* [ ] AI-powered gig recommendations
* [ ] Progressive Web App (PWA) support
* [ ] Multi-chain support
* [ ] DAO governance

### Phase 4 — Scale and Reliability

* [ ] Additional security testing and independent review
* [ ] Performance and scalability improvements
* [ ] Expanded analytics and monitoring
* [ ] Community governance enhancements

> Update the roadmap to reflect the current state of the code. A feature should not be marked completed solely because it was planned or demonstrated in a mock-up.

## Contributing

Contributions are welcome through bug reports, feature requests, and pull requests.

1. Fork the repository.

2. Create a feature branch:

   ```bash
   git checkout -b feature/your-feature
   ```

3. Commit your changes:

   ```bash
   git commit -m "Add your feature"
   ```

4. Push your branch:

   ```bash
   git push origin feature/your-feature
   ```

5. Open a pull request describing your changes.

Please review the project's contribution guidelines and documentation before contributing.

## License

This project states that it is licensed under the MIT License. See the [LICENSE](LICENSE) file for the full terms.

## Acknowledgements

Thanks to the developers and communities behind the technologies used in this project:

* [OpenZeppelin](https://www.openzeppelin.com/) — smart-contract libraries
* [Ethers.js](https://docs.ethers.org/) — Ethereum interaction library
* [Socket.IO](https://socket.io/) — real-time communication
* [Tailwind CSS](https://tailwindcss.com/) — styling framework
* [Hardhat](https://hardhat.org/) — smart-contract development tools

---

<p align="center">
  <strong>DeFree — Bringing freelancing, events, and communities together through Web3.</strong>
</p>
