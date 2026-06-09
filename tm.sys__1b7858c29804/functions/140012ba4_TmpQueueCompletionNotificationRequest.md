# TmpQueueCompletionNotificationRequest

- ea: `0x140012ba4`
- end: `0x140012c15`
- name: `TmpQueueCompletionNotificationRequest`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14001c010`

## import_xrefs

- `ntoskrnl!KeInitializeApc` at `0x140012be5`
- `ntoskrnl!KeInitializeApc` at `0x140012be5`
- `ntoskrnl!KeInsertQueueApc` at `0x140012bfd`
- `ntoskrnl!KeInsertQueueApc` at `0x140012bfd`

## pseudocode

```c
__int64 __fastcall TmpQueueCompletionNotificationRequest(__int64 a1, int a2, __int64 a3, int a4)
{
  __int64 v4; // rdx
  __int64 v5; // rbx
  __int64 v7; // r8
  char v9; // [rsp+30h] [rbp-18h]

  *(_DWORD *)(a1 + 32) = a2;
  v4 = *(_QWORD *)(a1 + 48);
  v5 = a1 + 64;
  v7 = *(unsigned int *)(a1 + 152);
  v9 = 0;
  *(_DWORD *)(a1 + 36) = a4;
  KeInitializeApc(a1 + 64, v4, v7, TmpCompleteNotificationRequestApc, 0, 0, v9, 0);
  return KeInsertQueueApc(v5, a3, 0, 0);
}

```

## disassembly

```asm
0x140012ba4  mov     r11, rsp
0x140012ba7  mov     [r11+8], rbx
0x140012bab  push    rdi
0x140012bac  sub     rsp, 40h
0x140012bb0  xor     eax, eax
0x140012bb2  mov     [rcx+20h], edx
0x140012bb5  mov     rdx, [rcx+30h]
0x140012bb9  lea     rbx, [rcx+40h]
0x140012bbd  mov     [r11-10h], rax
0x140012bc1  mov     rdi, r8
0x140012bc4  mov     r8d, [rcx+98h]
0x140012bcb  mov     [rsp+48h+var_18], al
0x140012bcf  mov     [rcx+24h], r9d
0x140012bd3  lea     r9, TmpCompleteNotificationRequestApc
0x140012bda  mov     [r11-20h], rax
0x140012bde  mov     rcx, rbx
0x140012be1  mov     [r11-28h], rax
0x140012be5  call    cs:__imp_KeInitializeApc
0x140012bec  nop     dword ptr [rax+rax+00h]
0x140012bf1  xor     r9d, r9d
0x140012bf4  xor     r8d, r8d
0x140012bf7  mov     rdx, rdi
0x140012bfa  mov     rcx, rbx
0x140012bfd  call    cs:__imp_KeInsertQueueApc
0x140012c04  nop     dword ptr [rax+rax+00h]
0x140012c09  mov     rbx, [rsp+48h+arg_0]
0x140012c0e  add     rsp, 40h
0x140012c12  pop     rdi
0x140012c13  retn
```
