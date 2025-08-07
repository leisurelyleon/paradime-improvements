<!-- PIP-0001: Genesis Configuration Parameters -->
# PIP-0001: Genesis Configuration Parameters

- **Author**: Joseph Edwards <josephleonedwards@gmail.com>  
- **Status**: Draft  
- **Created**: 2025-08-07  

## Simple Summary
Define and standardize the fields in `genesis.json` that specify `max_supply`, `total_supply`, and `circulating_supply`, and introduce the first on-chain minting schedule parameters.

## Abstract
The genesis configuration lays the foundation for Paradime’s monetary policy. This proposal formalizes the initial supply caps and the mechanism by which future coin releases are governed, ensuring consistency across client implementations and transparent on-chain governance.

## Motivation
- **Clarity**: Clients need an unambiguous schema for the genesis file.  
- **Consistency**: All node implementations must interpret supply parameters identically.  
- **Governance-ready**: Early inclusion of minting schedule parameters (e.g., block number or timestamp-based releases) allows PIP-driven adjustments post-launch.

## Specification
**Genesis JSON Schema**  
   ```jsonc
   {
     "maxSupply": u128,
     "totalSupply": u128,
     "circulatingSupply": u128,
     "mintSchedule": [
       { "block": u64, "amount": u128 },
       …
     ]
   }
