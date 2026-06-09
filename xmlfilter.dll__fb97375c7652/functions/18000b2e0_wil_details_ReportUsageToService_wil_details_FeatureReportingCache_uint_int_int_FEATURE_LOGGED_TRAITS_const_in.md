# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000b2e0`
- end: `0x18000b410`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: `_UNKNOWN **__fastcall(__int64, unsigned int, __int64, __int64, __int64, unsigned int, int)`
- caller_count: `11`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180007680`
- `0x1800077f0`
- `0x180007960`
- `0x180007ad0`
- `0x180007c40`
- `0x18000d2f4`
- `0x18000d394`
- `0x18000d430`
- `0x18000d4cc`
- `0x18000d568`
- `0x18000d604`

## callees

- `0x18000b2e0`
- `0x18000b418`
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
0x18000b2e0  mov     rax, rsp
0x18000b2e3  push    rbx
0x18000b2e4  push    rbp
0x18000b2e5  push    rsi
0x18000b2e6  push    rdi
0x18000b2e7  sub     rsp, 58h
0x18000b2eb  mov     r11d, [rax+38h]
0x18000b2ef  mov     esi, edx
0x18000b2f1  mov     rbp, rcx
0x18000b2f4  test    r11d, r11d
0x18000b2f7  jz      loc_18000B407
0x18000b2fd  mov     ebx, [rsp+78h+arg_28]
0x18000b304  mov     r10d, r11d
0x18000b307  sub     r10d, 1
0x18000b30b  jz      loc_18000B396
0x18000b311  sub     r10d, 1
0x18000b315  jz      short loc_18000B388
0x18000b317  sub     r10d, 1
0x18000b31b  jz      short loc_18000B37A
0x18000b31d  sub     r10d, 1
0x18000b321  jz      short loc_18000B36C
0x18000b323  sub     r10d, 1
0x18000b327  jz      short loc_18000B35E
0x18000b329  cmp     r10d, 1
0x18000b32d  jz      short loc_18000B350
0x18000b32f  sub     r11b, 64h ; 'd'
0x18000b333  cmp     r11b, 31h ; '1'
0x18000b337  ja      short loc_18000B3A3
0x18000b339  mov     eax, ebx
0x18000b33b  neg     eax
0x18000b33d  movzx   eax, r11b
0x18000b341  sbb     ecx, ecx
0x18000b343  and     ecx, 0FFFFFFCEh
0x18000b346  add     ecx, 96h
0x18000b34c  add     ecx, eax
0x18000b34e  jmp     short loc_18000B3A8
0x18000b350  mov     eax, ebx
0x18000b352  neg     eax
0x18000b354  sbb     ecx, ecx
0x18000b356  and     ecx, 0FFFFFFFEh
0x18000b359  add     ecx, 0Bh
0x18000b35c  jmp     short loc_18000B3A8
0x18000b35e  mov     eax, ebx
0x18000b360  neg     eax
0x18000b362  sbb     ecx, ecx
0x18000b364  and     ecx, 0FFFFFFFEh
0x18000b367  add     ecx, 0Ah
0x18000b36a  jmp     short loc_18000B3A8
0x18000b36c  mov     eax, ebx
0x18000b36e  neg     eax
0x18000b370  sbb     ecx, ecx
0x18000b372  and     ecx, 0FFFFFFFCh
0x18000b375  add     ecx, 7
0x18000b378  jmp     short loc_18000B3A8
0x18000b37a  mov     eax, ebx
0x18000b37c  neg     eax
0x18000b37e  sbb     ecx, ecx
0x18000b380  and     ecx, 0FFFFFFFCh
0x18000b383  add     ecx, 6
0x18000b386  jmp     short loc_18000B3A8
0x18000b388  mov     eax, ebx
0x18000b38a  neg     eax
0x18000b38c  sbb     ecx, ecx
0x18000b38e  and     ecx, 0FFFFFFFCh
0x18000b391  add     ecx, 5
0x18000b394  jmp     short loc_18000B3A8
0x18000b396  mov     eax, ebx
0x18000b398  neg     eax
0x18000b39a  sbb     ecx, ecx
0x18000b39c  not     ecx
0x18000b39e  and     ecx, 4
0x18000b3a1  jmp     short loc_18000B3A8
0x18000b3a3  mov     ecx, 0FFh
0x18000b3a8  mov     rdi, [rsp+78h+arg_20]
0x18000b3b0  mov     al, [rdi+4]
0x18000b3b3  mov     byte ptr [rsp+78h+var_40], al
0x18000b3b7  mov     dword ptr [rsp+78h+var_58], ecx
0x18000b3bb  mov     rcx, rbp
0x18000b3be  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000b3c3  test    eax, eax
0x18000b3c5  jz      short loc_18000B407
0x18000b3c7  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000b3ce  test    rax, rax
0x18000b3d1  jz      short loc_18000B407
0x18000b3d3  mov     [rsp+78h+var_40], 1
0x18000b3dc  lea     rcx, [rsp+78h+arg_30]
0x18000b3e4  mov     [rsp+78h+var_48], 0
0x18000b3e9  mov     r9d, ebx
0x18000b3ec  mov     [rsp+78h+var_50], 0
0x18000b3f5  xor     r8d, r8d
0x18000b3f8  mov     [rsp+78h+var_58], rcx
0x18000b3fd  mov     rdx, rdi
0x18000b400  mov     ecx, esi
0x18000b402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b407  add     rsp, 58h
0x18000b40b  pop     rdi
0x18000b40c  pop     rsi
0x18000b40d  pop     rbp
0x18000b40e  pop     rbx
0x18000b40f  retn
```
