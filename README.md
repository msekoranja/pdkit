Protocol Designer's Kit
=======================

The goal of this project is to make a toolkit that would allow to implement
a simple networking protocol in order of minutes. It also aims to make these
protocols easily composable: Instantiating a stack of multiple protocols
should be a one-line-of-code matter. The protocols should exhibit
production-level performance.

Project will rely on libmill for concurrency support.

Use cases and features to support
---------------------------------

* IP, UDP: header + data
* TCP: bytestream
* SCTP: channels, OOB
* PGM: one-way, unreliable, multicast
* WebSockets, TCPMUX: connection handover

Example
-------

```
sock s1 = tcpconnect("192.168.0.111", 5555);
sock s2 = size_prefixed_messages(s1);
sock s3 = version_handshake(s2, "1.8");
...
```
