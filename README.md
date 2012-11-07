OnionKit
========

Android Library Project for Multi-Layer Network Connections (Better TLS/SSL and Tor)

# StrongTrustManager

We have implemented a TrustManager for SSL Certificate verification that we believe is better than the default one provided by Android. For app developers, it provides for a consistent implementation of TLS/SSL verification and trust across various versions and devices.

It supports full chain verification, limited pinning, and a custom cacerts store based on the Debian set of certs. By providing our own cacert store, we can be assured that certificates are being validated against a known set of trusted Roots, and not compromised, expired or other non-desireable entities.

Developers can create their own CACert store using the information provided by our CACertMan project:
https://github.com/guardianproject/cacert

It can be used in combination with the MemorizingTrustManager, to support user prompted override for non-validating certificates.

# Proxied Connections (aka Orlib)

Once Orbot connects successfully to the Tor network, it offers two proxy servers running
on localhost that applications can route their traffic through.

HTTP Proxy: localhost:8118
SOCKS 4/5 Proxy: localhost:9050

The sample project shows the basics of how to use this library to open sockets and make HTTP requests via the
SOCKS and HTTP proxies available from Orbot The standard Apache HTTPClient libraries provide calls to setup proxying. This sample code
demonstrates that.  All applications using the SOCKS proxy should not resolve their DNS locally,
and instead should pass the hostnames through the SOCKS proxy. 

