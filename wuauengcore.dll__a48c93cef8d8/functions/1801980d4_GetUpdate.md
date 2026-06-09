# GetUpdate

- ea: `0x1801980d4`
- end: `0x180199a4b`
- name: `GetUpdate`
- size: `6519`
- prototype: `__int64 __fastcall(int, int, int, int, JET_TABLEID tableid, __int64, JET_TABLEID, __int64, __int64, int, __int64, __int64, __int64, __int64, __int64, struct tagDSUpdateMetadata *)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18019a050`

## callees

- `0x1800358a8`
- `0x18003a508`
- `0x180113ae8`
- `0x180113b9c`
- `0x180113c50`
- `0x180133470`
- `0x180133a10`
- `0x180182f58`
- `0x1801832c8`
- `0x1801839f0`
- `0x180183b94`
- `0x180184050`
- `0x180184a68`
- `0x1801853f0`
- `0x180185430`
- `0x1801916e0`
- `0x1801917ac`
- `0x180197044`
- `0x180197160`
- `0x1801977d0`
- `0x1801980d4`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18019977b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18019977b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801987f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801988f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801998dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801999f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801987f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198804`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801988f7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180198cfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801998dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199903`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801999f7`

## pseudocode

```c
__int64 __fastcall GetUpdate(
        int a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        JET_TABLEID tableid,
        __int64 a6,
        JET_TABLEID a7,
        __int64 a8,
        __int64 a9,
        int a10,
        _DWORD *a11,
        _QWORD *a12,
        __int64 a13,
        __int64 a14,
        const WCHAR *a15,
        struct tagDSUpdateMetadata *a16)
{
  struct JET_RETRIEVECOLUMN *v17; // rbx
  unsigned __int64 v18; // r13
  int FileFromRow; // edi
  struct JET_RETRIEVECOLUMN *v20; // rax
  unsigned int v21; // r9d
  __int128 v22; // xmm0
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v26; // eax
  __int64 v27; // r9
  unsigned int v28; // edx
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned int v31; // eax
  __int64 v32; // r9
  unsigned int v33; // edx
  __int64 v34; // rcx
  __int64 v35; // r9
  __int64 v36; // rcx
  __int64 v37; // r9
  __int64 v38; // rcx
  __int64 v39; // rcx
  unsigned __int64 v40; // r14
  int Data; // eax
  __int64 v42; // rax
  JET_ERR *p_err; // rcx
  int err; // ecx
  int v45; // r12d
  unsigned int *v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rax
  unsigned int itagSequence; // eax
  int v50; // eax
  int VarColumns; // eax
  unsigned int v52; // r13d
  struct tagDSFile *v53; // rax
  struct tagDSFile *v54; // r14
  _DWORD *v55; // r9
  __int64 v56; // r8
  __int64 v57; // rcx
  char *v58; // rdx
  _OWORD *v59; // rcx
  __int64 v60; // rax
  void *v61; // rcx
  int v62; // eax
  int v63; // eax
  int v64; // eax
  unsigned int v65; // r9d
  int MultiValSetVar; // eax
  int v67; // eax
  int v68; // eax
  int v69; // eax
  unsigned int v70; // r9d
  unsigned __int128 v71; // rax
  int v72; // eax
  void *v73; // rcx
  __int64 v74; // r14
  __int64 v75; // rax
  __int64 v76; // r14
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // r14
  __int64 v80; // rcx
  __int64 v81; // r14
  __int64 v82; // rcx
  __int64 v83; // r14
  __int64 v84; // rcx
  __int64 v85; // rcx
  int v86; // eax
  int v87; // eax
  unsigned int v88; // r9d
  unsigned int v89; // r9d
  int MultiValSetFixed; // eax
  _DWORD *v91; // r14
  int EulaState; // eax
  int v93; // eax
  int v94; // eax
  int v95; // eax
  int v96; // eax
  int v97; // eax
  int v98; // eax
  int v99; // eax
  int v100; // eax
  int v101; // r10d
  __int64 v102; // r9
  unsigned int v103; // r8d
  unsigned int v104; // ecx
  __int64 v105; // rdx
  __int64 v106; // r11
  const wchar_t *v107; // rcx
  char v108; // al
  int v109; // r14d
  int v110; // r12d
  int v111; // r15d
  unsigned __int64 v112; // rdi
  unsigned int v113; // r13d
  unsigned int v114; // edi
  _DWORD *v115; // rdx
  __int64 v116; // r12
  const WCHAR *v117; // r8
  const WCHAR *v118; // rcx
  int v119; // eax
  __int64 v120; // r12
  int v121; // ecx
  __int64 v122; // r8
  int v123; // eax
  struct tagDSEulaFile_V2 *v124; // rdx
  wchar_t **v125; // rcx
  int Lang; // eax
  void *v127; // rcx
  void *v128; // rcx
  __int64 v129; // rdx
  __int64 v130; // rdx
  LPVOID *p_pvData; // r14
  __int64 v132; // r15
  unsigned int *lpString2; // [rsp+20h] [rbp-E0h]
  unsigned int *lpString2a; // [rsp+20h] [rbp-E0h]
  unsigned int i; // [rsp+50h] [rbp-B0h]
  int v137; // [rsp+50h] [rbp-B0h]
  unsigned int v139; // [rsp+68h] [rbp-98h]
  char *v140; // [rsp+70h] [rbp-90h]
  _DWORD *pvData; // [rsp+78h] [rbp-88h]
  unsigned int v142[4]; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v143[4]; // [rsp+98h] [rbp-68h]
  int v144; // [rsp+A8h] [rbp-58h]
  __int64 v145; // [rsp+B0h] [rbp-50h]
  __int64 v146; // [rsp+B8h] [rbp-48h]
  LPCWCH v147; // [rsp+C0h] [rbp-40h]
  int v148; // [rsp+C8h] [rbp-38h] BYREF
  int v149; // [rsp+CCh] [rbp-34h] BYREF
  __int128 v150; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v151; // [rsp+E0h] [rbp-20h]
  _OWORD v152[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v153; // [rsp+108h] [rbp+8h]
  _OWORD v154[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v155; // [rsp+130h] [rbp+30h]

  v17 = 0;
  v145 = a3;
  v146 = a2;
  v144 = a1;
  v147 = a15;
  v149 = 0;
  v148 = 0;
  memset(a16, 0, 0x280u);
  v18 = tableid;
  FileFromRow = DsqSeekToUpdateI(a3, tableid, a13, 0, 0);
  if ( FileFromRow < 0 )
    goto LABEL_256;
  v20 = (struct JET_RETRIEVECOLUMN *)SafeSusAllocArray(0x1Eu, 0x30u);
  v17 = v20;
  if ( !v20 )
  {
    FileFromRow = -2147024882;
    goto LABEL_256;
  }
  v20->columnid = dword_180338414;
  v20->pvData = (char *)a16 + 24;
  v20->cbData = 4;
  v20->itagSequence = 1;
  v21 = 7;
  v20[1].columnid = dword_180338410;
  v20[1].pvData = (char *)a16 + 36;
  v20[1].cbData = 4;
  v20[1].itagSequence = 1;
  v20[2].columnid = dword_1803384C8;
  v20[2].pvData = &v149;
  v20[2].cbData = 4;
  v20[2].itagSequence = 1;
  v20[3].columnid = dword_180338464;
  v20[3].pvData = &v148;
  v20[3].cbData = 4;
  v20[3].itagSequence = 1;
  v20[4].columnid = dword_1803384A0;
  v20[4].pvData = (char *)a16 + 44;
  v20[4].cbData = 4;
  v20[4].itagSequence = 1;
  v20[5].columnid = dword_1803384CC;
  v20[5].pvData = (char *)a16 + 40;
  v20[5].cbData = 4;
  v20[5].itagSequence = 1;
  v20[6].columnid = dword_1803384F8;
  v20[6].pvData = (char *)a16 + 48;
  v20[6].cbData = 4;
  v20[6].itagSequence = 1;
  if ( *(_DWORD *)a13 == 1 || *(_DWORD *)a13 == 2 )
  {
    v21 = 9;
    v20[7].columnid = dword_180338404;
    v20[7].cbData = 16;
    v20[7].pvData = (char *)a16 + 4;
    v20[7].itagSequence = 1;
    v20[8].columnid = dword_180338408;
    v20[8].pvData = (char *)a16 + 20;
    v20[8].cbData = 4;
    v20[8].itagSequence = 1;
  }
  else
  {
    v22 = *(_OWORD *)(a13 + 4);
    if ( *(_DWORD *)a13 == 3 )
    {
      *(_OWORD *)((char *)a16 + 4) = v22;
      v21 = 8;
      v20[7].columnid = dword_180338408;
      v20[7].pvData = (char *)a16 + 20;
      v20[7].cbData = 4;
      v20[7].itagSequence = 1;
    }
    else
    {
      *(_OWORD *)((char *)a16 + 4) = v22;
      *((_DWORD *)a16 + 5) = *(_DWORD *)(a13 + 20);
    }
  }
  if ( *(_DWORD *)a13 == 2 )
  {
    *(_DWORD *)a16 = *(_DWORD *)(a13 + 4);
  }
  else
  {
    v23 = v21++;
    v20[v23].columnid = g_rgClientStoreColumnIds;
    v20[v23].pvData = a16;
    v20[v23].cbData = 4;
    v20[v23].itagSequence = 1;
  }
  *(_OWORD *)v142 = 0;
  *(_OWORD *)v143 = 0;
  if ( (a10 & 8) != 0 )
  {
    v24 = v21;
    v20[v24].columnid = dword_180338444;
    v142[0] = v21++;
    v20[v24].pvData = 0;
    v20[v24].cbData = 0;
    v20[v24].itagSequence = 0;
  }
  if ( (a10 & 0x400) != 0 )
  {
    v25 = v21;
    v20[v25].columnid = dword_1803384C0;
    v26 = v21;
    v17[v25].pvData = 0;
    v27 = v21 + 1;
    v17[v25].cbData = 0;
    v17[v25].itagSequence = 0;
    v28 = v27;
    v143[2] = v26;
    v29 = v27;
    v21 = v27 + 1;
    v143[3] = v28;
    v17[v29].columnid = dword_1803384C4;
    v17[v29].pvData = 0;
    v17[v29].cbData = 0;
    v17[v29].itagSequence = 0;
  }
  if ( (a10 & 0x800) != 0 )
  {
    v30 = v21;
    v17[v30].columnid = dword_180338498;
    v31 = v21;
    v17[v30].pvData = 0;
    v32 = v21 + 1;
    v17[v30].cbData = 0;
    v17[v30].itagSequence = 0;
    v33 = v32;
    v142[1] = v31;
    v34 = v32;
    v35 = (unsigned int)(v32 + 1);
    v142[3] = v33;
    v143[0] = v35;
    v17[v34].columnid = dword_1803384B4;
    v17[v34].pvData = 0;
    v17[v34].cbData = 0;
    v17[v34].itagSequence = 0;
    v36 = v35;
    v37 = (unsigned int)(v35 + 1);
    v143[1] = v37;
    v17[v36].columnid = dword_1803384B8;
    v17[v36].pvData = 0;
    v17[v36].cbData = 0;
    v17[v36].itagSequence = 0;
    v38 = v37;
    v21 = v37 + 1;
    v17[v38].columnid = dword_1803384BC;
    v17[v38].pvData = 0;
    v17[v38].cbData = 0;
    v17[v38].itagSequence = 0;
  }
  if ( (a10 & 2) != 0 )
  {
    v39 = v21;
    v17[v39].columnid = dword_180338450;
    v142[2] = v21++;
    v17[v39].pvData = 0;
    v17[v39].cbData = 0;
    v17[v39].itagSequence = 0;
  }
  v40 = a4;
  Data = DsqGetData(a4, tableid, v17, v21);
  FileFromRow = Data;
  if ( Data != -2145091577 )
  {
    if ( Data < 0 )
      goto LABEL_256;
LABEL_30:
    v45 = *((_DWORD *)a16 + 6);
    v46 = v142;
    v47 = 8;
    *((_DWORD *)a16 + 7) = v45 & (a10 | 1);
    do
    {
      if ( !*v46 || (v48 = *v46, v17[v48].err) )
        itagSequence = 0;
      else
        itagSequence = v17[v48].itagSequence;
      *v46++ = itagSequence;
      --v47;
    }
    while ( v47 );
    if ( v149
      || v148
      || (unsigned int)CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::GetIndexOf(
                         a14,
                         (char *)a16 + 4) >= *(_DWORD *)(a14 + 20) )
    {
      v50 = 0;
    }
    else
    {
      v50 = 2;
    }
    *((_DWORD *)a16 + 8) = v50;
    memset(v17, 0, 0x5A0u);
    if ( ((unsigned __int8)a10 & (unsigned __int8)v45 & 0x20) != 0
      || (*((_BYTE *)a16 + 24) & 0x20) != 0
      && (*a12 != *(_QWORD *)&c_idSrvNone.Data1 || a12[1] != *(_QWORD *)c_idSrvNone.Data4) )
    {
      v17->columnid = dword_180338448;
      v17->itagSequence = 1;
      VarColumns = DsqRetrieveVarColumns(a4, tableid, v17, 1);
      FileFromRow = VarColumns;
      if ( VarColumns < 0 )
      {
        if ( VarColumns != -2145091577 )
          goto LABEL_256;
        FileFromRow = 0;
      }
      v52 = v17->cbActual >> 2;
      pvData = v17->pvData;
      if ( v52 )
      {
        v155 = 0;
        v150 = 0;
        v153 = 0;
        memset(v154, 0, sizeof(v154));
        memset(v152, 0, sizeof(v152));
        v53 = (struct tagDSFile *)SafeSusComAllocArray(v52, 0xF8u);
        v54 = v53;
        if ( !v53 )
        {
          FileFromRow = -2147024882;
          goto LABEL_252;
        }
        v55 = pvData;
        v140 = (char *)v53 + 40;
        for ( i = 0; i < v52; ++i )
        {
          LODWORD(v150) = *v55;
          FileFromRow = DsqSeekToFileI(a4, a7, (const struct tagDsqFileId *)&v150);
          if ( FileFromRow >= 0 )
            FileFromRow = GetFileFromRow(a4, a7);
          if ( FileFromRow < 0 )
          {
            DsqFreeObject(v54, v52, 0);
            CoTaskMemFree(v54);
            if ( (unsigned int)(FileFromRow + 2145091552) <= 9 || FileFromRow == -2145091577 )
              FileFromRow = -2145091575;
            goto LABEL_252;
          }
          v56 = *(_QWORD *)&c_idSrvNone.Data1;
          v57 = *(_QWORD *)c_idSrvNone.Data4;
          if ( *a12 == *(_QWORD *)&c_idSrvNone.Data1 && a12[1] == *(_QWORD *)c_idSrvNone.Data4 )
          {
            v58 = v140;
          }
          else
          {
            v58 = v140;
            if ( *((_DWORD *)v140 + 18) <= 9u )
            {
              v59 = v154;
              if ( *(_QWORD *)v140 )
                v59 = v152;
              *((_DWORD *)v59 + *((int *)v140 + 18)) = 1;
              v57 = *(_QWORD *)c_idSrvNone.Data4;
              v56 = *(_QWORD *)&c_idSrvNone.Data1;
            }
          }
          v55 = ++pvData;
          v140 = v58 + 248;
        }
        if ( *a12 != v56 || a12[1] != v57 )
        {
          v60 = 0;
          while ( !*((_DWORD *)v152 + v60) || *((_DWORD *)v154 + v60) )
          {
            v60 = (unsigned int)(v60 + 1);
            if ( (unsigned int)v60 >= 0xA )
              goto LABEL_71;
          }
          *((_DWORD *)a16 + 6) |= 0x1000u;
        }
LABEL_71:
        if ( ((unsigned __int8)a10 & (unsigned __int8)v45 & 0x20) != 0 )
        {
          *((_QWORD *)a16 + 59) = v54;
          *((_DWORD *)a16 + 116) = v52;
        }
        else
        {
          DsqFreeObject(v54, v52, 0);
          CoTaskMemFree(v54);
        }
        v61 = v17->pvData;
        if ( v61 )
          CoTaskMemFree(v61);
        v40 = a4;
      }
      v18 = tableid;
      *(_OWORD *)&v17->columnid = 0;
      *(_OWORD *)&v17->cbData = 0;
      *(_OWORD *)&v17->itagSequence = 0;
    }
    if ( ((unsigned __int8)a10 & (unsigned __int8)v45 & 8) != 0 )
    {
      v17->columnid = dword_180338438;
      v17->itagSequence = 1;
      v62 = dword_18033843C;
      v17[1].pvData = 0;
      v17[1].cbData = 0;
      v17[1].columnid = v62;
      v17[1].itagSequence = 1;
      v63 = dword_180338440;
      v17[2].pvData = 0;
      v17[2].cbData = 0;
      v17[2].columnid = v63;
      v17[2].itagSequence = 1;
      v64 = DsqRetrieveVarColumns(v40, v18, v17, 3);
      FileFromRow = 0;
      if ( v64 != -2145091577 )
        FileFromRow = v64;
      if ( FileFromRow < 0 )
        goto LABEL_252;
      if ( v142[0] )
      {
        LODWORD(v150) = 17;
        LODWORD(v151) = v142[0];
        *((_QWORD *)&v150 + 1) = 0;
        MultiValSetVar = DsqGetMultiValSetVar(v40, v18, (struct tagDsqMultiValRetrieveVar *)&v150, v65);
        FileFromRow = MultiValSetVar;
        if ( MultiValSetVar < 0 )
          goto LABEL_84;
        *((_QWORD *)a16 + 77) = *((_QWORD *)&v150 + 1);
        *((_DWORD *)a16 + 152) = v151;
      }
      *((_QWORD *)a16 + 73) = v17->pvData;
      *((_DWORD *)a16 + 144) = v17->cbData;
      *((_QWORD *)a16 + 75) = v17[1].pvData;
      *((_DWORD *)a16 + 148) = v17[1].cbData;
      *((_QWORD *)a16 + 71) = v17[2].pvData;
      *((_DWORD *)a16 + 140) = v17[2].cbData;
      memset(v17, 0, 0x90u);
    }
    if ( ((unsigned __int8)a10 & (unsigned __int8)v45 & 4) != 0 )
    {
      v17->columnid = dword_180338468;
      v17->itagSequence = 1;
      v67 = DsqRetrieveVarColumns(v40, v18, v17, 1);
      FileFromRow = 0;
      if ( v67 != -2145091577 )
        FileFromRow = v67;
      if ( FileFromRow < 0 )
        goto LABEL_252;
      *((_QWORD *)a16 + 69) = v17->pvData;
      *((_DWORD *)a16 + 136) = v17->cbData;
      *(_OWORD *)&v17->columnid = 0;
      *(_OWORD *)&v17->cbData = 0;
      *(_OWORD *)&v17->itagSequence = 0;
    }
    if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x2000) != 0 )
    {
      v17->columnid = dword_18033846C;
      v17->itagSequence = 1;
      v68 = DsqRetrieveVarColumns(v40, v18, v17, 1);
      FileFromRow = 0;
      if ( v68 != -2145091577 )
        FileFromRow = v68;
      if ( FileFromRow < 0 )
        goto LABEL_256;
      *((_QWORD *)a16 + 79) = v17->pvData;
      *((_DWORD *)a16 + 156) = v17->cbData;
      *(_OWORD *)&v17->columnid = 0;
      *(_OWORD *)&v17->cbData = 0;
      *(_OWORD *)&v17->itagSequence = 0;
    }
    if ( ((unsigned __int8)a10 & (unsigned __int8)v45 & 2) != 0 )
    {
      v17->columnid = dword_180338454;
      v17->itagSequence = 1;
      v17[1].columnid = dword_180338458;
      v17[1].pvData = 0;
      v17[1].cbData = 0;
      v17[1].itagSequence = 1;
      v17[2].columnid = dword_18033845C;
      v17[2].pvData = 0;
      v17[2].cbData = 0;
      v17[2].itagSequence = 1;
      LODWORD(lpString2) = 0;
      v69 = DsqRetrieveVarColumns(v40, v18, v17, 3);
      FileFromRow = v69;
      if ( v69 == -2145091577 )
      {
        FileFromRow = 0;
      }
      else if ( v69 < 0 )
      {
        goto LABEL_252;
      }
      if ( v142[2] )
      {
        LODWORD(v150) = 20;
        *(_QWORD *)((char *)&v150 + 4) = v142[2] | 0x1000000000LL;
        v151 = 0;
        MultiValSetVar = DsqGetMultiValSetFixed(v40, v18, (struct tagDsqMultiValRetrieveFixed *)&v150, v70, lpString2);
        FileFromRow = MultiValSetVar;
        if ( MultiValSetVar < 0 )
        {
LABEL_84:
          if ( MultiValSetVar == -2145091577 )
            FileFromRow = -2145091576;
          goto LABEL_252;
        }
        *((_QWORD *)a16 + 61) = v151;
        *((_DWORD *)a16 + 120) = DWORD1(v150);
      }
      *((_QWORD *)a16 + 67) = v17->pvData;
      *((_DWORD *)a16 + 132) = v17->cbActual / 0x14;
      *((_QWORD *)a16 + 63) = v17[1].pvData;
      *((_DWORD *)a16 + 124) = v17[1].cbActual / 0x18;
      *((_QWORD *)a16 + 65) = v17[2].pvData;
      v71 = v17[2].cbActual * (unsigned __int128)0x2492492492492493uLL;
      *((_DWORD *)a16 + 128) = (*((_QWORD *)&v71 + 1)
                              + (((unsigned __int64)v17[2].cbActual - *((_QWORD *)&v71 + 1)) >> 1)) >> 4;
      memset(v17, 0, 0x90u);
    }
    if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x480) != 0 )
    {
      v17->columnid = dword_180338490;
      v17->cbData = 16;
      v17->pvData = (char *)a16 + 416;
      v17->itagSequence = 1;
      v72 = DsqGetData(v40, v18, v17, 1u);
      FileFromRow = v72;
      if ( v72 < 0 )
      {
        if ( v72 != -2145091577 )
          goto LABEL_256;
        FileFromRow = 0;
      }
      *(_OWORD *)&v17->columnid = 0;
      *(_OWORD *)&v17->cbData = 0;
      *(_OWORD *)&v17->itagSequence = 0;
    }
    v137 = 0;
    if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x980) == 0 )
    {
LABEL_121:
      if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0xE00) != 0 )
      {
        LODWORD(v74) = 0;
        v139 = -1;
        if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x800) != 0 )
        {
          v17->columnid = dword_1803384AC;
          v17->pvData = (char *)a16 + 184;
          v17->cbData = 4;
          v17->itagSequence = 1;
          v17[1].columnid = dword_18033848C;
          v17[1].pvData = (char *)a16 + 200;
          v17[1].cbData = 4;
          v17[1].itagSequence = 1;
          v17[2].columnid = dword_180338494;
          v17[2].pvData = (char *)a16 + 204;
          v17[2].cbData = 4;
          v17[2].itagSequence = 1;
          v17[3].columnid = dword_180338484;
          v17[3].pvData = (char *)a16 + 176;
          v17[3].cbData = 4;
          v17[3].itagSequence = 1;
          v17[4].columnid = dword_180338430;
          v17[4].pvData = (char *)a16 + 124;
          v17[4].cbData = 12;
          v17[4].itagSequence = 1;
          v17[5].columnid = dword_180338434;
          v17[5].pvData = (char *)a16 + 136;
          v17[5].cbData = 12;
          v17[5].itagSequence = 1;
          v17[6].columnid = dword_180338428;
          v17[6].pvData = (char *)a16 + 120;
          v17[6].cbData = 4;
          v17[6].itagSequence = 1;
          v17[7].columnid = dword_180338460;
          v17[7].pvData = (char *)a16 + 192;
          v17[7].cbData = 4;
          v17[7].itagSequence = 1;
          v17[8].columnid = dword_180338474;
          v17[8].pvData = (char *)a16 + 160;
          v17[8].cbData = 8;
          v17[8].itagSequence = 1;
          v17[9].columnid = dword_180338478;
          v17[9].pvData = (char *)a16 + 152;
          v17[9].cbData = 8;
          v17[9].itagSequence = 1;
          v17[10].columnid = dword_18033847C;
          v17[10].pvData = (char *)a16 + 168;
          v17[10].cbData = 4;
          v17[10].itagSequence = 1;
          v17[11].columnid = dword_180338480;
          v17[11].pvData = (char *)a16 + 172;
          v17[11].cbData = 4;
          v17[11].itagSequence = 1;
          v17[12].columnid = dword_180338488;
          v17[12].pvData = (char *)a16 + 180;
          v17[12].cbData = 4;
          v17[12].itagSequence = 1;
          v17[13].columnid = dword_1803384E4;
          v17[13].pvData = (char *)a16 + 344;
          LODWORD(v74) = 16;
          v17[13].cbData = 8;
          v17[13].itagSequence = 1;
          v17[14].columnid = dword_1803384EC;
          v17[14].pvData = (char *)a16 + 360;
          v17[14].cbData = 8;
          v17[14].itagSequence = 1;
          v17[15].columnid = dword_1803384F0;
          v17[15].pvData = (char *)a16 + 368;
          v17[15].cbData = 4;
          v17[15].itagSequence = 1;
          *((_DWORD *)a16 + 49) = v148;
        }
        else if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x200) != 0 )
        {
          LODWORD(v74) = 1;
          v17->columnid = dword_180338428;
          v17->pvData = (char *)a16 + 120;
          v17->cbData = 4;
          v17->itagSequence = 1;
        }
        if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x400) != 0 )
        {
          v75 = (unsigned int)v74;
          v139 = v74;
          v76 = (unsigned int)(v74 + 1);
          v77 = v75;
          v17[v77].columnid = dword_180338418;
          v17[v77].pvData = (char *)a16 + 80;
          v17[v77].cbData = 4;
          v17[v77].itagSequence = 1;
          v78 = v76;
          v79 = (unsigned int)(v76 + 1);
          v17[v78].columnid = dword_180338420;
          v17[v78].pvData = (char *)a16 + 88;
          v17[v78].cbData = 4;
          v17[v78].itagSequence = 1;
          v80 = v79;
          v81 = (unsigned int)(v79 + 1);
          v17[v80].columnid = dword_18033842C;
          v17[v80].pvData = (char *)a16 + 84;
          v17[v80].cbData = 4;
          v17[v80].itagSequence = 1;
          v82 = v81;
          v83 = (unsigned int)(v81 + 1);
          v17[v82].columnid = dword_1803384D0;
          v17[v82].pvData = (char *)a16 + 312;
          v17[v82].cbData = 8;
          v17[v82].itagSequence = 1;
          v84 = v83;
          v74 = (unsigned int)(v83 + 1);
          v17[v84].columnid = dword_1803384B0;
          v17[v84].pvData = (char *)a16 + 188;
          v17[v84].cbData = 4;
          v17[v84].itagSequence = 1;
          if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x800) == 0 )
          {
            v85 = v74;
            LODWORD(v74) = v74 + 1;
            v17[v85].columnid = dword_1803384AC;
            v17[v85].pvData = (char *)a16 + 184;
            v17[v85].cbData = 4;
            v17[v85].itagSequence = 1;
          }
        }
        if ( (_DWORD)v74 )
        {
          v86 = DsqGetData(a4, v18, v17, v74);
          FileFromRow = v86;
          if ( v86 == -2145091577 )
          {
            if ( v139 != -1 && v17[v139].err == 1004 )
              goto LABEL_133;
            FileFromRow = 0;
          }
          else if ( v86 < 0 )
          {
            goto LABEL_251;
          }
          memset(v17, 0, 48LL * (unsigned int)v74);
        }
        if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x400) != 0 )
        {
          v17->columnid = dword_1803384F4;
          v17->pvData = 0;
          v17->cbData = 0;
          v17->itagSequence = 1;
          v87 = DsqRetrieveVarColumns(a4, v18, v17, 1);
          FileFromRow = 0;
          if ( v87 != -2145091577 )
            FileFromRow = v87;
          if ( FileFromRow < 0 )
            goto LABEL_251;
          v88 = v143[2];
          *((_QWORD *)a16 + 12) = v17->pvData;
          *(_OWORD *)&v17->columnid = 0;
          *(_OWORD *)&v17->cbData = 0;
          *(_OWORD *)&v17->itagSequence = 0;
          FileFromRow = DSGetMVTextColumn(a4, v18, 48, v88, (wchar_t ***)a16 + 37, (unsigned int *)a16 + 72, 0, 0);
          if ( FileFromRow < 0 )
            goto LABEL_251;
          if ( v143[3] )
          {
            LODWORD(v150) = 49;
            *(_QWORD *)((char *)&v150 + 4) = v143[3] | 0xC00000000LL;
            v151 = 0;
            MultiValSetFixed = DsqGetMultiValSetFixed(
                                 a4,
                                 v18,
                                 (struct tagDsqMultiValRetrieveFixed *)&v150,
                                 v89,
                                 lpString2a);
            FileFromRow = MultiValSetFixed;
            if ( MultiValSetFixed < 0 )
            {
              if ( MultiValSetFixed == -2145091577 )
              {
LABEL_133:
                FileFromRow = -2145091576;
                goto LABEL_251;
              }
              goto LABEL_251;
            }
            *((_QWORD *)a16 + 14) = v151;
            *((_DWORD *)a16 + 26) = DWORD1(v150);
          }
        }
        if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x800) != 0 )
        {
          v91 = (_DWORD *)((char *)a16 + 148);
          if ( *((_DWORD *)a16 + 51) )
          {
            *v91 = 0;
          }
          else
          {
            EulaState = GetEulaState(
                          v145,
                          v144 & (unsigned int)-((*((_DWORD *)a16 + 46) & 0x20) != 0),
                          v146 & -(__int64)((*((_DWORD *)a16 + 46) & 0x20) != 0),
                          a4,
                          a6,
                          (char *)a16 + 416,
                          (char *)a16 + 148);
            FileFromRow = EulaState;
            if ( EulaState < 0 )
            {
              *v91 = 0;
              if ( EulaState != -2145091577 )
                goto LABEL_251;
            }
          }
          v93 = dword_18033849C;
          v17->itagSequence = 1;
          v17->columnid = v93;
          v17->pvData = 0;
          v17->cbData = 0;
          v94 = dword_180338424;
          v17[1].itagSequence = 1;
          v17[1].columnid = v94;
          v17[1].pvData = 0;
          v17[1].cbData = 0;
          v95 = dword_1803384D4;
          v17[2].itagSequence = 1;
          v17[2].columnid = v95;
          v17[2].pvData = 0;
          v17[2].cbData = 0;
          v96 = dword_1803384D8;
          v17[3].itagSequence = 1;
          v17[3].columnid = v96;
          v17[3].pvData = 0;
          v17[3].cbData = 0;
          v97 = dword_1803384DC;
          v17[4].itagSequence = 1;
          v17[4].columnid = v97;
          v17[4].pvData = 0;
          v17[4].cbData = 0;
          v98 = dword_1803384E0;
          v17[5].itagSequence = 1;
          v17[5].columnid = v98;
          v17[5].pvData = 0;
          v17[5].cbData = 0;
          v99 = dword_1803384E8;
          v17[6].itagSequence = 1;
          v137 = 1;
          v17[6].columnid = v99;
          v17[6].pvData = 0;
          v17[6].cbData = 0;
          v100 = DsqRetrieveVarColumns(a4, v18, v17, 7);
          FileFromRow = 0;
          if ( v100 != -2145091577 )
            FileFromRow = v100;
          if ( FileFromRow < 0 )
            goto LABEL_252;
          *((_QWORD *)a16 + 27) = v17->pvData;
          *((_QWORD *)a16 + 26) = v17[1].pvData;
          *((_QWORD *)a16 + 38) = v17[2].pvData;
          *((_QWORD *)a16 + 40) = v17[3].pvData;
          *((_QWORD *)a16 + 41) = v17[4].pvData;
          *((_QWORD *)a16 + 42) = v17[5].pvData;
          *((_QWORD *)a16 + 44) = v17[6].pvData;
          memset(v17, 0, 0x150u);
          FileFromRow = DSGetMVTextColumn(a4, v18, 38, v142[1], (wchar_t ***)a16 + 29, (unsigned int *)a16 + 56, 0, 0);
          if ( FileFromRow < 0 )
            goto LABEL_252;
          FileFromRow = DSGetMVTextColumn(a4, v18, 45, v142[3], (wchar_t ***)a16 + 31, (unsigned int *)a16 + 60, 0, 0);
          if ( FileFromRow < 0 )
            goto LABEL_252;
          FileFromRow = DSGetMVTextColumn(a4, v18, 46, v143[0], (wchar_t ***)a16 + 35, (unsigned int *)a16 + 68, 0, 0);
          if ( FileFromRow < 0 )
            goto LABEL_252;
          FileFromRow = DSGetMVTextColumn(a4, v18, 47, v143[1], (wchar_t ***)a16 + 33, (unsigned int *)a16 + 64, 0, 0);
          if ( FileFromRow < 0 )
            goto LABEL_252;
        }
        if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x200) != 0 )
        {
          v101 = *((_DWORD *)a16 + 30);
          if ( v101 != 7 && v101 != -1 )
          {
            v102 = *(_QWORD *)(v145 + 88);
            if ( !v102 )
            {
              FileFromRow = -2147483634;
              goto LABEL_251;
            }
            v103 = *(_DWORD *)(v102 + 732);
            v104 = 0;
            if ( !v103 )
              goto LABEL_168;
            v105 = 0;
            while ( 1 )
            {
              v106 = *(_QWORD *)(v105 + *(_QWORD *)(v102 + 720));
              if ( v101 == *(_DWORD *)(v106 + 8) )
                break;
              ++v104;
              v105 += 8;
              if ( v104 >= v103 )
                goto LABEL_168;
            }
            v107 = *(const wchar_t **)(v106 + 16);
            if ( !v107 )
            {
LABEL_168:
              FileFromRow = -2145091574;
              goto LABEL_251;
            }
            FileFromRow = DSStrDup(v107, (wchar_t **)a16 + 48);
            if ( FileFromRow < 0 )
            {
LABEL_251:
              if ( !v137 )
                goto LABEL_256;
              goto LABEL_252;
            }
          }
        }
      }
      if ( ((unsigned __int16)a10 & (unsigned __int16)v45 & 0x180) == 0 )
        goto LABEL_251;
      v108 = a10 & v45;
      v109 = ((unsigned __int8)a10 & (unsigned __int8)v45 & 0x80) != 0;
      v110 = (unsigned __int16)a10 & (unsigned __int16)v45 & 0x100;
      v111 = v110 != 0;
      if ( v108 < 0
        && *((_QWORD *)a16 + 52) == *(_QWORD *)&g_defGUID.Data1
        && *((_QWORD *)a16 + 53) == *(_QWORD *)g_defGUID.Data4 )
      {
        v109 = 0;
      }
      else if ( v109 )
      {
        goto LABEL_178;
      }
      if ( !v110 )
      {
LABEL_250:
        FileFromRow = 0;
        goto LABEL_251;
      }
