# Parser::CreateNode(OpCode,long)

- ea: `0x180030d80`
- end: `0x180030ebc`
- name: `?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@J@Z`
- size: `316`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ee0`
- `0x180030808`
- `0x18005e69c`
- `0x18005e8d0`
- `0x18005ea88`

## callees

- `0x18000b714`
- `0x180030d80`

## import_xrefs

- `msvcrt!malloc` at `0x180030e3f`
- `msvcrt!malloc` at `0x180030e71`
- `msvcrt!malloc` at `0x180030e3f`
- `msvcrt!malloc` at `0x180030e71`

## pseudocode

```c
_DWORD *__fastcall Parser::CreateNode(__int64 a1, int a2, int a3)
{
  __int64 v6; // rdi
  int v7; // r14d
  int v8; // esi
  _QWORD *v9; // rax
  _DWORD *result; // rax
  int v11; // r13d
  int v12; // eax
  int v13; // r14d
  _QWORD *v14; // rax
  _QWORD *v15; // rdx

  v6 = *((int *)qword_180080B00 + a2);
  if ( (int)v6 <= 0 )
    goto LABEL_23;
  v7 = *(_DWORD *)(a1 + 28);
  v8 = *(_DWORD *)(a1 + 24);
  if ( (int)v6 <= v7 - v8 )
  {
LABEL_3:
    *(_DWORD *)(a1 + 24) = v8 + ((v6 + 7) & 0xFFFFFFF8);
    v9 = (_QWORD *)(*(_QWORD *)(a1 + 16) + v8);
    goto LABEL_4;
  }
  v11 = *(_DWORD *)(a1 + 36);
  if ( (int)v6 < v11 )
  {
    v12 = *(_DWORD *)(a1 + 32);
    if ( v7 <= (int)v6 )
      v7 = *((_DWORD *)qword_180080B00 + a2);
    v13 = 2 * v7;
    if ( v12 <= v13 )
      v12 = v13;
    if ( v12 <= v11 )
    {
      if ( (int)v6 > v12 )
        goto LABEL_23;
      v11 = v12;
    }
    if ( v11 + 8 > v11 && v11 + 8 >= (int)v6 )
    {
      v14 = malloc(v11 + 8LL);
      if ( v14 )
      {
        v8 = 0;
        *v14 = *(_QWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 16) = v14;
        *(_DWORD *)(a1 + 28) = v11;
        goto LABEL_3;
      }
    }
LABEL_23:
    Parser::Error((Parser *)a1, 1001);
  }
  if ( (int)v6 + 8 <= (int)v6 )
    goto LABEL_23;
  v9 = malloc(v6 + 8);
  if ( !v9 )
    goto LABEL_23;
  v15 = *(_QWORD **)(a1 + 16);
  if ( v8 >= v7 )
  {
    *v9 = v15;
    *(_QWORD *)(a1 + 16) = v9;
  }
  else
  {
    *v9 = *v15;
    *v15 = v9;
  }
LABEL_4:
  result = v9 + 1;
  if ( !result )
    goto LABEL_23;
  *result = a2;
  result[1] = 0;
  result[2] = a3;
  result[3] = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 352) + 40LL) - *(_QWORD *)(*(_QWORD *)(a1 + 352) + 16LL)) >> 1;
  return result;
}

