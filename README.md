
<h1>Azure API Management </h1>
<h3> Policies, Operation, Developer Portal, User Portal, Management Portal(API) </h3>

Group : Administrator(complete operation CRUD), Developer, Group <br/>
Policies: sequence order when request is receiving..<br/>


<h2>Azure API Management is a fully managed solution that allows users to securely publish, adapt, manage, and monitor APIs. Users can construct an API facade in the Azure portal with a few clicks that serves as a "front door" through which external and internal apps can access data or business logic implemented by our custom-built backend services running on Azure.</h2>

<h2>Common for resource creation (subscription, resource group, Instance details, and pricing tier)</h2>


Azure API Management offers a scalable, multi-cloud API management platform for securing, publishing, and analyzing APIs.
API Management components
 ![alt text](https://learn.microsoft.com/en-us/azure/api-management/media/api-management-key-concepts-experiment/api-management-components.png)

Azure API Management is made up of an API gateway, a management plane, and a developer portal. These components are Azure-hosted and fully managed by default. API Management is available in various tiers differing in capacity and features.
 ![alt text](https://learn.microsoft.com/en-us/azure/api-management/media/api-management-howto-oauth2/overview-graphic-azure-ad.png)

Protect API
'"<validate-jwt header-name="Authorization" failed-validation-httpcode="401" failed-validation-error-message="Unauthorized. Access token is missing or invalid.">
    <openid-config url="https://login.microsoftonline.com/{aad-tenant}/v2.0/.well-known/openid-configuration" />
    <required-claims>
        <claim name="aud">
            <value>{backend-app-client-id}</value>
        </claim>
    </required-claims>
</validate-jwt>"'
Audience is the backend
 
•	 <b>API gateway is the endpoint that:</b><br>
        o	Accepts API calls and routes them to your backends.<br>
        o	Verifies API keys, JWT tokens, certificates, and other credentials.<br>
        o	Enforces usage quotas and rate limits.<br>
        o	Transforms your API on the fly without code modifications.<br>
        o	Caches backend responses were set up.<br>
        o	Logs call metadata for analytics purposes.<br>
•	<b>The Azure portal is the administrative interface where you set up your API program. Use it to:</b><br>
        o	Define or import API schema.<br>
        o	Package APIs into products.<br>
        o	Set up policies like quotas or transformations on the APIs.<br>
        o	Get insights from analytics.<br>
        o	Manage users.<br>
•	<b>The Developer portal serves as the main web presence for developers, where they can:</b><br>
        o	Read API documentation.<br>
        o	Try out an API via the interactive console.<br>
        o	Create an account and subscribe to get API keys.<br>
        o	Access analytics on their own usage.<br>



Headers
Content-Type: text/xml;charset=utf-8
Ocp-Apim-Subscription-Key: dd0bd20*********8***fc7da0
 
Put the above details into postman app and send the request.



Protect API


<validate-jwt header-name="Authorization" failed-validation-httpcode="401" failed-validation-error-message="Unauthorized. Access token is missing or invalid.">
    <openid-config url="https://login.microsoftonline.com/{aad-tenant}/v2.0/.well-known/openid-configuration" />
    <required-claims>
        <claim name="aud">
            <value>{backend-app-client-id}</value>
        </claim>
    </required-claims>
</validate-jwt>

![alt text](https://learn.microsoft.com/en-us/azure/api-management/media/set-edit-policies/form-editor.png)


1. In Azure AD - create app registration for Frontend-app and create app registration for Backend-app 
2. Register Backend app to Frontend-app using <b>API Permission </b>
3. Using Developer portal tab, Open Auth Open ID, Security --> OAuth
4. Check JWT token, Validate Inbound Policy..


<b>Quick Steps </b>
Created 2 accounts A and B <br/>
Created a api that requires OCP key and validates JWT<br/>
Created a product P for that API<br/>
Subscribed A to P<br/>
Got a JWT using B's credential<br/>
B "stole" A's subscription Key<br/>
B successfully consumed product P using his own JWT and A's subscription ke<br/>


ADDING A VALIDATE-JWT POLICY TO AZURE API MANAGEMENT

![image](https://user-images.githubusercontent.com/43515480/230013905-4268ccda-9187-4b3b-a338-1f1e7886e35a.png)

Let’s create an Azure App Registration. You can use an existing App Registration, or create a new one. We will use an existing one – go to App Registrations and copy the Application (Client) Id:
![image](https://user-images.githubusercontent.com/43515480/230014082-8758b82f-6d42-4626-ac7f-fe425f87133a.png)
Before we make any changes, the All operations looks like below:
![image](https://user-images.githubusercontent.com/43515480/230014201-97d7ad5d-72e8-4689-9f12-43b529d33690.png)

Now let’s add the new policy. We add the validate-jwt token header name = Authorization, and the claim AUD application id (the guid from the Application copied above):
![image](https://user-images.githubusercontent.com/43515480/230014385-0578827a-11ed-46b8-ab2f-357fa525f9f2.png)


Let’s add an Authorization header. We will need to pass the authorization token, so let’s generate a Bearer token. For the resource, you can use Application Id of the app registration.

Copy the generated bearer token and send it through in the headers with Authorization,  Bearer <token>:
  ![image](https://user-images.githubusercontent.com/43515480/230014937-fe876692-c9ad-46ca-82a5-ec8ebc240c13.png)

  
  ![image](https://user-images.githubusercontent.com/43515480/230014983-ef9a5354-d1b7-4c32-864e-17b3c69530be.png)

  
Step by step

https://techcommunity.microsoft.com/t5/azure-paas-blog/restricting-api-management-access-to-users-through-aad/ba-p/2116259


<img width="436" alt="image" src="https://user-images.githubusercontent.com/43515480/231391894-53be063c-3245-4f15-871b-db4c20bcf179.png">

  
<H3>What is Azure API?</H3>
<H3>What are API-Centric Applications?</H3>
<H3>What is API Management?</H3>
<H3>What are the features of APIM?</H3>
<H3>What are the components used in APIM?</H3>
<H3>What are Groups in APIM?</H3>
<H3>How do we Create an instance in APIM?</H3>
<H3>How can we manage my API Management instance programmatically?</H3>
<H3>How can we use Azure API Management as a passthrough?</H3>
<H3>How can we run SignalR hub through Azure API Management?</H3>
<H3>How can we prevent direct access to API hosted in Azure app service?</H3>
  
https://www.codeusingjava.com/interview/apim
  
  https://www.techgeeknext.com/azure/azure-apim-interview-questions
  
  
  Azure APIM Interview Questions and Answers
<H3>What is Azure APIM?</H3>
<H3>What is API gateway management?</H3>
<H3>Is APIM an API gateway?</H3>
<H3>What's the difference between API management and API gateway?</H3>
<H3>What is difference between proxy and gateway?</H3>
<H3>What is Gateway Routing?</H3>
<H3>What is Gateway Aggregation?</H3>
<H3>What is Gateway Offloading?</H3>
<H3>Is Azure APIM a load balancer?</H3>
<H3>How to create Azure API Management service instance from the Azure portal?</H3>
<H3>How to import a Postman collection into Azure API Management?</H3>
<H3>How can we redirect the URL to specific backend url depending upon the value of inbound request header in APIM?</H3>
<H3>In the Azure APIM policy, how can we verify if the value supplied in the header is a Guid or not?</H3>

  
  
  
Q: What is Azure APIM?
Ans:
Azure API Management is a fully managed solution that allows users to securely publish, adapt, manage, and monitor APIs. Users can construct an API facade in the Azure portal with a few clicks that serves as a "front door" through which external and internal apps can access data or business logic implemented by our custom-built backend services running on Azure.

Q: What is API gateway?
Ans:
An API gateway is a solution for managing APIs that lies between a client and a group of backend services. An API gateway serves as a reverse proxy, accepting all API calls, aggregating the numerous services required to fulfil them, and returning the accurate outcome. It can also handle cross-cutting activities including authentication, SSL termination, and rate limitation.

Q: Is APIM an API gateway?
Ans:
API Management (APIM) is a technique for creating consistent and modern API gateways for existing back-end services.

Take a look at our suggested post :
Azure Active Directory Interview Questions
Azure Cosmos DB Interview Questions
Azure Data Factory Interview Questions
Azure Fabric Interview Questions
Azure Functions Interview Questions
Jenkins Interview Questions
SonarQube Interview Questions
Q: What's the difference between API management and API gateway?
Ans:
An API gateway is a simple proxy server, whereas API management is the whole solution for managing APIs in production, which comprises a cluster of API gateways, an administrative UI, and so on.

Azure API Management Service is made of three main components.

Azure portal
Developer Portal -> URL -> https://<name>.developer.azure-api.net
API Gateway -> URL -> https://<name>.azure-api.net
API Management enables enterprises to publish APIs to external, vendor, and internal users in order to maximize the value of their data and services.
Q: What is difference between proxy and gateway?
Ans:
A gateway is a network that serves as a point of entry into another network.
A reverse proxy is a server that retrieves data sent from one or more other servers.
The proxy server is effectively requesting permission from the gateway for data to access the network.
Q: What is Gateway Routing?
Ans:
Using layer 7 routing and gateway as a reverse proxy to redirect requests to one or more backend services. The gateway serves as a single point of contact for clients and aids in the decoupling of clients from services.

Q: What is Gateway Aggregation?
Ans:
We can utilize this gateway pattern, when to combine several requests into a single request. When a single activity needs calls to several backend services, this pattern fits. A single request is sent to the gateway by the client. The gateway forward request to various backend services, then aggregates and returns the results back to the client. This minimizes the level of communication between the client and the backend.

Q: What is Gateway Offloading?
Ans:
Should use gateway to offload cross-cutting concerns and functionality from separate services to the gateway. Instead of making each service responsible for implementing these services, it may be more efficient to combine them into a single location. This is especially true for features like authentication and authorization, which require specialist skills to perform correctly.

Q: Is Azure APIM a load balancer?
Ans:
API Management will not really handle load balancing, it can be used in combination with a load balancer like Application Gateway or a reverse proxy.

Q: How to create Azure API Management service instance from the Azure portal?
Ans:
Select Create a resource from the Azure portal menu/Azure Home page.
Select Integration > API Management from the Create a resource page.
Select subscription, resource group, Instance details, and pricing tier on the Create API Management page, then click the Review+Create button.
Search API Management services from the Azure Portal Home Page once it's been setup.
Select the API Management service that you just built.
Q: How to import a Postman collection into Azure API Management?
Ans:
Step1: Convert the Postman Collection to Swagger V2 JSON File
There are various free tools that allow you to convert a Postman collection to any format you want, including Swagger in our instance. APIMATIC is one of these tools.
APIMATIC API Transformer can be found at https://apimatic.io/transformer.
Upload the file description for your Postman collection.
Select the Target Description Format -> "Swagger v2.0 (JSON)" -> click "Convert Now".
The output file will be downloaded to your computer automatically.
Step2: Upload in the Azure APIM Portal
In the Azure Portal, go to my API Management.
Select "Add API" from the left pane, then "OpenAPI specification" from the drop-down menu.
Click "Create" after importing the file prepared previously in the APIMATIC web tool.
Q: How can I verify that every coming inbound request has a specific header in APIM?
Ans:
We can verify the every coming inbound request header by setting varaible in inbound policy inside an API in Azure API Management.

Example:

<policies>
    <inbound>
     <set-variable name="checkHeaderVal"
                   value="@(context.Request.Headers.GetValueOrDefault("abc","").Contains("xxxxx") )" />
    </inbound>
</policies>
Q: How to set the backend url from header in APIM?
Ans:
We can set the backend url in the policies.

<policies>
    <inbound>
        <set-variable name="backendURL"
                     value="@(context.Request.Headers.GetValueOrDefault("uri","https://techgeeknext.com/"))" />
        <set-backend-service base-url="[parameters('backendURL')]"/>
        <base />
    </inbound>
    <backend>
        <base />
    </backend>
    <outbound>
        <base />
    </outbound>
    <on-error>
        <base />
    </on-error>
</policies>
Q: In the Azure APIM policy, how can we verify if the value supplied in the header is a Guid or not?
Ans:
<set-variable name="xguidId" value="@(context.Request.Headers.GetValueOrDefault("x-guid-id", Guid.NewGuid().ToString()))" />
    <choose>
        <!--If the variable x-guid-id is not specified, the request will be denied. -->
        <when condition="@(Guid.TryParse(context.Variables.GetValueOrDefault<string>("xguidId"), out Guid newGuid) == false)">
            <return-response>
                <set-status code="400" reason="Please provide a correct guid." />
            </return-response>
        </when>
    </choose>
