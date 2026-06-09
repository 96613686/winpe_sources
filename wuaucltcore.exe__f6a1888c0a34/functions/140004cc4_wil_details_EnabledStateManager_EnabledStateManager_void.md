# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140004cc4`
- end: `0x140004e1c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140022030`

## callees

- `0x140004cc4`
- `0x140004eb8`
- `0x1400206e0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004d71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004d63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ce2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004ce2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004d14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140004d14`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004d0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004e05`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004d0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140004e05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004cf5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004dee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004cf5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004dee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004d03`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004dfc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004d03`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140004dfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140004cc4  mov     [rsp+arg_0], rbx
0x140004cc9  mov     [rsp+arg_8], rsi
0x140004cce  push    rdi
0x140004ccf  sub     rsp, 20h
0x140004cd3  mov     rdi, rcx
0x140004cd6  mov     byte ptr [rcx], 0
0x140004cd9  mov     rsi, [rcx+10h]
0x140004cdd  test    rsi, rsi
0x140004ce0  jz      short loc_140004D1A
0x140004ce2  call    cs:__imp_GetLastError
0x140004ce8  mov     ebx, eax
0x140004cea  xor     r9d, r9d; msWindowLength
0x140004ced  xor     r8d, r8d; msPeriod
0x140004cf0  xor     edx, edx; pftDueTime
0x140004cf2  mov     rcx, rsi; pti
0x140004cf5  call    cs:__imp_SetThreadpoolTimer
0x140004cfb  mov     edx, 1; fCancelPendingCallbacks
0x140004d00  mov     rcx, rsi; pti
0x140004d03  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004d09  mov     rcx, rsi; pti
0x140004d0c  call    cs:__imp_CloseThreadpoolTimer
0x140004d12  mov     ecx, ebx; dwErrCode
0x140004d14  call    cs:__imp_SetLastError
0x140004d1a  mov     qword ptr [rdi+10h], 0
0x140004d22  mov     byte ptr [rdi], 0
0x140004d25  mov     rcx, rdi; this
0x140004d28  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x140004d2d  mov     rbx, [rdi+68h]
0x140004d31  mov     qword ptr [rdi+68h], 0
0x140004d39  test    rbx, rbx
0x140004d3c  jz      short loc_140004D52
0x140004d3e  call    cs:__imp_GetProcessHeap
0x140004d44  mov     rcx, rax; hHeap
0x140004d47  mov     r8, rbx; lpMem
0x140004d4a  xor     edx, edx; dwFlags
0x140004d4c  call    cs:__imp_HeapFree
0x140004d52  mov     rbx, [rdi+48h]
0x140004d56  mov     qword ptr [rdi+48h], 0
0x140004d5e  test    rbx, rbx
0x140004d61  jz      short loc_140004D77
0x140004d63  call    cs:__imp_GetProcessHeap
0x140004d69  mov     rcx, rax; hHeap
0x140004d6c  mov     r8, rbx; lpMem
0x140004d6f  xor     edx, edx; dwFlags
0x140004d71  call    cs:__imp_HeapFree
0x140004d77  mov     rcx, [rdi+28h]
0x140004d7b  test    rcx, rcx
0x140004d7e  jz      short loc_140004DB0
0x140004d80  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004d87  test    rax, rax
0x140004d8a  jnz     short loc_140004D9B
0x140004d8c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004d93  test    rdx, rdx
0x140004d96  jz      short loc_140004DAE
0x140004d98  mov     rax, rdx
0x140004d9b  call    _guard_dispatch_icall
0x140004da0  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004da7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004dae  jmp     short loc_140004DBE
0x140004db0  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004db7  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004dbe  mov     rcx, [rdi+20h]
0x140004dc2  test    rcx, rcx
0x140004dc5  jz      short loc_140004DDA
0x140004dc7  test    rax, rax
0x140004dca  jnz     short loc_140004DD4
0x140004dcc  test    rdx, rdx
0x140004dcf  jz      short loc_140004DDA
0x140004dd1  mov     rax, rdx
0x140004dd4  call    _guard_dispatch_icall
0x140004dd9  nop
0x140004dda  mov     rbx, [rdi+10h]
0x140004dde  test    rbx, rbx
0x140004de1  jz      short loc_140004E0C
0x140004de3  xor     r9d, r9d; msWindowLength
0x140004de6  xor     r8d, r8d; msPeriod
0x140004de9  xor     edx, edx; pftDueTime
0x140004deb  mov     rcx, rbx; pti
0x140004dee  call    cs:__imp_SetThreadpoolTimer
0x140004df4  mov     edx, 1; fCancelPendingCallbacks
0x140004df9  mov     rcx, rbx; pti
0x140004dfc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004e02  mov     rcx, rbx; pti
0x140004e05  call    cs:__imp_CloseThreadpoolTimer
0x140004e0b  nop
0x140004e0c  mov     rbx, [rsp+28h+arg_0]
0x140004e11  mov     rsi, [rsp+28h+arg_8]
0x140004e16  add     rsp, 20h
0x140004e1a  pop     rdi
0x140004e1b  retn
```
