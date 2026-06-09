# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180009424`
- end: `0x180009610`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180012630`

## callees

- `0x180009110`
- `0x180009424`
- `0x18000d784`
- `0x18000e49c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009549`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000958a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009549`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000958a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000948b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009442`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000948b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009474`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800094bd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009540`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009580`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800094f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009540`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009580`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009532`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009572`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800094e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009532`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009572`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009463`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800094ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095e3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009463`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800094ac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095b2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800095e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000946c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800094b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095ec`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000946c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800094b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800095ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009455`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000949e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009455`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000949e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095a4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800095d5`

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
  if ( v8 && qword_18001C068 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_18001C068[25], qword_18001C068, v8);
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
0x180009424  mov     [rsp+arg_0], rbx
0x180009429  mov     [rsp+arg_8], rsi
0x18000942e  push    rdi
0x18000942f  sub     rsp, 20h
0x180009433  mov     byte ptr [rcx], 0
0x180009436  mov     rdi, rcx
0x180009439  mov     rsi, [rcx+30h]
0x18000943d  test    rsi, rsi
0x180009440  jz      short loc_18000947A
0x180009442  call    cs:__imp_GetLastError
0x180009448  xor     r9d, r9d; msWindowLength
0x18000944b  xor     r8d, r8d; msPeriod
0x18000944e  xor     edx, edx; pftDueTime
0x180009450  mov     rcx, rsi; pti
0x180009453  mov     ebx, eax
0x180009455  call    cs:__imp_SetThreadpoolTimer
0x18000945b  mov     edx, 1; fCancelPendingCallbacks
0x180009460  mov     rcx, rsi; pti
0x180009463  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009469  mov     rcx, rsi; pti
0x18000946c  call    cs:__imp_CloseThreadpoolTimer
0x180009472  mov     ecx, ebx; dwErrCode
0x180009474  call    cs:__imp_SetLastError
0x18000947a  mov     qword ptr [rdi+30h], 0
0x180009482  mov     rsi, [rdi+38h]
0x180009486  test    rsi, rsi
0x180009489  jz      short loc_1800094C3
0x18000948b  call    cs:__imp_GetLastError
0x180009491  xor     r9d, r9d; msWindowLength
0x180009494  xor     r8d, r8d; msPeriod
0x180009497  xor     edx, edx; pftDueTime
0x180009499  mov     rcx, rsi; pti
0x18000949c  mov     ebx, eax
0x18000949e  call    cs:__imp_SetThreadpoolTimer
0x1800094a4  mov     edx, 1; fCancelPendingCallbacks
0x1800094a9  mov     rcx, rsi; pti
0x1800094ac  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800094b2  mov     rcx, rsi; pti
0x1800094b5  call    cs:__imp_CloseThreadpoolTimer
0x1800094bb  mov     ecx, ebx; dwErrCode
0x1800094bd  call    cs:__imp_SetLastError
0x1800094c3  mov     qword ptr [rdi+38h], 0
0x1800094cb  mov     rbx, [rdi+100h]
0x1800094d2  mov     qword ptr [rdi+100h], 0
0x1800094dd  test    rbx, rbx
0x1800094e0  jz      short loc_1800094F6
0x1800094e2  call    cs:__imp_GetProcessHeap
0x1800094e8  mov     r8, rbx; lpMem
0x1800094eb  xor     edx, edx; dwFlags
0x1800094ed  mov     rcx, rax; hHeap
0x1800094f0  call    cs:__imp_HeapFree
0x1800094f6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800094fd  test    r8, r8
0x180009500  jz      short loc_18000951A
0x180009502  mov     rdx, cs:qword_18001C068; SRWLock
0x180009509  test    rdx, rdx
0x18000950c  jz      short loc_18000951A
0x18000950e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009515  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000951a  lea     rbx, [rdi+98h]
0x180009521  mov     rsi, [rbx+40h]
0x180009525  mov     qword ptr [rbx+40h], 0
0x18000952d  test    rsi, rsi
0x180009530  jz      short loc_180009546
0x180009532  call    cs:__imp_GetProcessHeap
0x180009538  mov     r8, rsi; lpMem
0x18000953b  xor     edx, edx; dwFlags
0x18000953d  mov     rcx, rax; hHeap
0x180009540  call    cs:__imp_HeapFree
0x180009546  mov     rcx, rbx; lpCriticalSection
0x180009549  call    cs:__imp_DeleteCriticalSection
0x18000954f  lea     rcx, [rdi+90h]
0x180009556  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000955b  mov     rsi, [rdi+88h]
0x180009562  mov     qword ptr [rdi+88h], 0
0x18000956d  test    rsi, rsi
0x180009570  jz      short loc_180009586
0x180009572  call    cs:__imp_GetProcessHeap
0x180009578  mov     r8, rsi; lpMem
0x18000957b  xor     edx, edx; dwFlags
0x18000957d  mov     rcx, rax; hHeap
0x180009580  call    cs:__imp_HeapFree
0x180009586  lea     rcx, [rdi+48h]; lpCriticalSection
0x18000958a  call    cs:__imp_DeleteCriticalSection
0x180009590  mov     rbx, [rdi+38h]
0x180009594  test    rbx, rbx
0x180009597  jz      short loc_1800095C1
0x180009599  xor     r9d, r9d; msWindowLength
0x18000959c  xor     r8d, r8d; msPeriod
0x18000959f  xor     edx, edx; pftDueTime
0x1800095a1  mov     rcx, rbx; pti
0x1800095a4  call    cs:__imp_SetThreadpoolTimer
0x1800095aa  mov     edx, 1; fCancelPendingCallbacks
0x1800095af  mov     rcx, rbx; pti
0x1800095b2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800095b8  mov     rcx, rbx; pti
0x1800095bb  call    cs:__imp_CloseThreadpoolTimer
0x1800095c1  mov     rbx, [rdi+30h]
0x1800095c5  test    rbx, rbx
0x1800095c8  jz      short loc_1800095F2
0x1800095ca  xor     r9d, r9d; msWindowLength
0x1800095cd  xor     r8d, r8d; msPeriod
0x1800095d0  xor     edx, edx; pftDueTime
0x1800095d2  mov     rcx, rbx; pti
0x1800095d5  call    cs:__imp_SetThreadpoolTimer
0x1800095db  mov     edx, 1; fCancelPendingCallbacks
0x1800095e0  mov     rcx, rbx; pti
0x1800095e3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800095e9  mov     rcx, rbx; pti
0x1800095ec  call    cs:__imp_CloseThreadpoolTimer
0x1800095f2  mov     rcx, [rdi+10h]; lpMem
0x1800095f6  test    rcx, rcx
0x1800095f9  jz      short loc_180009600
0x1800095fb  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009600  mov     rbx, [rsp+28h+arg_0]
0x180009605  mov     rsi, [rsp+28h+arg_8]
0x18000960a  add     rsp, 20h
0x18000960e  pop     rdi
0x18000960f  retn
```
