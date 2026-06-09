# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18002d7c0`
- end: `0x18002d918`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180059880`

## callees

- `0x18002d7c0`
- `0x180030f2c`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d813`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d80b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d901`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d80b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d901`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d7f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d8ea`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d7f4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d8ea`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d802`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d8f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d802`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d8f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d89d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d8c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d89d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d8c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d8ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d8d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d8ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d8d0`

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
0x18002d7c0  mov     [rsp+arg_0], rbx
0x18002d7c5  mov     [rsp+arg_8], rsi
0x18002d7ca  push    rdi
0x18002d7cb  sub     rsp, 20h
0x18002d7cf  mov     rdi, rcx
0x18002d7d2  mov     dword ptr [rcx], 0
0x18002d7d8  mov     rsi, [rcx+10h]
0x18002d7dc  test    rsi, rsi
0x18002d7df  jz      short loc_18002D819
0x18002d7e1  call    cs:__imp_GetLastError
0x18002d7e7  mov     ebx, eax
0x18002d7e9  xor     r9d, r9d; msWindowLength
0x18002d7ec  xor     r8d, r8d; msPeriod
0x18002d7ef  xor     edx, edx; pftDueTime
0x18002d7f1  mov     rcx, rsi; pti
0x18002d7f4  call    cs:__imp_SetThreadpoolTimer
0x18002d7fa  mov     edx, 1; fCancelPendingCallbacks
0x18002d7ff  mov     rcx, rsi; pti
0x18002d802  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002d808  mov     rcx, rsi; pti
0x18002d80b  call    cs:__imp_CloseThreadpoolTimer
0x18002d811  mov     ecx, ebx; dwErrCode
0x18002d813  call    cs:__imp_SetLastError
0x18002d819  mov     qword ptr [rdi+10h], 0
0x18002d821  mov     rcx, rdi; this
0x18002d824  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18002d829  mov     rcx, [rdi+68h]
0x18002d82d  test    rcx, rcx
0x18002d830  jz      short loc_18002D862
0x18002d832  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18002d839  test    rax, rax
0x18002d83c  jnz     short loc_18002D84D
0x18002d83e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18002d845  test    rdx, rdx
0x18002d848  jz      short loc_18002D860
0x18002d84a  mov     rax, rdx
0x18002d84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d852  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18002d859  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18002d860  jmp     short loc_18002D870
0x18002d862  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18002d869  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18002d870  mov     rcx, [rdi+60h]
0x18002d874  test    rcx, rcx
0x18002d877  jz      short loc_18002D88C
0x18002d879  test    rax, rax
0x18002d87c  jnz     short loc_18002D886
0x18002d87e  test    rdx, rdx
0x18002d881  jz      short loc_18002D88C
0x18002d883  mov     rax, rdx
0x18002d886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d88b  nop
0x18002d88c  mov     rbx, [rdi+58h]
0x18002d890  mov     qword ptr [rdi+58h], 0
0x18002d898  test    rbx, rbx
0x18002d89b  jz      short loc_18002D8B1
0x18002d89d  call    cs:__imp_GetProcessHeap
0x18002d8a3  mov     rcx, rax; hHeap
0x18002d8a6  mov     r8, rbx; lpMem
0x18002d8a9  xor     edx, edx; dwFlags
0x18002d8ab  call    cs:__imp_HeapFree
0x18002d8b1  mov     rbx, [rdi+38h]
0x18002d8b5  mov     qword ptr [rdi+38h], 0
0x18002d8bd  test    rbx, rbx
0x18002d8c0  jz      short loc_18002D8D6
0x18002d8c2  call    cs:__imp_GetProcessHeap
0x18002d8c8  mov     rcx, rax; hHeap
0x18002d8cb  mov     r8, rbx; lpMem
0x18002d8ce  xor     edx, edx; dwFlags
0x18002d8d0  call    cs:__imp_HeapFree
0x18002d8d6  mov     rbx, [rdi+10h]
0x18002d8da  test    rbx, rbx
0x18002d8dd  jz      short loc_18002D908
0x18002d8df  xor     r9d, r9d; msWindowLength
0x18002d8e2  xor     r8d, r8d; msPeriod
0x18002d8e5  xor     edx, edx; pftDueTime
0x18002d8e7  mov     rcx, rbx; pti
0x18002d8ea  call    cs:__imp_SetThreadpoolTimer
0x18002d8f0  mov     edx, 1; fCancelPendingCallbacks
0x18002d8f5  mov     rcx, rbx; pti
0x18002d8f8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002d8fe  mov     rcx, rbx; pti
0x18002d901  call    cs:__imp_CloseThreadpoolTimer
0x18002d907  nop
0x18002d908  mov     rbx, [rsp+28h+arg_0]
0x18002d90d  mov     rsi, [rsp+28h+arg_8]
0x18002d912  add     rsp, 20h
0x18002d916  pop     rdi
0x18002d917  retn
```
