# CCommand::DeriveFromStmt(_GUID const *,ushort const *,unsigned __int64,unsigned __int64,PARAMINFO *,int *,unsigned __int64,unsigned __int64 *)

- ea: `0x383a73eb0`
- end: `0x383a75c4d`
- name: `?DeriveFromStmt@CCommand@@QEAAJPEBU_GUID@@PEBG_K2PEAUPARAMINFO@@PEAH2PEA_K@Z`
- size: `7581`
- prototype: `int(CCommand *__hidden this, const struct _GUID *, const unsigned __int16 *, unsigned __int64, unsigned __int64, struct PARAMINFO *, int *, unsigned __int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x383a73870`

## callees

- `0x383847f70`
- `0x383848660`
- `0x3838489f0`
- `0x383849f80`
- `0x38384c670`
- `0x3838527a0`
- `0x383876cf0`
- `0x383877450`
- `0x38387da60`
- `0x38389a5a0`
- `0x38391aed0`
- `0x38391afe0`
- `0x3839bd220`
- `0x3839bd770`
- `0x3839bdb30`
- `0x3839e3460`
- `0x3839edfc0`
- `0x383a14790`
- `0x383a1e790`
- `0x383a41b40`
- `0x383a58490`
- `0x383a70610`
- `0x383a73eb0`
- `0x383a75c60`
- `0x383a77a50`

## import_xrefs

- `MSVCR100!wcsstr` at `0x383a74b2f`
- `MSVCR100!wcsstr` at `0x383a74b2f`
- `MSVCR100!towlower` at `0x383a73ffa`
- `MSVCR100!towlower` at `0x383a73ffa`
- `MSVCR100!iswspace` at `0x383a74ab8`
- `MSVCR100!iswspace` at `0x383a74ab8`
- `MSVCR100!_wcsnicmp` at `0x383a73f9d`
- `MSVCR100!_wcsnicmp` at `0x383a73fb4`
- `MSVCR100!_wcsnicmp` at `0x383a73fcb`
- `MSVCR100!_wcsnicmp` at `0x383a73fe2`
- `MSVCR100!_wcsnicmp` at `0x383a7411d`
- `MSVCR100!_wcsnicmp` at `0x383a7417a`
- `MSVCR100!_wcsnicmp` at `0x383a741ef`
- `MSVCR100!_wcsnicmp` at `0x383a74242`
- `MSVCR100!_wcsnicmp` at `0x383a74357`
- `MSVCR100!_wcsnicmp` at `0x383a74669`
- `MSVCR100!_wcsnicmp` at `0x383a746ca`
- `MSVCR100!_wcsnicmp` at `0x383a74726`
- `MSVCR100!_wcsnicmp` at `0x383a73f9d`
- `MSVCR100!_wcsnicmp` at `0x383a73fb4`
- `MSVCR100!_wcsnicmp` at `0x383a73fcb`
- `MSVCR100!_wcsnicmp` at `0x383a73fe2`
- `MSVCR100!_wcsnicmp` at `0x383a7411d`
- `MSVCR100!_wcsnicmp` at `0x383a7417a`
- `MSVCR100!_wcsnicmp` at `0x383a741ef`
- `MSVCR100!_wcsnicmp` at `0x383a74242`
- `MSVCR100!_wcsnicmp` at `0x383a74357`
- `MSVCR100!_wcsnicmp` at `0x383a74669`
- `MSVCR100!_wcsnicmp` at `0x383a746ca`
- `MSVCR100!_wcsnicmp` at `0x383a74726`

## string_xrefs

- `0x383a73f90`: `update`
- `0x383a73fd5`: `delete`

## pseudocode

