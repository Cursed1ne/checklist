# JWT mitigation

## None algorithm modifications

Exploition is explained in [JWT exploit ](https://github.com/CursedOne69/checklist/blob/main/JWT.md#modify-the-algorithm-to-none-cve-2015-9235)

## Javascript mitigation for none algorithm

First, use a JWT library that is not exposed to this vulnerability.

Last, during token validation, explicitly request that the expected algorithm was used.


<code>
// HMAC key - Block serialization and storage as String in JVM memory
private transient byte[] keyHMAC =  ;

//Create a verification context for the token requesting
//explicitly the use of the HMAC-256 hashing algorithm<code>
  JWTVerifier verifier = JWT.require(Algorithm.HMAC256(keyHMAC)).build();</code>

  //Verify the token, if the verification fail then a exception is thrown
DecodedJWT decodedToken = verifier.verify(token);
 </code>

<br>

You can use the given algorithm [type](https://connect2id.com/products/nimbus-jose-jwt/algorithm-selection-guide#signatures) for the selection of better algorithm
