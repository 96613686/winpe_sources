# DrvChangeDisplaySettingsInternal(tagGRAPHICS_DEVICE *,_devicemodeW *,D3DKMT_GETPATHSMODALITY *,void *,_MDEV *,_MDEV * *,ulong,_CDS_INTERNAL_FLAGS,uchar *)

- ea: `0x1401eb644`
- end: `0x1401eca9d`
- name: `?DrvChangeDisplaySettingsInternal@@YAJPEAUtagGRAPHICS_DEVICE@@PEAU_devicemodeW@@PEAUD3DKMT_GETPATHSMODALITY@@PEAXPEAU_MDEV@@PEAPEAU4@KU_CDS_INTERNAL_FLAGS@@PEAE@Z`
- size: `5209`
- prototype: `__int64 __fastcall(WCHAR *, struct _devicemodeW *, struct D3DKMT_GETPATHSMODALITY *, void *, struct _MDEV *, struct _MDEV **, unsigned int, unsigned int, bool *)`
- caller_count: `3`
- callee_count: `66`
- tags: `registry_config`

## callers

- `0x1401c0540`
- `0x1401ea13c`
- `0x1401eb4c8`

## callees

- `0x140016780`
- `0x140017cd4`
- `0x140017d40`
- `0x140017d94`
- `0x140017de8`
- `0x140017e64`
- `0x140017ea8`
- `0x140017f6c`
- `0x140018124`
- `0x1400182b4`
- `0x140018da8`
- `0x1400190e8`
- `0x140019744`
- `0x140019dd4`
- `0x140019e28`
- `0x14001a0fc`
- `0x14001ccc0`
- `0x14001cf4c`
- `0x140031784`
- `0x140031da0`
- `0x14003214c`
- `0x140035ecc`
- `0x14006f0dc`
- `0x14007065c`
- `0x14007b930`
- `0x14008b1e4`
- `0x1400c63c0`
- `0x1400d565c`
- `0x1400e3144`
- `0x1400f64f8`
- `0x140101740`
- `0x14015355c`
- `0x140163e30`
- `0x140163f74`
- `0x140164670`
- `0x140168660`
- `0x140174e9c`
- `0x140179b44`
- `0x14017ae9c`
- `0x14017b008`
- `0x14017b450`
- `0x140180388`
- `0x140180a68`
- `0x14018364c`
- `0x140183ac0`
- `0x140186b54`
- `0x140187250`
- `0x140188900`
- `0x140192c18`
- `0x1401af1d8`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcess` at `0x1401eb8c8`
- `ntoskrnl!PsGetCurrentProcess` at `0x1401eb8c8`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401eb7eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401eb7eb`
- `watchdog!WdLogSingleEntry0` at `0x1401eb75f`
- `watchdog!WdLogSingleEntry0` at `0x1401eb781`
- `watchdog!WdLogSingleEntry0` at `0x1401eb860`
- `watchdog!WdLogSingleEntry0` at `0x1401eb9d1`
- `watchdog!WdLogSingleEntry0` at `0x1401eba67`
- `watchdog!WdLogSingleEntry0` at `0x1401ec850`
- `watchdog!WdLogSingleEntry0` at `0x1401eb75f`
- `watchdog!WdLogSingleEntry0` at `0x1401eb781`
- `watchdog!WdLogSingleEntry0` at `0x1401eb860`
- `watchdog!WdLogSingleEntry0` at `0x1401eb9d1`
- `watchdog!WdLogSingleEntry0` at `0x1401eba67`
- `watchdog!WdLogSingleEntry0` at `0x1401ec850`
- `watchdog!WdLogSingleEntry5` at `0x1401eb738`
- `watchdog!WdLogSingleEntry5` at `0x1401eb8ec`
- `watchdog!WdLogSingleEntry5` at `0x1401eb738`
- `watchdog!WdLogSingleEntry5` at `0x1401eb8ec`
- `watchdog!WdLogSingleEntry1` at `0x1401eca32`
- `watchdog!WdLogSingleEntry1` at `0x1401eca32`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ebf65`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ebf8f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec19a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec1c4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec3cc`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec3f6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec4d3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec4fd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec6cc`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ebf65`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ebf8f`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec19a`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec1c4`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec3cc`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec3f6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec4d3`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec4fd`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401ec6cc`
- `WIN32K!W32GetSessionState` at `0x1401eb6c7`
- `WIN32K!W32GetSessionState` at `0x1401ec76a`
- `WIN32K!W32GetSessionState` at `0x1401eb6c7`
- `WIN32K!W32GetSessionState` at `0x1401ec76a`

## pseudocode

```c

```
