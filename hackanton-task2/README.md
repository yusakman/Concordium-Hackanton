# Concordium-Hackanton-Task1

## Mainnet Address
4Gmodk64JAGqGjX5q5HNGjsg3qvYb6nLf8S14hnGUQpbmjRGXN

## 1. Deploy smart contract

Build using this command:

    cargo concordium build -e -o a.wasm.v1 -s schema.bin

Deployed the contract with this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 module deploy a.wasm.v1 --name concordium_task2 --sender Wallet1

Once deployed, we can take the tx hash. Transaction hash: <br/>

    2fc13a3c5dc643445fcd7d7345461bcd6fab5e3c0c4d4b1c965b6d12c9383cfd


## 2. Initialized The Contract

After deployment, initialized the contract with this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 contract init concordium_task2 --contract concordium_task2 --sender Wallet1 --energy 10000

The transaction hash:

    c66ca56bb51299d2eeb32a4c6fc1073acc60da500697c2e928df6381c58c2899

## 3. Update Smart Contract

Create a json file with the paramater and then update contract using this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 contract update 2824 --entrypoint increment --energy 10000 --sender Wallet1 --parameter-json update-param.json

Transaction hash:

    5aa447fecf742a44a2ec5e880fb90b741e3de0ed6f62722763a1e995c7a4fb23

## 4. Invoke Contract

To invoke the contract, see if the state has been updated, use this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 contract invoke 2824 --entrypoint view
 