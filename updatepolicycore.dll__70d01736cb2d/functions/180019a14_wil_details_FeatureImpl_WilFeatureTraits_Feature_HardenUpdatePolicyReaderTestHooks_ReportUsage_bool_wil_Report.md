# wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180019a14`
- end: `0x180019aad`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800196a4`

## callees

- `0x180016cac`
- `0x180019924`
- `0x180019a14`
- `0x18002ffd0`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2)
{
  unsigned int v2; // r8d
  unsigned int v4; // edi
  __int64 v6; // [rsp+40h] [rbp-28h] BYREF
  int v7; // [rsp+48h] [rbp-20h] BYREF
  __int16 v8; // [rsp+4Ch] [rbp-1Ch]

  v2 = *(_DWORD *)a1;
  v4 = a2;
  if ( (*(_DWORD *)a1 & 4) == 0 )
  {
    v6 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetCachedFeatureEnabledState(
            a1,
            &v6);
    v2 = v6;
  }
  v7 = 0;
  v8 = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x397658Eu,
           (v2 >> 10) & 1,
           (v2 >> 11) & 1,
           (__int64)&v7,
           v4,
           3);
}

```

## disassembly

```asm
0x180019a14  mov     [rsp+arg_8], rbx
0x180019a19  push    rdi
0x180019a1a  sub     rsp, 60h
0x180019a1e  mov     rax, cs:__security_cookie
0x180019a25  xor     rax, rsp
0x180019a28  mov     [rsp+68h+var_18], rax
0x180019a2d  mov     r8d, [rcx]
0x180019a30  mov     rbx, rcx
0x180019a33  movzx   edi, dl
0x180019a36  test    r8b, 4
0x180019a3a  jnz     short loc_180019A51
0x180019a3c  lea     rdx, [rsp+68h+var_28]
0x180019a41  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HardenUpdatePolicyReaderTestHooks>::GetCachedFeatureEnabledState(void)
0x180019a46  mov     rcx, [rax]
0x180019a49  mov     [rsp+68h+var_28], rcx
0x180019a4e  mov     r8d, ecx
0x180019a51  mov     r9d, r8d
0x180019a54  mov     [rsp+68h+var_38], 3
0x180019a5c  xor     eax, eax
0x180019a5e  shr     r9d, 0Bh
0x180019a62  mov     [rsp+68h+var_20], eax
0x180019a66  lea     rcx, [rbx+8]
0x180019a6a  shr     r8d, 0Ah
0x180019a6e  lea     rax, [rsp+68h+var_20]
0x180019a73  and     r9d, 1
0x180019a77  mov     [rsp+68h+var_40], edi
0x180019a7b  and     r8d, 1
0x180019a7f  mov     [rsp+68h+var_48], rax
0x180019a84  mov     edx, 397658Eh
0x180019a89  mov     [rsp+68h+var_1C], 2
0x180019a90  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180019a95  mov     rcx, [rsp+68h+var_18]
0x180019a9a  xor     rcx, rsp; StackCookie
0x180019a9d  call    __security_check_cookie
0x180019aa2  mov     rbx, [rsp+68h+arg_8]
0x180019aa7  add     rsp, 60h
0x180019aab  pop     rdi
0x180019aac  retn
```
