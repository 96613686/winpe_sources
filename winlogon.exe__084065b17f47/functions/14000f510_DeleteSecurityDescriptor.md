# DeleteSecurityDescriptor

- ea: `0x14000f510`
- end: `0x14000f5c9`
- name: `DeleteSecurityDescriptor`
- size: `185`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `7`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000c4a0`
- `0x14000cb50`
- `0x14000f400`
- `0x14000f5d0`
- `0x14000f8ec`
- `0x14005a68c`
- `0x14005a808`

## callees

- `0x1400057f4`
- `0x14000f510`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f564`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f57d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f564`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000f57d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f56f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000f56f`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x14000f53b`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x14000f53b`

## pseudocode

```c

```
