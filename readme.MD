

# 🚀 Bitz Miner Setup (For Users With Existing Solana Wallet)

This guide is for users who already have a **Solana wallet** (e.g. Backpack, Phantom, Solflare) and want to import it into the terminal instead of creating a new one.

---

## ✅ Prerequisites

- A **Solana wallet** (you must have your seed phrase or private key)
- **Linux Ubuntu Terminal**
- A **VPS or Local Machine** with minimal CPU  
  👉 Recommended VPS Provider: [Buy from Contabo](https://www.tkqlhce.com/5k117cy63y5LNMNPTTSSSLNRMOOPST?sid=medium)
- Your wallet must be **funded with ETH on the Eclipse Network**

---

## ⚙️ Step 1: Install Dependencies

```bash
sudo apt-get update && sudo apt-get upgrade -y
sudo apt install screen curl nano -y
```

---

## 🦀 Step 2: Install Rust

```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```

- When prompted, type `1` and press Enter
- After installation:
```bash
source $HOME/.cargo/env
```

---

## ☀️ Step 3: Install Solana CLI

```bash
curl --proto '=https' --tlsv1.2 -sSfL https://solana-install.solana.workers.dev | bash
```

- Close and reopen your terminal, then check:
```bash
solana --version
```

If it says `command not found`, run:

```bash
echo 'export PATH="/root/.local/share/solana/install/active_release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
solana --version
```

---

## 🔗 Step 4: Switch to Eclipse RPC

```bash
solana config set --url https://eclipse.helius-rpc.com/
```

---

## 🔑 Step 5: Import Your Existing Wallet

### Option A: Import Using Seed Phrase

```bash
solana-keygen recover
```

- Choose option `0` (prompt for seed phrase)
- Enter your **seed phrase**
- Press Enter to save to default path (`~/.config/solana/id.json`)

---

### Option B: Import Using Private Key JSON File

1. Move your private key JSON to Solana CLI folder:
```bash
mv your_id.json ~/.config/solana/id.json
```

2. Or configure Solana to use it directly:
```bash
solana config set --keypair /full/path/to/your_id.json
```

✅ Confirm with:
```bash
solana config get
```

---

## 🧪 Step 6: Fund Your Wallet

Fund your imported wallet with **ETH on the Eclipse Network**.  
To check your address:
```bash
solana address
```

---

## ⛏️ Step 7: Install and Run Bitz Miner

### Install Bitz:
```bash
cargo install bitz
```

### Run Bitz in a screen session:
```bash
screen -S bitz
bitz collect
```

👉 Default uses 1 core. To use more cores:
```bash
bitz collect --cores 4   # Replace 4 with your desired core count
```

---

## 🧰 Useful Screen Commands

- Minimize screen: `Ctrl + A + D`
- Return to screen: `screen -r bitz`
- Stop node: `Ctrl + C`
- List screens: `screen -ls`
- Kill screen: `screen -XS bitz quit`

---

## 💰 Wallet Commands

These should be run **outside** the screen session:

- Check your mining account:
```bash
bitz account
```

- Claim mining rewards:
```bash
bitz claim
```

- View all Bitz commands:
```bash
bitz -h
```

---

## 🖥️ Need a VPS?

Use Contabo for a reliable and affordable VPS:  
👉 [Buy from Contabo using this link](https://www.tkqlhce.com/5k117cy63y5LNMNPTTSSSLNRMOOPST?sid=medium)

---
```

---
