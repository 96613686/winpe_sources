# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800087d4`
- end: `0x18000892c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180035180`

## callees

- `0x1800087d4`
- `0x18000aed4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800088d6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800088e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087f5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008827`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008827`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008816`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000890c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008816`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000890c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000881f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008915`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000881f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008915`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008808`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800088fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008808`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800088fe`

## pseudocode

```c
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
0x1800087d4  mov     [rsp+arg_0], rbx
0x1800087d9  mov     [rsp+arg_8], rsi
0x1800087de  push    rdi
0x1800087df  sub     rsp, 20h
0x1800087e3  mov     rdi, rcx
0x1800087e6  mov     dword ptr [rcx], 0
0x1800087ec  mov     rsi, [rcx+10h]
0x1800087f0  test    rsi, rsi
0x1800087f3  jz      short loc_18000882D
0x1800087f5  call    cs:__imp_GetLastError
0x1800087fb  mov     ebx, eax
0x1800087fd  xor     r9d, r9d; msWindowLength
0x180008800  xor     r8d, r8d; msPeriod
0x180008803  xor     edx, edx; pftDueTime
0x180008805  mov     rcx, rsi; pti
0x180008808  call    cs:__imp_SetThreadpoolTimer
0x18000880e  mov     edx, 1; fCancelPendingCallbacks
0x180008813  mov     rcx, rsi; pti
0x180008816  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000881c  mov     rcx, rsi; pti
0x18000881f  call    cs:__imp_CloseThreadpoolTimer
0x180008825  mov     ecx, ebx; dwErrCode
0x180008827  call    cs:__imp_SetLastError
0x18000882d  mov     qword ptr [rdi+10h], 0
0x180008835  mov     rcx, rdi; this
0x180008838  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000883d  mov     rcx, [rdi+68h]
0x180008841  test    rcx, rcx
0x180008844  jz      short loc_180008876
0x180008846  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000884d  test    rax, rax
0x180008850  jnz     short loc_180008861
0x180008852  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008859  test    rdx, rdx
0x18000885c  jz      short loc_180008874
0x18000885e  mov     rax, rdx
0x180008861  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008866  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000886d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008874  jmp     short loc_180008884
0x180008876  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000887d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008884  mov     rcx, [rdi+60h]
0x180008888  test    rcx, rcx
0x18000888b  jz      short loc_1800088A0
0x18000888d  test    rax, rax
0x180008890  jnz     short loc_18000889A
0x180008892  test    rdx, rdx
0x180008895  jz      short loc_1800088A0
0x180008897  mov     rax, rdx
0x18000889a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000889f  nop
0x1800088a0  mov     rbx, [rdi+58h]
0x1800088a4  mov     qword ptr [rdi+58h], 0
0x1800088ac  test    rbx, rbx
0x1800088af  jz      short loc_1800088C5
0x1800088b1  call    cs:__imp_GetProcessHeap
0x1800088b7  mov     rcx, rax; hHeap
0x1800088ba  mov     r8, rbx; lpMem
0x1800088bd  xor     edx, edx; dwFlags
0x1800088bf  call    cs:__imp_HeapFree
0x1800088c5  mov     rbx, [rdi+38h]
0x1800088c9  mov     qword ptr [rdi+38h], 0
0x1800088d1  test    rbx, rbx
0x1800088d4  jz      short loc_1800088EA
0x1800088d6  call    cs:__imp_GetProcessHeap
0x1800088dc  mov     rcx, rax; hHeap
0x1800088df  mov     r8, rbx; lpMem
0x1800088e2  xor     edx, edx; dwFlags
0x1800088e4  call    cs:__imp_HeapFree
0x1800088ea  mov     rbx, [rdi+10h]
0x1800088ee  test    rbx, rbx
0x1800088f1  jz      short loc_18000891C
0x1800088f3  xor     r9d, r9d; msWindowLength
0x1800088f6  xor     r8d, r8d; msPeriod
0x1800088f9  xor     edx, edx; pftDueTime
0x1800088fb  mov     rcx, rbx; pti
0x1800088fe  call    cs:__imp_SetThreadpoolTimer
0x180008904  mov     edx, 1; fCancelPendingCallbacks
0x180008909  mov     rcx, rbx; pti
0x18000890c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008912  mov     rcx, rbx; pti
0x180008915  call    cs:__imp_CloseThreadpoolTimer
0x18000891b  nop
0x18000891c  mov     rbx, [rsp+28h+arg_0]
0x180008921  mov     rsi, [rsp+28h+arg_8]
0x180008926  add     rsp, 20h
0x18000892a  pop     rdi
0x18000892b  retn
```
