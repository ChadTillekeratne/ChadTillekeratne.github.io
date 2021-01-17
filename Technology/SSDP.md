Why am I looking at UDnP/SSDP?  To be able to control IOT/home media targets without using internet connected services.

# Overview
## Scenerios
### Discovery
```
M-SEARCH * HTTP/1.1
HOST: 239.255.255.250:1900
MAN: "ssdp:discover"
MX: 1
ST: urn:dial-multiscreen-org:service:dial:1
```
- `MAN` - Message Type
- `MX` - Maximum wait response time (seconds)
- `ST` - Search Target 
### Response
```
HTTP/1.1 200 OK
CACHE-CONTROL: max-age=3600
ST: urn:dial-multiscreen-org:service:dial:1
USN: uuid:0175c106-5400-10f8-802d-b0a7374360b7::urn:dial-multiscreen-org:service:dial:1
EXT:
SERVER: Roku UPnP/1.0 MiniUPnPd/1.4
LOCATION: http://192.168.1.104:8060/dial/dd.xml
```
- `USN` - Unique Service Name
- `EXT` - For backwards compatability

# Libraries and Helpers
## .NET
- [[GitHub] (Really) Simple Service Discovery Protocol For .Net](https://github.com/Yortw/RSSDP)
## Wireshark
- [[wireshark.org] SSDP Filtering](https://wiki.wireshark.org/SSDP)

# References
- [[PDF] UPnP Device Spec](https://openconnectivity.org/upnp-specs/UPnP-arch-DeviceArchitecture-v2.0-20200417.pdf)
- [Discovering what's out there](https://williamboles.me/discovering-whats-out-there-with-ssdp/)