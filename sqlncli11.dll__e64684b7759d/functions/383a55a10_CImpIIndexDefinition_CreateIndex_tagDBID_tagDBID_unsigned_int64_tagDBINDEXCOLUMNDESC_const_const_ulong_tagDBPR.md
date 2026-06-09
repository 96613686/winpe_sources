# CImpIIndexDefinition::CreateIndex(tagDBID *,tagDBID *,unsigned __int64,tagDBINDEXCOLUMNDESC const * const,ulong,tagDBPROPSET * const,tagDBID * *)

- ea: `0x383a55a10`
- end: `0x383a56901`
- name: `?CreateIndex@CImpIIndexDefinition@@UEAAJPEAUtagDBID@@0_KQEBUtagDBINDEXCOLUMNDESC@@KQEAUtagDBPROPSET@@PEAPEAU2@@Z`
- size: `3825`
- prototype: `__int64 __fastcall(CImpIIndexDefinition *__hidden this, struct tagDBID *, struct tagDBID *, unsigned __int64, const struct tagDBINDEXCOLUMNDESC *const, unsigned int, struct tagDBPROPSET *const, struct tagDBID **)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3838434c0`
- `0x3838463a4`
- `0x38384a190`
- `0x38384ac10`
- `0x38384ce20`
- `0x38384d2c0`
- `0x38384dd38`
- `0x38387da60`
- `0x38391ac40`
- `0x38391aed0`
- `0x38391af80`
- `0x38391afe0`
- `0x3839bd770`
- `0x3839bd830`
- `0x3839d3fc0`
- `0x383a02c50`
- `0x383a4b180`
- `0x383a55a10`
- `0x383a97d8c`
- `0x383a9eaa0`
- `0x383a9eb90`

## import_xrefs

- `MSVCR100!_ltow` at `0x383a563d8`
- `MSVCR100!_ltow` at `0x383a563d8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a55b33`
- `OLEAUT32!__imp_SetErrorInfo` at `0x383a55b33`

## string_xrefs

