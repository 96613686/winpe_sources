# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180009354`
- end: `0x180009542`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180029f10`

## callees

- `0x1800091a0`
- `0x180009354`
- `0x18000fa28`
- `0x180011458`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180009479`
- `KERNEL32!DeleteCriticalSection` at `0x1800094ba`
- `KERNEL32!DeleteCriticalSection` at `0x180009479`
- `KERNEL32!DeleteCriticalSection` at `0x1800094ba`
- `KERNEL32!GetLastError` at `0x180009372`
- `KERNEL32!GetLastError` at `0x1800093bb`
- `KERNEL32!GetLastError` at `0x180009372`
- `KERNEL32!GetLastError` at `0x1800093bb`
- `KERNEL32!GetProcessHeap` at `0x180009412`
- `KERNEL32!GetProcessHeap` at `0x180009462`
- `KERNEL32!GetProcessHeap` at `0x1800094a2`
- `KERNEL32!GetProcessHeap` at `0x180009412`
- `KERNEL32!GetProcessHeap` at `0x180009462`
- `KERNEL32!GetProcessHeap` at `0x1800094a2`
- `KERNEL32!HeapFree` at `0x180009420`
- `KERNEL32!HeapFree` at `0x180009470`
- `KERNEL32!HeapFree` at `0x1800094b0`
- `KERNEL32!HeapFree` at `0x180009420`
- `KERNEL32!HeapFree` at `0x180009470`
- `KERNEL32!HeapFree` at `0x1800094b0`
- `KERNEL32!SetLastError` at `0x1800093a4`
- `KERNEL32!SetLastError` at `0x1800093ed`
- `KERNEL32!SetLastError` at `0x1800093a4`
- `KERNEL32!SetLastError` at `0x1800093ed`
- `KERNEL32!SetThreadpoolTimer` at `0x180009385`
- `KERNEL32!SetThreadpoolTimer` at `0x1800093ce`
- `KERNEL32!SetThreadpoolTimer` at `0x1800094d4`
- `KERNEL32!SetThreadpoolTimer` at `0x180009505`
- `KERNEL32!SetThreadpoolTimer` at `0x180009385`
- `KERNEL32!SetThreadpoolTimer` at `0x1800093ce`
- `KERNEL32!SetThreadpoolTimer` at `0x1800094d4`
- `KERNEL32!SetThreadpoolTimer` at `0x180009505`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009393`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800093dc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800094e2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009513`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009393`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800093dc`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800094e2`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180009513`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000939c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800093e5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800094eb`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000951c`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000939c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800093e5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800094eb`
- `KERNEL32!CloseThreadpoolTimer` at `0x18000951c`

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
  if ( v8 && qword_1800380C8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800380C8[25], qword_1800380C8, v8);
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
0x180009354  mov     [rsp+arg_0], rbx
0x180009359  mov     [rsp+arg_8], rsi
0x18000935e  push    rdi
0x18000935f  sub     rsp, 20h
0x180009363  mov     rdi, rcx
0x180009366  mov     byte ptr [rcx], 0
0x180009369  mov     rsi, [rcx+30h]
0x18000936d  test    rsi, rsi
0x180009370  jz      short loc_1800093AA
0x180009372  call    cs:__imp_GetLastError
0x180009378  mov     ebx, eax
0x18000937a  xor     r9d, r9d; msWindowLength
0x18000937d  xor     r8d, r8d; msPeriod
0x180009380  xor     edx, edx; pftDueTime
0x180009382  mov     rcx, rsi; pti
0x180009385  call    cs:__imp_SetThreadpoolTimer
0x18000938b  mov     edx, 1; fCancelPendingCallbacks
0x180009390  mov     rcx, rsi; pti
0x180009393  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009399  mov     rcx, rsi; pti
0x18000939c  call    cs:__imp_CloseThreadpoolTimer
0x1800093a2  mov     ecx, ebx; dwErrCode
0x1800093a4  call    cs:__imp_SetLastError
0x1800093aa  mov     qword ptr [rdi+30h], 0
0x1800093b2  mov     rsi, [rdi+38h]
0x1800093b6  test    rsi, rsi
0x1800093b9  jz      short loc_1800093F3
0x1800093bb  call    cs:__imp_GetLastError
0x1800093c1  mov     ebx, eax
0x1800093c3  xor     r9d, r9d; msWindowLength
0x1800093c6  xor     r8d, r8d; msPeriod
0x1800093c9  xor     edx, edx; pftDueTime
0x1800093cb  mov     rcx, rsi; pti
0x1800093ce  call    cs:__imp_SetThreadpoolTimer
0x1800093d4  mov     edx, 1; fCancelPendingCallbacks
0x1800093d9  mov     rcx, rsi; pti
0x1800093dc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800093e2  mov     rcx, rsi; pti
0x1800093e5  call    cs:__imp_CloseThreadpoolTimer
0x1800093eb  mov     ecx, ebx; dwErrCode
0x1800093ed  call    cs:__imp_SetLastError
0x1800093f3  mov     qword ptr [rdi+38h], 0
0x1800093fb  mov     rbx, [rdi+100h]
0x180009402  mov     qword ptr [rdi+100h], 0
0x18000940d  test    rbx, rbx
0x180009410  jz      short loc_180009426
0x180009412  call    cs:__imp_GetProcessHeap
0x180009418  mov     rcx, rax; hHeap
0x18000941b  mov     r8, rbx; lpMem
0x18000941e  xor     edx, edx; dwFlags
0x180009420  call    cs:__imp_HeapFree
0x180009426  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x18000942d  test    r8, r8
0x180009430  jz      short loc_18000944A
0x180009432  mov     rdx, cs:qword_1800380C8; SRWLock
0x180009439  test    rdx, rdx
0x18000943c  jz      short loc_18000944A
0x18000943e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180009445  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x18000944a  lea     rbx, [rdi+98h]
0x180009451  mov     rsi, [rbx+40h]
0x180009455  mov     qword ptr [rbx+40h], 0
0x18000945d  test    rsi, rsi
0x180009460  jz      short loc_180009476
0x180009462  call    cs:__imp_GetProcessHeap
0x180009468  mov     rcx, rax; hHeap
0x18000946b  mov     r8, rsi; lpMem
0x18000946e  xor     edx, edx; dwFlags
0x180009470  call    cs:__imp_HeapFree
0x180009476  mov     rcx, rbx; lpCriticalSection
0x180009479  call    cs:__imp_DeleteCriticalSection
0x18000947f  lea     rcx, [rdi+90h]
0x180009486  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000948b  mov     rsi, [rdi+88h]
0x180009492  mov     qword ptr [rdi+88h], 0
0x18000949d  test    rsi, rsi
0x1800094a0  jz      short loc_1800094B6
0x1800094a2  call    cs:__imp_GetProcessHeap
0x1800094a8  mov     rcx, rax; hHeap
0x1800094ab  mov     r8, rsi; lpMem
0x1800094ae  xor     edx, edx; dwFlags
0x1800094b0  call    cs:__imp_HeapFree
0x1800094b6  lea     rcx, [rdi+48h]; lpCriticalSection
0x1800094ba  call    cs:__imp_DeleteCriticalSection
0x1800094c0  mov     rbx, [rdi+38h]
0x1800094c4  test    rbx, rbx
0x1800094c7  jz      short loc_1800094F1
0x1800094c9  xor     r9d, r9d; msWindowLength
0x1800094cc  xor     r8d, r8d; msPeriod
0x1800094cf  xor     edx, edx; pftDueTime
0x1800094d1  mov     rcx, rbx; pti
0x1800094d4  call    cs:__imp_SetThreadpoolTimer
0x1800094da  mov     edx, 1; fCancelPendingCallbacks
0x1800094df  mov     rcx, rbx; pti
0x1800094e2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800094e8  mov     rcx, rbx; pti
0x1800094eb  call    cs:__imp_CloseThreadpoolTimer
0x1800094f1  mov     rbx, [rdi+30h]
0x1800094f5  test    rbx, rbx
0x1800094f8  jz      short loc_180009523
0x1800094fa  xor     r9d, r9d; msWindowLength
0x1800094fd  xor     r8d, r8d; msPeriod
0x180009500  xor     edx, edx; pftDueTime
0x180009502  mov     rcx, rbx; pti
0x180009505  call    cs:__imp_SetThreadpoolTimer
0x18000950b  mov     edx, 1; fCancelPendingCallbacks
0x180009510  mov     rcx, rbx; pti
0x180009513  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009519  mov     rcx, rbx; pti
0x18000951c  call    cs:__imp_CloseThreadpoolTimer
0x180009522  nop
0x180009523  mov     rcx, [rdi+10h]; lpMem
0x180009527  test    rcx, rcx
0x18000952a  jz      short loc_180009532
0x18000952c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180009531  nop
0x180009532  mov     rbx, [rsp+28h+arg_0]
0x180009537  mov     rsi, [rsp+28h+arg_8]
0x18000953c  add     rsp, 20h
0x180009540  pop     rdi
0x180009541  retn
```
