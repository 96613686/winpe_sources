# DrvProcessWin32kEscape(_D3DKMT_ESCAPE *)

- ea: `0x1401618e8`
- end: `0x140161eeb`
- name: `?DrvProcessWin32kEscape@@YAJPEAU_D3DKMT_ESCAPE@@@Z`
- size: `1539`
- prototype: `__int64 __fastcall(struct _D3DKMT_ESCAPE *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1401618d0`

## callees

- `0x140012c80`
- `0x14002a0e4`
- `0x14002ce98`
- `0x140040394`
- `0x1400411c0`
- `0x140076ef0`
- `0x140076f80`
- `0x140091954`
- `0x140091e04`
- `0x1400c52e8`
- `0x1401618e8`
- `0x1401c6588`
- `0x1401cc1f0`
- `0x1401defb0`
- `0x1401e68c8`
- `0x1401f8c60`
- `0x140238bf0`
- `0x1402bd054`

## import_xrefs

- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140161d29`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140161d52`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140161d29`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140161d52`
- `ntoskrnl!RtlInitUnicodeString` at `0x140161cf6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140161d0e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140161cf6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140161d0e`
- `watchdog!WdLogSingleEntry0` at `0x140161973`
- `watchdog!WdLogSingleEntry0` at `0x140161ea8`
- `watchdog!WdLogSingleEntry0` at `0x140161973`
- `watchdog!WdLogSingleEntry0` at `0x140161ea8`
- `watchdog!WdLogSingleEntry1` at `0x14016193d`
- `watchdog!WdLogSingleEntry1` at `0x140161baa`
- `watchdog!WdLogSingleEntry1` at `0x140161c02`
- `watchdog!WdLogSingleEntry1` at `0x140161d7b`
- `watchdog!WdLogSingleEntry1` at `0x140161de4`
- `watchdog!WdLogSingleEntry1` at `0x14016193d`
- `watchdog!WdLogSingleEntry1` at `0x140161baa`
- `watchdog!WdLogSingleEntry1` at `0x140161c02`
- `watchdog!WdLogSingleEntry1` at `0x140161d7b`
- `watchdog!WdLogSingleEntry1` at `0x140161de4`
- `watchdog!WdLogSingleEntry2` at `0x140161db1`
- `watchdog!WdLogSingleEntry2` at `0x140161db1`
- `dxgkrnl!g_OutputDuplicationTestControl` at `0x140161bc5`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140161a73`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140161a8c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140161a73`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140161a8c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140161b16`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140161b49`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140161b16`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140161b49`
- `WIN32K!W32GetSessionState` at `0x140161a15`
- `WIN32K!W32GetSessionState` at `0x140161abd`
- `WIN32K!W32GetSessionState` at `0x140161a15`
- `WIN32K!W32GetSessionState` at `0x140161abd`
- `WIN32K!W32GetUserSessionState` at `0x140161dff`
- `WIN32K!W32GetUserSessionState` at `0x140161dff`

## string_xrefs

- `0x140161cea`: `shellExperienceComposer`

## pseudocode

```c

```
