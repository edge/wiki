---
description: >-
  As part of Edge's ongoing commitment to transparency and development in the
  open, the core team write weekly updates to the Edge community.
---

# 📰 Project Updates

{% hint style="danger" %}
**Updates are weekly on Telegram and Discord**. This archive is out of date.
{% endhint %}

There have been 206 of these so far.

{% content-ref url="weekly-updates.md" %}
[weekly-updates.md](weekly-updates.md)
{% endcontent-ref %}

## Latest Update

<figure><img src="../../.gitbook/assets/206Site.png" alt=""><figcaption></figcaption></figure>

Good evening everyone ![👋](https://discord.com/assets/df7ba0f4020ca70048a0226d1dfa73f6.svg)

The 2023 roadmap prioritisation proposal closed last week with 37 votes cast and 97.3% in favour. Thanks to everyone who voted and took part in the discussions.

You can find it here:

{% embed url="https://governance.edge.network/proposal/3224ddbdeabf358a87c31c693c0b9431177bf7b720927173fe7e3cfe83cf4cf8" %}

Today the first community proposal, to implement an automatic lottery system for active Hosts, closed with 34 votes cast, all in favour. Thanks to everyone who took part and to Pod & Max for submitting it.

You can find it here:

{% embed url="https://governance.edge.network/proposal/7f518bdffcf0b6cdfea093448739e69a9d06b819caa433edbccbdeee256adfbb" %}

The core team have also just published another proposal: **Implement a small fee for transactions within the XE Blockchain**.

The proposal seeks agreement for the implementation of a small transaction fee into the XE Blockchain, designed to help mitigate the potential for high frequency transactional attacks, further securing the network, and increasing the ![🔥](https://discord.com/assets/67069a13e006345ce28ecc581f2ed162.svg) at the same time.

You can find it here:

{% embed url="https://governance.edge.network/proposal/cee266bdbcd9b9c7371e40638f7db4a8cd939110cc668a3b808645c3d27bba11" %}

And discuss it here:

{% embed url="https://discord.com/channels/371989135172567051/1086431445620371468" %}

This week the team has continued work on multi-Stargate support. This will be broken down into two release stages: first there will be an update to the connection mechanism between Hosts, Gateways, and Stargates, and then following this, there will be a migration over to a new cluster of Stargates. We’ll keep you updated as we continue to press ahead towards this.

There have been a number of mainnet releases this week:

**Explorer v1.23.3** was deployed to mainnet. This patched a minor UI bug with the XE Burned amounts on the Overview page when accessed from mobile devices.

**Index v2.4.7** was deployed to mainnet. This patch fixed a minor issue with the display of revenue burn transactions. Revenue burns will now show up as “Revenue Burn” rather than “Misc” in the burns view.

**Explorer v1.24.1** was deployed to mainnet. This added a simple proxy endpoint for the Index API. All requests going to `https://xe.network/api` will be proxied through to the index API. For example, `https://xe.network/api/blocks` will return the results from `https://index.xe.network/blocks`. This makes it easier to access blockchain data.

In addition we have added endpoints for token supply information, including circulating supply ([https://xe.network/api/supply/circulating](https://xe.network/api/supply/circulating)), maximum supply ([https://xe.network/api/supply/maximum](https://xe.network/api/supply/maximum)), total supply ([https://xe.network/api/supply/total](https://xe.network/api/supply/total)), burned supply ([https://xe.network/api/supply/burned](https://xe.network/api/supply/burned)) and staked supply ([https://xe.network/api/supply/staked](https://xe.network/api/supply/staked)).

These endpoints include monitored address references and a brief summary of the purpose of the figure.

**Index v2.5.0**, **v2.5.1**, and **v2.5.2** were deployed to mainnet too. This series of updates introduced some new supply endpoints to the API. These endpoints allow you to see the total, max, circulating, burned, and staked supplies of XE. These will be used in upcoming changes to the explorer and will also be used by CoinMarketCap & CoinGecko as we work to improve our listings on those sites.

**Account v1.14.7** was deployed to mainnet, fixing a minor UI bug in Firefox.

In other news, Chris held a marketing focused live chat on telegram. This will be repeated in the coming weeks, and will probably happen on Twitter Spaces to allow for the session to be recorded. Watch this space.

Some of you may have noticed transactions for `Write For Edge`. For those of you who missed it, we’ve launched a docs site for Edge Products.

This can be found at [https://docs.edge.network/](https://docs.edge.network/) (short link: [ed.ge/docs](https://ed.ge/docs)).

We’ll be creating (with your help) a series of guides relating to the use of Edge products and services. From setting up linux boxes, to configuring CDN, to operating microservices on top of Edge servers using docker.

If you're a technical writer or have good knowledge about Linux systems and/or open-source software, you can get paid to write tutorials. You can find out more about the programme here:

{% embed url="https://ed.ge/write-for-edge" %}

We’ve already had a number of tutorials contributed, which you can find here: [https://docs.edge.network/edge-servers/tutorials](https://docs.edge.network/edge-servers/tutorials)

This week saw the addition of two new tutorials for Edge Servers:

1. MongoDB [https://docs.edge.network/edge-servers/tutorials/ubuntu/how-to-install-mongodb-on-ubuntu-22.04](https://docs.edge.network/edge-servers/tutorials/ubuntu/how-to-install-mongodb-on-ubuntu-22.04)
2. Docker [https://docs.edge.network/edge-servers/tutorials/ubuntu/installation-and-basic-usage-of-docker-on-ubuntu-22.04](https://docs.edge.network/edge-servers/tutorials/ubuntu/installation-and-basic-usage-of-docker-on-ubuntu-22.04)

As ever, we continue to support a number of projects that are building on top of Edge, from providing infrastructure via Edge Servers, DNS & CDN, to working directly with teams to integrate XE. When we can share more, we will, so always remember to tune in for the weekly updates ![🍿](https://discord.com/assets/0973f9db9b3cd198463d3d8bdea44264.svg)

And that's all for this week. Enjoy your weekend ![🍻](https://discord.com/assets/5e2ea03aa4963cda5e91d395c2587e6b.svg)

_Posted by: Joseph Denne_
