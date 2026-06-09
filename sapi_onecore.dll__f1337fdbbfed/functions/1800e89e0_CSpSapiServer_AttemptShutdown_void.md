# CSpSapiServer::AttemptShutdown(void)

- ea: `0x1800e89e0`
- end: `0x1800e8b29`
- name: `?AttemptShutdown@CSpSapiServer@@AEAAJXZ`
- size: `329`
- prototype: `__int64 __fastcall(CSpSapiServer *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800e9a40`

## callees

- `0x18000e570`
- `0x180013ec0`
- `0x180045938`
- `0x1800e89e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e8a7b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800e8a7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e8aaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e8aee`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e8aaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800e8aee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e8a2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e8a99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e8a2b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800e8a99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8afc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8afc`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!KillTimer` at `0x1800e8ae5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!KillTimer` at `0x1800e8ae5`

## string_xrefs

- `0x1800e8a81`: `Set stop server event. Sapisvr.exe will now shutdown completely.`

## pseudocode

```c

```
