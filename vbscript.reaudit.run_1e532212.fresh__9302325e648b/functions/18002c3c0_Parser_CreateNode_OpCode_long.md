# Parser::CreateNode(OpCode,long)

- ea: `0x18002c3c0`
- end: `0x18002c4ef`
- name: `?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@J@Z`
- size: `303`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180009da0`
- `0x18002be54`
- `0x18005cae0`
- `0x18005cd14`
- `0x18005cecc`

## callees

- `0x18000d4dc`
- `0x18002c3c0`

## import_xrefs

- `msvcrt!malloc` at `0x18002c47e`
- `msvcrt!malloc` at `0x18002c4aa`
- `msvcrt!malloc` at `0x18002c47e`
- `msvcrt!malloc` at `0x18002c4aa`

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

  v6 = *((int *)qword_18007DAC0 + a2);
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
      v7 = *((_DWORD *)qword_18007DAC0 + a2);
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
0x18002c3c0  push    rbx
0x18002c3c2  push    rbp
0x18002c3c3  push    rsi
0x18002c3c4  push    rdi
0x18002c3c5  push    r13
0x18002c3c7  push    r14
0x18002c3c9  push    r15
0x18002c3cb  sub     rsp, 20h
0x18002c3cf  movsxd  rbp, edx
0x18002c3d2  lea     rdi, qword_18007DAC0
0x18002c3d9  mov     r15d, r8d
0x18002c3dc  mov     rbx, rcx
0x18002c3df  movsxd  rdi, dword ptr [rdi+rbp*4]
0x18002c3e3  test    edi, edi
0x18002c3e5  jle     loc_18002C4E1
0x18002c3eb  mov     r14d, [rcx+1Ch]
0x18002c3ef  mov     eax, r14d
0x18002c3f2  mov     esi, [rcx+18h]
0x18002c3f5  sub     eax, esi
0x18002c3f7  cmp     edi, eax
0x18002c3f9  jg      short loc_18002C448
0x18002c3fb  lea     eax, [rdi+7]
0x18002c3fe  and     eax, 0FFFFFFF8h
0x18002c401  add     eax, esi
0x18002c403  mov     [rbx+18h], eax
0x18002c406  movsxd  rax, esi
0x18002c409  add     rax, [rbx+10h]
0x18002c40d  add     rax, 8
0x18002c411  jz      loc_18002C4E1
0x18002c417  mov     [rax], ebp
0x18002c419  mov     dword ptr [rax+4], 0
0x18002c420  mov     [rax+8], r15d
0x18002c424  mov     rcx, [rbx+160h]
0x18002c42b  mov     rdx, [rcx+28h]
0x18002c42f  sub     rdx, [rcx+10h]
0x18002c433  sar     rdx, 1
0x18002c436  mov     [rax+0Ch], edx
0x18002c439  add     rsp, 20h
0x18002c43d  pop     r15
0x18002c43f  pop     r14
0x18002c441  pop     r13
0x18002c443  pop     rdi
0x18002c444  pop     rsi
0x18002c445  pop     rbp
0x18002c446  pop     rbx
0x18002c447  retn
0x18002c448  mov     r13d, [rcx+24h]
0x18002c44c  cmp     edi, r13d
0x18002c44f  jge     short loc_18002C49F
0x18002c451  mov     eax, [rcx+20h]
0x18002c454  cmp     r14d, edi
0x18002c457  cmovle  r14d, edi
0x18002c45b  add     r14d, r14d
0x18002c45e  cmp     eax, r14d
0x18002c461  cmovle  eax, r14d
0x18002c465  cmp     eax, r13d
0x18002c468  jle     short loc_18002C4CC
0x18002c46a  lea     eax, [r13+8]
0x18002c46e  cmp     eax, r13d
0x18002c471  jl      short loc_18002C4E1
0x18002c473  cmp     eax, edi
0x18002c475  jl      short loc_18002C4E1
0x18002c477  movsxd  rcx, r13d
0x18002c47a  add     rcx, 8; Size
0x18002c47e  call    cs:__imp_malloc
0x18002c484  test    rax, rax
0x18002c487  jz      short loc_18002C4E1
0x18002c489  mov     rcx, [rbx+10h]
0x18002c48d  xor     esi, esi
0x18002c48f  mov     [rax], rcx
0x18002c492  mov     [rbx+10h], rax
0x18002c496  mov     [rbx+1Ch], r13d
0x18002c49a  jmp     loc_18002C3FB
0x18002c49f  lea     eax, [rdi+8]
0x18002c4a2  cmp     eax, edi
0x18002c4a4  jl      short loc_18002C4E1
0x18002c4a6  lea     rcx, [rdi+8]; Size
0x18002c4aa  call    cs:__imp_malloc
0x18002c4b0  test    rax, rax
0x18002c4b3  jz      short loc_18002C4E1
0x18002c4b5  mov     rdx, [rbx+10h]
0x18002c4b9  cmp     esi, r14d
0x18002c4bc  jge     short loc_18002C4D5
0x18002c4be  mov     rcx, [rdx]
0x18002c4c1  mov     [rax], rcx
0x18002c4c4  mov     [rdx], rax
0x18002c4c7  jmp     loc_18002C40D
0x18002c4cc  cmp     edi, eax
0x18002c4ce  jg      short loc_18002C4E1
0x18002c4d0  mov     r13d, eax
0x18002c4d3  jmp     short loc_18002C46A
0x18002c4d5  mov     [rax], rdx
0x18002c4d8  mov     [rbx+10h], rax
0x18002c4dc  jmp     loc_18002C40D
0x18002c4e1  mov     edx, 3E9h; int
0x18002c4e6  mov     rcx, rbx; this
0x18002c4e9  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
