# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x180015950`
- end: `0x180015a74`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64, int))(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180015de8`

## callees

- `0x180015950`
- `0x180015a7c`
- `0x180019010`

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
0x180015950  mov     [rsp+arg_0], rbx
0x180015955  mov     [rsp+arg_10], r8d
0x18001595a  push    rdi
0x18001595b  sub     rsp, 50h
0x18001595f  mov     ebx, edx
0x180015961  mov     r10d, r8d
0x180015964  and     ebx, 1
0x180015967  mov     rdi, rcx
0x18001596a  mov     r9d, r8d
0x18001596d  test    r8d, r8d
0x180015970  jz      loc_180015A1B
0x180015976  sub     r9d, 1
0x18001597a  jz      loc_180015A0E
0x180015980  sub     r9d, 1
0x180015984  jz      short loc_1800159FF
0x180015986  sub     r9d, 1
0x18001598a  jz      short loc_1800159F0
0x18001598c  sub     r9d, 1
0x180015990  jz      short loc_1800159E1
0x180015992  sub     r9d, 1
0x180015996  jz      short loc_1800159D2
0x180015998  cmp     r9d, 1
0x18001599c  jz      short loc_1800159C3
0x18001599e  sub     r10b, 64h ; 'd'
0x1800159a2  cmp     r10b, 31h ; '1'
0x1800159a6  ja      short loc_180015A1B
0x1800159a8  mov     eax, ebx
0x1800159aa  neg     eax
0x1800159ac  movzx   eax, r10b
0x1800159b0  sbb     r8d, r8d
0x1800159b3  and     r8d, 0FFFFFFCEh
0x1800159b7  add     r8d, 96h
0x1800159be  add     r8d, eax
0x1800159c1  jmp     short loc_180015A21
0x1800159c3  mov     eax, ebx
0x1800159c5  xor     eax, 1
0x1800159c8  lea     r8d, ds:9[rax*2]
0x1800159d0  jmp     short loc_180015A21
0x1800159d2  mov     eax, ebx
0x1800159d4  xor     eax, 1
0x1800159d7  lea     r8d, ds:8[rax*2]
0x1800159df  jmp     short loc_180015A21
0x1800159e1  mov     eax, ebx
0x1800159e3  xor     eax, 1
0x1800159e6  lea     r8d, ds:3[rax*4]
0x1800159ee  jmp     short loc_180015A21
0x1800159f0  mov     eax, ebx
0x1800159f2  xor     eax, 1
0x1800159f5  lea     r8d, ds:2[rax*4]
0x1800159fd  jmp     short loc_180015A21
0x1800159ff  mov     eax, ebx
0x180015a01  xor     eax, 1
0x180015a04  lea     r8d, ds:1[rax*4]
0x180015a0c  jmp     short loc_180015A21
0x180015a0e  mov     r8d, ebx
0x180015a11  xor     r8d, 1
0x180015a15  shl     r8d, 2
0x180015a19  jmp     short loc_180015A21
0x180015a1b  mov     r8d, 0FFh
0x180015a21  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x180015a26  test    eax, eax
0x180015a28  jz      short loc_180015A69
0x180015a2a  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x180015a31  test    rax, rax
0x180015a34  jz      short loc_180015A69
0x180015a36  mov     rdx, [rdi+10h]
0x180015a3a  lea     rcx, [rsp+58h+arg_10]
0x180015a3f  mov     [rsp+58h+var_20], 1
0x180015a48  mov     r9d, ebx
0x180015a4b  mov     [rsp+58h+var_28], 0
0x180015a50  xor     r8d, r8d
0x180015a53  mov     [rsp+58h+var_30], 0
0x180015a5c  mov     [rsp+58h+var_38], rcx
0x180015a61  mov     ecx, [rdi+18h]
0x180015a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a69  mov     rbx, [rsp+58h+arg_0]
0x180015a6e  add     rsp, 50h
0x180015a72  pop     rdi
0x180015a73  retn
```
