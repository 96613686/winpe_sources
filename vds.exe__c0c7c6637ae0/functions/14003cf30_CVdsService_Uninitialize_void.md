# CVdsService::Uninitialize(void)

- ea: `0x14003cf30`
- end: `0x14003d41a`
- name: `?Uninitialize@CVdsService@@SAXXZ`
- size: `1258`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14000ee10`

## callees

- `0x14000eb1c`
- `0x1400168c8`
- `0x140017014`
- `0x14003cf30`
- `0x14003f490`
- `0x140052e46`
- `0x140056010`

## import_xrefs

- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x14003d3d3`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x14003d3f8`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x14003d3d3`
- `msvcrt!?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z` at `0x14003d3f8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003cfbb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14003cfbb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003cfcd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14003cfcd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d0d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d17a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d22a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d32c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d34e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d0d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d17a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d22a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d32c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003d34e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d03c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d0de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d183`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d233`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d335`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d03c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d0de`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d183`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d233`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003d335`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d3e4`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003d3e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d094`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003d094`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d2f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14003d2f0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003cff3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d00c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d025`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003cff3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d00c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003d025`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003cf98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003cfda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d3a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d3bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003cf98`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003cfda`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d3a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003d3bf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14003cf70`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14003cf70`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003d0cb`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003d2ad`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003d322`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003d0cb`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003d2ad`
- `vdsutil!?RemoveAll@CRtlMap@@QEAAXH@Z` at `0x14003d322`
- `vdsutil!VdsHeapFree` at `0x14003d2fe`
- `vdsutil!VdsHeapFree` at `0x14003d2fe`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d0fc`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d1a4`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d0fc`
- `vdsutil!?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d1a4`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d116`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d1be`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d116`
- `vdsutil!?End@CRtlList@@QEAA?AVCRtlListIter@@XZ` at `0x14003d1be`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14003d170`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14003d220`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14003d170`
- `vdsutil!?RemoveAll@CRtlList@@QEAAXXZ` at `0x14003d220`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003d143`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003d1eb`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003d143`
- `vdsutil!?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ` at `0x14003d1eb`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003d165`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003d215`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003d165`
- `vdsutil!?Next@CRtlListIter@@QEAAAEAV1@XZ` at `0x14003d215`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003cf4f`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14003cf4f`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003d407`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14003d407`
- `vdsutil!?Uninitialize@CVdsAsyncObjectBase@@SAXXZ` at `0x14003d394`
- `vdsutil!?Uninitialize@CVdsAsyncObjectBase@@SAXXZ` at `0x14003d394`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003d0ba`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003d29c`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003d311`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003d0ba`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003d29c`
- `vdsutil!?Next@CRtlMapIter@@QEAAAEAV1@XZ` at `0x14003d311`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003d061`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003d258`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003d2c2`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003d061`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003d258`
- `vdsutil!?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ` at `0x14003d2c2`

## string_xrefs

- `0x14003cf3f`: `CVdsService::Uninitialize()`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void CVdsService::Uninitialize(void)
{
  int i; // ebx
  __int64 v1; // rax
  void *v2; // rcx
  __int64 v3; // rax
  void *EntryPointer; // rax
  CVdsIscsiInitiatorAdapterInternal *v5; // rax
  CVdsIscsiInitiatorAdapterInternal *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdi
  __int64 v11; // rbx
  HANDLE ProcessHeap; // rax
  void (*v13)(unsigned int, struct _EXCEPTION_POINTERS *); // rbx
  __int128 v14; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v15; // [rsp+30h] [rbp-A8h]
  __int128 v16; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v17; // [rsp+48h] [rbp-90h]
  __int128 Buf1; // [rsp+50h] [rbp-88h] BYREF
  __int128 j; // [rsp+60h] [rbp-78h] BYREF
  __int128 Buf2; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v21[24]; // [rsp+80h] [rbp-58h] BYREF
  _BYTE v22[64]; // [rsp+98h] [rbp-40h] BYREF

  CVdsCallTracer::CVdsCallTracer((CVdsCallTracer *)v22, 0x5Eu, "CVdsService::Uninitialize()");
  CVdsService::DumpUnallocatedDisks();
  for ( i = 0; i < 600; ++i )
  {
    if ( CVdsService::CanProvidersUnload(0) )
      break;
    Sleep(0x32u);
  }
  if ( (unsigned int)i >= 0x1E )
    CVdsService::CanProvidersUnload(1);
  if ( CVdsService::m_hInitializeThread )
  {
    CloseHandle(CVdsService::m_hInitializeThread);
    CVdsService::m_hInitializeThread = 0;
  }
  if ( CVdsService::m_hRemoveObsoleteDevNodesThread )
  {
    CVdsService::m_hShutdownRemoveObsoleteDevNodesThread = 1;
    SetEvent(CVdsService::m_hRemoveObsoleteDevNodesEvent);
    WaitForSingleObject(CVdsService::m_hRemoveObsoleteDevNodesThread, 0x3A98u);
    CloseHandle(CVdsService::m_hRemoveObsoleteDevNodesThread);
    CVdsService::m_hRemoveObsoleteDevNodesThread = 0;
  }
  if ( CVdsService::m_hHbaapiModule )
  {
    FreeLibrary(CVdsService::m_hHbaapiModule);
    CVdsService::m_hHbaapiModule = 0;
  }
  if ( CVdsService::m_hIscsidscModule )
  {
    FreeLibrary(CVdsService::m_hIscsidscModule);
    CVdsService::m_hIscsidscModule = 0;
  }
  if ( CVdsService::m_hFVEModule )
  {
    FreeLibrary(CVdsService::m_hFVEModule);
    CVdsService::m_hFVEModule = 0;
  }
  EnterCriticalSection(&g_GlobalCriticalSection);
  v16 = 0;
  v17 = 0;
  v1 = CRtlMap::Begin(CVdsService::m_mapLunIds, v21);
  v16 = *(_OWORD *)v1;
  v17 = *(_QWORD *)(v1 + 16);
  while ( (_QWORD)v16 && *((_QWORD *)&v16 + 1) )
  {
    v2 = *(void **)(*((_QWORD *)&v16 + 1) + 48LL);
    if ( v2 )
    {
      CoTaskMemFree(v2);
      if ( *((_QWORD *)&v16 + 1) )
        v3 = *((_QWORD *)&v16 + 1) + 32LL;
      else
        v3 = 0;
      *(_QWORD *)(v3 + 8) = 0;
      *(_QWORD *)(v3 + 16) = 0;
    }
    CRtlMapIter::Next((CRtlMapIter *)&v16);
  }
  CRtlMap::RemoveAll((CRtlMap *)CVdsService::m_mapLunIds, 0);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  EnterCriticalSection(&g_GlobalCriticalSection);
  Buf1 = 0;
  for ( Buf1 = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstHbaPorts, &Buf2); ; CRtlListIter::Next((CRtlListIter *)&Buf1) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstHbaPorts, v21);
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
      break;
    EntryPointer = CRtlListIter::GetEntryPointer((CRtlListIter *)&Buf1);
    if ( EntryPointer )
      (*(void (__fastcall **)(void *))(*(_QWORD *)EntryPointer + 16LL))(EntryPointer);
  }
  CRtlList::RemoveAll((CRtlList *)CVdsService::m_lstHbaPorts);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  EnterCriticalSection(&g_GlobalCriticalSection);
  j = 0;
  for ( j = *(_OWORD *)CRtlList::Begin(CVdsService::m_lstIscsiInitiatorAdapters, v21);
        ;
        CRtlListIter::Next((CRtlListIter *)&j) )
  {
    Buf2 = *(_OWORD *)CRtlList::End(CVdsService::m_lstIscsiInitiatorAdapters, v21);
    if ( !memcmp_0(&j, &Buf2, 0x10u) )
      break;
    v5 = (CVdsIscsiInitiatorAdapterInternal *)CRtlListIter::GetEntryPointer((CRtlListIter *)&j);
    v6 = v5;
    if ( v5 )
    {
      CVdsIscsiInitiatorAdapterInternal::RemoveInitiatorPortals(v5);
      (*(void (__fastcall **)(CVdsIscsiInitiatorAdapterInternal *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  CRtlList::RemoveAll((CRtlList *)CVdsService::m_lstIscsiInitiatorAdapters);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  EnterCriticalSection(&g_GlobalCriticalSection);
  v14 = 0;
  v15 = 0;
  v7 = CRtlMap::Begin(CVdsService::m_mapUnallocatedDisks, v21);
  v14 = *(_OWORD *)v7;
  v15 = *(_QWORD *)(v7 + 16);
  while ( (_QWORD)v14 && *((_QWORD *)&v14 + 1) )
  {
    v8 = *(_QWORD *)(*((_QWORD *)&v14 + 1) + 48LL);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    CRtlMapIter::Next((CRtlMapIter *)&v14);
  }
  CRtlMap::RemoveAll((CRtlMap *)CVdsService::m_mapUnallocatedDisks, 0);
  v9 = CRtlMap::Begin(CVdsService::m_mapUnallocatedDisksByDeviceId, v21);
  v14 = *(_OWORD *)v9;
  v15 = *(_QWORD *)(v9 + 16);
  while ( (_QWORD)v14 )
  {
    v10 = *((_QWORD *)&v14 + 1);
    if ( !*((_QWORD *)&v14 + 1) )
      break;
    v11 = *(_QWORD *)(*((_QWORD *)&v14 + 1) + 16LL);
    ProcessHeap = GetProcessHeap();
    VdsHeapFree(ProcessHeap, 0, v11);
    *(_QWORD *)(v10 + 8) = 0;
    *(_QWORD *)(v10 + 16) = 0;
    CRtlMapIter::Next((CRtlMapIter *)&v14);
  }
  CRtlMap::RemoveAll((CRtlMap *)CVdsService::m_mapUnallocatedDisksByDeviceId, 0);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  EnterCriticalSection(&g_GlobalCriticalSection);
  CVdsService::UnloadProviders((struct CRtlList *)CVdsService::m_lstSoftwareProviders, 0);
  LeaveCriticalSection(&g_GlobalCriticalSection);
  CVdsService::UnloadProviders(
    (struct CRtlList *)CVdsService::m_lstHardwareProviders,
    &CVdsService::m_pVdsHardwareProviderList);
  CVdsService::UnloadProviders((struct CRtlList *)CVdsService::m_lstVirtualDiskProviders, 0);
  if ( CVdsService::m_pCallbackObject )
  {
    (*(void (__fastcall **)(struct CVdsCallbackObject *))(*(_QWORD *)CVdsService::m_pCallbackObject + 16LL))(CVdsService::m_pCallbackObject);
    CVdsService::m_pCallbackObject = 0;
  }
  CVdsAsyncObjectBase::Uninitialize();
  if ( CVdsService::m_hProvidersLoadedEvent )
  {
    CloseHandle(CVdsService::m_hProvidersLoadedEvent);
    CVdsService::m_hProvidersLoadedEvent = 0;
  }
  if ( CVdsService::m_hRemoveObsoleteDevNodesEvent )
  {
    CloseHandle(CVdsService::m_hRemoveObsoleteDevNodesEvent);
    CVdsService::m_hRemoveObsoleteDevNodesEvent = 0;
  }
  v13 = _set_se_translator((void (*)(unsigned int, struct _EXCEPTION_POINTERS *))CVdsService::SETranslationFunction);
  try
  {
    CoUninitialize();
  }
  catch ( ... )
  {
    VdsTraceEx(94, 0, "CVdsService::Uninitialize: CoUninitialize triggered exception.");
  }
  _set_se_translator(v13);
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v22);
}

```

