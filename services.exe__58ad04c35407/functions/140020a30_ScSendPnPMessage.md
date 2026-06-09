# ScSendPnPMessage

- ea: `0x140020a30`
- end: `0x140020c06`
- name: `ScSendPnPMessage`
- size: `470`
- prototype: `__int64 __usercall@<rax>(struct CServiceRecord *@<rcx>, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x140020950`
- `0x14006d610`

## callees

- `0x140002890`
- `0x140004c58`
- `0x140007130`
- `0x1400089c8`
- `0x140020a30`
- `0x140020c0c`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140020a9f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x140020a9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140020b0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x140020b0b`
- `ntdll!RtlReleaseResource` at `0x140020af8`
- `ntdll!RtlReleaseResource` at `0x140020b18`
- `ntdll!RtlReleaseResource` at `0x140020af8`
- `ntdll!RtlReleaseResource` at `0x140020b18`
- `ntdll!RtlAcquireResourceShared` at `0x140020a8b`
- `ntdll!RtlAcquireResourceShared` at `0x140020a8b`

## pseudocode

```c

```
