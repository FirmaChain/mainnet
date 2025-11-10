# FirmaChain v0.5.1 Upgrade Notes (mainnet)
Same as upgrade note, only for proposal link

## Overview

The **v0.5.1 upgrade** focuses on **minor version updates of key modules** to enhance the overall **stability, performance, and security** of the Firmachain network.

This update ensures smoother operation across the ecosystem and strengthens network resilience by incorporating the latest improvements from the Cosmos SDK, IBC-go, Wasmd, and CometBFT modules. These upgrades optimize validator synchronization, consensus efficiency, and cross-chain interoperability.

Additionally, **v0.5.1 serves as a foundational update for the upcoming _Firmachain Validator Advisory Board (FVAB)_**, establishing a stable and secure technical environment for its launch and future operations.

With this release, Firmachain continues to advance toward building a **trusted, high-performance blockchain network** that supports both ecosystem growth and long-term governance stability.

Once this proposal passes, the FIRMACHAIN network will be upgraded at block height `20,672,000`(Colosseum).

## Changes

**Upgrade chain binary**
- Chain binary : v0.5.0 -> v0.5.1

**Upgrade module**
- **cosmos-sdk (Cosmos SDK)** : v0.50.12 -> v0.50.14
- **IBC-go (IBC)** : v8.6.1 -> v8.7.0
- **wasmd (CosmWasm)** : v0.54.0 -> v0.54.3
- **CometBFT (Consensus)** : v0.38.17 -> v0.38.18

**Requirements**
- Go : v1.21 or newer (same as Firmachain v0.5.0)

**Ecosystem Requirements**
- **firma-js** : v0.3.8 or newer


## Tests

Comprehensive end-to-end (E2E) testing was completed in both the devnet and testnet environments, verifying the upgrade’s stability.


## Timeline

The upgrade will be executed on the block height `20,672,000`(Colosseum),
with an estimated date and time of **November 18th, 2025, at 05:00 UTC**, based on an average block generation interval of `5.88` seconds.

Upgrade process is expected to take approximately 30 minutes and during this time any onchain activities including transactions will be suspended.

If any issues arise during the upgrade, prompt and effective communication via Discord will be essential to address and resolve them swiftly.

We urge all FIRMACHAIN Validators to join our Discord channel to facilitate this. Validators who have not yet joined are encouraged to contact us at `contact@firmachain.org` before the upgrade for seamless support.


## Actions required by node operators

Once this proposal passes and the block height reaches `20,672,000`(Colosseum),
any block creation activity on the FIRMACHAIN network will be halted.

All Validators must upgrade their FIRMACHAIN binaries by replacing
binary files manually, or using the Cosmovisor to conduct the upgrade.
