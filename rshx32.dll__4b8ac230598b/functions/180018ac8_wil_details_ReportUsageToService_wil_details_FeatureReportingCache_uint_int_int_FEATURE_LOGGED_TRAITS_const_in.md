# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x180018ac8`
- end: `0x180018bf8`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `13`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180017df8`
- `0x180017f68`
- `0x1800180d8`
- `0x180018248`
- `0x1800183b8`
- `0x180018528`
- `0x180018ee0`
- `0x180018f80`
- `0x18001901c`
- `0x1800190b8`
- `0x180019154`
- `0x1800191f0`
- `0x18001928c`

## callees

- `0x180018ac8`
- `0x180018c00`
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
0x180018ac8  mov     rax, rsp
0x180018acb  push    rbx
0x180018acc  push    rbp
0x180018acd  push    rsi
0x180018ace  push    rdi
0x180018acf  sub     rsp, 58h
0x180018ad3  mov     r11d, [rax+38h]
0x180018ad7  mov     esi, edx
0x180018ad9  mov     rbp, rcx
0x180018adc  test    r11d, r11d
0x180018adf  jz      loc_180018BEF
0x180018ae5  mov     ebx, [rsp+78h+arg_28]
0x180018aec  mov     r10d, r11d
0x180018aef  sub     r10d, 1
0x180018af3  jz      loc_180018B7E
0x180018af9  sub     r10d, 1
0x180018afd  jz      short loc_180018B70
0x180018aff  sub     r10d, 1
0x180018b03  jz      short loc_180018B62
0x180018b05  sub     r10d, 1
0x180018b09  jz      short loc_180018B54
0x180018b0b  sub     r10d, 1
0x180018b0f  jz      short loc_180018B46
0x180018b11  cmp     r10d, 1
0x180018b15  jz      short loc_180018B38
0x180018b17  sub     r11b, 64h ; 'd'
0x180018b1b  cmp     r11b, 31h ; '1'
0x180018b1f  ja      short loc_180018B8B
0x180018b21  mov     eax, ebx
0x180018b23  neg     eax
0x180018b25  movzx   eax, r11b
0x180018b29  sbb     ecx, ecx
0x180018b2b  and     ecx, 0FFFFFFCEh
0x180018b2e  add     ecx, 96h
0x180018b34  add     ecx, eax
0x180018b36  jmp     short loc_180018B90
0x180018b38  mov     eax, ebx
0x180018b3a  neg     eax
0x180018b3c  sbb     ecx, ecx
0x180018b3e  and     ecx, 0FFFFFFFEh
0x180018b41  add     ecx, 0Bh
0x180018b44  jmp     short loc_180018B90
0x180018b46  mov     eax, ebx
0x180018b48  neg     eax
0x180018b4a  sbb     ecx, ecx
0x180018b4c  and     ecx, 0FFFFFFFEh
0x180018b4f  add     ecx, 0Ah
0x180018b52  jmp     short loc_180018B90
0x180018b54  mov     eax, ebx
0x180018b56  neg     eax
0x180018b58  sbb     ecx, ecx
0x180018b5a  and     ecx, 0FFFFFFFCh
0x180018b5d  add     ecx, 7
0x180018b60  jmp     short loc_180018B90
0x180018b62  mov     eax, ebx
0x180018b64  neg     eax
0x180018b66  sbb     ecx, ecx
0x180018b68  and     ecx, 0FFFFFFFCh
0x180018b6b  add     ecx, 6
0x180018b6e  jmp     short loc_180018B90
0x180018b70  mov     eax, ebx
0x180018b72  neg     eax
0x180018b74  sbb     ecx, ecx
0x180018b76  and     ecx, 0FFFFFFFCh
0x180018b79  add     ecx, 5
0x180018b7c  jmp     short loc_180018B90
0x180018b7e  mov     eax, ebx
0x180018b80  neg     eax
0x180018b82  sbb     ecx, ecx
0x180018b84  not     ecx
0x180018b86  and     ecx, 4
0x180018b89  jmp     short loc_180018B90
0x180018b8b  mov     ecx, 0FFh
0x180018b90  mov     rdi, [rsp+78h+arg_20]
0x180018b98  mov     al, [rdi+4]
0x180018b9b  mov     byte ptr [rsp+78h+var_40], al
0x180018b9f  mov     dword ptr [rsp+78h+var_58], ecx
0x180018ba3  mov     rcx, rbp
0x180018ba6  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x180018bab  test    eax, eax
0x180018bad  jz      short loc_180018BEF
0x180018baf  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180018bb6  test    rax, rax
0x180018bb9  jz      short loc_180018BEF
0x180018bbb  mov     [rsp+78h+var_40], 1
0x180018bc4  lea     rcx, [rsp+78h+arg_30]
0x180018bcc  mov     [rsp+78h+var_48], 0
0x180018bd1  mov     r9d, ebx
0x180018bd4  mov     [rsp+78h+var_50], 0
0x180018bdd  xor     r8d, r8d
0x180018be0  mov     [rsp+78h+var_58], rcx
0x180018be5  mov     rdx, rdi
0x180018be8  mov     ecx, esi
0x180018bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bef  add     rsp, 58h
0x180018bf3  pop     rdi
0x180018bf4  pop     rsi
0x180018bf5  pop     rbp
0x180018bf6  pop     rbx
0x180018bf7  retn
```
