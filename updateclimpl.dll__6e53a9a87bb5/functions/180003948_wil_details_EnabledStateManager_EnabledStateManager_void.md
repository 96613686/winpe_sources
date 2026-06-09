# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003948`
- end: `0x180003aa0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800161d0`

## callees

- `0x180003020`
- `0x180003948`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003998`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003966`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800039e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800039f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003990`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a89`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003990`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003a89`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003987`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003987`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180003a80`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003979`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a72`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003979`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003a72`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax
  void (*v8)(void); // rax
  __int64 v9; // rdx
  struct _TP_TIMER *v10; // rbx

  *(_BYTE *)this = 0;
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
  *(_BYTE *)this = 0;
  wil::details::EnabledStateManager::RecordCachedUsageUnderLock(this);
  v4 = (void *)*((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_14;
  }
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_14;
    v8 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v8();
  v9 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v8 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_14:
  if ( !*((_QWORD *)this + 4) )
    goto LABEL_19;
  if ( !v8 )
  {
    if ( !v9 )
      goto LABEL_19;
    v8 = (void (*)(void))v9;
  }
  v8();
LABEL_19:
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
0x180003948  mov     [rsp+arg_0], rbx
0x18000394d  mov     [rsp+arg_8], rsi
0x180003952  push    rdi
0x180003953  sub     rsp, 20h
0x180003957  mov     rdi, rcx
0x18000395a  mov     byte ptr [rcx], 0
0x18000395d  mov     rsi, [rcx+10h]
0x180003961  test    rsi, rsi
0x180003964  jz      short loc_18000399E
0x180003966  call    cs:__imp_GetLastError
0x18000396c  mov     ebx, eax
0x18000396e  xor     r9d, r9d; msWindowLength
0x180003971  xor     r8d, r8d; msPeriod
0x180003974  xor     edx, edx; pftDueTime
0x180003976  mov     rcx, rsi; pti
0x180003979  call    cs:__imp_SetThreadpoolTimer
0x18000397f  mov     edx, 1; fCancelPendingCallbacks
0x180003984  mov     rcx, rsi; pti
0x180003987  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000398d  mov     rcx, rsi; pti
0x180003990  call    cs:__imp_CloseThreadpoolTimer
0x180003996  mov     ecx, ebx; dwErrCode
0x180003998  call    cs:__imp_SetLastError
0x18000399e  mov     qword ptr [rdi+10h], 0
0x1800039a6  mov     byte ptr [rdi], 0
0x1800039a9  mov     rcx, rdi; this
0x1800039ac  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x1800039b1  mov     rbx, [rdi+68h]
0x1800039b5  mov     qword ptr [rdi+68h], 0
0x1800039bd  test    rbx, rbx
0x1800039c0  jz      short loc_1800039D6
0x1800039c2  call    cs:__imp_GetProcessHeap
0x1800039c8  mov     rcx, rax; hHeap
0x1800039cb  mov     r8, rbx; lpMem
0x1800039ce  xor     edx, edx; dwFlags
0x1800039d0  call    cs:__imp_HeapFree
0x1800039d6  mov     rbx, [rdi+48h]
0x1800039da  mov     qword ptr [rdi+48h], 0
0x1800039e2  test    rbx, rbx
0x1800039e5  jz      short loc_1800039FB
0x1800039e7  call    cs:__imp_GetProcessHeap
0x1800039ed  mov     rcx, rax; hHeap
0x1800039f0  mov     r8, rbx; lpMem
0x1800039f3  xor     edx, edx; dwFlags
0x1800039f5  call    cs:__imp_HeapFree
0x1800039fb  mov     rcx, [rdi+28h]
0x1800039ff  test    rcx, rcx
0x180003a02  jz      short loc_180003A34
0x180003a04  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003a0b  test    rax, rax
0x180003a0e  jnz     short loc_180003A1F
0x180003a10  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003a17  test    rdx, rdx
0x180003a1a  jz      short loc_180003A32
0x180003a1c  mov     rax, rdx
0x180003a1f  call    _guard_dispatch_icall
0x180003a24  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003a2b  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003a32  jmp     short loc_180003A42
0x180003a34  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003a3b  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003a42  mov     rcx, [rdi+20h]
0x180003a46  test    rcx, rcx
0x180003a49  jz      short loc_180003A5E
0x180003a4b  test    rax, rax
0x180003a4e  jnz     short loc_180003A58
0x180003a50  test    rdx, rdx
0x180003a53  jz      short loc_180003A5E
0x180003a55  mov     rax, rdx
0x180003a58  call    _guard_dispatch_icall
0x180003a5d  nop
0x180003a5e  mov     rbx, [rdi+10h]
0x180003a62  test    rbx, rbx
0x180003a65  jz      short loc_180003A90
0x180003a67  xor     r9d, r9d; msWindowLength
0x180003a6a  xor     r8d, r8d; msPeriod
0x180003a6d  xor     edx, edx; pftDueTime
0x180003a6f  mov     rcx, rbx; pti
0x180003a72  call    cs:__imp_SetThreadpoolTimer
0x180003a78  mov     edx, 1; fCancelPendingCallbacks
0x180003a7d  mov     rcx, rbx; pti
0x180003a80  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003a86  mov     rcx, rbx; pti
0x180003a89  call    cs:__imp_CloseThreadpoolTimer
0x180003a8f  nop
0x180003a90  mov     rbx, [rsp+28h+arg_0]
0x180003a95  mov     rsi, [rsp+28h+arg_8]
0x180003a9a  add     rsp, 20h
0x180003a9e  pop     rdi
0x180003a9f  retn
```
