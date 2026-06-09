# WctGetSmbInfo(_WCT_CLIENT_HANDLE *,_WAITCHAIN_NODE_INFO *,ulong *,ulong *)

- ea: `0x18005dfb8`
- end: `0x18005e19b`
- name: `?WctGetSmbInfo@@YAKPEAU_WCT_CLIENT_HANDLE@@PEAU_WAITCHAIN_NODE_INFO@@PEAK2@Z`
- size: `483`
- prototype: `unsigned int __fastcall(struct _WCT_CLIENT_HANDLE *lpInBuffer, struct _WAITCHAIN_NODE_INFO *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x18005d450`

## callees

- `0x180004bb4`
- `0x180007e10`
- `0x18001fe24`
- `0x18002bed4`
- `0x180050db0`
- `0x18005dfb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e117`
- `ntdll!NtCreateFile` at `0x18005e0c4`
- `ntdll!NtCreateFile` at `0x18005e0c4`
- `ntdll!RtlNtStatusToDosError` at `0x18005e0d0`
- `ntdll!RtlNtStatusToDosError` at `0x18005e0d0`
- `ntdll!RtlInitUnicodeString` at `0x18005e058`
- `ntdll!RtlInitUnicodeString` at `0x18005e058`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005e10d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18005e10d`

## pseudocode

```c

```
