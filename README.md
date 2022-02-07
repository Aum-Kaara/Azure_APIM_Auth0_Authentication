# Secure API Management using Auth0

### Create API in Auth0

An API is an entity that represents an external resource that's capable of accepting and responding to requests made by applications. You'll need to create an Auth0 API using the Management Dashboard to represent the API managed by Azure's API Management Service that you want secured by Auth0.

![image](https://user-images.githubusercontent.com/6815990/152798013-9130aac9-6695-4f35-9093-5dc20fe8941b.png)

### Setup API Management Instances

Create Your API Management Instance

### Import Conference API 

For this tutorial, we will be importing and using the Conference API provided by Microsoft. You can, however, create your own API instead of using the Conference API.

https://conferenceapi.azurewebsites.net/?format=json

![image](https://user-images.githubusercontent.com/6815990/152799017-bdfde8df-0f0e-4e7b-9362-c9bbeb7ca256.png)

### Configure Your OAuth 2.0 Authorization Server

![image](https://user-images.githubusercontent.com/6815990/152799452-45889649-1bd6-47d2-92b3-5dcf2519e264.png)

![image](https://user-images.githubusercontent.com/6815990/152837781-78098b27-732e-4090-a451-81f4e0b669d5.png)

- Authorization Endpoint URL - https://dev-oi0r2rdz.us.auth0.com/authorize
- Token Endpoint URL - https://dev-oi0r2rdz.us.auth0.com/oauth/token
### Configure Allowed Callback URLs

copy Authorization code grant flow from Azure portal 

![image](https://user-images.githubusercontent.com/6815990/152838992-8156f091-619e-41fe-8e2e-fbbf53255941.png)


![image](https://user-images.githubusercontent.com/6815990/152838717-25d51c64-0703-4a30-ba01-e3f17671280f.png)

### Configure authorization code and client credentials at application

![image](https://user-images.githubusercontent.com/6815990/152840157-2ae3e278-348c-40b6-951e-0ce86a53180c.png)


### Azure Policy to Validate JWT Token for Auth0
```
<validate-jwt header-name="Authorization" failed-validation-httpcode="401" failed-validation-error-message="Unauthorized" require-expiration-time="true" require-scheme="Bearer" require-signed-tokens="true">
            <openid-config url="https://dev-oi0r2rdz.us.auth0.com/.well-known/openid-configuration" />
</validate-jwt>
```

# Testing

### Postman to fetch Token

![image](https://user-images.githubusercontent.com/6815990/152840926-4f24d796-1b69-4cf6-a45e-22fcb41fa650.png)