```c
int __fastcall CCommand::DeriveFromStmt(
        CDBConnection **this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        struct PARAMINFO *a6,
        int *a7,
        unsigned __int64 a8,
        unsigned __int64 *a9)
{
  CCommand *v9; // r13
  CDataSource *v10; // rbx
  unsigned __int16 *v11; // rsi
  unsigned __int64 v12; // r12
  __int64 v13; // r15
  struct CErrorData *v14; // r9
  int v15; // eax
  size_t v16; // rdi
  unsigned __int64 v17; // rbx
  unsigned __int64 v18; // r15
  wint_t v19; // r13
  const unsigned __int16 *v20; // rsi
  unsigned __int64 v21; // r12
  unsigned int LexToken; // eax
  unsigned __int64 v23; // rdi
  int v24; // ebx
  unsigned int v25; // eax
  unsigned __int16 v26; // di
  char *v27; // rcx
  __int64 v28; // rdx
  size_t v29; // rbx
  unsigned int i; // eax
  unsigned __int64 v31; // rdi
  const unsigned __int16 *v32; // rcx
  unsigned __int64 v33; // rdx
  unsigned __int64 v34; // r14
  const unsigned __int16 *v35; // rbx
  const unsigned __int16 *v36; // rbx
  unsigned __int64 v37; // r12
  unsigned __int16 *v38; // r14
  CCommand *v39; // rsi
  unsigned __int64 v40; // r12
  unsigned int v41; // r15d
  __int64 j; // rbx
  unsigned __int64 v43; // rdi
  __int16 v44; // ax
  unsigned __int64 v45; // r13
  const struct _GUID *v46; // r8
  unsigned __int64 v47; // rax
  unsigned __int64 v48; // rcx
  unsigned __int64 v49; // rbx
  __int64 v50; // rax
  unsigned __int16 *v51; // rax
  size_t v52; // rbx
  const unsigned __int16 *v53; // rcx
  unsigned __int64 v54; // rdx
  unsigned int v55; // esi
  unsigned __int64 v56; // r14
  size_t v57; // r15
  unsigned int v58; // eax
  int v59; // eax
  const unsigned __int16 *v60; // rbx
  unsigned __int64 v61; // rdi
  int v62; // r11d
  unsigned int v63; // edx
  size_t v64; // rcx
  const unsigned __int16 *v65; // rbx
  CCommand *v66; // r15
  unsigned __int64 v67; // rax
  size_t v68; // rcx
  struct IMallocVtbl *lpVtbl; // r8
  unsigned __int64 v70; // rax
  unsigned __int16 *v71; // rax
  unsigned __int64 v72; // r14
  unsigned __int64 v73; // rax
  __int64 v74; // rsi
  __int64 v75; // rax
  __int64 v76; // rax
  wchar_t *v77; // rax
  int *v78; // rsi
  __int64 v79; // r14
  unsigned __int64 v80; // rbx
  unsigned __int16 Expression; // ax
  unsigned __int64 v82; // rsi
  unsigned __int16 *v83; // rbx
  unsigned __int64 v84; // rax
  unsigned __int64 v85; // r15
  unsigned __int64 v86; // r12
  unsigned __int16 *v87; // rdi
  unsigned __int16 *v88; // rcx
  unsigned __int16 v89; // ax
  __int64 v90; // r15
  unsigned __int16 v91; // ax
  unsigned __int64 v92; // r12
  unsigned __int64 k; // rbx
  __int64 v94; // rcx
  __int64 v95; // rdi
  __int64 v96; // r15
  unsigned __int64 v97; // rsi
  wchar_t v98; // ax
  unsigned __int64 m; // rbx
  wchar_t *v100; // rcx
  unsigned __int64 v101; // r14
  wchar_t *v102; // rcx
  unsigned __int64 v103; // rax
  unsigned __int64 v104; // rbx
  unsigned __int16 v105; // ax
  unsigned __int64 v106; // rdi
  const unsigned __int16 *v107; // r8
  unsigned __int64 v108; // rbx
  unsigned __int16 *v109; // r14
  unsigned __int64 v110; // rdi
  unsigned __int64 v111; // r11
  unsigned __int16 *v112; // r8
  unsigned __int16 v113; // ax
  unsigned __int64 v114; // rax
  char *v115; // rcx
  __int64 v116; // rdx
  __int64 v117; // rcx
  int v118; // r14d
  int MetadataQuery; // ebx
  unsigned __int64 v120; // r10
  unsigned __int64 v121; // rbx
  unsigned __int16 *v122; // r14
  unsigned __int64 v123; // rdx
  unsigned __int16 *v124; // rcx
  unsigned __int64 v125; // r8
  unsigned __int16 v126; // ax
  unsigned __int64 v127; // rbx
  unsigned __int16 *v128; // rcx
  unsigned __int64 v129; // rdx
  unsigned __int16 *v130; // r13
  __int64 v131; // rsi
  unsigned __int64 v132; // rbx
  CCommand *v133; // r13
  int v134; // eax
  int v135; // ebx
  struct PARAMINFO *v136; // r14
  unsigned __int64 v137; // rsi
  unsigned __int64 v138; // rcx
  unsigned __int16 *v139; // rax
  const unsigned __int16 *v140; // rbx
  unsigned __int64 v141; // r12
  unsigned __int64 v142; // r15
  unsigned __int64 *v143; // r12
  struct PARAMINFO *v144; // r13
  unsigned __int64 v145; // r13
  CCommand *v146; // r12
  int v147; // edi
  __int16 v148; // ax
  int *v149; // rdi
  CCommand *v150; // rcx
  CDBConnection *v151; // rax
  __int64 v152; // r9
  __int64 v153; // r9
  int v154; // eax
  struct CExtByteBuffer *v156; // [rsp+20h] [rbp-E0h]
  unsigned __int16 v157; // [rsp+80h] [rbp-80h]
  wchar_t *SubStr; // [rsp+88h] [rbp-78h]
  __int64 v159; // [rsp+90h] [rbp-70h]
  unsigned __int64 v160; // [rsp+98h] [rbp-68h] BYREF
  size_t MaxCount; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int v162; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v163; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v164; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v165; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v166; // [rsp+C8h] [rbp-38h] BYREF
  int v167; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v168; // [rsp+D8h] [rbp-28h] BYREF
  const unsigned __int16 *v169; // [rsp+E0h] [rbp-20h]
  CCommand *v170; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v171; // [rsp+F0h] [rbp-10h]
  wint_t v172; // [rsp+F8h] [rbp-8h]
  wchar_t *Str; // [rsp+100h] [rbp+0h]
  unsigned __int64 v174; // [rsp+108h] [rbp+8h]
  unsigned __int16 *v175; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v176; // [rsp+118h] [rbp+18h]
  unsigned __int64 v177; // [rsp+120h] [rbp+20h] BYREF
  unsigned __int64 v178; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v179; // [rsp+130h] [rbp+30h]
  int v180; // [rsp+138h] [rbp+38h]
  unsigned __int64 v181; // [rsp+140h] [rbp+40h]
  unsigned __int64 v182; // [rsp+148h] [rbp+48h]
  unsigned __int64 v183; // [rsp+150h] [rbp+50h]
  __int64 v184; // [rsp+158h] [rbp+58h]
  CDataSource *v185; // [rsp+160h] [rbp+60h]
  unsigned __int64 v189; // [rsp+1D8h] [rbp+D8h] BYREF

  v189 = a4;
  v9 = (CCommand *)this;
  v10 = (CDataSource *)*((_QWORD *)this[55] + 104);
  v11 = a3;
  v12 = a4;
  v175 = 0;
  v163 = 0;
  v185 = v10;
  v157 = 0;
  v174 = 0;
  v167 = 0;
  v179 = 0;
  v13 = 0;
  v159 = 0;
  SubStr = 0;
  Str = 0;
  v181 = 0;
  while ( 2 )
  {
    if ( GetLexToken(v11, v12, &v160, &MaxCount) != 1
      || (v15 = CDataSource::FSQL11OrNewer(v10), v16 = MaxCount, v17 = v160, !v15)
      && !(unsigned int)FIsStmtKeyword(&v11[v160], MaxCount, *(struct CDataSource **)(*((_QWORD *)v9 + 55) + 832LL)) )
    {
      v26 = -25400;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_375;
      v27 = off_383B43460[0];
      if ( !off_383B49128[0] )
        goto LABEL_375;
      v28 = 4348969;
LABEL_374:
      bidTraceW(v27, v28, off_383B49128[0], 2147500037LL);
      goto LABEL_375;
    }
    if ( v16 == 6 )
    {
      if ( !_wcsnicmp(L"update", &v11[v17], 6u)
        || !_wcsnicmp(L"select", &v11[v17], 6u)
        || !_wcsnicmp(L"insert", &v11[v17], 6u)
        || !_wcsnicmp(L"delete", &v11[v17], 6u) )
      {
        goto LABEL_10;
      }
      goto LABEL_26;
    }
    if ( v16 == 4 )
    {
      if ( !_wcsnicmp(L"exec", &v11[v17], 4u) )
        goto LABEL_10;
LABEL_26:
      v26 = -25400;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_375;
      v27 = off_383B43460[0];
      if ( !off_383B49128[0] )
        goto LABEL_375;
      v28 = 4364329;
      goto LABEL_374;
    }
    if ( v16 != 7 || _wcsnicmp(L"execute", &v11[v17], 7u) )
      goto LABEL_26;
LABEL_10:
    v18 = 0;
    v19 = towlower(v11[v17]);
    v172 = v19;
    v20 = &v11[v17 + v16];
    v21 = v12 - (v17 + v16);
    if ( v19 == 115 && v21 )
    {
      while ( 1 )
      {
        LexToken = GetLexToken(v20, v21, &v160, &MaxCount);
        if ( LexToken != 3 )
          goto LABEL_36;
        do
        {
          v23 = v160;
          if ( v20[v160] != 40 )
          {
            if ( v20[v160] == 41 )
            {
              v26 = -25400;
              if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              {
                bidTraceW(off_383B43460[0], 4448297, off_383B49128[0], 2147500037LL);
                v13 = v159;
                goto LABEL_375;
              }
              goto LABEL_23;
            }
            if ( v20[v160] != 63 )
            {
LABEL_50:
              v29 = MaxCount;
              goto LABEL_51;
            }
            v26 = -25400;
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
            {
              bidTraceW(off_383B43460[0], 4464681, off_383B49128[0], 2147500037LL);
              v13 = v159;
              goto LABEL_375;
            }
LABEL_23:
            v13 = v159;
            goto LABEL_375;
          }
          v24 = 1;
          do
          {
            v20 += v23 + MaxCount;
            v21 -= v23 + MaxCount;
            if ( !v21 )
            {
              v26 = -25400;
              if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              {
                bidTraceW(off_383B43460[0], 4400169, off_383B49128[0], 2147500037LL);
                v13 = v159;
                goto LABEL_375;
              }
              goto LABEL_23;
            }
            v25 = GetLexToken(v20, v21, &v160, &MaxCount);
            v23 = v160;
            if ( v25 == 3 )
            {
              switch ( v20[v160] )
              {
                case '(':
                  ++v24;
                  break;
                case ')':
                  --v24;
                  break;
                case '?':
                  v26 = -25400;
                  if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                    bidTraceW(off_383B43460[0], 4425769, off_383B49128[0], 2147500037LL);
                  goto LABEL_23;
              }
            }
          }
          while ( v24 );
          v20 += v160 + MaxCount;
          v21 -= v160 + MaxCount;
          LexToken = GetLexToken(v20, v21, &v160, &MaxCount);
        }
        while ( LexToken == 3 );
LABEL_36:
        v23 = v160;
        if ( LexToken != 1 )
          goto LABEL_50;
        v29 = MaxCount;
        if ( MaxCount == 4 && !_wcsnicmp(L"from", &v20[v160], 4u) )
          break;
LABEL_51:
        v20 += v29 + v23;
        v21 -= v29 + v23;
        if ( !v21 )
        {
          v26 = -25400;
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          {
            bidTraceW(off_383B43460[0], 4473897, off_383B49128[0], 2147500037LL);
            v13 = v159;
            goto LABEL_375;
          }
          goto LABEL_23;
        }
      }
    }
    i = GetLexToken(v20, v21, &v160, &MaxCount);
    if ( i != 1 )
    {
      if ( i != 3 )
      {
LABEL_69:
        v31 = v160;
        goto LABEL_70;
      }
      if ( v19 != 101 || v20[v160] != 63 )
      {
LABEL_368:
        v26 = -25400;
        if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        {
          bidTraceW(off_383B43460[0], 4545577, off_383B49128[0], 2147500037LL);
          v13 = v159;
          goto LABEL_375;
        }
        goto LABEL_23;
      }
      v18 = 1;
      v36 = &v20[MaxCount + v160];
      v37 = v21 - (MaxCount + v160);
      GetLexToken(v36, v37, &v160, &MaxCount);
      v20 = &v36[MaxCount + v160];
      v21 = v37 - (MaxCount + v160);
      v32 = v20;
      v33 = v21;
LABEL_68:
      i = GetLexToken(v32, v33, &v160, &MaxCount);
      goto LABEL_69;
    }
    if ( MaxCount != 4 )
      goto LABEL_63;
    if ( v19 == 105 )
    {
      v31 = v160;
      if ( _wcsnicmp(L"into", &v20[v160], 4u) )
        goto LABEL_71;
LABEL_58:
      v20 += v31 + 4;
      v21 += -4LL - v31;
      v32 = v20;
      v33 = v21;
      if ( v19 == 115 )
      {
        v166 = v31;
        v168 = (unsigned __int16 *)4;
        v34 = v21;
        v31 = 0;
        v160 = 0;
        MaxCount = 0;
        v35 = v20;
        for ( i = GetLexToken(v20, v21, &v166, (unsigned __int64 *)&v168);
              i == 3;
              i = GetLexToken(v35, v34, &v166, (unsigned __int64 *)&v168) )
        {
          if ( v35[v166] != 40 )
            break;
          v35 += (__int64)v168 + v166;
          v34 -= (unsigned __int64)v168 + v166;
        }
LABEL_70:
        if ( i != 1 )
          goto LABEL_368;
        goto LABEL_71;
      }
      goto LABEL_68;
    }
    if ( v19 == 115 || v19 == 100 )
    {
      v31 = v160;
      if ( !_wcsnicmp(L"from", &v20[v160], 4u) )
        goto LABEL_58;
    }
    else
    {
LABEL_63:
      v31 = v160;
    }
LABEL_71:
    v38 = (unsigned __int16 *)&v20[v31];
    v168 = v38;
    v39 = (CCommand *)&v20[v31 + MaxCount];
    v40 = v21 - (v31 + MaxCount);
    v170 = v39;
    v166 = v40;
    if ( v19 == 101 )
      return CCommand::DeriveFromSProc(
               (CCommand *)this,
               a2,
               v38,
               MaxCount,
               (const unsigned __int16 *)v39,
               v40,
               a5,
               v18,
               a6,
               a9);
    v41 = GetLexToken((const unsigned __int16 *)v39, v40, &v160, &MaxCount);
    v162 = v41;
    if ( v19 == 115 )
    {
      for ( j = 0; v40; v162 = v41 )
      {
        v43 = v160;
        if ( v41 == 1 )
        {
          if ( !j && (unsigned int)FIsEndFromClause((wchar_t *)v39 + v160, v40 - v160) )
            goto LABEL_85;
        }
        else if ( v41 == 3 )
        {
          v44 = *((_WORD *)v39 + v160);
          if ( v44 == 40 )
          {
            ++j;
          }
          else if ( v44 == 41 )
          {
            --j;
          }
        }
        v39 = (CCommand *)((char *)v39 + 2 * v43 + 2 * MaxCount);
        v40 -= v43 + MaxCount;
        v170 = v39;
        v166 = v40;
        v41 = GetLexToken((const unsigned __int16 *)v39, v40, &v160, &MaxCount);
      }
    }
    v43 = v160;
LABEL_85:
    v45 = (v39 - (CCommand *)v38) >> 1;
    if ( IndexWChar(0x3Fu, v38, v45) < v45 )
    {
      v26 = -25400;
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      {
        bidTraceW(off_383B43460[0], 4609065, off_383B49128[0], 2147500037LL);
        v13 = v159;
        goto LABEL_375;
      }
      goto LABEL_23;
    }
    if ( !v163 )
    {
      v47 = 130 * a5;
      if ( !is_mul_ok(0x82u, a5)
        || (v48 = v47 + v189, v47 + v189 < v47)
        || (v49 = v48 + 13, v174 = v48 + 13, v48 + 13 < v48) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v115 = off_383B43460[0];
          if ( off_383B49128[0] )
          {
            v116 = 4621353;
            goto LABEL_213;
          }
        }
        goto LABEL_214;
      }
      v50 = 2 * v49;
      if ( !is_mul_ok(v49, 2u) )
        v50 = -1;
      v51 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v50);
      v163 = v51;
      if ( !v51 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          v115 = off_383B43460[0];
          if ( off_383B49128[0] )
          {
            v116 = 4629545;
            goto LABEL_213;
          }
        }
        goto LABEL_214;
      }
      StringCchCopyW(v51, v49, L"select ");
      v171 = 7;
    }
    v52 = MaxCount;
    v53 = (const unsigned __int16 *)v39;
    v54 = v40;
    v55 = v41;
    v56 = v43;
    v57 = MaxCount;
    v176 = v40;
    v169 = v53;
    if ( !v40 )
      goto LABEL_110;
    v58 = v162;
    while ( 1 )
    {
      if ( v58 == 1 && v52 == 5 )
      {
        if ( !_wcsnicmp(L"union", &v53[v43], 5u) )
          goto LABEL_114;
        v53 = v169;
        v54 = v176;
      }
      v169 = &v53[v52 + v43];
      v176 = v54 - (v52 + v43);
      v58 = GetLexToken(v169, v176, &v160, &MaxCount);
      v52 = MaxCount;
      v43 = v160;
      v162 = v58;
      if ( MaxCount != 5 )
      {
        v53 = v169;
        goto LABEL_109;
      }
      v59 = _wcsnicmp(L"union", &v169[v160], 5u);
      v53 = v169;
      if ( !v59 )
        break;
LABEL_108:
      v58 = v162;
LABEL_109:
      v54 = v176;
      if ( !v176 )
        goto LABEL_110;
    }
    v178 = 0;
    v177 = 0;
    v60 = &v169[v43 + 5];
    if ( v176 - v43 == 5 )
    {
LABEL_107:
      v52 = MaxCount;
      goto LABEL_108;
    }
    GetLexToken(&v169[v43 + 5], v176 - v43 - 5, &v178, &v177);
    if ( v177 != 3 )
    {
LABEL_106:
      v53 = v169;
      goto LABEL_107;
    }
    v61 = v178;
    if ( _wcsnicmp(L"all", &v60[v178], 3u) )
    {
      v43 = v160;
      goto LABEL_106;
    }
    v68 = v61 + 8;
    v43 = v160;
    MaxCount = v68;
LABEL_114:
    if ( v176 )
    {
      v180 = 1;
      v167 = 1;
      v65 = (const unsigned __int16 *)(v40 - v176);
      if ( v179 )
        goto LABEL_120;
      lpVtbl = g_pMO->lpVtbl;
      v182 = 0;
      v70 = 2 * v174;
      if ( !is_mul_ok(v174, 2u) )
        v70 = -1;
      v71 = (unsigned __int16 *)((__int64 (__fastcall *)(struct IMalloc *, unsigned __int64))lpVtbl[1].Free)(g_pMO, v70);
      v179 = v71;
      if ( v71 )
      {
        *v71 = 0;
LABEL_120:
        v13 = v159;
        v72 = v189;
        if ( !v159 )
        {
          v73 = 2 * v189;
          if ( !is_mul_ok(v189, 2u) )
            v73 = -1;
          v13 = ((__int64 (__fastcall *)(struct IMalloc *, unsigned __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v73);
          v159 = v13;
          if ( !v13 )
          {
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43460[0], 4728873, off_383B49128[0], 2147942414LL);
            v118 = (int)a2;
            v26 = v157;
            MetadataQuery = CError::PostHResult((CError *)0x8007000ELL, (int)a2, v46);
            goto LABEL_377;
          }
        }
        v74 = (__int64)SubStr;
        if ( !SubStr )
        {
          v75 = 2 * v72;
          if ( !is_mul_ok(v72, 2u) )
            v75 = -1;
          v74 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v75);
          SubStr = (wchar_t *)v74;
          if ( !v74 )
          {
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43460[0], 4740137, off_383B49128[0], 2147942414LL);
            v118 = (int)a2;
            v26 = v157;
            MetadataQuery = CError::PostHResult((CError *)0x8007000ELL, (int)a2, v46);
            goto LABEL_378;
          }
        }
        if ( !Str )
        {
          v76 = 2 * v72;
          if ( !is_mul_ok(v72, 2u) )
            v76 = -1;
          v77 = (wchar_t *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v76);
          Str = v77;
          if ( !v77 )
          {
            if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
              bidTraceW(off_383B43460[0], 4753449, off_383B49128[0], 2147942414LL);
            v118 = (int)a2;
            v26 = v157;
            MetadataQuery = CError::PostHResult((CError *)0x8007000ELL, (int)a2, v46);
            goto LABEL_380;
          }
          *v77 = 0;
        }
LABEL_111:
        v66 = v170;
        v67 = CCommand::CountParamMarkers(v170, v65, (unsigned __int64)v46);
        v64 = MaxCount;
        v63 = v162;
        v62 = v167;
        goto LABEL_134;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        v115 = off_383B43460[0];
        if ( off_383B49128[0] )
        {
          v116 = 4713513;
          goto LABEL_213;
        }
      }
      goto LABEL_214;
    }
LABEL_110:
    v62 = v167;
    v63 = v55;
    v64 = v57;
    v65 = (const unsigned __int16 *)v40;
    v43 = v56;
    v180 = 0;
    v162 = v55;
    v160 = v56;
    MaxCount = v57;
    if ( v167 )
      goto LABEL_111;
    v67 = a5;
    v66 = v170;
LABEL_134:
    v183 = v67;
    if ( v67 > a8 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B43460[0], 4772905, off_383B49128[0], 2147549183LL);
      v117 = 2147549183LL;
      goto LABEL_215;
    }
    v78 = a7;
    v79 = v62;
    v80 = 1;
    v184 = v62;
LABEL_136:
    v177 = (unsigned __int64)v78;
    v178 = v80;
    if ( v80 > v67 )
    {
LABEL_202:
      if ( v180 )
      {
        v13 = v159;
        v9 = (CCommand *)this;
        v10 = v185;
        v12 = v176 - v43 - MaxCount;
        v11 = (unsigned __int16 *)&v169[v43 + MaxCount];
        continue;
      }
      v120 = v174;
      v121 = v171 - 1;
      if ( v174 < v171 - 1 )
      {
        if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
          goto LABEL_237;
        bidTraceW(off_383B43460[0], 5014569, off_383B49128[0], 2147500037LL);
        v13 = v159;
        v26 = v157;
        goto LABEL_375;
      }
      v122 = v163;
      v123 = v174 - v121;
      if ( v174 != v121 && v123 <= 0x7FFFFFFF )
      {
        v124 = &v163[v121];
        v125 = 2147483646 - v123;
        v14 = (struct CErrorData *)((char *)L" from " - (char *)v124);
        while ( v125 + v123 )
        {
          v126 = *(_WORD *)((char *)v14 + (_QWORD)v124);
          if ( !v126 )
            break;
          *v124++ = v126;
          if ( !--v123 )
            goto LABEL_271;
        }
        if ( v123 )
          goto LABEL_272;
LABEL_271:
        --v124;
LABEL_272:
        *v124 = 0;
      }
      v127 = v121 + 6;
      if ( v120 < v127 )
      {
        if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
          goto LABEL_237;
        bidTraceW(off_383B43460[0], 5028905, off_383B49128[0], 2147500037LL);
        v13 = v159;
        v26 = v157;
        goto LABEL_375;
      }
      v128 = &v122[v127];
      v129 = v120 - v127;
      if ( v167 )
      {
        v130 = v179;
        v131 = v182 - 1;
        StringCchCopyNW(v128, v129, v179, v182 - 1);
        v132 = v131 + v127;
        if ( v130 )
        {
          ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v130);
          v179 = 0;
        }
      }
      else
      {
        StringCchCopyNW(v128, v129, v168, v45);
        v122 = v163;
        v132 = v45 + v127;
      }
      v133 = (CCommand *)this;
      MetadataQuery = CCommand::GetMetadataQuery((CCommand *)this, v122, v132, &v175, &v189);
      if ( MetadataQuery >= 0 )
      {
        if ( !v175 )
        {
          v26 = -25400;
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          {
            bidTraceW(off_383B43460[0], 5065769, off_383B49128[0], 2147500037LL);
            v13 = v159;
            goto LABEL_375;
          }
          goto LABEL_23;
        }
        MetadataQuery = CStmt::HandleFirehoseModeAtExecute(this[151], a2, 1, 0);
        if ( MetadataQuery >= 0 )
        {
          if ( (unsigned int)CDBConnection::CheckOptions(this[150], this[151]) == -1 )
          {
            if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
              goto LABEL_237;
            bidTraceW(off_383B43460[0], 5085225, off_383B49128[0], 2147500037LL);
            v13 = v159;
            v26 = v157;
            goto LABEL_375;
          }
          v134 = CStmt::SQLExecImmediate(this[151], v175, v189);
          if ( v134 == -1
            || v134 == 1
            && !*(_WORD *)CStmt::GetRowMetadata(this[151])
            && (CStmt::SQLMoreResults(this[151]) & 0xFFFE) != 0 )
          {
            CStmt::StmtXferErrors(this[151], (struct CErrorData *)(this + 142));
            CStmt::SQLExecImmediate(this[151], L" set fmtonly off", 0x10u);
            v26 = v157;
          }
          else
          {
            ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v175);
            v135 = 0;
            v175 = 0;
            if ( v122 )
            {
              ((void (__fastcall *)(struct IMalloc *, unsigned __int16 *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v122);
              v163 = 0;
            }
            v136 = (struct PARAMINFO *)(*((_QWORD *)CStmt::GetRowMetadata(this[151]) + 2) + 304LL);
            v137 = *(unsigned __int16 *)CStmt::GetRowMetadata(this[151]);
            if ( v137 >= a5 )
            {
              v138 = v164;
              v139 = v165;
              if ( v164 == 1 && *v165 == 42 )
              {
                v140 = (const unsigned __int16 *)((char *)v66 + 2 * v43 + 2 * MaxCount);
                v141 = v40 - (v43 + MaxCount);
                GetLexToken(v140, v141, &v160, &MaxCount);
                v138 = v164;
                v139 = v165;
                v170 = (CCommand *)&v140[MaxCount + v160];
                v166 = v141 - (MaxCount + v160);
                v135 = 0;
              }
              v142 = 1;
              v189 = 1;
              if ( !a5 )
              {
LABEL_346:
                if ( Str )
                  ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
                if ( v159 )
                  ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v159);
                if ( SubStr )
                  ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
                CStmt::SQLFreeStmt(*((CStmt **)v133 + 151), 0, 0);
                return 0;
              }
              v143 = a9;
              v144 = a6;
              while ( v138 == 1 && *v139 == 42 )
              {
                v145 = v166;
                v146 = v170;
                v147 = 0;
                do
                {
                  if ( GetLexToken((const unsigned __int16 *)v146, v145, &v160, &MaxCount) == 3 )
                  {
                    v148 = *((_WORD *)v146 + v160);
                    if ( v148 == 40 )
                    {
                      ++v147;
                    }
                    else if ( v148 == 41 )
                    {
                      if ( !v147 )
                        break;
                      --v147;
                    }
                    else if ( v148 != 44 || v147 )
                    {
                      if ( v148 == 63 )
                        ++v135;
                    }
                    else
                    {
                      if ( v135 )
                        break;
                      v136 = (struct PARAMINFO *)((char *)v136 + 304);
                      LOWORD(v137) = v137 - 1;
                    }
                  }
                  v146 = (CCommand *)((char *)v146 + 2 * v160 + 2 * MaxCount);
                  v145 -= v160 + MaxCount;
                }
                while ( v145 );
                v142 = v189;
                v170 = (CCommand *)((char *)v146 + 2 * v160 + 2 * MaxCount);
                v143 = a9;
                v166 = v145 - (v160 + MaxCount);
                v144 = a6;
                if ( v135 > 0 )
                  goto LABEL_323;
LABEL_333:
                if ( v142 > a5 )
                {
                  v133 = (CCommand *)this;
                  goto LABEL_346;
                }
                v139 = v165;
                v138 = v164;
                v135 = 0;
              }
              v135 = 1;
LABEL_323:
              v149 = &a7[v142 - 1];
              while ( 1 )
              {
                if ( !(_WORD)v137 )
                {
                  v26 = -24812;
                  goto LABEL_338;
                }
                v150 = (struct PARAMINFO *)((char *)v144 + 64 * (*v143)++);
                if ( v142 > a8 )
                  break;
                v151 = this[151];
                v152 = *((_QWORD *)v151 + 88);
                if ( !v152 || (v153 = *(_QWORD *)(v152 + 1952)) == 0 )
                  LODWORD(v153) = (_DWORD)v151 + 360;
                v154 = CCommand::ParamInfoFromColInfo(
                         v150,
                         v136,
                         (const struct COLINFO *)(unsigned int)*v149,
                         v153,
                         v156);
                if ( v154 < 0 )
                {
                  if ( (bidGblFlags & 2) != 0 )
                    bidTraceHR(off_383B43460[0], 5207049, (unsigned int)v154);
                  goto LABEL_337;
                }
                ++v142;
                --v135;
                v136 = (struct PARAMINFO *)((char *)v136 + 304);
                ++v149;
                LOWORD(v137) = v137 - 1;
                v189 = v142;
                if ( v135 <= 0 )
                  goto LABEL_333;
              }
              if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
                bidTraceW(off_383B43460[0], 5198889, off_383B49128[0], 2147549183LL);
LABEL_337:
              v26 = v157;
LABEL_338:
              v133 = (CCommand *)this;
            }
            else
            {
              v26 = -24812;
            }
          }
          CStmt::SQLFreeStmt(*((CStmt **)v133 + 151), 0, 0);
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          {
            bidTraceW(off_383B43460[0], 5245993, off_383B49128[0], 2147500037LL);
            v13 = v159;
            goto LABEL_375;
          }
          goto LABEL_23;
        }
      }
      else if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      {
        bidTraceW(off_383B43460[0], 5059625, off_383B49128[0], (unsigned int)MetadataQuery);
        v13 = v159;
        v26 = v157;
        goto LABEL_376;
      }
LABEL_258:
      v13 = v159;
      v26 = v157;
      goto LABEL_376;
    }
    break;
  }
  Expression = CCommand::FindExpression(
                 (CCommand *)this,
                 v40 + 1,
                 (const unsigned __int16 *)v66,
                 v40,
                 (const unsigned __int16 *)v66,
                 v172,
                 v80,
                 v43,
                 v64,
                 v63,
                 v189,
                 a3,
                 &v164,
                 (const unsigned __int16 **)&v165,
                 v78);
  v157 = Expression;
  if ( Expression )
  {
    if ( Expression == 999 )
    {
      v11 = v165;
      v12 = v164;
      v17 = 0;
      v16 = 0;
      MaxCount = 0;
      v160 = 0;
      goto LABEL_10;
    }
    if ( Expression == 40157 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        v115 = off_383B43460[0];
        if ( off_383B49128[0] )
        {
          v116 = 4810793;
LABEL_213:
          bidTraceW(v115, v116, off_383B49128[0], 2147942414LL);
        }
      }
LABEL_214:
      v117 = 2147942414LL;
LABEL_215:
      v118 = (int)a2;
      v13 = v159;
      v26 = v157;
      MetadataQuery = CError::PostHResult((CError *)v117, (int)a2, v46);
      goto LABEL_377;
    }
    if ( Expression != 40168 )
    {
      if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
        goto LABEL_237;
      bidTraceW(off_383B43460[0], 4818985, off_383B49128[0], 2147500037LL);
      v13 = v159;
      v26 = v157;
      goto LABEL_375;
    }
    MetadataQuery = -2147217900;
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43460[0], 4814889, off_383B49128[0], 2147749396LL);
    goto LABEL_258;
  }
  if ( !v79 )
  {
    v14 = (struct CErrorData *)v164;
    v112 = v165;
    if ( v164 )
    {
      do
      {
        v113 = *v112;
        if ( *v112 != 32 && v113 != 12 && v113 != 10 && v113 != 13 && v113 != 9 && v113 != 11 )
          break;
        v14 = (struct CErrorData *)((char *)v14 - 1);
        ++v112;
        v164 = (unsigned __int64)v14;
        v165 = v112;
      }
      while ( v14 );
    }
    if ( v174 < v171 )
    {
      if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
        goto LABEL_237;
      bidTraceW(off_383B43460[0], 4981801, off_383B49128[0], 2147500037LL);
      v13 = v159;
      v26 = v157;
      goto LABEL_375;
    }
    StringCchCopyNW(&v163[v171], v174 - v171, v112, (unsigned __int64)v14);
    v111 = v164;
    v114 = v164 + v171;
    v163[v114] = 44;
    v171 = v114 + 1;
    goto LABEL_187;
  }
  v82 = v164;
  v83 = v165;
  v84 = IndexWChar(Expression + 46, v165, v164);
  v85 = v171;
  v86 = v174;
  if ( v82 == v84 )
  {
    if ( v174 < v171 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B43460[0], 4836393, off_383B49128[0], 2147500037LL);
      goto LABEL_237;
    }
    v87 = v168;
    StringCchCopyNW(&v163[v171], v174 - v171, v168, v45);
    v88 = v163;
    v85 += v45 + 1;
    v163[v85 - 1] = 46;
  }
  else
  {
    v87 = v168;
    v88 = v163;
  }
  if ( v82 )
  {
    do
    {
      v89 = *v83;
      if ( *v83 != 32 && v89 != 12 && v89 != 10 && v89 != 13 && v89 != 9 && v89 != 11 )
        break;
      ++v83;
      --v82;
    }
    while ( v82 );
    v165 = v83;
    v164 = v82;
  }
  if ( v86 < v85 )
  {
    if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
      goto LABEL_237;
    bidTraceW(off_383B43460[0], 4855849, off_383B49128[0], 2147500037LL);
    v13 = v159;
    v26 = v157;
    goto LABEL_375;
  }
  StringCchCopyNW(&v88[v85], v86 - v85, v83, v82);
  v90 = v82 + v85 + 1;
  v163[v90 - 1] = 44;
  v171 = v90;
  if ( v45 )
  {
    do
    {
      v91 = *v87;
      if ( *v87 != 32 && v91 != 12 && v91 != 10 && v91 != 13 && v91 != 9 && v91 != 11 )
        break;
      ++v87;
      --v45;
    }
    while ( v45 );
    v168 = v87;
  }
  v92 = 0;
  for ( k = 0; k < v45; ++k )
  {
    if ( !iswspace(v87[k]) )
    {
      ++v92;
      *(_WORD *)(v159 + 2 * v92 - 2) = v87[k];
    }
  }
  v94 = v159;
  v95 = 0;
  *(_WORD *)(v159 + 2 * v92) = 0;
  v96 = 0;
  v97 = 0;
  if ( !v92 )
  {
LABEL_186:
    v111 = v164;
    v66 = v170;
    v78 = (int *)v177;
    v80 = v178;
    v43 = v160;
    v40 = v166;
LABEL_187:
    if ( v111 == 1 && *v165 == 42 )
      goto LABEL_202;
    v67 = v183;
    v64 = MaxCount;
    v63 = v162;
    ++v80;
    ++v78;
    goto LABEL_136;
  }
  while ( 1 )
  {
    v98 = *(_WORD *)(v94 + 2 * v97);
    for ( m = 0; v98 != 44; v98 = *(_WORD *)(v94 + 2 * v97) )
    {
      if ( !v98 )
        break;
      ++v97;
      SubStr[m++] = v98;
    }
    v100 = Str;
    ++v97;
    ++v96;
    SubStr[m] = 0;
    if ( !wcsstr(v100, SubStr) )
      break;
LABEL_184:
    v94 = v159;
    if ( v97 >= v92 )
    {
      v79 = v184;
      goto LABEL_186;
    }
  }
  v101 = 0;
  if ( v189 >= v181 )
  {
    StringCchCopyNW(&Str[v181], v189 - v181, SubStr, m);
    v102 = Str;
    v103 = m + v181;
    Str[v103++] = 44;
    v102[v103] = 0;
    v181 = v103;
    v104 = 0;
    while ( 1 )
    {
      v105 = v168[v104];
      if ( v105 == 44 || !v105 )
      {
        if ( ++v95 == v96 - 1 )
        {
          v101 = v104 + 1;
        }
        else if ( v95 == v96 )
        {
          if ( v104 <= v45 )
            goto LABEL_182;
LABEL_181:
          --v104;
LABEL_182:
          v106 = v182;
          if ( v174 >= v182 )
          {
            v107 = &v168[v101];
            v108 = v104 - v101;
            v109 = v179;
            StringCchCopyNW(&v179[v182], v174 - v182, v107, v108);
            v110 = v108 + v106;
            v109[v110++] = 44;
            v109[v110] = 0;
            v182 = v110;
            v95 = 0;
            goto LABEL_184;
          }
          if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
          {
            bidTraceW(off_383B43460[0], 4957225, off_383B49128[0], 2147500037LL);
            v13 = v159;
            v26 = v157;
            goto LABEL_375;
          }
LABEL_237:
          v13 = v159;
          v26 = v157;
          goto LABEL_375;
        }
      }
      if ( ++v104 > v45 )
        goto LABEL_181;
    }
  }
  if ( (bidGblFlags & 2) == 0 || !off_383B49128[0] )
    goto LABEL_237;
  bidTraceW(off_383B43460[0], 4915241, off_383B49128[0], 2147500037LL);
  v13 = v159;
  v26 = v157;
LABEL_375:
  MetadataQuery = -2147467259;
LABEL_376:
  v118 = (int)a2;
LABEL_377:
  v74 = (__int64)SubStr;
LABEL_378:
  if ( Str )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
LABEL_380:
  if ( v13 )
    ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v13);
  if ( v74 )
    ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].DidAlloc)(g_pMO, v74);
  if ( v163 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
  if ( v175 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
  if ( v179 )
    ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
  if ( MetadataQuery == -2147467259 )
  {
    if ( v26 )
    {
      if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
        bidTraceW(off_383B43460[0], 5261353, off_383B49128[0], 2147500037LL);
      CErrorData::PostStandardError((CErrorData *)(this + 142), v26, -2147467259, 0);
    }
    if ( this[142] )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_383B49128[0] )
          bidTraceW(off_383B43460[0], 5264425, off_383B49128[0], 2147500037LL);
      }
      CError::PostSqlErrors((CError *)0x80004005LL, v118, (const struct _GUID *)this + 71, v14);
    }
  }
  return MetadataQuery;
}

```

