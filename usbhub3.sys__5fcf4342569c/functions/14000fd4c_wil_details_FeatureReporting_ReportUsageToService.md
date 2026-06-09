# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14000fd4c`
- end: `0x14000fe71`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `293`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140010210`
- `0x140025f38`
- `0x140032d40`

## callees

- `0x14000fd4c`
- `0x14000fe78`
- `0x140045570`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        int a3))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v3; // ebx
  __int64 v5; // r8
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  int v7; // [rsp+70h] [rbp+18h] BYREF

  v7 = a3;
  v3 = a2 & 1;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        v5 = 4 * (unsigned int)!(a2 & 1);
        goto LABEL_17;
      case 2:
        v5 = 4 * (unsigned int)!(a2 & 1) + 1;
        goto LABEL_17;
      case 3:
        v5 = 4 * (unsigned int)!(a2 & 1) + 2;
        goto LABEL_17;
      case 4:
        v5 = 4 * (unsigned int)!(a2 & 1) + 3;
        goto LABEL_17;
      case 5:
        v5 = 2 * (unsigned int)!(a2 & 1) + 8;
        goto LABEL_17;
      case 6:
        v5 = 2 * (unsigned int)!(a2 & 1) + 9;
        goto LABEL_17;
    }
    if ( (unsigned __int8)(a3 - 100) <= 0x31u )
    {
      v5 = (unsigned __int8)(a3 - 100) + (v3 != 0 ? 100 : 150);
      goto LABEL_17;
    }
  }
  v5 = 255;
LABEL_17:
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     a2,
                                                                                                     v5);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v3, &v7, 0, 0, 1);
  }
  return result;
}

```

## disassembly

```asm
0x14000fd4c  mov     [rsp+arg_0], rbx
0x14000fd51  mov     [rsp+arg_10], r8d
0x14000fd56  push    rdi
0x14000fd57  sub     rsp, 50h
0x14000fd5b  mov     ebx, edx
0x14000fd5d  mov     r10d, r8d
0x14000fd60  and     ebx, 1
0x14000fd63  mov     rdi, rcx
0x14000fd66  mov     r9d, r8d
0x14000fd69  test    r8d, r8d
0x14000fd6c  jz      loc_14000FE17
0x14000fd72  sub     r9d, 1
0x14000fd76  jz      loc_14000FE0A
0x14000fd7c  sub     r9d, 1
0x14000fd80  jz      short loc_14000FDFB
0x14000fd82  sub     r9d, 1
0x14000fd86  jz      short loc_14000FDEC
0x14000fd88  sub     r9d, 1
0x14000fd8c  jz      short loc_14000FDDD
0x14000fd8e  sub     r9d, 1
0x14000fd92  jz      short loc_14000FDCE
0x14000fd94  cmp     r9d, 1
0x14000fd98  jz      short loc_14000FDBF
0x14000fd9a  sub     r10b, 64h ; 'd'
0x14000fd9e  cmp     r10b, 31h ; '1'
0x14000fda2  ja      short loc_14000FE17
0x14000fda4  mov     eax, ebx
0x14000fda6  neg     eax
0x14000fda8  movzx   eax, r10b
0x14000fdac  sbb     r8d, r8d
0x14000fdaf  and     r8d, 0FFFFFFCEh
0x14000fdb3  add     r8d, 96h
0x14000fdba  add     r8d, eax
0x14000fdbd  jmp     short loc_14000FE1D
0x14000fdbf  mov     eax, ebx
0x14000fdc1  xor     eax, 1
0x14000fdc4  lea     r8d, ds:9[rax*2]
0x14000fdcc  jmp     short loc_14000FE1D
0x14000fdce  mov     eax, ebx
0x14000fdd0  xor     eax, 1
0x14000fdd3  lea     r8d, ds:8[rax*2]
0x14000fddb  jmp     short loc_14000FE1D
0x14000fddd  mov     eax, ebx
0x14000fddf  xor     eax, 1
0x14000fde2  lea     r8d, ds:3[rax*4]
0x14000fdea  jmp     short loc_14000FE1D
0x14000fdec  mov     eax, ebx
0x14000fdee  xor     eax, 1
0x14000fdf1  lea     r8d, ds:2[rax*4]
0x14000fdf9  jmp     short loc_14000FE1D
0x14000fdfb  mov     eax, ebx
0x14000fdfd  xor     eax, 1
0x14000fe00  lea     r8d, ds:1[rax*4]
0x14000fe08  jmp     short loc_14000FE1D
0x14000fe0a  mov     r8d, ebx
0x14000fe0d  xor     r8d, 1
0x14000fe11  shl     r8d, 2
0x14000fe15  jmp     short loc_14000FE1D
0x14000fe17  mov     r8d, 0FFh
0x14000fe1d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x14000fe22  test    eax, eax
0x14000fe24  jz      short loc_14000FE65
0x14000fe26  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14000fe2d  test    rax, rax
0x14000fe30  jz      short loc_14000FE65
0x14000fe32  mov     rdx, [rdi+10h]
0x14000fe36  lea     rcx, [rsp+58h+arg_10]
0x14000fe3b  mov     [rsp+58h+var_20], 1
0x14000fe44  mov     r9d, ebx
0x14000fe47  mov     [rsp+58h+var_28], 0
0x14000fe4c  xor     r8d, r8d
0x14000fe4f  mov     [rsp+58h+var_30], 0
0x14000fe58  mov     [rsp+58h+var_38], rcx
0x14000fe5d  mov     ecx, [rdi+18h]
0x14000fe60  call    _guard_dispatch_icall
0x14000fe65  mov     rbx, [rsp+58h+arg_0]
0x14000fe6a  add     rsp, 50h
0x14000fe6e  pop     rdi
0x14000fe6f  retn
```
