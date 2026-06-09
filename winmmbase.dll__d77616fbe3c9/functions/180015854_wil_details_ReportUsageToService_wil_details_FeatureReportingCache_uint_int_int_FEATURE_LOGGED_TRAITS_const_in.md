# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180015854`
- end: `0x1800158f1`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `13`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800157c8`
- `0x18001c17c`
- `0x18001c204`
- `0x18001c28c`
- `0x18001c318`
- `0x18001c39c`
- `0x18001c420`
- `0x18001c4a4`
- `0x18001c528`
- `0x18001c5b0`
- `0x18001c638`
- `0x18001c6c0`
- `0x18001c748`

## callees

- `0x180015854`
- `0x1800158f8`
- `0x180016e30`
- `0x180021010`

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
0x180015854  mov     rax, rsp
0x180015857  mov     [rax+8], rbx
0x18001585b  push    rdi
0x18001585c  sub     rsp, 50h
0x180015860  mov     r11, rcx
0x180015863  mov     r10d, r8d
0x180015866  mov     ecx, [rax+38h]
0x180015869  mov     ebx, edx
0x18001586b  test    ecx, ecx
0x18001586d  jz      short loc_1800158E6
0x18001586f  mov     edx, [rsp+58h+arg_28]
0x180015876  call    wil_details_MapReportingKind
0x18001587b  mov     rdi, [rsp+58h+arg_20]
0x180015883  mov     edx, ebx
0x180015885  mov     rcx, r11
0x180015888  mov     r8b, [rdi+4]
0x18001588c  mov     byte ptr [rsp+58h+var_20], r8b
0x180015891  mov     r8d, r10d
0x180015894  mov     dword ptr [rsp+58h+var_38], eax
0x180015898  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18001589d  test    eax, eax
0x18001589f  jz      short loc_1800158E6
0x1800158a1  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800158a8  test    rax, rax
0x1800158ab  jz      short loc_1800158E6
0x1800158ad  mov     r9d, [rsp+58h+arg_28]
0x1800158b5  lea     rcx, [rsp+58h+arg_30]
0x1800158bd  mov     [rsp+58h+var_20], 1
0x1800158c6  xor     r8d, r8d
0x1800158c9  mov     [rsp+58h+var_28], 0
0x1800158ce  mov     rdx, rdi
0x1800158d1  mov     [rsp+58h+var_30], 0
0x1800158da  mov     [rsp+58h+var_38], rcx
0x1800158df  mov     ecx, ebx
0x1800158e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158e6  mov     rbx, [rsp+58h+arg_0]
0x1800158eb  add     rsp, 50h
0x1800158ef  pop     rdi
0x1800158f0  retn
```
