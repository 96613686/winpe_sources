# Parser::ParseArgList(tokens)

- ea: `0x18002aaa0`
- end: `0x18002ad0d`
- name: `?ParseArgList@Parser@@AEAAPEAUParseNode@@W4tokens@@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009da0`

## callees

- `0x18000c4b0`
- `0x18000d100`
- `0x18000d4dc`
- `0x18002a6c0`
- `0x18002aaa0`

## import_xrefs

- `msvcrt!malloc` at `0x18002ac34`
- `msvcrt!malloc` at `0x18002accd`
- `msvcrt!malloc` at `0x18002ac34`
- `msvcrt!malloc` at `0x18002accd`

## pseudocode

```c
struct ParseNode *__fastcall Parser::ParseArgList(__int64 a1, int a2)
{
  struct ParseNode **v3; // rsi
  struct ParseNode *Node; // rax
  struct ParseNode *v5; // rdi
  struct ParseNode *result; // rax
  int v7; // r15d
  int v8; // r14d
  struct ParseNode *v9; // rbp
  _QWORD *v10; // rax
  struct ParseNode *v11; // rdx
  int v12; // ecx
  int v13; // r13d
  int v14; // ecx
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rax
  _QWORD *v18; // rcx
  struct ParseNode *v19; // [rsp+60h] [rbp+18h] BYREF

  v19 = 0;
  if ( a2 == 183 || (unsigned int)Scanner::Scan(*(_QWORD *)(a1 + 352)) != a2 )
  {
    v3 = 0;
    while ( 1 )
    {
      if ( *(_DWORD *)(a1 + 336) == 155 )
        Node = (struct ParseNode *)Parser::CreateNode(a1, 12);
      else
        Node = Parser::ParseExpr((Parser *)a1, 0, 0);
      v5 = Node;
      if ( !v3 )
      {
        v19 = Node;
        v3 = &v19;
        goto LABEL_8;
      }
      v7 = *(_DWORD *)(a1 + 28);
      v8 = *(_DWORD *)(a1 + 24);
      v9 = *v3;
      if ( v7 - v8 < 40 )
      {
        v13 = *(_DWORD *)(a1 + 36);
        if ( v13 <= 40 )
        {
          v10 = malloc(0x30u);
          if ( !v10 )
            goto LABEL_38;
          v18 = *(_QWORD **)(a1 + 16);
          if ( v8 >= v7 )
          {
            *v10 = v18;
            *(_QWORD *)(a1 + 16) = v10;
          }
          else
          {
            *v10 = *v18;
            **(_QWORD **)(a1 + 16) = v10;
          }
          goto LABEL_12;
        }
        v14 = *(_DWORD *)(a1 + 32);
        v15 = 40;
        if ( v7 > 40 )
          v15 = *(_DWORD *)(a1 + 28);
        v16 = 2 * v15;
        if ( v14 <= v16 )
          v14 = v16;
        if ( v14 <= v13 )
        {
          if ( v14 < 40 )
            goto LABEL_38;
          v13 = v14;
        }
        if ( v13 + 8 <= v13 || v13 + 8 < 40 || (v17 = malloc((unsigned int)v13 + 8LL)) == 0 )
LABEL_38:
          Parser::Error((Parser *)a1, 1001);
        v8 = 0;
        *v17 = *(_QWORD *)(a1 + 16);
        *(_QWORD *)(a1 + 16) = v17;
        *(_DWORD *)(a1 + 28) = v13;
      }
      *(_DWORD *)(a1 + 24) = v8 + 40;
      v10 = (_QWORD *)(*(_QWORD *)(a1 + 16) + v8);
LABEL_12:
      v11 = (struct ParseNode *)(v10 + 1);
      if ( v10 == (_QWORD *)-8LL )
        goto LABEL_38;
      *(_QWORD *)v11 = 43;
      v10[3] = 0;
      v10[4] = v9;
      v10[5] = v5;
      if ( v9 )
      {
        *((_DWORD *)v10 + 4) = *((_DWORD *)v9 + 2);
        if ( v5 )
          v12 = *((_DWORD *)v5 + 3);
        else
          v12 = *((_DWORD *)v9 + 3);
        *((_DWORD *)v10 + 5) = v12;
        *v3 = v11;
        v3 = (struct ParseNode **)(v10 + 5);
        v5 = v19;
      }
      else
      {
        *((_DWORD *)v10 + 4) = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 352) + 32LL)
                                       - *(_QWORD *)(*(_QWORD *)(a1 + 352) + 16LL)) >> 1;
        *((_DWORD *)v10 + 5) = (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 352) + 40LL)
                                       - *(_QWORD *)(*(_QWORD *)(a1 + 352) + 16LL)) >> 1;
        *v3 = v11;
        v3 = (struct ParseNode **)(v10 + 5);
        v5 = v19;
      }
LABEL_8:
      if ( *(_DWORD *)(a1 + 336) != 155 )
      {
        result = v5;
        *((_DWORD *)v5 + 3) = *((_DWORD *)*v3 + 3);
        return result;
      }
      Scanner::Scan(*(_QWORD *)(a1 + 352));
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002aaa0  push    rbx
0x18002aaa2  push    rdi
0x18002aaa3  push    r12
0x18002aaa5  sub     rsp, 30h
0x18002aaa9  xor     r12d, r12d
0x18002aaac  mov     edi, edx
0x18002aaae  mov     [rsp+48h+arg_10], r12
0x18002aab3  mov     rbx, rcx
0x18002aab6  cmp     edx, 0B7h
0x18002aabc  jz      short loc_18002AAD2
0x18002aabe  mov     rcx, [rcx+160h]
0x18002aac5  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18002aaca  cmp     eax, edi
0x18002aacc  jz      loc_18002ABDF
0x18002aad2  mov     [rsp+48h+arg_8], rsi
0x18002aad7  mov     rsi, r12
0x18002aada  mov     [rsp+48h+arg_0], rbp
0x18002aadf  mov     [rsp+48h+arg_18], r13
0x18002aae4  mov     [rsp+48h+var_20], r14
0x18002aae9  mov     [rsp+48h+var_28], r15
0x18002aaee  cmp     dword ptr [rbx+150h], 9Bh
0x18002aaf8  mov     rcx, rbx; this
0x18002aafb  jz      loc_18002ACAC
0x18002ab01  xor     r8d, r8d; struct ParseNode *
0x18002ab04  xor     edx, edx; int
0x18002ab06  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x18002ab0b  mov     rdi, rax
0x18002ab0e  test    rsi, rsi
0x18002ab11  jnz     short loc_18002AB5B
0x18002ab13  mov     [rsp+48h+arg_10], rax
0x18002ab18  lea     rsi, [rsp+48h+arg_10]
0x18002ab1d  cmp     dword ptr [rbx+150h], 9Bh
0x18002ab27  jz      loc_18002ABCE
0x18002ab2d  mov     rcx, [rsi]
0x18002ab30  mov     rax, rdi
0x18002ab33  mov     r14, [rsp+48h+var_20]
0x18002ab38  mov     r13, [rsp+48h+arg_18]
0x18002ab3d  mov     rbp, [rsp+48h+arg_0]
0x18002ab42  mov     edx, [rcx+0Ch]
0x18002ab45  mov     r15, [rsp+48h+var_28]
0x18002ab4a  mov     rsi, [rsp+48h+arg_8]
0x18002ab4f  mov     [rdi+0Ch], edx
0x18002ab52  add     rsp, 30h
0x18002ab56  pop     r12
0x18002ab58  pop     rdi
0x18002ab59  pop     rbx
0x18002ab5a  retn
0x18002ab5b  mov     r15d, [rbx+1Ch]
0x18002ab5f  mov     eax, r15d
0x18002ab62  mov     r14d, [rbx+18h]
0x18002ab66  sub     eax, r14d
0x18002ab69  mov     rbp, [rsi]
0x18002ab6c  cmp     eax, 28h ; '('
0x18002ab6f  jl      short loc_18002ABEA
0x18002ab71  lea     eax, [r14+28h]
0x18002ab75  mov     [rbx+18h], eax
0x18002ab78  movsxd  rax, r14d
0x18002ab7b  add     rax, [rbx+10h]
0x18002ab7f  lea     rdx, [rax+8]
0x18002ab83  test    rdx, rdx
0x18002ab86  jz      loc_18002ACFF
0x18002ab8c  mov     qword ptr [rdx], 2Bh ; '+'
0x18002ab93  mov     [rdx+10h], r12
0x18002ab97  mov     [rdx+18h], rbp
0x18002ab9b  mov     [rdx+20h], rdi
0x18002ab9f  test    rbp, rbp
0x18002aba2  jz      loc_18002AC5A
0x18002aba8  mov     eax, [rbp+8]
0x18002abab  mov     [rdx+8], eax
0x18002abae  test    rdi, rdi
0x18002abb1  jz      loc_18002AC95
0x18002abb7  mov     ecx, [rdi+0Ch]
0x18002abba  mov     [rdx+0Ch], ecx
0x18002abbd  mov     [rsi], rdx
0x18002abc0  lea     rsi, [rdx+20h]
0x18002abc4  mov     rdi, [rsp+48h+arg_10]
0x18002abc9  jmp     loc_18002AB1D
0x18002abce  mov     rcx, [rbx+160h]
0x18002abd5  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18002abda  jmp     loc_18002AAEE
0x18002abdf  xor     eax, eax
0x18002abe1  add     rsp, 30h
0x18002abe5  pop     r12
0x18002abe7  pop     rdi
0x18002abe8  pop     rbx
0x18002abe9  retn
0x18002abea  mov     r13d, [rbx+24h]
0x18002abee  cmp     r13d, 28h ; '('
0x18002abf2  jle     loc_18002ACC8
0x18002abf8  mov     ecx, [rbx+20h]
0x18002abfb  mov     eax, 28h ; '('
0x18002ac00  cmp     r15d, eax
0x18002ac03  cmovg   eax, r15d
0x18002ac07  add     eax, eax
0x18002ac09  cmp     ecx, eax
0x18002ac0b  cmovle  ecx, eax
0x18002ac0e  cmp     ecx, r13d
0x18002ac11  jle     loc_18002ACBB
0x18002ac17  lea     eax, [r13+8]
0x18002ac1b  cmp     eax, r13d
0x18002ac1e  jl      loc_18002ACFF
0x18002ac24  cmp     eax, 28h ; '('
0x18002ac27  jl      loc_18002ACFF
0x18002ac2d  mov     ecx, r13d
0x18002ac30  add     rcx, 8; Size
0x18002ac34  call    cs:__imp_malloc
0x18002ac3a  test    rax, rax
0x18002ac3d  jz      loc_18002ACFF
0x18002ac43  mov     rcx, [rbx+10h]
0x18002ac47  mov     r14d, r12d
0x18002ac4a  mov     [rax], rcx
0x18002ac4d  mov     [rbx+10h], rax
0x18002ac51  mov     [rbx+1Ch], r13d
0x18002ac55  jmp     loc_18002AB71
0x18002ac5a  mov     rax, [rbx+160h]
0x18002ac61  mov     rcx, [rax+20h]
0x18002ac65  sub     rcx, [rax+10h]
0x18002ac69  sar     rcx, 1
0x18002ac6c  mov     [rdx+8], ecx
0x18002ac6f  mov     rax, [rbx+160h]
0x18002ac76  mov     rcx, [rax+28h]
0x18002ac7a  sub     rcx, [rax+10h]
0x18002ac7e  sar     rcx, 1
0x18002ac81  mov     [rdx+0Ch], ecx
0x18002ac84  mov     [rsi], rdx
0x18002ac87  lea     rsi, [rdx+20h]
0x18002ac8b  mov     rdi, [rsp+48h+arg_10]
0x18002ac90  jmp     loc_18002AB1D
0x18002ac95  mov     ecx, [rbp+0Ch]
0x18002ac98  mov     [rdx+0Ch], ecx
0x18002ac9b  mov     [rsi], rdx
0x18002ac9e  lea     rsi, [rdx+20h]
0x18002aca2  mov     rdi, [rsp+48h+arg_10]
0x18002aca7  jmp     loc_18002AB1D
0x18002acac  mov     edx, 0Ch
0x18002acb1  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z; Parser::CreateNode(OpCode)
0x18002acb6  jmp     loc_18002AB0B
0x18002acbb  cmp     ecx, 28h ; '('
0x18002acbe  jl      short loc_18002ACFF
0x18002acc0  mov     r13d, ecx
0x18002acc3  jmp     loc_18002AC17
0x18002acc8  mov     ecx, 30h ; '0'; Size
0x18002accd  call    cs:__imp_malloc
0x18002acd3  test    rax, rax
0x18002acd6  jz      short loc_18002ACFF
0x18002acd8  mov     rcx, [rbx+10h]
0x18002acdc  cmp     r14d, r15d
0x18002acdf  jge     short loc_18002ACF3
0x18002ace1  mov     rcx, [rcx]
0x18002ace4  mov     [rax], rcx
0x18002ace7  mov     rcx, [rbx+10h]
0x18002aceb  mov     [rcx], rax
0x18002acee  jmp     loc_18002AB7F
0x18002acf3  mov     [rax], rcx
0x18002acf6  mov     [rbx+10h], rax
0x18002acfa  jmp     loc_18002AB7F
0x18002acff  mov     edx, 3E9h; int
0x18002ad04  mov     rcx, rbx; this
0x18002ad07  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
