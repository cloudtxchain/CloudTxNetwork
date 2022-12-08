# Run a CloudTx Validator
## Setting up a node
1. Git clone https://github.com/cloudtxchain/CloudTxNetwork.git

2. Copy source form node-example to root folder
```
cp -r CloudTxNetwork/node-example/CloudTx  /root/
```
3. Create an Account

```
cd /root/CloudTx
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake CLD coin, all you should do is sending your CLD coin to the CloudTx Consensus contract address over the CloudTx network from the validator address.
    The CloudTx Consensus contract address: 0xBc7EcA0C38F885312A08993EAB143E733F46E589
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to CloudTx and send the CLD coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /CloudTx/nodes/validator/keys/CloudTx/UTC--xxxx
    /CloudTx/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
