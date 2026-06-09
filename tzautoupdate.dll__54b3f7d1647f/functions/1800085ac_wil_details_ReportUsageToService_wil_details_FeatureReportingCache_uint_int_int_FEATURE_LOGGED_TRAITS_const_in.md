# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x1800085ac`
- end: `0x180008649`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `157`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180008414`
- `0x1800084a0`
- `0x180008524`
- `0x180011d1c`
- `0x180011da8`

## callees

- `0x1800085ac`
- `0x180008650`
- `0x18000cc98`
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
0x1800085ac  mov     rax, rsp
0x1800085af  mov     [rax+8], rbx
0x1800085b3  push    rdi
0x1800085b4  sub     rsp, 50h
0x1800085b8  mov     r11, rcx
0x1800085bb  mov     r10d, r8d
0x1800085be  mov     ecx, [rax+38h]
0x1800085c1  mov     ebx, edx
0x1800085c3  test    ecx, ecx
0x1800085c5  jz      short loc_18000863E
0x1800085c7  mov     edx, [rsp+58h+arg_28]
0x1800085ce  call    wil_details_MapReportingKind
0x1800085d3  mov     rdi, [rsp+58h+arg_20]
0x1800085db  mov     edx, ebx
0x1800085dd  mov     rcx, r11
0x1800085e0  mov     r8b, [rdi+4]
0x1800085e4  mov     byte ptr [rsp+58h+var_20], r8b
0x1800085e9  mov     r8d, r10d
0x1800085ec  mov     dword ptr [rsp+58h+var_38], eax
0x1800085f0  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x1800085f5  test    eax, eax
0x1800085f7  jz      short loc_18000863E
0x1800085f9  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180008600  test    rax, rax
0x180008603  jz      short loc_18000863E
0x180008605  mov     r9d, [rsp+58h+arg_28]
0x18000860d  lea     rcx, [rsp+58h+arg_30]
0x180008615  mov     [rsp+58h+var_20], 1
0x18000861e  xor     r8d, r8d
0x180008621  mov     [rsp+58h+var_28], 0
0x180008626  mov     rdx, rdi
0x180008629  mov     [rsp+58h+var_30], 0
0x180008632  mov     [rsp+58h+var_38], rcx
0x180008637  mov     ecx, ebx
0x180008639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000863e  mov     rbx, [rsp+58h+arg_0]
0x180008643  add     rsp, 50h
0x180008647  pop     rdi
0x180008648  retn
```
