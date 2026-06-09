# CAgentDownloadManager::CopyPatchFilesToCache(DownloadManagerUpdateID const &,tagDSUpdateMetadata *,ulong,wchar_t const * * const,CERT_HASH_BLOB *,ulong,wchar_t * const *,int)

- ea: `0x180096b78`
- end: `0x180097ae4`
- name: `?CopyPatchFilesToCache@CAgentDownloadManager@@AEAAJAEBUDownloadManagerUpdateID@@PEAUtagDSUpdateMetadata@@KQEAPEB_WPEAUCERT_HASH_BLOB@@KPEBQEA_WH@Z`
- size: `3948`
- prototype: `__int64 __fastcall(CAgentDownloadManager *this, const wchar_t **, struct tagDSUpdateMetadata *, unsigned int, wchar_t **, struct CERT_HASH_BLOB *, unsigned int, wchar_t **, int)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, reparse_path, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18009d924`

## callees

- `0x180034fbc`
- `0x1800365ac`
- `0x18007ef74`
- `0x18007f84c`
- `0x180092ab8`
- `0x1800958d4`
- `0x1800962b4`
- `0x1800963fc`
- `0x1800969e0`
- `0x180096b78`
- `0x18009f044`
- `0x1800ab4cc`
- `0x1800ad4d4`
- `0x1800ad5f8`
- `0x1800ae018`
- `0x1800ae430`
- `0x1800af79c`
- `0x1800b1cf0`
- `0x1800e8d8c`
- `0x1800ea0b4`
- `0x1800ea5e0`
- `0x1800ea6e0`
- `0x1800ea734`
- `0x1800ea784`
- `0x1800f4320`
- `0x180113a10`
- `0x180113ae8`
- `0x180113b9c`
- `0x180114950`
- `0x180114c0c`
- `0x180115bf0`
- `0x180127fb8`
- `0x18012b618`
- `0x18012bf80`
- `0x1801b75f0`
- `0x1801bc428`
- `0x180238960`
- `0x180238984`
- `0x180240cc0`
- `0x180240d40`
- `0x180241100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180097452`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180097452`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800971e4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180097276`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800971e4`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180097276`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180096c2b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180096c2b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096f04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800971a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800971ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009735b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180096f04`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800971a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800971ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009735b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180097172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009726d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180097a08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180097172`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009726d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180097a08`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180097322`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180097322`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800975aa`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800975aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180097596`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180097596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800973ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180097a7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180097a7d`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097975`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097a6e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097975`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180097a6e`

## string_xrefs

- `0x180096eb5`: `Another CopyUpdateToCache for the update %ws currently in progress.`
- `0x18009740b`: `CopyPatchFilesToCache calling GDR`
- `0x180097368`: `CopyPatchFilesToCache: Download request generation succeeded.`
- `0x180097691`: `Calling HandleDownloadJobCompletion for update %ws`
- `0x180097715`: `HandleDownloadJobCompletion for update %ws returned 0x%08x`

## pseudocode

```c
__int64 __fastcall CAgentDownloadManager::CopyPatchFilesToCache(
        CAgentDownloadManager *this,
        const wchar_t **a2,
        struct tagDSUpdateMetadata *a3,
        unsigned int a4,
        wchar_t **a5,
        struct CERT_HASH_BLOB *a6,
        unsigned int a7,
        wchar_t **a8,
        int a9)
{
  CAgentDownloadManager *v10; // rbx
  wchar_t *v11; // r15
  wchar_t *v12; // r14
  char v13; // di
  HANDLE EventW; // r12
  signed int LastError; // eax
  signed int v16; // ecx
  signed int v17; // eax
  signed int Value; // r13d
  char *v19; // rsi
  unsigned int v20; // eax
  unsigned int v21; // r13d
  int v22; // eax
  BOOL v23; // ecx
  unsigned int v24; // eax
  unsigned int v25; // eax
  __int64 v26; // r13
  __int64 i; // rcx
  unsigned int v28; // ecx
  unsigned int v29; // eax
  const struct DownloadManagerUpdateID *v30; // rdx
  int v31; // edx
  unsigned int v32; // ecx
  unsigned int v33; // eax
  __int64 v34; // r9
  unsigned __int64 v35; // rbx
  unsigned __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 updated; // rax
  __int64 v39; // r8
  __int64 v40; // r13
  bool v41; // si
  wchar_t *v42; // rax
  __int64 v43; // r9
  DownloadRequestMapEntry *v44; // rbx
  CAgentDownloadManager *v45; // rdi
  __int64 v46; // rcx
  char *v47; // rdi
  char v48; // al
  signed int v49; // eax
  __int64 v50; // rcx
  struct tagSusFileRequest *v51; // rdi
  struct ISusFileRequestList *FileRequestList; // rax
  int v53; // edi
  unsigned int v54; // r13d
  wchar_t *v55; // rsi
  struct ISusFileRequestList *v56; // rax
  struct ISusFileRequestList *v57; // rax
  HANDLE ProcessHeap; // rax
  wchar_t *v59; // rax
  const wchar_t *v60; // r8
  bool v61; // al
  unsigned int v62; // eax
  int v63; // ecx
  __int64 v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rdx
  unsigned int v68; // eax
  int v69; // ecx
  int v70; // r9d
  int v71; // r8d
  CAgentDownloadManager *v72; // rdi
  int v73; // r9d
  int v74; // ecx
  int v75; // eax
  unsigned int IndexOf; // eax
  int v77; // r9d
  int v79; // [rsp+20h] [rbp-E0h]
  struct ExtendedError *v80; // [rsp+28h] [rbp-D8h]
  unsigned int v81; // [rsp+28h] [rbp-D8h]
  wchar_t **v82; // [rsp+38h] [rbp-C8h]
  int v83; // [rsp+40h] [rbp-C0h]
  bool v84; // [rsp+50h] [rbp-B0h]
  unsigned int v85; // [rsp+54h] [rbp-ACh]
  char v88; // [rsp+68h] [rbp-98h]
  __int128 v90; // [rsp+78h] [rbp-88h] BYREF
  int v91; // [rsp+88h] [rbp-78h]
  unsigned int v92; // [rsp+90h] [rbp-70h]
  DownloadRequestMapEntry *v93; // [rsp+98h] [rbp-68h] BYREF
  LPCWSTR lpPathName; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v95; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t **v96; // [rsp+B0h] [rbp-50h]
  struct CERT_HASH_BLOB *v97; // [rsp+B8h] [rbp-48h]
  wchar_t **v98; // [rsp+C0h] [rbp-40h]
  struct tagDSFile *v99; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *v100; // [rsp+D0h] [rbp-30h]
  struct tagSusFileRequest *v101; // [rsp+D8h] [rbp-28h]
  wchar_t *v102; // [rsp+E0h] [rbp-20h]
  HANDLE v103; // [rsp+E8h] [rbp-18h]
  HANDLE v104; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v105; // [rsp+F8h] [rbp-8h] BYREF
  int v106; // [rsp+108h] [rbp+8h]
  struct _GUID v107; // [rsp+10Ch] [rbp+Ch]
  void *lpMem; // [rsp+120h] [rbp+20h]
  struct _GUID v109[14]; // [rsp+160h] [rbp+60h] BYREF
  unsigned int v110; // [rsp+240h] [rbp+140h] BYREF
  unsigned int v111; // [rsp+244h] [rbp+144h] BYREF
  int v112; // [rsp+248h] [rbp+148h] BYREF
  __int64 v113; // [rsp+250h] [rbp+150h] BYREF
  struct ISusUpdateDownloadRequest *v114; // [rsp+258h] [rbp+158h] BYREF
  int v115; // [rsp+260h] [rbp+160h] BYREF
  int v116; // [rsp+264h] [rbp+164h] BYREF
  __int64 v117; // [rsp+268h] [rbp+168h]
  int v118; // [rsp+270h] [rbp+170h]
  __int16 v119; // [rsp+274h] [rbp+174h]

  v92 = a4;
  v10 = this;
  v98 = a5;
  v97 = a6;
  v96 = a8;
  v117 = 0;
  v118 = 0;
  v119 = 101;
  v11 = 0;
  lpPathName = 0;
  v12 = 0;
  v100 = 0;
  v95 = 0;
  v114 = 0;
  v115 = 1;
  v13 = 1;
  EventW = CreateEventW(0, 1, 0, 0);
  v103 = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v16 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v16 = LastError;
    if ( v16 >= 0 )
    {
      Value = -2147467259;
    }
    else
    {
      v17 = GetLastError();
      Value = (unsigned __int16)v17 | 0x80070000;
      if ( v17 <= 0 )
        Value = v17;
    }
    goto LABEL_160;
  }
  lpMem = 0;
  v105 = 0;
  v106 = 0;
  v107 = c_idSrvNone;
  DownloadManagerUpdateID::operator=(&v105, a2);
  v104 = EventW;
  v19 = (char *)v10 + 1528;
  LODWORD(v113) = 0;
  v112 = 0;
  Value = CSusArrayList<CSusMap<DownloadManagerUpdateID,enum tagDownloadPriority,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum tagDownloadPriority>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum tagDownloadPriority,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum tagDownloadPriority>>::CMapEntryOps>::Grow(
            (char *)v10 + 1528,
            (unsigned int)(*((_DWORD *)v10 + 387) + 1));
  if ( Value >= 0 )
  {
    if ( *((_DWORD *)v10 + 388) || (v20 = *((_DWORD *)v10 + 387)) == 0 )
    {
      v21 = v113;
    }
    else
    {
      v21 = *((_DWORD *)v10 + 387);
      v113 = v20;
      v22 = CSusDownloadManagerUpdateIDListOps::Compare(
              (const struct DownloadManagerUpdateID *)&v105,
              (const struct DownloadManagerUpdateID *)(((unsigned __int64)(v20 - 1) << 6) + *((_QWORD *)v10 + 192) + 8LL));
      if ( v22 >= 0 )
      {
        v23 = v22 == 0;
        v112 = v23;
        goto LABEL_17;
      }
      *((_DWORD *)v10 + 388) = 1;
    }
    v23 = v112;
LABEL_17:
    if ( *((_DWORD *)v10 + 388) )
    {
      v24 = *((_DWORD *)v10 + 387);
      v110 = v24;
      if ( v24 )
      {
        v85 = 0;
        v25 = v24 >> 1;
        v26 = v25;
        LODWORD(v93) = v25;
        v111 = v25;
        for ( i = v25; ; i = v29 )
        {
          v30 = (const struct DownloadManagerUpdateID *)((i << 6) + *((_QWORD *)v10 + 192) + 8LL);
          v113 = v26;
          v31 = CSusDownloadManagerUpdateIDListOps::Compare((const struct DownloadManagerUpdateID *)&v105, v30);
          if ( !v31 )
            break;
          v24 = v110;
          if ( v31 <= 0 )
            v24 = (unsigned int)v93;
          v28 = v111 + 1;
          if ( v31 <= 0 )
            v28 = v85;
          v85 = v28;
          if ( v24 <= v28 )
          {
            v23 = v112;
            goto LABEL_29;
          }
          v110 = v24;
          v29 = (v28 + v24) >> 1;
          v93 = (DownloadRequestMapEntry *)v29;
          v26 = v29;
          v111 = v29;
        }
        goto LABEL_40;
      }
LABEL_29:
      if ( !v23 )
      {
        v21 = v24;
        v113 = v24;
        goto LABEL_31;
      }
    }
    else if ( !v23 )
    {
LABEL_31:
      Value = CSusSortedArrayList<CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::CMapEntryOps>::InternalValidate(
                (char *)v10 + 1528,
                &v104,
                v21);
      if ( Value >= 0 )
      {
        v32 = *((_DWORD *)v10 + 387);
        v33 = v113;
        if ( (unsigned int)v113 < v32 )
        {
          v34 = *((_QWORD *)v10 + 192);
          v35 = (unsigned __int64)(unsigned int)v113 << 6;
          memmove(
            (void *)(v34 + ((unsigned __int64)(unsigned int)(v113 + 1) << 6)),
            (const void *)(v34 + v35),
            (unsigned __int64)(v32 - (unsigned int)v113) << 6);
          memset((void *)(v35 + *((_QWORD *)v19 + 1)), 0, 0x40u);
          v10 = this;
          v33 = v113;
        }
        v36 = (unsigned __int64)v33 << 6;
        v37 = *((_QWORD *)v19 + 1);
        *(_QWORD *)(v36 + v37) = v104;
        DownloadManagerUpdateID::operator=(v36 + v37 + 8, &v105);
        ++*((_DWORD *)v19 + 5);
      }
      goto LABEL_35;
    }
LABEL_40:
    Value = -2145124333;
  }
