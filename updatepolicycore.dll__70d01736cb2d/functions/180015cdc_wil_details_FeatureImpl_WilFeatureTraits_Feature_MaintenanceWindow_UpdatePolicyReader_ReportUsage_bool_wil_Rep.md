# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180015cdc`
- end: `0x180015d81`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `165`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180014ee4`
- `0x180015c9c`

## callees

- `0x180015cdc`
- `0x1800162c8`
- `0x180016cac`
- `0x18002ffd0`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2,
        unsigned __int8 a3)
{
  int v3; // edi
  unsigned int v5; // r8d
  unsigned int v6; // esi
  __int64 v8; // [rsp+40h] [rbp-28h] BYREF
  int v9; // [rsp+48h] [rbp-20h] BYREF
  __int16 v10; // [rsp+4Ch] [rbp-1Ch]

  v3 = a3;
  v5 = *(_DWORD *)a1;
  v6 = a2;
  if ( (*(_DWORD *)a1 & 4) == 0 )
  {
    v8 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::GetCachedFeatureEnabledState(
            a1,
            &v8);
    v5 = v8;
  }
  v9 = 0;
  v10 = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x2E89729u,
           (v5 >> 10) & 1,
           (v5 >> 11) & 1,
           (__int64)&v9,
           v6,
           v3);
}

```

## disassembly

```asm
0x180015cdc  mov     [rsp+arg_8], rbx
0x180015ce1  mov     [rsp+arg_10], rsi
0x180015ce6  push    rdi
0x180015ce7  sub     rsp, 60h
0x180015ceb  mov     rax, cs:__security_cookie
0x180015cf2  xor     rax, rsp
0x180015cf5  mov     [rsp+68h+var_18], rax
0x180015cfa  movzx   edi, r8b
0x180015cfe  mov     rbx, rcx
0x180015d01  mov     r8d, [rcx]
0x180015d04  movzx   esi, dl
0x180015d07  test    r8b, 4
0x180015d0b  jnz     short loc_180015D22
0x180015d0d  lea     rdx, [rsp+68h+var_28]
0x180015d12  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MaintenanceWindow_UpdatePolicyReader>::GetCachedFeatureEnabledState(void)
0x180015d17  mov     rcx, [rax]
0x180015d1a  mov     [rsp+68h+var_28], rcx
0x180015d1f  mov     r8d, ecx
0x180015d22  mov     r9d, r8d
0x180015d25  mov     [rsp+68h+var_38], edi
0x180015d29  xor     eax, eax
0x180015d2b  shr     r9d, 0Bh
0x180015d2f  mov     [rsp+68h+var_20], eax
0x180015d33  lea     rcx, [rbx+8]
0x180015d37  shr     r8d, 0Ah
0x180015d3b  lea     rax, [rsp+68h+var_20]
0x180015d40  and     r9d, 1
0x180015d44  mov     [rsp+68h+var_40], esi
0x180015d48  and     r8d, 1
0x180015d4c  mov     [rsp+68h+var_48], rax
0x180015d51  mov     edx, 2E89729h
0x180015d56  mov     [rsp+68h+var_1C], 2
0x180015d5d  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180015d62  mov     rcx, [rsp+68h+var_18]
0x180015d67  xor     rcx, rsp; StackCookie
0x180015d6a  call    __security_check_cookie
0x180015d6f  lea     r11, [rsp+68h+var_8]
0x180015d74  mov     rbx, [r11+18h]
0x180015d78  mov     rsi, [r11+20h]
0x180015d7c  mov     rsp, r11
0x180015d7f  pop     rdi
0x180015d80  retn
```
