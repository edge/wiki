# Edge CLI

{% hint style="info" %}
**This document is written for Edge CLI v1.5.3 and may not be up to date or necessarily complete. The output shown in examples may also change over time. The most accurate and up-to-date documentation is available as helptext within Edge CLI itself. Access helptext by adding** `--help` **to any command, for example** `edge --help` **or** `edge tx ls --help`
{% endhint %}

{% hint style="info" %}
**All usage examples here refer to the** `edge` **binary for continuity, but some examples actually use testnet data. Do not take information displayed in examples from this page as authoritative - it is for illustrative purposes only.**
{% endhint %}

* [Global options](./#global-options)
* [Wallet](./#wallet)
* [Transaction](./#transaction)
* [Stake](./#stake)
* [Device](./#device)
* [About Edge](./#about-edge)

## Global options

Edge CLI includes some global options that affect all commands. These can be provided before or after the sub-command.

### Wallet option

The `-w, --wallet <file>` option allows you to specify a different path to your wallet than the default. This may be useful if the default path is not usable or you want to use multiple wallets.

The wallet is stored in a single JSON file, so the `<file>` should not be a directory.

### Verbose option

The `-v, --verbose` option toggles greater verbosity in output. For example, CLI by default truncates stake hashes for readability:

```
% edge stake ls | awk '/Hash/ {print $2}' | head -n 1
f151dfbb9bb9
```

With greater verbosity, the full hash is shown:

```
% edge stake ls -v | awk '/Hash/ {print $2}' | head -n 1
f151dfbb9bb924c13a55d11ebaef4a49c061e849300ce101c5c0850fe9516499
```

### Debug option

The `--debug` option enables detailed output for complete visibility of CLI's behaviour. It also enables greater detail of any errors that may occur. This may be useful if you are having problems with CLI and you (or Edge support) need more information about what is happening.

{% hint style="warning" %}
**The debug option effects **_**very**_** noisy, sometimes abstruse output and its use is discouraged when not absolutely necessary.**
{% endhint %}

{% hint style="info" %}
**The debug option may be useful for understanding if you intend to contribute to** [**the CLI codebase**](https://github.com/edge/cli)**.**
{% endhint %}

### Other options

Other global options include disabling output colours with `--no-color` and specifying Docker connectivity (for `device` commands) with `--docker-socket-path`. You can see all available global options by running `edge --help`.

Global options are not displayed when viewing the helptext for specific commands, but are available to all commands nevertheless.

## Wallet

Wallet commands enable you to manage the XE wallet used by CLI. You can use a single wallet across multiple devices, or different wallets, depending on your needs.

### Create a Wallet

```bash
edge wallet create
```

This command creates a new XE wallet. This is an interactive command that asks you for a passphrase and private key export preference. Example:

```
% edge wallet create
A wallet already exists. Overwrite? [yn] y

To ensure your wallet is secure it will be encrypted locally using a passphrase.

Please enter a passphrase:
Please confirm passphrase:

Wallet xe_6B4C26b2BC0Fa4AA7B182266eEB5AdFba83AD998 created.

Would you like to (v)iew or (e)xport your private key? [ven] e
Enter filename to export private key to: my.key

Private key saved to my.key.
```

{% hint style="info" %}
If you choose not to view or export your private key, you can still retrieve it later using the `edge wallet info` command. See 'Display Information' below.
{% endhint %}

You can use this command non-interactively by providing all the options upfront. Example:

```
% edge wallet create -f -p 'mypassphrase' -K my.key
Wallet xe_6926C5ED28aAF6Aa12D842029fF81b014F107450 created.

Private key saved to my.key.
```

Run `edge wallet create --help` for more information on options.

### Restore a Wallet

```bash
edge wallet restore
```

This command restores an XE wallet. This is an interactive command that asks you for a private key and passphrase. Example:

```
% edge wallet restore
Please enter a private key:

To ensure your wallet is secure it will be encrypted locally using a passphrase.

Please enter a passphrase:
Please confirm passphrase:

Wallet xe_1c0561A342099962cD4a699f55DCfb9Fd6772bf2 restored.
```

Similarly to the create command, this command can be used non-interactively by providing all options upfront. Run `edge wallet restore --help` for more information on options.

### Display Information

```bash
edge wallet info
```

This command displays XE wallet information. By default it will only display the wallet address:

```
% edge wallet info
Address: xe_E82c7c2320b5F38A00ee5275E228eE708f79e3f8
```

If the `-p, --passphrase` or `-P, --passphrase-file` option is specified, the private key is also shown:

```
% edge wallet info -P passphrase.txt
Address: xe_E82c7c2320b5F38A00ee5275E228eE708f79e3f8
Private key: [REDACTED FOR WIKI]
```

### Display Balance

```bash
edge wallet balance
```

This command displays your current XE wallet balance.

```
% edge wallet balance
Address: xe_1c0561A342099962cD4a699f55DCfb9Fd6772bf2
Balance: 706,168.950000 XE
```

### Forget Wallet

```bash
edge wallet forget
```

This command forgets (deletes) your XE wallet. If no wallet is found, it has no effect.

```
% edge wallet forget
Address: xe_A0505511d43D98BAf391f0801a9C589291F8D645

Are you sure you want to forget this wallet? [yn] y

Your wallet is forgotten.
```

## Transaction

Transaction commands enable you to send XE to other wallets and display historic transactions to/from your wallet.

For ease of use, the command `edge transaction ...` can be abbreviated to `edge tx ...` as shown in usage examples.

### Send a Transaction

```bash
edge tx send <amount> <wallet>
```

This command sends a specified XE `<amount>` to the given `<wallet>` address. The amount can be specified in XE or mXE (0.000001 XE) by providing the unit e.g. `100xe` or `100mxe`. If no unit is given, XE is assumed.

You must provide your passphrase to sign the transaction.

An example of sending 10 XE to the testnet supply wallet:

```
% edge tx send 10 xe_00009f6354aa0449eACA1Af54FCf7171cAc85cB7
You are sending 10.000000 XE to xe_00009f6354aa0449eACA1Af54FCf7171cAc85cB7.
10.000000 XE will be deducted from your wallet. You will have 705,533.950000 XE remaining.

Proceed with transaction? [yn] y

This transaction must be signed with your private key.
Please enter your passphrase to decrypt your private key, sign your transaction, and submit it to the blockchain.

Passphrase:

Your transaction has been submitted and will appear in the explorer shortly.

https://test.network/transaction/a3a2067139179c2ac390a23e3000b023f7b3ac2401aec2846c5d27513e809669
```

This command can be used non-interactively by providing all options upfront. Run `edge tx send --help` for more information on options.

### List Transactions

```bash
edge tx list|ls
```

This command lists historic transactions to/from your XE wallet, from most recent to oldest. You can paginate transactions with the `-l, --limit` and `-p, --page` options. If these are not set, it will fetch your 10 most recent transactions.

An example fetching one (the most recent) transaction:

```
% edge tx ls -l 1
Page 1/98

Tx:        a3a2067139179c2ac390a23e3000b023f7b3ac2401aec2846c5d27513e809669
Nonce:     83
Block:     126409
At:        2022-00-02 13:30:41
To:        xe_00009f6354aa0449eACA1Af54FCf7171cAc85cB7
Amount:    10.000000 XE
Signature: ba3a8e549beb67c95da29e7ba4365a10cc2743e336fca68ed1edb094676041bb6478aa4d88c9eb820969428615172f08062c4a523cceef1ede98c2214a88561601
```

### List Pending Transactions

```bash
edge tx list-pending|lsp
```

This command lists any pending transactions that have not yet been processed by the XE blockchain. There are no options for this command.

## Stake

Stake commands enable you to manage your stakes on the XE blockchain. A stake is required for each device with which you intend to contribute computing power to the Edge network.

### Display Staking Information

```bash
edge stake info
```

This is an informational command that displays current staking amounts, as configured on the XE blockchain.

```
% edge stake info
Current staking amounts:
  Stargate: 250,000.000000 XE
  Gateway:   25,000.000000 XE
  Host:         100.000000 XE
```

### Create a Stake

```bash
edge stake create <type>
```

This command creates a stake which, once processed by the XE blockchain, allows you to run a device of the specified `<type>`.

{% hint style="info" %}
\*\*The types available are Host `host`, Gateway `gateway`, and Stargate `stargate`. At this time, only Host stakes are available to contributors. Access to create Gateway and Stargate stakes will be updated in future.
{% endhint %}

Your stake will be created via a blockchain transaction, signed using your private key. You will need to enter the passphrase for your XE wallet to decrypt your private key for this purpose.

An example of creating a Host:

```
% edge stake create host
You are staking 100.000000 XE to run a Host.
100.000000 XE will be deducted from your available balance. You will have 703,668.950000 XE remaining.

Proceed with staking? [yn] y

This transaction must be signed with your private key.
Please enter your passphrase to decrypt your private key, sign your transaction, and submit it to the blockchain.

Passphrase:

Your transaction has been submitted and will appear in the explorer shortly.

https://test.network/transaction/0b86daf2b729fb5d1fea8f8b41d8b2907358cb11dc052b3451c9fc0b0763bc0f
```

This command can be used non-interactively by providing all options upfront. Run `edge stake create --help` for more information on options.

### List Stakes

```bash
edge stake list|ls
```

This command displays all stakes associated with your wallet. For example, the stake that was created above:

```
% edge stake list | head -n 7
ID:      1a6e6511e3f8
Hash:    1df3e124915c
Tx:      0b86daf2b729fb5d1fea8f8b41d8b2907358cb11dc052b3451c9fc0b0763bc0f
Created: 2022-01-26 11:14:18
Amount:  100.000000 XE
Type:    Host
Status:  Active
```

### Unlock a Stake

```bash
edge stake unlock <id>
```

Unlocking a stake places the associated XE funds in a waiting period (currently 90 days) after which they can be released back to your XE wallet balance.

For ease of use, you can enter a truncated stake ID (minimum 3 characters).

For example, unlocking the stake created above:

```
% edge stake unlock 1a6e6511e3f8
You are requesting to unlock a Host stake.
After the unlock wait period of 90 days, you will be able to release the stake and return 100.000000 XE to your available balance.

Proceed with unlock? [yn] y

This transaction must be signed with your private key.
Please enter your passphrase to decrypt your private key, sign your transaction, and submit it to the blockchain.

Passphrase:

Your transaction has been submitted and will appear in the explorer shortly.

https://test.network/transaction/050b5ae60652e8578a6ab415c5352874dd60c4a2987c7ec90451ca3793aa7431
```

This command can be used non-interactively by providing all options upfront. Run `edge stake unlock --help` for more information on options.

### Release a Stake

```bash
edge stake release <id>
```

This command releases an unlocked stake, returning its funds to your XE wallet balance.

For ease of use, you can enter a truncated stake ID (minimum 3 characters).

To reclaim the full amount, your stake must have exited the unlock wait period (currently 90 days). Alternatively, you may use the `-e, --express` option to immediately release the stake for a fee.

For example, express-releasing the stake created above:

```
% edge stake release 1a6e6511e3f8 -e
You are releasing a Host stake.
1,875.000000 XE will be returned to your available balance after paying a 25% express release fee (625.000000 XE).

Proceed with release? [yn] y

This transaction must be signed with your private key.
Please enter your passphrase to decrypt your private key, sign your transaction, and submit it to the blockchain.

Passphrase:

Your transaction has been submitted and will appear in the explorer shortly.

https://test.network/transaction/357e386771e2797dd4515ec2431f6d94d789360cea0db8fc5ae87ec5e00909ba
```

This command can be used non-interactively by providing all options upfront. Run `edge stake release --help` for more information on options.

## Device

Device commands enable you to manage your device's participation in the Edge network.

Before using device commands, ensure the prerequisites are met:

1. Ensure your device meets the minimum specification (see [Network Nodes](https://wiki.edge.network/contributing-to-the-network/network-nodes))
2. [Install Docker](https://docs.docker.com/get-docker/) (v18.06+ required)

Device commands will not work if Docker is not running on your device.

If you are setting up a device for the first time, see [Set up a Host](set-up-a-host.md) for step-by-step guidance.

### Add Device

```bash
edge device add
```

This command adds your device to the Edge network. This works by associating your device's ID with a stake. You must have created a stake already, and you will need to enter your passphrase to sign the assignment transaction.

An example of adding a new device to the network:

```
% edge device add
Initializing device...

Select a stake to assign this device to:

1. 2afb74887fb9 (Gateway)
2. 69213d41cb2b (Host) (assigned to xe_8f5e0d...)
3. eb4c6478073b (Host)
4. 93e3718dba1d (Host)
5. 25f47bf9b04a (Host)

Enter a number: (1-5) 3

You are adding this device to Edge Testnet.

This device will be assigned to stake eb4c6478073b, allowing this device to operate a Host node.

Add this device? [yn] y

This transaction must be signed with your private key.
Please enter your passphrase to decrypt your private key, sign your transaction, and submit it to the blockchain.

Passphrase:

Your transaction has been submitted and will appear in the explorer shortly.

https://test.network/transaction/99447fb4eb6734f6dbdab6d508e127f7d4b936702af911accb2e9dff3e06df2a
```

Your device assignment may take a minute or two to be processed by the XE blockchain. Afterwards, the other `edge device` commands will be usable.

This command can be used non-interactively by providing all options upfront. Run `edge device add --help` for more information on options.

### Display Information

```bash
edge device info
```

This command displays information about your device and the stake to which it is associated. For example:

```
% edge device info
Network: Testnet
Device:  xe_3c627b72081a813B7864caB71f5DbA0D232E7053
Type:    Host
Stake:   eb4c6478073b
```

### Start Device

```bash
edge device start
```

This command starts the network node on your device. This is determined by the type of stake to which the device is assigned.

```
% edge device start
Checking Host version...
Updating Host v2.1.0-40...
Host started
```

### Display Device Status

```bash
edge device status
```

This command displays the current operational status of the node on your device: namely, whether it is running or stopped.

```
% edge device status
Host is running
```

### Update Device

```bash
edge device update
```

This command checks for an update to the node, downloading the update automatically if necessary.

If the node is running, it will be stopped and restarted to update to the new version.

```
% edge device update
Checking Host version...
Updating Host v2.1.0-40...
Host is up to date
```

{% hint style="info" %}
**Nodes are normally self-updating, so you should not normally need to use this command. However, it may be usefupl if you are troubleshooting or developing the node application.**
{% endhint %}

### Restart Device

```bash
edge device restart
```

This command restarts the node without checking for an update. If the node is not already running, this has no effect.

```
% edge device restart
Host restarted
```

### Stop Device

```bash
edge device stop
```

This command stops the node. If the node is not already running, this has no effect.

```
% edge device stop
Host stopped
```

Note that stopping a node does not remove the device from the network - it merely makes it inoperational until it is started again.

### Remove Device

```bash
edge device remove
```

This command removes the device from the Edge network. This consists of unassigning the device from the stake, stopping the node, and destroying the device's identity. (A new identity will be created if the device is added back to the network.)

An example of removing a device from Testnet:

```
% edge device remove
You are removing this device from Edge Testnet.

This will remove this device's assignment to stake eb4c6478073b (Host).

Remove this device? [yn] y

This transaction must be signed with your private key.
Please enter your passphrase to decrypt your private key, sign your transaction, and submit it to the blockchain.

Passphrase:

Unassigning stake...

Your transaction has been submitted and will appear in the explorer shortly.

https://test.network/transaction/3926669c672b47a1a67f08f5baaee09a57222aa6ec17529228bba4c69b117dc8

This device has been removed from Edge Testnet.
```

This command can be used non-interactively by providing all options upfront. Run `edge device remove --help` for more information on options.

{% hint style="info" %}
**It is possible to improperly remove a device from the network: by destroying Docker data (containing the device's identity), or through hardware failure that renders the device unusable. This does not render the stake irrecoverable. You can assign the stake to another device by running** `edge device add` **there and selecting the same stake again, overwriting the device assignment.**
{% endhint %}

## About Edge

Some commands are purely informational and do not affect your device or wallet in any way.

### Community Links

```bash
edge community
```

This command displays links to Edge communities and publications.
