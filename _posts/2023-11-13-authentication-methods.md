---
layout: post
title: Authentication Methods
date: 2023-11-13 23:32 +0000
categories: [Security, Network]
tags: [security, network, authentication, jwt, session, cookies]
img_path: /assets/postsImgs/authentication
---

Two main ways of doing user authentication

- Session Cookies
- JWT

## Session

> `Stateful` - Managed on the server
>
> - A stateful session between client and server.

![session diagram](session.drawio.svg)

Authentication Steps:

1. User submits login form
2. The server validates and creates a session that is stored in the database
3. Responds to the client with a session ID
4. Client Browser stores session ID in the cookie
5. Browser sends cookies with future requests for authentication

Cons:

- Vulnerable to CSRF (Cross-side request forgery)
- The session is stored on the server and due to most of the databases in the cloud being scaled horizontally that introduces a huge bottleneck issue.

## (JWT) Token-Based Authentication

> `Stateless` - Managed on the client
> `JWT` - JSON Web Token

![token diagram](token.drawio.svg)

Authentication steps:

1. User submits login form
2. The server creates JWT
    - This is created with a private key on the server
3. Sends JWT to the client
4. Client Browser saves JWT in local storage
5. Future requests signed JWT header validated

The user information is stored in the JWT, which gets deserialized once the JWT signature is verified.

JWT is signed using

- a secret (**HMAC algorithm**)
- or a public/private key using (**RSA** or **ECDSA**)

![jwt diagram](jwt.drawio.svg)

JWT use cases:

- `Authorization:` Once the user is logged in, it allows the user to access services, resources, and routes permitted with that token.
- `Information Exchange:` Good way of security transmitting info between parties. Because of using public/private keys for signing, it can be verified that content hasn’t been tampered with.

Payload content:

- Registered Claims:
  - `iss` - issuer
  - `sub` - Subject
  - `aud` - audience
  - `exp` - Expiration Time
  - `nbf` - Not Before
  - `iat` - Issued At
  - `jti` - JWT ID
  - `typ` - Type
  - `cty` - Content Type
- Public Claims: https://www.iana.org/assignments/jwt/jwt.xhtml
- Can also add private claims

- Note
  - As JWTs are sent through HTTP headers, you should keep them small.

Pro:

- Because all the info is stored in the token, don’t need to store any information on the server
  - Can be validated with a private key on the server, which solves the scaling issue
  - Can use the same JWT across different services
  - For example when using microservices

Cons:

- JWT can be highjacked
- Due to them being stateless, harder to revoke

## Resources

- [JWT.IO](https://jwt.io/)
- [https://datatracker.ietf.org/doc/html/rfc7519](https://datatracker.ietf.org/doc/html/rfc7519#section-4.1)
