# CProcess::GetProcessHandle(ulong,void * *)

- ea: `0x180059be4`
- end: `0x180059e11`
- name: `?GetProcessHandle@CProcess@@QEBAJKPEAPEAX@Z`
- size: `557`
- prototype: `__int64 __fastcall(CProcess *this, DWORD, void **)`
- caller_count: `7`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000866c`
- `0x18001b054`
- `0x180023230`
- `0x180053950`
- `0x18005970c`
- `0x1800599dc`
- `0x1800beab4`

## callees

- `0x18001ec28`
- `0x180025310`
- `0x18002ba28`
- `0x180034540`
- `0x180059be4`
- `0x18005ba08`
- `0x1800a1e98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059d48`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059c54`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059cfe`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059c54`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180059cfe`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180059d3c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180059d3c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059cca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059cca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180059cd7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180059dd0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180059dd0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059c0b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180059c0b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059c66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059ca6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059c66`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180059ca6`

## string_xrefs

- `0x180059c81`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059d16`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059db1`: `onecore\com\combase\rpcss\objex\process.cxx`
- `0x180059d8b`: `onecore\com\combase\rpcss\objex\token.cxx`
- `0x180059d84`: `CToken::Impersonate`

## pseudocode

```c

```
