# QueryWellKnownDnsName(ulong,ulong,ushort * *)

- ea: `0x18000dd20`
- end: `0x18000e1c3`
- name: `?QueryWellKnownDnsName@@YAKKKPEAPEAG@Z`
- size: `1187`
- prototype: `unsigned int __fastcall(unsigned int, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000e1d0`

## callees

- `0x18000dd20`
- `0x18001b480`
- `0x180058cb8`
- `0x18006c890`
- `0x180098320`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800c7944`
- `0x1800cf008`
- `0x1800db6b0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18000e174`
- `ntdll!RtlNtStatusToDosError` at `0x18000e174`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18000e132`
- `ntdll!RtlIpv4AddressToStringExW` at `0x18000e132`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18000e168`
- `ntdll!RtlIpv6AddressToStringExW` at `0x18000e168`
- `WS2_32!FreeAddrInfoExW` at `0x18000e07a`
- `WS2_32!FreeAddrInfoExW` at `0x18000e07a`
- `WS2_32!GetAddrInfoExW` at `0x18000df04`
- `WS2_32!GetAddrInfoExW` at `0x18000df04`
- `WS2_32!__imp_WSAStartup` at `0x18000de0f`
- `WS2_32!__imp_WSAStartup` at `0x18000de0f`
- `WS2_32!__imp_WSACleanup` at `0x18000dfb0`
- `WS2_32!__imp_WSACleanup` at `0x18000dfb0`

## pseudocode

```c

```