LABEL_178:
      v112 = 1;
      v113 = a11[1];
      if ( *a11 )
        v112 = v113;
      if ( v110 )
        *((_QWORD *)a16 + 55) = SafeSusComAllocArray((unsigned int)v112, 0x78u);
      if ( v109 )
        *((_QWORD *)a16 + 57) = SafeSusComAllocArray(v112, 0x88u);
      if ( !*((_QWORD *)a16 + 55) && v110 || !*((_QWORD *)a16 + 57) && v109 )
      {
        FileFromRow = -2147024882;
        goto LABEL_251;
      }
      if ( *((_QWORD *)a16 + 49) )
      {
        v114 = 0;
        if ( v113 )
        {
          v115 = a11;
          v116 = 0;
          while ( 1 )
          {
            v117 = (const WCHAR *)*((_QWORD *)a16 + 49);
            v118 = *(const WCHAR **)(v116 + *((_QWORD *)v115 + 1));
            if ( v117 == v118 )
              break;
            if ( v117 )
            {
              if ( v118 )
              {
                v119 = CompareStringW(0x7Fu, 1u, v117, -1, v118, -1);
                v115 = a11;
                if ( v119 == 2 )
                  break;
              }
            }
            ++v114;
            v116 += 8;
            if ( v114 >= v113 )
              goto LABEL_197;
          }
        }
        else
        {
LABEL_197:
          v115 = a11;
          if ( v114 == v113 )
            ++v113;
        }
      }
      else
      {
        v115 = a11;
      }
      v120 = 0;
      *((_DWORD *)a16 + 108) = 0;
      for ( *((_DWORD *)a16 + 112) = 0; (unsigned int)v120 < v113; v120 = (unsigned int)(v120 + 1) )
      {
        v121 = v109;
        if ( (unsigned int)v120 >= v115[1] )
        {
          v122 = *((_QWORD *)a16 + 49);
          v123 = 0;
          if ( !*((_DWORD *)a16 + 108) )
            v123 = v111;
          v109 = 0;
          v111 = v123;
          if ( !*((_DWORD *)a16 + 112) )
            v109 = v121;
          if ( !v123 && !v109 )
            break;
        }
        else
        {
          v122 = *(_QWORD *)(*((_QWORD *)v115 + 1) + 8 * v120);
        }
        if ( v122 )
        {
          if ( v109 )
            v124 = (struct tagDSEulaFile_V2 *)(*((_QWORD *)a16 + 57) + 136LL * *((unsigned int *)a16 + 112));
          else
            v124 = 0;
          if ( v111 )
            v125 = (wchar_t **)(*((_QWORD *)a16 + 55) + 120LL * *((unsigned int *)a16 + 108));
          else
            v125 = 0;
          Lang = GetLang(a4, *(_DWORD *)a16, v122, (__int64)a12, v147, v125, v124);
          FileFromRow = Lang;
          if ( Lang >= 0 )
          {
            if ( v111 )
            {
              v129 = *((unsigned int *)a16 + 108);
              if ( *(_QWORD *)(120 * v129 + *((_QWORD *)a16 + 55)) )
                *((_DWORD *)a16 + 108) = v129 + 1;
            }
            if ( v109 )
            {
              v130 = *((unsigned int *)a16 + 112);
              if ( *(_DWORD *)(136 * v130 + *((_QWORD *)a16 + 57)) != -1 )
                *((_DWORD *)a16 + 112) = v130 + 1;
            }
            v115 = a11;
            if ( v111 && *((_DWORD *)a16 + 108) )
              v111 = *a11;
            if ( v109 && *((_DWORD *)a16 + 112) )
              v109 = *a11;
            if ( !v111 && !v109 )
              break;
          }
          else
          {
            if ( (unsigned int)(Lang + 2145091552) > 9 && Lang != -2145091577 )
              goto LABEL_251;
            v115 = a11;
          }
        }
      }
      if ( !*((_DWORD *)a16 + 108) )
      {
        v127 = (void *)*((_QWORD *)a16 + 55);
        if ( v127 )
          CoTaskMemFree(v127);
        *((_QWORD *)a16 + 55) = 0;
      }
      if ( !*((_DWORD *)a16 + 112) )
      {
        v128 = (void *)*((_QWORD *)a16 + 57);
        if ( v128 )
          CoTaskMemFree(v128);
        *((_QWORD *)a16 + 57) = 0;
      }
      if ( !*((_DWORD *)a16 + 108) && v111 )
      {
        FileFromRow = -2145091576;
        DSAttemptRecovery(-2145091576);
        goto LABEL_251;
      }
      if ( !*((_DWORD *)a16 + 112) && v109 )
      {
        FileFromRow = -2145091550;
        goto LABEL_251;
      }
      goto LABEL_250;
    }
    v17->columnid = dword_18033841C;
    v17->itagSequence = 1;
    v17[1].columnid = dword_18033844C;
    v17[1].pvData = 0;
    v17[1].cbData = 0;
    v17[1].itagSequence = 1;
    v137 = 1;
    FileFromRow = DsqRetrieveVarColumns(v40, v18, v17, 2);
    if ( (int)(FileFromRow + 0x80000000) < 0 || FileFromRow == -2145091577 )
    {
      FileFromRow = DSTokenizeString(
                      (wchar_t ***const)a16 + 51,
                      (unsigned int *)a16 + 100,
                      0x7Cu,
                      (const wchar_t *)v17[1].pvData);
      if ( FileFromRow >= 0 )
      {
        *((_QWORD *)a16 + 49) = v17->pvData;
        v73 = v17[1].pvData;
        if ( v73 )
          CoTaskMemFree(v73);
        memset(v17, 0, 0x60u);
        goto LABEL_121;
      }
    }
