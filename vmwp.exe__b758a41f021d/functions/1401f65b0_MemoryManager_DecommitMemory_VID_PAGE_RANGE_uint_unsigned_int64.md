# MemoryManager::DecommitMemory(_VID_PAGE_RANGE *,uint,unsigned __int64 *)

- ea: `0x1401f65b0`
- end: `0x1401f6871`
- name: `?DecommitMemory@MemoryManager@@UEAAJPEAT_VID_PAGE_RANGE@@IPEA_K@Z`
- size: `705`
- prototype: `__int64 __fastcall(MemoryManager *__hidden this, union _VID_PAGE_RANGE *, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400cfe98`

## callees

- `0x140033020`
- `0x1400364a0`
- `0x14003b630`
- `0x1400544a8`
- `0x1400545bc`
- `0x1400d0060`
- `0x14011ea40`
- `0x1401f65b0`
- `0x1401f6880`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401f6659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1401f6659`
- `vid!VidDmSlpDisable` at `0x1401f6841`
- `vid!VidDmSlpDisable` at `0x1401f6841`
- `vid!VidDmBalloon` at `0x1401f6642`
- `vid!VidDmBalloon` at `0x1401f6642`

## string_xrefs

- `0x1401f66c5`: `hr == ERROR_VID_VTL_ACCESS_DENIED`

## pseudocode

```c

```
