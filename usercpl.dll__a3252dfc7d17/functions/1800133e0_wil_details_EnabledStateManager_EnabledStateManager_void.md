# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800133e0`
- end: `0x180013526`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800777f0`

## callees

- `0x1800133e0`
- `0x180016964`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800134ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800134df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800134ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800134df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800134ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800134d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800134ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800134d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013401`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013401`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013433`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013433`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013422`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013507`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013422`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180013507`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013414`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800134f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180013414`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800134f9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001342b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013510`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001342b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180013510`

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
0x1800133e0  mov     [rsp+arg_0], rbx
0x1800133e5  mov     [rsp+arg_8], rsi
0x1800133ea  push    rdi
0x1800133eb  sub     rsp, 20h
0x1800133ef  mov     dword ptr [rcx], 0
0x1800133f5  mov     rdi, rcx
0x1800133f8  mov     rsi, [rcx+10h]
0x1800133fc  test    rsi, rsi
0x1800133ff  jz      short loc_180013439
0x180013401  call    cs:__imp_GetLastError
0x180013407  xor     r9d, r9d; msWindowLength
0x18001340a  xor     r8d, r8d; msPeriod
0x18001340d  xor     edx, edx; pftDueTime
0x18001340f  mov     rcx, rsi; pti
0x180013412  mov     ebx, eax
0x180013414  call    cs:__imp_SetThreadpoolTimer
0x18001341a  mov     edx, 1; fCancelPendingCallbacks
0x18001341f  mov     rcx, rsi; pti
0x180013422  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180013428  mov     rcx, rsi; pti
0x18001342b  call    cs:__imp_CloseThreadpoolTimer
0x180013431  mov     ecx, ebx; dwErrCode
0x180013433  call    cs:__imp_SetLastError
0x180013439  mov     rcx, rdi; this
0x18001343c  mov     qword ptr [rdi+10h], 0
0x180013444  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180013449  mov     rcx, [rdi+68h]
0x18001344d  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180013454  test    rcx, rcx
0x180013457  jz      short loc_180013479
0x180013459  test    rax, rax
0x18001345c  jnz     short loc_18001346D
0x18001345e  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180013465  test    rdx, rdx
0x180013468  jz      short loc_180013480
0x18001346a  mov     rax, rdx
0x18001346d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013472  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180013479  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180013480  mov     rcx, [rdi+60h]
0x180013484  test    rcx, rcx
0x180013487  jz      short loc_18001349B
0x180013489  test    rax, rax
0x18001348c  jnz     short loc_180013496
0x18001348e  test    rdx, rdx
0x180013491  jz      short loc_18001349B
0x180013493  mov     rax, rdx
0x180013496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001349b  mov     rbx, [rdi+58h]
0x18001349f  mov     qword ptr [rdi+58h], 0
0x1800134a7  test    rbx, rbx
0x1800134aa  jz      short loc_1800134C0
0x1800134ac  call    cs:__imp_GetProcessHeap
0x1800134b2  mov     r8, rbx; lpMem
0x1800134b5  xor     edx, edx; dwFlags
0x1800134b7  mov     rcx, rax; hHeap
0x1800134ba  call    cs:__imp_HeapFree
0x1800134c0  mov     rbx, [rdi+38h]
0x1800134c4  mov     qword ptr [rdi+38h], 0
0x1800134cc  test    rbx, rbx
0x1800134cf  jz      short loc_1800134E5
0x1800134d1  call    cs:__imp_GetProcessHeap
0x1800134d7  mov     r8, rbx; lpMem
0x1800134da  xor     edx, edx; dwFlags
0x1800134dc  mov     rcx, rax; hHeap
0x1800134df  call    cs:__imp_HeapFree
0x1800134e5  mov     rbx, [rdi+10h]
0x1800134e9  test    rbx, rbx
0x1800134ec  jz      short loc_180013516
0x1800134ee  xor     r9d, r9d; msWindowLength
0x1800134f1  xor     r8d, r8d; msPeriod
0x1800134f4  xor     edx, edx; pftDueTime
0x1800134f6  mov     rcx, rbx; pti
0x1800134f9  call    cs:__imp_SetThreadpoolTimer
0x1800134ff  mov     edx, 1; fCancelPendingCallbacks
0x180013504  mov     rcx, rbx; pti
0x180013507  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001350d  mov     rcx, rbx; pti
0x180013510  call    cs:__imp_CloseThreadpoolTimer
0x180013516  mov     rbx, [rsp+28h+arg_0]
0x18001351b  mov     rsi, [rsp+28h+arg_8]
0x180013520  add     rsp, 20h
0x180013524  pop     rdi
0x180013525  retn
```
