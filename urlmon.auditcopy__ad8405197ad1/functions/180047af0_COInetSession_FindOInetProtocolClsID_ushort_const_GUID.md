# COInetSession::FindOInetProtocolClsID(ushort const *,_GUID *)

- ea: `0x180047af0`
- end: `0x1800480f6`
- name: `?FindOInetProtocolClsID@COInetSession@@QEAAJPEBGPEAU_GUID@@@Z`
- size: `1542`
- prototype: `__int64 __fastcall(COInetSession *this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18009e360`
- `0x1800f8cb0`

## callees

- `0x18001db50`
- `0x180024e2c`
- `0x180047af0`
- `0x180048d2c`
- `0x1800490d0`
- `0x180128660`
- `0x180129010`

## import_xrefs

- `msvcrt!wcschr` at `0x180047c6e`
- `msvcrt!wcschr` at `0x180047c6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047d58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047d58`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047cb3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047cb3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180047b64`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180047d98`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180047b64`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180047d98`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180047f1d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180047f1d`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x180047fd2`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x180047fd2`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180047cd4`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x180047cd4`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800480d0`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x1800480d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004801f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004802e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004801f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004802e`

## pseudocode

```c

```
