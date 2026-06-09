# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800037c8`
- end: `0x18000390e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000dd90`

## callees

- `0x1800037c8`
- `0x18000671c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000381b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000381b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800037e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800038c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003894`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003894`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800038e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800037fc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800038e1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003813`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800038f8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003813`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800038f8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000380a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800038ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000380a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800038ef`

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
0x1800037c8  mov     [rsp+arg_0], rbx
0x1800037cd  mov     [rsp+arg_8], rsi
0x1800037d2  push    rdi
0x1800037d3  sub     rsp, 20h
0x1800037d7  mov     dword ptr [rcx], 0
0x1800037dd  mov     rdi, rcx
0x1800037e0  mov     rsi, [rcx+10h]
0x1800037e4  test    rsi, rsi
0x1800037e7  jz      short loc_180003821
0x1800037e9  call    cs:__imp_GetLastError
0x1800037ef  xor     r9d, r9d; msWindowLength
0x1800037f2  xor     r8d, r8d; msPeriod
0x1800037f5  xor     edx, edx; pftDueTime
0x1800037f7  mov     rcx, rsi; pti
0x1800037fa  mov     ebx, eax
0x1800037fc  call    cs:__imp_SetThreadpoolTimer
0x180003802  mov     edx, 1; fCancelPendingCallbacks
0x180003807  mov     rcx, rsi; pti
0x18000380a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003810  mov     rcx, rsi; pti
0x180003813  call    cs:__imp_CloseThreadpoolTimer
0x180003819  mov     ecx, ebx; dwErrCode
0x18000381b  call    cs:__imp_SetLastError
0x180003821  mov     rcx, rdi; this
0x180003824  mov     qword ptr [rdi+10h], 0
0x18000382c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180003831  mov     rcx, [rdi+68h]
0x180003835  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000383c  test    rcx, rcx
0x18000383f  jz      short loc_180003861
0x180003841  test    rax, rax
0x180003844  jnz     short loc_180003855
0x180003846  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000384d  test    rdx, rdx
0x180003850  jz      short loc_180003868
0x180003852  mov     rax, rdx
0x180003855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000385a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180003861  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180003868  mov     rcx, [rdi+60h]
0x18000386c  test    rcx, rcx
0x18000386f  jz      short loc_180003883
0x180003871  test    rax, rax
0x180003874  jnz     short loc_18000387E
0x180003876  test    rdx, rdx
0x180003879  jz      short loc_180003883
0x18000387b  mov     rax, rdx
0x18000387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003883  mov     rbx, [rdi+58h]
0x180003887  mov     qword ptr [rdi+58h], 0
0x18000388f  test    rbx, rbx
0x180003892  jz      short loc_1800038A8
0x180003894  call    cs:__imp_GetProcessHeap
0x18000389a  mov     r8, rbx; lpMem
0x18000389d  xor     edx, edx; dwFlags
0x18000389f  mov     rcx, rax; hHeap
0x1800038a2  call    cs:__imp_HeapFree
0x1800038a8  mov     rbx, [rdi+38h]
0x1800038ac  mov     qword ptr [rdi+38h], 0
0x1800038b4  test    rbx, rbx
0x1800038b7  jz      short loc_1800038CD
0x1800038b9  call    cs:__imp_GetProcessHeap
0x1800038bf  mov     r8, rbx; lpMem
0x1800038c2  xor     edx, edx; dwFlags
0x1800038c4  mov     rcx, rax; hHeap
0x1800038c7  call    cs:__imp_HeapFree
0x1800038cd  mov     rbx, [rdi+10h]
0x1800038d1  test    rbx, rbx
0x1800038d4  jz      short loc_1800038FE
0x1800038d6  xor     r9d, r9d; msWindowLength
0x1800038d9  xor     r8d, r8d; msPeriod
0x1800038dc  xor     edx, edx; pftDueTime
0x1800038de  mov     rcx, rbx; pti
0x1800038e1  call    cs:__imp_SetThreadpoolTimer
0x1800038e7  mov     edx, 1; fCancelPendingCallbacks
0x1800038ec  mov     rcx, rbx; pti
0x1800038ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800038f5  mov     rcx, rbx; pti
0x1800038f8  call    cs:__imp_CloseThreadpoolTimer
0x1800038fe  mov     rbx, [rsp+28h+arg_0]
0x180003903  mov     rsi, [rsp+28h+arg_8]
0x180003908  add     rsp, 20h
0x18000390c  pop     rdi
0x18000390d  retn
```
