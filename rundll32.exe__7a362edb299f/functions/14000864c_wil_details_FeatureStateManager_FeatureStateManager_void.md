# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000864c`
- end: `0x140008838`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000b3f0`

## callees

- `0x140008508`
- `0x14000864c`
- `0x14000a168`
- `0x14000a688`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008771`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400087b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140008771`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400087b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008718`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008768`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400087a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008718`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140008768`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400087a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000870a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000875a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000879a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000870a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000875a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000879a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000866a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400086b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000866a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400086b3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000869c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400086e5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000869c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400086e5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000868b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400086d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400087da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000880b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000868b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400086d4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400087da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000880b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008694`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400086dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400087e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008814`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008694`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400086dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400087e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140008814`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000867d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400086c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400087cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400087fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000867d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400086c6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400087cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400087fd`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(wil::details::FeatureStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rsi
  DWORD v5; // ebx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *v8; // r8
  void *v9; // rsi
  HANDLE v10; // rax
  void *v11; // rsi
  HANDLE v12; // rax
  struct _TP_TIMER *v13; // rbx
  struct _TP_TIMER *v14; // rbx
  void *v15; // rcx

  *(_BYTE *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v4 )
  {
    v5 = GetLastError();
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
    SetLastError(v5);
  }
  *((_QWORD *)this + 7) = 0;
  v6 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)*((_QWORD *)this + 28);
  if ( v8 && qword_140012028 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_140012028[25], qword_140012028, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v11 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v11 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v11);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v13 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v13 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (void *)*((_QWORD *)this + 2);
  if ( v15 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v15);
}

