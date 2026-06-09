# D3DXShader::CParse::FindDecl(D3DXShader::_D3DXDECL_TYPE,D3DXShader::D3DXTOKEN *,D3DXShader::CNode *,D3DXShader::CNode *,D3DXShader::CNodeScope *,ulong,D3DXShader::CNode * *,D3DXShader::CNode * *)

- ea: `0x14009edd4`
- end: `0x14009f7f2`
- name: `?FindDecl@CParse@D3DXShader@@IEAAJW4_D3DXDECL_TYPE@2@PEAUD3DXTOKEN@2@PEAVCNode@2@2PEAVCNodeScope@2@KPEAPEAV52@4@Z`
- size: `2590`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `13`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14009ae2c`
- `0x1400a03a0`
- `0x1400a08ac`
- `0x1400a2b30`
- `0x1400a5d18`
- `0x1400a7a08`
- `0x1400c97a0`
- `0x1400c9e8c`

## callees

- `0x140003611`
- `0x14009bf98`
- `0x14009edd4`
- `0x14009f7f8`
- `0x1400a1c94`
- `0x1400a5538`
- `0x1400a571c`
- `0x1400a7cf0`
- `0x1400ab2f4`
- `0x1400ab36c`
- `0x1400accf8`
- `0x1401131ca`
- `0x140113220`

## import_xrefs

- `msvcrt!_stricmp` at `0x14009f2c5`
- `msvcrt!_stricmp` at `0x14009f2da`
- `msvcrt!_stricmp` at `0x14009f350`
- `msvcrt!_stricmp` at `0x14009f3b7`
- `msvcrt!_stricmp` at `0x14009f3fb`
- `msvcrt!_stricmp` at `0x14009f415`
- `msvcrt!_stricmp` at `0x14009f42f`
- `msvcrt!_stricmp` at `0x14009f449`
- `msvcrt!_stricmp` at `0x14009f2c5`
- `msvcrt!_stricmp` at `0x14009f2da`
- `msvcrt!_stricmp` at `0x14009f350`
- `msvcrt!_stricmp` at `0x14009f3b7`
- `msvcrt!_stricmp` at `0x14009f3fb`
- `msvcrt!_stricmp` at `0x14009f415`
- `msvcrt!_stricmp` at `0x14009f42f`
- `msvcrt!_stricmp` at `0x14009f449`

## string_xrefs

- `0x14009ef95`: `'%s': loop control variable used outside for-loop scope conflicts with a previous declaration in the outer scope; most recent definition used`
- `0x14009efd6`: `'%s': loop control variable used outside for-loop scope conflicts with a previous declaration in the outer scope; most recent definition used`

## pseudocode

```c
__int64 __fastcall D3DXShader::CParse::FindDecl(
        D3DXShader::CParse *a1,
        int a2,
        __int64 a3,
        struct D3DXShader::CNode *a4,
        struct D3DXShader::CNode *a5,
        struct D3DXShader::CNodeScope *a6,
        unsigned int a7,
        _QWORD *a8,
        struct D3DXShader::CNode **a9)
{
  int v10; // r12d
  struct D3DXShader::CNodeScope *v11; // rdi
  unsigned int v12; // esi
  unsigned int v13; // r15d
  struct D3DXShader::CNode *i; // rcx
  int v15; // r14d
  __int64 v16; // r13
  char v17; // al
  unsigned int v18; // edi
  __int64 v19; // rax
  struct D3DXShader::CNodeScope *v20; // r8
  struct D3DXShader::CNode *j; // r10
  struct D3DXShader::CNode *v22; // rcx
  char v24; // al
  __int64 v25; // rsi
  struct D3DXShader::CNode **v26; // r14
  unsigned int k; // edi
  __int64 v28; // r9
  struct D3DXShader::CNode *v29; // rcx
  struct D3DXShader::CNode *v30; // rax
  struct D3DXShader::CNode **v31; // r13
  struct D3DXShader::CNode **v32; // rbx
  __int64 m; // rdi
  unsigned __int8 *v34; // rax
  D3DXCore::CAlloc *v35; // rcx
  unsigned __int8 *v36; // rdx
  int v37; // eax
  unsigned __int8 *v38; // rax
  int v39; // esi
  unsigned __int16 *v40; // rdi
  __int64 v41; // rcx
  int v42; // esi
  char *v43; // rdi
  int v44; // ecx
  int v45; // edx
  int v46; // edx
  int v47; // edx
  unsigned __int8 *v48; // rcx
  int v49; // eax
  unsigned __int8 *v50; // r8
  int v51; // eax
  unsigned int v52; // ecx
  unsigned __int8 *v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdi
  D3DXCore::CAlloc *v56; // rcx
  unsigned __int8 *v57; // rax
  unsigned __int8 *v58; // rax
  unsigned int v59; // [rsp+20h] [rbp-2B8h]
  struct D3DXShader::CNodeScope *v60; // [rsp+40h] [rbp-298h]
  struct D3DXShader::CNode *v63; // [rsp+58h] [rbp-280h] BYREF
  struct D3DXShader::CNode *v64; // [rsp+60h] [rbp-278h]
  struct D3DXShader::CNode *v65; // [rsp+68h] [rbp-270h]
  struct D3DXShader::CNode **v66; // [rsp+70h] [rbp-268h]
  _QWORD v67[64]; // [rsp+80h] [rbp-258h] BYREF

