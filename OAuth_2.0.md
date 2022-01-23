# OAuth 2.0 Autherization Framework
- [OAuth 2.0 Autherization Framework](https://medium.com/@darutk/the-simplest-guide-to-oauth-2-0-8c71bd9a15bb)
- [OAuth](https://searchapparchitecture.techtarget.com/definition/OAuth)

In High Level It works in 6 simple steps. For more detailed Explanation [Watch this](https://www.youtube.com/watch?v=996OiexHze0&t)

// Getting the access code
1) Client application makes a request to access the resources this will redirect the user to authorize end point
2) Once the user is authenticated, authorized endpoint returns access code with grant permissions to the client application

// Passing the access code to get the access token

3) Then client makes request to Authorized server by passing the access code with grant permissions 
4) Then Authorize server will ask the user to grant access, Up on User approval autherization server will generate the access token and it will send to client

// passing the access token to get the resource access

5) With the access token the client application will make a request to resource server to access the user data
6) If token is valid, Resource server will respond with requested data.

# What is OAuth?
OAuth (Open Authorization) is an open standard authorization framework for token-based authorization on the internet. 
OAuth enables an end user's account information to be used by third-party services, such as Facebook and Google, without exposing the user's account credentials to the third party. 
It acts as an intermediary on behalf of the end user, providing the third-party service with an access token that authorizes specific account information to be shared. 
The process for obtaining the token is called an authorization flow.

Steps in detail:

1) The calendar creation application (the client) requests authorization to access protected resources, in this case image files, owned by the user (resource owner) by directing the user to the authorize endpoint.

2) The resource owner authenticates and authorizes the resource access request from the application, and the authorize endpoint returns an authorization grant to the client. The OAuth 2.0 protocol defines four types of grants: Authorization Code, Client Credentials, Device Code and Refresh Token.

3) The client then requests an access token from the authorization server by presenting the authorization grant returned from the authorize endpoint along with authentication of its own identity to the token endpoint. A token endpoint is a URL such as https://your_domain/oauth2/token.

4) If the client identity is authenticated and the authorization grant is valid, the authorization server or authentication provider -- Google's Authorization Server in this instance -- will issue an access token to the client.

5) The client can now request the protected resources from the resource server -- Google Drive in this example -- by presenting the access token for authentication.

6) If the access token is valid, the resource server returns the requested resources to the calendar creation application (client).

# Can we use OAuth2.0 for Authentication? What is the best tool for Authentication?
We can use it but the purpose of it is to use for Autherization. Open Id can be used for authentication.
