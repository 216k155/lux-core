![Luxcoin Logo](https://i.imgur.com/0Dtm0qk.png)

"Empowered By Intelligence" 

[![Build status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg=true)](https://ci.appveyor.com/project/tygerbytes/resourcefitness) |
[![Coveralls](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?branch=master)](https://coveralls.io/github/tygerbytes/ResourceFitness?branch=master) |
[![nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg)](https://www.nuget.org/packages/TW.Resfit.Core/)

[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](https://ci.appveyor.com/project/tygerbytes/resourcefitness/history)


![Website](https://luxcore.io) | ![Block Explorer](https://explorer.luxcoin.xyz/) | ![Discord](https://discord.gg/27xFP5Y) | ![Blog](https://reddit.com/r/LUXCoin) | ![Forum](https://bitcointalk.org/index.php?topic=2254046.0)

Features
=============

* Luxgate - Parallel masternode / masternode
* Segwit
* Smart contract 
* Luxgate
* New PHI1612 PoW/PoS hybrid algorithm
* Static PoS

The Luxcore Project  is a decentralized peer-to-peer banking financial platform, created under an open source license, featuring a built-in cryptocurrency, end-to-end encrypted messaging and decentralized marketplace. The decentralized network aims to provide anonymity and privacy for everyone through a simple user-friendly interface by taking care of all the advanced cryptography in the background. 

The luxgate allow for communications among validated blockchain with the ability to perform tasks and advanced functions. Through the use of pmn, lux is able to interact many other popular blockchains and create a unifying bond among those ecosystems.

Lux doesnt provide direct support for dapp database. Instead, a mechanism to interact with other blockchain via luxgate function where other blockchain can send and recieve trigger function notices and international data through the lux network via pmn and luxgate. Pmn & luxgate can also be used to interact with the centralised services such as banker. Those centralism service can connect to the lux network for specific trigger of the luxgate via pmn. It will allow for their developed autonomous system to act base on their behalf. The pmn will then be developed by the connecting blockchain developer. Luxcore will have to supply a deployment guide to assist their developer. In other to assist the centralised services, lux will need to provide a centralised trustworthy environments. So user have their trusted oversight to verify that the transactions are legitmate

In addition, without luxgate and pmn, bitcoin and ethereum cannot interact with each other on the same blockchain
because of the technology is incompatible, it almost impossible before our pmn and luxgate functions implemented.
Therefore, we have to introduce a smartcontract & segwit features in the next release to verify that we succeed to combine those different technology together to create a brand new unique features of LUX

## Coin Specifications

| Specification | Value |
|:-----------|:-----------|
| Total Blocks | `6,000,000` |
| Block Size | `4MB` |
| Block Time | `60s` |
| PoW Reward | `10 LUX` |
| PoS Reward | `1 LUX` |
| Stake Time | `36 hours` |
| Masternode Requirement | `16,120 LUX` |
| Masternode Reward | `40% PoS Block ` |
| Port | `28666` |
| RPC Port | `9888` |
| Masternode Port | `28666` |


Build Luxcore
----------
### Build on Ubuntu

    sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils git cmake libboost-all-dev
    sudo apt-get install software-properties-common
    sudo add-apt-repository ppa:bitcoin/bitcoin
    sudo apt-get update
    sudo apt-get install libdb4.8-dev libdb4.8++-dev

    # If you want to build the Qt GUI:
    sudo apt-get install libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev protobuf-compiler

    git clone https://github.com/Lux-core/lux --recursive
    
    cd lux

    # Note autogen will prompt to install some more dependencies if needed
    ./autogen.sh
    ./configure 
    make -j2

### Build on OSX

The commands in this guide should be executed in a Terminal application.
The built-in one is located in `/Applications/Utilities/Terminal.app`.

#### Preparation

Install the OS X command line tools:

`xcode-select --install`

When the popup appears, click `Install`.

Then install [Homebrew](https://brew.sh).

#### Dependencies

    brew install cmake automake berkeley-db4 libtool boost --c++11 --without-single --without-static miniupnpc openssl pkg-config protobuf qt5 libevent imagemagick --with-librsvg

NOTE: Building with Qt4 is still supported, however, could result in a broken UI. Building with Qt5 is recommended.

#### Build Lux Core

1. Clone the Lux source code and cd into `Lux`

        git clone --recursive https://github.com/Lux-core/lux.git
        cd Lux

2.  Build Luxcore:

    Configure and build the headless Lux binaries as well as the GUI (if Qt is found).

    You can disable the GUI build by passing `--without-gui` to configure.

        ./autogen.sh
        ./configure
        make

3.  It is recommended to build and run the unit tests:

        make check

### Run

Then you can either run the command-line daemon using `src/Luxd` and `src/Lux-cli`, or you can run the Qt GUI using `src/qt/Lux-qt`

For in-depth description of Sparknet and how to use Lux for interacting with contracts, please see [sparknet-guide](doc/sparknet-guide.md).

License
-------

Luxcore is GPLv3 licensed.

Development Process
-------------------

The `master` branch is regularly built and tested, but is not guaranteed to be
completely stable. [Tags](https://github.com/Lux-core/lux/tags) are created
regularly to indicate new official, stable release versions of Lux.

The contribution workflow is described in [CONTRIBUTING.md](CONTRIBUTING.md).


Testing
-------

Testing and code review is the bottleneck for development; we get more pull
requests than we can review and test on short notice. Please be patient and help out by testing
other people's pull requests, and remember this is a security-critical project where any mistake might cost people
lots of money.

### Automated Testing

Developers are strongly encouraged to write [unit tests](src/test/README.md) for new code, and to
submit new unit tests for old code. Unit tests can be compiled and run
(assuming they weren't disabled in configure) with: `make check`. Further details on running
and extending unit tests can be found in [/src/test/README.md](/src/test/README.md).

There are also [regression and integration tests](/qa) of the RPC interface, written
in Python, that are run automatically on the build server.
These tests can be run (if the [test dependencies](/qa) are installed) with: `qa/pull-tester/rpc-tests.py`

### Manual Quality Assurance (QA) Testing

Changes should be tested by somebody other than the developer who wrote the
code. This is especially important for large or high-risk changes. It is useful
to add a test plan to the pull request description if testing the changes is
not straightforward.
