# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)

- ea: `0x180017a94`
- end: `0x180017ac9`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800085b0`
- `0x18000a1b0`
- `0x18000a200`
- `0x18000b23c`
- `0x18000b2d0`
- `0x18000bdd8`
- `0x18000c25c`
- `0x180017ee0`
- `0x180018b50`

## callees

- `0x180015404`
- `0x180016d84`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(
        __int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(
    a1,
    &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x180017a94  mov     [rsp+arg_0], rbx
0x180017a99  push    rdi
0x180017a9a  sub     rsp, 20h
0x180017a9e  lea     rdx, [rsp+28h+arg_8]
0x180017aa3  mov     rdi, rcx
0x180017aa6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(void)
0x180017aab  mov     bl, [rsp+28h+arg_8]
0x180017aaf  mov     rcx, rdi
0x180017ab2  and     bl, 1
0x180017ab5  mov     dl, bl
0x180017ab7  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180017abc  mov     al, bl
0x180017abe  mov     rbx, [rsp+28h+arg_0]
0x180017ac3  add     rsp, 20h
0x180017ac7  pop     rdi
0x180017ac8  retn
```
