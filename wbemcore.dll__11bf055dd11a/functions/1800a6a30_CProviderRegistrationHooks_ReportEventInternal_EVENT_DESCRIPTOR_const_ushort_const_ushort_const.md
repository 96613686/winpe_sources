# CProviderRegistrationHooks::ReportEventInternal(_EVENT_DESCRIPTOR const &,ushort * const,ushort * const)

- ea: `0x1800a6a30`
- end: `0x1800a6cff`
- name: `?ReportEventInternal@CProviderRegistrationHooks@@AEAAJAEBU_EVENT_DESCRIPTOR@@QEAG1@Z`
- size: `719`
- prototype: `__int64 __fastcall(CProviderRegistrationHooks *__hidden this, const struct _EVENT_DESCRIPTOR *, unsigned __int16 *const, unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a7f28`

## callees

- `0x1800a6a30`
- `0x1800da010`

## import_xrefs

- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x1800a6b5b`
- `wbemcomn!??0CEventLog@@QEAA@PEBGAEBU_GUID@@K@Z` at `0x1800a6b5b`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x1800a6cbf`
- `wbemcomn!??1CEventLog@@QEAA@XZ` at `0x1800a6cbf`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800a6cac`
- `wbemcomn!?Close@CEventLog@@QEAAHXZ` at `0x1800a6cac`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x1800a6b69`
- `wbemcomn!?Open@CEventLog@@QEAAHXZ` at `0x1800a6b69`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x1800a6c34`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x1800a6c50`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x1800a6c34`
- `wbemcomn!??0CInsertionString@@QEAA@PEBG@Z` at `0x1800a6c50`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a6aed`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800a6aed`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a6ce3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800a6ce3`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6b83`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6b99`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6baf`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6bc4`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6bd9`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6bee`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6c03`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6c18`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6b83`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6b99`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6baf`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6bc4`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6bd9`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6bee`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6c03`
- `wbemcomn!??0CInsertionString@@QEAA@XZ` at `0x1800a6c18`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800a6c9f`
- `wbemcomn!?Report@CEventLog@@QEAAHGAEBU_EVENT_DESCRIPTOR@@VCInsertionString@@111111111@Z` at `0x1800a6c9f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800a6b37`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800a6b37`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800a6aa7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800a6aa7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a6a84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a6a84`

## pseudocode

```c

```
