# EdpCache::_AuditAndCheckAccess(ushort const *,ushort const *,Windows::Security::EnterpriseData::IProtectionPolicyAuditInfo *,Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)

- ea: `0x180072e40`
- end: `0x180073033`
- name: `?_AuditAndCheckAccess@EdpCache@@AEAAJPEBG0PEAUIProtectionPolicyAuditInfo@EnterpriseData@Security@Windows@@PEAW4ProtectionPolicyEvaluationResult@345@@Z`
- size: `499`
- prototype: `__int64 __fastcall(EdpCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Security::EnterpriseData::IProtectionPolicyAuditInfo *, enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180072884`

## callees

- `0x18001f6b0`
- `0x180028f0c`
- `0x18002beb8`
- `0x18002bee4`
- `0x180035590`
- `0x180072e40`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072ebc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072f8e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072ebc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180072f8e`

## string_xrefs

- `0x180072ecd`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180072fef`: `multimedia\wpd\ui\shellext\edpcache.cpp`
- `0x180072e91`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`
- `0x180072f63`: `Windows.Security.EnterpriseData.ProtectionPolicyManager`

## pseudocode

```c

```
