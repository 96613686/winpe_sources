# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800056a0`
- end: `0x1800057f8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18007c2a0`

## callees

- `0x1800056a0`
- `0x18000a390`
- `0x18007d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000578b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000578b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000577d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000577d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800056d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800057ca`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800056d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800057ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800057d8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800056e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800057d8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800056eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800057e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800056eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800057e1`

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
0x1800056a0  mov     [rsp+arg_0], rbx
0x1800056a5  mov     [rsp+arg_8], rsi
0x1800056aa  push    rdi
0x1800056ab  sub     rsp, 20h
0x1800056af  mov     rdi, rcx
0x1800056b2  mov     dword ptr [rcx], 0
0x1800056b8  mov     rsi, [rcx+10h]
0x1800056bc  test    rsi, rsi
0x1800056bf  jz      short loc_1800056F9
0x1800056c1  call    cs:__imp_GetLastError
0x1800056c7  mov     ebx, eax
0x1800056c9  xor     r9d, r9d; msWindowLength
0x1800056cc  xor     r8d, r8d; msPeriod
0x1800056cf  xor     edx, edx; pftDueTime
0x1800056d1  mov     rcx, rsi; pti
0x1800056d4  call    cs:__imp_SetThreadpoolTimer
0x1800056da  mov     edx, 1; fCancelPendingCallbacks
0x1800056df  mov     rcx, rsi; pti
0x1800056e2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800056e8  mov     rcx, rsi; pti
0x1800056eb  call    cs:__imp_CloseThreadpoolTimer
0x1800056f1  mov     ecx, ebx; dwErrCode
0x1800056f3  call    cs:__imp_SetLastError
0x1800056f9  mov     qword ptr [rdi+10h], 0
0x180005701  mov     rcx, rdi; this
0x180005704  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180005709  mov     rcx, [rdi+68h]
0x18000570d  test    rcx, rcx
0x180005710  jz      short loc_180005742
0x180005712  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005719  test    rax, rax
0x18000571c  jnz     short loc_18000572D
0x18000571e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005725  test    rdx, rdx
0x180005728  jz      short loc_180005740
0x18000572a  mov     rax, rdx
0x18000572d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005732  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005739  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005740  jmp     short loc_180005750
0x180005742  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180005749  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180005750  mov     rcx, [rdi+60h]
0x180005754  test    rcx, rcx
0x180005757  jz      short loc_18000576C
0x180005759  test    rax, rax
0x18000575c  jnz     short loc_180005766
0x18000575e  test    rdx, rdx
0x180005761  jz      short loc_18000576C
0x180005763  mov     rax, rdx
0x180005766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000576b  nop
0x18000576c  mov     rbx, [rdi+58h]
0x180005770  mov     qword ptr [rdi+58h], 0
0x180005778  test    rbx, rbx
0x18000577b  jz      short loc_180005791
0x18000577d  call    cs:__imp_GetProcessHeap
0x180005783  mov     rcx, rax; hHeap
0x180005786  mov     r8, rbx; lpMem
0x180005789  xor     edx, edx; dwFlags
0x18000578b  call    cs:__imp_HeapFree
0x180005791  mov     rbx, [rdi+38h]
0x180005795  mov     qword ptr [rdi+38h], 0
0x18000579d  test    rbx, rbx
0x1800057a0  jz      short loc_1800057B6
0x1800057a2  call    cs:__imp_GetProcessHeap
0x1800057a8  mov     rcx, rax; hHeap
0x1800057ab  mov     r8, rbx; lpMem
0x1800057ae  xor     edx, edx; dwFlags
0x1800057b0  call    cs:__imp_HeapFree
0x1800057b6  mov     rbx, [rdi+10h]
0x1800057ba  test    rbx, rbx
0x1800057bd  jz      short loc_1800057E8
0x1800057bf  xor     r9d, r9d; msWindowLength
0x1800057c2  xor     r8d, r8d; msPeriod
0x1800057c5  xor     edx, edx; pftDueTime
0x1800057c7  mov     rcx, rbx; pti
0x1800057ca  call    cs:__imp_SetThreadpoolTimer
0x1800057d0  mov     edx, 1; fCancelPendingCallbacks
0x1800057d5  mov     rcx, rbx; pti
0x1800057d8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800057de  mov     rcx, rbx; pti
0x1800057e1  call    cs:__imp_CloseThreadpoolTimer
0x1800057e7  nop
0x1800057e8  mov     rbx, [rsp+28h+arg_0]
0x1800057ed  mov     rsi, [rsp+28h+arg_8]
0x1800057f2  add     rsp, 20h
0x1800057f6  pop     rdi
0x1800057f7  retn
```
