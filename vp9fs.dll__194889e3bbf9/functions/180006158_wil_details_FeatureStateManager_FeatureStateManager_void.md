# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180006158`
- end: `0x180006333`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180033c00`

## callees

- `0x180006080`
- `0x180006158`
- `0x180009d34`
- `0x18000b12c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000626a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800062ab`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000626a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800062ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006261`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006224`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006261`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800062a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006216`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006253`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006293`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006216`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006253`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061f1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061a8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800061f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800061bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006189`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800061d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062f6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006189`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800061d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800062f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006197`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800061e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800062d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006304`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006197`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800061e0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800062d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006304`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800061a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800061e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800062dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000630d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800061a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800061e9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800062dc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000630d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((char *)this + 144);
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
0x180006158  mov     [rsp+arg_0], rbx
0x18000615d  mov     [rsp+arg_8], rsi
0x180006162  push    rdi
0x180006163  sub     rsp, 20h
0x180006167  mov     rdi, rcx
0x18000616a  mov     byte ptr [rcx], 0
0x18000616d  mov     rsi, [rcx+30h]
0x180006171  test    rsi, rsi
0x180006174  jz      short loc_1800061AE
0x180006176  call    cs:__imp_GetLastError
0x18000617c  mov     ebx, eax
0x18000617e  xor     r9d, r9d; msWindowLength
0x180006181  xor     r8d, r8d; msPeriod
0x180006184  xor     edx, edx; pftDueTime
0x180006186  mov     rcx, rsi; pti
0x180006189  call    cs:__imp_SetThreadpoolTimer
0x18000618f  mov     edx, 1; fCancelPendingCallbacks
0x180006194  mov     rcx, rsi; pti
0x180006197  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000619d  mov     rcx, rsi; pti
0x1800061a0  call    cs:__imp_CloseThreadpoolTimer
0x1800061a6  mov     ecx, ebx; dwErrCode
0x1800061a8  call    cs:__imp_SetLastError
0x1800061ae  mov     qword ptr [rdi+30h], 0
0x1800061b6  mov     rsi, [rdi+38h]
0x1800061ba  test    rsi, rsi
0x1800061bd  jz      short loc_1800061F7
0x1800061bf  call    cs:__imp_GetLastError
0x1800061c5  mov     ebx, eax
0x1800061c7  xor     r9d, r9d; msWindowLength
0x1800061ca  xor     r8d, r8d; msPeriod
0x1800061cd  xor     edx, edx; pftDueTime
0x1800061cf  mov     rcx, rsi; pti
0x1800061d2  call    cs:__imp_SetThreadpoolTimer
0x1800061d8  mov     edx, 1; fCancelPendingCallbacks
0x1800061dd  mov     rcx, rsi; pti
0x1800061e0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800061e6  mov     rcx, rsi; pti
0x1800061e9  call    cs:__imp_CloseThreadpoolTimer
0x1800061ef  mov     ecx, ebx; dwErrCode
0x1800061f1  call    cs:__imp_SetLastError
0x1800061f7  mov     qword ptr [rdi+38h], 0
0x1800061ff  mov     rbx, [rdi+100h]
0x180006206  mov     qword ptr [rdi+100h], 0
0x180006211  test    rbx, rbx
0x180006214  jz      short loc_18000622A
0x180006216  call    cs:__imp_GetProcessHeap
0x18000621c  mov     rcx, rax; hHeap
0x18000621f  mov     r8, rbx; lpMem
0x180006222  xor     edx, edx; dwFlags
0x180006224  call    cs:__imp_HeapFree
0x18000622a  mov     rcx, [rdi+0E0h]; this
0x180006231  test    rcx, rcx
0x180006234  jz      short loc_18000623B
0x180006236  call    ?UnsubscribeProcessWideUsageFlush@details@wil@@YAXPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details::UnsubscribeProcessWideUsageFlush(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000623b  lea     rbx, [rdi+98h]
0x180006242  mov     rsi, [rbx+40h]
0x180006246  mov     qword ptr [rbx+40h], 0
0x18000624e  test    rsi, rsi
0x180006251  jz      short loc_180006267
0x180006253  call    cs:__imp_GetProcessHeap
0x180006259  mov     rcx, rax; hHeap
0x18000625c  mov     r8, rsi; lpMem
0x18000625f  xor     edx, edx; dwFlags
0x180006261  call    cs:__imp_HeapFree
0x180006267  mov     rcx, rbx; lpCriticalSection
0x18000626a  call    cs:__imp_DeleteCriticalSection
0x180006270  lea     rcx, [rdi+90h]
0x180006277  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000627c  mov     rsi, [rdi+88h]
0x180006283  mov     qword ptr [rdi+88h], 0
0x18000628e  test    rsi, rsi
0x180006291  jz      short loc_1800062A7
0x180006293  call    cs:__imp_GetProcessHeap
0x180006299  mov     rcx, rax; hHeap
0x18000629c  mov     r8, rsi; lpMem
0x18000629f  xor     edx, edx; dwFlags
0x1800062a1  call    cs:__imp_HeapFree
0x1800062a7  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800062ab  call    cs:__imp_DeleteCriticalSection
0x1800062b1  mov     rbx, [rdi+38h]
0x1800062b5  test    rbx, rbx
0x1800062b8  jz      short loc_1800062E2
0x1800062ba  xor     r9d, r9d; msWindowLength
0x1800062bd  xor     r8d, r8d; msPeriod
0x1800062c0  xor     edx, edx; pftDueTime
0x1800062c2  mov     rcx, rbx; pti
0x1800062c5  call    cs:__imp_SetThreadpoolTimer
0x1800062cb  mov     edx, 1; fCancelPendingCallbacks
0x1800062d0  mov     rcx, rbx; pti
0x1800062d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800062d9  mov     rcx, rbx; pti
0x1800062dc  call    cs:__imp_CloseThreadpoolTimer
0x1800062e2  mov     rbx, [rdi+30h]
0x1800062e6  test    rbx, rbx
0x1800062e9  jz      short loc_180006314
0x1800062eb  xor     r9d, r9d; msWindowLength
0x1800062ee  xor     r8d, r8d; msPeriod
0x1800062f1  xor     edx, edx; pftDueTime
0x1800062f3  mov     rcx, rbx; pti
0x1800062f6  call    cs:__imp_SetThreadpoolTimer
0x1800062fc  mov     edx, 1; fCancelPendingCallbacks
0x180006301  mov     rcx, rbx; pti
0x180006304  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000630a  mov     rcx, rbx; pti
0x18000630d  call    cs:__imp_CloseThreadpoolTimer
0x180006313  nop
0x180006314  mov     rcx, [rdi+10h]; lpMem
0x180006318  test    rcx, rcx
0x18000631b  jz      short loc_180006323
0x18000631d  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180006322  nop
0x180006323  mov     rbx, [rsp+28h+arg_0]
0x180006328  mov     rsi, [rsp+28h+arg_8]
0x18000632d  add     rsp, 20h
0x180006331  pop     rdi
0x180006332  retn
```
