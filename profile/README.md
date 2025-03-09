# .github
# Mordor Testnet

<center>
  <h3 align="center">Mordor Testnet</h3>
  <p align="center">
    The Ethereum Classic Proof of Work testnet.
    <br />
    <a href="https://etc-mordor.blockscout.com">Explorer</a>
    ·
    <a href="#">Dashboard</a>
    ·
    <a href="#">Fork Mon</a>
    ·
    <a href="https://faucet.etcmc-monitor.org">Faucet</a>
    ·
    <a href="https://github.com/mordortestnet/contribute/issues/new">Create an Issue</a>
  </p>
</center>

_Launch: October 3, 2019 at ETCSummit. [eth-classic/mordor#1](https://github.com/eth-classic/mordor/issues/1)_

<p align="center">
<a href="https://www.youtube.com/watch?v=sURnZEeIqBU"><img src="https://img.youtube.com/vi/Msi6EItbslk/0.jpg" /><br />Mordor Testnet Launch: October 3, 2019 at ETCSummit.</a>
</p>

### Network Properties
- Network ID: `7`
- Chain ID: `63`
- SLIP44: `1`

### Network Upgrades | Activation Block
- Frontier: `0`
- Homestead: `0`
- GasReprice: `0`
- Diehard: `0`
- Gotham: `0`
- Defuse Difficulty Bomb: `0`
- Atlantis: `0`
- Agharta: `301_243`
- Phoenix: `999_983`
- Thanos: `2_520_000`
- Magneto: `3_985_893`
- Mystique: `5_520_000`
- Spiral: `9_957_000`

### Mordor Testnet Genesis hash

```
0xa68ebde7932eccb177d38d55dcc6461a019dd795a681e59b5a3e4f3a7259a3f1
```

### Resources

Status Dashboard:
- none

Fork Monitoring:
- none

Block Explorer:
- https://etc-mordor.blockscout.com
- https://explorer-expedition.etc-network.info/?network=Ethereum+Classic+at+etc-network.info+GETH+Mordor

Faucet:
- https://faucet.etcmc-monitor.org

Public End Points:
- https://chainlist.org/chain/63

### Core-Geth

Minimum required version: `v1.11.16`

```
geth --mordor
```
- https://github.com/etclabscore/core-geth/releases

### Hyperledger Besu

Minimum required version: `v20.10.0-RC2`

```
besu --network mordor
```
- https://github.com/hyperledger/besu/releases

---
## Mordor Testnet Guide
---


Mordor is a Proof of Work Ethereum Classic testnet. A testnet allows developers to perform specific tests. Developers may want to test protocol changes, test a smart contract, or interact with the network in anyway that does not require real EthClassic (ETC)—just don’t test on mainnet, mainnet is for production. This guide will teach you how to `mine` Mordor Testnet with your home computer to obtain the METC asset and pay for transaction on the testnet.

### Summary:

+ Install Core-geth https://etclabscore.github.io/core-geth/getting-started/installation/
+ Create an account on --mordor
+ Run --mordor with --mine enabled
+ Create a Script to mine Mordor Testnet's METC asset

### Install Core-geth

https://etclabscore.github.io/core-geth/getting-started/installation/

### Mordor Testnet Mining Guide

You can visit the Core-geth documentation for more installation options. I’m using Ubuntu 24.04 LTS.

If you just want to download and run `geth --mordor` or any of the other tools here, this is the quickest and simplest way.

Binary archives are published at https://github.com/etclabscore/core-geth/releases. Find the latest one for your OS, download it, (check the SHA sum), unarchive it, and run! As of the time this is being written, v1.12.20 is the most recent release that includes the next network upgrade: Spiral.

When running Core-geth use `--mordor` flag for Ethereum Classic's Mordor Testnet.

```shell
$ wget https://github.com/etclabscore/core-geth/releases/download/v1.12.20/core-geth-linux-v1.12.20.zip # Update to the most current release version
$ sudo unzip core-geth-linux-v1.12.20.zip -d /bin/ # Update to the most current release version
$ geth --help # Lists available options
$ geth --mordor # Runs Ethereum Classic's testnet Mordor
```

### Account Creation

You'll need an account with an address (0x...) to receive your METC mining rewards. Here is how you make an address and keystore file with core-geth. You'll be able to import the keystore file into wallets like MetaMask. Backup this file. You'll mine your Mordor Testnet block rewards to this address.

```shell
$ geth --mordor account new # Creates a new account with a public address and keystore file
$ geth --mordor account list
$ geth --mordor # Runs Ethereum Classic's testnet Mordor
```

You’ll notice listing the account will print the keystore file location.For example:keystore:///home/USER/.ethereum/mordor/keystore/UTC...

### Run Mordor with Mining Enable

```shell
$ geth --mordor --mine --miner.threads 1 --miner.gaslimit 8000000 --miner.etherbase 0x_INSERT_YOUR_ADDRESS_HERE_3a087
```

### Check your Mordor Testnet Balance

So, you’re running a Mordor node and mining testnet METC. Woohoo! An easy way to double check you’re actually growing a Mordor testnet balance is on [Blockscout](https://etc-mordor.blockscout.com). Just search the account address you created earlier.

### Add your Mordor Account to a Wallet?

You can use your keystore file to import your wallet into a wallet application such as MetaMask. In MetaMask

* Add the Ethereum Classic mainnet to your MetaMask by visiting https://chainlist.org/chain/61 and clicking the "Add to MetaMask" button.
* Add the Mordor testnet to your MetaMask by visiting https://chainlist.org/chain/63 and clicking the "Add to MetaMask" button.
* Under your account profile select import account > select type (JSON) > upload your keystore file. You may need to enter the account password.

## Mordor Mining Script

One way to avoid typing or copy and pasting this same text block is creating a shell script file.

```shell
$ geth --mordor --mine --miner.threads 1 --miner.gaslimit 8000000 --miner.etherbase 0x_INSERT_YOUR_ADDRESS_HERE_3a087
```

Enter the following in a new terminal window (ctrl + alt + t):

```shell
touch start-mordor.sh && echo "geth --mordor --mine --miner.threads 1 --miner.gaslimit 8000000 --miner.etherbase 0x_INSERT_YOUR_ADDRESS_HERE_3a087" >start-mordor.sh && chmod +x start-mordor.sh
```

touch start-mordor.sh to create the file && echo “the contents” into the shell script file && add chmod executable+x permissions to the file.

Enter the following in a new terminal window (ctrl + alt + t):

```shell
 ./start-mordor.sh
```

Great job! You are mining on Ethereum Classic's testnet.

### Donate Mined METC to a Community Faucet for Pubic Use

https://faucet.etcmc-monitor.org

A faucet is a developer tool that gives users testnet tokens to use when testing smart contracts or interacting with DApps on test networks. https://faucet.etcmc-monitor.org gives Mordor testnet ETC to test smart contracts before pushing them to production on the Ethereum Classic mainnet. Faucets like this allow network users and developers to interact with the Mordor network without the prerequisite of mining METC via a client node. To donate METC to this public faucet, please send your METC to address `0x51738162ED5E9f1251de429dfeb70D5e9f67aE95`.

### Video Mordor Testnet Guide

https://www.youtube.com/watch?v=0hutSdb-dV8

