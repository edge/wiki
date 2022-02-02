# Nodes

{% content-ref url="../../contributing-to-the-network/network-nodes.md" %}
[network-nodes.md](../../contributing-to-the-network/network-nodes.md)
{% endcontent-ref %}

### What Is an Edge Node?

An Edge node is a computing device that is connected to the Edge Network in order to contribute its spare capacity. Edge nodes earn $XE coins in return for this, and these can be used to purchase services from the network, or they can be swapped for $EDGE tokens, which can be traded.

### Who Can Run an Edge Node?

At the moment the software for running an Edge node is only available for Linux. However versions are being made available for Windows, OSX and mobile devices.

### What Is a Stargate?

Stargates are Edge masternodes. They are responsible for the routing and security in the network, for monitoring resources and for controlling the payout contract.

### What Is a Gateway?

Gateways are Edge masternodes. They are responsible for connectivity in the network and act as the entry points for end user requests.

### What Is a Host?

Hosts are Edge nodes responsible for the provision of computational power and storage within the network.

### Is Edge Proof of Work or Proof of Stake?

Edge operates a hybrid model of proof of stake and proof of work. Proof of stake is used to help to secure the network, with a stake required to operate a node. Proof of work is used to distribute yield based on the jobs that nodes successfully complete in the network.

### **Do we need to manually update our Edge hosts or do they upgrade automatically?**

When a new version goes out, all nodes receive a notification and automagically update, and if a node is offline, upon connecting to the network, it'll receive a message that it needs to update, which it will then do. Should something happen and your node not appear to be updating, it _can_ be manually updated by running `edge device update`.

### **I have an old stake, how do I transfer it to my XE wallet?**

If you have a legacy stake, you need to fill in the stake transfer request form, which you can find here: [https://ed.ge/stake-migration-request](https://ed.ge/stake-migration-request). After that, you'll receive an email from the team confirming the request, or asking for more information, and once your request has been verified, you'll have a stake transferred to your XE wallet. Be sure to include as much information as you can.

### **Can I lose my stake if I make a mistake during device setup?**

Simply put, no. You're not at risk of losing your stake while setting up a node. When you create a stake, you're locking a portion of XE but that stake, that portion of XE, remains in your wallet. When you assign a device to a stake, it is simply updating the stake with the assigned device ID. The only things that you can do to a stake are unlocking them and releasing them, and the XE within a stake will always be returned to the wallet in which they live.

### **Do I have to run my Host node 24/7?**

Not at all. If you can contribute a device 24/7 then it'll be able to handle more jobs and therefore will earn more, but it isn't a requirement. If your machine with spare capacity is only available sometimes, for example during the day, that's fine too. There are no uptime requirements for Hosts and the network is designed to allow Hosts to join as they become available and leave as they become unavailable.

### **Once a stake has been migrated, how do I assign it to a Host?**

Migrated stakes are actually no different from regular stakes, so once you have your stake, you can use it just like you would a regular stake you created with the CLI. To assign a host, it's simply a case of running `edge device add` and following the instructions.
