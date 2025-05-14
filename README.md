
A decentralized, blockchain-powered supply chain management system that ensures end-to-end transparency, traceability, and security from manufacturer to end customer.
----------------------------------------------------------------------------------------------------------------------------------------------------------------------

---

## 📖 Overview

Traditional supply chain systems suffer from fragmentation, lack of transparency, and vulnerability to fraud, leading to inefficiencies and loss of trust. It leverages blockchain technology to create a decentralized supply chain management platform that:

* Records every transaction in a tamper-proof, transparent ledger.
* Provides real-time product provenance and ownership history.
* Integrates multimedia assets (images & videos) via IPFS and Livepeer for rich traceability.
* Protects against counterfeiting using non-duplicable "Secure QR" codes.

By tokenizing products as NFTs on Polygon, stakeholders can seamlessly transfer ownership, view event history, and authenticate authenticity with a simple QR code scan.

---

![Supplychain1](/images/supply3.png)
## ✨ Features

* **Product Minting**: Manufacturers register products (title, description, images, videos) and mint an NFT with embedded metadata.
* **Live Video Tracking**: Upload and stream supply chain videos using Livepeer, with metadata stored on IPFS.
* **Transparent Transfers**: Ownership transfers recorded on-chain; each scan of the product’s QR code displays current and past owner data.
* **Secure QR Codes**: Prevent fraud with non-reproducible QR codes that lose data on reprinting.
* **Decentralized Auth**: Social login (Arcana + RainbowKit), email auth, and Polygon ID for secure interactions.
* **Scalable Backend**: Node.js + Express API with MongoDB (via Mongoose) for off-chain data storage and indexing.

---

## 🏗 Architecture

```
[Manufacturer] --> [Next.js Frontend] --> [Express.js API] --> [MongoDB Atlas]
                                     \                      
                                      \---> [Polygon Smart Contracts]
                                              |              
                                              v              
                                      [IPFS] & [Livepeer]
```

1. **Front-End** (Next.js + Redux Thunk + RainbowKit + Arcana)
2. **Back-End** (Node.js + Express + Mongoose)
3. **Blockchain Layer** (NFT & Product Registry on Polygon Mumbai)
4. **Storage & Media** (IPFS for metadata; Livepeer for video streaming)

---

## 🛠 Tech Stack

| Layer          | Technology                                   |
| -------------- | -------------------------------------------- |
| Frontend       | Next.js, React, Redux Thunk                  |
| Styling        | Tailwind CSS                                 |
| Backend        | Node.js, Express, Mongoose                   |
| Database       | MongoDB Atlas                                |
| Authentication | Arcana, RainbowKit, Polygon ID               |
| Blockchain     | Solidity, Hardhat, Ethers.js, Polygon Mumbai |
| Storage        | IPFS (metadata), Livepeer (videos)           |
| Deployment     | Vercel (Frontend), Render.com (Backend)      |

---

## 🔧 Prerequisites

* Node.js (v16+)
* npm (v8+)
* MetaMask (or any EVM wallet) connected to Polygon Mumbai
* [Livepeer account](https://livepeer.org)
* [Arcana account](https://arcana.network)

---
![Supplychain2](/images/supply2.png)
## 💻 Installation

### Frontend

1. Clone the repo:

   ```bash
   https://github.com/nikhlu07/Supply-chain.git
   cd Supply-chain/frontend
   ```
2. Install dependencies:

   ```bash
   npm install
   ```
3. Copy environment template and fill in values:

   ```bash
   cp .env.example .env.local
   ```
4. Start development server:

   ```bash
   npm run dev
   ```

### Backend

1. Navigate to server directory:

   ```bash
   cd ../server
   ```
2. Install dependencies:

   ```bash
   npm install
   ```
3. Copy environment template:

   ```bash
   cp .env.example .env
   ```
4. Start server:

   ```bash
   npm run dev
   ```

---

## ⚙️ Configuration

Ensure the following environment variables are set in **both** frontend (`.env.local`) and backend (`.env`):

| Variable              | Description                                                      |
| --------------------- | ---------------------------------------------------------------- |
| `NEXT_PUBLIC_API_URL` | Base URL of backend API (e.g., `https://ethforall.onrender.com`) |
| `MONGODB_URI`         | MongoDB connection string                                        |
| `PRIVATE_KEY`         | Deployer wallet private key for Hardhat                          |
| `RPC_URL`             | Polygon Mumbai RPC endpoint                                      |
| `LIVEPEER_API_KEY`    | Livepeer API key for video uploads                               |
| `ARCANA_APP_ID`       | Arcana application ID for auth                                   |

---

## 🚀 Usage

1. **Mint a Product**: In the frontend, navigate to **Mint Product**, enter details, upload images/videos, and click **Mint**.
2. **Print & Attach QR**: Download the Secure QR code, print, and attach to the physical product.
3. **Transfer Ownership**: Scan the QR code, confirm transfer in your wallet, and enter the new owner’s address.
4. **View History**: Any stakeholder scans the QR to see full provenance, media, and current owner.

---

![Supplychain3](/images/supply1.png)
## 📝 Smart Contract Addresses

* **NFT Contract**: [0xf3E09b01F9678A1562b184Bb4512E163A387B4Cd](https://mumbai.polygonscan.com/address/0xf3E09b01F9678A1562b184Bb4512E163A387B4Cd#code)
* **Product Registry**: [0x573e31dF36aCb997aAC134d26Ba69d8C09b6C995](https://mumbai.polygonscan.com/address/0x573e31dF36aCb997aAC134d26Ba69d8C09b6C995#code)

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository.
2. Create a feature branch: `git checkout -b feature/YourFeature`.
3. Commit your changes: `git commit -m "Add YourFeature"`.
4. Push to the branch: `git push origin feature/YourFeature`.
5. Open a pull request.

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Happy tracing! 🌐🔗🛡
