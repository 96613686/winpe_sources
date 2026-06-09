# Parser::CreateNode(OpCode)

- ea: `0x18002fc50`
- end: `0x18002fda5`
- name: `?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z`
- size: `341`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ee0`
- `0x180008ee0`
- `0x1800095c0`
- `0x18002dea8`
- `0x18002e740`
- `0x18002f95c`
- `0x180030050`
- `0x180030808`
- `0x18005e69c`
- `0x18005e8d0`

## callees

- `0x18000b714`
- `0x18002fc50`

## import_xrefs

- `msvcrt!malloc` at `0x18002fd27`
- `msvcrt!malloc` at `0x18002fd5a`
- `msvcrt!malloc` at `0x18002fd27`
- `msvcrt!malloc` at `0x18002fd5a`

## pseudocode

```c
_DWORD *__fastcall Parser::CreateNode(__int64 a1, int a2)
{
  __int64 v4; // rsi
  __int64 v5; // rax
  int v6; // r15d
  int v7; // r14d
  __int64 v8; // rdi
  __int64 v9; // r12
  _QWORD *v10; // rax
  _DWORD *result; // rax
  int v12; // r13d
  int v13; // eax
  int v14; // r15d
  _QWORD *v15; // rax
  _QWORD *v16; // rdx

  v4 = *((int *)qword_180080B00 + a2);
  if ( (int)v4 <= 0 )
    goto LABEL_23;
  v5 = *(_QWORD *)(a1 + 352);
  v6 = *(_DWORD *)(a1 + 28);
  v7 = *(_DWORD *)(a1 + 24);
  v8 = *(_QWORD *)(v5 + 32);
  v9 = *(_QWORD *)(v5 + 16);
  if ( (int)v4 <= v6 - v7 )
  {
LABEL_3:
    *(_DWORD *)(a1 + 24) = v7 + ((v4 + 7) & 0xFFFFFFF8);
    v10 = (_QWORD *)(*(_QWORD *)(a1 + 16) + v7);
    goto LABEL_4;
  }
  v12 = *(_DWORD *)(a1 + 36);
  if ( (int)v4 < v12 )
  {
    v13 = *(_DWORD *)(a1 + 32);
    if ( v6 <= (int)v4 )
      v6 = *((_DWORD *)qword_180080B00 + a2);
    v14 = 2 * v6;
    if ( v13 <= v14 )
      v13 = v14;
    if ( v13 <= v12 )
    {
      if ( (int)v4 > v13 )
        goto LABEL_23;
      v12 = v13;
    }
    if ( v12 + 8 > v12 && v12 + 8 >= (int)v4 )
    {
      v15 = malloc(v12 + 8LL);
      if ( v15 )
      {
        v7 = 0;
        *v15 = *(_QWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 16) = v15;
        *(_DWORD *)(a1 + 28) = v12;
        goto LABEL_3;
      }
    }
LABEL_23:
    Parser::Error((Parser *)a1, 1001);
  }
  if ( (int)v4 + 8 <= (int)v4 )
    goto LABEL_23;
  v10 = malloc(v4 + 8);
  if ( !v10 )
    goto LABEL_23;
  v16 = *(_QWORD **)(a1 + 16);
  if ( v7 >= v6 )
  {
    *v10 = v16;
    *(_QWORD *)(a1 + 16) = v10;
  }
  else
  {
    *v10 = *v16;
    *v16 = v10;
  }
LABEL_4:
  result = v10 + 1;
  if ( !result )
    goto LABEL_23;
  *result = a2;
  result[1] = 0;
  result[2] = (v8 - v9) >> 1;
  result[3] = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 352) + 40LL) - *(_QWORD *)(*(_QWORD *)(a1 + 352) + 16LL)) >> 1;
  return result;
}

