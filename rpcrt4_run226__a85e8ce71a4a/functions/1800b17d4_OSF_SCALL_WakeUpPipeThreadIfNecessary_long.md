# OSF_SCALL::WakeUpPipeThreadIfNecessary(long)

- ea: `0x1800b17d4`
- end: `0x1800b18c5`
- name: `?WakeUpPipeThreadIfNecessary@OSF_SCALL@@QEAAHJ@Z`
- size: `241`
- prototype: `__int64 __fastcall(OSF_SCALL *__hidden this, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180059af0`
- `0x18005a9ac`
- `0x180090f90`

## callees

- `0x180021ce0`
- `0x1800b17d4`
- `0x1800b3bf0`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800b1820`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b188b`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b1820`
- `ntdll!RtlLeaveCriticalSection` at `0x1800b188b`
- `ntdll!RtlEnterCriticalSection` at `0x1800b1800`
- `ntdll!RtlEnterCriticalSection` at `0x1800b186a`
- `ntdll!RtlEnterCriticalSection` at `0x1800b1800`
- `ntdll!RtlEnterCriticalSection` at `0x1800b186a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b1849`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800b1849`

## pseudocode

```c

```