LABEL_35:
  if ( lpMem )
    SusFree(lpMem);
  if ( Value == -2145124333 )
  {
    v90 = *(_OWORD *)a2;
    v91 = *((_DWORD *)a2 + 4);
    updated = Trace::UpdateIdToString::UpdateIdToString(
                (Trace::UpdateIdToString *)&v104,
                (const struct tagDSGlobalUpdateId *)&v90);
    WUTrace(0, 0, 2, 4, 0, L"Another CopyUpdateToCache for the update %ws currently in progress.", updated);
    Value = -2145124343;
    goto LABEL_160;
  }
  if ( Value >= 0 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v10 + 624));
    Value = CSusMap<enum tagEndpointType,CSLSEndpointProvider::EndpointDetails *,CSusSortedArrayListItemOpsBasic<enum tagEndpointType>,CSusSortedArrayListItemOpsDelete<CSLSEndpointProvider::EndpointDetails *>>::get_Value(
              (char *)v10 + 584,
              (char *)a3 + 120,
              &v95);
    if ( Value >= 0 )
    {
      v40 = *((_QWORD *)v10 + 27);
      if ( v114 )
      {
        (*(void (__fastcall **)(struct ISusUpdateDownloadRequest *))(*(_QWORD *)v114 + 16LL))(v114);
        v114 = 0;
      }
      Value = CUHHandlerManager::GetHandler(
                v40,
                *((unsigned int *)a3 + 30),
                v39,
                1,
                &GUID_dde28533_d0b1_4b84_8610_2d24fcdcb9c1,
                &v114);
      if ( Value >= 0 )
      {
        (*(void (__fastcall **)(struct ISusUpdateDownloadRequest *, struct tagDSUpdateMetadata *, int *))(*(_QWORD *)v114 + 128LL))(
          v114,
          a3,
          &v115);
        v41 = v115 == 1;
        v84 = v115 == 1;
        v12 = (wchar_t *)SafeSusAllocArray(0x104u, 2u);
        v100 = v12;
        Value = v12 == 0 ? 0x8007000E : 0;
        v13 = v41;
        if ( v12 )
        {
          v90 = *(_OWORD *)a2;
          v91 = *((_DWORD *)a2 + 4);
          Value = CAgentDownloadManager::GetUpdateDownloadPath(
                    v10,
                    (const struct tagDSGlobalUpdateId *)&v90,
                    a2[5],
                    v12,
                    0x104u);
          if ( Value >= 0 )
          {
            if ( v41 )
            {
              v90 = *(_OWORD *)a2;
              v91 = *((_DWORD *)a2 + 4);
              Value = CAgentDownloadManager::CreateCopyToCacheSandbox(
                        v10,
                        (const struct tagDSGlobalUpdateId *)&v90,
                        a2[5],
                        (wchar_t **)&lpPathName);
              v11 = (wchar_t *)lpPathName;
            }
            else
            {
              Value = SusMakeDirectoryW(v12, 0xAu, *((void **)v10 + 25));
              v13 = 0;
            }
            if ( Value >= 0 )
            {
              if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WUSAMultiMSURebase>::GetImpl'::`2'::impl)
                || !a9 )
              {
                goto LABEL_56;
              }
              v42 = v12;
              if ( v41 )
                v42 = v11;
              Value = CAgentDownloadManager::CopyPayloadFilesToSandbox(
                        v10,
                        (const struct DownloadManagerUpdateID *)a2,
                        a3,
                        v92,
                        (const wchar_t **const)v98,
                        v97,
                        a7,
                        v96,
                        v42);
              v13 = v41;
              if ( Value >= 0 )
              {
LABEL_56:
                while ( 1 )
                {
                  v93 = 0;
                  v88 = 1;
                  Value = WuSmartPtr::XPtrBase<DownloadRequestMapEntry,WuSmartPtr::Policies::STPolicy<DownloadRequestMapEntry>>::ReleaseAndAlloc(&v93);
                  if ( Value < 0 )
                  {
                    v13 = v41;
                    v44 = v93;
                    if ( !v93 )
                      break;
                    goto LABEL_158;
                  }
                  v43 = (__int64)v12;
                  if ( v41 )
                    v43 = (__int64)v11;
                  v44 = v93;
                  Value = DownloadRequestMapEntry::Init(
                            (__int64)v93,
                            (__int64)a2,
                            *((_DWORD *)a3 + 30),
                            v43,
                            0,
                            !v41,
                            0,
                            0,
                            0,
                            0);
                  if ( Value < 0 )
                    goto LABEL_142;
                  v45 = this;
                  do
                  {
                    if ( (unsigned int)CAgentDownloadManager::IsShuttingDown(v45) )
                    {
LABEL_144:
                      Value = -2145116152;
                      goto LABEL_142;
                    }
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v45 + 624));
                    v46 = v95;
                    if ( _InterlockedCompareExchange((volatile signed __int32 *)(v95 + 80), 1, 0) )
                    {
                      Value = CAgentDownloadManager::WaitForRequestGenerationCompleteOrShutdown(
                                v45,
                                *(void **)(v46 + 96));
                      if ( Value >= 0 )
                      {
                        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v45 + 624));
                        continue;
                      }
                      goto LABEL_142;
                    }
                    v111 = 0;
                    v110 = 0;
                    ResetEvent(*(HANDLE *)(v46 + 96));
                    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v45 + 624));
                    LODWORD(v113) = 0;
                    memset(v109, 0, sizeof(v109));
                    LOWORD(v112) = 105;
                    v116 = 0;
                    Value = CAgentDownloadManager::GetDownloadData(v45, (wchar_t *)v114, (const OLECHAR **)v44, 0, v109);
                    if ( Value < 0 )
                      goto LABEL_84;
                    *(_DWORD *)v109[2].Data4 = 0;
                    *(_DWORD *)&v109[2].Data4[4] = 1;
                    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v45 + 624));
                    while ( 1 )
                    {
                      if ( !ResetEvent(EventW) )
                      {
                        v49 = GetLastError();
                        Value = (unsigned __int16)v49 | 0x80070000;
                        if ( v49 <= 0 )
                          Value = v49;
                        if ( Value >= 0 )
                          Value = -2147418113;
LABEL_84:
                        if ( Value == -2145116152 && (unsigned int)CAgentDownloadManager::IsShuttingDown(v45) )
                          WUTrace(0, 0, 2, 4, 0, L"Operation cancelled due to shutdown.");
                        else
                          WUTrace(0, 0, 2, 3, Value, L"CopyPatchFilesToCache calling GDR");
                        v88 = 0;
                        goto LABEL_89;
                      }
                      if ( (unsigned int)CAgentDownloadManager::IsShuttingDown(v45) )
                        goto LABEL_144;
                      v47 = (char *)v45 + 96;
                      (*(void (__fastcall **)(char *))(*(_QWORD *)v47 + 8LL))(v47);
                      Value = (*(__int64 (__fastcall **)(struct ISusUpdateDownloadRequest *, struct _GUID *, char *, unsigned int *, unsigned int *, int *, __int64 *, int *))(*(_QWORD *)v114 + 24LL))(
                                v114,
                                v109,
                                v47,
                                &v111,
                                &v110,
                                &v112,
                                &v113,
                                &v116);
                      (*(void (__fastcall **)(char *))(*(_QWORD *)v47 + 16LL))(v47);
                      if ( Value != -2145124343 )
                        break;
                      if ( v110 )
                      {
                        Sleep(0x7D0u);
                        v45 = this;
                      }
                      else
                      {
                        v45 = this;
                        Value = CAgentDownloadManager::WaitForRequestGenerationCompleteOrShutdown(this, EventW);
                        if ( Value < 0 )
                          goto LABEL_76;
                      }
                    }
                    v45 = this;
