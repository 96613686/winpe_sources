# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18001104c`
- end: `0x1800110e9`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000fba4`
- `0x180010f38`
- `0x180010fc4`
- `0x180013bd8`

## callees

- `0x180009480`
- `0x18001104c`
- `0x1800110f0`
- `0x180016010`

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
0x18001104c  mov     rax, rsp
0x18001104f  mov     [rax+8], rbx
0x180011053  push    rdi
0x180011054  sub     rsp, 50h
0x180011058  mov     r11, rcx
0x18001105b  mov     r10d, r8d
0x18001105e  mov     ecx, [rax+38h]
0x180011061  mov     ebx, edx
0x180011063  test    ecx, ecx
0x180011065  jz      short loc_1800110DE
0x180011067  mov     edx, [rsp+58h+arg_28]
0x18001106e  call    wil_details_MapReportingKind
0x180011073  mov     rdi, [rsp+58h+arg_20]
0x18001107b  mov     edx, ebx
0x18001107d  mov     rcx, r11
0x180011080  mov     r8b, [rdi+4]
0x180011084  mov     byte ptr [rsp+58h+var_20], r8b
0x180011089  mov     r8d, r10d
0x18001108c  mov     dword ptr [rsp+58h+var_38], eax
0x180011090  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180011095  test    eax, eax
0x180011097  jz      short loc_1800110DE
0x180011099  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x1800110a0  test    rax, rax
0x1800110a3  jz      short loc_1800110DE
0x1800110a5  mov     r9d, [rsp+58h+arg_28]
0x1800110ad  lea     rcx, [rsp+58h+arg_30]
0x1800110b5  mov     [rsp+58h+var_20], 1
0x1800110be  xor     r8d, r8d
0x1800110c1  mov     [rsp+58h+var_28], 0
0x1800110c6  mov     rdx, rdi
0x1800110c9  mov     [rsp+58h+var_30], 0
0x1800110d2  mov     [rsp+58h+var_38], rcx
0x1800110d7  mov     ecx, ebx
0x1800110d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110de  mov     rbx, [rsp+58h+arg_0]
0x1800110e3  add     rsp, 50h
0x1800110e7  pop     rdi
0x1800110e8  retn
```
