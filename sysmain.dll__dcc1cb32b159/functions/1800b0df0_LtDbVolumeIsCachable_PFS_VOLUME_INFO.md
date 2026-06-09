# LtDbVolumeIsCachable(_PFS_VOLUME_INFO *)

- ea: `0x1800b0df0`
- end: `0x1800b0fce`
- name: `?LtDbVolumeIsCachable@@YAKPEAU_PFS_VOLUME_INFO@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(struct _PFS_VOLUME_INFO *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800afcf4`

## callees

- `0x180007568`
- `0x1800b0df0`
- `0x1800b4f40`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800b0f1a`
- `ntdll!NtCreateFile` at `0x1800b0f1a`
- `ntdll!RtlInitUnicodeString` at `0x1800b0ea1`
- `ntdll!RtlInitUnicodeString` at `0x1800b0ea1`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0e65`
- `ntdll!RtlNtStatusToDosError` at `0x1800b0e65`
- `ntdll!NtClose` at `0x1800b0f6e`
- `ntdll!NtClose` at `0x1800b0f7e`
- `ntdll!NtClose` at `0x1800b0f6e`
- `ntdll!NtClose` at `0x1800b0f7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b0fa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b0fa2`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x1800b0e57`
- `ext-ms-win-sysmain-pfsapi-l1-1-0!SmuGetControlDeviceHandle` at `0x1800b0e57`

## pseudocode

```c

```
