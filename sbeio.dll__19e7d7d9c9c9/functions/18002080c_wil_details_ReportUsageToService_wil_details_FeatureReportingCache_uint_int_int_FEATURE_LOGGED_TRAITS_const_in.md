# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18002080c`
- end: `0x1800208a7`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `155`
- prototype: ``
- caller_count: `10`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800201c8`
- `0x180020270`
- `0x18002030c`
- `0x1800203a8`
- `0x180020444`
- `0x1800204e0`
- `0x180020584`
- `0x180020628`
- `0x1800206cc`
- `0x180020770`

## callees

- `0x18002080c`
- `0x1800208b0`
- `0x180027750`
- `0x18002b010`

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
0x18002080c  mov     rax, rsp
0x18002080f  mov     [rax+18h], rbx
0x180020813  push    rdi
0x180020814  sub     rsp, 50h
0x180020818  mov     rdi, [rsp+58h+arg_20]
0x180020820  mov     r11, rcx
0x180020823  mov     ecx, [rax+38h]
0x180020826  mov     r10d, r8d
0x180020829  mov     ebx, edx
0x18002082b  test    ecx, ecx
0x18002082d  jz      short loc_18002089C
0x18002082f  mov     edx, [rsp+58h+arg_28]
0x180020836  call    wil_details_MapReportingKind
0x18002083b  mov     dl, [rdi+4]
0x18002083e  mov     r8d, r10d
0x180020841  mov     byte ptr [rsp+58h+var_20], dl
0x180020845  mov     rcx, r11
0x180020848  mov     edx, ebx
0x18002084a  mov     dword ptr [rsp+58h+var_38], eax
0x18002084e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180020853  test    eax, eax
0x180020855  jz      short loc_18002089C
0x180020857  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18002085e  test    rax, rax
0x180020861  jz      short loc_18002089C
0x180020863  mov     r9d, [rsp+58h+arg_28]
0x18002086b  lea     rcx, [rsp+58h+arg_30]
0x180020873  mov     [rsp+58h+var_20], 1
0x18002087c  xor     r8d, r8d
0x18002087f  mov     [rsp+58h+var_28], 0
0x180020884  mov     rdx, rdi
0x180020887  mov     [rsp+58h+var_30], 0
0x180020890  mov     [rsp+58h+var_38], rcx
0x180020895  mov     ecx, ebx
0x180020897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002089c  mov     rbx, [rsp+58h+arg_10]
0x1800208a1  add     rsp, 50h
0x1800208a5  pop     rdi
0x1800208a6  retn
```
