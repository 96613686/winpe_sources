# CheckInstalledVersionHint(HKEY__ *,CLocalComponentInfo *,ulong,ulong)

- ea: `0x18007c108`
- end: `0x18007c447`
- name: `?CheckInstalledVersionHint@@YAJPEAUHKEY__@@PEAVCLocalComponentInfo@@KK@Z`
- size: `831`
- prototype: `__int64 __fastcall(HKEY hKey, struct CLocalComponentInfo *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18007bd9c`
- `0x18007c548`
- `0x1800d1240`

## callees

- `0x18001db50`
- `0x18002fee0`
- `0x18007c108`
- `0x18007c450`
- `0x180128660`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18007c2d7`
- `msvcrt!memcpy_s` at `0x18007c2d7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c184`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c1e4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c184`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18007c1e4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007c3bd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x18007c3bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007c270`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007c30b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007c34f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007c270`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007c30b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18007c34f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c3f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c40e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c3f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007c40e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18007c3d1`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18007c3d1`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007c2b3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18007c2b3`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x18007c299`
- `api-ms-win-http-time-l1-1-0!InternetTimeToSystemTimeA` at `0x18007c299`

## string_xrefs

- `0x18007c1da`: `InstalledVersion`

## pseudocode

```c

```
