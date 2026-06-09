# CClientUtils::ReadRegistryExpandString(ushort const *,ushort const *,ushort * *,int *,UT_REGREAD_LOCATION)

- ea: `0x180082d80`
- end: `0x180083041`
- name: `?ReadRegistryExpandString@CClientUtils@@UEAAHPEBG0PEAPEAGPEAHW4UT_REGREAD_LOCATION@@@Z`
- size: `705`
- prototype: `int __high(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, int *, enum UT_REGREAD_LOCATION)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ece0`
- `0x180082aa0`
- `0x180082d80`
- `0x180087938`
- `0x180087b50`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180082f89`
- `ADVAPI32!RegCloseKey` at `0x180082f89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082f4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180082f4b`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180082f38`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180082f65`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180082f38`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180082f65`

## string_xrefs

- `0x180082e24`: `Unable to get AppContainer registry location.`

## pseudocode

```c

```
