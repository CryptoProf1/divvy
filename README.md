DIVVY [DVY] CORE
================================

Specifications:
--------------

* PoW (proof of work) / PoS (proof of stake)
* Algorithms: Skein
* Blocktime: 60 seconds
* RPC port: 11446
* P2P port: 11445
* Blockreward (PoW):
  * Block 71 to 100 : 1 DVY
  * 100 to 10,000 : 10 DVY
  * 10,001 to 20,000: 8 DVY
  * 20,001 to 30,000: 6 DVY
  * 30,001 to 40,000: 4 DVY
  * 40,001 to 50,000: 2 DVY
  * Total PoW: 50,000 Blocks

* Blockreward (PoS):
  * Block 101 to 10,000 : 10 DVY
  * 10,001 to 20,000: 12 DVY
  * 20,001 to 30,000: 13 DVY
  * 30,001 to 40,000: 14 DVY
  * 40,001 to 50,000: 15 DVY
  * 50,001 to 100,000: 10 DVY
  * After 100,001: 8 DVY  

* Masternode Collaterial - 5 000 DVY.
* Masternodes Rewards - 75% of PoS Blocks.
* Diff Retarget: 5 Blocks
* Maturity: 30 Blocks
* Stake Minimum Age: 24 Hours
* 40 MegaByte Maximum Block Size (40X Bitcoin Core)


Divvy includes an Address Index feature, based on the address index API (searchrawtransactions RPC command) implemented in Bitcoin Core but modified implementation to work with the DVY codebase (PoS coins maintain a txindex by default for instance).

Initialize the Address Index By Running with -reindexaddr Command Line Argument.  It may take 10-15 minutes to build the initial index.


Linux Build Instructions and Notes
==================================

Dependencies
----------------------
1.  Update packages

        sudo apt-get update

2.  Install required packagages

        sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
        sudo apt-get install libboost-all-dev git
        sudo apt-get install libminiupnpc-dev libgmp3-dev

3.  Install Berkeley DB 4.8

        sudo apt-get install software-properties-common
        sudo add-apt-repository ppa:bitcoin/bitcoin
        sudo apt-get update
        sudo apt-get install libdb4.8-dev libdb4.8++-dev


Build
----------------------
1.  Clone the source:

        git clone https://github.com/divvycrypto/divvy/

2.  Build divvy:

    Configure and build.

        cd divvy
        cd src/
        make -f makefile.unix   



Masternode configuration is very similiar to other Masternodes coins.
----------------------

edit divvy.conf

      rpcuser=divvy
      rpcpassword=putyourpasswordhere
      rpcallowip=127.0.0.1
      rpcport=11446
      masternode=1
      masternodeaddr=192.168.0.1:11445
      port=11445
      masternodeprivkey=putyourkeyhere
      daemon=1

