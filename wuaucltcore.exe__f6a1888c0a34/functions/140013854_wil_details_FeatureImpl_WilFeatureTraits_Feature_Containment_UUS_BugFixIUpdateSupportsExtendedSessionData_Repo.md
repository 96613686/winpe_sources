# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x140013854`
- end: `0x1400138ed`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x140013728`

## callees

- `0x14000a99c`
- `0x140013764`
- `0x140013854`
- `0x14001aa60`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::ReportUsage(
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
    v6 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCachedFeatureEnabledState(
            a1,
            &v6);
    v2 = v6;
  }
  v7 = 0;
  v8 = 1;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x3509F92u,
           (v2 >> 10) & 1,
           (v2 >> 11) & 1,
           (__int64)&v7,
           v4,
           3);
}

```

## disassembly

```asm
0x140013854  mov     [rsp+arg_8], rbx
0x140013859  push    rdi
0x14001385a  sub     rsp, 60h
0x14001385e  mov     rax, cs:__security_cookie
0x140013865  xor     rax, rsp
0x140013868  mov     [rsp+68h+var_18], rax
0x14001386d  mov     r8d, [rcx]
0x140013870  mov     rbx, rcx
0x140013873  movzx   edi, dl
0x140013876  test    r8b, 4
0x14001387a  jnz     short loc_140013891
0x14001387c  lea     rdx, [rsp+68h+var_28]
0x140013881  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetCachedFeatureEnabledState(void)
0x140013886  mov     rcx, [rax]
0x140013889  mov     [rsp+68h+var_28], rcx
0x14001388e  mov     r8d, ecx
0x140013891  mov     r9d, r8d
0x140013894  mov     [rsp+68h+var_38], 3
0x14001389c  xor     eax, eax
0x14001389e  shr     r9d, 0Bh
0x1400138a2  mov     [rsp+68h+var_20], eax
0x1400138a6  lea     rcx, [rbx+8]
0x1400138aa  shr     r8d, 0Ah
0x1400138ae  lea     rax, [rsp+68h+var_20]
0x1400138b3  and     r9d, 1
0x1400138b7  mov     [rsp+68h+var_40], edi
0x1400138bb  and     r8d, 1
0x1400138bf  mov     [rsp+68h+var_48], rax
0x1400138c4  mov     edx, 3509F92h
0x1400138c9  mov     [rsp+68h+var_1C], 1
0x1400138d0  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x1400138d5  mov     rcx, [rsp+68h+var_18]
0x1400138da  xor     rcx, rsp; StackCookie
0x1400138dd  call    __security_check_cookie
0x1400138e2  mov     rbx, [rsp+68h+arg_8]
0x1400138e7  add     rsp, 60h
0x1400138eb  pop     rdi
0x1400138ec  retn
```
