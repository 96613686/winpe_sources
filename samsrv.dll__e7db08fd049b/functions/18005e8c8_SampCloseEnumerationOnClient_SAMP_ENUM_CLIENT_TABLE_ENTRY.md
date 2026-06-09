# SampCloseEnumerationOnClient(_SAMP_ENUM_CLIENT_TABLE_ENTRY *)

- ea: `0x18005e8c8`
- end: `0x18005e992`
- name: `?SampCloseEnumerationOnClient@@YAXPEAU_SAMP_ENUM_CLIENT_TABLE_ENTRY@@@Z`
- size: `202`
- prototype: `void __fastcall(struct _SAMP_ENUM_CLIENT_TABLE_ENTRY *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005f0b4`
- `0x18005f414`

## callees

- `0x1800250a0`
- `0x18005e8c8`
- `0x18005fa14`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e92a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e92a`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e90a`
- `ntdll!RtlLeaveCriticalSection` at `0x18005e90a`
- `ntdll!RtlEnterCriticalSection` at `0x18005e8e3`
- `ntdll!RtlEnterCriticalSection` at `0x18005e8e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e96d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e97c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e96d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005e97c`

## pseudocode

```c

```
