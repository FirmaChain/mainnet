## Overview

This is a patch note for the FIRMACHAIN v0.5.1-patch.

The `v0.5.1-patch` resolves an [issue](https://github.com/FirmaChain/firmachain/issues/20) where **temporary WASM directories** (e.g., `/tmp/.firmachainXXXXXXX`) were generated on every `firmachaind` execution and **not cleaned up**. Over time, these orphaned directories could accumulate in `/tmp`, causing **inode exhaustion** and increased disk usage.

This patch ensures that **CosmWasm temporary directories are properly removed** after each command execution.

This release is **non-consensus breaking** and requires **no governance proposal**. Nodes may upgrade at any time.

## Changes

**Upgrade chain binary**
- Chain binary: `v0.5.1` → `v0.5.1-patch`

**Fix**
- Ensure proper cleanup of CosmWasm temporary directories (`/tmp/.firmachain*`)
- Prevent inode and disk growth caused by leftover WASM temp dirs
- Improve operational stability for all node environments

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
- Node operators experiencing **growing `/tmp/.firmachain*` directories** should upgrade to prevent inode exhaustion.

### Recommended
- **All validators and full nodes**: upgrading is recommended to avoid future disk bloat and ensure a clean execution environment.

### Upgrade procedure
```bash
# Stop your node
sudo systemctl stop firmachaind

# Navigate to your firmachain directory
cd /path/to/firmachain

# Pull latest changes
git pull

# Checkout the patch version
git checkout v0.5.1-patch

# Build and install the new version
make install

# Restart the node
sudo systemctl restart firmachaind

# Check version
firmachaind version

# Should show: v0.5.1-patch
```
