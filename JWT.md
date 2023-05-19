# JWT token 

JSON web tokens (JWTs) are a standardized format for sending cryptographically signed JSON data between systems. They can theoretically contain any kind of data, but are most commonly used to send information ("claims") about users as part of authentication, session handling, and access control mechanisms.

Unlike with classic session tokens, all of the data that a server needs is stored client-side within the JWT itself. This makes JWTs a popular choice for highly distributed websites where users need to interact seamlessly with multiple back-end servers.

* You can have a more over view on what exactly JWT is and how it works [JWT working](https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/06-Session_Management_Testing/10-Testing_JSON_Web_Tokens#:~:text=JWTs%20are%20a%20common%20source,complete%20compromise%20of%20the%20application)

## How to test JWT 

Jwt has 3 sections:
1- Header
2- Payload
3- Signature

<p> Header is basically just base64URL-encoded JASON object. <br> The header contains metadata about the token itself. for given below example of JWT <br> This devides 3 parts as said earlier , the first part is header </p>

`
 eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJsb2dnZWRJbkFzIjoiYWRtaW4iLCJpYXQiOjE0MjI3Nzk2Mzh9.gzSraSYS8EXBxLN_oWnFSRgCzcmJmMjLiuyu5CSpyHI
`

![image](https://github.com/CursedOne69/checklist/assets/67145912/51c4aaf9-dcbc-4f94-99fc-a7714fd886d0)
