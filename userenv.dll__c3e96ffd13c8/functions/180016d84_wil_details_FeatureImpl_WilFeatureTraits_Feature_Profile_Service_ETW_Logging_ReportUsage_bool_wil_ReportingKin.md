# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)

- ea: `0x180016d84`
- end: `0x180016e56`
- name: `?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z`
- size: `210`
- prototype: `__int64 (__fastcall *(wil::details *, unsigned __int8, char, ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180017a94`

## callees

- `0x180015404`
- `0x180016d84`
- `0x180016e5c`
- `0x1800186d8`
- `0x18001c010`

## pseudocode

```c
__int64 (__fastcall *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::ReportUsage(
        wil::details *a1,
        unsigned __int8 a2,
        char a3,
        ...))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v4; // ebx
  int v5; // eax
  unsigned int v6; // r10d
  __int64 v7; // rdx
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  __int64 v9; // [rsp+60h] [rbp+8h] BYREF
  int v10; // [rsp+70h] [rbp+18h] BYREF
  __int64 v11; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v11 = va_arg(va1, _QWORD);
  LOBYTE(v10) = a3;
  v4 = a2;
  if ( (*(_DWORD *)Feature_Profile_Service_ETW_Logging__descriptor & 4) == 0 )
    v9 = *wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(
            a1,
            &v9);
  WORD2(v11) = 1;
  LODWORD(v11) = 0;
  v10 = 3;
  v5 = wil_details_MapReportingKind(3, v4);
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil::details::ReportUsageToServiceDirect(
                                                                                                     (char *)a1 + 8,
                                                                                                     v7,
                                                                                                     (v6 >> 10) & 1,
                                                                                                     (v6 >> 11) & 1,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(46832940, (__int64 *)va, 0, v4, &v10, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x180016d84  mov     r11, rsp
0x180016d87  mov     [r11+10h], rbx
0x180016d8b  mov     [r11+20h], r9
0x180016d8f  mov     [r11+18h], r8b
0x180016d93  push    rdi
0x180016d94  sub     rsp, 50h
0x180016d98  mov     rax, cs:Feature_Profile_Service_ETW_Logging__descriptor
0x180016d9f  mov     rdi, rcx
0x180016da2  movzx   ebx, dl
0x180016da5  mov     r10d, [rax]
0x180016da8  test    r10b, 4
0x180016dac  jnz     short loc_180016DC2
0x180016dae  lea     rdx, [r11+8]
0x180016db2  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Profile_Service_ETW_Logging@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Profile_Service_ETW_Logging>::GetCachedFeatureEnabledState(void)
0x180016db7  mov     r8, [rax]
0x180016dba  mov     [rsp+58h+arg_0], r8
0x180016dbf  mov     r10d, r8d
0x180016dc2  xor     eax, eax
0x180016dc4  mov     word ptr [rsp+58h+arg_18+4], 1
0x180016dcb  mov     edx, ebx
0x180016dcd  mov     dword ptr [rsp+58h+arg_18], eax
0x180016dd1  lea     ecx, [rax+3]
0x180016dd4  mov     [rsp+58h+arg_10], ecx
0x180016dd8  call    wil_details_MapReportingKind
0x180016ddd  mov     r9d, r10d
0x180016de0  mov     byte ptr [rsp+58h+var_20], 1
0x180016de5  shr     r10d, 0Ah
0x180016de9  lea     rcx, [rdi+8]
0x180016ded  and     r10d, 1
0x180016df1  shr     r9d, 0Bh
0x180016df5  mov     r8d, r10d
0x180016df8  mov     dword ptr [rsp+58h+var_38], eax
0x180016dfc  and     r9d, 1
0x180016e00  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180016e05  test    eax, eax
0x180016e07  jz      short loc_180016E4B
0x180016e09  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180016e10  test    rax, rax
0x180016e13  jz      short loc_180016E4B
0x180016e15  mov     [rsp+58h+var_20], 1
0x180016e1e  lea     rcx, [rsp+58h+arg_10]
0x180016e23  mov     [rsp+58h+var_28], 0
0x180016e28  lea     rdx, [rsp+58h+arg_18]
0x180016e2d  mov     [rsp+58h+var_30], 0
0x180016e36  mov     r9d, ebx
0x180016e39  mov     [rsp+58h+var_38], rcx
0x180016e3e  xor     r8d, r8d
0x180016e41  mov     ecx, 2CA9D2Ch
0x180016e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e4b  mov     rbx, [rsp+58h+arg_8]
0x180016e50  add     rsp, 50h
0x180016e54  pop     rdi
0x180016e55  retn
```
