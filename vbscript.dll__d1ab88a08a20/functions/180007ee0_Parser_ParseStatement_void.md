# Parser::ParseStatement(void)

- ea: `0x180007ee0`
- end: `0x180008b6a`
- name: `?ParseStatement@Parser@@AEAAPEAUParseNode@@XZ`
- size: `3210`
- prototype: `struct ParseNode *__fastcall(Parser *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x180008b70`

## callees

- `0x1800070c0`
- `0x180007ee0`
- `0x180008b70`
- `0x180008ee0`
- `0x1800095c0`
- `0x18000a6c0`
- `0x18000b320`
- `0x18000b714`
- `0x18000c2a0`
- `0x18002dc3c`
- `0x18002dc68`
- `0x18002dea8`
- `0x18002e740`
- `0x18002f7d0`
- `0x18002fc50`
- `0x18002fe20`
- `0x180030050`
- `0x180030808`
- `0x180030d80`
- `0x1800344c8`
- `0x180034b60`
- `0x18005e69c`
- `0x18005e8d0`
- `0x18005ea88`

## import_xrefs

- `msvcrt!malloc` at `0x180008242`
- `msvcrt!malloc` at `0x1800088b6`
- `msvcrt!malloc` at `0x180008242`
- `msvcrt!malloc` at `0x1800088b6`

## string_xrefs

- `0x1800084a1`: `WriteLine`

## pseudocode

