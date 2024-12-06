## Overview
This is a proposal for the FIRMACHAIN software upgrade.

The v0.4.0 upgrade brings version updates to core modules and requirements on the FIRMACHAIN network, expected to improve overall stability, security, and performance.

Once this proposal passes, the FIRMACHAIN network will be upgraded at block height [15,678,000].

## Changes
**Upgrade chain binary**
- Chain binary : v0.3.5 -> v0.4.0

**Upgrade module**
- cosmos-sdk(Cosmos SDK) : v0.45.9 -> v0.45.16
- IBC-go(IBC) : v3.3.0 -> v4.4.0
- wasmd(CosmWasm) : v0.29.2 -> v0.33.0

**Replace module**
- Tendermint : v0.34.21 -> CometBFT : v0.34.33

**Requirements**
- Go : v1.18 -> v1.21

## Tests
Comprehensive end-to-end (E2E) testing was completed in both the devnet and testnet (Imperium) environments, verifying the upgrade’s stability.

## Timeline
The upgrade will be executes on the block height [15,678,000], with an estimated date and time of [December 19, 2024, at 06:05 UTC], based on an average block generation interval of [5.78] seconds.

Upgrade process is expected to take approximately 30 minutes and during this time any onchain activities including transactions will be suspended.

If any issues arise during the upgrade, prompt and effective communication via Discord will be essential to address and resolve them swiftly.

We urge all FIRMACHAIN Validators to join our Discord channel to facilitate this. Validators who have not yet joined are encouraged to contact us at contact@firmachain.org before the upgrade for seamless support.

## Actions required by node operators
Once this proposal passes and the block height reaches [15,678,000], any block creation activity on the FIRMACHAIN network will be halted.

All Validators must upgrade their FIRMACHAIN binaries by replacing binary files manually, or using the Cosmovisor to conduct the upgrade.

For more detailed upgrade guide, please visit https://github.com/FirmaChain/mainnet/upgrade-notes-v0.4.0.md
