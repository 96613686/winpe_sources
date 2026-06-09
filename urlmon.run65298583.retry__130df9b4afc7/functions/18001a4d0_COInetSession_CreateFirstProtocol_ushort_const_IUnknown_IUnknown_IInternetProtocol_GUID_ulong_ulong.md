# COInetSession::CreateFirstProtocol(ushort const *,IUnknown *,IUnknown * *,IInternetProtocol * *,_GUID *,ulong *,ulong)

- ea: `0x18001a4d0`
- end: `0x18001abdf`
- name: `?CreateFirstProtocol@COInetSession@@QEAAJPEBGPEAUIUnknown@@PEAPEAU2@PEAPEAUIInternetProtocol@@PEAU_GUID@@PEAKK@Z`
- size: `1807`
- prototype: `__int64 __fastcall(COInetSession *__hidden this, const unsigned __int16 *, struct IUnknown *, struct IUnknown **, struct IInternetProtocol **, IID *rclsid, unsigned int *, unsigned int)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180022f50`
- `0x180024bd0`
- `0x18007af20`
- `0x180097e00`
- `0x180098360`
- `0x1800eee00`

## callees

- `0x1800150e0`
- `0x1800151d0`
- `0x1800197a0`
- `0x18001a4d0`
- `0x18001abe8`
- `0x18001e2cc`
- `0x18006a578`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcschr` at `0x18001a5a6`
- `msvcrt!wcschr` at `0x18001a5a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a64b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a64b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a9d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a9d6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001a698`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001a698`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001a87e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001a87e`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001a939`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001a939`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001a9f8`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001a9f8`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001ab0a`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001abb5`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001ab0a`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001abb5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a98d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a98d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a996`

## pseudocode

```c

```