  v10 = a2;
  v11 = a6;
  v63 = a4;
  v65 = a5;
  v60 = a6;
  v66 = a9;
  if ( a8 )
    *a8 = 0;
  if ( a9 )
    *a9 = 0;
  v12 = -1;
  v13 = 0;
  memset_0(v67, 0, sizeof(v67));
  v15 = 4;
LABEL_6:
  if ( v11 )
  {
    if ( v12 )
    {
      for ( i = D3DXShader::CParse::FindDecls(i, (struct D3DXShader::D3DXTOKEN *)a3, v11);
            ;
            i = (struct D3DXShader::CNode *)*((_QWORD *)v64 + 3) )
      {
        v64 = i;
        if ( !i || !v12 )
        {
          v11 = (struct D3DXShader::CNodeScope *)*((_QWORD *)v11 + 8);
          v60 = v11;
          goto LABEL_6;
        }
        v16 = *((_QWORD *)i + 2);
        if ( v10 != *(_DWORD *)(v16 + 32) )
        {
          if ( (a7 & 5) != 0 )
            D3DXShader::CParse::Error(
              a1,
              (struct D3DXShader::D3DXTOKEN *)a3,
              0xBBDu,
              "'%s': identifier represents a %s, not a %s",
              *(const char **)(a3 + 8),
              off_140120A60[*(int *)(v16 + 32)],
              off_140120A60[v10]);
          if ( a8 )
            *a8 = 0;
          return 2147500037LL;
        }
        v17 = a7;
        v18 = 0;
        if ( (a7 & 4) != 0 )
        {
          v18 = D3DXShader::CParse::ScoreFunctionCall(
                  a1,
                  *(struct D3DXShader::CNodeFunction **)(v16 + 48),
                  v63,
                  v65,
                  a7);
          v17 = a7;
        }
        if ( (v17 & 8) != 0 )
          v18 += D3DXShader::CParse::ScoreFunctionDecl(
                   a1,
                   *(struct D3DXShader::CNodeFunction **)(v16 + 48),
                   v63,
                   v65,
                   v59);
        if ( v18 == -1 )
          break;
        if ( v18 >= v12 )
        {
          if ( v18 != v12 || v13 >= 0x40 )
            break;
        }
        else
        {
          v12 = v18;
          v13 = 0;
        }
        v11 = v60;
        v19 = v13++;
        v67[v19] = v16;
        if ( !v12 && *(_DWORD *)(v16 + 80) && !*(_DWORD *)(v16 + 76) )
        {
          v20 = (struct D3DXShader::CNodeScope *)*((_QWORD *)v60 + 8);
          if ( v20 && *((_DWORD *)v20 + 8) == 4 )
          {
            for ( j = D3DXShader::CParse::FindDecls(i, (struct D3DXShader::D3DXTOKEN *)a3, v20);
                  j;
                  j = (struct D3DXShader::CNode *)*((_QWORD *)j + 3) )
            {
              if ( !*(_DWORD *)(*((_QWORD *)j + 2) + 80LL) )
              {
                D3DXShader::CParse::Warning(
                  a1,
                  (struct D3DXShader::D3DXTOKEN *)a3,
                  0xC06u,
                  "'%s': loop control variable used outside for-loop scope conflicts with a previous declaration in the o"
                  "uter scope; most recent definition used",
                  *(const char **)(a3 + 8));
                *(_DWORD *)(v16 + 76) = 1;
                break;
              }
            }
          }
          v22 = v64;
          while ( 1 )
          {
            v22 = (struct D3DXShader::CNode *)*((_QWORD *)v22 + 3);
            if ( !v22 )
              break;
            if ( !*(_DWORD *)(*((_QWORD *)v22 + 2) + 80LL) )
            {
              D3DXShader::CParse::Warning(
                a1,
                (struct D3DXShader::D3DXTOKEN *)a3,
                0xC06u,
                "'%s': loop control variable used outside for-loop scope conflicts with a previous declaration in the out"
                "er scope; most recent definition used",
                *(const char **)(a3 + 8));
              *(_DWORD *)(v16 + 76) = 1;
              break;
            }
          }
        }
LABEL_36:
        v10 = a2;
      }
      v11 = v60;
      goto LABEL_36;
    }
    goto LABEL_44;
  }
  if ( v12 != -1 )
  {
LABEL_44:
    v24 = a7;
    v25 = v67[0];
    if ( (a7 & 4) != 0 && v13 > 1 )
    {
      v26 = *(struct D3DXShader::CNode ***)(v67[0] + 48LL);
      for ( k = 1; k < v13; ++k )
      {
        if ( !(unsigned int)D3DXShader::CParse::IsTypeEqual(
                              a1,
                              v26[7],
                              *(struct D3DXShader::CNode **)(*(_QWORD *)(v67[k] + 48LL) + 56LL)) )
          break;
        if ( D3DXShader::CParse::ScoreFunctionDecl(
               a1,
               (struct D3DXShader::CNodeFunction *)v26,
               v26[6],
               *(struct D3DXShader::CNode **)(v28 + 64),
               v59) == -1 )
          break;
      }
      v25 = v67[0];
      if ( k < v13 )
        D3DXShader::CParse::Error(
          a1,
          (struct D3DXShader::D3DXTOKEN *)a3,
          0xBFBu,
          "'%s': ambiguous function call",
          *(const char **)(a3 + 8));
      v24 = a7;
    }
    if ( a8 )
    {
      if ( (v24 & 2) != 0 )
      {
        *a8 = *(_QWORD *)(v25 + 48);
      }
      else
      {
        v29 = *(struct D3DXShader::CNode **)(v25 + 48);
        if ( v29 )
        {
          v30 = D3DXShader::CNode::Copy(v29);
          *a8 = v30;
          if ( !v30 )
            return 2147942414LL;
        }
      }
    }
    v31 = v66;
    if ( v66 )
    {
      v63 = 0;
      v32 = &v63;
      for ( m = 0; (unsigned int)m < v13; m = (unsigned int)(m + 1) )
      {
        v34 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x28u, 16);
        if ( !v34 )
        {
          *v32 = 0;
          return 2147942414LL;
        }
        *((_DWORD *)v34 + 2) = 1;
        *(_QWORD *)v34 = &D3DXShader::CNodeList::`vftable';
        *((_QWORD *)v34 + 2) = 0;
        *((_QWORD *)v34 + 4) = "Values";
        v35 = D3DXShader::CNode::s_pAlloc;
        *((_QWORD *)v34 + 3) = 0;
        *v32 = (struct D3DXShader::CNode *)v34;
        v36 = D3DXCore::CAlloc::Alloc(v35, 0x68u, 16);
        if ( v36 )
        {
          v37 = *(_DWORD *)(v67[m] + 72LL);
          *((_DWORD *)v36 + 2) = 14;
          *((_QWORD *)v36 + 2) = 0;
          *((_QWORD *)v36 + 3) = 0;
          *(_QWORD *)v36 = &D3DXShader::CNodeValue::`vftable';
          *((_DWORD *)v36 + 8) = 2;
          *((_DWORD *)v36 + 10) = v37;
          *(_OWORD *)(v36 + 56) = *(_OWORD *)a3;
          *(_OWORD *)(v36 + 72) = *(_OWORD *)(a3 + 16);
          *(_OWORD *)(v36 + 88) = *(_OWORD *)(a3 + 32);
        }
        else
        {
          v36 = 0;
        }
        *((_QWORD *)*v32 + 2) = v36;
        if ( !v36 )
          return 2147942414LL;
        v32 = (struct D3DXShader::CNode **)((char *)*v32 + 24);
      }
      *v31 = v63;
    }
    return 0;
  }
  if ( (a7 & 2) != 0 || v66 )
    goto LABEL_153;
  if ( a2 )
  {
    if ( a2 == 1 && !strcmp_0(*(const char **)(a3 + 8), "NULL") )
    {
      if ( a8 )
      {
        v53 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x70u, 16);
        if ( !v53 )
          return 2147942414LL;
        v54 = D3DXShader::CNodeVariable::CNodeVariable((D3DXShader::CNodeVariable *)v53);
        v55 = v54;
        if ( !v54 )
          return 2147942414LL;
        v56 = D3DXShader::CNode::s_pAlloc;
        *(_QWORD *)(v54 + 36) = 1;
        *(_DWORD *)(v54 + 44) = 514;
        v57 = D3DXCore::CAlloc::Alloc(v56, 0x38u, 16);
        if ( v57 )
        {
          *((_DWORD *)v57 + 2) = 9;
          *(_QWORD *)v57 = &D3DXShader::CNodeType::`vftable';
          *((_QWORD *)v57 + 2) = 0;
          *((_QWORD *)v57 + 3) = 0;
          *((_DWORD *)v57 + 8) = 3;
          *((_DWORD *)v57 + 9) = 13;
          *((_DWORD *)v57 + 10) = 1;
          *((_DWORD *)v57 + 11) = 1;
          *((_DWORD *)v57 + 12) = 512;
        }
        else
        {
          v57 = 0;
        }
        *(_QWORD *)(v55 + 48) = v57;
        if ( !v57 )
          return 2147942414LL;
        v58 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x68u, 16);
        if ( v58 )
        {
          *((_DWORD *)v58 + 2) = 14;
          *(_QWORD *)v58 = &D3DXShader::CNodeValue::`vftable';
          *((_QWORD *)v58 + 2) = 0;
          *((_QWORD *)v58 + 3) = 0;
          *((_DWORD *)v58 + 8) = 5;
          *((_QWORD *)v58 + 5) = 0;
          *((_DWORD *)v58 + 12) = 0;
          *(_OWORD *)(v58 + 56) = *(_OWORD *)a3;
          *(_OWORD *)(v58 + 72) = *(_OWORD *)(a3 + 16);
          *(_OWORD *)(v58 + 88) = *(_OWORD *)(a3 + 32);
        }
        else
        {
          v58 = 0;
        }
        *(_QWORD *)(v55 + 56) = v58;
        if ( !v58 )
          return 2147942414LL;
        *a8 = v55;
      }
      return 0;
    }
    goto LABEL_153;
  }
  if ( !_stricmp(*(const char **)(a3 + 8), "dword") )
    goto LABEL_77;
  if ( !_stricmp(*(const char **)(a3 + 8), "float") )
  {
    v15 = 11;
LABEL_77:
    if ( !a8 )
      return 0;
    v38 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x38u, 16);
    if ( v38 )
    {
      *((_DWORD *)v38 + 8) = 0;
      *((_DWORD *)v38 + 9) = v15;
LABEL_80:
      *(_QWORD *)v38 = &D3DXShader::CNodeType::`vftable';
      *((_QWORD *)v38 + 3) = 0;
      *((_QWORD *)v38 + 2) = 0;
      *((_DWORD *)v38 + 2) = 9;
      *((_DWORD *)v38 + 10) = 1;
      *(_QWORD *)(v38 + 44) = 1;
LABEL_81:
      *a8 = v38;
      return 0;
    }
    goto LABEL_82;
  }
  if ( !_stricmp(*(const char **)(a3 + 8), "vector") )
  {
    if ( !a8 )
      return 0;
    v38 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x38u, 16);
    if ( !v38 )
      goto LABEL_82;
    *((_DWORD *)v38 + 8) = 1;
    *((_DWORD *)v38 + 10) = 1;
LABEL_87:
    *((_DWORD *)v38 + 9) = 11;
    *(_QWORD *)v38 = &D3DXShader::CNodeType::`vftable';
    *((_QWORD *)v38 + 3) = 0;
    *((_QWORD *)v38 + 2) = 0;
    *((_DWORD *)v38 + 2) = 9;
    *(_QWORD *)(v38 + 44) = 4;
    goto LABEL_81;
  }
  if ( !_stricmp(*(const char **)(a3 + 8), "matrix") )
  {
    if ( !a8 )
      return 0;
    v38 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x38u, 16);
    if ( !v38 )
      goto LABEL_82;
    *((_DWORD *)v38 + 8) = 2;
    *((_DWORD *)v38 + 10) = 4;
    goto LABEL_87;
  }
  if ( !_stricmp(*(const char **)(a3 + 8), "string") )
  {
    v39 = 14;
    goto LABEL_100;
  }
  if ( !_stricmp(*(const char **)(a3 + 8), "texture") )
  {
    v39 = 15;
    goto LABEL_100;
  }
  if ( !_stricmp(*(const char **)(a3 + 8), "pixelshader") )
  {
    v39 = 25;
    goto LABEL_100;
  }
  if ( !_stricmp(*(const char **)(a3 + 8), "vertexshader") )
  {
    v39 = 26;
LABEL_100:
    if ( !a8 )
      return 0;
    v38 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x38u, 16);
    if ( v38 )
    {
      *((_DWORD *)v38 + 8) = 3;
      *((_DWORD *)v38 + 9) = v39;
      goto LABEL_80;
    }
