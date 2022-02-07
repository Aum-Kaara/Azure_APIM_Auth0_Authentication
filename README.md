# Secure API Management using Auth0

### Create API in Auth0

An API is an entity that represents an external resource that's capable of accepting and responding to requests made by applications. You'll need to create an Auth0 API using the Management Dashboard to represent the API managed by Azure's API Management Service that you want secured by Auth0.

![image](https://user-images.githubusercontent.com/6815990/152798013-9130aac9-6695-4f35-9093-5dc20fe8941b.png)


### Azure Policy to Validate JWT Token for Auth0
```
<validate-jwt header-name="Authorization" failed-validation-httpcode="401" failed-validation-error-message="Unauthorized" require-expiration-time="true" require-scheme="Bearer" require-signed-tokens="true">
            <openid-config url="https://dev-oi0r2rdz.us.auth0.com/.well-known/openid-configuration" />
</validate-jwt>
```
