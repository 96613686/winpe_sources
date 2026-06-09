# CSusService::InitProviders(void)

- ea: `0x180060d90`
- end: `0x18006152a`
- name: `?InitProviders@CSusService@@AEAAJXZ`
- size: `1946`
- prototype: `__int64 __fastcall(CSusService *__hidden this)`
- caller_count: `3`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005d4b8`
- `0x1800606e8`
- `0x180060c10`

## callees

- `0x18000c824`
- `0x18000def4`
- `0x180014964`
- `0x180060920`
- `0x180060d90`
- `0x180062898`
- `0x1800d9e30`
- `0x18010eec4`
- `0x180110914`
- `0x18011098c`
- `0x180113ae8`
- `0x18011ce34`
- `0x180128814`
- `0x18012b618`
- `0x18012bed4`
- `0x1801cd8e8`
- `0x180238960`
- `0x180239110`
- `0x180240cc0`
- `0x180240d40`
- `0x180241780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800612cd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800612f9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800612cd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800612f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060e92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060ecf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060f09`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060e92`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060ecf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060f09`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060ead`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060efb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f32`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060ead`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060efb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800611fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800611fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800610f8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800610f8`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800611d7`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800611d7`

## string_xrefs

- `0x180061079`: `Failed to initialize WSUS endpoint provider for service %ws`
- `0x180061355`: `Failed to initialize SLS endpoint provider for service %ws`
- `0x180061470`: `Service %ws using no STS token`
- `0x180061438`: `Service %ws using plugin STS token with plugin %ws.`
- `0x1800610ea`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c

```
