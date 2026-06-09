# CAgentDownloadManager::PurgeExpiredUpdates(tagDSGlobalUpdateId const *,wchar_t const *)

- ea: `0x1800911d0`
- end: `0x180092288`
- name: `?PurgeExpiredUpdates@CAgentDownloadManager@@AEAAJPEBUtagDSGlobalUpdateId@@PEB_W@Z`
- size: `4280`
- prototype: `__int64 __fastcall(CAgentDownloadManager *__hidden this, const struct tagDSGlobalUpdateId *, const wchar_t *)`
- caller_count: `2`
- callee_count: `33`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004f5e0`
- `0x1800a3c90`

## callees

- `0x18007f4e0`
- `0x18007f564`
- `0x18007f904`
- `0x18008027c`
- `0x180081440`
- `0x18008e034`
- `0x180090a94`
- `0x180090b6c`
- `0x1800911d0`
- `0x18009f044`
- `0x1800a5664`
- `0x1800a591c`
- `0x1800aa668`
- `0x1800b0e00`
- `0x1800b0ea4`
- `0x1800b0f30`
- `0x1800b0fd8`
- `0x1800e5dfc`
- `0x1800e6358`
- `0x180110914`
- `0x18011098c`
- `0x180113ae8`
- `0x180115c90`
- `0x180116648`
- `0x18011b2b0`
- `0x18012b618`
- `0x18012bed4`
- `0x18012bf80`
- `0x180132048`
- `0x180133a10`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091e4a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180091e4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009207c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092191`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009207c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092191`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091876`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180091876`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800915f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009164c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009166a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091dd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091e11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800921c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800921f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800915f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009164c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009166a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091d1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091dd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180091e11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800921c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800921f4`
- `ntdll!RtlPublishWnfStateData` at `0x1800919da`
- `ntdll!RtlPublishWnfStateData` at `0x1800919da`

## string_xrefs

