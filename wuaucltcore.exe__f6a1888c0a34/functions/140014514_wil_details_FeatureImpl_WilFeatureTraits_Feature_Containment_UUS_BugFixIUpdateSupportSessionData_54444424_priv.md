# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(wil::ReportingKind)

- ea: `0x140014514`
- end: `0x14001454c`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAA_NW4ReportingKind@3@@Z`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140013938`

## callees

- `0x140014378`
- `0x140014468`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v4; // [rsp+40h] [rbp+18h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCachedFeatureEnabledState(
    a1,
    &v4);
  v2 = v4 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::ReportUsage(
    a1,
    v4 & 1,
    0);
  return v2;
}

```

## disassembly

```asm
0x140014514  mov     [rsp+arg_0], rbx
0x140014519  push    rdi
0x14001451a  sub     rsp, 20h
0x14001451e  lea     rdx, [rsp+28h+arg_10]
0x140014523  mov     rdi, rcx
0x140014526  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCachedFeatureEnabledState(void)
0x14001452b  mov     bl, byte ptr [rsp+28h+arg_10]
0x14001452f  xor     r8d, r8d
0x140014532  and     bl, 1
0x140014535  mov     rcx, rdi
0x140014538  mov     dl, bl
0x14001453a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x14001453f  mov     al, bl
0x140014541  mov     rbx, [rsp+28h+arg_0]
0x140014546  add     rsp, 20h
0x14001454a  pop     rdi
0x14001454b  retn
```