```

## disassembly

```asm
0x14000864c  mov     [rsp+arg_0], rbx
0x140008651  mov     [rsp+arg_8], rsi
0x140008656  push    rdi
0x140008657  sub     rsp, 20h
0x14000865b  mov     byte ptr [rcx], 0
0x14000865e  mov     rdi, rcx
0x140008661  mov     rsi, [rcx+30h]
0x140008665  test    rsi, rsi
0x140008668  jz      short loc_1400086A2
0x14000866a  call    cs:__imp_GetLastError
0x140008670  xor     r9d, r9d; msWindowLength
0x140008673  xor     r8d, r8d; msPeriod
0x140008676  xor     edx, edx; pftDueTime
0x140008678  mov     rcx, rsi; pti
0x14000867b  mov     ebx, eax
0x14000867d  call    cs:__imp_SetThreadpoolTimer
0x140008683  mov     edx, 1; fCancelPendingCallbacks
0x140008688  mov     rcx, rsi; pti
0x14000868b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008691  mov     rcx, rsi; pti
0x140008694  call    cs:__imp_CloseThreadpoolTimer
0x14000869a  mov     ecx, ebx; dwErrCode
0x14000869c  call    cs:__imp_SetLastError
0x1400086a2  mov     qword ptr [rdi+30h], 0
0x1400086aa  mov     rsi, [rdi+38h]
0x1400086ae  test    rsi, rsi
0x1400086b1  jz      short loc_1400086EB
0x1400086b3  call    cs:__imp_GetLastError
0x1400086b9  xor     r9d, r9d; msWindowLength
0x1400086bc  xor     r8d, r8d; msPeriod
0x1400086bf  xor     edx, edx; pftDueTime
0x1400086c1  mov     rcx, rsi; pti
0x1400086c4  mov     ebx, eax
0x1400086c6  call    cs:__imp_SetThreadpoolTimer
0x1400086cc  mov     edx, 1; fCancelPendingCallbacks
0x1400086d1  mov     rcx, rsi; pti
0x1400086d4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400086da  mov     rcx, rsi; pti
0x1400086dd  call    cs:__imp_CloseThreadpoolTimer
0x1400086e3  mov     ecx, ebx; dwErrCode
0x1400086e5  call    cs:__imp_SetLastError
0x1400086eb  mov     qword ptr [rdi+38h], 0
0x1400086f3  mov     rbx, [rdi+100h]
0x1400086fa  mov     qword ptr [rdi+100h], 0
0x140008705  test    rbx, rbx
0x140008708  jz      short loc_14000871E
0x14000870a  call    cs:__imp_GetProcessHeap
0x140008710  mov     r8, rbx; lpMem
0x140008713  xor     edx, edx; dwFlags
0x140008715  mov     rcx, rax; hHeap
0x140008718  call    cs:__imp_HeapFree
0x14000871e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140008725  test    r8, r8
0x140008728  jz      short loc_140008742
0x14000872a  mov     rdx, cs:qword_140012028; SRWLock
0x140008731  test    rdx, rdx
0x140008734  jz      short loc_140008742
0x140008736  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000873d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x140008742  lea     rbx, [rdi+98h]
0x140008749  mov     rsi, [rbx+40h]
0x14000874d  mov     qword ptr [rbx+40h], 0
0x140008755  test    rsi, rsi
0x140008758  jz      short loc_14000876E
0x14000875a  call    cs:__imp_GetProcessHeap
0x140008760  mov     r8, rsi; lpMem
0x140008763  xor     edx, edx; dwFlags
0x140008765  mov     rcx, rax; hHeap
0x140008768  call    cs:__imp_HeapFree
0x14000876e  mov     rcx, rbx; lpCriticalSection
0x140008771  call    cs:__imp_DeleteCriticalSection
0x140008777  lea     rcx, [rdi+90h]
0x14000877e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140008783  mov     rsi, [rdi+88h]
0x14000878a  mov     qword ptr [rdi+88h], 0
0x140008795  test    rsi, rsi
0x140008798  jz      short loc_1400087AE
0x14000879a  call    cs:__imp_GetProcessHeap
0x1400087a0  mov     r8, rsi; lpMem
0x1400087a3  xor     edx, edx; dwFlags
0x1400087a5  mov     rcx, rax; hHeap
0x1400087a8  call    cs:__imp_HeapFree
0x1400087ae  lea     rcx, [rdi+48h]; lpCriticalSection
0x1400087b2  call    cs:__imp_DeleteCriticalSection
0x1400087b8  mov     rbx, [rdi+38h]
0x1400087bc  test    rbx, rbx
0x1400087bf  jz      short loc_1400087E9
0x1400087c1  xor     r9d, r9d; msWindowLength
0x1400087c4  xor     r8d, r8d; msPeriod
0x1400087c7  xor     edx, edx; pftDueTime
0x1400087c9  mov     rcx, rbx; pti
0x1400087cc  call    cs:__imp_SetThreadpoolTimer
0x1400087d2  mov     edx, 1; fCancelPendingCallbacks
0x1400087d7  mov     rcx, rbx; pti
0x1400087da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400087e0  mov     rcx, rbx; pti
0x1400087e3  call    cs:__imp_CloseThreadpoolTimer
0x1400087e9  mov     rbx, [rdi+30h]
0x1400087ed  test    rbx, rbx
0x1400087f0  jz      short loc_14000881A
0x1400087f2  xor     r9d, r9d; msWindowLength
0x1400087f5  xor     r8d, r8d; msPeriod
0x1400087f8  xor     edx, edx; pftDueTime
0x1400087fa  mov     rcx, rbx; pti
0x1400087fd  call    cs:__imp_SetThreadpoolTimer
0x140008803  mov     edx, 1; fCancelPendingCallbacks
0x140008808  mov     rcx, rbx; pti
0x14000880b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008811  mov     rcx, rbx; pti
0x140008814  call    cs:__imp_CloseThreadpoolTimer
0x14000881a  mov     rcx, [rdi+10h]; lpMem
0x14000881e  test    rcx, rcx
0x140008821  jz      short loc_140008828
0x140008823  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140008828  mov     rbx, [rsp+28h+arg_0]
0x14000882d  mov     rsi, [rsp+28h+arg_8]
0x140008832  add     rsp, 20h
0x140008836  pop     rdi
0x140008837  retn
```
