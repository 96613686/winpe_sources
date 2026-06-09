# ClientOperation::Complete(long,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,ProcessInformation *)

- ea: `0x18003816c`
- end: `0x180038708`
- name: `?Complete@ClientOperation@@QEAA_NJV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUProcessInformation@@@Z`
- size: `1436`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock)`
- caller_count: `4`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003d3b4`
- `0x18003d4cc`
- `0x1800470c0`
- `0x1800471c0`

## callees

- `0x180001700`
- `0x1800021a4`
- `0x180002f50`
- `0x1800033cc`
- `0x180006660`
- `0x18001801c`
- `0x180018df0`
- `0x18001a960`
- `0x18001ed48`
- `0x180038040`
- `0x18003816c`
- `0x180038710`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800382ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038581`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800382ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180038581`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800383d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800385a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800383d5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800385a9`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18003859a`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18003859a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038338`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038338`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038357`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180038357`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003842e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18003842e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038349`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003868e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038349`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003868e`

## string_xrefs

- `0x1800386c6`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`
- `0x1800386de`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`
- `0x1800386f6`: `onecore\vm\compute\dll\lib\core\clientoperation.cpp`

## pseudocode

```c

```
