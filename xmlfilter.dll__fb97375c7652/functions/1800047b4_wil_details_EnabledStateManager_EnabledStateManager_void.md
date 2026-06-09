# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800047b4`
- end: `0x18000490c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016040`

## callees

- `0x1800047b4`
- `0x180009914`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004807`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004807`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000489f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000489f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800048c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004891`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048b6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004891`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800048b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048de`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800047e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800047ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800048f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800047ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800048f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800047f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800048ec`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800047f6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800048ec`

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
0x1800047b4  mov     [rsp+arg_0], rbx
0x1800047b9  mov     [rsp+arg_8], rsi
0x1800047be  push    rdi
0x1800047bf  sub     rsp, 20h
0x1800047c3  mov     rdi, rcx
0x1800047c6  mov     dword ptr [rcx], 0
0x1800047cc  mov     rsi, [rcx+10h]
0x1800047d0  test    rsi, rsi
0x1800047d3  jz      short loc_18000480D
0x1800047d5  call    cs:__imp_GetLastError
0x1800047db  mov     ebx, eax
0x1800047dd  xor     r9d, r9d; msWindowLength
0x1800047e0  xor     r8d, r8d; msPeriod
0x1800047e3  xor     edx, edx; pftDueTime
0x1800047e5  mov     rcx, rsi; pti
0x1800047e8  call    cs:__imp_SetThreadpoolTimer
0x1800047ee  mov     edx, 1; fCancelPendingCallbacks
0x1800047f3  mov     rcx, rsi; pti
0x1800047f6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800047fc  mov     rcx, rsi; pti
0x1800047ff  call    cs:__imp_CloseThreadpoolTimer
0x180004805  mov     ecx, ebx; dwErrCode
0x180004807  call    cs:__imp_SetLastError
0x18000480d  mov     qword ptr [rdi+10h], 0
0x180004815  mov     rcx, rdi; this
0x180004818  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x18000481d  mov     rcx, [rdi+68h]
0x180004821  test    rcx, rcx
0x180004824  jz      short loc_180004856
0x180004826  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000482d  test    rax, rax
0x180004830  jnz     short loc_180004841
0x180004832  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004839  test    rdx, rdx
0x18000483c  jz      short loc_180004854
0x18000483e  mov     rax, rdx
0x180004841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004846  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000484d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004854  jmp     short loc_180004864
0x180004856  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000485d  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180004864  mov     rcx, [rdi+60h]
0x180004868  test    rcx, rcx
0x18000486b  jz      short loc_180004880
0x18000486d  test    rax, rax
0x180004870  jnz     short loc_18000487A
0x180004872  test    rdx, rdx
0x180004875  jz      short loc_180004880
0x180004877  mov     rax, rdx
0x18000487a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487f  nop
0x180004880  mov     rbx, [rdi+58h]
0x180004884  mov     qword ptr [rdi+58h], 0
0x18000488c  test    rbx, rbx
0x18000488f  jz      short loc_1800048A5
0x180004891  call    cs:__imp_GetProcessHeap
0x180004897  mov     rcx, rax; hHeap
0x18000489a  mov     r8, rbx; lpMem
0x18000489d  xor     edx, edx; dwFlags
0x18000489f  call    cs:__imp_HeapFree
0x1800048a5  mov     rbx, [rdi+38h]
0x1800048a9  mov     qword ptr [rdi+38h], 0
0x1800048b1  test    rbx, rbx
0x1800048b4  jz      short loc_1800048CA
0x1800048b6  call    cs:__imp_GetProcessHeap
0x1800048bc  mov     rcx, rax; hHeap
0x1800048bf  mov     r8, rbx; lpMem
0x1800048c2  xor     edx, edx; dwFlags
0x1800048c4  call    cs:__imp_HeapFree
0x1800048ca  mov     rbx, [rdi+10h]
0x1800048ce  test    rbx, rbx
0x1800048d1  jz      short loc_1800048FC
0x1800048d3  xor     r9d, r9d; msWindowLength
0x1800048d6  xor     r8d, r8d; msPeriod
0x1800048d9  xor     edx, edx; pftDueTime
0x1800048db  mov     rcx, rbx; pti
0x1800048de  call    cs:__imp_SetThreadpoolTimer
0x1800048e4  mov     edx, 1; fCancelPendingCallbacks
0x1800048e9  mov     rcx, rbx; pti
0x1800048ec  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800048f2  mov     rcx, rbx; pti
0x1800048f5  call    cs:__imp_CloseThreadpoolTimer
0x1800048fb  nop
0x1800048fc  mov     rbx, [rsp+28h+arg_0]
0x180004901  mov     rsi, [rsp+28h+arg_8]
0x180004906  add     rsp, 20h
0x18000490a  pop     rdi
0x18000490b  retn
```
