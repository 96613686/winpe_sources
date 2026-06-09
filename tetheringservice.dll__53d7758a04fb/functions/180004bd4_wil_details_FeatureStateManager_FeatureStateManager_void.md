# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180004bd4`
- end: `0x180004dc2`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180032780`

## callees

- `0x180004930`
- `0x180004bd4`
- `0x180008600`
- `0x180009bdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004cf9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d3a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004cf9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180004d3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ce2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004c92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ce2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ca0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ca0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004cf0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004bf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c24`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c6d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004d6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004d9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c1c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004c65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004d6b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004d9c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004c4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d54`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004d85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c5c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004d62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004d93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004c5c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004d62`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004d93`

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
  if ( v8 && qword_180041668 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_180041668[25], qword_180041668, v8);
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
0x180004bd4  mov     [rsp+arg_0], rbx
0x180004bd9  mov     [rsp+arg_8], rsi
0x180004bde  push    rdi
0x180004bdf  sub     rsp, 20h
0x180004be3  mov     rdi, rcx
0x180004be6  mov     byte ptr [rcx], 0
0x180004be9  mov     rsi, [rcx+30h]
0x180004bed  test    rsi, rsi
0x180004bf0  jz      short loc_180004C2A
0x180004bf2  call    cs:__imp_GetLastError
0x180004bf8  mov     ebx, eax
0x180004bfa  xor     r9d, r9d; msWindowLength
0x180004bfd  xor     r8d, r8d; msPeriod
0x180004c00  xor     edx, edx; pftDueTime
0x180004c02  mov     rcx, rsi; pti
0x180004c05  call    cs:__imp_SetThreadpoolTimer
0x180004c0b  mov     edx, 1; fCancelPendingCallbacks
0x180004c10  mov     rcx, rsi; pti
0x180004c13  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004c19  mov     rcx, rsi; pti
0x180004c1c  call    cs:__imp_CloseThreadpoolTimer
0x180004c22  mov     ecx, ebx; dwErrCode
0x180004c24  call    cs:__imp_SetLastError
0x180004c2a  mov     qword ptr [rdi+30h], 0
0x180004c32  mov     rsi, [rdi+38h]
0x180004c36  test    rsi, rsi
0x180004c39  jz      short loc_180004C73
0x180004c3b  call    cs:__imp_GetLastError
0x180004c41  mov     ebx, eax
0x180004c43  xor     r9d, r9d; msWindowLength
0x180004c46  xor     r8d, r8d; msPeriod
0x180004c49  xor     edx, edx; pftDueTime
0x180004c4b  mov     rcx, rsi; pti
0x180004c4e  call    cs:__imp_SetThreadpoolTimer
0x180004c54  mov     edx, 1; fCancelPendingCallbacks
0x180004c59  mov     rcx, rsi; pti
0x180004c5c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004c62  mov     rcx, rsi; pti
0x180004c65  call    cs:__imp_CloseThreadpoolTimer
0x180004c6b  mov     ecx, ebx; dwErrCode
0x180004c6d  call    cs:__imp_SetLastError
0x180004c73  mov     qword ptr [rdi+38h], 0
0x180004c7b  mov     rbx, [rdi+100h]
0x180004c82  mov     qword ptr [rdi+100h], 0
0x180004c8d  test    rbx, rbx
0x180004c90  jz      short loc_180004CA6
0x180004c92  call    cs:__imp_GetProcessHeap
0x180004c98  mov     rcx, rax; hHeap
0x180004c9b  mov     r8, rbx; lpMem
0x180004c9e  xor     edx, edx; dwFlags
0x180004ca0  call    cs:__imp_HeapFree
0x180004ca6  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x180004cad  test    r8, r8
0x180004cb0  jz      short loc_180004CCA
0x180004cb2  mov     rdx, cs:qword_180041668; SRWLock
0x180004cb9  test    rdx, rdx
0x180004cbc  jz      short loc_180004CCA
0x180004cbe  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x180004cc5  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x180004cca  lea     rbx, [rdi+98h]
0x180004cd1  mov     rsi, [rbx+40h]
0x180004cd5  mov     qword ptr [rbx+40h], 0
0x180004cdd  test    rsi, rsi
0x180004ce0  jz      short loc_180004CF6
0x180004ce2  call    cs:__imp_GetProcessHeap
0x180004ce8  mov     rcx, rax; hHeap
0x180004ceb  mov     r8, rsi; lpMem
0x180004cee  xor     edx, edx; dwFlags
0x180004cf0  call    cs:__imp_HeapFree
0x180004cf6  mov     rcx, rbx; lpCriticalSection
0x180004cf9  call    cs:__imp_DeleteCriticalSection
0x180004cff  lea     rcx, [rdi+90h]
0x180004d06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180004d0b  mov     rsi, [rdi+88h]
0x180004d12  mov     qword ptr [rdi+88h], 0
0x180004d1d  test    rsi, rsi
0x180004d20  jz      short loc_180004D36
0x180004d22  call    cs:__imp_GetProcessHeap
0x180004d28  mov     rcx, rax; hHeap
0x180004d2b  mov     r8, rsi; lpMem
0x180004d2e  xor     edx, edx; dwFlags
0x180004d30  call    cs:__imp_HeapFree
0x180004d36  lea     rcx, [rdi+48h]; lpCriticalSection
0x180004d3a  call    cs:__imp_DeleteCriticalSection
0x180004d40  mov     rbx, [rdi+38h]
0x180004d44  test    rbx, rbx
0x180004d47  jz      short loc_180004D71
0x180004d49  xor     r9d, r9d; msWindowLength
0x180004d4c  xor     r8d, r8d; msPeriod
0x180004d4f  xor     edx, edx; pftDueTime
0x180004d51  mov     rcx, rbx; pti
0x180004d54  call    cs:__imp_SetThreadpoolTimer
0x180004d5a  mov     edx, 1; fCancelPendingCallbacks
0x180004d5f  mov     rcx, rbx; pti
0x180004d62  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004d68  mov     rcx, rbx; pti
0x180004d6b  call    cs:__imp_CloseThreadpoolTimer
0x180004d71  mov     rbx, [rdi+30h]
0x180004d75  test    rbx, rbx
0x180004d78  jz      short loc_180004DA3
0x180004d7a  xor     r9d, r9d; msWindowLength
0x180004d7d  xor     r8d, r8d; msPeriod
0x180004d80  xor     edx, edx; pftDueTime
0x180004d82  mov     rcx, rbx; pti
0x180004d85  call    cs:__imp_SetThreadpoolTimer
0x180004d8b  mov     edx, 1; fCancelPendingCallbacks
0x180004d90  mov     rcx, rbx; pti
0x180004d93  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004d99  mov     rcx, rbx; pti
0x180004d9c  call    cs:__imp_CloseThreadpoolTimer
0x180004da2  nop
0x180004da3  mov     rcx, [rdi+10h]; lpMem
0x180004da7  test    rcx, rcx
0x180004daa  jz      short loc_180004DB2
0x180004dac  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x180004db1  nop
0x180004db2  mov     rbx, [rsp+28h+arg_0]
0x180004db7  mov     rsi, [rsp+28h+arg_8]
0x180004dbc  add     rsp, 20h
0x180004dc0  pop     rdi
0x180004dc1  retn
```
