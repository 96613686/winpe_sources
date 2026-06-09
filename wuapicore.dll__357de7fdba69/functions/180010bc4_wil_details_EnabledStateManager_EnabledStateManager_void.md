# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180010bc4`
- end: `0x180010d1c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800a3ca0`

## callees

- `0x1800101b0`
- `0x180010bc4`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010c14`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010be2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010be2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c71`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c4c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c63`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c3e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010c0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010d05`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010c0c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010d05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010bf5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010cee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010bf5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010cee`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010c03`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010cfc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010c03`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010cfc`

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
0x180010bc4  mov     [rsp+arg_0], rbx
0x180010bc9  mov     [rsp+arg_8], rsi
0x180010bce  push    rdi
0x180010bcf  sub     rsp, 20h
0x180010bd3  mov     rdi, rcx
0x180010bd6  mov     byte ptr [rcx], 0
0x180010bd9  mov     rsi, [rcx+10h]
0x180010bdd  test    rsi, rsi
0x180010be0  jz      short loc_180010C1A
0x180010be2  call    cs:__imp_GetLastError
0x180010be8  mov     ebx, eax
0x180010bea  xor     r9d, r9d; msWindowLength
0x180010bed  xor     r8d, r8d; msPeriod
0x180010bf0  xor     edx, edx; pftDueTime
0x180010bf2  mov     rcx, rsi; pti
0x180010bf5  call    cs:__imp_SetThreadpoolTimer
0x180010bfb  mov     edx, 1; fCancelPendingCallbacks
0x180010c00  mov     rcx, rsi; pti
0x180010c03  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010c09  mov     rcx, rsi; pti
0x180010c0c  call    cs:__imp_CloseThreadpoolTimer
0x180010c12  mov     ecx, ebx; dwErrCode
0x180010c14  call    cs:__imp_SetLastError
0x180010c1a  mov     qword ptr [rdi+10h], 0
0x180010c22  mov     byte ptr [rdi], 0
0x180010c25  mov     rcx, rdi; this
0x180010c28  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x180010c2d  mov     rbx, [rdi+68h]
0x180010c31  mov     qword ptr [rdi+68h], 0
0x180010c39  test    rbx, rbx
0x180010c3c  jz      short loc_180010C52
0x180010c3e  call    cs:__imp_GetProcessHeap
0x180010c44  mov     rcx, rax; hHeap
0x180010c47  mov     r8, rbx; lpMem
0x180010c4a  xor     edx, edx; dwFlags
0x180010c4c  call    cs:__imp_HeapFree
0x180010c52  mov     rbx, [rdi+48h]
0x180010c56  mov     qword ptr [rdi+48h], 0
0x180010c5e  test    rbx, rbx
0x180010c61  jz      short loc_180010C77
0x180010c63  call    cs:__imp_GetProcessHeap
0x180010c69  mov     rcx, rax; hHeap
0x180010c6c  mov     r8, rbx; lpMem
0x180010c6f  xor     edx, edx; dwFlags
0x180010c71  call    cs:__imp_HeapFree
0x180010c77  mov     rcx, [rdi+28h]
0x180010c7b  test    rcx, rcx
0x180010c7e  jz      short loc_180010CB0
0x180010c80  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010c87  test    rax, rax
0x180010c8a  jnz     short loc_180010C9B
0x180010c8c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010c93  test    rdx, rdx
0x180010c96  jz      short loc_180010CAE
0x180010c98  mov     rax, rdx
0x180010c9b  call    _guard_dispatch_icall
0x180010ca0  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010ca7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010cae  jmp     short loc_180010CBE
0x180010cb0  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010cb7  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010cbe  mov     rcx, [rdi+20h]
0x180010cc2  test    rcx, rcx
0x180010cc5  jz      short loc_180010CDA
0x180010cc7  test    rax, rax
0x180010cca  jnz     short loc_180010CD4
0x180010ccc  test    rdx, rdx
0x180010ccf  jz      short loc_180010CDA
0x180010cd1  mov     rax, rdx
0x180010cd4  call    _guard_dispatch_icall
0x180010cd9  nop
0x180010cda  mov     rbx, [rdi+10h]
0x180010cde  test    rbx, rbx
0x180010ce1  jz      short loc_180010D0C
0x180010ce3  xor     r9d, r9d; msWindowLength
0x180010ce6  xor     r8d, r8d; msPeriod
0x180010ce9  xor     edx, edx; pftDueTime
0x180010ceb  mov     rcx, rbx; pti
0x180010cee  call    cs:__imp_SetThreadpoolTimer
0x180010cf4  mov     edx, 1; fCancelPendingCallbacks
0x180010cf9  mov     rcx, rbx; pti
0x180010cfc  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010d02  mov     rcx, rbx; pti
0x180010d05  call    cs:__imp_CloseThreadpoolTimer
0x180010d0b  nop
0x180010d0c  mov     rbx, [rsp+28h+arg_0]
0x180010d11  mov     rsi, [rsp+28h+arg_8]
0x180010d16  add     rsp, 20h
0x180010d1a  pop     rdi
0x180010d1b  retn
```
