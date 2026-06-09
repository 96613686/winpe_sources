# WctGetSmbInfo(_WCT_CLIENT_HANDLE *,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x1800605c8`
- end: `0x1800607ca`
- name: `?WctGetSmbInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK2@Z`
- size: `514`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *lpInBuffer, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18005fa0c`

## callees

- `0x180004c64`
- `0x180007fd8`
- `0x180020680`
- `0x18002d930`
- `0x180053300`
- `0x1800605c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006073f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006073f`
- `ntdll!NtCreateFile` at `0x1800606da`
- `ntdll!NtCreateFile` at `0x1800606da`
- `ntdll!RtlNtStatusToDosError` at `0x1800606ec`
- `ntdll!RtlNtStatusToDosError` at `0x1800606ec`
- `ntdll!RtlInitUnicodeString` at `0x180060668`
- `ntdll!RtlInitUnicodeString` at `0x180060668`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006072f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006072f`

## pseudocode

```c

```
