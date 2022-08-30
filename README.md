# Jetpack
A Burp extension dedicated to automated JWT token attacks (still in development).


## Introduction
JWT is a type of stateless authentication token, comprised of three sections divided by dots(.)
The first two sections are base64 encoded.


### Header
This contains things like the type of token and the algorithm used for calculating the signature.


### Payload
Consists of information about the token holder.


### Signature
As the name implies, it's a signature calculated with a server-side secret.

Signature section = signature_algorithm(base64encoded(header) + "." + base64UrlEncode(payload),server_side_secret)


## What Jetpack does (at least for now)
Jetpack performs automated signature stripping attacks by doing the following:
+ Obtaining the token
+ Decoding it
+ Changing the 'alg' parameter to 'none' (all cases - NONE, None, NoNe, etc.)
+ Encoding it back
+ Sending it to the server


## Installation
+ Open up Burp
+ Go to Extender
+ Navigate to Extensions
+ Press the 'Add' button
+ Choose 'Python' as the extension type
+ Supply it with the path to the downloaded .py file
+ Click on 'Next', and it should be ready!

### Known issues
+ The HTTPS checkbox is currently useless.
