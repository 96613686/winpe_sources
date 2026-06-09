# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18002d9f8`
- end: `0x18002dbe6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800598d0`

## callees

- `0x18002d754`
- `0x18002d9f8`
- `0x1800323a4`
- `0x180033880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002db1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002db5e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002db1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002db5e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002da48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002da91`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002da48`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002da91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002da5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002da40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002da89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002db8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002dbc0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002da40`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002da89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002db8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002dbc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002da29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002da72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002db78`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002dba9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002da29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002da72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002db78`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002dba9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002da37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002da80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002db86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002dbb7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002da37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002da80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002db86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002dbb7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002db06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002db46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002dab6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002db06`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002db46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dac4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002db14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002db54`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002dac4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002db14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002db54`

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
  if ( v8 && qword_180074110 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180074110[25], qword_180074110, v8);
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
0x18002d9f8  mov     [rsp+arg_0], rbx
0x18002d9fd  mov     [rsp+arg_8], rsi
0x18002da02  push    rdi
0x18002da03  sub     rsp, 20h
0x18002da07  mov     rdi, rcx
0x18002da0a  mov     byte ptr [rcx], 0
0x18002da0d  mov     rsi, [rcx+30h]
0x18002da11  test    rsi, rsi
0x18002da14  jz      short loc_18002DA4E
0x18002da16  call    cs:__imp_GetLastError
0x18002da1c  mov     ebx, eax
0x18002da1e  xor     r9d, r9d; msWindowLength
0x18002da21  xor     r8d, r8d; msPeriod
0x18002da24  xor     edx, edx; pftDueTime
0x18002da26  mov     rcx, rsi; pti
0x18002da29  call    cs:__imp_SetThreadpoolTimer
0x18002da2f  mov     edx, 1; fCancelPendingCallbacks
0x18002da34  mov     rcx, rsi; pti
0x18002da37  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002da3d  mov     rcx, rsi; pti
0x18002da40  call    cs:__imp_CloseThreadpoolTimer
0x18002da46  mov     ecx, ebx; dwErrCode
0x18002da48  call    cs:__imp_SetLastError
0x18002da4e  mov     qword ptr [rdi+30h], 0
0x18002da56  mov     rsi, [rdi+38h]
0x18002da5a  test    rsi, rsi
0x18002da5d  jz      short loc_18002DA97
0x18002da5f  call    cs:__imp_GetLastError
0x18002da65  mov     ebx, eax
0x18002da67  xor     r9d, r9d; msWindowLength
0x18002da6a  xor     r8d, r8d; msPeriod
0x18002da6d  xor     edx, edx; pftDueTime
0x18002da6f  mov     rcx, rsi; pti
0x18002da72  call    cs:__imp_SetThreadpoolTimer
0x18002da78  mov     edx, 1; fCancelPendingCallbacks
0x18002da7d  mov     rcx, rsi; pti
0x18002da80  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002da86  mov     rcx, rsi; pti
0x18002da89  call    cs:__imp_CloseThreadpoolTimer
0x18002da8f  mov     ecx, ebx; dwErrCode
0x18002da91  call    cs:__imp_SetLastError
0x18002da97  mov     qword ptr [rdi+38h], 0
0x18002da9f  mov     rbx, [rdi+100h]
0x18002daa6  mov     qword ptr [rdi+100h], 0
0x18002dab1  test    rbx, rbx
0x18002dab4  jz      short loc_18002DACA
0x18002dab6  call    cs:__imp_GetProcessHeap
0x18002dabc  mov     rcx, rax; hHeap
0x18002dabf  mov     r8, rbx; lpMem
0x18002dac2  xor     edx, edx; dwFlags
0x18002dac4  call    cs:__imp_HeapFree
0x18002daca  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18002dad1  test    r8, r8
0x18002dad4  jz      short loc_18002DAEE
0x18002dad6  mov     rdx, cs:qword_180074110; SRWLock
0x18002dadd  test    rdx, rdx
0x18002dae0  jz      short loc_18002DAEE
0x18002dae2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18002dae9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18002daee  lea     rbx, [rdi+98h]
0x18002daf5  mov     rsi, [rbx+40h]
0x18002daf9  mov     qword ptr [rbx+40h], 0
0x18002db01  test    rsi, rsi
0x18002db04  jz      short loc_18002DB1A
0x18002db06  call    cs:__imp_GetProcessHeap
0x18002db0c  mov     rcx, rax; hHeap
0x18002db0f  mov     r8, rsi; lpMem
0x18002db12  xor     edx, edx; dwFlags
0x18002db14  call    cs:__imp_HeapFree
0x18002db1a  mov     rcx, rbx; lpCriticalSection
0x18002db1d  call    cs:__imp_DeleteCriticalSection
0x18002db23  lea     rcx, [rdi+90h]
0x18002db2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002db2f  mov     rsi, [rdi+88h]
0x18002db36  mov     qword ptr [rdi+88h], 0
0x18002db41  test    rsi, rsi
0x18002db44  jz      short loc_18002DB5A
0x18002db46  call    cs:__imp_GetProcessHeap
0x18002db4c  mov     rcx, rax; hHeap
0x18002db4f  mov     r8, rsi; lpMem
0x18002db52  xor     edx, edx; dwFlags
0x18002db54  call    cs:__imp_HeapFree
0x18002db5a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18002db5e  call    cs:__imp_DeleteCriticalSection
0x18002db64  mov     rbx, [rdi+38h]
0x18002db68  test    rbx, rbx
0x18002db6b  jz      short loc_18002DB95
0x18002db6d  xor     r9d, r9d; msWindowLength
0x18002db70  xor     r8d, r8d; msPeriod
0x18002db73  xor     edx, edx; pftDueTime
0x18002db75  mov     rcx, rbx; pti
0x18002db78  call    cs:__imp_SetThreadpoolTimer
0x18002db7e  mov     edx, 1; fCancelPendingCallbacks
0x18002db83  mov     rcx, rbx; pti
0x18002db86  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002db8c  mov     rcx, rbx; pti
0x18002db8f  call    cs:__imp_CloseThreadpoolTimer
0x18002db95  mov     rbx, [rdi+30h]
0x18002db99  test    rbx, rbx
0x18002db9c  jz      short loc_18002DBC7
0x18002db9e  xor     r9d, r9d; msWindowLength
0x18002dba1  xor     r8d, r8d; msPeriod
0x18002dba4  xor     edx, edx; pftDueTime
0x18002dba6  mov     rcx, rbx; pti
0x18002dba9  call    cs:__imp_SetThreadpoolTimer
0x18002dbaf  mov     edx, 1; fCancelPendingCallbacks
0x18002dbb4  mov     rcx, rbx; pti
0x18002dbb7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002dbbd  mov     rcx, rbx; pti
0x18002dbc0  call    cs:__imp_CloseThreadpoolTimer
0x18002dbc6  nop
0x18002dbc7  mov     rcx, [rdi+10h]; lpMem
0x18002dbcb  test    rcx, rcx
0x18002dbce  jz      short loc_18002DBD6
0x18002dbd0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x18002dbd5  nop
0x18002dbd6  mov     rbx, [rsp+28h+arg_0]
0x18002dbdb  mov     rsi, [rsp+28h+arg_8]
0x18002dbe0  add     rsp, 20h
0x18002dbe4  pop     rdi
0x18002dbe5  retn
```
