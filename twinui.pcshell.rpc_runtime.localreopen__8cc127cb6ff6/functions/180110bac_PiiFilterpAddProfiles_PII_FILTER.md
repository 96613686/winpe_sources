# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x180110bac`
- end: `0x180110ef4`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `840`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18010f524`

## callees

- `0x180110bac`
- `0x180110efc`
- `0x180111458`
- `0x1801114f0`
- `0x1802dc6ac`
- `0x180356e04`
- `0x180356e10`
- `0x180356edc`
- `0x180667e88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180110d92`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180110d92`
- `ntdll!ZwOpenKey` at `0x180110d45`
- `ntdll!ZwOpenKey` at `0x180110d45`
- `ntdll!RtlInitUnicodeStringEx` at `0x180110d05`
- `ntdll!RtlInitUnicodeStringEx` at `0x180110d05`
- `ntdll!ZwClose` at `0x180110e8c`
- `ntdll!ZwClose` at `0x180110ede`
- `ntdll!ZwClose` at `0x180110ee9`
- `ntdll!ZwClose` at `0x180110e8c`
- `ntdll!ZwClose` at `0x180110ede`
- `ntdll!ZwClose` at `0x180110ee9`
- `ntdll!RtlFreeHeap` at `0x180110c71`
- `ntdll!RtlFreeHeap` at `0x180110dbe`
- `ntdll!RtlFreeHeap` at `0x180110ddb`
- `ntdll!RtlFreeHeap` at `0x180110df8`
- `ntdll!RtlFreeHeap` at `0x180110c71`
- `ntdll!RtlFreeHeap` at `0x180110dbe`
- `ntdll!RtlFreeHeap` at `0x180110ddb`
- `ntdll!RtlFreeHeap` at `0x180110df8`
- `ntdll!ZwEnumerateKey` at `0x180110cbb`
- `ntdll!ZwEnumerateKey` at `0x180110cbb`
- `ntdll!RtlAllocateHeap` at `0x180110bf7`
- `ntdll!RtlAllocateHeap` at `0x180110c1b`
- `ntdll!RtlAllocateHeap` at `0x180110bf7`
- `ntdll!RtlAllocateHeap` at `0x180110c1b`

## string_xrefs

- `0x180110d53`: `ProfileImagePath`
- `0x180110c30`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x180110eb7`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x180110ec8`: `AslRegistryOpenSubKey`

## pseudocode

```c

```
