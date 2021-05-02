---
description: Page collection of all the terms used in this project.
---

# Terms and Glossary

**Smart Contract**

The core of how functionality is provided on the blockchain \(Ethereum and BSC\). These are programed contracts that provide functions and features for a project. Normally smart contracts are written in a language called Solidity.

It is important to note that once a smart contract is deployed to the block chain, the core functions of that smart contract cannot be changed. Sure there are functions on the contract that can be called to make changes to parameters on the smart contract but nobody can actually change how the function fundamentally works or operates.

This raises two points. New features and functions cannot be added to smart contracts without deploying a new version. Which in turn means that if there is any vulnerability in a smart contract, you cannot just "fix" it in the smart contract. It is important to understand this.

**Token Contract**

This is the contract that represents a token itself. It s the token contract that can create new "coins". Token contracts have a function called MINT, which can be called to create new tokens and also controls the total supply as well as the burn address associated to a token

**Timelock**

Contract used to ensure that all transactions and changes to be made on the masterchef are executed after the preset time agreed by the community. In this case we agree to 8 hours, and set queue transactions to 8 hours in the future. This can be checked on the timelock contract function and checking the epochTime listed and converting that back to your local time

**Masterchef Contract**

This is the main contract that handles all the tokens, minting, pools, allocations etc. The masterchef is owned by a timelock. All functions that are marked as owner only are only allowed to be executed by the timelock

**QueueTransaction**

This is a function that is used on the timelock to queue a transaction. It’s a place holder that tells the Timelock that someone is looking to execute a transaction at some stage in the future \(shown by the epochtime on the function\)

**ExecuteTransaction**

This is the function that is run to actually make the changes to the masterchef. This function can only be run by the timelock and the function will only work if it finds an underlying QueueTransaction with the same parameters marked. IE it can only execute a QueueTransaction that has already been queued where the allocated time has passed.

**ALLOCPOINT**

This is essentially the multiplier for each pool/lp on the masterchef. Solidity \(the programing language used for BSC\) has a weird way of showing numbers, but in essence you need to divide this number by 100 to get the multiplier. If you see an ALLOC of 1000 that would mean a 10X multiplier

**Multiplier**

Multiplier is the ratio number used on the pools/lps to decide how much of the share of minted tokens that specific pool gets. To get the full amount of the ratios on a masterchef you need to add all the allocPoints for each pool/lp together and compare that to the "totalAlloc" value on the masterchef. Each pool is in a proportionate ratio of the total Alloc Points

**Pools**

Pools are single tokens added to a masterchef. This is when you want to stake a single token, instead of a LP pair. Eg, you can stake MIST by itself in a pool. On the alchemist Website this is the "Spells" section for MIST.

**LP's**

LP's are Liquidity Pairs, they constitute 2 tokens mixed into a pair to provide liquidity to the market. A pair has its own contract and can be added to a masterchef to earn rewards

**Emissions**

This is the total amount of new tokens being minted per block. This can be checked on the project info page and also on the masterchef contract as well.

**EPochTime**

Time represented in unix time.

**V1**

This is a term used to explain the version of something. Most commonly used to explain the version of the pools being used.

In can also mean the version of the masterchef contract deployed

