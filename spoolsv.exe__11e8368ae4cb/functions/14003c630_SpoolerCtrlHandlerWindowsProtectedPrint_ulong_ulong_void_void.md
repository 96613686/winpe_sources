# SpoolerCtrlHandlerWindowsProtectedPrint(ulong,ulong,void *,void *)

- ea: `0x14003c630`
- end: `0x14003c9c7`
- name: `?SpoolerCtrlHandlerWindowsProtectedPrint@@YAKKKPEAX0@Z`
- size: `919`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callees

- `0x1400160a0`
- `0x14002b810`
- `0x14002f030`
- `0x14003bd60`
- `0x14003beac`
- `0x14003c630`
- `0x14003cf44`
- `0x140079338`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003c92a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003c933`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003c92a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14003c933`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003c7d3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003c880`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003c7d3`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14003c880`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003c9ae`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003c9ae`

## string_xrefs

- `0x14003c998`: `Failed to send service stop request to worker process`

## pseudocode

```c

```
