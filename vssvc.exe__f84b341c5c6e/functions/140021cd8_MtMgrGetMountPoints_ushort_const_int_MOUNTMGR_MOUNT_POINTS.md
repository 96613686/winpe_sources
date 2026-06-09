# MtMgrGetMountPoints(ushort const *,int,_MOUNTMGR_MOUNT_POINTS * *)

- ea: `0x140021cd8`
- end: `0x140021f0e`
- name: `?MtMgrGetMountPoints@@YAHPEBGHPEAPEAU_MOUNTMGR_MOUNT_POINTS@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(const unsigned __int16 *, int, struct _MOUNTMGR_MOUNT_POINTS **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x1400212d4`

## callees

- `0x140021cd8`
- `0x1400222d0`
- `0x1400227a0`
- `0x1400228bc`
- `0x14003b0c0`
- `0x1400d257c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140021ef3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140021ef3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021dfb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021e15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140021e7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021ebd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140021ebd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021eaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021eaa`

## string_xrefs

- `0x140021d0d`: `MtMgrGetMountPoints`
- `0x140021ed9`: `MtMgrGetMountPoints`
- `0x140021da1`: `ppMountPointsOut`

## pseudocode

```c

```
