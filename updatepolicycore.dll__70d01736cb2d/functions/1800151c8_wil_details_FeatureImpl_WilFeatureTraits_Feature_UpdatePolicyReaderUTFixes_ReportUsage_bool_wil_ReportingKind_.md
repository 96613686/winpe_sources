# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x1800151c8`
- end: `0x180015261`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180014ea8`

## callees

- `0x1800150d8`
- `0x1800151c8`
- `0x180016cac`
- `0x18002ffd0`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::ReportUsage(
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
    v6 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetCachedFeatureEnabledState(
            a1,
            &v6);
    v2 = v6;
  }
  v7 = 0;
  v8 = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x3946E9Au,
           (v2 >> 10) & 1,
           (v2 >> 11) & 1,
           (__int64)&v7,
           v4,
           3);
}

```

## disassembly

```asm
0x1800151c8  mov     [rsp+arg_8], rbx
0x1800151cd  push    rdi
0x1800151ce  sub     rsp, 60h
0x1800151d2  mov     rax, cs:__security_cookie
0x1800151d9  xor     rax, rsp
0x1800151dc  mov     [rsp+68h+var_18], rax
0x1800151e1  mov     r8d, [rcx]
0x1800151e4  mov     rbx, rcx
0x1800151e7  movzx   edi, dl
0x1800151ea  test    r8b, 4
0x1800151ee  jnz     short loc_180015205
0x1800151f0  lea     rdx, [rsp+68h+var_28]
0x1800151f5  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UpdatePolicyReaderUTFixes>::GetCachedFeatureEnabledState(void)
0x1800151fa  mov     rcx, [rax]
0x1800151fd  mov     [rsp+68h+var_28], rcx
0x180015202  mov     r8d, ecx
0x180015205  mov     r9d, r8d
0x180015208  mov     [rsp+68h+var_38], 3
0x180015210  xor     eax, eax
0x180015212  shr     r9d, 0Bh
0x180015216  mov     [rsp+68h+var_20], eax
0x18001521a  lea     rcx, [rbx+8]
0x18001521e  shr     r8d, 0Ah
0x180015222  lea     rax, [rsp+68h+var_20]
0x180015227  and     r9d, 1
0x18001522b  mov     [rsp+68h+var_40], edi
0x18001522f  and     r8d, 1
0x180015233  mov     [rsp+68h+var_48], rax
0x180015238  mov     edx, 3946E9Ah
0x18001523d  mov     [rsp+68h+var_1C], 2
0x180015244  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180015249  mov     rcx, [rsp+68h+var_18]
0x18001524e  xor     rcx, rsp; StackCookie
0x180015251  call    __security_check_cookie
0x180015256  mov     rbx, [rsp+68h+arg_8]
0x18001525b  add     rsp, 60h
0x18001525f  pop     rdi
0x180015260  retn
```
