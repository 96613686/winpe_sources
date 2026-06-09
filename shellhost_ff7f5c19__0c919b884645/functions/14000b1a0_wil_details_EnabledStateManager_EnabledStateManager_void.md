# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x14000b1a0`
- end: `0x14000b2dd`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `317`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140065890`

## callees

- `0x140009610`
- `0x14000b1a0`
- `0x140067010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b26d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b28e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b26d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b28e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b27b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b29c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b27b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b29c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b1eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000b1eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b1b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b1e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b2cd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b1e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b2cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b1cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b2b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b1cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b2b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b1da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b2c4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b1da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b2c4`

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
0x14000b1a0  push    rbx
0x14000b1a2  push    rbp
0x14000b1a3  push    rsi
0x14000b1a4  push    rdi
0x14000b1a5  sub     rsp, 28h
0x14000b1a9  mov     rdi, rcx
0x14000b1ac  xor     ebp, ebp
0x14000b1ae  mov     [rcx], ebp
0x14000b1b0  mov     rsi, [rcx+10h]
0x14000b1b4  test    rsi, rsi
0x14000b1b7  jz      short loc_14000B1F1
0x14000b1b9  call    cs:__imp_GetLastError
0x14000b1bf  mov     ebx, eax
0x14000b1c1  xor     r9d, r9d; msWindowLength
0x14000b1c4  xor     r8d, r8d; msPeriod
0x14000b1c7  xor     edx, edx; pftDueTime
0x14000b1c9  mov     rcx, rsi; pti
0x14000b1cc  call    cs:__imp_SetThreadpoolTimer
0x14000b1d2  mov     edx, 1; fCancelPendingCallbacks
0x14000b1d7  mov     rcx, rsi; pti
0x14000b1da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b1e0  mov     rcx, rsi; pti
0x14000b1e3  call    cs:__imp_CloseThreadpoolTimer
0x14000b1e9  mov     ecx, ebx; dwErrCode
0x14000b1eb  call    cs:__imp_SetLastError
0x14000b1f1  mov     [rdi+10h], rbp
0x14000b1f5  mov     rcx, rdi; this
0x14000b1f8  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000b1fd  mov     rcx, [rdi+68h]
0x14000b201  test    rcx, rcx
0x14000b204  jz      short loc_14000B236
0x14000b206  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000b20d  test    rax, rax
0x14000b210  jnz     short loc_14000B221
0x14000b212  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000b219  test    rdx, rdx
0x14000b21c  jz      short loc_14000B234
0x14000b21e  mov     rax, rdx
0x14000b221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b226  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000b22d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000b234  jmp     short loc_14000B244
0x14000b236  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000b23d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000b244  mov     rcx, [rdi+60h]
0x14000b248  test    rcx, rcx
0x14000b24b  jz      short loc_14000B260
0x14000b24d  test    rax, rax
0x14000b250  jnz     short loc_14000B25A
0x14000b252  test    rdx, rdx
0x14000b255  jz      short loc_14000B260
0x14000b257  mov     rax, rdx
0x14000b25a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b25f  nop
0x14000b260  mov     rbx, [rdi+58h]
0x14000b264  mov     [rdi+58h], rbp
0x14000b268  test    rbx, rbx
0x14000b26b  jz      short loc_14000B281
0x14000b26d  call    cs:__imp_GetProcessHeap
0x14000b273  mov     rcx, rax; hHeap
0x14000b276  mov     r8, rbx; lpMem
0x14000b279  xor     edx, edx; dwFlags
0x14000b27b  call    cs:__imp_HeapFree
0x14000b281  mov     rbx, [rdi+38h]
0x14000b285  mov     [rdi+38h], rbp
0x14000b289  test    rbx, rbx
0x14000b28c  jz      short loc_14000B2A2
0x14000b28e  call    cs:__imp_GetProcessHeap
0x14000b294  mov     rcx, rax; hHeap
0x14000b297  mov     r8, rbx; lpMem
0x14000b29a  xor     edx, edx; dwFlags
0x14000b29c  call    cs:__imp_HeapFree
0x14000b2a2  mov     rbx, [rdi+10h]
0x14000b2a6  test    rbx, rbx
0x14000b2a9  jz      short loc_14000B2D4
0x14000b2ab  xor     r9d, r9d; msWindowLength
0x14000b2ae  xor     r8d, r8d; msPeriod
0x14000b2b1  xor     edx, edx; pftDueTime
0x14000b2b3  mov     rcx, rbx; pti
0x14000b2b6  call    cs:__imp_SetThreadpoolTimer
0x14000b2bc  mov     edx, 1; fCancelPendingCallbacks
0x14000b2c1  mov     rcx, rbx; pti
0x14000b2c4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b2ca  mov     rcx, rbx; pti
0x14000b2cd  call    cs:__imp_CloseThreadpoolTimer
0x14000b2d3  nop
0x14000b2d4  add     rsp, 28h
0x14000b2d8  pop     rdi
0x14000b2d9  pop     rsi
0x14000b2da  pop     rbp
0x14000b2db  pop     rbx
0x14000b2dc  retn
```
