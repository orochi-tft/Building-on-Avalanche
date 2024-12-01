# DegenToken Smart Contract

## Overview
`DegenToken` is an ERC20-compatible token designed for use in blockchain-based gaming. The contract includes functionalities for minting, transferring, burning tokens, and redeeming tokens for in-game items.

---

## Features

- **ERC20 Token Implementation**:
  - **Name**: `Degen`
  - **Symbol**: `DGN`
  - **Decimals**: `0` (No fractional tokens).
- **Game Mechanics**:
  - Redeem tokens for predefined in-game items.
  - Track owned items for individual users.
- **Admin Capabilities**:
  - The owner can mint new tokens.
- **Token Operations**:
  - Transfer tokens to other addresses.
  - Burn tokens to reduce supply.

---

## Contract Details

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
import "@openzeppelin/contracts/access/Ownable.sol";

contract DegenToken is ERC20, Ownable {
    // Full code in repository.
}
```

# Available Functions
1. Mint Tokens (Owner-only)

Allows the contract owner to mint new tokens.
function mint(address to, uint256 amount) public onlyOwner

2. Transfer Tokens
Enables token transfers between accounts.
function transferTokens(address recipient, uint256 amount) external

4. Burn Tokens
Allows a user to burn their tokens, reducing the total supply.
function burnTokens(uint256 amount) public

4. Redeem Tokens for Game Items
Exchange tokens for in-game items using their itemId.
function redeem(uint256 itemId) external

6. Fetch Owned Items
Retrieve the list of items owned by the caller.
function getOwnedItems() external view returns (GameItem[] memory)

6. Fetch All Available Items
Retrieve the list of all available in-game items.
function getGameItems() external view returns (GameItem[] memory)

In-Game Items
Item ID	Item Name	Cost (DGN)
1	Rare Sword	15
2	Epic Shield	30
3	Legendary Potion	75
Deployment Instructions
Clone the Repository:

git clone https://github.com/orochi-tft/Building-on-Avalanche.git
cd Building-on-Avalanche

# Compile the Contract:

Use Remix, Hardhat, or Truffle to compile the DegenToken.sol file.
Deploy the Contract: Example using Hardhat:

const DegenToken = await ethers.getContractFactory("DegenToken");
const token = await DegenToken.deploy();
console.log("DegenToken deployed to:", token.address);
Verify Deployment: Ensure the contract is properly deployed to the desired blockchain.

# Usage Example

Mint Tokens
contractInstance.mint("0xRecipientAddress", 100);

Transfer Tokens
contractInstance.transferTokens("0xRecipientAddress", 50);

Burn Tokens
contractInstance.burnTokens(25);

Redeem Tokens for a Game Item
contractInstance.redeem(1); // Redeems "Rare Sword"
Check Owned Items

GameItem[] memory items = contractInstance.getOwnedItems();
Events
ItemRedeemed: Logs when a user redeems a game item.

event ItemRedeemed(
    address indexed redeemer,
    uint256 itemId,
    string itemName,
    uint256 itemCost
);
License
This project is licensed under the MIT License.

// SPDX-License-Identifier: MIT
Contributing
Feel free to fork this repository, submit pull requests, or raise issues for any bugs or feature suggestions.

Contact
For any queries or collaborations, please reach out via GitHub issues or contact the repository owner.

This README ensures that the content is well-organized, professional, and adheres to markdown best practices. You can copy and paste it directly into a `README.md` file in your repository. Let me know if you need help with anything else!
