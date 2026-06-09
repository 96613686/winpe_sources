# RefreshAllUserSessions(_WLAN_SESSION_CONTEXT *)

- ea: `0x180036920`
- end: `0x180036df4`
- name: `?RefreshAllUserSessions@@YAKPEAU_WLAN_SESSION_CONTEXT@@@Z`
- size: `1236`
- prototype: `unsigned int __fastcall(struct _WLAN_SESSION_CONTEXT *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003702c`

## callees

- `0x18000aa0c`
- `0x180011530`
- `0x180029ed4`
- `0x180036214`
- `0x18003666c`
- `0x180036920`
- `0x180036dfc`
- `0x180036ef4`
- `0x18003765c`
- `0x180106340`
- `0x180108288`
- `0x180108474`
- `0x180163294`
- `0x18016339c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036bd0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036bd0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800369ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036a22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036c14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180036c14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036d1f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180036d1f`
- `ntdll!RtlGetActiveConsoleId` at `0x1800369c0`
- `ntdll!RtlGetActiveConsoleId` at `0x1800369c0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180036a18`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x180036a18`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180036b91`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180036b91`

## pseudocode

```c

```