```

## disassembly

```asm
0x18002fc50  push    rbx
0x18002fc52  push    rbp
0x18002fc53  push    rsi
0x18002fc54  push    rdi
0x18002fc55  push    r12
0x18002fc57  push    r13
0x18002fc59  push    r14
0x18002fc5b  push    r15
0x18002fc5d  sub     rsp, 28h
0x18002fc61  movsxd  rbp, edx
0x18002fc64  lea     rsi, qword_180080B00
0x18002fc6b  mov     rbx, rcx
0x18002fc6e  movsxd  rsi, dword ptr [rsi+rbp*4]
0x18002fc72  test    esi, esi
0x18002fc74  jle     loc_18002FD97
0x18002fc7a  mov     rax, [rcx+160h]
0x18002fc81  mov     r15d, [rcx+1Ch]
0x18002fc85  mov     r14d, [rcx+18h]
0x18002fc89  mov     rdi, [rax+20h]
0x18002fc8d  mov     r12, [rax+10h]
0x18002fc91  mov     eax, r15d
0x18002fc94  sub     eax, r14d
0x18002fc97  cmp     esi, eax
0x18002fc99  jg      short loc_18002FCF1
0x18002fc9b  lea     eax, [rsi+7]
0x18002fc9e  and     eax, 0FFFFFFF8h
0x18002fca1  add     eax, r14d
0x18002fca4  mov     [rbx+18h], eax
0x18002fca7  movsxd  rax, r14d
0x18002fcaa  add     rax, [rbx+10h]
0x18002fcae  add     rax, 8
0x18002fcb2  jz      loc_18002FD97
0x18002fcb8  mov     [rax], ebp
0x18002fcba  sub     rdi, r12
0x18002fcbd  mov     dword ptr [rax+4], 0
0x18002fcc4  sar     rdi, 1
0x18002fcc7  mov     [rax+8], edi
0x18002fcca  mov     rcx, [rbx+160h]
0x18002fcd1  mov     rdx, [rcx+28h]
0x18002fcd5  sub     rdx, [rcx+10h]
0x18002fcd9  sar     rdx, 1
0x18002fcdc  mov     [rax+0Ch], edx
0x18002fcdf  add     rsp, 28h
0x18002fce3  pop     r15
0x18002fce5  pop     r14
0x18002fce7  pop     r13
0x18002fce9  pop     r12
0x18002fceb  pop     rdi
0x18002fcec  pop     rsi
0x18002fced  pop     rbp
0x18002fcee  pop     rbx
0x18002fcef  retn
0x18002fcf1  mov     r13d, [rcx+24h]
0x18002fcf5  cmp     esi, r13d
0x18002fcf8  jge     short loc_18002FD4F
0x18002fcfa  mov     eax, [rcx+20h]
0x18002fcfd  cmp     r15d, esi
0x18002fd00  cmovle  r15d, esi
0x18002fd04  add     r15d, r15d
0x18002fd07  cmp     eax, r15d
0x18002fd0a  cmovle  eax, r15d
0x18002fd0e  cmp     eax, r13d
0x18002fd11  jle     short loc_18002FD82
0x18002fd13  lea     eax, [r13+8]
0x18002fd17  cmp     eax, r13d
0x18002fd1a  jl      short loc_18002FD97
0x18002fd1c  cmp     eax, esi
0x18002fd1e  jl      short loc_18002FD97
0x18002fd20  movsxd  rcx, r13d
0x18002fd23  add     rcx, 8; Size
0x18002fd27  call    cs:__imp_malloc
0x18002fd2e  nop     dword ptr [rax+rax+00h]
0x18002fd33  test    rax, rax
0x18002fd36  jz      short loc_18002FD97
0x18002fd38  mov     rcx, [rbx+10h]
0x18002fd3c  xor     r14d, r14d
0x18002fd3f  mov     [rax], rcx
0x18002fd42  mov     [rbx+10h], rax
0x18002fd46  mov     [rbx+1Ch], r13d
0x18002fd4a  jmp     loc_18002FC9B
0x18002fd4f  lea     eax, [rsi+8]
0x18002fd52  cmp     eax, esi
0x18002fd54  jl      short loc_18002FD97
0x18002fd56  lea     rcx, [rsi+8]; Size
0x18002fd5a  call    cs:__imp_malloc
0x18002fd61  nop     dword ptr [rax+rax+00h]
0x18002fd66  test    rax, rax
0x18002fd69  jz      short loc_18002FD97
0x18002fd6b  mov     rdx, [rbx+10h]
0x18002fd6f  cmp     r14d, r15d
0x18002fd72  jge     short loc_18002FD8B
0x18002fd74  mov     rcx, [rdx]
0x18002fd77  mov     [rax], rcx
0x18002fd7a  mov     [rdx], rax
0x18002fd7d  jmp     loc_18002FCAE
0x18002fd82  cmp     esi, eax
0x18002fd84  jg      short loc_18002FD97
0x18002fd86  mov     r13d, eax
0x18002fd89  jmp     short loc_18002FD13
0x18002fd8b  mov     [rax], rdx
0x18002fd8e  mov     [rbx+10h], rax
0x18002fd92  jmp     loc_18002FCAE
0x18002fd97  mov     edx, 3E9h; int
0x18002fd9c  mov     rcx, rbx; this
0x18002fd9f  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