- `0x383a56042`: `create`
- `0x383a56090`: ` primary xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CImpIIndexDefinition::CreateIndex(
        CImpIIndexDefinition *this,
        struct tagDBID *a2,
        struct tagDISPPARAMS *a3,
        unsigned __int64 a4,
        const struct tagDBINDEXCOLUMNDESC *const a5,
        unsigned int a6,
        struct tagDBPROPSET *const a7,
        struct tagDBID **a8)
{
  const struct tagDBINDEXCOLUMNDESC *v12; // r15
  __int64 v13; // rax
  CDataSource *v14; // rsi
  CIndexProps *v15; // r12
  __int64 *v16; // rbx
  __int64 v17; // rax
  const struct _GUID *v18; // r8
  int v19; // eax
  unsigned __int64 *v20; // r9
  int v21; // ebx
  LPOLESTR pwszName; // rcx
  unsigned __int64 v23; // rdx
  LPOLESTR p_vt; // r14
  unsigned __int64 v25; // rdx
  char *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  int v29; // eax
  int v30; // eax
  unsigned int v31; // r9d
  char v32; // al
  unsigned int v33; // edi
  struct CExtByteBuffer *v34; // rax
  struct CExtByteBuffer *v35; // rdi
  unsigned int v36; // esi
  __int64 v37; // rax
  LPOLESTR v38; // rdx
  __int64 v39; // r8
  __int64 v40; // r8
  int v41; // eax
  int v42; // eax
  int v43; // eax
  __int64 v44; // rcx
  int v45; // eax
  int v46; // eax
  int v47; // eax
  __int64 v48; // r8
  LPOLESTR v49; // rdx
  __int64 v50; // r8
  int v51; // eax
  DBID *pColumnID; // rbx
  const unsigned __int16 *v53; // rbx
  unsigned __int64 v54; // rdx
  __int64 v55; // r8
  int v56; // eax
  int v57; // eax
  int v58; // ecx
  __int64 v59; // r8
  CCommand *v60; // rax
  CImpIIndexDefinition *v61; // rbx
  CCommand *v62; // rsi
  int v63; // eax
  __int64 v64; // r8
  __int64 v65; // rdx
  int v66; // eax
  int v67; // eax
  struct tagDBID *v68; // rax
  __int64 v69; // rdi
  unsigned __int16 *v70; // rcx
  __int64 v71; // rdx
  struct CExtByteBuffer *v72; // rdi
  struct tagDISPPARAMS *v74; // [rsp+20h] [rbp-218h]
  int v75; // [rsp+70h] [rbp-1C8h]
  __int64 v76; // [rsp+78h] [rbp-1C0h] BYREF
  struct CExtByteBuffer *v77; // [rsp+80h] [rbp-1B8h] BYREF
  struct tagDBPROPSET *v78; // [rsp+88h] [rbp-1B0h]
  struct CExtByteBuffer *v79; // [rsp+90h] [rbp-1A8h]
  __int64 v80; // [rsp+98h] [rbp-1A0h]
  CImpIIndexDefinition *v81; // [rsp+A0h] [rbp-198h]
  __int64 v82; // [rsp+A8h] [rbp-190h]
  wchar_t Buffer[16]; // [rsp+B0h] [rbp-188h] BYREF
  unsigned __int16 v84[136]; // [rsp+D0h] [rbp-168h] BYREF

  v82 = -2;
  v81 = this;
  v12 = a5;
  v78 = a7;
  v76 = -1;
  if ( (bidGblFlags & 4) != 0 && off_383B4AC08[0] )
  {
    v74 = a3;
    bidScopeEnterW(&v76, off_383B4AC08[0], *(unsigned int *)(*((_QWORD *)this + 1) + 52LL), a2);
  }
  v75 = 0;
  v13 = *((_QWORD *)this + 1);
  v14 = *(CDataSource **)(v13 + 832);
  v77 = 0;
  v15 = 0;
  v16 = (__int64 *)(v13 + 24);
  if ( v13 == -24 )
  {
    v17 = 0;
  }
  else
  {
    if ( *v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)(*v16 + 32) + 8LL))(*v16 + 32);
    v17 = *v16;
  }
  v80 = v17;
  SetErrorInfo(0, 0);
  if ( a8 )
    *a8 = 0;
  if ( !a2 || !a3 && !a8 || !a4 || !a5 )
  {
    v21 = -2147024809;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_175;
    v26 = off_383B43410[0];
    if ( !off_383B49128[0] )
      goto LABEL_175;
    v27 = 143401;
LABEL_174:
    bidTraceW(v26, v27, off_383B49128[0], (unsigned int)v21);
    goto LABEL_175;
  }
  v19 = CUtlProps2::SetPropertiesArgChk(a6, v78);
  v21 = v19;
  if ( v19 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 148489, (unsigned int)v19);
    goto LABEL_175;
  }
  if ( a2->eKind != 2 )
    goto LABEL_168;
  pwszName = a2->uName.pwszName;
  if ( !pwszName )
    goto LABEL_168;
  if ( !*pwszName )
    goto LABEL_168;
  v23 = -1;
  do
    ++v23;
  while ( pwszName[v23] );
  if ( !(unsigned int)FIsValidQualifiedName(pwszName, v23, 3u, v20) )
  {
LABEL_168:
    v21 = -2147217865;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_175;
    v26 = off_383B43410[0];
    if ( !off_383B49128[0] )
      goto LABEL_175;
    v27 = 159785;
    goto LABEL_174;
  }
  if ( a3 )
  {
    if ( a3->cArgs != 2 )
      goto LABEL_32;
    p_vt = &a3[1].rgvarg->vt;
    if ( !p_vt )
      goto LABEL_32;
    if ( !*p_vt )
      goto LABEL_32;
    v25 = -1;
    do
      ++v25;
    while ( p_vt[v25] );
    if ( !FIsValidIdentifier(&a3[1].rgvarg->vt, v25) )
    {
LABEL_32:
      v21 = -2147217806;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_175;
      v26 = off_383B43410[0];
      if ( !off_383B49128[0] )
        goto LABEL_175;
      v27 = 174121;
      goto LABEL_174;
    }
  }
  else
  {
    p_vt = v84;
    CDataSource::CreateUniqueIdentifier(v14, v84, 0);
  }
  v28 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 576);
  v15 = (CIndexProps *)v28;
  v79 = (struct CExtByteBuffer *)v28;
  if ( v28 )
  {
    *(_QWORD *)(v28 + 12) = 0;
    *(_DWORD *)(v28 + 40) = 0;
    *(_DWORD *)(v28 + 8) = 0;
    *(_QWORD *)(v28 + 32) = 0;
    *(_QWORD *)(v28 + 48) = 0;
    *(_DWORD *)(v28 + 296) = 0;
    *(_QWORD *)(v28 + 560) = 0;
    *(_QWORD *)(v28 + 568) = 0;
    *(_QWORD *)(v28 + 24) = 0;
    *(_QWORD *)v28 = &CIndexProps::`vftable';
  }
  else
  {
    v15 = 0;
  }
  if ( !v15 )
  {
    v21 = -2147024882;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_175;
    v26 = off_383B43410[0];
    if ( !off_383B49128[0] )
      goto LABEL_175;
    v27 = 190505;
    goto LABEL_174;
  }
  v29 = (*(__int64 (__fastcall **)(CIndexProps *, _QWORD))(*(_QWORD *)v15 + 16LL))(v15, 0);
  v21 = v29;
  if ( v29 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 196617, (unsigned int)v29);
    goto LABEL_175;
  }
  v30 = CIndexProps::SetProperties(v15, a6, v78);
  v21 = v30;
  if ( v30 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 200713, (unsigned int)v30);
    goto LABEL_175;
  }
  v75 = v30;
  if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 40LL) + 40LL) == 0xFFFF && a4 != 1 )
  {
    v32 = bidGblFlags;
    v33 = -2147467259;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_383B49128[0] )
      {
        LODWORD(v74) = 207;
        bidTraceW(off_383B43410[0], 212009, off_383B49128[0], 2147500037LL);
      }
      v32 = bidGblFlags;
    }
    v21 = -2147467259;
    if ( (v32 & 2) != 0 )
      v33 = bidTraceHR(off_383B43410[0], 213001, 2147500037LL);
    CError::PostError((CError *)v33, (int)&IID_IIndexDefinition, (const struct _GUID *)0x9F19, v31, v74);
    goto LABEL_191;
  }
  v34 = (struct CExtByteBuffer *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(
                                   g_pMO,
                                   48);
  v35 = v34;
  v79 = v34;
  v36 = 0;
  if ( v34 )
  {
    *(_QWORD *)v34 = 0;
    *((_QWORD *)v34 + 1) = 0;
    *((_QWORD *)v34 + 2) = 0;
    *((_QWORD *)v34 + 3) = 0;
    *((_QWORD *)v34 + 4) = 0;
    *((_QWORD *)v34 + 5) = 0;
  }
  else
  {
    v35 = 0;
  }
  v77 = v35;
  if ( !v35
    || (*(_QWORD *)v35 = 1, *((_QWORD *)v35 + 3) = 1024, *((_QWORD *)v35 + 2) = 1024, *((_QWORD *)v35 + 4))
    || (v37 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl->Alloc)(g_pMO, 1024),
        (*((_QWORD *)v35 + 4) = v37) == 0) )
  {
    v21 = -2147024882;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_175;
    v26 = off_383B43410[0];
    if ( !off_383B49128[0] )
      goto LABEL_175;
    v27 = 225321;
    goto LABEL_174;
  }
  if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 16LL) + 152LL) != 0xFFFF )
  {
    v43 = CExtByteBuffer::WriteIntoExtBuffer(v35, L"create", 0xCu);
    v21 = v43;
    if ( v43 >= 0 )
    {
      v44 = *((_QWORD *)v15 + 6);
      if ( *(_WORD *)(*(_QWORD *)(v44 + 40) + 40LL) == 0xFFFF )
      {
        v45 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" primary xml", 0x18u);
        v21 = v45;
        if ( v45 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
            bidTraceHR(off_383B43410[0], 271369, (unsigned int)v45);
          goto LABEL_175;
        }
      }
      else
      {
        if ( *(_WORD *)(*(_QWORD *)(v44 + 16) + 208LL) == 0xFFFF )
        {
          v46 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" unique", 0xEu);
          v21 = v46;
          if ( v46 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
              bidTraceHR(off_383B43410[0], 280585, (unsigned int)v46);
            goto LABEL_175;
          }
        }
        if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 16LL) + 40LL) == 0xFFFF )
        {
          v47 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" clustered", 0x14u);
          v21 = v47;
          if ( v47 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
              bidTraceHR(off_383B43410[0], 288777, (unsigned int)v47);
            goto LABEL_175;
          }
        }
      }
      v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" index ", 0xEu);
      if ( v21 < 0 )
        goto LABEL_175;
      v48 = -1;
      do
        ++v48;
      while ( p_vt[v48] );
      v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, p_vt, 2 * v48);
      if ( v21 < 0 )
        goto LABEL_175;
      v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" on ", 8u);
      if ( v21 < 0 )
        goto LABEL_175;
      v49 = a2->uName.pwszName;
      v50 = -1;
      do
        ++v50;
      while ( v49[v50] );
      v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, v49, 2 * v50);
      if ( v21 < 0 )
        goto LABEL_175;
      goto LABEL_104;
    }
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 263177, (unsigned int)v43);
LABEL_175:
    v62 = 0;
    goto LABEL_176;
  }
  v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, L"alter table ", 0x18u);
  if ( v21 < 0 )
    goto LABEL_175;
  v38 = a2->uName.pwszName;
  v39 = -1;
  do
    ++v39;
  while ( v38[v39] );
  v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, v38, 2 * v39);
  if ( v21 < 0 )
    goto LABEL_175;
  v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" add constraint ", 0x20u);
  if ( v21 < 0 )
    goto LABEL_175;
  v40 = -1;
  do
    ++v40;
  while ( p_vt[v40] );
  v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, p_vt, 2 * v40);
  if ( v21 < 0 )
    goto LABEL_175;
  v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" primary key ", 0x1Au);
  if ( v21 < 0 )
    goto LABEL_175;
  if ( *(_WORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 16LL) + 40LL) != 0xFFFF )
  {
    v42 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" nonclustered", 0x1Au);
    v21 = v42;
    if ( v42 >= 0 )
      goto LABEL_104;
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 256009, (unsigned int)v42);
    goto LABEL_175;
  }
  v41 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" clustered", 0x14u);
  v21 = v41;
  if ( v41 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 249865, (unsigned int)v41);
    goto LABEL_175;
  }
