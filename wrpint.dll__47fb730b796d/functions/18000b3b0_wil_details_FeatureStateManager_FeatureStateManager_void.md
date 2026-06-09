# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000b3b0`
- end: `0x18000b589`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `473`
- prototype: `void __fastcall(wil::details::FeatureStateManager *this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001bbc0`

## callees

- `0x18000b2d8`
- `0x18000b3b0`
- `0x18000ec34`
- `0x18000f8d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b400`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b449`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b400`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b449`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b417`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b4c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b503`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b4c2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000b503`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b46e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b46e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4ab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b4eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b47c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b47c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4b9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b4f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b3f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b441`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b534`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b565`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b3f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b441`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b534`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b565`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b3ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b438`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b52b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b55c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b3ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b438`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b52b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b55c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b3e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b42a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b51d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b54e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b3e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b42a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b51d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b54e`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::~FeatureStateManager(
        wil::details::FeatureStateManager *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *a2)
{
  struct _TP_TIMER *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v5; // rsi
  DWORD v6; // ebx
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  wil::details *v9; // rcx
  void *v10; // rsi
  HANDLE v11; // rax
  void *v12; // rsi
  HANDLE v13; // rax
  struct _TP_TIMER *v14; // rbx
  struct _TP_TIMER *v15; // rbx
  void *v16; // rcx

  *(_BYTE *)this = 0;
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v3 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v3, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v3, 1);
    CloseThreadpoolTimer(v3);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 6) = 0;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v5 )
  {
    v6 = GetLastError();
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
    SetLastError(v6);
  }
  *((_QWORD *)this + 7) = 0;
  v7 = (void *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
  }
  v9 = (wil::details *)*((_QWORD *)this + 28);
  if ( v9 )
    wil::details::UnsubscribeProcessWideUsageFlush(v9, a2);
  v10 = (void *)*((_QWORD *)this + 27);
  *((_QWORD *)this + 27) = 0;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((__int64 *)this + 18);
  v12 = (void *)*((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v12 )
  {
    v13 = GetProcessHeap();
    HeapFree(v13, 0, v12);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  v14 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v14 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 7), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v14, 1);
    CloseThreadpoolTimer(v14);
  }
  v15 = (struct _TP_TIMER *)*((_QWORD *)this + 6);
  if ( v15 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 6), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v15, 1);
    CloseThreadpoolTimer(v15);
  }
  v16 = (void *)*((_QWORD *)this + 2);
  if ( v16 )
    wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(v16);
}

```

## disassembly

