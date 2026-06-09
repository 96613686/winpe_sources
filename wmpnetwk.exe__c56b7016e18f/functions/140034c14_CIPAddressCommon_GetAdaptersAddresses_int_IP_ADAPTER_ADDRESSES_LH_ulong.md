# CIPAddressCommon::GetAdaptersAddresses(int,_IP_ADAPTER_ADDRESSES_LH * *,ulong *)

- ea: `0x140034c14`
- end: `0x140034e0b`
- name: `?GetAdaptersAddresses@CIPAddressCommon@@SAJHPEAPEAU_IP_ADAPTER_ADDRESSES_LH@@PEAK@Z`
- size: `503`
- prototype: `__int64 __fastcall(ULONG Family, struct _IP_ADAPTER_ADDRESSES_LH **, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14003b9c0`

## callees

- `0x140034c14`
- `0x14003f17c`
- `0x140046020`
- `0x14004639c`
- `0x14004a834`
- `0x140054984`
- `0x1400989d8`

## import_xrefs

- `IPHLPAPI!GetAdaptersAddresses` at `0x140034c98`
- `IPHLPAPI!GetAdaptersAddresses` at `0x140034cd1`
- `IPHLPAPI!GetAdaptersAddresses` at `0x140034c98`
- `IPHLPAPI!GetAdaptersAddresses` at `0x140034cd1`

## pseudocode

```c

```
