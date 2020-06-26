
# Managing technical lock-in in the cloud

This guidance outlines how to make informed choices about your organisation’s reliance on cloud technologies.

Please note - this document is translated from a guidance used for public sector organisations considering using cloud hosting in the UK

From:

[Government Digital Service](https://www.gov.uk/government/organisations/government-digital-service)


When using the public cloud you only pay for what you use and avoid upfront infrastructure costs. This can provide your organisation with significant savings and efficiencies over traditional data centre models.

But while there is more flexibility available in the cloud, there is a risk you can become dependent on the products and services from particular providers. This is called lock-in, where switching from one technology or provider to another is difficult, time consuming and disproportionately expensive.

Typically, lock-in is considered something organisations should avoid. However, in the cloud the advantages of being locked-in can often outweigh the disadvantages. For example, using a cloud provider to manage your storage lifecycle might lead to lock-in, but will reduce the work required to manage your service. Accepting some lock-in can allow developers to:

-   write less code
    
-   spend less time on configuration
    
-   build a less complex service
    

You should balance these benefits of cloud lock-in against the potential risks, so you can get the best value and [reduce the burden of future legacy technology](https://www.gov.uk/guidance/managing-legacy-technology).

## The different types of lock-in

There are generally 2 different types of lock-in. Many organisations have experience with commercial lock-in where long and inflexible contracts with providers can prevent organisations from changing their technology strategy when circumstances change.To avoid lock in you should make sure you:

-   [agree contracts of appropriate length](https://www.gov.uk/guidance/g-cloud-buyers-guide)
    
-   retain ownership of intellectual property of your products and services
    
-   retain access to any data held by third parties
    

The UK government has [Crown Commercial Services’ contract management standards](https://www.gov.uk/government/publications/commercial-capability-contract-management-standards) to help with this

With public cloud services, providers typically have rolling, pay-as-you-go contracts. In theory this means you can stop using their services at any time, but in practice this can be difficult. This is technical lock-in, and can be caused by:

-   other providers not offering equivalent services
    
-   technical architecture which relies on doing things a certain way
    
-   too much tight integration with provider-specific services or products
    
-   a lack of technical architecture skills within your organisation
    

It’s impossible to avoid technical lock-in completely. Even the simplest service requires some technical integration with your existing architecture. But decisions you make early on that may make development easier can lead to a greater degree of lock-in than you’re comfortable with.

For example, using a fully-managed orchestration service to deploy your applications for you can make it much easier for a new development team to get up and running. It can also remove the risks that come from bespoke development. However, this can mean an increased dependence on the provider, which becomes a constraint for development as the service grows in complexity.

Every organisation will have a different view of the opportunities and risks around public cloud. These opportunities and risks can be varied, so you’ll need commercial and technical teams to work together to understand and mitigate them. It can also be worth considering the alternative costs or benefits of building and managing the environment if you did not use managed public cloud components.

## Monitor your cloud portfolio

You should monitor your cloud portfolio to identify situations early where the exit or switching costs could grow disproportionately as development continues. Monitoring should be carried out by a person or governance board responsible for the organisation’s cloud strategy

The governance board or person responsible for your cloud strategy should have an overview of all the organisation’s cloud services. This can help prevent duplication of contracts with providers and ensure interoperability of services across the organisation.

The governance board or person responsible for monitoring your cloud strategy can also set baseline expectations for what a disproportionately large switching cost for your organisation or service might be. For example, you may be comfortable knowing you’ll need to invest more development time and switching costs for a service that gets more benefits from using the cloud than with a commodity or low-benefit service.

[User research has shown a centrally coordinated approach to cloud can provide consistency](https://technology.blog.gov.uk/2019/08/30/finding-out-what-government-organisations-need-to-consider-when-using-cloud/) across an organisation. In addition the governance board or person responsible for your cloud strategy can encourage reusability of patterns. An internal assurance process can make sure projects match an agreed strategic approach. This is similar to [how the UK spend controls pipelines work](https://www.gov.uk/guidance/set-up-a-commercial-or-digital-and-technology-spend-controls-pipeline).

While there will always be some level of technical lock-in, this will help you to understand how it affects your organisation and to mitigate it where necessary.

## Understand your technical lock-in

Technical lock-in affects different organisations in different ways. You can become dependent on a provider whether you have a single cloud strategy or are making use of multiple cloud technologies.

For some organisations there may be advantages to extensively adopting the services of a particular provider. These include:

-   close integration of services providing a better user experience
    
-   the ability to reuse common patterns and components across services
    
-   a shared security and monitoring approach backed by mature management tools
    
-   consolidated billing or management across the organisation’s activities
    

For other organisations, this could lead to an unacceptable level of dependency on one provider. These organisations may take steps to limit their technical reliance on certain providers. But protecting yourself against provider lock-in can be expensive, and might involve some compromises in your technology choices.

For example, making sure you can move your infrastructure from one provider to another may present a significant engineering and cost challenge. Trying to avoid services specific to particular providers is difficult and is likely to result in reduced functionality for a particular platform.

Avoiding these very customised services can often lead to organisations only being able to use a basic Infrastructure as a Service (IaaS) solution because they see cloud native services as requiring too much lock-in. You would lose out on other benefits of using these cloud native services, like the significant added value that automated key management or monitoring can offer.

The UK’s National Cyber Security Centre (NCSC) found a number of these [benefits when using serverless technology](https://www.ncsc.gov.uk/blog-post/cloud-security-made-easier-with-serverless). For example, serverless technology:

-   can make patching easier
    
-   can prevent common attacks
    
-   better integrates many of the monitoring and defensive capabilities modern cloud platforms offer
    

## Balancing risk and opportunity in the cloud

If in doubt, weigh the value a cloud service offers your organisation against the possibility of switching providers. It may be useful to consider those criteria on a graph.

Cloud services typically offer value by offering a capability you cannot provide yourself at a lower cost than you can achieve in-house. For example, integrated security monitoring or automated load balancing. This means your staff are free to focus on tasks that are specific to your business objectives.

By placing your services on a graph that compares value and portability, it can be easier to quickly determine how much lock-in risk you find acceptable. You should aim to maximise both the value and portability of the services where possible. You may choose to accept a lower degree of portability if a service offers good value for money.

![](https://lh3.googleusercontent.com/C8hhEulxNTi4axzE7R4I1d-kXf80gDEDOXdcwwAwSVbIKoqOOI3ZYdDGDMEmkcdem-QDslJscewb7Si9bCfmzWRQZ1T0EHcQU_p1mMFJavqKme0WE4Z0Ue2x0Lj5nhFc7AIqI01m)

The graph shows 4 examples on opposite ends of the value and portability spectrum, showing how much lock-in is acceptable and what sorts of services you might find at different ends of the spectrum.

The graph shows:

-   you should avoid services in the low value and low portability quadrant
    
-   where a service offers high value but low portability, the level of lock-in may be acceptable
    
-   many common and non-complex services will be found in the high portability, low-value quadrant
    
-   it is difficult to find services with a high portability and high value but where these services do exist, they can be good value and offer a low lock-in risk
    

For example, [serverless technology](https://en.wikipedia.org/wiki/Serverless_computing) can have lower portability, but the high value it can provide, such as automated patching and deployment, make it worth considering. When portability is very low, you should consider how you would change provider in future.

Another example could be a complex, pre-built machine learning algorithm. The value to your organisation of not having to build and train your own algorithm may outweigh the risk that it would not be very portable.

On the other hand, choosing a relatively obscure object storage service because of a useful feature is an example of something to avoid, if it does not use common standards. The lack of portability would not be an acceptable trade off for the extra feature, as it does not provide much more value over popular alternatives.

At a strategic level, your organisation should set expectations for how delivery teams should [evaluate different hosting options](https://www.gov.uk/service-manual/technology/deciding-how-to-host-your-service) and where you should prioritise value over portability. You should also make sure you understand your teams’ levels of preparedness to switch hosting providers.

To assess their ability to switch providers, some organisations periodically reevaluate switching-cost estimates by rebuilding or testing critical components in a different cloud provider’s environment. This ongoing reassessment can help you to make sure risk assessments are accurate.

At the level of individual products and services, hosting plans and [business cases](https://www.gov.uk/guidance/how-to-assess-a-hosting-business-case) should include estimated costs (after any negotiated discounts or benefits have lapsed) and time to exit hosting arrangements.

## Manage your technical lock-in

If you decide you want to take technical steps to mitigate provider lock-in, your approach will change depending on the kind of deployment you have.

At a strategic level, organisations using a single cloud provider should develop contingency plans in the event their strategy changes, such as moving services to different providers. Those with multi-cloud strategies will need to plan how they could move individual components or services to different hosting arrangements, and possibly test these regularly.

Delivery teams working on individual products and services should also make decisions with a view that they might need to change provider in the future.

An exit strategy should be balanced between the impact of changing provider and the benefit of staying. For example, you may allow for it to take longer to migrate a service because the amount of integration provides a lot of value to your organisation.

For Software as a Service (SaaS), that means choosing products that use open standards and formats, so you have control of your data. This will mean you have the option to export your data to a new environment. For Platform as a Service (PaaS) and IaaS, that could mean [using open source](https://www.gov.uk/guidance/be-open-and-use-open-source) where possible, loosely coupling your components so you can easily replace them, or using infrastructure as code tools which work across multiple cloud platforms.

Assessing your cloud providers should not stop after procurement. You should [use agile methods to continually review your hosting arrangements](https://www.gov.uk/service-manual/agile-delivery) to check they offer the best value for money. Optimising your spending in the cloud will help you to make sure you’re using services efficiently, but you should complement this by evaluating new technologies that are becoming available.

## Build teams to manage your cloud providers

A common cause of technical lock-in is the availability of skills and knowledge. If you have a team with more experience of one provider, you may find it easier in the short term to continue to use that provider’s services.

Some cloud providers offer free training in using their products, but this can lead to increased reliance on those products. Similarly, many suppliers also offer enterprise and community support to supplement the skills of your internal team, though this can be expensive.

At a strategic level, you should hire people with the right skills to meet your shorter term technical requirements. But you should also make sure you have access to knowledge of a broad range of technical solutions, perhaps through your the governance board/person responsible for your cloud strategy or architecture community. This will mean you have an appropriate perspective of the cloud market and can make informed decisions for the future.

At the level of individual products and services, you should build multidisciplinary teams to bring together the right knowledge for choosing and deploying cloud solutions. This means bringing together procurement, financial and technology specialists to make collaborative decisions on cloud and to understand the advantages and disadvantages of the various kinds of cloud lock-in.

## Related guides

Policies and guidance available includes:

-   [the UK government’s Cloud First policy](https://www.gov.uk/guidance/government-cloud-first-policy)
    
-   [the Technology Code of Practice](https://www.gov.uk/government/publications/technology-code-of-practice/technology-code-of-practice)
    
-   [the Service Manual](https://www.gov.uk/service-manual)
    
-   [how to assess a hosting business case](https://www.gov.uk/guidance/how-to-assess-a-hosting-business-case)
