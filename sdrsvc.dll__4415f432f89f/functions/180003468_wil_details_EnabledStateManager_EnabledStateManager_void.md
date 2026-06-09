# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180003468`
- end: `0x1800035ae`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180021be0`

## callees

- `0x180003468`
- `0x180005d8c`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003534`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003559`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003534`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003559`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003542`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003567`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003542`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003489`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034bb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800034bb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800034b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003598`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800034b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003598`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000349c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003581`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000349c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003581`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800034aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000358f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800034aa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000358f`

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
0x180003468  mov     [rsp+arg_0], rbx
0x18000346d  mov     [rsp+arg_8], rsi
0x180003472  push    rdi
0x180003473  sub     rsp, 20h
0x180003477  mov     dword ptr [rcx], 0
0x18000347d  mov     rdi, rcx
0x180003480  mov     rsi, [rcx+10h]
0x180003484  test    rsi, rsi
0x180003487  jz      short loc_1800034C1
0x180003489  call    cs:__imp_GetLastError
0x18000348f  xor     r9d, r9d; msWindowLength
0x180003492  xor     r8d, r8d; msPeriod
0x180003495  xor     edx, edx; pftDueTime
0x180003497  mov     rcx, rsi; pti
0x18000349a  mov     ebx, eax
0x18000349c  call    cs:__imp_SetThreadpoolTimer
0x1800034a2  mov     edx, 1; fCancelPendingCallbacks
0x1800034a7  mov     rcx, rsi; pti
0x1800034aa  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800034b0  mov     rcx, rsi; pti
0x1800034b3  call    cs:__imp_CloseThreadpoolTimer
0x1800034b9  mov     ecx, ebx; dwErrCode
0x1800034bb  call    cs:__imp_SetLastError
0x1800034c1  mov     rcx, rdi; this
0x1800034c4  mov     qword ptr [rdi+10h], 0
0x1800034cc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x1800034d1  mov     rcx, [rdi+68h]
0x1800034d5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800034dc  test    rcx, rcx
0x1800034df  jz      short loc_180003501
0x1800034e1  test    rax, rax
0x1800034e4  jnz     short loc_1800034F5
0x1800034e6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800034ed  test    rdx, rdx
0x1800034f0  jz      short loc_180003508
0x1800034f2  mov     rax, rdx
0x1800034f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034fa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003501  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003508  mov     rcx, [rdi+60h]
0x18000350c  test    rcx, rcx
0x18000350f  jz      short loc_180003523
0x180003511  test    rax, rax
0x180003514  jnz     short loc_18000351E
0x180003516  test    rdx, rdx
0x180003519  jz      short loc_180003523
0x18000351b  mov     rax, rdx
0x18000351e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003523  mov     rbx, [rdi+58h]
0x180003527  mov     qword ptr [rdi+58h], 0
0x18000352f  test    rbx, rbx
0x180003532  jz      short loc_180003548
0x180003534  call    cs:__imp_GetProcessHeap
0x18000353a  mov     r8, rbx; lpMem
0x18000353d  xor     edx, edx; dwFlags
0x18000353f  mov     rcx, rax; hHeap
0x180003542  call    cs:__imp_HeapFree
0x180003548  mov     rbx, [rdi+38h]
0x18000354c  mov     qword ptr [rdi+38h], 0
0x180003554  test    rbx, rbx
0x180003557  jz      short loc_18000356D
0x180003559  call    cs:__imp_GetProcessHeap
0x18000355f  mov     r8, rbx; lpMem
0x180003562  xor     edx, edx; dwFlags
0x180003564  mov     rcx, rax; hHeap
0x180003567  call    cs:__imp_HeapFree
0x18000356d  mov     rbx, [rdi+10h]
0x180003571  test    rbx, rbx
0x180003574  jz      short loc_18000359E
0x180003576  xor     r9d, r9d; msWindowLength
0x180003579  xor     r8d, r8d; msPeriod
0x18000357c  xor     edx, edx; pftDueTime
0x18000357e  mov     rcx, rbx; pti
0x180003581  call    cs:__imp_SetThreadpoolTimer
0x180003587  mov     edx, 1; fCancelPendingCallbacks
0x18000358c  mov     rcx, rbx; pti
0x18000358f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003595  mov     rcx, rbx; pti
0x180003598  call    cs:__imp_CloseThreadpoolTimer
0x18000359e  mov     rbx, [rsp+28h+arg_0]
0x1800035a3  mov     rsi, [rsp+28h+arg_8]
0x1800035a8  add     rsp, 20h
0x1800035ac  pop     rdi
0x1800035ad  retn
```
