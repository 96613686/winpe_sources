# CAgentUpdateManager::~CAgentUpdateManager(void)

- ea: `0x18001f40c`
- end: `0x18001f61e`
- name: `??1CAgentUpdateManager@@QEAA@XZ`
- size: `530`
- prototype: `void __fastcall(CAgentUpdateManager *__hidden this)`
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013b6c`
- `0x180014c74`
- `0x180241dd3`

## callees

- `0x18001f40c`
- `0x180037ae0`
- `0x180037bd8`
- `0x180037c70`
- `0x180037d7c`
- `0x180037e94`
- `0x1800380d8`
- `0x180038210`
- `0x1800682ec`
- `0x18007c160`
- `0x180098134`
- `0x180144c50`
- `0x1801bbf5c`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f443`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f4a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f4e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f556`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f596`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f5b3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f443`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f4a0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f4e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f556`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f596`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001f5b3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f479`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f52f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f56f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f479`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f52f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f56f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f54d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f58d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f54d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f58d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f4bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAgentUpdateManager::~CAgentUpdateManager(CAgentUpdateManager *this)
{
  char *v2; // rbx
  __int64 v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx

  v2 = (char *)this + 3760;
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::CMapEntryOps>((char *)this + 3856);
  *((_QWORD *)v2 + 6) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 56));
  v3 = *((_QWORD *)v2 + 5);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)v2 + 5) = 0;
  }
  CSusArrayList<CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::CMapEntryOps>(v2);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 92);
  CSusArrayList<CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::_tagMapEntry,CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::CMapEntryOps>::RemoveArraySection(
    (char *)this + 3720,
    0,
    0xFFFFFFFFLL,
    1);
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 92);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 92);
  CSusArrayList<CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::_tagMapEntry,CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::_tagMapEntry,CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::CMapEntryOps>((char *)this + 3720);
  v4 = (void *)*((_QWORD *)this + 459);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 459) = 0;
  }
  CSusArrayList<CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::_tagMapEntry,CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::CMapEntryOps>::~CSusArrayList<CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::_tagMapEntry,CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::CMapEntryOps>((char *)this + 3632);
  *((_QWORD *)this + 448) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 3592));
  CPendingReportingEventHandler::~CPendingReportingEventHandler((CAgentUpdateManager *)((char *)this + 2848));
  *((_DWORD *)this + 706) = 0;
  *((_QWORD *)this + 354) = 0;
  *((_DWORD *)this + 710) = 0;
  *((_QWORD *)this + 345) = &CSusEvent::`vftable';
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2688));
  CSusArrayList<CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::_tagMapEntry,CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::CMapEntryOps>::RemoveArraySection(
    (char *)this + 2728,
    0,
    0xFFFFFFFFLL,
    1);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2688));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2688));
  CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>((char *)this + 2728);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2616));
  CSusArrayList<CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::_tagMapEntry,CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::CMapEntryOps>::RemoveArraySection(
    (char *)this + 2656,
    0,
    0xFFFFFFFFLL,
    1);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 2616));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2616));
  CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>((char *)this + 2656);
  *((_QWORD *)this + 310) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 2488));
  CUHHandlerManager::~CUHHandlerManager((CAgentUpdateManager *)((char *)this + 2256));
  v5 = *((_QWORD *)this + 281);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 281) = 0;
  }
  CAgentDownloadManager::~CAgentDownloadManager((CAgentUpdateManager *)((char *)this + 160));
  CDriverUtilPrxy::~CDriverUtilPrxy((CAgentUpdateManager *)((char *)this + 136));
  CAgentProtocolTalker::~CAgentProtocolTalker(this);
}

