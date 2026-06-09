# XPartAllocateSendMessage

- ea: `0x14001270c`
- end: `0x14001278e`
- name: `XPartAllocateSendMessage`
- size: `130`
- prototype: `_QWORD *__fastcall(__int64, int, __int64 (__fastcall *)(), __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f9cc`
- `0x140010fa4`
- `0x140014198`
- `0x14002e06c`

## callees

- `0x14001270c`
- `0x140017540`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140012737`
- `ntoskrnl!ExAllocatePool2` at `0x140012737`

## pseudocode

```c
_QWORD *__fastcall XPartAllocateSendMessage(__int64 a1, int a2, __int64 (__fastcall *a3)(), __int64 a4)
{
  size_t v6; // r14
  _QWORD *result; // rax
  _QWORD *v10; // rbx

  v6 = (unsigned int)(a2 + 56);
  result = (_QWORD *)ExAllocatePool2(64, v6, 1937072726);
  v10 = result;
  if ( result )
  {
    memset(result, 0, v6);
    v10[2] = a1;
    v10[6] = v10 + 7;
    *((_DWORD *)v10 + 6) = a2;
    if ( a3 )
      v10[5] = a4;
    else
      a3 = XPartFreeSendMessageCB;
    v10[4] = a3;
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x14001270c  push    rbx
0x14001270e  push    rbp
0x14001270f  push    rsi
0x140012710  push    rdi
0x140012711  push    r14
0x140012713  push    r15
0x140012715  sub     rsp, 28h
0x140012719  lea     eax, [rdx+38h]
0x14001271c  mov     rdi, r8
0x14001271f  mov     ebp, edx
0x140012721  mov     r14d, eax
0x140012724  mov     r15, rcx
0x140012727  mov     edx, eax
0x140012729  mov     r8d, 73756256h
0x14001272f  mov     ecx, 40h ; '@'
0x140012734  mov     rsi, r9
0x140012737  call    cs:__imp_ExAllocatePool2
0x14001273e  nop     dword ptr [rax+rax+00h]
0x140012743  mov     rbx, rax
0x140012746  test    rax, rax
0x140012749  jz      short loc_140012780
0x14001274b  mov     r8, r14; Size
0x14001274e  xor     edx, edx; Val
0x140012750  mov     rcx, rbx; void *
0x140012753  call    memset
0x140012758  mov     [rbx+10h], r15
0x14001275c  lea     rax, [rbx+38h]
0x140012760  mov     [rbx+30h], rax
0x140012764  mov     [rbx+18h], ebp
0x140012767  test    rdi, rdi
0x14001276a  jz      short loc_140012772
0x14001276c  mov     [rbx+28h], rsi
0x140012770  jmp     short loc_140012779
0x140012772  lea     rdi, XPartFreeSendMessageCB
0x140012779  mov     [rbx+20h], rdi
0x14001277d  mov     rax, rbx
0x140012780  add     rsp, 28h
0x140012784  pop     r15
0x140012786  pop     r14
0x140012788  pop     rdi
0x140012789  pop     rsi
0x14001278a  pop     rbp
0x14001278b  pop     rbx
0x14001278c  retn
```
