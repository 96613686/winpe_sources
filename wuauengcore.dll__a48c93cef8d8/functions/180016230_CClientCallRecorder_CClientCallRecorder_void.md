# CClientCallRecorder::~CClientCallRecorder(void)

- ea: `0x180016230`
- end: `0x1800164f7`
- name: `??1CClientCallRecorder@@UEAA@XZ`
- size: `711`
- prototype: `void __fastcall(CClientCallRecorder *__hidden this)`
- caller_count: `4`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x180013b6c`
- `0x180014c74`
- `0x180015210`
- `0x180241dbd`

## callees

- `0x180015568`
- `0x1800156dc`
- `0x180015868`
- `0x18001596c`
- `0x1800159a8`
- `0x180015c98`
- `0x180015de0`
- `0x180015e28`
- `0x1800161b4`
- `0x180016230`
- `0x18011333c`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016343`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016343`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016331`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001640e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001644e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016331`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001640e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001644e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016433`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163e9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016433`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016405`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016445`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016405`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016445`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001637b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001637b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800163b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CClientCallRecorder::~CClientCallRecorder(CClientCallRecorder *this)
{
  CWuaClassFactoryBase *v2; // r14
  void (__fastcall ***v3)(_QWORD, __int64); // rcx
  HMODULE v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdx

  *(_QWORD *)this = &CClientCallRecorder::`vftable'{for `ISusInternal'};
  *((_QWORD *)this + 1) = &CClientCallRecorder::`vftable'{for `ISusInternalUpgrade'};
  *((_QWORD *)this + 2) = &CClientCallRecorder::`vftable'{for `ISusInternalPrivate'};
  *((_QWORD *)this + 3) = &CClientCallRecorder::`vftable'{for `ISusInternalLocal'};
  *((_QWORD *)this + 4) = &CClientCallRecorder::`vftable'{for `ISusWorker'};
  v2 = (CClientCallRecorder *)((char *)this + 40);
  *((_QWORD *)this + 5) = &CClientCallRecorder::`vftable'{for `CWuaSingletonClassFactory'};
  *((_QWORD *)this + 11) = &CClientCallRecorder::`vftable'{for `ISusRebootStatus'};
  *((_QWORD *)this + 12) = &CClientCallRecorder::`vftable'{for `ISubmitWorkItem'};
  *((_QWORD *)this + 13) = &CClientCallRecorder::`vftable'{for `IGetBundleInfo'};
  *((_QWORD *)this + 14) = &CClientCallRecorder::`vftable'{for `IPersistDownloadCalls'};
  *((_QWORD *)this + 15) = &CClientCallRecorder::`vftable'{for `IUpdateDeploymentHasEnded'};
  *((_QWORD *)this + 16) = &CClientCallRecorder::`vftable'{for `ISusServiceStatus'};
  *((_QWORD *)this + 17) = &CClientCallRecorder::`vftable'{for `IWUUpdateDeploymentData'};
  *((_QWORD *)this + 18) = &CClientCallRecorder::`vftable'{for `IWUInternalTelemetryFactory'};
  v3 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 84);
  *((_QWORD *)this + 84) = 0;
  if ( v3 )
    (**v3)(v3, 1);
  CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>::~CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>((char *)this + 648);
  *((_QWORD *)this + 75) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
  v4 = (HMODULE)*((_QWORD *)this + 74);
  if ( v4 )
  {
    FreeLibrary(v4);
    *((_QWORD *)this + 74) = 0;
  }
  v5 = *((_QWORD *)this + 73);
  if ( v5 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    *((_QWORD *)this + 73) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 72);
  if ( v6 )
  {
    CloseHandle(v6);
    *((_QWORD *)this + 72) = 0;
  }
  v7 = *((_QWORD *)this + 71);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 71) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 70);
  if ( v8 )
  {
    CloseHandle(v8);
    *((_QWORD *)this + 70) = 0;
  }
  v9 = *((_QWORD *)this + 57);
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    *((_QWORD *)this + 57) = 0;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::RemoveArraySection(
    (char *)this + 408,
    v10,
    0xFFFFFFFFLL,
    1);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 368));
  CSusArrayList<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>>::~CSusArrayList<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>>((char *)this + 408);
  CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>((char *)this + 336);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  CSusArrayList<CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::_tagMapEntry,CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::CMapEntryOps>::RemoveArraySection((char *)this + 304);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  CSusArrayList<CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::_tagMapEntry,CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::_tagMapEntry,CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::CMapEntryOps>((char *)this + 304);
  CSusArrayList<unsigned long,CSusArrayListItemOpNoop<unsigned long>>::~CSusArrayList<unsigned long,CSusArrayListItemOpNoop<unsigned long>>((char *)this + 232);
  CSusListIterator<CClientRegistrationEntry>::~CSusListIterator<CClientRegistrationEntry>((char *)this + 192);
  *((_QWORD *)this + 19) = &CSusListIterator<CSusAsyncCall>::`vftable';
  CSusListIterator<CSusAsyncCall>::~CSusListIterator<CSusAsyncCall>();
  *((_QWORD *)this + 16) = &CBaseContentHandler::`vftable';
  *((_QWORD *)this + 15) = &CBaseContentHandler::`vftable';
  *((_QWORD *)this + 14) = &IReportingEventEnumerator<CUpdateManagerReportingEvent>::`vftable';
  *((_QWORD *)this + 13) = &CBaseContentHandler::`vftable';
  *((_QWORD *)this + 12) = &CBaseContentHandler::`vftable';
  *((_QWORD *)this + 11) = &ISusRebootStatus::`vftable';
  *(_QWORD *)v2 = &CWuaSingletonClassFactory::`vftable';
  CWuaClassFactoryBase::~CWuaClassFactoryBase(v2);
}

