## Overview

This is a patch note for the FIRMACHAIN v0.5.0-patch.

The `v0.5.0-patch` resolves an [issue](https://github.com/FirmaChain/firmachain/issues/11) where **state-synced nodes** would stop syncing due to AppHash mismatches when processing smart contract transactions. This fix ensures that **CosmWasm contract data** (code, pinned codes, checkpoints) is properly included in state-sync snapshots, improving reliability and stability for all nodes.

This patch is **non-consensus breaking** and requires **no governance proposal**. It can be safely applied by all participants at any time.

## Changes

**Upgrade chain binary**
- Chain binary : `v0.5.0` → `v0.5.0-patch`

**Fix**
- Include CosmWasm contract data in state-sync snapshots
- Prevent AppHash mismatch on first smart contract execution for state-synced nodes

**Type**
- Non-breaking patch. Chain version stays at `v0.5.0`
- No governance changes required


## Tests

Comprehensive testing has been performed:
- **Local**: Unit tests, CLI command validation  
- **Devnet**: Unit tests, CLI commands, end-to-end tests  
- **Testnet (Imperium-4)**: Smart contract execution tests with state-sync validation  


## Timeline

This is a patch release and not tied to a fixed upgrade block height.  
- The patch can be **applied immediately** by any validator or full node.  
- No chain halt or governance coordination is required.  


## Actions required by node operators

### Required
- **State-sync providers**: must upgrade to provide valid snapshots (new snapshots will include CosmWasm data).  
- **State-sync users**: must upgrade to restore from new snapshots successfully.  

### Recommended
- **All validators and full nodes**: upgrade to prevent future issues and improve network stability.  

### Upgrade procedure
```bash
# Stop your node
sudo systemctl stop firmachaind

# Navigate to your firmachain directory
cd /path/to/firmachain

# Pull latest changes
git pull

# Checkout the patch version
git checkout v0.5.0-patch

# Build and install the new version
make install

# Restart the node
sudo systemctl restart firmachaind

# Check version
firmachaind version

# Should show: v0.5.0-patch
```