LABEL_104:
  v51 = CExtByteBuffer::WriteWCharToExtBuffer(v35, 0x28u);
  v21 = v51;
  if ( v51 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 306185, (unsigned int)v51);
    goto LABEL_175;
  }
  do
  {
    if ( v36 )
    {
      v21 = CExtByteBuffer::WriteWCharToExtBuffer(v35, 0x2Cu);
      if ( v21 < 0 )
        goto LABEL_175;
    }
    if ( v12->eIndexColOrder )
    {
      v21 = -2147024809;
      if ( (bidGblFlags & 2) != 0 )
      {
        v26 = off_383B43410[0];
        if ( off_383B49128[0] )
        {
          v27 = 317481;
          goto LABEL_174;
        }
      }
      goto LABEL_175;
    }
    pColumnID = v12->pColumnID;
    if ( !v12->pColumnID )
      goto LABEL_124;
    if ( pColumnID->eKind != 2 )
      goto LABEL_124;
    v53 = pColumnID->uName.pwszName;
    if ( !v53 )
      goto LABEL_124;
    if ( !*v53 )
      goto LABEL_124;
    v54 = -1;
    do
      ++v54;
    while ( v53[v54] );
    if ( !FIsValidIdentifier(v53, v54) )
    {
LABEL_124:
      v21 = -2147217819;
      if ( (bidGblFlags & 2) != 0 )
      {
        v26 = off_383B43410[0];
        if ( off_383B49128[0] )
        {
          v27 = 329769;
          goto LABEL_174;
        }
      }
      goto LABEL_175;
    }
    v55 = -1;
    do
      ++v55;
    while ( v53[v55] );
    v56 = CExtByteBuffer::WriteIntoExtBuffer(v35, v53, 2 * v55);
    v21 = v56;
    if ( v56 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
        bidTraceHR(off_383B43410[0], 336905, (unsigned int)v56);
      goto LABEL_175;
    }
    ++v36;
    ++v12;
  }
  while ( v36 < a4 );
  v57 = CExtByteBuffer::WriteWCharToExtBuffer(v35, 0x29u);
  v21 = v57;
  if ( v57 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
      bidTraceHR(off_383B43410[0], 341001, (unsigned int)v57);
    goto LABEL_175;
  }
  v58 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v15 + 6) + 16LL) + 96LL);
  if ( v58 )
  {
    _ltow(v58, Buffer, 10);
    v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, L" with fillfactor=", 0x22u);
    if ( v21 < 0 )
      goto LABEL_175;
    v59 = -1;
    do
      ++v59;
    while ( Buffer[v59] );
    v21 = CExtByteBuffer::WriteIntoExtBuffer(v35, Buffer, 2 * v59);
    if ( v21 < 0 )
      goto LABEL_175;
  }
  v60 = (CCommand *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 1552);
  v79 = v60;
  v61 = v81;
  if ( v60 )
    v62 = CCommand::CCommand(v60, *((struct CDBSession **)v81 + 1), 0);
  else
    v62 = 0;
  if ( !v62 )
  {
    v21 = -2147024882;
    if ( (bidGblFlags & 2) != 0 && off_383B49128[0] )
      bidTraceW(off_383B43410[0], 367657, off_383B49128[0], 2147942414LL);
    goto LABEL_176;
  }
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v61 + 1) + 40LL) + 8LL))(*(_QWORD *)(*((_QWORD *)v61 + 1)
                                                                                                + 40LL));
  (*(void (__fastcall **)(CCommand *))(*(_QWORD *)v62 + 8LL))(v62);
  v63 = CCommand::FInit(v62, 0, 0);
  v21 = v63;
  if ( v63 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_185;
    v64 = (unsigned int)v63;
    v65 = 376841;
LABEL_184:
    bidTraceHR(off_383B43410[0], v65, v64);
    goto LABEL_185;
  }
  *((GUID *)v62 + 79) = IID_IIndexDefinition;
  *((_DWORD *)v62 + 374) = 5;
  CCommand::ApplyGeneralTimeout(v62);
  v66 = CCommand::Prepare(v62, 0x40u, &IID_IIndexDefinition, &v77);
  v21 = v66;
  if ( v66 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_185;
    v64 = (unsigned int)v66;
    v65 = 388105;
    goto LABEL_184;
  }
  v67 = CCommand::Execute(v62, 0, &GUID_NULL, 0, 0, 0);
  v21 = v67;
  if ( v67 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_185;
    v64 = (unsigned int)v67;
    v65 = 392201;
    goto LABEL_184;
  }
  if ( !a8 )
    goto LABEL_185;
  v68 = (struct tagDBID *)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(g_pIMalloc, 32);
  *a8 = v68;
  if ( v68 )
  {
    v69 = -1;
    do
      ++v69;
    while ( p_vt[v69] );
    v68->eKind = 2;
    (*a8)->uName.pwszName = (LPOLESTR)((__int64 (__fastcall *)(LPMALLOC, __int64))g_pIMalloc->lpVtbl->Alloc)(
                                        g_pIMalloc,
                                        2 * v69 + 2);
    v70 = (*a8)->uName.pwszName;
    if ( v70 )
    {
      StringCchCopyW(v70, v69 + 1, p_vt);
      if ( *a8 )
        goto LABEL_185;
    }
    else
    {
      ((void (__fastcall *)(LPMALLOC))g_pIMalloc->lpVtbl->Free)(g_pIMalloc);
      *a8 = 0;
    }
  }
  v21 = -2147024882;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_383B49128[0] )
      bidTraceW(off_383B43410[0], 417833, off_383B49128[0], 2147942414LL);
