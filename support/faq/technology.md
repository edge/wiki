# Technology

{% content-ref url="../../getting-started/the-edge-network.md" %}
[the-edge-network.md](../../getting-started/the-edge-network.md)
{% endcontent-ref %}

### What Blockchain Does Edge Use?

Edge has its own blockchain, developed end-to-end by the core team. The chain itself is known as the XE Blockchain, and the Edge Ledger runs on top of that technology.

### What is Layer 2?

Layer 2 is a general term for solutions designed to handle transactions off of the main Ethereum chain (layer 1). Transaction speed suffers when the network is busy, which slows down processing and also increases the cost of transactions.

$XE currently runs as a layer 2 solution, which enables fast and free transactions within the Edge Network. These are essential to run the technology.

### What Technology Is the Edge Network Built On?

The Edge Network is a completely unique technology stack, created by the core team and developed over many years. It's predominantly written in TypeScript and Golang.

### Where Can I Find the Source Code for the Edge Network?

Edge's source code is partially open source, although we're already working towards being fully open source. You can access the project's code repository on GitHub at: [github.com/edge](https://github.com/edge)

### How Is the Web Wallet Secured?

You'll need a private key to sign transactions in the XE Blockchain. No matter what type of wallet application you're using, the private key has to be available in order to create those cryptographic signatures. The XE Web Wallet stores the private key locally, encrypted using your chosen passphrase. The Web Wallet is a client-side application only (not server-side).

Your private keys never leave your device, and they're only decrypted when a transaction needs to be signed. This is the reason that the wallet asks you for your passphrase every time you send a transaction.

### What Is the Licence for the Project’s Source Code?

{% file src="../../.gitbook/assets/licence.md" %}
Edge Project Licence
{% endfile %}
