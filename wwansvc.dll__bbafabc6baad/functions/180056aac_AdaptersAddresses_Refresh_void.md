# AdaptersAddresses::Refresh(void)

- ea: `0x180056aac`
- end: `0x180056d55`
- name: `?Refresh@AdaptersAddresses@@QEAAKXZ`
- size: `681`
- prototype: `unsigned int __fastcall(AdaptersAddresses *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002a684`
- `0x1800536d0`

## callees

- `0x1800085d0`
- `0x180008a7c`
- `0x180008b24`
- `0x1800094f4`
- `0x180014f1c`
- `0x180016c50`
- `0x180056aac`

## import_xrefs

- `ntdll!RtlIpv6AddressToStringW` at `0x180056c8d`
- `ntdll!RtlIpv6AddressToStringW` at `0x180056c8d`
- `ntdll!RtlIpv4AddressToStringW` at `0x180056c76`
- `ntdll!RtlIpv4AddressToStringW` at `0x180056c76`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180056b4e`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180056b4e`

## string_xrefs

- `0x180056d1a`: ` Failed to retrieve IP_ADAPTER_ADDRESSES after [%d] attempts, error [0x%x].`

## pseudocode

```c

```
