# CNetworkAddress::StringToIpAddress(ulong,ushort const *,tagWDS_IP_ADDRESS6 *)

- ea: `0x180022990`
- end: `0x180022a2a`
- name: `?StringToIpAddress@CNetworkAddress@@SAKKPEBGPEAUtagWDS_IP_ADDRESS6@@@Z`
- size: `154`
- prototype: `static unsigned int(unsigned int, const unsigned __int16 *, struct tagWDS_IP_ADDRESS6 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fe00`
- `0x1800204d0`
- `0x1800221a0`
- `0x1800224a0`
- `0x180022a30`

## callees

- `0x1800208e0`
- `0x180022990`

## import_xrefs

- `WS2_32!GetAddrInfoW` at `0x1800229d2`
- `WS2_32!GetAddrInfoW` at `0x1800229d2`
- `WS2_32!FreeAddrInfoW` at `0x180022a10`
- `WS2_32!FreeAddrInfoW` at `0x180022a10`

## pseudocode

```c

```
