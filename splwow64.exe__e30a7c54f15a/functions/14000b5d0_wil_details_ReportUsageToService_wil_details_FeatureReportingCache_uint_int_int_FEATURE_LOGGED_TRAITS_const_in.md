# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x14000b5d0`
- end: `0x14000b700`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `304`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140009d6c`
- `0x14000c2b4`
- `0x14000f940`

## callees

- `0x14000b5d0`
- `0x14000b708`
- `0x140016010`

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
0x14000b5d0  mov     rax, rsp
0x14000b5d3  push    rbx
0x14000b5d4  push    rbp
0x14000b5d5  push    rsi
0x14000b5d6  push    rdi
0x14000b5d7  sub     rsp, 58h
0x14000b5db  mov     r11d, [rax+38h]
0x14000b5df  mov     esi, edx
0x14000b5e1  mov     rbp, rcx
0x14000b5e4  test    r11d, r11d
0x14000b5e7  jz      loc_14000B6F7
0x14000b5ed  mov     ebx, [rsp+78h+arg_28]
0x14000b5f4  mov     r10d, r11d
0x14000b5f7  sub     r10d, 1
0x14000b5fb  jz      loc_14000B686
0x14000b601  sub     r10d, 1
0x14000b605  jz      short loc_14000B678
0x14000b607  sub     r10d, 1
0x14000b60b  jz      short loc_14000B66A
0x14000b60d  sub     r10d, 1
0x14000b611  jz      short loc_14000B65C
0x14000b613  sub     r10d, 1
0x14000b617  jz      short loc_14000B64E
0x14000b619  cmp     r10d, 1
0x14000b61d  jz      short loc_14000B640
0x14000b61f  sub     r11b, 64h ; 'd'
0x14000b623  cmp     r11b, 31h ; '1'
0x14000b627  ja      short loc_14000B693
0x14000b629  mov     eax, ebx
0x14000b62b  neg     eax
0x14000b62d  movzx   eax, r11b
0x14000b631  sbb     ecx, ecx
0x14000b633  and     ecx, 0FFFFFFCEh
0x14000b636  add     ecx, 96h
0x14000b63c  add     ecx, eax
0x14000b63e  jmp     short loc_14000B698
0x14000b640  mov     eax, ebx
0x14000b642  neg     eax
0x14000b644  sbb     ecx, ecx
0x14000b646  and     ecx, 0FFFFFFFEh
0x14000b649  add     ecx, 0Bh
0x14000b64c  jmp     short loc_14000B698
0x14000b64e  mov     eax, ebx
0x14000b650  neg     eax
0x14000b652  sbb     ecx, ecx
0x14000b654  and     ecx, 0FFFFFFFEh
0x14000b657  add     ecx, 0Ah
0x14000b65a  jmp     short loc_14000B698
0x14000b65c  mov     eax, ebx
0x14000b65e  neg     eax
0x14000b660  sbb     ecx, ecx
0x14000b662  and     ecx, 0FFFFFFFCh
0x14000b665  add     ecx, 7
0x14000b668  jmp     short loc_14000B698
0x14000b66a  mov     eax, ebx
0x14000b66c  neg     eax
0x14000b66e  sbb     ecx, ecx
0x14000b670  and     ecx, 0FFFFFFFCh
0x14000b673  add     ecx, 6
0x14000b676  jmp     short loc_14000B698
0x14000b678  mov     eax, ebx
0x14000b67a  neg     eax
0x14000b67c  sbb     ecx, ecx
0x14000b67e  and     ecx, 0FFFFFFFCh
0x14000b681  add     ecx, 5
0x14000b684  jmp     short loc_14000B698
0x14000b686  mov     eax, ebx
0x14000b688  neg     eax
0x14000b68a  sbb     ecx, ecx
0x14000b68c  not     ecx
0x14000b68e  and     ecx, 4
0x14000b691  jmp     short loc_14000B698
0x14000b693  mov     ecx, 0FFh
0x14000b698  mov     rdi, [rsp+78h+arg_20]
0x14000b6a0  mov     al, [rdi+4]
0x14000b6a3  mov     byte ptr [rsp+78h+var_40], al
0x14000b6a7  mov     dword ptr [rsp+78h+var_58], ecx
0x14000b6ab  mov     rcx, rbp
0x14000b6ae  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x14000b6b3  test    eax, eax
0x14000b6b5  jz      short loc_14000B6F7
0x14000b6b7  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000b6be  test    rax, rax
0x14000b6c1  jz      short loc_14000B6F7
0x14000b6c3  mov     [rsp+78h+var_40], 1
0x14000b6cc  lea     rcx, [rsp+78h+arg_30]
0x14000b6d4  mov     [rsp+78h+var_48], 0
0x14000b6d9  mov     r9d, ebx
0x14000b6dc  mov     [rsp+78h+var_50], 0
0x14000b6e5  xor     r8d, r8d
0x14000b6e8  mov     [rsp+78h+var_58], rcx
0x14000b6ed  mov     rdx, rdi
0x14000b6f0  mov     ecx, esi
0x14000b6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b6f7  add     rsp, 58h
0x14000b6fb  pop     rdi
0x14000b6fc  pop     rsi
0x14000b6fd  pop     rbp
0x14000b6fe  pop     rbx
0x14000b6ff  retn
```
