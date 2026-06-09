# DrvCreateMDEV(_UNICODE_STRING *,_devicemodeW *,void *,ulong,_MDEV *,ulong,int,int,D3DKMT_GETPATHSMODALITY *)

- ea: `0x1401ecafc`
- end: `0x1401ee5a9`
- name: `?DrvCreateMDEV@@YAPEAU_MDEV@@PEAU_UNICODE_STRING@@PEAU_devicemodeW@@PEAXKPEAU1@KHHPEAUD3DKMT_GETPATHSMODALITY@@@Z`
- size: `6829`
- prototype: `struct _MDEV *__fastcall(struct _UNICODE_STRING *, struct _devicemodeW *, void *, unsigned int, struct _MDEV *, unsigned int, int, int, struct D3DKMT_GETPATHSMODALITY *)`
- caller_count: `2`
- callee_count: `55`
- tags: `installer_update`

## callers

- `0x1400b00d0`
- `0x1401eb5a4`

## callees

- `0x140013ff0`
- `0x14001bf04`
- `0x14001c970`
- `0x140027340`
- `0x1400273c4`
- `0x140027418`
- `0x1400276ec`
- `0x140028974`
- `0x14002aa70`
- `0x14003a180`
- `0x140040394`
- `0x1400411c0`
- `0x1400429a0`
- `0x140050c34`
- `0x1400630e0`
- `0x14009202c`
- `0x1400aeff4`
- `0x1400af048`
- `0x1400af450`
- `0x1400af768`
- `0x1400b05d4`
- `0x1400c5f50`
- `0x1400c661c`
- `0x1400c7290`
- `0x140110208`
- `0x1401536c4`
- `0x140160fc0`
- `0x1401611d0`
- `0x140164da8`
- `0x1401695ac`
- `0x14016bff4`
- `0x140174240`
- `0x140175c94`
- `0x140175ce0`
- `0x14017a870`
- `0x14017d974`
- `0x140180070`
- `0x140184e38`
- `0x140186f54`
- `0x1401b2624`
- `0x1401b29c8`
- `0x1401b53d0`
- `0x1401cc0fc`
- `0x1401e66f4`
- `0x1401e9e44`
- `0x1401eb2c4`
- `0x1401ecafc`
- `0x1401eef44`
- `0x1401f0ee4`
- `0x1401f114c`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ee511`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401ee511`
- `watchdog!WdLogSingleEntry3` at `0x1401edf14`
- `watchdog!WdLogSingleEntry3` at `0x1401edf14`
- `watchdog!WdLogSingleEntry4` at `0x1401ecb6f`
- `watchdog!WdLogSingleEntry4` at `0x1401ecb6f`
- `watchdog!WdLogSingleEntry0` at `0x1401eced8`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf31`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf5c`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf83`
- `watchdog!WdLogSingleEntry0` at `0x1401ed1da`
- `watchdog!WdLogSingleEntry0` at `0x1401ed391`
- `watchdog!WdLogSingleEntry0` at `0x1401ed3cd`
- `watchdog!WdLogSingleEntry0` at `0x1401ed94a`
- `watchdog!WdLogSingleEntry0` at `0x1401eda94`
- `watchdog!WdLogSingleEntry0` at `0x1401edb02`
- `watchdog!WdLogSingleEntry0` at `0x1401edb39`
- `watchdog!WdLogSingleEntry0` at `0x1401edb9d`
- `watchdog!WdLogSingleEntry0` at `0x1401edbbd`
- `watchdog!WdLogSingleEntry0` at `0x1401edf6b`
- `watchdog!WdLogSingleEntry0` at `0x1401ee306`
- `watchdog!WdLogSingleEntry0` at `0x1401ee429`
- `watchdog!WdLogSingleEntry0` at `0x1401eced8`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf31`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf5c`
- `watchdog!WdLogSingleEntry0` at `0x1401ecf83`
- `watchdog!WdLogSingleEntry0` at `0x1401ed1da`
- `watchdog!WdLogSingleEntry0` at `0x1401ed391`
- `watchdog!WdLogSingleEntry0` at `0x1401ed3cd`
- `watchdog!WdLogSingleEntry0` at `0x1401ed94a`
- `watchdog!WdLogSingleEntry0` at `0x1401eda94`
- `watchdog!WdLogSingleEntry0` at `0x1401edb02`
- `watchdog!WdLogSingleEntry0` at `0x1401edb39`
- `watchdog!WdLogSingleEntry0` at `0x1401edb9d`
- `watchdog!WdLogSingleEntry0` at `0x1401edbbd`
- `watchdog!WdLogSingleEntry0` at `0x1401edf6b`
- `watchdog!WdLogSingleEntry0` at `0x1401ee306`
- `watchdog!WdLogSingleEntry0` at `0x1401ee429`
- `watchdog!WdLogSingleEntry1` at `0x1401edb79`
- `watchdog!WdLogSingleEntry1` at `0x1401edf8b`
- `watchdog!WdLogSingleEntry1` at `0x1401ee57b`
- `watchdog!WdLogSingleEntry1` at `0x1401edb79`
- `watchdog!WdLogSingleEntry1` at `0x1401edf8b`
- `watchdog!WdLogSingleEntry1` at `0x1401ee57b`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401edeb8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401edeb8`
- `WIN32K!W32GetSessionState` at `0x1401ecb42`
- `WIN32K!W32GetSessionState` at `0x1401ed289`
- `WIN32K!W32GetSessionState` at `0x1401ed8e3`
- `WIN32K!W32GetSessionState` at `0x1401eddda`
- `WIN32K!W32GetSessionState` at `0x1401ecb42`
- `WIN32K!W32GetSessionState` at `0x1401ed289`
- `WIN32K!W32GetSessionState` at `0x1401ed8e3`
- `WIN32K!W32GetSessionState` at `0x1401eddda`
- `WIN32K!W32GetUserSessionState` at `0x1401ed2a7`
- `WIN32K!W32GetUserSessionState` at `0x1401ed2a7`

## pseudocode

```c

```
