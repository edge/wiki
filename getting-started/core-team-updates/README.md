# Core Team Updates

As part of Edge's ongoing commitment to transparency and development in the open, the core team write weekly updates to the Edge community.

There have been 144 of these so far.

{% content-ref url="weekly-updates.md" %}
[weekly-updates.md](weekly-updates.md)
{% endcontent-ref %}

## Latest Update

![](../../.gitbook/assets/weeklyUpdate03012022.png)

Hi everyone, and Happy New year!

The team have been back full time this week and have got 2022 off to a cracking start.

We’ve spent a block of time prioritising the roadmap for 2022; have had 10+ customer meetings; several sessions with two new partners; delivered a series of updates to testnet and to mainnet; and have moved forward with a brand and site refresh.

**CLI v1.5.2** was released to mainnet. This version fixes an issue Windows users may have encountered (thanks to japoilski for the community fix) as well as a small issue with debug mode crashing.

**Index v1.11.0** was deployed. This update introduces a token value endpoint, which is used by the new Edge Price bot (which you can see in Discord) 🤖. We’re planning to expand on this to provide historical data too. More on that next week.

**Stargate v2.1.0-64** was deployed to mainnet introducing some additional session endpoints (used by the new Network Status bot here in Discord). This was also a great opportunity to test the update process which worked perfectly, with all devices reconnecting to the gateway quickly and smoothly.

**Stargate v2.1.1-70** was deployed to mainnet with fixes for session concurrency issues along with a security patch.

**Stargate v2.1.2-79** was deployed to mainnet introducing session metrics collection for monitoring. 📊

**Stargate v2.1.3-85** and **Gateway v2.0.1-47** were deployed to mainnet. These two updates fix an issue with sessions where a node reconnecting while still connected causes both to be disconnected. While only one device should be used per device wallet, this protects against anyone trying to use one device wallet (ergo, one stake) for multiple devices. Only one session can be active per stake at any one time.

Finally, **Stargate v2.1.4-91**, **Gateway v2.0.2-51**, and **Host v2.0.1-38** were deployed to mainnet which introduced recording of network node versions in metrics to help us monitor and optimise network updates. These updates also included some refinement of messaging processing in all three nodes.

This last set of releases also saw us introduce the first Host update to mainnet, and here you can see how the update progressed: quick and smooth, with the majority of host nodes updating within a minute.

![](https://cdn.edge.network/uploads/media/2022/01/08/1.png)

(The others returned within a few more minutes.)

![](https://cdn.edge.network/uploads/media/2022/01/08/2.png)

We’ve also given the Discord server a bit of a facelift to make the channels more friendly. A new channel named `💾│releases` has been created for release information like those above so that the main announcements channel isn't clogged up with releases (which happen highly regularly).

The team also released a couple of bots to Discord: `@Edge Price` & `@Edge Network Status`

We have 78 stakes in network v2, and the update process for their associated nodes has been working extremely well.

This means that there is now 465,000 XE staked in the network, with more on the way. We expect to see this number in the millions very soon.

We've also started running through the stake migration requests, and many of you will be receiving emails asking you to confirm your request in the coming days.

Please ensure that you make your request with your Console account email to make it easier for us to process. Also for Founding Node requests, please include your original staking transaction or your device name if you can find it.

Don’t forget to check your inbox and spam messages for emails from us to confirm your request. If anything is unclear, you can always ask in Discord or drop one of our community admins a DM.

We’re slightly delayed in the processing of the remaining payouts for 2021, which we had planned to complete last week. They’ll now be completed next week.

The latest issue of our weekly newsletter dropped yesterday. You can read it here:

{% embed url="https://ed.ge/digest/issue-26" %}

And if you’re not signed up, sign up now:

{% embed url="https://edge.press" %}

For the latest from the core team join our Discord. It gets all the good stuff, including automatic build notices and announcements. Here’s the invite:

{% embed url="https://discord.gg/edge-network" %}

If you missed the last update of 2021, you can read it on site now:

{% embed url="https://ed.ge/update/2021/12/20" %}

And finally, look out for my 2021 TL;DR. It’s taken me longer than I hoped to get this one out because it was such a packed year. It should drop over the next couple of days.

And that’s it for the first update of 2022! Enjoy your weekends 😎

_Posted by: Joseph Denne_
