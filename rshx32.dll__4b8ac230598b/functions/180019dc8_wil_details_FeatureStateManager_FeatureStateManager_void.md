# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180019dc8`
- end: `0x180019fb4`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d840`

## callees

- `0x180019ba8`
- `0x180019dc8`
- `0x18001c090`
- `0x18001c880`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019eed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f2e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019eed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ed6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019f16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019e86`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ed6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019f16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ee4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019f24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019e94`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019ee4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019f24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019e18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019e61`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019e18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e2f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019e10`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019e59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019f5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019f90`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019e10`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019e59`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019f5f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019f90`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019e07`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019e50`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019f56`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019f87`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019e07`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019e50`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019f56`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019f87`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019df9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019e42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019f48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019f79`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019df9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019e42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019f48`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019f79`

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
  if ( v8 && qword_180028820 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180028820[25], qword_180028820, v8);
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
0x180019dc8  mov     [rsp+arg_0], rbx
0x180019dcd  mov     [rsp+arg_8], rsi
0x180019dd2  push    rdi
0x180019dd3  sub     rsp, 20h
0x180019dd7  mov     byte ptr [rcx], 0
0x180019dda  mov     rdi, rcx
0x180019ddd  mov     rsi, [rcx+30h]
0x180019de1  test    rsi, rsi
0x180019de4  jz      short loc_180019E1E
0x180019de6  call    cs:__imp_GetLastError
0x180019dec  xor     r9d, r9d; msWindowLength
0x180019def  xor     r8d, r8d; msPeriod
0x180019df2  xor     edx, edx; pftDueTime
0x180019df4  mov     rcx, rsi; pti
0x180019df7  mov     ebx, eax
0x180019df9  call    cs:__imp_SetThreadpoolTimer
0x180019dff  mov     edx, 1; fCancelPendingCallbacks
0x180019e04  mov     rcx, rsi; pti
0x180019e07  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019e0d  mov     rcx, rsi; pti
0x180019e10  call    cs:__imp_CloseThreadpoolTimer
0x180019e16  mov     ecx, ebx; dwErrCode
0x180019e18  call    cs:__imp_SetLastError
0x180019e1e  mov     qword ptr [rdi+30h], 0
0x180019e26  mov     rsi, [rdi+38h]
0x180019e2a  test    rsi, rsi
0x180019e2d  jz      short loc_180019E67
0x180019e2f  call    cs:__imp_GetLastError
0x180019e35  xor     r9d, r9d; msWindowLength
0x180019e38  xor     r8d, r8d; msPeriod
0x180019e3b  xor     edx, edx; pftDueTime
0x180019e3d  mov     rcx, rsi; pti
0x180019e40  mov     ebx, eax
0x180019e42  call    cs:__imp_SetThreadpoolTimer
0x180019e48  mov     edx, 1; fCancelPendingCallbacks
0x180019e4d  mov     rcx, rsi; pti
0x180019e50  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019e56  mov     rcx, rsi; pti
0x180019e59  call    cs:__imp_CloseThreadpoolTimer
0x180019e5f  mov     ecx, ebx; dwErrCode
0x180019e61  call    cs:__imp_SetLastError
0x180019e67  mov     qword ptr [rdi+38h], 0
0x180019e6f  mov     rbx, [rdi+100h]
0x180019e76  mov     qword ptr [rdi+100h], 0
0x180019e81  test    rbx, rbx
0x180019e84  jz      short loc_180019E9A
0x180019e86  call    cs:__imp_GetProcessHeap
0x180019e8c  mov     r8, rbx; lpMem
0x180019e8f  xor     edx, edx; dwFlags
0x180019e91  mov     rcx, rax; hHeap
0x180019e94  call    cs:__imp_HeapFree
0x180019e9a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180019ea1  test    r8, r8
0x180019ea4  jz      short loc_180019EBE
0x180019ea6  mov     rdx, cs:qword_180028820; SRWLock
0x180019ead  test    rdx, rdx
0x180019eb0  jz      short loc_180019EBE
0x180019eb2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180019eb9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180019ebe  lea     rbx, [rdi+98h]
0x180019ec5  mov     rsi, [rbx+40h]
0x180019ec9  mov     qword ptr [rbx+40h], 0
0x180019ed1  test    rsi, rsi
0x180019ed4  jz      short loc_180019EEA
0x180019ed6  call    cs:__imp_GetProcessHeap
0x180019edc  mov     r8, rsi; lpMem
0x180019edf  xor     edx, edx; dwFlags
0x180019ee1  mov     rcx, rax; hHeap
0x180019ee4  call    cs:__imp_HeapFree
0x180019eea  mov     rcx, rbx; lpCriticalSection
0x180019eed  call    cs:__imp_DeleteCriticalSection
0x180019ef3  lea     rcx, [rdi+90h]
0x180019efa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180019eff  mov     rsi, [rdi+88h]
0x180019f06  mov     qword ptr [rdi+88h], 0
0x180019f11  test    rsi, rsi
0x180019f14  jz      short loc_180019F2A
0x180019f16  call    cs:__imp_GetProcessHeap
0x180019f1c  mov     r8, rsi; lpMem
0x180019f1f  xor     edx, edx; dwFlags
0x180019f21  mov     rcx, rax; hHeap
0x180019f24  call    cs:__imp_HeapFree
0x180019f2a  lea     rcx, [rdi+48h]; lpCriticalSection
0x180019f2e  call    cs:__imp_DeleteCriticalSection
0x180019f34  mov     rbx, [rdi+38h]
0x180019f38  test    rbx, rbx
0x180019f3b  jz      short loc_180019F65
0x180019f3d  xor     r9d, r9d; msWindowLength
0x180019f40  xor     r8d, r8d; msPeriod
0x180019f43  xor     edx, edx; pftDueTime
0x180019f45  mov     rcx, rbx; pti
0x180019f48  call    cs:__imp_SetThreadpoolTimer
0x180019f4e  mov     edx, 1; fCancelPendingCallbacks
0x180019f53  mov     rcx, rbx; pti
0x180019f56  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019f5c  mov     rcx, rbx; pti
0x180019f5f  call    cs:__imp_CloseThreadpoolTimer
0x180019f65  mov     rbx, [rdi+30h]
0x180019f69  test    rbx, rbx
0x180019f6c  jz      short loc_180019F96
0x180019f6e  xor     r9d, r9d; msWindowLength
0x180019f71  xor     r8d, r8d; msPeriod
0x180019f74  xor     edx, edx; pftDueTime
0x180019f76  mov     rcx, rbx; pti
0x180019f79  call    cs:__imp_SetThreadpoolTimer
0x180019f7f  mov     edx, 1; fCancelPendingCallbacks
0x180019f84  mov     rcx, rbx; pti
0x180019f87  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019f8d  mov     rcx, rbx; pti
0x180019f90  call    cs:__imp_CloseThreadpoolTimer
0x180019f96  mov     rcx, [rdi+10h]; lpMem
0x180019f9a  test    rcx, rcx
0x180019f9d  jz      short loc_180019FA4
0x180019f9f  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180019fa4  mov     rbx, [rsp+28h+arg_0]
0x180019fa9  mov     rsi, [rsp+28h+arg_8]
0x180019fae  add     rsp, 20h
0x180019fb2  pop     rdi
0x180019fb3  retn
```
