# MemoryManager::DecommitMemory(_VID_PAGE_RANGE *,uint,unsigned __int64 *)

- ea: `0x140206590`
- end: `0x140206851`
- name: `?DecommitMemory@MemoryManager@@UEAAJPEAT_VID_PAGE_RANGE@@IPEA_K@Z`
- size: `705`
- prototype: `__int64 __fastcall(MemoryManager *__hidden this, union _VID_PAGE_RANGE *, unsigned int, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1400dfde8`

## callees

- `0x14002ec00`
- `0x14003ede0`
- `0x140042260`
- `0x14005497c`
- `0x140054a90`
- `0x1400dff90`
- `0x140132960`
- `0x140206590`
- `0x140206860`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140206639`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140206639`
- `vid!VidDmSlpDisable` at `0x140206821`
- `vid!VidDmSlpDisable` at `0x140206821`
- `vid!VidDmBalloon` at `0x140206622`
- `vid!VidDmBalloon` at `0x140206622`

## string_xrefs

- `0x1402066a5`: `hr == ERROR_VID_VTL_ACCESS_DENIED`

## pseudocode

```c

```
