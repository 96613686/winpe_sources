# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::__private_IsEnabled(void)

- ea: `0x180019404`
- end: `0x18001943a`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAA_NXZ`
- size: `54`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180008dd8`
- `0x18000ab30`
- `0x18000ab88`
- `0x18000bca8`
- `0x18000bd3c`
- `0x18000c8c0`
- `0x18000cdc4`
- `0x1800197f0`
- `0x18001a508`

## callees

- `0x1800166dc`
- `0x180018610`

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
0x180019404  mov     [rsp+arg_0], rbx
0x180019409  push    rdi
0x18001940a  sub     rsp, 20h
0x18001940e  lea     rdx, [rsp+28h+arg_8]
0x180019413  mov     rdi, rcx
0x180019416  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(void)
0x18001941b  mov     bl, [rsp+28h+arg_8]
0x18001941f  mov     rcx, rdi
0x180019422  and     bl, 1
0x180019425  mov     dl, bl
0x180019427  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001942c  mov     al, bl
0x18001942e  mov     rbx, [rsp+28h+arg_0]
0x180019433  add     rsp, 20h
0x180019437  pop     rdi
0x180019438  retn
```
