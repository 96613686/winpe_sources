# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000345c`
- end: `0x18000357c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `288`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180002304`
- `0x1800027e8`
- `0x180002acc`

## callees

- `0x180003248`
- `0x18000345c`
- `0x1800148e0`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::ReportUsageToService(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7)
{
  _UNKNOWN **result; // rax
  char v9; // [rsp+30h] [rbp-38h]
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1, a2);
    if ( (_DWORD)result )
    {
      result = (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook;
      if ( g_wil_details_pfnFeatureLoggingHook )
      {
        v9 = 0;
        return (_UNKNOWN **)g_wil_details_pfnFeatureLoggingHook(a2, a5, 0, a6, &a7, 0, v9, 1);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000345c  mov     rax, rsp
0x18000345f  push    rbx
0x180003460  push    rsi
0x180003461  push    rdi
0x180003462  sub     rsp, 50h
0x180003466  mov     rsi, [rsp+68h+arg_20]
0x18000346e  mov     edi, edx
0x180003470  mov     edx, [rax+38h]
0x180003473  mov     r10, rcx
0x180003476  test    edx, edx
0x180003478  jz      loc_180003574
0x18000347e  mov     ebx, [rsp+68h+arg_28]
0x180003485  mov     ecx, edx
0x180003487  sub     ecx, 1
0x18000348a  jz      short loc_180003509
0x18000348c  sub     ecx, 1
0x18000348f  jz      short loc_1800034FB
0x180003491  sub     ecx, 1
0x180003494  jz      short loc_1800034ED
0x180003496  sub     ecx, 1
0x180003499  jz      short loc_1800034DF
0x18000349b  sub     ecx, 1
0x18000349e  jz      short loc_1800034D1
0x1800034a0  cmp     ecx, 1
0x1800034a3  jz      short loc_1800034C3
0x1800034a5  sub     dl, 64h ; 'd'
0x1800034a8  cmp     dl, 31h ; '1'
0x1800034ab  ja      short loc_180003516
0x1800034ad  mov     eax, ebx
0x1800034af  neg     eax
0x1800034b1  movzx   eax, dl
0x1800034b4  sbb     ecx, ecx
0x1800034b6  and     ecx, 0FFFFFFCEh
0x1800034b9  add     ecx, 96h
0x1800034bf  add     ecx, eax
0x1800034c1  jmp     short loc_18000351B
0x1800034c3  mov     eax, ebx
0x1800034c5  neg     eax
0x1800034c7  sbb     ecx, ecx
0x1800034c9  and     ecx, 0FFFFFFFEh
0x1800034cc  add     ecx, 0Bh
0x1800034cf  jmp     short loc_18000351B
0x1800034d1  mov     eax, ebx
0x1800034d3  neg     eax
0x1800034d5  sbb     ecx, ecx
0x1800034d7  and     ecx, 0FFFFFFFEh
0x1800034da  add     ecx, 0Ah
0x1800034dd  jmp     short loc_18000351B
0x1800034df  mov     eax, ebx
0x1800034e1  neg     eax
0x1800034e3  sbb     ecx, ecx
0x1800034e5  and     ecx, 0FFFFFFFCh
0x1800034e8  add     ecx, 7
0x1800034eb  jmp     short loc_18000351B
0x1800034ed  mov     eax, ebx
0x1800034ef  neg     eax
0x1800034f1  sbb     ecx, ecx
0x1800034f3  and     ecx, 0FFFFFFFCh
0x1800034f6  add     ecx, 6
0x1800034f9  jmp     short loc_18000351B
0x1800034fb  mov     eax, ebx
0x1800034fd  neg     eax
0x1800034ff  sbb     ecx, ecx
0x180003501  and     ecx, 0FFFFFFFCh
0x180003504  add     ecx, 5
0x180003507  jmp     short loc_18000351B
0x180003509  mov     eax, ebx
0x18000350b  neg     eax
0x18000350d  sbb     ecx, ecx
0x18000350f  not     ecx
0x180003511  and     ecx, 4
0x180003514  jmp     short loc_18000351B
0x180003516  mov     ecx, 0FFh
0x18000351b  mov     al, [rsi+4]
0x18000351e  mov     edx, edi
0x180003520  mov     byte ptr [rsp+68h+var_30], al
0x180003524  mov     dword ptr [rsp+68h+var_48], ecx
0x180003528  mov     rcx, r10
0x18000352b  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180003530  test    eax, eax
0x180003532  jz      short loc_180003574
0x180003534  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000353b  test    rax, rax
0x18000353e  jz      short loc_180003574
0x180003540  mov     [rsp+68h+var_30], 1
0x180003549  lea     rcx, [rsp+68h+arg_30]
0x180003551  mov     [rsp+68h+var_38], 0
0x180003556  mov     r9d, ebx
0x180003559  mov     [rsp+68h+var_40], 0
0x180003562  xor     r8d, r8d
0x180003565  mov     [rsp+68h+var_48], rcx
0x18000356a  mov     rdx, rsi
0x18000356d  mov     ecx, edi
0x18000356f  call    _guard_dispatch_icall
0x180003574  add     rsp, 50h
0x180003578  pop     rdi
0x180003579  pop     rsi
0x18000357a  pop     rbx
0x18000357b  retn
```
