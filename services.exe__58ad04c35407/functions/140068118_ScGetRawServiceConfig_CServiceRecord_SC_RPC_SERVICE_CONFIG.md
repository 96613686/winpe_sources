# ScGetRawServiceConfig(CServiceRecord *,_SC_RPC_SERVICE_CONFIG *)

- ea: `0x140068118`
- end: `0x14006859e`
- name: `?ScGetRawServiceConfig@@YAKPEAVCServiceRecord@@PEAT_SC_RPC_SERVICE_CONFIG@@@Z`
- size: `1158`
- prototype: `unsigned int __fastcall(struct CServiceRecord *this, union _SC_RPC_SERVICE_CONFIG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140005270`

## callees

- `0x140002890`
- `0x140003e54`
- `0x14000bebc`
- `0x14000c8f0`
- `0x14000cee0`
- `0x140013f60`
- `0x140021d08`
- `0x14002e930`
- `0x140068118`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14006841d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14006841d`
- `ntdll!RtlReleaseResource` at `0x140068585`
- `ntdll!RtlReleaseResource` at `0x140068585`
- `ntdll!RtlAcquireResourceShared` at `0x140068158`
- `ntdll!RtlAcquireResourceShared` at `0x140068158`
- `ntdll!NtClose` at `0x14006851f`
- `ntdll!NtClose` at `0x14006851f`
- `ntdll!RtlNtStatusToDosError` at `0x140068527`
- `ntdll!RtlNtStatusToDosError` at `0x140068527`
- `ntdll!RtlFreeHeap` at `0x14006853f`
- `ntdll!RtlFreeHeap` at `0x140068557`
- `ntdll!RtlFreeHeap` at `0x14006856f`
- `ntdll!RtlFreeHeap` at `0x14006853f`
- `ntdll!RtlFreeHeap` at `0x140068557`
- `ntdll!RtlFreeHeap` at `0x14006856f`
- `ntdll!RtlAllocateHeap` at `0x140068248`
- `ntdll!RtlAllocateHeap` at `0x140068248`

## string_xrefs

- `0x1400681d8`: `ImagePath`
- `0x140068290`: `ImagePath`

## pseudocode

```c

```
