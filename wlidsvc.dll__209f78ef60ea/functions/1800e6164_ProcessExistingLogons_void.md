# ProcessExistingLogons(void)

- ea: `0x1800e6164`
- end: `0x1800e6373`
- name: `?ProcessExistingLogons@@YAXXZ`
- size: `527`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180078a50`

## callees

- `0x1800023c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18002351c`
- `0x18005538c`
- `0x18008a314`
- `0x18008c554`
- `0x1800a63ec`
- `0x1800e6164`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e61ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e61ea`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800e61e0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x1800e61e0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800e6288`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800e6288`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800e62aa`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x1800e62aa`

## string_xrefs

- `0x1800e61a2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\liveconnector.cpp`
- `0x1800e6210`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\liveconnector.cpp`
- `0x1800e6250`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\liveconnector.cpp`
- `0x1800e62f5`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\liveconnector.cpp`
- `0x1800e6243`: `CreateProcessUserTask for session id %d for %s.`

## pseudocode

```c

```
