# DrvProcessWin32kEscape(_D3DKMT_ESCAPE *)

- ea: `0x140164758`
- end: `0x140164d5b`
- name: `?DrvProcessWin32kEscape@@YAJPEAU_D3DKMT_ESCAPE@@@Z`
- size: `1539`
- prototype: `__int64 __fastcall(struct _D3DKMT_ESCAPE *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x140164740`

## callees

- `0x14000d094`
- `0x14000d544`
- `0x140029710`
- `0x14004f4c0`
- `0x14004f550`
- `0x1400701d4`
- `0x14007ab04`
- `0x14007b930`
- `0x1400d4328`
- `0x1400d7988`
- `0x140164758`
- `0x1401c7158`
- `0x1401cca10`
- `0x1401df590`
- `0x1401e6a08`
- `0x1401f8ca0`
- `0x1402389c0`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140164b99`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140164bc2`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140164b99`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x140164bc2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140164b66`
- `ntoskrnl!RtlInitUnicodeString` at `0x140164b7e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140164b66`
- `ntoskrnl!RtlInitUnicodeString` at `0x140164b7e`
- `watchdog!WdLogSingleEntry0` at `0x1401647e3`
- `watchdog!WdLogSingleEntry0` at `0x140164d18`
- `watchdog!WdLogSingleEntry0` at `0x1401647e3`
- `watchdog!WdLogSingleEntry0` at `0x140164d18`
- `watchdog!WdLogSingleEntry1` at `0x1401647ad`
- `watchdog!WdLogSingleEntry1` at `0x140164a1a`
- `watchdog!WdLogSingleEntry1` at `0x140164a72`
- `watchdog!WdLogSingleEntry1` at `0x140164beb`
- `watchdog!WdLogSingleEntry1` at `0x140164c54`
- `watchdog!WdLogSingleEntry1` at `0x1401647ad`
- `watchdog!WdLogSingleEntry1` at `0x140164a1a`
- `watchdog!WdLogSingleEntry1` at `0x140164a72`
- `watchdog!WdLogSingleEntry1` at `0x140164beb`
- `watchdog!WdLogSingleEntry1` at `0x140164c54`
- `watchdog!WdLogSingleEntry2` at `0x140164c21`
- `watchdog!WdLogSingleEntry2` at `0x140164c21`
- `dxgkrnl!g_OutputDuplicationTestControl` at `0x140164a35`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401648e3`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401648fc`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401648e3`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1401648fc`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140164986`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401649b9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x140164986`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401649b9`
- `WIN32K!W32GetSessionState` at `0x140164885`
- `WIN32K!W32GetSessionState` at `0x14016492d`
- `WIN32K!W32GetSessionState` at `0x140164885`
- `WIN32K!W32GetSessionState` at `0x14016492d`
- `WIN32K!W32GetUserSessionState` at `0x140164c6f`
- `WIN32K!W32GetUserSessionState` at `0x140164c6f`

## string_xrefs

- `0x140164b5a`: `shellExperienceComposer`

## pseudocode

```c

```
