# COInetSession::CreateFirstProtocol(ushort const *,IUnknown *,IUnknown * *,IInternetProtocol * *,_GUID *,ulong *,ulong)

- ea: `0x180048100`
- end: `0x18004884d`
- name: `?CreateFirstProtocol@COInetSession@@QEAAJPEBGPEAUIUnknown@@PEAPEAU2@PEAPEAUIInternetProtocol@@PEAU_GUID@@PEAKK@Z`
- size: `1869`
- prototype: `__int64 __fastcall(COInetSession *this, wchar_t *, struct IUnknown *, struct IUnknown **, struct IInternetProtocol **, IID *rclsid, unsigned int *, unsigned int)`
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180029e70`
- `0x18002bc70`
- `0x180080c50`
- `0x18009e670`
- `0x18009ebd0`
- `0x1800f8f60`

## callees

- `0x18001db50`
- `0x180024e2c`
- `0x180048100`
- `0x180048854`
- `0x180048d2c`
- `0x1800490d0`
- `0x18006f330`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x1800481d6`
- `msvcrt!wcschr` at `0x1800481d6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048282`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180048282`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004862e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004862e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800482cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x1800482cf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800484be`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800484be`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18004857f`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18004857f`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180048656`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180048656`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18004876c`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18004881d`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18004876c`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18004881d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800485d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800485e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800485d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800485e8`

## pseudocode

```c

```
