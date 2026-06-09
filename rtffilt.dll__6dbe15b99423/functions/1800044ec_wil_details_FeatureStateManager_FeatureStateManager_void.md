# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800044ec`
- end: `0x1800046da`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001a910`

## callees

- `0x180004248`
- `0x1800044ec`
- `0x180009c80`
- `0x18000bddc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004611`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004652`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004611`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004652`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000463a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800045fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000463a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800045b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004608`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004648`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800045b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004608`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004648`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000453c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004585`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000453c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004585`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000450a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004553`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000450a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004553`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004534`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000457d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004683`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800046b4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004534`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000457d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004683`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800046b4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000452b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004574`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000467a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800046ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000452b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004574`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000467a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800046ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000451d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004566`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000466c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000469d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000451d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004566`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000466c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000469d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( v8 && qword_180023088 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180023088[25], qword_180023088, v8);
  v9 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v9 )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
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
0x1800044ec  mov     [rsp+arg_0], rbx
0x1800044f1  mov     [rsp+arg_8], rsi
0x1800044f6  push    rdi
0x1800044f7  sub     rsp, 20h
0x1800044fb  mov     rdi, rcx
0x1800044fe  mov     byte ptr [rcx], 0
0x180004501  mov     rsi, [rcx+30h]
0x180004505  test    rsi, rsi
0x180004508  jz      short loc_180004542
0x18000450a  call    cs:__imp_GetLastError
0x180004510  mov     ebx, eax
0x180004512  xor     r9d, r9d; msWindowLength
0x180004515  xor     r8d, r8d; msPeriod
0x180004518  xor     edx, edx; pftDueTime
0x18000451a  mov     rcx, rsi; pti
0x18000451d  call    cs:__imp_SetThreadpoolTimer
0x180004523  mov     edx, 1; fCancelPendingCallbacks
0x180004528  mov     rcx, rsi; pti
0x18000452b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004531  mov     rcx, rsi; pti
0x180004534  call    cs:__imp_CloseThreadpoolTimer
0x18000453a  mov     ecx, ebx; dwErrCode
0x18000453c  call    cs:__imp_SetLastError
0x180004542  mov     qword ptr [rdi+30h], 0
0x18000454a  mov     rsi, [rdi+38h]
0x18000454e  test    rsi, rsi
0x180004551  jz      short loc_18000458B
0x180004553  call    cs:__imp_GetLastError
0x180004559  mov     ebx, eax
0x18000455b  xor     r9d, r9d; msWindowLength
0x18000455e  xor     r8d, r8d; msPeriod
0x180004561  xor     edx, edx; pftDueTime
0x180004563  mov     rcx, rsi; pti
0x180004566  call    cs:__imp_SetThreadpoolTimer
0x18000456c  mov     edx, 1; fCancelPendingCallbacks
0x180004571  mov     rcx, rsi; pti
0x180004574  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000457a  mov     rcx, rsi; pti
0x18000457d  call    cs:__imp_CloseThreadpoolTimer
0x180004583  mov     ecx, ebx; dwErrCode
0x180004585  call    cs:__imp_SetLastError
0x18000458b  mov     qword ptr [rdi+38h], 0
0x180004593  mov     rbx, [rdi+100h]
0x18000459a  mov     qword ptr [rdi+100h], 0
0x1800045a5  test    rbx, rbx
0x1800045a8  jz      short loc_1800045BE
0x1800045aa  call    cs:__imp_GetProcessHeap
0x1800045b0  mov     rcx, rax; hHeap
0x1800045b3  mov     r8, rbx; lpMem
0x1800045b6  xor     edx, edx; dwFlags
0x1800045b8  call    cs:__imp_HeapFree
0x1800045be  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800045c5  test    r8, r8
0x1800045c8  jz      short loc_1800045E2
0x1800045ca  mov     rdx, cs:qword_180023088; SRWLock
0x1800045d1  test    rdx, rdx
0x1800045d4  jz      short loc_1800045E2
0x1800045d6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800045dd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800045e2  lea     rbx, [rdi+98h]
0x1800045e9  mov     rsi, [rbx+40h]
0x1800045ed  mov     qword ptr [rbx+40h], 0
0x1800045f5  test    rsi, rsi
0x1800045f8  jz      short loc_18000460E
0x1800045fa  call    cs:__imp_GetProcessHeap
0x180004600  mov     rcx, rax; hHeap
0x180004603  mov     r8, rsi; lpMem
0x180004606  xor     edx, edx; dwFlags
0x180004608  call    cs:__imp_HeapFree
0x18000460e  mov     rcx, rbx; lpCriticalSection
0x180004611  call    cs:__imp_DeleteCriticalSection
0x180004617  lea     rcx, [rdi+90h]
0x18000461e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004623  mov     rsi, [rdi+88h]
0x18000462a  mov     qword ptr [rdi+88h], 0
0x180004635  test    rsi, rsi
0x180004638  jz      short loc_18000464E
0x18000463a  call    cs:__imp_GetProcessHeap
0x180004640  mov     rcx, rax; hHeap
0x180004643  mov     r8, rsi; lpMem
0x180004646  xor     edx, edx; dwFlags
0x180004648  call    cs:__imp_HeapFree
0x18000464e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180004652  call    cs:__imp_DeleteCriticalSection
0x180004658  mov     rbx, [rdi+38h]
0x18000465c  test    rbx, rbx
0x18000465f  jz      short loc_180004689
0x180004661  xor     r9d, r9d; msWindowLength
0x180004664  xor     r8d, r8d; msPeriod
0x180004667  xor     edx, edx; pftDueTime
0x180004669  mov     rcx, rbx; pti
0x18000466c  call    cs:__imp_SetThreadpoolTimer
0x180004672  mov     edx, 1; fCancelPendingCallbacks
0x180004677  mov     rcx, rbx; pti
0x18000467a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004680  mov     rcx, rbx; pti
0x180004683  call    cs:__imp_CloseThreadpoolTimer
0x180004689  mov     rbx, [rdi+30h]
0x18000468d  test    rbx, rbx
0x180004690  jz      short loc_1800046BB
0x180004692  xor     r9d, r9d; msWindowLength
0x180004695  xor     r8d, r8d; msPeriod
0x180004698  xor     edx, edx; pftDueTime
0x18000469a  mov     rcx, rbx; pti
0x18000469d  call    cs:__imp_SetThreadpoolTimer
0x1800046a3  mov     edx, 1; fCancelPendingCallbacks
0x1800046a8  mov     rcx, rbx; pti
0x1800046ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800046b1  mov     rcx, rbx; pti
0x1800046b4  call    cs:__imp_CloseThreadpoolTimer
0x1800046ba  nop
0x1800046bb  mov     rcx, [rdi+10h]; lpMem
0x1800046bf  test    rcx, rcx
0x1800046c2  jz      short loc_1800046CA
0x1800046c4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800046c9  nop
0x1800046ca  mov     rbx, [rsp+28h+arg_0]
0x1800046cf  mov     rsi, [rsp+28h+arg_8]
0x1800046d4  add     rsp, 20h
0x1800046d8  pop     rdi
0x1800046d9  retn
```
