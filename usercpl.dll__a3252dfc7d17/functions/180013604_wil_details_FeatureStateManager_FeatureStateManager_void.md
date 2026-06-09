# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180013604`
- end: `0x1800137f0`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180077840`

## callees

- `0x180013304`
- `0x180013604`
- `0x180017acc`
- `0x1800187a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013729`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001376a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013729`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001376a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800136d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013760`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800136d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013720`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013760`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800136c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013752`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800136c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013712`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013752`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001366b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013622`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001366b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013654`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001369d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013654`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001369d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013643`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001368c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013792`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800137c3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013643`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001368c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013792`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800137c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013635`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001367e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013784`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800137b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013635`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001367e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013784`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800137b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001364c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013695`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001379b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800137cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001364c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013695`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001379b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800137cc`

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
  if ( v8 && qword_1800A1388 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800A1388[25], qword_1800A1388, v8);
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
0x180013604  mov     [rsp+arg_0], rbx
0x180013609  mov     [rsp+arg_8], rsi
0x18001360e  push    rdi
0x18001360f  sub     rsp, 20h
0x180013613  mov     byte ptr [rcx], 0
0x180013616  mov     rdi, rcx
0x180013619  mov     rsi, [rcx+30h]
0x18001361d  test    rsi, rsi
0x180013620  jz      short loc_18001365A
0x180013622  call    cs:__imp_GetLastError
0x180013628  xor     r9d, r9d; msWindowLength
0x18001362b  xor     r8d, r8d; msPeriod
0x18001362e  xor     edx, edx; pftDueTime
0x180013630  mov     rcx, rsi; pti
0x180013633  mov     ebx, eax
0x180013635  call    cs:__imp_SetThreadpoolTimer
0x18001363b  mov     edx, 1; fCancelPendingCallbacks
0x180013640  mov     rcx, rsi; pti
0x180013643  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013649  mov     rcx, rsi; pti
0x18001364c  call    cs:__imp_CloseThreadpoolTimer
0x180013652  mov     ecx, ebx; dwErrCode
0x180013654  call    cs:__imp_SetLastError
0x18001365a  mov     qword ptr [rdi+30h], 0
0x180013662  mov     rsi, [rdi+38h]
0x180013666  test    rsi, rsi
0x180013669  jz      short loc_1800136A3
0x18001366b  call    cs:__imp_GetLastError
0x180013671  xor     r9d, r9d; msWindowLength
0x180013674  xor     r8d, r8d; msPeriod
0x180013677  xor     edx, edx; pftDueTime
0x180013679  mov     rcx, rsi; pti
0x18001367c  mov     ebx, eax
0x18001367e  call    cs:__imp_SetThreadpoolTimer
0x180013684  mov     edx, 1; fCancelPendingCallbacks
0x180013689  mov     rcx, rsi; pti
0x18001368c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013692  mov     rcx, rsi; pti
0x180013695  call    cs:__imp_CloseThreadpoolTimer
0x18001369b  mov     ecx, ebx; dwErrCode
0x18001369d  call    cs:__imp_SetLastError
0x1800136a3  mov     qword ptr [rdi+38h], 0
0x1800136ab  mov     rbx, [rdi+100h]
0x1800136b2  mov     qword ptr [rdi+100h], 0
0x1800136bd  test    rbx, rbx
0x1800136c0  jz      short loc_1800136D6
0x1800136c2  call    cs:__imp_GetProcessHeap
0x1800136c8  mov     r8, rbx; lpMem
0x1800136cb  xor     edx, edx; dwFlags
0x1800136cd  mov     rcx, rax; hHeap
0x1800136d0  call    cs:__imp_HeapFree
0x1800136d6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800136dd  test    r8, r8
0x1800136e0  jz      short loc_1800136FA
0x1800136e2  mov     rdx, cs:qword_1800A1388; SRWLock
0x1800136e9  test    rdx, rdx
0x1800136ec  jz      short loc_1800136FA
0x1800136ee  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800136f5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800136fa  lea     rbx, [rdi+98h]
0x180013701  mov     rsi, [rbx+40h]
0x180013705  mov     qword ptr [rbx+40h], 0
0x18001370d  test    rsi, rsi
0x180013710  jz      short loc_180013726
0x180013712  call    cs:__imp_GetProcessHeap
0x180013718  mov     r8, rsi; lpMem
0x18001371b  xor     edx, edx; dwFlags
0x18001371d  mov     rcx, rax; hHeap
0x180013720  call    cs:__imp_HeapFree
0x180013726  mov     rcx, rbx; lpCriticalSection
0x180013729  call    cs:__imp_DeleteCriticalSection
0x18001372f  lea     rcx, [rdi+90h]
0x180013736  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18001373b  mov     rsi, [rdi+88h]
0x180013742  mov     qword ptr [rdi+88h], 0
0x18001374d  test    rsi, rsi
0x180013750  jz      short loc_180013766
0x180013752  call    cs:__imp_GetProcessHeap
0x180013758  mov     r8, rsi; lpMem
0x18001375b  xor     edx, edx; dwFlags
0x18001375d  mov     rcx, rax; hHeap
0x180013760  call    cs:__imp_HeapFree
0x180013766  lea     rcx, [rdi+48h]; lpCriticalSection
0x18001376a  call    cs:__imp_DeleteCriticalSection
0x180013770  mov     rbx, [rdi+38h]
0x180013774  test    rbx, rbx
0x180013777  jz      short loc_1800137A1
0x180013779  xor     r9d, r9d; msWindowLength
0x18001377c  xor     r8d, r8d; msPeriod
0x18001377f  xor     edx, edx; pftDueTime
0x180013781  mov     rcx, rbx; pti
0x180013784  call    cs:__imp_SetThreadpoolTimer
0x18001378a  mov     edx, 1; fCancelPendingCallbacks
0x18001378f  mov     rcx, rbx; pti
0x180013792  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013798  mov     rcx, rbx; pti
0x18001379b  call    cs:__imp_CloseThreadpoolTimer
0x1800137a1  mov     rbx, [rdi+30h]
0x1800137a5  test    rbx, rbx
0x1800137a8  jz      short loc_1800137D2
0x1800137aa  xor     r9d, r9d; msWindowLength
0x1800137ad  xor     r8d, r8d; msPeriod
0x1800137b0  xor     edx, edx; pftDueTime
0x1800137b2  mov     rcx, rbx; pti
0x1800137b5  call    cs:__imp_SetThreadpoolTimer
0x1800137bb  mov     edx, 1; fCancelPendingCallbacks
0x1800137c0  mov     rcx, rbx; pti
0x1800137c3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800137c9  mov     rcx, rbx; pti
0x1800137cc  call    cs:__imp_CloseThreadpoolTimer
0x1800137d2  mov     rcx, [rdi+10h]; lpMem
0x1800137d6  test    rcx, rcx
0x1800137d9  jz      short loc_1800137E0
0x1800137db  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800137e0  mov     rbx, [rsp+28h+arg_0]
0x1800137e5  mov     rsi, [rsp+28h+arg_8]
0x1800137ea  add     rsp, 20h
0x1800137ee  pop     rdi
0x1800137ef  retn
```
