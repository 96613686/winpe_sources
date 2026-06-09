# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180014198`
- end: `0x1800142f0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18006f3b0`

## callees

- `0x180014198`
- `0x180016c7c`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014283`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014283`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001429a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014275`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001429a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800141b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800141eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800141eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800141da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800142d0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800141da`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800142d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800141e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800142d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800141e3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800142d9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800141cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800142c2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800141cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800142c2`

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
0x180014198  mov     [rsp+arg_0], rbx
0x18001419d  mov     [rsp+arg_8], rsi
0x1800141a2  push    rdi
0x1800141a3  sub     rsp, 20h
0x1800141a7  mov     rdi, rcx
0x1800141aa  mov     dword ptr [rcx], 0
0x1800141b0  mov     rsi, [rcx+10h]
0x1800141b4  test    rsi, rsi
0x1800141b7  jz      short loc_1800141F1
0x1800141b9  call    cs:__imp_GetLastError
0x1800141bf  mov     ebx, eax
0x1800141c1  xor     r9d, r9d; msWindowLength
0x1800141c4  xor     r8d, r8d; msPeriod
0x1800141c7  xor     edx, edx; pftDueTime
0x1800141c9  mov     rcx, rsi; pti
0x1800141cc  call    cs:__imp_SetThreadpoolTimer
0x1800141d2  mov     edx, 1; fCancelPendingCallbacks
0x1800141d7  mov     rcx, rsi; pti
0x1800141da  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800141e0  mov     rcx, rsi; pti
0x1800141e3  call    cs:__imp_CloseThreadpoolTimer
0x1800141e9  mov     ecx, ebx; dwErrCode
0x1800141eb  call    cs:__imp_SetLastError
0x1800141f1  mov     qword ptr [rdi+10h], 0
0x1800141f9  mov     rcx, rdi; this
0x1800141fc  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180014201  mov     rcx, [rdi+68h]
0x180014205  test    rcx, rcx
0x180014208  jz      short loc_18001423A
0x18001420a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180014211  test    rax, rax
0x180014214  jnz     short loc_180014225
0x180014216  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001421d  test    rdx, rdx
0x180014220  jz      short loc_180014238
0x180014222  mov     rax, rdx
0x180014225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001422a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180014231  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180014238  jmp     short loc_180014248
0x18001423a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180014241  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180014248  mov     rcx, [rdi+60h]
0x18001424c  test    rcx, rcx
0x18001424f  jz      short loc_180014264
0x180014251  test    rax, rax
0x180014254  jnz     short loc_18001425E
0x180014256  test    rdx, rdx
0x180014259  jz      short loc_180014264
0x18001425b  mov     rax, rdx
0x18001425e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014263  nop
0x180014264  mov     rbx, [rdi+58h]
0x180014268  mov     qword ptr [rdi+58h], 0
0x180014270  test    rbx, rbx
0x180014273  jz      short loc_180014289
0x180014275  call    cs:__imp_GetProcessHeap
0x18001427b  mov     rcx, rax; hHeap
0x18001427e  mov     r8, rbx; lpMem
0x180014281  xor     edx, edx; dwFlags
0x180014283  call    cs:__imp_HeapFree
0x180014289  mov     rbx, [rdi+38h]
0x18001428d  mov     qword ptr [rdi+38h], 0
0x180014295  test    rbx, rbx
0x180014298  jz      short loc_1800142AE
0x18001429a  call    cs:__imp_GetProcessHeap
0x1800142a0  mov     rcx, rax; hHeap
0x1800142a3  mov     r8, rbx; lpMem
0x1800142a6  xor     edx, edx; dwFlags
0x1800142a8  call    cs:__imp_HeapFree
0x1800142ae  mov     rbx, [rdi+10h]
0x1800142b2  test    rbx, rbx
0x1800142b5  jz      short loc_1800142E0
0x1800142b7  xor     r9d, r9d; msWindowLength
0x1800142ba  xor     r8d, r8d; msPeriod
0x1800142bd  xor     edx, edx; pftDueTime
0x1800142bf  mov     rcx, rbx; pti
0x1800142c2  call    cs:__imp_SetThreadpoolTimer
0x1800142c8  mov     edx, 1; fCancelPendingCallbacks
0x1800142cd  mov     rcx, rbx; pti
0x1800142d0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800142d6  mov     rcx, rbx; pti
0x1800142d9  call    cs:__imp_CloseThreadpoolTimer
0x1800142df  nop
0x1800142e0  mov     rbx, [rsp+28h+arg_0]
0x1800142e5  mov     rsi, [rsp+28h+arg_8]
0x1800142ea  add     rsp, 20h
0x1800142ee  pop     rdi
0x1800142ef  retn
```