```c
struct ParseNode *__fastcall Parser::ParseStatement(HashTbl **this)
{
  int v2; // edx
  struct ParseNode *v3; // rax
  HashTbl *v4; // rdi
  struct ParseNode *v5; // rax
  int v6; // ecx
  __int64 BinNode; // rdi
  struct ParseNode *v8; // rax
  int v9; // r15d
  int v10; // ebp
  struct ParseNode *v11; // rsi
  HashTbl *v12; // rax
  int v13; // ecx
  __int64 Node; // rsi
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  int v17; // eax
  HashTbl *v19; // rcx
  __int64 v20; // rdi
  struct ParseNode *v21; // rax
  __int64 v22; // r9
  int v23; // r13d
  int v24; // ecx
  int v25; // eax
  int v26; // eax
  HashTbl *v27; // rax
  HashTbl *v28; // rcx
  __int64 v29; // rsi
  __int64 v30; // rbp
  struct ParseNode *v31; // rdi
  _DWORD *v32; // rax
  __int64 v33; // rax
  int v34; // eax
  struct ParseNode *v35; // rax
  struct Ident *v36; // rdi
  __int64 v37; // rsi
  struct Ident *v38; // rdi
  __int64 v39; // rax
  int v40; // edx
  __int64 v41; // r14
  __int16 v42; // cx
  __int64 v43; // rsi
  int v44; // eax
  int v45; // r8d
  int v46; // edx
  HashTbl *v47; // rax
  int v48; // edx
  int v49; // edx
  int v50; // ecx
  int v51; // ecx
  int v52; // ecx
  int v53; // ecx
  __int64 v54; // rax
  HashTbl *v55; // rbp
  __int64 v56; // rsi
  struct ParseNode *v57; // rax
  int v58; // edx
  HashTbl *v59; // rdx
  int v60; // ecx

  if ( !(unsigned int)FStackAvailable(0x2000u) )
    Parser::Error((Parser *)this, 1001);
  if ( !this[45] && this[48] )
  {
    switch ( *((_DWORD *)this + 84) )
    {
      case 0x2F:
      case 0x37:
      case 0x44:
      case 0x6D:
      case 0x70:
      case 0x74:
      case 0x84:
      case 0x9C:
      case 0x9E:
      case 0xB7:
      case 0xB8:
        break;
      case 0x95:
        v42 = *((_WORD *)this[43] + 4);
        if ( v42 == 35 )
          Parser::Error((Parser *)this, 1057);
        if ( v42 == 110 )
          break;
        goto LABEL_64;
      default:
        goto LABEL_64;
    }
  }
  v2 = *((_DWORD *)this + 84);
  if ( v2 != 178 )
  {
    if ( v2 == 184 )
      return 0;
    if ( v2 != 132 )
    {
      switch ( v2 )
      {
        case 12:
          v56 = (__int64)(*((_QWORD *)this[44] + 4) - *((_QWORD *)this[44] + 2)) >> 1;
          ((void (*)(void))Scanner::Scan)();
          v57 = Parser::ParseTerm((Parser *)this);
          BinNode = (__int64)v57;
          if ( *(_DWORD *)v57 != 32 )
            BinNode = Parser::CreateBinNode(this, 32, v57, 0);
          *(_DWORD *)(BinNode + 8) = v56;
          goto LABEL_23;
        case 23:
          v3 = Parser::ParseClass((Parser *)this);
          goto LABEL_22;
        case 26:
        case 47:
        case 109:
        case 112:
        case 115:
          v3 = Parser::ParseVarDecl((Parser *)this);
          goto LABEL_22;
        case 48:
          v3 = Parser::ParseDoStmt((Parser *)this);
          goto LABEL_22;
        case 62:
          v43 = (__int64)(*((_QWORD *)this[44] + 4) - *((_QWORD *)this[44] + 2)) >> 1;
          v44 = ((__int64 (*)(void))Scanner::Scan)();
          v45 = v44;
          if ( v44 == 48 || (v46 = v44 - 66, v44 == 66) )
          {
            v54 = 55;
            if ( v45 != 48 )
              v54 = 54;
            v55 = this[v54];
            if ( !v55 )
              goto LABEL_111;
            BinNode = Parser::CreateNode(this, 66);
            *(_DWORD *)(BinNode + 8) = v43;
            *(_DWORD *)(BinNode + 12) = (__int64)(*((_QWORD *)this[44] + 5) - *((_QWORD *)this[44] + 2)) >> 1;
            *(_DWORD *)(BinNode + 24) = *((_DWORD *)this + 120);
            *(_QWORD *)(BinNode + 16) = v55;
            goto LABEL_97;
          }
          v47 = this[45];
          v48 = v46 - 2;
          if ( v48 )
          {
            v49 = v48 - 64;
            if ( v49 )
            {
              if ( v49 != 17 )
              {
                if ( v47 )
                {
                  v50 = *((_DWORD *)v47 + 1);
                  if ( (v50 & 0x4000) == 0 )
                  {
                    if ( (v50 & 0x1C00) != 0 )
                      goto LABEL_91;
LABEL_101:
                    Parser::Error((Parser *)this, 1015);
                  }
LABEL_106:
                  Parser::Error((Parser *)this, 1016);
                }
LABEL_111:
                Parser::Error((Parser *)this, 1039);
              }
              if ( !v47 )
                goto LABEL_111;
              v51 = *((_DWORD *)v47 + 1);
              if ( (v51 & 0x4000) != 0 )
                goto LABEL_106;
              if ( (v51 & 0x1C00) == 0 )
                goto LABEL_101;
              if ( *((_WORD *)this[43] + 4) == 110 )
                goto LABEL_96;
LABEL_91:
              Parser::Error((Parser *)this, 1050);
            }
            if ( !v47 )
              goto LABEL_111;
            v52 = *((_DWORD *)v47 + 1);
            if ( (v52 & 0x1C00) != 0 )
              goto LABEL_91;
            if ( (v52 & 0x4000) == 0 )
              goto LABEL_101;
          }
          else
          {
            if ( !v47 )
              goto LABEL_111;
            v53 = *((_DWORD *)v47 + 1);
            if ( (v53 & 0x4000) != 0 )
              goto LABEL_106;
            if ( (v53 & 0x1C00) != 0 )
              goto LABEL_91;
          }
LABEL_96:
          BinNode = Parser::CreateNode(this, 53);
          *(_DWORD *)(BinNode + 8) = v43;
          *(_DWORD *)(BinNode + 12) = (__int64)(*((_QWORD *)this[44] + 5) - *((_QWORD *)this[44] + 2)) >> 1;
LABEL_97:
          Scanner::Scan(this[44]);
          goto LABEL_23;
        case 66:
          v3 = Parser::ParseForStmt((Parser *)this);
          goto LABEL_22;
        case 68:
          break;
        case 73:
          v3 = Parser::ParseIfStmt((Parser *)this, 0);
          goto LABEL_22;
        case 91:
          Parser::Error((Parser *)this, 1038);
        case 93:
        case 149:
          if ( v2 != 149 )
            goto LABEL_10;
          v4 = this[43];
          if ( *((_WORD *)v4 + 4) != 110 )
            goto LABEL_10;
          Node = Parser::CreateNode(this, 1);
          *(_QWORD *)(Node + 16) = v4;
          Scanner::Scan(this[44]);
          v15 = (unsigned int)(*((_DWORD *)this + 84) - 69);
          if ( (unsigned int)v15 <= 0x36 )
          {
            v16 = 0x40000000010001LL;
            if ( _bittest64(&v16, v15) )
              break;
          }
          if ( this[48] && !this[45] )
            Parser::Error((Parser *)this, 1049);
          v5 = Parser::ParsePostfixOperators((Parser *)this, (struct ParseNode *)Node);
          goto LABEL_11;
        case 96:
          Parser::Error((Parser *)this, 1055);
        case 101:
          BinNode = Parser::CreateNode(this, 64);
          if ( (unsigned int)Scanner::Scan(this[44]) != 149 || *((_WORD *)this[43] + 4) != 60 )
            goto LABEL_64;
          v34 = Scanner::Scan(this[44]);
          if ( v34 == 72 )
          {
            if ( (unsigned int)Scanner::Scan(this[44]) == 185 && !*((_DWORD *)this + 86) )
            {
              *(_DWORD *)(BinNode + 12) = (__int64)(*((_QWORD *)this[44] + 5) - *((_QWORD *)this[44] + 2)) >> 1;
              Scanner::Scan(this[44]);
              goto LABEL_23;
            }
          }
          else if ( v34 == 117 )
          {
            Scanner::Scan(this[44]);
            *(_DWORD *)(BinNode + 12) = (__int64)(*((_QWORD *)this[44] + 5) - *((_QWORD *)this[44] + 2)) >> 1;
            Parser::ChkCurTok((Parser *)this, 96, 1002);
            *(_DWORD *)(BinNode + 4) |= 0x4000u;
            goto LABEL_23;
          }
LABEL_64:
          Parser::Error((Parser *)this, 1002);
        case 116:
        case 156:
        case 158:
        case 183:
          BinNode = 0;
          goto LABEL_23;
        case 122:
          v3 = Parser::ParseSelStmt((Parser *)this);
          goto LABEL_22;
        case 123:
          v28 = this[44];
          v29 = *((_QWORD *)v28 + 4);
          v30 = *((_QWORD *)v28 + 2);
          Scanner::Scan(v28);
          v31 = Parser::ParseTerm((Parser *)this);
          if ( *(_DWORD *)v31 == 7 )
            Parser::Error((Parser *)this, 1037);
          if ( *((_DWORD *)this + 84) != 164 )
            Parser::Error((Parser *)this, 1011);
          Scanner::Scan(this[44]);
          v35 = Parser::ParseExpr((Parser *)this, 0, 0);
          v3 = (struct ParseNode *)Parser::CreateBinNode(this, 35, v31, v35);
          *((_DWORD *)v3 + 2) = (v29 - v30) >> 1;
          goto LABEL_22;
        case 130:
          BinNode = Parser::CreateNode(this, 48);
          Scanner::Scan(this[44]);
          goto LABEL_23;
        case 144:
          v19 = this[44];
          v20 = (__int64)(*((_QWORD *)v19 + 4) - *((_QWORD *)v19 + 2)) >> 1;
          Scanner::Scan(v19);
          BinNode = Parser::CreateNode(this, 51, (unsigned int)v20);
          *(_DWORD *)(BinNode + 40) = *((_DWORD *)this + 120);
          v21 = Parser::ParseExpr((Parser *)this, 0, 0);
          *(_QWORD *)(BinNode + 24) = v21;
          if ( v21 )
            *(_DWORD *)(BinNode + 12) = *((_DWORD *)v21 + 3);
          *(_QWORD *)(BinNode + 16) = this[56];
          this[56] = (HashTbl *)BinNode;
          Parser::ParseStmtList(this, 143, BinNode + 32, 0);
          if ( *((_DWORD *)this + 84) != 143 )
            Parser::Error((Parser *)this, 1018);
          Scanner::Scan(this[44]);
          this[56] = *(HashTbl **)(BinNode + 16);
          goto LABEL_23;
        case 145:
          v3 = Parser::ParseWithStmt((Parser *)this);
          goto LABEL_22;
        case 182:
          v36 = HashTbl::PidHashNameLen(this[1], L"Debug", 5, 0);
          v37 = Parser::CreateNode(this, 1);
          *(_QWORD *)(v37 + 16) = v36;
          v38 = HashTbl::PidHashNameLen(this[1], L"WriteLine", 9, 0);
          v39 = Parser::CreateNode(this, 1);
          *(_QWORD *)(v39 + 16) = v38;
          BinNode = Parser::CreateBinNode(this, 33, v37, v39);
          Scanner::Scan(this[44]);
          v40 = *((_DWORD *)this + 84);
          if ( v40 == 156 || (v58 = v40 - 158) == 0 || (unsigned int)(v58 - 25) < 2 )
            v41 = 0;
          else
            v41 = Parser::ParseArgList(this, 183);
          v22 = v41;
          goto LABEL_36;
        default:
          Parser::Error((Parser *)this, 1024);
      }
    }
    v3 = Parser::ParseFncDecl((Parser *)this, 0);
    goto LABEL_22;
  }
LABEL_10:
  v5 = Parser::ParseTerm((Parser *)this);
LABEL_11:
  v6 = *((_DWORD *)this + 84);
  BinNode = (__int64)v5;
  if ( v6 != 164 )
  {
    if ( *(_DWORD *)v5 == 32 )
    {
      v32 = (_DWORD *)*((_QWORD *)v5 + 4);
      if ( v32 )
      {
        if ( *v32 == 43 )
          Parser::Error((Parser *)this, 1044);
        v32[1] |= 1u;
        if ( HashTbl::KwdOfTok(*((unsigned int *)this + 84)) )
          *(_QWORD *)(BinNode + 32) = Parser::ParseExpr((Parser *)this, 0, *(struct ParseNode **)(BinNode + 32));
        if ( *((_DWORD *)this + 84) == 155 )
        {
          Scanner::Scan(this[44]);
          v33 = Parser::ParseArgList(this, 183);
          *(_QWORD *)(BinNode + 32) = Parser::CreateBinNode(this, 43, *(_QWORD *)(BinNode + 32), v33);
        }
      }
      goto LABEL_23;
    }
    if ( v6 == 156 || (v60 = v6 - 158) == 0 || (unsigned int)(v60 - 25) < 2 )
      v22 = 0;
    else
      v22 = Parser::ParseArgList(this, 183);
LABEL_36:
    v3 = (struct ParseNode *)Parser::CreateBinNode(this, 32, BinNode, v22);
LABEL_22:
    BinNode = (__int64)v3;
    goto LABEL_23;
  }
  Scanner::Scan(this[44]);
  v8 = Parser::ParseExpr((Parser *)this, 0, 0);
  v9 = *((_DWORD *)this + 7);
  v10 = *((_DWORD *)this + 6);
  v11 = v8;
  if ( v9 - v10 >= 40 )
    goto LABEL_13;
  v23 = *((_DWORD *)this + 9);
  if ( v23 > 40 )
  {
    v24 = *((_DWORD *)this + 8);
    v25 = 40;
    if ( v9 > 40 )
      v25 = *((_DWORD *)this + 7);
    v26 = 2 * v25;
    if ( v24 <= v26 )
      v24 = v26;
    if ( v24 <= v23 )
    {
      if ( v24 < 40 )
        goto LABEL_135;
      v23 = v24;
    }
    if ( v23 + 8 > v23 && v23 + 8 >= 40 )
    {
      v27 = (HashTbl *)malloc((unsigned int)v23 + 8LL);
      if ( v27 )
      {
        v10 = 0;
        *(_QWORD *)v27 = this[2];
        this[2] = v27;
        *((_DWORD *)this + 7) = v23;
LABEL_13:
        *((_DWORD *)this + 6) = v10 + 40;
        v12 = (HashTbl *)((char *)this[2] + v10);
        goto LABEL_14;
      }
    }
LABEL_135:
    Parser::Error((Parser *)this, 1001);
  }
  v12 = (HashTbl *)malloc(0x30u);
  if ( !v12 )
    goto LABEL_135;
  v59 = this[2];
  if ( v10 >= v9 )
  {
    *(_QWORD *)v12 = v59;
    this[2] = v12;
  }
  else
  {
    *(_QWORD *)v12 = *(_QWORD *)v59;
    *(_QWORD *)v59 = v12;
  }
LABEL_14:
  if ( v12 == (HashTbl *)-8LL )
    goto LABEL_135;
  *((_QWORD *)v12 + 1) = 34;
  *((_QWORD *)v12 + 3) = 0;
  *((_QWORD *)v12 + 4) = BinNode;
  *((_QWORD *)v12 + 5) = v11;
  if ( BinNode )
  {
    *((_DWORD *)v12 + 4) = *(_DWORD *)(BinNode + 8);
    if ( v11 )
      v13 = *((_DWORD *)v11 + 3);
    else
      v13 = *(_DWORD *)(BinNode + 12);
    BinNode = (__int64)v12 + 8;
    *((_DWORD *)v12 + 5) = v13;
  }
  else
  {
    BinNode = (__int64)v12 + 8;
    *((_DWORD *)v12 + 4) = (__int64)(*((_QWORD *)this[44] + 4) - *((_QWORD *)this[44] + 2)) >> 1;
    *((_DWORD *)v12 + 5) = (__int64)(*((_QWORD *)this[44] + 5) - *((_QWORD *)this[44] + 2)) >> 1;
  }
LABEL_23:
  v17 = *((_DWORD *)this + 84);
  if ( v17 != 52 )
  {
    switch ( v17 )
    {
      case 55:
      case 158:
      case 183:
      case 184:
        return (struct ParseNode *)BinNode;
      case 116:
      case 156:
        Scanner::SkipToEOL(this[44]);
        break;
      default:
        Parser::Error((Parser *)this, 1025);
    }
  }
  return (struct ParseNode *)BinNode;
}

```

