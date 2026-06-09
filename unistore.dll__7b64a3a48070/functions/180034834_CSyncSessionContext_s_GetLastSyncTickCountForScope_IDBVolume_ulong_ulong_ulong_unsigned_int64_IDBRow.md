# CSyncSessionContext::s_GetLastSyncTickCountForScope(IDBVolume *,ulong,ulong,ulong,unsigned __int64 *,IDBRow * *)

- ea: `0x180034834`
- end: `0x1800349b5`
- name: `?s_GetLastSyncTickCountForScope@CSyncSessionContext@@CAJPEAVIDBVolume@@KKKPEA_KPEAPEAVIDBRow@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(struct IDBVolume *, unsigned int, unsigned int, unsigned int, unsigned __int64 *, struct IDBRow **)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180039aa8`
- `0x18003c958`

## callees

- `0x180004440`
- `0x1800068f0`
- `0x180034834`
- `0x180035254`
- `0x1800bcd70`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034947`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034994`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034913`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034947`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034994`

## string_xrefs

- `0x1800348ab`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncsessioncontext.cpp`
- `0x1800348e5`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncsessioncontext.cpp`
- `0x180034975`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\syncsessioncontext.cpp`

## pseudocode

```c

```
