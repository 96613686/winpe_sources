# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x14000d4cc`
- end: `0x14000d624`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400a6e00`

## callees

- `0x14000d4cc`
- `0x140014630`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x14000d5a9`
- `KERNEL32!GetProcessHeap` at `0x14000d5ce`
- `KERNEL32!GetProcessHeap` at `0x14000d5a9`
- `KERNEL32!GetProcessHeap` at `0x14000d5ce`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d500`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d5f6`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d500`
- `KERNEL32!SetThreadpoolTimer` at `0x14000d5f6`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d517`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d60d`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d517`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000d60d`
- `KERNEL32!GetLastError` at `0x14000d4ed`
- `KERNEL32!GetLastError` at `0x14000d4ed`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d50e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d604`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d50e`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000d604`
- `KERNEL32!SetLastError` at `0x14000d51f`
- `KERNEL32!SetLastError` at `0x14000d51f`
- `KERNEL32!HeapFree` at `0x14000d5b7`
- `KERNEL32!HeapFree` at `0x14000d5dc`
- `KERNEL32!HeapFree` at `0x14000d5b7`
- `KERNEL32!HeapFree` at `0x14000d5dc`

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
0x14000d4cc  mov     [rsp+arg_0], rbx
0x14000d4d1  mov     [rsp+arg_8], rsi
0x14000d4d6  push    rdi
0x14000d4d7  sub     rsp, 20h
0x14000d4db  mov     rdi, rcx
0x14000d4de  mov     dword ptr [rcx], 0
0x14000d4e4  mov     rsi, [rcx+10h]
0x14000d4e8  test    rsi, rsi
0x14000d4eb  jz      short loc_14000D525
0x14000d4ed  call    cs:__imp_GetLastError
0x14000d4f3  mov     ebx, eax
0x14000d4f5  xor     r9d, r9d; msWindowLength
0x14000d4f8  xor     r8d, r8d; msPeriod
0x14000d4fb  xor     edx, edx; pftDueTime
0x14000d4fd  mov     rcx, rsi; pti
0x14000d500  call    cs:__imp_SetThreadpoolTimer
0x14000d506  mov     edx, 1; fCancelPendingCallbacks
0x14000d50b  mov     rcx, rsi; pti
0x14000d50e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d514  mov     rcx, rsi; pti
0x14000d517  call    cs:__imp_CloseThreadpoolTimer
0x14000d51d  mov     ecx, ebx; dwErrCode
0x14000d51f  call    cs:__imp_SetLastError
0x14000d525  mov     qword ptr [rdi+10h], 0
0x14000d52d  mov     rcx, rdi; this
0x14000d530  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x14000d535  mov     rcx, [rdi+68h]
0x14000d539  test    rcx, rcx
0x14000d53c  jz      short loc_14000D56E
0x14000d53e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000d545  test    rax, rax
0x14000d548  jnz     short loc_14000D559
0x14000d54a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000d551  test    rdx, rdx
0x14000d554  jz      short loc_14000D56C
0x14000d556  mov     rax, rdx
0x14000d559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d55e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000d565  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000d56c  jmp     short loc_14000D57C
0x14000d56e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x14000d575  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x14000d57c  mov     rcx, [rdi+60h]
0x14000d580  test    rcx, rcx
0x14000d583  jz      short loc_14000D598
0x14000d585  test    rax, rax
0x14000d588  jnz     short loc_14000D592
0x14000d58a  test    rdx, rdx
0x14000d58d  jz      short loc_14000D598
0x14000d58f  mov     rax, rdx
0x14000d592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d597  nop
0x14000d598  mov     rbx, [rdi+58h]
0x14000d59c  mov     qword ptr [rdi+58h], 0
0x14000d5a4  test    rbx, rbx
0x14000d5a7  jz      short loc_14000D5BD
0x14000d5a9  call    cs:__imp_GetProcessHeap
0x14000d5af  mov     rcx, rax; hHeap
0x14000d5b2  mov     r8, rbx; lpMem
0x14000d5b5  xor     edx, edx; dwFlags
0x14000d5b7  call    cs:__imp_HeapFree
0x14000d5bd  mov     rbx, [rdi+38h]
0x14000d5c1  mov     qword ptr [rdi+38h], 0
0x14000d5c9  test    rbx, rbx
0x14000d5cc  jz      short loc_14000D5E2
0x14000d5ce  call    cs:__imp_GetProcessHeap
0x14000d5d4  mov     rcx, rax; hHeap
0x14000d5d7  mov     r8, rbx; lpMem
0x14000d5da  xor     edx, edx; dwFlags
0x14000d5dc  call    cs:__imp_HeapFree
0x14000d5e2  mov     rbx, [rdi+10h]
0x14000d5e6  test    rbx, rbx
0x14000d5e9  jz      short loc_14000D614
0x14000d5eb  xor     r9d, r9d; msWindowLength
0x14000d5ee  xor     r8d, r8d; msPeriod
0x14000d5f1  xor     edx, edx; pftDueTime
0x14000d5f3  mov     rcx, rbx; pti
0x14000d5f6  call    cs:__imp_SetThreadpoolTimer
0x14000d5fc  mov     edx, 1; fCancelPendingCallbacks
0x14000d601  mov     rcx, rbx; pti
0x14000d604  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000d60a  mov     rcx, rbx; pti
0x14000d60d  call    cs:__imp_CloseThreadpoolTimer
0x14000d613  nop
0x14000d614  mov     rbx, [rsp+28h+arg_0]
0x14000d619  mov     rsi, [rsp+28h+arg_8]
0x14000d61e  add     rsp, 20h
0x14000d622  pop     rdi
0x14000d623  retn
```
