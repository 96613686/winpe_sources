# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180016b00`
- end: `0x180016b9c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `156`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800165fc`
- `0x1800166a4`
- `0x180016740`
- `0x1800167dc`
- `0x180016878`
- `0x18001691c`
- `0x1800169c0`
- `0x180016a64`
- `0x18001c1b4`

## callees

- `0x180016b00`
- `0x180016ba4`
- `0x1800171ec`
- `0x18001e010`

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
0x180016b00  mov     rax, rsp
0x180016b03  mov     [rax+18h], rbx
0x180016b07  push    rdi
0x180016b08  sub     rsp, 50h
0x180016b0c  mov     rdi, [rsp+58h+arg_20]
0x180016b14  mov     r11, rcx
0x180016b17  mov     ecx, [rax+38h]
0x180016b1a  mov     r10d, r8d
0x180016b1d  mov     ebx, edx
0x180016b1f  test    ecx, ecx
0x180016b21  jz      short loc_180016B90
0x180016b23  mov     edx, [rsp+58h+arg_28]
0x180016b2a  call    wil_details_MapReportingKind
0x180016b2f  mov     dl, [rdi+4]
0x180016b32  mov     r8d, r10d
0x180016b35  mov     byte ptr [rsp+58h+var_20], dl
0x180016b39  mov     rcx, r11
0x180016b3c  mov     edx, ebx
0x180016b3e  mov     dword ptr [rsp+58h+var_38], eax
0x180016b42  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180016b47  test    eax, eax
0x180016b49  jz      short loc_180016B90
0x180016b4b  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180016b52  test    rax, rax
0x180016b55  jz      short loc_180016B90
0x180016b57  mov     r9d, [rsp+58h+arg_28]
0x180016b5f  lea     rcx, [rsp+58h+arg_30]
0x180016b67  mov     [rsp+58h+var_20], 1
0x180016b70  xor     r8d, r8d
0x180016b73  mov     [rsp+58h+var_28], 0
0x180016b78  mov     rdx, rdi
0x180016b7b  mov     [rsp+58h+var_30], 0
0x180016b84  mov     [rsp+58h+var_38], rcx
0x180016b89  mov     ecx, ebx
0x180016b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b90  mov     rbx, [rsp+58h+arg_10]
0x180016b95  add     rsp, 50h
0x180016b99  pop     rdi
0x180016b9a  retn
```
