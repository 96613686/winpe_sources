# GetRegistrySecurityDescriptor(HKEY__ *,ushort const *,_SECURITY_DESCRIPTOR * *,ulong *)

- ea: `0x180064c50`
- end: `0x180064ec8`
- name: `?GetRegistrySecurityDescriptor@@YAJPEAUHKEY__@@PEBGPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z`
- size: `632`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct _SECURITY_DESCRIPTOR **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800782dc`

## callees

- `0x180034260`
- `0x180064c50`
- `0x180069914`
- `0x1800d2db0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064da4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064d57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064da4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180064e44`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064d00`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180064d00`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064caf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064d39`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064caf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064d39`

## string_xrefs

- `0x180064de9`: `onecore\com\combase\catalog\services.cxx`
- `0x180064e80`: `onecore\com\combase\catalog\services.cxx`
- `0x180064dde`: `GetRegistrySecurityDescriptor`
- `0x180064e74`: `GetRegistrySecurityDescriptor`

## pseudocode

```c

```
