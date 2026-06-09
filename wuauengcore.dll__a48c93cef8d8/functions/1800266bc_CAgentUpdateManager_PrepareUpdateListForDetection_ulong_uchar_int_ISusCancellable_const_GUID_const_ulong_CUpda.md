# CAgentUpdateManager::PrepareUpdateListForDetection(ulong,uchar *,int,ISusCancellable const *,_GUID const &,ulong,CUpdateDetectInfoList &,tagUpdateQueryBehavior,CatScanContext *,ulong,tagDSFilterIdGroup const *,CUpdateToHwIdListMap *)

- ea: `0x1800266bc`
- end: `0x1800275f2`
- name: `?PrepareUpdateListForDetection@CAgentUpdateManager@@AEAAJKPEAEHPEBUISusCancellable@@AEBU_GUID@@KAEAVCUpdateDetectInfoList@@W4tagUpdateQueryBehavior@@PEAVCatScanContext@@KPEBUtagDSFilterIdGroup@@PEAVCUpdateToHwIdListMap@@@Z`
- size: `3894`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18002532c`
- `0x18002e560`
- `0x180031980`

## callees

- `0x18000def4`
- `0x18001d708`
- `0x1800263a0`
- `0x1800266bc`
- `0x180033f38`
- `0x1800341a4`
- `0x180034324`
- `0x1800351f4`
- `0x1800358a8`
- `0x180038254`
- `0x18003a9d0`
- `0x18003aa98`
- `0x18003abc0`
- `0x18003acc8`
- `0x18003ad58`
- `0x18003ae60`
- `0x18003b104`
- `0x18003b1e8`
- `0x18003b2e4`
- `0x18003b350`
- `0x18003b3d0`
- `0x18003ba00`
- `0x18003baf4`
- `0x1800666b4`
- `0x1800672a0`
- `0x180113ae8`
- `0x180113b9c`
- `0x180113c50`
- `0x180133a10`
- `0x1801821d8`
- `0x1802388b4`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800273d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800268be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002729f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002759c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800268be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026c2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180026f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002729f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800272b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002759c`

## string_xrefs

