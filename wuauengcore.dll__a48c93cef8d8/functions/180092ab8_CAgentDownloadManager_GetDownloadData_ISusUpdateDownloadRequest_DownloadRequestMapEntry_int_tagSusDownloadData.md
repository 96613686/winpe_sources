# CAgentDownloadManager::GetDownloadData(ISusUpdateDownloadRequest *,DownloadRequestMapEntry *,int,tagSusDownloadData *,ExtendedError *)

- ea: `0x180092ab8`
- end: `0x18009360e`
- name: `?GetDownloadData@CAgentDownloadManager@@AEAAJPEAUISusUpdateDownloadRequest@@PEAVDownloadRequestMapEntry@@HPEAUtagSusDownloadData@@PEAVExtendedError@@@Z`
- size: `2902`
- prototype: `__int64 __fastcall(CAgentDownloadManager *this, wchar_t *, const OLECHAR **, unsigned int, struct _GUID *)`
- caller_count: `3`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180096b78`
- `0x1800f0414`
- `0x1800f09fc`

## callees

- `0x180014964`
- `0x18005c9a4`
- `0x180064d24`
- `0x18007f174`
- `0x18007f424`
- `0x18007f564`
- `0x180092ab8`
- `0x180093614`
- `0x1800a4528`
- `0x1800a5280`
- `0x1800a5664`
- `0x1800a6344`
- `0x1800abda0`
- `0x1800ad5f8`
- `0x1800b5680`
- `0x1800db980`
- `0x1800e94f4`
- `0x180110d24`
- `0x180113a10`
- `0x180113ae8`
- `0x18012b618`
- `0x18012bf80`
- `0x18012daa0`
- `0x18012dc08`
- `0x180133a10`
- `0x1801b798c`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092c0f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180092c0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c34`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180092c5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092e15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092e30`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092e15`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180092e30`
- `OLEAUT32!__imp_SysAllocString` at `0x180092d17`
- `OLEAUT32!__imp_SysAllocString` at `0x180092e00`
- `OLEAUT32!__imp_SysAllocString` at `0x180092d17`
- `OLEAUT32!__imp_SysAllocString` at `0x180092e00`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d02`
- `OLEAUT32!__imp_SysFreeString` at `0x180092df7`
- `OLEAUT32!__imp_SysFreeString` at `0x180093551`
- `OLEAUT32!__imp_SysFreeString` at `0x180093595`
- `OLEAUT32!__imp_SysFreeString` at `0x180092d02`
- `OLEAUT32!__imp_SysFreeString` at `0x180092df7`
- `OLEAUT32!__imp_SysFreeString` at `0x180093551`
- `OLEAUT32!__imp_SysFreeString` at `0x180093595`

## string_xrefs

- `0x180092bab`: `LoadUpdateMetadataFromDatastore for %ws failed`
- `0x180092ecc`: `Find update %ws as alternate update of %ws`
- `0x180092f3f`: `LoadUpdateMetadataFromDatastore for alternate update %ws failed`
- `0x18009338f`: `Unable to find app category for update %ws`
- `0x1800934d1`: `Disabling chunked mode for download. updateid: %ws`
- `0x18009349b`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAgentDownloadManager::GetDownloadData(
        CAgentDownloadManager *this,
        wchar_t *a2,
        const OLECHAR **a3,
        unsigned int a4,
        struct _GUID *a5)
{
  struct tagDSUpdateMetadata *v8; // r12
  int updated; // ebx
  __int64 v10; // rax
  struct tagDSUpdateMetadata *v11; // rsi
  char *v12; // rbx
  struct _RTL_CRITICAL_SECTION *v13; // r14
  unsigned int IndexOf; // eax
  bool v15; // di
  unsigned int v16; // ecx
  unsigned int v17; // r8d
  __int64 v18; // r9
  __int64 v19; // rdx
  const OLECHAR *v20; // rbx
  OLECHAR *v21; // rdi
  struct CSusFileRequestList *v22; // r13
  struct CSusFileRequestList *v23; // r14
  OLECHAR *v24; // r15
  struct DownloadManagerUpdateID *v25; // r12
  int UpdateDownloadVolumeFromDataStore; // eax
  OLECHAR *v27; // rbx
  struct tagDSUpdateMetadata *v28; // rbx
  __int64 v29; // rbx
  __int64 v30; // rax
  int UpdateMetadata; // r12d
  __int64 v32; // rax
  struct tagDSUpdateMetadata *v33; // rbx
  OLECHAR *v34; // rax
  struct _GUID *v35; // rcx
  OLECHAR *v36; // rax
  struct tagDSUpdateMetadata *v37; // rax
  unsigned int v38; // edx
  wchar_t *v39; // rax
  wchar_t *v40; // r13
  OLECHAR *v41; // rax
  OLECHAR *v42; // r12
  struct DownloadManagerUpdateID *v43; // rax
  struct _GUID *v44; // rbx
  __int64 v45; // rdx
  int v46; // eax
  unsigned int v47; // r8d
  unsigned int v48; // ecx
  struct ISusEseSession *v49; // rbx
  struct tagDSUpdateMetadata *v50; // rax
  __int64 v51; // rax
  struct _GUID *v52; // rcx
  int v53; // eax
  __int64 v54; // rcx
  int v55; // eax
  __int64 v56; // rcx
  __int64 v57; // rax
  bool *v59; // [rsp+28h] [rbp-D8h]
  bool v60[4]; // [rsp+40h] [rbp-C0h] BYREF
  int UpdateDownloadState; // [rsp+44h] [rbp-BCh] BYREF
  struct DownloadManagerUpdateID *MaxAppDownloadJobSize; // [rsp+48h] [rbp-B8h]
  unsigned int v63; // [rsp+50h] [rbp-B0h] BYREF
  int v64; // [rsp+54h] [rbp-ACh]
  unsigned int v65; // [rsp+58h] [rbp-A8h]
  OLECHAR *psz; // [rsp+60h] [rbp-A0h] BYREF
  struct _GUID *v67; // [rsp+68h] [rbp-98h]
  wchar_t *v68; // [rsp+70h] [rbp-90h] BYREF
  struct CSusService *v69; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v70; // [rsp+80h] [rbp-80h] BYREF
  struct tagDSUpdateMetadata *v71; // [rsp+88h] [rbp-78h]
  struct ISusEseSession *v72; // [rsp+90h] [rbp-70h] BYREF
  struct tagDSUpdateMetadata *v73; // [rsp+98h] [rbp-68h] BYREF
  struct tagDSUpdateMetadata *v74; // [rsp+A0h] [rbp-60h] BYREF
  struct CSusFileRequestList *v75; // [rsp+A8h] [rbp-58h] BYREF
  struct tagDSUpdateMetadata *v76; // [rsp+B0h] [rbp-50h]
  __int128 v77; // [rsp+B8h] [rbp-48h] BYREF
  int v78; // [rsp+C8h] [rbp-38h]
  struct CSusFileRequestList *v79; // [rsp+D0h] [rbp-30h] BYREF
  OLECHAR *v80; // [rsp+D8h] [rbp-28h]
  OLECHAR *v81; // [rsp+E0h] [rbp-20h]
  __int128 v82; // [rsp+E8h] [rbp-18h] BYREF
  int v83; // [rsp+F8h] [rbp-8h]
  _BYTE v84[112]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v85[112]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD v86[2]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int128 v87; // [rsp+1F0h] [rbp+F0h]
  struct tagDSUpdateMetadata *v88; // [rsp+200h] [rbp+100h] BYREF
  struct _GUID v89; // [rsp+208h] [rbp+108h] BYREF
  int v90; // [rsp+218h] [rbp+118h] BYREF
  __int128 v91; // [rsp+21Ch] [rbp+11Ch]
  int v92; // [rsp+22Ch] [rbp+12Ch]
  _QWORD v93[24]; // [rsp+230h] [rbp+130h] BYREF
  _QWORD v94[10]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wchar_t v95[264]; // [rsp+340h] [rbp+240h] BYREF

