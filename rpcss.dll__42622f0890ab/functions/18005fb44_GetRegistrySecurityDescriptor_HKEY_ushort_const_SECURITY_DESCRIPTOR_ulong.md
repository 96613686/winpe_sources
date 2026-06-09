# GetRegistrySecurityDescriptor(HKEY__ *,ushort const *,_SECURITY_DESCRIPTOR * *,ulong *)

- ea: `0x18005fb44`
- end: `0x18005fd97`
- name: `?GetRegistrySecurityDescriptor@@YAJPEAUHKEY__@@PEBGPEAPEAU_SECURITY_DESCRIPTOR@@PEAK@Z`
- size: `595`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, struct _SECURITY_DESCRIPTOR_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180073bd4`

## callees

- `0x180034540`
- `0x18005fb44`
- `0x180064c28`
- `0x1800ccb70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fc39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fc80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fd1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fc39`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fc80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005fd1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fbee`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005fbee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005fba3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005fc21`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005fba3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005fc21`

## string_xrefs

- `0x18005fcbf`: `onecore\com\combase\catalog\services.cxx`
- `0x18005fd50`: `onecore\com\combase\catalog\services.cxx`
- `0x18005fcb4`: `GetRegistrySecurityDescriptor`
- `0x18005fd44`: `GetRegistrySecurityDescriptor`

## pseudocode

```c

```