```asm
0x18000b3b0  mov     [rsp+arg_0], rbx
0x18000b3b5  mov     [rsp+arg_8], rsi
0x18000b3ba  push    rdi
0x18000b3bb  sub     rsp, 20h
0x18000b3bf  mov     byte ptr [rcx], 0
0x18000b3c2  mov     rdi, rcx
0x18000b3c5  mov     rsi, [rcx+30h]
0x18000b3c9  test    rsi, rsi
0x18000b3cc  jz      short loc_18000B406
0x18000b3ce  call    cs:__imp_GetLastError
0x18000b3d4  xor     r9d, r9d; msWindowLength
0x18000b3d7  xor     r8d, r8d; msPeriod
0x18000b3da  xor     edx, edx; pftDueTime
0x18000b3dc  mov     rcx, rsi; pti
0x18000b3df  mov     ebx, eax
0x18000b3e1  call    cs:__imp_SetThreadpoolTimer
0x18000b3e7  mov     edx, 1; fCancelPendingCallbacks
0x18000b3ec  mov     rcx, rsi; pti
0x18000b3ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b3f5  mov     rcx, rsi; pti
0x18000b3f8  call    cs:__imp_CloseThreadpoolTimer
0x18000b3fe  mov     ecx, ebx; dwErrCode
0x18000b400  call    cs:__imp_SetLastError
0x18000b406  mov     qword ptr [rdi+30h], 0
0x18000b40e  mov     rsi, [rdi+38h]
0x18000b412  test    rsi, rsi
0x18000b415  jz      short loc_18000B44F
0x18000b417  call    cs:__imp_GetLastError
0x18000b41d  xor     r9d, r9d; msWindowLength
0x18000b420  xor     r8d, r8d; msPeriod
0x18000b423  xor     edx, edx; pftDueTime
0x18000b425  mov     rcx, rsi; pti
0x18000b428  mov     ebx, eax
0x18000b42a  call    cs:__imp_SetThreadpoolTimer
0x18000b430  mov     edx, 1; fCancelPendingCallbacks
0x18000b435  mov     rcx, rsi; pti
0x18000b438  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b43e  mov     rcx, rsi; pti
0x18000b441  call    cs:__imp_CloseThreadpoolTimer
0x18000b447  mov     ecx, ebx; dwErrCode
0x18000b449  call    cs:__imp_SetLastError
0x18000b44f  mov     qword ptr [rdi+38h], 0
0x18000b457  mov     rbx, [rdi+100h]
0x18000b45e  mov     qword ptr [rdi+100h], 0
0x18000b469  test    rbx, rbx
0x18000b46c  jz      short loc_18000B482
0x18000b46e  call    cs:__imp_GetProcessHeap
0x18000b474  mov     r8, rbx; lpMem
0x18000b477  xor     edx, edx; dwFlags
0x18000b479  mov     rcx, rax; hHeap
0x18000b47c  call    cs:__imp_HeapFree
0x18000b482  mov     rcx, [rdi+0E0h]; this
0x18000b489  test    rcx, rcx
0x18000b48c  jz      short loc_18000B493
0x18000b48e  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000b493  lea     rbx, [rdi+98h]
0x18000b49a  mov     rsi, [rbx+40h]
0x18000b49e  mov     qword ptr [rbx+40h], 0
0x18000b4a6  test    rsi, rsi
0x18000b4a9  jz      short loc_18000B4BF
0x18000b4ab  call    cs:__imp_GetProcessHeap
0x18000b4b1  mov     r8, rsi; lpMem
0x18000b4b4  xor     edx, edx; dwFlags
0x18000b4b6  mov     rcx, rax; hHeap
0x18000b4b9  call    cs:__imp_HeapFree
0x18000b4bf  mov     rcx, rbx; lpCriticalSection
0x18000b4c2  call    cs:__imp_DeleteCriticalSection
0x18000b4c8  lea     rcx, [rdi+90h]
0x18000b4cf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000b4d4  mov     rsi, [rdi+88h]
0x18000b4db  mov     qword ptr [rdi+88h], 0
0x18000b4e6  test    rsi, rsi
0x18000b4e9  jz      short loc_18000B4FF
0x18000b4eb  call    cs:__imp_GetProcessHeap
0x18000b4f1  mov     r8, rsi; lpMem
0x18000b4f4  xor     edx, edx; dwFlags
0x18000b4f6  mov     rcx, rax; hHeap
0x18000b4f9  call    cs:__imp_HeapFree
0x18000b4ff  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000b503  call    cs:__imp_DeleteCriticalSection
0x18000b509  mov     rbx, [rdi+38h]
0x18000b50d  test    rbx, rbx
0x18000b510  jz      short loc_18000B53A
0x18000b512  xor     r9d, r9d; msWindowLength
0x18000b515  xor     r8d, r8d; msPeriod
0x18000b518  xor     edx, edx; pftDueTime
0x18000b51a  mov     rcx, rbx; pti
0x18000b51d  call    cs:__imp_SetThreadpoolTimer
0x18000b523  mov     edx, 1; fCancelPendingCallbacks
0x18000b528  mov     rcx, rbx; pti
0x18000b52b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b531  mov     rcx, rbx; pti
0x18000b534  call    cs:__imp_CloseThreadpoolTimer
0x18000b53a  mov     rbx, [rdi+30h]
0x18000b53e  test    rbx, rbx
0x18000b541  jz      short loc_18000B56B
0x18000b543  xor     r9d, r9d; msWindowLength
0x18000b546  xor     r8d, r8d; msPeriod
0x18000b549  xor     edx, edx; pftDueTime
0x18000b54b  mov     rcx, rbx; pti
0x18000b54e  call    cs:__imp_SetThreadpoolTimer
0x18000b554  mov     edx, 1; fCancelPendingCallbacks
0x18000b559  mov     rcx, rbx; pti
0x18000b55c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b562  mov     rcx, rbx; pti
0x18000b565  call    cs:__imp_CloseThreadpoolTimer
0x18000b56b  mov     rcx, [rdi+10h]; lpMem
0x18000b56f  test    rcx, rcx
0x18000b572  jz      short loc_18000B579
0x18000b574  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18000b579  mov     rbx, [rsp+28h+arg_0]
0x18000b57e  mov     rsi, [rsp+28h+arg_8]
0x18000b583  add     rsp, 20h
0x18000b587  pop     rdi
0x18000b588  retn
```
