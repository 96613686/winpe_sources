# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x18000368c`
- end: `0x180003878`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180021c30`

## callees

- `0x1800033fc`
- `0x18000368c`
- `0x180007044`
- `0x180007db0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037f2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800037f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000374a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000379a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000374a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000379a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800037da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003758`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003758`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003725`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003725`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000371d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003823`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003854`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800036d4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000371d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003823`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003854`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003706`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000380c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000383d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800036bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003706`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000380c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000383d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003714`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000381a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000384b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800036cb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003714`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000381a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000384b`

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
  if ( v8 && qword_18002D0F8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18002D0F8[25], qword_18002D0F8, v8);
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
0x18000368c  mov     [rsp+arg_0], rbx
0x180003691  mov     [rsp+arg_8], rsi
0x180003696  push    rdi
0x180003697  sub     rsp, 20h
0x18000369b  mov     byte ptr [rcx], 0
0x18000369e  mov     rdi, rcx
0x1800036a1  mov     rsi, [rcx+30h]
0x1800036a5  test    rsi, rsi
0x1800036a8  jz      short loc_1800036E2
0x1800036aa  call    cs:__imp_GetLastError
0x1800036b0  xor     r9d, r9d; msWindowLength
0x1800036b3  xor     r8d, r8d; msPeriod
0x1800036b6  xor     edx, edx; pftDueTime
0x1800036b8  mov     rcx, rsi; pti
0x1800036bb  mov     ebx, eax
0x1800036bd  call    cs:__imp_SetThreadpoolTimer
0x1800036c3  mov     edx, 1; fCancelPendingCallbacks
0x1800036c8  mov     rcx, rsi; pti
0x1800036cb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800036d1  mov     rcx, rsi; pti
0x1800036d4  call    cs:__imp_CloseThreadpoolTimer
0x1800036da  mov     ecx, ebx; dwErrCode
0x1800036dc  call    cs:__imp_SetLastError
0x1800036e2  mov     qword ptr [rdi+30h], 0
0x1800036ea  mov     rsi, [rdi+38h]
0x1800036ee  test    rsi, rsi
0x1800036f1  jz      short loc_18000372B
0x1800036f3  call    cs:__imp_GetLastError
0x1800036f9  xor     r9d, r9d; msWindowLength
0x1800036fc  xor     r8d, r8d; msPeriod
0x1800036ff  xor     edx, edx; pftDueTime
0x180003701  mov     rcx, rsi; pti
0x180003704  mov     ebx, eax
0x180003706  call    cs:__imp_SetThreadpoolTimer
0x18000370c  mov     edx, 1; fCancelPendingCallbacks
0x180003711  mov     rcx, rsi; pti
0x180003714  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000371a  mov     rcx, rsi; pti
0x18000371d  call    cs:__imp_CloseThreadpoolTimer
0x180003723  mov     ecx, ebx; dwErrCode
0x180003725  call    cs:__imp_SetLastError
0x18000372b  mov     qword ptr [rdi+38h], 0
0x180003733  mov     rbx, [rdi+100h]
0x18000373a  mov     qword ptr [rdi+100h], 0
0x180003745  test    rbx, rbx
0x180003748  jz      short loc_18000375E
0x18000374a  call    cs:__imp_GetProcessHeap
0x180003750  mov     r8, rbx; lpMem
0x180003753  xor     edx, edx; dwFlags
0x180003755  mov     rcx, rax; hHeap
0x180003758  call    cs:__imp_HeapFree
0x18000375e  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003765  test    r8, r8
0x180003768  jz      short loc_180003782
0x18000376a  mov     rdx, cs:qword_18002D0F8; SRWLock
0x180003771  test    rdx, rdx
0x180003774  jz      short loc_180003782
0x180003776  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x18000377d  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003782  lea     rbx, [rdi+98h]
0x180003789  mov     rsi, [rbx+40h]
0x18000378d  mov     qword ptr [rbx+40h], 0
0x180003795  test    rsi, rsi
0x180003798  jz      short loc_1800037AE
0x18000379a  call    cs:__imp_GetProcessHeap
0x1800037a0  mov     r8, rsi; lpMem
0x1800037a3  xor     edx, edx; dwFlags
0x1800037a5  mov     rcx, rax; hHeap
0x1800037a8  call    cs:__imp_HeapFree
0x1800037ae  mov     rcx, rbx; lpCriticalSection
0x1800037b1  call    cs:__imp_DeleteCriticalSection
0x1800037b7  lea     rcx, [rdi+90h]
0x1800037be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800037c3  mov     rsi, [rdi+88h]
0x1800037ca  mov     qword ptr [rdi+88h], 0
0x1800037d5  test    rsi, rsi
0x1800037d8  jz      short loc_1800037EE
0x1800037da  call    cs:__imp_GetProcessHeap
0x1800037e0  mov     r8, rsi; lpMem
0x1800037e3  xor     edx, edx; dwFlags
0x1800037e5  mov     rcx, rax; hHeap
0x1800037e8  call    cs:__imp_HeapFree
0x1800037ee  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800037f2  call    cs:__imp_DeleteCriticalSection
0x1800037f8  mov     rbx, [rdi+38h]
0x1800037fc  test    rbx, rbx
0x1800037ff  jz      short loc_180003829
0x180003801  xor     r9d, r9d; msWindowLength
0x180003804  xor     r8d, r8d; msPeriod
0x180003807  xor     edx, edx; pftDueTime
0x180003809  mov     rcx, rbx; pti
0x18000380c  call    cs:__imp_SetThreadpoolTimer
0x180003812  mov     edx, 1; fCancelPendingCallbacks
0x180003817  mov     rcx, rbx; pti
0x18000381a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003820  mov     rcx, rbx; pti
0x180003823  call    cs:__imp_CloseThreadpoolTimer
0x180003829  mov     rbx, [rdi+30h]
0x18000382d  test    rbx, rbx
0x180003830  jz      short loc_18000385A
0x180003832  xor     r9d, r9d; msWindowLength
0x180003835  xor     r8d, r8d; msPeriod
0x180003838  xor     edx, edx; pftDueTime
0x18000383a  mov     rcx, rbx; pti
0x18000383d  call    cs:__imp_SetThreadpoolTimer
0x180003843  mov     edx, 1; fCancelPendingCallbacks
0x180003848  mov     rcx, rbx; pti
0x18000384b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003851  mov     rcx, rbx; pti
0x180003854  call    cs:__imp_CloseThreadpoolTimer
0x18000385a  mov     rcx, [rdi+10h]; lpMem
0x18000385e  test    rcx, rcx
0x180003861  jz      short loc_180003868
0x180003863  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003868  mov     rbx, [rsp+28h+arg_0]
0x18000386d  mov     rsi, [rsp+28h+arg_8]
0x180003872  add     rsp, 20h
0x180003876  pop     rdi
0x180003877  retn
```