LABEL_82:
    *a8 = 0;
    return 2147942414LL;
  }
  v40 = *(unsigned __int16 **)(a3 + 8);
  v41 = -1;
  do
    ++v41;
  while ( *((_BYTE *)v40 + v41) );
  if ( (unsigned int)v41 < 4 )
  {
    if ( (unsigned int)v41 < 3 )
      goto LABEL_153;
  }
  else if ( *(_DWORD *)v40 == 1819242338 )
  {
    v42 = 0;
LABEL_108:
    v43 = (char *)(v40 + 2);
    v44 = v41 - 4;
    goto LABEL_127;
  }
  v45 = *v40 - 28265;
  if ( *v40 == 28265 )
    v45 = *((unsigned __int8 *)v40 + 2) - 116;
  if ( v45 )
  {
    if ( (unsigned int)v41 < 4 || *(_DWORD *)v40 != 1718378856 )
    {
      if ( (unsigned int)v41 < 5 )
        goto LABEL_125;
      v46 = *(_DWORD *)v40 - 1634692198;
      if ( *(_DWORD *)v40 == 1634692198 )
        v46 = *((unsigned __int8 *)v40 + 4) - 116;
      if ( v46 )
      {
LABEL_125:
        if ( (unsigned int)v41 < 6 )
          goto LABEL_153;
        v47 = *(_DWORD *)v40 - 1651863396;
        if ( *(_DWORD *)v40 == 1651863396 )
          v47 = v40[2] - 25964;
        if ( v47 )
          goto LABEL_153;
        v43 = (char *)(v40 + 3);
        v42 = 12;
        v44 = v41 - 6;
      }
      else
      {
        v43 = (char *)v40 + 5;
        v42 = 11;
        v44 = v41 - 5;
      }
      goto LABEL_127;
    }
    v42 = 10;
    goto LABEL_108;
  }
  v43 = (char *)v40 + 3;
  v42 = 4;
  v44 = v41 - 3;
