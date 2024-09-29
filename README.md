
# Project: Custom Subnet Creation


## Project Overview

This project aims to create a custom virtual machine using the HyperSDK framework to facilitate minting and transferring tokens. It enables users to build a tailored blockchain solution that supports token creation, asset transfer, and trading via order books.

The goal is to provide a streamlined process for developers looking to implement blockchain features into their applications, leveraging the power of HyperSDK for scalability and customization.


## Prerequisites

Ensure the following tools are installed before proceeding:

1. **WSL (Windows Subsystem for Linux)**:  
   - This project is developed using Ubuntu on WSL.
   
2. **Go Programming Language**:  
   - Install Go using the following command:
     ```bash
     sudo snap install go --classic
     ```
   - Verify the installation:
     ```bash
     go version
     ```

3. **GCC (GNU Compiler Collection)**:  
   - Install GCC on WSL:
     ```bash
     sudo apt update
     sudo apt install build-essential
     ```
   - Verify the installation:
     ```bash
     gcc --version
     ```

## Installation Steps

1. **Clone the repository**:
   ```bash
   git clone https://github.com/jasrotia15/Create-a-Custom-Subnet.git
   ```

2. **Open the repository in VS Code**:
   - From the Ubuntu terminal, run:
     ```bash
     code .
     ```

3. **Install dependencies**:
   - Open a terminal in VS Code and run:
     ```bash
     go mod tidy
     ```

4. **Ensure Go is in your system PATH**:
   - Run:
     ```bash
     export PATH=$PATH:$(go env GOPATH)/bin
     ```
   - If this doesn’t work, try:
     ```bash
     export PATH=$PATH:/usr/local/go/bin
     ```

## Running the Project

1. **Launch the Subnet**:
   ```bash
   MODE="run-single" ./scripts/run.sh
   ```
   > **Note**: This process may take a few minutes.

2. **Build the project**:
   ```bash
   ./scripts/build.sh
   ```
   - The compiled CLI will be available at `./build/token-cli`.

3. **Import the demo private key**:
   ```bash
   ./build/token-cli key import demo.pk
   ./build/token-cli chain import-anr
   ```

4. **Interact with the HyperChain**:

   - **Create an asset**:
     ```bash
     ./build/token-cli action create-asset
     ```
   - **Mint your asset**:
     ```bash
     ./build/token-cli action mint-asset
     ```
   - **View account balance**:
     ```bash
     ./build/token-cli key balance
     ```
   - **Transfer tokens**:
     ```bash
     ./build/token-cli action transfer
     ```
   - **Create an order**:
     ```bash
     ./build/token-cli action create-order
     ```
   - **Fill an order**:
     ```bash
     ./build/token-cli action fill-order
     ```
   - **Close an order**:
     ```bash
     ./build/token-cli action close-order
     ```

## Troubleshooting


## Troubleshooting

Here are some common issues you might encounter while running the project and how to resolve them:

1. **Issue**: Go command not recognized.  
   **Solution**: Ensure that Go is properly installed and that the correct PATH is set. Run:
   ```bash
   export PATH=$PATH:/usr/local/go/bin
   ```

2. **Issue**: Network issues when launching the subnet.  
   **Solution**: Check that all necessary dependencies are installed, and ensure no conflicting processes are running. Try stopping all processes:
   ```bash
   killall avalanche-network-runner
   ```

3. **Issue**: Build script fails.  
   **Solution**: Make sure all dependencies are installed by running:
   ```bash
   go mod tidy
   ```


## Monitoring On-Chain Activity

Watch real-time on-chain activity by running:
```bash
./build/token-cli chain watch
```

## Contributing


## Contributing

We welcome contributions from the community! Here's how you can contribute:

1. **Fork the Repository**: Create a fork of the repository to make your changes.
2. **Create a Branch**: Make a new branch for your changes:
   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Submit a Pull Request**: Once your changes are ready, submit a pull request for review.
4. **Ensure Code Quality**: Follow coding standards and best practices. Check for issues using linters and run all tests before submitting.

Feel free to open an issue if you encounter bugs or have suggestions for enhancements.


## License


## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.


## Acknowledgements

This project is based on the [TokenVM](https://github.com/Metacrafters/tokenvm.git). Special thanks to the Metacrafters team for their contributions to the blockchain community.