- `0x18002683d`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x180026865`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x18002688a`: `C:\__w\1\s\src\Client\Engine\Agent\updatemanager.cpp`
- `0x18002747e`: `C:\__w\1\s\src\Client\Engine\Agent\UpdateDetectInfoList.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
__int64 __fastcall CAgentUpdateManager::PrepareUpdateListForDetection(
        CAgentUpdateManager *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        unsigned int (__fastcall ***a5)(_QWORD),
        struct _GUID *a6,
        unsigned int a7,
        __int64 a8,
        __int64 a9,
        unsigned int *a10,
        unsigned int a11,
        __int64 a12,
        __int64 a13)
{
  unsigned int (__fastcall ***v14)(_QWORD); // r15
  const struct _GUID *v15; // r12
  _DWORD *v16; // rdi
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, struct ISusEseSession **); // rsi
  int refreshed; // eax
  signed int v20; // esi
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned int *v23; // r8
  struct ISusEseSession *v24; // rbx
  __int64 (__fastcall *v25)(struct ISusEseSession *, struct _GUID *, _QWORD, __int64); // rsi
  int v26; // eax
  unsigned __int64 v27; // r9
  __int64 v28; // r15
  unsigned int v29; // ebx
  unsigned __int64 v30; // rsi
  __int64 v31; // rdx
  unsigned int v32; // ecx
  unsigned int *v33; // rax
  __int64 v34; // r15
  unsigned __int64 v35; // r13
  __int64 v36; // r15
  char *v37; // rax
  unsigned int v38; // r12d
  __int64 v39; // rbx
  unsigned int v40; // eax
  __int64 v41; // rbx
  char *j; // rax
  int v43; // eax
  struct ISusEseSession *v44; // rbx
  __int64 (__fastcall *v45)(struct ISusEseSession *, struct _GUID *, __int64, __int64); // rsi
  __int64 v46; // r8
  int v47; // eax
  unsigned int k; // ebx
  int v49; // eax
  __int64 v50; // rbx
  unsigned int v51; // r15d
  __int64 v52; // r9
  __int64 v53; // rax
  unsigned int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // r9
  __int64 v57; // r8
  int v58; // ecx
  __int64 v59; // rdx
  _DWORD *v60; // rax
  int v61; // ecx
  _DWORD *v62; // rax
  __int64 i; // r9
  __int64 v64; // r8
  int v65; // edx
  unsigned __int64 v66; // rbx
  __int64 v67; // rbx
  __int64 v68; // r15
  unsigned int IndexOf; // eax
  __int64 v70; // rsi
  unsigned int (__fastcall ***v71)(_QWORD); // r15
  void *v72; // r12
  LPVOID *v73; // r15
  __int64 v74; // r13
  unsigned int (__fastcall **v75)(_QWORD); // rcx
  int v76; // eax
  CAgentUpdateManager *v77; // rsi
  struct _RTL_CRITICAL_SECTION *v78; // rbx
  unsigned int v79; // r15d
  unsigned int v80; // r12d
  __int64 v81; // r13
  char *v82; // rsi
  __int64 v83; // rsi
  void *v84; // rcx
  int v85; // r8d
  unsigned int *v87; // [rsp+20h] [rbp-E0h]
  unsigned int v88; // [rsp+50h] [rbp-B0h]
  __int64 v90; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID *v91; // [rsp+60h] [rbp-A0h]
  int v92; // [rsp+68h] [rbp-98h]
  unsigned int (__fastcall ***v93)(_QWORD); // [rsp+70h] [rbp-90h]
  __int128 v94; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v95[24]; // [rsp+88h] [rbp-78h] BYREF
  int v96; // [rsp+A0h] [rbp-60h]
  CAgentUpdateManager *v97; // [rsp+A8h] [rbp-58h]
  __int64 v98; // [rsp+B0h] [rbp-50h]
  __int64 v99; // [rsp+B8h] [rbp-48h]
  _DWORD *v100; // [rsp+C0h] [rbp-40h]
  __int64 v101; // [rsp+C8h] [rbp-38h]
  __int64 v102; // [rsp+D0h] [rbp-30h]
  struct tagDSUpdateMetadata **v103; // [rsp+D8h] [rbp-28h]
  unsigned int *v104; // [rsp+E0h] [rbp-20h]
  unsigned int **v105; // [rsp+E8h] [rbp-18h]
  void **p_lpMem; // [rsp+F0h] [rbp-10h]
  char v107; // [rsp+F8h] [rbp-8h]
  LPVOID v108[128]; // [rsp+100h] [rbp+0h] BYREF
  unsigned int *v109; // [rsp+500h] [rbp+400h] BYREF
  unsigned int v110[2]; // [rsp+508h] [rbp+408h] BYREF
  LPVOID pv; // [rsp+510h] [rbp+410h]
  void *lpMem; // [rsp+518h] [rbp+418h] BYREF
  struct tagDSUpdateMetadata *v113; // [rsp+520h] [rbp+420h] BYREF
  struct ISusEseSession *v114; // [rsp+528h] [rbp+428h] BYREF
  void *Base[2]; // [rsp+530h] [rbp+430h] BYREF
  size_t NumOfElements[2]; // [rsp+540h] [rbp+440h]
  __int64 v117; // [rsp+550h] [rbp+450h]
  void **v118; // [rsp+558h] [rbp+458h] BYREF
  __int64 v119; // [rsp+560h] [rbp+460h]
  __int128 v120; // [rsp+568h] [rbp+468h]
  void **v121; // [rsp+578h] [rbp+478h] BYREF
  __int64 v122; // [rsp+580h] [rbp+480h]
  __int128 v123; // [rsp+588h] [rbp+488h]
  wil::details::in1diag3 *retaddr; // [rsp+5D8h] [rbp+4D8h]

  v92 = a4;
  v90 = a3;
  v97 = a1;
  v14 = a5;
  v93 = a5;
  v15 = a6;
  v91 = a6;
  v102 = a8;
  v109 = a10;
  v99 = a12;
  v101 = a13;
  v114 = 0;
  pv = 0;
  v16 = 0;
  v100 = 0;
  v113 = 0;
  lpMem = 0;
  Base[1] = 0;
  NumOfElements[0] = 0;
  Base[0] = &CSusSortedArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::`vftable';
  NumOfElements[1] = 0;
  v117 = 0;
  v110[0] = 0;
  v103 = &v113;
  v104 = v110;
  v105 = &v109;
  p_lpMem = &lpMem;
  v107 = 1;
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::RemoveArraySection(
    a8,
    0,
    0xFFFFFFFFLL,
    1);
  v17 = *((_QWORD *)a1 + 281);
  v18 = *(__int64 (__fastcall **)(__int64, struct ISusEseSession **))(*(_QWORD *)v17 + 24LL);
  if ( v114 )
  {
    (*(void (__fastcall **)(struct ISusEseSession *))(*(_QWORD *)v114 + 16LL))(v114);
    v114 = 0;
  }
  refreshed = v18(v17, &v114);
  v20 = refreshed;
  if ( refreshed < 0 )
  {
    v21 = 4783;
LABEL_147:
    v27 = (unsigned int)refreshed;
    goto LABEL_148;
  }
  if ( a5 && (**a5)(a5) )
  {
    v22 = 4784;
    goto LABEL_8;
  }
  v23 = v109;
  if ( !v109 )
  {
    v24 = v114;
    v25 = *(__int64 (__fastcall **)(struct ISusEseSession *, struct _GUID *, _QWORD, __int64))(*(_QWORD *)v114 + 440LL);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v87 = v110;
    v26 = v25(v24, a6, a11, a12);
    v20 = v26;
    if ( v26 <= -2145091548 )
    {
      if ( (unsigned int)(v26 + 2145091552) > 4 && v26 != -2145091577 )
        goto LABEL_18;
      goto LABEL_21;
    }
    if ( (unsigned int)(v26 + 2145091547) <= 4 )
      goto LABEL_21;
    if ( v26 < 0 )
    {
LABEL_18:
      v27 = (unsigned int)v26;
      v21 = 4802;
      goto LABEL_148;
    }
    if ( !v110[0] || !pv )
    {
LABEL_21:
      v20 = 0;
      goto LABEL_160;
    }
LABEL_99:
    if ( !v110[0] || (v16 = SafeSusAllocArray(v110[0], 0x18u), v100 = v16, v20 = v16 == 0 ? 0x8007000E : 0, v16) )
    {
      for ( i = 0; (unsigned int)i < v110[0]; i = (unsigned int)(i + 1) )
      {
        v64 = 3 * i;
        v16[2 * v64] = 1;
        v65 = *((_DWORD *)pv + 12 * i + 9);
        *(_OWORD *)&v16[2 * v64 + 1] = *(_OWORD *)((char *)pv + 48 * i + 20);
        v16[2 * v64 + 5] = v65;
      }
      if ( v14 && (**v14)(v14) )
      {
        v22 = 4957;
        goto LABEL_8;
      }
      v66 = v110[0];
      if ( v113 )
      {
        SusFree(v113);
        v113 = 0;
      }
      if ( !v66
        || (v113 = (struct tagDSUpdateMetadata *)SafeSusAllocArray(v66, 0x280u), v20 = v113 == 0 ? 0x8007000E : 0, v113) )
      {
        LODWORD(v87) = 0;
        refreshed = (*(__int64 (__fastcall **)(struct ISusEseSession *, _QWORD, __int64, _QWORD))(*(_QWORD *)v114 + 208LL))(
                      v114,
                      a2,
                      v90,
                      a7);
        v20 = refreshed;
        if ( refreshed < 0 )
        {
          v21 = 4971;
          goto LABEL_147;
        }
        if ( !v14 || !(**v14)(v14) )
        {
          refreshed = CSusArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::Grow(
                        Base,
                        v110[0]);
          v20 = refreshed;
          if ( refreshed >= 0 )
          {
            v67 = 0;
            if ( v110[0] )
            {
              while ( 1 )
              {
                memset(v108, 0, sizeof(v108));
                CUpdateDetectInfo::CUpdateDetectInfo(
                  (CUpdateDetectInfo *)v108,
                  (const struct tagDSIdAndLeaf *)((char *)pv + 48 * v67),
                  (struct tagDSUpdateMetadata *)((char *)v113 + 640 * v67));
                if ( v92 )
                {
                  v68 = v101;
                  if ( v101 )
                  {
                    IndexOf = CSusMap<tagDSGlobalUpdateId,CUpdateHardwareIdList *,UpdateIdSortedArrayListOps,CSusArrayListItemOpDelete<CUpdateHardwareIdList *>>::GetIndexOf(
                                v101,
                                v108);
                    if ( IndexOf < *(_DWORD *)(v68 + 20) )
                    {
                      v70 = 4LL * IndexOf;
                      v71 = *(unsigned int (__fastcall ****)(_QWORD))(v68 + 8);
                      v93 = v71;
                      if ( v71[v70] )
                      {
                        v72 = v108[96];
                        if ( v108[96] && HIDWORD(v108[95]) )
                        {
                          v73 = (LPVOID *)v108[96];
                          v74 = HIDWORD(v108[95]);
                          do
                          {
                            if ( *v73 )
                              CoTaskMemFree(*v73);
                            ++v73;
                            --v74;
                          }
                          while ( v74 );
                          v71 = v93;
                          CoTaskMemFree(v72);
                        }
                        v75 = v71[v70];
                        v108[96] = v75[1];
                        HIDWORD(v108[95]) = *((_DWORD *)v75 + 5);
                        v75[1] = 0;
                        v75[2] = 0;
                      }
                    }
                  }
                }
                v76 = CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::AddUnsorted(
                        Base,
                        v108,
                        v108);
                if ( v76 < 0 )
                  break;
                v67 = (unsigned int)(v67 + 1);
                if ( (unsigned int)v67 >= v110[0] )
                  goto LABEL_139;
              }
              wil::details::in1diag3::Log_Hr(
                retaddr,
                (void *)0x139C,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
                (const char *)(unsigned int)v76,
                0);
LABEL_139:
              if ( (_DWORD)v67 )
              {
                memset(v113, 0, 640 * v67);
                if ( HIDWORD(NumOfElements[0]) > 1 )
                  qsort(
                    Base[1],
                    HIDWORD(NumOfElements[0]),
                    0x418u,
                    CSusSortedArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::CompareWeights);
              }
              v15 = v91;
            }
            refreshed = CUpdateDetectInfoList::RefreshDeploymentInfo((CUpdateDetectInfoList *)Base, v15, v114);
            v20 = refreshed;
            if ( refreshed >= 0 )
            {
              refreshed = CUpdateDetectInfoList::RefreshLatestRevisionNumbers((CUpdateDetectInfoList *)Base);
              v20 = refreshed;
              if ( refreshed >= 0 )
              {
                v90 = 0;
                v77 = v97;
                v78 = (struct _RTL_CRITICAL_SECTION *)((char *)v97 + 2616);
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)v97 + 2616));
                if ( (int)CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::get_Value(
                            &v78[1],
                            v15,
                            &v90) >= 0 )
                {
                  v79 = 0;
                  v80 = HIDWORD(NumOfElements[0]);
                  if ( HIDWORD(NumOfElements[0]) )
                  {
                    v81 = v90;
                    do
                    {
                      v82 = (char *)Base[1] + 1048 * v79;
                      *((_DWORD *)v82 + 229) = 2
                                             - ((unsigned int)CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::GetIndexOf(
                                                                v81,
                                                                v82) < *(_DWORD *)(v81 + 20));
                      ++v79;
                    }
                    while ( v79 < v80 );
                    v77 = v97;
                  }
                }
                v20 = CAgentUpdateManager::PopulateCUpdateDetectInfoAdditionalMetadata(
                        v77,
                        (struct CUpdateDetectInfoList *)Base);
                if ( v20 >= 0 )
                {
                  v83 = v102;
                  CSusArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::RemoveArraySection(
                    v102,
                    0,
                    0xFFFFFFFFLL,
                    1);
                  v84 = *(void **)(v83 + 8);
                  if ( v84 )
                    SusFree(v84);
                  *(void **)(v83 + 8) = Base[1];
                  Base[1] = 0;
                  *(_DWORD *)(v83 + 16) = NumOfElements[0];
                  LODWORD(NumOfElements[0]) = 0;
                  *(_DWORD *)(v83 + 20) = HIDWORD(NumOfElements[0]);
                  HIDWORD(NumOfElements[0]) = 0;
                  v20 = 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x13CD,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
                    (const char *)(unsigned int)v20,
                    (int)v87);
                }
                LeaveCriticalSection(v78);
                goto LABEL_160;
              }
              v21 = 5053;
            }
            else
            {
              v21 = 5048;
            }
          }
          else
          {
            v21 = 4978;
          }
          goto LABEL_147;
        }
        v22 = 4973;
