# SvcControl(ulong,ulong,void *,void *)

- ea: `0x180084a10`
- end: `0x180084baa`
- name: `?SvcControl@@YAKKKPEAX0@Z`
- size: `410`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180084a10`
- `0x1800cf008`
- `0x1800d2124`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084a3f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180084a3f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084a73`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180084a73`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084b6a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180084b6a`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180084a66`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180084a66`

## pseudocode

```c

```