```

## disassembly

```asm
0x18001f40c  mov     [rsp+arg_0], rbx
0x18001f411  mov     [rsp+arg_8], rsi
0x18001f416  mov     [rsp+arg_10], rdi
0x18001f41b  push    r14
0x18001f41d  sub     rsp, 20h
0x18001f421  mov     rsi, rcx
0x18001f424  lea     rbx, [rcx+0EB0h]
0x18001f42b  lea     rcx, [rbx+60h]
0x18001f42f  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@U1@V?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@V2@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,tagDSGlobalUpdateId,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>>::CMapEntryOps>(void)
0x18001f434  lea     r14, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x18001f43b  mov     [rbx+30h], r14
0x18001f43f  lea     rcx, [rbx+38h]; lpCriticalSection
0x18001f443  call    cs:__imp_DeleteCriticalSection
0x18001f449  nop
0x18001f44a  mov     rcx, [rbx+28h]
0x18001f44e  test    rcx, rcx
0x18001f451  jz      short loc_18001F467
0x18001f453  mov     rax, [rcx]
0x18001f456  mov     rax, [rax+10h]
0x18001f45a  call    _guard_dispatch_icall
0x18001f45f  mov     qword ptr [rbx+28h], 0
0x18001f467  mov     rcx, rbx
0x18001f46a  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@UtagDSGlobalUpdateId@@PEAV?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@V?$CSusSortedArrayListItemOpsBasic@UtagDSGlobalUpdateId@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusSortedArrayList@PEA_WVCSusSortedArrayListItemOpsLPWSTR@@@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::_tagMapEntry,CSusMap<tagDSGlobalUpdateId,CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *,CSusSortedArrayListItemOpsBasic<tagDSGlobalUpdateId>,CSusArrayListItemOpDelete<CSusSortedArrayList<wchar_t *,CSusSortedArrayListItemOpsLPWSTR> *>>::CMapEntryOps>(void)
0x18001f46f  lea     rdi, [rsi+0E60h]
0x18001f476  mov     rcx, rdi; lpCriticalSection
0x18001f479  call    cs:__imp_EnterCriticalSection
0x18001f47f  mov     r9d, 1
0x18001f485  or      r8d, 0FFFFFFFFh
0x18001f489  xor     edx, edx
0x18001f48b  lea     rcx, [rdi+28h]
0x18001f48f  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAUtagSystemSpec@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@VCSusArrayListItemOpSystemSpec@CAgentUpdateManager@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::_tagMapEntry,CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18001f494  mov     rcx, rdi; lpCriticalSection
0x18001f497  call    cs:__imp_LeaveCriticalSection
0x18001f49d  mov     rcx, rdi; lpCriticalSection
0x18001f4a0  call    cs:__imp_DeleteCriticalSection
0x18001f4a6  lea     rcx, [rdi+28h]
0x18001f4aa  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAUtagSystemSpec@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@VCSusArrayListItemOpSystemSpec@CAgentUpdateManager@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::_tagMapEntry,CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::_tagMapEntry,CSusMap<_GUID,tagSystemSpec *,CSusSortedArrayListItemOpsBasic<_GUID>,CAgentUpdateManager::CSusArrayListItemOpSystemSpec>::CMapEntryOps>(void)
0x18001f4af  mov     rcx, [rsi+0E58h]; hObject
0x18001f4b6  test    rcx, rcx
0x18001f4b9  jz      short loc_18001F4CC
0x18001f4bb  call    cs:__imp_CloseHandle
0x18001f4c1  mov     qword ptr [rsi+0E58h], 0
0x18001f4cc  lea     rcx, [rsi+0E30h]
0x18001f4d3  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@HPEAUtagDeployDriverInfo@@V?$CSusSortedArrayListItemOpsBasic@H@@V?$CSusArrayListItemOpNoop@PEAUtagDeployDriverInfo@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::_tagMapEntry,CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::CMapEntryOps>::~CSusArrayList<CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::_tagMapEntry,CSusMap<int,tagDeployDriverInfo *,CSusSortedArrayListItemOpsBasic<int>,CSusArrayListItemOpNoop<tagDeployDriverInfo *>>::CMapEntryOps>(void)
0x18001f4d8  mov     [rsi+0E00h], r14
0x18001f4df  lea     rcx, [rsi+0E08h]; lpCriticalSection
0x18001f4e6  call    cs:__imp_DeleteCriticalSection
0x18001f4ec  lea     rcx, [rsi+0B20h]; this
0x18001f4f3  call    ??1CPendingReportingEventHandler@@QEAA@XZ; CPendingReportingEventHandler::~CPendingReportingEventHandler(void)
0x18001f4f8  mov     dword ptr [rsi+0B08h], 0
0x18001f502  mov     qword ptr [rsi+0B10h], 0
0x18001f50d  mov     dword ptr [rsi+0B18h], 0
0x18001f517  lea     rax, ??_7CSusEvent@@6B@; const CSusEvent::`vftable'
0x18001f51e  mov     [rsi+0AC8h], rax
0x18001f525  lea     rdi, [rsi+0A80h]
0x18001f52c  mov     rcx, rdi; lpCriticalSection
0x18001f52f  call    cs:__imp_EnterCriticalSection
0x18001f535  mov     r9d, 1
0x18001f53b  or      r8d, 0FFFFFFFFh
0x18001f53f  xor     edx, edx
0x18001f541  lea     rcx, [rdi+28h]
0x18001f545  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAV?$CSusArrayList@UFileIdListData@FlatBundleFileIdList@@V?$CSusArrayListItemOpNoop@UFileIdListData@FlatBundleFileIdList@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusArrayList@UFileIdListData@FlatBundleFileIdList@@V?$CSusArrayListItemOpNoop@UFileIdListData@FlatBundleFileIdList@@@@@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::_tagMapEntry,CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18001f54a  mov     rcx, rdi; lpCriticalSection
0x18001f54d  call    cs:__imp_LeaveCriticalSection
0x18001f553  mov     rcx, rdi; lpCriticalSection
0x18001f556  call    cs:__imp_DeleteCriticalSection
0x18001f55c  lea     rcx, [rdi+28h]
0x18001f560  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>(void)
0x18001f565  lea     rdi, [rsi+0A38h]
0x18001f56c  mov     rcx, rdi; lpCriticalSection
0x18001f56f  call    cs:__imp_EnterCriticalSection
0x18001f575  mov     r9d, 1
0x18001f57b  or      r8d, 0FFFFFFFFh
0x18001f57f  xor     edx, edx
0x18001f581  lea     rcx, [rdi+28h]
0x18001f585  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAV?$CSusArrayList@UFileIdListData@FlatBundleFileIdList@@V?$CSusArrayListItemOpNoop@UFileIdListData@FlatBundleFileIdList@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusArrayList@UFileIdListData@FlatBundleFileIdList@@V?$CSusArrayListItemOpNoop@UFileIdListData@FlatBundleFileIdList@@@@@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::_tagMapEntry,CSusMap<_GUID,CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusArrayList<FlatBundleFileIdList::FileIdListData,CSusArrayListItemOpNoop<FlatBundleFileIdList::FileIdListData>> *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18001f58a  mov     rcx, rdi; lpCriticalSection
0x18001f58d  call    cs:__imp_LeaveCriticalSection
0x18001f593  mov     rcx, rdi; lpCriticalSection
0x18001f596  call    cs:__imp_DeleteCriticalSection
0x18001f59c  lea     rcx, [rdi+28h]
0x18001f5a0  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::_tagMapEntry,CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::CMapEntryOps>(void)
0x18001f5a5  mov     [rsi+9B0h], r14
0x18001f5ac  lea     rcx, [rsi+9B8h]; lpCriticalSection
0x18001f5b3  call    cs:__imp_DeleteCriticalSection
0x18001f5b9  lea     rcx, [rsi+8D0h]; this
0x18001f5c0  call    ??1CUHHandlerManager@@UEAA@XZ; CUHHandlerManager::~CUHHandlerManager(void)
0x18001f5c5  nop
0x18001f5c6  mov     rcx, [rsi+8C8h]
0x18001f5cd  test    rcx, rcx
0x18001f5d0  jz      short loc_18001F5E9
0x18001f5d2  mov     rax, [rcx]
0x18001f5d5  mov     rax, [rax+10h]
0x18001f5d9  call    _guard_dispatch_icall
0x18001f5de  mov     qword ptr [rsi+8C8h], 0
0x18001f5e9  lea     rcx, [rsi+0A0h]; this
0x18001f5f0  call    ??1CAgentDownloadManager@@QEAA@XZ; CAgentDownloadManager::~CAgentDownloadManager(void)
0x18001f5f5  lea     rcx, [rsi+88h]; this
0x18001f5fc  call    ??1CDriverUtilPrxy@@QEAA@XZ; CDriverUtilPrxy::~CDriverUtilPrxy(void)
0x18001f601  mov     rcx, rsi; this
0x18001f604  mov     rbx, [rsp+28h+arg_0]
0x18001f609  mov     rsi, [rsp+28h+arg_8]
0x18001f60e  mov     rdi, [rsp+28h+arg_10]
0x18001f613  add     rsp, 20h
0x18001f617  pop     r14
0x18001f619  jmp     ??1CAgentProtocolTalker@@UEAA@XZ; CAgentProtocolTalker::~CAgentProtocolTalker(void)
```