LABEL_8:
        v20 = -2145124341;
        wil::details::in1diag3::Return_HrSuppressTelemetry(
          retaddr,
          (void *)v22,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
          (const char *)0x8024000BLL,
          (int)v87);
        goto LABEL_160;
      }
      v27 = (unsigned int)v20;
      v21 = 4962;
    }
    else
    {
      v27 = (unsigned int)v20;
      v21 = 4948;
    }
LABEL_148:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
      (const char *)v27,
      (int)v87);
    goto LABEL_160;
  }
  v28 = 0;
  v122 = 0;
  v123 = 0u;
  v29 = 0;
  v121 = &CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::`vftable';
  v119 = 0;
  v120 = 0u;
  v118 = &CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::`vftable';
  v30 = *v109;
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
    v23 = v109;
  }
  if ( v30 )
  {
    lpMem = SafeSusAllocArray(v30, 0x20u);
    v20 = lpMem == 0 ? 0x8007000E : 0;
    if ( !lpMem )
    {
      v31 = 4811;
      goto LABEL_103;
    }
    v23 = v109;
  }
  if ( *v23 != 1 && *v23 > a11 )
  {
    v20 = -2145120257;
    v31 = 4813;
    goto LABEL_103;
  }
  LODWORD(v87) = *v23;
  v20 = (*(__int64 (__fastcall **)(struct ISusEseSession *, _QWORD, __int64, struct _GUID *))(*(_QWORD *)v114 + 136LL))(
          v114,
          a2,
          v90,
          a6);
  if ( v20 < 0 )
  {
    v31 = 4820;
    goto LABEL_103;
  }
  v32 = 0;
  v88 = 0;
  v33 = v109;
  if ( !*v109 )
  {
LABEL_84:
    v110[0] = v29;
    if ( !v29 )
    {
      v20 = 0;
      goto LABEL_104;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    pv = SafeSusComAllocArray(v29, 0x30u);
    v20 = pv == 0 ? 0x8007000E : 0;
    if ( !pv )
    {
      v31 = 4934;
      goto LABEL_103;
    }
    v56 = 0;
    if ( v110[0] )
    {
      while ( (unsigned int)v56 < v29 )
      {
        v57 = v28 + 44LL * (unsigned int)v56;
        v58 = *(_DWORD *)(v57 + 16);
        v59 = 6 * v56;
        v60 = pv;
        *(_OWORD *)((char *)pv + 8 * v59) = *(_OWORD *)v57;
        v60[2 * v59 + 4] = v58;
        v61 = *(_DWORD *)(v57 + 36);
        v62 = pv;
        *(_OWORD *)((char *)pv + 8 * v59 + 20) = *(_OWORD *)(v57 + 20);
        v62[2 * v59 + 9] = v61;
        *((_DWORD *)pv + 2 * v59 + 10) = *(_DWORD *)(v57 + 40);
        v56 = (unsigned int)(v56 + 1);
        if ( (unsigned int)v56 >= v110[0] )
          goto LABEL_98;
      }
      v31 = 4939;
      v20 = -2145124345;
      goto LABEL_103;
    }
LABEL_98:
    CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::~CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>(&v118);
    CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::~CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>(&v121);
    v14 = v93;
    goto LABEL_99;
  }
  while ( 1 )
  {
    v34 = v32;
    v98 = v32;
    v35 = *((_QWORD *)v33 + 2) + ((unsigned __int64)v32 << 6);
    CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::RemoveArraySection(
      &v118,
      0,
      0xFFFFFFFFLL);
    v36 = 32 * v34;
    v37 = (char *)lpMem;
    if ( *(_DWORD *)((char *)lpMem + v36 + 8) )
    {
      v20 = CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Grow(v35);
      if ( v20 < 0 )
      {
        v31 = 4831;
        goto LABEL_103;
      }
      v38 = 0;
      v37 = (char *)lpMem;
      if ( *(_DWORD *)((char *)lpMem + v36 + 8) )
        break;
    }
LABEL_40:
    if ( *(_DWORD *)&v37[v36 + 24] )
    {
      v20 = CSusArrayList<SusWsStructs::SusUpdateIdentity,CSusArrayListItemOpSusServiceStruct<SusWsStructs::SusUpdateIdentity>>::Grow(v35 + 32);
      if ( v20 < 0 )
      {
        v31 = 4855;
        goto LABEL_103;
      }
      v41 = 0;
      for ( j = (char *)lpMem; (unsigned int)v41 < *(_DWORD *)((char *)lpMem + v36 + 24); j = (char *)lpMem )
      {
        v43 = CSusSortedArrayList<tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::Add(
                v35 + 32,
                *(_QWORD *)&j[v36 + 16] + 20 * v41,
                0);
        if ( v43 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x12FD,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
            (const char *)(unsigned int)v43,
            (int)v87);
        v41 = (unsigned int)(v41 + 1);
      }
    }
    v44 = v114;
    v45 = *(__int64 (__fastcall **)(struct ISusEseSession *, struct _GUID *, __int64, __int64))(*(_QWORD *)v114 + 440LL);
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v46 = 1;
    if ( *v109 == 1 )
      v46 = a11;
    v87 = v110;
    v15 = v91;
    v47 = v45(v44, v91, v46, v99 + 16 * v98);
    v20 = v47;
    if ( v47 >= 0 )
      goto LABEL_57;
    if ( v47 <= -2145091548 )
    {
      if ( (unsigned int)(v47 + 2145091552) > 4 && v47 != -2145091577 )
      {
LABEL_54:
        v31 = 4875;
        goto LABEL_103;
      }
      goto LABEL_82;
    }
    if ( (unsigned int)(v47 + 2145091547) > 3 )
    {
      if ( v47 != -2145091543 )
        goto LABEL_54;
LABEL_57:
      if ( (unsigned int)(v47 + 2145091552) > 9 && v110[0] && pv )
      {
        v20 = CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Grow(&v118);
        if ( v20 < 0 )
        {
          v31 = 4884;
          goto LABEL_103;
        }
        for ( k = 0; k < v110[0]; ++k )
        {
          memset(v95, 0, sizeof(v95));
          v94 = *((_OWORD *)pv + 3 * k);
          *(_DWORD *)v95 = *((_DWORD *)pv + 12 * k + 4);
          *(_OWORD *)&v95[4] = *(_OWORD *)((char *)pv + 48 * k + 20);
          *(_DWORD *)&v95[20] = *((_DWORD *)pv + 12 * k + 9);
          v96 = *((_DWORD *)pv + 12 * k + 10);
          v49 = CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Add(
                  &v118,
                  &v94,
                  0);
          if ( v49 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x131E,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
              (const char *)(unsigned int)v49,
              (int)v87);
        }
        LODWORD(v50) = *(_DWORD *)(v35 + 52);
LABEL_66:
        v51 = DWORD1(v120);
        while ( (_DWORD)v50 )
        {
          v50 = (unsigned int)(v50 - 1);
          v94 = 0;
          memset(v95, 0, sizeof(v95));
          v96 = 0;
          v52 = 0;
          if ( (unsigned int)v50 < *(_DWORD *)(v35 + 52) )
          {
            v53 = *(_QWORD *)(v35 + 40);
            v94 = *(_OWORD *)(v53 + 20 * v50);
            *(_DWORD *)v95 = *(_DWORD *)(v53 + 20 * v50 + 16);
          }
          else
          {
            v52 = 2149842951LL;
          }
          if ( (int)v52 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x132B,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
              (const char *)v52,
              (int)v87);
          v54 = CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::GetIndexOf(
                  &v118,
                  &v94);
          if ( v54 == v51 )
          {
            if ( (unsigned int)v50 < *(_DWORD *)(v35 + 52) )
              CSusArrayList<tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::RemoveArraySection(
                v35 + 32,
                (unsigned int)v50,
                (unsigned int)v50);
          }
          else if ( v54 < v51 )
          {
            CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::RemoveArraySection(
              &v118,
              v54,
              v54);
            goto LABEL_66;
          }
        }
        v55 = 0;
        if ( v51 )
        {
          while ( 1 )
          {
            v20 = CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Add(
                    &v121,
                    v119 + 44LL * v55,
                    1);
            if ( (int)(v20 + 0x80000000) >= 0 && v20 != -2145124333 )
              break;
            if ( ++v55 >= v51 )
              goto LABEL_82;
          }
          v31 = 4927;
          goto LABEL_103;
        }
      }
    }
LABEL_82:
    v32 = v88 + 1;
    v88 = v32;
    v33 = v109;
    if ( v32 >= *v109 )
    {
      v29 = DWORD1(v123);
      v28 = v122;
      goto LABEL_84;
    }
  }
  while ( 1 )
  {
    v39 = 44LL * v38;
    v40 = CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Add(
            v35,
            v39 + *(_QWORD *)&v37[v36],
            1);
    wil::details::in1diag3::Log_IfFailedWithExpected(
      retaddr,
      (void *)0x12E8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
      (const char *)v40,
      1,
      19);
    v20 = CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Add(
            &v121,
            v39 + *(_QWORD *)((char *)lpMem + v36),
            1);
    if ( (int)(v20 + 0x80000000) >= 0 && v20 != -2145124333 )
      break;
    ++v38;
    v37 = (char *)lpMem;
    if ( v38 >= *(_DWORD *)((char *)lpMem + v36 + 8) )
      goto LABEL_40;
  }
  v31 = 4848;
LABEL_103:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v31,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\updatemanager.cpp",
    (const char *)(unsigned int)v20,
    (int)v87);
