
# BlockVote — Blockchain-Based Online Voting System

> A capstone project from the Blockchain Developer Course demonstrating core blockchain concepts through a functional voting application — with real SHA-256 hashing, real ECDSA key pairs, and real proof-of-work mining running entirely in the browser.

**Live Demo →** `https://YOUR-USERNAME.github.io/blockvote`

---

## What This Project Is

BlockVote is an online voting system that applies blockchain principles to solve a real problem: how do you run an election where every vote is transparent, tamper-proof, and verifiable — without trusting any single authority?

The project implements a working blockchain in the browser using the **Web Crypto API** — real SHA-256 hashing, real ECDSA digital signatures, and real proof-of-work mining. Every block hash you see in the explorer is a genuine cryptographic output, not a simulation.

---

## Blockchain Concepts Demonstrated

| Concept | Implementation | Status |
|---|---|---|
| Block structure | Each vote creates a block with index, timestamp, data, nonce, and hash | ✅ Real |
| Linked hashing | Every block stores the SHA-256 hash of the previous block | ✅ Real SHA-256 |
| Genesis block | Block #0 initialises the chain with election metadata | ✅ Real |
| Proof of Work | Nonce found by real computation — hash must start with `00` | ✅ Real PoW |
| Wallet addresses | Derived from real ECDSA P-256 public key (last 20 bytes) | ✅ Real ECDSA |
| Transaction signing | Each vote signed with voter's real ECDSA private key | ✅ Real signature |
| Immutability | Tamper demo shows SHA-256 chain break in real time | ✅ Real detection |
| Smart contract logic | `castVote()` enforces one-wallet-one-vote | Modelled in JS |
| P2P network | Decentralised node network | Simulated |

---

## Five Tabs Explained

**Dashboard** — live vote distribution with real-time stats as blocks are mined.

**Cast Your Vote** — walks through the full transaction lifecycle: ECDSA sign → broadcast → SHA-256 mine → confirm.

**Blockchain Explorer** — every block shows its real SHA-256 hash, previous hash, nonce, and proof-of-work validation. Each hash genuinely starts with `00`.

**Tamper Demo** — edit any past vote directly. The SHA-256 chain breaks instantly and the Verify button proves it cryptographically. This is the most important demo for understanding immutability.

**Key Concepts** — all course modules explained with live Solidity contract reference.

---

## Project Structure

```
blockvote/
└── index.html      # Complete single-file application — HTML + CSS + JS + real crypto
README.md           # This file
```

No dependencies. No build step. No server. Open `index.html` in any modern browser and it runs.

---

## How to Run Locally

1. Download `index.html`
2. Open it in Chrome, Firefox, or Edge
3. The app generates a real ECDSA key pair and mines the genesis block on load (~2–3 seconds)

---

## Real vs Simulated

| Component | This Project | Real Blockchain (e.g. Ethereum) |
|---|---|---|
| Hashing algorithm | **Real SHA-256** via `crypto.subtle.digest` | SHA-256 / Keccak-256 |
| Key pairs | **Real ECDSA P-256** via `crypto.subtle.generateKey` | ECDSA secp256k1 |
| Transaction signing | **Real ECDSA signature** via `crypto.subtle.sign` | Real ECDSA signature |
| Proof of Work | **Real PoW loop** — nonce found by computation | Real PoW / PoS |
| Wallet address | Derived from public key (last 20 bytes) | Keccak-256 of public key |
| Smart contract | Modelled in JavaScript | Solidity on EVM |
| Network nodes | Single browser tab | Distributed P2P network |
| Persistence | Browser memory (resets on refresh) | Distributed ledger |

---

## Solidity Smart Contract (modelled)

The election rules are modelled on this contract. The next step is deploying this to the Ethereum Sepolia testnet.

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract BlockVote {
    struct Candidate {
        string name;
        uint256 voteCount;
    }

    mapping(address => bool) public hasVoted;
    Candidate[] public candidates;
    uint256 public deadline;

    event VoteCast(address voter, uint256 candidateId);

    function castVote(uint256 candidateId) external {
        require(block.timestamp < deadline, "Voting closed");
        require(!hasVoted[msg.sender], "Already voted");
        require(candidateId < candidates.length, "Invalid candidate");
        hasVoted[msg.sender] = true;
        candidates[candidateId].voteCount++;
        emit VoteCast(msg.sender, candidateId);
    }
}
```

---

## Tech Stack

- **Frontend:** Vanilla HTML, CSS, JavaScript — no frameworks, no libraries
- **Cryptography:** Web Crypto API (`crypto.subtle`) — built into every modern browser
- **Fonts:** Syne + Space Mono via Google Fonts
- **Smart contract:** Solidity (modelled, not yet deployed)
- **Hosting:** GitHub Pages

---

## Course Concepts Covered

- Block and chain data structures
- SHA-256 cryptographic hashing
- Public/private key pairs and ECDSA digital signatures
- Proof of Work consensus and nonce computation
- Wallet address derivation from public keys
- Transaction lifecycle: sign → broadcast → mine → confirm
- Immutability and tamper detection
- Smart contract development in Solidity
- Decentralised network architecture

---

## Roadmap

- [x] Block chain data structure with linked hashes
- [x] Genesis block and vote block creation
- [x] Real SHA-256 hashing via Web Crypto API
- [x] Real ECDSA P-256 key pair generation
- [x] Real ECDSA digital signature on every vote
- [x] Real proof-of-work mining (difficulty = 2)
- [x] Transaction log and block explorer
- [x] Tamper detection demo with live SHA-256 verification
- [ ] Deploy `castVote()` to Ethereum Sepolia testnet
- [ ] Connect frontend with ethers.js and MetaMask
- [ ] Zero-knowledge proof for voter privacy

---

## Author

