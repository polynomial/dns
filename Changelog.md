# 3.0.0

- The version introduces some breaking changes internally. But upper layer APIs in the `Lookup` and `Resolver` modules remain the same.
- Breaking change: `Network.DNS.Types` is redesigned. `ResourceRecord` is not a sum type anymore. It holds only normal RRs. For EDNS0, a new scheme is implemented. [#63](https://github.com/kazu-yamamoto/dns/issues/63)
- Breaking change: the `Encode` and `Decode` modules use strict ByteString instead of lazy one. [#59](https://github.com/kazu-yamamoto/dns/issues/59)
- Default DNS servers are detected automatically on Windows if `RCFilePath` is used. Use vanilla `defaultResolvConf` on Windows! [#83](https://github.com/kazu-yamamoto/dns/pull/83)
- Multiple DNS servers are used automatically if found. [#81](https://github.com/kazu-yamamoto/dns/pull/81)
- Some constructors such as ANY are added in the `Types` module.
- Some bug fixes and code clean-up.

# 2.0.13
- Testing with AppVeyor.
- Detecting a default DNS server on Windows.
- Fixing sendAll on Windows [#72](https://github.com/kazu-yamamoto/dns/pull/72)

# 2.0.12
- Fixing Windows build again

# 2.0.11
- Fixing the StateBinary.get32 parser [#57](https://github.com/kazu-yamamoto/dns/pull/57)
- Removing bytestring-builder dependency [#61](https://github.com/kazu-yamamoto/dns/pull/61)
- Fixing Windows build [#62](https://github.com/kazu-yamamoto/dns/pull/62)

# 2.0.10
- Cleaning up the code. [#47](https://github.com/kazu-yamamoto/dns/pull/47)

# 2.0.9
- Implemented TCP fallback after a truncated UDP response. [#46](https://github.com/kazu-yamamoto/dns/pull/46)

# 2.0.8
- Better handling of encoding and decoding the "root" domain ".". [#45](https://github.com/kazu-yamamoto/dns/pull/45)

# 2.0.7
- Add length checks for A and AAAA records. [#43](https://github.com/kazu-yamamoto/dns/pull/43)

# 2.0.6
- Adding Ord instance. [#41](https://github.com/kazu-yamamoto/dns/pull/41)
- Adding DNSSEC-related RRTYPEs [#40](https://github.com/kazu-yamamoto/dns/pull/40)

# 2.0.5
- Supporting DNS-SEC AD (authenticated data). [#38](https://github.com/kazu-yamamoto/dns/pull/38)
- Removing the dependency to blaze-builder.

# 2.0.4
- Renaming a variable to fix preprocessor conflicts [#37](https://github.com/kazu-yamamoto/dns/pull/37)

# 2.0.3
- Handle invalid opcodes gracefully. [#36](https://github.com/kazu-yamamoto/dns/pull/36)

# 2.0.2
- Providing a new API: decodeMany.

# 2.0.1
- Updating document.

# 2.0.0
- DNSMessage is now monomorphic
- RDATA is now monomorphic
- Removed traversal instance for DNSMessage
- EDNS0 encoding/decoding is now supported
- Removed dnsMapWithType and dnsTraverseWithType functions
- responseA and responseAAAA now take lists of IP addresses as their arguments
- DNSHeader type no longer has qdCount, anCount, nsCount, and arCount fields