LABEL_76:
                    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v45 + 624));
                    if ( Value < 0 )
                      goto LABEL_84;
                    WUTrace(0, 0, 2, 4, 0, L"CopyPatchFilesToCache: Download request generation succeeded.");
                    Value = DownloadRequestMapEntry::MakeComplete(
                              v44,
                              *(struct ISusFileRequestList **)v109[1].Data4,
                              *(const wchar_t **)&v109[1].Data1,
                              1);
                    v48 = v88;
                    if ( Value < 0 )
                      v48 = 0;
                    v88 = v48;
                    *(_QWORD *)v109[1].Data4 = 0;
LABEL_89:
                    SusFreeDownloadData((struct tagSusDownloadData *)v109);
                    v50 = v95;
                    _InterlockedCompareExchange((volatile signed __int32 *)(v95 + 80), 0, 1);
                    SetEvent(*(HANDLE *)(v50 + 96));
                  }
                  while ( !(unsigned int)DownloadRequestMapEntry::IsComplete(v44) && v88 );
                  v51 = 0;
                  if ( !v88 )
                    goto LABEL_142;
                  if ( (unsigned int)DownloadRequestMapEntry::IsComplete(v44) )
                  {
                    v110 = 0;
                    FileRequestList = DownloadRequestMapEntry::GetFileRequestList(v44);
                    Value = (*(__int64 (__fastcall **)(struct ISusFileRequestList *, unsigned int *))(*(_QWORD *)FileRequestList + 56LL))(
                              FileRequestList,
                              &v110);
                    if ( Value >= 0 )
                    {
                      if ( !v110 )
                      {
                        v53 = 1;
                        goto LABEL_133;
                      }
                      v99 = 0;
                      v54 = 0;
                      v111 = 0;
LABEL_99:
                      v101 = 0;
                      v55 = 0;
                      v102 = 0;
                      if ( (unsigned int)CAgentDownloadManager::IsShuttingDown(this) )
                      {
                        Value = -2145116152;
                      }
                      else
                      {
                        v51 = (struct tagSusFileRequest *)SusAlloc(0x30u);
                        v101 = v51;
                        if ( v51 )
                        {
                          v56 = DownloadRequestMapEntry::GetFileRequestList(v44);
                          Value = FindFileInUpdateMetadata(v56, v54, a3, &v99);
                          if ( Value < 0 )
                            goto LABEL_125;
                          v57 = DownloadRequestMapEntry::GetFileRequestList(v44);
                          Value = (*(__int64 (__fastcall **)(struct ISusFileRequestList *, _QWORD, struct tagSusFileRequest *))(*(_QWORD *)v57 + 120LL))(
                                    v57,
                                    v111,
                                    v51);
                          if ( Value < 0 )
                            goto LABEL_125;
                          if ( *((_DWORD *)v51 + 6) )
                          {
                            Value = -2145095681;
                            goto LABEL_125;
                          }
                          ProcessHeap = GetProcessHeap();
                          v59 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, 0x208u);
                          v55 = v59;
                          v102 = v59;
                          if ( v59 )
                          {
                            v60 = v12;
                            if ( v84 )
                              v60 = v11;
                            Value = WUPathCchCombine(v59, 0x104u, v60, *((const wchar_t **)v51 + 1));
                            if ( Value < 0 )
                              goto LABEL_125;
                            v61 = v84;
                            if ( !v84 )
                            {
                              v62 = *((_DWORD *)a3 + 30);
                              if ( v62 == 8 || v62 <= 0xC && (v63 = 5650, _bittest(&v63, v62)) )
                                v64 = 11;
                              else
                                v64 = 3;
                              v83 = a7;
                              LODWORD(v80) = v92;
                              Value = CAgentDownloadManager::MatchAndCopyFileToCache(
                                        this,
                                        v64,
                                        a2,
                                        v99,
                                        v55,
                                        v80,
                                        v98,
                                        v97);
                              if ( Value < 0 )
                                goto LABEL_125;
                              v90 = *(_OWORD *)a2;
                              v91 = *((_DWORD *)a2 + 4);
                              v65 = Trace::UpdateIdToString::UpdateIdToString(
                                      (Trace::UpdateIdToString *)&v104,
                                      (const struct tagDSGlobalUpdateId *)&v90);
                              WUTrace(0, 0, 2, 5, 0, L"Calling HandleDownloadJobCompletion for update %ws", v65);
                              Value = (*(__int64 (__fastcall **)(struct ISusUpdateDownloadRequest *, struct tagDSUpdateMetadata *, _QWORD, wchar_t *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v114 + 56LL))(
                                        v114,
                                        a3,
                                        *((_QWORD *)v44 + 7),
                                        v55,
                                        *(_QWORD *)v51,
                                        0,
                                        0);
                              v90 = *(_OWORD *)a2;
                              v91 = *((_DWORD *)a2 + 4);
                              v66 = Trace::UpdateIdToString::UpdateIdToString(
                                      (Trace::UpdateIdToString *)&v104,
                                      (const struct tagDSGlobalUpdateId *)&v90);
                              LODWORD(v82) = Value;
                              WUTrace(
                                0,
                                0,
                                2,
                                5,
                                0,
                                L"HandleDownloadJobCompletion for update %ws returned 0x%08x",
                                v66,
                                v82);
                              if ( Value != -2147467263 )
                                goto LABEL_125;
                              v61 = 0;
                            }
                            v67 = 4 * !v61 + 1;
                            v68 = *((_DWORD *)a3 + 30);
                            if ( v68 == 8 || v68 <= 0xC && (v69 = 5650, _bittest(&v69, v68)) )
                              v67 = (unsigned int)v67 | 8;
                            v83 = a7;
                            LODWORD(v80) = v92;
                            Value = CAgentDownloadManager::MatchAndCopyFileToCache(
                                      this,
                                      v67,
                                      a2,
                                      v99,
                                      v55,
                                      v80,
                                      v98,
                                      v97);
                            goto LABEL_125;
                          }
                        }
                        Value = -2147024882;
                      }
LABEL_125:
                      UHFreeObject(v51);
                      if ( Value < 0 )
                      {
                        if ( v55 )
                          SusFree(v55);
                        if ( v51 )
                          SusFree(v51);
                        if ( v44 )
                        {
                          DownloadRequestMapEntry::~DownloadRequestMapEntry(v44);
                          operator delete(v44, (const struct std::nothrow_t *)0x110);
                        }
                        v13 = v84;
                        break;
                      }
                      if ( v55 )
                        SusFree(v55);
                      if ( v51 )
                        SusFree(v51);
                      v54 = v111 + 1;
                      v111 = v54;
                      if ( v54 >= v110 )
                      {
                        v41 = v84;
                        goto LABEL_132;
                      }
                      v51 = 0;
                      goto LABEL_99;
                    }
LABEL_142:
                    if ( v44 )
                    {
LABEL_158:
                      DownloadRequestMapEntry::~DownloadRequestMapEntry(v44);
                      operator delete(v44, (const struct std::nothrow_t *)0x110);
                    }
                    v13 = v41;
                    break;
                  }
