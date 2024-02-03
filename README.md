Pure Nim implementation of HMAC (Hash-Based Message Authentication Code). Currently only supports SHA256 and SHA512.

```nim
let key = "your-secret-key"
let message = "your-message"

var hmac256 = newHmacCtx(key, message, digestMod=SHA256)
var hmac512 = newHmacCtx(key, message, digestMod=SHA512)

assert hmac256.hexDigest() == "85af3c047c3d807cb870748905d81ad4b1833e1928ba1dc59d45e84f546fbf9f"
assert hmac512.hexDigest() == "f3f9a54180e33ff0ca7cd1d563b98bb5cd75161bce2bbec2d9621fa96a9c47212eaa5c4208bfea68b3ccd79aa026d245affa200a21429b2a02b9be3fa663bccc"

hmac256.update("more-of-your-message")
hmac512.update("more-of-your-message")

assert hmac256.hexDigest() == "31458f4fea72ca51cab0151894589ac9d6ec6d569b53099405c9ad307f7825e0"
assert hmac512.hexDigest() == "de7f03db3638d7f8f45128b5a8633f71cc91073bf3b6cf4d7c9307cb767f8dfb0aa7def66788c17060938a92896923893a20ab0d18a41a2dd7cc0a7686932026"
```
