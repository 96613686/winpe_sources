# wil::details::FeatureStateManager::~FeatureStateManager(void)

- ea: `0x180033fc8`
- end: `0x1800341b6`
- name: `??1FeatureStateManager@details@wil@@QEAA@XZ`
- size: `494`
- prototype: `void __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18009bbd0`

## callees

- `0x180033d24`
- `0x180033fc8`
- `0x180037c90`
- `0x1800390b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800340ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003412e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800340ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003412e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800340e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034124`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034094`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800340e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034124`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034086`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800340d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034116`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034086`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800340d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034116`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034061`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034018`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180034061`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003402f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003402f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034007`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034050`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034156`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034187`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034007`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034050`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034156`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180034187`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034010`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034059`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003415f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034190`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034010`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034059`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003415f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180034190`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033ff9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034042`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034148`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034179`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033ff9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034042`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034148`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180034179`

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
  if ( v8 && qword_1800BD730 )
    wil::details_abi::SubscriptionList::Unsubscribe((LPCRITICAL_SECTION)&qword_1800BD730[25], qword_1800BD730, v8);
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
0x180033fc8  mov     [rsp+arg_0], rbx
0x180033fcd  mov     [rsp+arg_8], rsi
0x180033fd2  push    rdi
0x180033fd3  sub     rsp, 20h
0x180033fd7  mov     rdi, rcx
0x180033fda  mov     byte ptr [rcx], 0
0x180033fdd  mov     rsi, [rcx+30h]
0x180033fe1  test    rsi, rsi
0x180033fe4  jz      short loc_18003401E
0x180033fe6  call    cs:__imp_GetLastError
0x180033fec  mov     ebx, eax
0x180033fee  xor     r9d, r9d; msWindowLength
0x180033ff1  xor     r8d, r8d; msPeriod
0x180033ff4  xor     edx, edx; pftDueTime
0x180033ff6  mov     rcx, rsi; pti
0x180033ff9  call    cs:__imp_SetThreadpoolTimer
0x180033fff  mov     edx, 1; fCancelPendingCallbacks
0x180034004  mov     rcx, rsi; pti
0x180034007  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003400d  mov     rcx, rsi; pti
0x180034010  call    cs:__imp_CloseThreadpoolTimer
0x180034016  mov     ecx, ebx; dwErrCode
0x180034018  call    cs:__imp_SetLastError
0x18003401e  mov     qword ptr [rdi+30h], 0
0x180034026  mov     rsi, [rdi+38h]
0x18003402a  test    rsi, rsi
0x18003402d  jz      short loc_180034067
0x18003402f  call    cs:__imp_GetLastError
0x180034035  mov     ebx, eax
0x180034037  xor     r9d, r9d; msWindowLength
0x18003403a  xor     r8d, r8d; msPeriod
0x18003403d  xor     edx, edx; pftDueTime
0x18003403f  mov     rcx, rsi; pti
0x180034042  call    cs:__imp_SetThreadpoolTimer
0x180034048  mov     edx, 1; fCancelPendingCallbacks
0x18003404d  mov     rcx, rsi; pti
0x180034050  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180034056  mov     rcx, rsi; pti
0x180034059  call    cs:__imp_CloseThreadpoolTimer
0x18003405f  mov     ecx, ebx; dwErrCode
0x180034061  call    cs:__imp_SetLastError
0x180034067  mov     qword ptr [rdi+38h], 0
0x18003406f  mov     rbx, [rdi+100h]
0x180034076  mov     qword ptr [rdi+100h], 0
0x180034081  test    rbx, rbx
0x180034084  jz      short loc_18003409A
0x180034086  call    cs:__imp_GetProcessHeap
0x18003408c  mov     rcx, rax; hHeap
0x18003408f  mov     r8, rbx; lpMem
0x180034092  xor     edx, edx; dwFlags
0x180034094  call    cs:__imp_HeapFree
0x18003409a  mov     r8, [rdi+0E0h]; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ *
0x1800340a1  test    r8, r8
0x1800340a4  jz      short loc_1800340BE
0x1800340a6  mov     rdx, cs:qword_1800BD730; SRWLock
0x1800340ad  test    rdx, rdx
0x1800340b0  jz      short loc_1800340BE
0x1800340b2  lea     rcx, [rdx+0C8h]; lpCriticalSection
0x1800340b9  call    ?Unsubscribe@SubscriptionList@details_abi@wil@@QEAAXAEAVsrwlock@3@PEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@@Z; wil::details_abi::SubscriptionList::Unsubscribe(wil::srwlock &,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *)
0x1800340be  lea     rbx, [rdi+98h]
0x1800340c5  mov     rsi, [rbx+40h]
0x1800340c9  mov     qword ptr [rbx+40h], 0
0x1800340d1  test    rsi, rsi
0x1800340d4  jz      short loc_1800340EA
0x1800340d6  call    cs:__imp_GetProcessHeap
0x1800340dc  mov     rcx, rax; hHeap
0x1800340df  mov     r8, rsi; lpMem
0x1800340e2  xor     edx, edx; dwFlags
0x1800340e4  call    cs:__imp_HeapFree
0x1800340ea  mov     rcx, rbx; lpCriticalSection
0x1800340ed  call    cs:__imp_DeleteCriticalSection
0x1800340f3  lea     rcx, [rdi+90h]
0x1800340fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800340ff  mov     rsi, [rdi+88h]
0x180034106  mov     qword ptr [rdi+88h], 0
0x180034111  test    rsi, rsi
0x180034114  jz      short loc_18003412A
0x180034116  call    cs:__imp_GetProcessHeap
0x18003411c  mov     rcx, rax; hHeap
0x18003411f  mov     r8, rsi; lpMem
0x180034122  xor     edx, edx; dwFlags
0x180034124  call    cs:__imp_HeapFree
0x18003412a  lea     rcx, [rdi+48h]; lpCriticalSection
0x18003412e  call    cs:__imp_DeleteCriticalSection
0x180034134  mov     rbx, [rdi+38h]
0x180034138  test    rbx, rbx
0x18003413b  jz      short loc_180034165
0x18003413d  xor     r9d, r9d; msWindowLength
0x180034140  xor     r8d, r8d; msPeriod
0x180034143  xor     edx, edx; pftDueTime
0x180034145  mov     rcx, rbx; pti
0x180034148  call    cs:__imp_SetThreadpoolTimer
0x18003414e  mov     edx, 1; fCancelPendingCallbacks
0x180034153  mov     rcx, rbx; pti
0x180034156  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003415c  mov     rcx, rbx; pti
0x18003415f  call    cs:__imp_CloseThreadpoolTimer
0x180034165  mov     rbx, [rdi+30h]
0x180034169  test    rbx, rbx
0x18003416c  jz      short loc_180034197
0x18003416e  xor     r9d, r9d; msWindowLength
0x180034171  xor     r8d, r8d; msPeriod
0x180034174  xor     edx, edx; pftDueTime
0x180034176  mov     rcx, rbx; pti
0x180034179  call    cs:__imp_SetThreadpoolTimer
0x18003417f  mov     edx, 1; fCancelPendingCallbacks
0x180034184  mov     rcx, rbx; pti
0x180034187  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003418d  mov     rcx, rbx; pti
0x180034190  call    cs:__imp_CloseThreadpoolTimer
0x180034196  nop
0x180034197  mov     rcx, [rdi+10h]; lpMem
0x18003419b  test    rcx, rcx
0x18003419e  jz      short loc_1800341A6
0x1800341a0  call    ?Release@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAXXZ; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Release(void)
0x1800341a5  nop
0x1800341a6  mov     rbx, [rsp+28h+arg_0]
0x1800341ab  mov     rsi, [rsp+28h+arg_8]
0x1800341b0  add     rsp, 20h
0x1800341b4  pop     rdi
0x1800341b5  retn
```
