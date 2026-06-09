# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000499c`
- end: `0x180004af4`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180032730`

## callees

- `0x18000499c`
- `0x18000725c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a79`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004a9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004aac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004a87`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004aac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800049ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004add`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800049e7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004add`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004ac6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049d0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004ac6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004ad4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049de`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004ad4`

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
0x18000499c  mov     [rsp+arg_0], rbx
0x1800049a1  mov     [rsp+arg_8], rsi
0x1800049a6  push    rdi
0x1800049a7  sub     rsp, 20h
0x1800049ab  mov     rdi, rcx
0x1800049ae  mov     dword ptr [rcx], 0
0x1800049b4  mov     rsi, [rcx+10h]
0x1800049b8  test    rsi, rsi
0x1800049bb  jz      short loc_1800049F5
0x1800049bd  call    cs:__imp_GetLastError
0x1800049c3  mov     ebx, eax
0x1800049c5  xor     r9d, r9d; msWindowLength
0x1800049c8  xor     r8d, r8d; msPeriod
0x1800049cb  xor     edx, edx; pftDueTime
0x1800049cd  mov     rcx, rsi; pti
0x1800049d0  call    cs:__imp_SetThreadpoolTimer
0x1800049d6  mov     edx, 1; fCancelPendingCallbacks
0x1800049db  mov     rcx, rsi; pti
0x1800049de  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800049e4  mov     rcx, rsi; pti
0x1800049e7  call    cs:__imp_CloseThreadpoolTimer
0x1800049ed  mov     ecx, ebx; dwErrCode
0x1800049ef  call    cs:__imp_SetLastError
0x1800049f5  mov     qword ptr [rdi+10h], 0
0x1800049fd  mov     rcx, rdi; this
0x180004a00  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180004a05  mov     rcx, [rdi+68h]
0x180004a09  test    rcx, rcx
0x180004a0c  jz      short loc_180004A3E
0x180004a0e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004a15  test    rax, rax
0x180004a18  jnz     short loc_180004A29
0x180004a1a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004a21  test    rdx, rdx
0x180004a24  jz      short loc_180004A3C
0x180004a26  mov     rax, rdx
0x180004a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a2e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004a35  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004a3c  jmp     short loc_180004A4C
0x180004a3e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004a45  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004a4c  mov     rcx, [rdi+60h]
0x180004a50  test    rcx, rcx
0x180004a53  jz      short loc_180004A68
0x180004a55  test    rax, rax
0x180004a58  jnz     short loc_180004A62
0x180004a5a  test    rdx, rdx
0x180004a5d  jz      short loc_180004A68
0x180004a5f  mov     rax, rdx
0x180004a62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a67  nop
0x180004a68  mov     rbx, [rdi+58h]
0x180004a6c  mov     qword ptr [rdi+58h], 0
0x180004a74  test    rbx, rbx
0x180004a77  jz      short loc_180004A8D
0x180004a79  call    cs:__imp_GetProcessHeap
0x180004a7f  mov     rcx, rax; hHeap
0x180004a82  mov     r8, rbx; lpMem
0x180004a85  xor     edx, edx; dwFlags
0x180004a87  call    cs:__imp_HeapFree
0x180004a8d  mov     rbx, [rdi+38h]
0x180004a91  mov     qword ptr [rdi+38h], 0
0x180004a99  test    rbx, rbx
0x180004a9c  jz      short loc_180004AB2
0x180004a9e  call    cs:__imp_GetProcessHeap
0x180004aa4  mov     rcx, rax; hHeap
0x180004aa7  mov     r8, rbx; lpMem
0x180004aaa  xor     edx, edx; dwFlags
0x180004aac  call    cs:__imp_HeapFree
0x180004ab2  mov     rbx, [rdi+10h]
0x180004ab6  test    rbx, rbx
0x180004ab9  jz      short loc_180004AE4
0x180004abb  xor     r9d, r9d; msWindowLength
0x180004abe  xor     r8d, r8d; msPeriod
0x180004ac1  xor     edx, edx; pftDueTime
0x180004ac3  mov     rcx, rbx; pti
0x180004ac6  call    cs:__imp_SetThreadpoolTimer
0x180004acc  mov     edx, 1; fCancelPendingCallbacks
0x180004ad1  mov     rcx, rbx; pti
0x180004ad4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004ada  mov     rcx, rbx; pti
0x180004add  call    cs:__imp_CloseThreadpoolTimer
0x180004ae3  nop
0x180004ae4  mov     rbx, [rsp+28h+arg_0]
0x180004ae9  mov     rsi, [rsp+28h+arg_8]
0x180004aee  add     rsp, 20h
0x180004af2  pop     rdi
0x180004af3  retn
```
