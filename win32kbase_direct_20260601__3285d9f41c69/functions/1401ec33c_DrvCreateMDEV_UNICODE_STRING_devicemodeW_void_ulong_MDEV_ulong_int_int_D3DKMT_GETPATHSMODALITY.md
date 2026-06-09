# DrvCreateMDEV(_UNICODE_STRING *,_devicemodeW *,void *,ulong,_MDEV *,ulong,int,int,D3DKMT_GETPATHSMODALITY *)

- ea: `0x1401ec33c`
- end: `0x1401edde9`
- name: `?DrvCreateMDEV@@YAPEAU_MDEV@@PEAU_UNICODE_STRING@@PEAU_devicemodeW@@PEAXKPEAU1@KHHPEAUD3DKMT_GETPATHSMODALITY@@@Z`
- size: `6829`
- prototype: `struct _MDEV *__fastcall(struct _UNICODE_STRING *, struct _devicemodeW *, void *, unsigned int, struct _MDEV *, unsigned int, int, int, struct D3DKMT_GETPATHSMODALITY *)`
- caller_count: `2`
- callee_count: `55`
- tags: `installer_update`

## callers

- `0x1400657c0`
- `0x1401eade4`

## callees

- `0x14000dc4c`
- `0x14001d160`
- `0x140024f24`
- `0x140025990`
- `0x1400305c0`
- `0x140030644`
- `0x140030698`
- `0x14003096c`
- `0x140031bf4`
- `0x140033cf0`
- `0x140041ac0`
- `0x1400492a4`
- `0x14004a0d0`
- `0x14004b8b0`
- `0x1400599f4`
- `0x140063ae4`
- `0x140063b38`
- `0x140063f40`
- `0x140064258`
- `0x140065cc4`
- `0x1400ab680`
- `0x1400abd4c`
- `0x1400ac9c0`
- `0x140106d98`
- `0x14010bd30`
- `0x140153fe4`
- `0x140161860`
- `0x140161a70`
- `0x140165648`
- `0x140169dac`
- `0x14016c794`
- `0x140174fa0`
- `0x1401769f4`
- `0x140176a40`
- `0x14017b3d0`
- `0x14017e3e4`
- `0x140180a20`
- `0x140185f98`
- `0x1401880b4`
- `0x1401b20c4`
- `0x1401b2468`
- `0x1401b4e70`
- `0x1401cbb9c`
- `0x1401e5fd4`
- `0x1401e9684`
- `0x1401eab04`
- `0x1401ec33c`
- `0x1401ee784`
- `0x1401f0724`
- `0x1401f098c`

## import_xrefs

- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401edd51`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x1401edd51`
- `watchdog!WdLogSingleEntry3` at `0x1401ed754`
- `watchdog!WdLogSingleEntry3` at `0x1401ed754`
- `watchdog!WdLogSingleEntry4` at `0x1401ec3af`
- `watchdog!WdLogSingleEntry4` at `0x1401ec3af`
- `watchdog!WdLogSingleEntry0` at `0x1401ec718`
- `watchdog!WdLogSingleEntry0` at `0x1401ec771`
- `watchdog!WdLogSingleEntry0` at `0x1401ec79c`
- `watchdog!WdLogSingleEntry0` at `0x1401ec7c3`
- `watchdog!WdLogSingleEntry0` at `0x1401eca1a`
- `watchdog!WdLogSingleEntry0` at `0x1401ecbd1`
- `watchdog!WdLogSingleEntry0` at `0x1401ecc0d`
- `watchdog!WdLogSingleEntry0` at `0x1401ed18a`
- `watchdog!WdLogSingleEntry0` at `0x1401ed2d4`
- `watchdog!WdLogSingleEntry0` at `0x1401ed342`
- `watchdog!WdLogSingleEntry0` at `0x1401ed379`
- `watchdog!WdLogSingleEntry0` at `0x1401ed3dd`
- `watchdog!WdLogSingleEntry0` at `0x1401ed3fd`
- `watchdog!WdLogSingleEntry0` at `0x1401ed7ab`
- `watchdog!WdLogSingleEntry0` at `0x1401edb46`
- `watchdog!WdLogSingleEntry0` at `0x1401edc69`
- `watchdog!WdLogSingleEntry0` at `0x1401ec718`
- `watchdog!WdLogSingleEntry0` at `0x1401ec771`
- `watchdog!WdLogSingleEntry0` at `0x1401ec79c`
- `watchdog!WdLogSingleEntry0` at `0x1401ec7c3`
- `watchdog!WdLogSingleEntry0` at `0x1401eca1a`
- `watchdog!WdLogSingleEntry0` at `0x1401ecbd1`
- `watchdog!WdLogSingleEntry0` at `0x1401ecc0d`
- `watchdog!WdLogSingleEntry0` at `0x1401ed18a`
- `watchdog!WdLogSingleEntry0` at `0x1401ed2d4`
- `watchdog!WdLogSingleEntry0` at `0x1401ed342`
- `watchdog!WdLogSingleEntry0` at `0x1401ed379`
- `watchdog!WdLogSingleEntry0` at `0x1401ed3dd`
- `watchdog!WdLogSingleEntry0` at `0x1401ed3fd`
- `watchdog!WdLogSingleEntry0` at `0x1401ed7ab`
- `watchdog!WdLogSingleEntry0` at `0x1401edb46`
- `watchdog!WdLogSingleEntry0` at `0x1401edc69`
- `watchdog!WdLogSingleEntry1` at `0x1401ed3b9`
- `watchdog!WdLogSingleEntry1` at `0x1401ed7cb`
- `watchdog!WdLogSingleEntry1` at `0x1401eddbb`
- `watchdog!WdLogSingleEntry1` at `0x1401ed3b9`
- `watchdog!WdLogSingleEntry1` at `0x1401ed7cb`
- `watchdog!WdLogSingleEntry1` at `0x1401eddbb`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401ed6f8`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401ed6f8`
- `WIN32K!W32GetSessionState` at `0x1401ec382`
- `WIN32K!W32GetSessionState` at `0x1401ecac9`
- `WIN32K!W32GetSessionState` at `0x1401ed123`
- `WIN32K!W32GetSessionState` at `0x1401ed61a`
- `WIN32K!W32GetSessionState` at `0x1401ec382`
- `WIN32K!W32GetSessionState` at `0x1401ecac9`
- `WIN32K!W32GetSessionState` at `0x1401ed123`
- `WIN32K!W32GetSessionState` at `0x1401ed61a`
- `WIN32K!W32GetUserSessionState` at `0x1401ecae7`
- `WIN32K!W32GetUserSessionState` at `0x1401ecae7`

## pseudocode

```c

```
