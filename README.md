# Secure API Management using Auth0


# Azure Policy to Validate JWT Token for Auth0
```
<validate-jwt header-name="Authorization" failed-validation-httpcode="401" failed-validation-error-message="Unauthorized" require-expiration-time="true" require-scheme="Bearer" require-signed-tokens="true">
            <openid-config url="https://dev-oi0r2rdz.us.auth0.com/.well-known/openid-configuration" />
</validate-jwt>
```
