---
description: >-
  The process of onboarding a Host is designed to be as straightforward as
  possible.
---

# Set up a Host

### Prerequisites

1. Ensure your device meets the minimum specification (see [Network Nodes](https://wiki.edge.network/contributing-to-the-network/network-nodes))
2. Install Edge CLI
3. [Install Docker](https://docs.docker.com/get-docker/) (v18.06+ required)

{% hint style="info" %}
**Devices with higher performance/capacity will return a higher yield.**
{% endhint %}

### Process

Once the prerequisites are satisfied, the process to set up a host is as follows:

1. Create/restore a wallet
2. Create a stake
3. Assign the device to the stake
4. Start the node

{% hint style="info" %}
The instructions below refer to the `edge` mainnet CLI. If you are using the `edgetest` testnet CLI, simply substitute `edgetest` as appropriate.
{% endhint %}

#### Create/restore a Wallet

An XE wallet is required to participate in the network. This will hold your staked funds and earnings. An XE wallet consists of an XE address (which looks like `xe_abcd...`) and a private key.

Edge CLI allows you to use an existing wallet, or can create one for you if you need one.

**Create a wallet**

Run the following command for interactive setup:

```bash
edge wallet create
```

You will be asked to set a passphrase. This will be used to encrypt your new wallet. The setup will also offer you a copy of your private key so you can back it up securely.

**Restore a wallet**

If you have an XE wallet already, for instance from the [web wallet](https://wallet.xe.network), you can restore it with your private key using the following command:

```bash
edge wallet restore
```

You will be asked to provide your private key and a passphrase. The private key will be used to restore your wallet data, and the passphrase will encrypt it.

#### Create Stake

If you do not already have funds in your XE wallet, you will need to get acquire some before you can stake.

**Funding your wallet**

On the [Testnet (XE) Explorer](https://test.network) you can use the XE Automated Faucet to request funds.

On Mainnet, you will need to deposit EDGE to receive XE. This can be done via the [Web Wallet](https://wallet.xe.network).

**Creating a stake**

Now that you have funds, you can choose which type of stake to create. A stake allows network nodes to authenticate with the network, and can be one of the following three types:

* Host (`host`)
* Gateway (`gateway`)
* Stargate (`stargate`)

{% hint style="warning" %}
**Only Host onboarding is currently available to the community. More information about onboarding Gateway/Stargate nodes will be provided in future.**
{% endhint %}

Run the following command to create a Host stake:

```bash
edge stake create host
```

This will advise of the stake amount required and your remaining available balance after creating the stake. You will need your passphrase in order to decrypt your wallet and sign the staking transaction.

Once the stake is created, you will need to wait a few moments until it is processed by the blockchain. To check the status of your pending transaction, you can run `edge tx lsp`. To check whether your new stake is available, you can run `edge stake ls`.

#### Prepare Device

Now that you have a stake, you can add your device to the network to run a node corresponding to the stake type. Run the following command to set up your device interactively:

```bash
edge device add
```

You will need your passphrase again for this transaction. Once it has been submitted to the blockchain, it'll take around 1-2 minutes before you're ready to start your node.

Run `edge tx lsp` and/or `edge stake ls` to check its status.

#### Start Node

Once the transaction has been confirmed, you're ready to start your node.

Run the following command:

```bash
edge device start
```

This will download and start the node software, which should then run in the background and self-update. Your device is successfully onboarded!

#### Further Usage

Edge CLI offers a variety of functions for managing your wallet, stakes, transactions, and the device itself. Have a look at the Commands Overview for more information.

#### Help

If you're struggling or encountering issues, then join our Discord server and let us know in the #onboarding channel and one of the team or a community member will be happy to help.

**Apple Silicon M1 Chipsets**

If you're using the new Apple Silicon M1 chipsets you may run into an issue running the CLI. These new chips have additional requirements and while we work to fix these issues, you may need to run the following command to unlock the `edge` binary:

```
xattr -cr /usr/local/bin/edge
```
