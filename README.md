                                          Azure API Management
Azure API Management offers a scalable, multi-cloud API management platform for securing, publishing, and analyzing APIs.
API Management components
 ![alt text](https://learn.microsoft.com/en-us/azure/api-management/media/api-management-key-concepts-experiment/api-management-components.png)

Azure API Management is made up of an API gateway, a management plane, and a developer portal. These components are Azure-hosted and fully managed by default. API Management is available in various tiers differing in capacity and features.
 ![alt text](https://learn.microsoft.com/en-us/azure/api-management/media/api-management-howto-oauth2/overview-graphic-azure-ad.png)

Protect API
'<validate-jwt header-name="Authorization" failed-validation-httpcode="401" failed-validation-error-message="Unauthorized. Access token is missing or invalid.">
    <openid-config url="https://login.microsoftonline.com/{aad-tenant}/v2.0/.well-known/openid-configuration" />
    <required-claims>
        <claim name="aud">
            <value>{backend-app-client-id}</value>
        </claim>
    </required-claims>
</validate-jwt>'
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
