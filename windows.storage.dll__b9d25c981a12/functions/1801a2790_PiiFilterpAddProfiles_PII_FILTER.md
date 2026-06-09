# PiiFilterpAddProfiles(_PII_FILTER *)

- ea: `0x1801a2790`
- end: `0x1801a2e4c`
- name: `?PiiFilterpAddProfiles@@YAJPEAU_PII_FILTER@@@Z`
- size: `1724`
- prototype: `__int64 __fastcall(struct _PII_FILTER *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007fbec`

## callees

- `0x1801a1bb4`
- `0x1801a2790`
- `0x1801a3130`
- `0x180374040`
- `0x1803b1f60`
- `0x1803b2a24`
- `0x1803b2a30`
- `0x1803b2ac0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801a2bd1`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801a2bd1`
- `ntdll!RtlInitUnicodeString` at `0x1801a2a20`
- `ntdll!RtlInitUnicodeString` at `0x1801a2a20`
- `ntdll!RtlAllocateHeap` at `0x1801a27ea`
- `ntdll!RtlAllocateHeap` at `0x1801a2822`
- `ntdll!RtlAllocateHeap` at `0x1801a2a80`
- `ntdll!RtlAllocateHeap` at `0x1801a27ea`
- `ntdll!RtlAllocateHeap` at `0x1801a2822`
- `ntdll!RtlAllocateHeap` at `0x1801a2a80`
- `ntdll!ZwEnumerateKey` at `0x1801a2941`
- `ntdll!ZwEnumerateKey` at `0x1801a2941`
- `ntdll!ZwClose` at `0x1801a28c9`
- `ntdll!ZwClose` at `0x1801a2cb3`
- `ntdll!ZwClose` at `0x1801a2e3b`
- `ntdll!ZwClose` at `0x1801a28c9`
- `ntdll!ZwClose` at `0x1801a2cb3`
- `ntdll!ZwClose` at `0x1801a2e3b`
- `ntdll!ZwOpenKey` at `0x1801a289f`
- `ntdll!ZwOpenKey` at `0x1801a29f1`
- `ntdll!ZwOpenKey` at `0x1801a289f`
- `ntdll!ZwOpenKey` at `0x1801a29f1`
- `ntdll!ZwQueryValueKey` at `0x1801a2a49`
- `ntdll!ZwQueryValueKey` at `0x1801a2ab8`
- `ntdll!ZwQueryValueKey` at `0x1801a2a49`
- `ntdll!ZwQueryValueKey` at `0x1801a2ab8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801a2854`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801a29ae`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801a2854`
- `ntdll!RtlInitUnicodeStringEx` at `0x1801a29ae`
- `ntdll!RtlFreeHeap` at `0x1801a28f0`
- `ntdll!RtlFreeHeap` at `0x1801a2b15`
- `ntdll!RtlFreeHeap` at `0x1801a2c2d`
- `ntdll!RtlFreeHeap` at `0x1801a2c4b`
- `ntdll!RtlFreeHeap` at `0x1801a2c96`
- `ntdll!RtlFreeHeap` at `0x1801a2d91`
- `ntdll!RtlFreeHeap` at `0x1801a28f0`
- `ntdll!RtlFreeHeap` at `0x1801a2b15`
- `ntdll!RtlFreeHeap` at `0x1801a2c2d`
- `ntdll!RtlFreeHeap` at `0x1801a2c4b`
- `ntdll!RtlFreeHeap` at `0x1801a2c96`
- `ntdll!RtlFreeHeap` at `0x1801a2d91`

## string_xrefs

- `0x1801a2a09`: `ProfileImagePath`
- `0x1801a2845`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList`
- `0x1801a2d0c`: `AslRegistryGetString`
- `0x1801a2d33`: `AslRegistryGetString`
- `0x1801a2d5a`: `AslRegistryGetString`
- `0x1801a2dfd`: `AslRegistryGetString`
- `0x1801a2e20`: `AslRegistryGetString`
- `0x1801a2da2`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x1801a2db3`: `AslRegistryOpenKey`
- `0x1801a2dc9`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x1801a2dda`: `AslRegistryOpenSubKey`

## pseudocode

```c

```
