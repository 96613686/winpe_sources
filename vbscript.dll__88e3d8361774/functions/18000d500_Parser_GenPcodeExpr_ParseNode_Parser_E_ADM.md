# Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)

- ea: `0x18000d500`
- end: `0x18000e040`
- name: `?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z`
- size: `2880`
- prototype: ``
- caller_count: `8`
- callee_count: `12`
- tags: ``

## callers

- `0x18000d500`
- `0x1800134fc`
- `0x180013698`
- `0x180013dc0`
- `0x18001477c`
- `0x180015700`
- `0x180016188`
- `0x1800350cc`

## callees

- `0x180008fc0`
- `0x18000d4dc`
- `0x18000d500`
- `0x18001349c`
- `0x180013ab0`
- `0x180013b80`
- `0x180013c00`
- `0x180015270`
- `0x180015588`
- `0x1800158bc`
- `0x1800350cc`
- `0x18005d058`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000deee`
- `msvcrt!_wcsnicmp` at `0x18000df15`
- `msvcrt!_wcsnicmp` at `0x18000df67`
- `msvcrt!_wcsnicmp` at `0x18000deee`
- `msvcrt!_wcsnicmp` at `0x18000df15`
- `msvcrt!_wcsnicmp` at `0x18000df67`

## string_xrefs

- `0x18000df00`: `write`
- `0x18000df52`: `WriteBlock`

## pseudocode

```c
void __fastcall Parser::GenPcodeExpr(__int64 a1, int *a2, signed int a3)
{
  __int64 v3; // rdi
  signed int v4; // r14d
  int *v5; // rsi
  signed int v6; // ebx
  __int64 v7; // rbp
  int v8; // eax
  __int64 v9; // r15
  __int64 v10; // r14
  __int64 v11; // rsi
  unsigned int i; // ebp
  __int64 v13; // rsi
  __int64 v14; // rax
  __int64 v15; // rbx
  int v16; // edx
  __int16 v17; // cx
  int v18; // ecx
  _QWORD *v19; // rax
  int v20; // ebx
  __int16 v21; // bx
  _WORD *v22; // rcx
  __int64 v23; // rsi
  __int64 v24; // rdx
  int v25; // ebp
  int v26; // ecx
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rbx
  char v30; // si
  int v31; // edx
  _WORD *v32; // rcx
  int v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  int v37; // edx
  __int64 v38; // rbx
  char v39; // bp
  int v40; // edx
  __int16 v41; // cx
  int v42; // ecx
  _QWORD *v43; // rax
  int v44; // ebx
  __int64 v45; // rbx
  int v46; // edx
  __int16 v47; // cx
  _QWORD *v48; // rax
  int v49; // ebx
  int v50; // ebx
  int v51; // edx
  _BYTE *v52; // rcx
  __int64 v53; // rsi
  char v54; // r15
  __int64 v55; // rbx
  int v56; // edx
  __int16 v57; // cx
  int v58; // ecx
  _QWORD *v59; // rax
  int v60; // ebx
  __int64 v61; // rbp
  char v62; // r14
  int *v63; // rbx
  int v64; // edx
  int *v65; // rbx
  int v66; // edx
  __int64 v67; // r8
  __int64 v68; // rdx

?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z:
  v3 = a1;
  v4 = a3;
  v5 = a2;
  if ( !(unsigned int)FStackAvailable(0x2000u) )
    goto LABEL_2;
  while ( 1 )
  {
    v6 = v4;
    if ( v4 == 1 )
      v6 = (v5[1] & 1) == 0;
    v7 = *v5;
    v8 = *((_DWORD *)&ParseNode::mpnopgrfnop + v7);
    if ( (v8 & 2) != 0 )
    {
      if ( (_DWORD)v7 != 1 )
      {
        if ( (_DWORD)v7 == 4 )
        {
          v45 = *((_QWORD *)v5 + 2);
          *Parser::PvGen((Parser *)v3, 1) = 14;
          ++*(_DWORD *)(v3 + 600);
          goto LABEL_59;
        }
        switch ( (int)v7 )
        {
          case 2:
            v50 = v5[4];
            if ( (char)v50 == v50 )
            {
              *Parser::PvGen((Parser *)v3, 1) = 11;
              v51 = ++*(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
              if ( *(_DWORD *)(v3 + 596) < v51 )
                *(_DWORD *)(v3 + 596) = v51;
              if ( (__int64)(*(_QWORD *)(v3 + 560) - *(_QWORD *)(v3 + 552)) < 1 )
                Parser::AllocBlob((Parser *)v3, 1);
              v52 = *(_BYTE **)(v3 + 552);
              ++*(_DWORD *)(v3 + 568);
              *(_QWORD *)(v3 + 552) = v52 + 1;
              *v52 = v50;
            }
            else
            {
              Parser::GenPcode(v3, 12);
              *(_DWORD *)Parser::PvGen((Parser *)v3, 4) = v50;
            }
            break;
          case 3:
            Parser::GenPcode_DBL(v3, 13);
            break;
          case 5:
            Parser::GenPcode_DBL(v3, 15);
            break;
          case 6:
            v34 = 23;
            goto LABEL_111;
          case 7:
            v34 = (unsigned int)dword_180080208[v6];
            goto LABEL_111;
          case 8:
          case 9:
          case 10:
          case 11:
          case 12:
          case 13:
            v34 = (unsigned int)dword_1800800E0[v7];
            goto LABEL_111;
          case 14:
            Parser::GenPcode_NM(v3, 90, *((_QWORD *)v5 + 2));
            break;
          default:
            return;
        }
        return;
      }
      v23 = *((_QWORD *)v5 + 2);
      if ( *(_DWORD *)(v23 + 20) != *(_DWORD *)(v3 + 328) )
        goto LABEL_51;
      v24 = *(_QWORD *)(v23 + 24);
      v25 = 0;
      v26 = 0;
      if ( !v24 )
        goto LABEL_34;
      v27 = *(_DWORD *)(v24 + 4);
      if ( (v27 & 0x400) == 0 )
      {
        v25 = *(_DWORD *)(v24 + 24);
        if ( v25 || (v27 & 0x2000) != 0 )
        {
          v26 = 1;
LABEL_34:
          v28 = 4LL * v6;
          if ( v26 )
          {
            v29 = *(int *)((char *)&qword_180080088[2] + v28);
            if ( (unsigned __int8)v29 == (_DWORD)v29 )
            {
              v30 = *(_DWORD *)((char *)&qword_180080088[2] + v28);
              *Parser::PvGen((Parser *)v3, 1) = v30;
              *(_DWORD *)(v3 + 600) += *((char *)&qword_18007D080 + v29);
              v31 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
              if ( *(_DWORD *)(v3 + 596) < v31 )
                *(_DWORD *)(v3 + 596) = v31;
              if ( (__int16)v25 == v25 )
              {
                if ( (__int64)(*(_QWORD *)(v3 + 560) - *(_QWORD *)(v3 + 552)) < 2 )
                  Parser::AllocBlob((Parser *)v3, 2);
                v32 = *(_WORD **)(v3 + 552);
                *(_DWORD *)(v3 + 568) += 2;
                *(_QWORD *)(v3 + 552) = v32 + 1;
                *v32 = v25;
                return;
              }
            }
            goto LABEL_2;
          }
        }
        else
        {
LABEL_51:
          v28 = 4LL * v6;
        }
        v38 = *(int *)((char *)&qword_1800800B8[2] + v28);
        if ( (unsigned __int8)v38 == (_DWORD)v38 )
        {
          v39 = *(_DWORD *)((char *)&qword_1800800B8[2] + v28);
          *Parser::PvGen((Parser *)v3, 1) = v39;
          *(_DWORD *)(v3 + 600) += *((char *)&qword_18007D080 + v38);
          v40 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
          if ( *(_DWORD *)(v3 + 596) < v40 )
            *(_DWORD *)(v3 + 596) = v40;
          v41 = *(_WORD *)(v23 + 10);
          if ( (v41 & 0x4000) == 0 )
          {
            *(_WORD *)(v23 + 10) = v41 | 0x4000;
            v42 = *(_DWORD *)(v23 + 40);
            *(_DWORD *)(v23 + 16) = *(_DWORD *)(v3 + 612) + 8;
            v43 = *(_QWORD **)(v3 + 632);
            *(_DWORD *)(v3 + 612) = (*(_DWORD *)(v3 + 612) + 13 + 2 * v42) & 0xFFFFFFFC;
            *v43 = v23;
            *(_QWORD *)(v3 + 632) = v23 + 32;
          }
          v44 = *(_DWORD *)(v23 + 16);
          *(_DWORD *)Parser::PvGen((Parser *)v3, 4) = v44;
          return;
        }
        goto LABEL_2;
      }
      if ( (unsigned int)v6 > 1 )
        goto LABEL_34;
      a2 = *(int **)(v24 + 40);
      a3 = v6;
      a1 = v3;
      goto ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z;
    }
    if ( (v8 & 0x20) != 0 )
    {
      Parser::GenPcodeExpr(v3, *((_QWORD *)v5 + 4), 1);
      v33 = *(_DWORD *)(v3 + 600);
      Parser::GenPcodeExpr(v3, *((_QWORD *)v5 + 3), (unsigned int)((_DWORD)v7 == 35) + 3);
      if ( v33 != *(_DWORD *)(v3 + 600) + 1 )
      {
        v34 = 57;
LABEL_111:
        Parser::GenPcode(v3, v34);
      }
      return;
    }
    v9 = dword_1800800E0[v7];
    if ( (_DWORD)v9 )
    {
      v35 = v3;
      if ( (v8 & 0x10) != 0 )
      {
        v63 = (int *)*((_QWORD *)v5 + 3);
        Parser::GenPcodeExpr(v3, v63, 1);
        if ( (*((_BYTE *)&ParseNode::mpnopgrfnop + 4 * *v63) & 1) != 0 )
        {
          Parser::Gen_byte((Parser *)v3, 84);
          v64 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
          if ( *(_DWORD *)(v3 + 596) < v64 )
            *(_DWORD *)(v3 + 596) = v64;
        }
        v65 = (int *)*((_QWORD *)v5 + 4);
        Parser::GenPcodeExpr(v3, v65, 1);
        if ( (*((_BYTE *)&ParseNode::mpnopgrfnop + 4 * *v65) & 1) != 0 )
        {
          Parser::Gen_byte((Parser *)v3, 84);
          v66 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
          if ( *(_DWORD *)(v3 + 596) < v66 )
            *(_DWORD *)(v3 + 596) = v66;
        }
      }
      else
      {
        if ( (v8 & 4) != 0 )
        {
          v36 = *((_QWORD *)v5 + 2);
        }
        else
        {
          Parser::GenPcodeExpr(v3, *((_QWORD *)v5 + 3), 1);
          v36 = *((_QWORD *)v5 + 4);
          v35 = v3;
        }
        Parser::GenPcodeExpr(v35, v36, 1);
      }
      if ( (unsigned __int8)v9 == (_DWORD)v9 )
      {
        *Parser::PvGen((Parser *)v3, 1) = v9;
        *(_DWORD *)(v3 + 600) += *((char *)&qword_18007D080 + v9);
        v37 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
        if ( *(_DWORD *)(v3 + 596) < v37 )
          *(_DWORD *)(v3 + 596) = v37;
        return;
      }
LABEL_2:
      Parser::Error((Parser *)v3, 1001);
    }
    if ( (_DWORD)v7 == 32 )
    {
      v10 = *((_QWORD *)v5 + 3);
      v11 = *((_QWORD *)v5 + 4);
      if ( *(_DWORD *)v10 == 1 )
      {
        if ( v11 )
        {
          for ( i = 1; *(_DWORD *)v11 == 43; ++i )
          {
            Parser::GenPcodeExpr(v3, *(_QWORD *)(v11 + 24), 1);
            v11 = *(_QWORD *)(v11 + 32);
          }
          Parser::GenPcodeExpr(v3, v11, 1);
        }
        else
        {
          i = 0;
        }
        v13 = *(_QWORD *)(v10 + 16);
        if ( *(_DWORD *)(v13 + 20) == *(_DWORD *)(v3 + 328) )
        {
          v14 = *(_QWORD *)(v13 + 24);
          if ( v14 )
          {
            v67 = *(unsigned int *)(v14 + 24);
            if ( (_DWORD)v67 )
            {
              Parser::GenPcode_LCCV(v3, (unsigned int)dword_1800800B0[v6], v67, i);
              goto LABEL_28;
            }
          }
        }
        v15 = dword_180080068[v6];
        if ( (unsigned __int8)v15 != (_DWORD)v15 )
          goto LABEL_2;
        *Parser::PvGen((Parser *)v3, 1) = v15;
        *(_DWORD *)(v3 + 600) += *((char *)&qword_18007D080 + v15);
        v16 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
        if ( *(_DWORD *)(v3 + 596) < v16 )
          *(_DWORD *)(v3 + 596) = v16;
        v17 = *(_WORD *)(v13 + 10);
        if ( (v17 & 0x4000) == 0 )
        {
          *(_WORD *)(v13 + 10) = v17 | 0x4000;
          v18 = *(_DWORD *)(v13 + 40);
          *(_DWORD *)(v13 + 16) = *(_DWORD *)(v3 + 612) + 8;
          v19 = *(_QWORD **)(v3 + 632);
          *(_DWORD *)(v3 + 612) = (*(_DWORD *)(v3 + 612) + 13 + 2 * v18) & 0xFFFFFFFC;
          *v19 = v13;
          *(_QWORD *)(v3 + 632) = v13 + 32;
        }
        v20 = *(_DWORD *)(v13 + 16);
        *(_DWORD *)Parser::PvGen((Parser *)v3, 4) = v20;
        v21 = i;
        if ( (unsigned __int16)i != i )
          goto LABEL_2;
        if ( (__int64)(*(_QWORD *)(v3 + 560) - *(_QWORD *)(v3 + 552)) >= 2 )
        {
LABEL_27:
          v22 = *(_WORD **)(v3 + 552);
          *(_DWORD *)(v3 + 568) += 2;
          *(_QWORD *)(v3 + 552) = v22 + 1;
          *v22 = v21;
LABEL_28:
          *(_DWORD *)(v3 + 600) -= i;
          return;
        }
      }
      else
      {
        if ( *(_DWORD *)v10 != 33 )
        {
          Parser::GenPcodeExpr(v3, v10, 1);
          if ( v11 )
          {
            for ( i = 1; *(_DWORD *)v11 == 43; ++i )
            {
              Parser::GenPcodeExpr(v3, *(_QWORD *)(v11 + 24), 1);
              v11 = *(_QWORD *)(v11 + 32);
            }
            Parser::GenPcodeExpr(v3, v11, 1);
          }
          else
          {
            i = 0;
          }
          Parser::GenPcode(v3, (unsigned int)dword_1800801F0[v6]);
          Parser::Gen_ushort((Parser *)v3, i);
          goto LABEL_28;
        }
        if ( *(_QWORD *)v3 )
        {
          if ( v6 == 2 )
          {
            v68 = *(_QWORD *)(v10 + 24);
            if ( *(_DWORD *)v68 == 1 && !_wcsnicmp(L"Response", (const wchar_t *)(*(_QWORD *)(v68 + 16) + 44LL), 9u) )
            {
              if ( !_wcsnicmp(L"write", (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v10 + 32) + 16LL) + 44LL), 6u)
                && v11
                && *(_DWORD *)v11 != 43 )
              {
                i = Parser::GenExprList(v3, v11, 1);
                Parser::GenPcode(v3, 110);
                goto LABEL_28;
              }
              if ( !_wcsnicmp(L"WriteBlock", (const wchar_t *)(*(_QWORD *)(*(_QWORD *)(v10 + 32) + 16LL) + 44LL), 0xBu)
                && v11
                && *(_DWORD *)v11 != 43 )
              {
                i = Parser::GenExprList(v3, v11, 1);
                Parser::GenPcode(v3, 111);
                goto LABEL_28;
              }
            }
          }
        }
        Parser::GenPcodeExpr(v3, *(_QWORD *)(v10 + 24), 1);
        if ( v11 )
        {
          for ( i = 1; *(_DWORD *)v11 == 43; ++i )
          {
            Parser::GenPcodeExpr(v3, *(_QWORD *)(v11 + 24), 1);
            v11 = *(_QWORD *)(v11 + 32);
          }
          Parser::GenPcodeExpr(v3, v11, 1);
        }
        else
        {
          i = 0;
        }
        v53 = dword_180080050[v6];
        v54 = dword_180080050[v6];
        if ( (unsigned __int8)v53 != (_DWORD)v53 )
          goto LABEL_2;
        v55 = *(_QWORD *)(*(_QWORD *)(v10 + 32) + 16LL);
        *Parser::PvGen((Parser *)v3, 1) = v54;
        *(_DWORD *)(v3 + 600) += *((char *)&qword_18007D080 + v53);
        v56 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
        if ( *(_DWORD *)(v3 + 596) < v56 )
          *(_DWORD *)(v3 + 596) = v56;
        v57 = *(_WORD *)(v55 + 10);
        if ( (v57 & 0x4000) == 0 )
        {
          *(_WORD *)(v55 + 10) = v57 | 0x4000;
          v58 = *(_DWORD *)(v55 + 40);
          *(_DWORD *)(v55 + 16) = *(_DWORD *)(v3 + 612) + 8;
          v59 = *(_QWORD **)(v3 + 632);
          *(_DWORD *)(v3 + 612) = (*(_DWORD *)(v3 + 612) + 13 + 2 * v58) & 0xFFFFFFFC;
          *v59 = v55;
          *(_QWORD *)(v3 + 632) = v55 + 32;
        }
        v60 = *(_DWORD *)(v55 + 16);
        *(_DWORD *)Parser::PvGen((Parser *)v3, 4) = v60;
        v21 = i;
        if ( (unsigned __int16)i != i )
          goto LABEL_2;
        if ( (__int64)(*(_QWORD *)(v3 + 560) - *(_QWORD *)(v3 + 552)) >= 2 )
          goto LABEL_27;
      }
      Parser::AllocBlob((Parser *)v3, 2);
      goto LABEL_27;
    }
    if ( (_DWORD)v7 == 33 )
      break;
    if ( (_DWORD)v7 == 17 )
    {
      v5 = (int *)*((_QWORD *)v5 + 2);
    }
    else
    {
      if ( (_DWORD)v7 != 43 )
        return;
      Parser::GenPcodeExpr(v3, *((_QWORD *)v5 + 3), 1);
      v5 = (int *)*((_QWORD *)v5 + 4);
    }
  }
  Parser::GenPcodeExpr(v3, *((_QWORD *)v5 + 3), 1);
  v61 = dword_180080080[v6];
  v62 = dword_180080080[v6];
  if ( (unsigned __int8)v61 != (_DWORD)v61 )
    goto LABEL_2;
  v45 = *(_QWORD *)(*((_QWORD *)v5 + 4) + 16LL);
  *Parser::PvGen((Parser *)v3, 1) = v62;
  *(_DWORD *)(v3 + 600) += *((char *)&qword_18007D080 + v61);
