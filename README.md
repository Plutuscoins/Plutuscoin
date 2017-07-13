# Plutuscoin
I. Basics
    1. Open up terminal ((⌘ + F) > Type: Terminal > Return)
    2. 
    3. 
    4.  
    5. 
    6. Copy & Paste all "$ [commands]” into the terminal above 

II. MAC OSX ONLY

    A. SET UP ENVIRONMENT
        // INSTALL XCODE
    1. $ xcode-select —-install  
        // INSTAL HOMEBREW
    1. $ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)”
    2. $ brew install wget
        // SET UP ENVIRONMENT 
    1. $ brew install automake berkeley-db4 libtool boost --c++11 miniupnpc openssl pkg-config protobuf qt libevent
    2. $ brew install librsvg

    B. CLONE & GET INTO bitcoin 
    1.  $ git clone https://github.com/bitcoin/bitcoin 
    2. $ cd ls -la 
        * (make sure you see a plutuscoin and/or plutuscoin.zip in list) 
        * If not go to Downloads folder and look up plutuscoin and/or plutuscoin.zip folder/file. Copy file and go to $HOME directory (in Finder window (⌘ + Shift + G) > Type: /Users/$YourUSERName/ > RTturn) 
        * 
        * 
        * Back to Terminal 
    1. $ ls -la (Plutuscoin should be on the list)
    2. $ cd plutuscoin

    // This is only if you are editing Source Code (ADVANCED)
    1. $ export LC_CTYPE=C && export LANG=C
    2. $ find . -type f -exec sed -i '' 's/bitcoin/plutuscoin/g' {} \;
    3. $ find . -type f -exec sed -i '' 's/Bitcoin/Plutuscoin/g' {} \;
    4. $ find . -type f -exec sed -i '' 's/BitCoin/PlutusCoin/g' {} \;
    5. $ find . -type f -exec sed -i '' 's/BitCoind/PlutusCoind/g' {} \;
    6. $ find . -type f -exec sed -i '' 's/Bitcoind/Plutuscoind/g' {} \;
    7. $ find . -type f -exec sed -i '' 's/bitcoind/plutuscoind/g' {} \;
    8. $ find . -type f -exec sed -i '' 's/BTC/PLTC/g' {} \;
    9. $ find . -type f -exec sed -i '' 's/litecoin/plutuscoin/g' {} \;
    10. $ find . -type f -exec sed -i '' 's/Litecoin/Plutuscoin/g' {} \;
    11. $ find . -type f -exec sed -i '' 's/LiteCoin/PlutusCoin/g' {} \;
    12. $ find . -type f -exec sed -i '' 's/LiteCoind/PlutusCoind/g' {} \;
    13. $ find . -type f -exec sed -i '' 's/Litecoind/Plutuscoind/g' {} \;
    14. $ find . -type f -exec sed -i '' 's/litecoind/plutuscoind/g' {} \;
    15. $ find . -type f -exec sed -i '' 's/LTC/PLTC/g' {} \;

C. BUILD BITCOIN-CORE
    1. $ ./autogen.sh
    2. $ ./configure
    3. $ make
D. TEST BITCOIN-CORE *OPTIONAL
    1. $ make check
   
E. DEPLOY BITCOIN-CORE
    1. $ make deploy


III. RUN BITCOIN-CORE
    A. CREATE .CONF FILE
    1. $ mkdir /Users/$YourUSERName/Library/Application\ Support/Plutuscoin
    2. $ echo -e "rpcuser=plutuscoinrpc\nrpcpassword=$(xxd -l 16 -p /dev/urandom)" > “/Users/$YourUSERName/Library/Application\ Support/Plutuscoin/plutuscoin.conf”
        * // USE THIS AS A REFERENCE 
        * https://litecoin.info/Litecoin.conf (Sample litecoin.conf) 

    B. RCP CONFIGURATION 
    1. $ chmod 600 "/Users/${USER}/Library/Application\ Support/Plutuscoin/plutuscoin.conf"

    C. RUN BITCOIN-CORE &&  DEBUG.LOG
    1. $ ./src/plutuscoind
            // DEBUG.LOG in real-time
        * $ tail -f $HOME/Library/Application\ Support/plutuscoin/debug.log
    D.OPEN APP
    1. FINDER: (in Finder window (⌘ + Shift + G) > Type: /Applications > Return) 
    2. Locate Plutuscoin (Plutuscoin-qt), open
        * 
IV. WITHOUT APP OPEN (IN TERMINAL)
    A.  RUN PLUTUSCOIN & Get Acct info & Wallet Address
    1. Go to terminal 
    2. $ cd
    3. $ cd plutuscoin
    4. $ ./src/plutuscoind
    5. (⌘ +  T) 
    6. $ ./src/plutuscoind getinfo 
        * IF ERROR: $./src/plutuscoin-cli getinfo
    7. $ ./src/plutuscoind getaccountaddress “"
        * IF ERROR: $./src/plutuscoin-cli getaccountaddress
    8. $ ./src/plutuscoind getaccount [COPY & PASTE ADDRESS FROM ABOVE OUTPUT]
        * IF ERROR: $./src/plutuscoin-cli [COPY & PASTE ADDRESS FROM ABOVE OUTPUT]
