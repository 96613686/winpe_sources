# CEseLayerLogicalDatabase::CreateOrOpenExistingObjectStore(CEseLayerTransaction *,ulong,ushort const *,ulong,ushort const *,bool,bool,CEseLayerObjectStore * *,__int64 *)

- ea: `0x1800107e0`
- end: `0x180011cc3`
- name: `?CreateOrOpenExistingObjectStore@CEseLayerLogicalDatabase@@AEAAJPEAVCEseLayerTransaction@@KPEBGK1_N2PEAPEAVCEseLayerObjectStore@@PEA_J@Z`
- size: `5347`
- prototype: `int(CEseLayerLogicalDatabase *__hidden this, struct CEseLayerTransaction *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, bool, bool, struct CEseLayerObjectStore **, __int64 *)`
- caller_count: `2`
- callee_count: `28`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020308`
- `0x1800b122c`

## callees

- `0x18000c250`
- `0x18000cfb0`
- `0x18000d440`
- `0x18000d5a0`
- `0x18000dd40`
- `0x18000f630`
- `0x18000f810`
- `0x1800107e0`
- `0x180011cd0`
- `0x180012680`
- `0x180015a40`
- `0x180015bb0`
- `0x180016b40`
- `0x180017c20`
- `0x1800182a4`
- `0x180022740`
- `0x180024650`
- `0x1800314c4`
- `0x180031580`
- `0x1800315f0`
- `0x18003166c`
- `0x180056a88`
- `0x1800766b8`
- `0x180080fb0`
- `0x1800814bc`
- `0x1800babe4`
- `0x1800baf14`
- `0x1800c6010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010eba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ef4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001159a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001160e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011648`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010eba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010ef4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010fa2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800111bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001159a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800115d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001160e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011648`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a68`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a68`
- `ESENT!JetCloseTable` at `0x180011b3d`
- `ESENT!JetCloseTable` at `0x180011b50`
- `ESENT!JetCloseTable` at `0x180011b63`
- `ESENT!JetCloseTable` at `0x180011b3d`
- `ESENT!JetCloseTable` at `0x180011b50`
- `ESENT!JetCloseTable` at `0x180011b63`

## pseudocode

