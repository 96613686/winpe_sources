# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180003dd0`
- end: `0x180003e73`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `163`
- prototype: ``
- caller_count: `20`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000e83c`
- `0x18000e990`
- `0x18000eae4`
- `0x18000ed24`
- `0x18000faa8`
- `0x18000fb34`
- `0x18000fbc0`
- `0x18000fc4c`
- `0x18000fcd0`
- `0x18000fd58`
- `0x18000fde0`
- `0x18000fe68`
- `0x18000fef0`
- `0x180016850`
- `0x180018cd4`
- `0x180018d60`
- `0x180018de4`
- `0x180018e6c`
- `0x180022d98`
- `0x180023d30`

## callees

- `0x180003dd0`
- `0x18000ff78`
- `0x180011f3c`
- `0x180029010`

## pseudocode

```c
void __fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        unsigned int a7)
{
  unsigned int v8; // r10d
  __int64 v9; // r11
  char v10; // [rsp+30h] [rbp-28h]

  if ( a7 )
  {
    wil_details_MapReportingKind(a7, a6);
    if ( (unsigned int)wil::details::ReportUsageToServiceDirect(v9, a2, v8) )
    {
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v10 = 0;
        g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v10, 1);
      }
    }
  }
}

```

## disassembly

```asm
0x180003dd0  push    rbx
0x180003dd2  sub     rsp, 50h
0x180003dd6  mov     r11, rcx
0x180003dd9  mov     r10d, r8d
0x180003ddc  mov     ecx, [rsp+58h+arg_30]
0x180003de3  mov     ebx, edx
0x180003de5  test    ecx, ecx
0x180003de7  jz      loc_180003E6D
0x180003ded  mov     edx, [rsp+58h+arg_28]
0x180003df4  mov     [rsp+58h+arg_0], rsi
0x180003df9  call    wil_details_MapReportingKind
0x180003dfe  mov     rsi, [rsp+58h+arg_20]
0x180003e06  mov     r8d, r10d
0x180003e09  mov     rcx, r11
0x180003e0c  movzx   edx, byte ptr [rsi+4]
0x180003e10  mov     byte ptr [rsp+58h+var_20], dl
0x180003e14  mov     edx, ebx
0x180003e16  mov     dword ptr [rsp+58h+var_38], eax
0x180003e1a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180003e1f  test    eax, eax
0x180003e21  jz      short loc_180003E68
0x180003e23  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180003e2a  test    rax, rax
0x180003e2d  jz      short loc_180003E68
0x180003e2f  mov     r9d, [rsp+58h+arg_28]
0x180003e37  lea     rcx, [rsp+58h+arg_30]
0x180003e3f  mov     [rsp+58h+var_20], 1
0x180003e48  xor     r8d, r8d
0x180003e4b  mov     [rsp+58h+var_28], 0
0x180003e50  mov     rdx, rsi
0x180003e53  mov     [rsp+58h+var_30], 0
0x180003e5c  mov     [rsp+58h+var_38], rcx
0x180003e61  mov     ecx, ebx
0x180003e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e68  mov     rsi, [rsp+58h+arg_0]
0x180003e6d  add     rsp, 50h
0x180003e71  pop     rbx
0x180003e72  retn
```
