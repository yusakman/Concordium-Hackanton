# Concordium-Hackanton-Task1

## Mainnet Address
4Gmodk64JAGqGjX5q5HNGjsg3qvYb6nLf8S14hnGUQpbmjRGXN

## 1. Install Rust and Wasm

Navigate to [Rustup](https://rustup.rs/) to install Rust.  Install it on your system by choosing number 1. 

We'll see the picture below once done:
![Pict 1](https://user-images.githubusercontent.com/36572181/217238563-7826d09a-628c-488d-9045-fd438605ea31.jpg)

Also you can check with this command:

    rustup -h

Next don't forget to install wasm. Run this command in your terminal:

    rustup target add wasm32-unknown-unknown

Once completed we'll see the picture below:<br/>

![2](https://user-images.githubusercontent.com/36572181/217240416-3285ce5e-23aa-4b84-9529-053d884876f9.jpg)

## 2. Install Cargo Concordium

Navigate to [this](https://developer.concordium.software/en/mainnet/net/installation/downloads-testnet.html#cargo-concordium-testnet) to install Cargo Concordium.

Rename cargo-concordium v2.7.0 to cargo-concordium

Move it to **%HOMEPATH%\.cargo\bin\ for Windows**

Once done, we can check if this command works:

    cargo concordium --help

You can see the picture below: <br/>
![3](https://user-images.githubusercontent.com/36572181/217241605-a0b3b15e-c314-4200-982d-48cf6d6cd868.jpg)

## 3. Install Concordium Client

Navigate to [this](https://developer.concordium.software/en/mainnet/net/installation/downloads-testnet.html#concordium-node-and-client-download-testnet) to Install Concordium Client.

Move it to **%HOMEPATH%\.cargo\bin\ for Windows** 

Run this command:

    concordium-client --help

As seen in the picture below:

![4](https://user-images.githubusercontent.com/36572181/217242318-6528988e-46c0-4ddb-af98-98847e83296a.jpg)

Now run this command to connect to the public node:

    concordium-client consensus status --grpc-port 10000 --grpc-ip node.testnet.concordium.com

See the picture below: <br/>

![5](https://user-images.githubusercontent.com/36572181/217242904-fd357bab-c5c5-46e2-9abe-1c9587f852f2.jpg)

## 4. Install Web Based Wallet

Navigate to [this](https://chrome.google.com/webstore/detail/concordium-wallet/mnnkpffndmickbiakofclnpoiajlegmg?hl=en-US) to install the web based wallet.

## 5. Create a Testnet Account

Once installed the web wallet. Create a testnet account by choosing the Concordium Testnet. <br/>

![6](https://user-images.githubusercontent.com/36572181/217243736-5c56225e-9c4d-4b14-b732-ca840311163b.jpg)

No need to provide an id for the testnet.

## 6. Acquiring testnet CCD via the CCD faucet

After we create the testnet account. Go to the trasanction in the web app, we'll see that we can request a faucet. And after that, the transfer will start, as seen below:

![8](https://user-images.githubusercontent.com/36572181/217244139-3e77b8e6-c4a3-40a7-89eb-de53d241e42a.jpg)

## 7. Export the account from web wallet and import it into concordium client

Navigate to the **Setting** in the Web Wallet and **Export Private Key**:<br/>

![9](https://user-images.githubusercontent.com/36572181/217244940-2097a35a-e72e-4e87-8b42-99bee6ba47d0.jpg)

Move it to a folder so it'll be easy to access. And run the command:

    concordium-client config account import <YOUR PUBLIC ADDRESS.export> --name <Your-Wallet-Name>

After created the encrypt password. We'll be able to see this message in the command:


![7](https://user-images.githubusercontent.com/36572181/217245340-dc131ed5-e2ae-41ee-bf15-9d45a74a85d6.jpg)
