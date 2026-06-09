# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(void)

- ea: `0x14000c2b4`
- end: `0x14000c34b`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000cca0`
- `0x14000e110`
- `0x14000e3c0`
- `0x140012740`

## callees

- `0x140009b0c`
- `0x14000b5d0`
- `0x14000c2b4`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::__private_IsEnabled(
        wil::details *a1)
{
  wil::details *v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(
    a1,
    &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor;
  if ( (*(_DWORD *)Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor & 4) == 0 )
  {
    v7 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(
            v2,
            &v7);
    v4 = v7;
  }
  LODWORD(v6) = 0;
  WORD2(v6) = 2;
  wil::details::ReportUsageToService((__int64)a1 + 8, 0x35E7C60u, (v4 >> 10) & 1, (v4 >> 11) & 1, (__int64)&v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x14000c2b4  mov     [rsp+arg_10], rbx
0x14000c2b9  push    rdi
0x14000c2ba  sub     rsp, 40h
0x14000c2be  lea     rdx, [rsp+48h+arg_0]
0x14000c2c3  mov     rdi, rcx
0x14000c2c6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(void)
0x14000c2cb  mov     rax, cs:Feature_Print_PlatformStabilizationFixes_2025_Wave1__descriptor
0x14000c2d2  mov     bl, byte ptr [rsp+48h+arg_0]
0x14000c2d6  and     bl, 1
0x14000c2d9  mov     r8d, [rax]
0x14000c2dc  test    r8b, 4
0x14000c2e0  jnz     short loc_14000C2F7
0x14000c2e2  lea     rdx, [rsp+48h+arg_8]
0x14000c2e7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2025_Wave1>::GetCachedFeatureEnabledState(void)
0x14000c2ec  mov     rcx, [rax]
0x14000c2ef  mov     [rsp+48h+arg_8], rcx
0x14000c2f4  mov     r8d, ecx
0x14000c2f7  mov     r9d, r8d
0x14000c2fa  movzx   edx, bl
0x14000c2fd  xor     eax, eax
0x14000c2ff  shr     r9d, 0Bh
0x14000c303  mov     [rsp+48h+arg_0], eax
0x14000c307  lea     rcx, [rdi+8]
0x14000c30b  shr     r8d, 0Ah
0x14000c30f  lea     rax, [rsp+48h+arg_0]
0x14000c314  mov     [rsp+48h+var_18], 3
0x14000c31c  and     r9d, 1
0x14000c320  mov     [rsp+48h+var_20], edx
0x14000c324  and     r8d, 1
0x14000c328  mov     edx, 35E7C60h
0x14000c32d  mov     [rsp+48h+var_28], rax
0x14000c332  mov     [rsp+48h+arg_4], 2
0x14000c339  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14000c33e  mov     al, bl
0x14000c340  mov     rbx, [rsp+48h+arg_10]
0x14000c345  add     rsp, 40h
0x14000c349  pop     rdi
0x14000c34a  retn
```