LABEL_59:
  v46 = *(_DWORD *)(v3 + 600) + *(_DWORD *)(v3 + 604);
  if ( *(_DWORD *)(v3 + 596) < v46 )
    *(_DWORD *)(v3 + 596) = v46;
  v47 = *(_WORD *)(v45 + 10);
  if ( (v47 & 0x4000) == 0 )
  {
    *(_WORD *)(v45 + 10) = v47 | 0x4000;
    *(_DWORD *)(v45 + 16) = *(_DWORD *)(v3 + 612) + 8;
    v48 = *(_QWORD **)(v3 + 632);
    *(_DWORD *)(v3 + 612) = (*(_DWORD *)(v3 + 612) + 13 + 2 * *(_DWORD *)(v45 + 40)) & 0xFFFFFFFC;
    *v48 = v45;
    *(_QWORD *)(v3 + 632) = v45 + 32;
  }
  v49 = *(_DWORD *)(v45 + 16);
  *(_DWORD *)Parser::PvGen((Parser *)v3, 4) = v49;
}

```

## disassembly

```asm
0x18000d500  push    rbx
0x18000d502  push    rbp
0x18000d503  push    rsi
0x18000d504  push    rdi
0x18000d505  push    r12
0x18000d507  push    r14
0x18000d509  push    r15
0x18000d50b  sub     rsp, 20h
0x18000d50f  mov     rdi, rcx
0x18000d512  mov     r14d, r8d
0x18000d515  mov     ecx, 2000h; unsigned int
0x18000d51a  mov     rsi, rdx
0x18000d51d  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x18000d522  test    eax, eax
0x18000d524  jnz     loc_18000DEAE
0x18000d52a  mov     edx, 3E9h; int
0x18000d52f  mov     rcx, rdi; this
0x18000d532  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18000d540  mov     ebx, r14d
0x18000d543  cmp     r14d, 1
0x18000d547  jnz     short loc_18000D555
0x18000d549  test    [rsi+4], r14b
0x18000d54d  mov     eax, 0
0x18000d552  cmovnz  ebx, eax
0x18000d555  movsxd  rbp, dword ptr [rsi]
0x18000d558  mov     rdx, rbp
0x18000d55b  mov     eax, ds:rva ?mpnopgrfnop@ParseNode@@2QBIB[r12+rbp*4]; uint const near * const ParseNode::mpnopgrfnop ...
0x18000d563  test    al, 2
0x18000d565  jz      short loc_18000D594
0x18000d567  cmp     ebp, 1
0x18000d56a  jz      loc_18000D72C
0x18000d570  cmp     ebp, 4
0x18000d573  jz      loc_18000D9B4
0x18000d579  add     ebp, 0FFFFFFFEh; switch 13 cases
0x18000d57c  cmp     ebp, 0Ch
0x18000d57f  jbe     loc_18000DA57
0x18000d585  add     rsp, 20h; jumptable 000000018000DA65 default case, case 4
0x18000d589  pop     r15
0x18000d58b  pop     r14
0x18000d58d  pop     r12
0x18000d58f  pop     rdi
0x18000d590  pop     rsi
0x18000d591  pop     rbp
0x18000d592  pop     rbx
0x18000d593  retn
0x18000d594  test    al, 20h
0x18000d596  jnz     loc_18000D816
0x18000d59c  movsxd  r15, ds:rva dword_1800800E0[r12+rbp*4]
0x18000d5a4  test    r15d, r15d
0x18000d5a7  jnz     loc_18000D862
0x18000d5ad  cmp     ebp, 20h ; ' '
0x18000d5b0  jnz     loc_18000DC3A
0x18000d5b6  mov     r14, [rsi+18h]
0x18000d5ba  mov     rsi, [rsi+20h]
0x18000d5be  mov     ecx, [r14]
0x18000d5c1  sub     ecx, 1
0x18000d5c4  jnz     loc_18000DAE6
0x18000d5ca  test    rsi, rsi
0x18000d5cd  jz      loc_18000DE87
0x18000d5d3  cmp     dword ptr [rsi], 2Bh ; '+'
0x18000d5d6  mov     ebp, 1
0x18000d5db  jnz     short loc_18000D5FA
0x18000d5dd  mov     rdx, [rsi+18h]
0x18000d5e1  mov     r8d, 1
0x18000d5e7  mov     rcx, rdi
0x18000d5ea  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000d5ef  mov     rsi, [rsi+20h]
0x18000d5f3  inc     ebp
0x18000d5f5  cmp     dword ptr [rsi], 2Bh ; '+'
0x18000d5f8  jz      short loc_18000D5DD
0x18000d5fa  mov     r8d, 1
0x18000d600  mov     rdx, rsi
0x18000d603  mov     rcx, rdi
0x18000d606  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000d60b  mov     rsi, [r14+10h]
0x18000d60f  mov     eax, [rdi+148h]
0x18000d615  cmp     [rsi+14h], eax
0x18000d618  jnz     short loc_18000D627
0x18000d61a  mov     rax, [rsi+18h]
0x18000d61e  test    rax, rax
0x18000d621  jnz     loc_18000DE4A
0x18000d627  movsxd  rax, ebx
0x18000d62a  movsxd  rbx, ds:rva dword_180080068[r12+rax*4]
0x18000d632  movzx   r14d, bl
0x18000d636  cmp     r14d, ebx
0x18000d639  jnz     loc_18000D52A
0x18000d63f  mov     edx, 1; int
0x18000d644  mov     rcx, rdi; this
0x18000d647  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000d64c  mov     [rax], r14b
0x18000d64f  movsx   eax, byte ptr [rbx+r12+7D080h]
0x18000d658  add     [rdi+258h], eax
0x18000d65e  mov     edx, [rdi+25Ch]
0x18000d664  add     edx, [rdi+258h]
0x18000d66a  cmp     [rdi+254h], edx
0x18000d670  jge     short loc_18000D678
0x18000d672  mov     [rdi+254h], edx
0x18000d678  movzx   ecx, word ptr [rsi+0Ah]
0x18000d67c  mov     eax, 4000h
0x18000d681  test    ax, cx
0x18000d684  jnz     short loc_18000D6C6
0x18000d686  or      cx, ax
0x18000d689  mov     [rsi+0Ah], cx
0x18000d68d  mov     eax, [rdi+264h]
0x18000d693  mov     ecx, [rsi+28h]
0x18000d696  add     eax, 8
0x18000d699  mov     [rsi+10h], eax
0x18000d69c  mov     edx, [rdi+264h]
0x18000d6a2  mov     rax, [rdi+278h]
0x18000d6a9  add     edx, 0Dh
0x18000d6ac  lea     edx, [rdx+rcx*2]
0x18000d6af  and     edx, 0FFFFFFFCh
0x18000d6b2  mov     [rdi+264h], edx
0x18000d6b8  mov     [rax], rsi
0x18000d6bb  lea     rax, [rsi+20h]
0x18000d6bf  mov     [rdi+278h], rax
0x18000d6c6  mov     ebx, [rsi+10h]
0x18000d6c9  mov     edx, 4; int
0x18000d6ce  mov     rcx, rdi; this
0x18000d6d1  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000d6d6  mov     [rax], ebx
0x18000d6d8  movzx   ebx, bp
0x18000d6db  cmp     ebx, ebp
0x18000d6dd  jnz     loc_18000D52A
0x18000d6e3  mov     rax, [rdi+230h]
0x18000d6ea  sub     rax, [rdi+228h]
0x18000d6f1  cmp     rax, 2
0x18000d6f5  jl      loc_18000DC28
0x18000d6fb  mov     rcx, [rdi+228h]
0x18000d702  add     dword ptr [rdi+238h], 2
0x18000d709  lea     rax, [rcx+2]
0x18000d70d  mov     [rdi+228h], rax
0x18000d714  mov     [rcx], bx
0x18000d717  sub     [rdi+258h], ebp
0x18000d71d  add     rsp, 20h
0x18000d721  pop     r15
0x18000d723  pop     r14
0x18000d725  pop     r12
0x18000d727  pop     rdi
0x18000d728  pop     rsi
0x18000d729  pop     rbp
0x18000d72a  pop     rbx
0x18000d72b  retn
0x18000d72c  mov     rsi, [rsi+10h]
0x18000d730  mov     eax, [rdi+148h]
0x18000d736  cmp     [rsi+14h], eax
0x18000d739  jnz     loc_18000D8EE
0x18000d73f  mov     rdx, [rsi+18h]
0x18000d743  xor     ebp, ebp
0x18000d745  xor     ecx, ecx
0x18000d747  test    rdx, rdx
0x18000d74a  jz      short loc_18000D769
0x18000d74c  mov     eax, [rdx+4]
0x18000d74f  bt      eax, 0Ah
0x18000d753  jb      loc_18000DDFC
0x18000d759  mov     ebp, [rdx+18h]
0x18000d75c  test    ebp, ebp
0x18000d75e  jz      loc_18000DDA5
0x18000d764  mov     ecx, 1
0x18000d769  movsxd  rax, ebx
0x18000d76c  lea     rax, ds:0[rax*4]
0x18000d774  test    ecx, ecx
0x18000d776  jz      loc_18000D8F9
0x18000d77c  movsxd  rbx, dword ptr [rax+r12+80098h]
0x18000d784  movzx   esi, bl
0x18000d787  cmp     esi, ebx
0x18000d789  jnz     loc_18000D52A
0x18000d78f  mov     edx, 1; int
0x18000d794  mov     rcx, rdi; this
0x18000d797  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000d79c  mov     [rax], sil
0x18000d79f  movsx   eax, byte ptr [rbx+r12+7D080h]
0x18000d7a8  add     [rdi+258h], eax
0x18000d7ae  mov     edx, [rdi+25Ch]
0x18000d7b4  add     edx, [rdi+258h]
0x18000d7ba  cmp     [rdi+254h], edx
0x18000d7c0  jge     short loc_18000D7C8
0x18000d7c2  mov     [rdi+254h], edx
0x18000d7c8  movsx   eax, bp
0x18000d7cb  cmp     eax, ebp
0x18000d7cd  jnz     loc_18000D52A
0x18000d7d3  mov     rax, [rdi+230h]
0x18000d7da  sub     rax, [rdi+228h]
0x18000d7e1  cmp     rax, 2
0x18000d7e5  jl      loc_18000DE9C
0x18000d7eb  mov     rcx, [rdi+228h]
0x18000d7f2  add     dword ptr [rdi+238h], 2
0x18000d7f9  lea     rax, [rcx+2]
0x18000d7fd  mov     [rdi+228h], rax
0x18000d804  mov     [rcx], bp
0x18000d807  add     rsp, 20h
0x18000d80b  pop     r15
0x18000d80d  pop     r14
0x18000d80f  pop     r12
0x18000d811  pop     rdi
0x18000d812  pop     rsi
0x18000d813  pop     rbp
0x18000d814  pop     rbx
0x18000d815  retn
0x18000d816  mov     rdx, [rsi+20h]
0x18000d81a  mov     r8d, 1
0x18000d820  mov     rcx, rdi
0x18000d823  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000d828  mov     rdx, [rsi+18h]
0x18000d82c  xor     r8d, r8d
0x18000d82f  mov     ebx, [rdi+258h]
0x18000d835  cmp     ebp, 23h ; '#'
0x18000d838  mov     rcx, rdi
0x18000d83b  setz    r8b
0x18000d83f  add     r8d, 3
0x18000d843  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000d848  mov     eax, [rdi+258h]
0x18000d84e  inc     eax
0x18000d850  cmp     ebx, eax
0x18000d852  jz      def_18000DA65; jumptable 000000018000DA65 default case, case 4
0x18000d858  mov     edx, 39h ; '9'
0x18000d85d  jmp     loc_18000DE7A
0x18000d862  mov     r8d, 1
0x18000d868  mov     rcx, rdi
0x18000d86b  test    al, 10h
0x18000d86d  jnz     loc_18000DC99
0x18000d873  test    al, 4
0x18000d875  jnz     loc_18000DDF3
0x18000d87b  mov     rdx, [rsi+18h]
0x18000d87f  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000d884  mov     rdx, [rsi+20h]
0x18000d888  mov     r8d, 1
0x18000d88e  mov     rcx, rdi
0x18000d891  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000d896  movzx   ebx, r15b
0x18000d89a  cmp     ebx, r15d
0x18000d89d  jnz     loc_18000D52A
0x18000d8a3  mov     edx, 1; int
0x18000d8a8  mov     rcx, rdi; this
0x18000d8ab  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000d8b0  mov     [rax], bl
0x18000d8b2  movsx   eax, byte ptr [r15+r12+7D080h]
0x18000d8bb  add     [rdi+258h], eax
0x18000d8c1  mov     edx, [rdi+25Ch]
0x18000d8c7  add     edx, [rdi+258h]
0x18000d8cd  cmp     [rdi+254h], edx
0x18000d8d3  jge     def_18000DA65; jumptable 000000018000DA65 default case, case 4
0x18000d8d9  mov     [rdi+254h], edx
0x18000d8df  add     rsp, 20h
0x18000d8e3  pop     r15
0x18000d8e5  pop     r14
0x18000d8e7  pop     r12
0x18000d8e9  pop     rdi
0x18000d8ea  pop     rsi
0x18000d8eb  pop     rbp
0x18000d8ec  pop     rbx
0x18000d8ed  retn
0x18000d8ee  movsxd  rax, ebx
0x18000d8f1  lea     rax, ds:0[rax*4]
0x18000d8f9  movsxd  rbx, dword ptr [rax+r12+800C8h]
0x18000d901  movzx   ebp, bl
0x18000d904  cmp     ebp, ebx
0x18000d906  jnz     loc_18000D52A
0x18000d90c  mov     edx, 1; int
0x18000d911  mov     rcx, rdi; this
0x18000d914  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000d919  mov     [rax], bpl
0x18000d91c  movsx   eax, byte ptr [rbx+r12+7D080h]
0x18000d925  add     [rdi+258h], eax
0x18000d92b  mov     edx, [rdi+25Ch]
0x18000d931  add     edx, [rdi+258h]
0x18000d937  cmp     [rdi+254h], edx
0x18000d93d  jge     short loc_18000D945
0x18000d93f  mov     [rdi+254h], edx
0x18000d945  movzx   ecx, word ptr [rsi+0Ah]
0x18000d949  mov     eax, 4000h
0x18000d94e  test    ax, cx
0x18000d951  jnz     short loc_18000D993
0x18000d953  or      cx, ax
0x18000d956  mov     [rsi+0Ah], cx
0x18000d95a  mov     eax, [rdi+264h]
0x18000d960  mov     ecx, [rsi+28h]
0x18000d963  add     eax, 8
0x18000d966  mov     [rsi+10h], eax
0x18000d969  mov     edx, [rdi+264h]
0x18000d96f  mov     rax, [rdi+278h]
0x18000d976  add     edx, 0Dh
0x18000d979  lea     edx, [rdx+rcx*2]
0x18000d97c  and     edx, 0FFFFFFFCh
0x18000d97f  mov     [rdi+264h], edx
0x18000d985  mov     [rax], rsi
0x18000d988  lea     rax, [rsi+20h]
0x18000d98c  mov     [rdi+278h], rax
0x18000d993  mov     ebx, [rsi+10h]
0x18000d996  mov     edx, 4; int
0x18000d99b  mov     rcx, rdi; this
0x18000d99e  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000d9a3  mov     [rax], ebx
0x18000d9a5  add     rsp, 20h
0x18000d9a9  pop     r15
0x18000d9ab  pop     r14
0x18000d9ad  pop     r12
0x18000d9af  pop     rdi
0x18000d9b0  pop     rsi
0x18000d9b1  pop     rbp
  ... truncated ...
```