```

## disassembly

```asm
0x180030d80  push    rbx
0x180030d82  push    rbp
0x180030d83  push    rsi
0x180030d84  push    rdi
0x180030d85  push    r13
0x180030d87  push    r14
0x180030d89  push    r15
0x180030d8b  sub     rsp, 20h
0x180030d8f  movsxd  rbp, edx
0x180030d92  lea     rdi, qword_180080B00
0x180030d99  mov     r15d, r8d
0x180030d9c  mov     rbx, rcx
0x180030d9f  movsxd  rdi, dword ptr [rdi+rbp*4]
0x180030da3  test    edi, edi
0x180030da5  jle     loc_180030EAE
0x180030dab  mov     r14d, [rcx+1Ch]
0x180030daf  mov     eax, r14d
0x180030db2  mov     esi, [rcx+18h]
0x180030db5  sub     eax, esi
0x180030db7  cmp     edi, eax
0x180030db9  jg      short loc_180030E09
0x180030dbb  lea     eax, [rdi+7]
0x180030dbe  and     eax, 0FFFFFFF8h
0x180030dc1  add     eax, esi
0x180030dc3  mov     [rbx+18h], eax
0x180030dc6  movsxd  rax, esi
0x180030dc9  add     rax, [rbx+10h]
0x180030dcd  add     rax, 8
0x180030dd1  jz      loc_180030EAE
0x180030dd7  mov     [rax], ebp
0x180030dd9  mov     dword ptr [rax+4], 0
0x180030de0  mov     [rax+8], r15d
0x180030de4  mov     rcx, [rbx+160h]
0x180030deb  mov     rdx, [rcx+28h]
0x180030def  sub     rdx, [rcx+10h]
0x180030df3  sar     rdx, 1
0x180030df6  mov     [rax+0Ch], edx
0x180030df9  add     rsp, 20h
0x180030dfd  pop     r15
0x180030dff  pop     r14
0x180030e01  pop     r13
0x180030e03  pop     rdi
0x180030e04  pop     rsi
0x180030e05  pop     rbp
0x180030e06  pop     rbx
0x180030e07  retn
0x180030e09  mov     r13d, [rcx+24h]
0x180030e0d  cmp     edi, r13d
0x180030e10  jge     short loc_180030E66
0x180030e12  mov     eax, [rcx+20h]
0x180030e15  cmp     r14d, edi
0x180030e18  cmovle  r14d, edi
0x180030e1c  add     r14d, r14d
0x180030e1f  cmp     eax, r14d
0x180030e22  cmovle  eax, r14d
0x180030e26  cmp     eax, r13d
0x180030e29  jle     short loc_180030E99
0x180030e2b  lea     eax, [r13+8]
0x180030e2f  cmp     eax, r13d
0x180030e32  jl      short loc_180030EAE
0x180030e34  cmp     eax, edi
0x180030e36  jl      short loc_180030EAE
0x180030e38  movsxd  rcx, r13d
0x180030e3b  add     rcx, 8; Size
0x180030e3f  call    cs:__imp_malloc
0x180030e46  nop     dword ptr [rax+rax+00h]
0x180030e4b  test    rax, rax
0x180030e4e  jz      short loc_180030EAE
0x180030e50  mov     rcx, [rbx+10h]
0x180030e54  xor     esi, esi
0x180030e56  mov     [rax], rcx
0x180030e59  mov     [rbx+10h], rax
0x180030e5d  mov     [rbx+1Ch], r13d
0x180030e61  jmp     loc_180030DBB
0x180030e66  lea     eax, [rdi+8]
0x180030e69  cmp     eax, edi
0x180030e6b  jl      short loc_180030EAE
0x180030e6d  lea     rcx, [rdi+8]; Size
0x180030e71  call    cs:__imp_malloc
0x180030e78  nop     dword ptr [rax+rax+00h]
0x180030e7d  test    rax, rax
0x180030e80  jz      short loc_180030EAE
0x180030e82  mov     rdx, [rbx+10h]
0x180030e86  cmp     esi, r14d
0x180030e89  jge     short loc_180030EA2
0x180030e8b  mov     rcx, [rdx]
0x180030e8e  mov     [rax], rcx
0x180030e91  mov     [rdx], rax
0x180030e94  jmp     loc_180030DCD
0x180030e99  cmp     edi, eax
0x180030e9b  jg      short loc_180030EAE
0x180030e9d  mov     r13d, eax
0x180030ea0  jmp     short loc_180030E2B
0x180030ea2  mov     [rax], rdx
0x180030ea5  mov     [rbx+10h], rax
0x180030ea9  jmp     loc_180030DCD
0x180030eae  mov     edx, 3E9h; int
0x180030eb3  mov     rcx, rbx; this
0x180030eb6  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
