---
description: >-
  $XE is the coin of the XE Blockchain, a layer 1 solution designed for fast
  transactions mapped to resource usage. It is bridged into the Ethereum network
  on a 1:1 basis with the $EDGE token.
---

# 💰 Edge Tokenomics

Transactions within the Edge Network are free. Bridging $XE in/out of the network to $EDGE in other networks – such as Ethereum – carries a variable gas fee.

For transactions out of Edge Network, this fee is taken in $XE. Individuals can choose their target gas fees and the bridge will automatically transmit their transaction to meet the target set. This acts to help to keep transaction fees as low as possible.

For transactions into the Edge Network, the gas fee is taken in the native token of the other chain (for example, in $ETH).

As a network native coin, $XE does not count towards the circulating supply of $EDGE. Therefore service usage, staking, governance and fees all act to reduce the circulating supply of $EDGE by locking value in the network itself.

{% hint style="success" %}
**Changes relating to network tokenomics are run through project governance**
{% endhint %}

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

## $XE

$XE is the coin of the XE Blockchain, a layer 1 solution designed for fast transactions mapped to resource usage. It is bridged into the Ethereum network on a 1:1 basis with the $EDGE token, meaning that for every 1 $XE bridged out of the Edge Network, you will receive 1 $EDGE.

$XE is used for the purchasing of Edge services, for staking, network governance, and for node rewards.

### Transactions

Transactions within the Edge Network are free.

There is an active governance proposal to introduce a small fee to help to maintain the security of the chain (mitigating against flood attacks). These fees would be burned. You can access and vote on the proposal here:

{% embed url="https://governance.edge.network/proposal/cee266bdbcd9b9c7371e40638f7db4a8cd939110cc668a3b808645c3d27bba11" %}

### Service Purchase

Services can be purchased directly in $XE.

### Node Staking

Edge is a Proof of Stake network. Contributing a node to the network requires a POS in $XE. Stakes are locked in the network for a minimum period of time and for the duration of the node being online.

Nodes that are found to be bad actors will have their stake penalised or removed. Stakes reclaimed by the network in this manner are burned (sent to a zero address in the XE chain).

### Network Governance

Participation in network governance requires a stake locked in the network in $XE. This can be a stake used for the contribution of a node or an unassigned stake used purely for governance participation.

Fees tied to the raising of proposals in the governance mechanism are put into the growth fund.

### Buy Back and Make

A buy back and make programme assigns network revenue recieved in fiat and other cryptocurrencies to the dev fund and to the growth fund.

### Burn

75% of network revenues is burned. The coins are sent to the zero address of the network at the end of every month: `xe_0000000000000000000000000000000000000000`

{% embed url="https://xe.network/wallet/xe_0000000000000000000000000000000000000000" %}

## $EDGE

$EDGE is a tradable utility token on the Ethereum network (ERC-20). It is the entry point to the Edge ecosystem and can be used for the purchasing of Edge services.

$EDGE tokens can be bridged into the Edge network and converted to $XE using the Edge Bridge. The relationship between $EDGE and $XE is 1:1, meaning that for every 1 $EDGE bridged into the network, you will receive 1 $XE.

When $EDGE is bridged into the network, it is locked in the token bridge hot wallet [0x956..](https://etherscan.io/address/0x9560f507e34d375b6593d551bb2c10d48884c787), which is backfilled by the bridge cold wallet [0x8f18..](https://etherscan.io/address/0x8f1800a97844c542c04763aD7c126875032eF3D0) if necessary. Currently over 85% of all tokens are circulating as $XE, and thus locked in the $EDGE cold wallet (deployer contract).

When services are purchased in $EDGE, the $EDGE is automatically bridged into the network, reducing circulating supply.

### Service Purchase

Services in the Edge Network can be purchased with $EDGE. They are also available for purchase within the Visa and MasterCard networks. Enterprises wishing to be invoiced directly can do so by reaching out on: [sales@edge.network](mailto:%20sales@edge.network)

Purchases made in $EDGE are automatically bridged in to Edge Network and swapped for $XE.

Purchases made in fiat (Visa/MasterCard) or in other cryptocurrencies are swapped for $EDGE before being bridged into Edge Network, converting them to $XE.

### Liquidity Mining

An $EDGE liquidity pool is available on Uniswap. This is part funded by the network treasury, part by individual contributors.

Uniswap applies a small fee for every trade that takes place on their platform and automatically sends this to a liquidity reserve. Whenever a liquidity provider decides they want to exit the $EDGE pool, they will receive a portion of the total fees from the reserve relative to their staked amount in $EDGE the pool.

In addition to this, a 0.75% fee is applied to all $XE transactions moving through the network bridge. This amount is automatically deducted from the sent amount and is collected in an $XE vault wallet ([xe\_4845075Ad790DD979Ab3f7834Ff507244e7a5449](https://xe.network/wallet/xe\_4845075Ad790DD979Ab3f7834Ff507244e7a5449)).

## Monitoring Project Tokenomics

The network explorer exposes all on-chain activity and can be used for the monitoring of network transactions.

{% embed url="https://xe.network" %}

In addition to this, the explorer exposes a series of endpoints covering key tokenomic figures such as circulating supply. These can been seen below:

<table><thead><tr><th width="197.33333333333331">Endpoint</th><th width="560">URL</th></tr></thead><tbody><tr><td>Maximum Supply</td><td><a href="https://xe.network/api/supply/maximum">xe.network/api/supply/maximum</a></td></tr><tr><td>Total Supply</td><td><a href="https://xe.network/api/supply/total">xe.network/api/supply/total</a></td></tr><tr><td>Circulating Supply</td><td><a href="https://xe.network/api/supply/circulating">xe.network/api/supply/circulating</a></td></tr><tr><td>Staked Supply</td><td><a href="https://xe.network/api/supply/staked">xe.network/api/supply/staked</a></td></tr><tr><td>Burned Supply</td><td><a href="https://xe.network/api/supply/burned">xe.network/api/supply/burned</a></td></tr></tbody></table>

To see a raw numerical response for each endpoint, add `?raw=true` to the end of the URLs above. For example: [https://xe.network/api/supply/maximum?raw=true](https://xe.network/api/supply/maximum?raw=true)
