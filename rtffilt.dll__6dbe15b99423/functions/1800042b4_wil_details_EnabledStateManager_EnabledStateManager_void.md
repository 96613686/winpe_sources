# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800042b4`
- end: `0x18000440c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a8c0`

## callees

- `0x1800042b4`
- `0x180007dcc`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004391`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004391`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800043b6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000439f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000439f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800043c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004307`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004307`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800042ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800043f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800042ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800043f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800042f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800043ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800042f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800043ec`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800042e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800043de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800042e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800043de`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void (*v4)(void); // rax
  __int64 v5; // rdx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_15;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_15;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_15:
  v6 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x1800042b4  mov     [rsp+arg_0], rbx
0x1800042b9  mov     [rsp+arg_8], rsi
0x1800042be  push    rdi
0x1800042bf  sub     rsp, 20h
0x1800042c3  mov     rdi, rcx
0x1800042c6  mov     dword ptr [rcx], 0
0x1800042cc  mov     rsi, [rcx+10h]
0x1800042d0  test    rsi, rsi
0x1800042d3  jz      short loc_18000430D
0x1800042d5  call    cs:__imp_GetLastError
0x1800042db  mov     ebx, eax
0x1800042dd  xor     r9d, r9d; msWindowLength
0x1800042e0  xor     r8d, r8d; msPeriod
0x1800042e3  xor     edx, edx; pftDueTime
0x1800042e5  mov     rcx, rsi; pti
0x1800042e8  call    cs:__imp_SetThreadpoolTimer
0x1800042ee  mov     edx, 1; fCancelPendingCallbacks
0x1800042f3  mov     rcx, rsi; pti
0x1800042f6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800042fc  mov     rcx, rsi; pti
0x1800042ff  call    cs:__imp_CloseThreadpoolTimer
0x180004305  mov     ecx, ebx; dwErrCode
0x180004307  call    cs:__imp_SetLastError
0x18000430d  mov     qword ptr [rdi+10h], 0
0x180004315  mov     rcx, rdi; this
0x180004318  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000431d  mov     rcx, [rdi+68h]
0x180004321  test    rcx, rcx
0x180004324  jz      short loc_180004356
0x180004326  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000432d  test    rax, rax
0x180004330  jnz     short loc_180004341
0x180004332  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004339  test    rdx, rdx
0x18000433c  jz      short loc_180004354
0x18000433e  mov     rax, rdx
0x180004341  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004346  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000434d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004354  jmp     short loc_180004364
0x180004356  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000435d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004364  mov     rcx, [rdi+60h]
0x180004368  test    rcx, rcx
0x18000436b  jz      short loc_180004380
0x18000436d  test    rax, rax
0x180004370  jnz     short loc_18000437A
0x180004372  test    rdx, rdx
0x180004375  jz      short loc_180004380
0x180004377  mov     rax, rdx
0x18000437a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000437f  nop
0x180004380  mov     rbx, [rdi+58h]
0x180004384  mov     qword ptr [rdi+58h], 0
0x18000438c  test    rbx, rbx
0x18000438f  jz      short loc_1800043A5
0x180004391  call    cs:__imp_GetProcessHeap
0x180004397  mov     rcx, rax; hHeap
0x18000439a  mov     r8, rbx; lpMem
0x18000439d  xor     edx, edx; dwFlags
0x18000439f  call    cs:__imp_HeapFree
0x1800043a5  mov     rbx, [rdi+38h]
0x1800043a9  mov     qword ptr [rdi+38h], 0
0x1800043b1  test    rbx, rbx
0x1800043b4  jz      short loc_1800043CA
0x1800043b6  call    cs:__imp_GetProcessHeap
0x1800043bc  mov     rcx, rax; hHeap
0x1800043bf  mov     r8, rbx; lpMem
0x1800043c2  xor     edx, edx; dwFlags
0x1800043c4  call    cs:__imp_HeapFree
0x1800043ca  mov     rbx, [rdi+10h]
0x1800043ce  test    rbx, rbx
0x1800043d1  jz      short loc_1800043FC
0x1800043d3  xor     r9d, r9d; msWindowLength
0x1800043d6  xor     r8d, r8d; msPeriod
0x1800043d9  xor     edx, edx; pftDueTime
0x1800043db  mov     rcx, rbx; pti
0x1800043de  call    cs:__imp_SetThreadpoolTimer
0x1800043e4  mov     edx, 1; fCancelPendingCallbacks
0x1800043e9  mov     rcx, rbx; pti
0x1800043ec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800043f2  mov     rcx, rbx; pti
0x1800043f5  call    cs:__imp_CloseThreadpoolTimer
0x1800043fb  nop
0x1800043fc  mov     rbx, [rsp+28h+arg_0]
0x180004401  mov     rsi, [rsp+28h+arg_8]
0x180004406  add     rsp, 20h
0x18000440a  pop     rdi
0x18000440b  retn
```
