# CMountPoint::GetDriveJunctionCLSID(int,_GUID *)

- ea: `0x18012f610`
- end: `0x18012f9c7`
- name: `?GetDriveJunctionCLSID@CMountPoint@@SAJHPEAU_GUID@@@Z`
- size: `951`
- prototype: `__int64 __fastcall(int iDrive, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012e900`
- `0x18012eaa0`

## callees

- `0x18012f610`
- `0x18012f9d0`
- `0x1803295a0`
- `0x1803a4cb0`
- `0x1803a96d9`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012f671`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012f671`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f6e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f73c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f769`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f6e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f73c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012f769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f6f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18012f6f4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012f7de`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18012f7de`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f797`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18012f797`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18012f664`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18012f664`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012f694`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012f729`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012f694`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18012f729`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18012f93f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18012f93f`
- `SHCORE!__imp_GUIDFromStringW` at `0x18012f9ab`
- `SHCORE!__imp_GUIDFromStringW` at `0x18012f9ab`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x18012f92f`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x18012f92f`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18012f91e`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x18012f91e`

## string_xrefs

- `0x18012f789`: `Drive\shellex\FolderExtensions`
- `0x18012f7f4`: `Drive\shellex\FolderExtensions\`

## pseudocode

```c

```
