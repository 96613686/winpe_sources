# Microsoft::Diagnostics::UtcWatchdog::AcquireTimeoutsMutex(std::unique_lock<std::timed_mutex> &)

- ea: `0x180040258`
- end: `0x18004044d`
- name: `?AcquireTimeoutsMutex@UtcWatchdog@Diagnostics@Microsoft@@AEAA_NAEAV?$unique_lock@Vtimed_mutex@std@@@std@@@Z`
- size: `501`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180198694`
- `0x1801b2f70`
- `0x1801b3b10`

## callees

- `0x18001cf30`
- `0x180040258`
- `0x180040a38`
- `0x180040b90`
- `0x1800d2ee8`
- `0x1800dbc08`
- `0x180190328`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180040375`
- `msvcp_win!_Mtx_unlock` at `0x180040375`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040423`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040435`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040423`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180040435`
- `msvcp_win!_Mtx_lock` at `0x18004031c`
- `msvcp_win!_Mtx_lock` at `0x18004031c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800403e7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800403e7`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18004028f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18004028f`

## string_xrefs

- `0x1800403fd`: `onecore\base\telemetry\utc\service\include\UtcWatchdog.h`

## pseudocode

```c

```
