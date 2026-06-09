# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000b830`
- end: `0x18000b988`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800f1090`

## callees

- `0x18000b830`
- `0x18000ba18`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b8cf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b8dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b84e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b84e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b880`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b880`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b861`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b95a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b861`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b95a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b878`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b971`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b878`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b971`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b86f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b968`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b86f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b968`

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
0x18000b830  mov     [rsp+arg_0], rbx
0x18000b835  mov     [rsp+arg_8], rsi
0x18000b83a  push    rdi
0x18000b83b  sub     rsp, 20h
0x18000b83f  mov     rdi, rcx
0x18000b842  mov     byte ptr [rcx], 0
0x18000b845  mov     rsi, [rcx+10h]
0x18000b849  test    rsi, rsi
0x18000b84c  jz      short loc_18000B886
0x18000b84e  call    cs:__imp_GetLastError
0x18000b854  mov     ebx, eax
0x18000b856  xor     r9d, r9d; msWindowLength
0x18000b859  xor     r8d, r8d; msPeriod
0x18000b85c  xor     edx, edx; pftDueTime
0x18000b85e  mov     rcx, rsi; pti
0x18000b861  call    cs:__imp_SetThreadpoolTimer
0x18000b867  mov     edx, 1; fCancelPendingCallbacks
0x18000b86c  mov     rcx, rsi; pti
0x18000b86f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b875  mov     rcx, rsi; pti
0x18000b878  call    cs:__imp_CloseThreadpoolTimer
0x18000b87e  mov     ecx, ebx; dwErrCode
0x18000b880  call    cs:__imp_SetLastError
0x18000b886  mov     qword ptr [rdi+10h], 0
0x18000b88e  mov     byte ptr [rdi], 0
0x18000b891  mov     rcx, rdi; this
0x18000b894  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18000b899  mov     rbx, [rdi+68h]
0x18000b89d  mov     qword ptr [rdi+68h], 0
0x18000b8a5  test    rbx, rbx
0x18000b8a8  jz      short loc_18000B8BE
0x18000b8aa  call    cs:__imp_GetProcessHeap
0x18000b8b0  mov     rcx, rax; hHeap
0x18000b8b3  mov     r8, rbx; lpMem
0x18000b8b6  xor     edx, edx; dwFlags
0x18000b8b8  call    cs:__imp_HeapFree
0x18000b8be  mov     rbx, [rdi+48h]
0x18000b8c2  mov     qword ptr [rdi+48h], 0
0x18000b8ca  test    rbx, rbx
0x18000b8cd  jz      short loc_18000B8E3
0x18000b8cf  call    cs:__imp_GetProcessHeap
0x18000b8d5  mov     rcx, rax; hHeap
0x18000b8d8  mov     r8, rbx; lpMem
0x18000b8db  xor     edx, edx; dwFlags
0x18000b8dd  call    cs:__imp_HeapFree
0x18000b8e3  mov     rcx, [rdi+28h]
0x18000b8e7  test    rcx, rcx
0x18000b8ea  jz      short loc_18000B91C
0x18000b8ec  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000b8f3  test    rax, rax
0x18000b8f6  jnz     short loc_18000B907
0x18000b8f8  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000b8ff  test    rdx, rdx
0x18000b902  jz      short loc_18000B91A
0x18000b904  mov     rax, rdx
0x18000b907  call    _guard_dispatch_icall
0x18000b90c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000b913  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000b91a  jmp     short loc_18000B92A
0x18000b91c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000b923  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000b92a  mov     rcx, [rdi+20h]
0x18000b92e  test    rcx, rcx
0x18000b931  jz      short loc_18000B946
0x18000b933  test    rax, rax
0x18000b936  jnz     short loc_18000B940
0x18000b938  test    rdx, rdx
0x18000b93b  jz      short loc_18000B946
0x18000b93d  mov     rax, rdx
0x18000b940  call    _guard_dispatch_icall
0x18000b945  nop
0x18000b946  mov     rbx, [rdi+10h]
0x18000b94a  test    rbx, rbx
0x18000b94d  jz      short loc_18000B978
0x18000b94f  xor     r9d, r9d; msWindowLength
0x18000b952  xor     r8d, r8d; msPeriod
0x18000b955  xor     edx, edx; pftDueTime
0x18000b957  mov     rcx, rbx; pti
0x18000b95a  call    cs:__imp_SetThreadpoolTimer
0x18000b960  mov     edx, 1; fCancelPendingCallbacks
0x18000b965  mov     rcx, rbx; pti
0x18000b968  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b96e  mov     rcx, rbx; pti
0x18000b971  call    cs:__imp_CloseThreadpoolTimer
0x18000b977  nop
0x18000b978  mov     rbx, [rsp+28h+arg_0]
0x18000b97d  mov     rsi, [rsp+28h+arg_8]
0x18000b982  add     rsp, 20h
0x18000b986  pop     rdi
0x18000b987  retn
```
