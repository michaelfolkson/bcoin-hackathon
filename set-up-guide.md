# Set up Instructions

7 terminals are required in total so open 7 Terminals (Download iTerm to be able to easily navigate between panes) https://www.iterm2.com

### Terminal 1: Bcoin

There are some set up instructions for setting up Bcoin at https://github.com/bcoin-org/bcoin. Complete these instructions first.

```
$ git clone git://github.com/bcoin-org/bcoin.git
$ cd bcoin
$ npm install
$ bcoin
```
bcoin should be installed globally so you should be able to run ```bcoin```. If this command is not found, run ```/path/to/bcoin/bin/bcoin``` substituting the path to bcoin into ```/path/to```

See https://github.com/bcoin-org/bcoin/wiki/Beginner's-Guide for more in-depth installation instructions.

Once you have confirmed that bcoin has been successfully installed globally, you may stop running bcoin and instead run the following:

```$ bin/bcoin --network simnet --nodes 10.7.64.53,redsquad.dev.purse.io --host '::' --public-host 172.17.0.1```

Replace 172.17.0.1 with your Local IP address on the Wireless LAN. This can be be found in Mac by going to System Preferences -> Network and the IP address should be under Status: Connected

(Alternatively instead of the Wireless LAN, put whatever public facing IP address is specific to that host)

#### Terminal 2: BTCD ####

After following teh instructions here: https://github.com/lightningnetwork/lnd/blob/master/docs/INSTALL.md
you are ready to run the following:

```~/gocode/src/github.com/roasbeef/btcd$ btcd --simnet --txindex --rpcuser=riskb --rpcpass=riskb --listen='127.0.0.1:18999' --rpclisten='127.0.0.1:19999' --addpeer='redsquad.dev.purse.io' --addpeer='10.7.64.53' --configfile='/home/nb/.btcd/btcd.conf' --generate --miningaddr=re1mKZbSabroCw5XzoAL9uLRXtnvPDoyDB --miningaddr=4NyX3pGCt6Zv5nRahysL4nSGNfvKUS44cC5X9 --miningaddr=rZ5dLBFvyUAsE6oBx8bsuf2PEPNcE5kahh```

REPLACE THE VALUES FOR `miningaddr=` WITH ADDRESSES YOU GENERATE IN `lndcli` USING `lncli --rpcserver "127.0.0.1:10009" newaddress np2wkh`

#### TERMINAL 3: LND ####

After following the instructions here: https://github.com/lightningnetwork/lnd , run the following in any folder:

```$ lnd --simnet --btcdhost=127.0.0.1:19999 --rpcuser=riskblimitedusername --rpcpass=riskblimitedpass```

REPLACE THE VALUES FOR `--rpcuser=` and `--rpcpass=` with your own user and password configured in the instructions in the attached screenshot.

#### TERMINAL 4: btcctl ####

```btcctl --help```
```btcctl --simnet getpeerinfo --rpcserver='127.0.0.1:19999' --rpcpass='riskblimitedpass' --rpcuser='riskblimitedusername'```

#### TERMINAL 5: vim ~/.btcd/btcd.conf ####

```$ vim ~/.btcd/btcd.conf```

#### TERMINAL 6: vim ~/.lnd/lnd.conf ####

```$ vim ~/.lnd/lnd.conf```

#### TERMINAL 7: lncli ####

nathanforhire [6:20 PM] 
```lncli help```


 ```lncli --rpcserver "127.0.0.1:10009" newaddress np2wkh```
```lncli --rpcserver "127.0.0.1:10009" newaddress np2wkh```
```lncli --rpcserver "127.0.0.1:10009" newaddress np2wkh```

  
Use the values generated above as the values for `--miningaddr=` in ####TERMINAL 2: BTCD####

nathanforhire [6:58 PM] 
// , Here is a good command to see stuff that is open on your computer: `$ netstat`


// , run this to get them muns:

```lncli connect 038017b5220d2cafa70460dd5d9d82015cddd65232de8d1140778857d9ebd33e4e@10.7.64.88:10011```

// , My identity pubkey is as follows: 0345affabb5ba4eb5d2055a90f8ce71637dd8802601d9345796a25271669476316

// , my address on our internal LAN is as follows:

172.17.0.1

yqm8tbstwsj7sbhsbzn6cfz6y4qqzar3ystdwqnhmnq67ncifgwouod5e7pfqiounrim9rog1fnajbopqpw1yx1hayjh43szra8ifwxayyyyyyyyyynprkrwhyko

`$ lncli sendpayment --pay_req=yqm8tbstwsj7sbhsbzn6cfz6y4qqzar3ystdwqnhmnq67ncifgwouod5e7pfqiounrim9rog1fnajbopqpw1yx1hayjh43szra8ifwxayyyyyyyyyynprkrwhyko` (edited)

`lncli addinvoice --memo='magic' --value=1234` (edited)
