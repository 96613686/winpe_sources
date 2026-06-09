# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x140016c04`
- end: `0x140016ca2`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `158`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140016b74`
- `0x14001a540`
- `0x140021e38`
- `0x140021ec8`
- `0x140021f58`

## callees

- `0x140016c04`
- `0x140016ca8`
- `0x1400185f4`
- `0x140029010`

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
  unsigned int v9; // r10d
  __int64 v10; // r11
  char v11; // [rsp+30h] [rbp-28h]
  _UNKNOWN *retaddr; // [rsp+58h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    wil_details_MapReportingKind(a7, a6);
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(v10, a2, v9);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v11 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v11, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140016c04  mov     rax, rsp
0x140016c07  mov     [rax+8], rbx
0x140016c0b  push    rdi
0x140016c0c  sub     rsp, 50h
0x140016c10  mov     r11, rcx
0x140016c13  mov     r10d, r8d
0x140016c16  mov     ecx, [rax+38h]
0x140016c19  mov     ebx, edx
0x140016c1b  test    ecx, ecx
0x140016c1d  jz      short loc_140016C96
0x140016c1f  mov     edx, [rsp+58h+arg_28]
0x140016c26  call    wil_details_MapReportingKind
0x140016c2b  mov     rdi, [rsp+58h+arg_20]
0x140016c33  mov     edx, ebx
0x140016c35  mov     rcx, r11
0x140016c38  mov     r8b, [rdi+4]
0x140016c3c  mov     byte ptr [rsp+58h+var_20], r8b
0x140016c41  mov     r8d, r10d
0x140016c44  mov     dword ptr [rsp+58h+var_38], eax
0x140016c48  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x140016c4d  test    eax, eax
0x140016c4f  jz      short loc_140016C96
0x140016c51  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140016c58  test    rax, rax
0x140016c5b  jz      short loc_140016C96
0x140016c5d  mov     r9d, [rsp+58h+arg_28]
0x140016c65  lea     rcx, [rsp+58h+arg_30]
0x140016c6d  mov     [rsp+58h+var_20], 1
0x140016c76  xor     r8d, r8d
0x140016c79  mov     [rsp+58h+var_28], 0
0x140016c7e  mov     rdx, rdi
0x140016c81  mov     [rsp+58h+var_30], 0
0x140016c8a  mov     [rsp+58h+var_38], rcx
0x140016c8f  mov     ecx, ebx
0x140016c91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016c96  mov     rbx, [rsp+58h+arg_0]
0x140016c9b  add     rsp, 50h
0x140016c9f  pop     rdi
0x140016ca0  retn
```
