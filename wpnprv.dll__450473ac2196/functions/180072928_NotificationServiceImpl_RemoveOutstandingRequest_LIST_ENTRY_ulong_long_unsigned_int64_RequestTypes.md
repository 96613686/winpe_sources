# NotificationServiceImpl::RemoveOutstandingRequest(_LIST_ENTRY *,ulong,long *,unsigned __int64 *,_RequestTypes *)

- ea: `0x180072928`
- end: `0x180072a58`
- name: `?RemoveOutstandingRequest@NotificationServiceImpl@@AEAAJPEAU_LIST_ENTRY@@KPEAJPEA_KPEAW4_RequestTypes@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(NotificationServiceImpl *__hidden this, struct _LIST_ENTRY *, unsigned int, int *, unsigned __int64 *, enum _RequestTypes *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18006f850`

## callees

- `0x18000fe54`
- `0x18001c06c`
- `0x180072928`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072a0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180072a0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007298d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007298d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800729fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800729fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800729f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800729f0`

## pseudocode

```c

```
