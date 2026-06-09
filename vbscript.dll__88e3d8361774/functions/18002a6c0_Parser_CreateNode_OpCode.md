# Parser::CreateNode(OpCode)

- ea: `0x18002a6c0`
- end: `0x18002a808`
- name: `?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z`
- size: `328`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180009da0`
- `0x18000ad80`
- `0x18000b430`
- `0x1800289a8`
- `0x180029220`
- `0x18002a3d0`
- `0x18002aaa0`
- `0x18002be54`
- `0x18005cae0`
- `0x18005cd14`

## callees

- `0x18000d4dc`
- `0x18002a6c0`

## import_xrefs

- `msvcrt!malloc` at `0x18002a796`
- `msvcrt!malloc` at `0x18002a7c3`
- `msvcrt!malloc` at `0x18002a796`
- `msvcrt!malloc` at `0x18002a7c3`

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

  v4 = *((int *)qword_18007DAC0 + a2);
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
      v6 = *((_DWORD *)qword_18007DAC0 + a2);
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
0x18002a6c0  push    rbx
0x18002a6c2  push    rbp
0x18002a6c3  push    rsi
0x18002a6c4  push    rdi
0x18002a6c5  push    r12
0x18002a6c7  push    r13
0x18002a6c9  push    r14
0x18002a6cb  push    r15
0x18002a6cd  sub     rsp, 28h
0x18002a6d1  movsxd  rbp, edx
0x18002a6d4  lea     rsi, qword_18007DAC0
0x18002a6db  mov     rbx, rcx
0x18002a6de  movsxd  rsi, dword ptr [rsi+rbp*4]
0x18002a6e2  test    esi, esi
0x18002a6e4  jle     loc_18002A7FA
0x18002a6ea  mov     rax, [rcx+160h]
0x18002a6f1  mov     r15d, [rcx+1Ch]
0x18002a6f5  mov     r14d, [rcx+18h]
0x18002a6f9  mov     rdi, [rax+20h]
0x18002a6fd  mov     r12, [rax+10h]
0x18002a701  mov     eax, r15d
0x18002a704  sub     eax, r14d
0x18002a707  cmp     esi, eax
0x18002a709  jg      short loc_18002A760
0x18002a70b  lea     eax, [rsi+7]
0x18002a70e  and     eax, 0FFFFFFF8h
0x18002a711  add     eax, r14d
0x18002a714  mov     [rbx+18h], eax
0x18002a717  movsxd  rax, r14d
0x18002a71a  add     rax, [rbx+10h]
0x18002a71e  add     rax, 8
0x18002a722  jz      loc_18002A7FA
0x18002a728  mov     [rax], ebp
0x18002a72a  sub     rdi, r12
0x18002a72d  mov     dword ptr [rax+4], 0
0x18002a734  sar     rdi, 1
0x18002a737  mov     [rax+8], edi
0x18002a73a  mov     rcx, [rbx+160h]
0x18002a741  mov     rdx, [rcx+28h]
0x18002a745  sub     rdx, [rcx+10h]
0x18002a749  sar     rdx, 1
0x18002a74c  mov     [rax+0Ch], edx
0x18002a74f  add     rsp, 28h
0x18002a753  pop     r15
0x18002a755  pop     r14
0x18002a757  pop     r13
0x18002a759  pop     r12
0x18002a75b  pop     rdi
0x18002a75c  pop     rsi
0x18002a75d  pop     rbp
0x18002a75e  pop     rbx
0x18002a75f  retn
0x18002a760  mov     r13d, [rcx+24h]
0x18002a764  cmp     esi, r13d
0x18002a767  jge     short loc_18002A7B8
0x18002a769  mov     eax, [rcx+20h]
0x18002a76c  cmp     r15d, esi
0x18002a76f  cmovle  r15d, esi
0x18002a773  add     r15d, r15d
0x18002a776  cmp     eax, r15d
0x18002a779  cmovle  eax, r15d
0x18002a77d  cmp     eax, r13d
0x18002a780  jle     short loc_18002A7E5
0x18002a782  lea     eax, [r13+8]
0x18002a786  cmp     eax, r13d
0x18002a789  jl      short loc_18002A7FA
0x18002a78b  cmp     eax, esi
0x18002a78d  jl      short loc_18002A7FA
0x18002a78f  movsxd  rcx, r13d
0x18002a792  add     rcx, 8; Size
0x18002a796  call    cs:__imp_malloc
0x18002a79c  test    rax, rax
0x18002a79f  jz      short loc_18002A7FA
0x18002a7a1  mov     rcx, [rbx+10h]
0x18002a7a5  xor     r14d, r14d
0x18002a7a8  mov     [rax], rcx
0x18002a7ab  mov     [rbx+10h], rax
0x18002a7af  mov     [rbx+1Ch], r13d
0x18002a7b3  jmp     loc_18002A70B
0x18002a7b8  lea     eax, [rsi+8]
0x18002a7bb  cmp     eax, esi
0x18002a7bd  jl      short loc_18002A7FA
0x18002a7bf  lea     rcx, [rsi+8]; Size
0x18002a7c3  call    cs:__imp_malloc
0x18002a7c9  test    rax, rax
0x18002a7cc  jz      short loc_18002A7FA
0x18002a7ce  mov     rdx, [rbx+10h]
0x18002a7d2  cmp     r14d, r15d
0x18002a7d5  jge     short loc_18002A7EE
0x18002a7d7  mov     rcx, [rdx]
0x18002a7da  mov     [rax], rcx
0x18002a7dd  mov     [rdx], rax
0x18002a7e0  jmp     loc_18002A71E
0x18002a7e5  cmp     esi, eax
0x18002a7e7  jg      short loc_18002A7FA
0x18002a7e9  mov     r13d, eax
0x18002a7ec  jmp     short loc_18002A782
0x18002a7ee  mov     [rax], rdx
0x18002a7f1  mov     [rbx+10h], rax
0x18002a7f5  jmp     loc_18002A71E
0x18002a7fa  mov     edx, 3E9h; int
0x18002a7ff  mov     rcx, rbx; this
0x18002a802  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
