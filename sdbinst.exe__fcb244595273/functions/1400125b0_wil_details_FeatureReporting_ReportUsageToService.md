# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x1400125b0`
- end: `0x1400126d4`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140012b60`

## callees

- `0x1400125b0`
- `0x1400126dc`
- `0x14002f010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil_details_FeatureReporting_ReportUsageToService(
        __int64 a1,
        unsigned __int64 a2,
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
0x1400125b0  mov     [rsp+arg_0], rbx
0x1400125b5  mov     [rsp+arg_10], r8d
0x1400125ba  push    rdi
0x1400125bb  sub     rsp, 50h
0x1400125bf  mov     ebx, edx
0x1400125c1  mov     r10d, r8d
0x1400125c4  and     ebx, 1
0x1400125c7  mov     rdi, rcx
0x1400125ca  mov     r9d, r8d
0x1400125cd  test    r8d, r8d
0x1400125d0  jz      loc_14001267B
0x1400125d6  sub     r9d, 1
0x1400125da  jz      loc_14001266E
0x1400125e0  sub     r9d, 1
0x1400125e4  jz      short loc_14001265F
0x1400125e6  sub     r9d, 1
0x1400125ea  jz      short loc_140012650
0x1400125ec  sub     r9d, 1
0x1400125f0  jz      short loc_140012641
0x1400125f2  sub     r9d, 1
0x1400125f6  jz      short loc_140012632
0x1400125f8  cmp     r9d, 1
0x1400125fc  jz      short loc_140012623
0x1400125fe  sub     r10b, 64h ; 'd'
0x140012602  cmp     r10b, 31h ; '1'
0x140012606  ja      short loc_14001267B
0x140012608  mov     eax, ebx
0x14001260a  neg     eax
0x14001260c  movzx   eax, r10b
0x140012610  sbb     r8d, r8d
0x140012613  and     r8d, 0FFFFFFCEh
0x140012617  add     r8d, 96h
0x14001261e  add     r8d, eax
0x140012621  jmp     short loc_140012681
0x140012623  mov     eax, ebx
0x140012625  xor     eax, 1
0x140012628  lea     r8d, ds:9[rax*2]
0x140012630  jmp     short loc_140012681
0x140012632  mov     eax, ebx
0x140012634  xor     eax, 1
0x140012637  lea     r8d, ds:8[rax*2]
0x14001263f  jmp     short loc_140012681
0x140012641  mov     eax, ebx
0x140012643  xor     eax, 1
0x140012646  lea     r8d, ds:3[rax*4]
0x14001264e  jmp     short loc_140012681
0x140012650  mov     eax, ebx
0x140012652  xor     eax, 1
0x140012655  lea     r8d, ds:2[rax*4]
0x14001265d  jmp     short loc_140012681
0x14001265f  mov     eax, ebx
0x140012661  xor     eax, 1
0x140012664  lea     r8d, ds:1[rax*4]
0x14001266c  jmp     short loc_140012681
0x14001266e  mov     r8d, ebx
0x140012671  xor     r8d, 1
0x140012675  shl     r8d, 2
0x140012679  jmp     short loc_140012681
0x14001267b  mov     r8d, 0FFh
0x140012681  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140012686  test    eax, eax
0x140012688  jz      short loc_1400126C9
0x14001268a  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x140012691  test    rax, rax
0x140012694  jz      short loc_1400126C9
0x140012696  mov     rdx, [rdi+10h]
0x14001269a  lea     rcx, [rsp+58h+arg_10]
0x14001269f  mov     [rsp+58h+var_20], 1
0x1400126a8  mov     r9d, ebx
0x1400126ab  mov     [rsp+58h+var_28], 0
0x1400126b0  xor     r8d, r8d
0x1400126b3  mov     [rsp+58h+var_30], 0
0x1400126bc  mov     [rsp+58h+var_38], rcx
0x1400126c1  mov     ecx, [rdi+18h]
0x1400126c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400126c9  mov     rbx, [rsp+58h+arg_0]
0x1400126ce  add     rsp, 50h
0x1400126d2  pop     rdi
0x1400126d3  retn
```
