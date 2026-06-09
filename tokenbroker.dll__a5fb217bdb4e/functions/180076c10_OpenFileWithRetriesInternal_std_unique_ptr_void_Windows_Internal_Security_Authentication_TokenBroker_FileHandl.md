# OpenFileWithRetriesInternal(std::unique_ptr<void *,Windows::Internal::Security::Authentication::TokenBroker::FileHandleDeleter> &,Windows::Internal::String const &,FileAccessType,ulong *,ulong)

- ea: `0x180076c10`
- end: `0x180076f55`
- name: `?OpenFileWithRetriesInternal@@YAJAEAV?$unique_ptr@PEAXUFileHandleDeleter@TokenBroker@Authentication@Security@Internal@Windows@@@std@@AEBVString@Internal@Windows@@W4FileAccessType@@PEAKK@Z`
- size: `837`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180076ad0`
- `0x180112144`

## callees

- `0x18000730c`
- `0x18000bd40`
- `0x18003ea90`
- `0x180045a04`
- `0x180049878`
- `0x18004ac04`
- `0x18004ba4c`
- `0x180056ea4`
- `0x180076c10`
- `0x18007f07c`
- `0x18008e690`
- `0x180110d70`
- `0x180110fd0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180076e4c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180076e4c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076d9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180076d9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076d54`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180076d54`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076de0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180076de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076d2a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076c7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180076d2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076e9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180076e9e`

## string_xrefs

- `0x180076ecf`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`
- `0x180076f11`: `onecore\ds\security\tokenbroker\datastore\lib\filestore.cpp`

## pseudocode

```c

```
