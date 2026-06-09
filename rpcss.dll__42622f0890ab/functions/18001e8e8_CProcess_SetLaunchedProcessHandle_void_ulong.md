# CProcess::SetLaunchedProcessHandle(void *,ulong)

- ea: `0x18001e8e8`
- end: `0x18001e9be`
- name: `?SetLaunchedProcessHandle@CProcess@@QEAAJPEAXK@Z`
- size: `214`
- prototype: `__int64 __fastcall(CProcess *this, HANDLE hSourceHandle, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001e9c4`

## callees

- `0x18001cbf8`
- `0x18001e8e8`
- `0x18001ec28`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e91d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e91d`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e96a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18001e96a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e940`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e937`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e940`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e90b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e90b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e97c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e9ad`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e97c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e9ad`

## string_xrefs

- `0x18001e992`: `onecore\com\combase\rpcss\objex\process.cxx`

## pseudocode

```c

```
