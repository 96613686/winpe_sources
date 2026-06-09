# Parser::ParseStmtList(tokens,ParseNode * *,ParseNode * * *)

- ea: `0x180008b70`
- end: `0x180008ed3`
- name: `?ParseStmtList@Parser@@AEAAXW4tokens@@PEAPEAUParseNode@@PEAPEAPEAU3@@Z`
- size: `867`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180007ee0`
- `0x18002dc68`
- `0x18002e740`
- `0x18002f95c`
- `0x180030808`
- `0x1800344c8`
- `0x18005e69c`
- `0x18005e8d0`
- `0x18005ea88`

## callees

- `0x180007ee0`
- `0x180008b70`
- `0x18000a6c0`
- `0x18000b714`

## import_xrefs

- `msvcrt!malloc` at `0x180008d69`
- `msvcrt!malloc` at `0x180008df9`
- `msvcrt!malloc` at `0x180008d69`
- `msvcrt!malloc` at `0x180008df9`

## pseudocode

```c
__int64 __fastcall Parser::ParseStmtList(__int64 a1, int a2, __int64 *a3, __int64 **a4)
{
  __int64 *v4; // r12
  unsigned int v5; // ebp
  __int64 *v6; // rdi
  int v7; // esi
  __int64 result; // rax
  __int64 v10; // rbx
  int v11; // edx
  int v12; // r14d
  int v13; // edi
  __int64 v14; // rsi
  _QWORD *v15; // rax
  char *v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  unsigned __int16 *v19; // rdx
  int v20; // r15d
  int v21; // ecx
  int v22; // eax
  int v23; // eax
  _QWORD *v24; // rax
  _QWORD *v25; // rcx

  v4 = 0;
  *a3 = 0;
  v5 = 0;
  v6 = a3;
  v7 = a2;
LABEL_2:
  result = (__int64)Parser::ParseStatement((HashTbl **)a1);
  v10 = result;
  if ( !result )
    goto LABEL_5;
  if ( !v4 )
  {
    *v6 = result;
    v4 = v6;
    goto LABEL_5;
  }
  v12 = *(_DWORD *)(a1 + 28);
  v13 = *(_DWORD *)(a1 + 24);
  v14 = *v4;
  if ( v12 - v13 < 40 )
  {
    v20 = *(_DWORD *)(a1 + 36);
    if ( v20 <= 40 )
    {
      v15 = malloc(0x30u);
      if ( !v15 )
        goto LABEL_52;
      v25 = *(_QWORD **)(a1 + 16);
      if ( v13 >= v12 )
      {
        *v15 = v25;
        *(_QWORD *)(a1 + 16) = v15;
      }
      else
      {
        *v15 = *v25;
        **(_QWORD **)(a1 + 16) = v15;
      }
      goto LABEL_23;
    }
    v21 = *(_DWORD *)(a1 + 32);
    v22 = 40;
    if ( v12 > 40 )
      v22 = *(_DWORD *)(a1 + 28);
    v23 = 2 * v22;
    if ( v21 <= v23 )
      v21 = v23;
    if ( v21 <= v20 )
    {
      if ( v21 < 40 )
        goto LABEL_52;
      v20 = v21;
    }
    if ( v20 + 8 <= v20 || v20 + 8 < 40 || (v24 = malloc((unsigned int)v20 + 8LL)) == 0 )
LABEL_52:
      Parser::Error((Parser *)a1, 1001);
    *v24 = *(_QWORD *)(a1 + 16);
    v13 = 0;
    *(_DWORD *)(a1 + 28) = v20;
    *(_QWORD *)(a1 + 16) = v24;
  }
  *(_DWORD *)(a1 + 24) = v13 + 40;
  v15 = (_QWORD *)(*(_QWORD *)(a1 + 16) + v13);
LABEL_23:
  v16 = (char *)(v15 + 1);
  if ( v15 == (_QWORD *)-8LL )
    goto LABEL_52;
  *(_QWORD *)v16 = 43;
  v15[3] = 0;
  v15[4] = v14;
  v15[5] = v10;
  if ( v14 )
  {
    result = *(unsigned int *)(v14 + 8);
    *((_DWORD *)v16 + 2) = result;
    LODWORD(v17) = *(_DWORD *)(v10 + 12);
  }
  else
  {
    *((_DWORD *)v15 + 4) = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 352) + 32LL)
                                   - *(_QWORD *)(*(_QWORD *)(a1 + 352) + 16LL)) >> 1;
    result = *(_QWORD *)(a1 + 352);
    v17 = (__int64)(*(_QWORD *)(result + 40) - *(_QWORD *)(result + 16)) >> 1;
  }
  *((_DWORD *)v16 + 3) = v17;
  v6 = a3;
  v7 = a2;
  *v4 = (__int64)v16;
  v4 = (__int64 *)(v16 + 32);
  while ( 1 )
  {
LABEL_5:
    v11 = *(_DWORD *)(a1 + 336);
    if ( v11 != 183 )
    {
      LODWORD(result) = v11 - 52;
      result = (int)result;
      switch ( v11 )
      {
        case 52:
        case 53:
          goto LABEL_16;
        case 55:
          if ( v7 != 13 && v7 != 53 )
            goto LABEL_7;
LABEL_16:
          if ( !*(_DWORD *)(a1 + 484) && v5 )
            Parser::Error((Parser *)a1, 1042);
          goto LABEL_18;
        case 116:
        case 156:
          v18 = *(_QWORD *)(a1 + 352);
          do
          {
            v19 = *(unsigned __int16 **)(v18 + 40);
            result = *v19;
            *(_QWORD *)(v18 + 40) = v19 + 1;
          }
          while ( (_WORD)result && (_WORD)result != 13 && (_WORD)result != 10 );
          *(_QWORD *)(v18 + 40) = v19;
          goto LABEL_11;
        case 158:
          Scanner::Scan(*(_QWORD *)(a1 + 352));
          result = 0;
          if ( v7 != 13 )
            result = v5;
          v5 = result;
          continue;
        default:
          result = (unsigned int)(v11 - 52);
LABEL_7:
          if ( v11 == v7 || v11 == 184 )
            goto LABEL_18;
          v5 = 1;
          break;
      }
      goto LABEL_2;
    }
LABEL_11:
    if ( *(_DWORD *)(a1 + 484) )
      break;
    v5 = 0;
    result = Scanner::Scan(*(_QWORD *)(a1 + 352));
  }