LABEL_127:
  if ( v44 == 1 )
  {
    if ( (unsigned __int8)(*v43 - 49) <= 3u )
    {
      if ( !a8 )
        return 0;
      v48 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x38u, 16);
      if ( v48 )
      {
        v49 = *v43;
        *(_QWORD *)v48 = &D3DXShader::CNodeType::`vftable';
        *((_DWORD *)v48 + 2) = 9;
        *((_DWORD *)v48 + 8) = 1;
        *((_DWORD *)v48 + 10) = 1;
        *((_QWORD *)v48 + 2) = 0;
        *((_QWORD *)v48 + 3) = 0;
        *((_DWORD *)v48 + 9) = v42;
        *(_QWORD *)(v48 + 44) = (unsigned int)(v49 - 48);
        *a8 = v48;
        return 0;
      }
      goto LABEL_82;
    }
  }
  else if ( v44 == 3 && (unsigned __int8)(*v43 - 49) <= 3u && v43[1] == 120 && (unsigned __int8)(v43[2] - 49) <= 3u )
  {
    if ( !a8 )
      return 0;
    v50 = D3DXCore::CAlloc::Alloc(D3DXShader::CNode::s_pAlloc, 0x38u, 16);
    if ( v50 )
    {
      v51 = *v43;
      v52 = v43[2] - 48;
      *((_DWORD *)v50 + 2) = 9;
      *((_DWORD *)v50 + 10) = v51 - 48;
      *((_QWORD *)v50 + 2) = 0;
      *((_QWORD *)v50 + 3) = 0;
      *(_QWORD *)v50 = &D3DXShader::CNodeType::`vftable';
      *((_DWORD *)v50 + 8) = 2;
      *((_DWORD *)v50 + 9) = v42;
      *(_QWORD *)(v50 + 44) = v52;
      *a8 = v50;
      return 0;
    }
    goto LABEL_82;
  }
