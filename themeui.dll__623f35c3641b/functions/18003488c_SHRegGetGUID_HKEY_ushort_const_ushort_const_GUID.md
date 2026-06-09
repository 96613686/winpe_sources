# SHRegGetGUID(HKEY__ *,ushort const *,ushort const *,_GUID *)

- ea: `0x18003488c`
- end: `0x180034949`
- name: `?SHRegGetGUID@@YAJPEAUHKEY__@@PEBG1PEAU_GUID@@@Z`
- size: `189`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180054290`
- `0x180056d14`

## callees

- `0x18003488c`
- `0x1800358c0`
- `0x18003633c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180034926`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180034926`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800348fa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800348fa`

## pseudocode

```c

```
