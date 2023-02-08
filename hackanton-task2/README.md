# Concordium-Hackanton-Task2

## Mainnet Address
4Gmodk64JAGqGjX5q5HNGjsg3qvYb6nLf8S14hnGUQpbmjRGXN

## 1. Deploy smart contract

Build using this command:

    cargo concordium build -e -o a.wasm.v1 -s schema.bin

![3_build](https://user-images.githubusercontent.com/36572181/217535931-ee9b38c3-4c3e-4741-a90f-5674bb5e83a5.jpg)


Deployed the contract with this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 module deploy a.wasm.v1 --name concordium_task2 --sender Wallet1

![4_deployed](https://user-images.githubusercontent.com/36572181/217536037-e283d9a0-baef-40ae-aa88-1b7276d217a6.jpg)


Once deployed, we can take the tx hash. Transaction hash: <br/>

    2fc13a3c5dc643445fcd7d7345461bcd6fab5e3c0c4d4b1c965b6d12c9383cfd


## 2. Initialized The Contract

After deployment, initialized the contract with this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 contract init concordium_task2 --contract concordium_task2 --sender Wallet1 --energy 10000
    
![5_init](https://user-images.githubusercontent.com/36572181/217536167-d5da9252-a774-40fd-82dc-fa988edd0fc1.jpg)



The transaction hash:

    c66ca56bb51299d2eeb32a4c6fc1073acc60da500697c2e928df6381c58c2899

## 3. Update Smart Contract

Create a json file with the paramater and then update contract using this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 contract update 2824 --entrypoint increment --energy 10000 --sender Wallet1 --parameter-json update-param.json

![7_UpdateParam](https://user-images.githubusercontent.com/36572181/217536417-c608e650-ec2e-4a55-9db1-bc225e31c671.jpg)

Transaction hash:

    5aa447fecf742a44a2ec5e880fb90b741e3de0ed6f62722763a1e995c7a4fb23

## 4. Invoke Contract

To invoke the contract, see if the state has been updated, use this command:

    concordium-client --grpc-ip node.testnet.concordium.com --grpc-port 10000 contract invoke 2824 --entrypoint view

 ![8_Invoke](https://user-images.githubusercontent.com/36572181/217536564-0f220353-1767-45ea-b5f3-6c1bd17535a1.jpg)

As seen in the picture. The contract has been updated and return value same as update-param.json.
