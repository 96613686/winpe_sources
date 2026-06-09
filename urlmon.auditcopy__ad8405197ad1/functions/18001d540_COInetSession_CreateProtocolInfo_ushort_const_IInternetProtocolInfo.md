# COInetSession::CreateProtocolInfo(ushort const *,IInternetProtocolInfo * *)

- ea: `0x18001d540`
- end: `0x18001db47`
- name: `?CreateProtocolInfo@COInetSession@@AEAAJPEBGPEAPEAUIInternetProtocolInfo@@@Z`
- size: `1543`
- prototype: `__int64 __fastcall(COInetSession *this, wchar_t *, struct IInternetProtocolInfo **)`
- caller_count: `6`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001cb00`
- `0x180020fd0`
- `0x18006d2d0`
- `0x180077a40`
- `0x18007a410`
- `0x18007da40`

## callees

- `0x18001d540`
- `0x18001db50`
- `0x180024e2c`
- `0x1800490d0`
- `0x1801285e6`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x18001d5de`
- `msvcrt!wcschr` at `0x18001d5de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d6e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d6e4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d62e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001d62e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001d731`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001d731`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001d8b0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001d8b0`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001d913`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001d913`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001d64f`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001d64f`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001db21`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001db21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001da7d`

## pseudocode

```c

```
