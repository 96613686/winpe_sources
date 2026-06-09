# SpoolerCtrlHandlerWindowsProtectedPrint(ulong,ulong,void *,void *)

- ea: `0x14003feb0`
- end: `0x140040266`
- name: `?SpoolerCtrlHandlerWindowsProtectedPrint@@YAKKKPEAX0@Z`
- size: `950`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x14001748c`
- `0x14002dd20`
- `0x140031720`
- `0x14003f56c`
- `0x14003f6c0`
- `0x14003feb0`
- `0x1400408b4`
- `0x140080828`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400401b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400401c5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400401b6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1400401c5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140040053`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140040106`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140040053`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x140040106`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140040246`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140040246`

## string_xrefs

- `0x140040230`: `Failed to send service stop request to worker process`

## pseudocode

```c

```
