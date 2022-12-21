# FIRMACHAIN v0.3.5 Upgrade Notes
This document is a user guide to upgrade FIRMACHAIN from v0.3.3 to v0.3.5.

</br>

## **Overview**
- Governance Proposal: https://explorer.firmachain.dev/proposals/3
- Estimated Date: December 20, 2022 UTC 14:00
- Target Block Height: `4,806,000`
- Upgrade Type: Soft-fork by governance software upgrade proposal

|                         |  Before  |   After  | Others                                                       |
| ----------------------- | :------: | :------: | --------------------------------------------------------- |
| FirmaChain              |  v0.3.3  |  v0.3.5-patch  | -                                                |
| Cosmos SDK              |  v0.44.5 |  v0.45.9 | -                                                         |
| Tendermint              | v0.34.14 | v0.34.21 | -                                                         |
| IBC                     |  v1.2.2  |  v3.3.0  | -                                                         |
| Wasmd                   |     -    |  v0.29.2 | -                                                         |
| Minimum commission rate |    0%    |    5%    | [Proposal/2](https://explorer.firmachain.dev/proposals/2) |

</br>

### **Main Chainges**
- Support Cosmos SDK 0.45.9
- Support IBC v3.3.0
- Support Wasmd v0.29.2 (support cosmwasm-std 1.0-1.1)
- Change 'Minimum Commission Rate' (0% -> 5%)

</br>

### **Preparing for the Upgrade Binary**
Prepare the FirmaChain v0.3.5-patch binary for the upgrade.

This upgrade will not support the binary download method used in the previous upgrades. This is because with the addition of the CosmWasm module, users must install the "libwasmvm.so" library that suits the user’s respective operating system and version.

```bash
# The installation of go, gcc and make are required in order to continue with the build.
# (If you have them already installed, you can skip this process)
> sudo snap install go --classic
> sudo apt install gcc
> sudo apt-get install make

# Binary build
> git clone https://github.com/firmachain/firmachain.git
> cd firmachain
> git checkout v0.3.5-patch
> make install
```

</br>

### **Check binary version**
Please check the version once you’ve prepared your binary. If the version information is different from the one mentioned in the “Code Block” below, please create a new binary or [contact us](mailto:contact@firmachain.org) to solve the issue.

```bash
> ~/go/bin/firmachaind version
0.3.5-patch

> ~/go/bin/firmachaind version --long
name: FirmaChain
server_name: firmachaind
version: 0.3.5-patch
...
cosmos_sdk_version: v0.45.9
```

</br>

## **Upgrade Manually**
Once you've completed all of the above without any problems, let's restart the chain.

</br>

### **Stand by at upgrade height**
Once the chain network reaches block height `4,806,000` on the v0.3.3, the network will display an “Error Message’ and will come to a halt. However, the process will still remain in alive state. If you see the following error message, please manually kill the nodes.
</br>
*(If you have registered using system service, you must STOP the service.)*

```bash
# using binary
> pkill firmachaind

# or using system service
> sudo systemctl stop firmachaind
```

### **Backup (optional)**
If you are faced with an issue while upgrading the network, you might have to restart from the original version. Therefore, we highly recommend you backup the original version of FirmaChain before upgrading the network. (Per Pruning Default, approximately 200~250 GB expected)
```bash
> tar -cvf firmachain_bak_20221220.tar .firmachain
```

</br>

### **Start FirmaChain**
Once you've completed all of the above without any problems, let's restart the chain.
```bash
# Binary move
> sudo mv ~/go/bin/firmachaind /usr/local/bin/firmachaind

# using binary
> firmachaind start

# or using system service
> sudo systemctl start firmachaind
```

</br>

## **Upgrade using Cosmovisor**
Move the v0.3.5-patch binary to the appropriate folder space.

</br>

### **Installation Process**
- If you do not have a Cosmovisor installed, please proceed with the installation through the link below.
- https://docs.firmachain.org/master/validator-guide/upgrade/cosmovisor-guide

</br>

### **Setting up the upgrade binary on the "Cosmovisor" directory.**
Once you’ve completed the above step, the chain will automatically restart from the upgraded block height using the new binary.
```bash
# If the "go/bin/" folder has a binary
> mv go/bin/firmachaind $DAEMON_HOME/cosmovisor/upgrades/v0.3.5/bin/firmachaind

# If the "/usr/local/bin/" folder has a binary
mkdir -p $DAEMON_HOME/cosmovisor/genesis/bin
> cp $(which firmachaind) $DAEMON_HOME/cosmovisor/genesis/bin/
```

</br>

## **Notes for reference**
Please contact us if you are faced with any issues during the upgrade.\
E-mail: contact@firmachain.org
