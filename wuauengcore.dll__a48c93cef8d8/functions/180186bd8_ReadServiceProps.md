# ReadServiceProps

- ea: `0x180186bd8`
- end: `0x180187722`
- name: `ReadServiceProps`
- size: `2890`
- prototype: `__int64 __usercall@<rax>(unsigned __int64@<rcx>, JET_TABLEID tableid@<rdx>, unsigned int, struct tagDSServicePropsAll *, void *)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18018a58c`
- `0x18018abc0`
- `0x18018baf0`

## callees

- `0x18010ec98`
- `0x180113c50`
- `0x18012b618`
- `0x1801342ec`
- `0x180182f58`
- `0x1801832c8`
- `0x1801839f0`
- `0x180183d54`
- `0x180184050`
- `0x1801853f0`
- `0x180186bd8`
- `0x180238960`
- `0x180240d40`
- `0x180241100`
- `0x180241780`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801872fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180187578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018758f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801875ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801875b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801872fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180187578`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018758f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801875ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801875b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180186c74`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180186c74`
- `ESENT!JetMove` at `0x1801875f7`
- `ESENT!JetMove` at `0x1801875f7`

## string_xrefs

- `0x180187691`: `JetMove`
- `0x1801876a6`: `DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix`
- `0x1801872b5`: `Service has cert hash without cert hash algo or vice versa\n`
- `0x180187657`: `Service has mismatched count of languages & names\n`
- `0x18018761d`: `Service missing localized properites (name)\n`

## pseudocode

```c
__int64 __fastcall ReadServiceProps(
        JET_SESID a1,
        JET_TABLEID tableid,
        char a3,
        _DWORD *a4,
        unsigned int a5,
        struct tagDSServicePropsAll *a6,
        char *a7)
{
  unsigned __int64 v7; // r12
  unsigned __int64 v8; // r13
  int Data; // edi
  unsigned int v11; // ecx
  __int64 v12; // rdi
  __int64 v13; // rbx
  unsigned int v14; // r9d
  __int64 v15; // rax
  __int64 v16; // r9
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // r9
  JET_COLUMNID v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r9
  JET_COLUMNID v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // r9
  JET_COLUMNID v27; // eax
  __int64 v28; // rcx
  __int64 v29; // r9
  JET_COLUMNID v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  unsigned int itagSequence; // eax
  _QWORD *v35; // r14
  char v36; // cl
  int VarColumns; // eax
  unsigned int v38; // r9d
  int v39; // r12d
  void *v40; // rax
  unsigned int v41; // r15d
  __int64 v42; // rax
  unsigned __int64 v43; // r13
  void *v44; // rcx
  unsigned __int64 v45; // r15
  unsigned int v46; // r14d
  __int64 v47; // r14
  int v48; // eax
  void **p_pvData; // rbx
  void *v50; // rax
  unsigned int v51; // r12d
  _DWORD *v52; // r8
  int v53; // eax
  unsigned int v54; // r15d
  unsigned int v55; // r13d
  unsigned int v56; // r14d
  const WCHAR *v57; // rdx
  __int64 v58; // rdx
  LPVOID *v59; // rcx
  __int64 v60; // rdx
  _QWORD *v61; // rax
  _BYTE *v62; // r12
  LPVOID *v63; // r13
  __int64 v64; // r8
  __int64 v65; // rdx
  LPVOID *v66; // rcx
  _QWORD *v67; // rax
  unsigned int v68; // eax
  unsigned int v69; // ebx
  LPVOID *v70; // r14
  void *v71; // rcx
  JET_ERR v72; // eax
  unsigned int *v74; // [rsp+20h] [rbp-E0h]
  __int64 v75; // [rsp+30h] [rbp-D0h]
  unsigned int v76; // [rsp+50h] [rbp-B0h]
  unsigned int v77; // [rsp+54h] [rbp-ACh]
  int v79; // [rsp+5Ch] [rbp-A4h]
  unsigned int v80; // [rsp+60h] [rbp-A0h]
  int v81; // [rsp+64h] [rbp-9Ch]
  unsigned int v82; // [rsp+68h] [rbp-98h]
  int v84; // [rsp+78h] [rbp-88h]
  int v85; // [rsp+7Ch] [rbp-84h]
  unsigned int v86; // [rsp+80h] [rbp-80h]
  unsigned int v87; // [rsp+84h] [rbp-7Ch]
  int v89; // [rsp+90h] [rbp-70h]
  int v91; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v92; // [rsp+ACh] [rbp-54h]
  __int64 v93; // [rsp+B0h] [rbp-50h]
  __int64 v94; // [rsp+B8h] [rbp-48h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID pv[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v97; // [rsp+D8h] [rbp-28h]
  LPVOID v98[3]; // [rsp+E8h] [rbp-18h]
  struct JET_RETRIEVECOLUMN v99[16]; // [rsp+100h] [rbp+0h] BYREF

  v7 = tableid;
  v8 = a1;
  Data = 0;
  SystemTimeAsFileTime = 0;
  v76 = 0;
  v80 = 0;
  v86 = 0;
  v87 = 0;
  memset(a7, 0, 4LL * a5);
  memset(a6, 0, 240LL * a5);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v82 = 0;
  v11 = 0;
  if ( !a5 )
    return (unsigned int)Data;
  v79 = a3 & 6;
  v85 = a3 & 8;
  v84 = a3 & 0x10;
  v89 = a3 & 1;
  while ( 1 )
  {
    v12 = v11;
    v13 = 240LL * v11;
    memset(v99, 0, sizeof(v99));
    v14 = 0;
    if ( v79 )
    {
      v14 = 5;
      v99[0].columnid = dword_1803385F4;
      v99[1].columnid = dword_1803385F8;
      v99[2].columnid = dword_1803385DC;
      v99[3].columnid = dword_180338620;
      v99[4].columnid = dword_18033862C;
      v99[0].pvData = 0;
      v99[0].cbData = 0;
      v99[0].itagSequence = 0;
      v99[1].pvData = 0;
      v99[1].cbData = 0;
      v99[1].itagSequence = 0;
      v99[2].pvData = 0;
      v99[2].cbData = 0;
      v99[2].itagSequence = 0;
      v99[3].pvData = 0;
      v99[3].cbData = 0;
      v99[3].itagSequence = 0;
      v99[4].pvData = 0;
      v99[4].cbData = 0;
      v99[4].itagSequence = 0;
    }
    v15 = v14;
    v16 = v14 + 1;
    v17 = v15;
    v99[v17].columnid = dword_1803385D0;
    v99[v17].pvData = (char *)a6 + v13 + 28;
    v99[v17].cbData = 16;
    v99[v17].itagSequence = 1;
    if ( v85 )
    {
      v18 = v16;
      v19 = (unsigned int)(v16 + 1);
      v99[v18].columnid = dword_1803385E8;
      v99[v18].cbData = 8;
      v99[v18].pvData = (char *)a6 + v13 + 72;
      v20 = dword_1803385EC;
      v99[v18].itagSequence = 1;
      v21 = v19;
      v22 = (unsigned int)(v19 + 1);
      v99[v21].columnid = v20;
      v99[v21].cbData = 8;
      v99[v21].pvData = (char *)a6 + v13 + 64;
      v23 = dword_1803385F0;
      v99[v21].itagSequence = 1;
      v24 = v22;
      v99[v24].columnid = v23;
      v99[v24].cbData = 4;
      v99[v24].pvData = (char *)a6 + v13 + 96;
      v16 = (unsigned int)(v22 + 1);
      v99[v24].itagSequence = 1;
    }
    if ( v84 )
    {
      v25 = v16;
      v26 = (unsigned int)(v16 + 1);
      v99[v25].columnid = dword_180338624;
      v99[v25].cbData = 4;
      v99[v25].pvData = (char *)a6 + v13 + 188;
      v27 = dword_180338618;
      v99[v25].itagSequence = 1;
      v28 = v26;
      v29 = (unsigned int)(v26 + 1);
      v99[v28].columnid = v27;
      v30 = dword_180338628;
      v99[v28].pvData = (char *)a6 + v13 + 144;
      v99[v28].cbData = 16;
      v99[v28].itagSequence = 1;
      v31 = v29;
      v99[v31].columnid = v30;
      v99[v31].cbData = 2;
      v99[v31].pvData = (char *)a6 + v13 + 192;
      v16 = (unsigned int)(v29 + 1);
      v99[v31].itagSequence = 1;
    }
    if ( v89 )
    {
      v32 = v16;
      v16 = (unsigned int)(v16 + 1);
      v99[v32].columnid = dword_1803385FC;
      v99[v32].cbData = 4;
      v99[v32].itagSequence = 1;
      v99[v32].pvData = &a7[4 * v12];
      v33 = v16;
      v99[v33].columnid = dword_1803385E0;
      v99[v33].cbData = 4;
      v99[v33].pvData = (char *)a6 + v13 + 24;
      LODWORD(v16) = v16 + 1;
      v99[v33].itagSequence = 1;
    }
    Data = DsqGetData(v8, v7, v99, v16);
    if ( Data < 0 )
    {
      if ( Data == -2145091577 )
        Data = -2145091576;
      goto LABEL_119;
    }
    itagSequence = v80;
    if ( v79 )
      itagSequence = v99[2].itagSequence;
    v80 = itagSequence;
    if ( v84 )
    {
      v86 = v99[3].itagSequence;
      v87 = v99[4].itagSequence;
    }
    v35 = &c_svcPolicyDriven;
    if ( memcmp((char *)a6 + v13 + 28, &c_idSrvPolicyDriven, 0x10u) )
      v35 = 0;
    if ( v35 && v85 )
    {
      *(_QWORD *)((char *)a6 + v13 + 72) = v35[9];
      *(_QWORD *)((char *)a6 + v13 + 64) = v35[8];
      *(_DWORD *)((char *)a6 + v13 + 96) = *((_DWORD *)v35 + 24);
    }
    v36 = a3;
    if ( (a3 & 0x16) != 0 )
    {
      if ( v84 )
      {
        *(&v99[0].columnid + 1) = 0;
        *(_OWORD *)&v99[0].cbData = 0;
        v99[0].columnid = dword_18033861C;
        *(_OWORD *)&v99[0].itagSequence = 0;
        v99[0].pvData = 0;
        v99[0].cbData = 0;
        v99[0].itagSequence = 1;
        LODWORD(v74) = 0;
        VarColumns = DsqRetrieveVarColumns(v8, v7, v99, 1);
        Data = VarColumns;
        if ( VarColumns < 0 )
        {
          if ( VarColumns != -2145091577 )
            goto LABEL_119;
          Data = 0;
        }
        *(_QWORD *)((char *)a6 + v13 + 160) = v99[0].pvData;
        if ( v86 )
        {
          v93 = 16;
          v91 = 136;
          v92 = v86;
          v94 = 0;
          Data = DsqGetMultiValSetFixed(v8, v7, (struct tagDsqMultiValRetrieveFixed *)&v91, v38, v74);
          if ( Data < 0 )
            goto LABEL_119;
          *(_QWORD *)((char *)a6 + v13 + 176) = v94;
          *(_DWORD *)((char *)a6 + v13 + 168) = v92;
        }
        if ( v87 )
        {
          v93 = 16;
          v91 = 139;
          v92 = v87;
          v94 = 0;
          Data = DsqGetMultiValSetFixed(v8, v7, (struct tagDsqMultiValRetrieveFixed *)&v91, v38, v74);
          if ( Data < 0 )
            goto LABEL_119;
          *(_QWORD *)((char *)a6 + v13 + 232) = v94;
          *(_DWORD *)((char *)a6 + v13 + 224) = v92;
        }
        v36 = a3;
      }
      if ( v79 )
      {
        v39 = v36 & 2;
        if ( (v36 & 2) != 0 )
        {
          v76 = v99[0].itagSequence;
          if ( v99[0].itagSequence != v99[1].itagSequence )
          {
            Data = -2145091582;
            LODWORD(v75) = -2145091582;
            WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %ws", v75, L"Service has mismatched count of languages & names\n");
            goto LABEL_119;
          }
          if ( !v99[0].itagSequence )
          {
            Data = -2145091576;
            LODWORD(v75) = -2145091576;
            WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %ws", v75, L"Service missing localized properites (name)\n");
            goto LABEL_119;
          }
        }
        if ( (v36 & 4) != 0 )
        {
          if ( !v35 )
          {
            memset(v99, 0, 0xC0u);
            v99[0].columnid = dword_1803385D4;
            v99[1].columnid = dword_180338600;
            v47 = 4;
            v99[0].itagSequence = 1;
            v99[1].itagSequence = 1;
            v99[2].itagSequence = 1;
            v99[3].itagSequence = 1;
            v45 = tableid;
            v99[0].pvData = 0;
            v99[0].cbData = 0;
            v99[1].pvData = 0;
            v99[1].cbData = 0;
            v99[2].columnid = dword_1803385E4;
            v99[2].pvData = 0;
            v99[2].cbData = 0;
            v99[3].pvData = 0;
            v99[3].cbData = 0;
            v99[3].columnid = dword_1803385D8;
            v48 = DsqRetrieveVarColumns(v8, tableid, v99, 4);
            Data = v48;
            if ( v48 < 0 )
            {
              if ( v48 != -2145091577 )
                goto LABEL_119;
              if ( v99[1].err )
              {
                if ( !v99[2].err )
                  goto LABEL_55;
              }
              else if ( v99[2].err )
              {
LABEL_55:
                Data = -2145091582;
                LODWORD(v75) = -2145091582;
                WUTrace(
                  0,
                  0,
                  0x2000,
                  1,
                  0,
                  L"DS: 0x%08x: %ws",
                  v75,
                  L"Service has cert hash without cert hash algo or vice versa\n");
                p_pvData = &v99[0].pvData;
                do
                {
                  if ( *p_pvData )
                    CoTaskMemFree(*p_pvData);
                  p_pvData += 6;
                  --v47;
                }
                while ( v47 );
                goto LABEL_119;
              }
              Data = 0;
            }
            *(_QWORD *)((char *)a6 + v13) = v99[0].pvData;
            *(_QWORD *)((char *)a6 + v13 + 16) = v99[1].pvData;
            *(_DWORD *)((char *)a6 + v13 + 48) = v99[2].cbActual;
            *(_QWORD *)((char *)a6 + v13 + 56) = v99[2].pvData;
            if ( v80 )
            {
              Data = DSGetMVTextColumn(
                       v8,
                       tableid,
                       119,
                       v80,
                       (wchar_t ***)((char *)a6 + v13 + 128),
                       (unsigned int *)((char *)a6 + v13 + 120),
                       1,
                       0);
              if ( Data < 0 )
                goto LABEL_119;
            }
            goto LABEL_48;
          }
          if ( *((_DWORD *)v35 + 30) )
          {
            v40 = SafeSusComAllocArray(*((unsigned int *)v35 + 30), 8u);
            *(_QWORD *)((char *)a6 + v13 + 128) = v40;
            if ( !v40 )
              goto LABEL_110;
            v41 = 0;
            *(_DWORD *)((char *)a6 + v13 + 120) = *((_DWORD *)v35 + 30);
            if ( *((_DWORD *)v35 + 30) )
            {
              while ( 1 )
              {
                v42 = -1;
                do
                  ++v42;
                while ( *(_WORD *)(*(_QWORD *)(v35[16] + 8LL * v41) + 2 * v42) );
                v43 = (int)v42 + 1;
                *(_QWORD *)(*(_QWORD *)((char *)a6 + v13 + 128) + 8LL * v41) = SafeSusComAllocArray(v43, 2u);
                v44 = *(void **)(*(_QWORD *)((char *)a6 + v13 + 128) + 8LL * v41);
                if ( !v44 )
                  break;
                memmove(v44, *(const void **)(v35[16] + 8LL * v41++), 2 * v43);
                if ( v41 >= *((_DWORD *)v35 + 30) )
                {
                  v8 = a1;
                  goto LABEL_47;
                }
              }
LABEL_110:
              Data = -2147024882;
              goto LABEL_119;
            }
          }
        }
LABEL_47:
        v45 = tableid;
LABEL_48:
        if ( v39 )
        {
          if ( *a4 )
            v46 = a4[1];
          else
            v46 = 1;
          v77 = v46;
          v50 = SafeSusComAllocArray(v46, 0x10u);
          *(_QWORD *)((char *)a6 + v13 + 112) = v50;
          if ( !v50 )
            goto LABEL_110;
          v51 = v76;
          pv[1] = 0;
          v98[0] = 0;
          pv[0] = (LPVOID)126;
          v97 = v76;
          v98[1] = (LPVOID)v76;
          Data = DsqGetMultiValSetText(v8, v45, (struct tagDsqMultiValRetrieveText *)pv, 2u, 0, 0);
          if ( Data < 0 )
            goto LABEL_119;
          v52 = a4;
          v53 = -1;
          v54 = 0;
          v81 = -1;
          v55 = 0;
          if ( !a4[1] )
            goto LABEL_88;
          do
          {
            if ( v54 >= v46 )
              break;
            v56 = 0;
            if ( v51 )
            {
              while ( v56 < (unsigned int)v97 )
              {
                v57 = (const WCHAR *)*((_QWORD *)pv[1] + v56);
                if ( v57 )
                {
                  if ( v53 == -1 )
                    v53 = v56;
                  v81 = v53;
                  Data = AsciiStringCompareI(*(PCNZWCH *)(*((_QWORD *)v52 + 1) + 8LL * v55), v57);
                  if ( !Data )
                  {
                    v58 = 2LL * v54;
                    *(_QWORD *)(*(_QWORD *)((char *)a6 + v13 + 112) + 8 * v58) = *((_QWORD *)pv[1] + v56);
                    *(_QWORD *)(*(_QWORD *)((char *)a6 + v13 + 112) + 8 * v58 + 8) = *((_QWORD *)v98[0] + v56);
                    v59 = &pv[1];
                    v60 = 2;
                    do
                    {
                      v61 = *v59;
                      v59 += 3;
                      v61[v56] = 0;
                      --v60;
                    }
                    while ( v60 );
                    v51 = v76;
                    ++v54;
                    v52 = a4;
                    break;
                  }
                  v53 = v81;
                  v52 = a4;
                }
                v51 = v76;
                if ( ++v56 >= v76 )
                  break;
              }
            }
            v53 = v81;
            ++v55;
            v46 = v77;
          }
          while ( v55 < v52[1] );
          if ( v54 )
          {
LABEL_88:
            v63 = (LPVOID *)v98[0];
            v62 = pv[1];
          }
          else
          {
            v62 = pv[1];
            v63 = (LPVOID *)v98[0];
            if ( v53 != -1 )
            {
              v64 = 2;
              v65 = v53;
              **(_QWORD **)((char *)a6 + v13 + 112) = *((_QWORD *)pv[1] + v53);
              *(_QWORD *)(*(_QWORD *)((char *)a6 + v13 + 112) + 8LL) = v63[v53];
              v66 = &pv[1];
              do
              {
                v67 = *v66;
                v66 += 3;
                v67[v65] = 0;
                --v64;
              }
              while ( v64 );
              v54 = 1;
            }
          }
          v68 = v76;
          *(_DWORD *)((char *)a6 + v13 + 108) = v54;
          v69 = 0;
          if ( v76 )
          {
            v70 = v63;
            do
            {
              if ( v69 < (unsigned int)v97 )
              {
                v71 = *(LPVOID *)((char *)v70 + v62 - (_BYTE *)v63);
                if ( v71 )
                {
                  CoTaskMemFree(v71);
                  v68 = v76;
                }
              }
              if ( v69 < LODWORD(v98[1]) && *v70 )
              {
                CoTaskMemFree(*v70);
                v68 = v76;
              }
              ++v69;
              ++v70;
            }
            while ( v69 < v68 );
          }
          if ( v62 )
            CoTaskMemFree(v62);
          if ( v63 )
            CoTaskMemFree(v63);
          *(_OWORD *)pv = 0;
          v97 = 0;
          *(_OWORD *)v98 = 0;
        }
        v7 = tableid;
      }
    }
    if ( v82 == a5 - 1 )
      goto LABEL_115;
    v8 = a1;
    v72 = JetMove(a1, v7, 1, 0);
    if ( v72 )
      break;
    v11 = v82 + 1;
    v82 = v11;
    if ( v11 >= a5 )
      goto LABEL_115;
  }
  if ( v72 == -1603 )
    Data = -2145091582;
  else
    Data = JETErrToHRESULTAndAttemptRecovery(v72);
  LODWORD(v75) = Data;
  WUTrace(0, 0, 0x2000, 1, 0, L"DS: 0x%08x: %hs failed. sesid: %Ix. tableid: %Ix", v75, "JetMove", a1, v7);
LABEL_115:
  if ( Data >= 0 )
    return (unsigned int)Data;
LABEL_119:
  DsqFreeObject(a6, a5, 1);
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x180186bd8  mov     [rsp-8+arg_10], rbx
0x180186bdd  push    rbp
0x180186bde  push    rsi
0x180186bdf  push    rdi
0x180186be0  push    r12
0x180186be2  push    r13
0x180186be4  push    r14
0x180186be6  push    r15
0x180186be8  lea     rbp, [rsp-310h]
0x180186bf0  sub     rsp, 410h
0x180186bf7  mov     rax, cs:__security_cookie
0x180186bfe  xor     rax, rsp
0x180186c01  mov     [rbp+340h+var_40], rax
0x180186c08  mov     r15d, [rbp+340h+arg_20]
0x180186c0f  mov     r12, rdx
0x180186c12  mov     rsi, [rbp+340h+arg_28]
0x180186c19  mov     r13, rcx
0x180186c1c  mov     [rsp+440h+var_3D0], rdx
0x180186c21  mov     r14d, r8d
0x180186c24  xor     edx, edx; Val
0x180186c26  mov     [rbp+340h+sesid], rcx
0x180186c2a  mov     rcx, [rbp+340h+arg_30]; void *
0x180186c31  mov     edi, edx
0x180186c33  mov     [rsp+440h+var_3E8], r8d
0x180186c38  lea     r8, ds:0[r15*4]; Size
0x180186c40  mov     [rbp+340h+var_3B8], r9
0x180186c44  mov     [rbp+340h+var_3A0], rcx
0x180186c48  mov     qword ptr [rbp+340h+SystemTimeAsFileTime.dwLowDateTime], rdx
0x180186c4c  mov     [rsp+440h+var_3F0], edx
0x180186c50  mov     [rsp+440h+var_3E0], edx
0x180186c54  mov     [rbp+340h+var_3C0], edx
0x180186c57  mov     [rbp+340h+var_3BC], edx
0x180186c5a  call    memset
0x180186c5f  imul    r8, r15, 0F0h; Size
0x180186c66  xor     edx, edx; Val
0x180186c68  mov     rcx, rsi; void *
0x180186c6b  call    memset
0x180186c70  lea     rcx, [rbp+340h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180186c74  call    cs:__imp_GetSystemTimeAsFileTime
0x180186c7a  xor     eax, eax
0x180186c7c  mov     [rsp+440h+var_3D8], eax
0x180186c80  mov     ecx, eax
0x180186c82  test    r15d, r15d
0x180186c85  jz      loc_1801876F6
0x180186c8b  mov     eax, r14d
0x180186c8e  and     eax, 6
0x180186c91  mov     [rsp+440h+var_3E4], eax
0x180186c95  mov     eax, r14d
0x180186c98  and     eax, 8
0x180186c9b  mov     [rsp+440h+var_3C4], eax
0x180186c9f  mov     eax, r14d
0x180186ca2  and     eax, 10h
0x180186ca5  mov     [rsp+440h+var_3C8], eax
0x180186ca9  mov     eax, r14d
0x180186cac  and     eax, 1
0x180186caf  mov     [rbp+340h+var_3B0], eax
0x180186cb2  mov     edi, ecx
0x180186cb4  lea     r15, [rsi+90h]
0x180186cbb  imul    rbx, rdi, 0F0h
0x180186cc2  xor     edx, edx; Val
0x180186cc4  lea     rcx, [rbp+340h+var_340]; void *
0x180186cc8  mov     r8d, 300h; Size
0x180186cce  add     r15, rbx
0x180186cd1  call    memset
0x180186cd6  xor     r8d, r8d
0x180186cd9  mov     r9d, r8d
0x180186cdc  cmp     [rsp+440h+var_3E4], r8d
0x180186ce1  jz      loc_180186D6F
0x180186ce7  mov     eax, cs:dword_1803385F4
0x180186ced  lea     r9d, [r8+5]
0x180186cf1  mov     [rbp+340h+var_340.columnid], eax
0x180186cf4  mov     eax, cs:dword_1803385F8
0x180186cfa  mov     [rbp+340h+var_310], eax
0x180186cfd  mov     eax, cs:dword_1803385DC
0x180186d03  mov     [rbp+340h+var_2E0], eax
0x180186d06  mov     eax, cs:dword_180338620
0x180186d0c  mov     [rbp+340h+var_2B0], eax
0x180186d12  mov     eax, cs:dword_18033862C
0x180186d18  mov     [rbp+340h+var_280], eax
0x180186d1e  mov     [rbp+340h+var_340.pvData], r8
0x180186d22  mov     [rbp+340h+var_340.cbData], r8d
0x180186d26  mov     [rbp+340h+var_340.itagSequence], r8d
0x180186d2a  mov     [rbp+340h+var_308], r8
0x180186d2e  mov     [rbp+340h+var_300], r8d
0x180186d32  mov     [rbp+340h+var_2F0], r8d
0x180186d36  mov     [rbp+340h+var_2D8], r8
0x180186d3a  mov     [rbp+340h+var_2D0], r8d
0x180186d3e  mov     [rbp+340h+var_2C0], r8d
0x180186d45  mov     [rbp+340h+var_2A8], r8
0x180186d4c  mov     [rbp+340h+var_2A0], r8d
0x180186d53  mov     [rbp+340h+var_290], r8d
0x180186d5a  mov     [rbp+340h+var_278], r8
0x180186d61  mov     [rbp+340h+var_270], r8d
0x180186d68  mov     [rbp+340h+var_260], r8d
0x180186d6f  mov     eax, r9d
0x180186d72  lea     r14, [rsi+1Ch]
0x180186d76  mov     r10d, 1
0x180186d7c  add     r14, rbx
0x180186d7f  add     r9d, r10d
0x180186d82  lea     rcx, [rax+rax*2]
0x180186d86  mov     eax, cs:dword_1803385D0
0x180186d8c  add     rcx, rcx
0x180186d8f  lea     edx, [r10+3]
0x180186d93  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186d97  mov     [rbp+rcx*8+340h+var_340.pvData], r14
0x180186d9c  mov     [rbp+rcx*8+340h+var_340.cbData], 10h
0x180186da4  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186da9  cmp     [rsp+440h+var_3C4], r8d
0x180186dae  jz      loc_180186E37
0x180186db4  mov     eax, cs:dword_1803385E8
0x180186dba  lea     rcx, [r9+r9*2]
0x180186dbe  add     rcx, rcx
0x180186dc1  add     r9d, r10d
0x180186dc4  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186dc8  lea     rax, [rsi+48h]
0x180186dcc  mov     [rbp+rcx*8+340h+var_340.cbData], 8
0x180186dd4  add     rax, rbx
0x180186dd7  mov     [rbp+rcx*8+340h+var_340.pvData], rax
0x180186ddc  mov     eax, cs:dword_1803385EC
0x180186de2  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186de7  lea     rcx, [r9+r9*2]
0x180186deb  add     rcx, rcx
0x180186dee  add     r9d, r10d
0x180186df1  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186df5  lea     rax, [rsi+40h]
0x180186df9  mov     [rbp+rcx*8+340h+var_340.cbData], 8
0x180186e01  add     rax, rbx
0x180186e04  mov     [rbp+rcx*8+340h+var_340.pvData], rax
0x180186e09  mov     eax, cs:dword_1803385F0
0x180186e0f  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186e14  lea     rcx, [r9+r9*2]
0x180186e18  add     rcx, rcx
0x180186e1b  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186e1f  lea     rax, [rsi+60h]
0x180186e23  add     rax, rbx
0x180186e26  mov     [rbp+rcx*8+340h+var_340.cbData], edx
0x180186e2a  mov     [rbp+rcx*8+340h+var_340.pvData], rax
0x180186e2f  add     r9d, r10d
0x180186e32  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186e37  cmp     [rsp+440h+var_3C8], r8d
0x180186e3c  jz      loc_180186EC4
0x180186e42  mov     eax, cs:dword_180338624
0x180186e48  lea     rcx, [r9+r9*2]
0x180186e4c  add     rcx, rcx
0x180186e4f  add     r9d, r10d
0x180186e52  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186e56  lea     rax, [rsi+0BCh]
0x180186e5d  mov     [rbp+rcx*8+340h+var_340.cbData], edx
0x180186e61  add     rax, rbx
0x180186e64  mov     [rbp+rcx*8+340h+var_340.pvData], rax
0x180186e69  mov     eax, cs:dword_180338618
0x180186e6f  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186e74  lea     rcx, [r9+r9*2]
0x180186e78  add     rcx, rcx
0x180186e7b  add     r9d, r10d
0x180186e7e  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186e82  mov     eax, cs:dword_180338628
0x180186e88  mov     [rbp+rcx*8+340h+var_340.pvData], r15
0x180186e8d  mov     [rbp+rcx*8+340h+var_340.cbData], 10h
0x180186e95  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186e9a  lea     rcx, [r9+r9*2]
0x180186e9e  add     rcx, rcx
0x180186ea1  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186ea5  lea     rax, [rsi+0C0h]
0x180186eac  add     rax, rbx
0x180186eaf  mov     [rbp+rcx*8+340h+var_340.cbData], 2
0x180186eb7  mov     [rbp+rcx*8+340h+var_340.pvData], rax
0x180186ebc  add     r9d, r10d
0x180186ebf  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186ec4  cmp     [rbp+340h+var_3B0], r8d
0x180186ec8  jz      short loc_180186F1D
0x180186eca  mov     eax, cs:dword_1803385FC
0x180186ed0  lea     rcx, [r9+r9*2]
0x180186ed4  add     rcx, rcx
0x180186ed7  add     r9d, r10d
0x180186eda  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186ede  mov     rax, [rbp+340h+var_3A0]
0x180186ee2  mov     [rbp+rcx*8+340h+var_340.cbData], edx
0x180186ee6  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186eeb  lea     rax, [rax+rdi*4]
0x180186eef  mov     [rbp+rcx*8+340h+var_340.pvData], rax
0x180186ef4  lea     rcx, [r9+r9*2]
0x180186ef8  mov     eax, cs:dword_1803385E0
0x180186efe  add     rcx, rcx
0x180186f01  mov     [rbp+rcx*8+340h+var_340.columnid], eax
0x180186f05  lea     rax, [rsi+18h]
0x180186f09  add     rax, rbx
0x180186f0c  mov     [rbp+rcx*8+340h+var_340.cbData], edx
0x180186f10  mov     [rbp+rcx*8+340h+var_340.pvData], rax
0x180186f15  add     r9d, r10d; unsigned int
0x180186f18  mov     [rbp+rcx*8+340h+var_340.itagSequence], r10d
0x180186f1d  lea     r8, [rbp+340h+var_340]; struct JET_RETRIEVECOLUMN *
0x180186f21  mov     rdx, r12; unsigned __int64
0x180186f24  mov     rcx, r13; unsigned __int64
0x180186f27  call    ?DsqGetData@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@K@Z; DsqGetData(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong)
0x180186f2c  xor     ecx, ecx
0x180186f2e  mov     edi, eax
0x180186f30  test    eax, eax
0x180186f32  js      loc_1801876D4
0x180186f38  cmp     [rsp+440h+var_3E4], ecx
0x180186f3c  mov     eax, [rsp+440h+var_3E0]
0x180186f40  cmovnz  eax, [rbp+340h+var_2C0]
0x180186f47  mov     r15d, [rsp+440h+var_3C8]
0x180186f4c  mov     [rsp+440h+var_3E0], eax
0x180186f50  test    r15d, r15d
0x180186f53  jz      short loc_180186F67
0x180186f55  mov     eax, [rbp+340h+var_290]
0x180186f5b  mov     [rbp+340h+var_3C0], eax
0x180186f5e  mov     eax, [rbp+340h+var_260]
0x180186f64  mov     [rbp+340h+var_3BC], eax
0x180186f67  mov     r8d, 10h; Size
0x180186f6d  lea     rdx, c_idSrvPolicyDriven; Buf2
0x180186f74  mov     rcx, r14; Buf1
0x180186f77  call    memcmp
0x180186f7c  xor     r10d, r10d
0x180186f7f  lea     r14, ?c_svcPolicyDriven@@3UtagDSServicePropsAll@@B; tagDSServicePropsAll const c_svcPolicyDriven
0x180186f86  test    eax, eax
0x180186f88  cmovnz  r14, r10
0x180186f8c  test    r14, r14
0x180186f8f  jz      short loc_180186FB2
0x180186f91  cmp     [rsp+440h+var_3C4], r10d
0x180186f96  jz      short loc_180186FB2
0x180186f98  mov     rax, [r14+48h]
0x180186f9c  mov     [rbx+rsi+48h], rax
0x180186fa1  mov     rax, [r14+40h]
0x180186fa5  mov     [rbx+rsi+40h], rax
0x180186faa  mov     eax, [r14+60h]
0x180186fae  mov     [rbx+rsi+60h], eax
0x180186fb2  mov     ecx, [rsp+440h+var_3E8]
0x180186fb6  test    cl, 16h
0x180186fb9  jz      loc_1801875D3
0x180186fbf  test    r15d, r15d
0x180186fc2  mov     r15d, 1
0x180186fc8  jz      loc_1801870D3
0x180186fce  mov     eax, cs:dword_18033861C
0x180186fd4  lea     r8, [rbp+340h+var_340]
0x180186fd8  xorps   xmm0, xmm0
0x180186fdb  mov     [rsp+440h+var_418], r10
0x180186fe0  movups  xmmword ptr [rbp+340h+var_340.columnid], xmm0
0x180186fe4  mov     r9d, r15d
0x180186fe7  mov     rdx, r12
0x180186fea  movups  xmmword ptr [rbp+340h+var_340.cbData], xmm0
0x180186fee  mov     rcx, r13
0x180186ff1  mov     [rbp+340h+var_340.columnid], eax
0x180186ff4  movups  xmmword ptr [rbp+340h+var_340.itagSequence], xmm0
0x180186ff8  mov     [rbp+340h+var_340.pvData], r10
0x180186ffc  mov     [rbp+340h+var_340.cbData], r10d
0x180187000  mov     [rbp+340h+var_340.itagSequence], r15d
0x180187004  mov     dword ptr [rsp+440h+var_420], r10d; unsigned int *
0x180187009  call    ?DsqRetrieveVarColumns@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@KW4tagDsqAllocMethod@@PEAW42@@Z; DsqRetrieveVarColumns(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong,tagDsqAllocMethod,tagDsqAllocMethod *)
0x18018700e  xor     r10d, r10d
0x180187011  mov     edi, eax
0x180187013  test    eax, eax
0x180187015  jns     short loc_180187025
0x180187017  cmp     eax, 80248007h
0x18018701c  jnz     loc_1801876E2
0x180187022  mov     edi, r10d
0x180187025  mov     rax, [rbp+340h+var_340.pvData]
0x180187029  mov     [rbx+rsi+0A0h], rax
0x180187031  mov     eax, [rbp+340h+var_3C0]
0x180187034  test    eax, eax
0x180187036  jz      short loc_180187080
0x180187038  lea     r8, [rbp+340h+var_398]; struct tagDsqMultiValRetrieveFixed *
0x18018703c  mov     [rbp+340h+var_390], 10h
0x180187044  mov     rdx, r12; tableid
0x180187047  mov     [rbp+340h+var_398], 88h
0x18018704e  mov     rcx, r13; sesid
0x180187051  mov     [rbp+340h+var_394], eax
0x180187054  mov     [rbp+340h+var_388], r10
0x180187058  call    ?DsqGetMultiValSetFixed@@YAJ_K0PEAUtagDsqMultiValRetrieveFixed@@KQEAK@Z; DsqGetMultiValSetFixed(unsigned __int64,unsigned __int64,tagDsqMultiValRetrieveFixed *,ulong,ulong * const)
0x18018705d  xor     r10d, r10d
0x180187060  mov     edi, eax
0x180187062  test    eax, eax
0x180187064  js      loc_1801876E2
0x18018706a  mov     rax, [rbp+340h+var_388]
0x18018706e  mov     [rbx+rsi+0B0h], rax
0x180187076  mov     eax, [rbp+340h+var_394]
0x180187079  mov     [rbx+rsi+0A8h], eax
0x180187080  mov     eax, [rbp+340h+var_3BC]
0x180187083  test    eax, eax
0x180187085  jz      short loc_1801870CF
0x180187087  lea     r8, [rbp+340h+var_398]; struct tagDsqMultiValRetrieveFixed *
0x18018708b  mov     [rbp+340h+var_390], 10h
0x180187093  mov     rdx, r12; tableid
0x180187096  mov     [rbp+340h+var_398], 8Bh
0x18018709d  mov     rcx, r13; sesid
0x1801870a0  mov     [rbp+340h+var_394], eax
0x1801870a3  mov     [rbp+340h+var_388], r10
0x1801870a7  call    ?DsqGetMultiValSetFixed@@YAJ_K0PEAUtagDsqMultiValRetrieveFixed@@KQEAK@Z; DsqGetMultiValSetFixed(unsigned __int64,unsigned __int64,tagDsqMultiValRetrieveFixed *,ulong,ulong * const)
0x1801870ac  xor     r10d, r10d
0x1801870af  mov     edi, eax
0x1801870b1  test    eax, eax
0x1801870b3  js      loc_1801876E2
0x1801870b9  mov     rax, [rbp+340h+var_388]
0x1801870bd  mov     [rbx+rsi+0E8h], rax
0x1801870c5  mov     eax, [rbp+340h+var_394]
0x1801870c8  mov     [rbx+rsi+0E0h], eax
0x1801870cf  mov     ecx, [rsp+440h+var_3E8]
0x1801870d3  cmp     [rsp+440h+var_3E4], r10d
0x1801870d8  jz      loc_1801875D3
  ... truncated ...
```