LABEL_132:
                  v53 = 0;
LABEL_133:
                  if ( v44 )
                  {
                    DownloadRequestMapEntry::~DownloadRequestMapEntry(v44);
                    operator delete(v44, (const struct std::nothrow_t *)0x110);
                  }
                  if ( v53 )
                  {
                    if ( v41 )
                    {
                      LODWORD(v113) = 0;
                      v90 = *(_OWORD *)a2;
                      v91 = *((_DWORD *)a2 + 4);
                      Value = CAgentDownloadManager::SetUpdateDownloadStatus(
                                this,
                                &v90,
                                a2[5],
                                &v113,
                                *((_DWORD *)a2 + 12));
                      v13 = v41;
                      if ( Value < 0 )
                        break;
                      Value = SusDeleteDirectoryW(v12, 1, 1, v70, 1, 0, 0xAu, *((void **)this + 25), v83);
                      if ( Value < 0 )
                        break;
                      v72 = this;
                      Value = SusMoveDirectoryContents(v11, v12, v71, 0, v79, v81, *((void **)this + 25));
                      if ( Value < 0 )
                      {
                        SusDeleteDirectoryW(v12, 1, 1, v73, 1, 0, 0xAu, *((void **)this + 25), v83);
LABEL_141:
                        v13 = v41;
                        break;
                      }
                      RemoveDirectoryW(v11);
                    }
                    else
                    {
                      v72 = this;
                    }
                    v74 = *((_DWORD *)a2 + 12);
                    v75 = 1;
                    if ( v74 == 1 )
                      v75 = 5;
                    LODWORD(v113) = v75;
                    v90 = *(_OWORD *)a2;
                    v91 = *((_DWORD *)a2 + 4);
                    Value = CAgentDownloadManager::SetUpdateDownloadStatus(v72, &v90, a2[5], &v113, v74);
                    goto LABEL_141;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_160:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  IndexOf = CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::GetIndexOf(
              (char *)this + 1528,
              a2);
  if ( IndexOf < *((_DWORD *)this + 387) )
    CSusArrayList<CSusMap<DownloadManagerUpdateID,enum tagDownloadPriority,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum tagDownloadPriority>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum tagDownloadPriority,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum tagDownloadPriority>>::CMapEntryOps>::RemoveArraySection(
      (char *)this + 1528,
      IndexOf,
      IndexOf,
      1);
  if ( Value < 0 && v13 )
  {
    SusDeleteDirectoryW(v11, 1, 1, v77, 1, 0, 0, 0, v83);
    RemoveDirectoryW(v11);
  }
  if ( EventW )
    CloseHandle(EventW);
  if ( v114 )
  {
    (*(void (__fastcall **)(struct ISusUpdateDownloadRequest *))(*(_QWORD *)v114 + 16LL))(v114);
    v114 = 0;
  }
  if ( v12 )
    SusFree(v12);
  if ( v11 )
    SusFree(v11);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180096b78  push    rbp
0x180096b7a  push    rbx
0x180096b7b  push    rsi
0x180096b7c  push    rdi
0x180096b7d  push    r12
0x180096b7f  push    r13
0x180096b81  push    r14
0x180096b83  push    r15
0x180096b85  lea     rbp, [rsp-188h]
0x180096b8d  sub     rsp, 288h
0x180096b94  mov     rax, cs:__security_cookie
0x180096b9b  xor     rax, rsp
0x180096b9e  mov     [rbp+1C0h+var_48], rax
0x180096ba5  mov     [rbp+1C0h+var_230], r9d
0x180096ba9  mov     [rsp+2C0h+var_250], r8
0x180096bae  mov     rsi, rdx
0x180096bb1  mov     [rsp+2C0h+var_260], rdx
0x180096bb6  mov     rbx, rcx
0x180096bb9  mov     [rsp+2C0h+var_268], rcx
0x180096bbe  mov     rax, [rbp+1C0h+arg_20]
0x180096bc5  mov     [rbp+1C0h+var_200], rax
0x180096bc9  mov     rax, [rbp+1C0h+arg_28]
0x180096bd0  mov     [rbp+1C0h+var_208], rax
0x180096bd4  mov     rax, [rbp+1C0h+arg_38]
0x180096bdb  mov     [rbp+1C0h+var_210], rax
0x180096bdf  xor     r13d, r13d
0x180096be2  mov     [rbp+1C0h+var_58], r13
0x180096be9  mov     [rbp+1C0h+var_50], r13d
0x180096bf0  lea     eax, [r13+65h]
0x180096bf4  mov     [rbp+1C0h+var_4C], ax
0x180096bfb  mov     r15d, r13d
0x180096bfe  mov     [rbp+1C0h+lpPathName], r13
0x180096c02  mov     r14d, r13d
0x180096c05  mov     [rbp+1C0h+var_1F0], r13
0x180096c09  mov     [rbp+1C0h+var_218], r13
0x180096c0d  mov     [rbp+1C0h+var_68], r13
0x180096c14  lea     eax, [r13+1]
0x180096c18  mov     [rbp+1C0h+var_60], eax
0x180096c1e  mov     dil, al
0x180096c21  xor     r9d, r9d; lpName
0x180096c24  xor     r8d, r8d; bInitialState
0x180096c27  mov     edx, eax; bManualReset
0x180096c29  xor     ecx, ecx; lpEventAttributes
0x180096c2b  call    cs:__imp_CreateEventW
0x180096c31  mov     r12, rax
0x180096c34  mov     [rbp+1C0h+var_1D8], rax
0x180096c38  test    rax, rax
0x180096c3b  jnz     short loc_180096C7B
0x180096c3d  call    cs:__imp_GetLastError
0x180096c43  movzx   ecx, ax
0x180096c46  mov     ebx, 80070000h
0x180096c4b  or      ecx, ebx
0x180096c4d  test    eax, eax
0x180096c4f  cmovle  ecx, eax
0x180096c52  test    ecx, ecx
0x180096c54  jns     short loc_180096C70
0x180096c56  call    cs:__imp_GetLastError
0x180096c5c  movzx   r13d, ax
0x180096c60  or      r13d, ebx
0x180096c63  xor     ebx, ebx
0x180096c65  test    eax, eax
0x180096c67  cmovle  r13d, eax
0x180096c6b  jmp     loc_1800979FC
0x180096c70  mov     r13d, 80004005h
0x180096c76  jmp     loc_1800979FA
0x180096c7b  mov     [rbp+1C0h+lpMem], r13
0x180096c7f  xorps   xmm0, xmm0
0x180096c82  xor     eax, eax
0x180096c84  movups  [rbp+1C0h+var_1C8], xmm0
0x180096c88  mov     [rbp+1C0h+var_1B8], eax
0x180096c8b  movups  xmm0, xmmword ptr cs:c_idSrvNone.Data1
0x180096c92  movdqu  [rbp+1C0h+var_1B4], xmm0
0x180096c97  mov     rdx, rsi
0x180096c9a  lea     rcx, [rbp+1C0h+var_1C8]
0x180096c9e  call    ??4DownloadManagerUpdateID@@QEAAXAEBU0@@Z; DownloadManagerUpdateID::operator=(DownloadManagerUpdateID const &)
0x180096ca3  mov     [rbp+1C0h+var_1D0], r12
0x180096ca7  lea     rsi, [rbx+5F8h]
0x180096cae  mov     dword ptr [rbp+1C0h+var_70], r13d
0x180096cb5  mov     [rbp+1C0h+var_78], r13d
0x180096cbc  mov     edx, [rsi+14h]
0x180096cbf  inc     edx
0x180096cc1  mov     rcx, rsi
0x180096cc4  call    ?Grow@?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@W4tagDownloadPriority@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@W4tagDownloadPriority@@@@@@VCMapEntryOps@2@@@QEAAJK@Z; CSusArrayList<CSusMap<DownloadManagerUpdateID,tagDownloadPriority,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDownloadPriority>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,tagDownloadPriority,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDownloadPriority>>::CMapEntryOps>::Grow(ulong)
0x180096cc9  mov     r13d, eax
0x180096ccc  xor     r8d, r8d
0x180096ccf  test    eax, eax
0x180096cd1  js      loc_180096E78
0x180096cd7  cmp     [rsi+18h], r8d
0x180096cdb  jnz     short loc_180096D27
0x180096cdd  mov     eax, [rsi+14h]
0x180096ce0  test    eax, eax
0x180096ce2  jz      short loc_180096D27
0x180096ce4  mov     r13d, eax
0x180096ce7  mov     [rbp+1C0h+var_70], r13
0x180096cee  lea     ecx, [rax-1]
0x180096cf1  shl     rcx, 6
0x180096cf5  mov     rdx, [rsi+8]
0x180096cf9  add     rdx, 8
0x180096cfd  add     rdx, rcx; struct DownloadManagerUpdateID *
0x180096d00  lea     rcx, [rbp+1C0h+var_1C8]; struct DownloadManagerUpdateID *
0x180096d04  call    ?Compare@CSusDownloadManagerUpdateIDListOps@@SAHAEBUDownloadManagerUpdateID@@0@Z; CSusDownloadManagerUpdateIDListOps::Compare(DownloadManagerUpdateID const &,DownloadManagerUpdateID const &)
0x180096d09  xor     r8d, r8d
0x180096d0c  test    eax, eax
0x180096d0e  js      short loc_180096D1E
0x180096d10  mov     ecx, r8d
0x180096d13  setz    cl
0x180096d16  mov     [rbp+1C0h+var_78], ecx
0x180096d1c  jmp     short loc_180096D34
0x180096d1e  mov     dword ptr [rsi+18h], 1
0x180096d25  jmp     short loc_180096D2E
0x180096d27  mov     r13, [rbp+1C0h+var_70]
0x180096d2e  mov     ecx, [rbp+1C0h+var_78]
0x180096d34  cmp     [rsi+18h], r8d
0x180096d38  jz      loc_180096EE4
0x180096d3e  mov     eax, [rsi+14h]
0x180096d41  mov     [rbp+1C0h+var_80], eax
0x180096d47  test    eax, eax
0x180096d49  jz      loc_180096DD4
0x180096d4f  mov     [rsp+2C0h+var_26C], r8d
0x180096d54  shr     eax, 1
0x180096d56  mov     r13d, eax
0x180096d59  mov     dword ptr [rbp+1C0h+var_228], r13d
0x180096d5d  mov     [rbp+1C0h+var_7C], r13d
0x180096d64  mov     ecx, eax
0x180096d66  jmp     short loc_180096DA4
0x180096d68  mov     eax, [rbp+1C0h+var_80]
0x180096d6e  test    edx, edx
0x180096d70  cmovle  eax, dword ptr [rbp+1C0h+var_228]
0x180096d74  mov     ecx, [rbp+1C0h+var_7C]
0x180096d7a  inc     ecx
0x180096d7c  test    edx, edx
0x180096d7e  cmovle  ecx, [rsp+2C0h+var_26C]
0x180096d83  mov     [rsp+2C0h+var_26C], ecx
0x180096d87  cmp     eax, ecx
0x180096d89  jbe     short loc_180096DCE
0x180096d8b  mov     [rbp+1C0h+var_80], eax
0x180096d91  add     eax, ecx
0x180096d93  shr     eax, 1
0x180096d95  mov     [rbp+1C0h+var_228], rax
0x180096d99  mov     r13d, eax
0x180096d9c  mov     [rbp+1C0h+var_7C], eax
0x180096da2  mov     ecx, eax
0x180096da4  mov     rdx, [rsi+8]
0x180096da8  shl     rcx, 6
0x180096dac  add     rdx, 8
0x180096db0  add     rdx, rcx; struct DownloadManagerUpdateID *
0x180096db3  mov     [rbp+1C0h+var_70], r13
0x180096dba  lea     rcx, [rbp+1C0h+var_1C8]; struct DownloadManagerUpdateID *
0x180096dbe  call    ?Compare@CSusDownloadManagerUpdateIDListOps@@SAHAEBUDownloadManagerUpdateID@@0@Z; CSusDownloadManagerUpdateIDListOps::Compare(DownloadManagerUpdateID const &,DownloadManagerUpdateID const &)
0x180096dc3  test    eax, eax
0x180096dc5  mov     edx, eax
0x180096dc7  jnz     short loc_180096D68
0x180096dc9  jmp     loc_180096EEC
0x180096dce  mov     ecx, [rbp+1C0h+var_78]
0x180096dd4  test    ecx, ecx
0x180096dd6  jnz     loc_180096EEC
0x180096ddc  mov     r13d, eax
0x180096ddf  mov     [rbp+1C0h+var_70], r13
0x180096de6  mov     r8d, r13d
0x180096de9  lea     rdx, [rbp+1C0h+var_1D0]
0x180096ded  mov     rcx, rsi
0x180096df0  call    ?InternalValidate@?$CSusSortedArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@W4RetryStatus@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@W4RetryStatus@@@@@@VCMapEntryOps@2@@@IEBAJAEBU_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@W4RetryStatus@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@W4RetryStatus@@@@@@K@Z; CSusSortedArrayList<CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::CMapEntryOps>::InternalValidate(CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry const &,ulong)
0x180096df5  mov     r13d, eax
0x180096df8  test    eax, eax
0x180096dfa  js      short loc_180096E78
0x180096dfc  mov     ecx, [rsi+14h]
0x180096dff  mov     rax, [rbp+1C0h+var_70]
0x180096e06  cmp     eax, ecx
0x180096e08  jnb     short loc_180096E4E
0x180096e0a  mov     r9, [rsi+8]
0x180096e0e  mov     ebx, eax
0x180096e10  shl     rbx, 6
0x180096e14  sub     ecx, eax
0x180096e16  mov     r8d, ecx
0x180096e19  shl     r8, 6; Size
0x180096e1d  lea     rdx, [r9+rbx]; Src
0x180096e21  lea     ecx, [rax+1]
0x180096e24  shl     rcx, 6
0x180096e28  add     rcx, r9; void *
0x180096e2b  call    memmove
0x180096e30  mov     rcx, [rsi+8]
0x180096e34  add     rcx, rbx; void *
0x180096e37  xor     edx, edx; Val
0x180096e39  lea     r8d, [rdx+40h]; Size
0x180096e3d  call    memset
0x180096e42  mov     rbx, [rsp+2C0h+var_268]
0x180096e47  mov     rax, [rbp+1C0h+var_70]
0x180096e4e  mov     edx, eax
0x180096e50  shl     rdx, 6
0x180096e54  mov     rcx, [rsi+8]
0x180096e58  mov     rax, [rbp+1C0h+var_1D0]
0x180096e5c  mov     [rdx+rcx], rax
0x180096e60  add     rcx, 8
0x180096e64  add     rcx, rdx
0x180096e67  lea     rdx, [rbp+1C0h+var_1C8]
0x180096e6b  call    ??4DownloadManagerUpdateID@@QEAAXAEBU0@@Z; DownloadManagerUpdateID::operator=(DownloadManagerUpdateID const &)
0x180096e70  mov     ecx, 1
0x180096e75  add     [rsi+14h], ecx
0x180096e78  mov     rcx, [rbp+1C0h+lpMem]; lpMem
0x180096e7c  test    rcx, rcx
0x180096e7f  jz      short loc_180096E86
0x180096e81  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x180096e86  cmp     r13d, 80240013h
0x180096e8d  jnz     short loc_180096EF4
0x180096e8f  mov     rax, [rsp+2C0h+var_260]
0x180096e94  movups  xmm0, xmmword ptr [rax]
0x180096e97  movups  [rsp+2C0h+var_248], xmm0
0x180096e9c  mov     eax, [rax+10h]
0x180096e9f  mov     [rbp+1C0h+var_238], eax
0x180096ea2  lea     rdx, [rsp+2C0h+var_248]; struct tagDSGlobalUpdateId *
0x180096ea7  lea     rcx, [rbp+1C0h+var_1D0]; this
0x180096eab  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180096eb0  mov     [rsp+2C0h+var_290], rax
0x180096eb5  lea     rax, aAnotherCopyupd; "Another CopyUpdateToCache for the updat"...
0x180096ebc  mov     [rsp+2C0h+var_298], rax
0x180096ec1  xor     ebx, ebx
0x180096ec3  mov     [rsp+2C0h+var_2A0], rbx
0x180096ec8  xor     edx, edx
0x180096eca  xor     ecx, ecx
0x180096ecc  lea     r9d, [rbx+4]
0x180096ed0  lea     r8d, [rbx+2]
0x180096ed4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180096ed9  mov     r13d, 80240009h
0x180096edf  jmp     loc_1800979FC
0x180096ee4  test    ecx, ecx
0x180096ee6  jz      loc_180096DE6
0x180096eec  mov     r13d, 80240013h
0x180096ef2  jmp     short loc_180096E78
0x180096ef4  test    r13d, r13d
0x180096ef7  js      loc_1800979FA
0x180096efd  lea     rcx, [rbx+270h]; lpCriticalSection
0x180096f04  call    cs:__imp_EnterCriticalSection
0x180096f0a  mov     rsi, [rsp+2C0h+var_250]
0x180096f0f  lea     rcx, [rbx+248h]
0x180096f16  lea     r8, [rbp+1C0h+var_218]
0x180096f1a  lea     rdx, [rsi+78h]
0x180096f1e  call    ?get_Value@?$CSusMap@W4tagEndpointType@@PEAUEndpointDetails@CSLSEndpointProvider@@V?$CSusSortedArrayListItemOpsBasic@W4tagEndpointType@@@@V?$CSusSortedArrayListItemOpsDelete@PEAUEndpointDetails@CSLSEndpointProvider@@@@@@QEBAJAEBW4tagEndpointType@@PEAPEAUEndpointDetails@CSLSEndpointProvider@@@Z; CSusMap<tagEndpointType,CSLSEndpointProvider::EndpointDetails *,CSusSortedArrayListItemOpsBasic<tagEndpointType>,CSusSortedArrayListItemOpsDelete<CSLSEndpointProvider::EndpointDetails *>>::get_Value(tagEndpointType const &,CSLSEndpointProvider::EndpointDetails * *)
0x180096f23  mov     r13d, eax
0x180096f26  test    eax, eax
0x180096f28  js      loc_1800979FA
0x180096f2e  mov     r13, [rbx+0D8h]
0x180096f35  mov     rcx, [rbp+1C0h+var_68]
0x180096f3c  test    rcx, rcx
0x180096f3f  jz      short loc_180096F56
0x180096f41  mov     rax, [rcx]
0x180096f44  mov     rax, [rax+10h]
0x180096f48  call    _guard_dispatch_icall
0x180096f4d  xor     edx, edx
0x180096f4f  mov     [rbp+1C0h+var_68], rdx
0x180096f56  lea     rax, [rbp+1C0h+var_68]
0x180096f5d  mov     [rsp+2C0h+var_298], rax
0x180096f62  lea     rax, _GUID_dde28533_d0b1_4b84_8610_2d24fcdcb9c1
0x180096f69  mov     [rsp+2C0h+var_2A0], rax
0x180096f6e  mov     r9d, 1
0x180096f74  mov     edx, [rsi+78h]
0x180096f77  mov     rcx, r13
0x180096f7a  call    ?GetHandler@CUHHandlerManager@@QEAAJW4tagUHUpdateHandler@@HHAEBU_GUID@@PEAPEAX@Z; CUHHandlerManager::GetHandler(tagUHUpdateHandler,int,int,_GUID const &,void * *)
0x180096f7f  mov     r13d, eax
0x180096f82  test    eax, eax
0x180096f84  js      loc_1800979FA
0x180096f8a  mov     rcx, [rbp+1C0h+var_68]
0x180096f91  mov     rax, [rcx]
0x180096f94  lea     r8, [rbp+1C0h+var_60]
0x180096f9b  mov     rdx, rsi
0x180096f9e  mov     rax, [rax+80h]
0x180096fa5  call    _guard_dispatch_icall
0x180096faa  mov     eax, 1
0x180096faf  cmp     [rbp+1C0h+var_60], eax
0x180096fb5  setz    sil
0x180096fb9  mov     [rsp+2C0h+var_270], sil
0x180096fbe  lea     edx, [rax+1]; unsigned __int64
0x180096fc1  mov     ecx, 104h; unsigned __int64
0x180096fc6  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180096fcb  mov     r14, rax
0x180096fce  mov     [rbp+1C0h+var_1F0], rax
0x180096fd2  neg     rax
0x180096fd5  sbb     r13d, r13d
0x180096fd8  not     r13d
0x180096fdb  and     r13d, 8007000Eh
0x180096fe2  mov     dil, sil
0x180096fe5  test    r14, r14
0x180096fe8  jz      loc_1800979FA
0x180096fee  mov     rcx, [rsp+2C0h+var_260]
0x180096ff3  movups  xmm0, xmmword ptr [rcx]
0x180096ff6  movups  [rsp+2C0h+var_248], xmm0
0x180096ffb  mov     eax, [rcx+10h]
0x180096ffe  mov     [rbp+1C0h+var_238], eax
0x180097001  mov     dword ptr [rsp+2C0h+var_2A0], 104h; unsigned int
0x180097009  mov     r9, r14; wchar_t *
0x18009700c  mov     r8, [rcx+28h]; wchar_t *
0x180097010  lea     rdx, [rsp+2C0h+var_248]; struct tagDSGlobalUpdateId *
0x180097015  mov     rcx, rbx; this
0x180097018  call    ?GetUpdateDownloadPath@CAgentDownloadManager@@QEAAJAEBUtagDSGlobalUpdateId@@PEB_WPEA_WK@Z; CAgentDownloadManager::GetUpdateDownloadPath(tagDSGlobalUpdateId const &,wchar_t const *,wchar_t *,ulong)
0x18009701d  mov     r13d, eax
0x180097020  test    eax, eax
0x180097022  js      loc_1800979FA
0x180097028  test    sil, sil
0x18009702b  jz      loc_1800971B1
0x180097031  mov     rcx, [rsp+2C0h+var_260]
0x180097036  movups  xmm0, xmmword ptr [rcx]
  ... truncated ...
```
