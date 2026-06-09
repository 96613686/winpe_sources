# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x140010164`
- end: `0x140010352`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001cff0`

## callees

- `0x140010020`
- `0x140010164`
- `0x140013248`
- `0x1400143dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400101cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010182`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400101cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400101b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400101fd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400101b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400101fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010289`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400102ca`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140010289`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400102ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010272`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400102b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010222`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010272`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400102b2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010230`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010280`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400102c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010230`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010280`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400102c0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400101ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400101f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400102fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001032c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400101ac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400101f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400102fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001032c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400101a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400101ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400102f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010323`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400101a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400101ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400102f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140010323`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010195`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400101de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400102e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010315`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010195`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400101de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400102e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140010315`

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
  if ( v8 && qword_14002C090 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_14002C090[25], qword_14002C090, v8);
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
0x140010164  mov     [rsp+arg_0], rbx
0x140010169  mov     [rsp+arg_8], rsi
0x14001016e  push    rdi
0x14001016f  sub     rsp, 20h
0x140010173  mov     rdi, rcx
0x140010176  mov     byte ptr [rcx], 0
0x140010179  mov     rsi, [rcx+30h]
0x14001017d  test    rsi, rsi
0x140010180  jz      short loc_1400101BA
0x140010182  call    cs:__imp_GetLastError
0x140010188  mov     ebx, eax
0x14001018a  xor     r9d, r9d; msWindowLength
0x14001018d  xor     r8d, r8d; msPeriod
0x140010190  xor     edx, edx; pftDueTime
0x140010192  mov     rcx, rsi; pti
0x140010195  call    cs:__imp_SetThreadpoolTimer
0x14001019b  mov     edx, 1; fCancelPendingCallbacks
0x1400101a0  mov     rcx, rsi; pti
0x1400101a3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400101a9  mov     rcx, rsi; pti
0x1400101ac  call    cs:__imp_CloseThreadpoolTimer
0x1400101b2  mov     ecx, ebx; dwErrCode
0x1400101b4  call    cs:__imp_SetLastError
0x1400101ba  mov     qword ptr [rdi+30h], 0
0x1400101c2  mov     rsi, [rdi+38h]
0x1400101c6  test    rsi, rsi
0x1400101c9  jz      short loc_140010203
0x1400101cb  call    cs:__imp_GetLastError
0x1400101d1  mov     ebx, eax
0x1400101d3  xor     r9d, r9d; msWindowLength
0x1400101d6  xor     r8d, r8d; msPeriod
0x1400101d9  xor     edx, edx; pftDueTime
0x1400101db  mov     rcx, rsi; pti
0x1400101de  call    cs:__imp_SetThreadpoolTimer
0x1400101e4  mov     edx, 1; fCancelPendingCallbacks
0x1400101e9  mov     rcx, rsi; pti
0x1400101ec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400101f2  mov     rcx, rsi; pti
0x1400101f5  call    cs:__imp_CloseThreadpoolTimer
0x1400101fb  mov     ecx, ebx; dwErrCode
0x1400101fd  call    cs:__imp_SetLastError
0x140010203  mov     qword ptr [rdi+38h], 0
0x14001020b  mov     rbx, [rdi+100h]
0x140010212  mov     qword ptr [rdi+100h], 0
0x14001021d  test    rbx, rbx
0x140010220  jz      short loc_140010236
0x140010222  call    cs:__imp_GetProcessHeap
0x140010228  mov     rcx, rax; hHeap
0x14001022b  mov     r8, rbx; lpMem
0x14001022e  xor     edx, edx; dwFlags
0x140010230  call    cs:__imp_HeapFree
0x140010236  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x14001023d  test    r8, r8
0x140010240  jz      short loc_14001025A
0x140010242  mov     rdx, cs:qword_14002C090; SRWLock
0x140010249  test    rdx, rdx
0x14001024c  jz      short loc_14001025A
0x14001024e  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x140010255  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x14001025a  lea     rbx, [rdi+98h]
0x140010261  mov     rsi, [rbx+40h]
0x140010265  mov     qword ptr [rbx+40h], 0
0x14001026d  test    rsi, rsi
0x140010270  jz      short loc_140010286
0x140010272  call    cs:__imp_GetProcessHeap
0x140010278  mov     rcx, rax; hHeap
0x14001027b  mov     r8, rsi; lpMem
0x14001027e  xor     edx, edx; dwFlags
0x140010280  call    cs:__imp_HeapFree
0x140010286  mov     rcx, rbx; lpCriticalSection
0x140010289  call    cs:__imp_DeleteCriticalSection
0x14001028f  lea     rcx, [rdi+90h]
0x140010296  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14001029b  mov     rsi, [rdi+88h]
0x1400102a2  mov     qword ptr [rdi+88h], 0
0x1400102ad  test    rsi, rsi
0x1400102b0  jz      short loc_1400102C6
0x1400102b2  call    cs:__imp_GetProcessHeap
0x1400102b8  mov     rcx, rax; hHeap
0x1400102bb  mov     r8, rsi; lpMem
0x1400102be  xor     edx, edx; dwFlags
0x1400102c0  call    cs:__imp_HeapFree
0x1400102c6  lea     rcx, [rdi+48h]; lpCriticalSection
0x1400102ca  call    cs:__imp_DeleteCriticalSection
0x1400102d0  mov     rbx, [rdi+38h]
0x1400102d4  test    rbx, rbx
0x1400102d7  jz      short loc_140010301
0x1400102d9  xor     r9d, r9d; msWindowLength
0x1400102dc  xor     r8d, r8d; msPeriod
0x1400102df  xor     edx, edx; pftDueTime
0x1400102e1  mov     rcx, rbx; pti
0x1400102e4  call    cs:__imp_SetThreadpoolTimer
0x1400102ea  mov     edx, 1; fCancelPendingCallbacks
0x1400102ef  mov     rcx, rbx; pti
0x1400102f2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400102f8  mov     rcx, rbx; pti
0x1400102fb  call    cs:__imp_CloseThreadpoolTimer
0x140010301  mov     rbx, [rdi+30h]
0x140010305  test    rbx, rbx
0x140010308  jz      short loc_140010333
0x14001030a  xor     r9d, r9d; msWindowLength
0x14001030d  xor     r8d, r8d; msPeriod
0x140010310  xor     edx, edx; pftDueTime
0x140010312  mov     rcx, rbx; pti
0x140010315  call    cs:__imp_SetThreadpoolTimer
0x14001031b  mov     edx, 1; fCancelPendingCallbacks
0x140010320  mov     rcx, rbx; pti
0x140010323  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140010329  mov     rcx, rbx; pti
0x14001032c  call    cs:__imp_CloseThreadpoolTimer
0x140010332  nop
0x140010333  mov     rcx, [rdi+10h]; lpMem
0x140010337  test    rcx, rcx
0x14001033a  jz      short loc_140010342
0x14001033c  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x140010341  nop
0x140010342  mov     rbx, [rsp+28h+arg_0]
0x140010347  mov     rsi, [rsp+28h+arg_8]
0x14001034c  add     rsp, 20h
0x140010350  pop     rdi
0x140010351  retn
```
