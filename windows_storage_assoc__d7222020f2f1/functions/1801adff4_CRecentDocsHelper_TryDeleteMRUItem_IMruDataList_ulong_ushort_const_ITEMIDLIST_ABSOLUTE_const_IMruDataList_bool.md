# CRecentDocsHelper::_TryDeleteMRUItem(IMruDataList *,ulong,ushort const *,_ITEMIDLIST_ABSOLUTE const *,IMruDataList *,bool)

- ea: `0x1801adff4`
- end: `0x1801ae277`
- name: `?_TryDeleteMRUItem@CRecentDocsHelper@@AEAA_NPEAUIMruDataList@@KPEBGPEBU_ITEMIDLIST_ABSOLUTE@@0_N@Z`
- size: `643`
- prototype: `bool __fastcall(CRecentDocsHelper *__hidden this, struct IMruDataList *, unsigned int, const unsigned __int16 *, LPCITEMIDLIST pidl2, struct IMruDataList *, bool)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18033295c`
- `0x180547b30`

## callees

- `0x180063050`
- `0x1800b03d0`
- `0x180133f50`
- `0x180171de0`
- `0x1801720f0`
- `0x1801adff4`
- `0x1801ae280`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x18067d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18067016f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18067016f`
- `ntdll!RtlGetLastNtStatus` at `0x1806700e2`
- `ntdll!RtlGetLastNtStatus` at `0x18067014b`
- `ntdll!RtlGetLastNtStatus` at `0x1806700e2`
- `ntdll!RtlGetLastNtStatus` at `0x18067014b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180670128`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180670128`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180670109`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180670109`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801ae21f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18067013d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801ae21f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18067013d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae1ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae20c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae1ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801ae20c`
- `SHCORE!__imp_IsNotifySuspended` at `0x1801ae233`
- `SHCORE!__imp_IsNotifySuspended` at `0x1801ae233`

## pseudocode

```c

```
