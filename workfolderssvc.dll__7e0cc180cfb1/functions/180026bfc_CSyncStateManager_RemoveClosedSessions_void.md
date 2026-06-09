# CSyncStateManager::RemoveClosedSessions(void)

- ea: `0x180026bfc`
- end: `0x180026f25`
- name: `?RemoveClosedSessions@CSyncStateManager@@QEAAXXZ`
- size: `809`
- prototype: `void __fastcall(CSyncStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: ``

## callers

- `0x18000f3b0`
- `0x180023e64`

## callees

- `0x180007e10`
- `0x1800083b4`
- `0x180008b60`
- `0x180009424`
- `0x180011314`
- `0x18001133c`
- `0x1800151c0`
- `0x180015a5c`
- `0x18001db80`
- `0x180023d28`
- `0x180026bfc`
- `0x180026f2c`
- `0x1800287a0`
- `0x180028830`
- `0x18002895c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180026da0`
- `KERNEL32!GetLastError` at `0x180026da0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180026d92`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180026d92`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180026e2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026d34`

## string_xrefs

- `0x180026c6d`: `CSyncStateManager::RemoveClosedSessions`

## pseudocode

```c

```
