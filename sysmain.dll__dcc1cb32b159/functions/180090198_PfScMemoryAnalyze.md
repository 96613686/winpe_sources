# PfScMemoryAnalyze

- ea: `0x180090198`
- end: `0x1800902a2`
- name: `PfScMemoryAnalyze`
- size: `266`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18005afd0`

## callees

- `0x180082618`
- `0x18008e8e0`
- `0x180090198`

## import_xrefs

- `msvcrt!fprintf` at `0x180090291`
- `msvcrt!fprintf` at `0x180090291`
- `ntdll!RtlReleaseSRWLockShared` at `0x180090269`
- `ntdll!RtlReleaseSRWLockShared` at `0x180090269`
- `ntdll!RtlAcquireSRWLockShared` at `0x18009024d`
- `ntdll!RtlAcquireSRWLockShared` at `0x18009024d`

## string_xrefs

- `0x1800901d0`: `StringCache`
- `0x1800901f1`: `StringCache`
- `0x180090222`: `StringCache`
- `0x180090280`: `StringCache`
- `0x18009025a`: `StringCacheHeap`

## pseudocode

```c

```
