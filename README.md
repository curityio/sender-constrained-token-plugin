# Sender Constrained Token Plugin

[![Quality](https://img.shields.io/badge/quality-experiment-red)](https://curity.io/resources/code-examples/status/)
[![Availability](https://img.shields.io/badge/availability-source-blue)](https://curity.io/resources/code-examples/status/)

A LUA plugin for verifying sender constrained tokens in the reverse proxy.

## Overview

Sender-constrained tokens are tokens that are bound to a certain client. These tokens cannot - in contrary to ordinary Bearer tokens - be used by a malicious client to access protected resources.

In financial-grade systems, APIs are secured by Mutual TLS, and [Certificate Bound Access Tokens](https://www.rfc-editor.org/rfc/rfc8705.html) are used.\
The client certificate used in API requests must then match that used at the time of authentication.

[Demonstrating Proof-of-Possession (DPoP)](https://datatracker.ietf.org/doc/draft-ietf-oauth-dpop/) or [OAuth 2.0 Token Binding](https://datatracker.ietf.org/doc/html/draft-ietf-oauth-token-binding) are other mechanism for sender constraining tokens though not supported by this plugin.

## Plugin

This plugin makes the above token binding checks in an NGINX based reverse proxy.\
See the following article for further details on how this plugin is used:

- [Mutual TLS APIs Code Example](https://curity.io/resources/learn/mutual-tls-api/)

### Configuration Parameters

`type`: Specify which type of constraint the token has. Currently, the only supported value is `certificate-bound`.

### Running the Plugin
The following configuration at the reverse proxy will load and execute the plugin:

```
local tokenConfig = {
  type = 'certificate-bound'
}
local senderConstrainedTokenPlugin = require 'sender-constrained-token-plugin'
senderConstrainedTokenPlugin.execute(tokenConfig)
```

## More Information

Please visit [curity.io](https://curity.io/) for more information about the Curity Identity Server.
