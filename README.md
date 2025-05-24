# HTTToken.eth IPFS Deployment Site

This repository is dedicated to hosting and managing the decentralized frontends for `htttoken.eth` and all of its functional subdomains using IPFS + ENS. Each subdomain represents a different logical or functional part of the HTT Token ecosystem.

> ⚠️ **Security Note:**
> This is a public repository to support transparency and open development. However, only the wallet that owns the ENS domains (e.g., `htttoken.eth`, `wallet.htttoken.eth`) can publish updates via content hash changes. Cloning or copying this repository does not allow others to alter or replace the official website or `.eth.limo` links. All IPFS content updates are controlled by the ENS owner.

## 🌐 Overview
The ENS system requires that each `.eth` domain and its subdomains be linked to their own **separate IPFS uploads**, with unique CIDs. These are then resolved via the `.eth.limo` gateway for user access.

## 📁 Project Structure (Directory = IPFS Upload)
```
htttoken-eth-site/
├── htttoken-eth/              # Main ENS root: htttoken.eth
│   └── index.html
├── wallet.htttoken.eth/       # Wallet interface and HTT balance viewer
│   └── index.html
├── bookinger.htttoken.eth/    # Hotel and tour booking frontend
│   └── index.html
├── admin.htttoken.eth/        # Platform admin interface
│   └── index.html
├── app.htttoken.eth/          # Booking app user dashboard
│   └── index.html
├── api.htttoken.eth/          # Developer / API documentation
│   └── index.html
├── dao.htttoken.eth/          # DAO governance frontend
│   └── index.html
├── assets/                    # Shared image/logo resources
│   └── htt-logo.png
```

Each folder above is:
- Zipped independently
- Uploaded to IPFS (e.g. via [web3.storage](https://web3.storage))
- Then linked to its corresponding ENS subdomain via the content hash

## 🚀 Deployment Steps

### 1. Zip Each Directory
Do **not zip the root repo**. Only zip individual folders like `wallet.htttoken.eth/`, `dao.htttoken.eth/`, etc.

### 2. Upload to IPFS
- Go to: https://web3.storage
- Upload the zipped folder
- Copy the IPFS CID

### 3. Update ENS Record
- Visit https://app.ens.domains
- Navigate to the matching ENS domain/subdomain
- Under **Content**, set the value:
  ```
  ipfs://<your-cid>
  ```
- Confirm via wallet (MetaMask, etc.)

### 4. Visit via ENS Gateway
Once the ENS content hash is set:
- `htttoken.eth` → `https://htttoken.eth.limo`
- `wallet.htttoken.eth` → `https://wallet.htttoken.eth.limo`
- And so on...

## ✏️ Updating Pages
To change a specific subdomain:
1. Edit files in the relevant folder (e.g. `wallet.htttoken.eth/index.html`)
2. Re-zip only that folder
3. Upload to IPFS
4. Update the ENS content hash

## 🧠 Tips
- Use **relative paths** to access shared assets like:
  ```html
  <img src="../assets/htt-logo.png">
  ```
- Do **not nest subdomain folders** inside `htttoken-eth/` or each other
- Each ENS record must have its **own unique CID**

## 🔐 ENS and Control
- Each subdomain (`wallet`, `admin`, etc.) must be created in ENS if not already
- Only the **ENS owner** can set content hashes
- Subdomains are resolved independently through ENS + IPFS

---

Built and maintained for the HTT Token project.

Contact: [support@htttoken.com](mailto:support@htttoken.com)
Website: [https://htttoken.com](https://htttoken.com)
