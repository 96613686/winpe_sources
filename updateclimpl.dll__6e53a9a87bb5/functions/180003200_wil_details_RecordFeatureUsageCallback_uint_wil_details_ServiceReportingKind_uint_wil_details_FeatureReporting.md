# `wil::details::RecordFeatureUsageCallback(uint,wil_details_ServiceReportingKind,uint,wil_details_FeatureReportingCache *,wil_details_RecordUsageResult *)'::`17'::_lambda_1_::_lambda_invoker_cdecl_(void *)

- ea: `0x180003200`
- end: `0x18000323f`
- name: `?_lambda_invoker_cdecl_@_lambda_1_@?BB@??RecordFeatureUsageCallback@details@wil@@YAXIW4wil_details_ServiceReportingKind@@IPEAUwil_details_FeatureReportingCache@@PEAUwil_details_RecordUsageResult@@@Z@SA@PEAX@Z`
- size: `63`
- prototype: `void()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180003020`
- `0x180003200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003214`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003214`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003234`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003234`

## pseudocode

```c
void `wil::details::RecordFeatureUsageCallback'::`17'::_lambda_1_::_lambda_invoker_cdecl_()
{
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    wil::details::EnabledStateManager::RecordCachedUsageUnderLock((wil::details::EnabledStateManager *)&wil::details::g_enabledStateManager);
    byte_18001F1E8 = 0;
    ReleaseSRWLockExclusive(&SRWLock);
  }
}

```

## disassembly

```asm
0x180003200  sub     rsp, 28h
0x180003204  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, 0; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000320b  jz      short loc_18000323A
0x18000320d  lea     rcx, SRWLock; SRWLock
0x180003214  call    cs:__imp_AcquireSRWLockExclusive
0x18000321a  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180003221  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x180003226  lea     rcx, SRWLock; SRWLock
0x18000322d  mov     cs:byte_18001F1E8, 0
0x180003234  call    cs:__imp_ReleaseSRWLockExclusive
0x18000323a  add     rsp, 28h
0x18000323e  retn
```
