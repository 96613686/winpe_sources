# OSF_SCALL::WakeUpPipeThreadIfNecessary(long)

- ea: `0x1800b55e8`
- end: `0x1800b56f8`
- name: `?WakeUpPipeThreadIfNecessary@OSF_SCALL@@QEAAHJ@Z`
- size: `272`
- prototype: `__int64 __fastcall(OSF_SCALL *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180062120`
- `0x180063010`
- `0x180094e20`

## callees

- `0x180022e80`
- `0x1800b55e8`
- `0x1800b7c30`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800b563a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b56b7`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b563a`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b56b7`
- `ntdll!RtlEnterCriticalSection` at `0x1800b5614`
- `ntdll!RtlEnterCriticalSection` at `0x1800b5690`
- `ntdll!RtlEnterCriticalSection` at `0x1800b5614`
- `ntdll!RtlEnterCriticalSection` at `0x1800b5690`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b5669`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b5669`

## pseudocode

```c

```
