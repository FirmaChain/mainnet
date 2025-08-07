## Overview

This is a proposal for the FIRMACHAIN software upgrade.

The v0.5.0 upgrade brings **major version updates** to core modules, new parameters for latest governance system, and changes on requirements on the FIRMACHAIN network, expected to significantly improve platform performance, interoperability, and the developer experience, laying the foundation for long-term scalability and reliability.

Starting from this upgrade, FIRMACHAIN will move beyond infrastructure to create real-world impact. Our goal is to become a **Global Trust Layer**, driving synergy with active contributors and building an ecosystem that delivers maximum impact.

Once this proposal passes, the FIRMACHAIN network will be upgraded at block height `19,350,000`(Colosseum).


## Changes

**Upgrade chain binary**
- Chain binary : v0.4.0 -> v0.5.0

**Upgrade module**
- **cosmos-sdk (Cosmos SDK)** : v0.45.16 -> v0.50.12 **[Major Upgrade]**
- **IBC-go (IBC)** : v4.4.0 -> v8.6.1 **[Major Upgrade]**
- **wasmd (CosmWasm)** : v0.33.0 -> v0.54.0 (WasmVM 2.2.1) **[Major Upgrade]**
- **CometBFT (Consensus)** : v0.34.33 -> v0.38.17 **[Major Upgrade]**

**Ecosystem Requirements**
- **firma-js** : v0.3.7 or newer  **[Major Upgrade]**

**New modules**
- sdk module : `x/circuit`
- ibc middleware : `packet-forward-middleware`
- ibc module : `ibc-hooks`, `ibc-fee`, `ica-host`, `icq`

**New Governance Parameters**
- MinInitialDepositRatio : `0.5`
- ProposalCancelRatio : `0.5`
- ProposalCancelDest : `firma1kvlelvv6u7h4jasqlpu956czt4543xqzc37h2v`


## Tests

Comprehensive end-to-end (E2E) testing was completed in both the
devnet and testnet (Imperium) environments, verifying the upgrade's stability.


## Timeline

The upgrade will be executes on the block height `19,350,000`(Colosseum).
with an estimated date and time of **August 21st, 2025, at 05:00 UTC**, based on an average block generation interval of 5.75 seconds.

Upgrade process is expected to take approximately 30 minutes and during this time any onchain activities including transactions will be suspended.

If any issues arise during the upgrade, prompt and effective communication via Discord will be essential to address and resolve them swiftly.

We urge all FIRMACHAIN Validators to join our Discord channel to facilitate this. Validators who have not yet joined are encouraged to contact us at contact@firmachain.org before the upgrade for seamless support.


## Actions required by node operators

Once this proposal passes and the block height reaches `19,350,000`(Colosseum),
any block creation activity on the FIRMACHAIN network will be halted.

All Validators must upgrade their FIRMACHAIN binaries by replacing
binary files manually, or using the Cosmovisor to conduct the upgrade.

For more detailed upgrade guide, please visit
https://github.com/FirmaChain/mainnet/blob/master/docs/update-notes-v0.5.0.md