## disassembly

```asm
0x14003cf30  mov     rax, rsp
0x14003cf33  push    rbx
0x14003cf34  push    rsi
0x14003cf35  push    rdi
0x14003cf36  push    r14
0x14003cf38  sub     rsp, 0B8h
0x14003cf3f  lea     r8, aCvdsserviceUni_25; "CVdsService::Uninitialize()"
0x14003cf46  mov     edx, 5Eh ; '^'
0x14003cf4b  lea     rcx, [rax-40h]
0x14003cf4f  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14003cf55  nop
0x14003cf56  call    ?DumpUnallocatedDisks@CVdsService@@SAXXZ; CVdsService::DumpUnallocatedDisks(void)
0x14003cf5b  xor     esi, esi
0x14003cf5d  mov     ebx, esi
0x14003cf5f  lea     edi, [rsi+1]
0x14003cf62  xor     ecx, ecx; int
0x14003cf64  call    ?CanProvidersUnload@CVdsService@@SAHH@Z; CVdsService::CanProvidersUnload(int)
0x14003cf69  test    eax, eax
0x14003cf6b  jnz     short loc_14003CF80
0x14003cf6d  lea     ecx, [rax+32h]; dwMilliseconds
0x14003cf70  call    cs:__imp_Sleep
0x14003cf76  add     ebx, edi
0x14003cf78  cmp     ebx, 258h
0x14003cf7e  jl      short loc_14003CF62
0x14003cf80  cmp     ebx, 1Eh
0x14003cf83  jb      short loc_14003CF8C
0x14003cf85  mov     ecx, edi; int
0x14003cf87  call    ?CanProvidersUnload@CVdsService@@SAHH@Z; CVdsService::CanProvidersUnload(int)
0x14003cf8c  mov     rcx, cs:?m_hInitializeThread@CVdsService@@0PEAXEA; hObject
0x14003cf93  test    rcx, rcx
0x14003cf96  jz      short loc_14003CFA5
0x14003cf98  call    cs:__imp_CloseHandle
0x14003cf9e  mov     cs:?m_hInitializeThread@CVdsService@@0PEAXEA, rsi; void * CVdsService::m_hInitializeThread
0x14003cfa5  cmp     cs:?m_hRemoveObsoleteDevNodesThread@CVdsService@@0PEAXEA, rsi; void * CVdsService::m_hRemoveObsoleteDevNodesThread
0x14003cfac  jz      short loc_14003CFE7
0x14003cfae  mov     cs:?m_hShutdownRemoveObsoleteDevNodesThread@CVdsService@@0HA, edi; int CVdsService::m_hShutdownRemoveObsoleteDevNodesThread
0x14003cfb4  mov     rcx, cs:?m_hRemoveObsoleteDevNodesEvent@CVdsService@@0PEAXEA; hEvent
0x14003cfbb  call    cs:__imp_SetEvent
0x14003cfc1  mov     edx, 3A98h; dwMilliseconds
0x14003cfc6  mov     rcx, cs:?m_hRemoveObsoleteDevNodesThread@CVdsService@@0PEAXEA; hHandle
0x14003cfcd  call    cs:__imp_WaitForSingleObject
0x14003cfd3  mov     rcx, cs:?m_hRemoveObsoleteDevNodesThread@CVdsService@@0PEAXEA; hObject
0x14003cfda  call    cs:__imp_CloseHandle
0x14003cfe0  mov     cs:?m_hRemoveObsoleteDevNodesThread@CVdsService@@0PEAXEA, rsi; void * CVdsService::m_hRemoveObsoleteDevNodesThread
0x14003cfe7  mov     rcx, cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA; hLibModule
0x14003cfee  test    rcx, rcx
0x14003cff1  jz      short loc_14003D000
0x14003cff3  call    cs:__imp_FreeLibrary
0x14003cff9  mov     cs:?m_hHbaapiModule@CVdsService@@2PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CVdsService::m_hHbaapiModule
0x14003d000  mov     rcx, cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA; hLibModule
0x14003d007  test    rcx, rcx
0x14003d00a  jz      short loc_14003D019
0x14003d00c  call    cs:__imp_FreeLibrary
0x14003d012  mov     cs:?m_hIscsidscModule@CVdsService@@2PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CVdsService::m_hIscsidscModule
0x14003d019  mov     rcx, cs:?m_hFVEModule@CVdsService@@2PEAUHINSTANCE__@@EA; hLibModule
0x14003d020  test    rcx, rcx
0x14003d023  jz      short loc_14003D032
0x14003d025  call    cs:__imp_FreeLibrary
0x14003d02b  mov     cs:?m_hFVEModule@CVdsService@@2PEAUHINSTANCE__@@EA, rsi; HINSTANCE__ * CVdsService::m_hFVEModule
0x14003d032  lea     r14, ?g_GlobalCriticalSection@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_GlobalCriticalSection
0x14003d039  mov     rcx, r14; lpCriticalSection
0x14003d03c  call    cs:__imp_EnterCriticalSection
0x14003d042  nop
0x14003d043  xorps   xmm0, xmm0
0x14003d046  xor     eax, eax
0x14003d048  movups  [rsp+0D8h+var_A0], xmm0
0x14003d04d  mov     [rsp+0D8h+var_90], rax
0x14003d052  lea     rdx, [rsp+0D8h+var_58]
0x14003d05a  lea     rcx, ?m_mapLunIds@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapLunIds
0x14003d061  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14003d067  movups  xmm0, xmmword ptr [rax]
0x14003d06a  movups  [rsp+0D8h+var_A0], xmm0
0x14003d06f  movsd   xmm1, qword ptr [rax+10h]
0x14003d074  movsd   [rsp+0D8h+var_90], xmm1
0x14003d07a  cmp     qword ptr [rsp+0D8h+var_A0], rsi
0x14003d07f  jz      short loc_14003D0C2
0x14003d081  mov     rax, qword ptr [rsp+0D8h+var_A0+8]
0x14003d086  test    rax, rax
0x14003d089  jz      short loc_14003D0C2
0x14003d08b  mov     rcx, [rax+30h]; pv
0x14003d08f  test    rcx, rcx
0x14003d092  jz      short loc_14003D0B5
0x14003d094  call    cs:__imp_CoTaskMemFree
0x14003d09a  mov     rax, qword ptr [rsp+0D8h+var_A0+8]
0x14003d09f  test    rax, rax
0x14003d0a2  jz      short loc_14003D0AA
0x14003d0a4  add     rax, 20h ; ' '
0x14003d0a8  jmp     short loc_14003D0AD
0x14003d0aa  mov     rax, rsi
0x14003d0ad  mov     [rax+8], rsi
0x14003d0b1  mov     [rax+10h], rsi
0x14003d0b5  lea     rcx, [rsp+0D8h+var_A0]
0x14003d0ba  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x14003d0c0  jmp     short loc_14003D07A
0x14003d0c2  xor     edx, edx
0x14003d0c4  lea     rcx, ?m_mapLunIds@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapLunIds
0x14003d0cb  call    cs:__imp_?RemoveAll@CRtlMap@@QEAAXH@Z; CRtlMap::RemoveAll(int)
0x14003d0d1  nop
0x14003d0d2  mov     rcx, r14; lpCriticalSection
0x14003d0d5  call    cs:__imp_LeaveCriticalSection
0x14003d0db  mov     rcx, r14; lpCriticalSection
0x14003d0de  call    cs:__imp_EnterCriticalSection
0x14003d0e4  nop
0x14003d0e5  xorps   xmm0, xmm0
0x14003d0e8  movups  [rsp+0D8h+Buf1], xmm0
0x14003d0ed  lea     rdx, [rsp+0D8h+Buf2]
0x14003d0f2  lea     rbx, ?m_lstHbaPorts@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstHbaPorts
0x14003d0f9  mov     rcx, rbx
0x14003d0fc  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003d102  movups  xmm0, xmmword ptr [rax]
0x14003d105  movdqu  [rsp+0D8h+Buf1], xmm0
0x14003d10b  lea     rdx, [rsp+0D8h+var_58]
0x14003d113  mov     rcx, rbx
0x14003d116  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003d11c  movups  xmm0, xmmword ptr [rax]
0x14003d11f  movdqu  [rsp+0D8h+Buf2], xmm0
0x14003d125  mov     r8d, 10h; Size
0x14003d12b  lea     rdx, [rsp+0D8h+Buf2]; Buf2
0x14003d130  lea     rcx, [rsp+0D8h+Buf1]; Buf1
0x14003d135  call    memcmp_0
0x14003d13a  test    eax, eax
0x14003d13c  jz      short loc_14003D16D
0x14003d13e  lea     rcx, [rsp+0D8h+Buf1]
0x14003d143  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003d149  mov     rdx, rax
0x14003d14c  test    rax, rax
0x14003d14f  jz      short loc_14003D160
0x14003d151  mov     rcx, [rax]
0x14003d154  mov     rax, [rcx+10h]
0x14003d158  mov     rcx, rdx
0x14003d15b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d160  lea     rcx, [rsp+0D8h+Buf1]
0x14003d165  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003d16b  jmp     short loc_14003D10B
0x14003d16d  mov     rcx, rbx
0x14003d170  call    cs:__imp_?RemoveAll@CRtlList@@QEAAXXZ; CRtlList::RemoveAll(void)
0x14003d176  nop
0x14003d177  mov     rcx, r14; lpCriticalSection
0x14003d17a  call    cs:__imp_LeaveCriticalSection
0x14003d180  mov     rcx, r14; lpCriticalSection
0x14003d183  call    cs:__imp_EnterCriticalSection
0x14003d189  nop
0x14003d18a  xorps   xmm0, xmm0
0x14003d18d  movups  [rsp+0D8h+var_78], xmm0
0x14003d192  lea     rdx, [rsp+0D8h+var_58]
0x14003d19a  lea     rdi, ?m_lstIscsiInitiatorAdapters@CVdsService@@0VCRtlList@@A; CRtlList CVdsService::m_lstIscsiInitiatorAdapters
0x14003d1a1  mov     rcx, rdi
0x14003d1a4  call    cs:__imp_?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x14003d1aa  movups  xmm0, xmmword ptr [rax]
0x14003d1ad  movdqu  [rsp+0D8h+var_78], xmm0
0x14003d1b3  lea     rdx, [rsp+0D8h+var_58]
0x14003d1bb  mov     rcx, rdi
0x14003d1be  call    cs:__imp_?End@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::End(void)
0x14003d1c4  movups  xmm0, xmmword ptr [rax]
0x14003d1c7  movdqu  [rsp+0D8h+Buf2], xmm0
0x14003d1cd  mov     r8d, 10h; Size
0x14003d1d3  lea     rdx, [rsp+0D8h+Buf2]; Buf2
0x14003d1d8  lea     rcx, [rsp+0D8h+var_78]; Buf1
0x14003d1dd  call    memcmp_0
0x14003d1e2  test    eax, eax
0x14003d1e4  jz      short loc_14003D21D
0x14003d1e6  lea     rcx, [rsp+0D8h+var_78]
0x14003d1eb  call    cs:__imp_?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x14003d1f1  mov     rbx, rax
0x14003d1f4  test    rax, rax
0x14003d1f7  jz      short loc_14003D210
0x14003d1f9  mov     rcx, rax; this
0x14003d1fc  call    ?RemoveInitiatorPortals@CVdsIscsiInitiatorAdapterInternal@@QEAAXXZ; CVdsIscsiInitiatorAdapterInternal::RemoveInitiatorPortals(void)
0x14003d201  mov     rcx, [rbx]
0x14003d204  mov     rax, [rcx+10h]
0x14003d208  mov     rcx, rbx
0x14003d20b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d210  lea     rcx, [rsp+0D8h+var_78]
0x14003d215  call    cs:__imp_?Next@CRtlListIter@@QEAAAEAV1@XZ; CRtlListIter::Next(void)
0x14003d21b  jmp     short loc_14003D1B3
0x14003d21d  mov     rcx, rdi
0x14003d220  call    cs:__imp_?RemoveAll@CRtlList@@QEAAXXZ; CRtlList::RemoveAll(void)
0x14003d226  nop
0x14003d227  mov     rcx, r14; lpCriticalSection
0x14003d22a  call    cs:__imp_LeaveCriticalSection
0x14003d230  mov     rcx, r14; lpCriticalSection
0x14003d233  call    cs:__imp_EnterCriticalSection
0x14003d239  nop
0x14003d23a  xorps   xmm0, xmm0
0x14003d23d  xor     eax, eax
0x14003d23f  movups  [rsp+0D8h+var_B8], xmm0
0x14003d244  mov     [rsp+0D8h+var_A8], rax
0x14003d249  lea     rdx, [rsp+0D8h+var_58]
0x14003d251  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14003d258  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14003d25e  movups  xmm0, xmmword ptr [rax]
0x14003d261  movups  [rsp+0D8h+var_B8], xmm0
0x14003d266  movsd   xmm1, qword ptr [rax+10h]
0x14003d26b  movsd   [rsp+0D8h+var_A8], xmm1
0x14003d271  cmp     qword ptr [rsp+0D8h+var_B8], rsi
0x14003d276  jz      short loc_14003D2A4
0x14003d278  mov     rcx, qword ptr [rsp+0D8h+var_B8+8]
0x14003d27d  test    rcx, rcx
0x14003d280  jz      short loc_14003D2A4
0x14003d282  mov     rcx, [rcx+30h]
0x14003d286  test    rcx, rcx
0x14003d289  jz      short loc_14003D297
0x14003d28b  mov     rax, [rcx]
0x14003d28e  mov     rax, [rax+10h]
0x14003d292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d297  lea     rcx, [rsp+0D8h+var_B8]
0x14003d29c  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x14003d2a2  jmp     short loc_14003D271
0x14003d2a4  xor     edx, edx
0x14003d2a6  lea     rcx, ?m_mapUnallocatedDisks@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisks
0x14003d2ad  call    cs:__imp_?RemoveAll@CRtlMap@@QEAAXH@Z; CRtlMap::RemoveAll(int)
0x14003d2b3  lea     rdx, [rsp+0D8h+var_58]
0x14003d2bb  lea     rcx, ?m_mapUnallocatedDisksByDeviceId@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisksByDeviceId
0x14003d2c2  call    cs:__imp_?Begin@CRtlMap@@QEAA?AVCRtlMapIter@@XZ; CRtlMap::Begin(void)
0x14003d2c8  movups  xmm0, xmmword ptr [rax]
0x14003d2cb  movups  [rsp+0D8h+var_B8], xmm0
0x14003d2d0  movsd   xmm1, qword ptr [rax+10h]
0x14003d2d5  movsd   [rsp+0D8h+var_A8], xmm1
0x14003d2db  cmp     qword ptr [rsp+0D8h+var_B8], rsi
0x14003d2e0  jz      short loc_14003D319
0x14003d2e2  mov     rdi, qword ptr [rsp+0D8h+var_B8+8]
0x14003d2e7  test    rdi, rdi
0x14003d2ea  jz      short loc_14003D319
0x14003d2ec  mov     rbx, [rdi+10h]
0x14003d2f0  call    cs:__imp_GetProcessHeap
0x14003d2f6  mov     r8, rbx
0x14003d2f9  xor     edx, edx
0x14003d2fb  mov     rcx, rax
0x14003d2fe  call    cs:__imp_VdsHeapFree
0x14003d304  mov     [rdi+8], rsi
0x14003d308  mov     [rdi+10h], rsi
0x14003d30c  lea     rcx, [rsp+0D8h+var_B8]
0x14003d311  call    cs:__imp_?Next@CRtlMapIter@@QEAAAEAV1@XZ; CRtlMapIter::Next(void)
0x14003d317  jmp     short loc_14003D2DB
0x14003d319  xor     edx, edx
0x14003d31b  lea     rcx, ?m_mapUnallocatedDisksByDeviceId@CVdsService@@0VCRtlMap@@A; CRtlMap CVdsService::m_mapUnallocatedDisksByDeviceId
0x14003d322  call    cs:__imp_?RemoveAll@CRtlMap@@QEAAXH@Z; CRtlMap::RemoveAll(int)
0x14003d328  nop
0x14003d329  mov     rcx, r14; lpCriticalSection
0x14003d32c  call    cs:__imp_LeaveCriticalSection
0x14003d332  mov     rcx, r14; lpCriticalSection
0x14003d335  call    cs:__imp_EnterCriticalSection
0x14003d33b  nop
0x14003d33c  xor     edx, edx; struct _VDSSVC_PROVIDER_LIST **
0x14003d33e  lea     rcx, ?m_lstSoftwareProviders@CVdsService@@2VCRtlList@@A; struct CRtlList *
0x14003d345  call    ?UnloadProviders@CVdsService@@CAXAEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z; CVdsService::UnloadProviders(CRtlList &,_VDSSVC_PROVIDER_LIST * *)
0x14003d34a  nop
0x14003d34b  mov     rcx, r14; lpCriticalSection
0x14003d34e  call    cs:__imp_LeaveCriticalSection
0x14003d354  lea     rdx, ?m_pVdsHardwareProviderList@CVdsService@@0PEAU_VDSSVC_PROVIDER_LIST@@EA; struct _VDSSVC_PROVIDER_LIST **
0x14003d35b  lea     rcx, ?m_lstHardwareProviders@CVdsService@@2VCRtlList@@A; struct CRtlList *
0x14003d362  call    ?UnloadProviders@CVdsService@@CAXAEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z; CVdsService::UnloadProviders(CRtlList &,_VDSSVC_PROVIDER_LIST * *)
0x14003d367  xor     edx, edx; struct _VDSSVC_PROVIDER_LIST **
0x14003d369  lea     rcx, ?m_lstVirtualDiskProviders@CVdsService@@2VCRtlList@@A; struct CRtlList *
0x14003d370  call    ?UnloadProviders@CVdsService@@CAXAEAVCRtlList@@PEAPEAU_VDSSVC_PROVIDER_LIST@@@Z; CVdsService::UnloadProviders(CRtlList &,_VDSSVC_PROVIDER_LIST * *)
0x14003d375  mov     rcx, cs:?m_pCallbackObject@CVdsService@@0PEAVCVdsCallbackObject@@EA; CVdsCallbackObject * CVdsService::m_pCallbackObject
0x14003d37c  test    rcx, rcx
0x14003d37f  jz      short loc_14003D394
0x14003d381  mov     rax, [rcx]
0x14003d384  mov     rax, [rax+10h]
0x14003d388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003d38d  mov     cs:?m_pCallbackObject@CVdsService@@0PEAVCVdsCallbackObject@@EA, rsi; CVdsCallbackObject * CVdsService::m_pCallbackObject
0x14003d394  call    cs:__imp_?Uninitialize@CVdsAsyncObjectBase@@SAXXZ; CVdsAsyncObjectBase::Uninitialize(void)
0x14003d39a  mov     rcx, cs:?m_hProvidersLoadedEvent@CVdsService@@0PEAXEA; hObject
0x14003d3a1  test    rcx, rcx
0x14003d3a4  jz      short loc_14003D3B3
0x14003d3a6  call    cs:__imp_CloseHandle
0x14003d3ac  mov     cs:?m_hProvidersLoadedEvent@CVdsService@@0PEAXEA, rsi; void * CVdsService::m_hProvidersLoadedEvent
0x14003d3b3  mov     rcx, cs:?m_hRemoveObsoleteDevNodesEvent@CVdsService@@0PEAXEA; hObject
0x14003d3ba  test    rcx, rcx
0x14003d3bd  jz      short loc_14003D3CC
0x14003d3bf  call    cs:__imp_CloseHandle
0x14003d3c5  mov     cs:?m_hRemoveObsoleteDevNodesEvent@CVdsService@@0PEAXEA, rsi; void * CVdsService::m_hRemoveObsoleteDevNodesEvent
0x14003d3cc  lea     rcx, ?SETranslationFunction@CVdsService@@CAXIPEAU_EXCEPTION_POINTERS@@@Z; CVdsService::SETranslationFunction(uint,_EXCEPTION_POINTERS *)
0x14003d3d3  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x14003d3d9  mov     rbx, rax
0x14003d3dc  mov     [rsp+0D8h+arg_0], rax
0x14003d3e4  call    cs:__imp_CoUninitialize
0x14003d3ea  nop
0x14003d3eb  jmp     short loc_14003D3F5
0x14003d3ed  mov     rbx, [rsp+0D8h+arg_0]
0x14003d3f5  mov     rcx, rbx
0x14003d3f8  call    cs:__imp_?_set_se_translator@@YAP6AXIPEAU_EXCEPTION_POINTERS@@@ZP6AXI0@Z@Z; _set_se_translator(void (*)(uint,_EXCEPTION_POINTERS *))
0x14003d3fe  nop
0x14003d3ff  lea     rcx, [rsp+0D8h+var_40]
0x14003d407  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14003d40d  add     rsp, 0B8h
0x14003d414  pop     r14
0x14003d416  pop     rdi
0x14003d417  pop     rsi
0x14003d418  pop     rbx
0x14003d419  retn
```
