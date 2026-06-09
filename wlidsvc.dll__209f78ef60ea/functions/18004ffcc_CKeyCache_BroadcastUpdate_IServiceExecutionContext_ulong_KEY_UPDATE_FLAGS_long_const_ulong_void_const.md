# CKeyCache::BroadcastUpdate(IServiceExecutionContext *,ulong,KEY_UPDATE_FLAGS,long (*const)(ulong,void * const))

- ea: `0x18004ffcc`
- end: `0x18005035e`
- name: `?BroadcastUpdate@CKeyCache@@QEAAJPEAVIServiceExecutionContext@@KW4KEY_UPDATE_FLAGS@@Q6AJKQEAX@Z@Z`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180029c40`

## callees

- `0x18000ac0c`
- `0x18000c050`
- `0x18000d664`
- `0x18000d764`
- `0x18000d89c`
- `0x18000dec4`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015fb0`
- `0x1800167e4`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18004ffcc`
- `0x180050364`
- `0x1800872e4`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180050325`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180050325`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005005b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180050065`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18005005b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180050065`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005032f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005032f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050081`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180050081`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050051`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180050051`

## string_xrefs

- `0x180050038`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x1800502e1`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\keycache.cpp`
- `0x180050009`: `CKeyCache::BroadcastUpdate`
- `0x1800502da`: `CKeyCache::BroadcastUpdate`

## pseudocode

```c

```
