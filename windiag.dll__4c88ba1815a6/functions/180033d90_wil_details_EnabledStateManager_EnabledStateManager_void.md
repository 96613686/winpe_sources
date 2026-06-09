# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180033d90`
- end: `0x180033ee8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18009bb80`

## callees

- `0x180033d90`
- `0x18003692c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033ea0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033e7b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180033ea0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033e6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033e92`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033e6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180033e92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033de3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180033de3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033db1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033dd2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033ec8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033dd2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180033ec8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033ddb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033ed1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033ddb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180033ed1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033dc4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033eba`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033dc4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180033eba`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
0x180033d90  mov     [rsp+arg_0], rbx
0x180033d95  mov     [rsp+arg_8], rsi
0x180033d9a  push    rdi
0x180033d9b  sub     rsp, 20h
0x180033d9f  mov     rdi, rcx
0x180033da2  mov     dword ptr [rcx], 0
0x180033da8  mov     rsi, [rcx+10h]
0x180033dac  test    rsi, rsi
0x180033daf  jz      short loc_180033DE9
0x180033db1  call    cs:__imp_GetLastError
0x180033db7  mov     ebx, eax
0x180033db9  xor     r9d, r9d; msWindowLength
0x180033dbc  xor     r8d, r8d; msPeriod
0x180033dbf  xor     edx, edx; pftDueTime
0x180033dc1  mov     rcx, rsi; pti
0x180033dc4  call    cs:__imp_SetThreadpoolTimer
0x180033dca  mov     edx, 1; fCancelPendingCallbacks
0x180033dcf  mov     rcx, rsi; pti
0x180033dd2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180033dd8  mov     rcx, rsi; pti
0x180033ddb  call    cs:__imp_CloseThreadpoolTimer
0x180033de1  mov     ecx, ebx; dwErrCode
0x180033de3  call    cs:__imp_SetLastError
0x180033de9  mov     qword ptr [rdi+10h], 0
0x180033df1  mov     rcx, rdi; this
0x180033df4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180033df9  mov     rcx, [rdi+68h]
0x180033dfd  test    rcx, rcx
0x180033e00  jz      short loc_180033E32
0x180033e02  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180033e09  test    rax, rax
0x180033e0c  jnz     short loc_180033E1D
0x180033e0e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180033e15  test    rdx, rdx
0x180033e18  jz      short loc_180033E30
0x180033e1a  mov     rax, rdx
0x180033e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e22  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180033e29  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180033e30  jmp     short loc_180033E40
0x180033e32  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180033e39  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180033e40  mov     rcx, [rdi+60h]
0x180033e44  test    rcx, rcx
0x180033e47  jz      short loc_180033E5C
0x180033e49  test    rax, rax
0x180033e4c  jnz     short loc_180033E56
0x180033e4e  test    rdx, rdx
0x180033e51  jz      short loc_180033E5C
0x180033e53  mov     rax, rdx
0x180033e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e5b  nop
0x180033e5c  mov     rbx, [rdi+58h]
0x180033e60  mov     qword ptr [rdi+58h], 0
0x180033e68  test    rbx, rbx
0x180033e6b  jz      short loc_180033E81
0x180033e6d  call    cs:__imp_GetProcessHeap
0x180033e73  mov     rcx, rax; hHeap
0x180033e76  mov     r8, rbx; lpMem
0x180033e79  xor     edx, edx; dwFlags
0x180033e7b  call    cs:__imp_HeapFree
0x180033e81  mov     rbx, [rdi+38h]
0x180033e85  mov     qword ptr [rdi+38h], 0
0x180033e8d  test    rbx, rbx
0x180033e90  jz      short loc_180033EA6
0x180033e92  call    cs:__imp_GetProcessHeap
0x180033e98  mov     rcx, rax; hHeap
0x180033e9b  mov     r8, rbx; lpMem
0x180033e9e  xor     edx, edx; dwFlags
0x180033ea0  call    cs:__imp_HeapFree
0x180033ea6  mov     rbx, [rdi+10h]
0x180033eaa  test    rbx, rbx
0x180033ead  jz      short loc_180033ED8
0x180033eaf  xor     r9d, r9d; msWindowLength
0x180033eb2  xor     r8d, r8d; msPeriod
0x180033eb5  xor     edx, edx; pftDueTime
0x180033eb7  mov     rcx, rbx; pti
0x180033eba  call    cs:__imp_SetThreadpoolTimer
0x180033ec0  mov     edx, 1; fCancelPendingCallbacks
0x180033ec5  mov     rcx, rbx; pti
0x180033ec8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180033ece  mov     rcx, rbx; pti
0x180033ed1  call    cs:__imp_CloseThreadpoolTimer
0x180033ed7  nop
0x180033ed8  mov     rbx, [rsp+28h+arg_0]
0x180033edd  mov     rsi, [rsp+28h+arg_8]
0x180033ee2  add     rsp, 20h
0x180033ee6  pop     rdi
0x180033ee7  retn
```
