# Microsoft::Diagnostics::Utils::Os::IsPersonalizationAllowedByPolicyForUser(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)

- ea: `0x1802de91c`
- end: `0x1802debc3`
- name: `?IsPersonalizationAllowedByPolicyForUser@Os@Utils@Diagnostics@Microsoft@@SA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `679`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1802debcc`
- `0x1802ded70`

## callees

- `0x180002524`
- `0x1800035ec`
- `0x18005d050`
- `0x1800d0d9c`
- `0x18012f9b4`
- `0x18015f810`
- `0x1801812c4`
- `0x1802de91c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802dea94`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802deb49`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802deb6f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802dea94`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802deb49`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1802deb6f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802de933`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1802de933`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x1802de984`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_IsPolicySetByMobileDeviceManager` at `0x1802de984`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1802dea18`
- `ext-ms-win-devmgmt-policy-l1-1-0!PolicyManager_GetPolicyInt` at `0x1802dea18`

## pseudocode

```c

```