  v63 = a4;
  MaxAppDownloadJobSize = (struct DownloadManagerUpdateID *)a3;
  v68 = a2;
  v88 = this;
  v67 = a5;
  memset(a5, 0, 0xE0u);
  v89 = *(struct _GUID *)((char *)a3 + 20);
  v77 = *(_OWORD *)a3;
  v78 = *((_DWORD *)a3 + 4);
  v90 = 0;
  v91 = v77;
  v92 = v78;
  v73 = 0;
  v8 = 0;
  v71 = 0;
  v74 = 0;
  updated = CAgentDownloadManager::LoadUpdateMetadataFromDatastore(this, &v90, 7727, 0, &v89, &v73);
  if ( updated < 0 )
  {
    v10 = Trace::UpdateIdToString::UpdateIdToString(
            (Trace::UpdateIdToString *)v85,
            (const struct tagDSGlobalUpdateId *)&v77);
    WUTrace(0, 0, 2, 3, updated, L"LoadUpdateMetadataFromDatastore for %ws failed", v10);
    v11 = v73;
    goto LABEL_97;
  }
  v11 = v73;
  if ( *((_DWORD *)this + 372) || !a4 || (unsigned int)AreRangeRequestsProhibitedByAdmin() )
    goto LABEL_22;
  v12 = (char *)this + 616;
  v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 624);
  if ( this != (CAgentDownloadManager *)-616LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  IndexOf = CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::GetIndexOf(
              (char *)this + 1496,
              a3);
  if ( IndexOf < *((_DWORD *)this + 379) )
  {
    v15 = (*(_DWORD *)(((unsigned __int64)IndexOf << 6) + *((_QWORD *)this + 188)) & 8) != 0;
    if ( v12 )
      LeaveCriticalSection(v13);
    if ( v15 )
    {
LABEL_22:
      v64 = 0;
      WUTrace(0, 0, 2, 4, 0, L"Asking handler to generate non-range requests.");
      goto LABEL_23;
    }
  }
  else if ( this != (CAgentDownloadManager *)-616LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  }
  v64 = 1;
  v69 = 0;
  if ( (int)CAgentServiceManager::GetServiceObjectHelper(&v89, &v69) >= 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(struct CSusService *))(*(_QWORD *)v69 + 24LL))(v69) )
    {
      v16 = 0;
      v17 = *((_DWORD *)v11 + 116);
      if ( v17 )
      {
        v18 = *((_QWORD *)v11 + 59);
        do
        {
          v19 = 248LL * v16;
          if ( *(_DWORD *)(v19 + v18 + 112) == 2 && !*(_QWORD *)(v19 + v18 + 40) )
            goto LABEL_22;
        }
        while ( ++v16 < v17 );
      }
    }
  }
