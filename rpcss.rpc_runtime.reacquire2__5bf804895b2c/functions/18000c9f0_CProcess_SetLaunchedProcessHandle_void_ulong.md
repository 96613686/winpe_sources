# CProcess::SetLaunchedProcessHandle(void *,ulong)

- ea: `0x18000c9f0`
- end: `0x18000caf1`
- name: `?SetLaunchedProcessHandle@CProcess@@QEAAJPEAXK@Z`
- size: `257`
- prototype: `__int64 __fastcall(CProcess *__hidden this, HANDLE hSourceHandle, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c894`

## callees

- `0x18000c9f0`
- `0x18000ce5c`
- `0x180031b98`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ca2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ca2b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000ca8a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18000ca8a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ca5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca13`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ca13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000caa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cada`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000caa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000cada`

## string_xrefs

- `0x18000cabf`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c

```
