# CSoftDist::IsLogo3LocallyInstalled(ushort const *,ulong,ulong,char const *)

- ea: `0x1800c2304`
- end: `0x1800c2529`
- name: `?IsLogo3LocallyInstalled@CSoftDist@@AEAAJPEBGKKPEBD@Z`
- size: `549`
- prototype: `__int64 __fastcall(CSoftDist *this, const unsigned __int16 *, unsigned int, unsigned int, const char *Type)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800c1e08`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x1800c2304`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c2375`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c23c1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c2375`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800c23c1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c23ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c241f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c23ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800c241f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c2465`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c249c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c2465`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800c249c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c24df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c24f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c24df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c24f4`

## string_xrefs

- `0x1800c23e1`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c

```
