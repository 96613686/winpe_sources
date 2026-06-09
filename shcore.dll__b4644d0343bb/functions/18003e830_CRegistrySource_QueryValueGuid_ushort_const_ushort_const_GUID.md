# CRegistrySource::QueryValueGuid(ushort const *,ushort const *,_GUID *)

- ea: `0x18003e830`
- end: `0x18003e8ce`
- name: `?QueryValueGuid@CRegistrySource@@UEAAJPEBG0PEAU_GUID@@@Z`
- size: `158`
- prototype: `int(CRegistrySource *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18003e830`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e87d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003e87d`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003e8c4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18003e8c4`

## pseudocode

```c

```