## disassembly

```asm
0x383a73eb0  mov     [rsp-8+arg_18], r9
0x383a73eb5  mov     [rsp-8+arg_10], r8
0x383a73eba  mov     [rsp-8+arg_8], rdx
0x383a73ebf  mov     [rsp-8+arg_0], rcx
0x383a73ec4  push    rbp
0x383a73ec5  push    rbx
0x383a73ec6  push    rsi
0x383a73ec7  push    rdi
0x383a73ec8  push    r12
0x383a73eca  push    r13
0x383a73ecc  push    r14
0x383a73ece  push    r15
0x383a73ed0  lea     rbp, [rsp-78h]
0x383a73ed5  sub     rsp, 178h
0x383a73edc  mov     rax, [rcx+1B8h]
0x383a73ee3  xor     r14d, r14d
0x383a73ee6  mov     r13, rcx
0x383a73ee9  mov     rbx, [rax+340h]
0x383a73ef0  movzx   edi, r14w
0x383a73ef4  mov     rsi, r8
0x383a73ef7  mov     r12, r9
0x383a73efa  mov     [rbp+0B0h+var_A0], r14
0x383a73efe  mov     [rbp+0B0h+var_100], r14
0x383a73f02  mov     [rbp+0B0h+var_50], rbx
0x383a73f06  mov     dword ptr [rbp+0B0h+var_130], edi
0x383a73f09  mov     [rbp+0B0h+var_A8], r14
0x383a73f0d  mov     [rbp+0B0h+var_E0], r14d
0x383a73f11  mov     [rbp+0B0h+var_80], r14
0x383a73f15  mov     r15d, r14d
0x383a73f18  mov     [rbp+0B0h+var_120], r14
0x383a73f1c  mov     [rbp+0B0h+SubStr], r14
0x383a73f20  mov     [rbp+0B0h+Str], r14
0x383a73f24  mov     [rbp+0B0h+var_70], r14
0x383a73f28  nop     dword ptr [rax+rax+00000000h]
0x383a73f30  lea     r9, [rbp+0B0h+MaxCount]; unsigned __int64 *
0x383a73f34  lea     r8, [rbp+0B0h+var_118]; unsigned __int64 *
0x383a73f38  mov     rdx, r12; unsigned __int64
0x383a73f3b  mov     rcx, rsi; unsigned __int16 *
0x383a73f3e  call    ?GetLexToken@@YAKPEBG_KPEA_K2@Z; GetLexToken(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x383a73f43  cmp     eax, 1
0x383a73f46  jnz     loc_383A75A8B
0x383a73f4c  mov     rcx, rbx; this
0x383a73f4f  call    ?FSQL11OrNewer@CDataSource@@QEAAHXZ; CDataSource::FSQL11OrNewer(void)
0x383a73f54  mov     rdi, [rbp+0B0h+MaxCount]
0x383a73f58  mov     rbx, [rbp+0B0h+var_118]
0x383a73f5c  test    eax, eax
0x383a73f5e  jnz     short loc_383A73F82
0x383a73f60  mov     rax, [r13+1B8h]
0x383a73f67  lea     rcx, [rsi+rbx*2]; String1
0x383a73f6b  mov     rdx, rdi; MaxCount
0x383a73f6e  mov     r8, [rax+340h]; struct CDataSource *
0x383a73f75  call    ?FIsStmtKeyword@@YAHPEBG_KPEAVCDataSource@@@Z; FIsStmtKeyword(ushort const *,unsigned __int64,CDataSource *)
0x383a73f7a  test    eax, eax
0x383a73f7c  jz      loc_383A75A8B
0x383a73f82  cmp     rdi, 6
0x383a73f86  jnz     loc_383A74109
0x383a73f8c  lea     r14, [rsi+rbx*2]
0x383a73f90  lea     rcx, aUpdate; "update"
0x383a73f97  mov     r8, rdi; MaxCount
0x383a73f9a  mov     rdx, r14; String2
0x383a73f9d  call    cs:__imp__wcsnicmp
0x383a73fa3  test    eax, eax
0x383a73fa5  jz      short loc_383A73FF0
0x383a73fa7  lea     rcx, aSelect_0; "select"
0x383a73fae  mov     r8, rdi; MaxCount
0x383a73fb1  mov     rdx, r14; String2
0x383a73fb4  call    cs:__imp__wcsnicmp
0x383a73fba  test    eax, eax
0x383a73fbc  jz      short loc_383A73FF0
0x383a73fbe  lea     rcx, aInsert; "insert"
0x383a73fc5  mov     r8, rdi; MaxCount
0x383a73fc8  mov     rdx, r14; String2
0x383a73fcb  call    cs:__imp__wcsnicmp
0x383a73fd1  test    eax, eax
0x383a73fd3  jz      short loc_383A73FF0
0x383a73fd5  lea     rcx, aDelete; "delete"
0x383a73fdc  mov     r8, rdi; MaxCount
0x383a73fdf  mov     rdx, r14; String2
0x383a73fe2  call    cs:__imp__wcsnicmp
0x383a73fe8  test    eax, eax
0x383a73fea  jnz     loc_383A7412B
0x383a73ff0  xor     r14d, r14d
0x383a73ff3  movzx   ecx, word ptr [rsi+rbx*2]; C
0x383a73ff7  mov     r15, r14
0x383a73ffa  call    cs:__imp_towlower
0x383a74000  movzx   r13d, ax
0x383a74004  mov     [rbp+0B0h+var_B8], ax
0x383a74008  lea     rax, [rbx+rdi]
0x383a7400c  lea     rsi, [rsi+rax*2]
0x383a74010  lea     rax, [rbx+rdi]
0x383a74014  sub     r12, rax
0x383a74017  cmp     r13w, 73h ; 's'
0x383a7401c  jnz     loc_383A741FD
0x383a74022  test    r12, r12
0x383a74025  jz      loc_383A741FD
0x383a7402b  nop     dword ptr [rax+rax+00h]
0x383a74030  lea     r9, [rbp+0B0h+MaxCount]; unsigned __int64 *
0x383a74034  lea     r8, [rbp+0B0h+var_118]; unsigned __int64 *
0x383a74038  mov     rdx, r12; unsigned __int64
0x383a7403b  mov     rcx, rsi; unsigned __int16 *
0x383a7403e  call    ?GetLexToken@@YAKPEBG_KPEA_K2@Z; GetLexToken(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x383a74043  cmp     eax, 3
0x383a74046  jnz     loc_383A741C6
0x383a7404c  nop     dword ptr [rax+00h]
0x383a74050  mov     rdi, [rbp+0B0h+var_118]
0x383a74054  cmp     word ptr [rsi+rdi*2], 28h ; '('
0x383a74059  jnz     loc_383A74255
0x383a7405f  mov     ebx, 1
0x383a74064  nop     word ptr [rax+rax]
0x383a74069  mov     rcx, [rbp+0B0h+MaxCount]
0x383a7406d  lea     rax, [rdi+rcx]
0x383a74071  lea     rsi, [rsi+rax*2]
0x383a74075  lea     rax, [rdi+rcx]
0x383a74079  sub     r12, rax
0x383a7407c  jz      loc_383A74D69
0x383a74082  lea     r9, [rbp+0B0h+MaxCount]; unsigned __int64 *
0x383a74086  lea     r8, [rbp+0B0h+var_118]; unsigned __int64 *
0x383a7408a  mov     rdx, r12; unsigned __int64
0x383a7408d  mov     rcx, rsi; unsigned __int16 *
0x383a74090  call    ?GetLexToken@@YAKPEBG_KPEA_K2@Z; GetLexToken(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x383a74095  mov     rdi, [rbp+0B0h+var_118]
0x383a74099  cmp     eax, 3
0x383a7409c  jnz     loc_383A7418F
0x383a740a2  movzx   eax, word ptr [rsi+rdi*2]
0x383a740a6  sub     eax, 28h ; '('
0x383a740a9  jz      loc_383A7418D
0x383a740af  dec     eax
0x383a740b1  jz      loc_383A74189
0x383a740b7  cmp     eax, 16h
0x383a740ba  jnz     loc_383A7418F
0x383a740c0  test    byte ptr cs:_bidGblFlags, 2
0x383a740c7  mov     edi, 9CC8h
0x383a740cc  jz      short loc_383A74100
0x383a740ce  mov     rcx, cs:off_383B43460; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a740d5  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a740dc  test    rax, rax
0x383a740df  jz      short loc_383A74100
0x383a740e1  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a740e8  mov     r9d, 80004005h
0x383a740ee  mov     edx, 438829h
0x383a740f3  mov     dword ptr [rsp+1B0h+var_190], 10E2h
0x383a740fb  call    _bidTraceW
0x383a74100  mov     r15, [rbp+0B0h+var_120]
0x383a74104  jmp     loc_383A75ACB
0x383a74109  cmp     rdi, 4
0x383a7410d  jnz     short loc_383A74166
0x383a7410f  lea     rdx, [rsi+rbx*2]; String2
0x383a74113  lea     rcx, aExec; "exec"
0x383a7411a  mov     r8, rdi; MaxCount
0x383a7411d  call    cs:__imp__wcsnicmp
0x383a74123  test    eax, eax
0x383a74125  jz      loc_383A73FF3
0x383a7412b  test    byte ptr cs:_bidGblFlags, 2
0x383a74132  mov     edi, 9CC8h
0x383a74137  jz      loc_383A75ACB
0x383a7413d  mov     rcx, cs:off_383B43460; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a74144  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a7414b  test    rax, rax
0x383a7414e  jz      loc_383A75ACB
0x383a74154  mov     dword ptr [rsp+1B0h+var_190], 10A6h
0x383a7415c  mov     edx, 429829h
0x383a74161  jmp     loc_383A75AB9
0x383a74166  cmp     rdi, 7
0x383a7416a  jnz     short loc_383A7412B
0x383a7416c  lea     rdx, [rsi+rbx*2]; String2
0x383a74170  lea     rcx, aExecute_0; "execute"
0x383a74177  mov     r8, rdi; MaxCount
0x383a7417a  call    cs:__imp__wcsnicmp
0x383a74180  test    eax, eax
0x383a74182  jnz     short loc_383A7412B
0x383a74184  jmp     loc_383A73FF3
0x383a74189  dec     ebx
0x383a7418b  jmp     short loc_383A7418F
0x383a7418d  inc     ebx
0x383a7418f  test    ebx, ebx
0x383a74191  jnz     loc_383A74069
0x383a74197  mov     rcx, [rbp+0B0h+MaxCount]
0x383a7419b  lea     r9, [rbp+0B0h+MaxCount]; unsigned __int64 *
0x383a7419f  lea     r8, [rbp+0B0h+var_118]; unsigned __int64 *
0x383a741a3  lea     rax, [rdi+rcx]
0x383a741a7  lea     rsi, [rsi+rax*2]
0x383a741ab  lea     rax, [rdi+rcx]
0x383a741af  sub     r12, rax
0x383a741b2  mov     rcx, rsi; unsigned __int16 *
0x383a741b5  mov     rdx, r12; unsigned __int64
0x383a741b8  call    ?GetLexToken@@YAKPEBG_KPEA_K2@Z; GetLexToken(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x383a741bd  cmp     eax, 3
0x383a741c0  jz      loc_383A74050
0x383a741c6  mov     rdi, [rbp+0B0h+var_118]
0x383a741ca  cmp     eax, 1
0x383a741cd  jnz     loc_383A742B6
0x383a741d3  mov     rbx, [rbp+0B0h+MaxCount]
0x383a741d7  cmp     rbx, 4
0x383a741db  jnz     loc_383A742CA
0x383a741e1  lea     rdx, [rsi+rdi*2]; String2
0x383a741e5  lea     rcx, aFrom_0; "from"
0x383a741ec  mov     r8, rbx; MaxCount
0x383a741ef  call    cs:__imp__wcsnicmp
0x383a741f5  test    eax, eax
0x383a741f7  jnz     loc_383A742CA
0x383a741fd  lea     r9, [rbp+0B0h+MaxCount]; unsigned __int64 *
0x383a74201  lea     r8, [rbp+0B0h+var_118]; unsigned __int64 *
0x383a74205  mov     rdx, r12; unsigned __int64
0x383a74208  mov     rcx, rsi; unsigned __int16 *
0x383a7420b  call    ?GetLexToken@@YAKPEBG_KPEA_K2@Z; GetLexToken(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x383a74210  cmp     eax, 1
0x383a74213  jnz     loc_383A74408
0x383a74219  cmp     [rbp+0B0h+MaxCount], 4
0x383a7421e  jnz     loc_383A743FF
0x383a74224  cmp     r13w, 69h ; 'i'
0x383a74229  jnz     loc_383A74330
0x383a7422f  mov     rdi, [rbp+0B0h+var_118]
0x383a74233  lea     r8d, [rax+3]; MaxCount
0x383a74237  lea     rcx, aInto; "into"
0x383a7423e  lea     rdx, [rsi+rdi*2]; String2
0x383a74242  call    cs:__imp__wcsnicmp
0x383a74248  test    eax, eax
0x383a7424a  jz      loc_383A74365
0x383a74250  jmp     loc_383A74488
0x383a74255  cmp     eax, 3
0x383a74258  jnz     loc_383A741CA
0x383a7425e  cmp     word ptr [rsi+rdi*2], 29h ; ')'
0x383a74263  jnz     short loc_383A742BB
0x383a74265  test    byte ptr cs:_bidGblFlags, 2
0x383a7426c  mov     edi, 9CC8h
0x383a74271  jz      loc_383A74100
0x383a74277  mov     rcx, cs:off_383B43460; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a7427e  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a74285  test    rax, rax
0x383a74288  jz      loc_383A74100
0x383a7428e  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a74295  mov     r9d, 80004005h
0x383a7429b  mov     edx, 43E029h
0x383a742a0  mov     dword ptr [rsp+1B0h+var_190], 10F8h
0x383a742a8  call    _bidTraceW
0x383a742ad  mov     r15, [rbp+0B0h+var_120]
0x383a742b1  jmp     loc_383A75ACB
0x383a742b6  cmp     eax, 3
0x383a742b9  jnz     short loc_383A742C6
0x383a742bb  cmp     word ptr [rsi+rdi*2], 3Fh ; '?'
0x383a742c0  jz      loc_383A74DBA
0x383a742c6  mov     rbx, [rbp+0B0h+MaxCount]
0x383a742ca  lea     rax, [rbx+rdi]
0x383a742ce  lea     rsi, [rsi+rax*2]
0x383a742d2  lea     rax, [rbx+rdi]
0x383a742d6  sub     r12, rax
0x383a742d9  jnz     loc_383A74030
0x383a742df  test    byte ptr cs:_bidGblFlags, 2
0x383a742e6  mov     edi, 9CC8h
0x383a742eb  jz      loc_383A74100
0x383a742f1  mov     rcx, cs:off_383B43460; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a742f8  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a742ff  test    rax, rax
0x383a74302  jz      loc_383A74100
0x383a74308  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a7430f  mov     r9d, 80004005h
0x383a74315  mov     edx, 444429h
0x383a7431a  mov     dword ptr [rsp+1B0h+var_190], 1111h
0x383a74322  call    _bidTraceW
0x383a74327  mov     r15, [rbp+0B0h+var_120]
0x383a7432b  jmp     loc_383A75ACB
0x383a74330  cmp     r13w, 73h ; 's'
0x383a74335  jz      short loc_383A74342
0x383a74337  cmp     r13w, 64h ; 'd'
0x383a7433c  jnz     loc_383A743FF
0x383a74342  mov     rdi, [rbp+0B0h+var_118]
0x383a74346  lea     rcx, aFrom_0; "from"
0x383a7434d  mov     r8d, 4; MaxCount
0x383a74353  lea     rdx, [rsi+rdi*2]; String2
0x383a74357  call    cs:__imp__wcsnicmp
0x383a7435d  test    eax, eax
0x383a7435f  jnz     loc_383A74488
0x383a74365  mov     rax, 0FFFFFFFFFFFFFFFCh
0x383a7436c  lea     rsi, [rsi+rdi*2]
0x383a74370  sub     rax, rdi
0x383a74373  add     rsi, 8
0x383a74377  add     r12, rax
0x383a7437a  mov     rcx, rsi; unsigned __int16 *
0x383a7437d  mov     rdx, r12; unsigned __int64
0x383a74380  cmp     r13w, 73h ; 's'
0x383a74385  jnz     loc_383A7446E
0x383a7438b  xor     eax, eax
0x383a7438d  mov     [rbp+0B0h+var_E8], rdi
0x383a74391  lea     r9, [rbp+0B0h+var_D8]; unsigned __int64 *
0x383a74395  lea     r8, [rbp+0B0h+var_E8]; unsigned __int64 *
0x383a74399  mov     [rbp+0B0h+var_D8], 4
0x383a743a1  mov     r14, r12
0x383a743a4  mov     edi, eax
0x383a743a6  mov     [rbp+0B0h+var_118], rax
0x383a743aa  mov     [rbp+0B0h+MaxCount], rax
0x383a743ae  mov     rbx, rsi
0x383a743b1  call    ?GetLexToken@@YAKPEBG_KPEA_K2@Z; GetLexToken(ushort const *,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x383a743b6  cmp     eax, 3
0x383a743b9  jnz     loc_383A7447F
0x383a743bf  nop
0x383a743c0  mov     rdx, [rbp+0B0h+var_E8]
0x383a743c4  cmp     word ptr [rbx+rdx*2], 28h ; '('
0x383a743c9  jnz     loc_383A7447F
0x383a743cf  mov     rcx, [rbp+0B0h+var_D8]
0x383a743d3  lea     r9, [rbp+0B0h+var_D8]; unsigned __int64 *
  ... truncated ...
```