LABEL_252:
    p_pvData = &v17->pvData;
    v132 = 30;
    do
    {
      if ( *p_pvData )
        CoTaskMemFree(*p_pvData);
      p_pvData += 6;
      --v132;
    }
    while ( v132 );
    goto LABEL_256;
  }
  v42 = 0;
  p_err = &v17->err;
  while ( !*p_err )
  {
    v42 = (unsigned int)(v42 + 1);
    p_err += 12;
    if ( (unsigned int)v42 >= 7 )
    {
      FileFromRow = 0;
      goto LABEL_30;
    }
  }
  err = v17[v42].err;
  if ( err == 1004 )
    FileFromRow = -2145091576;
  else
    FileFromRow = JETErrToHRESULTAndAttemptRecovery(err);
LABEL_256:
  SusFree(v17);
  if ( FileFromRow < 0 )
    DsqFreeObject(a16, 1u, 12207, 1);
  return (unsigned int)FileFromRow;
}

```

## disassembly

```asm
0x1801980d4  push    rbp
0x1801980d6  push    rbx
0x1801980d7  push    rsi
0x1801980d8  push    rdi
0x1801980d9  push    r12
0x1801980db  push    r13
0x1801980dd  push    r14
0x1801980df  push    r15
0x1801980e1  lea     rbp, [rsp-48h]
0x1801980e6  sub     rsp, 148h
0x1801980ed  mov     rax, cs:__security_cookie
0x1801980f4  xor     rax, rsp
0x1801980f7  mov     [rbp+80h+var_48], rax
0x1801980fb  mov     rax, [rbp+80h+arg_50]
0x180198102  xor     r13d, r13d
0x180198105  mov     rsi, [rbp+80h+arg_78]
0x18019810c  mov     rdi, r8
0x18019810f  mov     r15d, [rbp+80h+arg_48]
0x180198116  mov     ebx, r13d
0x180198119  mov     r14, [rbp+80h+arg_60]
0x180198120  mov     [rsp+180h+var_128], rax
0x180198125  mov     rax, [rbp+80h+arg_58]
0x18019812c  mov     [rbp+80h+var_100], rax
0x180198130  mov     rax, [rbp+80h+arg_68]
0x180198137  mov     [rsp+180h+var_110], rax
0x18019813c  mov     rax, [rbp+80h+arg_70]
0x180198143  mov     [rbp+80h+var_D0], r8
0x180198147  mov     r8d, 280h; Size
0x18019814d  mov     [rbp+80h+var_C8], rdx
0x180198151  xor     edx, edx; Val
0x180198153  mov     [rbp+80h+var_D8], ecx
0x180198156  mov     rcx, rsi; void *
0x180198159  mov     [rbp+80h+var_C0], rax
0x18019815d  mov     [rsp+180h+sesid], r9
0x180198162  mov     [rbp+80h+var_B4], r13d
0x180198166  mov     [rbp+80h+var_B8], r13d
0x18019816a  call    memset
0x18019816f  mov     [rsp+180h+lpString2], r13
0x180198174  xor     r9d, r9d
0x180198177  mov     r13, [rbp+80h+tableid]
0x18019817e  mov     r8, r14
0x180198181  mov     rdx, r13
0x180198184  mov     rcx, rdi
0x180198187  call    ?DsqSeekToUpdateI@@YAJPEAVCSusEseSession@@_KAEBUtagDsqUpdateId@@W4SeekToUpdateFlags@@PEB_W@Z; DsqSeekToUpdateI(CSusEseSession *,unsigned __int64,tagDsqUpdateId const &,SeekToUpdateFlags,wchar_t const *)
0x18019818c  mov     edi, eax
0x18019818e  test    eax, eax
0x180198190  js      loc_180199A07
0x180198196  lea     edx, [rbx+30h]; unsigned __int64
0x180198199  lea     ecx, [rbx+1Eh]; unsigned __int64
0x18019819c  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1801981a1  xor     r10d, r10d
0x1801981a4  mov     rbx, rax
0x1801981a7  test    rax, rax
0x1801981aa  jnz     short loc_1801981B6
0x1801981ac  mov     edi, 8007000Eh
0x1801981b1  jmp     loc_180199A07
0x1801981b6  mov     eax, cs:dword_180338414
0x1801981bc  lea     r12, [rsi+18h]
0x1801981c0  mov     [rbx], eax
0x1801981c2  mov     edx, 4
0x1801981c7  mov     [rbx+8], r12
0x1801981cb  mov     [rbx+10h], edx
0x1801981ce  lea     r11d, [rdx-3]
0x1801981d2  mov     [rbx+20h], r11d
0x1801981d6  lea     r9d, [rdx+3]
0x1801981da  mov     eax, cs:dword_180338410
0x1801981e0  mov     [rbx+30h], eax
0x1801981e3  lea     rax, [rsi+24h]
0x1801981e7  mov     [rbx+38h], rax
0x1801981eb  mov     [rbx+40h], edx
0x1801981ee  mov     [rbx+50h], r11d
0x1801981f2  mov     eax, cs:dword_1803384C8
0x1801981f8  mov     [rbx+60h], eax
0x1801981fb  lea     rax, [rbp+80h+var_B4]
0x1801981ff  mov     [rbx+68h], rax
0x180198203  mov     [rbx+70h], edx
0x180198206  mov     [rbx+80h], r11d
0x18019820d  mov     eax, cs:dword_180338464
0x180198213  mov     [rbx+90h], eax
0x180198219  lea     rax, [rbp+80h+var_B8]
0x18019821d  mov     [rbx+98h], rax
0x180198224  mov     [rbx+0A0h], edx
0x18019822a  mov     [rbx+0B0h], r11d
0x180198231  mov     eax, cs:dword_1803384A0
0x180198237  mov     [rbx+0C0h], eax
0x18019823d  lea     rax, [rsi+2Ch]
0x180198241  mov     [rbx+0C8h], rax
0x180198248  mov     [rbx+0D0h], edx
0x18019824e  mov     [rbx+0E0h], r11d
0x180198255  mov     eax, cs:dword_1803384CC
0x18019825b  mov     [rbx+0F0h], eax
0x180198261  lea     rax, [rsi+28h]
0x180198265  mov     [rbx+0F8h], rax
0x18019826c  mov     [rbx+100h], edx
0x180198272  mov     [rbx+110h], r11d
0x180198279  mov     eax, cs:dword_1803384F8
0x18019827f  mov     [rbx+120h], eax
0x180198285  lea     rax, [rsi+30h]
0x180198289  mov     [rbx+128h], rax
0x180198290  mov     [rbx+130h], edx
0x180198296  mov     [rbx+140h], r11d
0x18019829d  cmp     [r14], r11d
0x1801982a0  jz      short loc_1801982F1
0x1801982a2  cmp     dword ptr [r14], 2
0x1801982a6  jz      short loc_1801982F1
0x1801982a8  cmp     dword ptr [r14], 3
0x1801982ac  mov     ecx, edx
0x1801982ae  movups  xmm0, xmmword ptr [r14+4]
0x1801982b3  jnz     short loc_1801982E4
0x1801982b5  movdqu  xmmword ptr [rsi+4], xmm0
0x1801982ba  mov     eax, cs:dword_180338408
0x1801982c0  lea     r9d, [rdx+4]
0x1801982c4  mov     [rbx+150h], eax
0x1801982ca  lea     rax, [rsi+14h]
0x1801982ce  mov     [rbx+158h], rax
0x1801982d5  mov     [rbx+160h], edx
0x1801982db  mov     [rbx+170h], r11d
0x1801982e2  jmp     short loc_180198346
0x1801982e4  movups  xmmword ptr [rsi+4], xmm0
0x1801982e8  mov     eax, [r14+14h]
0x1801982ec  mov     [rsi+14h], eax
0x1801982ef  jmp     short loc_180198346
0x1801982f1  mov     eax, cs:dword_180338404
0x1801982f7  mov     r9d, 9
0x1801982fd  mov     [rbx+150h], eax
0x180198303  mov     rcx, rdx
0x180198306  mov     dword ptr [rbx+160h], 10h
0x180198310  lea     rax, [rsi+4]
0x180198314  mov     [rbx+158h], rax
0x18019831b  mov     [rbx+170h], r11d
0x180198322  mov     eax, cs:dword_180338408
0x180198328  mov     [rbx+180h], eax
0x18019832e  lea     rax, [rsi+14h]
0x180198332  mov     [rbx+188h], rax
0x180198339  mov     [rbx+190h], edx
0x18019833f  mov     [rbx+1A0h], r11d
0x180198346  cmp     dword ptr [r14], 2
0x18019834a  mov     rax, r14
0x18019834d  jz      short loc_180198375
0x18019834f  mov     eax, r9d
0x180198352  lea     rcx, [rax+rax*2]
0x180198356  mov     eax, cs:?g_rgClientStoreColumnIds@@3PAKA; ulong near * g_rgClientStoreColumnIds
0x18019835c  add     rcx, rcx
0x18019835f  add     r9d, r11d
0x180198362  mov     [rbx+rcx*8], eax
0x180198365  mov     [rbx+rcx*8+8], rsi
0x18019836a  mov     [rbx+rcx*8+10h], edx
0x18019836e  mov     [rbx+rcx*8+20h], r11d
0x180198373  jmp     short loc_18019837A
0x180198375  mov     eax, [rcx+rax]
0x180198378  mov     [rsi], eax
0x18019837a  xorps   xmm0, xmm0
0x18019837d  movups  xmmword ptr [rbp+80h+var_F8], xmm0
0x180198381  movups  xmmword ptr [rbp+80h+var_E8], xmm0
0x180198385  test    r15b, 8
0x180198389  jz      short loc_1801983B6
0x18019838b  mov     eax, r9d
0x18019838e  lea     rcx, [rax+rax*2]
0x180198392  mov     eax, cs:dword_180338444
0x180198398  add     rcx, rcx
0x18019839b  mov     [rbx+rcx*8], eax
0x18019839e  mov     eax, r9d
0x1801983a1  mov     [rbp+80h+var_F8], eax
0x1801983a4  add     r9d, r11d
0x1801983a7  mov     [rbx+rcx*8+8], r10
0x1801983ac  mov     [rbx+rcx*8+10h], r10d
0x1801983b1  mov     [rbx+rcx*8+20h], r10d
0x1801983b6  bt      r15d, 0Ah
0x1801983bb  jnb     short loc_180198410
0x1801983bd  mov     eax, r9d
0x1801983c0  lea     rcx, [rax+rax*2]
0x1801983c4  mov     eax, cs:dword_1803384C0
0x1801983ca  add     rcx, rcx
0x1801983cd  mov     [rbx+rcx*8], eax
0x1801983d0  mov     eax, r9d
0x1801983d3  mov     [rbx+rcx*8+8], r10
0x1801983d8  add     r9d, r11d
0x1801983db  mov     [rbx+rcx*8+10h], r10d
0x1801983e0  mov     [rbx+rcx*8+20h], r10d
0x1801983e5  mov     edx, r9d
0x1801983e8  lea     rcx, [r9+r9*2]
0x1801983ec  mov     [rbp+80h+var_E8+8], eax
0x1801983ef  mov     eax, cs:dword_1803384C4
0x1801983f5  add     rcx, rcx
0x1801983f8  add     r9d, r11d
0x1801983fb  mov     [rbp+80h+var_E8+0Ch], edx
0x1801983fe  mov     [rbx+rcx*8], eax
0x180198401  mov     [rbx+rcx*8+8], r10
0x180198406  mov     [rbx+rcx*8+10h], r10d
0x18019840b  mov     [rbx+rcx*8+20h], r10d
0x180198410  bt      r15d, 0Bh
0x180198415  jnb     loc_1801984BF
0x18019841b  mov     eax, r9d
0x18019841e  lea     rcx, [rax+rax*2]
0x180198422  mov     eax, cs:dword_180338498
0x180198428  add     rcx, rcx
0x18019842b  mov     [rbx+rcx*8], eax
0x18019842e  mov     eax, r9d
0x180198431  mov     [rbx+rcx*8+8], r10
0x180198436  add     r9d, r11d
0x180198439  mov     [rbx+rcx*8+10h], r10d
0x18019843e  mov     [rbx+rcx*8+20h], r10d
0x180198443  mov     edx, r9d
0x180198446  lea     rcx, [r9+r9*2]
0x18019844a  mov     [rbp+80h+var_F8+4], eax
0x18019844d  mov     eax, cs:dword_1803384B4
0x180198453  add     rcx, rcx
0x180198456  add     r9d, r11d
0x180198459  mov     [rbp+80h+var_F8+0Ch], edx
0x18019845c  mov     r8d, r9d
0x18019845f  mov     [rbp+80h+var_E8], r8d
0x180198463  mov     [rbx+rcx*8], eax
0x180198466  mov     [rbx+rcx*8+8], r10
0x18019846b  mov     [rbx+rcx*8+10h], r10d
0x180198470  mov     [rbx+rcx*8+20h], r10d
0x180198475  lea     rcx, [r9+r9*2]
0x180198479  mov     eax, cs:dword_1803384B8
0x18019847f  add     rcx, rcx
0x180198482  add     r9d, r11d
0x180198485  mov     edx, r9d
0x180198488  mov     [rbp+80h+var_E8+4], edx
0x18019848b  mov     [rbx+rcx*8], eax
0x18019848e  mov     [rbx+rcx*8+8], r10
0x180198493  mov     [rbx+rcx*8+10h], r10d
0x180198498  mov     [rbx+rcx*8+20h], r10d
0x18019849d  lea     rcx, [r9+r9*2]
0x1801984a1  mov     eax, cs:dword_1803384BC
0x1801984a7  add     rcx, rcx
0x1801984aa  add     r9d, r11d
0x1801984ad  mov     [rbx+rcx*8], eax
0x1801984b0  mov     [rbx+rcx*8+8], r10
0x1801984b5  mov     [rbx+rcx*8+10h], r10d
0x1801984ba  mov     [rbx+rcx*8+20h], r10d
0x1801984bf  test    r15b, 2
0x1801984c3  jz      short loc_1801984F0
0x1801984c5  mov     eax, r9d
0x1801984c8  lea     rcx, [rax+rax*2]
0x1801984cc  mov     eax, cs:dword_180338450
0x1801984d2  add     rcx, rcx
0x1801984d5  mov     [rbx+rcx*8], eax
0x1801984d8  mov     eax, r9d
0x1801984db  mov     [rbp+80h+var_F8+8], eax
0x1801984de  add     r9d, r11d; unsigned int
0x1801984e1  mov     [rbx+rcx*8+8], r10
0x1801984e6  mov     [rbx+rcx*8+10h], r10d
0x1801984eb  mov     [rbx+rcx*8+20h], r10d
0x1801984f0  mov     r14, [rsp+180h+sesid]
0x1801984f5  mov     r8, rbx; struct JET_RETRIEVECOLUMN *
0x1801984f8  mov     rcx, r14; unsigned __int64
0x1801984fb  mov     rdx, r13; unsigned __int64
0x1801984fe  call    ?DsqGetData@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@K@Z; DsqGetData(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong)
0x180198503  mov     edi, eax
0x180198505  cmp     eax, 80248007h
0x18019850a  jnz     short loc_18019854F
0x18019850c  xor     eax, eax
0x18019850e  lea     rcx, [rbx+28h]
0x180198512  cmp     dword ptr [rcx], 0
0x180198515  jnz     short loc_180198526
0x180198517  inc     eax
0x180198519  add     rcx, 30h ; '0'
0x18019851d  cmp     eax, 7
0x180198520  jb      short loc_180198512
0x180198522  xor     edi, edi
0x180198524  jmp     short loc_180198557
0x180198526  lea     rcx, [rax+rax*2]
0x18019852a  add     rcx, rcx
0x18019852d  mov     ecx, [rbx+rcx*8+28h]; int
0x180198531  cmp     ecx, 3ECh
0x180198537  jnz     short loc_180198543
0x180198539  mov     edi, 80248008h
0x18019853e  jmp     loc_180199A07
0x180198543  call    ?JETErrToHRESULTAndAttemptRecovery@@YAJJ@Z; JETErrToHRESULTAndAttemptRecovery(long)
0x180198548  mov     edi, eax
0x18019854a  jmp     loc_180199A07
0x18019854f  test    eax, eax
0x180198551  js      loc_180199A07
0x180198557  mov     r12d, [r12]
0x18019855b  lea     rdx, [rbp+80h+var_F8]
0x18019855f  mov     eax, r15d
0x180198562  mov     r8d, 8
0x180198568  or      eax, 1
0x18019856b  and     eax, r12d
0x18019856e  mov     [rsi+1Ch], eax
0x180198571  cmp     dword ptr [rdx], 0
0x180198574  jz      short loc_18019858C
0x180198576  mov     eax, [rdx]
0x180198578  lea     rcx, [rax+rax*2]
0x18019857c  add     rcx, rcx
0x18019857f  cmp     dword ptr [rbx+rcx*8+28h], 0
0x180198584  jnz     short loc_18019858C
0x180198586  mov     eax, [rbx+rcx*8+20h]
0x18019858a  jmp     short loc_18019858E
0x18019858c  xor     eax, eax
0x18019858e  mov     [rdx], eax
0x180198590  add     rdx, 4
0x180198594  sub     r8, 1
0x180198598  jnz     short loc_180198571
0x18019859a  cmp     [rbp+80h+var_B4], r8d
0x18019859e  jnz     short loc_1801985C5
0x1801985a0  cmp     [rbp+80h+var_B8], r8d
  ... truncated ...
```
