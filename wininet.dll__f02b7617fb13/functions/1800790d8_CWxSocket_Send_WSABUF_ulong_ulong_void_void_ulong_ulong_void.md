# CWxSocket::Send(_WSABUF *,ulong,ulong *,void (*)(void *,ulong,ulong),void *)

- ea: `0x1800790d8`
- end: `0x180079412`
- name: `?Send@CWxSocket@@QEAAJPEAU_WSABUF@@KPEAKP6AXPEAXKK@Z2@Z`
- size: `826`
- prototype: `__int64 __usercall@<rax>(CWxSocket *__hidden this@<rcx>, LPWSABUF lpBuffers@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, void (*)(void *, unsigned int, unsigned int), void *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800ea8a4`

## callees

- `0x1800790d8`
- `0x18007a12c`
- `0x180087c14`
- `0x1800bbbc4`
- `0x1800e2fe8`
- `0x18014a3a4`
- `0x18014a7a0`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007921d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007921d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800791e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800791e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800792b5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800792b5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180079231`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180079231`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079149`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180079149`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007929b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18007929b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007925c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18007925c`
- `WS2_32!WSASend` at `0x180079284`
- `WS2_32!WSASend` at `0x180079284`

## pseudocode

```c

```
