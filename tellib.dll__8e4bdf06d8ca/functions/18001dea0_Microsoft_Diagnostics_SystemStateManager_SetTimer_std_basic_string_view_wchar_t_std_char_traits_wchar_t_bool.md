# Microsoft::Diagnostics::SystemStateManager::SetTimer(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool)

- ea: `0x18001dea0`
- end: `0x18001e322`
- name: `?SetTimer@SystemStateManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N@Z`
- size: `1154`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005d700`
- `0x1800675d4`
- `0x1800ef820`
- `0x1801900b0`
- `0x1801cdee8`
- `0x1801ce2c8`
- `0x18020f838`
- `0x18025eb50`
- `0x18028d7d0`
- `0x18028ec4c`

## callees

- `0x18001ca90`
- `0x18001dea0`
- `0x18001e328`
- `0x1800bc2e0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001e0de`
- `msvcp_win!_Mtx_unlock` at `0x18001e26b`
- `msvcp_win!_Mtx_unlock` at `0x18001e0de`
- `msvcp_win!_Mtx_unlock` at `0x18001e26b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001e28e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001e2a7`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001e28e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001e2a7`
- `msvcp_win!_Mtx_lock` at `0x18001ded0`
- `msvcp_win!_Mtx_lock` at `0x18001ded0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e24e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e24e`

## string_xrefs

- `0x18001e310`: `onecore\base\telemetry\utc\service\engine\systemstatemanager.cpp`

## pseudocode

```c

```
