# DegenToken Smart Contract

## Overview

The `DegenToken` contract is an ERC20 token integrated with a simple in-game item redemption system. Players can mint tokens, transfer tokens, burn tokens, and redeem tokens for in-game items. The contract is designed to work within a gaming ecosystem, where tokens serve as the currency for acquiring various game items. The system supports a list of pre-defined game items with different costs and allows players to redeem tokens for these items.

## Features

- **ERC20 Token**: Implements the ERC20 standard for fungible tokens.
- **Minting**: Only the contract owner can mint new tokens.
- **Token Transfers**: Players can transfer tokens to other players.
- **Burning**: Players can burn their tokens to reduce their balance.
- **Item Redemption**: Players can redeem their tokens for in-game items.
- **Game Items**: The contract comes with a predefined list of game items with unique IDs, names, and costs.
- **Item Ownership**: Players' redeemed items are tracked and stored privately for each address.

## Contract Details

### Token Name: `Degen`
### Token Symbol: `DGN`
### Decimals: 0 (no fractional tokens)

### Predefined Game Items:
- **Rare Sword**: Cost 15 Degen Tokens
- **Epic Shield**: Cost 30 Degen Tokens
- **Legendary Potion**: Cost 75 Degen Tokens

## Functions

### `mint(address to, uint256 amount)`
- Mints new tokens and assigns them to the `to` address.
- **Access Control**: Only the contract owner can mint new tokens.

### `decimals()`
- Returns the number of decimal places for the token (0 in this case).

### `getBalance()`
- Returns the balance of Degen Tokens for the caller (msg.sender).

### `burnTokens(uint256 amount)`
- Burns a specific amount of tokens from the caller's balance.

### `transferTokens(address recipient, uint256 amount)`
- Transfers a specified amount of tokens to the recipient address.
- Approves the transaction before transferring the tokens.

### `redeem(uint256 itemId)`
- Redeems tokens for a specific in-game item.
- The caller must have enough tokens to cover the cost of the item.

### `getGameItems()`
- Returns an array of all available game items.

### `getOwnedItems()`
- Returns an array of items owned by the caller (msg.sender).

## Events

### `ItemRedeemed(address indexed redeemer, uint256 itemId, string itemName, uint256 itemCost)`
- Emitted when a player successfully redeems tokens for an item.

