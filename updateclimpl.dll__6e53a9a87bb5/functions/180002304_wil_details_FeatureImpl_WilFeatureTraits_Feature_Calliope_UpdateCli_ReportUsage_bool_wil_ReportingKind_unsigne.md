# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180002304`
- end: `0x18000239d`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `153`
- prototype: `__int64 __fastcall(wil::details *, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800021d8`

## callees

- `0x180002214`
- `0x180002304`
- `0x18000345c`
- `0x180010310`

## pseudocode

```c
__int64 __fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2)
{
  unsigned int v2; // r8d
  int v4; // edi
  __int64 v6; // [rsp+40h] [rbp-28h] BYREF
  int v7; // [rsp+48h] [rbp-20h] BYREF
  __int16 v8; // [rsp+4Ch] [rbp-1Ch]

  v2 = *(_DWORD *)a1;
  v4 = a2;
  if ( (*(_DWORD *)a1 & 4) == 0 )
  {
    v6 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCachedFeatureEnabledState(
            a1,
            &v6);
    v2 = v6;
  }
  v7 = 0;
  v8 = 2;
  return wil::details::ReportUsageToService((char *)a1 + 8, 59428333, (v2 >> 10) & 1, (v2 >> 11) & 1, &v7, v4, 3);
}

```

## disassembly

```asm
0x180002304  mov     [rsp+arg_8], rbx
0x180002309  push    rdi
0x18000230a  sub     rsp, 60h
0x18000230e  mov     rax, cs:__security_cookie
0x180002315  xor     rax, rsp
0x180002318  mov     [rsp+68h+var_18], rax
0x18000231d  mov     r8d, [rcx]
0x180002320  mov     rbx, rcx
0x180002323  movzx   edi, dl
0x180002326  test    r8b, 4
0x18000232a  jnz     short loc_180002341
0x18000232c  lea     rdx, [rsp+68h+var_28]
0x180002331  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Calliope_UpdateCli@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Calliope_UpdateCli>::GetCachedFeatureEnabledState(void)
0x180002336  mov     rcx, [rax]
0x180002339  mov     [rsp+68h+var_28], rcx
0x18000233e  mov     r8d, ecx
0x180002341  mov     r9d, r8d
0x180002344  mov     [rsp+68h+var_38], 3
0x18000234c  xor     eax, eax
0x18000234e  shr     r9d, 0Bh
0x180002352  mov     [rsp+68h+var_20], eax
0x180002356  lea     rcx, [rbx+8]
0x18000235a  shr     r8d, 0Ah
0x18000235e  lea     rax, [rsp+68h+var_20]
0x180002363  and     r9d, 1
0x180002367  mov     [rsp+68h+var_40], edi
0x18000236b  and     r8d, 1
0x18000236f  mov     [rsp+68h+var_48], rax
0x180002374  mov     edx, 38ACDEDh
0x180002379  mov     [rsp+68h+var_1C], 2
0x180002380  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180002385  mov     rcx, [rsp+68h+var_18]
0x18000238a  xor     rcx, rsp; StackCookie
0x18000238d  call    __security_check_cookie
0x180002392  mov     rbx, [rsp+68h+arg_8]
0x180002397  add     rsp, 60h
0x18000239b  pop     rdi
0x18000239c  retn
```
