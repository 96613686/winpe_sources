# CMountPoint::GetDriveJunctionCLSID(int,_GUID *)

- ea: `0x1800580b0`
- end: `0x1800584c3`
- name: `?GetDriveJunctionCLSID@CMountPoint@@SAJHPEAU_GUID@@@Z`
- size: `1043`
- prototype: `__int64 __fastcall(int iDrive, struct _GUID *)`
- caller_count: `2`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180057350`
- `0x180057500`

## callees

- `0x1800580b0`
- `0x1800584d0`
- `0x18033bfc0`
- `0x1803b1f60`
- `0x1803b69b9`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058117`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058117`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058200`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058234`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058194`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058200`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058234`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800581ac`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800582b5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800582b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058268`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180058268`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058104`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180058104`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058140`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800581e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058140`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800581e7`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18005842f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18005842f`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800584a1`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800584a1`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x180058415`
- `api-ms-win-shcore-path-l1-1-0!__imp_PathBuildRootW` at `0x180058415`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800583fe`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800583fe`

## string_xrefs

- `0x18005825a`: `Drive\shellex\FolderExtensions`
- `0x1800582d1`: `Drive\shellex\FolderExtensions\`

## pseudocode

```c

```
