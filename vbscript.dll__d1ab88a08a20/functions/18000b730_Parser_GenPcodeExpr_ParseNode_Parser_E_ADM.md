# Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)

- ea: `0x18000b730`
- end: `0x18000c28c`
- name: `?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z`
- size: `2908`
- prototype: ``
- caller_count: `8`
- callee_count: `12`
- tags: ``

## callers

- `0x18000b730`
- `0x180026cb0`
- `0x180026e4c`
- `0x180027590`
- `0x180027f68`
- `0x180028f38`
- `0x1800299d4`
- `0x1800364f4`

## callees

- `0x1800070c0`
- `0x18000b714`
- `0x18000b730`
- `0x180026c50`
- `0x180027270`
- `0x180027340`
- `0x1800273c0`
- `0x180028a80`
- `0x180028db4`
- `0x1800290f4`
- `0x1800364f4`
- `0x18005ec14`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000c12a`
- `msvcrt!_wcsnicmp` at `0x18000c157`
- `msvcrt!_wcsnicmp` at `0x18000c1af`
- `msvcrt!_wcsnicmp` at `0x18000c12a`
- `msvcrt!_wcsnicmp` at `0x18000c157`
- `msvcrt!_wcsnicmp` at `0x18000c1af`

## string_xrefs

- `0x18000c142`: `write`
- `0x18000c19a`: `WriteBlock`

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
          *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = 14;
          ++*(_DWORD *)(v3 + 600);
          goto LABEL_59;
        }
        switch ( (int)v7 )
        {
          case 2:
            v50 = v5[4];
            if ( (char)v50 == v50 )
            {
              *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = 11;
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
            v34 = (unsigned int)dword_1800831E8[v6];
            goto LABEL_111;
          case 8:
          case 9:
          case 10:
          case 11:
          case 12:
          case 13:
            v34 = (unsigned int)dword_1800830C0[v7];
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
            v29 = *(int *)((char *)&qword_180083060[2] + v28);
            if ( (unsigned __int8)v29 == (_DWORD)v29 )
            {
              v30 = *(_DWORD *)((char *)&qword_180083060[2] + v28);
              *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = v30;
              *(_DWORD *)(v3 + 600) += *((char *)&qword_180080660 + v29);
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
        v38 = *(int *)((char *)&qword_180083090[2] + v28);
        if ( (unsigned __int8)v38 == (_DWORD)v38 )
        {
          v39 = *(_DWORD *)((char *)&qword_180083090[2] + v28);
          *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = v39;
          *(_DWORD *)(v3 + 600) += *((char *)&qword_180080660 + v38);
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
    v9 = dword_1800830C0[v7];
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
        *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = v9;
        *(_DWORD *)(v3 + 600) += *((char *)&qword_180080660 + v9);
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
              Parser::GenPcode_LCCV(v3, (unsigned int)dword_180083088[v6], v67, i);
              goto LABEL_28;
            }
          }
        }
        v15 = dword_180083040[v6];
        if ( (unsigned __int8)v15 != (_DWORD)v15 )
          goto LABEL_2;
        *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = v15;
        *(_DWORD *)(v3 + 600) += *((char *)&qword_180080660 + v15);
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
          Parser::GenPcode(v3, (unsigned int)dword_1800831D0[v6]);
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
        v53 = dword_180083028[v6];
        v54 = dword_180083028[v6];
        if ( (unsigned __int8)v53 != (_DWORD)v53 )
          goto LABEL_2;
        v55 = *(_QWORD *)(*(_QWORD *)(v10 + 32) + 16LL);
        *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = v54;
        *(_DWORD *)(v3 + 600) += *((char *)&qword_180080660 + v53);
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
  v61 = dword_180083058[v6];
  v62 = dword_180083058[v6];
  if ( (unsigned __int8)v61 != (_DWORD)v61 )
    goto LABEL_2;
  v45 = *(_QWORD *)(*((_QWORD *)v5 + 4) + 16LL);
  *(_BYTE *)Parser::PvGen((Parser *)v3, 1) = v62;
  *(_DWORD *)(v3 + 600) += *((char *)&qword_180080660 + v61);
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
0x18000b730  push    rbx
0x18000b732  push    rbp
0x18000b733  push    rsi
0x18000b734  push    rdi
0x18000b735  push    r12
0x18000b737  push    r14
0x18000b739  push    r15
0x18000b73b  sub     rsp, 20h
0x18000b73f  mov     rdi, rcx
0x18000b742  mov     r14d, r8d
0x18000b745  mov     ecx, 2000h; unsigned int
0x18000b74a  mov     rsi, rdx
0x18000b74d  call    ?FStackAvailable@@YAHI@Z; FStackAvailable(uint)
0x18000b752  test    eax, eax
0x18000b754  jnz     loc_18000C0EA
0x18000b75a  mov     edx, 3E9h; int
0x18000b75f  mov     rcx, rdi; this
0x18000b762  call    ?Error@Parser@@AEAAXH@Z; Parser::Error(int)
0x18000b770  mov     ebx, r14d
0x18000b773  cmp     r14d, 1
0x18000b777  jnz     short loc_18000B785
0x18000b779  test    [rsi+4], r14b
0x18000b77d  mov     eax, 0
0x18000b782  cmovnz  ebx, eax
0x18000b785  movsxd  rbp, dword ptr [rsi]
0x18000b788  mov     rdx, rbp
0x18000b78b  mov     eax, ds:rva ?mpnopgrfnop@ParseNode@@2QBIB[r12+rbp*4]; uint const near * const ParseNode::mpnopgrfnop ...
0x18000b793  test    al, 2
0x18000b795  jz      short loc_18000B7C5
0x18000b797  cmp     ebp, 1
0x18000b79a  jz      loc_18000B95E
0x18000b7a0  cmp     ebp, 4
0x18000b7a3  jz      loc_18000BBE9
0x18000b7a9  add     ebp, 0FFFFFFFEh; switch 13 cases
0x18000b7ac  cmp     ebp, 0Ch
0x18000b7af  jbe     loc_18000BC8D
0x18000b7b5  add     rsp, 20h; jumptable 000000018000BC9B default case, case 4
0x18000b7b9  pop     r15
0x18000b7bb  pop     r14
0x18000b7bd  pop     r12
0x18000b7bf  pop     rdi
0x18000b7c0  pop     rsi
0x18000b7c1  pop     rbp
0x18000b7c2  pop     rbx
0x18000b7c3  retn
0x18000b7c5  test    al, 20h
0x18000b7c7  jnz     loc_18000BA49
0x18000b7cd  movsxd  r15, ds:rva dword_1800830C0[r12+rbp*4]
0x18000b7d5  test    r15d, r15d
0x18000b7d8  jnz     loc_18000BA95
0x18000b7de  cmp     ebp, 20h ; ' '
0x18000b7e1  jnz     loc_18000BE75
0x18000b7e7  mov     r14, [rsi+18h]
0x18000b7eb  mov     rsi, [rsi+20h]
0x18000b7ef  mov     ecx, [r14]
0x18000b7f2  sub     ecx, 1
0x18000b7f5  jnz     loc_18000BD21
0x18000b7fb  test    rsi, rsi
0x18000b7fe  jz      loc_18000C0C3
0x18000b804  cmp     dword ptr [rsi], 2Bh ; '+'
0x18000b807  mov     ebp, 1
0x18000b80c  jnz     short loc_18000B82B
0x18000b80e  mov     rdx, [rsi+18h]
0x18000b812  mov     r8d, 1
0x18000b818  mov     rcx, rdi
0x18000b81b  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000b820  mov     rsi, [rsi+20h]
0x18000b824  inc     ebp
0x18000b826  cmp     dword ptr [rsi], 2Bh ; '+'
0x18000b829  jz      short loc_18000B80E
0x18000b82b  mov     r8d, 1
0x18000b831  mov     rdx, rsi
0x18000b834  mov     rcx, rdi
0x18000b837  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000b83c  mov     rsi, [r14+10h]
0x18000b840  mov     eax, [rdi+148h]
0x18000b846  cmp     [rsi+14h], eax
0x18000b849  jnz     short loc_18000B858
0x18000b84b  mov     rax, [rsi+18h]
0x18000b84f  test    rax, rax
0x18000b852  jnz     loc_18000C086
0x18000b858  movsxd  rax, ebx
0x18000b85b  movsxd  rbx, ds:rva dword_180083040[r12+rax*4]
0x18000b863  movzx   r14d, bl
0x18000b867  cmp     r14d, ebx
0x18000b86a  jnz     loc_18000B75A
0x18000b870  mov     edx, 1; int
0x18000b875  mov     rcx, rdi; this
0x18000b878  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000b87d  mov     [rax], r14b
0x18000b880  movsx   eax, byte ptr [rbx+r12+80660h]
0x18000b889  add     [rdi+258h], eax
0x18000b88f  mov     edx, [rdi+25Ch]
0x18000b895  add     edx, [rdi+258h]
0x18000b89b  cmp     [rdi+254h], edx
0x18000b8a1  jge     short loc_18000B8A9
0x18000b8a3  mov     [rdi+254h], edx
0x18000b8a9  movzx   ecx, word ptr [rsi+0Ah]
0x18000b8ad  mov     eax, 4000h
0x18000b8b2  test    ax, cx
0x18000b8b5  jnz     short loc_18000B8F7
0x18000b8b7  or      cx, ax
0x18000b8ba  mov     [rsi+0Ah], cx
0x18000b8be  mov     eax, [rdi+264h]
0x18000b8c4  mov     ecx, [rsi+28h]
0x18000b8c7  add     eax, 8
0x18000b8ca  mov     [rsi+10h], eax
0x18000b8cd  mov     edx, [rdi+264h]
0x18000b8d3  mov     rax, [rdi+278h]
0x18000b8da  add     edx, 0Dh
0x18000b8dd  lea     edx, [rdx+rcx*2]
0x18000b8e0  and     edx, 0FFFFFFFCh
0x18000b8e3  mov     [rdi+264h], edx
0x18000b8e9  mov     [rax], rsi
0x18000b8ec  lea     rax, [rsi+20h]
0x18000b8f0  mov     [rdi+278h], rax
0x18000b8f7  mov     ebx, [rsi+10h]
0x18000b8fa  mov     edx, 4; int
0x18000b8ff  mov     rcx, rdi; this
0x18000b902  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000b907  mov     [rax], ebx
0x18000b909  movzx   ebx, bp
0x18000b90c  cmp     ebx, ebp
0x18000b90e  jnz     loc_18000B75A
0x18000b914  mov     rax, [rdi+230h]
0x18000b91b  sub     rax, [rdi+228h]
0x18000b922  cmp     rax, 2
0x18000b926  jl      loc_18000BE63
0x18000b92c  mov     rcx, [rdi+228h]
0x18000b933  add     dword ptr [rdi+238h], 2
0x18000b93a  lea     rax, [rcx+2]
0x18000b93e  mov     [rdi+228h], rax
0x18000b945  mov     [rcx], bx
0x18000b948  sub     [rdi+258h], ebp
0x18000b94e  add     rsp, 20h
0x18000b952  pop     r15
0x18000b954  pop     r14
0x18000b956  pop     r12
0x18000b958  pop     rdi
0x18000b959  pop     rsi
0x18000b95a  pop     rbp
0x18000b95b  pop     rbx
0x18000b95c  retn
0x18000b95e  mov     rsi, [rsi+10h]
0x18000b962  mov     eax, [rdi+148h]
0x18000b968  cmp     [rsi+14h], eax
0x18000b96b  jnz     loc_18000BB22
0x18000b971  mov     rdx, [rsi+18h]
0x18000b975  xor     ebp, ebp
0x18000b977  xor     ecx, ecx
0x18000b979  test    rdx, rdx
0x18000b97c  jz      short loc_18000B99B
0x18000b97e  mov     eax, [rdx+4]
0x18000b981  bt      eax, 0Ah
0x18000b985  jb      loc_18000C037
0x18000b98b  mov     ebp, [rdx+18h]
0x18000b98e  test    ebp, ebp
0x18000b990  jz      loc_18000BFE0
0x18000b996  mov     ecx, 1
0x18000b99b  movsxd  rax, ebx
0x18000b99e  lea     rax, ds:0[rax*4]
0x18000b9a6  test    ecx, ecx
0x18000b9a8  jz      loc_18000BB2D
0x18000b9ae  movsxd  rbx, dword ptr [rax+r12+83070h]
0x18000b9b6  movzx   esi, bl
0x18000b9b9  cmp     esi, ebx
0x18000b9bb  jnz     loc_18000B75A
0x18000b9c1  mov     edx, 1; int
0x18000b9c6  mov     rcx, rdi; this
0x18000b9c9  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000b9ce  mov     [rax], sil
0x18000b9d1  movsx   eax, byte ptr [rbx+r12+80660h]
0x18000b9da  add     [rdi+258h], eax
0x18000b9e0  mov     edx, [rdi+25Ch]
0x18000b9e6  add     edx, [rdi+258h]
0x18000b9ec  cmp     [rdi+254h], edx
0x18000b9f2  jge     short loc_18000B9FA
0x18000b9f4  mov     [rdi+254h], edx
0x18000b9fa  movsx   eax, bp
0x18000b9fd  cmp     eax, ebp
0x18000b9ff  jnz     loc_18000B75A
0x18000ba05  mov     rax, [rdi+230h]
0x18000ba0c  sub     rax, [rdi+228h]
0x18000ba13  cmp     rax, 2
0x18000ba17  jl      loc_18000C0D8
0x18000ba1d  mov     rcx, [rdi+228h]
0x18000ba24  add     dword ptr [rdi+238h], 2
0x18000ba2b  lea     rax, [rcx+2]
0x18000ba2f  mov     [rdi+228h], rax
0x18000ba36  mov     [rcx], bp
0x18000ba39  add     rsp, 20h
0x18000ba3d  pop     r15
0x18000ba3f  pop     r14
0x18000ba41  pop     r12
0x18000ba43  pop     rdi
0x18000ba44  pop     rsi
0x18000ba45  pop     rbp
0x18000ba46  pop     rbx
0x18000ba47  retn
0x18000ba49  mov     rdx, [rsi+20h]
0x18000ba4d  mov     r8d, 1
0x18000ba53  mov     rcx, rdi
0x18000ba56  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000ba5b  mov     rdx, [rsi+18h]
0x18000ba5f  xor     r8d, r8d
0x18000ba62  mov     ebx, [rdi+258h]
0x18000ba68  cmp     ebp, 23h ; '#'
0x18000ba6b  mov     rcx, rdi
0x18000ba6e  setz    r8b
0x18000ba72  add     r8d, 3
0x18000ba76  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000ba7b  mov     eax, [rdi+258h]
0x18000ba81  inc     eax
0x18000ba83  cmp     ebx, eax
0x18000ba85  jz      def_18000BC9B; jumptable 000000018000BC9B default case, case 4
0x18000ba8b  mov     edx, 39h ; '9'
0x18000ba90  jmp     loc_18000C0B6
0x18000ba95  mov     r8d, 1
0x18000ba9b  mov     rcx, rdi
0x18000ba9e  test    al, 10h
0x18000baa0  jnz     loc_18000BED4
0x18000baa6  test    al, 4
0x18000baa8  jnz     loc_18000C02E
0x18000baae  mov     rdx, [rsi+18h]
0x18000bab2  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000bab7  mov     rdx, [rsi+20h]
0x18000babb  mov     r8d, 1
0x18000bac1  mov     rcx, rdi
0x18000bac4  call    ?GenPcodeExpr@Parser@@AEAAXPEAUParseNode@@W4E_ADM@1@@Z; Parser::GenPcodeExpr(ParseNode *,Parser::E_ADM)
0x18000bac9  movzx   ebx, r15b
0x18000bacd  cmp     ebx, r15d
0x18000bad0  jnz     loc_18000B75A
0x18000bad6  mov     edx, 1; int
0x18000badb  mov     rcx, rdi; this
0x18000bade  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000bae3  mov     [rax], bl
0x18000bae5  movsx   eax, byte ptr [r15+r12+80660h]
0x18000baee  add     [rdi+258h], eax
0x18000baf4  mov     edx, [rdi+25Ch]
0x18000bafa  add     edx, [rdi+258h]
0x18000bb00  cmp     [rdi+254h], edx
0x18000bb06  jge     def_18000BC9B; jumptable 000000018000BC9B default case, case 4
0x18000bb0c  mov     [rdi+254h], edx
0x18000bb12  add     rsp, 20h
0x18000bb16  pop     r15
0x18000bb18  pop     r14
0x18000bb1a  pop     r12
0x18000bb1c  pop     rdi
0x18000bb1d  pop     rsi
0x18000bb1e  pop     rbp
0x18000bb1f  pop     rbx
0x18000bb20  retn
0x18000bb22  movsxd  rax, ebx
0x18000bb25  lea     rax, ds:0[rax*4]
0x18000bb2d  movsxd  rbx, dword ptr [rax+r12+830A0h]
0x18000bb35  movzx   ebp, bl
0x18000bb38  cmp     ebp, ebx
0x18000bb3a  jnz     loc_18000B75A
0x18000bb40  mov     edx, 1; int
0x18000bb45  mov     rcx, rdi; this
0x18000bb48  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000bb4d  mov     [rax], bpl
0x18000bb50  movsx   eax, byte ptr [rbx+r12+80660h]
0x18000bb59  add     [rdi+258h], eax
0x18000bb5f  mov     edx, [rdi+25Ch]
0x18000bb65  add     edx, [rdi+258h]
0x18000bb6b  cmp     [rdi+254h], edx
0x18000bb71  jge     short loc_18000BB79
0x18000bb73  mov     [rdi+254h], edx
0x18000bb79  movzx   ecx, word ptr [rsi+0Ah]
0x18000bb7d  mov     eax, 4000h
0x18000bb82  test    ax, cx
0x18000bb85  jnz     short loc_18000BBC7
0x18000bb87  or      cx, ax
0x18000bb8a  mov     [rsi+0Ah], cx
0x18000bb8e  mov     eax, [rdi+264h]
0x18000bb94  mov     ecx, [rsi+28h]
0x18000bb97  add     eax, 8
0x18000bb9a  mov     [rsi+10h], eax
0x18000bb9d  mov     edx, [rdi+264h]
0x18000bba3  mov     rax, [rdi+278h]
0x18000bbaa  add     edx, 0Dh
0x18000bbad  lea     edx, [rdx+rcx*2]
0x18000bbb0  and     edx, 0FFFFFFFCh
0x18000bbb3  mov     [rdi+264h], edx
0x18000bbb9  mov     [rax], rsi
0x18000bbbc  lea     rax, [rsi+20h]
0x18000bbc0  mov     [rdi+278h], rax
0x18000bbc7  mov     ebx, [rsi+10h]
0x18000bbca  mov     edx, 4; int
0x18000bbcf  mov     rcx, rdi; this
0x18000bbd2  call    ?PvGen@Parser@@AEAAPEAXJ@Z; Parser::PvGen(long)
0x18000bbd7  mov     [rax], ebx
0x18000bbd9  add     rsp, 20h
0x18000bbdd  pop     r15
0x18000bbdf  pop     r14
0x18000bbe1  pop     r12
0x18000bbe3  pop     rdi
0x18000bbe4  pop     rsi
0x18000bbe5  pop     rbp
  ... truncated ...
```
