# 📰 Project Updates

As part of Edge's ongoing commitment to transparency and development in the open, the core team write weekly updates to the Edge community.

There have been 204 of these so far.

{% content-ref url="weekly-updates.md" %}
[weekly-updates.md](weekly-updates.md)
{% endcontent-ref %}

## Latest Update

Good evening everyone ![👋](https://discord.com/assets/df7ba0f4020ca70048a0226d1dfa73f6.svg)

<figure><img src="../../.gitbook/assets/204Site.png" alt=""><figcaption></figcaption></figure>

In February, the proposal for implementing a scheduled burn of XE passed with 32 votes and 100% support. In it, we proposed to burn 75% of revenue, and this week we conducted the first of these scheduled burns: `Revenue Burn February 2023` saw 277,305.152629 XE sent to the zero address, burning it immediately. That’s 0.5% of the current supply! ![🔥](https://discord.com/assets/67069a13e006345ce28ecc581f2ed162.svg)

You can see the transaction here: [https://xe.network/transaction/7a497f1e8daac8f0c1a383fa703546180965d0fd706a61dc413e3e59b471e61b](https://xe.network/transaction/7a497f1e8daac8f0c1a383fa703546180965d0fd706a61dc413e3e59b471e61b)

You can see the proposal here: [https://governance.edge.network/proposal/cd0cd6f364370119133c830ac4d435b28df41ab96cb12d6a1997cc2e12d68b81](https://governance.edge.network/proposal/cd0cd6f364370119133c830ac4d435b28df41ab96cb12d6a1997cc2e12d68b81)

Other active proposals on the governance portal include:

The 2023 roadmap prioritisation proposal, which currently has 35 votes with 97.1% in favour, found here: [https://governance.edge.network/proposal/3224ddbdeabf358a87c31c693c0b9431177bf7b720927173fe7e3cfe83cf4cf8](https://governance.edge.network/proposal/3224ddbdeabf358a87c31c693c0b9431177bf7b720927173fe7e3cfe83cf4cf8)

And of course, our very own community proposal for the implementation of an automatic lottery for active hosts, which has 33 votes and sits at 100% in favour, found here: [https://governance.edge.network/proposal/7f518bdffcf0b6cdfea093448739e69a9d06b819caa433edbccbdeee256adfbb](https://governance.edge.network/proposal/7f518bdffcf0b6cdfea093448739e69a9d06b819caa433edbccbdeee256adfbb)

If you haven’t had a chance to read or vote upon these yet, please do.

Now, some news from an operations perspective. On Saturday, we identified an issue with the XE blockchain. During routine operations, some of the nodes attempted to resynchronise with one another, but encountered issues replaying blocks. During development of the governance stakes, a simple check was put in place to ensure governance stakes could be created. When replaying the chain with previous stakes, this code was triggered on historical data, and stopped the nodes from being able to resynchronise.

The other nodes continued to work as usual, and on (a very early) Saturday morning, we looked into what was causing some of the nodes to be sitting there, refusing to synchronise. One of these nodes was the node that the index uses to access the chain and so it appeared that blocks and transactions had ceased in the Explorer. Fortunately, this was not the case.

We identified and fixed the issue in the algorithm (where the transactions of a block are replayed, and verified) and pushed out an update. We then resynchronised the nodes that had previously been reluctant to take part, and everything came back to normal. The blockchain nodes will resynchronise their local chains if they detect any abnormalities or data loss, and thus are fully self-healing. In this event, it was simply a mistake in the algorithm caused by the excitement of delivering Governance.

Going forward, we now have in place a policy of running a full blockchain sync on algorithm and protocol changes, to ensure that (unintentional) breaking changes such as this no longer occur.

It’s worth noting that this is the first time that our trusty XE nodes have had an issue, and it was entirely understandable when the issue was spotted. Other than this, the mighty nodes continue to run, self-heal, self-manage adverse network conditions, and otherwise behave perfectly well.

In other news, there have been quite a few releases this week:

**Governance API v1.0.1** and **Governance API v1.0.2** were deployed to mainnet. These updates fixed a few bugs related to handling pending transactions. Thanks to @d736nsd1164 for his help in identifying this issue and working with us to deliver a fix.

**Account API v1.11.0** was deployed to mainnet, adding some minor administrative capabilities around account management.

**Account v1.14.6** was deployed to mainnet too, this time adding a Documentation link to the side menu, while fixing a minor menu-related bug. More on that later.

**Index v2.4.4** was deployed to mainnet. This minor update fixed a bug when sorting wallets by number of active stakes.

Finally, **Monitor v1.0.1** was deployed to mainnet. Monitor is one of the services we employ to have visibility of network performance. This update extended the tool with a web interface and the ability to manage multiple targets easily.

We’ve also been pushing forward with multi-Stargate. This is quite a large piece of work with many moving parts. The next step will be to scale up the testnet to over 200+ devices as we test session management changes (to support distributed authoritative nodes). We’ll keep you updated!

The team have also been continuing their support of the security startup in integrating Edge & XE into their product offerings. We will continue to provide support to them and updates to you.

And that's all for this week. Enjoy your weekend ![🍻](https://discord.com/assets/5e2ea03aa4963cda5e91d395c2587e6b.svg)

_Posted by: Adam K Dean_
