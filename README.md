# Pactus Mainnet Node
## Upgrade Pactus v1.6.2
```Bash
cd node_pactus && sudo screen -r pactus
```
- Ctrl + C, to stop your node
```Bash
cd $HOME && rm -rf node_pactus 
wget https://github.com/pactus-project/pactus/releases/download/v1.6.0/pactus-cli_1.6.0_linux_amd64.tar.gz && \
tar -xzf pactus-cli_1.6.0_linux_amd64.tar.gz && \
rm -rf pactus-cli_1.6.0_linux_amd64.tar.gz && \
mv pactus-cli_1.6.0 node_pactus && cd node_pactus
```
```Bash
sudo ./pactus-daemon start
```
## Done!
....................................................................................
# Install Pactus Mainnet Node
## Server preparation:
```Bash
sudo apt update && sudo apt upgrade -y && sudo apt install tmux git curl -y && sudo apt install make clang pkg-config libssl-dev build-essential -y
```
## Download Pactus v1.4.0: (amd64)
```Bash
cd $HOME && rm -rf node_pactus && \
wget https://github.com/pactus-project/pactus/releases/download/v1.4.0/pactus-cli_1.4.0_linux_amd64.tar.gz && \
tar -xzf pactus-cli_1.4.0_linux_amd64.tar.gz && \
rm -rf pactus-cli_1.4.0_linux_amd64.tar.gz && \
mv pactus-cli_1.4.0 node_pactus && cd node_pactus
```
## Setup: 
*Note: It is recommended to run 1-7 validator. Chose 1
Save all important information in this step (Address validator, Wallet & seed).
### Creat new:
```Bash
./pactus-daemon init
```
### Restore old wallet:
```Bash
./pactus-daemon init --restore "<your-seed>"
```
## Important: Set tx_pool = 1000 -> 50
```Bash
sed -i.bak '/^\s*[tx_pool]/, /^\s*[/{s/(max_size = )100/\150/;}' $HOME/pactus/config.toml
```
## Start Node:
```Bash
sudo screen -S pactus
```
```Bash
sudo ./pactus-daemon start
```
## Useful Command:
### Wallet seed:
```Bash
./pactus-wallet seed
```
### List of Addr:
```Bash
./pactus-wallet address all
```
### Check Balance:
```Bash
./pactus-wallet address balance <ADDRESS>
```
### Bond to the validator
```Bash
./pactus-wallet tx bond <Reward address> <Validator address> <AMOUNT>
```
### Send token
```Bash
./pactus-wallet tx transfer <reward address> <receiver address> <AMOUNT>
```

## ...............Thank you!...............








