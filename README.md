# LIDO 1.0 
LIDO(Lightweight IDentity Online) 1.0 is a strong authentication framework for online services and websites and reduce the problems associated with passwords.

# LIDO 1.0 Architecture
![LIDO 1.0 Architecture](LIDO_10_Architecture.png)

# LIDO 1.0 CLIENT
Download: [**Android**](https://play.google.com/store/apps/details?id=lido.client)

![LIDO_10_Client](LIDO_10_Client.png)

# URL Scheme
* http:// ---> lido://
* https:// ---> lidos://

# Javascript Interface

<pre>

[lido.request]

lido.request( reqeustJson );

[lido.response]

#callack
function lidoResponse( responseJson ){
   //code here
}

</pre>

# APIs
* *getKeyid*
* *genKey*
* *sign*
* *rmKey*

## getKeyid
Check if a key exists in LIDO Client.

<pre>

[lido.request]
{ "command" : "getKeyid" }

[lido.response]
{ "returnCode" : 200 , "keyid" : null or keyidValue }

</pre>

## genKey
Generate new key if keyid is null

<pre>

[lido.request]
{ "command" : "genKey", "title" : ${SITE_NAME}, "data" : ${NONCE OR DATA} }

[lido.response]
{ "returnCode" : 200 , "jwt" = ${JWT(INCLUDE-RSA-PUBLICK-KEY)} }

</pre>

## sign
Issuance JWT(Json Web Token) - signing data with Private-Key

<pre>

[lido.request]
{ "command" : "sign", "data" : ${NONCE OR DATA} }

[lido.response]
{ "returnCode" : 200 , "jwt" = ${JWT} }

</pre>

## rmKey
remove key

<pre>

[lido.request]
{ "command" : "rmKey" }

[lido.response]
{ "returnCode" : 200 }

</pre>

# [JWT(Json Web Token)](https://jwt.io)
JSON Web Tokens are an open, industry standard RFC 7519 method for representing claims securely between two parties.


# [LIDO Demo](https://github.com/LIDOKIM/LIDO-Demo)
LIDO(Lightweight IDentity Online) sample web application


# License
Copyright 2018 LIDOKIM. All Rights Reserved.

Licensed to the Apache Software Foundation (ASF) under one or more contributor license agreements. See the NOTICE file distributed with this work for additional information regarding copyright ownership. The ASF licenses this file to you under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
