# OSI Model


## Layer 1 Physical
copper, cable, fiber obtic, **NIC**

NIC = Network Interface Card : stored MAC address

## Layer 2 Data
Ethernet, **MAC address**, LAN, switch

**Ethernet Frame**
```
┌──────────────────────────────────────────────────────────────┐
│                     Ethernet Frame                           │
│                                                              │
│  Preamble                 → 7 bytes                          │
│  SFD                      → 1 byte                           │
│  Destination MAC Address  → 6 bytes                          │
│  Source MAC Address       → 6 bytes                          │
│  EtherType                → 2 bytes                          │
│  Payload                  → 46–1500 bytes                    │
│  FCS                      → 4 bytes                          │
│                                                              │
└──────────────────────────────────────────────────────────────┘

MAC address discovery
IPv4 : ARP + broadcast
IPv6 : NDP + ICMPv6
```


## Layer 3 Transport
**IP address**, router

**IPv4 Packet**
```
IPv4 Packet
┌────────┬────────┬──────────┬───────────────────────────────┐
│Version │  IHL   │ DSCP/ECN │       Total Length            │
│  4 bit │ 4 bit  │ 6+2 bit  │          16 bit               │
├─────────────────────────────┬──────────┬───────────────────┤
│       Identification        │Flags     │ Fragment Offset   │
│           16 bit            │ 3 bit    │     13 bit        │
├──────────┬──────────┬──────────────────────────────────────┤
│   TTL    │ Protocol │          Header Checksum             │
│  8 bit   │  8 bit   │              16 bit                  │
├────────────────────────────────────────────────────────────┤
│                    Source IP Address                       │
│                         32 bit                             │
├────────────────────────────────────────────────────────────┤
│                  Destination IP Address                    │
│                         32 bit                             │
├────────────────────────────────────────────────────────────┤
│                 Options (Optional)                         │
│                    0–40 bytes                              │
├────────────────────────────────────────────────────────────┤
│                         Payload                            │
│                         Variable                           │
└────────────────────────────────────────────────────────────┘
```
- version : IPv4, IPv6
- IHL : basically 20 bytes
- DSCP = Differentiated Services Code Point
- ECN = Explicit Congestion Notification
```
                 ECN Congestion Control

   Sender              Router              Receiver
     │                    │                    │
     │ ─── Packet ──────> │                    │
     │                    │── ECN Mark ──────> │
     │                    │                    │
     │ <──────────────────────── ECE ───────── │
     │                    │                    │
     │ ───────────────────────── CWR ────────> │
     │                                         │
     │           Reduce sending rate           │
     │                                         │
```
- flag : MF, DF
- identification : which segment
- fragment offset: which part of segment (sequence)
- TTL : decrease hop by hop (when pass through each router)
  when TTL 1 -> 0 : router -> traceroute
- protocal:  6 -> TCP
            17 -> UDP
             1 -> ICPM

...

---

**IPv6 Packet**

```                    IPv6 Packet
┌──────────┬────────────────┬──────────────────────────────────┐
│ Version  │ Traffic Class  │           Flow Label             │
│  4 bit   │     8 bit      │             20 bit               │
├───────────────────────────┬───────────────┬──────────────────┤
│     Payload Length        │  Next Header  │   Hop Limit      │
│          16 bit           │     8 bit     │     8 bit        │
├──────────────────────────────────────────────────────────────┤
│                    Source IP Address                         │
│                          128 bit                             │
├──────────────────────────────────────────────────────────────┤
│                 Destination IP Address                       │
│                          128 bit                             │
├──────────────────────────────────────────────────────────────┤
│                  Extension Headers (Optional)                │
│                         Variable                             │
├──────────────────────────────────────────────────────────────┤
│                          Payload                             │
│                          Variable                            │
└──────────────────────────────────────────────────────────────┘
```
