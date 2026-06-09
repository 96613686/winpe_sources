# CWxSocket::Connect(sockaddr const *,ulong,void (*)(void *,ulong,ulong),void *,_WSABUF *)

- ea: `0x1800bb7fc`
- end: `0x1800bbbbd`
- name: `?Connect@CWxSocket@@QEAAJPEBUsockaddr@@KP6AXPEAXKK@Z1PEAU_WSABUF@@@Z`
- size: `961`
- prototype: `__int64 __usercall@<rax>(CWxSocket *__hidden this@<rcx>, const struct sockaddr *@<rdx>, unsigned int@<r8d>, void (*)(void *, unsigned int, unsigned int)@<r9>, void *, struct _WSABUF *)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x1800bc5c8`
- `0x1801b6f88`

## callees

- `0x18007a12c`
- `0x180087c14`
- `0x1800bb7fc`
- `0x1800bbbc4`
- `0x1800bebc8`
- `0x18014a7a0`
- `0x1801cf128`
- `0x1801dbf80`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb92f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800bb92f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb903`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800bb903`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bba59`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800bba59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb96b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800bb96b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb871`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bb871`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800bbb8b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800bbb8b`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800bba07`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800bba07`
- `WS2_32!WSAIoctl` at `0x1800bb9b8`
- `WS2_32!WSAIoctl` at `0x1800bb9b8`

## pseudocode

```c

```
