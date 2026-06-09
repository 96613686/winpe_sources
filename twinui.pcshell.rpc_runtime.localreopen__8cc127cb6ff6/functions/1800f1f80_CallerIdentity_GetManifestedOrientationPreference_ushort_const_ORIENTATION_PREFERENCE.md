# CallerIdentity::GetManifestedOrientationPreference(ushort const *,ORIENTATION_PREFERENCE *)

- ea: `0x1800f1f80`
- end: `0x1800f211d`
- name: `?GetManifestedOrientationPreference@CallerIdentity@@YAJPEBGPEAW4ORIENTATION_PREFERENCE@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, const unsigned __int16 *, enum ORIENTATION_PREFERENCE *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f2d00`
- `0x1806aadf0`

## callees

- `0x180028b40`
- `0x1800290dc`
- `0x1800f1f80`
- `0x1800f2670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f208b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800f208b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f20d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f20d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f202a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f202a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f2057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f2079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f2057`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f2079`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800f1fd0`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x1800f1fd0`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800f2061`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x1800f2061`

## pseudocode

```c

```
