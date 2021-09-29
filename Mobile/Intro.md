# MOBILE
| Services                     | Use Cases                                                      | Database type
| :---                         | :----                                                          | :-----:
| Amazon Amplify               | Authentication                                                 | Develop   
|                              | Storage.                                                       |   
|                              | Datastore.                                                     |
|                              | Functions.                                                     | 
|                              | Apis(GraphQL,REST).                                            |  
|                              | Analytics.                                                     |  
|                              | Chatbot.                                                       |  
|                              | AI/ML.                                                         |  
|                              | Push notifications.                                            |  
| Amazon Chime SDK             | Audio, video, desktop sharing.                                 |   
| Amazon Localization Service  | Geolocalization.                                               |  
| AWS Amplify                  | Deploy and host static and server-rendered web applications .  | Deliver  
| AWS APP Runner               | Deploy and run containerized applications.                     |  
| AWS Device Farm              | Device and browser testing.                                    | Test & monitor  
| CloudWatch                   | Monitor app performance.                                       |  
| Amazon Pinpoint              | Marketing campaigns.                                           | Engage 
|                              | Transactional messages.                                        |  
|                              | Bulk communications.                                           |  



## [Api Gateway](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html)

Amazon API Gateway is a fully managed service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. APIs act as the "front door" for applications to access data, business logic, or functionality from your backend services. Using API Gateway, you can create RESTful APIs and WebSocket APIs that enable real-time two-way communication applications. API Gateway supports containerized and serverless workloads, as well as web applications.

API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management, CORS support, authorization and access control, throttling, monitoring, and API version management. API Gateway has no minimum fees or startup costs. You pay for the API calls you receive and the amount of data transferred out and, with the API Gateway tiered pricing model, you can reduce your cost as your API usage scales.

![](https://github.com/camilonfs1/AWS-CLOUD-SERVICES/blob/main/src/images/Mobile1.PNG)

## Cors for a Rest Api
> Cors (Cross-origin resource sharing) is a browser security feature that restrict cross-origin HTTP requests thatt are initiated from scripts running in the browser. If your APIs resources receive nom-simple cross-origin HTTP requests, you need to enable CORS support.

If you are using the API Gateway Import API, you can set up CORS support using an OpenApI file. You must first define an OPTIONS method in your resource that returns the requered headers.

Once you have configured the OPTIONS for you resource, you can add the required headers to the other methods in the same resource that same resource that to accept CORS requests.

>1. Declare the **ACCESS-CONTROL-ALLOW-ORIGIN** and **Heaaders** to the response types.

```json
responses:
      200:
        description: Default response for CORS method
        headers:
          Access-Control-Allow-Origin:
            schema:
              type: string
          Access-Control-Allow-Methods:
            schema:
              type: string
          Access-Control-Allow-Headers:
            schema:
              type: string
        content: {}
```
> 2. In the **x-amazon-apigateway-integration** tag, set up the mapping for those headers to your static values:

```json
    responses:
        default:
          statusCode: "200"
          responseParameters:
            method.response.header.Access-Control-Allow-Headers: '''Content-Type,X-Amz-Date,Authorization,X-Api-Key'''
            method.response.header.Access-Control-Allow-Methods: '''*'''
            method.response.header.Access-Control-Allow-Origin: '''*'''
          responseTemplates:
            application/json: |
              {}
```