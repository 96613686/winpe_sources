# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x1800047d4`
- end: `0x18000492c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004b850`

## callees

- `0x1800047d4`
- `0x1800049c8`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000484e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004873`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000484e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004873`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000485c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004881`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000485c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004881`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004824`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800047f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004813`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000490c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004813`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000490c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000481c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004915`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000481c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004915`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004805`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004805`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800048fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800047d4  mov     [rsp+arg_0], rbx
0x1800047d9  mov     [rsp+arg_8], rsi
0x1800047de  push    rdi
0x1800047df  sub     rsp, 20h
0x1800047e3  mov     rdi, rcx
0x1800047e6  mov     byte ptr [rcx], 0
0x1800047e9  mov     rsi, [rcx+10h]
0x1800047ed  test    rsi, rsi
0x1800047f0  jz      short loc_18000482A
0x1800047f2  call    cs:__imp_GetLastError
0x1800047f8  mov     ebx, eax
0x1800047fa  xor     r9d, r9d; msWindowLength
0x1800047fd  xor     r8d, r8d; msPeriod
0x180004800  xor     edx, edx; pftDueTime
0x180004802  mov     rcx, rsi; pti
0x180004805  call    cs:__imp_SetThreadpoolTimer
0x18000480b  mov     edx, 1; fCancelPendingCallbacks
0x180004810  mov     rcx, rsi; pti
0x180004813  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004819  mov     rcx, rsi; pti
0x18000481c  call    cs:__imp_CloseThreadpoolTimer
0x180004822  mov     ecx, ebx; dwErrCode
0x180004824  call    cs:__imp_SetLastError
0x18000482a  mov     qword ptr [rdi+10h], 0
0x180004832  mov     byte ptr [rdi], 0
0x180004835  mov     rcx, rdi; this
0x180004838  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18000483d  mov     rbx, [rdi+68h]
0x180004841  mov     qword ptr [rdi+68h], 0
0x180004849  test    rbx, rbx
0x18000484c  jz      short loc_180004862
0x18000484e  call    cs:__imp_GetProcessHeap
0x180004854  mov     rcx, rax; hHeap
0x180004857  mov     r8, rbx; lpMem
0x18000485a  xor     edx, edx; dwFlags
0x18000485c  call    cs:__imp_HeapFree
0x180004862  mov     rbx, [rdi+48h]
0x180004866  mov     qword ptr [rdi+48h], 0
0x18000486e  test    rbx, rbx
0x180004871  jz      short loc_180004887
0x180004873  call    cs:__imp_GetProcessHeap
0x180004879  mov     rcx, rax; hHeap
0x18000487c  mov     r8, rbx; lpMem
0x18000487f  xor     edx, edx; dwFlags
0x180004881  call    cs:__imp_HeapFree
0x180004887  mov     rcx, [rdi+28h]
0x18000488b  test    rcx, rcx
0x18000488e  jz      short loc_1800048C0
0x180004890  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180004897  test    rax, rax
0x18000489a  jnz     short loc_1800048AB
0x18000489c  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800048a3  test    rdx, rdx
0x1800048a6  jz      short loc_1800048BE
0x1800048a8  mov     rax, rdx
0x1800048ab  call    _guard_dispatch_icall
0x1800048b0  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800048b7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800048be  jmp     short loc_1800048CE
0x1800048c0  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x1800048c7  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x1800048ce  mov     rcx, [rdi+20h]
0x1800048d2  test    rcx, rcx
0x1800048d5  jz      short loc_1800048EA
0x1800048d7  test    rax, rax
0x1800048da  jnz     short loc_1800048E4
0x1800048dc  test    rdx, rdx
0x1800048df  jz      short loc_1800048EA
0x1800048e1  mov     rax, rdx
0x1800048e4  call    _guard_dispatch_icall
0x1800048e9  nop
0x1800048ea  mov     rbx, [rdi+10h]
0x1800048ee  test    rbx, rbx
0x1800048f1  jz      short loc_18000491C
0x1800048f3  xor     r9d, r9d; msWindowLength
0x1800048f6  xor     r8d, r8d; msPeriod
0x1800048f9  xor     edx, edx; pftDueTime
0x1800048fb  mov     rcx, rbx; pti
0x1800048fe  call    cs:__imp_SetThreadpoolTimer
0x180004904  mov     edx, 1; fCancelPendingCallbacks
0x180004909  mov     rcx, rbx; pti
0x18000490c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004912  mov     rcx, rbx; pti
0x180004915  call    cs:__imp_CloseThreadpoolTimer
0x18000491b  nop
0x18000491c  mov     rbx, [rsp+28h+arg_0]
0x180004921  mov     rsi, [rsp+28h+arg_8]
0x180004926  add     rsp, 20h
0x18000492a  pop     rdi
0x18000492b  retn
```
