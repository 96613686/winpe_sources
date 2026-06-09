# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180013bd8`
- end: `0x180013c5e`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180014aac`

## callees

- `0x18001104c`
- `0x1800128d0`
- `0x180013bd8`

## pseudocode

```c
_UNKNOWN **wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2,
        __int64 a3,
        ...)
{
  unsigned int v4; // ebx
  __int64 v5; // r8
  __int64 v7; // [rsp+50h] [rbp+8h] BYREF
  __int64 v8; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v8 = va_arg(va1, _QWORD);
  v4 = a2;
  LODWORD(v5) = *(_DWORD *)Feature_BugFixJsonHelperCannotBeUsedInMTA__descriptor;
  if ( (*(_DWORD *)Feature_BugFixJsonHelperCannotBeUsedInMTA__descriptor & 4) == 0 )
  {
    v5 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetCachedFeatureEnabledState(
            a1,
            &v7);
    v7 = v5;
  }
  LODWORD(v8) = 0;
  WORD2(v8) = 1;
  return wil::details::ReportUsageToService(
           (__int64)a1 + 8,
           0x391F742u,
           ((unsigned int)v5 >> 10) & 1,
           ((unsigned int)v5 >> 11) & 1,
           (__int64)va,
           v4,
           3u);
}

```

## disassembly

```asm
0x180013bd8  mov     [rsp+arg_8], rbx
0x180013bdd  mov     [rsp+arg_18], r9
0x180013be2  push    rdi
0x180013be3  sub     rsp, 40h
0x180013be7  mov     rax, cs:Feature_BugFixJsonHelperCannotBeUsedInMTA__descriptor
0x180013bee  mov     rdi, rcx
0x180013bf1  movzx   ebx, dl
0x180013bf4  mov     r8d, [rax]
0x180013bf7  test    r8b, 4
0x180013bfb  jnz     short loc_180013C0F
0x180013bfd  lea     rdx, [rsp+48h+arg_0]
0x180013c02  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetCachedFeatureEnabledState(void)
0x180013c07  mov     r8, [rax]
0x180013c0a  mov     [rsp+48h+arg_0], r8
0x180013c0f  mov     r9d, r8d
0x180013c12  mov     [rsp+48h+var_18], 3
0x180013c1a  xor     eax, eax
0x180013c1c  shr     r9d, 0Bh
0x180013c20  mov     dword ptr [rsp+48h+arg_18], eax
0x180013c24  lea     rcx, [rdi+8]
0x180013c28  shr     r8d, 0Ah
0x180013c2c  lea     rax, [rsp+48h+arg_18]
0x180013c31  and     r9d, 1
0x180013c35  mov     [rsp+48h+var_20], ebx
0x180013c39  and     r8d, 1
0x180013c3d  mov     [rsp+48h+var_28], rax
0x180013c42  mov     edx, 391F742h
0x180013c47  mov     word ptr [rsp+48h+arg_18+4], 1
0x180013c4e  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180013c53  mov     rbx, [rsp+48h+arg_8]
0x180013c58  add     rsp, 40h
0x180013c5c  pop     rdi
0x180013c5d  retn
```
