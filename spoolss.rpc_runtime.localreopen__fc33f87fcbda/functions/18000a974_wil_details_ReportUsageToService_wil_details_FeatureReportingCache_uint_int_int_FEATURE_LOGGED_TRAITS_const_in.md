# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000a974`
- end: `0x18000aa12`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `158`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000a738`
- `0x18000a7c4`
- `0x18000a860`
- `0x18000a8e4`

## callees

- `0x18000a974`
- `0x18000aa18`
- `0x1800108dc`
- `0x180017010`

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
0x18000a974  mov     rax, rsp
0x18000a977  mov     [rax+8], rbx
0x18000a97b  push    rdi
0x18000a97c  sub     rsp, 50h
0x18000a980  mov     r11, rcx
0x18000a983  mov     r10d, r8d
0x18000a986  mov     ecx, [rax+38h]
0x18000a989  mov     ebx, edx
0x18000a98b  test    ecx, ecx
0x18000a98d  jz      short loc_18000AA06
0x18000a98f  mov     edx, [rsp+58h+arg_28]
0x18000a996  call    wil_details_MapReportingKind
0x18000a99b  mov     rdi, [rsp+58h+arg_20]
0x18000a9a3  mov     edx, ebx
0x18000a9a5  mov     rcx, r11
0x18000a9a8  mov     r8b, [rdi+4]
0x18000a9ac  mov     byte ptr [rsp+58h+var_20], r8b
0x18000a9b1  mov     r8d, r10d
0x18000a9b4  mov     dword ptr [rsp+58h+var_38], eax
0x18000a9b8  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000a9bd  test    eax, eax
0x18000a9bf  jz      short loc_18000AA06
0x18000a9c1  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000a9c8  test    rax, rax
0x18000a9cb  jz      short loc_18000AA06
0x18000a9cd  mov     r9d, [rsp+58h+arg_28]
0x18000a9d5  lea     rcx, [rsp+58h+arg_30]
0x18000a9dd  mov     [rsp+58h+var_20], 1
0x18000a9e6  xor     r8d, r8d
0x18000a9e9  mov     [rsp+58h+var_28], 0
0x18000a9ee  mov     rdx, rdi
0x18000a9f1  mov     [rsp+58h+var_30], 0
0x18000a9fa  mov     [rsp+58h+var_38], rcx
0x18000a9ff  mov     ecx, ebx
0x18000aa01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa06  mov     rbx, [rsp+58h+arg_0]
0x18000aa0b  add     rsp, 50h
0x18000aa0f  pop     rdi
0x18000aa10  retn
```
