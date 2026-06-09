# Microsoft::Diagnostics::EventBlockCache::IsTriggerAllowedByPrivacyPolicy(Microsoft::Diagnostics::ITriggerInst const &,unsigned __int64 *)

- ea: `0x1800669a0`
- end: `0x1800675cc`
- name: `?IsTriggerAllowedByPrivacyPolicy@EventBlockCache@Diagnostics@Microsoft@@QEAA_NAEBVITriggerInst@23@PEA_K@Z`
- size: `3116`
- prototype: `bool(Microsoft::Diagnostics::EventBlockCache *__hidden this, const struct Microsoft::Diagnostics::ITriggerInst *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005ecd8`
- `0x180080e20`

## callees

- `0x18001d160`
- `0x180024e2c`
- `0x180024fb0`
- `0x1800333b0`
- `0x18003f14c`
- `0x18003f4e8`
- `0x180046ab0`
- `0x180049380`
- `0x18004f298`
- `0x1800502bc`
- `0x1800508e0`
- `0x180058f8c`
- `0x18005b974`
- `0x18005c8d4`
- `0x18006634c`
- `0x1800669a0`
- `0x180068174`
- `0x1800a4df0`
- `0x18012de40`
- `0x18012e324`
- `0x18012eae4`
- `0x180177bbc`
- `0x180190328`
- `0x1801b7eac`
- `0x1801b7fb4`
- `0x180346010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18006750f`
- `msvcp_win!_Mtx_unlock` at `0x180067537`
- `msvcp_win!_Mtx_unlock` at `0x18006750f`
- `msvcp_win!_Mtx_unlock` at `0x180067537`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180067448`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006746b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180067448`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18006746b`
- `msvcp_win!_Mtx_lock` at `0x180067433`
- `msvcp_win!_Mtx_lock` at `0x180067433`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180066f91`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180066f91`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067408`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180067408`

## string_xrefs

- `0x180066fba`: `EventBlockCache_AllowListEmpty`
- `0x1800675ba`: `onecore\base\telemetry\utc\service\engine\eventblockcache.cpp`

## pseudocode

```c

```
