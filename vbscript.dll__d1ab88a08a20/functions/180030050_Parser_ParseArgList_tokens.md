# Parser::ParseArgList(tokens)

- ea: `0x180030050`
- end: `0x1800302cb`
- name: `?ParseArgList@Parser@@AEAAPEAUParseNode@@W4tokens@@@Z`
- size: `635`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180007ee0`

## callees

- `0x18000a6c0`
- `0x18000b320`
- `0x18000b714`
- `0x18002fc50`
- `0x180030050`

## import_xrefs

- `msvcrt!malloc` at `0x1800301e6`
- `msvcrt!malloc` at `0x180030285`
- `msvcrt!malloc` at `0x1800301e6`
- `msvcrt!malloc` at `0x180030285`

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
0x180030050  push    rbx
0x180030052  push    rdi
0x180030053  push    r12
0x180030055  sub     rsp, 30h
0x180030059  xor     r12d, r12d
0x18003005c  mov     edi, edx
0x18003005e  mov     [rsp+48h+arg_10], r12
0x180030063  mov     rbx, rcx
0x180030066  cmp     edx, 0B7h
0x18003006c  jz      short loc_180030082
0x18003006e  mov     rcx, [rcx+160h]
0x180030075  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18003007a  cmp     eax, edi
0x18003007c  jz      loc_180030190
0x180030082  mov     [rsp+48h+arg_8], rsi
0x180030087  mov     rsi, r12
0x18003008a  mov     [rsp+48h+arg_0], rbp
0x18003008f  mov     [rsp+48h+arg_18], r13
0x180030094  mov     [rsp+48h+var_20], r14
0x180030099  mov     [rsp+48h+var_28], r15
0x18003009e  cmp     dword ptr [rbx+150h], 9Bh
0x1800300a8  mov     rcx, rbx; this
0x1800300ab  jz      loc_180030264
0x1800300b1  xor     r8d, r8d; struct ParseNode *
0x1800300b4  xor     edx, edx; int
0x1800300b6  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x1800300bb  mov     rdi, rax
0x1800300be  test    rsi, rsi
0x1800300c1  jnz     short loc_18003010C
0x1800300c3  mov     [rsp+48h+arg_10], rax
0x1800300c8  lea     rsi, [rsp+48h+arg_10]
0x1800300cd  cmp     dword ptr [rbx+150h], 9Bh
0x1800300d7  jz      loc_18003017F
0x1800300dd  mov     rcx, [rsi]
0x1800300e0  mov     rax, rdi
0x1800300e3  mov     r14, [rsp+48h+var_20]
0x1800300e8  mov     r13, [rsp+48h+arg_18]
0x1800300ed  mov     rbp, [rsp+48h+arg_0]
0x1800300f2  mov     edx, [rcx+0Ch]
0x1800300f5  mov     r15, [rsp+48h+var_28]
0x1800300fa  mov     rsi, [rsp+48h+arg_8]
0x1800300ff  mov     [rdi+0Ch], edx
0x180030102  add     rsp, 30h
0x180030106  pop     r12
0x180030108  pop     rdi
0x180030109  pop     rbx
0x18003010a  retn
0x18003010c  mov     r15d, [rbx+1Ch]
0x180030110  mov     eax, r15d
0x180030113  mov     r14d, [rbx+18h]
0x180030117  sub     eax, r14d
0x18003011a  mov     rbp, [rsi]
0x18003011d  cmp     eax, 28h ; '('
0x180030120  jl      short loc_18003019C
0x180030122  lea     eax, [r14+28h]
0x180030126  mov     [rbx+18h], eax
0x180030129  movsxd  rax, r14d
0x18003012c  add     rax, [rbx+10h]
0x180030130  lea     rdx, [rax+8]
0x180030134  test    rdx, rdx
0x180030137  jz      loc_1800302BD
0x18003013d  mov     qword ptr [rdx], 2Bh ; '+'
0x180030144  mov     [rdx+10h], r12
0x180030148  mov     [rdx+18h], rbp
0x18003014c  mov     [rdx+20h], rdi
0x180030150  test    rbp, rbp
0x180030153  jz      loc_180030212
0x180030159  mov     eax, [rbp+8]
0x18003015c  mov     [rdx+8], eax
0x18003015f  test    rdi, rdi
0x180030162  jz      loc_18003024D
0x180030168  mov     ecx, [rdi+0Ch]
0x18003016b  mov     [rdx+0Ch], ecx
0x18003016e  mov     [rsi], rdx
0x180030171  lea     rsi, [rdx+20h]
0x180030175  mov     rdi, [rsp+48h+arg_10]
0x18003017a  jmp     loc_1800300CD
0x18003017f  mov     rcx, [rbx+160h]
0x180030186  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18003018b  jmp     loc_18003009E
0x180030190  xor     eax, eax
0x180030192  add     rsp, 30h
0x180030196  pop     r12
0x180030198  pop     rdi
0x180030199  pop     rbx
0x18003019a  retn
0x18003019c  mov     r13d, [rbx+24h]
0x1800301a0  cmp     r13d, 28h ; '('
0x1800301a4  jle     loc_180030280
0x1800301aa  mov     ecx, [rbx+20h]
0x1800301ad  mov     eax, 28h ; '('
0x1800301b2  cmp     r15d, eax
0x1800301b5  cmovg   eax, r15d
0x1800301b9  add     eax, eax
0x1800301bb  cmp     ecx, eax
0x1800301bd  cmovle  ecx, eax
0x1800301c0  cmp     ecx, r13d
0x1800301c3  jle     loc_180030273
0x1800301c9  lea     eax, [r13+8]
0x1800301cd  cmp     eax, r13d
0x1800301d0  jl      loc_1800302BD
0x1800301d6  cmp     eax, 28h ; '('
0x1800301d9  jl      loc_1800302BD
0x1800301df  mov     ecx, r13d
0x1800301e2  add     rcx, 8; Size
0x1800301e6  call    cs:__imp_malloc
0x1800301ed  nop     dword ptr [rax+rax+00h]
0x1800301f2  test    rax, rax
0x1800301f5  jz      loc_1800302BD
0x1800301fb  mov     rcx, [rbx+10h]
0x1800301ff  mov     r14d, r12d
0x180030202  mov     [rax], rcx
0x180030205  mov     [rbx+10h], rax
0x180030209  mov     [rbx+1Ch], r13d
0x18003020d  jmp     loc_180030122
0x180030212  mov     rax, [rbx+160h]
0x180030219  mov     rcx, [rax+20h]
0x18003021d  sub     rcx, [rax+10h]
0x180030221  sar     rcx, 1
0x180030224  mov     [rdx+8], ecx
0x180030227  mov     rax, [rbx+160h]
0x18003022e  mov     rcx, [rax+28h]
0x180030232  sub     rcx, [rax+10h]
0x180030236  sar     rcx, 1
0x180030239  mov     [rdx+0Ch], ecx
0x18003023c  mov     [rsi], rdx
0x18003023f  lea     rsi, [rdx+20h]
0x180030243  mov     rdi, [rsp+48h+arg_10]
0x180030248  jmp     loc_1800300CD
0x18003024d  mov     ecx, [rbp+0Ch]
0x180030250  mov     [rdx+0Ch], ecx
0x180030253  mov     [rsi], rdx
0x180030256  lea     rsi, [rdx+20h]
0x18003025a  mov     rdi, [rsp+48h+arg_10]
0x18003025f  jmp     loc_1800300CD
0x180030264  mov     edx, 0Ch
0x180030269  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z; Parser::CreateNode(OpCode)
0x18003026e  jmp     loc_1800300BB
0x180030273  cmp     ecx, 28h ; '('
0x180030276  jl      short loc_1800302BD
0x180030278  mov     r13d, ecx
0x18003027b  jmp     loc_1800301C9
0x180030280  mov     ecx, 30h ; '0'; Size
0x180030285  call    cs:__imp_malloc
0x18003028c  nop     dword ptr [rax+rax+00h]
0x180030291  test    rax, rax
0x180030294  jz      short loc_1800302BD
0x180030296  mov     rcx, [rbx+10h]
0x18003029a  cmp     r14d, r15d
0x18003029d  jge     short loc_1800302B1
0x18003029f  mov     rcx, [rcx]
0x1800302a2  mov     [rax], rcx
0x1800302a5  mov     rcx, [rbx+10h]
0x1800302a9  mov     [rcx], rax
0x1800302ac  jmp     loc_180030130
0x1800302b1  mov     [rax], rcx
0x1800302b4  mov     [rbx+10h], rax
0x1800302b8  jmp     loc_180030130
0x1800302bd  mov     edx, 3E9h; int
0x1800302c2  mov     rcx, rbx; this
0x1800302c5  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
```
