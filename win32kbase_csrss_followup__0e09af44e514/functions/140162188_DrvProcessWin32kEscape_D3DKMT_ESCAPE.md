# DrvProcessWin32kEscape(_D3DKMT_ESCAPE *)

- ea: `0x140162188`
- end: `0x14016278b`
- name: `?DrvProcessWin32kEscape@@YAJPEAU_D3DKMT_ESCAPE@@@Z`
- size: `1539`
- prototype: `__int64 __fastcall(struct _D3DKMT_ESCAPE *)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x140162170`

## callees

- `0x14000d574`
- `0x14000da24`
- `0x14001bdf0`
- `0x140033364`
- `0x140036118`
- `0x1400492a4`
- `0x14004a0d0`
- `0x140078090`
- `0x140078120`
- `0x1400aaa18`
- `0x140162188`
- `0x1401c6028`
- `0x1401cbc90`
- `0x1401dea50`
- `0x1401e61a8`
- `0x1401f8440`
- `0x140238240`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x1401625c9`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x1401625f2`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x1401625c9`
- `ntoskrnl!RtlCapabilityCheckForSingleSessionSku` at `0x1401625f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140162596`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401625ae`
- `ntoskrnl!RtlInitUnicodeString` at `0x140162596`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401625ae`
- `watchdog!WdLogSingleEntry0` at `0x140162213`
- `watchdog!WdLogSingleEntry0` at `0x140162748`
- `watchdog!WdLogSingleEntry0` at `0x140162213`
- `watchdog!WdLogSingleEntry0` at `0x140162748`
- `watchdog!WdLogSingleEntry1` at `0x1401621dd`
- `watchdog!WdLogSingleEntry1` at `0x14016244a`
- `watchdog!WdLogSingleEntry1` at `0x1401624a2`
- `watchdog!WdLogSingleEntry1` at `0x14016261b`
- `watchdog!WdLogSingleEntry1` at `0x140162684`
- `watchdog!WdLogSingleEntry1` at `0x1401621dd`
- `watchdog!WdLogSingleEntry1` at `0x14016244a`
- `watchdog!WdLogSingleEntry1` at `0x1401624a2`
- `watchdog!WdLogSingleEntry1` at `0x14016261b`
- `watchdog!WdLogSingleEntry1` at `0x140162684`
- `watchdog!WdLogSingleEntry2` at `0x140162651`
- `watchdog!WdLogSingleEntry2` at `0x140162651`
- `dxgkrnl!g_OutputDuplicationTestControl` at `0x140162465`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140162313`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14016232c`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x140162313`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14016232c`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401623b6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401623e9`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401623b6`
- `WIN32K!W32GetWin32kBaseApiSetTable` at `0x1401623e9`
- `WIN32K!W32GetSessionState` at `0x1401622b5`
- `WIN32K!W32GetSessionState` at `0x14016235d`
- `WIN32K!W32GetSessionState` at `0x1401622b5`
- `WIN32K!W32GetSessionState` at `0x14016235d`
- `WIN32K!W32GetUserSessionState` at `0x14016269f`
- `WIN32K!W32GetUserSessionState` at `0x14016269f`

## string_xrefs

- `0x14016258a`: `shellExperienceComposer`

## pseudocode

```c

```
