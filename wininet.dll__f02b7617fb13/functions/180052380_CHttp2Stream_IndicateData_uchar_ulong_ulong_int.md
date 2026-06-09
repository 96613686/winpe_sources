# CHttp2Stream::IndicateData(uchar *,ulong,ulong,int)

- ea: `0x180052380`
- end: `0x180052a55`
- name: `?IndicateData@CHttp2Stream@@QEAAXPEAEKKH@Z`
- size: `1749`
- prototype: `void __usercall(CHttp2Stream *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, int)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800504c4`
- `0x180051edc`

## callees

- `0x180009cf0`
- `0x18000baa0`
- `0x18004f064`
- `0x180050d70`
- `0x180052380`
- `0x180052a5c`
- `0x180052d00`
- `0x180053858`
- `0x18008a970`
- `0x1800e0e0c`
- `0x180125220`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x1801d7618`
- `0x1801e1790`
- `0x1801e3c78`
- `0x1801e41b0`
- `0x1801e8d44`
- `0x1801e9d2c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800524c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005250a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800524c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005250a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052402`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180052402`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180052802`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180052802`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005280a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005280a`
- `ntdll!EtwEventActivityIdControl` at `0x1800525a6`
- `ntdll!EtwEventActivityIdControl` at `0x1800525df`
- `ntdll!EtwEventActivityIdControl` at `0x1800525a6`
- `ntdll!EtwEventActivityIdControl` at `0x1800525df`

## pseudocode

```c

```
