<h1>
  <img src="logo.png" alt="Logo" style="vertical-align: middle; margin-right: 10px; width: 50px; height: 50px;">
  IPFS-BlockchainLib
</h1>

## Installation

### Prerequisites

1. **Check Node.js and npm versions**
    ```sh
    node -v
    npm -v
    ```
    If your device doesn't have node.js, please install it first.

### Setting Up Node Version (if needed)

2. **Install nvm (Node Version Manager)**
    ```sh
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.2/install.sh)"
    ```

3. **Use nvm to install and use Node.js version 18**
    ```sh
    nvm install 18
    nvm use 18
    ```

### Installing Dependencies

4. **Install required npm packages**
    ```sh
    npm install --verbose
    ```

5. **Install Truffle globally**
    ```sh
    npm install -g truffle --verbose
    ```

### Running the Project

6. **Start the development server**
    ```sh
    npm start
    ```

## IPFS Deployment on Terminal

### Download and Install IPFS

1. Open terminal and download IPFS:
    ```sh
    wget https://dist.ipfs.tech/go-ipfs/v0.27.0/go-ipfs_v0.27.0_darwin-arm64.tar.gz
    ```

2. Extract the downloaded file:
    ```sh
    tar -xvzf go-ipfs_v0.27.0_darwin-arm64.tar.gz
    ```

3. Navigate to the extracted directory:
    ```sh
    cd go-ipfs
    ```

4. Install IPFS:
    ```sh
    sudo bash install.sh
    ```

5. Initialize IPFS:
    ```sh
    ipfs init
    ```

### Starting IPFS Daemon

Each time you open a terminal and want to start IPFS, run:
```sh
ipfs daemon
```
This command will keep the terminal running in daemon mode. Open a new terminal for other commands.

### Adding Files to IPFS

1. Open a new terminal and upload a file to IPFS:
    ```sh
    ipfs add <file-path>
    ```
    Output: `added <CID> filename`

2. You can access the file using its CID:
    - **Local Access**: `http://127.0.0.1:8080/ipfs/<CID>`
    - **Public Gateway Access**: `https://ipfs.io/ipfs/<CID>`

### Pinning Files (Optional)

Pinning files ensures they are available on the node:
```sh
ipfs pin add <CID>
```

### Other Useful Commands

- **Display Peer ID**:
    ```sh
    ipfs id
    ```
- **Download File with CID**:
    ```sh
    ipfs get <CID>
    ```

## MetaMask Browser Installation

### Why This Project Requires MetaMask

This project interacts with the Ethereum blockchain to record transactions and manage data securely. MetaMask acts as a bridge between your browser and the Ethereum blockchain, allowing you to manage Ethereum accounts and sign transactions directly from the browser.

### How to Install MetaMask

1. **Visit the MetaMask Website**:
    - Go to the [MetaMask website](https://metamask.io/).
2. **Install the Extension**:
    - Click on the "Download" button.
    - Choose your browser (e.g., Chrome, Firefox).
    - Follow the instructions to add the MetaMask extension.
3. **Set Up MetaMask**:
    - Click on the MetaMask icon in your browser toolbar.
    - Create a new wallet or import an existing one.
    - Securely store your seed phrase for account recovery.
4. **Connect MetaMask to the Project**:
    - Ensure MetaMask is connected to the correct Ethereum network (e.g., Mainnet, Ropsten).
    - Authorize the connection when prompted by the application.

## OrbitDB Setup

### Install OrbitDB

1. Install OrbitDB:
    ```sh
    npm install orbit-db
    ```

2. Install required dependencies:
    ```sh
    npm install @ipld/dag-cbor
    ```

## Local Blockchain Setup with Foundry

1. Install Foundry:
    ```sh
    curl -L https://foundry.paradigm.xyz | bash
    ```

2. Restart the terminal or follow the instructions from the output to complete the installation:
    ```sh
    foundryup
    ```

3. Verify installation:
    ```sh
    anvil --version
    ```

4. **Connect MetaMask to Anvil**:
    - **Network Name**: Anvil Localhost
    - **New RPC URL**: `http://127.0.0.1:8545`
    - **Chain ID**: 31337
    - **Currency Symbol**: ETH

5. Import an account using one of the private keys from the Anvil terminal output.

6. Connect MetaMask to the network and disable real account connections for testing purposes.

7. Refresh the application and continue uploading files or interacting with the blockchain.

## Start IPFS Library

Open 4 seperate terminals. 

1. For the first terminal, run 
    ```sh
    ipfs daemon
    ```

2. For the second terminal, run 
    ```sh
    node server.mjs
    ```

3. For the third terminal, run 
    ```sh
    anvil
    ```

4. For the first terminal, run 
    ```sh
    npm start
    ```