## disassembly

```asm
0x180007ee0  push    rbx
0x180007ee2  sub     rsp, 40h
0x180007ee6  mov     rbx, rcx
0x180007ee9  mov     ecx, 2000h; unsigned int
0x180007eee  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180007ef3  test    eax, eax
0x180007ef5  jz      loc_180008511
0x180007efb  cmp     qword ptr [rbx+168h], 0
0x180007f03  mov     [rsp+48h+arg_0], rbp
0x180007f08  mov     [rsp+48h+arg_8], rsi
0x180007f0d  mov     [rsp+48h+arg_10], rdi
0x180007f12  mov     [rsp+48h+var_10], r12
0x180007f17  lea     r12, __ImageBase
0x180007f1e  mov     [rsp+48h+var_18], r13
0x180007f23  mov     [rsp+48h+var_20], r14
0x180007f28  mov     [rsp+48h+var_28], r15
0x180007f2d  jz      loc_1800080E0
0x180007f33  mov     edx, [rbx+150h]; jumptable 0000000180008118 cases 47,55,68,109,112,116,132,156,158,183,184
0x180007f39  cmp     edx, 0B2h
0x180007f3f  jz      short loc_180007FAC
0x180007f41  cmp     edx, 0B8h
0x180007f47  jz      loc_1800080DC
0x180007f4d  cmp     edx, 84h
0x180007f53  jz      loc_180008093; jumptable 0000000180007F7D case 68
0x180007f59  lea     eax, [rdx-0Ch]; switch 172 cases
0x180007f5c  cmp     eax, 0ABh
0x180007f61  ja      def_180007F7D; jumptable 0000000180007F7D default case, cases 13-22,24,25,27-46,49-61,63-65,67,69-72,74-90,92,94,95,97-100,102-108,110,111,113,114,117-121,124-129,131-143,146-148,150-155,157,159-181
0x180007f67  cdqe
0x180007f69  movzx   eax, ds:(byte_180008998 - 180000000h)[r12+rax]
0x180007f72  mov     ecx, ds:(jpt_180007F7D - 180000000h)[r12+rax*4]
0x180007f7a  add     rcx, r12
0x180007f7d  jmp     rcx; switch jump
0x180007f83  xor     edx, edx; jumptable 0000000180007F7D case 73
0x180007f85  mov     rcx, rbx; this
0x180007f88  call    ?ParseIfStmt@Parser@@AEAAPEAUParseNode@@H@Z; Parser::ParseIfStmt(int)
0x180007f8d  jmp     loc_18000809D
0x180007f92  cmp     edx, 95h; jumptable 0000000180007F7D cases 93,149
0x180007f98  jnz     short loc_180007FAC
0x180007f9a  mov     rdi, [rbx+158h]
0x180007fa1  cmp     word ptr [rdi+8], 6Eh ; 'n'
0x180007fa6  jz      loc_18000804D
0x180007fac  mov     rcx, rbx; this
0x180007faf  call    ?ParseTerm@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseTerm(void)
0x180007fb4  mov     ecx, [rbx+150h]
0x180007fba  mov     rdi, rax
0x180007fbd  cmp     ecx, 0A4h
0x180007fc3  jnz     loc_1800081BE
0x180007fc9  mov     rcx, [rbx+160h]
0x180007fd0  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180007fd5  xor     r8d, r8d; struct ParseNode *
0x180007fd8  xor     edx, edx; int
0x180007fda  mov     rcx, rbx; this
0x180007fdd  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x180007fe2  mov     r15d, [rbx+1Ch]
0x180007fe6  xor     r14d, r14d
0x180007fe9  mov     ebp, [rbx+18h]
0x180007fec  mov     ecx, r15d
0x180007fef  sub     ecx, ebp
0x180007ff1  mov     rsi, rax
0x180007ff4  cmp     ecx, 28h ; '('
0x180007ff7  jl      loc_1800081F8
0x180007ffd  lea     eax, [rbp+28h]
0x180008000  mov     [rbx+18h], eax
0x180008003  movsxd  rax, ebp
0x180008006  add     rax, [rbx+10h]
0x18000800a  lea     rdx, [rax+8]
0x18000800e  test    rdx, rdx
0x180008011  jz      loc_1800088EA
0x180008017  mov     qword ptr [rdx], 22h ; '"'
0x18000801e  mov     [rdx+10h], r14
0x180008022  mov     [rdx+18h], rdi
0x180008026  mov     [rdx+20h], rsi
0x18000802a  test    rdi, rdi
0x18000802d  jz      loc_1800083EA
0x180008033  mov     eax, [rdi+8]
0x180008036  mov     [rdx+8], eax
0x180008039  test    rsi, rsi
0x18000803c  jz      loc_180008456
0x180008042  mov     ecx, [rsi+0Ch]
0x180008045  mov     rdi, rdx
0x180008048  mov     [rdx+0Ch], ecx
0x18000804b  jmp     short loc_1800080A0
0x18000804d  mov     edx, 1
0x180008052  mov     rcx, rbx
0x180008055  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z; Parser::CreateNode(OpCode)
0x18000805a  mov     rsi, rax
0x18000805d  mov     [rax+10h], rdi
0x180008061  mov     rcx, [rbx+160h]
0x180008068  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000806d  mov     ecx, [rbx+150h]
0x180008073  add     ecx, 0FFFFFFBBh
0x180008076  cmp     ecx, 36h ; '6'
0x180008079  ja      loc_180008871
0x18000807f  mov     rax, 40000000010001h
0x180008089  bt      rax, rcx
0x18000808d  jnb     loc_180008871
0x180008093  xor     edx, edx; jumptable 0000000180007F7D case 68
0x180008095  mov     rcx, rbx; this
0x180008098  call    ?ParseFncDecl@Parser@@AEAAPEAUParseNode@@K@Z; Parser::ParseFncDecl(ulong)
0x18000809d  mov     rdi, rax
0x1800080a0  mov     eax, [rbx+150h]
0x1800080a6  cmp     eax, 34h ; '4'
0x1800080a9  jnz     loc_180008336
0x1800080af  mov     rax, rdi; jumptable 000000018000835A cases 55,158,183,184
0x1800080b2  mov     r14, [rsp+48h+var_20]
0x1800080b7  mov     r13, [rsp+48h+var_18]
0x1800080bc  mov     r12, [rsp+48h+var_10]
0x1800080c1  mov     rdi, [rsp+48h+arg_10]
0x1800080c6  mov     rsi, [rsp+48h+arg_8]
0x1800080cb  mov     rbp, [rsp+48h+arg_0]
0x1800080d0  mov     r15, [rsp+48h+var_28]
0x1800080d5  add     rsp, 40h
0x1800080d9  pop     rbx
0x1800080da  retn
0x1800080dc  xor     eax, eax
0x1800080de  jmp     short loc_1800080B2
0x1800080e0  cmp     qword ptr [rbx+180h], 0
0x1800080e8  jz      loc_180007F33; jumptable 0000000180008118 cases 47,55,68,109,112,116,132,156,158,183,184
0x1800080ee  mov     eax, [rbx+150h]
0x1800080f4  add     eax, 0FFFFFFD1h; switch 138 cases
0x1800080f7  cmp     eax, 89h
0x1800080fc  ja      def_180008118; jumptable 0000000180008118 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x180008102  cdqe
0x180008104  movzx   eax, ds:(byte_180008A50 - 180000000h)[r12+rax]
0x18000810d  mov     ecx, ds:(jpt_180008118 - 180000000h)[r12+rax*4]
0x180008115  add     rcx, r12
0x180008118  jmp     rcx; switch jump
0x18000811e  mov     rcx, [rbx+160h]; jumptable 0000000180007F7D case 144
0x180008125  mov     rdi, [rcx+20h]
0x180008129  sub     rdi, [rcx+10h]
0x18000812d  sar     rdi, 1
0x180008130  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180008135  mov     r8d, edi
0x180008138  mov     edx, 33h ; '3'
0x18000813d  mov     rcx, rbx
0x180008140  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@J@Z; Parser::CreateNode(OpCode,long)
0x180008145  mov     rdi, rax
0x180008148  xor     r8d, r8d; struct ParseNode *
0x18000814b  mov     eax, [rbx+1E0h]
0x180008151  xor     edx, edx; int
0x180008153  mov     rcx, rbx; this
0x180008156  mov     [rdi+28h], eax
0x180008159  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x18000815e  mov     [rdi+18h], rax
0x180008162  test    rax, rax
0x180008165  jz      short loc_18000816D
0x180008167  mov     eax, [rax+0Ch]
0x18000816a  mov     [rdi+0Ch], eax
0x18000816d  mov     rax, [rbx+1C0h]
0x180008174  lea     r8, [rdi+20h]
0x180008178  mov     [rdi+10h], rax
0x18000817c  xor     r9d, r9d
0x18000817f  mov     edx, 8Fh
0x180008184  mov     [rbx+1C0h], rdi
0x18000818b  mov     rcx, rbx
0x18000818e  call    ?ParseStmtList@Parser@@AEAAXW4tokens@@PEAPEAUParseNode@@PEAPEAPEAU3@@Z; Parser::ParseStmtList(tokens,ParseNode * *,ParseNode * * *)
0x180008193  cmp     dword ptr [rbx+150h], 8Fh
0x18000819d  jz      loc_180008371
0x1800081a3  mov     edx, 3FAh; int
0x1800081a8  mov     rcx, rbx; this
0x1800081ab  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x1800081b1  mov     rcx, rbx; jumptable 0000000180007F7D cases 26,47,109,112,115
0x1800081b4  call    ?ParseVarDecl@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseVarDecl(void)
0x1800081b9  jmp     loc_18000809D
0x1800081be  cmp     dword ptr [rdi], 20h ; ' '
0x1800081c1  jz      loc_1800082B4
0x1800081c7  cmp     ecx, 9Ch
0x1800081cd  jnz     loc_180008906
0x1800081d3  xor     r9d, r9d
0x1800081d6  mov     r8, rdi
0x1800081d9  mov     edx, 20h ; ' '
0x1800081de  mov     rcx, rbx
0x1800081e1  call    ?CreateBinNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@PEAU2@1@Z; Parser::CreateBinNode(OpCode,ParseNode *,ParseNode *)
0x1800081e6  jmp     loc_18000809D
0x1800081eb  mov     rcx, rbx; jumptable 0000000180007F7D case 66
0x1800081ee  call    ?ParseForStmt@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseForStmt(void)
0x1800081f3  jmp     loc_18000809D
0x1800081f8  mov     r13d, [rbx+24h]
0x1800081fc  cmp     r13d, 28h ; '('
0x180008200  jle     loc_1800088B1
0x180008206  mov     ecx, [rbx+20h]
0x180008209  mov     eax, 28h ; '('
0x18000820e  cmp     r15d, eax
0x180008211  cmovg   eax, r15d
0x180008215  add     eax, eax
0x180008217  cmp     ecx, eax
0x180008219  cmovle  ecx, eax
0x18000821c  cmp     ecx, r13d
0x18000821f  jle     loc_180008464
0x180008225  lea     eax, [r13+8]
0x180008229  cmp     eax, r13d
0x18000822c  jl      loc_1800088EA
0x180008232  cmp     eax, 28h ; '('
0x180008235  jl      loc_1800088EA
0x18000823b  mov     ecx, r13d
0x18000823e  add     rcx, 8; Size
0x180008242  call    cs:__imp_malloc
0x180008249  nop     dword ptr [rax+rax+00h]
0x18000824e  test    rax, rax
0x180008251  jz      loc_1800088EA
0x180008257  mov     rcx, [rbx+10h]
0x18000825b  mov     ebp, r14d
0x18000825e  mov     [rax], rcx
0x180008261  mov     [rbx+10h], rax
0x180008265  mov     [rbx+1Ch], r13d
0x180008269  jmp     loc_180007FFD
0x18000826e  mov     rcx, [rbx+160h]; jumptable 0000000180007F7D case 123
0x180008275  mov     rsi, [rcx+20h]
0x180008279  mov     rbp, [rcx+10h]
0x18000827d  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180008282  mov     rcx, rbx; this
0x180008285  call    ?ParseTerm@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseTerm(void)
0x18000828a  mov     rdi, rax
0x18000828d  cmp     dword ptr [rax], 7
0x180008290  jz      loc_180008748
0x180008296  cmp     dword ptr [rbx+150h], 0A4h
0x1800082a0  jz      loc_18000841C
0x1800082a6  mov     edx, 3F3h; int
0x1800082ab  mov     rcx, rbx; this
0x1800082ae  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x1800082b4  mov     rax, [rdi+20h]
0x1800082b8  test    rax, rax
0x1800082bb  jz      loc_1800080A0
0x1800082c1  cmp     dword ptr [rax], 2Bh ; '+'
0x1800082c4  jz      loc_1800088F8
0x1800082ca  or      dword ptr [rax+4], 1
0x1800082ce  mov     ecx, [rbx+150h]
0x1800082d4  call    ?KwdOfTok@HashTbl@@CAPEBUKWD@1@W4tokens@@@Z; HashTbl::KwdOfTok(tokens)
0x1800082d9  test    rax, rax
0x1800082dc  jz      short loc_1800082F0
0x1800082de  mov     r8, [rdi+20h]; struct ParseNode *
0x1800082e2  xor     edx, edx; int
0x1800082e4  mov     rcx, rbx; this
0x1800082e7  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x1800082ec  mov     [rdi+20h], rax
0x1800082f0  cmp     dword ptr [rbx+150h], 9Bh
0x1800082fa  jnz     loc_1800080A0
0x180008300  mov     rcx, [rbx+160h]
0x180008307  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000830c  mov     edx, 0B7h
0x180008311  mov     rcx, rbx
0x180008314  call    ?ParseArgList@Parser@@AEAAPEAUParseNode@@W4tokens@@@Z; Parser::ParseArgList(tokens)
0x180008319  mov     r8, [rdi+20h]
0x18000831d  mov     r9, rax
0x180008320  mov     edx, 2Bh ; '+'
0x180008325  mov     rcx, rbx
0x180008328  call    ?CreateBinNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@PEAU2@1@Z; Parser::CreateBinNode(OpCode,ParseNode *,ParseNode *)
0x18000832d  mov     [rdi+20h], rax
0x180008331  jmp     loc_1800080A0
0x180008336  add     eax, 0FFFFFFC9h; switch 130 cases
0x180008339  cmp     eax, 81h
0x18000833e  ja      def_18000835A; jumptable 000000018000835A default case, cases 56-115,117-155,157,159-182
0x180008344  cdqe
0x180008346  movzx   eax, ds:(byte_180008AE8 - 180000000h)[r12+rax]
0x18000834f  mov     ecx, ds:(jpt_18000835A - 180000000h)[r12+rax*4]
0x180008357  add     rcx, r12
0x18000835a  jmp     rcx; switch jump
0x180008360  mov     rcx, [rbx+160h]; jumptable 000000018000835A cases 116,156
0x180008367  call    ?SkipToEOL@Scanner@@QEAAXXZ; Scanner::SkipToEOL(void)
0x18000836c  jmp     loc_1800080AF; jumptable 000000018000835A cases 55,158,183,184
0x180008371  mov     rcx, [rbx+160h]
0x180008378  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000837d  mov     rax, [rdi+10h]
0x180008381  mov     [rbx+1C0h], rax
0x180008388  jmp     loc_1800080A0
0x18000838d  mov     edx, 40h ; '@'; jumptable 0000000180007F7D case 101
0x180008392  mov     rcx, rbx
0x180008395  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z; Parser::CreateNode(OpCode)
0x18000839a  mov     rcx, [rbx+160h]
0x1800083a1  mov     rdi, rax
0x1800083a4  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x1800083a9  cmp     eax, 95h
0x1800083ae  jnz     short def_180008118; jumptable 0000000180008118 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x1800083b0  mov     rax, [rbx+158h]
0x1800083b7  cmp     word ptr [rax+8], 3Ch ; '<'
0x1800083bc  jnz     short def_180008118; jumptable 0000000180008118 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x1800083be  mov     rcx, [rbx+160h]
0x1800083c5  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x1800083ca  cmp     eax, 48h ; 'H'
0x1800083cd  jz      loc_1800087E6
0x1800083d3  cmp     eax, 75h ; 'u'
0x1800083d6  jz      loc_1800087A6
0x1800083dc  mov     edx, 3EAh; jumptable 0000000180008118 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x1800083e1  mov     rcx, rbx; this
0x1800083e4  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x1800083ea  mov     rax, [rbx+160h]
0x1800083f1  mov     rdi, rdx
0x1800083f4  mov     rcx, [rax+20h]
0x1800083f8  sub     rcx, [rax+10h]
0x1800083fc  sar     rcx, 1
0x1800083ff  mov     [rdx+8], ecx
0x180008402  mov     rax, [rbx+160h]
0x180008409  mov     rcx, [rax+28h]
0x18000840d  sub     rcx, [rax+10h]
0x180008411  sar     rcx, 1
0x180008414  mov     [rdx+0Ch], ecx
0x180008417  jmp     loc_1800080A0
0x18000841c  mov     rcx, [rbx+160h]
0x180008423  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180008428  xor     r8d, r8d; struct ParseNode *
  ... truncated ...
```
