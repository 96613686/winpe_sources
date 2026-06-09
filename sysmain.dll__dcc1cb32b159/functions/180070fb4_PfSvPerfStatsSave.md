# PfSvPerfStatsSave

- ea: `0x180070fb4`
- end: `0x180071143`
- name: `PfSvPerfStatsSave`
- size: `399`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006a020`
- `0x180071db8`

## callees

- `0x180023244`
- `0x180039f94`
- `0x180070fb4`
- `0x180078746`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!RtlComputeCrc32` at `0x1800710ae`
- `ntdll!RtlComputeCrc32` at `0x1800710ae`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180070ff5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180070ff5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180071011`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180071011`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071113`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180071113`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071056`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180071056`

## pseudocode

```c

```