LABEL_153:
  if ( (a7 & 1) != 0 )
    D3DXShader::CParse::Error(
      a1,
      (struct D3DXShader::D3DXTOKEN *)a3,
      0xBBCu,
      "undeclared identifier '%s'",
      *(const char **)(a3 + 8));
  return 1;
}

```

## disassembly

```asm
0x14009edd4  push    rbx
0x14009edd6  push    rbp
0x14009edd7  push    rsi
0x14009edd8  push    rdi
0x14009edd9  push    r12
0x14009eddb  push    r13
0x14009eddd  push    r14
0x14009eddf  push    r15
0x14009ede1  sub     rsp, 298h
0x14009ede8  mov     rax, cs:__security_cookie
0x14009edef  xor     rax, rsp
0x14009edf2  mov     [rsp+2D8h+var_58], rax
0x14009edfa  mov     rbx, [rsp+2D8h+arg_38]
0x14009ee02  mov     rbp, r8
0x14009ee05  mov     rax, [rsp+2D8h+arg_20]
0x14009ee0d  mov     r12d, edx
0x14009ee10  mov     rdi, [rsp+2D8h+arg_28]
0x14009ee18  mov     r13, [rsp+2D8h+arg_40]
0x14009ee20  mov     [rsp+2D8h+var_280], r9
0x14009ee25  mov     [rsp+2D8h+var_288], edx
0x14009ee29  mov     [rsp+2D8h+var_290], rcx
0x14009ee2e  mov     [rsp+2D8h+var_270], rax
0x14009ee33  mov     [rsp+2D8h+var_298], rdi
0x14009ee38  mov     [rsp+2D8h+var_268], r13
0x14009ee3d  test    rbx, rbx
0x14009ee40  jz      short loc_14009EE49
0x14009ee42  mov     qword ptr [rbx], 0
0x14009ee49  test    r13, r13
0x14009ee4c  jz      short loc_14009EE56
0x14009ee4e  mov     qword ptr [r13+0], 0
0x14009ee56  xor     r13d, r13d
0x14009ee59  lea     rcx, [rsp+2D8h+var_258]; void *
0x14009ee61  or      esi, 0FFFFFFFFh
0x14009ee64  xor     edx, edx; Val
0x14009ee66  mov     r8d, 200h; Size
0x14009ee6c  mov     r15d, r13d
0x14009ee6f  call    memset_0
0x14009ee74  lea     r14d, [r13+4]
0x14009ee78  test    rdi, rdi
0x14009ee7b  jz      loc_14009F08D
0x14009ee81  test    esi, esi
0x14009ee83  jz      loc_14009F096
0x14009ee89  mov     r8, rdi; struct D3DXShader::CNodeScope *
0x14009ee8c  mov     rdx, rbp; struct D3DXShader::D3DXTOKEN *
0x14009ee8f  call    ?FindDecls@CParse@D3DXShader@@IEAAPEAVCNode@2@PEAUD3DXTOKEN@2@PEAVCNodeScope@2@@Z; D3DXShader::CParse::FindDecls(D3DXShader::D3DXTOKEN *,D3DXShader::CNodeScope *)
0x14009ee94  mov     rcx, rax
0x14009ee97  mov     [rsp+2D8h+var_278], rcx
0x14009ee9c  test    rcx, rcx
0x14009ee9f  jz      loc_14009F018
0x14009eea5  test    esi, esi
0x14009eea7  jz      loc_14009F018
0x14009eead  mov     r13, [rcx+10h]
0x14009eeb1  cmp     r12d, [r13+20h]
0x14009eeb5  jnz     loc_14009F026
0x14009eebb  mov     eax, [rsp+2D8h+arg_30]
0x14009eec2  xor     edi, edi
0x14009eec4  test    r14b, al
0x14009eec7  jz      short loc_14009EEEE
0x14009eec9  mov     r9, [rsp+2D8h+var_270]; struct D3DXShader::CNode *
0x14009eece  mov     r8, [rsp+2D8h+var_280]; struct D3DXShader::CNode *
0x14009eed3  mov     rdx, [r13+30h]; struct D3DXShader::CNodeFunction *
0x14009eed7  mov     rcx, [rsp+2D8h+var_290]; this
0x14009eedc  mov     [rsp+2D8h+var_2B8], eax; unsigned int
0x14009eee0  call    ?ScoreFunctionCall@CParse@D3DXShader@@IEAAIPEAVCNodeFunction@2@PEAVCNode@2@1K@Z; D3DXShader::CParse::ScoreFunctionCall(D3DXShader::CNodeFunction *,D3DXShader::CNode *,D3DXShader::CNode *,ulong)
0x14009eee5  mov     edi, eax
0x14009eee7  mov     eax, [rsp+2D8h+arg_30]
0x14009eeee  mov     r12, [rsp+2D8h+var_290]
0x14009eef3  test    al, 8
0x14009eef5  jz      short loc_14009EF0F
0x14009eef7  mov     r9, [rsp+2D8h+var_270]; struct D3DXShader::CNode *
0x14009eefc  mov     rcx, r12; this
0x14009eeff  mov     r8, [rsp+2D8h+var_280]; struct D3DXShader::CNode *
0x14009ef04  mov     rdx, [r13+30h]; struct D3DXShader::CNodeFunction *
0x14009ef08  call    ?ScoreFunctionDecl@CParse@D3DXShader@@IEAAIPEAVCNodeFunction@2@PEAVCNode@2@1K@Z; D3DXShader::CParse::ScoreFunctionDecl(D3DXShader::CNodeFunction *,D3DXShader::CNode *,D3DXShader::CNode *,ulong)
0x14009ef0d  add     edi, eax
0x14009ef0f  cmp     edi, 0FFFFFFFFh
0x14009ef12  jz      loc_14009EFFD
0x14009ef18  cmp     edi, esi
0x14009ef1a  jnb     short loc_14009EF23
0x14009ef1c  mov     esi, edi
0x14009ef1e  xor     r15d, r15d
0x14009ef21  jmp     short loc_14009EF33
0x14009ef23  jnz     loc_14009EFFD
0x14009ef29  cmp     r15d, 40h ; '@'
0x14009ef2d  jnb     loc_14009EFFD
0x14009ef33  mov     rdi, [rsp+2D8h+var_298]
0x14009ef38  mov     eax, r15d
0x14009ef3b  inc     r15d
0x14009ef3e  mov     [rsp+rax*8+2D8h+var_258], r13
0x14009ef46  test    esi, esi
0x14009ef48  jnz     loc_14009F002
0x14009ef4e  cmp     [r13+50h], esi
0x14009ef52  jz      loc_14009F002
0x14009ef58  cmp     [r13+4Ch], esi
0x14009ef5c  jnz     loc_14009F002
0x14009ef62  mov     r8, [rdi+40h]; struct D3DXShader::CNodeScope *
0x14009ef66  test    r8, r8
0x14009ef69  jz      short loc_14009EFBA
0x14009ef6b  cmp     [r8+20h], r14d
0x14009ef6f  jnz     short loc_14009EFBA
0x14009ef71  mov     rdx, rbp; struct D3DXShader::D3DXTOKEN *
0x14009ef74  call    ?FindDecls@CParse@D3DXShader@@IEAAPEAVCNode@2@PEAUD3DXTOKEN@2@PEAVCNodeScope@2@@Z; D3DXShader::CParse::FindDecls(D3DXShader::D3DXTOKEN *,D3DXShader::CNodeScope *)
0x14009ef79  mov     r10, rax
0x14009ef7c  test    r10, r10
0x14009ef7f  jz      short loc_14009EFBA
0x14009ef81  mov     rax, [r10+10h]
0x14009ef85  cmp     dword ptr [rax+50h], 0
0x14009ef89  jz      short loc_14009EF91
0x14009ef8b  mov     r10, [r10+18h]
0x14009ef8f  jmp     short loc_14009EF7C
0x14009ef91  mov     rax, [rbp+8]
0x14009ef95  lea     r9, aSLoopControlVa; "'%s': loop control variable used outsid"...
0x14009ef9c  mov     r8d, 0C06h; unsigned int
0x14009efa2  mov     qword ptr [rsp+2D8h+var_2B8], rax
0x14009efa7  mov     rdx, rbp; struct D3DXShader::D3DXTOKEN *
0x14009efaa  mov     rcx, r12; this
0x14009efad  call    ?Warning@CParse@D3DXShader@@IEAAXPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CParse::Warning(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x14009efb2  mov     dword ptr [r13+4Ch], 1
0x14009efba  mov     rcx, [rsp+2D8h+var_278]
0x14009efbf  mov     rcx, [rcx+18h]
0x14009efc3  test    rcx, rcx
0x14009efc6  jz      short loc_14009F002
0x14009efc8  mov     rax, [rcx+10h]
0x14009efcc  cmp     dword ptr [rax+50h], 0
0x14009efd0  jnz     short loc_14009EFBF
0x14009efd2  mov     rax, [rbp+8]
0x14009efd6  lea     r9, aSLoopControlVa; "'%s': loop control variable used outsid"...
0x14009efdd  mov     r8d, 0C06h; unsigned int
0x14009efe3  mov     qword ptr [rsp+2D8h+var_2B8], rax
0x14009efe8  mov     rdx, rbp; struct D3DXShader::D3DXTOKEN *
0x14009efeb  mov     rcx, r12; this
0x14009efee  call    ?Warning@CParse@D3DXShader@@IEAAXPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CParse::Warning(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x14009eff3  mov     dword ptr [r13+4Ch], 1
0x14009effb  jmp     short loc_14009F002
0x14009effd  mov     rdi, [rsp+2D8h+var_298]
0x14009f002  mov     rcx, [rsp+2D8h+var_278]
0x14009f007  xor     r13d, r13d
0x14009f00a  mov     r12d, [rsp+2D8h+var_288]
0x14009f00f  mov     rcx, [rcx+18h]
0x14009f013  jmp     loc_14009EE97
0x14009f018  mov     rdi, [rdi+40h]
0x14009f01c  mov     [rsp+2D8h+var_298], rdi
0x14009f021  jmp     loc_14009EE78
0x14009f026  mov     r15d, [rsp+2D8h+arg_30]
0x14009f02e  test    r15b, 5
0x14009f032  jz      short loc_14009F077
0x14009f034  movsxd  r8, dword ptr [r13+20h]
0x14009f038  lea     rcx, off_140120A60; "type"
0x14009f03f  movsxd  rax, r12d
0x14009f042  lea     r9, aSIdentifierRep; "'%s': identifier represents a %s, not a"...
0x14009f049  mov     rdx, rbp; struct D3DXShader::D3DXTOKEN *
0x14009f04c  mov     rax, [rcx+rax*8]
0x14009f050  mov     [rsp+2D8h+var_2A8], rax
0x14009f055  mov     rax, [rcx+r8*8]
0x14009f059  mov     r8d, 0BBDh; unsigned int
0x14009f05f  mov     rcx, [rsp+2D8h+var_290]; this
0x14009f064  mov     [rsp+2D8h+var_2B0], rax
0x14009f069  mov     rax, [rbp+8]
0x14009f06d  mov     qword ptr [rsp+2D8h+var_2B8], rax
0x14009f072  call    ?Error@CParse@D3DXShader@@IEAAXPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CParse::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x14009f077  test    rbx, rbx
0x14009f07a  jz      short loc_14009F083
0x14009f07c  mov     qword ptr [rbx], 0
0x14009f083  mov     eax, 80004005h
0x14009f088  jmp     loc_14009F7CE
0x14009f08d  cmp     esi, 0FFFFFFFFh
0x14009f090  jz      loc_14009F28C
0x14009f096  mov     eax, [rsp+2D8h+arg_30]
0x14009f09d  mov     rsi, [rsp+2D8h+var_258]
0x14009f0a5  test    r14b, al
0x14009f0a8  jz      loc_14009F13E
0x14009f0ae  cmp     r15d, 1
0x14009f0b2  jbe     loc_14009F13E
0x14009f0b8  mov     r14, [rsi+30h]
0x14009f0bc  mov     edi, 1
0x14009f0c1  mov     rsi, [rsp+2D8h+var_290]
0x14009f0c6  mov     rdx, [r14+38h]; struct D3DXShader::CNode *
0x14009f0ca  mov     eax, edi
0x14009f0cc  mov     rcx, [rsp+rax*8+2D8h+var_258]
0x14009f0d4  mov     r9, [rcx+30h]
0x14009f0d8  mov     rcx, rsi; this
0x14009f0db  mov     r8, [r9+38h]; struct D3DXShader::CNode *
0x14009f0df  call    ?IsTypeEqual@CParse@D3DXShader@@IEAAHPEAVCNode@2@0@Z; D3DXShader::CParse::IsTypeEqual(D3DXShader::CNode *,D3DXShader::CNode *)
0x14009f0e4  test    eax, eax
0x14009f0e6  jz      short loc_14009F107
0x14009f0e8  mov     r9, [r9+40h]; struct D3DXShader::CNode *
0x14009f0ec  mov     rdx, r14; struct D3DXShader::CNodeFunction *
0x14009f0ef  mov     r8, [r14+30h]; struct D3DXShader::CNode *
0x14009f0f3  mov     rcx, rsi; this
0x14009f0f6  call    ?ScoreFunctionDecl@CParse@D3DXShader@@IEAAIPEAVCNodeFunction@2@PEAVCNode@2@1K@Z; D3DXShader::CParse::ScoreFunctionDecl(D3DXShader::CNodeFunction *,D3DXShader::CNode *,D3DXShader::CNode *,ulong)
0x14009f0fb  cmp     eax, 0FFFFFFFFh
0x14009f0fe  jz      short loc_14009F107
0x14009f100  inc     edi
0x14009f102  cmp     edi, r15d
0x14009f105  jb      short loc_14009F0C6
0x14009f107  mov     rsi, [rsp+2D8h+var_258]
0x14009f10f  cmp     edi, r15d
0x14009f112  jnb     short loc_14009F137
0x14009f114  mov     rax, [rbp+8]
0x14009f118  lea     r9, aSAmbiguousFunc; "'%s': ambiguous function call"
0x14009f11f  mov     rcx, [rsp+2D8h+var_290]; this
0x14009f124  mov     r8d, 0BFBh; unsigned int
0x14009f12a  mov     rdx, rbp; struct D3DXShader::D3DXTOKEN *
0x14009f12d  mov     qword ptr [rsp+2D8h+var_2B8], rax
0x14009f132  call    ?Error@CParse@D3DXShader@@IEAAXPEAUD3DXTOKEN@2@IPEBDZZ; D3DXShader::CParse::Error(D3DXShader::D3DXTOKEN *,uint,char const *,...)
0x14009f137  mov     eax, [rsp+2D8h+arg_30]
0x14009f13e  mov     r12d, 2
0x14009f144  test    rbx, rbx
0x14009f147  jz      short loc_14009F171
0x14009f149  test    r12b, al
0x14009f14c  jz      short loc_14009F157
0x14009f14e  mov     rax, [rsi+30h]
0x14009f152  mov     [rbx], rax
0x14009f155  jmp     short loc_14009F171
0x14009f157  mov     rcx, [rsi+30h]; struct D3DXShader::CNode *
0x14009f15b  test    rcx, rcx
0x14009f15e  jz      short loc_14009F171
0x14009f160  call    ?Copy@CNode@D3DXShader@@SAPEAV12@PEAV12@@Z; D3DXShader::CNode::Copy(D3DXShader::CNode *)
0x14009f165  mov     [rbx], rax
0x14009f168  test    rax, rax
0x14009f16b  jz      loc_14009F272
0x14009f171  mov     r13, [rsp+2D8h+var_268]
0x14009f176  test    r13, r13
0x14009f179  jz      loc_14009F285
0x14009f17f  mov     [rsp+2D8h+var_280], 0
0x14009f188  lea     rbx, [rsp+2D8h+var_280]
0x14009f18d  xor     edi, edi
0x14009f18f  lea     r14, ??_7CNodeValue@D3DXShader@@6B@; const D3DXShader::CNodeValue::`vftable'
0x14009f196  cmp     edi, r15d
0x14009f199  jnb     loc_14009F27C
0x14009f19f  mov     rcx, cs:?s_pAlloc@CNode@D3DXShader@@1PEAVCAlloc@D3DXCore@@EA; this
0x14009f1a6  mov     edx, 28h ; '('; unsigned int
0x14009f1ab  lea     r8d, [rdx-18h]; unsigned int
0x14009f1af  call    ?Alloc@CAlloc@D3DXCore@@QEAAPEAEII@Z; D3DXCore::CAlloc::Alloc(uint,uint)
0x14009f1b4  test    rax, rax
0x14009f1b7  jz      loc_14009F26B
0x14009f1bd  lea     rcx, ??_7CNodeList@D3DXShader@@6B@; const D3DXShader::CNodeList::`vftable'
0x14009f1c4  mov     dword ptr [rax+8], 1
0x14009f1cb  mov     [rax], rcx
0x14009f1ce  mov     edx, 68h ; 'h'; unsigned int
0x14009f1d3  lea     rcx, aValues; "Values"
0x14009f1da  mov     qword ptr [rax+10h], 0
0x14009f1e2  mov     [rax+20h], rcx
0x14009f1e6  mov     rcx, cs:?s_pAlloc@CNode@D3DXShader@@1PEAVCAlloc@D3DXCore@@EA; this
0x14009f1ed  mov     qword ptr [rax+18h], 0
0x14009f1f5  lea     r8d, [rdx-58h]; unsigned int
0x14009f1f9  mov     [rbx], rax
0x14009f1fc  call    ?Alloc@CAlloc@D3DXCore@@QEAAPEAEII@Z; D3DXCore::CAlloc::Alloc(uint,uint)
0x14009f201  mov     rdx, rax
0x14009f204  test    rax, rax
0x14009f207  jz      short loc_14009F24F
0x14009f209  mov     rcx, [rsp+rdi*8+2D8h+var_258]
0x14009f211  mov     eax, [rcx+48h]
0x14009f214  mov     dword ptr [rdx+8], 0Eh
0x14009f21b  mov     qword ptr [rdx+10h], 0
0x14009f223  mov     qword ptr [rdx+18h], 0
0x14009f22b  mov     [rdx], r14
0x14009f22e  mov     [rdx+20h], r12d
0x14009f232  mov     [rdx+28h], eax
0x14009f235  movups  xmm0, xmmword ptr [rbp+0]
0x14009f239  movups  xmmword ptr [rdx+38h], xmm0
0x14009f23d  movups  xmm1, xmmword ptr [rbp+10h]
0x14009f241  movups  xmmword ptr [rdx+48h], xmm1
0x14009f245  movups  xmm0, xmmword ptr [rbp+20h]
0x14009f249  movups  xmmword ptr [rdx+58h], xmm0
0x14009f24d  jmp     short loc_14009F251
0x14009f24f  xor     edx, edx
0x14009f251  mov     rax, [rbx]
0x14009f254  mov     [rax+10h], rdx
0x14009f258  test    rdx, rdx
0x14009f25b  jz      short loc_14009F272
0x14009f25d  mov     rbx, [rbx]
0x14009f260  add     rbx, 18h
0x14009f264  inc     edi
0x14009f266  jmp     loc_14009F196
0x14009f26b  mov     qword ptr [rbx], 0
0x14009f272  mov     eax, 8007000Eh
0x14009f277  jmp     loc_14009F7CE
0x14009f27c  mov     rax, [rsp+2D8h+var_280]
0x14009f281  mov     [r13+0], rax
0x14009f285  xor     eax, eax
0x14009f287  jmp     loc_14009F7CE
0x14009f28c  mov     r15d, [rsp+2D8h+arg_30]
0x14009f294  mov     r12d, 2
0x14009f29a  test    r12b, r15b
0x14009f29d  jnz     loc_14009F7A0
0x14009f2a3  cmp     [rsp+2D8h+var_268], r13
0x14009f2a8  jnz     loc_14009F7A0
0x14009f2ae  mov     eax, [rsp+2D8h+var_288]
0x14009f2b2  test    eax, eax
0x14009f2b4  jnz     loc_14009F660
0x14009f2ba  mov     rcx, [rbp+8]; String1
0x14009f2be  lea     rdx, aDword; "dword"
0x14009f2c5  call    cs:__imp__stricmp
0x14009f2cb  test    eax, eax
0x14009f2cd  jz      short loc_14009F2E9
0x14009f2cf  mov     rcx, [rbp+8]; String1
0x14009f2d3  lea     rdx, aFloat; "float"
0x14009f2da  call    cs:__imp__stricmp
0x14009f2e0  test    eax, eax
  ... truncated ...
```