- `0x180091376`: `PurgeExpiredUpdates: Found %d non expired updates.`
- `0x180091770`: `PurgeExpiredUpdates: Found %d expired updates.`
- `0x1800918b6`: `PurgeExpiredUpdates: Not deleting update content for %ws because its sandbox is in use.`
- `0x1800918e3`: `PurgeExpiredUpdates: Not deleting update content for %ws because there is an active download call.`
- `0x18009199d`: `PurgeExpiredUpdates: Not deleting update content for %ws as WNF wasn't sent yet- sending Wnf now.`
- `0x180091a2a`: `PurgeExpiredUpdates: Expiring update content for %ws now as WNF was sent.`
- `0x180091d8c`: `PurgeExpiredUpdates: Explicit expired update id %ws session data %ws wasn't found`
- `0x180092005`: `PurgeExpiredUpdates: Excluding %ws because the %ws job %ws is using it`
- `0x1800920d7`: `InstallDependent`
- `0x18009208d`: `Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CAgentDownloadManager::PurgeExpiredUpdates(
        CAgentDownloadManager *this,
        wchar_t **a2,
        const wchar_t *a3)
{
  CAgentDownloadManager *v3; // rsi
  unsigned int v4; // r12d
  struct ISusEseSession *v5; // r15
  wchar_t *v6; // r14
  int DatastoreSession; // r13d
  void *v8; // rdi
  int v9; // eax
  __int64 v10; // rax
  struct tagDSUpdateMetadata *v11; // rbx
  int v12; // eax
  void *v13; // rsi
  __int64 v14; // r12
  int v15; // eax
  struct tagDSUpdateMetadata *v16; // rcx
  int v17; // eax
  char v18; // r13
  unsigned int v19; // ebx
  __m128i v20; // xmm0
  int v21; // ecx
  WCHAR *lpString2; // r12
  char v23; // bl
  __int64 v24; // rax
  __int64 v25; // rax
  bool IsPatchUpdateHandler; // r9
  char v27; // r9
  int v28; // eax
  void *v29; // rsi
  int v30; // eax
  __int64 updated; // rax
  char *v32; // rbx
  wchar_t **v33; // rsi
  int v34; // edx
  unsigned int v35; // r13d
  wchar_t *v36; // r9
  __int64 v37; // r8
  wchar_t *v38; // rax
  unsigned __int64 v39; // rdx
  CUpdateDownloadJob *v40; // r13
  const struct _GUID *v41; // rax
  __int64 v42; // rsi
  const wchar_t *JobTypeAsString; // rax
  CUpdateDownloadJob *v44; // rsi
  unsigned int v45; // ebx
  unsigned int i; // edx
  void *v47; // rcx
  unsigned int v48; // ebx
  unsigned int j; // edx
  void *v50; // rcx
  __int64 v52; // [rsp+30h] [rbp-D0h]
  __int64 v53; // [rsp+30h] [rbp-D0h]
  __int64 v54; // [rsp+30h] [rbp-D0h]
  __int64 v55; // [rsp+40h] [rbp-C0h]
  char v56; // [rsp+50h] [rbp-B0h]
  char v57; // [rsp+51h] [rbp-AFh]
  void *v58; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v59; // [rsp+60h] [rbp-A0h] BYREF
  struct tagDSUpdateMetadata *v60; // [rsp+68h] [rbp-98h] BYREF
  CUpdateDownloadJob *v61; // [rsp+70h] [rbp-90h] BYREF
  __int64 v62; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v63; // [rsp+80h] [rbp-80h] BYREF
  void *lpMem; // [rsp+88h] [rbp-78h] BYREF
  wchar_t **v65; // [rsp+90h] [rbp-70h] BYREF
  CAgentDownloadManager *v66; // [rsp+98h] [rbp-68h]
  struct ISusEseSession *v67; // [rsp+A0h] [rbp-60h] BYREF
  PCNZWCH lpString1; // [rsp+A8h] [rbp-58h]
  _OWORD v69[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v70; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v71; // [rsp+E0h] [rbp-20h]
  _BYTE v72[112]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v73; // [rsp+160h] [rbp+60h] BYREF
  __int128 v74; // [rsp+170h] [rbp+70h] BYREF
  LPVOID pv; // [rsp+180h] [rbp+80h] BYREF
  void *v76[3]; // [rsp+188h] [rbp+88h] BYREF
  _QWORD v77[2]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v78; // [rsp+1B0h] [rbp+B0h]
  _QWORD v79[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v80; // [rsp+1D0h] [rbp+D0h]
  _QWORD v81[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v82; // [rsp+1F0h] [rbp+F0h]
  struct _FILETIME v83[10]; // [rsp+200h] [rbp+100h] BYREF
  wchar_t v84[264]; // [rsp+250h] [rbp+150h] BYREF

  lpString1 = a3;
  v65 = a2;
  v3 = this;
  v66 = this;
  v4 = 0;
  v5 = 0;
  v67 = 0;
  v73 = 0;
  v74 = 0;
  v58 = 0;
  v77[1] = 0;
  v78 = 0u;
  v77[0] = &CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::`vftable';
  v81[1] = 0;
  v82 = 0u;
  v81[0] = &CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::`vftable';
  v79[1] = 0;
  v80 = 0u;
  v79[0] = &CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::`vftable';
  v6 = 0;
  v63 = 0;
  DatastoreSession = DuplicateString<wchar_t const *,wchar_t *>(*((_QWORD *)this + 148), &v58);
  v8 = v58;
  if ( DatastoreSession < 0 )
    goto LABEL_167;
  v60 = (struct tagDSUpdateMetadata *)v58;
  DatastoreSession = CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v77, &v60, 0);
  if ( DatastoreSession < 0 )
    goto LABEL_167;
  v8 = 0;
  v58 = 0;
  DatastoreSession = CAgentDownloadManager::GetDatastoreSession(v3, &v67);
  v5 = v67;
  if ( DatastoreSession < 0 )
    goto LABEL_167;
  v9 = (*(__int64 (__fastcall **)(struct ISusEseSession *, __int128 *, char *))(*(_QWORD *)v67 + 512LL))(
         v67,
         &v73,
         (char *)&v73 + 8);
  DatastoreSession = v9;
  if ( v9 > -2145091548 )
  {
    if ( (unsigned int)(v9 + 2145091547) > 4 && v9 < 0 )
      goto LABEL_167;
  }
  else if ( (unsigned int)(v9 + 2145091552) > 4 && v9 != -2145091577 )
  {
    goto LABEL_167;
  }
  WUTrace(0, 0, 2, 4, 0, L"PurgeExpiredUpdates: Found %d non expired updates.", (_DWORD)v73);
  v10 = 0;
  v59 = 0;
  if ( !(_DWORD)v73 )
  {
LABEL_48:
    v17 = (*(__int64 (__fastcall **)(struct ISusEseSession *, __int128 *, char *))(*(_QWORD *)v5 + 504LL))(
            v5,
            &v74,
            (char *)&v74 + 8);
    DatastoreSession = v17;
    if ( v17 > -2145091548 )
    {
      if ( (unsigned int)(v17 + 2145091547) > 4 && v17 < 0 )
        goto LABEL_167;
    }
    else if ( (unsigned int)(v17 + 2145091552) > 4 && v17 != -2145091577 )
    {
      goto LABEL_167;
    }
    LODWORD(v52) = v74;
    WUTrace(0, 0, 2, 4, 0, L"PurgeExpiredUpdates: Found %d expired updates.", v52);
    v18 = 0;
    v57 = 0;
    v19 = 0;
    v59 = 0;
    if ( !(_DWORD)v74 )
    {
LABEL_118:
      if ( v65 && !v18 )
      {
        updated = Trace::UpdateIdToString::UpdateIdToString(
                    (Trace::UpdateIdToString *)v72,
                    (const struct tagDSGlobalUpdateId *)v65);
        WUTrace(
          0,
          0,
          2,
          1,
          0,
          L"PurgeExpiredUpdates: Explicit expired update id %ws session data %ws wasn't found",
          updated,
          lpString1);
        DatastoreSession = -2145091577;
        goto LABEL_167;
      }
      v32 = (char *)v3 + 616;
      v62 = (__int64)v3 + 616;
      if ( v3 != (CAgentDownloadManager *)-616LL )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 624));
      LODWORD(pv) = *((_DWORD *)v3 + 71);
      if ( (_DWORD)pv )
      {
        while ( 1 )
        {
          v65 = 0;
          v59 = 0;
          v76[0] = &CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::`vftable';
          v33 = 0;
          v76[1] = 0;
          v76[2] = 0;
          v60 = 0;
          if ( v4 < *((_DWORD *)v66 + 71) )
          {
            v61 = *(CUpdateDownloadJob **)(*((_QWORD *)v66 + 34) + 24LL * v4);
            if ( (int)CUpdateDownloadJob::GetFileLocalNamesAndDigests(v61, &v59, &v65, 0) >= 0 )
            {
              v35 = v59;
              if ( v59 )
              {
                if ( v65 )
                {
                  CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::RemoveArraySection(v76);
                  SusFree(v76[1]);
                  v33 = v65;
                  v76[1] = v65;
                  HIDWORD(v76[2]) = v35;
                  LODWORD(v76[2]) = v35;
                }
                if ( (int)GetFileBasePath(*v33, v34) >= 0 )
                {
                  v36 = *v33;
                  if ( *v33 )
                  {
                    v37 = 0x7FFFFFFF;
                    v38 = *v33;
                    do
                    {
                      if ( !*v38 )
                        break;
                      ++v38;
                      --v37;
                    }
                    while ( v37 );
                    v39 = (0x7FFFFFFF - v37) & ((unsigned __int128)-(__int128)(unsigned __int64)v37 >> 64);
                    if ( v37 )
                    {
                      if ( v39 > 1 )
                      {
                        if ( v36[v39 - 1] == 92 )
                          v36[v39 - 1] = 0;
                        if ( (int)DuplicateString<wchar_t *,wchar_t *>(*v33, &v60) >= 0 )
                        {
                          v40 = v61;
                          v41 = (const struct _GUID *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v61 + 13) + 40LL))(*((_QWORD *)v61 + 13));
                          v42 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v83, v41);
                          JobTypeAsString = CUpdateDownloadJob::GetJobTypeAsString(v40);
                          v55 = v42;
                          v44 = v60;
                          WUTrace(
                            0,
                            0,
                            2,
                            4,
                            0,
                            L"PurgeExpiredUpdates: Excluding %ws because the %ws job %ws is using it",
                            v60,
                            JobTypeAsString,
                            v55);
                          v61 = v44;
                          DatastoreSession = CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(
                                               v77,
                                               &v61,
                                               0);
                          if ( DatastoreSession < 0 )
                          {
                            WUTrace(
                              0,
                              0,
                              2,
                              3,
                              DatastoreSession,
                              L"Failed to add the sandbox %ws into the exception list",
                              v44);
                            if ( v44 )
                              SusFree(v44);
                            CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(v76);
                            if ( v32 )
                              LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 8));
                            goto LABEL_167;
                          }
                        }
                        else if ( v60 )
                        {
                          SusFree(v60);
                        }
                      }
                    }
                  }
                }
              }
            }
          }
          CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>::~CSusArrayList<wchar_t *,CSusArrayListItemOpCoTaskMemFree<wchar_t *>>(v76);
          if ( ++v4 >= (unsigned int)pv )
          {
            v3 = v66;
            break;
          }
        }
      }
      if ( v32 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 8));
      DatastoreSession = CreateCombinedPath((const wchar_t *)v3 + 332, L"Install", &v63);
      if ( DatastoreSession < 0 )
        goto LABEL_166;
      v6 = v63;
      v61 = (CUpdateDownloadJob *)v63;
      DatastoreSession = CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v77, &v61, 0);
      if ( DatastoreSession < 0 )
        goto LABEL_167;
      v63 = 0;
      DatastoreSession = CreateCombinedPath((const wchar_t *)v3 + 332, L"InstallDependent", &v63);
      if ( DatastoreSession < 0 )
      {
LABEL_166:
        v6 = v63;
      }
      else
      {
        v6 = v63;
        v61 = (CUpdateDownloadJob *)v63;
        DatastoreSession = CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v77, &v61, 0);
        if ( DatastoreSession >= 0 )
        {
          v6 = 0;
          v63 = 0;
          DatastoreSession = CAgentDownloadManager::PurgeContentForPatchUpdates(v3, v77, v81, v79);
        }
      }
LABEL_167:
      CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::RemoveArraySection(v77);
      v45 = 0;
      for ( i = v74; v45 < i; ++v45 )
      {
        v47 = *(void **)(56LL * v45 + *((_QWORD *)&v74 + 1) + 48);
        if ( v47 )
        {
          CoTaskMemFree(v47);
          i = v74;
        }
      }
      v48 = 0;
      for ( j = v73; v48 < j; ++v48 )
      {
        v50 = *(void **)(56LL * v48 + *((_QWORD *)&v73 + 1) + 48);
        if ( v50 )
        {
          CoTaskMemFree(v50);
          j = v73;
        }
      }
      goto LABEL_175;
    }
    while ( 1 )
    {
      v60 = 0;
      v56 = 0;
      memset(v83, 0, sizeof(v83));
      memset(v76, 0, 20);
      v61 = (CUpdateDownloadJob *)(56LL * v19);
      v20 = *(__m128i *)((char *)v61 + *((_QWORD *)&v74 + 1));
      *(__m128i *)v76 = v20;
      v21 = *(_DWORD *)((char *)v61 + *((_QWORD *)&v74 + 1) + 16);
      LODWORD(v76[2]) = v21;
      lpString2 = *(WCHAR **)((char *)v61 + *((_QWORD *)&v74 + 1) + 48);
      pv = lpString2;
      v23 = 0;
      if ( v65 )
      {
        if ( *v65 != (wchar_t *)v20.m128i_i64[0]
          || v65[1] != (wchar_t *)_mm_srli_si128(v20, 8).m128i_i64[0]
          || *((_DWORD *)v65 + 4) != v21
          || lpString1 != lpString2
          && (!lpString1 || !lpString2 || CompareStringW(0x7Fu, 1u, lpString1, -1, lpString2, -1) != 2) )
        {
          goto LABEL_69;
        }
        v23 = 1;
        v57 = 1;
      }
      if ( CAgentDownloadManager::IsUpdateSandboxInUse(v3, (const struct tagDSGlobalUpdateId *)v76, lpString2) )
      {
        v53 = Trace::UpdateIdToString::UpdateIdToString(
                (Trace::UpdateIdToString *)v72,
                (const struct tagDSGlobalUpdateId *)v76);
        WUTrace(
          0,
          0,
          2,
          5,
          0,
          L"PurgeExpiredUpdates: Not deleting update content for %ws because its sandbox is in use.",
          v53);
      }
      else
      {
        if ( !CAgentDownloadManager::AnyCallerForUpdate(v3, (const struct LockedUpdateId *)v76, lpString2) )
          goto LABEL_70;
        v54 = Trace::UpdateIdToString::UpdateIdToString(
                (Trace::UpdateIdToString *)v72,
                (const struct tagDSGlobalUpdateId *)v76);
        WUTrace(
          0,
          0,
          2,
          5,
          0,
          L"PurgeExpiredUpdates: Not deleting update content for %ws because there is an active download call.",
          v54);
      }
      if ( v23 )
      {
        DatastoreSession = -2145124343;
        goto LABEL_167;
      }
LABEL_69:
      v56 = 1;
LABEL_70:
      DatastoreSession = CAgentDownloadManager::GetUpdateDownloadState(
                           v3,
                           (const struct LockedUpdateId *)v76,
                           lpString2,
                           0x88u,
                           (struct tagDSUpdateDLState *)v83);
      if ( DatastoreSession < 0 )
        goto LABEL_167;
      if ( !v65
        && (v83[2].dwHighDateTime != 0x7FFFFFFF || v83[2].dwLowDateTime != -1)
        && (unsigned int)IsInThePast(&v83[2]) )
      {
        if ( v83[3].dwLowDateTime )
        {
          v25 = Trace::UpdateIdToString::UpdateIdToString(
                  (Trace::UpdateIdToString *)v72,
                  (const struct tagDSGlobalUpdateId *)v76);
          WUTrace(0, 0, 2, 4, 0, L"PurgeExpiredUpdates: Expiring update content for %ws now as WNF was sent.", v25);
        }
        else
        {
          v24 = Trace::UpdateIdToString::UpdateIdToString(
                  (Trace::UpdateIdToString *)v72,
                  (const struct tagDSGlobalUpdateId *)v76);
          WUTrace(
            0,
            0,
            2,
            4,
            0,
            L"PurgeExpiredUpdates: Not deleting update content for %ws as WNF wasn't sent yet- sending Wnf now.",
            v24);
          RtlPublishWnfStateData(WNF_WUA_UPDATE_EXPIRING, 0, v76, 16, 0);
          v83[3].dwLowDateTime = 1;
          DatastoreSession = CAgentDownloadManager::SetUpdateDownloadState(
                               v3,
                               (const struct LockedUpdateId *)v76,
                               lpString2,
                               0x80u,
                               (const struct tagDSUpdateDLState *)v83);
          if ( DatastoreSession < 0 )
            goto LABEL_167;
          v56 = 1;
        }
      }
      DatastoreSession = CAgentDownloadManager::GetUpdateMetadata(v3, v76, 3616, 0, &c_idSrvNone, &v60);
      if ( DatastoreSession < 0 )
      {
        v11 = v60;
LABEL_45:
        if ( !v11 )
          goto LABEL_167;
LABEL_46:
        v16 = v11;
LABEL_47:
        DsqFreeObject(v16, 1u, 12207, 1);
        SusFree(v11);
        goto LABEL_167;
      }
      v11 = v60;
      IsPatchUpdateHandler = CAgentDownloadManager::IsPatchUpdateHandler(
                               v3,
                               (struct tagDSUpdateMetadata *)((char *)v60 + 120));
      if ( !v56
        && (IsPatchUpdateHandler && (v83[0].dwLowDateTime == 1 || v83[0].dwLowDateTime == 4)
         || (*((_DWORD *)v11 + 46) & 0x20) != 0
         || (unsigned __int16)*((_DWORD *)v11 + 9)) )
      {
        DatastoreSession = CAgentDownloadManager::PurgeContentForPatchUpdate(
                             v3,
                             (const struct tagDSGlobalUpdateId *)v76,
                             lpString2);
        if ( DatastoreSession < 0 )
          goto LABEL_43;
        v27 = 0;
LABEL_88:
        DatastoreSession = CAgentDownloadManager::ResetUpdateDownloadState(
                             v3,
                             (const struct LockedUpdateId *)v76,
                             lpString2,
                             v27);
        v4 = 0;
        v16 = v11;
        if ( DatastoreSession < 0 )
          goto LABEL_47;
        goto LABEL_116;
      }
      if ( v83[0].dwLowDateTime == 1 && !v56 )
      {
        v27 = 1;
        goto LABEL_88;
      }
      v4 = 0;
      if ( IsPatchUpdateHandler )
      {
        if ( *((_DWORD *)v11 + 116) )
        {
          do
          {
            lpMem = 0;
            v28 = HexStringFromBlobAllocW(
                    *(const unsigned __int8 **)(248LL * v4 + *((_QWORD *)v11 + 59) + 128),
                    *(_DWORD *)(248LL * v4 + *((_QWORD *)v11 + 59) + 124),
                    (wchar_t **)&lpMem);
            v29 = lpMem;
            if ( v28 >= 0 )
            {
              v62 = (__int64)lpMem;
              if ( (int)CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v81, &v62, 1) >= 0 )
                v29 = 0;
            }
            if ( v29 )
              SusFree(v29);
            ++v4;
          }
          while ( v4 < *((_DWORD *)v11 + 116) );
          v3 = v66;
        }
        DatastoreSession = CAgentDownloadManager::GetUpdateDownloadPath(
                             v3,
                             (const struct tagDSGlobalUpdateId *)v76,
                             (const wchar_t *)pv,
                             v84,
                             0x104u);
        v4 = 0;
        if ( DatastoreSession < 0 )
          goto LABEL_46;
        if ( v8 )
        {
          SusFree(v8);
          v58 = 0;
        }
        DatastoreSession = DuplicateString<wchar_t *,wchar_t *>(v84, &v58);
        if ( DatastoreSession < 0 )
          goto LABEL_41;
        v8 = v58;
        v62 = (__int64)v58;
        if ( (int)CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v77, &v62, 0) >= 0 )
        {
          v8 = 0;
          v58 = 0;
          memset(v69, 0, 24);
          pv = 0;
          *(_OWORD *)((char *)v69 + 4) = *(_OWORD *)((char *)v61 + *((_QWORD *)&v74 + 1));
          DWORD1(v69[1]) = *(_DWORD *)((char *)v61 + *((_QWORD *)&v74 + 1) + 16);
          v70 = v69[0];
          v71 = *(_QWORD *)&v69[1];
          if ( (*(int (__fastcall **)(struct ISusEseSession *, __int128 *, LPVOID *))(*(_QWORD *)v5 + 744LL))(
                 v5,
                 &v70,
                 &pv) >= 0 )
          {
            DatastoreSession = DuplicateString<wchar_t *,wchar_t *>(pv, &v58);
            if ( DatastoreSession < 0 )
            {
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              goto LABEL_41;
            }
            v8 = v58;
            v61 = (CUpdateDownloadJob *)v58;
            v30 = CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v79, &v61, 1);
            DatastoreSession = 0;
            if ( v30 != -2145124333 )
              DatastoreSession = v30;
            if ( DatastoreSession < 0 )
            {
              if ( pv )
              {
                CoTaskMemFree(pv);
                pv = 0;
              }
              goto LABEL_126;
            }
            v8 = 0;
            v58 = 0;
          }
          if ( pv )
            CoTaskMemFree(pv);
        }
      }
      v16 = v11;
LABEL_116:
      DsqFreeObject(v16, 1u, 12207, 1);
      SusFree(v11);
      v19 = v59 + 1;
      v59 = v19;
      if ( v19 >= (unsigned int)v74 )
      {
        v18 = v57;
        goto LABEL_118;
      }
    }
  }
  while ( 1 )
  {
    v62 = 56 * v10;
    *(_OWORD *)v76 = *(_OWORD *)(56 * v10 + *((_QWORD *)&v73 + 1));
    LODWORD(v76[2]) = *(_DWORD *)(56 * v10 + *((_QWORD *)&v73 + 1) + 16);
    lpMem = 0;
    DatastoreSession = CAgentDownloadManager::GetUpdateMetadata(v3, v76, 3616, 0, &c_idSrvNone, &lpMem);
    if ( DatastoreSession < 0 )
    {
      v11 = (struct tagDSUpdateMetadata *)lpMem;
      goto LABEL_45;
    }
    v11 = (struct tagDSUpdateMetadata *)lpMem;
    if ( *((_DWORD *)lpMem + 116) )
    {
      do
      {
        pv = 0;
        v12 = HexStringFromBlobAllocW(
                *(const unsigned __int8 **)(248LL * v4 + *((_QWORD *)v11 + 59) + 128),
                *(_DWORD *)(248LL * v4 + *((_QWORD *)v11 + 59) + 124),
                (wchar_t **)&pv);
        v13 = pv;
        if ( v12 >= 0 )
        {
          v60 = (struct tagDSUpdateMetadata *)pv;
          if ( (int)CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v81, &v60, 1) >= 0 )
            v13 = 0;
        }
        if ( v13 )
          SusFree(v13);
        ++v4;
      }
      while ( v4 < *((_DWORD *)v11 + 116) );
      v3 = v66;
    }
    v14 = v62;
    DatastoreSession = CAgentDownloadManager::GetUpdateDownloadPath(
                         v3,
                         (const struct tagDSGlobalUpdateId *)(v62 + *((_QWORD *)&v73 + 1)),
                         *(const wchar_t **)(v62 + *((_QWORD *)&v73 + 1) + 48),
                         v84,
                         0x104u);
    if ( DatastoreSession < 0 )
    {
LABEL_43:
      DsqFreeObject(v11, 1u, 12207, 1);
      SusFree(v11);
      goto LABEL_167;
    }
    if ( v8 )
    {
      SusFree(v8);
      v58 = 0;
    }
    DatastoreSession = DuplicateString<wchar_t *,wchar_t *>(v84, &v58);
    if ( DatastoreSession < 0 )
    {
LABEL_41:
      DsqFreeObject(v11, 1u, 12207, 1);
      SusFree(v11);
      v8 = v58;
      goto LABEL_167;
    }
    v8 = v58;
    v62 = (__int64)v58;
    if ( (int)CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v77, &v62, 0) >= 0 )
      break;
    v4 = 0;
LABEL_34:
    DsqFreeObject(v11, 1u, 12207, 1);
    SusFree(v11);
    v10 = v59 + 1;
    v59 = v10;
    if ( (unsigned int)v10 >= (unsigned int)v73 )
      goto LABEL_48;
  }
  v8 = 0;
  v58 = 0;
  memset(v76, 0, sizeof(v76));
  pv = 0;
  *(_OWORD *)((char *)v76 + 4) = *(_OWORD *)(v14 + *((_QWORD *)&v73 + 1));
  HIDWORD(v76[2]) = *(_DWORD *)(v14 + *((_QWORD *)&v73 + 1) + 16);
  v69[0] = *(_OWORD *)v76;
  *(void **)&v69[1] = v76[2];
  v4 = 0;
  if ( (*(int (__fastcall **)(struct ISusEseSession *, _OWORD *, LPVOID *))(*(_QWORD *)v5 + 744LL))(v5, v69, &pv) < 0 )
  {
LABEL_31:
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_34;
  }
  DatastoreSession = DuplicateString<wchar_t *,wchar_t *>(pv, &v58);
  if ( DatastoreSession < 0 )
  {
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    goto LABEL_41;
  }
  v8 = v58;
  v62 = (__int64)v58;
  v15 = CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(v79, &v62, 1);
  DatastoreSession = 0;
  if ( v15 != -2145124333 )
    DatastoreSession = v15;
  if ( DatastoreSession >= 0 )
  {
    v8 = 0;
    v58 = 0;
    goto LABEL_31;
  }
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
LABEL_126:
  DsqFreeObject(v11, 1u, 12207, 1);
  SusFree(v11);
LABEL_175:
  if ( v6 )
    SusFree(v6);
  CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::~CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>(v79);
  CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::~CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>(v81);
  CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::~CSusArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>(v77);
  if ( v8 )
    SusFree(v8);
  if ( v5 )
    (*(void (__fastcall **)(struct ISusEseSession *))(*(_QWORD *)v5 + 16LL))(v5);
  return (unsigned int)DatastoreSession;
}

```

## disassembly

```asm
0x1800911d0  mov     [rsp-8+arg_18], rbx
0x1800911d5  push    rbp
0x1800911d6  push    rsi
0x1800911d7  push    rdi
0x1800911d8  push    r12
0x1800911da  push    r13
0x1800911dc  push    r14
0x1800911de  push    r15
0x1800911e0  lea     rbp, [rsp-370h]
0x1800911e8  sub     rsp, 470h
0x1800911ef  mov     rax, cs:__security_cookie
0x1800911f6  xor     rax, rsp
0x1800911f9  mov     [rbp+3A0h+var_40], rax
0x180091200  mov     [rbp+3A0h+lpString1], r8
0x180091204  mov     [rbp+3A0h+var_410], rdx
0x180091208  mov     rsi, rcx
0x18009120b  mov     [rbp+3A0h+var_408], rcx
0x18009120f  xor     r12d, r12d
0x180091212  mov     r15d, r12d
0x180091215  mov     [rbp+3A0h+var_400], r12
0x180091219  xorps   xmm0, xmm0
0x18009121c  movups  [rbp+3A0h+var_340], xmm0
0x180091220  xorps   xmm1, xmm1
0x180091223  movups  [rbp+3A0h+var_330], xmm1
0x180091227  mov     [rsp+4A0h+var_448], r12
0x18009122c  movups  [rbp+3A0h+var_300], xmm0
0x180091233  movups  [rbp+3A0h+var_2F0], xmm0
0x18009123a  mov     qword ptr [rbp+3A0h+var_300+8], r12
0x180091241  mov     qword ptr [rbp+3A0h+var_2F0], r12
0x180091248  lea     rax, ??_7?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@6B@; const CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::`vftable'
0x18009124f  mov     qword ptr [rbp+3A0h+var_300], rax
0x180091256  mov     dword ptr [rbp+3A0h+var_2F0+8], r12d
0x18009125d  movups  [rbp+3A0h+var_2C0], xmm0
0x180091264  movups  [rbp+3A0h+var_2B0], xmm0
0x18009126b  mov     qword ptr [rbp+3A0h+var_2C0+8], r12
0x180091272  mov     qword ptr [rbp+3A0h+var_2B0], r12
0x180091279  mov     qword ptr [rbp+3A0h+var_2C0], rax
0x180091280  mov     dword ptr [rbp+3A0h+var_2B0+8], r12d
0x180091287  movups  [rbp+3A0h+var_2E0], xmm0
0x18009128e  movups  [rbp+3A0h+var_2D0], xmm0
0x180091295  mov     qword ptr [rbp+3A0h+var_2E0+8], r12
0x18009129c  mov     qword ptr [rbp+3A0h+var_2D0], r12
0x1800912a3  mov     qword ptr [rbp+3A0h+var_2E0], rax
0x1800912aa  mov     dword ptr [rbp+3A0h+var_2D0+8], r12d
0x1800912b1  mov     r14d, r12d
0x1800912b4  mov     [rbp+3A0h+var_420], r12
0x1800912b8  lea     rdx, [rsp+4A0h+var_448]
0x1800912bd  mov     rcx, [rcx+4A0h]
0x1800912c4  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x1800912c9  mov     r13d, eax
0x1800912cc  mov     rdi, [rsp+4A0h+var_448]
0x1800912d1  test    eax, eax
0x1800912d3  js      loc_18009219D
0x1800912d9  mov     [rsp+4A0h+var_438], rdi
0x1800912de  xor     r8d, r8d
0x1800912e1  lea     rdx, [rsp+4A0h+var_438]
0x1800912e6  lea     rcx, [rbp+3A0h+var_300]
0x1800912ed  call    ?Add@?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@QEAAJAEBQEA_WK@Z; CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(wchar_t * const &,ulong)
0x1800912f2  mov     r13d, eax
0x1800912f5  test    eax, eax
0x1800912f7  js      loc_18009219D
0x1800912fd  mov     edi, r12d
0x180091300  mov     [rsp+4A0h+var_448], r12
0x180091305  lea     rdx, [rbp+3A0h+var_400]; struct ISusEseSession **
0x180091309  mov     rcx, rsi; this
0x18009130c  call    ?GetDatastoreSession@CAgentDownloadManager@@AEAAJPEAPEAUISusEseSession@@@Z; CAgentDownloadManager::GetDatastoreSession(ISusEseSession * *)
0x180091311  mov     r13d, eax
0x180091314  mov     r15, [rbp+3A0h+var_400]
0x180091318  test    eax, eax
0x18009131a  js      loc_18009219D
0x180091320  mov     rax, [r15]
0x180091323  lea     r8, [rbp+3A0h+var_340+8]
0x180091327  lea     rdx, [rbp+3A0h+var_340]
0x18009132b  mov     rcx, r15
0x18009132e  mov     rax, [rax+200h]
0x180091335  call    _guard_dispatch_icall
0x18009133a  mov     r13d, eax
0x18009133d  cmp     eax, 80248024h
0x180091342  jg      short loc_18009135C
0x180091344  add     eax, 7FDB7FE0h
0x180091349  cmp     eax, 4
0x18009134c  jbe     short loc_18009136F
0x18009134e  cmp     r13d, 80248007h
0x180091355  jz      short loc_18009136F
0x180091357  jmp     loc_18009219D
0x18009135c  add     eax, 7FDB7FDBh
0x180091361  cmp     eax, 4
0x180091364  jbe     short loc_18009136F
0x180091366  test    r13d, r13d
0x180091369  js      loc_18009219D
0x18009136f  mov     eax, dword ptr [rbp+3A0h+var_340]
0x180091372  mov     dword ptr [rsp+4A0h+var_470], eax
0x180091376  lea     rax, aPurgeexpiredup; "PurgeExpiredUpdates: Found %d non expir"...
0x18009137d  mov     qword ptr [rsp+4A0h+cchCount2], rax
0x180091382  mov     [rsp+4A0h+lpString2], r12
0x180091387  xor     edx, edx
0x180091389  xor     ecx, ecx
0x18009138b  lea     r9d, [rdx+4]
0x18009138f  lea     r8d, [rdx+2]
0x180091393  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180091398  mov     eax, r12d
0x18009139b  mov     [rsp+4A0h+var_440], eax
0x18009139f  lea     rdx, c_idSrvNone
0x1800913a6  cmp     dword ptr [rbp+3A0h+var_340], r12d
0x1800913aa  jbe     loc_18009171A
0x1800913b0  imul    rcx, rax, 38h ; '8'
0x1800913b4  mov     [rsp+4A0h+var_428], rcx
0x1800913b9  mov     rax, qword ptr [rbp+3A0h+var_340+8]
0x1800913bd  movups  xmm0, xmmword ptr [rcx+rax]
0x1800913c1  movdqu  xmmword ptr [rbp+3A0h+var_318], xmm0
0x1800913c9  mov     eax, [rcx+rax+10h]
0x1800913cd  mov     dword ptr [rbp+3A0h+var_308], eax
0x1800913d3  mov     [rbp+3A0h+lpMem], r12
0x1800913d7  lea     rax, [rbp+3A0h+lpMem]
0x1800913db  mov     qword ptr [rsp+4A0h+cchCount2], rax
0x1800913e0  mov     [rsp+4A0h+lpString2], rdx
0x1800913e5  xor     r9d, r9d
0x1800913e8  mov     r8d, 0E20h
0x1800913ee  lea     rdx, [rbp+3A0h+var_318]
0x1800913f5  mov     rcx, rsi
0x1800913f8  call    ?GetUpdateMetadata@CAgentDownloadManager@@AEAAJAEBULockedUpdateId@@KW4UpdateMetadataPolicyFlags@@AEBU_GUID@@PEAPEAUtagDSUpdateMetadata@@@Z; CAgentDownloadManager::GetUpdateMetadata(LockedUpdateId const &,ulong,UpdateMetadataPolicyFlags,_GUID const &,tagDSUpdateMetadata * *)
0x1800913fd  mov     r13d, eax
0x180091400  test    eax, eax
0x180091402  js      loc_1800916EA
0x180091408  mov     rbx, [rbp+3A0h+lpMem]
0x18009140c  xor     r13d, r13d
0x18009140f  cmp     [rbx+1D0h], r13d
0x180091416  jbe     short loc_180091493
0x180091418  mov     [rbp+3A0h+pv], r13
0x18009141f  mov     eax, r12d
0x180091422  imul    r9, rax, 0F8h
0x180091429  mov     rcx, [rbx+1D8h]
0x180091430  lea     r8, [rbp+3A0h+pv]; wchar_t **
0x180091437  mov     edx, [r9+rcx+7Ch]; unsigned int
0x18009143c  mov     rcx, [r9+rcx+80h]; unsigned __int8 *
0x180091444  call    ?HexStringFromBlobAllocW@@YAJPEBEKPEAPEA_W@Z; HexStringFromBlobAllocW(uchar const *,ulong,wchar_t * *)
0x180091449  mov     rsi, [rbp+3A0h+pv]
0x180091450  test    eax, eax
0x180091452  js      short loc_180091476
0x180091454  mov     [rsp+4A0h+var_438], rsi
0x180091459  mov     r8d, 1
0x18009145f  lea     rdx, [rsp+4A0h+var_438]
0x180091464  lea     rcx, [rbp+3A0h+var_2C0]
0x18009146b  call    ?Add@?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@QEAAJAEBQEA_WK@Z; CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(wchar_t * const &,ulong)
0x180091470  test    eax, eax
0x180091472  cmovns  rsi, r13
0x180091476  test    rsi, rsi
0x180091479  jz      short loc_180091483
0x18009147b  mov     rcx, rsi; lpMem
0x18009147e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180091483  inc     r12d
0x180091486  cmp     r12d, [rbx+1D0h]
0x18009148d  jb      short loc_180091418
0x18009148f  mov     rsi, [rbp+3A0h+var_408]
0x180091493  mov     rdx, qword ptr [rbp+3A0h+var_340+8]
0x180091497  mov     r12, [rsp+4A0h+var_428]
0x18009149c  add     rdx, r12; struct tagDSGlobalUpdateId *
0x18009149f  mov     dword ptr [rsp+4A0h+lpString2], 104h; unsigned int
0x1800914a7  lea     r9, [rbp+3A0h+var_250]; wchar_t *
0x1800914ae  mov     r8, [rdx+30h]; wchar_t *
0x1800914b2  mov     rcx, rsi; this
0x1800914b5  call    ?GetUpdateDownloadPath@CAgentDownloadManager@@QEAAJAEBUtagDSGlobalUpdateId@@PEB_WPEA_WK@Z; CAgentDownloadManager::GetUpdateDownloadPath(tagDSGlobalUpdateId const &,wchar_t const *,wchar_t *,ulong)
0x1800914ba  mov     r13d, eax
0x1800914bd  test    eax, eax
0x1800914bf  js      loc_1800916C4
0x1800914c5  test    rdi, rdi
0x1800914c8  jz      short loc_1800914DB
0x1800914ca  mov     rcx, rdi; lpMem
0x1800914cd  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800914d2  mov     [rsp+4A0h+var_448], 0
0x1800914db  lea     rdx, [rsp+4A0h+var_448]
0x1800914e0  lea     rcx, [rbp+3A0h+var_250]
0x1800914e7  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x1800914ec  mov     r13d, eax
0x1800914ef  test    eax, eax
0x1800914f1  js      loc_18009169F
0x1800914f7  mov     rdi, [rsp+4A0h+var_448]
0x1800914fc  mov     [rsp+4A0h+var_428], rdi
0x180091501  xor     r8d, r8d
0x180091504  lea     rdx, [rsp+4A0h+var_428]
0x180091509  lea     rcx, [rbp+3A0h+var_300]
0x180091510  call    ?Add@?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@QEAAJAEBQEA_WK@Z; CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(wchar_t * const &,ulong)
0x180091515  xor     ecx, ecx
0x180091517  test    eax, eax
0x180091519  js      loc_180091600
0x18009151f  mov     edi, ecx
0x180091521  mov     [rsp+4A0h+var_448], rcx
0x180091526  xorps   xmm0, xmm0
0x180091529  xor     eax, eax
0x18009152b  movups  xmmword ptr [rbp+3A0h+var_318], xmm0
0x180091532  mov     [rbp+3A0h+var_308], rax
0x180091539  mov     [rbp+3A0h+pv], rcx
0x180091540  mov     rax, qword ptr [rbp+3A0h+var_340+8]
0x180091544  movups  xmm0, xmmword ptr [r12+rax]
0x180091549  movups  xmmword ptr [rbp+3A0h+var_318+4], xmm0
0x180091550  mov     eax, [r12+rax+10h]
0x180091555  mov     dword ptr [rbp+3A0h+var_308+4], eax
0x18009155b  movups  xmm0, xmmword ptr [rbp+3A0h+var_318]
0x180091562  movaps  [rbp+3A0h+var_3F0], xmm0
0x180091566  movsd   xmm1, [rbp+3A0h+var_308]
0x18009156e  movsd   [rbp+3A0h+var_3E0], xmm1
0x180091573  mov     rax, [r15]
0x180091576  lea     r8, [rbp+3A0h+pv]
0x18009157d  lea     rdx, [rbp+3A0h+var_3F0]
0x180091581  mov     rcx, r15
0x180091584  mov     rax, [rax+2E8h]
0x18009158b  call    _guard_dispatch_icall
0x180091590  xor     r12d, r12d
0x180091593  test    eax, eax
0x180091595  js      short loc_1800915EC
0x180091597  lea     rdx, [rsp+4A0h+var_448]
0x18009159c  mov     rcx, [rbp+3A0h+pv]
0x1800915a3  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x1800915a8  mov     r13d, eax
0x1800915ab  test    eax, eax
0x1800915ad  js      loc_18009165E
0x1800915b3  mov     rdi, [rsp+4A0h+var_448]
0x1800915b8  mov     [rsp+4A0h+var_428], rdi
0x1800915bd  lea     r8d, [r12+1]
0x1800915c2  lea     rdx, [rsp+4A0h+var_428]
0x1800915c7  lea     rcx, [rbp+3A0h+var_2E0]
0x1800915ce  call    ?Add@?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@QEAAJAEBQEA_WK@Z; CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR>::Add(wchar_t * const &,ulong)
0x1800915d3  mov     r13d, r12d
0x1800915d6  cmp     eax, 80240013h
0x1800915db  cmovnz  r13d, eax
0x1800915df  test    r13d, r13d
0x1800915e2  js      short loc_180091640
0x1800915e4  mov     edi, r12d
0x1800915e7  mov     [rsp+4A0h+var_448], r12
0x1800915ec  mov     rcx, [rbp+3A0h+pv]; pv
0x1800915f3  test    rcx, rcx
0x1800915f6  jz      short loc_180091603
0x1800915f8  call    cs:__imp_CoTaskMemFree
0x1800915fe  jmp     short loc_180091603
0x180091600  xor     r12d, r12d
0x180091603  mov     edx, 1; unsigned int
0x180091608  mov     r9d, edx; int
0x18009160b  mov     r8d, 2FAFh; unsigned int
0x180091611  mov     rcx, rbx; struct tagDSUpdateMetadata *
0x180091614  call    ?DsqFreeObject@@YAXPEAUtagDSUpdateMetadata@@KKH@Z; DsqFreeObject(tagDSUpdateMetadata *,ulong,ulong,int)
0x180091619  mov     rcx, rbx; lpMem
0x18009161c  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180091621  mov     eax, [rsp+4A0h+var_440]
0x180091625  inc     eax
0x180091627  mov     [rsp+4A0h+var_440], eax
0x18009162b  cmp     eax, dword ptr [rbp+3A0h+var_340]
0x18009162e  jnb     loc_18009171A
0x180091634  lea     rdx, c_idSrvNone
0x18009163b  jmp     loc_1800913B0
0x180091640  mov     rcx, [rbp+3A0h+pv]; pv
0x180091647  test    rcx, rcx
0x18009164a  jz      short loc_180091659
0x18009164c  call    cs:__imp_CoTaskMemFree
0x180091652  mov     [rbp+3A0h+pv], r12
0x180091659  jmp     loc_180091DE2
0x18009165e  mov     rcx, [rbp+3A0h+pv]; pv
0x180091665  test    rcx, rcx
0x180091668  jz      short loc_180091677
0x18009166a  call    cs:__imp_CoTaskMemFree
0x180091670  mov     [rbp+3A0h+pv], r12
0x180091677  mov     edx, 1; unsigned int
0x18009167c  mov     r9d, edx; int
0x18009167f  mov     r8d, 2FAFh; unsigned int
0x180091685  mov     rcx, rbx; struct tagDSUpdateMetadata *
0x180091688  call    ?DsqFreeObject@@YAXPEAUtagDSUpdateMetadata@@KKH@Z; DsqFreeObject(tagDSUpdateMetadata *,ulong,ulong,int)
0x18009168d  mov     rcx, rbx; lpMem
0x180091690  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180091695  mov     rdi, [rsp+4A0h+var_448]
0x18009169a  jmp     loc_18009219D
0x18009169f  mov     edx, 1; unsigned int
0x1800916a4  mov     r9d, edx; int
0x1800916a7  mov     r8d, 2FAFh; unsigned int
0x1800916ad  mov     rcx, rbx; struct tagDSUpdateMetadata *
0x1800916b0  call    ?DsqFreeObject@@YAXPEAUtagDSUpdateMetadata@@KKH@Z; DsqFreeObject(tagDSUpdateMetadata *,ulong,ulong,int)
0x1800916b5  mov     rcx, rbx; lpMem
0x1800916b8  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800916bd  mov     rdi, [rsp+4A0h+var_448]
0x1800916c2  jmp     short loc_1800916E2
0x1800916c4  mov     edx, 1; unsigned int
0x1800916c9  mov     r9d, edx; int
0x1800916cc  mov     r8d, 2FAFh; unsigned int
0x1800916d2  mov     rcx, rbx; struct tagDSUpdateMetadata *
0x1800916d5  call    ?DsqFreeObject@@YAXPEAUtagDSUpdateMetadata@@KKH@Z; DsqFreeObject(tagDSUpdateMetadata *,ulong,ulong,int)
0x1800916da  mov     rcx, rbx; lpMem
0x1800916dd  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800916e2  xor     r12d, r12d
0x1800916e5  jmp     loc_18009219D
0x1800916ea  mov     rbx, [rbp+3A0h+lpMem]
0x1800916ee  test    rbx, rbx
0x1800916f1  jz      loc_18009219D
0x1800916f7  mov     edx, 1; unsigned int
0x1800916fc  mov     r9d, edx; int
0x1800916ff  mov     r8d, 2FAFh; unsigned int
0x180091705  mov     rcx, rbx; struct tagDSUpdateMetadata *
0x180091708  call    ?DsqFreeObject@@YAXPEAUtagDSUpdateMetadata@@KKH@Z; DsqFreeObject(tagDSUpdateMetadata *,ulong,ulong,int)
0x18009170d  mov     rcx, rbx; lpMem
0x180091710  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180091715  jmp     loc_18009219D
0x18009171a  mov     rax, [r15]
0x18009171d  lea     r8, [rbp+3A0h+var_330+8]
  ... truncated ...
```
