# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x14000d720`
- end: `0x14000d90e`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400a6e50`

## callees

- `0x14000cfac`
- `0x14000d720`
- `0x140015c74`
- `0x140018db0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000d845`
- `KERNEL32!DeleteCriticalSection` at `0x14000d886`
- `KERNEL32!DeleteCriticalSection` at `0x14000d845`
- `KERNEL32!DeleteCriticalSection` at `0x14000d886`
- `KERNEL32!GetProcessHeap` at `0x14000d7de`
- `KERNEL32!GetProcessHeap` at `0x14000d82e`
- `KERNEL32!GetProcessHeap` at `0x14000d86e`
- `KERNEL32!GetProcessHeap` at `0x14000d7de`
- `KERNEL32!GetProcessHeap` at `0x14000d82e`
- `KERNEL32!GetProcessHeap` at `0x14000d86e`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d751`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d79a`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d8a0`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d8d1`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d751`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d79a`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d8a0`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d8d1`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d768`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d7b1`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d8b7`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d8e8`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d768`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d7b1`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d8b7`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d8e8`
- `KERNEL32!GetLastError` at `0x14000d73e`
- `KERNEL32!GetLastError` at `0x14000d787`
- `KERNEL32!GetLastError` at `0x14000d73e`
- `KERNEL32!GetLastError` at `0x14000d787`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d75f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d7a8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d8ae`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d8df`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d75f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d7a8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d8ae`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d8df`
- `KERNEL32!SetLastError` at `0x14000d770`
- `KERNEL32!SetLastError` at `0x14000d7b9`
- `KERNEL32!SetLastError` at `0x14000d770`
- `KERNEL32!SetLastError` at `0x14000d7b9`
- `KERNEL32!HeapFree` at `0x14000d7ec`
- `KERNEL32!HeapFree` at `0x14000d83c`
- `KERNEL32!HeapFree` at `0x14000d87c`
- `KERNEL32!HeapFree` at `0x14000d7ec`
- `KERNEL32!HeapFree` at `0x14000d83c`
- `KERNEL32!HeapFree` at `0x14000d87c`

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
  if ( v8 && qword_1400F1298 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400F1298[25], qword_1400F1298, v8);
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
0x14000d720  mov     [rsp+arg_0], rbx
0x14000d725  mov     [rsp+arg_8], rsi
0x14000d72a  push    rdi
0x14000d72b  sub     rsp, 20h
0x14000d72f  mov     rdi, rcx
0x14000d732  mov     byte ptr [rcx], 0
0x14000d735  mov     rsi, [rcx+30h]
0x14000d739  test    rsi, rsi
0x14000d73c  jz      short loc_14000D776
0x14000d73e  call    cs:__imp_GetLastError
0x14000d744  mov     ebx, eax
0x14000d746  xor     r9d, r9d; msWindowLength
0x14000d749  xor     r8d, r8d; msPeriod
0x14000d74c  xor     edx, edx; pftDueTime
0x14000d74e  mov     rcx, rsi; pti
0x14000d751  call    cs:__imp_SetThreadpoolTimer
0x14000d757  mov     edx, 1; fCancelPendingCallbacks
0x14000d75c  mov     rcx, rsi; pti
0x14000d75f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d765  mov     rcx, rsi; pti
0x14000d768  call    cs:__imp_CloseThreadpoolTimer
0x14000d76e  mov     ecx, ebx; dwErrCode
0x14000d770  call    cs:__imp_SetLastError
0x14000d776  mov     qword ptr [rdi+30h], 0
0x14000d77e  mov     rsi, [rdi+38h]
0x14000d782  test    rsi, rsi
0x14000d785  jz      short loc_14000D7BF
0x14000d787  call    cs:__imp_GetLastError
0x14000d78d  mov     ebx, eax
0x14000d78f  xor     r9d, r9d; msWindowLength
0x14000d792  xor     r8d, r8d; msPeriod
0x14000d795  xor     edx, edx; pftDueTime
0x14000d797  mov     rcx, rsi; pti
0x14000d79a  call    cs:__imp_SetThreadpoolTimer
0x14000d7a0  mov     edx, 1; fCancelPendingCallbacks
0x14000d7a5  mov     rcx, rsi; pti
0x14000d7a8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d7ae  mov     rcx, rsi; pti
0x14000d7b1  call    cs:__imp_CloseThreadpoolTimer
0x14000d7b7  mov     ecx, ebx; dwErrCode
0x14000d7b9  call    cs:__imp_SetLastError
0x14000d7bf  mov     qword ptr [rdi+38h], 0
0x14000d7c7  mov     rbx, [rdi+100h]
0x14000d7ce  mov     qword ptr [rdi+100h], 0
0x14000d7d9  test    rbx, rbx
0x14000d7dc  jz      short loc_14000D7F2
0x14000d7de  call    cs:__imp_GetProcessHeap
0x14000d7e4  mov     rcx, rax; hHeap
0x14000d7e7  mov     r8, rbx; lpMem
0x14000d7ea  xor     edx, edx; dwFlags
0x14000d7ec  call    cs:__imp_HeapFree
0x14000d7f2  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14000d7f9  test    r8, r8
0x14000d7fc  jz      short loc_14000D816
0x14000d7fe  mov     rdx, cs:qword_1400F1298; SRWLock
0x14000d805  test    rdx, rdx
0x14000d808  jz      short loc_14000D816
0x14000d80a  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x14000d811  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14000d816  lea     rbx, [rdi+98h]
0x14000d81d  mov     rsi, [rbx+40h]
0x14000d821  mov     qword ptr [rbx+40h], 0
0x14000d829  test    rsi, rsi
0x14000d82c  jz      short loc_14000D842
0x14000d82e  call    cs:__imp_GetProcessHeap
0x14000d834  mov     rcx, rax; hHeap
0x14000d837  mov     r8, rsi; lpMem
0x14000d83a  xor     edx, edx; dwFlags
0x14000d83c  call    cs:__imp_HeapFree
0x14000d842  mov     rcx, rbx; lpCriticalSection
0x14000d845  call    cs:__imp_DeleteCriticalSection
0x14000d84b  lea     rcx, [rdi+90h]
0x14000d852  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14000d857  mov     rsi, [rdi+88h]
0x14000d85e  mov     qword ptr [rdi+88h], 0
0x14000d869  test    rsi, rsi
0x14000d86c  jz      short loc_14000D882
0x14000d86e  call    cs:__imp_GetProcessHeap
0x14000d874  mov     rcx, rax; hHeap
0x14000d877  mov     r8, rsi; lpMem
0x14000d87a  xor     edx, edx; dwFlags
0x14000d87c  call    cs:__imp_HeapFree
0x14000d882  lea     rcx, [rdi+48h]; lpCriticalSection
0x14000d886  call    cs:__imp_DeleteCriticalSection
0x14000d88c  mov     rbx, [rdi+38h]
0x14000d890  test    rbx, rbx
0x14000d893  jz      short loc_14000D8BD
0x14000d895  xor     r9d, r9d; msWindowLength
0x14000d898  xor     r8d, r8d; msPeriod
0x14000d89b  xor     edx, edx; pftDueTime
0x14000d89d  mov     rcx, rbx; pti
0x14000d8a0  call    cs:__imp_SetThreadpoolTimer
0x14000d8a6  mov     edx, 1; fCancelPendingCallbacks
0x14000d8ab  mov     rcx, rbx; pti
0x14000d8ae  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d8b4  mov     rcx, rbx; pti
0x14000d8b7  call    cs:__imp_CloseThreadpoolTimer
0x14000d8bd  mov     rbx, [rdi+30h]
0x14000d8c1  test    rbx, rbx
0x14000d8c4  jz      short loc_14000D8EF
0x14000d8c6  xor     r9d, r9d; msWindowLength
0x14000d8c9  xor     r8d, r8d; msPeriod
0x14000d8cc  xor     edx, edx; pftDueTime
0x14000d8ce  mov     rcx, rbx; pti
0x14000d8d1  call    cs:__imp_SetThreadpoolTimer
0x14000d8d7  mov     edx, 1; fCancelPendingCallbacks
0x14000d8dc  mov     rcx, rbx; pti
0x14000d8df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d8e5  mov     rcx, rbx; pti
0x14000d8e8  call    cs:__imp_CloseThreadpoolTimer
0x14000d8ee  nop
0x14000d8ef  mov     rcx, [rdi+10h]; lpMem
0x14000d8f3  test    rcx, rcx
0x14000d8f6  jz      short loc_14000D8FE
0x14000d8f8  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000d8fd  nop
0x14000d8fe  mov     rbx, [rsp+28h+arg_0]
0x14000d903  mov     rsi, [rsp+28h+arg_8]
0x14000d908  add     rsp, 20h
0x14000d90c  pop     rdi
0x14000d90d  retn
```
