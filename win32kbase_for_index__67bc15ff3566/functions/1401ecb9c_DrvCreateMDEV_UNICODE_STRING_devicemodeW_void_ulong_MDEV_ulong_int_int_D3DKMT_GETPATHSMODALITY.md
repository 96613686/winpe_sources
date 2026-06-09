# DrvCreateMDEV(_UNICODE_STRING *,_devicemodeW *,void *,ulong,_MDEV *,ulong,int,int,D3DKMT_GETPATHSMODALITY *)

- ea: `0x1401ecb9c`
- end: `0x1401ee649`
- name: `?DrvCreateMDEV@@YAPEAU_MDEV@@PEAU_UNICODE_STRING@@PEAU_devicemodeW@@PEAXKPEAU1@KHHPEAUD3DKMT_GETPATHSMODALITY@@@Z`
- size: `6829`
- prototype: `struct _MDEV *__fastcall(struct _UNICODE_STRING *, struct _devicemodeW *, void *, unsigned int, struct _MDEV *, unsigned int, int, int, struct D3DKMT_GETPATHSMODALITY *)`
- caller_count: `2`
- callee_count: `55`
- tags: `installer_update`

## callers

- `0x140018870`
- `0x1401eb644`

## callees

- `0x14000d76c`
- `0x140017d94`
- `0x140017de8`
- `0x140018124`
- `0x140018308`
- `0x140018d74`
- `0x140019410`
- `0x140019d50`
- `0x140019dd4`
- `0x140019e28`
- `0x14001a0fc`
- `0x140031784`
- `0x140031fa0`
- `0x140032300`
- `0x1400371c0`
- `0x14003b6a0`
- `0x14006e970`
- `0x14007ab04`
- `0x14007b930`
- `0x14007d110`
- `0x14008b1e4`
- `0x1400c63c0`
- `0x1400d4f90`
- `0x1400d565c`
- `0x1400d62d0`
- `0x140112ba8`
- `0x140163e30`
- `0x140164040`
- `0x140167bd8`
- `0x14016c4d4`
- `0x14016e6b4`
- `0x140176bc0`
- `0x140178694`
- `0x1401786e0`
- `0x14017d370`
- `0x1401800e4`
- `0x1401825a0`
- `0x140187e08`
- `0x140189a34`
- `0x1401b32d4`
- `0x1401b3678`
- `0x1401b5ff0`
- `0x1401cc914`
- `0x1401e6834`
- `0x1401e9ee4`
- `0x1401eb364`
- `0x1401ecb9c`
- `0x1401eefe4`
- `0x1401f0f84`
- `0x1401f11ec`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ee5b1`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ee5b1`
- `watchdog!WdLogSingleEntry3` at `0x1401edfb4`
- `watchdog!WdLogSingleEntry3` at `0x1401edfb4`
- `watchdog!WdLogSingleEntry4` at `0x1401ecc0f`
- `watchdog!WdLogSingleEntry4` at `0x1401ecc0f`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf78`
- `watchdog!WdLogSingleEntry0` at `0x1401ecfd1`
- `watchdog!WdLogSingleEntry0` at `0x1401ecffc`
- `watchdog!WdLogSingleEntry0` at `0x1401ed023`
- `watchdog!WdLogSingleEntry0` at `0x1401ed27a`
- `watchdog!WdLogSingleEntry0` at `0x1401ed431`
- `watchdog!WdLogSingleEntry0` at `0x1401ed46d`
- `watchdog!WdLogSingleEntry0` at `0x1401ed9ea`
- `watchdog!WdLogSingleEntry0` at `0x1401edb34`
- `watchdog!WdLogSingleEntry0` at `0x1401edba2`
- `watchdog!WdLogSingleEntry0` at `0x1401edbd9`
- `watchdog!WdLogSingleEntry0` at `0x1401edc3d`
- `watchdog!WdLogSingleEntry0` at `0x1401edc5d`
- `watchdog!WdLogSingleEntry0` at `0x1401ee00b`
- `watchdog!WdLogSingleEntry0` at `0x1401ee3a6`
- `watchdog!WdLogSingleEntry0` at `0x1401ee4c9`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf78`
- `watchdog!WdLogSingleEntry0` at `0x1401ecfd1`
- `watchdog!WdLogSingleEntry0` at `0x1401ecffc`
- `watchdog!WdLogSingleEntry0` at `0x1401ed023`
- `watchdog!WdLogSingleEntry0` at `0x1401ed27a`
- `watchdog!WdLogSingleEntry0` at `0x1401ed431`
- `watchdog!WdLogSingleEntry0` at `0x1401ed46d`
- `watchdog!WdLogSingleEntry0` at `0x1401ed9ea`
- `watchdog!WdLogSingleEntry0` at `0x1401edb34`
- `watchdog!WdLogSingleEntry0` at `0x1401edba2`
- `watchdog!WdLogSingleEntry0` at `0x1401edbd9`
- `watchdog!WdLogSingleEntry0` at `0x1401edc3d`
- `watchdog!WdLogSingleEntry0` at `0x1401edc5d`
- `watchdog!WdLogSingleEntry0` at `0x1401ee00b`
- `watchdog!WdLogSingleEntry0` at `0x1401ee3a6`
- `watchdog!WdLogSingleEntry0` at `0x1401ee4c9`
- `watchdog!WdLogSingleEntry1` at `0x1401edc19`
- `watchdog!WdLogSingleEntry1` at `0x1401ee02b`
- `watchdog!WdLogSingleEntry1` at `0x1401ee61b`
- `watchdog!WdLogSingleEntry1` at `0x1401edc19`
- `watchdog!WdLogSingleEntry1` at `0x1401ee02b`
- `watchdog!WdLogSingleEntry1` at `0x1401ee61b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401edf58`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401edf58`
- `WIN32K!W32GetSessionState` at `0x1401ecbe2`
- `WIN32K!W32GetSessionState` at `0x1401ed329`
- `WIN32K!W32GetSessionState` at `0x1401ed983`
- `WIN32K!W32GetSessionState` at `0x1401ede7a`
- `WIN32K!W32GetSessionState` at `0x1401ecbe2`
- `WIN32K!W32GetSessionState` at `0x1401ed329`
- `WIN32K!W32GetSessionState` at `0x1401ed983`
- `WIN32K!W32GetSessionState` at `0x1401ede7a`
- `WIN32K!W32GetUserSessionState` at `0x1401ed347`
- `WIN32K!W32GetUserSessionState` at `0x1401ed347`

## pseudocode

```c

```
