# Setting up a Host

Onboarding is now open for Host nodes on the Edge network, with support for:

* Linux based x64/arm64 devices
* MacOS x64/arm64 devices
* Windows x64/arm64 devices

## Minimum Specifications

To see the minimum required device specifications, please take a look at [Network Nodes](https://wiki.edge.network/contributing-to-the-network/network-nodes).

{% hint style="info" %}
**Devices with higher performance/capacity will return a higher yield**
{% endhint %}

## Installation Process

The process of onboarding a host has been designed to be as straightforward as possible.

The process is as follows:

1. Install Docker (vs. 18.06+)
2. Install Edge CLI (`edge`)
3. Create/restore a wallet
4. Create a stake
5. Assign the device
6. Start node

{% hint style="info" %}Prefer a visual guide? Check out the tutorial by community member Pod. {% endhint %}

{% embed url="https://wiki.edge.network/contributing-to-the-network/setup-host/staking-gui" %}

### Install Edge CLI

Browse [Edge Network Files](https://files.edge.network/cli/) to find the right build of CLI for your system, and download it to an executable path.

Note that there are separate builds for mainnet and testnet so make sure you download the right one for your purposes.

For example, to download the mainnet CLI on an Ubuntu x64 host:

```bash
curl -s https://files.edge.network/cli/mainnet/linux/x64/latest/edge -o /usr/local/bin/edge && chmod +x /usr/local/bin/edge
```

In the same path as the file you downloaded, you can find a checksum file which you can compare against to ensure your download was not corrupted. If you downloaded the latest Linux x64 build (as above), you would find its checksum [here](https://files.edge.network/cli/mainnet/linux/x64/latest/checksum).

```bash
sha256 $(which edge)
```

You only need to manually download Edge CLI once. Afterwards, you can use `edge update` to automatically update the CLI, including checksum validation.

{% hint style="info" %}
**When you download an Edge CLI binary, it's recommended to keep the original filename i.e.** `edge` **for mainnet and** `edgetest` **for testnet to help distinguish them on your own system.**
{% endhint %}

### Create/Restore Wallet

Now you have Edge CLI installed, you need to set up an XE wallet for it to use. If you already have an existing wallet then you can restore that using your private key, alternatively, you can create a new wallet.

#### Create a wallet

If you do not already have an XE wallet, CLI can create one for you. Run this command for an interactive setup:

```bash
edge wallet create
```

You will be asked to set a passphrase. This will be used to encrypt your new wallet. The setup will also offer you a copy of your private key so you can back it up securely.

#### Restore a wallet

If you already have an XE wallet and have the private key in hand, run this command to restore it for CLI to use:

```bash
edge wallet restore
```

You will be asked to provide your private key and a passphrase. The private key will be used to restore your wallet, and the passphrase will encrypt it.

### Create Stake

If you do not already have funds in your XE wallet, you will need to get acquire some before you can stake.

#### Funding your wallet

On the [Testnet (XE) Explorer](https://test.network) you can use the XE Automated Faucet to request funds.

On Mainnet, you will need to deposit EDGE to receive XE. This can be done via the [Web Wallet](https://wallet.xe.network).

#### Creating a stake

Now that you have funds, you can choose which type of stake to create. A stake allows network nodes to authenticate with the network, and can be one of the following three types:

* Host (`host`)
* Gateway (`gateway`)
* Stargate (`stargate`)

{% hint style="info" %}
**Only Host onboarding is currently available to the community. More information about onboarding Gateway/Stargate nodes will be provided in future.**
{% endhint %}

Run the following command to create a Host stake:

```bash
edge stake create host
```

This will advise of the stake amount required and your remaining available balance after creating the stake. You will need your passphrase in order to decrypt your wallet and sign the staking transaction.

Once the stake is created, you will need to wait a few moments until it is processed by the blockchain. To check the status of your pending transaction, you can run `edge tx lsp`. To check whether your new stake is available, you can run `edge stake ls`.

### Prepare Device

Now that you have a stake, you can add your device to the network to run a node corresponding to the stake type. Run the following command to set up your device interactively:

```bash
edge device add
```

You will need your passphrase again for this transaction. Once it has been submitted to the blockchain, it'll take around 1-2 minutes before you're ready to start your node.

Run `edge tx lsp` and/or `edge stake ls` to check its status.

### Start Node

Once the transaction has been confirmed, you're ready to start your node.

Run the following command:

```bash
edge device start
```

This will download and start the node software, which should then run in the background and self-update. Your device is successfully onboarded!

### Further Usage

Edge CLI offers a variety of functions for managing your wallet, stakes, transactions, and the device itself. To display information about CLI commands and options, add `-h` or `--help` to any command, for example:

```bash
edge tx ls -h
```

### Help

If you're struggling or encountering issues, then join our Discord server and let us know in the #onboarding channel and one of the team or a community member will be happy to help.

#### Apple Silicon M1 Chipsets

If you're using the new Apple Silicon M1 chipsets you may run into an issue running the CLI. These new chips have additional requirements and while we work to fix these issues, you may need to run the following command to unlock the `edge` binary:

```
xattr -cr /usr/local/bin/edge
```
