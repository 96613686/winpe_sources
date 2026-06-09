# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled(void)

- ea: `0x14000daa4`
- end: `0x14000db3b`
- name: `?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@QEAA_NXZ`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x140004e18`
- `0x140005cec`

## callees

- `0x140006b0c`
- `0x14000936c`
- `0x14000daa4`

## pseudocode

```c
unsigned __int8 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::__private_IsEnabled(
        __int64 a1)
{
  __int64 v2; // rcx
  unsigned __int8 v3; // bl
  unsigned int v4; // r8d
  int v6; // [rsp+50h] [rbp+8h] BYREF
  __int16 v7; // [rsp+54h] [rbp+Ch]
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCachedFeatureEnabledState(a1, &v6);
  v3 = v6 & 1;
  v4 = *(_DWORD *)Feature_WerMgrFixInsiderChange__descriptor;
  if ( (*(_DWORD *)Feature_WerMgrFixInsiderChange__descriptor & 4) == 0 )
  {
    v8 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCachedFeatureEnabledState(
                      v2,
                      &v8);
    v4 = v8;
  }
  v6 = 0;
  v7 = 2;
  wil::details::ReportUsageToService(a1 + 8, 0x363AD61u, (v4 >> 10) & 1, (v4 >> 11) & 1, (__int64)&v6, v3, 3);
  return v3;
}

```

## disassembly

```asm
0x14000daa4  mov     [rsp+arg_10], rbx
0x14000daa9  push    rdi
0x14000daaa  sub     rsp, 40h
0x14000daae  lea     rdx, [rsp+48h+arg_0]
0x14000dab3  mov     rdi, rcx
0x14000dab6  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCachedFeatureEnabledState(void)
0x14000dabb  mov     rax, cs:Feature_WerMgrFixInsiderChange__descriptor
0x14000dac2  mov     bl, byte ptr [rsp+48h+arg_0]
0x14000dac6  and     bl, 1
0x14000dac9  mov     r8d, [rax]
0x14000dacc  test    r8b, 4
0x14000dad0  jnz     short loc_14000DAE7
0x14000dad2  lea     rdx, [rsp+48h+arg_8]
0x14000dad7  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WerMgrFixInsiderChange@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WerMgrFixInsiderChange>::GetCachedFeatureEnabledState(void)
0x14000dadc  mov     rcx, [rax]
0x14000dadf  mov     [rsp+48h+arg_8], rcx
0x14000dae4  mov     r8d, ecx
0x14000dae7  mov     r9d, r8d
0x14000daea  movzx   edx, bl
0x14000daed  xor     eax, eax
0x14000daef  shr     r9d, 0Bh
0x14000daf3  mov     [rsp+48h+arg_0], eax
0x14000daf7  lea     rcx, [rdi+8]
0x14000dafb  shr     r8d, 0Ah
0x14000daff  lea     rax, [rsp+48h+arg_0]
0x14000db04  mov     [rsp+48h+var_18], 3
0x14000db0c  and     r9d, 1
0x14000db10  mov     [rsp+48h+var_20], edx
0x14000db14  and     r8d, 1
0x14000db18  mov     edx, 363AD61h
0x14000db1d  mov     [rsp+48h+var_28], rax
0x14000db22  mov     [rsp+48h+arg_4], 2
0x14000db29  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14000db2e  mov     al, bl
0x14000db30  mov     rbx, [rsp+48h+arg_10]
0x14000db35  add     rsp, 40h
0x14000db39  pop     rdi
0x14000db3a  retn
```
