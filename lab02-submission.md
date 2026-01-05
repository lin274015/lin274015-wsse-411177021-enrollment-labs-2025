# Lab 02 - AWS Cognito Resource Server & API Security

## 1. Cognito Configuration
The user pool and resource server have been successfully configured in AWS.

### User Pool & App Client
- **User Pool ID:** `你的 User Pool ID`
- **Client ID:** `你的 Client ID`

![](images/01-cognito-pool.png)
*Figure 1: Cognito User Pool Overview*

![](images/03-cognito-appclient.png)
*Figure 2: App Client Configuration*

### Resource Server & Custom Scopes
The resource server defines the following scopes to protect the API:
- `https://api.myapp.com/read`
- `https://api.myapp.com/write`

![](images/04-cognito-scopes.png)
*Figure 3: Resource Server Scopes definition*

---

## 2. JWT Authorization Test
The API was tested using the provided Access Token.

### JWT Claims Validation
The Access Token issued by AWS Cognito contains the authorized scopes. 
Below is the decoded token from [jwt.io](https://jwt.io/):

![](images/05-jwt-access-claims.png)

### Swagger Editor Validation
When authorized with a JWT access token, the request contains:
`Authorization: Bearer <access_token>`

![](images/06-editor-no-errors.png)
*Figure 4: Swagger Editor with no validation errors*

---

## 3. CI/CD Integration
A GitHub Action was configured to validate the OpenAPI specification on every Pull Request.

![](images/07-pr-ci-green.png)
*Figure 5: GitHub Actions CI check passing with a green tick*
