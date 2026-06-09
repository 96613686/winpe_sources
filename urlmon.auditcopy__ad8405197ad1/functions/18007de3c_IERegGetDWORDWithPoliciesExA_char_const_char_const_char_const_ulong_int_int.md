# IERegGetDWORDWithPoliciesExA(char const *,char const *,char const *,ulong,int *,int *)

- ea: `0x18007de3c`
- end: `0x18007e0f4`
- name: `?IERegGetDWORDWithPoliciesExA@@YAKPEBD00KPEAH1@Z`
- size: `696`
- prototype: `__int64 __fastcall(const char *, const char *, const char *, DWORD, HKEY phkResult)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007dbe0`
- `0x1800a435c`

## callees

- `0x18007de3c`

## import_xrefs

- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007de7e`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007deb5`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007dfe5`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007de7e`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007deb5`
- `iertutil!__imp_IsPolicyKeyPresentA` at `0x18007dfe5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007e019`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007e094`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007e019`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007e094`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007df15`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007df63`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007dfb5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007df15`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007df63`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007dfb5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007e054`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007e0d1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007e054`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007e0d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0e3`

## string_xrefs

- `0x18007df92`: `Security_HKLM_Only`

## pseudocode

```c

```
