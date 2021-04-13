
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://travis-ci.com/artrepreneur/PKT-Cash-Wallet.svg?branch=master)](https://travis-ci.com/artrepreneur/PKT-Cash-Wallet)
# Zulu
Zulu wallet is a QT wallet for the PKT Cash blockchain mainnet. This wallet adds a graphical user interface (GUI) to the command line daemon [pktwallet](https://github.com/pkt-cash/pktd/tree/master/pktwallet). Zulu Wallet runs as a standalone application for macOS currently, and eventually will have support for Unix. 

This is a SPV wallet, and no longer a full node. It comes bundled with binaries for [pktwallet](https://github.com/pkt-cash/pktd/tree/master/pktwallet), and the remote procedure call (RPC) client [pktctl](https://github.com/pkt-cash/pktd/tree/master/cmd/btcctl). These binaries are stored in the bin folder of this repo. It is also possible to compile these binaries from their respective repositories. If you decide to compile on your own, use this branch of the [pkt-cash](https://github.com/pkt-cash/pktd) repo. These binaries should be placed in the bin folder or the wallet will cease to work. It is important to note that the pktwallet binary should be renamed to wallet, and the btcctl binary should be renamed pktctl else they will fail to function properly.     

## Wallet Features
The wallet includes the following features. 

1. Send and receive transactions.
2. Sign transactions.
3. Verify transactions.
4. Generate new regular addresses.
5. Export private keys and import new private keys.
6. Password-protect the wallet.
7. Save and restore the wallet backup from seed.
8. Fold wallet addresses - for large UTXO sets.
9. View full transaction history.

## Installation
Clone the repository.

```
git clone https://github.com/artrepreneur/Zulu
```

Please use Python 3. Create an [Anaconda](https://www.anaconda.com/products/individual) environment.

Install `zbar`. The zbar DLLs are included with the Windows Python wheels. However, you will need to install the `zbar` shared library on other operation systems

##### Mac OS X:

```
brew install zbar
```
##### Linux:

```
sudo apt-get install libzbar0
```

Use pip to install the dependencies from requirements.txt. 

```
pip install -r requirements.txt
```

##### Linux (required):


Swap the binaries for pktwallet and pktctl in the bin directory for linux binaries. You can build them from the repo's mentioned above or use these [releases.](https://github.com/pkt-cash/pktd/releases) This is required for linux to work but is optional on mac's. 

Finally, change the permissions of the binaries.

```
chmod 755 bin/*
```



## Running PKT Cash Wallet

To run Zulu wallet, just invoke the python script as follows. 

##### Mac OS X:
```
pythonw PKTWallet.py
```

##### Linux:
```
pythonw PKTWallet.py
```

That's it. If you have a legacy command line wallet already running it will use the existing wallet database already present on your system. If you don't have a command line wallet you will be prompted to create a new wallet. Always, make sure to store your wallet seed in a safe place. 

## Build A DMG
By default, .dmg's are available in [releases](https://github.com/artrepreneur/Zulu/releases), but for completeness, and security, you can build your own .dmg using the bundled make script. On mac's you can do the following.

```
sudo ./make_osx.sh
```

Your .dmg, and a PKTWallet executable `PKTWallet.app`, are both available in the `./dist` directory. To run it, copy it to the applications folder and run it as a normal app. 

```
cp -rf ./dist/PKTWallet.app /Applications
```

You can also run the .dmg which will install the PKTWallet.app where it needs to go. Mac's will require you to go to `System Preferences > Security & Privacy` and allow the application to run. 



