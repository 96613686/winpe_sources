# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800179e0`
- end: `0x180017b38`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180080140`

## callees

- `0x1800179e0`
- `0x18003da5c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017a33`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180017a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017a01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017acb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017af0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017acb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017af0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017abd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ae2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017abd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017ae2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017a2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017b21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017a2b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180017b21`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017a22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017b18`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017a22`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180017b18`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017a14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017b0a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017a14`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180017b0a`

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
0x1800179e0  mov     [rsp+arg_0], rbx
0x1800179e5  mov     [rsp+arg_8], rsi
0x1800179ea  push    rdi
0x1800179eb  sub     rsp, 20h
0x1800179ef  mov     rdi, rcx
0x1800179f2  mov     dword ptr [rcx], 0
0x1800179f8  mov     rsi, [rcx+10h]
0x1800179fc  test    rsi, rsi
0x1800179ff  jz      short loc_180017A39
0x180017a01  call    cs:__imp_GetLastError
0x180017a07  mov     ebx, eax
0x180017a09  xor     r9d, r9d; msWindowLength
0x180017a0c  xor     r8d, r8d; msPeriod
0x180017a0f  xor     edx, edx; pftDueTime
0x180017a11  mov     rcx, rsi; pti
0x180017a14  call    cs:__imp_SetThreadpoolTimer
0x180017a1a  mov     edx, 1; fCancelPendingCallbacks
0x180017a1f  mov     rcx, rsi; pti
0x180017a22  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017a28  mov     rcx, rsi; pti
0x180017a2b  call    cs:__imp_CloseThreadpoolTimer
0x180017a31  mov     ecx, ebx; dwErrCode
0x180017a33  call    cs:__imp_SetLastError
0x180017a39  mov     qword ptr [rdi+10h], 0
0x180017a41  mov     rcx, rdi; this
0x180017a44  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180017a49  mov     rcx, [rdi+68h]
0x180017a4d  test    rcx, rcx
0x180017a50  jz      short loc_180017A82
0x180017a52  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180017a59  test    rax, rax
0x180017a5c  jnz     short loc_180017A6D
0x180017a5e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180017a65  test    rdx, rdx
0x180017a68  jz      short loc_180017A80
0x180017a6a  mov     rax, rdx
0x180017a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a72  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180017a79  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180017a80  jmp     short loc_180017A90
0x180017a82  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180017a89  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180017a90  mov     rcx, [rdi+60h]
0x180017a94  test    rcx, rcx
0x180017a97  jz      short loc_180017AAC
0x180017a99  test    rax, rax
0x180017a9c  jnz     short loc_180017AA6
0x180017a9e  test    rdx, rdx
0x180017aa1  jz      short loc_180017AAC
0x180017aa3  mov     rax, rdx
0x180017aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017aab  nop
0x180017aac  mov     rbx, [rdi+58h]
0x180017ab0  mov     qword ptr [rdi+58h], 0
0x180017ab8  test    rbx, rbx
0x180017abb  jz      short loc_180017AD1
0x180017abd  call    cs:__imp_GetProcessHeap
0x180017ac3  mov     rcx, rax; hHeap
0x180017ac6  mov     r8, rbx; lpMem
0x180017ac9  xor     edx, edx; dwFlags
0x180017acb  call    cs:__imp_HeapFree
0x180017ad1  mov     rbx, [rdi+38h]
0x180017ad5  mov     qword ptr [rdi+38h], 0
0x180017add  test    rbx, rbx
0x180017ae0  jz      short loc_180017AF6
0x180017ae2  call    cs:__imp_GetProcessHeap
0x180017ae8  mov     rcx, rax; hHeap
0x180017aeb  mov     r8, rbx; lpMem
0x180017aee  xor     edx, edx; dwFlags
0x180017af0  call    cs:__imp_HeapFree
0x180017af6  mov     rbx, [rdi+10h]
0x180017afa  test    rbx, rbx
0x180017afd  jz      short loc_180017B28
0x180017aff  xor     r9d, r9d; msWindowLength
0x180017b02  xor     r8d, r8d; msPeriod
0x180017b05  xor     edx, edx; pftDueTime
0x180017b07  mov     rcx, rbx; pti
0x180017b0a  call    cs:__imp_SetThreadpoolTimer
0x180017b10  mov     edx, 1; fCancelPendingCallbacks
0x180017b15  mov     rcx, rbx; pti
0x180017b18  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017b1e  mov     rcx, rbx; pti
0x180017b21  call    cs:__imp_CloseThreadpoolTimer
0x180017b27  nop
0x180017b28  mov     rbx, [rsp+28h+arg_0]
0x180017b2d  mov     rsi, [rsp+28h+arg_8]
0x180017b32  add     rsp, 20h
0x180017b36  pop     rdi
0x180017b37  retn
```