LABEL_104:
  CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::~CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>(&v118);
  CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::~CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>(&v121);
LABEL_160:
  DsqFreeObject(v113, v110[0], 12207, 1);
  if ( v109 )
    DsqFreeObject((struct tagDSCatScanContext *)lpMem, *v109, v85);
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>(Base);
  if ( lpMem )
  {
    SusFree(lpMem);
    lpMem = 0;
  }
  if ( v113 )
  {
    SusFree(v113);
    v113 = 0;
  }
  if ( v16 )
    SusFree(v16);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v114 )
    (*(void (__fastcall **)(struct ISusEseSession *))(*(_QWORD *)v114 + 16LL))(v114);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x1800266bc  mov     [rsp-8+arg_18], rbx
0x1800266c1  push    rbp
0x1800266c2  push    rsi
0x1800266c3  push    rdi
0x1800266c4  push    r12
0x1800266c6  push    r13
0x1800266c8  push    r14
0x1800266ca  push    r15
0x1800266cc  lea     rbp, [rsp-4A0h]
0x1800266d4  sub     rsp, 5A0h
0x1800266db  mov     rax, cs:__security_cookie
0x1800266e2  xor     rax, rsp
0x1800266e5  mov     [rbp+4D0h+var_38], rax
0x1800266ec  mov     [rsp+5D0h+var_568], r9d
0x1800266f1  mov     [rsp+5D0h+var_578], r8
0x1800266f6  mov     [rsp+5D0h+var_57C], edx
0x1800266fa  mov     rbx, rcx
0x1800266fd  mov     [rbp+4D0h+var_528], rcx
0x180026701  mov     r15, [rbp+4D0h+arg_20]
0x180026708  mov     [rsp+5D0h+var_560], r15
0x18002670d  mov     r12, [rbp+4D0h+arg_28]
0x180026714  mov     [rsp+5D0h+var_570], r12
0x180026719  mov     rcx, [rbp+4D0h+arg_38]
0x180026720  mov     [rbp+4D0h+var_500], rcx
0x180026724  mov     rax, [rbp+4D0h+arg_48]
0x18002672b  mov     [rbp+4D0h+var_D0], rax
0x180026732  mov     r13, [rbp+4D0h+arg_58]
0x180026739  mov     [rbp+4D0h+var_518], r13
0x18002673d  mov     rax, [rbp+4D0h+arg_60]
0x180026744  mov     [rbp+4D0h+var_508], rax
0x180026748  xor     r14d, r14d
0x18002674b  mov     [rbp+4D0h+var_A8], r14
0x180026752  mov     [rbp+4D0h+pv], r14
0x180026759  mov     edi, r14d
0x18002675c  mov     [rbp+4D0h+var_510], r14
0x180026760  mov     [rbp+4D0h+var_B0], r14
0x180026767  mov     [rbp+4D0h+lpMem], r14
0x18002676e  xorps   xmm0, xmm0
0x180026771  xor     eax, eax
0x180026773  movups  xmmword ptr [rbp+4D0h+Base], xmm0
0x18002677a  movups  xmmword ptr [rbp+4D0h+NumOfElements], xmm0
0x180026781  mov     [rbp+4D0h+var_80], rax
0x180026788  mov     [rbp+4D0h+Base+8], r14
0x18002678f  mov     [rbp+4D0h+NumOfElements], r14
0x180026796  lea     rax, ??_7?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@VCUpdateDetectInfo@@V?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@V2@@@VCMapEntryOps@2@@@6B@; const CSusSortedArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::`vftable'
0x18002679d  mov     [rbp+4D0h+Base], rax
0x1800267a4  mov     dword ptr [rbp+4D0h+NumOfElements+8], r14d
0x1800267ab  mov     dword ptr [rbp+4D0h+var_80], r14d
0x1800267b2  mov     [rbp+4D0h+var_C8], r14d
0x1800267b9  lea     rax, [rbp+4D0h+var_B0]
0x1800267c0  mov     [rbp+4D0h+var_4F8], rax
0x1800267c4  lea     rax, [rbp+4D0h+var_C8]
0x1800267cb  mov     [rbp+4D0h+var_4F0], rax
0x1800267cf  lea     rax, [rbp+4D0h+var_D0]
0x1800267d6  mov     [rbp+4D0h+var_4E8], rax
0x1800267da  lea     rax, [rbp+4D0h+lpMem]
0x1800267e1  mov     [rbp+4D0h+var_4E0], rax
0x1800267e5  mov     [rbp+4D0h+var_4D8], 1
0x1800267e9  lea     r9d, [r14+1]
0x1800267ed  or      r8d, 0FFFFFFFFh
0x1800267f1  xor     edx, edx
0x1800267f3  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@VCUpdateDetectInfo@@V?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@V2@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CUpdateDetectInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CUpdateDetectInfo>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x1800267f8  mov     rbx, [rbx+8C8h]
0x1800267ff  mov     rax, [rbx]
0x180026802  mov     rsi, [rax+18h]
0x180026806  mov     rcx, [rbp+4D0h+var_A8]
0x18002680d  test    rcx, rcx
0x180026810  jz      short loc_180026825
0x180026812  mov     rax, [rcx]
0x180026815  mov     rax, [rax+10h]
0x180026819  call    _guard_dispatch_icall
0x18002681e  mov     [rbp+4D0h+var_A8], r14
0x180026825  lea     rdx, [rbp+4D0h+var_A8]
0x18002682c  mov     rcx, rbx
0x18002682f  mov     rax, rsi
0x180026832  call    _guard_dispatch_icall
0x180026837  mov     esi, eax
0x180026839  test    eax, eax
0x18002683b  jns     short loc_18002684E
0x18002683d  lea     r8, aCW1SSrcClientE_96; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180026844  mov     edx, 12AFh
0x180026849  jmp     loc_1800273A8
0x18002684e  test    r15, r15
0x180026851  jz      short loc_18002688A
0x180026853  mov     rax, [r15]
0x180026856  mov     rcx, r15
0x180026859  mov     rax, [rax]
0x18002685c  call    _guard_dispatch_icall
0x180026861  test    eax, eax
0x180026863  jz      short loc_18002688A
0x180026865  lea     r8, aCW1SSrcClientE_96; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18002686c  mov     edx, 12B0h; void *
0x180026871  mov     esi, 8024000Bh
0x180026876  mov     rcx, [rbp+4D8h]; this
0x18002687d  mov     r9d, esi; char *
0x180026880  call    ?Return_HrSuppressTelemetry@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_HrSuppressTelemetry(void *,uint,char const *,long)
0x180026885  jmp     loc_180027504
0x18002688a  lea     r14, aCW1SSrcClientE_96; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x180026891  mov     r8, [rbp+4D0h+var_D0]
0x180026898  test    r8, r8
0x18002689b  jnz     loc_180026962
0x1800268a1  mov     rbx, [rbp+4D0h+var_A8]
0x1800268a8  mov     rax, [rbx]
0x1800268ab  mov     rsi, [rax+1B8h]
0x1800268b2  mov     rcx, [rbp+4D0h+pv]; pv
0x1800268b9  test    rcx, rcx
0x1800268bc  jz      short loc_1800268CF
0x1800268be  call    cs:__imp_CoTaskMemFree
0x1800268c4  mov     [rbp+4D0h+pv], 0
0x1800268cf  mov     eax, [rbp+4D0h+arg_40]
0x1800268d5  mov     dword ptr [rsp+5D0h+var_5A0], eax
0x1800268d9  lea     rax, [rbp+4D0h+pv]
0x1800268e0  mov     qword ptr [rsp+5D0h+var_5A8], rax
0x1800268e5  lea     rax, [rbp+4D0h+var_C8]
0x1800268ec  mov     qword ptr [rsp+5D0h+var_5B0], rax
0x1800268f1  mov     r9, r13
0x1800268f4  mov     r8d, [rbp+4D0h+arg_50]
0x1800268fb  mov     rdx, r12
0x1800268fe  mov     rcx, rbx
0x180026901  mov     rax, rsi
0x180026904  call    _guard_dispatch_icall
0x180026909  mov     esi, eax
0x18002690b  cmp     eax, 80248024h
0x180026910  jg      short loc_180026926
0x180026912  add     eax, 7FDB7FE0h
0x180026917  cmp     eax, 4
0x18002691a  jbe     short loc_18002695B
0x18002691c  cmp     esi, 80248007h
0x180026922  jz      short loc_18002695B
0x180026924  jmp     short loc_180026934
0x180026926  add     eax, 7FDB7FDBh
0x18002692b  cmp     eax, 4
0x18002692e  jbe     short loc_18002695B
0x180026930  test    esi, esi
0x180026932  jns     short loc_180026944
0x180026934  mov     r9d, esi
0x180026937  mov     r8, r14
0x18002693a  mov     edx, 12C2h
0x18002693f  jmp     loc_1800273AB
0x180026944  cmp     [rbp+4D0h+var_C8], 0
0x18002694b  jz      short loc_18002695B
0x18002694d  cmp     [rbp+4D0h+pv], 0
0x180026955  jnz     loc_180027006
0x18002695b  xor     esi, esi
0x18002695d  jmp     loc_180027504
0x180026962  xorps   xmm0, xmm0
0x180026965  movups  [rbp+4D0h+var_58], xmm0
0x18002696c  movups  [rbp+4D0h+var_48], xmm0
0x180026973  xor     r15d, r15d
0x180026976  mov     qword ptr [rbp+4D0h+var_58+8], r15
0x18002697d  mov     qword ptr [rbp+4D0h+var_48], r15
0x180026984  xor     ebx, ebx
0x180026986  lea     rax, ??_7?$CSusSortedArrayList@UtagDSUpdateIdMap@@VCSusSortedArrayListItemOpsUpdateIdMapByGlobalId@@@@6B@; const CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::`vftable'
0x18002698d  mov     qword ptr [rbp+4D0h+var_58], rax
0x180026994  mov     dword ptr [rbp+4D0h+var_48+8], ebx
0x18002699a  movups  [rbp+4D0h+var_78], xmm0
0x1800269a1  movups  [rbp+4D0h+var_68], xmm0
0x1800269a8  mov     qword ptr [rbp+4D0h+var_78+8], rbx
0x1800269af  mov     qword ptr [rbp+4D0h+var_68], rbx
0x1800269b6  mov     qword ptr [rbp+4D0h+var_78], rax
0x1800269bd  mov     dword ptr [rbp+4D0h+var_68+8], ebx
0x1800269c3  mov     esi, [r8]
0x1800269c6  mov     rax, [rbp+4D0h+lpMem]
0x1800269cd  test    rax, rax
0x1800269d0  jz      short loc_1800269EA
0x1800269d2  mov     rcx, rax; lpMem
0x1800269d5  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800269da  xor     eax, eax
0x1800269dc  mov     [rbp+4D0h+lpMem], rax
0x1800269e3  mov     r8, [rbp+4D0h+var_D0]
0x1800269ea  test    rsi, rsi
0x1800269ed  jz      short loc_180026A29
0x1800269ef  mov     edx, 20h ; ' '; unsigned __int64
0x1800269f4  mov     rcx, rsi; unsigned __int64
0x1800269f7  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1800269fc  mov     [rbp+4D0h+lpMem], rax
0x180026a03  mov     rcx, rax
0x180026a06  neg     rcx
0x180026a09  sbb     esi, esi
0x180026a0b  not     esi
0x180026a0d  and     esi, 8007000Eh
0x180026a13  test    rax, rax
0x180026a16  jnz     short loc_180026A22
0x180026a18  mov     edx, 12CBh
0x180026a1d  jmp     loc_180027051
0x180026a22  mov     r8, [rbp+4D0h+var_D0]
0x180026a29  mov     r9d, [r8]
0x180026a2c  cmp     r9d, 1
0x180026a30  jz      short loc_180026A4A
0x180026a32  cmp     r9d, [rbp+4D0h+arg_50]
0x180026a39  jbe     short loc_180026A4A
0x180026a3b  mov     esi, 80240FFFh
0x180026a40  mov     edx, 12CDh
0x180026a45  jmp     loc_180027051
0x180026a4a  mov     rcx, [rbp+4D0h+var_A8]
0x180026a51  mov     rdx, [rcx]
0x180026a54  mov     r10, [rdx+88h]
0x180026a5b  mov     [rsp+5D0h+var_5A0], rax
0x180026a60  mov     rax, [r8+8]
0x180026a64  mov     qword ptr [rsp+5D0h+var_5A8], rax
0x180026a69  mov     [rsp+5D0h+var_5B0], r9d
0x180026a6e  mov     r9, r12
0x180026a71  mov     r8, [rsp+5D0h+var_578]
0x180026a76  mov     edx, [rsp+5D0h+var_57C]
0x180026a7a  mov     rax, r10
0x180026a7d  call    _guard_dispatch_icall
0x180026a82  mov     esi, eax
0x180026a84  test    eax, eax
0x180026a86  jns     short loc_180026A92
0x180026a88  mov     edx, 12D4h
0x180026a8d  jmp     loc_180027051
0x180026a92  xor     ecx, ecx
0x180026a94  mov     [rsp+5D0h+var_580], ecx
0x180026a98  mov     rax, [rbp+4D0h+var_D0]
0x180026a9f  cmp     [rax], ecx
0x180026aa1  jbe     loc_180026ED4
0x180026aa7  mov     r15d, ecx
0x180026aaa  mov     [rbp+4D0h+var_520], r15
0x180026aae  mov     r13d, ecx
0x180026ab1  shl     r13, 6
0x180026ab5  add     r13, [rax+10h]
0x180026ab9  or      r8d, 0FFFFFFFFh
0x180026abd  xor     edx, edx
0x180026abf  lea     rcx, [rbp+4D0h+var_78]
0x180026ac6  call    ?RemoveArraySection@?$CSusArrayList@UtagDSUpdateIdMap@@VCSusSortedArrayListItemOpsUpdateIdMapByGlobalId@@@@IEAAXKKH@Z; CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::RemoveArraySection(ulong,ulong,int)
0x180026acb  shl     r15, 5
0x180026acf  mov     rax, [rbp+4D0h+lpMem]
0x180026ad6  mov     edx, [r15+rax+8]
0x180026adb  test    edx, edx
0x180026add  jz      loc_180026B9B
0x180026ae3  mov     rcx, r13
0x180026ae6  call    ?Grow@?$CSusArrayList@UtagDSUpdateIdMap@@VCSusSortedArrayListItemOpsUpdateIdMapByGlobalId@@@@QEAAJK@Z; CSusArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Grow(ulong)
0x180026aeb  mov     esi, eax
0x180026aed  test    eax, eax
0x180026aef  js      loc_180026EEF
0x180026af5  xor     r12d, r12d
0x180026af8  mov     rax, [rbp+4D0h+lpMem]
0x180026aff  cmp     [r15+rax+8], r12d
0x180026b04  jbe     loc_180026B9B
0x180026b0a  mov     ecx, r12d
0x180026b0d  imul    rbx, rcx, 2Ch ; ','
0x180026b11  mov     rdx, [r15+rax]
0x180026b15  add     rdx, rbx
0x180026b18  mov     r8d, 1
0x180026b1e  mov     rcx, r13
0x180026b21  call    ?Add@?$CSusSortedArrayList@UtagDSUpdateIdMap@@VCSusSortedArrayListItemOpsUpdateIdMapByGlobalId@@@@QEAAJAEBUtagDSUpdateIdMap@@K@Z; CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Add(tagDSUpdateIdMap const &,ulong)
0x180026b26  mov     rcx, [rbp+4D8h]; this
0x180026b2d  mov     dword ptr [rsp+5D0h+var_5A8], 80240013h; char
0x180026b35  mov     [rsp+5D0h+var_5B0], 1; int
0x180026b3d  mov     r9d, eax; char *
0x180026b40  mov     r8, r14; unsigned int
0x180026b43  mov     edx, 12E8h; void *
0x180026b48  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x180026b4d  mov     rax, [rbp+4D0h+lpMem]
0x180026b54  mov     rdx, [r15+rax]
0x180026b58  add     rdx, rbx
0x180026b5b  mov     r8d, 1
0x180026b61  lea     rcx, [rbp+4D0h+var_58]
0x180026b68  call    ?Add@?$CSusSortedArrayList@UtagDSUpdateIdMap@@VCSusSortedArrayListItemOpsUpdateIdMapByGlobalId@@@@QEAAJAEBUtagDSUpdateIdMap@@K@Z; CSusSortedArrayList<tagDSUpdateIdMap,CSusSortedArrayListItemOpsUpdateIdMapByGlobalId>::Add(tagDSUpdateIdMap const &,ulong)
0x180026b6d  mov     esi, eax
0x180026b6f  mov     ebx, 80000000h
0x180026b74  add     eax, ebx
0x180026b76  test    ebx, eax
0x180026b78  jnz     short loc_180026B86
0x180026b7a  cmp     esi, 80240013h
0x180026b80  jnz     loc_180026EE5
0x180026b86  inc     r12d
0x180026b89  mov     rax, [rbp+4D0h+lpMem]
0x180026b90  cmp     r12d, [r15+rax+8]
0x180026b95  jb      loc_180026B0A
0x180026b9b  mov     edx, [r15+rax+18h]
0x180026ba0  test    edx, edx
0x180026ba2  jz      short loc_180026C0B
0x180026ba4  lea     rcx, [r13+20h]
0x180026ba8  call    ?Grow@?$CSusArrayList@USusUpdateIdentity@SusWsStructs@@V?$CSusArrayListItemOpSusServiceStruct@USusUpdateIdentity@SusWsStructs@@@@@@QEAAJK@Z; CSusArrayList<SusWsStructs::SusUpdateIdentity,CSusArrayListItemOpSusServiceStruct<SusWsStructs::SusUpdateIdentity>>::Grow(ulong)
0x180026bad  mov     esi, eax
0x180026baf  test    eax, eax
0x180026bb1  js      loc_180026EF9
0x180026bb7  xor     ebx, ebx
0x180026bb9  mov     rax, [rbp+4D0h+lpMem]
0x180026bc0  cmp     [r15+rax+18h], ebx
0x180026bc5  jbe     short loc_180026C0B
0x180026bc7  lea     rdx, [rbx+rbx*4]
0x180026bcb  mov     rcx, [r15+rax+10h]
0x180026bd0  lea     rdx, [rcx+rdx*4]
0x180026bd4  xor     r8d, r8d
0x180026bd7  lea     rcx, [r13+20h]
0x180026bdb  call    ?Add@?$CSusSortedArrayList@UtagDSGlobalUpdateId@@V?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@@@QEAAJAEBUtagDSGlobalUpdateId@@K@Z; CSusSortedArrayList<tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::Add(tagDSGlobalUpdateId const &,ulong)
0x180026be0  mov     rcx, [rbp+4D8h]; this
0x180026be7  test    eax, eax
0x180026be9  jns     short loc_180026BFB
0x180026beb  mov     r9d, eax; char *
0x180026bee  mov     r8, r14; unsigned int
0x180026bf1  mov     edx, 12FDh; void *
0x180026bf6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180026bfb  inc     ebx
0x180026bfd  mov     rax, [rbp+4D0h+lpMem]
0x180026c04  cmp     ebx, [r15+rax+18h]
0x180026c09  jb      short loc_180026BC7
0x180026c0b  mov     rbx, [rbp+4D0h+var_A8]
  ... truncated ...
```
