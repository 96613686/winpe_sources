# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x140014468`
- end: `0x14001450d`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140014514`

## callees

- `0x14000a99c`
- `0x140014378`
- `0x140014468`
- `0x14001aa60`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::ReportUsage(
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
    v8 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCachedFeatureEnabledState(
            a1,
            &v8);
    v5 = v8;
  }
  v9 = 0;
  v10 = 2;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x33EC188u,
           (v5 >> 10) & 1,
           (v5 >> 11) & 1,
           (__int64)&v9,
           v6,
           v3);
}

```

## disassembly

```asm
0x140014468  mov     [rsp+arg_8], rbx
0x14001446d  mov     [rsp+arg_10], rsi
0x140014472  push    rdi
0x140014473  sub     rsp, 60h
0x140014477  mov     rax, cs:__security_cookie
0x14001447e  xor     rax, rsp
0x140014481  mov     [rsp+68h+var_18], rax
0x140014486  movzx   edi, r8b
0x14001448a  mov     rbx, rcx
0x14001448d  mov     r8d, [rcx]
0x140014490  movzx   esi, dl
0x140014493  test    r8b, 4
0x140014497  jnz     short loc_1400144AE
0x140014499  lea     rdx, [rsp+68h+var_28]
0x14001449e  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportSessionData_54444424>::GetCachedFeatureEnabledState(void)
0x1400144a3  mov     rcx, [rax]
0x1400144a6  mov     [rsp+68h+var_28], rcx
0x1400144ab  mov     r8d, ecx
0x1400144ae  mov     r9d, r8d
0x1400144b1  mov     [rsp+68h+var_38], edi
0x1400144b5  xor     eax, eax
0x1400144b7  shr     r9d, 0Bh
0x1400144bb  mov     [rsp+68h+var_20], eax
0x1400144bf  lea     rcx, [rbx+8]
0x1400144c3  shr     r8d, 0Ah
0x1400144c7  lea     rax, [rsp+68h+var_20]
0x1400144cc  and     r9d, 1
0x1400144d0  mov     [rsp+68h+var_40], esi
0x1400144d4  and     r8d, 1
0x1400144d8  mov     [rsp+68h+var_48], rax
0x1400144dd  mov     edx, 33EC188h
0x1400144e2  mov     [rsp+68h+var_1C], 2
0x1400144e9  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1400144ee  mov     rcx, [rsp+68h+var_18]
0x1400144f3  xor     rcx, rsp; StackCookie
0x1400144f6  call    __security_check_cookie
0x1400144fb  lea     r11, [rsp+68h+var_8]
0x140014500  mov     rbx, [r11+18h]
0x140014504  mov     rsi, [r11+20h]
0x140014508  mov     rsp, r11
0x14001450b  pop     rdi
0x14001450c  retn
```
