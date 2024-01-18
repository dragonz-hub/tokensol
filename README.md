# Creating a Token on Solana: Rejects (RJCT)

## Introduction
This README provides instructions for creating a new token on the Solana blockchain, named "Rejects" with the ticker "RJCT".

## Prerequisites
- Install [Rust](https://www.rust-lang.org/tools/install)
- Install [Solana CLI tools](https://docs.solana.com/cli/install-solana-cli-tools)

## Step-by-Step Guide

### Step 1: Set Up Solana CLI
Configure the Solana CLI to use the Devnet for testing.

solana config set --url https://api.devnet.solana.com


### Step 2: Generate a Key Pair
Create a new Solana wallet key pair. If you already have one, you can skip this step.

solana-keygen new


### Step 3: Airdrop SOL
Get some SOL for transaction fees in the Devnet environment.

solana airdrop 1


### Step 4: Create the Token
Use the SPL Token program to create your token.

spl-token create-token

*Note: Copy the token address output from this command for later use.*

### Step 5: Create a Token Account
Create an account for your new token using its mint address.

spl-token create-account <Token_Address>

*Replace `<Token_Address>` with the mint address from Step 4.*

### Step 6: Mint Tokens
Mint an initial supply of your token.

spl-token mint <Token_Address> 1000000


### Step 7: Verify Token Creation
Check the token balance in your account to confirm creation.

spl-token accounts
