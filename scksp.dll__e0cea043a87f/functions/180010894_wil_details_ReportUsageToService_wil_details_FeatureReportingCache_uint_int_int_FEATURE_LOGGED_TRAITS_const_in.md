# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180010894`
- end: `0x180010931`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800106fc`
- `0x180010788`
- `0x18001080c`

## callees

- `0x18000bbb8`
- `0x180010894`
- `0x180010938`
- `0x18003d010`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  _UNKNOWN **result; // rax
  unsigned int v9; // eax
  int v10; // r9d
  int v11; // r10d
  struct wil_details_FeatureReportingCache *v12; // r11
  __int64 v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-28h]
  int v15; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    v9 = wil_details_MapReportingKind(a7, a6);
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(v12, a2, v11, v10, v9, v13, v14, *(_BYTE *)(a5 + 4));
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        LOBYTE(v15) = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v15, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010894  mov     rax, rsp
0x180010897  mov     [rax+8], rbx
0x18001089b  push    rdi
0x18001089c  sub     rsp, 50h
0x1800108a0  mov     r11, rcx
0x1800108a3  mov     r10d, r8d
0x1800108a6  mov     ecx, [rax+38h]
0x1800108a9  mov     ebx, edx
0x1800108ab  test    ecx, ecx
0x1800108ad  jz      short loc_180010926
0x1800108af  mov     edx, [rsp+58h+arg_28]
0x1800108b6  call    wil_details_MapReportingKind
0x1800108bb  mov     rdi, [rsp+58h+arg_20]
0x1800108c3  mov     edx, ebx
0x1800108c5  mov     rcx, r11
0x1800108c8  mov     r8b, [rdi+4]
0x1800108cc  mov     byte ptr [rsp+58h+var_20], r8b
0x1800108d1  mov     r8d, r10d
0x1800108d4  mov     dword ptr [rsp+58h+var_38], eax
0x1800108d8  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800108dd  test    eax, eax
0x1800108df  jz      short loc_180010926
0x1800108e1  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800108e8  test    rax, rax
0x1800108eb  jz      short loc_180010926
0x1800108ed  mov     r9d, [rsp+58h+arg_28]
0x1800108f5  lea     rcx, [rsp+58h+arg_30]
0x1800108fd  mov     [rsp+58h+var_20], 1
0x180010906  xor     r8d, r8d
0x180010909  mov     byte ptr [rsp+58h+var_28], 0
0x18001090e  mov     rdx, rdi
0x180010911  mov     [rsp+58h+var_30], 0
0x18001091a  mov     [rsp+58h+var_38], rcx
0x18001091f  mov     ecx, ebx
0x180010921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010926  mov     rbx, [rsp+58h+arg_0]
0x18001092b  add     rsp, 50h
0x18001092f  pop     rdi
0x180010930  retn
```
