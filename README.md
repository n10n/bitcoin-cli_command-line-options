# bitcoin-cli --help

Bitcoin Core RPC client version v0.10.0.0-g047a898


Usage:
  bitcoin-cli [options] <command> [params]  Send command to Bitcoin Core
  
  bitcoin-cli [options] help                List commands
  
  bitcoin-cli [options] help <command>      Get help for a command
  

Options:

  -?                     This help message
  
  -conf=<file>           Specify configuration file (default: bitcoin.conf)
  
  -datadir=<dir>         Specify data directory
  
  -testnet               Use the test network
  -regtest               Enter regression test mode, which uses a special chain in which blocks can be solved instantly. This is intended for regression testing tools and app deelopment.
  -rpcconnect=<ip>       Send commands to node running on <ip> (default: 127.0.0.1)
  -rpcport=<port>        Connect to JSON-RPC on <port> (default: 8332 or testnet: 18332)
  -rpcwait               Wait for RPC server to start
  -rpcuser=<user>        Username for JSON-RPC connections
  -rpcpassword=<pw>      Password for JSON-RPC connections

SSL options: (see the Bitcoin Wiki for SSL setup instructions)
  -rpcssl                Use OpenSSL (https) for JSON-RPC connections
  
# bitcoin-cli help

== Blockchain ==
getbestblockhash
getblock "hash" ( verbose )
getblockchaininfo
getblockcount
getblockhash index
getchaintips
getdifficulty
getmempoolinfo
getrawmempool ( verbose )
gettxout "txid" n ( includemempool )
gettxoutsetinfo
verifychain ( checklevel numblocks )

== Control ==
getinfo
help ( "command" )
stop

== Generating ==
getgenerate
gethashespersec
setgenerate generate ( genproclimit )

== Mining ==
getblocktemplate ( "jsonrequestobject" )
getmininginfo
getnetworkhashps ( blocks height )
prioritisetransaction <txid> <priority delta> <fee delta>
submitblock "hexdata" ( "jsonparametersobject" )

== Network ==
addnode "node" "add|remove|onetry"
getaddednodeinfo dns ( "node" )
getconnectioncount
getnettotals
getnetworkinfo
getpeerinfo
ping

== Rawtransactions ==
createrawtransaction [{"txid":"id","vout":n},...] {"address":amount,...}
decoderawtransaction "hexstring"
decodescript "hex"
getrawtransaction "txid" ( verbose )
sendrawtransaction "hexstring" ( allowhighfees )
signrawtransaction "hexstring" ( [{"txid":"id","vout":n,"scriptPubKey":"hex","redeemScript":"hex"},...] ["privatekey1",...]
ighashtype )

== Util ==
createmultisig nrequired ["key",...]
estimatefee nblocks
estimatepriority nblocks
validateaddress "bitcoinaddress"
verifymessage "bitcoinaddress" "signature" "message"

== Wallet ==
addmultisigaddress nrequired ["key",...] ( "account" )
backupwallet "destination"
dumpprivkey "bitcoinaddress"
dumpwallet "filename"
encryptwallet "passphrase"
getaccount "bitcoinaddress"
getaccountaddress "account"
getaddressesbyaccount "account"
getbalance ( "account" minconf includeWatchonly )
getnewaddress ( "account" )
getrawchangeaddress
getreceivedbyaccount "account" ( minconf )
getreceivedbyaddress "bitcoinaddress" ( minconf )
gettransaction "txid" ( includeWatchonly )
getunconfirmedbalance
getwalletinfo
importaddress "address" ( "label" rescan )
importprivkey "bitcoinprivkey" ( "label" rescan )
importwallet "filename"
keypoolrefill ( newsize )
listaccounts ( minconf includeWatchonly)
listaddressgroupings
listlockunspent
listreceivedbyaccount ( minconf includeempty includeWatchonly)
listreceivedbyaddress ( minconf includeempty includeWatchonly)
listsinceblock ( "blockhash" target-confirmations includeWatchonly)
listtransactions ( "account" count from includeWatchonly)
listunspent ( minconf maxconf  ["address",...] )
lockunspent unlock [{"txid":"txid","vout":n},...]
move "fromaccount" "toaccount" amount ( minconf "comment" )
sendfrom "fromaccount" "tobitcoinaddress" amount ( minconf "comment" "comment-to" )
sendmany "fromaccount" {"address":amount,...} ( minconf "comment" )
sendtoaddress "bitcoinaddress" amount ( "comment" "comment-to" )
setaccount "bitcoinaddress" "account"
settxfee amount
signmessage "bitcoinaddress" "message"


# bitcoin.conf
rpcuser=SECRET
rpcpassword=SECRET
rpcport=8332
server=1
maxconnections=120
daemon=1
txindex=0
txconfirmtarget=1
sendfreetransactions=0
limitfreerelay=0
mintxrelayfee=0.001
listen=1
port=8333
onion=127.0.0.1:9150
bind=0.0.0.0
discover=1
addnode=155.94.64.98:8333
addnode=93.188.224.253:8333
addnode=77.240.112.3:8333
addnode=31.146.211.3:8333
