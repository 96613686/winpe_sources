# CIndexedDBServerFactoryWithSecurityContext::GetDatabaseHelper(ulong,ushort const *,std::shared_ptr<IQuotaSession> const &,CIndexedDBServerDatabase * *)

- ea: `0x180045c4c`
- end: `0x180045f54`
- name: `?GetDatabaseHelper@CIndexedDBServerFactoryWithSecurityContext@@IEAAJKPEBGAEBV?$shared_ptr@UIQuotaSession@@@std@@PEAPEAVCIndexedDBServerDatabase@@@Z`
- size: `776`
- prototype: `__int64 __fastcall(__int64, unsigned int, const wchar_t *, __int64, CIndexedDBServerDatabase **)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18002bf80`

## callees

- `0x18002078c`
- `0x180024650`
- `0x18002fab0`
- `0x180033c7c`
- `0x180045210`
- `0x180045c4c`
- `0x18004604c`
- `0x1800460b0`
- `0x180046110`
- `0x18004fd6c`
- `0x1800814bc`
- `0x180081b10`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e1c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045c9f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180045e1c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045d56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180045d56`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045e8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180045e8b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ed4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045e3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045ed4`

## pseudocode

```c

```
