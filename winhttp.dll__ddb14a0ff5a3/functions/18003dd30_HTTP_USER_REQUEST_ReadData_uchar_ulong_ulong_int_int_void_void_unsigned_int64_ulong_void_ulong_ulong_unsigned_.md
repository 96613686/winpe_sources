# HTTP_USER_REQUEST::ReadData(uchar *,ulong,ulong *,int,int,void (*)(void *,unsigned __int64,ulong,void *,ulong),ulong,unsigned __int64)

- ea: `0x18003dd30`
- end: `0x18003e236`
- name: `?ReadData@HTTP_USER_REQUEST@@QEAAKPEAEKPEAKHHP6AXPEAX_KK2K@ZK3@Z`
- size: `1286`
- prototype: `unsigned int __usercall@<eax>(HTTP_USER_REQUEST *__hidden this@<rcx>, unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, int, int, void (*)(void *, unsigned __int64, unsigned int, void *, unsigned int), unsigned int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18003caf0`

## callees

- `0x180037600`
- `0x180037b20`
- `0x180039160`
- `0x18003dd30`
- `0x1800a2660`
- `0x1800cdd7c`
- `0x1800cf58c`
- `0x1800db704`
- `0x1800dd2e4`
- `0x1800de010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dd88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003decd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dfa3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dd88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003decd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003dfa3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ddb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003df06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003df8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dfc3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ddb7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003df06`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003df8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003dfc3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003dde6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003dde6`

## string_xrefs

- `0x18003de10`: `ReadData`

## pseudocode

```c

```
