# CSecurityManager::GetSecurityIdEx2Internal(IUri *,uchar *,ulong *,unsigned __int64,ulong)

- ea: `0x180012e20`
- end: `0x180013726`
- name: `?GetSecurityIdEx2Internal@CSecurityManager@@AEAAJPEAUIUri@@PEAEPEAK_KK@Z`
- size: `2310`
- prototype: `int(CSecurityManager *__hidden this, struct IUri *, unsigned __int8 *, unsigned int *, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800129a0`
- `0x180036b90`

## callees

- `0x18000d3fc`
- `0x18000d870`
- `0x18000e618`
- `0x1800121e4`
- `0x180012960`
- `0x180012e20`
- `0x180013be0`
- `0x180014600`
- `0x1800215c0`
- `0x180038ca0`
- `0x180045720`
- `0x180073020`
- `0x18007a044`
- `0x18007a624`
- `0x180099afc`
- `0x18011ba3e`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180013246`
- `msvcrt!memcpy_s` at `0x180013246`
- `iertutil!GetIUriPriv` at `0x180012ec7`
- `iertutil!GetIUriPriv` at `0x180012ec7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001328e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013551`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001359b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001328e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013551`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001359b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001348f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012f17`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001348f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800136fb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800136fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800135b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800135b8`
- `OLEAUT32!__imp_SysFreeString` at `0x180013561`
- `OLEAUT32!__imp_SysFreeString` at `0x18001356b`
- `OLEAUT32!__imp_SysFreeString` at `0x180013561`
- `OLEAUT32!__imp_SysFreeString` at `0x18001356b`

## pseudocode

```c

```
