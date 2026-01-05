## JWT Authorization Test

The API was tested using Swagger Editor.

When authorized with a JWT access token issued by AWS Cognito,
the request contains the following header:

Authorization: Bearer <access_token>

![](05-swagger-request.png)

When no token is provided, the request is rejected.

![](06-swagger-unauthorized.png)
