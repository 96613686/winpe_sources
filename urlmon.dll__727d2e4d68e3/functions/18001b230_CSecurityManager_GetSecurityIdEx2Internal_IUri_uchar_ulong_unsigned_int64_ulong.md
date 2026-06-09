# CSecurityManager::GetSecurityIdEx2Internal(IUri *,uchar *,ulong *,unsigned __int64,ulong)

- ea: `0x18001b230`
- end: `0x18001bb8d`
- name: `?GetSecurityIdEx2Internal@CSecurityManager@@AEAAJPEAUIUri@@PEAEPEAK_KK@Z`
- size: `2397`
- prototype: `__int64 __fastcall(const WCHAR *this, struct IUri *, unsigned __int8 *, unsigned int *, const WCHAR *, unsigned int)`
- caller_count: `2`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ad70`
- `0x180040a60`

## callees

- `0x180013b8c`
- `0x180013dd0`
- `0x180016d20`
- `0x18001a4ac`
- `0x18001ad30`
- `0x18001b230`
- `0x18001c070`
- `0x18001cb00`
- `0x180028510`
- `0x18003e540`
- `0x180042ba0`
- `0x180077dc0`
- `0x18007f924`
- `0x180080488`
- `0x1800a03ec`
- `0x1801285fe`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18001b666`
- `msvcrt!memcpy_s` at `0x18001b666`
- `iertutil!GetIUriPriv` at `0x18001b2d7`
- `iertutil!GetIUriPriv` at `0x18001b2d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b98a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b696`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b6ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b98a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b9e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b32d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8c2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b32d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b8c2`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001bb56`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001bb56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bb72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001bb72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ba09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ba09`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b9a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b9b0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b9a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b9b0`

## pseudocode

```c

```
