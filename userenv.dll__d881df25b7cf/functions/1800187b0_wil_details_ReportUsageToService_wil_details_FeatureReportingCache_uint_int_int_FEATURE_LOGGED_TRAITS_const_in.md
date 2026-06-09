# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800187b0`
- end: `0x18001884e`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180018610`
- `0x1800186a0`
- `0x180018724`

## callees

- `0x1800187b0`
- `0x180018854`
- `0x18001a07c`
- `0x18001d010`

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
0x1800187b0  mov     rax, rsp
0x1800187b3  mov     [rax+8], rbx
0x1800187b7  push    rdi
0x1800187b8  sub     rsp, 50h
0x1800187bc  mov     r11, rcx
0x1800187bf  mov     r10d, r8d
0x1800187c2  mov     ecx, [rax+38h]
0x1800187c5  mov     ebx, edx
0x1800187c7  test    ecx, ecx
0x1800187c9  jz      short loc_180018842
0x1800187cb  mov     edx, [rsp+58h+arg_28]
0x1800187d2  call    wil_details_MapReportingKind
0x1800187d7  mov     rdi, [rsp+58h+arg_20]
0x1800187df  mov     edx, ebx
0x1800187e1  mov     rcx, r11
0x1800187e4  mov     r8b, [rdi+4]
0x1800187e8  mov     byte ptr [rsp+58h+var_20], r8b
0x1800187ed  mov     r8d, r10d
0x1800187f0  mov     dword ptr [rsp+58h+var_38], eax
0x1800187f4  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800187f9  test    eax, eax
0x1800187fb  jz      short loc_180018842
0x1800187fd  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180018804  test    rax, rax
0x180018807  jz      short loc_180018842
0x180018809  mov     r9d, [rsp+58h+arg_28]
0x180018811  lea     rcx, [rsp+58h+arg_30]
0x180018819  mov     [rsp+58h+var_20], 1
0x180018822  xor     r8d, r8d
0x180018825  mov     byte ptr [rsp+58h+var_28], 0
0x18001882a  mov     rdx, rdi
0x18001882d  mov     [rsp+58h+var_30], 0
0x180018836  mov     [rsp+58h+var_38], rcx
0x18001883b  mov     ecx, ebx
0x18001883d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018842  mov     rbx, [rsp+58h+arg_0]
0x180018847  add     rsp, 50h
0x18001884b  pop     rdi
0x18001884c  retn
```
