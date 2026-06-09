# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140004e48`
- end: `0x140004f8e`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140014b70`

## callees

- `0x140004e48`
- `0x140008b44`
- `0x140015010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004f22`
- `KERNEL32!HeapFree` at `0x140004f47`
- `KERNEL32!HeapFree` at `0x140004f22`
- `KERNEL32!HeapFree` at `0x140004f47`
- `KERNEL32!SetThreadpoolTimer` at `0x140004e7c`
- `KERNEL32!SetThreadpoolTimer` at `0x140004f61`
- `KERNEL32!SetThreadpoolTimer` at `0x140004e7c`
- `KERNEL32!SetThreadpoolTimer` at `0x140004f61`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004e8a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004f6f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004e8a`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140004f6f`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004e93`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004f78`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004e93`
- `KERNEL32!CloseThreadpoolTimer` at `0x140004f78`
- `KERNEL32!GetLastError` at `0x140004e69`
- `KERNEL32!GetLastError` at `0x140004e69`
- `KERNEL32!SetLastError` at `0x140004e9b`
- `KERNEL32!SetLastError` at `0x140004e9b`
- `KERNEL32!GetProcessHeap` at `0x140004f14`
- `KERNEL32!GetProcessHeap` at `0x140004f39`
- `KERNEL32!GetProcessHeap` at `0x140004f14`
- `KERNEL32!GetProcessHeap` at `0x140004f39`

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
0x140004e48  mov     [rsp+arg_0], rbx
0x140004e4d  mov     [rsp+arg_8], rsi
0x140004e52  push    rdi
0x140004e53  sub     rsp, 20h
0x140004e57  mov     dword ptr [rcx], 0
0x140004e5d  mov     rdi, rcx
0x140004e60  mov     rsi, [rcx+10h]
0x140004e64  test    rsi, rsi
0x140004e67  jz      short loc_140004EA1
0x140004e69  call    cs:__imp_GetLastError
0x140004e6f  xor     r9d, r9d; msWindowLength
0x140004e72  xor     r8d, r8d; msPeriod
0x140004e75  xor     edx, edx; pftDueTime
0x140004e77  mov     rcx, rsi; pti
0x140004e7a  mov     ebx, eax
0x140004e7c  call    cs:__imp_SetThreadpoolTimer
0x140004e82  mov     edx, 1; fCancelPendingCallbacks
0x140004e87  mov     rcx, rsi; pti
0x140004e8a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004e90  mov     rcx, rsi; pti
0x140004e93  call    cs:__imp_CloseThreadpoolTimer
0x140004e99  mov     ecx, ebx; dwErrCode
0x140004e9b  call    cs:__imp_SetLastError
0x140004ea1  mov     rcx, rdi; this
0x140004ea4  mov     qword ptr [rdi+10h], 0
0x140004eac  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140004eb1  mov     rcx, [rdi+68h]
0x140004eb5  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004ebc  test    rcx, rcx
0x140004ebf  jz      short loc_140004EE1
0x140004ec1  test    rax, rax
0x140004ec4  jnz     short loc_140004ED5
0x140004ec6  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004ecd  test    rdx, rdx
0x140004ed0  jz      short loc_140004EE8
0x140004ed2  mov     rax, rdx
0x140004ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004eda  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140004ee1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140004ee8  mov     rcx, [rdi+60h]
0x140004eec  test    rcx, rcx
0x140004eef  jz      short loc_140004F03
0x140004ef1  test    rax, rax
0x140004ef4  jnz     short loc_140004EFE
0x140004ef6  test    rdx, rdx
0x140004ef9  jz      short loc_140004F03
0x140004efb  mov     rax, rdx
0x140004efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f03  mov     rbx, [rdi+58h]
0x140004f07  mov     qword ptr [rdi+58h], 0
0x140004f0f  test    rbx, rbx
0x140004f12  jz      short loc_140004F28
0x140004f14  call    cs:__imp_GetProcessHeap
0x140004f1a  mov     r8, rbx; lpMem
0x140004f1d  xor     edx, edx; dwFlags
0x140004f1f  mov     rcx, rax; hHeap
0x140004f22  call    cs:__imp_HeapFree
0x140004f28  mov     rbx, [rdi+38h]
0x140004f2c  mov     qword ptr [rdi+38h], 0
0x140004f34  test    rbx, rbx
0x140004f37  jz      short loc_140004F4D
0x140004f39  call    cs:__imp_GetProcessHeap
0x140004f3f  mov     r8, rbx; lpMem
0x140004f42  xor     edx, edx; dwFlags
0x140004f44  mov     rcx, rax; hHeap
0x140004f47  call    cs:__imp_HeapFree
0x140004f4d  mov     rbx, [rdi+10h]
0x140004f51  test    rbx, rbx
0x140004f54  jz      short loc_140004F7E
0x140004f56  xor     r9d, r9d; msWindowLength
0x140004f59  xor     r8d, r8d; msPeriod
0x140004f5c  xor     edx, edx; pftDueTime
0x140004f5e  mov     rcx, rbx; pti
0x140004f61  call    cs:__imp_SetThreadpoolTimer
0x140004f67  mov     edx, 1; fCancelPendingCallbacks
0x140004f6c  mov     rcx, rbx; pti
0x140004f6f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004f75  mov     rcx, rbx; pti
0x140004f78  call    cs:__imp_CloseThreadpoolTimer
0x140004f7e  mov     rbx, [rsp+28h+arg_0]
0x140004f83  mov     rsi, [rsp+28h+arg_8]
0x140004f88  add     rsp, 20h
0x140004f8c  pop     rdi
0x140004f8d  retn
```
