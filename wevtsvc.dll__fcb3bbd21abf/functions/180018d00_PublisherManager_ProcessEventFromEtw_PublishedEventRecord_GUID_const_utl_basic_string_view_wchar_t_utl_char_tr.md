# PublisherManager::ProcessEventFromEtw(PublishedEventRecord &,_GUID const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,SYS_TEMPLATE const &,SYS_TEMPLATE const &)

- ea: `0x180018d00`
- end: `0x180019d22`
- name: `?ProcessEventFromEtw@PublisherManager@@QEAAXAEAVPublishedEventRecord@@AEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@AEBUSYS_TEMPLATE@@3@Z`
- size: `4130`
- prototype: `void __fastcall(PublisherManager *this, PublishedEventRecord *, struct _GUID *, _OWORD *, _QWORD *, __int64)`
- caller_count: `5`
- callee_count: `39`
- tags: `broker_com_uri`

## callers

- `0x18001827c`
- `0x1800183c0`
- `0x180018d00`
- `0x180063194`
- `0x180074b00`

## callees

- `0x180003de0`
- `0x1800062fc`
- `0x18000bf10`
- `0x180014bd0`
- `0x180016250`
- `0x180016ef0`
- `0x180017b60`
- `0x1800184c8`
- `0x180018d00`
- `0x180019d28`
- `0x180019d60`
- `0x18001a5bc`
- `0x18001bbc0`
- `0x180022100`
- `0x1800237b0`
- `0x1800248c0`
- `0x180024918`
- `0x180031a38`
- `0x180034924`
- `0x18003b0e8`
- `0x18003b87c`
- `0x18003cb38`
- `0x18003d170`
- `0x180055804`
- `0x18005cab8`
- `0x180063194`
- `0x18006599c`
- `0x1800701ac`
- `0x180074b00`
- `0x180078034`
- `0x18007aa1c`
- `0x180086c90`
- `0x180086d2c`
- `0x180086de4`
- `0x180091e34`
- `0x18009aee0`
- `0x1800d3364`
- `0x1800d3370`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018fba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018fe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001922d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001946f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800194cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800197dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019856`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800198d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019902`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018fba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018fe8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001922d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001946f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800194cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800197dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019856`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800198d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019902`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018fda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001921f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019461`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800194c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019848`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018fda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001921f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019461`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800194c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800197ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019848`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800198f4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018e0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800192ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019481`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001992f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180018e0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800192ba`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019481`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001992f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019499`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800194a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019965`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019c13`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018eb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019499`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800194a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019965`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019c13`

## string_xrefs

- `0x18001990d`: `Security`

## pseudocode

```c

```
