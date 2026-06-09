# COInetSession::CreateProtocolInfo(ushort const *,IInternetProtocolInfo * *)

- ea: `0x180018e90`
- end: `0x180019465`
- name: `?CreateProtocolInfo@COInetSession@@AEAAJPEBGPEAPEAUIInternetProtocolInfo@@@Z`
- size: `1493`
- prototype: `__int64 __fastcall(COInetSession *__hidden this, const unsigned __int16 *, struct IInternetProtocolInfo **)`
- caller_count: `5`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014600`
- `0x180018870`
- `0x1800188f0`
- `0x180018d10`
- `0x180018dd0`

## callees

- `0x1800150e0`
- `0x180018e90`
- `0x1800197a0`
- `0x18001e2cc`
- `0x18011ba26`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcschr` at `0x180018f2e`
- `msvcrt!wcschr` at `0x180018f2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019024`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019024`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018f77`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001906f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001906f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800191ef`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800191ef`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001924c`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001924c`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180018f92`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180018f92`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180019445`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180019445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001939e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001939e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800193a7`

## pseudocode

```c

```
