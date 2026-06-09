# FindProvidor(HKEY__ *,ushort *)

- ea: `0x14005e334`
- end: `0x14005e41b`
- name: `?FindProvidor@@YAPEAU_PROVIDOR@@PEAUHKEY__@@PEAG@Z`
- size: `231`
- prototype: `struct _PROVIDOR *__fastcall(HKEY, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14005e8ac`
- `0x14005ef30`

## callees

- `0x14002abc0`
- `0x14005e334`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005e3d1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14005e3d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005e3ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14005e3ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005e37a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14005e37a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005e3aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14005e3aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e3b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e3fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e3b9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005e3fa`

## pseudocode

```c

```
