# Parser::ParseStmtList(tokens,ParseNode * *,ParseNode * * *)

- ea: `0x18000aa20`
- end: `0x18000ad77`
- name: `?ParseStmtList@Parser@@AEAAXW4tokens@@PEAPEAUParseNode@@PEAPEAPEAU3@@Z`
- size: `855`
- prototype: ``
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180009da0`
- `0x180028768`
- `0x180029220`
- `0x18002a3d0`
- `0x18002be54`
- `0x18002f674`
- `0x18005cae0`
- `0x18005cd14`
- `0x18005cecc`

## callees

- `0x180009da0`
- `0x18000aa20`
- `0x18000c4b0`
- `0x18000d4dc`

## import_xrefs

- `msvcrt!malloc` at `0x18000ac18`
- `msvcrt!malloc` at `0x18000aca2`
- `msvcrt!malloc` at `0x18000ac18`
- `msvcrt!malloc` at `0x18000aca2`

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
0x18000aa20  mov     [rsp+arg_0], rbx
0x18000aa25  mov     [rsp+arg_18], r9
0x18000aa2a  mov     [rsp+arg_10], r8
0x18000aa2f  mov     [rsp+arg_8], edx
0x18000aa33  push    rbp
0x18000aa34  push    rsi
0x18000aa35  push    rdi
0x18000aa36  push    r12
0x18000aa38  push    r13
0x18000aa3a  push    r14
0x18000aa3c  push    r15
0x18000aa3e  sub     rsp, 20h
0x18000aa42  xor     r14d, r14d
0x18000aa45  lea     r15, __ImageBase
0x18000aa4c  mov     r12d, r14d
0x18000aa4f  mov     [r8], r14
0x18000aa52  mov     ebp, r14d
0x18000aa55  mov     rdi, r8
0x18000aa58  mov     esi, edx
0x18000aa5a  mov     r13, rcx
0x18000aa5d  mov     rcx, r13; this
0x18000aa60  call    ?ParseStatement@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseStatement(void)
0x18000aa65  mov     rbx, rax
0x18000aa68  test    rax, rax
0x18000aa6b  jz      short loc_18000AA80
0x18000aa6d  test    r12, r12
0x18000aa70  jnz     loc_18000AB1F
0x18000aa76  mov     [rdi], rax
0x18000aa79  mov     r12, rdi
0x18000aa7c  nop     dword ptr [rax+00h]
0x18000aa80  mov     edx, [r13+150h]
0x18000aa87  cmp     edx, 0B7h
0x18000aa8d  jz      short loc_18000AAAE
0x18000aa8f  lea     eax, [rdx-34h]; switch 107 cases
0x18000aa92  cmp     eax, 6Ah
0x18000aa95  jbe     short loc_18000AAC9
0x18000aa97  cmp     edx, esi; jumptable 000000018000AADF default case, cases 54,56-115,117-155,157
0x18000aa99  jz      short loc_18000AAFD
0x18000aa9b  cmp     edx, 0B8h
0x18000aaa1  jz      short loc_18000AAFD
0x18000aaa3  mov     ebp, 1
0x18000aaa8  jmp     short loc_18000AA5D
0x18000aaaa  mov     [r8+28h], rdx
0x18000aaae  cmp     dword ptr [r13+1E4h], 0
0x18000aab6  jnz     short loc_18000AAFD
0x18000aab8  mov     rcx, [r13+160h]
0x18000aabf  mov     ebp, r14d
0x18000aac2  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000aac7  jmp     short loc_18000AA80
0x18000aac9  cdqe
0x18000aacb  movzx   eax, ds:(byte_18000AD0C - 180000000h)[r15+rax]
0x18000aad4  mov     ecx, ds:(jpt_18000AADF - 180000000h)[r15+rax*4]
0x18000aadc  add     rcx, r15
0x18000aadf  jmp     rcx; switch jump
0x18000aae1  cmp     esi, 0Dh; jumptable 000000018000AADF case 55
0x18000aae4  jz      short loc_18000AAEB; jumptable 000000018000AADF cases 52,53
0x18000aae6  cmp     esi, 35h ; '5'
0x18000aae9  jnz     short def_18000AADF; jumptable 000000018000AADF default case, cases 54,56-115,117-155,157
0x18000aaeb  cmp     dword ptr [r13+1E4h], 0; jumptable 000000018000AADF cases 52,53
0x18000aaf3  jnz     short loc_18000AAFD
0x18000aaf5  test    ebp, ebp
0x18000aaf7  jnz     loc_18000ACE9
0x18000aafd  mov     r14, [rsp+58h+arg_18]
0x18000ab02  test    r14, r14
0x18000ab05  jz      short loc_18000AB0A
0x18000ab07  mov     [r14], r12
0x18000ab0a  mov     rbx, [rsp+58h+arg_0]
0x18000ab0f  add     rsp, 20h
0x18000ab13  pop     r15
0x18000ab15  pop     r14
0x18000ab17  pop     r13
0x18000ab19  pop     r12
0x18000ab1b  pop     rdi
0x18000ab1c  pop     rsi
0x18000ab1d  pop     rbp
0x18000ab1e  retn
0x18000ab1f  mov     r14d, [r13+1Ch]
0x18000ab23  mov     eax, r14d
0x18000ab26  mov     edi, [r13+18h]
0x18000ab2a  sub     eax, edi
0x18000ab2c  mov     rsi, [r12]
0x18000ab30  cmp     eax, 28h ; '('
0x18000ab33  jl      loc_18000ABCD
0x18000ab39  xor     r14d, r14d
0x18000ab3c  lea     eax, [rdi+28h]
0x18000ab3f  mov     [r13+18h], eax
0x18000ab43  movsxd  rax, edi
0x18000ab46  add     rax, [r13+10h]
0x18000ab4a  lea     rdx, [rax+8]
0x18000ab4e  test    rdx, rdx
0x18000ab51  jz      loc_18000ACDB
0x18000ab57  mov     qword ptr [rdx], 2Bh ; '+'
0x18000ab5e  mov     [rdx+10h], r14
0x18000ab62  mov     [rdx+18h], rsi
0x18000ab66  mov     [rdx+20h], rbx
0x18000ab6a  test    rsi, rsi
0x18000ab6d  jz      loc_18000AC64
0x18000ab73  mov     eax, [rsi+8]
0x18000ab76  mov     [rdx+8], eax
0x18000ab79  mov     ecx, [rbx+0Ch]
0x18000ab7c  mov     [rdx+0Ch], ecx
0x18000ab7f  mov     rdi, [rsp+58h+arg_10]
0x18000ab84  mov     esi, [rsp+58h+arg_8]
0x18000ab88  mov     [r12], rdx
0x18000ab8c  lea     r12, [rdx+20h]
0x18000ab90  jmp     loc_18000AA80
0x18000ab95  mov     r8, [r13+160h]; jumptable 000000018000AADF cases 116,156
0x18000ab9c  nop     dword ptr [rax+00h]
0x18000aba0  mov     rdx, [r8+28h]
0x18000aba4  movzx   eax, word ptr [rdx]
0x18000aba7  lea     rcx, [rdx+2]
0x18000abab  mov     [r8+28h], rcx
0x18000abaf  test    ax, ax
0x18000abb2  jz      loc_18000AAAA
0x18000abb8  cmp     ax, 0Dh
0x18000abbc  jz      loc_18000AAAA
0x18000abc2  cmp     ax, 0Ah
0x18000abc6  jnz     short loc_18000ABA0
0x18000abc8  jmp     loc_18000AAAA
0x18000abcd  mov     r15d, [r13+24h]
0x18000abd1  cmp     r15d, 28h ; '('
0x18000abd5  jle     loc_18000AC9D
0x18000abdb  mov     ecx, [r13+20h]
0x18000abdf  mov     eax, 28h ; '('
0x18000abe4  cmp     r14d, eax
0x18000abe7  cmovg   eax, r14d
0x18000abeb  add     eax, eax
0x18000abed  cmp     ecx, eax
0x18000abef  cmovle  ecx, eax
0x18000abf2  cmp     ecx, r15d
0x18000abf5  jle     loc_18000AC90
0x18000abfb  lea     eax, [r15+8]
0x18000abff  cmp     eax, r15d
0x18000ac02  jl      loc_18000ACDB
0x18000ac08  cmp     eax, 28h ; '('
0x18000ac0b  jl      loc_18000ACDB
0x18000ac11  mov     ecx, r15d
0x18000ac14  add     rcx, 8; Size
0x18000ac18  call    cs:__imp_malloc
0x18000ac1e  test    rax, rax
0x18000ac21  jz      loc_18000ACDB
0x18000ac27  mov     rcx, [r13+10h]
0x18000ac2b  xor     r14d, r14d
0x18000ac2e  mov     [rax], rcx
0x18000ac31  mov     edi, r14d
0x18000ac34  mov     [r13+1Ch], r15d
0x18000ac38  lea     r15, __ImageBase
0x18000ac3f  mov     [r13+10h], rax
0x18000ac43  jmp     loc_18000AB3C
0x18000ac48  mov     rcx, [r13+160h]; jumptable 000000018000AADF case 158
0x18000ac4f  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000ac54  cmp     esi, 0Dh
0x18000ac57  mov     eax, r14d
0x18000ac5a  cmovnz  eax, ebp
0x18000ac5d  mov     ebp, eax
0x18000ac5f  jmp     loc_18000AA80
0x18000ac64  mov     rax, [r13+160h]
0x18000ac6b  mov     rcx, [rax+20h]
0x18000ac6f  sub     rcx, [rax+10h]
0x18000ac73  sar     rcx, 1
0x18000ac76  mov     [rdx+8], ecx
0x18000ac79  mov     rax, [r13+160h]
0x18000ac80  mov     rcx, [rax+28h]
0x18000ac84  sub     rcx, [rax+10h]
0x18000ac88  sar     rcx, 1
0x18000ac8b  jmp     loc_18000AB7C
0x18000ac90  cmp     ecx, 28h ; '('
0x18000ac93  jl      short loc_18000ACDB
0x18000ac95  mov     r15d, ecx
0x18000ac98  jmp     loc_18000ABFB
0x18000ac9d  mov     ecx, 30h ; '0'; Size
0x18000aca2  call    cs:__imp_malloc
0x18000aca8  test    rax, rax
0x18000acab  jz      short loc_18000ACDB
0x18000acad  mov     rcx, [r13+10h]
0x18000acb1  cmp     edi, r14d
0x18000acb4  jge     short loc_18000ACC5
0x18000acb6  mov     rcx, [rcx]
0x18000acb9  mov     [rax], rcx
0x18000acbc  mov     rcx, [r13+10h]
0x18000acc0  mov     [rcx], rax
0x18000acc3  jmp     short loc_18000ACCC
0x18000acc5  mov     [rax], rcx
0x18000acc8  mov     [r13+10h], rax
0x18000accc  xor     r14d, r14d
0x18000accf  lea     r15, __ImageBase
0x18000acd6  jmp     loc_18000AB4A
0x18000acdb  mov     edx, 3E9h; int
0x18000ace0  mov     rcx, r13; this
0x18000ace3  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18000ace9  mov     edx, 412h; int
0x18000acee  mov     rcx, r13; this
0x18000acf1  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
