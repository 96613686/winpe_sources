# ScProcessServiceHandleClose(_SC_HANDLE_STRUCT *,int,ulong *)

- ea: `0x1400129f4`
- end: `0x140012dc0`
- name: `?ScProcessServiceHandleClose@@YAXPEAU_SC_HANDLE_STRUCT@@HPEAK@Z`
- size: `972`
- prototype: `void __fastcall(struct _SC_HANDLE_STRUCT *, int, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task`

## callers

- `0x1400127f0`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x1400129f4`
- `0x140016fb0`
- `0x14001700c`
- `0x1400221f4`
- `0x14002e420`
- `0x1400800b4`
- `0x140080db8`
- `0x140080ee8`
- `0x140081470`

## import_xrefs

- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x140012cab`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x140012cab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012bb5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140012bb5`
- `ntdll!RtlAcquireResourceExclusive` at `0x140012a2a`
- `ntdll!RtlAcquireResourceExclusive` at `0x140012a2a`
- `ntdll!RtlReleaseResource` at `0x140012d73`
- `ntdll!RtlReleaseResource` at `0x140012d73`
- `ntdll!RtlFreeHeap` at `0x140012bcd`
- `ntdll!RtlFreeHeap` at `0x140012d66`
- `ntdll!RtlFreeHeap` at `0x140012bcd`
- `ntdll!RtlFreeHeap` at `0x140012d66`

## pseudocode

```c

```