```c
__int64 __fastcall CEseLayerLogicalDatabase::CreateOrOpenExistingObjectStore(
        CEseLayerLogicalDatabase *this,
        struct CEseLayerTransaction *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        char a7,
        bool a8,
        struct CEseLayerObjectStore **a9,
        __int64 *a10)
{
  const char *v13; // r9
  unsigned __int64 v14; // r13
  unsigned int v15; // ebx
  const void *v16; // r9
  HRESULT Key; // r15d
  unsigned int v18; // edx
  JET_TABLEID v19; // rbx
  JET_COLUMNID *v20; // r13
  int v21; // eax
  JET_COLUMNID v22; // eax
  char v23; // bl
  JET_TABLEID v24; // rdi
  unsigned int v25; // edx
  CEseLayerIndexSchema *v26; // rsi
  char *v27; // rax
  const void *v28; // r9
  CEseLayerObjectStore **v29; // r13
  bool v30; // zf
  CEseLayerLogicalDatabase *v31; // rbx
  char *v32; // r15
  JET_TABLEID v33; // r12
  JET_TABLEID v34; // rsi
  unsigned __int64 v35; // r14
  unsigned int v36; // r13d
  int ColumnInfo; // edi
  _DWORD *v38; // rsi
  const void *v39; // r9
  unsigned int v40; // edx
  __int64 v41; // r12
  CEseLayerIndexSchema *v42; // rcx
  char v43; // bl
  __int64 v45; // r12
  CEseLayerIndexSchema *v46; // rbx
  unsigned int j; // ebx
  const unsigned __int16 *v48; // r9
  const unsigned __int16 *v49; // r8
  CEseLayerIndexSchema *v50; // rcx
  char *v51; // rbx
  __int64 v52; // rax
  const void *v53; // r9
  __int64 *v54; // rsi
  JET_TABLEID v55; // r12
  unsigned int v56; // edi
  unsigned int v57; // edx
  int v58; // ebx
  int v59; // eax
  JET_TABLEID v60; // r14
  int v61; // r13d
  unsigned __int64 v62; // rdx
  int v63; // eax
  unsigned int v64; // ebx
  unsigned int v65; // edi
  const unsigned __int16 *v66; // r9
  const unsigned __int16 *v67; // r8
  void *v68; // rax
  char *v69; // rcx
  JET_TABLEID v70; // r12
  unsigned int i; // esi
  void *v72; // rax
  __int64 v73; // rcx
  __int64 v74; // rax
  CEseLayerObjectStore *v75; // rdi
  int v76; // ebx
  const char *v77; // r9
  unsigned __int64 v78; // rbx
  unsigned int v79; // esi
  const void *v80; // r9
  const void *v81; // r9
  const struct CEseLayerDatabaseSchema *v82; // r8
  CEseLayerObjectStore **v83; // rbx
  __int64 v84; // r8
  unsigned int v85; // [rsp+20h] [rbp-E0h]
  unsigned int v86; // [rsp+20h] [rbp-E0h]
  unsigned int pvData; // [rsp+20h] [rbp-E0h]
  struct JET_COLUMNDEF *v88; // [rsp+20h] [rbp-E0h]
  struct JET_COLUMNDEF *v89; // [rsp+20h] [rbp-E0h]
  unsigned int v90; // [rsp+20h] [rbp-E0h]
  unsigned int v91; // [rsp+20h] [rbp-E0h]
  unsigned int v92; // [rsp+30h] [rbp-D0h]
  unsigned int v93; // [rsp+30h] [rbp-D0h]
  __int64 v94; // [rsp+50h] [rbp-B0h]
  bool v95[4]; // [rsp+60h] [rbp-A0h] BYREF
  int v96; // [rsp+64h] [rbp-9Ch]
  char v97; // [rsp+68h] [rbp-98h]
  unsigned int v98; // [rsp+70h] [rbp-90h] BYREF
  JET_TABLEID v99; // [rsp+78h] [rbp-88h] BYREF
  JET_TABLEID v100; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v101; // [rsp+88h] [rbp-78h]
  JET_TABLEID tableid; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v103; // [rsp+98h] [rbp-68h]
  _DWORD *v104; // [rsp+A0h] [rbp-60h]
  JET_TABLEID v105; // [rsp+A8h] [rbp-58h] BYREF
  char *v106; // [rsp+B0h] [rbp-50h]
  JET_TABLEID v107; // [rsp+B8h] [rbp-48h] BYREF
  struct JET_RETRIEVECOLUMN v108; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t *v109; // [rsp+F0h] [rbp-10h]
  __int64 *v110; // [rsp+F8h] [rbp-8h]
  __int64 v111; // [rsp+100h] [rbp+0h]
  wchar_t *v112; // [rsp+108h] [rbp+8h]
  __int64 v113; // [rsp+110h] [rbp+10h]
  char *v114; // [rsp+118h] [rbp+18h]
  wchar_t *v115; // [rsp+120h] [rbp+20h]
  _QWORD *v116; // [rsp+128h] [rbp+28h]
  _QWORD *v117; // [rsp+130h] [rbp+30h]
  unsigned int v118; // [rsp+140h] [rbp+40h]
  __int64 v119; // [rsp+148h] [rbp+48h] BYREF
  JET_TABLEID v120; // [rsp+150h] [rbp+50h] BYREF
  CEseLayerLogicalDatabase *v121; // [rsp+158h] [rbp+58h]
  __int64 v122; // [rsp+160h] [rbp+60h]
  JET_TABLEID v123; // [rsp+168h] [rbp+68h] BYREF
  __int64 v124; // [rsp+170h] [rbp+70h]
  CEseLayerIndexSchema *v125; // [rsp+178h] [rbp+78h] BYREF
  __int64 v126; // [rsp+180h] [rbp+80h] BYREF
  __int64 v127; // [rsp+188h] [rbp+88h] BYREF
  __int64 v128; // [rsp+190h] [rbp+90h] BYREF
  CEseLayerIndexSchema *v129; // [rsp+198h] [rbp+98h]
  CEseLayerObjectStore **v130; // [rsp+1A0h] [rbp+A0h]
  struct JET_RETRIEVECOLUMN v131; // [rsp+1B0h] [rbp+B0h] BYREF
  int v132; // [rsp+1E0h] [rbp+E0h]
  LPVOID v133; // [rsp+1E8h] [rbp+E8h]
  __int64 v134; // [rsp+1F0h] [rbp+F0h]
  __int64 v135; // [rsp+1F8h] [rbp+F8h]
  __int64 v136; // [rsp+200h] [rbp+100h]
  int v137; // [rsp+208h] [rbp+108h]
  int v138; // [rsp+210h] [rbp+110h]
  LPVOID v139; // [rsp+218h] [rbp+118h]
  __int64 v140; // [rsp+220h] [rbp+120h]
  __int64 v141; // [rsp+228h] [rbp+128h]
  __int64 v142; // [rsp+230h] [rbp+130h]
  int v143; // [rsp+238h] [rbp+138h]
  int v144; // [rsp+240h] [rbp+140h]
  LPVOID p_tableid; // [rsp+248h] [rbp+148h]
  __int64 v146; // [rsp+250h] [rbp+150h]
  __int64 v147; // [rsp+258h] [rbp+158h]
  __int64 v148; // [rsp+260h] [rbp+160h]
  int v149; // [rsp+268h] [rbp+168h]
  int v150; // [rsp+270h] [rbp+170h]
  LPVOID v151; // [rsp+278h] [rbp+178h]
  __int64 v152; // [rsp+280h] [rbp+180h]
  __int64 v153; // [rsp+288h] [rbp+188h]
  __int64 v154; // [rsp+290h] [rbp+190h]
  int v155; // [rsp+298h] [rbp+198h]
  wchar_t pszDest[64]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+278h]

  v130 = a9;
  v107 = (JET_TABLEID)a2;
  v121 = this;
  if ( *((_DWORD *)a2 + 3) != GetCurrentThreadId() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xB5,
      (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\ese\\transaction.cxx",
      v13);
  v14 = *((_QWORD *)a2 + 3);
  v15 = *((_DWORD *)a2 + 8);
  v101 = v14;
  Key = HrJetBeginTransaction(v14);
  if ( Key >= 0 )
  {
    v123 = -1;
    Key = HrJetOpenTable(v14, v15, L"DatabaseAndObjectStoreCatalog", v16, v85, 0, &v123);
    if ( Key < 0 )
      goto LABEL_194;
    v19 = v123;
    v20 = (JET_COLUMNID *)*((_QWORD *)v121 + 1);
    v98 = *((_DWORD *)v121 + 6);
    v127 = 0;
    v126 = 0;
    Key = HrJetSetCurrentIndex(v101, v123, L"objectStoreFinder");
    if ( Key >= 0 )
    {
      Key = HrJetMakeKey(v101, v19, &v98, 4u, 1u);
      if ( Key >= 0 )
      {
        Key = HrJetMakeKey(v101, v19, a4, 2 * a3, 0);
        if ( Key >= 0 )
        {
          v21 = HrJetSeek(v101, v19, 1u);
          Key = v21;
          if ( v21 == -1906378305 )
          {
            if ( a8 )
            {
              v82 = (const struct CEseLayerDatabaseSchema *)v20;
              v14 = v101;
              v126 = 0;
              Key = CreateObjectStoreId(v101, v19, v82, v98, a3, a4, &v127, a10);
              if ( Key >= 0 )
              {
                v23 = 1;
                goto LABEL_12;
              }
LABEL_10:
              if ( Key < 0 )
              {
LABEL_190:
                v43 = 1;
                goto LABEL_34;
              }
              v23 = 0;
LABEL_12:
              v24 = v123;
              v128 = v126;
              v122 = v127;
              Key = StringCchPrintfW(pszDest, 0x40u, L"T-%I64x", v127);
              if ( Key >= 0 )
              {
                v125 = (CEseLayerIndexSchema *)operator new(0x400u);
                v129 = CEseLayerIndexSchema::CEseLayerIndexSchema(v125);
                v26 = v129;
                if ( v129 )
                {
                  v27 = (char *)operator new(0xC0u);
                  v29 = v130;
                  v125 = (CEseLayerIndexSchema *)v27;
                  v30 = v23 == 0;
                  v31 = v121;
                  *(_QWORD *)v27 = 0;
                  v32 = v27 + 24;
                  *((_QWORD *)v27 + 1) = 0;
                  *((_QWORD *)v27 + 2) = 0;
                  *((_QWORD *)v27 + 3) = v27 + 24;
                  *((_QWORD *)v27 + 4) = v27 + 24;
                  *((_DWORD *)v27 + 10) = 0;
                  *((_QWORD *)v27 + 6) = 0;
                  *((_QWORD *)v27 + 23) = 0;
                  *((_WORD *)v27 + 28) = 0;
                  *v29 = (CEseLayerObjectStore *)v27;
                  v106 = v27 + 24;
                  if ( v30 )
                  {
                    v33 = v128;
                    v34 = v107;
                    v104 = (_DWORD *)*((_QWORD *)v31 + 1);
                    v35 = *(_QWORD *)(v107 + 24);
                    v36 = *(_DWORD *)(v107 + 32);
                    v124 = v128;
                    v118 = v36;
                    v103 = v35;
                    tableid = v128;
                    v100 = -1;
                    ColumnInfo = HrJetOpenTable(v35, v36, L"IndexCatalog", v28, v86, 0, &v100);
                    if ( ColumnInfo >= 0 )
                    {
                      ColumnInfo = HrJetSetCurrentIndex2(v35, v100, L"indicesById", 0);
                      if ( ColumnInfo < 0
                        || (ColumnInfo = HrJetMakeKey(v35, v100, &tableid, 8u, 1u), ColumnInfo < 0)
                        || (ColumnInfo = HrJetSeek(v35, v100, 1u), ColumnInfo < 0) )
                      {
                        CloseTableIfNecessary(v35, &v100, ColumnInfo);
                      }
                    }
                    if ( ColumnInfo < 0 )
                      goto LABEL_40;
                    v38 = v104;
                    v119 = 0;
                    v120 = 0;
                    v108.columnid = v104[127];
                    v108.pvData = &v119;
                    LODWORD(v109) = v104[120];
                    v110 = (__int64 *)&v120;
                    *(_QWORD *)&v108.cbData = 8;
                    *(_QWORD *)&v108.grbit = 0;
                    *(_QWORD *)&v108.itagSequence = 1;
                    v108.err = 0;
                    v111 = 8;
                    v112 = 0;
                    v113 = 1;
                    LODWORD(v114) = 0;
                    v95[0] = 0;
                    ColumnInfo = HrJetRetrieveColumns(v35, v100, &v108, 2u, v95);
                    if ( ColumnInfo >= 0 )
                    {
                      tableid = v33;
                      v99 = -1;
                      ColumnInfo = HrJetOpenTable(v35, v36, L"IndexCatalog", v39, pvData, 0, &v99);
                      if ( ColumnInfo >= 0 )
                      {
                        ColumnInfo = HrJetSetCurrentIndex2(v35, v99, L"indicesById", 0);
                        if ( ColumnInfo < 0
                          || (ColumnInfo = HrJetMakeKey(v35, v99, &tableid, 8u, 1u), ColumnInfo < 0)
                          || (ColumnInfo = HrJetSeek(v35, v99, 1u), ColumnInfo < 0) )
                        {
                          CloseTableIfNecessary(v35, &v99, ColumnInfo);
                        }
                      }
                      if ( ColumnInfo < 0 )
                        goto LABEL_165;
                      v70 = v99;
                      v131.columnid = v38[134];
                      v132 = v38[141];
                      v138 = v38[148];
                      v139 = &v98;
                      v144 = v38[120];
                      p_tableid = &tableid;
                      v150 = v38[155];
                      v151 = &v105;
                      v96 = 0;
                      v97 = 0;
                      v95[0] = 0;
                      v98 = 0;
                      tableid = 0;
                      v105 = 0;
                      memset(&v131.pvData, 0, 24);
                      *(_QWORD *)&v131.itagSequence = 1;
                      v131.err = 0;
                      v133 = 0;
                      v134 = 0;
                      v135 = 0;
                      v136 = 1;
                      v137 = 0;
                      v140 = 4;
                      v141 = 0;
                      v142 = 1;
                      v143 = 0;
                      v146 = 8;
                      v147 = 0;
                      v148 = 1;
                      v149 = 0;
                      v152 = 8;
                      v153 = 0;
                      v154 = 1;
                      v155 = 0;
                      ColumnInfo = HrJetRetrieveColumns(v35, v99, &v131, 5u, v95);
                      if ( ColumnInfo >= 0 && v95[0] )
                      {
                        for ( i = 0; i < 5; ++i )
                        {
                          if ( ColumnInfo < 0 )
                          {
                            v35 = v103;
                            goto LABEL_43;
                          }
                          if ( *(&v131.err + 12 * i) == 1006 )
                          {
                            v72 = MIDL_user_allocate(*(&v131.cbActual + 12 * i));
                            *((_QWORD *)&v131.pvData + 6 * i) = v72;
                            if ( v72 )
                            {
                              *(&v131.cbData + 12 * i) = *(&v131.cbActual + 12 * i);
                              *((_BYTE *)&v96 + i) = 1;
                            }
                            else
                            {
                              ColumnInfo = -2147024882;
                            }
                          }
                        }
                        v35 = v103;
                        if ( ColumnInfo >= 0 )
                          ColumnInfo = HrJetRetrieveColumns(v103, v70, &v131, 5u, v95);
LABEL_43:
                        v38 = v104;
                      }
                      v45 = v124;
                      if ( ColumnInfo >= 0 )
                      {
                        v46 = v129;
                        v92 = HIDWORD(v134) >> 1;
                        pvData = (unsigned int)v131.pvData;
                        ColumnInfo = CEseLayerIndexSchema::Init(v129, v124, v122, v131.cbActual >> 1);
                        if ( ColumnInfo >= 0 )
                        {
                          *(_QWORD *)&v108.columnid = pszDest;
                          v108.pvData = (char *)v46 + 88;
                          *(_QWORD *)&v108.cbData = (char *)v46 + 216;
                          *(_QWORD *)&v108.grbit = pszDest;
                          *(_QWORD *)&v108.itagSequence = (char *)v46 + 244;
                          *(_QWORD *)&v108.err = (char *)v46 + 372;
                          v109 = pszDest;
                          v110 = (__int64 *)((char *)v46 + 400);
                          v111 = (__int64)v46 + 528;
                          v112 = pszDest;
                          v113 = (__int64)v46 + 556;
                          v114 = (char *)v46 + 684;
                          v115 = pszDest;
                          v116 = (_QWORD *)((char *)v46 + 840);
                          v117 = (_QWORD *)((char *)v46 + 968);
                          for ( j = 0; j < 5; ++j )
                          {
                            v48 = (const unsigned __int16 *)*((_QWORD *)&v108.pvData + 3 * (int)j);
                            v49 = (const unsigned __int16 *)*((_QWORD *)&v108.columnid + 3 * (int)j);
                            v88 = (struct JET_COLUMNDEF *)*((_QWORD *)&v108.cbData + 3 * (int)j);
                            v88->cbStruct = 28;
                            ColumnInfo = HrJetGetColumnInfo(v35, v36, v49, v48, v88, 0x1Cu, v92);
                            if ( ColumnInfo < 0 )
                              break;
                          }
                        }
                      }
                      if ( (_BYTE)v96 )
                      {
                        if ( v131.pvData )
                        {
                          if ( g_fWxHeapExtensionInitialized )
                            g_WxHeapExtensionInterfaces(v131.pvData);
                          else
                            HeapFree(g_hWxProcessHeap, 0, v131.pvData);
                        }
                        v131.pvData = 0;
                      }
                      if ( BYTE1(v96) )
                      {
                        if ( v133 )
                        {
                          if ( g_fWxHeapExtensionInitialized )
                            g_WxHeapExtensionInterfaces(v133);
                          else
                            HeapFree(g_hWxProcessHeap, 0, v133);
                        }
                        v133 = 0;
                      }
                      if ( BYTE2(v96) )
                      {
                        if ( v139 )
                        {
                          if ( g_fWxHeapExtensionInitialized )
                            g_WxHeapExtensionInterfaces(v139);
                          else
                            HeapFree(g_hWxProcessHeap, 0, v139);
                        }
                        v139 = 0;
                      }
                      if ( HIBYTE(v96) )
                      {
                        if ( p_tableid )
                        {
                          if ( g_fWxHeapExtensionInitialized )
                            g_WxHeapExtensionInterfaces(p_tableid);
                          else
                            HeapFree(g_hWxProcessHeap, 0, p_tableid);
                        }
                        p_tableid = 0;
                      }
                      if ( v97 && v151 )
                      {
                        if ( g_fWxHeapExtensionInitialized )
                          g_WxHeapExtensionInterfaces(v151);
                        else
                          HeapFree(g_hWxProcessHeap, 0, v151);
                      }
                      if ( v99 != -1 )
                        HrJetCloseTable(v35, v99);
                      if ( ColumnInfo < 0 )
                      {
LABEL_165:
                        v32 = v106;
                      }
                      else
                      {
                        v50 = v129;
                        v51 = v106;
                        v52 = *(_QWORD *)v106;
                        *(_QWORD *)v129 = *(_QWORD *)v106;
                        *((_QWORD *)v50 + 1) = v51;
                        *(_QWORD *)(v52 + 8) = v50;
                        **((_QWORD **)v50 + 1) = v50;
                        ColumnInfo = HrJetSetCurrentIndex2(v35, v100, L"indicesByName", 0);
                        if ( ColumnInfo < 0 || (ColumnInfo = HrJetMakeKey(v35, v100, &v119, 8u, 1u), ColumnInfo < 0) )
                        {
                          v32 = v51;
                        }
                        else
                        {
                          ColumnInfo = HrJetSeek(v35, v100, 8u);
                          if ( ColumnInfo >= 0 )
                          {
                            do
                            {
                              v108.columnid = v38[127];
                              v119 = 0;
                              v108.pvData = &v119;
                              LODWORD(v109) = v38[120];
                              v110 = (__int64 *)&v120;
                              v120 = 0;
                              *(_QWORD *)&v108.grbit = 0;
                              v108.err = 0;
                              v112 = 0;
                              LODWORD(v114) = 0;
                              v95[0] = 0;
                              *(_QWORD *)&v108.cbData = 8;
                              *(_QWORD *)&v108.itagSequence = 1;
                              v111 = 8;
                              v113 = 1;
                              ColumnInfo = HrJetRetrieveColumns(v35, v100, &v108, 2u, v95);
                              if ( v45 != v120 )
                              {
                                if ( v122 != v119 )
                                  break;
                                v125 = (CEseLayerIndexSchema *)operator new(0x400u);
                                v105 = (JET_TABLEID)CEseLayerIndexSchema::CEseLayerIndexSchema(v125);
                                v54 = (__int64 *)v105;
                                if ( v105 && ColumnInfo >= 0 )
                                {
                                  v55 = v120;
                                  v56 = 0;
                                  tableid = v120;
                                  v99 = -1;
                                  v58 = HrJetOpenTable(v35, v36, L"IndexCatalog", v53, pvData, 0, &v99);
                                  if ( v58 >= 0 )
                                  {
                                    v58 = HrJetSetCurrentIndex2(v35, v99, L"indicesById", 0);
                                    if ( v58 < 0
                                      || (v58 = HrJetMakeKey(v35, v99, &tableid, 8u, 1u), v58 < 0)
                                      || (v58 = HrJetSeek(v35, v99, 1u), v58 < 0) )
                                    {
                                      CloseTableIfNecessary(v35, &v99, v58);
                                    }
                                  }
                                  if ( v58 < 0 )
                                    goto LABEL_92;
                                  v60 = v99;
                                  v98 = 0;
                                  v125 = 0;
                                  v131.columnid = v104[134];
                                  v132 = v104[141];
                                  v138 = v104[148];
                                  v139 = &v98;
                                  v144 = v104[120];
                                  p_tableid = &v125;
                                  v150 = v104[155];
                                  v151 = &tableid;
                                  v96 = 0;
                                  v97 = 0;
                                  v95[0] = 0;
                                  tableid = 0;
                                  memset(&v131.pvData, 0, 24);
                                  *(_QWORD *)&v131.itagSequence = 1;
                                  v131.err = 0;
                                  v133 = 0;
                                  v134 = 0;
                                  v135 = 0;
                                  v136 = 1;
                                  v137 = 0;
                                  v140 = 4;
                                  v141 = 0;
                                  v142 = 1;
                                  v143 = 0;
                                  v146 = 8;
                                  v147 = 0;
                                  v148 = 1;
                                  v149 = 0;
                                  v152 = 8;
                                  v153 = 0;
                                  v154 = 1;
                                  v155 = 0;
                                  v61 = HrJetRetrieveColumns(v103, v99, &v131, 5u, v95);
                                  if ( v61 >= 0 && v95[0] )
                                  {
                                    while ( v61 >= 0 )
                                    {
                                      if ( *(&v131.err + 12 * v56) == 1006 )
                                      {
                                        v68 = MIDL_user_allocate(*(&v131.cbActual + 12 * v56));
                                        *((_QWORD *)&v131.pvData + 6 * v56) = v68;
                                        if ( v68 )
                                        {
                                          *(&v131.cbData + 12 * v56) = *(&v131.cbActual + 12 * v56);
                                          *((_BYTE *)&v96 + v56) = 1;
                                        }
                                        else
                                        {
                                          v61 = -2147024882;
                                        }
                                      }
                                      if ( ++v56 >= 5 )
                                      {
                                        if ( v61 >= 0 )
                                        {
                                          v62 = v60;
                                          v35 = v103;
                                          v63 = HrJetRetrieveColumns(v103, v62, &v131, 5u, v95);
                                          v54 = (__int64 *)v105;
                                          v61 = v63;
                                          goto LABEL_107;
                                        }
                                        break;
                                      }
                                    }
                                    v54 = (__int64 *)v105;
                                  }
                                  v35 = v103;
LABEL_107:
                                  if ( v61 >= 0 )
                                  {
                                    v93 = HIDWORD(v134) >> 1;
                                    pvData = (unsigned int)v131.pvData;
                                    v61 = CEseLayerIndexSchema::Init(v54, v55, v122, v131.cbActual >> 1);
                                    if ( v61 >= 0 )
                                    {
                                      v64 = 0;
                                      v65 = v118;
                                      *(_QWORD *)&v108.columnid = pszDest;
                                      v108.pvData = v54 + 11;
                                      *(_QWORD *)&v108.cbData = v54 + 27;
                                      *(_QWORD *)&v108.grbit = pszDest;
                                      *(_QWORD *)&v108.itagSequence = (char *)v54 + 244;
                                      *(_QWORD *)&v108.err = (char *)v54 + 372;
                                      v109 = pszDest;
                                      v110 = v54 + 50;
                                      v111 = (__int64)(v54 + 66);
                                      v112 = pszDest;
                                      v113 = (__int64)v54 + 556;
                                      v114 = (char *)v54 + 684;
                                      v115 = pszDest;
                                      v116 = v54 + 105;
                                      v117 = v54 + 121;
                                      do
                                      {
                                        v66 = (const unsigned __int16 *)*((_QWORD *)&v108.pvData + 3 * (int)v64);
                                        v67 = (const unsigned __int16 *)*((_QWORD *)&v108.columnid + 3 * (int)v64);
                                        v89 = (struct JET_COLUMNDEF *)*((_QWORD *)&v108.cbData + 3 * (int)v64);
                                        v89->cbStruct = 28;
                                        v61 = HrJetGetColumnInfo(v35, v65, v67, v66, v89, 0x1Cu, v93);
                                        if ( v61 < 0 )
                                          break;
                                        ++v64;
                                      }
                                      while ( v64 < 5 );
                                    }
                                  }
                                  if ( (_BYTE)v96 )
                                  {
                                    if ( v131.pvData )
                                    {
                                      if ( g_fWxHeapExtensionInitialized )
                                        g_WxHeapExtensionInterfaces(v131.pvData);
                                      else
                                        HeapFree(g_hWxProcessHeap, 0, v131.pvData);
                                    }
                                    v131.pvData = 0;
                                  }
                                  if ( BYTE1(v96) )
                                  {
                                    if ( v133 )
                                    {
                                      if ( g_fWxHeapExtensionInitialized )
                                        g_WxHeapExtensionInterfaces(v133);
                                      else
                                        HeapFree(g_hWxProcessHeap, 0, v133);
                                    }
                                    v133 = 0;
                                  }
                                  if ( BYTE2(v96) )
                                  {
                                    if ( v139 )
                                    {
                                      if ( g_fWxHeapExtensionInitialized )
                                        g_WxHeapExtensionInterfaces(v139);
                                      else
                                        HeapFree(g_hWxProcessHeap, 0, v139);
                                    }
                                    v139 = 0;
                                  }
                                  if ( HIBYTE(v96) )
                                  {
                                    if ( p_tableid )
                                    {
                                      if ( g_fWxHeapExtensionInitialized )
                                        g_WxHeapExtensionInterfaces(p_tableid);
                                      else
                                        HeapFree(g_hWxProcessHeap, 0, p_tableid);
                                    }
                                    p_tableid = 0;
                                  }
                                  if ( v97 && v151 )
                                  {
                                    if ( g_fWxHeapExtensionInitialized )
                                      g_WxHeapExtensionInterfaces(v151);
                                    else
                                      HeapFree(g_hWxProcessHeap, 0, v151);
                                  }
                                  v57 = v99;
                                  if ( v99 != -1 )
                                    HrJetCloseTable(v35, v99);
                                  if ( v61 >= 0 )
                                  {
                                    v69 = v106;
                                    *v54 = (__int64)v106;
                                    v54[1] = *((_QWORD *)v69 + 1);
                                    *((_QWORD *)v69 + 1) = v54;
                                    *(_QWORD *)v54[1] = v54;
                                  }
                                  else
                                  {
LABEL_92:
                                    CEseLayerIndexSchema::`scalar deleting destructor'((CEseLayerIndexSchema *)v54, v57);
                                  }
                                  v45 = v124;
                                }
                                v38 = v104;
                              }
                              v59 = HrJetMove(v35, v100, 1, 0);
                              v36 = v118;
                              ColumnInfo = v59;
                            }
                            while ( v59 >= 0 );
                          }
                          v32 = v106;
                          if ( ColumnInfo == -1906378307 )
                            ColumnInfo = 0;
                        }
                      }
                    }
                    v40 = v100;
                    if ( v100 != -1 && (int)HrJetCloseTable(v35, v100) >= 0 )
                      v100 = -1;
                    v34 = v107;
                    v31 = v121;
                    if ( ColumnInfo < 0 )
