# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000af2c`
- end: `0x18000b11a`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e9e0`

## callees

- `0x18000ad0c`
- `0x18000af2c`
- `0x18000d35c`
- `0x18000db78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b051`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b092`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b051`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b092`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b03a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b07a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000afea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b03a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b07a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aff8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b088`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aff8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b048`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b088`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afc5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000af7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000afc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af93`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af74`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000afbd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b0c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b0f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000af74`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000afbd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b0c3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b0f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000afb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b0ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b0eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000af6b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000afb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b0ba`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b0eb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000afa6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000af5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000afa6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0ac`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b0dd`

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
  if ( v8 && qword_1800150A0 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800150A0[25], qword_1800150A0, v8);
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
0x18000af2c  mov     [rsp+arg_0], rbx
0x18000af31  mov     [rsp+arg_8], rsi
0x18000af36  push    rdi
0x18000af37  sub     rsp, 20h
0x18000af3b  mov     rdi, rcx
0x18000af3e  mov     byte ptr [rcx], 0
0x18000af41  mov     rsi, [rcx+30h]
0x18000af45  test    rsi, rsi
0x18000af48  jz      short loc_18000AF82
0x18000af4a  call    cs:__imp_GetLastError
0x18000af50  mov     ebx, eax
0x18000af52  xor     r9d, r9d; msWindowLength
0x18000af55  xor     r8d, r8d; msPeriod
0x18000af58  xor     edx, edx; pftDueTime
0x18000af5a  mov     rcx, rsi; pti
0x18000af5d  call    cs:__imp_SetThreadpoolTimer
0x18000af63  mov     edx, 1; fCancelPendingCallbacks
0x18000af68  mov     rcx, rsi; pti
0x18000af6b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000af71  mov     rcx, rsi; pti
0x18000af74  call    cs:__imp_CloseThreadpoolTimer
0x18000af7a  mov     ecx, ebx; dwErrCode
0x18000af7c  call    cs:__imp_SetLastError
0x18000af82  mov     qword ptr [rdi+30h], 0
0x18000af8a  mov     rsi, [rdi+38h]
0x18000af8e  test    rsi, rsi
0x18000af91  jz      short loc_18000AFCB
0x18000af93  call    cs:__imp_GetLastError
0x18000af99  mov     ebx, eax
0x18000af9b  xor     r9d, r9d; msWindowLength
0x18000af9e  xor     r8d, r8d; msPeriod
0x18000afa1  xor     edx, edx; pftDueTime
0x18000afa3  mov     rcx, rsi; pti
0x18000afa6  call    cs:__imp_SetThreadpoolTimer
0x18000afac  mov     edx, 1; fCancelPendingCallbacks
0x18000afb1  mov     rcx, rsi; pti
0x18000afb4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000afba  mov     rcx, rsi; pti
0x18000afbd  call    cs:__imp_CloseThreadpoolTimer
0x18000afc3  mov     ecx, ebx; dwErrCode
0x18000afc5  call    cs:__imp_SetLastError
0x18000afcb  mov     qword ptr [rdi+38h], 0
0x18000afd3  mov     rbx, [rdi+100h]
0x18000afda  mov     qword ptr [rdi+100h], 0
0x18000afe5  test    rbx, rbx
0x18000afe8  jz      short loc_18000AFFE
0x18000afea  call    cs:__imp_GetProcessHeap
0x18000aff0  mov     rcx, rax; hHeap
0x18000aff3  mov     r8, rbx; lpMem
0x18000aff6  xor     edx, edx; dwFlags
0x18000aff8  call    cs:__imp_HeapFree
0x18000affe  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000b005  test    r8, r8
0x18000b008  jz      short loc_18000B022
0x18000b00a  mov     rdx, cs:qword_1800150A0; SRWLock
0x18000b011  test    rdx, rdx
0x18000b014  jz      short loc_18000B022
0x18000b016  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000b01d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000b022  lea     rbx, [rdi+98h]
0x18000b029  mov     rsi, [rbx+40h]
0x18000b02d  mov     qword ptr [rbx+40h], 0
0x18000b035  test    rsi, rsi
0x18000b038  jz      short loc_18000B04E
0x18000b03a  call    cs:__imp_GetProcessHeap
0x18000b040  mov     rcx, rax; hHeap
0x18000b043  mov     r8, rsi; lpMem
0x18000b046  xor     edx, edx; dwFlags
0x18000b048  call    cs:__imp_HeapFree
0x18000b04e  mov     rcx, rbx; lpCriticalSection
0x18000b051  call    cs:__imp_DeleteCriticalSection
0x18000b057  lea     rcx, [rdi+90h]
0x18000b05e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000b063  mov     rsi, [rdi+88h]
0x18000b06a  mov     qword ptr [rdi+88h], 0
0x18000b075  test    rsi, rsi
0x18000b078  jz      short loc_18000B08E
0x18000b07a  call    cs:__imp_GetProcessHeap
0x18000b080  mov     rcx, rax; hHeap
0x18000b083  mov     r8, rsi; lpMem
0x18000b086  xor     edx, edx; dwFlags
0x18000b088  call    cs:__imp_HeapFree
0x18000b08e  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000b092  call    cs:__imp_DeleteCriticalSection
0x18000b098  mov     rbx, [rdi+38h]
0x18000b09c  test    rbx, rbx
0x18000b09f  jz      short loc_18000B0C9
0x18000b0a1  xor     r9d, r9d; msWindowLength
0x18000b0a4  xor     r8d, r8d; msPeriod
0x18000b0a7  xor     edx, edx; pftDueTime
0x18000b0a9  mov     rcx, rbx; pti
0x18000b0ac  call    cs:__imp_SetThreadpoolTimer
0x18000b0b2  mov     edx, 1; fCancelPendingCallbacks
0x18000b0b7  mov     rcx, rbx; pti
0x18000b0ba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b0c0  mov     rcx, rbx; pti
0x18000b0c3  call    cs:__imp_CloseThreadpoolTimer
0x18000b0c9  mov     rbx, [rdi+30h]
0x18000b0cd  test    rbx, rbx
0x18000b0d0  jz      short loc_18000B0FB
0x18000b0d2  xor     r9d, r9d; msWindowLength
0x18000b0d5  xor     r8d, r8d; msPeriod
0x18000b0d8  xor     edx, edx; pftDueTime
0x18000b0da  mov     rcx, rbx; pti
0x18000b0dd  call    cs:__imp_SetThreadpoolTimer
0x18000b0e3  mov     edx, 1; fCancelPendingCallbacks
0x18000b0e8  mov     rcx, rbx; pti
0x18000b0eb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b0f1  mov     rcx, rbx; pti
0x18000b0f4  call    cs:__imp_CloseThreadpoolTimer
0x18000b0fa  nop
0x18000b0fb  mov     rcx, [rdi+10h]; lpMem
0x18000b0ff  test    rcx, rcx
0x18000b102  jz      short loc_18000B10A
0x18000b104  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000b109  nop
0x18000b10a  mov     rbx, [rsp+28h+arg_0]
0x18000b10f  mov     rsi, [rsp+28h+arg_8]
0x18000b114  add     rsp, 20h
0x18000b118  pop     rdi
0x18000b119  retn
```
