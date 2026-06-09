# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000bfdc`
- end: `0x18000c134`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180028380`

## callees

- `0x18000bfdc`
- `0x18000d0f0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c0ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c0de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bffd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c02f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c02f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c027`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c11d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c027`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c11d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c010`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c106`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c010`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c106`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c01e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c114`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c01e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c114`

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
0x18000bfdc  mov     [rsp+arg_0], rbx
0x18000bfe1  mov     [rsp+arg_8], rsi
0x18000bfe6  push    rdi
0x18000bfe7  sub     rsp, 20h
0x18000bfeb  mov     rdi, rcx
0x18000bfee  mov     dword ptr [rcx], 0
0x18000bff4  mov     rsi, [rcx+10h]
0x18000bff8  test    rsi, rsi
0x18000bffb  jz      short loc_18000C035
0x18000bffd  call    cs:__imp_GetLastError
0x18000c003  mov     ebx, eax
0x18000c005  xor     r9d, r9d; msWindowLength
0x18000c008  xor     r8d, r8d; msPeriod
0x18000c00b  xor     edx, edx; pftDueTime
0x18000c00d  mov     rcx, rsi; pti
0x18000c010  call    cs:__imp_SetThreadpoolTimer
0x18000c016  mov     edx, 1; fCancelPendingCallbacks
0x18000c01b  mov     rcx, rsi; pti
0x18000c01e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c024  mov     rcx, rsi; pti
0x18000c027  call    cs:__imp_CloseThreadpoolTimer
0x18000c02d  mov     ecx, ebx; dwErrCode
0x18000c02f  call    cs:__imp_SetLastError
0x18000c035  mov     qword ptr [rdi+10h], 0
0x18000c03d  mov     rcx, rdi; this
0x18000c040  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000c045  mov     rcx, [rdi+68h]
0x18000c049  test    rcx, rcx
0x18000c04c  jz      short loc_18000C07E
0x18000c04e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c055  test    rax, rax
0x18000c058  jnz     short loc_18000C069
0x18000c05a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c061  test    rdx, rdx
0x18000c064  jz      short loc_18000C07C
0x18000c066  mov     rax, rdx
0x18000c069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c06e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c075  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c07c  jmp     short loc_18000C08C
0x18000c07e  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000c085  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000c08c  mov     rcx, [rdi+60h]
0x18000c090  test    rcx, rcx
0x18000c093  jz      short loc_18000C0A8
0x18000c095  test    rax, rax
0x18000c098  jnz     short loc_18000C0A2
0x18000c09a  test    rdx, rdx
0x18000c09d  jz      short loc_18000C0A8
0x18000c09f  mov     rax, rdx
0x18000c0a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0a7  nop
0x18000c0a8  mov     rbx, [rdi+58h]
0x18000c0ac  mov     qword ptr [rdi+58h], 0
0x18000c0b4  test    rbx, rbx
0x18000c0b7  jz      short loc_18000C0CD
0x18000c0b9  call    cs:__imp_GetProcessHeap
0x18000c0bf  mov     rcx, rax; hHeap
0x18000c0c2  mov     r8, rbx; lpMem
0x18000c0c5  xor     edx, edx; dwFlags
0x18000c0c7  call    cs:__imp_HeapFree
0x18000c0cd  mov     rbx, [rdi+38h]
0x18000c0d1  mov     qword ptr [rdi+38h], 0
0x18000c0d9  test    rbx, rbx
0x18000c0dc  jz      short loc_18000C0F2
0x18000c0de  call    cs:__imp_GetProcessHeap
0x18000c0e4  mov     rcx, rax; hHeap
0x18000c0e7  mov     r8, rbx; lpMem
0x18000c0ea  xor     edx, edx; dwFlags
0x18000c0ec  call    cs:__imp_HeapFree
0x18000c0f2  mov     rbx, [rdi+10h]
0x18000c0f6  test    rbx, rbx
0x18000c0f9  jz      short loc_18000C124
0x18000c0fb  xor     r9d, r9d; msWindowLength
0x18000c0fe  xor     r8d, r8d; msPeriod
0x18000c101  xor     edx, edx; pftDueTime
0x18000c103  mov     rcx, rbx; pti
0x18000c106  call    cs:__imp_SetThreadpoolTimer
0x18000c10c  mov     edx, 1; fCancelPendingCallbacks
0x18000c111  mov     rcx, rbx; pti
0x18000c114  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c11a  mov     rcx, rbx; pti
0x18000c11d  call    cs:__imp_CloseThreadpoolTimer
0x18000c123  nop
0x18000c124  mov     rbx, [rsp+28h+arg_0]
0x18000c129  mov     rsi, [rsp+28h+arg_8]
0x18000c12e  add     rsp, 20h
0x18000c132  pop     rdi
0x18000c133  retn
```