LABEL_18:
  if ( a4 )
    *a4 = v4;
  return result;
}

```

## disassembly

```asm
0x180008b70  mov     [rsp+arg_0], rbx
0x180008b75  mov     [rsp+arg_18], r9
0x180008b7a  mov     [rsp+arg_10], r8
0x180008b7f  mov     [rsp+arg_8], edx
0x180008b83  push    rbp
0x180008b84  push    rsi
0x180008b85  push    rdi
0x180008b86  push    r12
0x180008b88  push    r13
0x180008b8a  push    r14
0x180008b8c  push    r15
0x180008b8e  sub     rsp, 20h
0x180008b92  xor     r14d, r14d
0x180008b95  lea     r15, __ImageBase
0x180008b9c  mov     r12d, r14d
0x180008b9f  mov     [r8], r14
0x180008ba2  mov     ebp, r14d
0x180008ba5  mov     rdi, r8
0x180008ba8  mov     esi, edx
0x180008baa  mov     r13, rcx
0x180008bad  mov     rcx, r13; this
0x180008bb0  call    ?ParseStatement@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseStatement(void)
0x180008bb5  mov     rbx, rax
0x180008bb8  test    rax, rax
0x180008bbb  jz      short loc_180008BD0
0x180008bbd  test    r12, r12
0x180008bc0  jnz     loc_180008C74
0x180008bc6  mov     [rdi], rax
0x180008bc9  mov     r12, rdi
0x180008bcc  nop     dword ptr [rax+00h]
0x180008bd0  mov     edx, [r13+150h]
0x180008bd7  cmp     edx, 0B7h
0x180008bdd  jz      short loc_180008BFE
0x180008bdf  lea     eax, [rdx-34h]; switch 107 cases
0x180008be2  cmp     eax, 6Ah
0x180008be5  jbe     short loc_180008C19
0x180008be7  cmp     edx, esi; jumptable 0000000180008C2F default case, cases 54,56-115,117-155,157
0x180008be9  jz      short loc_180008C51
0x180008beb  cmp     edx, 0B8h
0x180008bf1  jz      short loc_180008C51
0x180008bf3  mov     ebp, 1
0x180008bf8  jmp     short loc_180008BAD
0x180008bfa  mov     [r8+28h], rdx
0x180008bfe  cmp     dword ptr [r13+1E4h], 0
0x180008c06  jnz     short loc_180008C51
0x180008c08  mov     rcx, [r13+160h]
0x180008c0f  mov     ebp, r14d
0x180008c12  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180008c17  jmp     short loc_180008BD0
0x180008c19  cdqe
0x180008c1b  movzx   eax, ds:(byte_180008E68 - 180000000h)[r15+rax]
0x180008c24  mov     ecx, ds:(jpt_180008C2F - 180000000h)[r15+rax*4]
0x180008c2c  add     rcx, r15
0x180008c2f  jmp     rcx; switch jump
0x180008c35  cmp     esi, 0Dh; jumptable 0000000180008C2F case 55
0x180008c38  jz      short loc_180008C3F; jumptable 0000000180008C2F cases 52,53
0x180008c3a  cmp     esi, 35h ; '5'
0x180008c3d  jnz     short def_180008C2F; jumptable 0000000180008C2F default case, cases 54,56-115,117-155,157
0x180008c3f  cmp     dword ptr [r13+1E4h], 0; jumptable 0000000180008C2F cases 52,53
0x180008c47  jnz     short loc_180008C51
0x180008c49  test    ebp, ebp
0x180008c4b  jnz     loc_180008E46
0x180008c51  mov     r14, [rsp+58h+arg_18]
0x180008c56  test    r14, r14
0x180008c59  jz      short loc_180008C5E
0x180008c5b  mov     [r14], r12
0x180008c5e  mov     rbx, [rsp+58h+arg_0]
0x180008c63  add     rsp, 20h
0x180008c67  pop     r15
0x180008c69  pop     r14
0x180008c6b  pop     r13
0x180008c6d  pop     r12
0x180008c6f  pop     rdi
0x180008c70  pop     rsi
0x180008c71  pop     rbp
0x180008c72  retn
0x180008c74  mov     r14d, [r13+1Ch]
0x180008c78  mov     eax, r14d
0x180008c7b  mov     edi, [r13+18h]
0x180008c7f  sub     eax, edi
0x180008c81  mov     rsi, [r12]
0x180008c85  cmp     eax, 28h ; '('
0x180008c88  jl      loc_180008D1E
0x180008c8e  xor     r14d, r14d
0x180008c91  lea     eax, [rdi+28h]
0x180008c94  mov     [r13+18h], eax
0x180008c98  movsxd  rax, edi
0x180008c9b  add     rax, [r13+10h]
0x180008c9f  lea     rdx, [rax+8]
0x180008ca3  test    rdx, rdx
0x180008ca6  jz      loc_180008E38
0x180008cac  mov     qword ptr [rdx], 2Bh ; '+'
0x180008cb3  mov     [rdx+10h], r14
0x180008cb7  mov     [rdx+18h], rsi
0x180008cbb  mov     [rdx+20h], rbx
0x180008cbf  test    rsi, rsi
0x180008cc2  jz      loc_180008DBB
0x180008cc8  mov     eax, [rsi+8]
0x180008ccb  mov     [rdx+8], eax
0x180008cce  mov     ecx, [rbx+0Ch]
0x180008cd1  mov     [rdx+0Ch], ecx
0x180008cd4  mov     rdi, [rsp+58h+arg_10]
0x180008cd9  mov     esi, [rsp+58h+arg_8]
0x180008cdd  mov     [r12], rdx
0x180008ce1  lea     r12, [rdx+20h]
0x180008ce5  jmp     loc_180008BD0
0x180008cea  mov     r8, [r13+160h]; jumptable 0000000180008C2F cases 116,156
0x180008cf1  mov     rdx, [r8+28h]
0x180008cf5  movzx   eax, word ptr [rdx]
0x180008cf8  lea     rcx, [rdx+2]
0x180008cfc  mov     [r8+28h], rcx
0x180008d00  test    ax, ax
0x180008d03  jz      loc_180008BFA
0x180008d09  cmp     ax, 0Dh
0x180008d0d  jz      loc_180008BFA
0x180008d13  cmp     ax, 0Ah
0x180008d17  jnz     short loc_180008CF1
0x180008d19  jmp     loc_180008BFA
0x180008d1e  mov     r15d, [r13+24h]
0x180008d22  cmp     r15d, 28h ; '('
0x180008d26  jle     loc_180008DF4
0x180008d2c  mov     ecx, [r13+20h]
0x180008d30  mov     eax, 28h ; '('
0x180008d35  cmp     r14d, eax
0x180008d38  cmovg   eax, r14d
0x180008d3c  add     eax, eax
0x180008d3e  cmp     ecx, eax
0x180008d40  cmovle  ecx, eax
0x180008d43  cmp     ecx, r15d
0x180008d46  jle     loc_180008DE7
0x180008d4c  lea     eax, [r15+8]
0x180008d50  cmp     eax, r15d
0x180008d53  jl      loc_180008E38
0x180008d59  cmp     eax, 28h ; '('
0x180008d5c  jl      loc_180008E38
0x180008d62  mov     ecx, r15d
0x180008d65  add     rcx, 8; Size
0x180008d69  call    cs:__imp_malloc
0x180008d70  nop     dword ptr [rax+rax+00h]
0x180008d75  test    rax, rax
0x180008d78  jz      loc_180008E38
0x180008d7e  mov     rcx, [r13+10h]
0x180008d82  xor     r14d, r14d
0x180008d85  mov     [rax], rcx
0x180008d88  mov     edi, r14d
0x180008d8b  mov     [r13+1Ch], r15d
0x180008d8f  lea     r15, __ImageBase
0x180008d96  mov     [r13+10h], rax
0x180008d9a  jmp     loc_180008C91
0x180008d9f  mov     rcx, [r13+160h]; jumptable 0000000180008C2F case 158
0x180008da6  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180008dab  cmp     esi, 0Dh
0x180008dae  mov     eax, r14d
0x180008db1  cmovnz  eax, ebp
0x180008db4  mov     ebp, eax
0x180008db6  jmp     loc_180008BD0
0x180008dbb  mov     rax, [r13+160h]
0x180008dc2  mov     rcx, [rax+20h]
0x180008dc6  sub     rcx, [rax+10h]
0x180008dca  sar     rcx, 1
0x180008dcd  mov     [rdx+8], ecx
0x180008dd0  mov     rax, [r13+160h]
0x180008dd7  mov     rcx, [rax+28h]
0x180008ddb  sub     rcx, [rax+10h]
0x180008ddf  sar     rcx, 1
0x180008de2  jmp     loc_180008CD1
0x180008de7  cmp     ecx, 28h ; '('
0x180008dea  jl      short loc_180008E38
0x180008dec  mov     r15d, ecx
0x180008def  jmp     loc_180008D4C
0x180008df4  mov     ecx, 30h ; '0'; Size
0x180008df9  call    cs:__imp_malloc
0x180008e00  nop     dword ptr [rax+rax+00h]
0x180008e05  test    rax, rax
0x180008e08  jz      short loc_180008E38
0x180008e0a  mov     rcx, [r13+10h]
0x180008e0e  cmp     edi, r14d
0x180008e11  jge     short loc_180008E22
0x180008e13  mov     rcx, [rcx]
0x180008e16  mov     [rax], rcx
0x180008e19  mov     rcx, [r13+10h]
0x180008e1d  mov     [rcx], rax
0x180008e20  jmp     short loc_180008E29
0x180008e22  mov     [rax], rcx
0x180008e25  mov     [r13+10h], rax
0x180008e29  xor     r14d, r14d
0x180008e2c  lea     r15, __ImageBase
0x180008e33  jmp     loc_180008C9F
0x180008e38  mov     edx, 3E9h; int
0x180008e3d  mov     rcx, r13; this
0x180008e40  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x180008e46  mov     edx, 412h; int
0x180008e4b  mov     rcx, r13; this
0x180008e4e  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
