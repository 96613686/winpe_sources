# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x18000b280`
- end: `0x18000b3a9`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000b830`

## callees

- `0x18000b280`
- `0x18000b3b0`
- `0x180014010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)
{
  unsigned int v6; // ebx
  int v7; // r8d
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rax
  int v9; // [rsp+70h] [rbp+18h] BYREF

  v9 = a3;
  v6 = a2 & 1;
  if ( a3 )
  {
    switch ( a3 )
    {
      case 1:
        v7 = 4 * !(a2 & 1);
        goto LABEL_17;
      case 2:
        v7 = 4 * !(a2 & 1) + 1;
        goto LABEL_17;
      case 3:
        v7 = 4 * !(a2 & 1) + 2;
        goto LABEL_17;
      case 4:
        v7 = 4 * !(a2 & 1) + 3;
        goto LABEL_17;
      case 5:
        v7 = 2 * !(a2 & 1) + 8;
        goto LABEL_17;
      case 6:
        v7 = 2 * !(a2 & 1) + 9;
        goto LABEL_17;
    }
    if ( (unsigned __int8)(a3 - 100) <= 0x31u )
    {
      v7 = (unsigned __int8)(a3 - 100) + (v6 != 0 ? 100 : 150);
      goto LABEL_17;
    }
  }
  v7 = 255;
LABEL_17:
  result = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))wil_details_FeatureReporting_ReportUsageToServiceDirect(
                                                                                                     a1,
                                                                                                     a2,
                                                                                                     v7,
                                                                                                     a4);
  if ( (_DWORD)result )
  {
    result = g_wil_details_pfnFeatureLoggingHook;
    if ( g_wil_details_pfnFeatureLoggingHook )
      return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))g_wil_details_pfnFeatureLoggingHook(*(unsigned int *)(a1 + 24), *(_QWORD *)(a1 + 16), 0, v6, &v9, 0, 0, a4);
  }
  return result;
}

```

## disassembly

```asm
0x18000b280  mov     [rsp+arg_0], rbx
0x18000b285  mov     [rsp+arg_8], rsi
0x18000b28a  mov     [rsp+arg_10], r8d
0x18000b28f  push    rdi
0x18000b290  sub     rsp, 50h
0x18000b294  mov     rdi, rcx
0x18000b297  mov     ebx, edx
0x18000b299  mov     ecx, 1
0x18000b29e  mov     rsi, r9
0x18000b2a1  and     ebx, ecx
0x18000b2a3  mov     r11d, r8d
0x18000b2a6  mov     r10d, r8d
0x18000b2a9  test    r8d, r8d
0x18000b2ac  jz      loc_18000B34B
0x18000b2b2  sub     r10d, ecx
0x18000b2b5  jz      loc_18000B33F
0x18000b2bb  sub     r10d, ecx
0x18000b2be  jz      short loc_18000B331
0x18000b2c0  sub     r10d, ecx
0x18000b2c3  jz      short loc_18000B323
0x18000b2c5  sub     r10d, ecx
0x18000b2c8  jz      short loc_18000B315
0x18000b2ca  sub     r10d, ecx
0x18000b2cd  jz      short loc_18000B307
0x18000b2cf  cmp     r10d, ecx
0x18000b2d2  jz      short loc_18000B2F9
0x18000b2d4  sub     r11b, 64h ; 'd'
0x18000b2d8  cmp     r11b, 31h ; '1'
0x18000b2dc  ja      short loc_18000B34B
0x18000b2de  mov     eax, ebx
0x18000b2e0  neg     eax
0x18000b2e2  movzx   eax, r11b
0x18000b2e6  sbb     r8d, r8d
0x18000b2e9  and     r8d, 0FFFFFFCEh
0x18000b2ed  add     r8d, 96h
0x18000b2f4  add     r8d, eax
0x18000b2f7  jmp     short loc_18000B351
0x18000b2f9  mov     eax, ebx
0x18000b2fb  xor     eax, ecx
0x18000b2fd  lea     r8d, ds:9[rax*2]
0x18000b305  jmp     short loc_18000B351
0x18000b307  mov     eax, ebx
0x18000b309  xor     eax, ecx
0x18000b30b  lea     r8d, ds:8[rax*2]
0x18000b313  jmp     short loc_18000B351
0x18000b315  mov     eax, ebx
0x18000b317  xor     eax, ecx
0x18000b319  lea     r8d, ds:3[rax*4]
0x18000b321  jmp     short loc_18000B351
0x18000b323  mov     eax, ebx
0x18000b325  xor     eax, ecx
0x18000b327  lea     r8d, ds:2[rax*4]
0x18000b32f  jmp     short loc_18000B351
0x18000b331  mov     eax, ebx
0x18000b333  xor     eax, ecx
0x18000b335  lea     r8d, ds:1[rax*4]
0x18000b33d  jmp     short loc_18000B351
0x18000b33f  mov     r8d, ebx
0x18000b342  xor     r8d, ecx
0x18000b345  shl     r8d, 2
0x18000b349  jmp     short loc_18000B351
0x18000b34b  mov     r8d, 0FFh
0x18000b351  mov     rcx, rdi
0x18000b354  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x18000b359  test    eax, eax
0x18000b35b  jz      short loc_18000B398
0x18000b35d  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x18000b364  test    rax, rax
0x18000b367  jz      short loc_18000B398
0x18000b369  mov     rdx, [rdi+10h]
0x18000b36d  lea     rcx, [rsp+58h+arg_10]
0x18000b372  mov     [rsp+58h+var_20], rsi
0x18000b377  mov     r9d, ebx
0x18000b37a  mov     [rsp+58h+var_28], 0
0x18000b37f  xor     r8d, r8d
0x18000b382  mov     [rsp+58h+var_30], 0
0x18000b38b  mov     [rsp+58h+var_38], rcx
0x18000b390  mov     ecx, [rdi+18h]
0x18000b393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b398  mov     rbx, [rsp+58h+arg_0]
0x18000b39d  mov     rsi, [rsp+58h+arg_8]
0x18000b3a2  add     rsp, 50h
0x18000b3a6  pop     rdi
0x18000b3a7  retn
```
