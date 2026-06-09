# WdcDataMonitor::ListUpdateRow(HWND__ *,WdcColumnList *,ulong,_WDC_DATA_INFO *,ushort *,ushort *,unsigned __int64)

- ea: `0x18000b000`
- end: `0x18000b2cc`
- name: `?ListUpdateRow@WdcDataMonitor@@QEAAJPEAUHWND__@@PEAVWdcColumnList@@KPEAU_WDC_DATA_INFO@@PEAG3_K@Z`
- size: `716`
- prototype: `__int64 __fastcall(WdcDataMonitor *__hidden this, HWND, struct WdcColumnList *, unsigned int, struct _WDC_DATA_INFO *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1800096f0`

## callees

- `0x18000b000`
- `0x18000b2e0`
- `0x18000b854`
- `0x18003b0ac`
- `0x180086010`

## import_xrefs

- `USER32!SendMessageW` at `0x18000b154`
- `USER32!SendMessageW` at `0x18000b1bd`
- `USER32!SendMessageW` at `0x18000b231`
- `USER32!SendMessageW` at `0x18000b154`
- `USER32!SendMessageW` at `0x18000b1bd`
- `USER32!SendMessageW` at `0x18000b231`

## string_xrefs

- `0x18000b2b4`: `WdcDataMonitor::ListUpdateRow`

## pseudocode

```c

```