```

## disassembly

```asm
0x180016230  mov     [rsp+arg_0], rbx
0x180016235  mov     [rsp+arg_8], rsi
0x18001623a  mov     [rsp+arg_10], rdi
0x18001623f  push    r14
0x180016241  sub     rsp, 20h
0x180016245  mov     rsi, rcx
0x180016248  lea     rax, ??_7CClientCallRecorder@@6BISusInternal@@@; const CClientCallRecorder::`vftable'{for `ISusInternal'}
0x18001624f  mov     [rcx], rax
0x180016252  lea     rax, ??_7CClientCallRecorder@@6BISusInternalUpgrade@@@; const CClientCallRecorder::`vftable'{for `ISusInternalUpgrade'}
0x180016259  mov     [rcx+8], rax
0x18001625d  lea     rax, ??_7CClientCallRecorder@@6BISusInternalPrivate@@@; const CClientCallRecorder::`vftable'{for `ISusInternalPrivate'}
0x180016264  mov     [rcx+10h], rax
0x180016268  lea     rax, ??_7CClientCallRecorder@@6BISusInternalLocal@@@; const CClientCallRecorder::`vftable'{for `ISusInternalLocal'}
0x18001626f  mov     [rcx+18h], rax
0x180016273  lea     rax, ??_7CClientCallRecorder@@6BISusWorker@@@; const CClientCallRecorder::`vftable'{for `ISusWorker'}
0x18001627a  mov     [rcx+20h], rax
0x18001627e  lea     r14, [rcx+28h]
0x180016282  lea     rax, ??_7CClientCallRecorder@@6BCWuaSingletonClassFactory@@@; const CClientCallRecorder::`vftable'{for `CWuaSingletonClassFactory'}
0x180016289  mov     [r14], rax
0x18001628c  lea     rax, ??_7CClientCallRecorder@@6BISusRebootStatus@@@; const CClientCallRecorder::`vftable'{for `ISusRebootStatus'}
0x180016293  mov     [rcx+58h], rax
0x180016297  lea     rax, ??_7CClientCallRecorder@@6BISubmitWorkItem@@@; const CClientCallRecorder::`vftable'{for `ISubmitWorkItem'}
0x18001629e  mov     [rcx+60h], rax
0x1800162a2  lea     rax, ??_7CClientCallRecorder@@6BIGetBundleInfo@@@; const CClientCallRecorder::`vftable'{for `IGetBundleInfo'}
0x1800162a9  mov     [rcx+68h], rax
0x1800162ad  lea     rax, ??_7CClientCallRecorder@@6BIPersistDownloadCalls@@@; const CClientCallRecorder::`vftable'{for `IPersistDownloadCalls'}
0x1800162b4  mov     [rcx+70h], rax
0x1800162b8  lea     rax, ??_7CClientCallRecorder@@6BIUpdateDeploymentHasEnded@@@; const CClientCallRecorder::`vftable'{for `IUpdateDeploymentHasEnded'}
0x1800162bf  mov     [rcx+78h], rax
0x1800162c3  lea     rax, ??_7CClientCallRecorder@@6BISusServiceStatus@@@; const CClientCallRecorder::`vftable'{for `ISusServiceStatus'}
0x1800162ca  mov     [rcx+80h], rax
0x1800162d1  lea     rax, ??_7CClientCallRecorder@@6BIWUUpdateDeploymentData@@@; const CClientCallRecorder::`vftable'{for `IWUUpdateDeploymentData'}
0x1800162d8  mov     [rcx+88h], rax
0x1800162df  lea     rax, ??_7CClientCallRecorder@@6BIWUInternalTelemetryFactory@@@; const CClientCallRecorder::`vftable'{for `IWUInternalTelemetryFactory'}
0x1800162e6  mov     [rcx+90h], rax
0x1800162ed  mov     rcx, [rcx+2A0h]
0x1800162f4  xor     ebx, ebx
0x1800162f6  mov     [rsi+2A0h], rbx
0x1800162fd  test    rcx, rcx
0x180016300  jz      short loc_180016310
0x180016302  mov     rax, [rcx]
0x180016305  lea     edx, [rbx+1]
0x180016308  mov     rax, [rax]
0x18001630b  call    _guard_dispatch_icall
0x180016310  lea     rcx, [rsi+288h]
0x180016317  call    ??1?$CSusArrayList@PEAUtagUpdateDeploymentSessionHostInfo@@V?$CSusArrayListItemOpDelete@PEAUtagUpdateDeploymentSessionHostInfo@@@@@@UEAA@XZ; CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>::~CSusArrayList<tagUpdateDeploymentSessionHostInfo *,CSusArrayListItemOpDelete<tagUpdateDeploymentSessionHostInfo *>>(void)
0x18001631c  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x180016323  mov     [rsi+258h], rax
0x18001632a  lea     rcx, [rsi+260h]; lpCriticalSection
0x180016331  call    cs:__imp_DeleteCriticalSection
0x180016337  mov     rcx, [rsi+250h]; hLibModule
0x18001633e  test    rcx, rcx
0x180016341  jz      short loc_180016350
0x180016343  call    cs:__imp_FreeLibrary
0x180016349  mov     [rsi+250h], rbx
0x180016350  mov     rcx, [rsi+248h]
0x180016357  test    rcx, rcx
0x18001635a  jz      short loc_18001636F
0x18001635c  mov     rax, [rcx]
0x18001635f  mov     rax, [rax+10h]
0x180016363  call    _guard_dispatch_icall
0x180016368  mov     [rsi+248h], rbx
0x18001636f  mov     rcx, [rsi+240h]; hObject
0x180016376  test    rcx, rcx
0x180016379  jz      short loc_180016388
0x18001637b  call    cs:__imp_CloseHandle
0x180016381  mov     [rsi+240h], rbx
0x180016388  mov     rcx, [rsi+238h]
0x18001638f  test    rcx, rcx
0x180016392  jz      short loc_1800163A7
0x180016394  mov     rax, [rcx]
0x180016397  mov     rax, [rax+10h]
0x18001639b  call    _guard_dispatch_icall
0x1800163a0  mov     [rsi+238h], rbx
0x1800163a7  mov     rcx, [rsi+230h]; hObject
0x1800163ae  test    rcx, rcx
0x1800163b1  jz      short loc_1800163C0
0x1800163b3  call    cs:__imp_CloseHandle
0x1800163b9  mov     [rsi+230h], rbx
0x1800163c0  mov     rcx, [rsi+1C8h]
0x1800163c7  test    rcx, rcx
0x1800163ca  jz      short loc_1800163DF
0x1800163cc  mov     rax, [rcx]
0x1800163cf  mov     rax, [rax+10h]
0x1800163d3  call    _guard_dispatch_icall
0x1800163d8  mov     [rsi+1C8h], rbx
0x1800163df  lea     rdi, [rsi+170h]
0x1800163e6  mov     rcx, rdi; lpCriticalSection
0x1800163e9  call    cs:__imp_EnterCriticalSection
0x1800163ef  mov     r9d, 1
0x1800163f5  or      r8d, 0FFFFFFFFh
0x1800163f9  lea     rcx, [rdi+28h]
0x1800163fd  call    ?RemoveArraySection@?$CSusArrayList@PEA_WV?$CSusArrayListItemOpSusFree@PEA_W@@@@IEAAXKKH@Z; CSusArrayList<wchar_t *,CSusArrayListItemOpSusFree<wchar_t *>>::RemoveArraySection(ulong,ulong,int)
0x180016402  mov     rcx, rdi; lpCriticalSection
0x180016405  call    cs:__imp_LeaveCriticalSection
0x18001640b  mov     rcx, rdi; lpCriticalSection
0x18001640e  call    cs:__imp_DeleteCriticalSection
0x180016414  lea     rcx, [rdi+28h]
0x180016418  call    ??1?$CSusArrayList@PEAUtagSusAsyncCallInfo@@V?$CSusArrayListItemOpSusFree@PEAUtagSusAsyncCallInfo@@@@@@UEAA@XZ; CSusArrayList<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>>::~CSusArrayList<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>>(void)
0x18001641d  lea     rcx, [rsi+150h]
0x180016424  call    ??1?$CSusArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@UEAA@XZ; CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>::~CSusArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>>(void)
0x180016429  lea     rdi, [rsi+108h]
0x180016430  mov     rcx, rdi; lpCriticalSection
0x180016433  call    cs:__imp_EnterCriticalSection
0x180016439  lea     rcx, [rdi+28h]
0x18001643d  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAV?$CSusThreadSafeArray@PEAUtagSusAsyncCallInfo@@V?$CSusArrayListItemOpSusFree@PEAUtagSusAsyncCallInfo@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusThreadSafeArray@PEAUtagSusAsyncCallInfo@@V?$CSusArrayListItemOpSusFree@PEAUtagSusAsyncCallInfo@@@@@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::_tagMapEntry,CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x180016442  mov     rcx, rdi; lpCriticalSection
0x180016445  call    cs:__imp_LeaveCriticalSection
0x18001644b  mov     rcx, rdi; lpCriticalSection
0x18001644e  call    cs:__imp_DeleteCriticalSection
0x180016454  lea     rcx, [rdi+28h]
0x180016458  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAV?$CSusThreadSafeArray@PEAUtagSusAsyncCallInfo@@V?$CSusArrayListItemOpSusFree@PEAUtagSusAsyncCallInfo@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusThreadSafeArray@PEAUtagSusAsyncCallInfo@@V?$CSusArrayListItemOpSusFree@PEAUtagSusAsyncCallInfo@@@@@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::_tagMapEntry,CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::CMapEntryOps>::~CSusArrayList<CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::_tagMapEntry,CSusMap<_GUID,CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusThreadSafeArray<tagSusAsyncCallInfo *,CSusArrayListItemOpSusFree<tagSusAsyncCallInfo *>> *>>::CMapEntryOps>(void)
0x18001645d  lea     rcx, [rsi+0E8h]
0x180016464  call    ??1?$CSusArrayList@KV?$CSusArrayListItemOpNoop@K@@@@UEAA@XZ; CSusArrayList<ulong,CSusArrayListItemOpNoop<ulong>>::~CSusArrayList<ulong,CSusArrayListItemOpNoop<ulong>>(void)
0x180016469  lea     rcx, [rsi+0C0h]
0x180016470  call    ??1?$CSusListIterator@VCClientRegistrationEntry@@@@QEAA@XZ; CSusListIterator<CClientRegistrationEntry>::~CSusListIterator<CClientRegistrationEntry>(void)
0x180016475  lea     rcx, [rsi+98h]
0x18001647c  lea     rax, ??_7?$CSusListIterator@VCSusAsyncCall@@@@6B@; const CSusListIterator<CSusAsyncCall>::`vftable'
0x180016483  mov     [rcx], rax
0x180016486  call    ??1?$CSusListIterator@VCSusAsyncCall@@@@QEAA@XZ; CSusListIterator<CSusAsyncCall>::~CSusListIterator<CSusAsyncCall>(void)
0x18001648b  lea     rax, ??_7CBaseContentHandler@@6B@; const CBaseContentHandler::`vftable'
0x180016492  mov     [rsi+80h], rax
0x180016499  lea     rax, ??_7CBaseContentHandler@@6B@; const CBaseContentHandler::`vftable'
0x1800164a0  mov     [rsi+78h], rax
0x1800164a4  lea     rax, ??_7?$IReportingEventEnumerator@VCUpdateManagerReportingEvent@@@@6B@; const IReportingEventEnumerator<CUpdateManagerReportingEvent>::`vftable'
0x1800164ab  mov     [rsi+70h], rax
0x1800164af  lea     rax, ??_7CBaseContentHandler@@6B@; const CBaseContentHandler::`vftable'
0x1800164b6  mov     [rsi+68h], rax
0x1800164ba  lea     rax, ??_7CBaseContentHandler@@6B@; const CBaseContentHandler::`vftable'
0x1800164c1  mov     [rsi+60h], rax
0x1800164c5  lea     rax, ??_7ISusRebootStatus@@6B@; const ISusRebootStatus::`vftable'
0x1800164cc  mov     [rsi+58h], rax
0x1800164d0  lea     rax, ??_7CWuaSingletonClassFactory@@6B@; const CWuaSingletonClassFactory::`vftable'
0x1800164d7  mov     [r14], rax
0x1800164da  mov     rcx, r14; this
0x1800164dd  mov     rbx, [rsp+28h+arg_0]
0x1800164e2  mov     rsi, [rsp+28h+arg_8]
0x1800164e7  mov     rdi, [rsp+28h+arg_10]
0x1800164ec  add     rsp, 20h
0x1800164f0  pop     r14
0x1800164f2  jmp     ??1CWuaClassFactoryBase@@MEAA@XZ; CWuaClassFactoryBase::~CWuaClassFactoryBase(void)
```
