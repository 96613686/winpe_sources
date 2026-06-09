# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::__private_IsEnabled(void)

- ea: `0x1800021d8`
- end: `0x18000220d`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@QEAA_NXZ`
- size: `53`
- prototype: `char __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800021a0`

## callees

- `0x180002214`
- `0x180002304`

## pseudocode

```c
char __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::__private_IsEnabled(
        __int64 a1)
{
  char v2; // bl
  __int64 v3; // rdx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCachedFeatureEnabledState(a1, &v5);
  v2 = v5 & 1;
  LOBYTE(v3) = v5 & 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::ReportUsage(a1, v3);
  return v2;
}

```

## disassembly

```asm
0x1800021d8  mov     [rsp+arg_0], rbx
0x1800021dd  push    rdi
0x1800021de  sub     rsp, 20h
0x1800021e2  lea     rdx, [rsp+28h+arg_8]
0x1800021e7  mov     rdi, rcx
0x1800021ea  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCachedFeatureEnabledState(void)
0x1800021ef  mov     bl, [rsp+28h+arg_8]
0x1800021f3  mov     rcx, rdi
0x1800021f6  and     bl, 1
0x1800021f9  mov     dl, bl
0x1800021fb  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180002200  mov     al, bl
0x180002202  mov     rbx, [rsp+28h+arg_0]
0x180002207  add     rsp, 20h
0x18000220b  pop     rdi
0x18000220c  retn
```
