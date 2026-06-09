# FindMediaTypeFormat(ushort const *,ushort *,ulong *)

- ea: `0x180025a18`
- end: `0x180025c29`
- name: `?FindMediaTypeFormat@@YAJPEBGPEAGPEAK@Z`
- size: `529`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026810`

## callees

- `0x180025a18`
- `0x180025c30`
- `0x18002fee0`
- `0x1801285fe`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025bf3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025b2a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180025bf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025a39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b10`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025a39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180025b10`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x180025b85`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICA` at `0x180025b85`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025a76`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025ad5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025a76`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180025ad5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180025a8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025be0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025be0`

## pseudocode

```c

```
