Potentials for blockchain at ZBank.

Tesnet Setup

In order to set up the Testnet we need to do the following :
•	Installs required There are two installs to complete 
•	MyCrypto
•	GoEthereum (known as Geth)
•	MyCrypto is a regular application. (Though you may need to allow some security permissions)                                                                         You can find the installation guide here.                                                                                                                           Geth has several different versions, so follow the install guide to download the correct one. It is a portable app that you'll need to create a folder and name it   HomeWork18 save this folder and to keep it somewhere handy.

Setup the custom out-of-the-box blockchain

•	Create “rose3” folder for your new network inside the HomeWork18 .
•	Create "Screenshots" folder inside of the project directory inside the HomeWork1
•	Create accounts for two nodes for the network open terminal and run the “geth“commands (line interface for running Ethereum node implemented in Go language. You     can join the Ethereum network transfer mine ETH.                                                                                                                     ./geth --datadir node1 account new                                                                                                                                   ./geth --datadir node2 account new 
  (look in the screenshots folder). 
•	Create a password =rose for each node
•	Copy the address Public and Private key of both nodes as follow:                                                                            
Node1                                                                                                                                                                   Public address of the key:   0xeE8fE1C80eaA67CFDf1C0FEA06B2663d88d71838                                                                                             Path of the secret key file: node1/keystore/UTC--2021-02-10T01-10-43.664002000Z--ee8fe1c80eaa67cfdf1c0fea06b2663d88d71838
Node2                                                                                                                                                                   Public address of the key:   0xCC2f6414dcD0A41cA6159Fe89aF8d87F74435179                                                                                             Path of the secret key file: node2/keystore/UTC--2021-02-10T01-13-38.904160000Z--cc2f6414dcd0a41ca6159fe89af8d87f74435179


Create a new network:

•	 In the terminal run the command   ./puppet  
•	 Name your network rose3 and select the option to configure a new genesis block, then select the option building from scratch.
•	Select the POA proof of authority consensus algorithm, a cryptographic consensus mechanism that requires less power and can run on relatively low-end hardware       compared to its precursors. PoA claims to score higher than traditional consensus algorithms such as Proof of Work (PoW) and Proof of Stake (PoS)
•	 When prompted paste both account addresses from the first step one at a time into the list of accounts to seal.                                                        eE8fE1C80eaA67CFDf1C0FEA06B2663d88d71838                 CC2f6414dcD0A41cA6159Fe89aF8d87F7443517                                                                •	Paste them again in the list of accounts to pre-fund. Don’t need to put any amount.
•	Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.
•	Export genesis configurations. This will fail to create two of the files, but you only need rose3.json.
•	Chose for the ID number. 2009
•	You can delete the rose3harmony.json file from HomeWork18 folder and create “rose3network” folder for rose3.json inside the HomeWork18
•	In terminal initialize each node with the new rose3.json with geth command  
    ./geth --datadir node1 init rose3.json                                                                                       			                                   ./geth --datadir node2 init rose3.jso]                                                                                                       	                     There is a screenshot of puppet configuration
•	 In the  terminal  run the first node, unlock the account, enable mining, and the RPC flag. 
•	Only one node needs RPC enabled running this command Node 1 start mining
    ./geth --datadir node1 --unlock "eE8fE1C80eaA67CFDf1C0FEA06B2663d88d71838" --mine --nodiscover --rpc --allow-insecure-unlock
•	 When prompted don’t forget to add the password= rose and copy the ” enode “ description. Keep it running 
    "enode://18da8e8bdc78e33476b9f04e7242105af946d34418a5f7fe9b96a721f00e2eb6a973d8cdf2d3da00eae2028d0afd994748fb0ba1459cbabaaa16d0d7e17c283b@127.0.0.1:30303?            discport=0"
•	Open a second terminal shell  Set a different peer port for the second node and use the first node's enode address as the bootnode as follows                          /geth --datadir node2 --unlock "C2f6414dcD0A41cA6159Fe89aF8d87F74435179" --mine --port 30304 --bootnodes                                         "enode://18da8e8bdc78e33476b9f04e7242105af946d34418a5f7fe9b96a721f00e2eb6a973d8cdf2d3da00eae2028d0afd994748fb0ba1459cbabaaa16d0d7e17c283b@127.0.0.1:30303?    discport=0"--allow-insecure-unlock –nodiscover
•	Use the password for the second node to unlock the account.
•	If. Everything runs smoothly you should see the creation of new blocks.
	
•	Send a test transaction

•	Use the MyCrypto GUI wallet to connect to the node with the exposed RPC port.
•	You will need to use a custom network rose3, and include the chain ID 2009, use ETH as the currency and use the url to point the default port on your local         machine. Click and save the custom node.
•	 Import the keystore file from the node1/keystore directory                                                                                                          UTC--2021-02-10T01-10-43.664002000Z-ee8fe1c80eaa67cfdf1c0fea06b2663d88d71838 into MyCrypto.This will import the private key.
•	Send a transaction from the node1 account to the node2 account.
•	Copy the transaction hash and paste it into the "TX Status" section of the app, or click "TX Status" in the popup.                   
•	Screenshot the transaction metadata (status, tx hash, block number, etc) and save it to your Screenshots folder.

•	And as Julia said Voila!!  Your Testnet is done
