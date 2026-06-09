# CVIQueryManager::FindOffsetToValue(ulong,UserSID *,ulong,ulong)

- ea: `0x1801ca00c`
- end: `0x1801ca13f`
- name: `?FindOffsetToValue@CVIQueryManager@@QEAA?AV?$MPtr@VCOffsetToValue@@@@KPEAVUserSID@@KK@Z`
- size: `307`
- prototype: `__int64 __usercall@<rax>(LPCRITICAL_SECTION lpCriticalSection@<rcx>, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1801d0cd0`

## callees

- `0x1800ada08`
- `0x180179da0`
- `0x180179de0`
- `0x1801ca00c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ca03d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ca08a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ca03d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1801ca08a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801ca0dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801ca11d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801ca0dd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1801ca11d`

## pseudocode

```c

```
