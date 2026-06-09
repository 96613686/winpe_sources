# CPolicyCache::_GetQfeValue(SHPOLICYTABLE_ const *,_GUID const &,void *,ulong *)

- ea: `0x180005724`
- end: `0x18000588f`
- name: `?_GetQfeValue@CPolicyCache@@CAJPEBUSHPOLICYTABLE_@@AEBU_GUID@@PEAXPEAK@Z`
- size: `363`
- prototype: `static int(const struct SHPOLICYTABLE_ *, const struct _GUID *, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004df0`

## callees

- `0x18000450c`
- `0x180005534`
- `0x180005724`
- `0x180066910`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800057c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005826`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800057c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005826`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005884`

## pseudocode

```c

```
