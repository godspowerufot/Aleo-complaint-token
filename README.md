# Aleo Workshop Compliant Token

The **Aleo Workshop Compliant Token** is a smart contract built on the **Aleo blockchain** to ensure that token transfers adhere to regulatory and security standards. The contract integrates **KYC (Know Your Customer) verification, spending limits, jurisdictional restrictions**, and other compliance mechanisms.

## Deployment Information

- **Deployment ID:** at12z9t268fe0usptrc49x7gwqz7nw2d5ymxmgsd3ftf48rj4tnr5zsvc65yx
- **Deployment URL:** [View on Aleo Testnet](https://testnet.aleo.info/program/complaint_token.aleo)

## Key Features and Functionalities

### 1. Token Registration & Minting
- The token is **registered** with the Aleo Token Registry to ensure compliance.
- The contract **mints a fixed supply of tokens**, which can only be done **once** by an admin account.

### 2. KYC & Compliance Mechanisms
- **KYC Approval:** The admin can **approve users** by adding them to the **KYC whitelist**.
- **Blacklisting:** The admin can **revoke a user's KYC approval**, preventing them from transacting.
- **Jurisdiction Restrictions:** The admin can **restrict or lift bans** on transactions in specific countries.

### 3. Controlled Token Transfers
Token transfers are only allowed under these conditions:
- **Both sender and recipient** are **KYC-approved**.
- The recipient’s country **is not restricted**.
- Users have a **daily spending limit**, ensuring they do not exceed a maximum transaction threshold in a single day.

### 4. Spend Limit Enforcement
- Each user has a **spend limit record** that tracks their spending **per day (epoch-based)**.
- If a user tries to **exceed their allowed daily spend**, the transaction will be rejected.

### 5. Security and Authorization
- The contract **pre-authorizes** token transfers before execution.
- The **admin has control** over minting, KYC approvals, and jurisdiction restrictions.
- Transactions are finalized using **asynchronous processing (Future)** to improve performance.

##
## Smart Contract Functions

### **1. Initialize Token**
**Command:**
```sh
leo run initialize
```
This function sets up the token when the contract is first deployed. It defines the **token name, symbol, supply, and admin privileges**.

### **2. Mint Private Tokens**
**Command:**
```sh
leo run mint_private
```
Only the **admin** can call this function to mint new tokens privately while following compliance rules.

### **3. Transfer Private Tokens**
**Command:**
```sh
leo run transfer_private
```
Allows users to **send tokens privately** under **compliance conditions**:
- The recipient **must be KYC-approved**.
- The recipient’s **country must not be restricted**.
- The sender **must not exceed their daily spending limit**.

### **4. Set Timelock**
**Command:**
```sh
leo run set_timelock
```
Locks a user’s tokens for a **specific period**, preventing them from transferring the tokens before the lock period expires. This can be used for enforcing **holding periods** or preventing early withdrawals.

## Use Case Scenarios

### **1. Regulated Financial Applications**
- Ensures that **only verified users** can trade or transfer tokens.
- Prevents unauthorized access to digital assets.

### **2. Cross-Border Transactions**
- Blocks transactions **to restricted jurisdictions**.
- Enforces **global compliance laws** for financial transactions.

### **3. Corporate Token Management**
- Allows companies to enforce **spending limits** for employees or clients.
- Ensures that transactions remain within **company policies**.

### **4. Secure Private Transfers**
- Ensures **token privacy** while **complying with regulatory requirements**.
- Allows private transfers while enforcing **KYC, jurisdictional, and spending limit rules**.

### 🛑 Freeze User's Assets

#### **Purpose**
The admin can **temporarily freeze** a user's tokens, preventing them from making transactions.

#### **How It Works**
1. The **admin sets a freeze status** for a user.
2. If a user is **frozen**, they **cannot send tokens** until the freeze is lifted.
3. The **admin can later unfreeze** the user, restoring their ability to transact.

#### **Commands**

- **Freeze a User’s Assets:**
  ```sh
  leo run freeze_user <user_address>

---
![output](https://i.ibb.co/N24n1ZR5/deployment-two.png)
![output](https://i.ibb.co/Fbnk7WqS/deploymet.png)


## License
This project is licensed under the **MIT License**.

## Author
Developed for the **Aleo Workshop** as a **compliant token contract** to ensure secure and regulatory-compliant token transfers on the **Aleo blockchain**.

