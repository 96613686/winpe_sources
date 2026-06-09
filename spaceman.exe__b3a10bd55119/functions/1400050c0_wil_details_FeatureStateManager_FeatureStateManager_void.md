# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x1400050c0`
- end: `0x1400052ac`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `492`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000d380`

## callees

- `0x140004f7c`
- `0x1400050c0`
- `0x140008820`
- `0x140009aac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400050f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000513a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005240`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005271`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400050f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000513a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005240`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005271`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400050ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005148`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000524e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000527f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400050ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140005148`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000524e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000527f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005108`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005151`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005257`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005288`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005108`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005151`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005257`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140005288`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005110`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005159`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005110`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005159`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400050de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005127`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400051e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005226`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400051e5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140005226`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000518c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400051dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000521c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000518c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400051dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000521c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000517e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000520e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000517e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400051ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000520e`

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
  if ( v8 && qword_1400140E8 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1400140E8[25], qword_1400140E8, v8);
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
0x1400050c0  mov     [rsp+arg_0], rbx
0x1400050c5  mov     [rsp+arg_8], rsi
0x1400050ca  push    rdi
0x1400050cb  sub     rsp, 20h
0x1400050cf  mov     byte ptr [rcx], 0
0x1400050d2  mov     rdi, rcx
0x1400050d5  mov     rsi, [rcx+30h]
0x1400050d9  test    rsi, rsi
0x1400050dc  jz      short loc_140005116
0x1400050de  call    cs:__imp_GetLastError
0x1400050e4  xor     r9d, r9d; msWindowLength
0x1400050e7  xor     r8d, r8d; msPeriod
0x1400050ea  xor     edx, edx; pftDueTime
0x1400050ec  mov     rcx, rsi; pti
0x1400050ef  mov     ebx, eax
0x1400050f1  call    cs:__imp_SetThreadpoolTimer
0x1400050f7  mov     edx, 1; fCancelPendingCallbacks
0x1400050fc  mov     rcx, rsi; pti
0x1400050ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005105  mov     rcx, rsi; pti
0x140005108  call    cs:__imp_CloseThreadpoolTimer
0x14000510e  mov     ecx, ebx; dwErrCode
0x140005110  call    cs:__imp_SetLastError
0x140005116  mov     qword ptr [rdi+30h], 0
0x14000511e  mov     rsi, [rdi+38h]
0x140005122  test    rsi, rsi
0x140005125  jz      short loc_14000515F
0x140005127  call    cs:__imp_GetLastError
0x14000512d  xor     r9d, r9d; msWindowLength
0x140005130  xor     r8d, r8d; msPeriod
0x140005133  xor     edx, edx; pftDueTime
0x140005135  mov     rcx, rsi; pti
0x140005138  mov     ebx, eax
0x14000513a  call    cs:__imp_SetThreadpoolTimer
0x140005140  mov     edx, 1; fCancelPendingCallbacks
0x140005145  mov     rcx, rsi; pti
0x140005148  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000514e  mov     rcx, rsi; pti
0x140005151  call    cs:__imp_CloseThreadpoolTimer
0x140005157  mov     ecx, ebx; dwErrCode
0x140005159  call    cs:__imp_SetLastError
0x14000515f  mov     qword ptr [rdi+38h], 0
0x140005167  mov     rbx, [rdi+100h]
0x14000516e  mov     qword ptr [rdi+100h], 0
0x140005179  test    rbx, rbx
0x14000517c  jz      short loc_140005192
0x14000517e  call    cs:__imp_GetProcessHeap
0x140005184  mov     r8, rbx; lpMem
0x140005187  xor     edx, edx; dwFlags
0x140005189  mov     rcx, rax; hHeap
0x14000518c  call    cs:__imp_HeapFree
0x140005192  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x140005199  test    r8, r8
0x14000519c  jz      short loc_1400051B6
0x14000519e  mov     rdx, cs:qword_1400140E8; SRWLock
0x1400051a5  test    rdx, rdx
0x1400051a8  jz      short loc_1400051B6
0x1400051aa  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1400051b1  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1400051b6  lea     rbx, [rdi+98h]
0x1400051bd  mov     rsi, [rbx+40h]
0x1400051c1  mov     qword ptr [rbx+40h], 0
0x1400051c9  test    rsi, rsi
0x1400051cc  jz      short loc_1400051E2
0x1400051ce  call    cs:__imp_GetProcessHeap
0x1400051d4  mov     r8, rsi; lpMem
0x1400051d7  xor     edx, edx; dwFlags
0x1400051d9  mov     rcx, rax; hHeap
0x1400051dc  call    cs:__imp_HeapFree
0x1400051e2  mov     rcx, rbx; lpCriticalSection
0x1400051e5  call    cs:__imp_DeleteCriticalSection
0x1400051eb  lea     rcx, [rdi+90h]
0x1400051f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400051f7  mov     rsi, [rdi+88h]
0x1400051fe  mov     qword ptr [rdi+88h], 0
0x140005209  test    rsi, rsi
0x14000520c  jz      short loc_140005222
0x14000520e  call    cs:__imp_GetProcessHeap
0x140005214  mov     r8, rsi; lpMem
0x140005217  xor     edx, edx; dwFlags
0x140005219  mov     rcx, rax; hHeap
0x14000521c  call    cs:__imp_HeapFree
0x140005222  lea     rcx, [rdi+48h]; lpCriticalSection
0x140005226  call    cs:__imp_DeleteCriticalSection
0x14000522c  mov     rbx, [rdi+38h]
0x140005230  test    rbx, rbx
0x140005233  jz      short loc_14000525D
0x140005235  xor     r9d, r9d; msWindowLength
0x140005238  xor     r8d, r8d; msPeriod
0x14000523b  xor     edx, edx; pftDueTime
0x14000523d  mov     rcx, rbx; pti
0x140005240  call    cs:__imp_SetThreadpoolTimer
0x140005246  mov     edx, 1; fCancelPendingCallbacks
0x14000524b  mov     rcx, rbx; pti
0x14000524e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005254  mov     rcx, rbx; pti
0x140005257  call    cs:__imp_CloseThreadpoolTimer
0x14000525d  mov     rbx, [rdi+30h]
0x140005261  test    rbx, rbx
0x140005264  jz      short loc_14000528E
0x140005266  xor     r9d, r9d; msWindowLength
0x140005269  xor     r8d, r8d; msPeriod
0x14000526c  xor     edx, edx; pftDueTime
0x14000526e  mov     rcx, rbx; pti
0x140005271  call    cs:__imp_SetThreadpoolTimer
0x140005277  mov     edx, 1; fCancelPendingCallbacks
0x14000527c  mov     rcx, rbx; pti
0x14000527f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005285  mov     rcx, rbx; pti
0x140005288  call    cs:__imp_CloseThreadpoolTimer
0x14000528e  mov     rcx, [rdi+10h]; lpMem
0x140005292  test    rcx, rcx
0x140005295  jz      short loc_14000529C
0x140005297  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x14000529c  mov     rbx, [rsp+28h+arg_0]
0x1400052a1  mov     rsi, [rsp+28h+arg_8]
0x1400052a6  add     rsp, 20h
0x1400052aa  pop     rdi
0x1400052ab  retn
```
