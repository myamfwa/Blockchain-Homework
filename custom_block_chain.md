## Custom Block Chain File

This file outlines the steps required to create accounts for two nodes for the custom blockchain network with a separate datadir for each usting the ethereum tool geth.

---

### Set up the two nodes

(1) Run puppeth and name network and select 'configure a new genesis block' then 'create new genesis from scratch'. 

(2) Choose the Clique (Proof of Authority) consensus algorithm.

(3) Provide selected account from MyCrypto wallet to pre-fund.

(4) Continue the rest of the prompts and choose 'Manage existing genesis' option.

(5) Export genesis configurations. This will fail to create two of the files. only require homework.json file.

(6) initialize each node with a new homework.json with geth. NOTE: you will need to set a password for each node created.

(7) Exit puppeth using Ctrl+C keys combination.

(8) Create first node's data directory using geth command.

(9) Node1 public key and secret key will be created & Repeat #8 to create the second node (different name).

(9) Using geth, initialize each node with the new networkname.json.

./geth --datadir node1 init networkname.json
./geth --datadir node2 init networkname.json

(10) To mine: Run the nodes in separate terminal windows with the commands:

./geth --datadir node1 --unlock "SEALER_ONE_ADDRESS" --mine --rpc --allow-insecure-unlock
./geth --datadir node2 --unlock "SEALER_TWO_ADDRESS" --mine --port 30304 --bootnodes "enode://SEALER_ONE_ENODE_ADDRESS@127.0.0.1:30303" --ipcdisable --allow-insecure-unlock


### Send a test transaction via MyCrypto

(1) Use Custom network, chain ID, and ETH (currency).

(2) Import keystore file from node1/keystore direcotry into MyCrypto.

(3) Send a transaction from the node1 account to node2 account. 

(4) Copy transaction hash and paste it into the 'TX Status' section of the app or click 'TX Status in the popup. 

(5) Confirmation of transaction: 

