## Warning
**NEVER USE THIS ON PRODUCTION!!**


##Requeriments

- Linux System (For this tutorial i'm using Ubuntu 16.04.1)-
- Geth & Tools (I'm using 1.8.22)  - Install instructions: https://geth.ethereum.org/install/ 
- Basic knowledge about Ethereum BlockChain and PoA



## Starting network

### Start bootnode

    blockchaindev$ bootnode -nodekey boot.key -verbosity 9 -addr 127.0.0.1:30310
    
    blockchaindev$ bootnode -nodekey boot.key -writeaddress 
    685c3cb19746caf3a935d56edeebde3eb968a0bf47
    d43bb0b0dcbdd41a6bb181c46308525235ad8e5aba
    fa2291b076a19a0753d3433e809605097b72e95603ca

### Start sealer1

    blockchaindev$ geth --datadir sealer1/ --syncmode 'full' --port 30311 --rpc --rpcaddr 'localhost' 
    --rpcport 8501 --rpcapi 'personal,db,eth,net,web3,txpool,miner' 
    --bootnodes 'enode://685c3cb19746caf3a935d56edeebde3eb968a0bf47d43bb0b0dcbdd41a6bb181c46308525235ad8e5abafa2291b076a19a0753d3433e809605097b72e95603ca@127.0.0.1:30310' 
    --networkid 20190306 --gasprice '1' -unlock '0xc71dfcea0596fc9b8ae809e3d5977374240c5561' 
    --password sealer1/password.txt --mine

### Start sealer2

    blockchaindev$ geth --datadir sealer2/ --syncmode 'full' --port 30312 --rpc --rpcaddr 'localhost' 
    --rpcport 8502 --rpcapi 'personal,db,eth,net,web3,txpool,miner' 
    --bootnodes 'enode://685c3cb19746caf3a935d56edeebde3eb968a0bf47d43bb0b0dcbdd41a6bb181c46308525235ad8e5abafa2291b076a19a0753d3433e809605097b72e95603ca@127.0.0.1:30310' 
    --networkid 20190306 --gasprice '1' -unlock '0xfcb714af603d7a5e839c93bd30dee4cfd991ba7a' 
    --password sealer2/password.txt --mine

Enjoy :)

