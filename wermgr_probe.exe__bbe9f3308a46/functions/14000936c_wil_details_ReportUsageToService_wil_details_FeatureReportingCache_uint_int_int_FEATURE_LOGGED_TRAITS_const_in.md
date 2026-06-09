# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000936c`
- end: `0x14000949c`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140004e18`
- `0x140006bec`
- `0x14000daa4`

## callees

- `0x14000936c`
- `0x1400094a4`
- `0x14001e010`

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
  char v9; // [rsp+30h] [rbp-48h]
  _UNKNOWN *retaddr; // [rsp+78h] [rbp+0h] BYREF

  result = &retaddr;
  if ( a7 )
  {
    result = (_UNKNOWN **)wil::details::ReportUsageToServiceDirect(a1);
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
0x14000936c  mov     rax, rsp
0x14000936f  push    rbx
0x140009370  push    rbp
0x140009371  push    rsi
0x140009372  push    rdi
0x140009373  sub     rsp, 58h
0x140009377  mov     r11d, [rax+38h]
0x14000937b  mov     esi, edx
0x14000937d  mov     rbp, rcx
0x140009380  test    r11d, r11d
0x140009383  jz      loc_140009493
0x140009389  mov     ebx, [rsp+78h+arg_28]
0x140009390  mov     r10d, r11d
0x140009393  sub     r10d, 1
0x140009397  jz      loc_140009422
0x14000939d  sub     r10d, 1
0x1400093a1  jz      short loc_140009414
0x1400093a3  sub     r10d, 1
0x1400093a7  jz      short loc_140009406
0x1400093a9  sub     r10d, 1
0x1400093ad  jz      short loc_1400093F8
0x1400093af  sub     r10d, 1
0x1400093b3  jz      short loc_1400093EA
0x1400093b5  cmp     r10d, 1
0x1400093b9  jz      short loc_1400093DC
0x1400093bb  sub     r11b, 64h ; 'd'
0x1400093bf  cmp     r11b, 31h ; '1'
0x1400093c3  ja      short loc_14000942F
0x1400093c5  mov     eax, ebx
0x1400093c7  neg     eax
0x1400093c9  movzx   eax, r11b
0x1400093cd  sbb     ecx, ecx
0x1400093cf  and     ecx, 0FFFFFFCEh
0x1400093d2  add     ecx, 96h
0x1400093d8  add     ecx, eax
0x1400093da  jmp     short loc_140009434
0x1400093dc  mov     eax, ebx
0x1400093de  neg     eax
0x1400093e0  sbb     ecx, ecx
0x1400093e2  and     ecx, 0FFFFFFFEh
0x1400093e5  add     ecx, 0Bh
0x1400093e8  jmp     short loc_140009434
0x1400093ea  mov     eax, ebx
0x1400093ec  neg     eax
0x1400093ee  sbb     ecx, ecx
0x1400093f0  and     ecx, 0FFFFFFFEh
0x1400093f3  add     ecx, 0Ah
0x1400093f6  jmp     short loc_140009434
0x1400093f8  mov     eax, ebx
0x1400093fa  neg     eax
0x1400093fc  sbb     ecx, ecx
0x1400093fe  and     ecx, 0FFFFFFFCh
0x140009401  add     ecx, 7
0x140009404  jmp     short loc_140009434
0x140009406  mov     eax, ebx
0x140009408  neg     eax
0x14000940a  sbb     ecx, ecx
0x14000940c  and     ecx, 0FFFFFFFCh
0x14000940f  add     ecx, 6
0x140009412  jmp     short loc_140009434
0x140009414  mov     eax, ebx
0x140009416  neg     eax
0x140009418  sbb     ecx, ecx
0x14000941a  and     ecx, 0FFFFFFFCh
0x14000941d  add     ecx, 5
0x140009420  jmp     short loc_140009434
0x140009422  mov     eax, ebx
0x140009424  neg     eax
0x140009426  sbb     ecx, ecx
0x140009428  not     ecx
0x14000942a  and     ecx, 4
0x14000942d  jmp     short loc_140009434
0x14000942f  mov     ecx, 0FFh
0x140009434  mov     rdi, [rsp+78h+arg_20]
0x14000943c  mov     al, [rdi+4]
0x14000943f  mov     byte ptr [rsp+78h+var_40], al
0x140009443  mov     dword ptr [rsp+78h+var_58], ecx
0x140009447  mov     rcx, rbp
0x14000944a  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000944f  test    eax, eax
0x140009451  jz      short loc_140009493
0x140009453  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000945a  test    rax, rax
0x14000945d  jz      short loc_140009493
0x14000945f  mov     [rsp+78h+var_40], 1
0x140009468  lea     rcx, [rsp+78h+arg_30]
0x140009470  mov     [rsp+78h+var_48], 0
0x140009475  mov     r9d, ebx
0x140009478  mov     [rsp+78h+var_50], 0
0x140009481  xor     r8d, r8d
0x140009484  mov     [rsp+78h+var_58], rcx
0x140009489  mov     rdx, rdi
0x14000948c  mov     ecx, esi
0x14000948e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009493  add     rsp, 58h
0x140009497  pop     rdi
0x140009498  pop     rsi
0x140009499  pop     rbp
0x14000949a  pop     rbx
0x14000949b  retn
```
