> This issue is now resolved on the `v0.5.0-patch` release.
> 
> Please check this [note](https://github.com/FirmaChain/mainnet/blob/main/docs/patch-notes-v0.5.0-patch.md) and use latest release to automatically resolve this issue.

## Overview
This is a patch note for nodes and validators participated(or synced) Firmachain after `v0.4.0`.

The [issue](https://github.com/CosmWasm/wasmd/issues/478) from previous wasmd module causes **State Sync** nodes to not properly load/save contract binaries under `data/wasm`. It can cause AppHash error when a Firmachain node receives CosmWasm transaction using that stored contract.

*Nodes that have not been affected by the AppHash issue, or have been running stably since before `v0.3.5`, do not need to apply this patch.

## How to fix (Deprecated)
The wasmd issue was patched on `v0.5.0` upgrade, but to properly handle contracts that were deployed on `v0.4.0`, State Sync validators are recommeded to replace the data on `data/wasm` path with our patch file.

**Patch File**
- File Path: [references/wasm.tar.gz](references/wasm.tar.gz)
- Patch Path: `.firmachain/data/wasm`
- SHA256: `28ee18eda3dc8d025d467ba9191fc512c41f7356a9d5e821af03cc68c5e19af3`

**Commands**
```bash
# 1. Download patch file and stop firmachaind first

# 2. Check patch file hash
sha256sum wasm.tar.gz 

# 3. Hash result check
28ee18eda3dc8d025d467ba9191fc512c41f7356a9d5e821af03cc68c5e19af3 wasm.tar.gz

# 4. Remove old wasm directory
rm -rf ~/.firmachain/data/wasm

# 5. Unzip patched wasm directory
tar -C ~/.firmachain/data -xvzf wasm.tar.gz 

# 6. Start firmachaind again
```

If you still experience problem resolving the issue with this solution, contact us via contact@firmachain.org or join Validators' Discord.
