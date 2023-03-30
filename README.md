                                          Azure API Management
Azure API Management offers a scalable, multi-cloud API management platform for securing, publishing, and analyzing APIs.
API Management components
 ![alt text](https://learn.microsoft.com/en-us/azure/api-management/media/api-management-key-concepts-experiment/api-management-components.png)

Azure API Management is made up of an API gateway, a management plane, and a developer portal. These components are Azure-hosted and fully managed by default. API Management is available in various tiers differing in capacity and features.
 ![alt text](https://learn.microsoft.com/en-us/azure/api-management/media/api-management-howto-oauth2/overview-graphic-azure-ad.png)

 





Audience is the backend
 
•	 API gateway is the endpoint that:
o	Accepts API calls and routes them to your backends.
o	Verifies API keys, JWT tokens, certificates, and other credentials.
o	Enforces usage quotas and rate limits.
o	Transforms your API on the fly without code modifications.
o	Caches backend responses were set up.
o	Logs call metadata for analytics purposes.
•	The Azure portal is the administrative interface where you set up your API program. Use it to:
o	Define or import API schema.
o	Package APIs into products.
o	Set up policies like quotas or transformations on the APIs.
o	Get insights from analytics.
o	Manage users.
•	The Developer portal serves as the main web presence for developers, where they can:
o	Read API documentation.
o	Try out an API via the interactive console.
o	Create an account and subscribe to get API keys.
o	Access analytics on their own usage.
 


Headers
Content-Type: text/xml;charset=utf-8
Ocp-Apim-Subscription-Key: dd0bd20*********8***fc7da0
 
Put the above details into postman app and send the request.
 



