# COInetSession::FindOInetProtocolClsID(ushort const *,_GUID *)

- ea: `0x180019f10`
- end: `0x18001a4c8`
- name: `?FindOInetProtocolClsID@COInetSession@@QEAAJPEBGPEAU_GUID@@@Z`
- size: `1464`
- prototype: `__int64 __fastcall(COInetSession *this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180097b00`
- `0x1800eeb60`

## callees

- `0x1800150e0`
- `0x1800197a0`
- `0x180019f10`
- `0x18001abe8`
- `0x18001e2cc`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `msvcrt!wcschr` at `0x18001a07e`
- `msvcrt!wcschr` at `0x18001a07e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a156`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a156`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a0bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a0bd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180019f84`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001a18f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x180019f84`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICW` at `0x18001a18f`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001a30d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18001a30d`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001a3bc`
- `api-ms-win-core-atoms-l1-1-0!AddAtomW` at `0x18001a3bc`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001a0d8`
- `api-ms-win-core-atoms-l1-1-0!FindAtomW` at `0x18001a0d8`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001a4a8`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18001a4a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a403`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a40c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a403`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a40c`

## pseudocode

```c

```
