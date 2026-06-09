# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(void)

- ea: `0x180014aac`
- end: `0x180014ae1`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180013600`

## callees

- `0x1800128d0`
- `0x180013bd8`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(
        wil::details *a1)
{
  char v2; // bl
  __int64 v3; // r8
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetCachedFeatureEnabledState(
    a1,
    &v5);
  v2 = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::ReportUsage(a1, v5 & 1, v3);
  return v2;
}

```

## disassembly

```asm
0x180014aac  mov     [rsp+arg_0], rbx
0x180014ab1  push    rdi
0x180014ab2  sub     rsp, 20h
0x180014ab6  lea     rdx, [rsp+28h+arg_8]
0x180014abb  mov     rdi, rcx
0x180014abe  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetCachedFeatureEnabledState(void)
0x180014ac3  mov     bl, byte ptr [rsp+28h+arg_8]
0x180014ac7  mov     rcx, rdi
0x180014aca  and     bl, 1
0x180014acd  mov     dl, bl
0x180014acf  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180014ad4  mov     al, bl
0x180014ad6  mov     rbx, [rsp+28h+arg_0]
0x180014adb  add     rsp, 20h
0x180014adf  pop     rdi
0x180014ae0  retn
```
