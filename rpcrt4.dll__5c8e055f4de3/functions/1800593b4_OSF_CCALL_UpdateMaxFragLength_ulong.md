# OSF_CCALL::UpdateMaxFragLength(ulong)

- ea: `0x1800593b4`
- end: `0x1800594fc`
- name: `?UpdateMaxFragLength@OSF_CCALL@@AEAAXK@Z`
- size: `328`
- prototype: `void __fastcall(OSF_CCALL *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180059138`
- `0x1800592d8`
- `0x1800ace5c`

## callees

- `0x1800593b4`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180059485`
- `ntdll!RtlLeaveCriticalSection` at `0x180059485`
- `ntdll!RtlEnterCriticalSection` at `0x180059473`
- `ntdll!RtlEnterCriticalSection` at `0x180059473`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800594f1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800594f1`

## pseudocode

```c

```
