# Core Team Updates

As part of Edge's ongoing commitment to transparency and development in the open, the core team write weekly updates to the Edge community.

There have been 104 of these so far.

{% page-ref page="weekly-updates.md" %}

## Latest Update

![](../../.gitbook/assets/weeklyupdate050421.png)

Hi everyone 👋

Another short week this week after bank holiday weekend, but it was still jammed packed with development.

$XE moved ahead significantly \(detail below\). We are broadly on track for the end of April. Security testing starts soon, the output of which may affect timing in that anything highlighted that needs to be developed further will add time. This could add a week or two to the schedule. We’ll obviously keep the community updated as we progress.

We expect to be discussing tokenomics next week. And the Community Wiki will follow shortly thereafter.

Before I get into the week's updates, a reminder that you will need to go through the swap process in Edge Console in order to be able to claim $XE. The swap process closes towards the end of May.

On to the weeks updates:

The refactor of the upgrade process on Gateway and Host extended to Stargate, and after some issues with the way that Edge atomicstore handled callbacks, a new version of each of the core apps have been pushed to testnet.

These will be deployed to mainnet towards the middle of next week if testing is successful.

Essential maintenance has taken place on network registries, specifically looking at reducing footprint and removing the reliance on a single third party. This is critical path stuff, adding further security and redundancy to the core of the platform.

We now have a fully synchronised mempool – with persistent storage – for pending transactions in the network chain. This includes database cloning for redundancy.

Transactions and the ledger are now fully integrated into the mining process.

API endpoints for $XE covering transactions were also completed. These are being used in the explorer and will eventually be made public. The $XE Mainnet now has multiple nodes live across Europe. The initial deployment of the nodes also took place, moving us towards mainnet security testing.

Network DNS integration was also completed this week, along with core service proxies, status services, Grafana & Prometheus integrations and CI/CD jobs for builds & deployments.

We kicked off the engagement with the broadband provider mentioned in a previous update. There’s a lot of work happening here through Edit, with the expectation that core components of what’s being delivered will be running in the network in due course. As ever, as soon as we can share details on this, we will.

We picked up the domain ed.ge, which we’re planning on using for URL shortening in the network.

Chris wrote another article, The Network Under Your Nose:

[edge.network/en/knowledge/network/the-network-under-your-nose](https://edge.network/en/knowledge/network/the-network-under-your-nose)

And we sent the first Edge Digest, a fortnightly wrap up of all things Edge, delivered straight to your inbox. You can see the issue here:

[edge.press/issues/edge-digest-issue-1-469492](https://edge.press/issues/edge-digest-issue-1-469492)

If you’re not signed up, what are you waiting for! Sign up now at: [edge.press](https://edge.press/)

And that’s it for this week.

Enjoy your weekends.

_Posted by: Joseph Denne_

