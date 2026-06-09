# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180010550`
- end: `0x1800106a8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800395d0`

## callees

- `0x180010550`
- `0x180010738`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800105a0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800105a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001056e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001056e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105d8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800105fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800105ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010598`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010691`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010598`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010691`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001058f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010688`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001058f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010688`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010581`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001067a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010581`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001067a`

## pseudocode

```c
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
0x180010550  mov     [rsp+arg_0], rbx
0x180010555  mov     [rsp+arg_8], rsi
0x18001055a  push    rdi
0x18001055b  sub     rsp, 20h
0x18001055f  mov     rdi, rcx
0x180010562  mov     byte ptr [rcx], 0
0x180010565  mov     rsi, [rcx+10h]
0x180010569  test    rsi, rsi
0x18001056c  jz      short loc_1800105A6
0x18001056e  call    cs:__imp_GetLastError
0x180010574  mov     ebx, eax
0x180010576  xor     r9d, r9d; msWindowLength
0x180010579  xor     r8d, r8d; msPeriod
0x18001057c  xor     edx, edx; pftDueTime
0x18001057e  mov     rcx, rsi; pti
0x180010581  call    cs:__imp_SetThreadpoolTimer
0x180010587  mov     edx, 1; fCancelPendingCallbacks
0x18001058c  mov     rcx, rsi; pti
0x18001058f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010595  mov     rcx, rsi; pti
0x180010598  call    cs:__imp_CloseThreadpoolTimer
0x18001059e  mov     ecx, ebx; dwErrCode
0x1800105a0  call    cs:__imp_SetLastError
0x1800105a6  mov     qword ptr [rdi+10h], 0
0x1800105ae  mov     byte ptr [rdi], 0
0x1800105b1  mov     rcx, rdi; this
0x1800105b4  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x1800105b9  mov     rbx, [rdi+68h]
0x1800105bd  mov     qword ptr [rdi+68h], 0
0x1800105c5  test    rbx, rbx
0x1800105c8  jz      short loc_1800105DE
0x1800105ca  call    cs:__imp_GetProcessHeap
0x1800105d0  mov     rcx, rax; hHeap
0x1800105d3  mov     r8, rbx; lpMem
0x1800105d6  xor     edx, edx; dwFlags
0x1800105d8  call    cs:__imp_HeapFree
0x1800105de  mov     rbx, [rdi+48h]
0x1800105e2  mov     qword ptr [rdi+48h], 0
0x1800105ea  test    rbx, rbx
0x1800105ed  jz      short loc_180010603
0x1800105ef  call    cs:__imp_GetProcessHeap
0x1800105f5  mov     rcx, rax; hHeap
0x1800105f8  mov     r8, rbx; lpMem
0x1800105fb  xor     edx, edx; dwFlags
0x1800105fd  call    cs:__imp_HeapFree
0x180010603  mov     rcx, [rdi+28h]
0x180010607  test    rcx, rcx
0x18001060a  jz      short loc_18001063C
0x18001060c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010613  test    rax, rax
0x180010616  jnz     short loc_180010627
0x180010618  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001061f  test    rdx, rdx
0x180010622  jz      short loc_18001063A
0x180010624  mov     rax, rdx
0x180010627  call    _guard_dispatch_icall
0x18001062c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180010633  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18001063a  jmp     short loc_18001064A
0x18001063c  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180010643  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18001064a  mov     rcx, [rdi+20h]
0x18001064e  test    rcx, rcx
0x180010651  jz      short loc_180010666
0x180010653  test    rax, rax
0x180010656  jnz     short loc_180010660
0x180010658  test    rdx, rdx
0x18001065b  jz      short loc_180010666
0x18001065d  mov     rax, rdx
0x180010660  call    _guard_dispatch_icall
0x180010665  nop
0x180010666  mov     rbx, [rdi+10h]
0x18001066a  test    rbx, rbx
0x18001066d  jz      short loc_180010698
0x18001066f  xor     r9d, r9d; msWindowLength
0x180010672  xor     r8d, r8d; msPeriod
0x180010675  xor     edx, edx; pftDueTime
0x180010677  mov     rcx, rbx; pti
0x18001067a  call    cs:__imp_SetThreadpoolTimer
0x180010680  mov     edx, 1; fCancelPendingCallbacks
0x180010685  mov     rcx, rbx; pti
0x180010688  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001068e  mov     rcx, rbx; pti
0x180010691  call    cs:__imp_CloseThreadpoolTimer
0x180010697  nop
0x180010698  mov     rbx, [rsp+28h+arg_0]
0x18001069d  mov     rsi, [rsp+28h+arg_8]
0x1800106a2  add     rsp, 20h
0x1800106a6  pop     rdi
0x1800106a7  retn
```
