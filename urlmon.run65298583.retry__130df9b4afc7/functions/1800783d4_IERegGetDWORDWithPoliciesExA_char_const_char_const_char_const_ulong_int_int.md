# IERegGetDWORDWithPoliciesExA(char const *,char const *,char const *,ulong,int *,int *)

- ea: `0x1800783d4`
- end: `0x180078643`
- name: `?IERegGetDWORDWithPoliciesExA@@YAKPEBD00KPEAH1@Z`
- size: `623`
- prototype: `unsigned int __fastcall(const char *, const char *, const char *, unsigned int, HKEY phkResult, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180078188`
- `0x18009d698`

## callees

- `0x1800783d4`

## import_xrefs

- `iertutil!__imp_IsPolicyKeyPresentA` at `0x180078416`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x180078447`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007855e`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x180078416`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x180078447`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007855e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007858c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800785f5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007858c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800785f5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800784a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800784e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180078534`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800784a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800784e9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x180078534`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800785c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007862c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800785c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007862c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800785cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078638`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800785cd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180078638`

## string_xrefs

- `0x180078511`: `Security_HKLM_Only`

## pseudocode

```c

```