LABEL_176:
    if ( (bidGblFlags & 2) != 0 )
    {
      v71 = 433161;
      if ( v21 || (bidGblFlags & 0x40) != 0 )
      {
        if ( off_383B49128[0] )
        {
          if ( v21 < 0 )
            v71 = 433193;
          bidTraceW(off_383B43410[0], v71, off_383B49128[0], (unsigned int)v21);
        }
      }
    }
  }
  CError::PostHResult((CError *)(unsigned int)v21, (int)&IID_IIndexDefinition, v18);
LABEL_185:
  v72 = v77;
  if ( v77 )
  {
    v79 = v77;
    if ( *((_QWORD *)v77 + 4) )
    {
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
      *((_QWORD *)v72 + 4) = 0;
    }
    ((void (__fastcall *)(struct IMalloc *, struct CExtByteBuffer *))g_pMO->lpVtbl[1].Realloc)(g_pMO, v77);
  }
  if ( v62 )
    (*(void (__fastcall **)(CCommand *))(*(_QWORD *)v62 + 16LL))(v62);
LABEL_191:
  if ( v15 )
    (*(void (__fastcall **)(CIndexProps *, __int64))(*(_QWORD *)v15 + 8LL))(v15, 1);
  if ( !v21 )
    v21 = v75;
  if ( (bidGblFlags & 2) != 0 && off_383B49CF0[0] )
    bidTraceW(off_383B43410[0], 429056, off_383B49CF0[0], (unsigned int)v21);
  if ( v80 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v80 + 32) + 24LL))(v80 + 32);
    v80 = 0;
  }
  if ( v76 != -1 )
  {
    if ( (bidGblFlags & 4) != 0 )
    {
      if ( bidID != -1 )
        off_383B15058();
    }
    else
    {
      v76 = -1;
    }
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x383a55a10  push    rbx
0x383a55a12  push    rbp
0x383a55a13  push    rsi
0x383a55a14  push    rdi
0x383a55a15  push    r12
0x383a55a17  push    r13
0x383a55a19  push    r14
0x383a55a1b  push    r15
0x383a55a1d  sub     rsp, 1F8h
0x383a55a24  mov     [rsp+238h+var_190], 0FFFFFFFFFFFFFFFEh
0x383a55a30  mov     rax, cs:__security_cookie
0x383a55a37  xor     rax, rsp
0x383a55a3a  mov     [rsp+238h+var_58], rax
0x383a55a42  mov     r13, r9
0x383a55a45  mov     rdi, r8
0x383a55a48  mov     rbp, rdx
0x383a55a4b  mov     rbx, rcx
0x383a55a4e  mov     [rsp+238h+var_198], rcx
0x383a55a56  mov     r15, [rsp+238h+arg_20]
0x383a55a5e  mov     rcx, [rsp+238h+arg_30]
0x383a55a66  mov     [rsp+238h+var_1B0], rcx
0x383a55a6e  mov     r14, [rsp+238h+arg_38]
0x383a55a76  mov     [rsp+238h+var_1D8], r14
0x383a55a7b  mov     [rsp+238h+var_1C0], 0FFFFFFFFFFFFFFFFh
0x383a55a84  test    byte ptr cs:_bidGblFlags, 4
0x383a55a8b  jz      short loc_383A55AE3
0x383a55a8d  mov     rax, cs:off_383B4AC08; "<IIndexDefinition::CreateIndex|OLEDB|AP"...
0x383a55a94  test    rax, rax
0x383a55a97  jz      short loc_383A55AE3
0x383a55a99  mov     rax, [rbx+8]
0x383a55a9d  mov     [rsp+238h+var_1E0], r14
0x383a55aa2  mov     [rsp+238h+var_1E8], rcx
0x383a55aa7  mov     [rsp+238h+var_1F0], r9
0x383a55aac  mov     ecx, [rsp+238h+arg_28]
0x383a55ab3  mov     [rsp+238h+var_1F8], ecx
0x383a55ab7  mov     [rsp+238h+var_200], r15
0x383a55abc  mov     [rsp+238h+var_208], r9
0x383a55ac1  mov     [rsp+238h+var_210], r9
0x383a55ac6  mov     [rsp+238h+var_218], r8
0x383a55acb  mov     r9, rdx
0x383a55ace  mov     r8d, [rax+34h]
0x383a55ad2  mov     rdx, cs:off_383B4AC08; "<IIndexDefinition::CreateIndex|OLEDB|AP"...
0x383a55ad9  lea     rcx, [rsp+238h+var_1C0]
0x383a55ade  call    _bidScopeEnterW
0x383a55ae3  xor     ecx, ecx
0x383a55ae5  mov     [rsp+238h+var_1C8], ecx
0x383a55ae9  mov     rax, [rbx+8]
0x383a55aed  mov     rsi, [rax+340h]
0x383a55af4  mov     [rsp+238h+var_1D0], rcx
0x383a55af9  mov     [rsp+238h+var_1B8], rcx
0x383a55b01  mov     r12d, ecx
0x383a55b04  lea     rbx, [rax+18h]
0x383a55b08  test    rbx, rbx
0x383a55b0b  jz      short loc_383A55B24
0x383a55b0d  mov     rcx, [rbx]
0x383a55b10  test    rcx, rcx
0x383a55b13  jz      short loc_383A55B1F
0x383a55b15  add     rcx, 20h ; ' '
0x383a55b19  mov     rax, [rcx]
0x383a55b1c  call    qword ptr [rax+8]
0x383a55b1f  mov     rax, [rbx]
0x383a55b22  jmp     short loc_383A55B27
0x383a55b24  mov     rax, rcx
0x383a55b27  mov     [rsp+238h+var_1A0], rax
0x383a55b2f  xor     edx, edx; perrinfo
0x383a55b31  xor     ecx, ecx; dwReserved
0x383a55b33  call    cs:__imp_SetErrorInfo
0x383a55b39  test    r14, r14
0x383a55b3c  jz      short loc_383A55B45
0x383a55b3e  mov     qword ptr [r14], 0
0x383a55b45  test    rbp, rbp
0x383a55b48  jz      loc_383A56705
0x383a55b4e  test    rdi, rdi
0x383a55b51  jnz     short loc_383A55B5C
0x383a55b53  test    r14, r14
0x383a55b56  jz      loc_383A56705
0x383a55b5c  test    r13, r13
0x383a55b5f  jz      loc_383A56705
0x383a55b65  test    r15, r15
0x383a55b68  jz      loc_383A56705
0x383a55b6e  mov     rdx, [rsp+238h+var_1B0]; struct tagDBPROPSET *
0x383a55b76  mov     ecx, [rsp+238h+arg_28]; unsigned int
0x383a55b7d  call    ?SetPropertiesArgChk@CUtlProps2@@SAJKQEBUtagDBPROPSET@@@Z; CUtlProps2::SetPropertiesArgChk(ulong,tagDBPROPSET const * const)
0x383a55b82  mov     ebx, eax
0x383a55b84  test    eax, eax
0x383a55b86  jns     short loc_383A55BAE
0x383a55b88  test    byte ptr cs:_bidGblFlags, 2
0x383a55b8f  jz      loc_383A56742
0x383a55b95  mov     r8d, eax
0x383a55b98  mov     edx, 24409h
0x383a55b9d  mov     rcx, cs:off_383B43410; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a55ba4  call    _bidTraceHR
0x383a55ba9  jmp     loc_383A56742
0x383a55bae  cmp     dword ptr [rbp+10h], 2
0x383a55bb2  jnz     loc_383A566D5
0x383a55bb8  mov     rcx, [rbp+18h]; unsigned __int16 *
0x383a55bbc  test    rcx, rcx
0x383a55bbf  jz      loc_383A566D5
0x383a55bc5  cmp     word ptr [rcx], 0
0x383a55bc9  jz      loc_383A566D5
0x383a55bcf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x383a55bd3  inc     rdx; unsigned __int64
0x383a55bd6  cmp     word ptr [rcx+rdx*2], 0
0x383a55bdb  jnz     short loc_383A55BD3
0x383a55bdd  mov     r8d, 3; unsigned __int64
0x383a55be3  call    ?FIsValidQualifiedName@@YAHPEBG_K1PEA_K@Z; FIsValidQualifiedName(ushort const *,unsigned __int64,unsigned __int64,unsigned __int64 *)
0x383a55be8  test    eax, eax
0x383a55bea  jz      loc_383A566D5
0x383a55bf0  test    rdi, rdi
0x383a55bf3  jz      short loc_383A55C62
0x383a55bf5  cmp     dword ptr [rdi+10h], 2
0x383a55bf9  jnz     short loc_383A55C27
0x383a55bfb  mov     r14, [rdi+18h]
0x383a55bff  test    r14, r14
0x383a55c02  jz      short loc_383A55C27
0x383a55c04  cmp     word ptr [r14], 0
0x383a55c09  jz      short loc_383A55C27
0x383a55c0b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x383a55c0f  nop
0x383a55c10  inc     rdx; unsigned __int64
0x383a55c13  cmp     word ptr [r14+rdx*2], 0
0x383a55c19  jnz     short loc_383A55C10
0x383a55c1b  mov     rcx, r14; unsigned __int16 *
0x383a55c1e  call    ?FIsValidIdentifier@@YAHPEBG_K@Z; FIsValidIdentifier(ushort const *,unsigned __int64)
0x383a55c23  test    eax, eax
0x383a55c25  jnz     short loc_383A55C7D
0x383a55c27  mov     ebx, 80040E72h
0x383a55c2c  test    byte ptr cs:_bidGblFlags, 2
0x383a55c33  jz      loc_383A56742
0x383a55c39  mov     rcx, cs:off_383B43410; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a55c40  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a55c47  test    rax, rax
0x383a55c4a  jz      loc_383A56742
0x383a55c50  mov     dword ptr [rsp+238h+var_218], 0AAh
0x383a55c58  mov     edx, 2A829h
0x383a55c5d  jmp     loc_383A56733
0x383a55c62  lea     r14, [rsp+238h+var_168]
0x383a55c6a  xor     r8d, r8d; unsigned __int64
0x383a55c6d  lea     rdx, [rsp+238h+var_168]; unsigned __int16 *
0x383a55c75  mov     rcx, rsi; this
0x383a55c78  call    ?CreateUniqueIdentifier@CDataSource@@QEAAXPEAG_KH@Z; CDataSource::CreateUniqueIdentifier(ushort *,unsigned __int64,int)
0x383a55c7d  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a55c84  mov     rax, [rcx]
0x383a55c87  mov     edx, 240h
0x383a55c8c  call    qword ptr [rax+58h]
0x383a55c8f  mov     r12, rax
0x383a55c92  mov     [rsp+238h+var_1A8], rax
0x383a55c9a  test    rax, rax
0x383a55c9d  jz      short loc_383A55CE4
0x383a55c9f  xor     eax, eax
0x383a55ca1  mov     [r12+0Ch], rax
0x383a55ca6  mov     [r12+28h], eax
0x383a55cab  mov     [r12+8], eax
0x383a55cb0  mov     [r12+20h], rax
0x383a55cb5  mov     [r12+30h], rax
0x383a55cba  mov     [r12+128h], eax
0x383a55cc2  mov     [r12+230h], rax
0x383a55cca  mov     [r12+238h], rax
0x383a55cd2  mov     [r12+18h], rax
0x383a55cd7  lea     rax, ??_7CIndexProps@@6B@; const CIndexProps::`vftable'
0x383a55cde  mov     [r12], rax
0x383a55ce2  jmp     short loc_383A55CE7
0x383a55ce4  xor     r12d, r12d
0x383a55ce7  test    r12, r12
0x383a55cea  jnz     short loc_383A55D27
0x383a55cec  mov     ebx, 8007000Eh
0x383a55cf1  test    byte ptr cs:_bidGblFlags, 2
0x383a55cf8  jz      loc_383A56742
0x383a55cfe  mov     rcx, cs:off_383B43410; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a55d05  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a55d0c  test    rax, rax
0x383a55d0f  jz      loc_383A56742
0x383a55d15  mov     dword ptr [rsp+238h+var_218], 0BAh
0x383a55d1d  mov     edx, 2E829h
0x383a55d22  jmp     loc_383A56733
0x383a55d27  mov     rax, [r12]
0x383a55d2b  xor     edx, edx
0x383a55d2d  mov     rcx, r12
0x383a55d30  call    qword ptr [rax+10h]
0x383a55d33  mov     ebx, eax
0x383a55d35  test    eax, eax
0x383a55d37  jns     short loc_383A55D5F
0x383a55d39  test    byte ptr cs:_bidGblFlags, 2
0x383a55d40  jz      loc_383A56742
0x383a55d46  mov     r8d, eax
0x383a55d49  mov     edx, 30009h
0x383a55d4e  mov     rcx, cs:off_383B43410; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a55d55  call    _bidTraceHR
0x383a55d5a  jmp     loc_383A56742
0x383a55d5f  mov     rsi, [rsp+238h+var_1B0]
0x383a55d67  mov     r8, rsi; struct tagDBPROPSET *
0x383a55d6a  mov     edx, [rsp+238h+arg_28]; unsigned int
0x383a55d71  mov     rcx, r12; this
0x383a55d74  call    ?SetProperties@CIndexProps@@QEAAJKQEBUtagDBPROPSET@@@Z; CIndexProps::SetProperties(ulong,tagDBPROPSET const * const)
0x383a55d79  mov     ebx, eax
0x383a55d7b  test    eax, eax
0x383a55d7d  jns     short loc_383A55DA5
0x383a55d7f  test    byte ptr cs:_bidGblFlags, 2
0x383a55d86  jz      loc_383A56742
0x383a55d8c  mov     r8d, eax
0x383a55d8f  mov     edx, 31009h
0x383a55d94  mov     rcx, cs:off_383B43410; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a55d9b  call    _bidTraceHR
0x383a55da0  jmp     loc_383A56742
0x383a55da5  mov     [rsp+238h+var_1C8], eax
0x383a55da9  mov     rax, [r12+30h]
0x383a55dae  mov     rcx, [rax+28h]
0x383a55db2  cmp     word ptr [rcx+28h], 0FFFFh
0x383a55db7  jnz     loc_383A55E41
0x383a55dbd  cmp     r13, 1
0x383a55dc1  jz      short loc_383A55E41
0x383a55dc3  mov     eax, cs:_bidGblFlags
0x383a55dc9  mov     edi, 80004005h
0x383a55dce  test    al, 2
0x383a55dd0  jz      short loc_383A55E07
0x383a55dd2  mov     rcx, cs:off_383B43410; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a55dd9  mov     rax, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a55de0  test    rax, rax
0x383a55de3  jz      short loc_383A55E01
0x383a55de5  mov     dword ptr [rsp+238h+var_218], 0CFh; struct tagDISPPARAMS *
0x383a55ded  mov     r9d, edi
0x383a55df0  mov     r8, cs:off_383B49128; "<Trace|HR> 0x%08X{HRESULT} line %d\n"
0x383a55df7  mov     edx, 33C29h
0x383a55dfc  call    _bidTraceW
0x383a55e01  mov     eax, cs:_bidGblFlags
0x383a55e07  mov     ebx, edi
0x383a55e09  test    al, 2
0x383a55e0b  jz      short loc_383A55E23
0x383a55e0d  mov     r8d, edi
0x383a55e10  mov     edx, 34009h
0x383a55e15  mov     rcx, cs:off_383B43410; "d:\\b\\s1\\sources\\sql\\ntdbms\\sqlncl"...
0x383a55e1c  call    _bidTraceHR
0x383a55e21  mov     edi, eax
0x383a55e23  mov     r8d, 9F19h; struct _GUID *
0x383a55e29  lea     rdx, IID_IIndexDefinition; int
0x383a55e30  mov     ecx, edi; this
0x383a55e32  call    ?PostError@CError@@QEAAJJPEBU_GUID@@KPEAUtagDISPPARAMS@@@Z; CError::PostError(long,_GUID const *,ulong,tagDISPPARAMS *)
0x383a55e37  mov     r15, [rsp+238h+var_1D8]
0x383a55e3c  jmp     loc_383A5681E
0x383a55e41  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a55e48  mov     rax, [rcx]
0x383a55e4b  mov     edx, 30h ; '0'
0x383a55e50  call    qword ptr [rax+58h]
0x383a55e53  mov     rdi, rax
0x383a55e56  mov     [rsp+238h+var_1A8], rax
0x383a55e5e  xor     esi, esi
0x383a55e60  test    rax, rax
0x383a55e63  jz      short loc_383A55E7E
0x383a55e65  mov     [rax], rsi
0x383a55e68  mov     [rax+8], rsi
0x383a55e6c  mov     [rax+10h], rsi
0x383a55e70  mov     [rax+18h], rsi
0x383a55e74  mov     [rax+20h], rsi
0x383a55e78  mov     [rax+28h], rsi
0x383a55e7c  jmp     short loc_383A55E81
0x383a55e7e  mov     rdi, rsi
0x383a55e81  mov     [rsp+238h+var_1B8], rdi
0x383a55e89  test    rdi, rdi
0x383a55e8c  jz      loc_383A566A1
0x383a55e92  mov     qword ptr [rdi], 1
0x383a55e99  mov     qword ptr [rdi+18h], 400h
0x383a55ea1  mov     qword ptr [rdi+10h], 400h
0x383a55ea9  cmp     qword ptr [rdi+20h], 0
0x383a55eae  jnz     loc_383A566A1
0x383a55eb4  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a55ebb  mov     rax, [rcx]
0x383a55ebe  mov     edx, 400h
0x383a55ec3  call    qword ptr [rax+18h]
0x383a55ec6  mov     [rdi+20h], rax
0x383a55eca  mov     ecx, esi
0x383a55ecc  test    rax, rax
0x383a55ecf  setnz   cl
0x383a55ed2  test    ecx, ecx
0x383a55ed4  jz      loc_383A566A1
0x383a55eda  mov     rax, [r12+30h]
0x383a55edf  mov     rcx, [rax+10h]
0x383a55ee3  cmp     word ptr [rcx+98h], 0FFFFh
0x383a55eeb  mov     rcx, rdi; this
0x383a55eee  jnz     loc_383A5603C
0x383a55ef4  mov     r8d, 18h; Size
0x383a55efa  lea     rdx, aAlterTable_1; "alter table "
0x383a55f01  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x383a55f06  mov     ebx, eax
0x383a55f08  test    eax, eax
0x383a55f0a  js      loc_383A56742
0x383a55f10  mov     rdx, [rbp+18h]; Src
0x383a55f14  or      r8, 0FFFFFFFFFFFFFFFFh
0x383a55f18  nop     dword ptr [rax+rax+00000000h]
0x383a55f20  inc     r8
0x383a55f23  cmp     word ptr [rdx+r8*2], 0
0x383a55f29  jnz     short loc_383A55F20
0x383a55f2b  add     r8, r8; Size
0x383a55f2e  mov     rcx, rdi; this
0x383a55f31  call    ?WriteIntoExtBuffer@CExtByteBuffer@@QEAAJPEBX_K@Z; CExtByteBuffer::WriteIntoExtBuffer(void const *,unsigned __int64)
0x383a55f36  mov     ebx, eax
0x383a55f38  test    eax, eax
0x383a55f3a  js      loc_383A56742
0x383a55f40  mov     r8d, 20h ; ' '; Size
0x383a55f46  lea     rdx, aAddConstraint; " add constraint "
0x383a55f4d  mov     rcx, rdi; this
  ... truncated ...
```
