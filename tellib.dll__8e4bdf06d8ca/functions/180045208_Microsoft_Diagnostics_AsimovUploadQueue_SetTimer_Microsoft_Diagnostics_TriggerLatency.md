# Microsoft::Diagnostics::AsimovUploadQueue::SetTimer(Microsoft::Diagnostics::TriggerLatency)

- ea: `0x180045208`
- end: `0x180045681`
- name: `?SetTimer@AsimovUploadQueue@Diagnostics@Microsoft@@QEAAXVTriggerLatency@23@@Z`
- size: `1145`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005ecd8`
- `0x1800fe34c`

## callees

- `0x18001ca90`
- `0x18001e328`
- `0x180045208`
- `0x1800a0d08`
- `0x1800bc2e0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180045447`
- `msvcp_win!_Mtx_unlock` at `0x180045663`
- `msvcp_win!_Mtx_unlock` at `0x180045447`
- `msvcp_win!_Mtx_unlock` at `0x180045663`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800455b6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800455cf`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800455b6`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x1800455cf`
- `msvcp_win!_Mtx_lock` at `0x180045272`
- `msvcp_win!_Mtx_lock` at `0x180045272`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045646`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180045646`

## string_xrefs

- `0x180045634`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`
- `0x18004559f`: `onecore\base\telemetry\utc\service\include\LifetimeManager.h`

## pseudocode

```c

```
