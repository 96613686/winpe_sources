# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800058d8`
- end: `0x180005ac6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18007c2f0`

## callees

- `0x1800055cc`
- `0x1800058d8`
- `0x18000bcac`
- `0x18000dc3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a3e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800059fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a34`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800059f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005a34`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005996`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800059e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000593f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000593f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005928`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005971`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005928`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005971`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005909`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005952`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a58`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a89`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005909`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005952`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a58`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005a89`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005917`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005960`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a66`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a97`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005917`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005960`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a66`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005a97`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005920`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005969`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005aa0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005920`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005969`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005a6f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005aa0`

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
  if ( v8 && qword_18009C0F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18009C0F8[25], qword_18009C0F8, v8);
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
0x1800058d8  mov     [rsp+arg_0], rbx
0x1800058dd  mov     [rsp+arg_8], rsi
0x1800058e2  push    rdi
0x1800058e3  sub     rsp, 20h
0x1800058e7  mov     rdi, rcx
0x1800058ea  mov     byte ptr [rcx], 0
0x1800058ed  mov     rsi, [rcx+30h]
0x1800058f1  test    rsi, rsi
0x1800058f4  jz      short loc_18000592E
0x1800058f6  call    cs:__imp_GetLastError
0x1800058fc  mov     ebx, eax
0x1800058fe  xor     r9d, r9d; msWindowLength
0x180005901  xor     r8d, r8d; msPeriod
0x180005904  xor     edx, edx; pftDueTime
0x180005906  mov     rcx, rsi; pti
0x180005909  call    cs:__imp_SetThreadpoolTimer
0x18000590f  mov     edx, 1; fCancelPendingCallbacks
0x180005914  mov     rcx, rsi; pti
0x180005917  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000591d  mov     rcx, rsi; pti
0x180005920  call    cs:__imp_CloseThreadpoolTimer
0x180005926  mov     ecx, ebx; dwErrCode
0x180005928  call    cs:__imp_SetLastError
0x18000592e  mov     qword ptr [rdi+30h], 0
0x180005936  mov     rsi, [rdi+38h]
0x18000593a  test    rsi, rsi
0x18000593d  jz      short loc_180005977
0x18000593f  call    cs:__imp_GetLastError
0x180005945  mov     ebx, eax
0x180005947  xor     r9d, r9d; msWindowLength
0x18000594a  xor     r8d, r8d; msPeriod
0x18000594d  xor     edx, edx; pftDueTime
0x18000594f  mov     rcx, rsi; pti
0x180005952  call    cs:__imp_SetThreadpoolTimer
0x180005958  mov     edx, 1; fCancelPendingCallbacks
0x18000595d  mov     rcx, rsi; pti
0x180005960  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005966  mov     rcx, rsi; pti
0x180005969  call    cs:__imp_CloseThreadpoolTimer
0x18000596f  mov     ecx, ebx; dwErrCode
0x180005971  call    cs:__imp_SetLastError
0x180005977  mov     qword ptr [rdi+38h], 0
0x18000597f  mov     rbx, [rdi+100h]
0x180005986  mov     qword ptr [rdi+100h], 0
0x180005991  test    rbx, rbx
0x180005994  jz      short loc_1800059AA
0x180005996  call    cs:__imp_GetProcessHeap
0x18000599c  mov     rcx, rax; hHeap
0x18000599f  mov     r8, rbx; lpMem
0x1800059a2  xor     edx, edx; dwFlags
0x1800059a4  call    cs:__imp_HeapFree
0x1800059aa  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800059b1  test    r8, r8
0x1800059b4  jz      short loc_1800059CE
0x1800059b6  mov     rdx, cs:qword_18009C0F8; SRWLock
0x1800059bd  test    rdx, rdx
0x1800059c0  jz      short loc_1800059CE
0x1800059c2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800059c9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800059ce  lea     rbx, [rdi+98h]
0x1800059d5  mov     rsi, [rbx+40h]
0x1800059d9  mov     qword ptr [rbx+40h], 0
0x1800059e1  test    rsi, rsi
0x1800059e4  jz      short loc_1800059FA
0x1800059e6  call    cs:__imp_GetProcessHeap
0x1800059ec  mov     rcx, rax; hHeap
0x1800059ef  mov     r8, rsi; lpMem
0x1800059f2  xor     edx, edx; dwFlags
0x1800059f4  call    cs:__imp_HeapFree
0x1800059fa  mov     rcx, rbx; lpCriticalSection
0x1800059fd  call    cs:__imp_DeleteCriticalSection
0x180005a03  lea     rcx, [rdi+90h]
0x180005a0a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180005a0f  mov     rsi, [rdi+88h]
0x180005a16  mov     qword ptr [rdi+88h], 0
0x180005a21  test    rsi, rsi
0x180005a24  jz      short loc_180005A3A
0x180005a26  call    cs:__imp_GetProcessHeap
0x180005a2c  mov     rcx, rax; hHeap
0x180005a2f  mov     r8, rsi; lpMem
0x180005a32  xor     edx, edx; dwFlags
0x180005a34  call    cs:__imp_HeapFree
0x180005a3a  lea     rcx, [rdi+48h]; lpCriticalSection
0x180005a3e  call    cs:__imp_DeleteCriticalSection
0x180005a44  mov     rbx, [rdi+38h]
0x180005a48  test    rbx, rbx
0x180005a4b  jz      short loc_180005A75
0x180005a4d  xor     r9d, r9d; msWindowLength
0x180005a50  xor     r8d, r8d; msPeriod
0x180005a53  xor     edx, edx; pftDueTime
0x180005a55  mov     rcx, rbx; pti
0x180005a58  call    cs:__imp_SetThreadpoolTimer
0x180005a5e  mov     edx, 1; fCancelPendingCallbacks
0x180005a63  mov     rcx, rbx; pti
0x180005a66  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005a6c  mov     rcx, rbx; pti
0x180005a6f  call    cs:__imp_CloseThreadpoolTimer
0x180005a75  mov     rbx, [rdi+30h]
0x180005a79  test    rbx, rbx
0x180005a7c  jz      short loc_180005AA7
0x180005a7e  xor     r9d, r9d; msWindowLength
0x180005a81  xor     r8d, r8d; msPeriod
0x180005a84  xor     edx, edx; pftDueTime
0x180005a86  mov     rcx, rbx; pti
0x180005a89  call    cs:__imp_SetThreadpoolTimer
0x180005a8f  mov     edx, 1; fCancelPendingCallbacks
0x180005a94  mov     rcx, rbx; pti
0x180005a97  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005a9d  mov     rcx, rbx; pti
0x180005aa0  call    cs:__imp_CloseThreadpoolTimer
0x180005aa6  nop
0x180005aa7  mov     rcx, [rdi+10h]; lpMem
0x180005aab  test    rcx, rcx
0x180005aae  jz      short loc_180005AB6
0x180005ab0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180005ab5  nop
0x180005ab6  mov     rbx, [rsp+28h+arg_0]
0x180005abb  mov     rsi, [rsp+28h+arg_8]
0x180005ac0  add     rsp, 20h
0x180005ac4  pop     rdi
0x180005ac5  retn
```
