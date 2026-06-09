# ScCreateServiceSids(ushort *,CWin32ServiceRecord *,int,void * * *,ulong *,ulong *,int *,ulong *)

- ea: `0x14002c220`
- end: `0x14002cca0`
- name: `?ScCreateServiceSids@@YAKPEAGPEAVCWin32ServiceRecord@@HPEAPEAPEAXPEAK3PEAH3@Z`
- size: `2688`
- prototype: `unsigned int __fastcall(unsigned __int16 *, struct CWin32ServiceRecord *, int, void ***, unsigned int *, unsigned int *, int *, unsigned int *)`
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x1400381d4`
- `0x14003ae4c`

## callees

- `0x140002890`
- `0x140003e54`
- `0x140004c58`
- `0x140007960`
- `0x14000bac8`
- `0x140013f60`
- `0x1400157bc`
- `0x1400188fc`
- `0x140020864`
- `0x140022c34`
- `0x140029228`
- `0x14002c220`
- `0x140033ec4`
- `0x14004b1c0`
- `0x140057844`
- `0x140064a90`
- `0x140092420`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c9d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002c9d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002c29f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002c8ff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002c29f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14002c8ff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c3c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c3d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c931`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c3c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c3d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002c931`
- `ntdll!RtlNtStatusToDosError` at `0x14002c356`
- `ntdll!RtlNtStatusToDosError` at `0x14002c435`
- `ntdll!RtlNtStatusToDosError` at `0x14002ca51`
- `ntdll!RtlNtStatusToDosError` at `0x14002cae4`
- `ntdll!RtlNtStatusToDosError` at `0x14002c356`
- `ntdll!RtlNtStatusToDosError` at `0x14002c435`
- `ntdll!RtlNtStatusToDosError` at `0x14002ca51`
- `ntdll!RtlNtStatusToDosError` at `0x14002cae4`
- `ntdll!RtlFreeHeap` at `0x14002c3a3`
- `ntdll!RtlFreeHeap` at `0x14002c72d`
- `ntdll!RtlFreeHeap` at `0x14002c3a3`
- `ntdll!RtlFreeHeap` at `0x14002c72d`

## pseudocode

```c

```
