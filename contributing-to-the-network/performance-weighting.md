# Performance Weighting

The Edge Network grades contributed nodes with a realtime impact score. This looks at the average response time for job requests compared to its peers.

While it's entirely possible to grade a device based on its hardware spec, until a request has been resolved it's impossible to know what resources will actually be used. As a request terminates at the Gateway, there's no meaningful information about the request available. Therefore, there's no way of prioritising specific devices based on a perceived performance grade.

There are further complications too. For example, resizing a large source image may have a low CPU load whilst seriously impacting the system's memory and network bandwidth. A small source image requiring a colour or quality regrade may require little to no bandwidth, but have high CPU processing time.

There are other contributing factors that shape overall performance, so we must accept that unpredictable external factore will impact spare computational capacity. For example, the device owner may be running other applications, potentially consuming a significant proportion of resources — like a home network with a number of concurrent users.

These factors mean that establishing a reliable and sustained device grade isn't possible on the basis of device specification.

This is why the network uses a weighted moving average response time for completed jobs to establish performance score and weighting.

