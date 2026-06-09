# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180016a9c`
- end: `0x180016be2`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001d7f0`

## callees

- `0x180016a9c`
- `0x1800186d4`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016b8d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016b68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016b8d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b76`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016b9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016aef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016aef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016abd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016abd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016ae7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016bcc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016ae7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016bcc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016ade`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016bc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016ade`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016bc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016ad0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016bb5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016ad0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016bb5`

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
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( *((_QWORD *)this + 13) )
  {
    if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
    {
      v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
      if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
        goto LABEL_9;
      v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    }
    v4();
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  }
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
LABEL_9:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_14;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_14;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_14:
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
0x180016a9c  mov     [rsp+arg_0], rbx
0x180016aa1  mov     [rsp+arg_8], rsi
0x180016aa6  push    rdi
0x180016aa7  sub     rsp, 20h
0x180016aab  mov     dword ptr [rcx], 0
0x180016ab1  mov     rdi, rcx
0x180016ab4  mov     rsi, [rcx+10h]
0x180016ab8  test    rsi, rsi
0x180016abb  jz      short loc_180016AF5
0x180016abd  call    cs:__imp_GetLastError
0x180016ac3  xor     r9d, r9d; msWindowLength
0x180016ac6  xor     r8d, r8d; msPeriod
0x180016ac9  xor     edx, edx; pftDueTime
0x180016acb  mov     rcx, rsi; pti
0x180016ace  mov     ebx, eax
0x180016ad0  call    cs:__imp_SetThreadpoolTimer
0x180016ad6  mov     edx, 1; fCancelPendingCallbacks
0x180016adb  mov     rcx, rsi; pti
0x180016ade  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016ae4  mov     rcx, rsi; pti
0x180016ae7  call    cs:__imp_CloseThreadpoolTimer
0x180016aed  mov     ecx, ebx; dwErrCode
0x180016aef  call    cs:__imp_SetLastError
0x180016af5  mov     rcx, rdi; this
0x180016af8  mov     qword ptr [rdi+10h], 0
0x180016b00  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180016b05  mov     rcx, [rdi+68h]
0x180016b09  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180016b10  test    rcx, rcx
0x180016b13  jz      short loc_180016B35
0x180016b15  test    rax, rax
0x180016b18  jnz     short loc_180016B29
0x180016b1a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180016b21  test    rdx, rdx
0x180016b24  jz      short loc_180016B3C
0x180016b26  mov     rax, rdx
0x180016b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b2e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180016b35  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180016b3c  mov     rcx, [rdi+60h]
0x180016b40  test    rcx, rcx
0x180016b43  jz      short loc_180016B57
0x180016b45  test    rax, rax
0x180016b48  jnz     short loc_180016B52
0x180016b4a  test    rdx, rdx
0x180016b4d  jz      short loc_180016B57
0x180016b4f  mov     rax, rdx
0x180016b52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b57  mov     rbx, [rdi+58h]
0x180016b5b  mov     qword ptr [rdi+58h], 0
0x180016b63  test    rbx, rbx
0x180016b66  jz      short loc_180016B7C
0x180016b68  call    cs:__imp_GetProcessHeap
0x180016b6e  mov     r8, rbx; lpMem
0x180016b71  xor     edx, edx; dwFlags
0x180016b73  mov     rcx, rax; hHeap
0x180016b76  call    cs:__imp_HeapFree
0x180016b7c  mov     rbx, [rdi+38h]
0x180016b80  mov     qword ptr [rdi+38h], 0
0x180016b88  test    rbx, rbx
0x180016b8b  jz      short loc_180016BA1
0x180016b8d  call    cs:__imp_GetProcessHeap
0x180016b93  mov     r8, rbx; lpMem
0x180016b96  xor     edx, edx; dwFlags
0x180016b98  mov     rcx, rax; hHeap
0x180016b9b  call    cs:__imp_HeapFree
0x180016ba1  mov     rbx, [rdi+10h]
0x180016ba5  test    rbx, rbx
0x180016ba8  jz      short loc_180016BD2
0x180016baa  xor     r9d, r9d; msWindowLength
0x180016bad  xor     r8d, r8d; msPeriod
0x180016bb0  xor     edx, edx; pftDueTime
0x180016bb2  mov     rcx, rbx; pti
0x180016bb5  call    cs:__imp_SetThreadpoolTimer
0x180016bbb  mov     edx, 1; fCancelPendingCallbacks
0x180016bc0  mov     rcx, rbx; pti
0x180016bc3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016bc9  mov     rcx, rbx; pti
0x180016bcc  call    cs:__imp_CloseThreadpoolTimer
0x180016bd2  mov     rbx, [rsp+28h+arg_0]
0x180016bd7  mov     rsi, [rsp+28h+arg_8]
0x180016bdc  add     rsp, 20h
0x180016be0  pop     rdi
0x180016be1  retn
```
