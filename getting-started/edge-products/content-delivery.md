---
description: >-
  Edge Content Delivery is the world’s first CDN running exclusively on the
  edge. It's kinder to the environment and better for business.
cover: ../../.gitbook/assets/cdncover (1).png
coverY: 0
---

# Content Delivery

{% hint style="success" %}
**Available now**
{% endhint %}

{% embed url="https://vimeo.com/528575049" %}

Edge’s architecture creates a hyper-local peering system that routes traffic from nodes that are as close to the end consumer as possible – going as far as delivering within the local network loop.

This reduces the distance and volume of data being moved, which massively increases the performance of services.

![](../../.gitbook/assets/hyperLocal.png)

## Features

### **Hyper local**

Edge CDN has hundreds of nodes in over 80 countries, getting your content closer to your audience than ever before.

### **Integrated Image Transformation**

Edge Content Delivery includes a media pipeline that allows for just in time image manipulation: Blur, filter, flip, format, resize, rotate, saturate, sharpen and crop. This offsets the weight of media management to your delivery solution.

### **Real Time Optimisation**

Real time compression and resizing of assets at the point of request saves an average of 60% in filesize, speeding up delivery, reducing your overall costs and increasing conversion.

### **End to End TLS**

Take workload off your origin by serving SSL certificates directly at the edge, accelerating performance and increasing availability.

### **Cost Effective**

Edge CDN saves 20%+ on average vs. traditional CDNs as a result of better media compression and the use of edge devices instead of centralised data centres.

## Documentation

Documentation can be found here: [edge.network/en/content-delivery/documentation](https://edge.network/en/content-delivery/documentation/)

## IRL

Edge content delivery can be seen running on [Monocle.com](https://monocle.com), where it handles all media and asset delivery.

Checking the headers from an image call returns the cache state for the asset in the network, as well as the device IDs of the nodes involved in its delivery.

### Live Example

#### Image

[https://img.monocle.com/book-of-italy-chooser5-6058b1e-6059ca40f12b2.jpg?g=center\&q=50\&dpr=2](https://img.monocle.com/book-of-italy-chooser5-6058b1e-6059ca40f12b2.jpg?g=center\&q=50\&dpr=2)

![](../../.gitbook/assets/book-of-italy-chooser5-6058b1e-6059ca40f12b2.jpeg)

#### Headers Returned

```
HTTP/1.0 200 OK =>
Access-Control-Allow-Origin => *
Cache-Control => public, max-age=86400
Cdn-Version => 0.0.9
Content-Length => 180462
Content-Type => image/jpeg
Date => Tue, 23 Mar 2021 12:48:14 GMT
Edge-Device => deb70d83-ca59-4345-adbc-da1ae06e76ca
Edge-Gateway => fb7fe194-9b46-4bcc-b7ae-e813dbc4d278
Edge-Host => c41babfe-c9dd-43cb-aa1b-a5b31dc4d953
Etag => "180462-b12ba916f5f133e321ee67706cb8ba29f1014f4adf0b90a0a234d2cbe4b60022"
Strict-Transport-Security => max-age=10886400; includeSubDomains
Vary => Accept-Encoding
X-Cache => HIT
X-Cache-Origin => request
X-Cache-Type => mem
```

## Launch Edge CDN Now

{% embed url="https://account.edge.network" %}
