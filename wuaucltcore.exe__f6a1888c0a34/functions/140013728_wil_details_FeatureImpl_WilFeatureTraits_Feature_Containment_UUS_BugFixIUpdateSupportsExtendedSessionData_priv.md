# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)

- ea: `0x140013728`
- end: `0x14001375d`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140012128`
- `0x1400126b8`

## callees

- `0x140013764`
- `0x140013854`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v4; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCachedFeatureEnabledState(
    a1,
    &v4);
  v2 = v4 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::ReportUsage(
    a1,
    v4 & 1);
  return v2;
}

```

## disassembly

```asm
0x140013728  mov     [rsp+arg_0], rbx
0x14001372d  push    rdi
0x14001372e  sub     rsp, 20h
0x140013732  lea     rdx, [rsp+28h+arg_8]
0x140013737  mov     rdi, rcx
0x14001373a  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCachedFeatureEnabledState(void)
0x14001373f  mov     bl, byte ptr [rsp+28h+arg_8]
0x140013743  mov     rcx, rdi
0x140013746  and     bl, 1
0x140013749  mov     dl, bl
0x14001374b  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140013750  mov     al, bl
0x140013752  mov     rbx, [rsp+28h+arg_0]
0x140013757  add     rsp, 20h
0x14001375b  pop     rdi
0x14001375c  retn
```
