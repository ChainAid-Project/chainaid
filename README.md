# ChainAid

# UNIX BUILD NOTES
====================

To Build ChainAid Headless Wallet Daemon.
-----------------

# Firstly ensure your system has all the Required tools in order to build ChainAid Correctly with no issue's. Please commit these commands through the Terminal of your choice.


sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libdb++-dev libminiupnpc-dev 

sudo apt-get install software-properties-common

sudo add-apt-repository ppa:bitcoin/bitcoin

sudo apt-get update

sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libqrencode-dev



# Now you have all files Required by ChainAid's code in order to build the Wallet.



# Now we proceed onto making the ChainAid Wallet. Again use your preferred Terminal


git clone https://github.com/ChainAid-Project/chainaid.git

cd chainaid/src/secp256k1

chmod +x autogen.sh

sudo ./autogen.sh

sudo ./configure

sudo make && make install

cd ..

cd leveldb

sudo sh build_detect_platform build_config.mk .

cd ..

sudo make -f makefile.unix -j4

strip chainaidd

LD_LIBRARY_PATH=/usr/local/lib

export LD_LIBRARY_PATH



# You now have chainaidd Ready to run and connect to the network.


# To Build ChainAid Qt Wallet
------------------

# Firstly ensure your system has all the Required tools in order to build ChainAid Correctly with no issue's. Please commit these commands through the Terminal of your choice.


sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils

sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev libdb++-dev libminiupnpc-dev 

sudo apt-get install software-properties-common
sudo add-apt-repository ppa:bitcoin/bitcoin
sudo apt-get update
sudo apt-get install libdb4.8-dev libdb4.8++-dev

sudo apt-get install libqrencode-dev



# Now you have all files Required by ChainAid's code in order to build the Wallet.



# Now we proceed onto making the ChainAid Wallet. Again use your preferred Terminal



git clone https://github.com/ChainAid-Project/ChainAid.git

cd chainaid/src/secp256k1

chmod +x autogen.sh

sudo ./autogen.sh

sudo ./configure

sudo make && make install

cd

cd chainaid/src/leveldb

sudo sh build_detect_platform build_config.mk .

cd

cd chainaid

sudo qmake CHID.pro

sudo make -jnumofcoreshere