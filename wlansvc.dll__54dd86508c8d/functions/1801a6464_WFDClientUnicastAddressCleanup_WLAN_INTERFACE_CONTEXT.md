# WFDClientUnicastAddressCleanup(_WLAN_INTERFACE_CONTEXT *)

- ea: `0x1801a6464`
- end: `0x1801a68af`
- name: `?WFDClientUnicastAddressCleanup@@YAKPEAU_WLAN_INTERFACE_CONTEXT@@@Z`
- size: `1099`
- prototype: `unsigned int __fastcall(struct _WLAN_INTERFACE_CONTEXT *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1801a60b4`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x180011530`
- `0x18002f450`
- `0x18005aef0`
- `0x1800c6774`
- `0x180106340`
- `0x180107330`
- `0x1801a6464`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1801a6502`
- `ntdll!RtlNtStatusToDosError` at `0x1801a6502`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x1801a67f3`
- `IPHLPAPI!DeleteUnicastIpAddressEntry` at `0x1801a67f3`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801a64ec`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801a64ec`
- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x1801a67a3`
- `IPHLPAPI!GetUnicastIpAddressEntry` at `0x1801a67a3`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1801a65a6`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1801a65a6`

## pseudocode

```c

```
