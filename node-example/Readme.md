# Run a ECLAT Validator
## Setting up a node
1. Git clone https://github.com/ECLATWORLD/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/ECLAT  /root/
```
3. Create an Account

```
cd /root/ECLAT
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

    To stake ECLAT coin, all you should do is sending your ECLAT coin to the ECLAT Consensus contract address over the ECLAT network from the validator address.
    The ECLAT Consensus contract address: 0xcFEECa15E01323Efb82143C1Fa11B9925EfbF506
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to ECLAT and send the ECLAT coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /ECLAT/nodes/validator/keys/ECLAT/UTC--xxxx
    /ECLAT/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
