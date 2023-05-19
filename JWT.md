# JWT token 

JSON web tokens (JWTs) are a standardized format for sending cryptographically signed JSON data between systems. They can theoretically contain any kind of data, but are most commonly used to send information ("claims") about users as part of authentication, session handling, and access control mechanisms.

Unlike with classic session tokens, all of the data that a server needs is stored client-side within the JWT itself. This makes JWTs a popular choice for highly distributed websites where users need to interact seamlessly with multiple back-end servers.

* You can have a more over view on what exactly JWT is and how it works [JWT working](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/06-Session_Management_Testing/10-Testing_JSON_Web_Tokens#:~:text=JWTs%20are%20a%20common%20source,complete%20compromise%20of%20the%20application)

## How to test JWT 

Jwt has 3 sections:
1- Header
2- Payload
3- Signature

<p> Header and payload is basically just base64URL-encoded JASON object. <br> The header contains metadata about the token itself. for given below example of JWT <br> This devides 3 parts as said earlier , the first part is header, second is the payload and 3rd is the signature </p> <br> Signature : <p>The server that issues the token typically generates the signature by hashing the header and payload. In some cases, they also encrypt the resulting hash. Either way, this process involves a secret signing key. This mechanism provides a way for servers to verify that none of the data within the token has been tampered with since it was issued </p>

`
 eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJsb2dnZWRJbkFzIjoiYWRtaW4iLCJpYXQiOjE0MjI3Nzk2Mzh9.gzSraSYS8EXBxLN_oWnFSRgCzcmJmMjLiuyu5CSpyHI
`

![image](https://github.com/CursedOne69/checklist/assets/67145912/51c4aaf9-dcbc-4f94-99fc-a7714fd886d0)

As you got an idea what it lets move on to exploitation.

## Modify the algorithm to None (CVE-2015-9235)

Use the [burp jwt editor tool ](https://github.com/PortSwigger/jwt-editor)

 Capture the request with JWT , send it to repeater, select the JWT editor tab in request and edit the algorathm from "HS256" to none in header and send the request 