LABEL_40:
                      CDoubleLink<CEseLayerIndexSchema,&int CEseLayerIndexSchema_GetCIndexSchemaLink_lnkOffset(void)>::CList::RemoveAndDeleteAll(v32);
                    v29 = v130;
                    Key = ColumnInfo;
                    v41 = v122;
                  }
                  else
                  {
                    v94 = (__int64)v26;
                    v34 = v107;
                    v41 = v122;
                    Key = CreateNewObjectStoreTableAndPrimaryIndex(
                            *(_QWORD *)(v107 + 24),
                            v122,
                            (__int64)&v128,
                            a5,
                            (__int64)a6,
                            a7,
                            (__int64)(v27 + 24),
                            v94,
                            (__int64)a10);
                    if ( Key < 0 )
                    {
LABEL_28:
                      if ( *v29 )
                        CEseLayerObjectStore::`scalar deleting destructor'(*v29, v40);
                      v42 = v129;
                      *v29 = 0;
                      CEseLayerIndexSchema::`scalar deleting destructor'(v42, v40);
                      v14 = v101;
                      goto LABEL_187;
                    }
                    Key = UpdateDosCatalogWithPseudoPrimaryIndexId(
                            *(_QWORD *)(v34 + 24),
                            v24,
                            v84,
                            v128,
                            *((struct CEseLayerDatabaseSchema **)v31 + 1),
                            a10);
                  }
                  if ( Key >= 0 )
                  {
                    v73 = *((_QWORD *)v31 + 1);
                    v74 = *(_QWORD *)v31;
                    v75 = *v29;
                    *((_QWORD *)v75 + 6) = v34;
                    *(_QWORD *)v75 = v74;
                    *((_QWORD *)v75 + 1) = v31;
                    *((_QWORD *)v75 + 2) = v73;
                    *((_QWORD *)v75 + 23) = v41;
                    v76 = *(_DWORD *)(v34 + 12);
                    if ( v76 != GetCurrentThreadId() )
                      wil::details::in1diag3::_FailFast_Unexpected(
                        retaddr,
                        (void *)0xB5,
                        (unsigned int)"onecoreuap\\inetcore\\webplatstorageserver\\indexeddbv1\\ese\\transaction.cxx",
                        v77);
                    v78 = *(_QWORD *)(v34 + 24);
                    v79 = *(_DWORD *)(v34 + 32);
                    v107 = -1;
                    Key = HrJetOpenTable(v78, v79, L"HeaderTable", v77, pvData, 0, &v107);
                    if ( Key >= 0 )
                    {
                      v105 = -1;
                      Key = HrJetOpenTable(v78, v79, L"DatabaseAndObjectStoreCatalog", v80, v90, 0, &v105);
                      if ( Key >= 0 )
                      {
                        Key = StringCchPrintfW((STRSAFE_LPWSTR)v75 + 28, 0x40u, L"T-%I64x", *((_QWORD *)v75 + 23));
                        if ( Key >= 0 )
                        {
                          tableid = -1;
                          Key = HrJetOpenTable(v78, v79, (const unsigned __int16 *)v75 + 28, v81, v91, 0, &tableid);
                          if ( tableid != -1 )
                            JetCloseTable(v78, tableid);
                        }
                      }
                      if ( v105 != -1 )
                        JetCloseTable(v78, v105);
                    }
                    v40 = v107;
                    if ( v107 != -1 )
                      JetCloseTable(v78, v107);
                    if ( Key >= 0 )
                    {
                      v14 = v101;
                      Key = HrJetCommitTransaction(v101, 1u);
                      if ( Key >= 0 )
                      {
                        v43 = 0;
LABEL_34:
                        v18 = v123;
                        if ( v123 != -1 && (int)HrJetCloseTable(v14, v123) >= 0 )
                          v123 = -1;
                        if ( !v43 )
                          return (unsigned int)Key;
LABEL_194:
                        HrJetRollback(v14, v18);
                        return (unsigned int)Key;
                      }
                      goto LABEL_187;
                    }
                  }
                  goto LABEL_28;
                }
                Key = -2147024882;
              }
