# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180008a0c`
- end: `0x180008bfa`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800351d0`

## callees

- `0x18000873c`
- `0x180008a0c`
- `0x18000c3a0`
- `0x18000d5bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008aca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008aca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ad8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a73`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008aa5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008a5c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008aa5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b31`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008b72`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008a4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008a94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008b9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008bcb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008a4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008a94`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008b9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008bcb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ba3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008bd4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008a9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ba3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008bd4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bbd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a3d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008a86`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008b8c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008bbd`

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
  if ( v8 && qword_180047178 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180047178[25], qword_180047178, v8);
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
0x180008a0c  mov     [rsp+arg_0], rbx
0x180008a11  mov     [rsp+arg_8], rsi
0x180008a16  push    rdi
0x180008a17  sub     rsp, 20h
0x180008a1b  mov     rdi, rcx
0x180008a1e  mov     byte ptr [rcx], 0
0x180008a21  mov     rsi, [rcx+30h]
0x180008a25  test    rsi, rsi
0x180008a28  jz      short loc_180008A62
0x180008a2a  call    cs:__imp_GetLastError
0x180008a30  mov     ebx, eax
0x180008a32  xor     r9d, r9d; msWindowLength
0x180008a35  xor     r8d, r8d; msPeriod
0x180008a38  xor     edx, edx; pftDueTime
0x180008a3a  mov     rcx, rsi; pti
0x180008a3d  call    cs:__imp_SetThreadpoolTimer
0x180008a43  mov     edx, 1; fCancelPendingCallbacks
0x180008a48  mov     rcx, rsi; pti
0x180008a4b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008a51  mov     rcx, rsi; pti
0x180008a54  call    cs:__imp_CloseThreadpoolTimer
0x180008a5a  mov     ecx, ebx; dwErrCode
0x180008a5c  call    cs:__imp_SetLastError
0x180008a62  mov     qword ptr [rdi+30h], 0
0x180008a6a  mov     rsi, [rdi+38h]
0x180008a6e  test    rsi, rsi
0x180008a71  jz      short loc_180008AAB
0x180008a73  call    cs:__imp_GetLastError
0x180008a79  mov     ebx, eax
0x180008a7b  xor     r9d, r9d; msWindowLength
0x180008a7e  xor     r8d, r8d; msPeriod
0x180008a81  xor     edx, edx; pftDueTime
0x180008a83  mov     rcx, rsi; pti
0x180008a86  call    cs:__imp_SetThreadpoolTimer
0x180008a8c  mov     edx, 1; fCancelPendingCallbacks
0x180008a91  mov     rcx, rsi; pti
0x180008a94  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008a9a  mov     rcx, rsi; pti
0x180008a9d  call    cs:__imp_CloseThreadpoolTimer
0x180008aa3  mov     ecx, ebx; dwErrCode
0x180008aa5  call    cs:__imp_SetLastError
0x180008aab  mov     qword ptr [rdi+38h], 0
0x180008ab3  mov     rbx, [rdi+100h]
0x180008aba  mov     qword ptr [rdi+100h], 0
0x180008ac5  test    rbx, rbx
0x180008ac8  jz      short loc_180008ADE
0x180008aca  call    cs:__imp_GetProcessHeap
0x180008ad0  mov     rcx, rax; hHeap
0x180008ad3  mov     r8, rbx; lpMem
0x180008ad6  xor     edx, edx; dwFlags
0x180008ad8  call    cs:__imp_HeapFree
0x180008ade  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180008ae5  test    r8, r8
0x180008ae8  jz      short loc_180008B02
0x180008aea  mov     rdx, cs:qword_180047178; SRWLock
0x180008af1  test    rdx, rdx
0x180008af4  jz      short loc_180008B02
0x180008af6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180008afd  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180008b02  lea     rbx, [rdi+98h]
0x180008b09  mov     rsi, [rbx+40h]
0x180008b0d  mov     qword ptr [rbx+40h], 0
0x180008b15  test    rsi, rsi
0x180008b18  jz      short loc_180008B2E
0x180008b1a  call    cs:__imp_GetProcessHeap
0x180008b20  mov     rcx, rax; hHeap
0x180008b23  mov     r8, rsi; lpMem
0x180008b26  xor     edx, edx; dwFlags
0x180008b28  call    cs:__imp_HeapFree
0x180008b2e  mov     rcx, rbx; lpCriticalSection
0x180008b31  call    cs:__imp_DeleteCriticalSection
0x180008b37  lea     rcx, [rdi+90h]
0x180008b3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180008b43  mov     rsi, [rdi+88h]
0x180008b4a  mov     qword ptr [rdi+88h], 0
0x180008b55  test    rsi, rsi
0x180008b58  jz      short loc_180008B6E
0x180008b5a  call    cs:__imp_GetProcessHeap
0x180008b60  mov     rcx, rax; hHeap
0x180008b63  mov     r8, rsi; lpMem
0x180008b66  xor     edx, edx; dwFlags
0x180008b68  call    cs:__imp_HeapFree
0x180008b6e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180008b72  call    cs:__imp_DeleteCriticalSection
0x180008b78  mov     rbx, [rdi+38h]
0x180008b7c  test    rbx, rbx
0x180008b7f  jz      short loc_180008BA9
0x180008b81  xor     r9d, r9d; msWindowLength
0x180008b84  xor     r8d, r8d; msPeriod
0x180008b87  xor     edx, edx; pftDueTime
0x180008b89  mov     rcx, rbx; pti
0x180008b8c  call    cs:__imp_SetThreadpoolTimer
0x180008b92  mov     edx, 1; fCancelPendingCallbacks
0x180008b97  mov     rcx, rbx; pti
0x180008b9a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008ba0  mov     rcx, rbx; pti
0x180008ba3  call    cs:__imp_CloseThreadpoolTimer
0x180008ba9  mov     rbx, [rdi+30h]
0x180008bad  test    rbx, rbx
0x180008bb0  jz      short loc_180008BDB
0x180008bb2  xor     r9d, r9d; msWindowLength
0x180008bb5  xor     r8d, r8d; msPeriod
0x180008bb8  xor     edx, edx; pftDueTime
0x180008bba  mov     rcx, rbx; pti
0x180008bbd  call    cs:__imp_SetThreadpoolTimer
0x180008bc3  mov     edx, 1; fCancelPendingCallbacks
0x180008bc8  mov     rcx, rbx; pti
0x180008bcb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008bd1  mov     rcx, rbx; pti
0x180008bd4  call    cs:__imp_CloseThreadpoolTimer
0x180008bda  nop
0x180008bdb  mov     rcx, [rdi+10h]; lpMem
0x180008bdf  test    rcx, rcx
0x180008be2  jz      short loc_180008BEA
0x180008be4  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180008be9  nop
0x180008bea  mov     rbx, [rsp+28h+arg_0]
0x180008bef  mov     rsi, [rsp+28h+arg_8]
0x180008bf4  add     rsp, 20h
0x180008bf8  pop     rdi
0x180008bf9  retn
```
