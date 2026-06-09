# HandGet(HKEY__ *,ushort const *,ushort const *,ushort *)

- ea: `0x18001ec70`
- end: `0x18001ed3a`
- name: `?HandGet@@YAHPEAUHKEY__@@PEBG1PEAG@Z`
- size: `202`
- prototype: `int(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d490`
- `0x1800328e8`

## callees

- `0x18001ec70`
- `0x180058a60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ed29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ed29`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ecac`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ecac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ecda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ed09`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ecda`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ed09`

## pseudocode

```c

```
