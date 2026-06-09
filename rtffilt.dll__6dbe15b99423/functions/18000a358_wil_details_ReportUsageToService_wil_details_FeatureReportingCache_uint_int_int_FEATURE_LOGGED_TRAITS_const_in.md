# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18000a358`
- end: `0x18000a490`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `312`
- prototype: ``
- caller_count: `15`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180006970`
- `0x18000c614`
- `0x18000c6b4`
- `0x1800131e0`
- `0x1800133b4`
- `0x18001359c`
- `0x180014dd0`
- `0x180014e68`
- `0x180015190`
- `0x18001522c`
- `0x180015348`
- `0x1800153e4`
- `0x180015484`
- `0x180015524`
- `0x180015644`

## callees

- `0x18000a358`
- `0x18000a498`
- `0x18001b010`

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
0x18000a358  mov     rax, rsp
0x18000a35b  push    rbx
0x18000a35c  push    rbp
0x18000a35d  push    rsi
0x18000a35e  push    rdi
0x18000a35f  sub     rsp, 58h
0x18000a363  mov     r11d, [rax+38h]
0x18000a367  mov     esi, edx
0x18000a369  mov     rbp, rcx
0x18000a36c  test    r11d, r11d
0x18000a36f  jz      loc_18000A487
0x18000a375  mov     ebx, [rsp+78h+arg_28]
0x18000a37c  mov     r10d, r11d
0x18000a37f  sub     r10d, 1
0x18000a383  jz      loc_18000A40E
0x18000a389  sub     r10d, 1
0x18000a38d  jz      short loc_18000A400
0x18000a38f  sub     r10d, 1
0x18000a393  jz      short loc_18000A3F2
0x18000a395  sub     r10d, 1
0x18000a399  jz      short loc_18000A3E4
0x18000a39b  sub     r10d, 1
0x18000a39f  jz      short loc_18000A3D6
0x18000a3a1  cmp     r10d, 1
0x18000a3a5  jz      short loc_18000A3C8
0x18000a3a7  sub     r11b, 64h ; 'd'
0x18000a3ab  cmp     r11b, 31h ; '1'
0x18000a3af  ja      short loc_18000A41B
0x18000a3b1  mov     eax, ebx
0x18000a3b3  neg     eax
0x18000a3b5  movzx   eax, r11b
0x18000a3b9  sbb     ecx, ecx
0x18000a3bb  and     ecx, 0FFFFFFCEh
0x18000a3be  add     ecx, 96h
0x18000a3c4  add     ecx, eax
0x18000a3c6  jmp     short loc_18000A420
0x18000a3c8  mov     eax, ebx
0x18000a3ca  neg     eax
0x18000a3cc  sbb     ecx, ecx
0x18000a3ce  and     ecx, 0FFFFFFFEh
0x18000a3d1  add     ecx, 0Bh
0x18000a3d4  jmp     short loc_18000A420
0x18000a3d6  mov     eax, ebx
0x18000a3d8  neg     eax
0x18000a3da  sbb     ecx, ecx
0x18000a3dc  and     ecx, 0FFFFFFFEh
0x18000a3df  add     ecx, 0Ah
0x18000a3e2  jmp     short loc_18000A420
0x18000a3e4  mov     eax, ebx
0x18000a3e6  neg     eax
0x18000a3e8  sbb     ecx, ecx
0x18000a3ea  and     ecx, 0FFFFFFFCh
0x18000a3ed  add     ecx, 7
0x18000a3f0  jmp     short loc_18000A420
0x18000a3f2  mov     eax, ebx
0x18000a3f4  neg     eax
0x18000a3f6  sbb     ecx, ecx
0x18000a3f8  and     ecx, 0FFFFFFFCh
0x18000a3fb  add     ecx, 6
0x18000a3fe  jmp     short loc_18000A420
0x18000a400  mov     eax, ebx
0x18000a402  neg     eax
0x18000a404  sbb     ecx, ecx
0x18000a406  and     ecx, 0FFFFFFFCh
0x18000a409  add     ecx, 5
0x18000a40c  jmp     short loc_18000A420
0x18000a40e  mov     eax, ebx
0x18000a410  neg     eax
0x18000a412  sbb     ecx, ecx
0x18000a414  not     ecx
0x18000a416  and     ecx, 4
0x18000a419  jmp     short loc_18000A420
0x18000a41b  mov     ecx, 0FFh
0x18000a420  mov     rdi, [rsp+78h+arg_20]
0x18000a428  mov     al, [rdi+4]
0x18000a42b  mov     byte ptr [rsp+78h+var_40], al
0x18000a42f  mov     dword ptr [rsp+78h+var_50], 0
0x18000a437  mov     dword ptr [rsp+78h+var_58], ecx
0x18000a43b  mov     rcx, rbp
0x18000a43e  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18000a443  test    eax, eax
0x18000a445  jz      short loc_18000A487
0x18000a447  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000a44e  test    rax, rax
0x18000a451  jz      short loc_18000A487
0x18000a453  mov     [rsp+78h+var_40], 1
0x18000a45c  lea     rcx, [rsp+78h+arg_30]
0x18000a464  mov     [rsp+78h+var_48], 0
0x18000a469  mov     r9d, ebx
0x18000a46c  mov     [rsp+78h+var_50], 0
0x18000a475  xor     r8d, r8d
0x18000a478  mov     [rsp+78h+var_58], rcx
0x18000a47d  mov     rdx, rdi
0x18000a480  mov     ecx, esi
0x18000a482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a487  add     rsp, 58h
0x18000a48b  pop     rdi
0x18000a48c  pop     rsi
0x18000a48d  pop     rbp
0x18000a48e  pop     rbx
0x18000a48f  retn
```
