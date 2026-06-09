# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140008c78`
- end: `0x140008dbe`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140015760`

## callees

- `0x140008c78`
- `0x14000a0bc`
- `0x140016010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008d52`
- `KERNEL32!HeapFree` at `0x140008d77`
- `KERNEL32!HeapFree` at `0x140008d52`
- `KERNEL32!HeapFree` at `0x140008d77`
- `KERNEL32!SetLastError` at `0x140008ccb`
- `KERNEL32!SetLastError` at `0x140008ccb`
- `KERNEL32!GetLastError` at `0x140008c99`
- `KERNEL32!GetLastError` at `0x140008c99`
- `KERNEL32!GetProcessHeap` at `0x140008d44`
- `KERNEL32!GetProcessHeap` at `0x140008d69`
- `KERNEL32!GetProcessHeap` at `0x140008d44`
- `KERNEL32!GetProcessHeap` at `0x140008d69`
- `KERNEL32!SetThreadpoolTimer` at `0x140008cac`
- `KERNEL32!SetThreadpoolTimer` at `0x140008d91`
- `KERNEL32!SetThreadpoolTimer` at `0x140008cac`
- `KERNEL32!SetThreadpoolTimer` at `0x140008d91`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008cc3`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008da8`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008cc3`
- `KERNEL32!CloseThreadpoolTimer` at `0x140008da8`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008cba`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008d9f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008cba`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140008d9f`

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
0x140008c78  mov     [rsp+arg_0], rbx
0x140008c7d  mov     [rsp+arg_8], rsi
0x140008c82  push    rdi
0x140008c83  sub     rsp, 20h
0x140008c87  mov     dword ptr [rcx], 0
0x140008c8d  mov     rdi, rcx
0x140008c90  mov     rsi, [rcx+10h]
0x140008c94  test    rsi, rsi
0x140008c97  jz      short loc_140008CD1
0x140008c99  call    cs:__imp_GetLastError
0x140008c9f  xor     r9d, r9d; msWindowLength
0x140008ca2  xor     r8d, r8d; msPeriod
0x140008ca5  xor     edx, edx; pftDueTime
0x140008ca7  mov     rcx, rsi; pti
0x140008caa  mov     ebx, eax
0x140008cac  call    cs:__imp_SetThreadpoolTimer
0x140008cb2  mov     edx, 1; fCancelPendingCallbacks
0x140008cb7  mov     rcx, rsi; pti
0x140008cba  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008cc0  mov     rcx, rsi; pti
0x140008cc3  call    cs:__imp_CloseThreadpoolTimer
0x140008cc9  mov     ecx, ebx; dwErrCode
0x140008ccb  call    cs:__imp_SetLastError
0x140008cd1  mov     rcx, rdi; this
0x140008cd4  mov     qword ptr [rdi+10h], 0
0x140008cdc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140008ce1  mov     rcx, [rdi+68h]
0x140008ce5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140008cec  test    rcx, rcx
0x140008cef  jz      short loc_140008D11
0x140008cf1  test    rax, rax
0x140008cf4  jnz     short loc_140008D05
0x140008cf6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140008cfd  test    rdx, rdx
0x140008d00  jz      short loc_140008D18
0x140008d02  mov     rax, rdx
0x140008d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d0a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140008d11  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140008d18  mov     rcx, [rdi+60h]
0x140008d1c  test    rcx, rcx
0x140008d1f  jz      short loc_140008D33
0x140008d21  test    rax, rax
0x140008d24  jnz     short loc_140008D2E
0x140008d26  test    rdx, rdx
0x140008d29  jz      short loc_140008D33
0x140008d2b  mov     rax, rdx
0x140008d2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d33  mov     rbx, [rdi+58h]
0x140008d37  mov     qword ptr [rdi+58h], 0
0x140008d3f  test    rbx, rbx
0x140008d42  jz      short loc_140008D58
0x140008d44  call    cs:__imp_GetProcessHeap
0x140008d4a  mov     r8, rbx; lpMem
0x140008d4d  xor     edx, edx; dwFlags
0x140008d4f  mov     rcx, rax; hHeap
0x140008d52  call    cs:__imp_HeapFree
0x140008d58  mov     rbx, [rdi+38h]
0x140008d5c  mov     qword ptr [rdi+38h], 0
0x140008d64  test    rbx, rbx
0x140008d67  jz      short loc_140008D7D
0x140008d69  call    cs:__imp_GetProcessHeap
0x140008d6f  mov     r8, rbx; lpMem
0x140008d72  xor     edx, edx; dwFlags
0x140008d74  mov     rcx, rax; hHeap
0x140008d77  call    cs:__imp_HeapFree
0x140008d7d  mov     rbx, [rdi+10h]
0x140008d81  test    rbx, rbx
0x140008d84  jz      short loc_140008DAE
0x140008d86  xor     r9d, r9d; msWindowLength
0x140008d89  xor     r8d, r8d; msPeriod
0x140008d8c  xor     edx, edx; pftDueTime
0x140008d8e  mov     rcx, rbx; pti
0x140008d91  call    cs:__imp_SetThreadpoolTimer
0x140008d97  mov     edx, 1; fCancelPendingCallbacks
0x140008d9c  mov     rcx, rbx; pti
0x140008d9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140008da5  mov     rcx, rbx; pti
0x140008da8  call    cs:__imp_CloseThreadpoolTimer
0x140008dae  mov     rbx, [rsp+28h+arg_0]
0x140008db3  mov     rsi, [rsp+28h+arg_8]
0x140008db8  add     rsp, 20h
0x140008dbc  pop     rdi
0x140008dbd  retn
```
