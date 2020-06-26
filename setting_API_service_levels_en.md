# Setting API service levels

Optimise your API service level indicators based on your user needs.

When managing your API as a service, you need to understand what matters to your users and what you’ll commit to in your service level agreement. You may want to consider:

-   request latency
    
-   system throughput
    
-   availability and downtime
    

Each of these aspects is a service level indicator (SLI). This guidance describes different SLIs and how you can optimise them based on techniques that have worked for some government development teams. You should optimise your SLIs based on your number of API users and their needs.

High service levels can be expensive to deliver, so you should not set them higher than necessary.

## Establishing the best request latency for your API

One of the most important SLIs to agree is how long it takes an API request to return a response.

Engineering an API for a higher performance in request latency than your users need can be expensive, so you need to make an assessment about the context you’re working in. For example, a train network API must be able to provide data about train whereabouts in real time or suffer severe consequences. However, a tax API may not need to process tax returns so quickly.

To improve your API latency, you may want to consider:

-   installing a content delivery network
    
-   engineering a backend heavy-lifting data query API to pick up large amounts of data infrequently matched with a ‘chatty’ frontend API to pick up smaller amounts of data frequently
    
-   caching your API data - consider making GET requests cacheable to avoid forcing every API call to create network traffic and hit your database
    
-   investing resources in [data wrangling](https://en.wikipedia.org/wiki/Data_wrangling)
    

These approaches can decrease network costs and improve performance using the same hardware. However, all of these approaches will depend on how fresh your data needs to be. Your users may sometimes need to be able to access your API data during network interruptions when the data is unavailable from the servers.

When caching, you should:

-   cache as close to the user as possible - this stops requests causing any additional network activity
    
-   add Cache-Control or Vary HTTP headers - these will articulate your caching policy to your users, for example how a resource is cached, where it’s cached, and the maximum age it can reach before it expires
    

If you have a volatile API, you should not cache by default.

You should never cache sensitive or user-specific data especially anything sensitive.

When developing a [data API](https://gdstechnology.blog.gov.uk/2017/02/03/providing-access-to-datasets-through-apis/) (rather than a transactional API), you should consider whether to let users make large data requests or whether to restrict users to making a number of smaller requests. If you believe large data requests are necessary for your users, you may want to consider:

-   using data compression such as GZIP files - if your API is RESTful, let users send headers that say they will not accept compressed data
    
-   paginating requests - breaking your API resources into manageable chunks lets users make multiple requests rather than a single one
    
-   downloading data sets as CSV files periodically - taking snapshots of your data at regular periods and caching it for users to download is less resource-intensive than having users dynamically generate a CSV file from your active database
    
-   using operational data stores - this is useful if your data is in lots of different systems and you want to stage the data to make it readily accessible to user requests
    

Staging data using operational data stores will timestamp your data. When using these techniques you’ll need to consider how often you sync the staged data with your master data sets.

Operational data stores may not be suitable for users of APIs who need the most up-to-date data available. Keeping an operational data store updated in real time is unlikely to be cost-effective.

## System throughput for transactional APIs

System throughput is the number of requests that can be made to your API within a period of time. You may choose to apply ‘throttling’, or ‘rate limiting’ to set a limit on the number of requests applications can make to your API

It’s unlikely you’ll need to rate limit non-transactional APIs providing open data.

If you have transactional APIs, you may choose to apply rate limiting to:

-   manage capacity and costs - transactional APIs have a high cost per request compared to data APIs because every transaction goes through the whole stack, and probably results in at least one database write
    
-   encourage responsible consumption
    
-   protect from denial-of-service (DoS) attacks
    
-   enforce a strict semantic defining which headers and values to use
    

When applying rate limiting or throttling, you should not let your users go over the limits you set even if you have spare capacity. This is because if you need to take the spare capacity away in future and the user has developed their application with the higher rates in mind, their application could break. For the same reason, avoid retroactively enforcing rate-limiting caps.

When applying rate limiting to transactional APIs, you should:

-   clearly communicate with users - for example, use X-RateLimit_remaining in the header to let them know when they are close to your limit
    
-   understand performance limitations of backend systems - the backend system is usually the weakest link in terms of performance rather than the API
    
-   understand users may want to use your API a lot for a short period of time and this may be unpredictable - in these instances consider setting a [burst limit](https://apifriends.com/api-management/api-quota/)
    

When setting a burst limit, consider the volume of this facility. For example, your rate limit could be 10,000 requests per minute with a burst limit of 20,000 requests per minute for up to 5 minutes.

Refer to the [government API technical and data standards](https://www.gov.uk/guidance/gds-api-technical-and-data-standards) for more information on rate limiting.

## Managing your API availability and downtime

When considering SLIs around availability, you need to think about the kind of downtime that will be a problem for your API. For instance, your API could drop 1 in 20 connections or it could be unreachable for 2 hours a day. Both of these scenarios could result in the same percentage of uptime but one of them may be more problematic for users than the other.

You also need to make sure you balance the need for availability with the costs of achieving it. If users do not tend to use your API in the early hours of the morning then it makes sense to do API maintenance work at this time.

How you manage your API downtime will have implications for the cost of an on-call support team. You need to decide when it’s appropriate to pay a technology team overtime money to attend to your API downtime out of hours.

To improve the availability of your API you could consider scaling up your source system or putting a cache in front of it.

When designing a low-availability API, consider the use of HTTP 202 responses. For example, to indicate that the API has accepted a request but needs to wait to take further action.

## Related guidance

For more information, see the Service Manual guidance on [monitoring the status of a service](https://www.gov.uk/service-manual/technology/monitoring-the-status-of-your-service) and [testing performance](https://www.gov.uk/service-manual/technology/test-your-services-performance).
