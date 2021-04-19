# Performance Weighting

The Edge Network grades contributed nodes with a realtime impact score. This looks at the average response time for job requests per device releative to its peers at Gateway level.

While it is entirely possible to grade a device based on its hardware spec, until a request has been resolved it's impossible to know what resources will actually be utilised. As a request terminates at the Gateway, there is no meaningful information about the request available, and therefore no way of prioritising specific devices based on a perceived performance grade.

Adding to this uncertainty there are further complications during device appraisal in respect to the operational costs attached to each request. For example resizing a large source image may have a low CPU load whilst seriously impacting the systems memory and network bandwidth. A small source image requiring a colour or quality regrade may require little to no bandwidth, but have high CPU processing time.

There are other contributing factors that shape overall performance, therefore we must accept that spare computational capacity will be impacted by unpredictable external factors. For example, the device owner may be running other applications, potentially consuming a significant proportion of resources; for example a home network may have any number of concurrent users.

These factors mean that establishing a reliable and sustained device grade is not possible on the basis of device specification.

This is why the network uses a weighted moving average response time for completed jobs as the key driver for performance score and weighting.

