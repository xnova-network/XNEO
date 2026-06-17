# XNEO Wallet — User Documentation

**Version 1.0.0 · Self-Custodial · Open Source**

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Getting Started](#2-getting-started)
   - [Creating a New Wallet](#21-creating-a-new-wallet)
   - [Importing an Existing Wallet](#22-importing-an-existing-wallet)
3. [Unlocking Your Wallet](#3-unlocking-your-wallet)
4. [Dashboard](#4-dashboard)
5. [Portfolio](#5-portfolio)
6. [Sending Tokens](#6-sending-tokens)
7. [Swapping Tokens](#7-swapping-tokens)
8. [NFTs](#8-nfts)
9. [Transaction History](#9-transaction-history)
10. [Settings](#10-settings)
    - [Network Management](#101-network-management)
    - [Auto-Lock Timer](#102-auto-lock-timer)
    - [Viewing Your Seed Phrase](#103-viewing-your-seed-phrase)
    - [Resetting Your Wallet](#104-resetting-your-wallet)
11. [Security Model](#11-security-model)
12. [Supported Networks](#12-supported-networks)
13. [Frequently Asked Questions](#13-frequently-asked-questions)
14. [Glossary](#14-glossary)

---

## 1. Introduction

XNEO Wallet is a **self-custodial** Web3 wallet. This means:

- **You own your keys.** XNEO never has access to your private key or seed phrase.
- **You are responsible for your backup.** If you lose your seed phrase and forget your password, your funds cannot be recovered by anyone.
- **No account, no sign-up.** Your wallet lives entirely on your device.

XNEO supports EVM-compatible blockchains (Ethereum, BNB Smart Chain, Polygon, and more) and can be installed as a Progressive Web App (PWA) on any device.

> **Before you begin:** Write down your seed phrase on paper and store it somewhere safe. This is the only way to recover your wallet.

---

## 2. Getting Started

### 2.1 Creating a New Wallet

1. Open XNEO Wallet and tap **Create New Wallet** on the welcome screen.
2. You will be shown a **12-word seed phrase**. This is your wallet's master backup.
   - Write every word down in order on paper.
   - Never take a screenshot or store it in a notes app.
   - The clipboard is automatically cleared 30 seconds after you tap **Copy to Clipboard** — a countdown timer will remind you.
3. Tap **I Saved My Seed Phrase** to continue.
4. Set a **password**:
   - Minimum 8 characters.
   - The strength meter guides you — aim for **Good** or **Strong**.
   - A strong password includes uppercase letters, numbers, and symbols.
5. Confirm your password and tap **Create & Encrypt**.

Your private key is immediately encrypted with AES-256-GCM and stored locally. It never leaves your device.

---

### 2.2 Importing an Existing Wallet

Use this if you already have a wallet from another app (MetaMask, Trust Wallet, etc.) and want to access it in XNEO.

1. Tap **Import Existing Wallet** on the welcome screen.
2. Enter your **12 or 24-word seed phrase**, with words separated by spaces.
3. Set and confirm a new password for this device.
4. Tap **Import & Encrypt**.

> **Note:** Importing a wallet on a new device does not remove it from the old device. Both devices will have access to the same wallet.

---

## 3. Unlocking Your Wallet

When you return to XNEO after closing the app or after the auto-lock timer expires, you will see the unlock screen.

1. Enter your **password**.
2. Tap **Unlock Wallet**.

**Security features on the unlock screen:**

| Feature | Detail |
|---|---|
| Failed attempt limit | 5 incorrect attempts triggers a **30-minute lockout** |
| Lockout countdown | A live timer shows how long until you can try again |
| Attempts warning | Remaining attempts are shown after the first failure |
| Show/hide password | Tap the eye icon to toggle password visibility |

**Forgot your password?**
Tap **Reset wallet** at the bottom of the unlock screen. This permanently deletes the wallet from this device. You will need your seed phrase to import it again.

**Page refresh behaviour:**
Refreshing the page requires you to enter your password again. This is intentional — it ensures the decryption key is never written to disk. Navigation within the app (between Dashboard, Send, Settings, etc.) does not require re-authentication.

---

## 4. Dashboard

The Dashboard is your home screen after unlocking.

- **Balance overview** — total value of your native token (BNB, ETH, POL, etc.) on the active network.
- **Quick actions** — buttons to Send, Receive, and Swap.
- **Active network badge** — shows which network you are currently on. Tap it in Settings to switch.
- **Token list** — all tokens added to your wallet on the active network.

To receive tokens, tap **Receive** to display your wallet address and QR code.

---

## 5. Portfolio

The Portfolio page shows an aggregated view of all your token balances and their current market values.

- Values are fetched in real time from on-chain data.
- The chart shows your portfolio distribution by asset.
- Tap any token to see its details or navigate to the Send page pre-filled with that token.

---

## 6. Sending Tokens

1. From the Dashboard or Portfolio, tap **Send** (or the send icon next to a token).
2. **Select the token** to send — native coin or any ERC-20 token in your wallet.
3. **Enter the recipient address.** Tap the QR icon to scan a QR code instead of typing.
4. **Enter the amount.** Tap **MAX** to send your entire balance (gas fee is deducted automatically for native tokens).
5. **Choose a gas preset:**

| Preset | Speed | Cost |
|---|---|---|
| 🐢 Slow | ~1–3 min | Lowest |
| ⚡ Standard | ~30 sec | Normal |
| 🚀 Fast | ~10 sec | Higher |
| ✏️ Custom | Manual | You choose |

6. Review the estimated gas fee shown below the preset selector.
7. Tap **Send** and confirm.

After a successful transaction, you will see the transaction hash with a link to the block explorer.

> **Always double-check the recipient address.** Blockchain transactions are irreversible. A single wrong character sends funds to an unrecoverable address.

---

## 7. Swapping Tokens

The Swap page lets you exchange one token for another on the active network using on-chain liquidity.

1. Select the **From** token and enter the amount.
2. Select the **To** token.
3. Review the exchange rate, price impact, and minimum received amount.
4. Tap **Swap** to execute.

> Swaps interact directly with decentralised protocols. XNEO does not take a fee beyond the network gas cost.

---

## 8. NFTs

The NFTs page displays all NFTs (ERC-721 and ERC-1155 tokens) associated with your wallet address on the active network.

- NFTs are fetched automatically.
- Tap any NFT to view its metadata, image, and contract details.
- Use the network selector in Settings to view NFTs on a different chain.

---

## 9. Transaction History

A full log of all transactions sent from this wallet, stored locally on your device.

- Each entry shows: date, type, amount, token, recipient/sender, and status.
- Tap any transaction to open it in the network's block explorer.
- History is stored per-device and is not synced across devices.
- You can clear the history from **Settings → Clear History** (this only removes the local log, not the on-chain record).

---

## 10. Settings

### 10.1 Network Management

XNEO comes pre-configured with the following networks:

| Network | Symbol | Chain ID |
|---|---|---|
| BNB Smart Chain | BNB | 56 |
| Ethereum | ETH | 1 |
| Polygon | POL | 137 |
| Base | ETH | 8453 |
| Arbitrum One | ETH | 42161 |
| Optimism | ETH | 10 |
| Avalanche C-Chain | AVAX | 43114 |
| Linea | ETH | 59144 |
| zkSync Era | ETH | 324 |
| Fantom | FTM | 250 |
| BNB Testnet | tBNB | 97 |

**Adding a custom network:**

1. Tap **Add Network** in Settings.
2. Fill in: Network Name, RPC URL, Chain ID, Symbol, and Explorer URL.
3. Tap **Add Network** — XNEO will contact the RPC and verify that it actually serves the chain ID you entered before saving. If there is a mismatch, the network will not be added.

> Only HTTPS RPC URLs are accepted. HTTP endpoints are rejected to prevent traffic interception.

**Switching networks:**

Tap any network in the list to make it active. All balances, tokens, and NFTs will update to reflect the selected network.

---

### 10.2 Auto-Lock Timer

Controls how long XNEO waits before automatically locking your wallet after inactivity.

| Option | Behaviour |
|---|---|
| 1 minute | Locks after 1 minute of no interaction |
| 5 minutes | Default — recommended for most users |
| 15 minutes | Suitable for desktop use |
| 30 minutes | Lower security — use with caution |
| Never | Disabled — not recommended |

Any mouse movement, key press, tap, or scroll resets the timer. When the wallet locks, you must enter your password to continue.

Your choice is saved locally and persists across sessions.

---

### 10.3 Viewing Your Seed Phrase

If you need to view your seed phrase again (for example, to write it down properly):

1. Go to **Settings → View Seed Phrase**.
2. Enter your **current password** to decrypt and reveal the words.
3. Write them down carefully.
4. Close the modal when done — the words are not stored in any visible form.

> Never enter your seed phrase on any website or share it with anyone. XNEO support will never ask for it.

---

### 10.4 Resetting Your Wallet

Resetting permanently removes all wallet data from this device — your encrypted private key, tokens, NFT cache, and transaction history.

1. Go to **Settings → Reset Wallet**, or tap **Forgot password? Reset wallet** on the unlock screen.
2. Read the warning carefully.
3. Type **RESET** in the confirmation field.
4. Tap **Delete Wallet**.

This action cannot be undone. You can only recover your wallet afterwards by importing your seed phrase.

---

## 11. Security Model

Understanding how XNEO protects your funds:

### Encryption

| What | How |
|---|---|
| Private key at rest | AES-256-GCM, key derived from your password via PBKDF2 (600,000 iterations, SHA-256, random salt) |
| Seed phrase at rest | AES-256-GCM with a separate salt and IV, same password |
| Private key in session | AES-256-GCM with a non-exportable in-memory key — never written to disk |

### Session Security

- After unlocking, your private key is re-encrypted with a temporary key that exists only in memory (JavaScript module scope).
- This temporary key is **non-extractable** — it cannot be read from the browser by any script.
- Navigating between pages does not require re-authentication.
- A page refresh destroys the in-memory key, requiring your password again.
- Closing the browser tab clears all session data immediately.

### Brute Force Protection

- 5 incorrect password attempts trigger a 30-minute lockout.
- A live countdown is shown during the lockout period.
- The auto-lock timer closes the session after inactivity, reducing the window for physical access attacks.

### Network Security

- All RPC endpoints must use HTTPS.
- When adding a custom network, XNEO verifies the chain ID on the RPC before saving — this detects misconfigured or malicious endpoints.

### What XNEO Cannot Protect Against

- A compromised device (malware, keyloggers, or malicious browser extensions with full page access).
- Physical access to an unlocked device.
- A weak password that can be guessed offline if the encrypted data is extracted.
- User error — sending to a wrong address, sharing a seed phrase, or installing a fake version of XNEO.

For maximum security, use a strong unique password and consider a hardware wallet for large holdings.

---

## 12. Supported Networks

XNEO works with any **EVM-compatible** blockchain. The pre-configured networks are listed in [Section 10.1](#101-network-management). You can add any additional EVM network by providing its RPC URL and chain ID.

**Not supported:**
- Bitcoin (BTC)
- Solana (SOL)
- Non-EVM Layer 1 chains

---

## 13. Frequently Asked Questions

**Q: Does XNEO store my seed phrase on a server?**
No. Your seed phrase is encrypted on your device and never transmitted anywhere. XNEO has no backend that handles keys.

**Q: What happens if I clear my browser data?**
Your encrypted wallet data is stored in `localStorage`. Clearing browser data will delete it. Always keep your seed phrase backed up before clearing browser storage.

**Q: Can I use the same wallet on multiple devices?**
Yes — import your wallet on each device using your seed phrase and set a password on each device independently.

**Q: Why does the app ask for my password after a refresh?**
This is a deliberate security feature. The decryption key is kept only in memory and is never written to disk. A page refresh clears it, requiring re-authentication. Navigation within the app does not.

**Q: Is my transaction history private?**
The local history log is private to your device. However, all blockchain transactions are permanently public on-chain and visible to anyone with your address.

**Q: What is the difference between my password and my seed phrase?**
Your **password** encrypts your wallet on this device — it protects the local file. Your **seed phrase** is the master key to your wallet on any device. If you change devices, you use the seed phrase (not the password) to recover your wallet.

**Q: Can I have multiple wallets in XNEO?**
The current version supports one wallet at a time. To switch wallets, reset the app and import a different seed phrase.

**Q: What happens if I forget my password?**
There is no password recovery. Reset the wallet and re-import using your seed phrase. This is why backing up your seed phrase is critical.

---

## 14. Glossary

| Term | Definition |
|---|---|
| **Seed phrase** | 12 or 24 words that represent your wallet's master key. Anyone with these words controls your funds. |
| **Private key** | A cryptographic key derived from your seed phrase. Used to sign transactions. Never share it. |
| **Public address** | Your wallet's public identifier (starts with `0x`). Safe to share for receiving funds. |
| **Gas fee** | A fee paid to the network to process your transaction. Paid in the network's native token (BNB, ETH, etc.). |
| **EVM** | Ethereum Virtual Machine — the standard that allows a wallet to work across Ethereum, BNB Chain, Polygon, and other compatible chains. |
| **Self-custodial** | You hold your own keys. No third party (including XNEO) can access or freeze your funds. |
| **AES-256-GCM** | A strong encryption standard used to protect your private key at rest. |
| **PBKDF2** | A key derivation function that makes brute-force password attacks computationally expensive. |
| **RPC** | Remote Procedure Call — the connection point to a blockchain node that XNEO uses to read balances and send transactions. |
| **Chain ID** | A unique number that identifies a specific blockchain network (e.g., Ethereum = 1, BNB Smart Chain = 56). |
| **Block explorer** | A website (e.g., BscScan, Etherscan) where you can look up any transaction, address, or block on a public blockchain. |
| **PWA** | Progressive Web App — XNEO can be installed on your home screen and used like a native app, without going through an app store. |

---

*XNEO Wallet v1.0.0 · Self-Custodial · Open Source*
*For support and updates: [t.me/xnovatokn](https://t.me/xnovatokn) · [x.com/xnovatoken](https://x.com/xnovatoken) · [xnova.network](https://xnova.network)*