LABEL_23:
  v20 = a3[7];
  SysFreeString(0);
  v21 = 0;
  v80 = 0;
  if ( !v20 || (v21 = SysAllocString(v20), (v80 = v21) != 0) )
  {
    v75 = 0;
    UpdateDownloadState = CSusFileRequestList::CreateInstance(&v75);
    v22 = v75;
    v69 = v75;
    if ( UpdateDownloadState < 0
      || (UpdateDownloadState = (*(__int64 (__fastcall **)(struct CSusFileRequestList *, OLECHAR *))(*(_QWORD *)v75 + 32LL))(
                                  v75,
                                  v21),
          UpdateDownloadState < 0) )
    {
LABEL_93:
      if ( v22 )
        (**((void (__fastcall ***)(__int64, __int64))v22 + 1))((__int64)v22 + 8, 1);
      updated = UpdateDownloadState;
      goto LABEL_96;
    }
    v23 = 0;
    v79 = 0;
    if ( ((_BYTE)a3[24] & 2) != 0 )
    {
      UpdateDownloadState = CSusFileRequestList::CreateInstance(&v79);
      v23 = v79;
      if ( UpdateDownloadState < 0
        || (UpdateDownloadState = (*(__int64 (__fastcall **)(struct CSusFileRequestList *, OLECHAR *))(*(_QWORD *)v79 + 32LL))(
                                    v79,
                                    v21),
            UpdateDownloadState < 0) )
      {
LABEL_91:
        if ( v23 )
          (**((void (__fastcall ***)(__int64, __int64))v23 + 1))((__int64)v23 + 8, 1);
        goto LABEL_93;
      }
    }
    v24 = 0;
    v81 = 0;
    psz = 0;
    v25 = MaxAppDownloadJobSize;
    UpdateDownloadVolumeFromDataStore = CAgentDownloadManager::GetUpdateDownloadVolumeFromDataStore(
                                          v88,
                                          (const struct tagDSGlobalUpdateId *)&v77,
                                          *((const wchar_t **)MaxAppDownloadJobSize + 5),
                                          &psz);
    v27 = psz;
    if ( UpdateDownloadVolumeFromDataStore >= 0 )
    {
      if ( psz )
      {
        SysFreeString(0);
        v24 = SysAllocString(v27);
        v81 = v24;
        if ( !v24 )
        {
          CoTaskMemFree(v27);
          UpdateDownloadState = -2147024882;
LABEL_90:
          SysFreeString(v24);
          v8 = v71;
          goto LABEL_91;
        }
      }
    }
    if ( v27 )
      CoTaskMemFree(v27);
    memset(v94, 0, sizeof(v94));
    v28 = v88;
    UpdateDownloadState = CAgentDownloadManager::GetUpdateDownloadState(
                            v88,
                            (const struct LockedUpdateId *)&v77,
                            *((const wchar_t **)MaxAppDownloadJobSize + 5),
                            4u,
                            (struct tagDSUpdateDLState *)v94);
    if ( UpdateDownloadState < 0 )
      goto LABEL_90;
    v82 = 0;
    v83 = 0;
    if ( (int)CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::get_Value(
                (char *)v28 + 1912,
                MaxAppDownloadJobSize,
                &v82) < 0 )
    {
      v33 = v71;
    }
    else
    {
      v29 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v85,
              (const struct tagDSGlobalUpdateId *)&v77);
      v30 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v84,
              (const struct tagDSGlobalUpdateId *)&v82);
      WUTrace(0, 0, 2, 4, 0, L"Find update %ws as alternate update of %ws", v30, v29);
      UpdateMetadata = CAgentDownloadManager::GetUpdateMetadata(v88, &v82, 32, 0, &v89, &v74);
      UpdateDownloadState = UpdateMetadata;
      if ( UpdateMetadata < 0 )
      {
        v32 = Trace::UpdateIdToString::UpdateIdToString(
                (Trace::UpdateIdToString *)v84,
                (const struct tagDSGlobalUpdateId *)&v77);
        WUTrace(0, 0, 2, 3, UpdateMetadata, L"LoadUpdateMetadataFromDatastore for alternate update %ws failed", v32);
        v71 = v74;
        goto LABEL_90;
      }
      v33 = v74;
      v71 = v74;
      v25 = MaxAppDownloadJobSize;
    }
    v87 = 0;
    v86[1] = v94[4];
    v86[0] = *((_QWORD *)v25 + 5);
    memset(v93, 0, sizeof(v93));
    memset((char *)&v93[5] + 4, 0, 0x82u);
    v93[22] = 0;
    v93[23] = 0;
    UpdateDownloadState = (*(__int64 (__fastcall **)(wchar_t *, OLECHAR *, struct tagDSUpdateMetadata *, _QWORD *, _QWORD *))(*(_QWORD *)v68 + 48LL))(
                            v68,
                            v21,
                            v11,
                            v86,
                            v93);
    if ( UpdateDownloadState < 0 )
      goto LABEL_90;
    LODWORD(v72) = v93[0];
    v76 = (struct tagDSUpdateMetadata *)v93[2];
    SusFree((void *)v93[4]);
    v93[4] = 0;
    LODWORD(v93[5]) = 0;
    v65 = 0;
    UpdateDownloadState = 0;
    if ( v63 )
    {
      CAgentDownloadManager::GetAggregateGenerateDownloadRequestProperties(
        v88,
        v25,
        (enum AggregateGDRProperties *)&UpdateDownloadState);
      v65 = UpdateDownloadState;
    }
    v68 = 0;
    v70 = 0;
    psz = 0;
    v60[0] = 0;
    v63 = 0;
    UpdateDownloadState = CAgentDownloadManager::GetCallInfoForUpdate(v88, v25, &v68, &v70, (char **)&psz, v60, &v63);
    if ( UpdateDownloadState < 0 )
    {
      v40 = v68;
      v42 = psz;
      goto LABEL_85;
    }
    *((_DWORD *)v25 + 32) = (_DWORD)v72;
    *((_QWORD *)v25 + 17) = v76;
    v34 = v21;
    v21 = 0;
    v80 = 0;
    v35 = v67;
    *(_QWORD *)&v67[1].Data1 = v34;
    v36 = v24;
    v24 = 0;
    v81 = 0;
    *(_QWORD *)v35[5].Data4 = v36;
    v69 = 0;
    v75 = 0;
    *(_QWORD *)v35[1].Data4 = v22;
    v37 = v11;
    v11 = 0;
    v73 = 0;
    *(_QWORD *)&v35[2].Data1 = v37;
    *(_DWORD *)v35[2].Data4 = v64;
    *v35 = v89;
    v38 = v65;
    *(_DWORD *)&v35[2].Data4[4] = v65 & 1;
    v35[3].Data1 = (v38 >> 1) & 1;
    v39 = v68;
    v40 = 0;
    v68 = 0;
    *(_QWORD *)v35[3].Data4 = v39;
    v35[4].Data1 = v70;
    v41 = psz;
    v42 = 0;
    psz = 0;
    *(_QWORD *)v35[4].Data4 = v41;
    v35[5].Data1 = v60[0];
    *(_DWORD *)&v35[7].Data2 = (v38 >> 5) & 1;
    v43 = MaxAppDownloadJobSize;
    *(_QWORD *)v35[12].Data4 = *((_QWORD *)MaxAppDownloadJobSize + 32);
    v35[13].Data1 = *((_DWORD *)v43 + 66);
    v35[11].Data1 = v63;
    v71 = 0;
    v74 = 0;
    *(_QWORD *)v35[13].Data4 = v33;
    v35[7].Data1 = 0;
    UpdateDownloadState = CAgentDownloadManager::GetFlightData(
                            v88,
                            &v89,
                            (const struct tagDsqUpdateId *)&v90,
                            (wchar_t **)&v35[6],
                            (wchar_t **)v35[6].Data4);
    if ( UpdateDownloadState >= 0 )
    {
      v44 = v67;
      v45 = *(_QWORD *)&v67[2].Data1;
      v46 = *(_DWORD *)(v45 + 120);
      if ( v46 != 12 )
      {
        if ( ((v46 - 1) & 0xFFFFFFF7) == 0 )
        {
          v48 = v65;
          *(_DWORD *)v67[7].Data4 = (v65 >> 2) & 1;
          *(_DWORD *)&v44[7].Data4[4] = (v48 >> 3) & 1;
          v44[8].Data1 = (v48 >> 4) & 1;
          if ( *(_DWORD *)(v45 + 120) == 1 )
          {
            UpdateDownloadState = DuplicateOptionalString<wchar_t const *,wchar_t *>(
                                    *((_QWORD *)MaxAppDownloadJobSize + 21),
                                    v44[8].Data4);
            if ( UpdateDownloadState < 0 )
              goto LABEL_85;
          }
          v72 = 0;
          UpdateDownloadState = CAgentDownloadManager::GetDatastoreSession(v88, &v72);
          v49 = v72;
          if ( UpdateDownloadState >= 0 )
          {
            v50 = (struct tagDSUpdateMetadata *)SusAlloc(0x280u);
            v88 = v50;
            v76 = v50;
            if ( v50 )
            {
              v60[0] = 0;
              UpdateDownloadState = UpdateHelper::GetAppCategoryMetadataForUpdate(
                                      v49,
                                      *(struct ISusEseSession **)&v67[2].Data1,
                                      (const struct UpdateMetadata *)8,
                                      (unsigned int)v50,
                                      (struct UpdateMetadata *)v60,
                                      v59);
              if ( UpdateDownloadState >= 0 )
              {
                if ( v60[0] )
                {
                  v76 = 0;
                  v52 = v67;
                  *(_QWORD *)v67[9].Data4 = v88;
                  v53 = *((unsigned __int8 *)MaxAppDownloadJobSize + 161);
                  *(_DWORD *)&v52[8].Data2 = v53;
                  if ( v53 || *(_DWORD *)&v52[2].Data4[4] && !v52[8].Data1 )
                  {
                    v57 = Trace::UpdateIdToString::UpdateIdToString(
                            (Trace::UpdateIdToString *)v84,
                            (const struct tagDSGlobalUpdateId *)&v77);
                    WUTrace(0, 0, 2, 4, 0, L"Disabling chunked mode for download. updateid: %ws", v57);
                    v56 = -1;
                  }
                  else
                  {
                    v88 = 0;
                    MaxAppDownloadJobSize = (struct DownloadManagerUpdateID *)-1LL;
                    if ( (int)CAgentServiceManager::GetServiceObjectHelper(v52, &v88) >= 0 )
                      MaxAppDownloadJobSize = (struct DownloadManagerUpdateID *)CSusService::GetMaxAppDownloadJobSize(v88);
                    if ( (unsigned int)AreTestKeysAllowed(1) )
                    {
                      v88 = 0;
                      v55 = RegQueryQwordValue(
                              v54,
                              L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                              L"MaxAppDownloadJobSize",
                              &v88);
                      v56 = (__int64)MaxAppDownloadJobSize;
                      if ( v55 >= 0 )
                        v56 = (__int64)v88;
                    }
                    else
                    {
                      v56 = (__int64)MaxAppDownloadJobSize;
                    }
                  }
                  *(_QWORD *)&v67[9].Data1 = v56;
                  if ( v49 )
                    (*(void (__fastcall **)(struct ISusEseSession *))(*(_QWORD *)v49 + 16LL))(v49);
                  goto LABEL_83;
                }
                v51 = Trace::UpdateIdToString::UpdateIdToString(
                        (Trace::UpdateIdToString *)v84,
                        (const struct tagDSGlobalUpdateId *)&v77);
                WUTrace(0, 0, 2, 3, 0, L"Unable to find app category for update %ws", v51);
                UpdateDownloadState = -2145120257;
              }
            }
            else
            {
              UpdateDownloadState = -2147024882;
            }
            if ( v88 )
            {
              DsqFreeObject(v88, 1u, 0x2FAFu, 1);
              SusFree(v88);
            }
          }
          if ( v49 )
            (*(void (__fastcall **)(struct ISusEseSession *))(*(_QWORD *)v49 + 16LL))(v49);
          goto LABEL_85;
        }
LABEL_83:
        UpdateDownloadState = 0;
        goto LABEL_85;
      }
      UpdateDownloadState = DuplicateOptionalString<wchar_t const *,wchar_t *>(v86[0], v67[10].Data4);
      if ( UpdateDownloadState >= 0 )
      {
        if ( v44 == (struct _GUID *)-160LL )
        {
          UpdateDownloadState = -2147467261;
          goto LABEL_85;
        }
        *(_QWORD *)&v44[10].Data1 = 0;
        UpdateDownloadState = CServiceBackup::GetServiceRegistryPath(&v89, v95, v47);
        if ( UpdateDownloadState < 0 )
          goto LABEL_85;
        if ( (int)RegQueryStringValue(-2147483646, v95, L"CountryCode", &v44[10]) < 0 )
          *(_QWORD *)&v44[10].Data1 = 0;
        v44[7].Data1 = *((_DWORD *)MaxAppDownloadJobSize + 12);
        goto LABEL_83;
      }
    }
