# CSecurityManager::ProcessUrlActionEx2Internal(IUri *,ulong,uchar *,ulong,uchar *,ulong,ulong,unsigned __int64,ulong *,ulong,ulong *)

- ea: `0x180059eb0`
- end: `0x18005aedc`
- name: `?ProcessUrlActionEx2Internal@CSecurityManager@@AEAAJPEAUIUri@@KPEAEK1KK_KPEAKK3@Z`
- size: `4140`
- prototype: `__int64 __fastcall(CSecurityManager *this, struct IUri *, unsigned int, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int, unsigned __int64, unsigned int *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007f0f0`
- `0x18009ff50`
- `0x18010bde0`

## callees

- `0x1800124b0`
- `0x18001563c`
- `0x180015b60`
- `0x180015f80`
- `0x18001a4ac`
- `0x180028510`
- `0x180032374`
- `0x180032b1c`
- `0x180033980`
- `0x18003bf28`
- `0x180059eb0`
- `0x18005b29c`
- `0x18005b348`
- `0x18005b530`
- `0x18005ba44`
- `0x18005bc6c`
- `0x18007f0f0`
- `0x1800a5238`
- `0x180109bdc`
- `0x180109f24`
- `0x180109fd8`
- `0x18010a0e8`
- `0x18010a728`
- `0x18010ca10`
- `0x18010cdb4`
- `0x18010cf28`
- `0x18010d480`
- `0x18010e5d0`
- `0x18011370c`
- `0x18011a8c4`
- `0x180127054`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `iertutil!GetIUriPriv` at `0x180059f9d`
- `iertutil!GetIUriPriv` at `0x180059f9d`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18005a780`
- `iertutil!__imp_?IsProtectedModeProcess@@YAJXZ` at `0x18005a780`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a125`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005a125`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a10b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005a10b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005aab2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005aab2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005aa65`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005aa65`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005aaa1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005aaa1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005a59e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ac37`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005adaf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ade1`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005a59e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ac37`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005adaf`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005ade1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aecb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005aecb`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18005a445`
- `api-ms-win-core-url-l1-1-0!ParseURLW` at `0x18005a445`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005ace5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005ae2f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005ace5`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18005ae2f`

## string_xrefs

- `0x18005aa3b`: `Software\Microsoft\Internet Explorer\LowRegistry\DontShowMeThisDialogAgain`

## pseudocode

```c

```
