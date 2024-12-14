# Alerim (AIM) Token

A Solana-based cryptocurrency featuring referral rewards and automated investment allocation.

## Features

- Referral rewards up to 20% of minted tokens
- Automated investment allocation
- Integration with Phantom Wallet
- Web-based exchange interface

## Setup Instructions

1. Install dependencies:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
cargo install --git https://github.com/coral-xyz/anchor --tag v0.26.0 anchor-cli --locked
```

2. Build the program:
```bash
anchor build
```

3. Deploy to Solana devnet:
```bash
solana config set --url devnet
anchor deploy
```

4. connect to ssh server:
ssh root@147.78.130.55

## Ubuntu Server Installation

1. Update and upgrade your system: 
```bash
sudo apt update && sudo apt upgrade -y
```

2. Install required system dependencies:
```bash
sudo apt install -y build-essential git curl pkg-config libssl-dev libudev-dev
```

3. Install Rust and Cargo:
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
source $HOME/.cargo/env
```

4. Install Solana CLI:
```bash
# Download and install Solana tools
wget https://github.com/solana-labs/solana/releases/download/v1.17.9/solana-release-x86_64-unknown-linux-gnu.tar.bz2
tar jxf solana-release-x86_64-unknown-linux-gnu.tar.bz2
export PATH="$PWD/solana-release/bin:$PATH"
echo 'export PATH="$PWD/solana-release/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc

# Verify installation
solana --version
solana-keygen --version
```

5. Install Anchor Framework:
```bash
cargo install --git https://github.com/coral-xyz/anchor --tag v0.27.0 anchor-cli --locked
```

6. Clone and build the project:
```bash
git clone <your-repository-url>
cd alerim-token
anchor build
```

7. Configure Solana for deployment:
```bash
# Generate a new keypair for your Solana wallet
solana-keygen new

# Configure CLI to use Solana's devnet cluster
solana config set --url devnet

# Check your configuration
solana config get

# Get some devnet SOL tokens for testing
solana airdrop 2

# Verify your balance
solana balance
```

Note: The devnet configuration is for testing. For mainnet deployment, use `solana config set --url mainnet-beta`

Important configuration details:
- Your keypair file will be saved in `~/.config/solana/id.json`
- Keep this keypair secure and never share it
- Devnet SOL tokens are free but have no real value
- You can request up to 2 SOL per airdrop on devnet

8. Deploy the contract:
```bash
anchor deploy
```

Note: Make sure to securely store your keypair file and have sufficient SOL in your wallet for deployment.

## Smart Contract Structure

- `lib.rs`: Main contract logic
  - Token initialization
  - Minting with referral rewards
  - Investment allocation

## Testing

Run tests with:
```bash
anchor test
```
