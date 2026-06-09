# CSecurityManager::ProcessUrlActionEx2Internal(IUri *,ulong,uchar *,ulong,uchar *,ulong,ulong,unsigned __int64,ulong *,ulong,ulong *)

- ea: `0x180027dc0`
- end: `0x180028f05`
- name: `?ProcessUrlActionEx2Internal@CSecurityManager@@AEAAJPEAUIUri@@KPEAEK1KK_KPEAKK3@Z`
- size: `4421`
- prototype: `__int64 __usercall@<rax>(CSecurityManager *__hidden this@<rcx>, struct IUri *@<rdx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned __int64, unsigned int *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800792b0`
- `0x180099670`
- `0x180100d40`

## callees

- `0x1800101fc`
- `0x180011ce0`
- `0x1800121e4`
- `0x18001db54`
- `0x18001e160`
- `0x1800215c0`
- `0x180027dc0`
- `0x180029298`
- `0x180029380`
- `0x180029874`
- `0x18002c924`
- `0x18002d6f0`
- `0x180034300`
- `0x18003589c`
- `0x180039f68`
- `0x180047740`
- `0x1800792b0`
- `0x180084f68`
- `0x18009e4f0`
- `0x1800fec78`
- `0x1800fefa4`
- `0x1800ff054`
- `0x1800ff158`
- `0x1800ff78c`
- `0x180101940`
- `0x180101ca8`
- `0x180101e08`
- `0x1801022d0`
- `0x180103310`
- `0x180108164`
- `0x18010eb50`
- `0x18011a57c`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!GetIUriPriv` at `0x180027ea5`
- `iertutil!GetIUriPriv` at `0x180027ea5`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800286ab`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x1800286ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028019`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180028019`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028005`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180028005`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028a44`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028a89`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028a9d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ab1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ac5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ad9`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028a44`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028a89`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028a9d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ab1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ac5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180028ad9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289b8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800289b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028977`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180028977`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800289ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800289ae`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028490`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028c89`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028df7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028e24`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028490`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028c89`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028df7`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180028e24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028efa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028efa`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x180028343`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x180028343`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180028d30`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180028e6e`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180028d30`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180028e6e`

## string_xrefs

- `0x180028a3d`: `ieframe.dll`
- `0x18002894e`: `Software\Microsoft\Internet Explorer\LowRegistry\DontShowMeThisDialogAgain`

## pseudocode

```c

```
