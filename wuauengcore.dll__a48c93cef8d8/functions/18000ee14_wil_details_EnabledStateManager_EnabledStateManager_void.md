# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x18000ee14`
- end: `0x18000ef6c`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180248c80`

## callees

- `0x18000ee14`
- `0x18000f008`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eec1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ee9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eec1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eeb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ee8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eeb3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ee64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ee64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee32`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ee5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ef55`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ee5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ef55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ef3e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ef3e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ef4c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee53`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ef4c`

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
0x18000ee14  mov     [rsp+arg_0], rbx
0x18000ee19  mov     [rsp+arg_8], rsi
0x18000ee1e  push    rdi
0x18000ee1f  sub     rsp, 20h
0x18000ee23  mov     rdi, rcx
0x18000ee26  mov     byte ptr [rcx], 0
0x18000ee29  mov     rsi, [rcx+10h]
0x18000ee2d  test    rsi, rsi
0x18000ee30  jz      short loc_18000EE6A
0x18000ee32  call    cs:__imp_GetLastError
0x18000ee38  mov     ebx, eax
0x18000ee3a  xor     r9d, r9d; msWindowLength
0x18000ee3d  xor     r8d, r8d; msPeriod
0x18000ee40  xor     edx, edx; pftDueTime
0x18000ee42  mov     rcx, rsi; pti
0x18000ee45  call    cs:__imp_SetThreadpoolTimer
0x18000ee4b  mov     edx, 1; fCancelPendingCallbacks
0x18000ee50  mov     rcx, rsi; pti
0x18000ee53  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ee59  mov     rcx, rsi; pti
0x18000ee5c  call    cs:__imp_CloseThreadpoolTimer
0x18000ee62  mov     ecx, ebx; dwErrCode
0x18000ee64  call    cs:__imp_SetLastError
0x18000ee6a  mov     qword ptr [rdi+10h], 0
0x18000ee72  mov     byte ptr [rdi], 0
0x18000ee75  mov     rcx, rdi; this
0x18000ee78  call    ?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ; wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)
0x18000ee7d  mov     rbx, [rdi+68h]
0x18000ee81  mov     qword ptr [rdi+68h], 0
0x18000ee89  test    rbx, rbx
0x18000ee8c  jz      short loc_18000EEA2
0x18000ee8e  call    cs:__imp_GetProcessHeap
0x18000ee94  mov     rcx, rax; hHeap
0x18000ee97  mov     r8, rbx; lpMem
0x18000ee9a  xor     edx, edx; dwFlags
0x18000ee9c  call    cs:__imp_HeapFree
0x18000eea2  mov     rbx, [rdi+48h]
0x18000eea6  mov     qword ptr [rdi+48h], 0
0x18000eeae  test    rbx, rbx
0x18000eeb1  jz      short loc_18000EEC7
0x18000eeb3  call    cs:__imp_GetProcessHeap
0x18000eeb9  mov     rcx, rax; hHeap
0x18000eebc  mov     r8, rbx; lpMem
0x18000eebf  xor     edx, edx; dwFlags
0x18000eec1  call    cs:__imp_HeapFree
0x18000eec7  mov     rcx, [rdi+28h]
0x18000eecb  test    rcx, rcx
0x18000eece  jz      short loc_18000EF00
0x18000eed0  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000eed7  test    rax, rax
0x18000eeda  jnz     short loc_18000EEEB
0x18000eedc  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000eee3  test    rdx, rdx
0x18000eee6  jz      short loc_18000EEFE
0x18000eee8  mov     rax, rdx
0x18000eeeb  call    _guard_dispatch_icall
0x18000eef0  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000eef7  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000eefe  jmp     short loc_18000EF0E
0x18000ef00  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x18000ef07  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x18000ef0e  mov     rcx, [rdi+20h]
0x18000ef12  test    rcx, rcx
0x18000ef15  jz      short loc_18000EF2A
0x18000ef17  test    rax, rax
0x18000ef1a  jnz     short loc_18000EF24
0x18000ef1c  test    rdx, rdx
0x18000ef1f  jz      short loc_18000EF2A
0x18000ef21  mov     rax, rdx
0x18000ef24  call    _guard_dispatch_icall
0x18000ef29  nop
0x18000ef2a  mov     rbx, [rdi+10h]
0x18000ef2e  test    rbx, rbx
0x18000ef31  jz      short loc_18000EF5C
0x18000ef33  xor     r9d, r9d; msWindowLength
0x18000ef36  xor     r8d, r8d; msPeriod
0x18000ef39  xor     edx, edx; pftDueTime
0x18000ef3b  mov     rcx, rbx; pti
0x18000ef3e  call    cs:__imp_SetThreadpoolTimer
0x18000ef44  mov     edx, 1; fCancelPendingCallbacks
0x18000ef49  mov     rcx, rbx; pti
0x18000ef4c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ef52  mov     rcx, rbx; pti
0x18000ef55  call    cs:__imp_CloseThreadpoolTimer
0x18000ef5b  nop
0x18000ef5c  mov     rbx, [rsp+28h+arg_0]
0x18000ef61  mov     rsi, [rsp+28h+arg_8]
0x18000ef66  add     rsp, 20h
0x18000ef6a  pop     rdi
0x18000ef6b  retn
```
