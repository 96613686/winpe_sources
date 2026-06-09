# Parser::ParseStatement(void)

- ea: `0x180009da0`
- end: `0x18000aa12`
- name: `?ParseStatement@Parser@@AEAAPEAUParseNode@@XZ`
- size: `3186`
- prototype: `struct ParseNode *__fastcall(Parser *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config`

## callers

- `0x18000aa20`

## callees

- `0x180008fc0`
- `0x180009da0`
- `0x18000aa20`
- `0x18000ad80`
- `0x18000b430`
- `0x18000c4b0`
- `0x18000d100`
- `0x18000d4dc`
- `0x18000e050`
- `0x18002873c`
- `0x180028768`
- `0x1800289a8`
- `0x180029220`
- `0x18002a250`
- `0x18002a6c0`
- `0x18002a880`
- `0x18002aaa0`
- `0x18002be54`
- `0x18002c3c0`
- `0x18002f674`
- `0x18002ff20`
- `0x18005cae0`
- `0x18005cd14`
- `0x18005cecc`

## import_xrefs

- `msvcrt!malloc` at `0x18000a0f9`
- `msvcrt!malloc` at `0x18000a763`
- `msvcrt!malloc` at `0x18000a0f9`
- `msvcrt!malloc` at `0x18000a763`

## string_xrefs