LABEL_187:
              v83 = v130;
              if ( *v130 )
                CEseLayerObjectStore::`scalar deleting destructor'(*v130, v25);
              *v83 = 0;
              goto LABEL_190;
            }
          }
          else if ( v21 >= 0 )
          {
            v108.columnid = v20[50];
            *(_QWORD *)&v108.grbit = 0;
            v108.pvData = &v127;
            v22 = v20[113];
            v14 = v101;
            LODWORD(v109) = v22;
            v110 = &v126;
            v108.err = 0;
            v112 = 0;
            LODWORD(v114) = 0;
            v95[0] = 0;
            *(_QWORD *)&v108.cbData = 8;
            *(_QWORD *)&v108.itagSequence = 1;
            v111 = 8;
            v113 = 1;
            Key = HrJetRetrieveColumns(v101, v19, &v108, 2u, v95);
            goto LABEL_10;
          }
        }
      }
    }
    v14 = v101;
    goto LABEL_10;
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x1800107e0  push    rbp
0x1800107e2  push    rbx
0x1800107e3  push    rsi
0x1800107e4  push    rdi
0x1800107e5  push    r12
0x1800107e7  push    r14
0x1800107e9  lea     rbp, [rsp-248h]
0x1800107f1  sub     rsp, 348h
0x1800107f8  mov     rax, cs:__security_cookie
0x1800107ff  xor     rax, rsp
0x180010802  mov     [rbp+270h+var_50], rax
0x180010809  mov     rax, [rbp+270h+arg_40]
0x180010810  mov     rsi, r9
0x180010813  mov     r12, [rbp+270h+arg_28]
0x18001081a  mov     edi, r8d
0x18001081d  mov     r14, [rbp+270h+arg_48]
0x180010824  mov     rbx, rdx
0x180010827  mov     [rbp+270h+var_1D0], rax
0x18001082e  mov     [rbp+270h+var_2B8], rdx
0x180010832  mov     [rbp+270h+var_218], rcx
0x180010836  call    cs:__imp_GetCurrentThreadId
0x18001083c  mov     rcx, [rbp+278h]; this
0x180010843  cmp     [rbx+0Ch], eax
0x180010846  jnz     loc_180011B7B
0x18001084c  mov     [rsp+370h+var_30], r13
0x180010854  mov     r13, [rbx+18h]
0x180010858  mov     ebx, [rbx+20h]
0x18001085b  mov     rcx, r13; unsigned __int64
0x18001085e  mov     [rsp+370h+var_38], r15
0x180010866  mov     [rbp+270h+var_2E8], r13
0x18001086a  call    ?HrJetBeginTransaction@@YAJ_K@Z; HrJetBeginTransaction(unsigned __int64)
0x18001086f  mov     r15d, eax
0x180010872  test    eax, eax
0x180010874  js      loc_180010CC1
0x18001087a  lea     rax, [rbp+270h+var_208]
0x18001087e  mov     [rbp+270h+var_208], 0FFFFFFFFFFFFFFFFh
0x180010886  mov     [rsp+370h+var_340], rax; JET_TABLEID *
0x18001088b  lea     r8, aDatabaseandobj; "DatabaseAndObjectStoreCatalog"
0x180010892  mov     edx, ebx; unsigned int
0x180010894  mov     [rsp+370h+var_348], 0; JET_GRBIT
0x18001089c  mov     rcx, r13; unsigned __int64
0x18001089f  call    ?HrJetOpenTable@@YAJ_KKPEBGPEBXKKPEA_K@Z; HrJetOpenTable(unsigned __int64,ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x1800108a4  mov     r15d, eax
0x1800108a7  test    eax, eax
0x1800108a9  js      loc_180011CB6
0x1800108af  mov     r13, [rbp+270h+var_218]
0x1800108b3  lea     r8, aObjectstorefin; "objectStoreFinder"
0x1800108ba  mov     rbx, [rbp+270h+var_208]
0x1800108be  mov     rcx, [rbp+270h+var_2E8]; unsigned __int64
0x1800108c2  mov     rdx, rbx; unsigned __int64
0x1800108c5  mov     eax, [r13+18h]
0x1800108c9  mov     r13, [r13+8]
0x1800108cd  mov     [rsp+370h+var_300], eax
0x1800108d1  xor     eax, eax
0x1800108d3  mov     [rbp+270h+var_1E8], rax
0x1800108da  mov     [rbp+270h+var_1F0], rax
0x1800108e1  call    ?HrJetSetCurrentIndex@@YAJ_K0PEBG@Z; HrJetSetCurrentIndex(unsigned __int64,unsigned __int64,ushort const *)
0x1800108e6  mov     r15d, eax
0x1800108e9  test    eax, eax
0x1800108eb  js      loc_180010CF3
0x1800108f1  mov     rcx, [rbp+270h+var_2E8]; unsigned __int64
0x1800108f5  lea     r8, [rsp+370h+var_300]; void *
0x1800108fa  mov     r9d, 4; unsigned int
0x180010900  mov     [rsp+370h+var_350], 1; JET_GRBIT
0x180010908  mov     rdx, rbx; unsigned __int64
0x18001090b  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180010910  mov     r15d, eax
0x180010913  test    eax, eax
0x180010915  js      loc_180010CF3
0x18001091b  mov     rcx, [rbp+270h+var_2E8]; unsigned __int64
0x18001091f  lea     r9d, [rdi+rdi]; unsigned int
0x180010923  mov     r8, rsi; void *
0x180010926  mov     [rsp+370h+var_350], 0; JET_GRBIT
0x18001092e  mov     rdx, rbx; unsigned __int64
0x180010931  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180010936  mov     r15d, eax
0x180010939  test    eax, eax
0x18001093b  js      loc_180010CF3
0x180010941  mov     rcx, [rbp+270h+var_2E8]; unsigned __int64
0x180010945  mov     r8d, 1; unsigned int
0x18001094b  mov     rdx, rbx; unsigned __int64
0x18001094e  call    ?HrJetSeek@@YAJ_K0K@Z; HrJetSeek(unsigned __int64,unsigned __int64,ulong)
0x180010953  mov     r15d, eax
0x180010956  cmp     eax, 8E5EF9BFh
0x18001095b  jz      loc_180011B8D
0x180010961  test    eax, eax
0x180010963  js      loc_180010CF3
0x180010969  mov     eax, [r13+0C8h]
0x180010970  lea     r8, [rbp+270h+var_2B0]; struct JET_RETRIEVECOLUMN *
0x180010974  xor     ecx, ecx
0x180010976  mov     [rbp+270h+var_2B0.columnid], eax
0x180010979  lea     rax, [rbp+270h+var_1E8]
0x180010980  mov     qword ptr [rbp+270h+var_2B0.grbit], rcx
0x180010984  mov     [rbp+270h+var_2B0.pvData], rax
0x180010988  mov     r9d, 2; unsigned int
0x18001098e  mov     eax, [r13+1C4h]
0x180010995  mov     rdx, rbx; unsigned __int64
0x180010998  mov     r13, [rbp+270h+var_2E8]
0x18001099c  mov     dword ptr [rbp+270h+var_280], eax
0x18001099f  lea     rax, [rbp+270h+var_1F0]
0x1800109a6  mov     [rbp+270h+var_278], rax
0x1800109aa  lea     rax, [rsp+370h+var_310]
0x1800109af  mov     [rbp+270h+var_2B0.err], ecx
0x1800109b2  mov     [rbp+270h+var_268], rcx
0x1800109b6  mov     dword ptr [rbp+270h+var_258], ecx
0x1800109b9  mov     [rsp+370h+var_310], cl
0x1800109bd  mov     rcx, r13; unsigned __int64
0x1800109c0  mov     qword ptr [rsp+370h+var_350], rax; unsigned int
0x1800109c5  mov     qword ptr [rbp+270h+var_2B0.cbData], 8
0x1800109cd  mov     qword ptr [rbp+270h+var_2B0.itagSequence], 1
0x1800109d5  mov     [rbp+270h+var_270], 8
0x1800109dd  mov     [rbp+270h+var_260], 1
0x1800109e5  call    ?HrJetRetrieveColumns@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@KPEA_N@Z; HrJetRetrieveColumns(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong,bool *)
0x1800109ea  mov     r15d, eax
0x1800109ed  test    r15d, r15d
0x1800109f0  js      loc_180011C09
0x1800109f6  xor     bl, bl
0x1800109f8  mov     rax, [rbp+270h+var_1F0]
0x1800109ff  lea     r8, aTI64x; "T-%I64x"
0x180010a06  mov     rdi, [rbp+270h+var_208]
0x180010a0a  lea     rcx, [rbp+270h+pszDest]; pszDest
0x180010a11  mov     [rbp+270h+var_1E0], rax
0x180010a18  mov     edx, 40h ; '@'; cchDest
0x180010a1d  mov     rax, [rbp+270h+var_1E8]
0x180010a24  mov     r9, rax
0x180010a27  mov     [rbp+270h+var_210], rax
0x180010a2b  call    StringCchPrintfW
0x180010a30  mov     r15d, eax
0x180010a33  test    eax, eax
0x180010a35  js      loc_180010C78
0x180010a3b  mov     ecx, 400h; Size
0x180010a40  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010a45  mov     rcx, rax; this
0x180010a48  mov     [rbp+270h+var_1F8], rax
0x180010a4c  call    ??0CEseLayerIndexSchema@@QEAA@XZ; CEseLayerIndexSchema::CEseLayerIndexSchema(void)
0x180010a51  mov     [rbp+270h+var_1D8], rax
0x180010a58  mov     rsi, rax
0x180010a5b  test    rax, rax
0x180010a5e  jz      loc_180011BE8
0x180010a64  mov     ecx, 0C0h; Size
0x180010a69  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010a6e  mov     r13, [rbp+270h+var_1D0]
0x180010a75  xor     edx, edx
0x180010a77  mov     [rbp+270h+var_1F8], rax
0x180010a7b  test    bl, bl
0x180010a7d  mov     rbx, [rbp+270h+var_218]
0x180010a81  mov     [rax], rdx
0x180010a84  lea     r15, [rax+18h]
0x180010a88  mov     [rax+8], rdx
0x180010a8c  mov     [rax+10h], rdx
0x180010a90  mov     [r15], r15
0x180010a93  mov     [r15+8], r15
0x180010a97  mov     [r15+10h], edx
0x180010a9b  mov     [rax+30h], rdx
0x180010a9f  mov     [rax+0B8h], rdx
0x180010aa6  mov     [rax+38h], dx
0x180010aaa  mov     [r13+0], rax
0x180010aae  mov     [rbp+270h+var_2C0], r15
0x180010ab2  jnz     loc_180011C10
0x180010ab8  mov     rcx, [rbx+8]
0x180010abc  lea     rax, [rbp+270h+var_2F0]
0x180010ac0  mov     r12, [rbp+270h+var_1E0]
0x180010ac7  lea     r8, aIndexcatalog; "IndexCatalog"
0x180010ace  mov     rsi, [rbp+270h+var_2B8]
0x180010ad2  mov     [rsp+370h+var_340], rax; JET_TABLEID *
0x180010ad7  mov     [rbp+270h+var_2D0], rcx
0x180010adb  mov     [rsp+370h+var_348], edx; JET_GRBIT
0x180010adf  mov     r14, [rsi+18h]
0x180010ae3  mov     r13d, [rsi+20h]
0x180010ae7  mov     rcx, r14; unsigned __int64
0x180010aea  mov     edx, r13d; unsigned int
0x180010aed  mov     [rbp+270h+var_200], r12
0x180010af1  mov     [rbp+270h+var_230], r13d
0x180010af5  mov     [rbp+270h+var_2D8], r14
0x180010af9  mov     [rbp+270h+tableid], r12
0x180010afd  mov     [rbp+270h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x180010b05  call    ?HrJetOpenTable@@YAJ_KKPEBGPEBXKKPEA_K@Z; HrJetOpenTable(unsigned __int64,ulong,ushort const *,void const *,ulong,ulong,unsigned __int64 *)
0x180010b0a  mov     edi, eax
0x180010b0c  test    eax, eax
0x180010b0e  js      short loc_180010B79
0x180010b10  mov     rdx, [rbp+270h+var_2F0]; unsigned __int64
0x180010b14  lea     r8, aIndicesbyid; "indicesById"
0x180010b1b  xor     r9d, r9d; unsigned int
0x180010b1e  mov     rcx, r14; unsigned __int64
0x180010b21  call    ?HrJetSetCurrentIndex2@@YAJ_K0PEBGK@Z; HrJetSetCurrentIndex2(unsigned __int64,unsigned __int64,ushort const *,ulong)
0x180010b26  mov     edi, eax
0x180010b28  test    eax, eax
0x180010b2a  js      short loc_180010B50
0x180010b2c  mov     rdx, [rbp+270h+var_2F0]; unsigned __int64
0x180010b30  lea     r8, [rbp+270h+tableid]; void *
0x180010b34  mov     r9d, 8; unsigned int
0x180010b3a  mov     [rsp+370h+var_350], 1; JET_GRBIT
0x180010b42  mov     rcx, r14; unsigned __int64
0x180010b45  call    ?HrJetMakeKey@@YAJ_K0PEBXKK@Z; HrJetMakeKey(unsigned __int64,unsigned __int64,void const *,ulong,ulong)
0x180010b4a  mov     edi, eax
0x180010b4c  test    eax, eax
0x180010b4e  jns     short loc_180010B61
0x180010b50  mov     r8d, edi; int
0x180010b53  lea     rdx, [rbp+270h+var_2F0]; unsigned __int64 *
0x180010b57  mov     rcx, r14; unsigned __int64
0x180010b5a  call    ?CloseTableIfNecessary@@YAJ_KPEA_KJ@Z; CloseTableIfNecessary(unsigned __int64,unsigned __int64 *,long)
0x180010b5f  jmp     short loc_180010B79
0x180010b61  mov     rdx, [rbp+270h+var_2F0]; unsigned __int64
0x180010b65  mov     r8d, 1; unsigned int
0x180010b6b  mov     rcx, r14; unsigned __int64
0x180010b6e  call    ?HrJetSeek@@YAJ_K0K@Z; HrJetSeek(unsigned __int64,unsigned __int64,ulong)
0x180010b73  mov     edi, eax
0x180010b75  test    eax, eax
0x180010b77  js      short loc_180010B50
0x180010b79  test    edi, edi
0x180010b7b  js      loc_180010CFC
0x180010b81  mov     rsi, [rbp+270h+var_2D0]
0x180010b85  lea     r8, [rbp+270h+var_2B0]; struct JET_RETRIEVECOLUMN *
0x180010b89  mov     rdx, [rbp+270h+var_2F0]; unsigned __int64
0x180010b8d  xor     ebx, ebx
0x180010b8f  mov     r9d, 2; unsigned int
0x180010b95  mov     [rbp+270h+var_228], rbx
0x180010b99  mov     rcx, r14; unsigned __int64
0x180010b9c  mov     [rbp+270h+var_220], rbx
0x180010ba0  mov     eax, [rsi+1FCh]
0x180010ba6  mov     [rbp+270h+var_2B0.columnid], eax
0x180010ba9  lea     rax, [rbp+270h+var_228]
0x180010bad  mov     [rbp+270h+var_2B0.pvData], rax
0x180010bb1  mov     eax, [rsi+1E0h]
0x180010bb7  mov     dword ptr [rbp+270h+var_280], eax
0x180010bba  lea     rax, [rbp+270h+var_220]
0x180010bbe  mov     [rbp+270h+var_278], rax
0x180010bc2  lea     rax, [rsp+370h+var_310]
0x180010bc7  mov     qword ptr [rsp+370h+var_350], rax; unsigned int
0x180010bcc  mov     qword ptr [rbp+270h+var_2B0.cbData], 8
0x180010bd4  mov     qword ptr [rbp+270h+var_2B0.grbit], rbx
0x180010bd8  mov     qword ptr [rbp+270h+var_2B0.itagSequence], 1
0x180010be0  mov     [rbp+270h+var_2B0.err], ebx
0x180010be3  mov     [rbp+270h+var_270], 8
0x180010beb  mov     [rbp+270h+var_268], rbx
0x180010bef  mov     [rbp+270h+var_260], 1
0x180010bf7  mov     dword ptr [rbp+270h+var_258], ebx
0x180010bfa  mov     [rsp+370h+var_310], bl
0x180010bfe  call    ?HrJetRetrieveColumns@@YAJ_K0PEAUJET_RETRIEVECOLUMN@@KPEA_N@Z; HrJetRetrieveColumns(unsigned __int64,unsigned __int64,JET_RETRIEVECOLUMN *,ulong,bool *)
0x180010c03  mov     edi, eax
0x180010c05  test    eax, eax
0x180010c07  jns     loc_1800119B2
0x180010c0d  mov     rdx, [rbp+270h+var_2F0]; unsigned __int64
0x180010c11  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180010c15  jz      short loc_180010C2B
0x180010c17  mov     rcx, r14; unsigned __int64
0x180010c1a  call    ?HrJetCloseTable@@YAJ_K0@Z; HrJetCloseTable(unsigned __int64,unsigned __int64)
0x180010c1f  test    eax, eax
0x180010c21  js      short loc_180010C2B
0x180010c23  mov     [rbp+270h+var_2F0], 0FFFFFFFFFFFFFFFFh
0x180010c2b  mov     rsi, [rbp+270h+var_2B8]
0x180010c2f  mov     rbx, [rbp+270h+var_218]
0x180010c33  test    edi, edi
0x180010c35  js      loc_180010CFC
0x180010c3b  mov     r13, [rbp+270h+var_1D0]
0x180010c42  mov     r15d, edi
0x180010c45  mov     r12, [rbp+270h+var_210]
0x180010c49  test    r15d, r15d
0x180010c4c  jns     loc_180011A44
0x180010c52  mov     rcx, [r13+0]; this
0x180010c56  test    rcx, rcx
0x180010c59  jz      short loc_180010C60
0x180010c5b  call    ??_GCEseLayerObjectStore@@QEAAPEAXI@Z; CEseLayerObjectStore::`scalar deleting destructor'(uint)
0x180010c60  mov     rcx, [rbp+270h+var_1D8]; this
0x180010c67  mov     qword ptr [r13+0], 0
0x180010c6f  call    ??_GCEseLayerIndexSchema@@QEAAPEAXI@Z; CEseLayerIndexSchema::`scalar deleting destructor'(uint)
0x180010c74  mov     r13, [rbp+270h+var_2E8]
0x180010c78  test    r15d, r15d
0x180010c7b  js      loc_180011BEE
0x180010c81  mov     edx, 1; unsigned int
0x180010c86  mov     rcx, r13; unsigned __int64
0x180010c89  call    ?HrJetCommitTransaction@@YAJ_KK@Z; HrJetCommitTransaction(unsigned __int64,ulong)
0x180010c8e  mov     r15d, eax
0x180010c91  test    eax, eax
0x180010c93  js      loc_180011BEE
0x180010c99  xor     bl, bl
0x180010c9b  mov     rdx, [rbp+270h+var_208]; unsigned __int64
0x180010c9f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180010ca3  jz      short loc_180010CB9
0x180010ca5  mov     rcx, r13; unsigned __int64
0x180010ca8  call    ?HrJetCloseTable@@YAJ_K0@Z; HrJetCloseTable(unsigned __int64,unsigned __int64)
0x180010cad  test    eax, eax
0x180010caf  js      short loc_180010CB9
0x180010cb1  mov     [rbp+270h+var_208], 0FFFFFFFFFFFFFFFFh
0x180010cb9  test    bl, bl
0x180010cbb  jnz     loc_180011CB6
0x180010cc1  mov     r13, [rsp+370h+var_30]
0x180010cc9  mov     eax, r15d
0x180010ccc  mov     r15, [rsp+370h+var_38]
0x180010cd4  mov     rcx, [rbp+270h+var_50]
0x180010cdb  xor     rcx, rsp; StackCookie
0x180010cde  call    __security_check_cookie
0x180010ce3  add     rsp, 348h
0x180010cea  pop     r14
0x180010cec  pop     r12
0x180010cee  pop     rdi
0x180010cef  pop     rsi
0x180010cf0  pop     rbx
0x180010cf1  pop     rbp
0x180010cf2  retn
  ... truncated ...
```
