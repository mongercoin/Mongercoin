

### Coin Specs
<table>
<tr><td>Coin name</td><td>Monger Coin</td></tr>
<tr><td>Symbol</td><td>MGR</td></tr>
<tr><td>Algo</td><td>Quark Zerocoin</td></tr>
<tr><td>Type</td><td>PoS/MN</td></tr>
<tr><td>Rewards</td><td>MN 75% / POS 25%</td></tr>
<tr><td>Maturity</td><td>120 blocks</td></tr>
<tr><td>Max Coin Supply</td><td>140,000,000</td></tr>
<tr><td>Halving</td><td>~2 years (1,000,000 blocks)</td></tr>
<tr><td>Premine</td><td>0.08% (175000)</td></tr>
<tr><td>Block maturity</td><td>120 blocks</td></tr>
<tr><td>Block Time</td><td>60 Seconds</td></tr>
<tr><td>Min Staking age</td><td>3 hours</td></tr>
<tr><td>Masternode collateral</td><td>2000 MGR</td></tr>
<tr><td>P2P port:</td><td>7121 </td></tr>
<tr><td>RPC port: </td><td>7120 </td></tr>

</table>

### PoS Rewards Breakdown

<table>
<th>Block</th><th>Reward</th><th></th>
<tr><td>0-1</td><td>Premine</td><td></td></tr>
<tr><td>2-10000</td><td>0.1</td><td></td></tr>
<tr><td>10001-20000</td><td>20</td><td>PoS - 5 MGR, MN - 15 MGR</td></tr>
<tr><td>20001-30000</td><td>25</td><td>PoS - 6.25 MGR, MN - 18.75 MGR</td></tr>
<tr><td>30001-40000</td><td>35</td><td>PoS - 8.75 MGR, MN - 26.25 MGR</td></tr>
<tr><td>40001-50000</td><td>50</td><td>PoS - 12.5 MGR, MN - 37.5 MGR</td></tr>
<tr><td>50001-60000</td><td>35</td><td>PoS - 8.75 MGR, MN - 26.25 MGR</td></tr>
<tr><td>60001-70000</td><td>25</td><td>PoS - 6.25 MGR, MN - 18.75 MGR</td></tr>
<tr><td>70001-80000</td><td>20</td><td>PoS - 5 MGR, MN - 15 MGR</td></tr>
<tr><td>80001-1000000</td><td>15</td><td>PoS - 3.75 MGR, MN - 11.25 MGR</td></tr>
</table>


***

It is recommended [use the shell script](https://mongercoin.com/masternode.sh) to install a Monger Coin Masternode on a Linux server running Ubuntu 14.04 or 16.04

***

Quick installation of the Monger daemon under linux. See detailed instructions there [build-unix.md](build-unix.md)

Installation of libraries (using root user):

    add-apt-repository ppa:bitcoin/bitcoin -y
    apt-get update
    apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    apt-get install -y libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    apt-get install -y libdb4.8-dev libdb4.8++-dev

Cloning the repository and compiling (use any user with the sudo group):

    cd
    git clone https://github.com/mongercoin/Mongercoin.git
    cd Mongercoin
    chmod +x autogen.sh
    cd Mongercoin/share
    chmod +x genbuild.sh
    cd Mongercoin/src/leveldb
    chmod +x build_detect_platform
    cd .. / cd ..
    ./autogen.sh
    ./configure
    sudo make install
    cd src
    sudo strip Mongerd
    sudo strip Monger-cli
    sudo strip Monger-tx
    cd ..

Running the daemon:

    Mongerd 

Stopping the daemon:

    Monger-cli stop

Demon status:

    Monger-cli getinfo
    Monger-cli mnsync status

All binaries for different operating systems, you can download in the releases repository:

https://github.com/mongercoin/Mongercoin/releases


-
Distributed under the MIT software license, see the accompanying file COPYING or http://www.opensource.org/licenses/mit-license.php.
