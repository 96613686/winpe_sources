# RegisterForEMCPausedResumedCallbacks(void)

- ea: `0x180068640`
- end: `0x1800686e5`
- name: `?RegisterForEMCPausedResumedCallbacks@@YAJXZ`
- size: `165`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180072db4`

## callees

- `0x1800068f0`
- `0x180068640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006864d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006864d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800686d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800686d7`
- `ntdll!RtlNtStatusToDosError` at `0x180068694`
- `ntdll!RtlNtStatusToDosError` at `0x180068694`
- `api-ms-win-core-psm-app-l1-1-0!PsmRegisterAppStateChangeNotification` at `0x180068688`
- `api-ms-win-core-psm-app-l1-1-0!PsmRegisterAppStateChangeNotification` at `0x180068688`

## string_xrefs

- `0x1800686b3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\clientobjects.cpp`

## pseudocode

```c

```
