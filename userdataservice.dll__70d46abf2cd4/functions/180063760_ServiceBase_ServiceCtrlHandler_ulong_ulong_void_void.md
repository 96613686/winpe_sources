# ServiceBase::_ServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180063760`
- end: `0x18006399a`
- name: `?_ServiceCtrlHandler@ServiceBase@@CAKKKPEAX0@Z`
- size: `570`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180007760`
- `0x180063760`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006379c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006379c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800638cd`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800638cd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800637b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800637e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800638e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800637b3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800637e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800638e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800638b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800638b9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800638ab`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800638ab`

## pseudocode

```c

```
