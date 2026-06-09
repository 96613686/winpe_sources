# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1800039ec`
- end: `0x180003bd8`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000dde0`

## callees

- `0x18000375c`
- `0x1800039ec`
- `0x1800079d0`
- `0x1800086a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003a85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a53`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b52`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b11`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003b52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ab8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ab8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b08`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003b48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003aaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003afa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003aaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003afa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b3a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003b9d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003bb4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a7d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003b83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003bb4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003b7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a2b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003b7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003bab`

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
  if ( v8 && qword_180012088 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180012088[25], qword_180012088, v8);
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
0x1800039ec  mov     [rsp+arg_0], rbx
0x1800039f1  mov     [rsp+arg_8], rsi
0x1800039f6  push    rdi
0x1800039f7  sub     rsp, 20h
0x1800039fb  mov     byte ptr [rcx], 0
0x1800039fe  mov     rdi, rcx
0x180003a01  mov     rsi, [rcx+30h]
0x180003a05  test    rsi, rsi
0x180003a08  jz      short loc_180003A42
0x180003a0a  call    cs:__imp_GetLastError
0x180003a10  xor     r9d, r9d; msWindowLength
0x180003a13  xor     r8d, r8d; msPeriod
0x180003a16  xor     edx, edx; pftDueTime
0x180003a18  mov     rcx, rsi; pti
0x180003a1b  mov     ebx, eax
0x180003a1d  call    cs:__imp_SetThreadpoolTimer
0x180003a23  mov     edx, 1; fCancelPendingCallbacks
0x180003a28  mov     rcx, rsi; pti
0x180003a2b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003a31  mov     rcx, rsi; pti
0x180003a34  call    cs:__imp_CloseThreadpoolTimer
0x180003a3a  mov     ecx, ebx; dwErrCode
0x180003a3c  call    cs:__imp_SetLastError
0x180003a42  mov     qword ptr [rdi+30h], 0
0x180003a4a  mov     rsi, [rdi+38h]
0x180003a4e  test    rsi, rsi
0x180003a51  jz      short loc_180003A8B
0x180003a53  call    cs:__imp_GetLastError
0x180003a59  xor     r9d, r9d; msWindowLength
0x180003a5c  xor     r8d, r8d; msPeriod
0x180003a5f  xor     edx, edx; pftDueTime
0x180003a61  mov     rcx, rsi; pti
0x180003a64  mov     ebx, eax
0x180003a66  call    cs:__imp_SetThreadpoolTimer
0x180003a6c  mov     edx, 1; fCancelPendingCallbacks
0x180003a71  mov     rcx, rsi; pti
0x180003a74  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003a7a  mov     rcx, rsi; pti
0x180003a7d  call    cs:__imp_CloseThreadpoolTimer
0x180003a83  mov     ecx, ebx; dwErrCode
0x180003a85  call    cs:__imp_SetLastError
0x180003a8b  mov     qword ptr [rdi+38h], 0
0x180003a93  mov     rbx, [rdi+100h]
0x180003a9a  mov     qword ptr [rdi+100h], 0
0x180003aa5  test    rbx, rbx
0x180003aa8  jz      short loc_180003ABE
0x180003aaa  call    cs:__imp_GetProcessHeap
0x180003ab0  mov     r8, rbx; lpMem
0x180003ab3  xor     edx, edx; dwFlags
0x180003ab5  mov     rcx, rax; hHeap
0x180003ab8  call    cs:__imp_HeapFree
0x180003abe  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180003ac5  test    r8, r8
0x180003ac8  jz      short loc_180003AE2
0x180003aca  mov     rdx, cs:qword_180012088; SRWLock
0x180003ad1  test    rdx, rdx
0x180003ad4  jz      short loc_180003AE2
0x180003ad6  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180003add  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180003ae2  lea     rbx, [rdi+98h]
0x180003ae9  mov     rsi, [rbx+40h]
0x180003aed  mov     qword ptr [rbx+40h], 0
0x180003af5  test    rsi, rsi
0x180003af8  jz      short loc_180003B0E
0x180003afa  call    cs:__imp_GetProcessHeap
0x180003b00  mov     r8, rsi; lpMem
0x180003b03  xor     edx, edx; dwFlags
0x180003b05  mov     rcx, rax; hHeap
0x180003b08  call    cs:__imp_HeapFree
0x180003b0e  mov     rcx, rbx; lpCriticalSection
0x180003b11  call    cs:__imp_DeleteCriticalSection
0x180003b17  lea     rcx, [rdi+90h]
0x180003b1e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003b23  mov     rsi, [rdi+88h]
0x180003b2a  mov     qword ptr [rdi+88h], 0
0x180003b35  test    rsi, rsi
0x180003b38  jz      short loc_180003B4E
0x180003b3a  call    cs:__imp_GetProcessHeap
0x180003b40  mov     r8, rsi; lpMem
0x180003b43  xor     edx, edx; dwFlags
0x180003b45  mov     rcx, rax; hHeap
0x180003b48  call    cs:__imp_HeapFree
0x180003b4e  lea     rcx, [rdi+48h]; lpCriticalSection
0x180003b52  call    cs:__imp_DeleteCriticalSection
0x180003b58  mov     rbx, [rdi+38h]
0x180003b5c  test    rbx, rbx
0x180003b5f  jz      short loc_180003B89
0x180003b61  xor     r9d, r9d; msWindowLength
0x180003b64  xor     r8d, r8d; msPeriod
0x180003b67  xor     edx, edx; pftDueTime
0x180003b69  mov     rcx, rbx; pti
0x180003b6c  call    cs:__imp_SetThreadpoolTimer
0x180003b72  mov     edx, 1; fCancelPendingCallbacks
0x180003b77  mov     rcx, rbx; pti
0x180003b7a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003b80  mov     rcx, rbx; pti
0x180003b83  call    cs:__imp_CloseThreadpoolTimer
0x180003b89  mov     rbx, [rdi+30h]
0x180003b8d  test    rbx, rbx
0x180003b90  jz      short loc_180003BBA
0x180003b92  xor     r9d, r9d; msWindowLength
0x180003b95  xor     r8d, r8d; msPeriod
0x180003b98  xor     edx, edx; pftDueTime
0x180003b9a  mov     rcx, rbx; pti
0x180003b9d  call    cs:__imp_SetThreadpoolTimer
0x180003ba3  mov     edx, 1; fCancelPendingCallbacks
0x180003ba8  mov     rcx, rbx; pti
0x180003bab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003bb1  mov     rcx, rbx; pti
0x180003bb4  call    cs:__imp_CloseThreadpoolTimer
0x180003bba  mov     rcx, [rdi+10h]; lpMem
0x180003bbe  test    rcx, rcx
0x180003bc1  jz      short loc_180003BC8
0x180003bc3  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180003bc8  mov     rbx, [rsp+28h+arg_0]
0x180003bcd  mov     rsi, [rsp+28h+arg_8]
0x180003bd2  add     rsp, 20h
0x180003bd6  pop     rdi
0x180003bd7  retn
```
