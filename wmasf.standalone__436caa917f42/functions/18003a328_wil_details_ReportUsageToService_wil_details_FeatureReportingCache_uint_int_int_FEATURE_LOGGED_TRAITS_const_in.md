# wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)

- ea: `0x18003a328`
- end: `0x18003a448`
- name: `?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z`
- size: `288`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180039ce4`
- `0x180039d8c`
- `0x180039e28`
- `0x180039ec4`
- `0x180039f60`
- `0x180039ffc`
- `0x18003a0a0`
- `0x18003a144`
- `0x18003a1e8`
- `0x18003a28c`

## callees

- `0x18003a328`
- `0x18003a450`
- `0x180040010`

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
0x18003a328  mov     rax, rsp
0x18003a32b  push    rbx
0x18003a32c  push    rsi
0x18003a32d  push    rdi
0x18003a32e  sub     rsp, 50h
0x18003a332  mov     rsi, [rsp+68h+arg_20]
0x18003a33a  mov     edi, edx
0x18003a33c  mov     edx, [rax+38h]
0x18003a33f  mov     r10, rcx
0x18003a342  test    edx, edx
0x18003a344  jz      loc_18003A440
0x18003a34a  mov     ebx, [rsp+68h+arg_28]
0x18003a351  mov     ecx, edx
0x18003a353  sub     ecx, 1
0x18003a356  jz      short loc_18003A3D5
0x18003a358  sub     ecx, 1
0x18003a35b  jz      short loc_18003A3C7
0x18003a35d  sub     ecx, 1
0x18003a360  jz      short loc_18003A3B9
0x18003a362  sub     ecx, 1
0x18003a365  jz      short loc_18003A3AB
0x18003a367  sub     ecx, 1
0x18003a36a  jz      short loc_18003A39D
0x18003a36c  cmp     ecx, 1
0x18003a36f  jz      short loc_18003A38F
0x18003a371  sub     dl, 64h ; 'd'
0x18003a374  cmp     dl, 31h ; '1'
0x18003a377  ja      short loc_18003A3E2
0x18003a379  mov     eax, ebx
0x18003a37b  neg     eax
0x18003a37d  movzx   eax, dl
0x18003a380  sbb     ecx, ecx
0x18003a382  and     ecx, 0FFFFFFCEh
0x18003a385  add     ecx, 96h
0x18003a38b  add     ecx, eax
0x18003a38d  jmp     short loc_18003A3E7
0x18003a38f  mov     eax, ebx
0x18003a391  neg     eax
0x18003a393  sbb     ecx, ecx
0x18003a395  and     ecx, 0FFFFFFFEh
0x18003a398  add     ecx, 0Bh
0x18003a39b  jmp     short loc_18003A3E7
0x18003a39d  mov     eax, ebx
0x18003a39f  neg     eax
0x18003a3a1  sbb     ecx, ecx
0x18003a3a3  and     ecx, 0FFFFFFFEh
0x18003a3a6  add     ecx, 0Ah
0x18003a3a9  jmp     short loc_18003A3E7
0x18003a3ab  mov     eax, ebx
0x18003a3ad  neg     eax
0x18003a3af  sbb     ecx, ecx
0x18003a3b1  and     ecx, 0FFFFFFFCh
0x18003a3b4  add     ecx, 7
0x18003a3b7  jmp     short loc_18003A3E7
0x18003a3b9  mov     eax, ebx
0x18003a3bb  neg     eax
0x18003a3bd  sbb     ecx, ecx
0x18003a3bf  and     ecx, 0FFFFFFFCh
0x18003a3c2  add     ecx, 6
0x18003a3c5  jmp     short loc_18003A3E7
0x18003a3c7  mov     eax, ebx
0x18003a3c9  neg     eax
0x18003a3cb  sbb     ecx, ecx
0x18003a3cd  and     ecx, 0FFFFFFFCh
0x18003a3d0  add     ecx, 5
0x18003a3d3  jmp     short loc_18003A3E7
0x18003a3d5  mov     eax, ebx
0x18003a3d7  neg     eax
0x18003a3d9  sbb     ecx, ecx
0x18003a3db  not     ecx
0x18003a3dd  and     ecx, 4
0x18003a3e0  jmp     short loc_18003A3E7
0x18003a3e2  mov     ecx, 0FFh
0x18003a3e7  mov     al, [rsi+4]
0x18003a3ea  mov     edx, edi
0x18003a3ec  mov     byte ptr [rsp+68h+var_30], al
0x18003a3f0  mov     dword ptr [rsp+68h+var_48], ecx
0x18003a3f4  mov     rcx, r10
0x18003a3f7  call    ?ReportUsageToServiceDirect@details@wil@@YAHPEAUwil_details_FeatureReportingCache@@IHHW4wil_details_ServiceReportingKind@@I_KE@Z; wil::details::ReportUsageToServiceDirect(wil_details_FeatureReportingCache *,uint,int,int,wil_details_ServiceReportingKind,uint,unsigned __int64,uchar)
0x18003a3fc  test    eax, eax
0x18003a3fe  jz      short loc_18003A440
0x18003a400  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18003a407  test    rax, rax
0x18003a40a  jz      short loc_18003A440
0x18003a40c  mov     [rsp+68h+var_30], 1
0x18003a415  lea     rcx, [rsp+68h+arg_30]
0x18003a41d  mov     [rsp+68h+var_38], 0
0x18003a422  mov     r9d, ebx
0x18003a425  mov     [rsp+68h+var_40], 0
0x18003a42e  xor     r8d, r8d
0x18003a431  mov     [rsp+68h+var_48], rcx
0x18003a436  mov     rdx, rsi
0x18003a439  mov     ecx, edi
0x18003a43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a440  add     rsp, 50h
0x18003a444  pop     rdi
0x18003a445  pop     rsi
0x18003a446  pop     rbx
0x18003a447  retn
```