- `0x18000a34e`: `WriteLine`

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
0x180009da0  push    rbx
0x180009da2  sub     rsp, 40h
0x180009da6  mov     rbx, rcx
0x180009da9  mov     ecx, 2000h; unsigned int
0x180009dae  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x180009db3  test    eax, eax
0x180009db5  jz      loc_18000A3BE
0x180009dbb  cmp     qword ptr [rbx+168h], 0
0x180009dc3  mov     [rsp+48h+arg_0], rbp
0x180009dc8  mov     [rsp+48h+arg_8], rsi
0x180009dcd  mov     [rsp+48h+arg_10], rdi
0x180009dd2  mov     [rsp+48h+var_10], r12
0x180009dd7  lea     r12, __ImageBase
0x180009dde  mov     [rsp+48h+var_18], r13
0x180009de3  mov     [rsp+48h+var_20], r14
0x180009de8  mov     [rsp+48h+var_28], r15
0x180009ded  jz      loc_180009F9B
0x180009df3  mov     edx, [rbx+150h]; jumptable 0000000180009FD3 cases 47,55,68,109,112,116,132,156,158,183,184
0x180009df9  cmp     edx, 0B2h
0x180009dff  jz      short loc_180009E68
0x180009e01  cmp     edx, 0B8h
0x180009e07  jz      loc_180009F97
0x180009e0d  cmp     edx, 84h
0x180009e13  jz      loc_180009F4F; jumptable 0000000180009E3D case 68
0x180009e19  lea     eax, [rdx-0Ch]; switch 172 cases
0x180009e1c  cmp     eax, 0ABh
0x180009e21  ja      def_180009E3D; jumptable 0000000180009E3D default case, cases 13-22,24,25,27-46,49-61,63-65,67,69-72,74-90,92,94,95,97-100,102-108,110,111,113,114,117-121,124-129,131-143,146-148,150-155,157,159-181
0x180009e27  cdqe
0x180009e29  movzx   eax, ds:(byte_18000A840 - 180000000h)[r12+rax]
0x180009e32  mov     ecx, ds:(jpt_180009E3D - 180000000h)[r12+rax*4]
0x180009e3a  add     rcx, r12
0x180009e3d  jmp     rcx; switch jump
0x180009e3f  xor     edx, edx; jumptable 0000000180009E3D case 73
0x180009e41  mov     rcx, rbx; this
0x180009e44  call    ?ParseIfStmt@Parser@@AEAAPEAUParseNode@@H@Z; Parser::ParseIfStmt(int)
0x180009e49  jmp     loc_180009F59
0x180009e4e  cmp     edx, 95h; jumptable 0000000180009E3D cases 93,149
0x180009e54  jnz     short loc_180009E68
0x180009e56  mov     rdi, [rbx+158h]
0x180009e5d  cmp     word ptr [rdi+8], 6Eh ; 'n'
0x180009e62  jz      loc_180009F09
0x180009e68  mov     rcx, rbx; this
0x180009e6b  call    ?ParseTerm@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseTerm(void)
0x180009e70  mov     ecx, [rbx+150h]
0x180009e76  mov     rdi, rax
0x180009e79  cmp     ecx, 0A4h
0x180009e7f  jnz     loc_18000A075
0x180009e85  mov     rcx, [rbx+160h]
0x180009e8c  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180009e91  xor     r8d, r8d; struct ParseNode *
0x180009e94  xor     edx, edx; int
0x180009e96  mov     rcx, rbx; this
0x180009e99  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x180009e9e  mov     r15d, [rbx+1Ch]
0x180009ea2  xor     r14d, r14d
0x180009ea5  mov     ebp, [rbx+18h]
0x180009ea8  mov     ecx, r15d
0x180009eab  sub     ecx, ebp
0x180009ead  mov     rsi, rax
0x180009eb0  cmp     ecx, 28h ; '('
0x180009eb3  jl      loc_18000A0AF
0x180009eb9  lea     eax, [rbp+28h]
0x180009ebc  mov     [rbx+18h], eax
0x180009ebf  movsxd  rax, ebp
0x180009ec2  add     rax, [rbx+10h]
0x180009ec6  lea     rdx, [rax+8]
0x180009eca  test    rdx, rdx
0x180009ecd  jz      loc_18000A791
0x180009ed3  mov     qword ptr [rdx], 22h ; '"'
0x180009eda  mov     [rdx+10h], r14
0x180009ede  mov     [rdx+18h], rdi
0x180009ee2  mov     [rdx+20h], rsi
0x180009ee6  test    rdi, rdi
0x180009ee9  jz      loc_18000A297
0x180009eef  mov     eax, [rdi+8]
0x180009ef2  mov     [rdx+8], eax
0x180009ef5  test    rsi, rsi
0x180009ef8  jz      loc_18000A303
0x180009efe  mov     ecx, [rsi+0Ch]
0x180009f01  mov     rdi, rdx
0x180009f04  mov     [rdx+0Ch], ecx
0x180009f07  jmp     short loc_180009F5C
0x180009f09  mov     edx, 1
0x180009f0e  mov     rcx, rbx
0x180009f11  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z; Parser::CreateNode(OpCode)
0x180009f16  mov     rsi, rax
0x180009f19  mov     [rax+10h], rdi
0x180009f1d  mov     rcx, [rbx+160h]
0x180009f24  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180009f29  mov     ecx, [rbx+150h]
0x180009f2f  add     ecx, 0FFFFFFBBh
0x180009f32  cmp     ecx, 36h ; '6'
0x180009f35  ja      loc_18000A71E
0x180009f3b  mov     rax, 40000000010001h
0x180009f45  bt      rax, rcx
0x180009f49  jnb     loc_18000A71E
0x180009f4f  xor     edx, edx; jumptable 0000000180009E3D case 68
0x180009f51  mov     rcx, rbx; this
0x180009f54  call    ?ParseFncDecl@Parser@@AEAAPEAUParseNode@@K@Z; Parser::ParseFncDecl(ulong)
0x180009f59  mov     rdi, rax
0x180009f5c  mov     eax, [rbx+150h]
0x180009f62  cmp     eax, 34h ; '4'
0x180009f65  jnz     loc_18000A1E7
0x180009f6b  mov     rax, rdi; jumptable 000000018000A20B cases 55,158,183,184
0x180009f6e  mov     r14, [rsp+48h+var_20]
0x180009f73  mov     r13, [rsp+48h+var_18]
0x180009f78  mov     r12, [rsp+48h+var_10]
0x180009f7d  mov     rdi, [rsp+48h+arg_10]
0x180009f82  mov     rsi, [rsp+48h+arg_8]
0x180009f87  mov     rbp, [rsp+48h+arg_0]
0x180009f8c  mov     r15, [rsp+48h+var_28]
0x180009f91  add     rsp, 40h
0x180009f95  pop     rbx
0x180009f96  retn
0x180009f97  xor     eax, eax
0x180009f99  jmp     short loc_180009F6E
0x180009f9b  cmp     qword ptr [rbx+180h], 0
0x180009fa3  jz      loc_180009DF3; jumptable 0000000180009FD3 cases 47,55,68,109,112,116,132,156,158,183,184
0x180009fa9  mov     eax, [rbx+150h]
0x180009faf  add     eax, 0FFFFFFD1h; switch 138 cases
0x180009fb2  cmp     eax, 89h
0x180009fb7  ja      def_180009FD3; jumptable 0000000180009FD3 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x180009fbd  cdqe
0x180009fbf  movzx   eax, ds:(byte_18000A8F8 - 180000000h)[r12+rax]
0x180009fc8  mov     ecx, ds:(jpt_180009FD3 - 180000000h)[r12+rax*4]
0x180009fd0  add     rcx, r12
0x180009fd3  jmp     rcx; switch jump
0x180009fd5  mov     rcx, [rbx+160h]; jumptable 0000000180009E3D case 144
0x180009fdc  mov     rdi, [rcx+20h]
0x180009fe0  sub     rdi, [rcx+10h]
0x180009fe4  sar     rdi, 1
0x180009fe7  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x180009fec  mov     r8d, edi
0x180009fef  mov     edx, 33h ; '3'
0x180009ff4  mov     rcx, rbx
0x180009ff7  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@J@Z; Parser::CreateNode(OpCode,long)
0x180009ffc  mov     rdi, rax
0x180009fff  xor     r8d, r8d; struct ParseNode *
0x18000a002  mov     eax, [rbx+1E0h]
0x18000a008  xor     edx, edx; int
0x18000a00a  mov     rcx, rbx; this
0x18000a00d  mov     [rdi+28h], eax
0x18000a010  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x18000a015  mov     [rdi+18h], rax
0x18000a019  test    rax, rax
0x18000a01c  jz      short loc_18000A024
0x18000a01e  mov     eax, [rax+0Ch]
0x18000a021  mov     [rdi+0Ch], eax
0x18000a024  mov     rax, [rbx+1C0h]
0x18000a02b  lea     r8, [rdi+20h]
0x18000a02f  mov     [rdi+10h], rax
0x18000a033  xor     r9d, r9d
0x18000a036  mov     edx, 8Fh
0x18000a03b  mov     [rbx+1C0h], rdi
0x18000a042  mov     rcx, rbx
0x18000a045  call    ?ParseStmtList@Parser@@AEAAXW4tokens@@PEAPEAUParseNode@@PEAPEAPEAU3@@Z; Parser::ParseStmtList(tokens,ParseNode * *,ParseNode * * *)
0x18000a04a  cmp     dword ptr [rbx+150h], 8Fh
0x18000a054  jz      loc_18000A21E
0x18000a05a  mov     edx, 3FAh; int
0x18000a05f  mov     rcx, rbx; this
0x18000a062  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18000a068  mov     rcx, rbx; jumptable 0000000180009E3D cases 26,47,109,112,115
0x18000a06b  call    ?ParseVarDecl@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseVarDecl(void)
0x18000a070  jmp     loc_180009F59
0x18000a075  cmp     dword ptr [rdi], 20h ; ' '
0x18000a078  jz      loc_18000A165
0x18000a07e  cmp     ecx, 9Ch
0x18000a084  jnz     loc_18000A7AD
0x18000a08a  xor     r9d, r9d
0x18000a08d  mov     r8, rdi
0x18000a090  mov     edx, 20h ; ' '
0x18000a095  mov     rcx, rbx
0x18000a098  call    ?CreateBinNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@PEAU2@1@Z; Parser::CreateBinNode(OpCode,ParseNode *,ParseNode *)
0x18000a09d  jmp     loc_180009F59
0x18000a0a2  mov     rcx, rbx; jumptable 0000000180009E3D case 66
0x18000a0a5  call    ?ParseForStmt@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseForStmt(void)
0x18000a0aa  jmp     loc_180009F59
0x18000a0af  mov     r13d, [rbx+24h]
0x18000a0b3  cmp     r13d, 28h ; '('
0x18000a0b7  jle     loc_18000A75E
0x18000a0bd  mov     ecx, [rbx+20h]
0x18000a0c0  mov     eax, 28h ; '('
0x18000a0c5  cmp     r15d, eax
0x18000a0c8  cmovg   eax, r15d
0x18000a0cc  add     eax, eax
0x18000a0ce  cmp     ecx, eax
0x18000a0d0  cmovle  ecx, eax
0x18000a0d3  cmp     ecx, r13d
0x18000a0d6  jle     loc_18000A311
0x18000a0dc  lea     eax, [r13+8]
0x18000a0e0  cmp     eax, r13d
0x18000a0e3  jl      loc_18000A791
0x18000a0e9  cmp     eax, 28h ; '('
0x18000a0ec  jl      loc_18000A791
0x18000a0f2  mov     ecx, r13d
0x18000a0f5  add     rcx, 8; Size
0x18000a0f9  call    cs:__imp_malloc
0x18000a0ff  test    rax, rax
0x18000a102  jz      loc_18000A791
0x18000a108  mov     rcx, [rbx+10h]
0x18000a10c  mov     ebp, r14d
0x18000a10f  mov     [rax], rcx
0x18000a112  mov     [rbx+10h], rax
0x18000a116  mov     [rbx+1Ch], r13d
0x18000a11a  jmp     loc_180009EB9
0x18000a11f  mov     rcx, [rbx+160h]; jumptable 0000000180009E3D case 123
0x18000a126  mov     rsi, [rcx+20h]
0x18000a12a  mov     rbp, [rcx+10h]
0x18000a12e  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000a133  mov     rcx, rbx; this
0x18000a136  call    ?ParseTerm@Parser@@AEAAPEAUParseNode@@XZ; Parser::ParseTerm(void)
0x18000a13b  mov     rdi, rax
0x18000a13e  cmp     dword ptr [rax], 7
0x18000a141  jz      loc_18000A5F5
0x18000a147  cmp     dword ptr [rbx+150h], 0A4h
0x18000a151  jz      loc_18000A2C9
0x18000a157  mov     edx, 3F3h; int
0x18000a15c  mov     rcx, rbx; this
0x18000a15f  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18000a165  mov     rax, [rdi+20h]
0x18000a169  test    rax, rax
0x18000a16c  jz      loc_180009F5C
0x18000a172  cmp     dword ptr [rax], 2Bh ; '+'
0x18000a175  jz      loc_18000A79F
0x18000a17b  or      dword ptr [rax+4], 1
0x18000a17f  mov     ecx, [rbx+150h]
0x18000a185  call    ?KwdOfTok@HashTbl@@CAPEBUKWD@1@W4tokens@@@Z; HashTbl::KwdOfTok(tokens)
0x18000a18a  test    rax, rax
0x18000a18d  jz      short loc_18000A1A1
0x18000a18f  mov     r8, [rdi+20h]; struct ParseNode *
0x18000a193  xor     edx, edx; int
0x18000a195  mov     rcx, rbx; this
0x18000a198  call    ?ParseExpr@Parser@@AEAAPEAUParseNode@@HPEAU2@@Z; Parser::ParseExpr(int,ParseNode *)
0x18000a19d  mov     [rdi+20h], rax
0x18000a1a1  cmp     dword ptr [rbx+150h], 9Bh
0x18000a1ab  jnz     loc_180009F5C
0x18000a1b1  mov     rcx, [rbx+160h]
0x18000a1b8  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000a1bd  mov     edx, 0B7h
0x18000a1c2  mov     rcx, rbx
0x18000a1c5  call    ?ParseArgList@Parser@@AEAAPEAUParseNode@@W4tokens@@@Z; Parser::ParseArgList(tokens)
0x18000a1ca  mov     r8, [rdi+20h]
0x18000a1ce  mov     r9, rax
0x18000a1d1  mov     edx, 2Bh ; '+'
0x18000a1d6  mov     rcx, rbx
0x18000a1d9  call    ?CreateBinNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@PEAU2@1@Z; Parser::CreateBinNode(OpCode,ParseNode *,ParseNode *)
0x18000a1de  mov     [rdi+20h], rax
0x18000a1e2  jmp     loc_180009F5C
0x18000a1e7  add     eax, 0FFFFFFC9h; switch 130 cases
0x18000a1ea  cmp     eax, 81h
0x18000a1ef  ja      def_18000A20B; jumptable 000000018000A20B default case, cases 56-115,117-155,157,159-182
0x18000a1f5  cdqe
0x18000a1f7  movzx   eax, ds:(byte_18000A990 - 180000000h)[r12+rax]
0x18000a200  mov     ecx, ds:(jpt_18000A20B - 180000000h)[r12+rax*4]
0x18000a208  add     rcx, r12
0x18000a20b  jmp     rcx; switch jump
0x18000a20d  mov     rcx, [rbx+160h]; jumptable 000000018000A20B cases 116,156
0x18000a214  call    ?SkipToEOL@Scanner@@QEAAXXZ; Scanner::SkipToEOL(void)
0x18000a219  jmp     loc_180009F6B; jumptable 000000018000A20B cases 55,158,183,184
0x18000a21e  mov     rcx, [rbx+160h]
0x18000a225  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000a22a  mov     rax, [rdi+10h]
0x18000a22e  mov     [rbx+1C0h], rax
0x18000a235  jmp     loc_180009F5C
0x18000a23a  mov     edx, 40h ; '@'; jumptable 0000000180009E3D case 101
0x18000a23f  mov     rcx, rbx
0x18000a242  call    ?CreateNode@Parser@@AEAAPEAUParseNode@@W4OpCode@@@Z; Parser::CreateNode(OpCode)
0x18000a247  mov     rcx, [rbx+160h]
0x18000a24e  mov     rdi, rax
0x18000a251  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000a256  cmp     eax, 95h
0x18000a25b  jnz     short def_180009FD3; jumptable 0000000180009FD3 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x18000a25d  mov     rax, [rbx+158h]
0x18000a264  cmp     word ptr [rax+8], 3Ch ; '<'
0x18000a269  jnz     short def_180009FD3; jumptable 0000000180009FD3 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x18000a26b  mov     rcx, [rbx+160h]
0x18000a272  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000a277  cmp     eax, 48h ; 'H'
0x18000a27a  jz      loc_18000A693
0x18000a280  cmp     eax, 75h ; 'u'
0x18000a283  jz      loc_18000A653
0x18000a289  mov     edx, 3EAh; jumptable 0000000180009FD3 default case, cases 48-54,56-67,69-108,110,111,113-115,117-131,133-148,150-155,157,159-182
0x18000a28e  mov     rcx, rbx; this
0x18000a291  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18000a297  mov     rax, [rbx+160h]
0x18000a29e  mov     rdi, rdx
0x18000a2a1  mov     rcx, [rax+20h]
0x18000a2a5  sub     rcx, [rax+10h]
0x18000a2a9  sar     rcx, 1
0x18000a2ac  mov     [rdx+8], ecx
0x18000a2af  mov     rax, [rbx+160h]
0x18000a2b6  mov     rcx, [rax+28h]
0x18000a2ba  sub     rcx, [rax+10h]
0x18000a2be  sar     rcx, 1
0x18000a2c1  mov     [rdx+0Ch], ecx
0x18000a2c4  jmp     loc_180009F5C
0x18000a2c9  mov     rcx, [rbx+160h]
0x18000a2d0  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18000a2d5  xor     r8d, r8d; struct ParseNode *
0x18000a2d8  xor     edx, edx; int
  ... truncated ...
```
