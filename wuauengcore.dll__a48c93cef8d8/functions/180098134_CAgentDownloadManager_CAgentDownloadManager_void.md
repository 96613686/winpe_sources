# CAgentDownloadManager::~CAgentDownloadManager(void)

- ea: `0x180098134`
- end: `0x1800984fe`
- name: `??1CAgentDownloadManager@@QEAA@XZ`
- size: `970`
- prototype: `void __fastcall(CAgentDownloadManager *__hidden this)`
- caller_count: `2`
- callee_count: `27`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f40c`
- `0x180242029`

## callees

- `0x180015868`
- `0x180015c98`
- `0x18001a7f0`
- `0x180098134`
- `0x1800991d0`
- `0x1800af15c`
- `0x1800af248`
- `0x1800af43c`
- `0x1800af67c`
- `0x1800af87c`
- `0x1800afbe8`
- `0x1800afe10`
- `0x1800affd0`
- `0x1800b0070`
- `0x1800b0204`
- `0x1800b0290`
- `0x1800b04dc`
- `0x1800b06a8`
- `0x1800b08e4`
- `0x1800b171c`
- `0x1800eb0a4`
- `0x1800f1f10`
- `0x1800f3e3c`
- `0x1800f4498`
- `0x180113ae8`
- `0x180238984`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800981cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009820c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009825f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800983b4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800983ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098450`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098484`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800981cc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009820c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009825f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800983b4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800983ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098424`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098450`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180098484`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098460`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180098460`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009847b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009847b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAgentDownloadManager::~CAgentDownloadManager(CAgentDownloadManager *this)
{
  void *v2; // rbx
  void *v3; // rcx
  void (__fastcall ***v4)(_QWORD, __int64); // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  void (__fastcall ***v7)(_QWORD, __int64); // rcx
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  __int64 v9; // rcx
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  void *v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx

  *(_QWORD *)this = &CAgentDownloadManager::`vftable'{for `ISusWorker'};
  *((_QWORD *)this + 1) = &CAgentDownloadManager::`vftable'{for `IUpdateDownloadRequest'};
  CAgentDownloadManager::Uninit(this);
  v2 = (void *)*((_QWORD *)this + 259);
  if ( v2 )
  {
    CDownloadRegulator::~CDownloadRegulator(*((CDownloadRegulator **)this + 259));
    operator delete(v2, (const struct std::nothrow_t *)0xD8);
    *((_QWORD *)this + 259) = 0;
  }
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,unsigned char,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned char>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,unsigned char,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned char>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,unsigned char,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned char>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,unsigned char,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<unsigned char>>::CMapEntryOps>((char *)this + 2040);
  v3 = (void *)*((_QWORD *)this + 253);
  if ( v3 )
  {
    operator delete(v3, (const struct std::nothrow_t *)0x48);
    *((_QWORD *)this + 253) = 0;
  }
  *((_QWORD *)this + 247) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1984));
  CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>((char *)this + 1944);
  CSusArrayList<CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::CMapEntryOps>((char *)this + 1912);
  CSusArrayList<CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>((char *)this + 1880);
  CSusArrayList<CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::CMapEntryOps>((char *)this + 1824);
  *((_QWORD *)this + 222) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1784));
  CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>((char *)this + 1744);
  v4 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 216);
  if ( v4 )
  {
    (**v4)(v4, 1);
    *((_QWORD *)this + 216) = 0;
  }
  CSusArrayList<CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::CMapEntryOps>((char *)this + 1696);
  *((_QWORD *)this + 206) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1656));
  LockAllocator::~LockAllocator((CAgentDownloadManager *)((char *)this + 1560));
  CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>((char *)this + 1528);
  CSusArrayList<CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,enum RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<enum RetryStatus>>::CMapEntryOps>((char *)this + 1496);
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 185);
  if ( v5 )
  {
    (**v5)(v5, 1);
    *((_QWORD *)this + 185) = 0;
  }
  v6 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 184);
  if ( v6 )
  {
    (**v6)(v6, 1);
    *((_QWORD *)this + 184) = 0;
  }
  v7 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 183);
  if ( v7 )
  {
    (**v7)(v7, 1);
    *((_QWORD *)this + 183) = 0;
  }
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::CMapEntryOps>((char *)this + 1432);
  v8 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 178);
  if ( v8 )
  {
    (**v8)(v8, 1);
    *((_QWORD *)this + 178) = 0;
  }
  v9 = *((_QWORD *)this + 177);
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 108), 0xFFFFFFFF) == 1 )
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
    *((_QWORD *)this + 177) = 0;
  }
  v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 176);
  if ( v10 )
  {
    (**v10)(v10, 1);
    *((_QWORD *)this + 176) = 0;
  }
  CSusArrayList<unsigned long,CSusArrayListItemOpNoop<unsigned long>>::~CSusArrayList<unsigned long,CSusArrayListItemOpNoop<unsigned long>>((char *)this + 1384);
  CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>((char *)this + 1360);
  CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>((char *)this + 1336);
  CSusArrayList<CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::_tagMapEntry,CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::_tagMapEntry,CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::CMapEntryOps>((char *)this + 1304);
  *((_QWORD *)this + 153) = &CSearchCancellable::`vftable';
  *((_QWORD *)this + 156) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1256));
  CSusArrayList<DownloadManagerUpdateID,CSusDownloadManagerUpdateIDListOps>::~CSusArrayList<DownloadManagerUpdateID,CSusDownloadManagerUpdateIDListOps>((char *)this + 1192);
  v11 = (void *)*((_QWORD *)this + 148);
  if ( v11 )
  {
    SusFree(v11);
    *((_QWORD *)this + 148) = 0;
  }
  *((_QWORD *)this + 77) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  CSusArrayList<CSusMap<enum tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<enum tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::_tagMapEntry,CSusMap<enum tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<enum tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::CMapEntryOps>::~CSusArrayList<CSusMap<enum tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<enum tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::_tagMapEntry,CSusMap<enum tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<enum tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::CMapEntryOps>((char *)this + 584);
  CSusArrayList<CSusMap<unsigned long,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<unsigned long>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::_tagMapEntry,CSusMap<unsigned long,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<unsigned long>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::CMapEntryOps>::~CSusArrayList<CSusMap<unsigned long,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<unsigned long>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::_tagMapEntry,CSusMap<unsigned long,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<unsigned long>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::CMapEntryOps>((char *)this + 552);
  CSusArrayList<CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::CMapEntryOps>((char *)this + 520);
  *((_QWORD *)this + 59) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 12);
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::CMapEntryOps>((char *)this + 440);
  CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>((char *)this + 416);
  *((_QWORD *)this + 46) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 376));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  CSusArrayList<CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::CMapEntryOps>::RemoveArraySection(
    (char *)this + 336,
    0,
    0xFFFFFFFFLL,
    1);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 296));
  CSusArrayList<CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::CMapEntryOps>((char *)this + 336);
  CSusArrayList<CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::_tagMapEntry,CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::_tagMapEntry,CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::CMapEntryOps>((char *)this + 264);
  v12 = *((_QWORD *)this + 26);
  if ( v12 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 26) = 0;
  }
  CDownloadHandlerCallbackHandler::~CDownloadHandlerCallbackHandler((CAgentDownloadManager *)((char *)this + 96));
  CDownloadManagerCallbackHandler::~CDownloadManagerCallbackHandler((CAgentDownloadManager *)((char *)this + 48));
  v13 = *((_QWORD *)this + 3);
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180098134  mov     [rsp+arg_8], rbx
0x180098139  mov     [rsp+arg_10], rbp
0x18009813e  push    rsi
0x18009813f  push    rdi
0x180098140  push    r14
0x180098142  sub     rsp, 20h
0x180098146  mov     rsi, rcx
0x180098149  lea     rax, ??_7CAgentDownloadManager@@6BISusWorker@@@; const CAgentDownloadManager::`vftable'{for `ISusWorker'}
0x180098150  mov     [rcx], rax
0x180098153  lea     rax, ??_7CAgentDownloadManager@@6BIUpdateDownloadRequest@@@; const CAgentDownloadManager::`vftable'{for `IUpdateDownloadRequest'}
0x18009815a  mov     [rcx+8], rax
0x18009815e  call    ?Uninit@CAgentDownloadManager@@QEAAXXZ; CAgentDownloadManager::Uninit(void)
0x180098163  mov     rbx, [rsi+818h]
0x18009816a  xor     ebp, ebp
0x18009816c  test    rbx, rbx
0x18009816f  jz      short loc_18009818D
0x180098171  mov     rcx, rbx; this
0x180098174  call    ??1CDownloadRegulator@@QEAA@XZ; CDownloadRegulator::~CDownloadRegulator(void)
0x180098179  mov     edx, 0D8h; struct std::nothrow_t *
0x18009817e  mov     rcx, rbx; void *
0x180098181  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180098186  mov     [rsi+818h], rbp
0x18009818d  lea     rcx, [rsi+7F8h]
0x180098194  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@EV?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@V?$CSusArrayListItemOpNoop@E@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<tagDSGlobalUpdateId,uchar,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<uchar>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,uchar,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<uchar>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,uchar,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<uchar>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,uchar,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<uchar>>::CMapEntryOps>(void)
0x180098199  mov     rcx, [rsi+7E8h]; void *
0x1800981a0  test    rcx, rcx
0x1800981a3  jz      short loc_1800981B6
0x1800981a5  mov     edx, 48h ; 'H'; struct std::nothrow_t *
0x1800981aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800981af  mov     [rsi+7E8h], rbp
0x1800981b6  lea     rbx, [rsi+798h]
0x1800981bd  lea     rdi, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x1800981c4  mov     [rbx+20h], rdi
0x1800981c8  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800981cc  call    cs:__imp_DeleteCriticalSection
0x1800981d2  mov     rcx, rbx
0x1800981d5  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@U_FILETIME@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@U_FILETIME@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>(void)
0x1800981da  lea     rcx, [rsi+778h]
0x1800981e1  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@UtagDSGlobalUpdateId@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,tagDSGlobalUpdateId,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::CMapEntryOps>(void)
0x1800981e6  lea     rcx, [rsi+758h]
0x1800981ed  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@PEA_WVCSusDownloadManagerUpdateIDListOps@@VCSusSortedArrayListItemOpsLPWSTR@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,wchar_t *,CSusDownloadManagerUpdateIDListOps,CSusSortedArrayListItemOpsLPWSTR>::CMapEntryOps>(void)
0x1800981f2  lea     rcx, [rsi+720h]
0x1800981f9  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@W4RetryStatus@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@W4RetryStatus@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::CMapEntryOps>(void)
0x1800981fe  mov     [rsi+6F0h], rdi
0x180098205  lea     rcx, [rsi+6F8h]; lpCriticalSection
0x18009820c  call    cs:__imp_DeleteCriticalSection
0x180098212  lea     rcx, [rsi+6D0h]
0x180098219  call    ??1?$CSusArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@UEAA@XZ; CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(void)
0x18009821e  mov     rcx, [rsi+6C0h]
0x180098225  mov     r14d, 1
0x18009822b  test    rcx, rcx
0x18009822e  jz      short loc_180098245
0x180098230  mov     rax, [rcx]
0x180098233  mov     edx, r14d
0x180098236  mov     rax, [rax]
0x180098239  call    _guard_dispatch_icall
0x18009823e  mov     [rsi+6C0h], rbp
0x180098245  lea     rcx, [rsi+6A0h]
0x18009824c  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@W4RetryStatus@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@W4RetryStatus@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::CMapEntryOps>(void)
0x180098251  mov     [rsi+670h], rdi
0x180098258  lea     rcx, [rsi+678h]; lpCriticalSection
0x18009825f  call    cs:__imp_DeleteCriticalSection
0x180098265  lea     rcx, [rsi+618h]; this
0x18009826c  call    ??1LockAllocator@@QEAA@XZ; LockAllocator::~LockAllocator(void)
0x180098271  lea     rcx, [rsi+5F8h]
0x180098278  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@U_FILETIME@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@U_FILETIME@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_FILETIME,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_FILETIME>>::CMapEntryOps>(void)
0x18009827d  lea     rcx, [rsi+5D8h]
0x180098284  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@W4RetryStatus@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@W4RetryStatus@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,RetryStatus,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<RetryStatus>>::CMapEntryOps>(void)
0x180098289  mov     rcx, [rsi+5C8h]
0x180098290  test    rcx, rcx
0x180098293  jz      short loc_1800982AA
0x180098295  mov     rax, [rcx]
0x180098298  mov     edx, r14d
0x18009829b  mov     rax, [rax]
0x18009829e  call    _guard_dispatch_icall
0x1800982a3  mov     [rsi+5C8h], rbp
0x1800982aa  mov     rcx, [rsi+5C0h]
0x1800982b1  test    rcx, rcx
0x1800982b4  jz      short loc_1800982CB
0x1800982b6  mov     rax, [rcx]
0x1800982b9  mov     edx, r14d
0x1800982bc  mov     rax, [rax]
0x1800982bf  call    _guard_dispatch_icall
0x1800982c4  mov     [rsi+5C0h], rbp
0x1800982cb  mov     rcx, [rsi+5B8h]
0x1800982d2  test    rcx, rcx
0x1800982d5  jz      short loc_1800982EC
0x1800982d7  mov     rax, [rcx]
0x1800982da  mov     edx, r14d
0x1800982dd  mov     rax, [rax]
0x1800982e0  call    _guard_dispatch_icall
0x1800982e5  mov     [rsi+5B8h], rbp
0x1800982ec  lea     rcx, [rsi+598h]
0x1800982f3  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@UDownloadJobCompletionInfo@@V?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@VCSusArrayListItemOpDownloadJobCompletion@CAgentDownloadManager@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,DownloadJobCompletionInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CAgentDownloadManager::CSusArrayListItemOpDownloadJobCompletion>::CMapEntryOps>(void)
0x1800982f8  mov     rcx, [rsi+590h]
0x1800982ff  test    rcx, rcx
0x180098302  jz      short loc_180098319
0x180098304  mov     rax, [rcx]
0x180098307  mov     edx, r14d
0x18009830a  mov     rax, [rax]
0x18009830d  call    _guard_dispatch_icall
0x180098312  mov     [rsi+590h], rbp
0x180098319  mov     rcx, [rsi+588h]
0x180098320  test    rcx, rcx
0x180098323  jz      short loc_180098347
0x180098325  or      eax, 0FFFFFFFFh
0x180098328  lock xadd [rcx+6Ch], eax
0x18009832d  cmp     eax, r14d
0x180098330  jnz     short loc_180098340
0x180098332  mov     rax, [rcx]
0x180098335  mov     edx, r14d
0x180098338  mov     rax, [rax]
0x18009833b  call    _guard_dispatch_icall
0x180098340  mov     [rsi+588h], rbp
0x180098347  mov     rcx, [rsi+580h]
0x18009834e  test    rcx, rcx
0x180098351  jz      short loc_180098368
0x180098353  mov     rax, [rcx]
0x180098356  mov     edx, r14d
0x180098359  mov     rax, [rax]
0x18009835c  call    _guard_dispatch_icall
0x180098361  mov     [rsi+580h], rbp
0x180098368  lea     rcx, [rsi+568h]
0x18009836f  call    ??1?$CSusArrayList@KV?$CSusArrayListItemOpNoop@K@@@@UEAA@XZ; CSusArrayList<ulong,CSusArrayListItemOpNoop<ulong>>::~CSusArrayList<ulong,CSusArrayListItemOpNoop<ulong>>(void)
0x180098374  lea     rcx, [rsi+550h]
0x18009837b  call    ??1?$CSusArrayList@U_GUID@@V?$CSusArrayListItemOpNoop@U_GUID@@@@@@UEAA@XZ; CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>(void)
0x180098380  lea     rcx, [rsi+538h]
0x180098387  call    ??1?$CSusArrayList@U_GUID@@V?$CSusArrayListItemOpNoop@U_GUID@@@@@@UEAA@XZ; CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>(void)
0x18009838c  lea     rcx, [rsi+518h]
0x180098393  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAVCDynamicDownloadDataFetcher@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAVCDynamicDownloadDataFetcher@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::_tagMapEntry,CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::_tagMapEntry,CSusMap<_GUID,CDynamicDownloadDataFetcher *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CDynamicDownloadDataFetcher *>>::CMapEntryOps>(void)
0x180098398  lea     rax, ??_7CSearchCancellable@@6B@; const CSearchCancellable::`vftable'
0x18009839f  mov     [rsi+4C8h], rax
0x1800983a6  mov     [rsi+4E0h], rdi
0x1800983ad  lea     rcx, [rsi+4E8h]; lpCriticalSection
0x1800983b4  call    cs:__imp_DeleteCriticalSection
0x1800983ba  lea     rcx, [rsi+4A8h]
0x1800983c1  call    ??1?$CSusArrayList@UDownloadManagerUpdateID@@VCSusDownloadManagerUpdateIDListOps@@@@UEAA@XZ; CSusArrayList<DownloadManagerUpdateID,CSusDownloadManagerUpdateIDListOps>::~CSusArrayList<DownloadManagerUpdateID,CSusDownloadManagerUpdateIDListOps>(void)
0x1800983c6  mov     rcx, [rsi+4A0h]; lpMem
0x1800983cd  test    rcx, rcx
0x1800983d0  jz      short loc_1800983DE
0x1800983d2  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800983d7  mov     [rsi+4A0h], rbp
0x1800983de  mov     [rsi+268h], rdi
0x1800983e5  lea     rcx, [rsi+270h]; lpCriticalSection
0x1800983ec  call    cs:__imp_DeleteCriticalSection
0x1800983f2  lea     rcx, [rsi+248h]
0x1800983f9  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@W4tagUHUpdateHandler@@PEAVHandlerDownloadRequestMap@@V?$CSusSortedArrayListItemOpsBasic@W4tagUHUpdateHandler@@@@V?$CSusArrayListItemOpDelete@PEAVHandlerDownloadRequestMap@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::_tagMapEntry,CSusMap<tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::_tagMapEntry,CSusMap<tagUHUpdateHandler,HandlerDownloadRequestMap *,CSusSortedArrayListItemOpsBasic<tagUHUpdateHandler>,CSusArrayListItemOpDelete<HandlerDownloadRequestMap *>>::CMapEntryOps>(void)
0x1800983fe  lea     rcx, [rsi+228h]
0x180098405  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@KPEAVDownloadCallWrap@@V?$CSusSortedArrayListItemOpsBasic@K@@V?$CSusArrayListItemOpDelete@PEAVDownloadCallWrap@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<ulong,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<ulong>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::_tagMapEntry,CSusMap<ulong,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<ulong>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::CMapEntryOps>::~CSusArrayList<CSusMap<ulong,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<ulong>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::_tagMapEntry,CSusMap<ulong,DownloadCallWrap *,CSusSortedArrayListItemOpsBasic<ulong>,CSusArrayListItemOpDelete<DownloadCallWrap *>>::CMapEntryOps>(void)
0x18009840a  lea     rcx, [rsi+208h]
0x180098411  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@PEAVCCacheEntry@CDownloadDirNameCache@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpDelete@PEAVCCacheEntry@CDownloadDirNameCache@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,CDownloadDirNameCache::CCacheEntry *,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpDelete<CDownloadDirNameCache::CCacheEntry *>>::CMapEntryOps>(void)
0x180098416  mov     [rsi+1D8h], rdi
0x18009841d  lea     rcx, [rsi+1E0h]; lpCriticalSection
0x180098424  call    cs:__imp_DeleteCriticalSection
0x18009842a  lea     rcx, [rsi+1B8h]
0x180098431  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@UUpdateDownloadPerfTrackInfo@CAgentDownloadManager@@V?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@V?$CSusArrayListItemOpNoop@UUpdateDownloadPerfTrackInfo@CAgentDownloadManager@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CAgentDownloadManager::UpdateDownloadPerfTrackInfo,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpNoop<CAgentDownloadManager::UpdateDownloadPerfTrackInfo>>::CMapEntryOps>(void)
0x180098436  lea     rcx, [rsi+1A0h]
0x18009843d  call    ??1?$CSusArrayList@U_GUID@@V?$CSusArrayListItemOpNoop@U_GUID@@@@@@UEAA@XZ; CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>::~CSusArrayList<_GUID,CSusArrayListItemOpNoop<_GUID>>(void)
0x180098442  mov     [rsi+170h], rdi
0x180098449  lea     rcx, [rsi+178h]; lpCriticalSection
0x180098450  call    cs:__imp_DeleteCriticalSection
0x180098456  lea     rdi, [rsi+128h]
0x18009845d  mov     rcx, rdi; lpCriticalSection
0x180098460  call    cs:__imp_EnterCriticalSection
0x180098466  mov     r9d, r14d
0x180098469  or      r8d, 0FFFFFFFFh
0x18009846d  xor     edx, edx
0x18009846f  lea     rcx, [rdi+28h]
0x180098473  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@U_GUID@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@U_GUID@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x180098478  mov     rcx, rdi; lpCriticalSection
0x18009847b  call    cs:__imp_LeaveCriticalSection
0x180098481  mov     rcx, rdi; lpCriticalSection
0x180098484  call    cs:__imp_DeleteCriticalSection
0x18009848a  lea     rcx, [rdi+28h]
0x18009848e  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UDownloadManagerUpdateID@@U_GUID@@VCSusDownloadManagerUpdateIDListOps@@V?$CSusArrayListItemOpNoop@U_GUID@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::CMapEntryOps>::~CSusArrayList<CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::_tagMapEntry,CSusMap<DownloadManagerUpdateID,_GUID,CSusDownloadManagerUpdateIDListOps,CSusArrayListItemOpNoop<_GUID>>::CMapEntryOps>(void)
0x180098493  lea     rcx, [rsi+108h]
0x18009849a  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAVCUpdateDownloadJob@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpInterfacePtr@PEAVCUpdateDownloadJob@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::_tagMapEntry,CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::_tagMapEntry,CSusMap<_GUID,CUpdateDownloadJob *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpInterfacePtr<CUpdateDownloadJob *>>::CMapEntryOps>(void)
0x18009849f  nop
0x1800984a0  mov     rcx, [rsi+0D0h]
0x1800984a7  test    rcx, rcx
0x1800984aa  jz      short loc_1800984BF
0x1800984ac  mov     rax, [rcx]
0x1800984af  mov     rax, [rax+10h]
0x1800984b3  call    _guard_dispatch_icall
0x1800984b8  mov     [rsi+0D0h], rbp
0x1800984bf  lea     rcx, [rsi+60h]; this
0x1800984c3  call    ??1CDownloadHandlerCallbackHandler@@QEAA@XZ; CDownloadHandlerCallbackHandler::~CDownloadHandlerCallbackHandler(void)
0x1800984c8  lea     rcx, [rsi+30h]; this
0x1800984cc  call    ??1CDownloadManagerCallbackHandler@@QEAA@XZ; CDownloadManagerCallbackHandler::~CDownloadManagerCallbackHandler(void)
0x1800984d1  nop
0x1800984d2  mov     rcx, [rsi+18h]
0x1800984d6  test    rcx, rcx
0x1800984d9  jz      short loc_1800984EB
0x1800984db  mov     rax, [rcx]
0x1800984de  mov     rax, [rax+10h]
0x1800984e2  call    _guard_dispatch_icall
0x1800984e7  mov     [rsi+18h], rbp
0x1800984eb  mov     rbx, [rsp+38h+arg_8]
0x1800984f0  mov     rbp, [rsp+38h+arg_10]
0x1800984f5  add     rsp, 20h
0x1800984f9  pop     r14
0x1800984fb  pop     rdi
0x1800984fc  pop     rsi
0x1800984fd  retn
```
