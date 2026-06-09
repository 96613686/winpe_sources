# CInstClassFactory::GetKeyForNotifications(HKEY__ * *)

- ea: `0x18022b550`
- end: `0x18022b7b3`
- name: `?GetKeyForNotifications@CInstClassFactory@@AEAAJPEAPEAUHKEY__@@@Z`
- size: `611`
- prototype: `int(CInstClassFactory *__hidden this, HKEY *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18022b500`

## callees

- `0x180045bd0`
- `0x1800b5d60`
- `0x18022b550`
- `0x18022b7bc`
- `0x1803b1f60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18022b78a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18022b78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022b76b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022b76b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022b6c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022b73e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022b77c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022b6c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022b73e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18022b77c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b648`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b693`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b706`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b606`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b648`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b693`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18022b706`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x18022b5a3`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHStringFromGUIDW` at `0x18022b5a3`

## string_xrefs

- `0x18022b5b9`: `Software\Classes\CLSID\%ls\Instance`

## pseudocode

```c

```
