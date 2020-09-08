# OpenID Connect Demo

[![Quality](https://img.shields.io/badge/quality-demo-red)](https://curity.io/resources/code-examples/status/)
[![Availability](https://img.shields.io/badge/availability-source-blue)](https://curity.io/resources/code-examples/status/)

This is a demo application to explain how the OpenID Connect code flow is implemented.


## web.config
web.config is used as a configuration file for the example app. Change the values to match your system.

Name            | Type    | Mandatory | Default  | Description
----------------| ------- | :-------: | -------- | :---------------
`redirect_uri`  | string  |    ✓      |          | The redirect uri to use, must be registered for the client at the OpenID Connect server.
`client_id`     | string  |    ✓      |          | The id for the client. Used to authenticate the client against the authorization server endpoint.
`client_secret` | string  |    ✓      |          | The shared secret to use for authentication against the token endpoint.
`scope`         | string  |           | `openid` | The scopes to ask for.
`jwks_uri`      | URL     | if `issuer` is not set and the `openid` scope is requested          |          | The URL that points to the JWK set.
`authorization_endpoint` | URL | if `issuer` is not set     |          | The URL to the authorization_endpoint.
`token_endpoint`| URL     |    if `issuer` is not set      |          | The URL to the token_endpoint. 
`issuer`        | string  | if the `openid` scope is requested.           |          | The ID of the token issuer. This enables metadata discovery which will override the configuration set up in this file.
`base_url`      | string  |           |          | base url to be added to internal redirects. Set this to enable the client to be behind a proxy.

## Assignments
### Assignment 1
Fill in the the missing data for the token request. Without the correct pararmeters, the application will not receive a token in exchange for the code. When an access_token is recevied, the assignment is fullfilled.

### Assignment 2
Fill in the the missing data for the refresh request.
When the assignment is done, you will receive a new refresh and access token.

### Assignment 3
Fill in the the missing data for the revoke request. 
When the assignment is done, you won't get an error from the revoke request.

### Assignment 4
Call the api with a invalid token, i.e. revoked. Use the token to call an api, and when the response from the API is 401 Unauthorized; refresh the access token and try again. Expect a successful response.

### Assignment 5
Revoke the refresh_token token. Expect both the refresh token and access token to be invalidated.

### Assignment 6
Get the the configuration of the client by deriving the address from the issuer name. Update the endpoint configuration from the metadata object.

### Assignment 7
Call the jwks uri and cache the keys (in Application State)

## Questions and Support

For questions and support, contact Curity AB:

> Curity AB
>
> info@curity.io
> https://curity.io


Copyright (C) 2016 Curity AB.
