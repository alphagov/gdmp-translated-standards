---
permalink: "/writing-API-reference-documentation-en"
---

# Writing API reference documentation

## This guidance covers the tools and processes you need to help you write your API reference documentation

The API reference is often the largest and most-used part of your API documentation. It’s sometimes published on a separate page to the [conceptual or getting started information](https://www.gov.uk/guidance/how-to-document-apis). You should publish all of the reference information together.

This guidance assumes you’re following the [government API standards](https://www.gov.uk/guidance/gds-api-technical-and-data-standards), building APIs that are [RESTful](https://restfulapi.net/), which use HTTP verb requests to manipulate data.

## Generating API reference from code

You can write an API reference by hand or auto generate a reference from comments in the code of the API itself.

There are many tools that let you auto generate an HTML file from developer code comments to display to your users. The benefit of this approach is that when developers update comments in their code, your docs will be updated too.

You’ll still need to tidy up the reference information after it’s been generated and make sure it fits with any accompanying guidance. Ideally you will have a [technical writer](https://www.gov.uk/government/publications/technical-writer-role-description/technical-writer-role-description) to help you do this.

You can use a number of criteria to choose between different auto generation tools. As well as the [standard considerations when choosing new technology](https://www.gov.uk/service-manual/technology/choosing-technology-an-introduction), you should also consider if the tool:

-   supports the programming language you need
    
-   outputs in a suitable format, for example HTML
    
-   supports the format options you might need, for example code samples, tables, images
    

OpenAPI (formerly known as Swagger) is commonly used in government for RESTful API reference documentation. Alternative tools include:

-   RAML
    
-   I/O Docs
    
-   API Blueprint
    
-   JSON Schema
    

## What to include in an API reference

The API reference describes everything the API does including:

-   resources
    
-   endpoints and methods
    
-   parameters
    
-   example requests and responses
    
-   error codes
    

### Resources

A resource is a piece of data or a collection of data provided by an API in response to a request, for example a row in a database. Provide a short description of each of your API resources so users are clear what they’re for and why they should call them. You can read more about what resources are in [Roy Fielding’s dissertation](https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm#sec_5_2_1_1).

### Endpoints and methods

Underneath each resource description, list all of the endpoints related to that resource. The endpoints are the paths a user will use (or call) to access or manipulate the resource. The API you’re documenting is likely developed to accept standard methods in resource calls, for example GET, PUT, POST or DELETE. Even though these methods are standard, you should still list the methods applicable to the API you’re documenting and describe their functionality.

For example,in the UK the [Companies House API documentation provides a table for each endpoint with a short description and the method](https://developer.companieshouse.gov.uk/api/docs/company/company_number/registered-office-address/registered-office-address.html).

### Parameters and arguments

Parameters are optional filters that affect what the API will return. Next to the documented endpoints, you should list any parameters for that endpoint with a short description. If you have different types of parameters, for example, header and path parameters, you may find it useful to group them by type.

Arguments are the specific input of a parameter. You may find it useful to include these. For example, in the UK the[GOV.UK Notify Python library documentation includes all possible arguments for each method](https://docs.notifications.service.gov.uk/python.html#send-an-email).

Specify data types and constraints for parameters and arguments, and give relevant examples.

### Example requests and responses

One of the most useful things in an API reference is example code. For each endpoint, you should provide an example request, with example parameters (if they are available for that endpoint).

The request is usually published as a code snippet using curl, but it can be useful to show the request in different programming languages if available.

You should also publish an example response as a code snippet, in the same programming language as the example request. It should show the exact response a user can expect from the example request.

Be aware that your examples will not tell your user what the fields mean, for example if the fields are optional or mandatory, or if they carry any constraints. If this information is not clear from the example, consider including explanations alongside your example.

### Error response codes

You should include specific error responses associated with an endpoint close to the endpoint documentation or publish them together at the end of your API reference. Even if you only expect standard responses such as 400 or 200, you should interpret their specific meaning to your API.

For example, the in the UK the [GOV.UK content API documentation](https://content-api.publishing.service.gov.uk/reference.html#responses) includes a table with the endpoint name, error code, what it means and what caused it. This will help your users troubleshoot any problems they may have with your API before contacting you for support.

## Testing your documentation

You should always preview any changes to your documentation before publishing. If you’re documenting a RESTful API, you can test your example requests and responses using curl or a tool such as [Postman](https://www.getpostman.com/) (free tool).

## Related guidance

You might also find these guides useful:

-   [Documenting APIs](https://www.gov.uk/guidance/how-to-document-apis)
    
-   [API standards](https://www.gov.uk/guidance/gds-api-technical-and-data-standards)
    
-   [Tom Johnson’s guide to API documentation](http://idratherbewriting.com/learnapidoc/)
