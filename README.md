# Substrate NFTs Node

The [Substrate](https://substrate.io/) NFTs node is a specialized blockchain for testing use cases with the [FRAME NFTs Pallet](https://github.com/paritytech/substrate/tree/master/frame/nfts). :rocket:

The purpose of this node is to provide developers with an easy way to experiment with the NFTs pallet in a sand-boxed environment.
This node may be useful for anyone making guides, tutorials or workshops that cover use cases for the NFTs Pallet.

> Checkout the [`manual-seal`](https://github.com/sacha-l/substrate-nfts-node/tree/manual-seal) branch to run a version of this node that only creates a new block when the node receives a valid transaction. This makes testing faster and will cover most use cases except for setting minting deadlines.

## Launch the chain

The easiest way to launch a node is to download the node's binary from the releases page.
Alternatively, you can build and launch the node locally.

### Download using release binaries

Launch the chain by downloading the binary in the releases page of this repository (macOS and Linux) and running the executable. 

### Build the node locally

Follow the [official installation steps](https://docs.substrate.io/install/) to set up all Substrate prerequisites.

Afterwards you can install this node using:

```bash
cargo install substrate-nfts-node --git https://github.com/sacha-l/substrate-nfts-node.git
```

Alternatively, you can clone this repo and build the node using this command:

```sh
cargo build --release
```

To launch the chain in development mode (recommended):

```sh
./target/release/substrate-nfts-node --dev
```

About Development mode:

- Maintains state in a `tmp` folder while the node is running.
- Uses the **Alice** and **Bob** accounts as default validator authorities.
- Uses the **Alice** account as the default `sudo` account.
- Has a preconfigured genesis state (`/node/src/chain_spec.rs`) that includes several pre-funded development accounts.

### Embedded Docs

After you build the project, you can use the following command to explore its parameters and subcommands:

```sh
./target/release/node-template -h
```

You can generate and view the [Rust Docs](https://doc.rust-lang.org/cargo/commands/cargo-doc.html) for this template with this command:

```sh
cargo +nightly doc --open
```

## Connect with Polkadot-JS Apps Front-End

After you start the node template locally, you can interact with it using the hosted version of the [Polkadot/Substrate Portal](https://polkadot.js.org/apps/#/explorer?rpc=ws://localhost:9944) front-end by connecting to the local node endpoint.
A hosted version is also available on [IPFS (redirect) here](https://dotapps.io/) or [IPNS (direct) here](ipns://dotapps.io/?rpc=ws%3A%2F%2F127.0.0.1%3A9944#/explorer).
You can also find the source code and instructions for hosting your own instance on the [polkadot-js/apps](https://github.com/polkadot-js/apps) repository.

## Alternatives Installations

Instead of installing dependencies and building this source directly, consider the following alternatives.

### Nix

Install [nix](https://nixos.org/), and optionally [direnv](https://github.com/direnv/direnv) and [lorri](https://github.com/nix-community/lorri) for a fully plug-and-play experience for setting up the development environment.
To get all the correct dependencies, activate direnv `direnv allow` and lorri `lorri shell`.

### Docker

Please follow the [Substrate Docker instructions here](https://github.com/paritytech/substrate/blob/master/docker/README.md) to build the Docker container for this node.