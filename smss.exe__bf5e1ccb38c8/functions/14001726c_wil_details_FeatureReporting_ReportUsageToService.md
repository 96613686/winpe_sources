# wil_details_FeatureReporting_ReportUsageToService

- ea: `0x14001726c`
- end: `0x140017390`
- name: `wil_details_FeatureReporting_ReportUsageToService`
- size: `292`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400176c0`

## callees

- `0x14001726c`
- `0x140017398`
- `0x14001e010`

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
0x14001726c  mov     [rsp+arg_0], rbx
0x140017271  mov     [rsp+arg_10], r8d
0x140017276  push    rdi
0x140017277  sub     rsp, 50h
0x14001727b  mov     ebx, edx
0x14001727d  mov     r10d, r8d
0x140017280  and     ebx, 1
0x140017283  mov     rdi, rcx
0x140017286  mov     r9d, r8d
0x140017289  test    r8d, r8d
0x14001728c  jz      loc_140017337
0x140017292  sub     r9d, 1
0x140017296  jz      loc_14001732A
0x14001729c  sub     r9d, 1
0x1400172a0  jz      short loc_14001731B
0x1400172a2  sub     r9d, 1
0x1400172a6  jz      short loc_14001730C
0x1400172a8  sub     r9d, 1
0x1400172ac  jz      short loc_1400172FD
0x1400172ae  sub     r9d, 1
0x1400172b2  jz      short loc_1400172EE
0x1400172b4  cmp     r9d, 1
0x1400172b8  jz      short loc_1400172DF
0x1400172ba  sub     r10b, 64h ; 'd'
0x1400172be  cmp     r10b, 31h ; '1'
0x1400172c2  ja      short loc_140017337
0x1400172c4  mov     eax, ebx
0x1400172c6  neg     eax
0x1400172c8  movzx   eax, r10b
0x1400172cc  sbb     r8d, r8d
0x1400172cf  and     r8d, 0FFFFFFCEh
0x1400172d3  add     r8d, 96h
0x1400172da  add     r8d, eax
0x1400172dd  jmp     short loc_14001733D
0x1400172df  mov     eax, ebx
0x1400172e1  xor     eax, 1
0x1400172e4  lea     r8d, ds:9[rax*2]
0x1400172ec  jmp     short loc_14001733D
0x1400172ee  mov     eax, ebx
0x1400172f0  xor     eax, 1
0x1400172f3  lea     r8d, ds:8[rax*2]
0x1400172fb  jmp     short loc_14001733D
0x1400172fd  mov     eax, ebx
0x1400172ff  xor     eax, 1
0x140017302  lea     r8d, ds:3[rax*4]
0x14001730a  jmp     short loc_14001733D
0x14001730c  mov     eax, ebx
0x14001730e  xor     eax, 1
0x140017311  lea     r8d, ds:2[rax*4]
0x140017319  jmp     short loc_14001733D
0x14001731b  mov     eax, ebx
0x14001731d  xor     eax, 1
0x140017320  lea     r8d, ds:1[rax*4]
0x140017328  jmp     short loc_14001733D
0x14001732a  mov     r8d, ebx
0x14001732d  xor     r8d, 1
0x140017331  shl     r8d, 2
0x140017335  jmp     short loc_14001733D
0x140017337  mov     r8d, 0FFh
0x14001733d  call    wil_details_FeatureReporting_ReportUsageToServiceDirect
0x140017342  test    eax, eax
0x140017344  jz      short loc_140017385
0x140017346  mov     rax, cs:g_wil_details_pfnFeatureLoggingHook
0x14001734d  test    rax, rax
0x140017350  jz      short loc_140017385
0x140017352  mov     rdx, [rdi+10h]
0x140017356  lea     rcx, [rsp+58h+arg_10]
0x14001735b  mov     [rsp+58h+var_20], 1
0x140017364  mov     r9d, ebx
0x140017367  mov     [rsp+58h+var_28], 0
0x14001736c  xor     r8d, r8d
0x14001736f  mov     [rsp+58h+var_30], 0
0x140017378  mov     [rsp+58h+var_38], rcx
0x14001737d  mov     ecx, [rdi+18h]
0x140017380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017385  mov     rbx, [rsp+58h+arg_0]
0x14001738a  add     rsp, 50h
0x14001738e  pop     rdi
0x14001738f  retn
```
