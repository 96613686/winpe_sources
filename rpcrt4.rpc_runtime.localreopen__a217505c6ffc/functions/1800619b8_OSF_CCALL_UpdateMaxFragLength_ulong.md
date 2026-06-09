# OSF_CCALL::UpdateMaxFragLength(ulong)

- ea: `0x1800619b8`
- end: `0x180061b1b`
- name: `?UpdateMaxFragLength@OSF_CCALL@@AEAAXK@Z`
- size: `355`
- prototype: `void __fastcall(OSF_CCALL *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18006173c`
- `0x1800618dc`
- `0x1800b0988`

## callees

- `0x1800619b8`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180061a94`
- `ntdll!RtlLeaveCriticalSection` at `0x180061a94`
- `ntdll!RtlEnterCriticalSection` at `0x180061a7c`
- `ntdll!RtlEnterCriticalSection` at `0x180061a7c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061b0a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061b0a`

## pseudocode

```c

```