LABEL_85:
    if ( v42 )
      SusFree(v42);
    if ( v40 )
      SusFree(v40);
    v22 = v69;
    goto LABEL_90;
  }
  updated = -2147024882;
LABEL_96:
  SysFreeString(v21);
LABEL_97:
  if ( v8 )
  {
    DsqFreeObject(v8, 1u, 0x2FAFu, 1);
    SusFree(v8);
  }
  if ( v11 )
  {
    DsqFreeObject(v11, 1u, 0x2FAFu, 1);
    SusFree(v11);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180092ab8  mov     [rsp-8+arg_18], rbx
0x180092abd  push    rbp
0x180092abe  push    rsi
0x180092abf  push    rdi
0x180092ac0  push    r12
0x180092ac2  push    r13
0x180092ac4  push    r14
0x180092ac6  push    r15
0x180092ac8  lea     rbp, [rsp-460h]
0x180092ad0  sub     rsp, 560h
0x180092ad7  mov     rax, cs:__security_cookie
0x180092ade  xor     rax, rsp
0x180092ae1  mov     [rbp+490h+var_40], rax
0x180092ae8  mov     r14d, r9d
0x180092aeb  mov     [rsp+590h+var_540], r9d
0x180092af0  mov     r15, r8
0x180092af3  mov     [rsp+590h+var_548], r8
0x180092af8  mov     [rsp+590h+var_520], rdx
0x180092afd  mov     rdi, rcx
0x180092b00  mov     [rbp+490h+var_390], rcx
0x180092b07  mov     rax, [rbp+490h+arg_20]
0x180092b0e  mov     [rsp+590h+var_528], rax
0x180092b13  xor     edx, edx; Val
0x180092b15  mov     r8d, 0E0h; Size
0x180092b1b  mov     rcx, rax; void *
0x180092b1e  call    memset
0x180092b23  movups  xmm0, xmmword ptr [r15+14h]
0x180092b28  movdqu  xmmword ptr [rbp+490h+var_388.Data1], xmm0
0x180092b30  movups  xmm1, xmmword ptr [r15]
0x180092b34  movups  [rbp+490h+var_4D8], xmm1
0x180092b38  mov     eax, [r15+10h]
0x180092b3c  mov     [rbp+490h+var_4C8], eax
0x180092b3f  xor     r13d, r13d
0x180092b42  mov     [rbp+490h+var_378], r13d
0x180092b49  movdqu  [rbp+490h+var_374], xmm1
0x180092b51  mov     [rbp+490h+var_364], eax
0x180092b57  mov     [rbp+490h+var_4F8], r13
0x180092b5b  mov     r12d, r13d
0x180092b5e  mov     [rbp+490h+var_508], r13
0x180092b62  mov     [rbp+490h+var_4F0], r13
0x180092b66  lea     rax, [rbp+490h+var_4F8]
0x180092b6a  mov     [rsp+590h+var_568], rax
0x180092b6f  lea     rax, [rbp+490h+var_388]
0x180092b76  mov     [rsp+590h+var_570], rax
0x180092b7b  xor     r9d, r9d
0x180092b7e  mov     r8d, 1E2Fh
0x180092b84  lea     rdx, [rbp+490h+var_378]
0x180092b8b  mov     rcx, rdi
0x180092b8e  call    ?LoadUpdateMetadataFromDatastore@CAgentDownloadManager@@AEAAJAEBUtagDsqUpdateId@@KW4UpdateMetadataPolicyFlags@@AEBU_GUID@@PEAPEAUtagDSUpdateMetadata@@@Z; CAgentDownloadManager::LoadUpdateMetadataFromDatastore(tagDsqUpdateId const &,ulong,UpdateMetadataPolicyFlags,_GUID const &,tagDSUpdateMetadata * *)
0x180092b93  mov     ebx, eax
0x180092b95  test    eax, eax
0x180092b97  jns     short loc_180092BD5
0x180092b99  lea     rdx, [rbp+490h+var_4D8]; struct tagDSGlobalUpdateId *
0x180092b9d  lea     rcx, [rbp+490h+var_420]; this
0x180092ba1  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180092ba6  mov     [rsp+590h+var_560], rax
0x180092bab  lea     rax, aLoadupdatemeta; "LoadUpdateMetadataFromDatastore for %ws"...
0x180092bb2  mov     [rsp+590h+var_568], rax
0x180092bb7  mov     dword ptr [rsp+590h+var_570], ebx
0x180092bbb  xor     edx, edx
0x180092bbd  xor     ecx, ecx
0x180092bbf  lea     r9d, [r13+3]
0x180092bc3  lea     r8d, [r13+2]
0x180092bc7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180092bcc  mov     rsi, [rbp+490h+var_4F8]
0x180092bd0  jmp     loc_18009359C
0x180092bd5  mov     rsi, [rbp+490h+var_4F8]
0x180092bd9  cmp     [rdi+5D0h], r13d
0x180092be0  jnz     loc_180092CD4
0x180092be6  test    r14d, r14d
0x180092be9  jz      loc_180092CD4
0x180092bef  call    ?AreRangeRequestsProhibitedByAdmin@@YAHXZ; AreRangeRequestsProhibitedByAdmin(void)
0x180092bf4  test    eax, eax
0x180092bf6  jnz     loc_180092CD4
0x180092bfc  lea     rbx, [rdi+268h]
0x180092c03  lea     r14, [rbx+8]
0x180092c07  test    rbx, rbx
0x180092c0a  jz      short loc_180092C15
0x180092c0c  mov     rcx, r14; lpCriticalSection
0x180092c0f  call    cs:__imp_EnterCriticalSection
0x180092c15  mov     rdx, r15
0x180092c18  lea     rcx, [rdi+5D8h]
0x180092c1f  call    ?GetIndexOf@?$CSusMap@UDownloadManagerUpdateID@@PEAVCCacheEntry@CDownloadDirNameCache@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpDelete@PEAVCCacheEntry@CDownloadDirNameCache@@@@@@QEBAKAEBUDownloadManagerUpdateID@@@Z; CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::GetIndexOf(DownloadManagerUpdateID const &)
0x180092c24  cmp     eax, [rdi+5ECh]
0x180092c2a  jb      short loc_180092C3C
0x180092c2c  test    rbx, rbx
0x180092c2f  jz      short loc_180092C66
0x180092c31  mov     rcx, r14; lpCriticalSection
0x180092c34  call    cs:__imp_LeaveCriticalSection
0x180092c3a  jmp     short loc_180092C66
0x180092c3c  mov     ecx, eax
0x180092c3e  shl     rcx, 6
0x180092c42  mov     rax, [rdi+5E0h]
0x180092c49  mov     edi, [rcx+rax]
0x180092c4c  shr     edi, 3
0x180092c4f  and     dil, 1
0x180092c53  test    rbx, rbx
0x180092c56  jz      short loc_180092C61
0x180092c58  mov     rcx, r14; lpCriticalSection
0x180092c5b  call    cs:__imp_LeaveCriticalSection
0x180092c61  test    dil, dil
0x180092c64  jnz     short loc_180092CD4
0x180092c66  mov     [rsp+590h+var_53C], 1
0x180092c6e  mov     [rsp+590h+var_518], r13
0x180092c73  lea     rdx, [rsp+590h+var_518]; struct CSusService **
0x180092c78  lea     rcx, [rbp+490h+var_388]; struct _GUID *
0x180092c7f  call    ?GetServiceObjectHelper@CAgentServiceManager@@SAJAEBU_GUID@@PEAPEAVCSusService@@@Z; CAgentServiceManager::GetServiceObjectHelper(_GUID const &,CSusService * *)
0x180092c84  test    eax, eax
0x180092c86  js      short loc_180092CFC
0x180092c88  mov     rcx, [rsp+590h+var_518]
0x180092c8d  mov     rax, [rcx]
0x180092c90  mov     rax, [rax+18h]
0x180092c94  call    _guard_dispatch_icall
0x180092c99  test    al, al
0x180092c9b  jz      short loc_180092CFC
0x180092c9d  mov     ecx, r13d
0x180092ca0  mov     r8d, [rsi+1D0h]
0x180092ca7  test    r8d, r8d
0x180092caa  jz      short loc_180092CFC
0x180092cac  mov     r9, [rsi+1D8h]
0x180092cb3  mov     eax, ecx
0x180092cb5  imul    rdx, rax, 0F8h
0x180092cbc  cmp     dword ptr [rdx+r9+70h], 2
0x180092cc2  jnz     short loc_180092CCB
0x180092cc4  cmp     [rdx+r9+28h], r13
0x180092cc9  jz      short loc_180092CD4
0x180092ccb  inc     ecx
0x180092ccd  cmp     ecx, r8d
0x180092cd0  jb      short loc_180092CB3
0x180092cd2  jmp     short loc_180092CFC
0x180092cd4  mov     [rsp+590h+var_53C], r13d
0x180092cd9  lea     rax, aAskingHandlerT; "Asking handler to generate non-range re"...
0x180092ce0  mov     [rsp+590h+var_568], rax
0x180092ce5  mov     [rsp+590h+var_570], r13
0x180092cea  xor     edx, edx
0x180092cec  xor     ecx, ecx
0x180092cee  lea     r9d, [rdx+4]
0x180092cf2  lea     r8d, [rdx+2]
0x180092cf6  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180092cfb  nop
0x180092cfc  mov     rbx, [r15+38h]
0x180092d00  xor     ecx, ecx; bstrString
0x180092d02  call    cs:__imp_SysFreeString
0x180092d08  mov     rdi, r13
0x180092d0b  mov     [rbp+490h+var_4B8], r13
0x180092d0f  test    rbx, rbx
0x180092d12  jz      short loc_180092D33
0x180092d14  mov     rcx, rbx; psz
0x180092d17  call    cs:__imp_SysAllocString
0x180092d1d  mov     rdi, rax
0x180092d20  mov     [rbp+490h+var_4B8], rax
0x180092d24  test    rax, rax
0x180092d27  jnz     short loc_180092D33
0x180092d29  mov     ebx, 8007000Eh
0x180092d2e  jmp     loc_180093592
0x180092d33  mov     [rbp+490h+var_4E8], r13
0x180092d37  lea     rcx, [rbp+490h+var_4E8]; struct CSusFileRequestList **
0x180092d3b  call    ?CreateInstance@CSusFileRequestList@@SAJPEAPEAV1@@Z; CSusFileRequestList::CreateInstance(CSusFileRequestList * *)
0x180092d40  mov     [rsp+590h+var_54C], eax
0x180092d44  mov     r13, [rbp+490h+var_4E8]
0x180092d48  mov     [rsp+590h+var_518], r13
0x180092d4d  test    eax, eax
0x180092d4f  js      loc_180093575
0x180092d55  mov     rax, [r13+0]
0x180092d59  mov     rdx, rdi
0x180092d5c  mov     rcx, r13
0x180092d5f  mov     rax, [rax+20h]
0x180092d63  call    _guard_dispatch_icall
0x180092d68  mov     [rsp+590h+var_54C], eax
0x180092d6c  test    eax, eax
0x180092d6e  js      loc_180093575
0x180092d74  xor     r14d, r14d
0x180092d77  mov     [rbp+490h+var_4C0], r14
0x180092d7b  test    byte ptr [r15+0C0h], 2
0x180092d83  jz      short loc_180092DBC
0x180092d85  lea     rcx, [rbp+490h+var_4C0]; struct CSusFileRequestList **
0x180092d89  call    ?CreateInstance@CSusFileRequestList@@SAJPEAPEAV1@@Z; CSusFileRequestList::CreateInstance(CSusFileRequestList * *)
0x180092d8e  mov     [rsp+590h+var_54C], eax
0x180092d92  mov     r14, [rbp+490h+var_4C0]
0x180092d96  test    eax, eax
0x180092d98  js      loc_18009355B
0x180092d9e  mov     rax, [r14]
0x180092da1  mov     rdx, rdi
0x180092da4  mov     rcx, r14
0x180092da7  mov     rax, [rax+20h]
0x180092dab  call    _guard_dispatch_icall
0x180092db0  mov     [rsp+590h+var_54C], eax
0x180092db4  test    eax, eax
0x180092db6  js      loc_18009355B
0x180092dbc  xor     r15d, r15d
0x180092dbf  mov     [rbp+490h+var_4B0], r15
0x180092dc3  mov     [rsp+590h+psz], r15
0x180092dc8  lea     r9, [rsp+590h+psz]; wchar_t **
0x180092dcd  mov     r12, [rsp+590h+var_548]
0x180092dd2  mov     r8, [r12+28h]; wchar_t *
0x180092dd7  lea     rdx, [rbp+490h+var_4D8]; struct tagDSGlobalUpdateId *
0x180092ddb  mov     rcx, [rbp+490h+var_390]; this
0x180092de2  call    ?GetUpdateDownloadVolumeFromDataStore@CAgentDownloadManager@@QEAAJAEBUtagDSGlobalUpdateId@@PEB_WPEAPEA_W@Z; CAgentDownloadManager::GetUpdateDownloadVolumeFromDataStore(tagDSGlobalUpdateId const &,wchar_t const *,wchar_t * *)
0x180092de7  mov     rbx, [rsp+590h+psz]
0x180092dec  test    eax, eax
0x180092dee  js      short loc_180092E28
0x180092df0  test    rbx, rbx
0x180092df3  jz      short loc_180092E28
0x180092df5  xor     ecx, ecx; bstrString
0x180092df7  call    cs:__imp_SysFreeString
0x180092dfd  mov     rcx, rbx; psz
0x180092e00  call    cs:__imp_SysAllocString
0x180092e06  mov     r15, rax
0x180092e09  mov     [rbp+490h+var_4B0], rax
0x180092e0d  test    rax, rax
0x180092e10  jnz     short loc_180092E28
0x180092e12  mov     rcx, rbx; pv
0x180092e15  call    cs:__imp_CoTaskMemFree
0x180092e1b  mov     [rsp+590h+var_54C], 8007000Eh
0x180092e23  jmp     loc_18009354E
0x180092e28  test    rbx, rbx
0x180092e2b  jz      short loc_180092E36
0x180092e2d  mov     rcx, rbx; pv
0x180092e30  call    cs:__imp_CoTaskMemFree
0x180092e36  xor     edx, edx; Val
0x180092e38  lea     r8d, [rdx+50h]; Size
0x180092e3c  lea     rcx, [rbp+490h+var_2A0]; void *
0x180092e43  call    memset
0x180092e48  lea     rax, [rbp+490h+var_2A0]
0x180092e4f  mov     [rsp+590h+var_570], rax; struct tagDSUpdateDLState *
0x180092e54  mov     r9d, 4; unsigned int
0x180092e5a  mov     r8, [r12+28h]; wchar_t *
0x180092e5f  lea     rdx, [rbp+490h+var_4D8]; struct LockedUpdateId *
0x180092e63  mov     rbx, [rbp+490h+var_390]
0x180092e6a  mov     rcx, rbx; this
0x180092e6d  call    ?GetUpdateDownloadState@CAgentDownloadManager@@AEAAJAEBULockedUpdateId@@PEB_WKPEAUtagDSUpdateDLState@@@Z; CAgentDownloadManager::GetUpdateDownloadState(LockedUpdateId const &,wchar_t const *,ulong,tagDSUpdateDLState *)
0x180092e72  mov     [rsp+590h+var_54C], eax
0x180092e76  test    eax, eax
0x180092e78  js      loc_18009354E
0x180092e7e  xorps   xmm0, xmm0
0x180092e81  xor     eax, eax
0x180092e83  movups  [rbp+490h+var_4A8], xmm0
0x180092e87  mov     [rbp+490h+var_498], eax
0x180092e8a  lea     rcx, [rbx+778h]
0x180092e91  lea     r8, [rbp+490h+var_4A8]
0x180092e95  mov     rdx, r12
0x180092e98  call    ?get_Value@?$CSusMap@UDownloadManagerUpdateID@@UtagDSGlobalUpdateId@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@QEBAJAEBUDownloadManagerUpdateID@@PEAUtagDSGlobalUpdateId@@@Z; CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::get_Value(DownloadManagerUpdateID const &,tagDSGlobalUpdateId *)
0x180092e9d  test    eax, eax
0x180092e9f  js      loc_180092F7C
0x180092ea5  lea     rdx, [rbp+490h+var_4D8]; struct tagDSGlobalUpdateId *
0x180092ea9  lea     rcx, [rbp+490h+var_420]; this
0x180092ead  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180092eb2  mov     rbx, rax
0x180092eb5  lea     rdx, [rbp+490h+var_4A8]; struct tagDSGlobalUpdateId *
0x180092eb9  lea     rcx, [rbp+490h+var_490]; this
0x180092ebd  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180092ec2  mov     [rsp+590h+var_558], rbx
0x180092ec7  mov     [rsp+590h+var_560], rax
0x180092ecc  lea     rax, aFindUpdateWsAs; "Find update %ws as alternate update of "...
0x180092ed3  mov     [rsp+590h+var_568], rax
0x180092ed8  mov     [rsp+590h+var_570], 0
0x180092ee1  mov     ebx, 2
0x180092ee6  lea     r9d, [rbx+2]
0x180092eea  mov     r8d, ebx
0x180092eed  xor     edx, edx
0x180092eef  xor     ecx, ecx
0x180092ef1  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180092ef6  lea     rax, [rbp+490h+var_4F0]
0x180092efa  mov     [rsp+590h+var_568], rax
0x180092eff  lea     rax, [rbp+490h+var_388]
0x180092f06  mov     [rsp+590h+var_570], rax
0x180092f0b  xor     r9d, r9d
0x180092f0e  lea     r8d, [rbx+1Eh]
0x180092f12  lea     rdx, [rbp+490h+var_4A8]
0x180092f16  mov     rcx, [rbp+490h+var_390]
0x180092f1d  call    ?GetUpdateMetadata@CAgentDownloadManager@@AEAAJAEBUtagDSGlobalUpdateId@@KW4UpdateMetadataPolicyFlags@@AEBU_GUID@@PEAPEAUtagDSUpdateMetadata@@@Z; CAgentDownloadManager::GetUpdateMetadata(tagDSGlobalUpdateId const &,ulong,UpdateMetadataPolicyFlags,_GUID const &,tagDSUpdateMetadata * *)
0x180092f22  mov     r12d, eax
0x180092f25  mov     [rsp+590h+var_54C], eax
0x180092f29  test    eax, eax
0x180092f2b  jns     short loc_180092F6D
0x180092f2d  lea     rdx, [rbp+490h+var_4D8]; struct tagDSGlobalUpdateId *
0x180092f31  lea     rcx, [rbp+490h+var_490]; this
0x180092f35  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180092f3a  mov     [rsp+590h+var_560], rax
0x180092f3f  lea     rax, aLoadupdatemeta_0; "LoadUpdateMetadataFromDatastore for alt"...
0x180092f46  mov     [rsp+590h+var_568], rax
0x180092f4b  mov     dword ptr [rsp+590h+var_570], r12d
0x180092f50  lea     r9d, [rbx+1]
0x180092f54  mov     r8d, ebx
0x180092f57  xor     edx, edx
0x180092f59  xor     ecx, ecx
0x180092f5b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180092f60  mov     rbx, [rbp+490h+var_4F0]
0x180092f64  mov     [rbp+490h+var_508], rbx
0x180092f68  jmp     loc_18009354E
0x180092f6d  mov     rbx, [rbp+490h+var_4F0]
0x180092f71  mov     [rbp+490h+var_508], rbx
0x180092f75  mov     r12, [rsp+590h+var_548]
0x180092f7a  jmp     short loc_180092F80
0x180092f7c  mov     rbx, [rbp+490h+var_508]
0x180092f80  xorps   xmm0, xmm0
0x180092f83  movdqu  [rbp+490h+var_3A0], xmm0
0x180092f8b  mov     rax, [rbp+490h+var_280]
0x180092f92  mov     [rbp+490h+var_3A8], rax
0x180092f99  mov     rax, [r12+28h]
  ... truncated ...
```
