# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140004bf4`
- end: `0x140004d4c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001cfa0`

## callees

- `0x140004bf4`
- `0x140008f4c`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c15`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004c47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004c47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004cf6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004cd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004cf6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004cdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d04`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004cdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004c3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004d35`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004c3f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004d35`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004c36`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004d2c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004c36`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004d2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004c28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004d1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004c28`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004d1e`

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
0x140004bf4  mov     [rsp+arg_0], rbx
0x140004bf9  mov     [rsp+arg_8], rsi
0x140004bfe  push    rdi
0x140004bff  sub     rsp, 20h
0x140004c03  mov     rdi, rcx
0x140004c06  mov     dword ptr [rcx], 0
0x140004c0c  mov     rsi, [rcx+10h]
0x140004c10  test    rsi, rsi
0x140004c13  jz      short loc_140004C4D
0x140004c15  call    cs:__imp_GetLastError
0x140004c1b  mov     ebx, eax
0x140004c1d  xor     r9d, r9d; msWindowLength
0x140004c20  xor     r8d, r8d; msPeriod
0x140004c23  xor     edx, edx; pftDueTime
0x140004c25  mov     rcx, rsi; pti
0x140004c28  call    cs:__imp_SetThreadpoolTimer
0x140004c2e  mov     edx, 1; fCancelPendingCallbacks
0x140004c33  mov     rcx, rsi; pti
0x140004c36  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004c3c  mov     rcx, rsi; pti
0x140004c3f  call    cs:__imp_CloseThreadpoolTimer
0x140004c45  mov     ecx, ebx; dwErrCode
0x140004c47  call    cs:__imp_SetLastError
0x140004c4d  mov     qword ptr [rdi+10h], 0
0x140004c55  mov     rcx, rdi; this
0x140004c58  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140004c5d  mov     rcx, [rdi+68h]
0x140004c61  test    rcx, rcx
0x140004c64  jz      short loc_140004C96
0x140004c66  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004c6d  test    rax, rax
0x140004c70  jnz     short loc_140004C81
0x140004c72  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004c79  test    rdx, rdx
0x140004c7c  jz      short loc_140004C94
0x140004c7e  mov     rax, rdx
0x140004c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c86  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004c8d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004c94  jmp     short loc_140004CA4
0x140004c96  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004c9d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004ca4  mov     rcx, [rdi+60h]
0x140004ca8  test    rcx, rcx
0x140004cab  jz      short loc_140004CC0
0x140004cad  test    rax, rax
0x140004cb0  jnz     short loc_140004CBA
0x140004cb2  test    rdx, rdx
0x140004cb5  jz      short loc_140004CC0
0x140004cb7  mov     rax, rdx
0x140004cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004cbf  nop
0x140004cc0  mov     rbx, [rdi+58h]
0x140004cc4  mov     qword ptr [rdi+58h], 0
0x140004ccc  test    rbx, rbx
0x140004ccf  jz      short loc_140004CE5
0x140004cd1  call    cs:__imp_GetProcessHeap
0x140004cd7  mov     rcx, rax; hHeap
0x140004cda  mov     r8, rbx; lpMem
0x140004cdd  xor     edx, edx; dwFlags
0x140004cdf  call    cs:__imp_HeapFree
0x140004ce5  mov     rbx, [rdi+38h]
0x140004ce9  mov     qword ptr [rdi+38h], 0
0x140004cf1  test    rbx, rbx
0x140004cf4  jz      short loc_140004D0A
0x140004cf6  call    cs:__imp_GetProcessHeap
0x140004cfc  mov     rcx, rax; hHeap
0x140004cff  mov     r8, rbx; lpMem
0x140004d02  xor     edx, edx; dwFlags
0x140004d04  call    cs:__imp_HeapFree
0x140004d0a  mov     rbx, [rdi+10h]
0x140004d0e  test    rbx, rbx
0x140004d11  jz      short loc_140004D3C
0x140004d13  xor     r9d, r9d; msWindowLength
0x140004d16  xor     r8d, r8d; msPeriod
0x140004d19  xor     edx, edx; pftDueTime
0x140004d1b  mov     rcx, rbx; pti
0x140004d1e  call    cs:__imp_SetThreadpoolTimer
0x140004d24  mov     edx, 1; fCancelPendingCallbacks
0x140004d29  mov     rcx, rbx; pti
0x140004d2c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004d32  mov     rcx, rbx; pti
0x140004d35  call    cs:__imp_CloseThreadpoolTimer
0x140004d3b  nop
0x140004d3c  mov     rbx, [rsp+28h+arg_0]
0x140004d41  mov     rsi, [rsp+28h+arg_8]
0x140004d46  add     rsp, 20h
0x140004d4a  pop     rdi
0x140004d4b  retn
```
