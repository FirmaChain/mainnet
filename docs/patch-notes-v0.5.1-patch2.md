## Overview

This is a patch note for the FIRMACHAIN v0.5.1-patch2.

The `v0.5.1-patch2` addresses a security vulnerability in **CometBFT**, a core module of Cosmos. This patch is applied only to the Firmachain binary.

This release is **non-consensus breaking** and requires **no governance proposal**. Nodes may upgrade at any time.

## Changes

**Upgrade chain binary**
- Chain binary: `v0.5.1-patch` → `v0.5.1-patch2`

**Fix**
- Security vulnerability mitigation in CometBFT
- **CometBFT (Consensus)** : v0.38.18 -> v0.38.21

**Type**
- Non-breaking patch. Chain version stays at `v0.5.1`
- No governance changes required

## Tests

Comprehensive validation completed:
- **Local**: Unit tests, CLI command validation  
- **Devnet**: Unit tests, CLI commands, end-to-end tests  
- **Testnet (Imperium-4)**: Smart contract execution and state-sync validation  

## Timeline

This is a patch release and not tied to a fixed block height.  
- The patch can be **applied immediately** by any validator or full node.  
- No chain halt or governance coordination is required.

## Actions required by node operators

### Required
- All node operators and validators: patch highly recommended

### Recommended
- **All validators and full nodes**: upgrading is recommended to improve overall safety.

### Upgrade procedure
```bash
# Stop your node
sudo systemctl stop firmachaind

# Navigate to your firmachain directory
cd /path/to/firmachain

# Pull latest changes
git pull

# Checkout the patch version
git checkout v0.5.1-patch2

# Build and install the new version
make install

# Restart the node
sudo systemctl restart firmachaind

# Check version
firmachaind version

# Should show: v0.5.1-patch2
```
