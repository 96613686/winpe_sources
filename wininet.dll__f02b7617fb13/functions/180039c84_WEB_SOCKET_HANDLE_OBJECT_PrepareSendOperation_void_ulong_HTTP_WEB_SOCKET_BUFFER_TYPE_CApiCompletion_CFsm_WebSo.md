# WEB_SOCKET_HANDLE_OBJECT::PrepareSendOperation(void *,ulong,_HTTP_WEB_SOCKET_BUFFER_TYPE,CApiCompletion * *,CFsm_WebSocketSend * *)

- ea: `0x180039c84`
- end: `0x18003a1a3`
- name: `?PrepareSendOperation@WEB_SOCKET_HANDLE_OBJECT@@QEAAKPEAXKW4_HTTP_WEB_SOCKET_BUFFER_TYPE@@PEAPEAVCApiCompletion@@PEAPEAVCFsm_WebSocketSend@@@Z`
- size: `1311`
- prototype: `unsigned int __usercall@<eax>(WEB_SOCKET_HANDLE_OBJECT *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, enum _HTTP_WEB_SOCKET_BUFFER_TYPE@<r9d>, struct CApiCompletion **, struct CFsm_WebSocketSend **)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18003990c`

## callees

- `0x18000baa0`
- `0x18002ba10`
- `0x180038610`
- `0x180038c40`
- `0x180039bdc`
- `0x180039c84`
- `0x18003a1ac`
- `0x18003ab04`
- `0x18003b7fc`
- `0x18003c050`
- `0x18010fc90`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039db5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ead`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039db5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039ead`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039e86`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039d07`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039e86`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003a12f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003a12f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039d6c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180039e1a`

## pseudocode

```c

```
