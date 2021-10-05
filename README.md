# Token Binding Plugin

[![Quality](https://img.shields.io/badge/quality-experiment-red)](https://curity.io/resources/code-examples/status/)
[![Availability](https://img.shields.io/badge/availability-source-blue)](https://curity.io/resources/code-examples/status/)

A LUA plugin for verifying sender constrained tokens in the reverse proxy.

## Overview

In financial-grade, APIs are secured by Mutual TLS and [Certificate Bound Access Tokens](https://datatracker.ietf.org/doc/html/rfc8705) are used.\
The client certificate used in API requests must then match that used at the time of authentication.

## Plugin

This plugin makes the above token binding checks in an NGINX based reverse proxy, so that the API does not have to.\
See the following resources for further information on this design pattern:

- [Mutual TLS APIs How-to]()
- [Mutual TLS Api Code Example]()

## More Information

Please visit [curity.io](https://curity.io/) for more information about the Curity Identity Server.
