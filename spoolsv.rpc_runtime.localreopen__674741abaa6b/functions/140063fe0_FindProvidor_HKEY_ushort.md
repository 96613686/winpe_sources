# FindProvidor(HKEY__ *,ushort *)

- ea: `0x140063fe0`
- end: `0x1400640ec`
- name: `?FindProvidor@@YAPEAU_PROVIDOR@@PEAUHKEY__@@PEAG@Z`
- size: `268`
- prototype: `struct _PROVIDOR *__fastcall(HKEY, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14006457c`
- `0x140064ca0`

## callees

- `0x14002d0a0`
- `0x140063fe0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006408f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006408f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400640ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400640ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140064026`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140064026`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006405c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14006405c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400640c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140064071`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400640c4`

## pseudocode

```c

```
