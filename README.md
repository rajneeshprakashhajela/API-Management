                                          Azure API Management
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
  
