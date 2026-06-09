# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)

- ea: `0x18000c614`
- end: `0x18000c6ab`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800040f4`
- `0x1800049b0`
- `0x180005340`
- `0x18000555c`
- `0x180005750`
- `0x180005ae4`

## callees

- `0x180006324`
- `0x18000a358`
- `0x18000c614`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(
        wil::details *a1)
{
  wil::details *v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  __int64 v6; // [rsp+50h] [rbp+8h] BYREF
  __int64 v7; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_56494824__descriptor;
  if ( (*(_DWORD *)Feature_56494824__descriptor & 4) == 0 )
  {
    v7 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(v2, &v7);
    v4 = v7;
  }
  LODWORD(v6) = 0;
  WORD2(v6) = 1;
  wil::details::ReportUsageToService((__int64)a1 + 8, 0x35E0AE8u, (v4 >> 10) & 1, (v4 >> 11) & 1, (__int64)&v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x18000c614  mov     [rsp+arg_10], rbx
0x18000c619  push    rdi
0x18000c61a  sub     rsp, 40h
0x18000c61e  lea     rdx, [rsp+48h+arg_0]
0x18000c623  mov     rdi, rcx
0x18000c626  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)
0x18000c62b  mov     rax, cs:Feature_56494824__descriptor
0x18000c632  mov     bl, byte ptr [rsp+48h+arg_0]
0x18000c636  and     bl, 1
0x18000c639  mov     r8d, [rax]
0x18000c63c  test    r8b, 4
0x18000c640  jnz     short loc_18000C657
0x18000c642  lea     rdx, [rsp+48h+arg_8]
0x18000c647  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::GetCachedFeatureEnabledState(void)
0x18000c64c  mov     rcx, [rax]
0x18000c64f  mov     [rsp+48h+arg_8], rcx
0x18000c654  mov     r8d, ecx
0x18000c657  mov     r9d, r8d
0x18000c65a  movzx   edx, bl
0x18000c65d  xor     eax, eax
0x18000c65f  shr     r9d, 0Bh
0x18000c663  mov     [rsp+48h+arg_0], eax
0x18000c667  lea     rcx, [rdi+8]
0x18000c66b  shr     r8d, 0Ah
0x18000c66f  lea     rax, [rsp+48h+arg_0]
0x18000c674  mov     [rsp+48h+var_18], 3
0x18000c67c  and     r9d, 1
0x18000c680  mov     [rsp+48h+var_20], edx
0x18000c684  and     r8d, 1
0x18000c688  mov     edx, 35E0AE8h
0x18000c68d  mov     [rsp+48h+var_28], rax
0x18000c692  mov     [rsp+48h+arg_4], 1
0x18000c699  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x18000c69e  mov     al, bl
0x18000c6a0  mov     rbx, [rsp+48h+arg_10]
0x18000c6a5  add     rsp, 40h
0x18000c6a9  pop     rdi
0x18000c6aa  retn
```
