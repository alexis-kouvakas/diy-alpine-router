# DIY router with Alpine Linux

A lightweight, Alpine based Router for increased control in homelab setups. Creates an isolated homelab subnet within an existing home network, 
with self-managed DHCP, DNS, and WiFi.

## Status
- [x] Base Alpine install
- [x] DHCP via kea
- [ ] DNS via bind9
- [ ] WiFi via hostapd

## Topology

```
┌─────────────────┐
│   ISP Router    │
│  192.168.1.1    │
└────────┬────────┘
         │ WAN
         │ eth0
┌────────┴────────┐
│   Raspberry     │
│     Pi 5        │
│  192.168.2.1    │
└────────┬────────┘
         │ LAN
         │ eth0 (subnet)
┌────────┴────────┐
│  D-Link DGS-105 │
│     Switch      │
└──┬──────┬──────┬┘
   │      │      │
 dev1    dev2   dev3
```

## Hardware

- Raspberry Pi 5, 8GB RAM
- D-Link DGS 105 Switch

## Software

- Alpine Linux v3.23
- nftables
- dhcpcd
- hostapd
- kea
- Bind9
