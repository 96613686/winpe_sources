# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180004e08`
- end: `0x180004f60`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000e6a0`

## callees

- `0x180004e08`
- `0x180008474`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ef3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f18`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ef3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ee5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ee5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f0a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004e5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e29`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004e53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004f49`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004e53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004f49`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004e4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004f40`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004e4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004f40`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004e3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004f32`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004e3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004f32`

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
0x180004e08  mov     [rsp+arg_0], rbx
0x180004e0d  mov     [rsp+arg_8], rsi
0x180004e12  push    rdi
0x180004e13  sub     rsp, 20h
0x180004e17  mov     rdi, rcx
0x180004e1a  mov     dword ptr [rcx], 0
0x180004e20  mov     rsi, [rcx+10h]
0x180004e24  test    rsi, rsi
0x180004e27  jz      short loc_180004E61
0x180004e29  call    cs:__imp_GetLastError
0x180004e2f  mov     ebx, eax
0x180004e31  xor     r9d, r9d; msWindowLength
0x180004e34  xor     r8d, r8d; msPeriod
0x180004e37  xor     edx, edx; pftDueTime
0x180004e39  mov     rcx, rsi; pti
0x180004e3c  call    cs:__imp_SetThreadpoolTimer
0x180004e42  mov     edx, 1; fCancelPendingCallbacks
0x180004e47  mov     rcx, rsi; pti
0x180004e4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004e50  mov     rcx, rsi; pti
0x180004e53  call    cs:__imp_CloseThreadpoolTimer
0x180004e59  mov     ecx, ebx; dwErrCode
0x180004e5b  call    cs:__imp_SetLastError
0x180004e61  mov     qword ptr [rdi+10h], 0
0x180004e69  mov     rcx, rdi; this
0x180004e6c  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180004e71  mov     rcx, [rdi+68h]
0x180004e75  test    rcx, rcx
0x180004e78  jz      short loc_180004EAA
0x180004e7a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004e81  test    rax, rax
0x180004e84  jnz     short loc_180004E95
0x180004e86  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004e8d  test    rdx, rdx
0x180004e90  jz      short loc_180004EA8
0x180004e92  mov     rax, rdx
0x180004e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e9a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004ea1  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004ea8  jmp     short loc_180004EB8
0x180004eaa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004eb1  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004eb8  mov     rcx, [rdi+60h]
0x180004ebc  test    rcx, rcx
0x180004ebf  jz      short loc_180004ED4
0x180004ec1  test    rax, rax
0x180004ec4  jnz     short loc_180004ECE
0x180004ec6  test    rdx, rdx
0x180004ec9  jz      short loc_180004ED4
0x180004ecb  mov     rax, rdx
0x180004ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed3  nop
0x180004ed4  mov     rbx, [rdi+58h]
0x180004ed8  mov     qword ptr [rdi+58h], 0
0x180004ee0  test    rbx, rbx
0x180004ee3  jz      short loc_180004EF9
0x180004ee5  call    cs:__imp_GetProcessHeap
0x180004eeb  mov     rcx, rax; hHeap
0x180004eee  mov     r8, rbx; lpMem
0x180004ef1  xor     edx, edx; dwFlags
0x180004ef3  call    cs:__imp_HeapFree
0x180004ef9  mov     rbx, [rdi+38h]
0x180004efd  mov     qword ptr [rdi+38h], 0
0x180004f05  test    rbx, rbx
0x180004f08  jz      short loc_180004F1E
0x180004f0a  call    cs:__imp_GetProcessHeap
0x180004f10  mov     rcx, rax; hHeap
0x180004f13  mov     r8, rbx; lpMem
0x180004f16  xor     edx, edx; dwFlags
0x180004f18  call    cs:__imp_HeapFree
0x180004f1e  mov     rbx, [rdi+10h]
0x180004f22  test    rbx, rbx
0x180004f25  jz      short loc_180004F50
0x180004f27  xor     r9d, r9d; msWindowLength
0x180004f2a  xor     r8d, r8d; msPeriod
0x180004f2d  xor     edx, edx; pftDueTime
0x180004f2f  mov     rcx, rbx; pti
0x180004f32  call    cs:__imp_SetThreadpoolTimer
0x180004f38  mov     edx, 1; fCancelPendingCallbacks
0x180004f3d  mov     rcx, rbx; pti
0x180004f40  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004f46  mov     rcx, rbx; pti
0x180004f49  call    cs:__imp_CloseThreadpoolTimer
0x180004f4f  nop
0x180004f50  mov     rbx, [rsp+28h+arg_0]
0x180004f55  mov     rsi, [rsp+28h+arg_8]
0x180004f5a  add     rsp, 20h
0x180004f5e  pop     rdi
0x180004f5f  retn
```
