# ReplyPrinterChangeNotificationWorker(void *,ulong,ulong,ulong *,_PRINTER_NOTIFY_INFO *,int,int *)

- ea: `0x140066f9c`
- end: `0x140067250`
- name: `?ReplyPrinterChangeNotificationWorker@@YAHPEAXKKPEAKPEAU_PRINTER_NOTIFY_INFO@@HPEAH@Z`
- size: `692`
- prototype: `__int64 __usercall@<rax>(struct _PRINTHANDLE *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned int *@<r9>, struct _PRINTER_NOTIFY_INFO *, int, int *)`
- caller_count: `6`
- callee_count: `9`
- tags: ``

## callers

- `0x14005c8e0`
- `0x140066e50`
- `0x140068680`
- `0x140068840`
- `0x140068e30`
- `0x140068e70`

## callees

- `0x14000fa7c`
- `0x1400122f0`
- `0x140013fe8`
- `0x1400140cc`
- `0x140066ca8`
- `0x140066f9c`
- `0x140067e48`
- `0x140068918`
- `0x14006f580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400670fc`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1400670fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006718a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140067240`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006718a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140067240`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140066fd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400671ea`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140066fd7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400671ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140067106`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140067144`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400671ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140067144`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400671ae`

## string_xrefs

- `0x1400671f3`: `ThreadNotify`
- `0x14006722a`: `In List already 0x%p, refcount %d.`
- `0x140067207`: `Link added 0x%p, refcount %d.`

## pseudocode

```c

```
