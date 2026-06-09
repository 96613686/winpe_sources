# WpnQoSLoggerImpl::Uninitialize(void)

- ea: `0x18001e4cc`
- end: `0x18001e667`
- name: `?Uninitialize@WpnQoSLoggerImpl@@SAJXZ`
- size: `411`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800108d8`

## callees

- `0x18001c06c`
- `0x18001e4cc`
- `0x180096010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e654`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001e654`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e5ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e611`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e63c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e5ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e611`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001e63c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e5e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e603`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e62e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e5e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e603`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e62e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e5ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e5ba`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001e572`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18001e572`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18001e584`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x18001e584`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001e565`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18001e565`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e5ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e5ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e59e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e59e`

## pseudocode

```c
__int64 WpnQoSLoggerImpl::Uninitialize(void)
{
  struct WpnQoSLoggerImpl *v0; // rcx
  struct WpnQoSLoggerImpl *v1; // rdx
  struct WpnQoSLoggerImpl::_QOS_DATA *v2; // rbx
  void *v3; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v5; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v0 = WpnQoSLoggerImpl::s_DataConnectionLogger;
  if ( !WpnQoSLoggerImpl::s_DataConnectionLogger )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
    v0 = WpnQoSLoggerImpl::s_DataConnectionLogger;
  }
  v1 = WpnQoSLoggerImpl::s_TestConnectionLogger;
  if ( !WpnQoSLoggerImpl::s_TestConnectionLogger )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(v0);
    v0 = WpnQoSLoggerImpl::s_DataConnectionLogger;
    v1 = WpnQoSLoggerImpl::s_TestConnectionLogger;
  }
  if ( v0 )
  {
    (*(void (__fastcall **)(struct WpnQoSLoggerImpl *))(*(_QWORD *)v0 + 16LL))(v0);
    v1 = WpnQoSLoggerImpl::s_TestConnectionLogger;
    WpnQoSLoggerImpl::s_DataConnectionLogger = 0;
  }
  if ( v1 )
  {
    (*(void (__fastcall **)(struct WpnQoSLoggerImpl *))(*(_QWORD *)v1 + 16LL))(v1);
    WpnQoSLoggerImpl::s_TestConnectionLogger = 0;
  }
  if ( WpnQoSLoggerImpl::s_CleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(WpnQoSLoggerImpl::s_CleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(WpnQoSLoggerImpl::s_CleanupGroup);
  }
  if ( WpnQoSLoggerImpl::s_ThreadPool )
    CloseThreadpool(WpnQoSLoggerImpl::s_ThreadPool);
  if ( WpnQoSLoggerImpl::s_Timer )
  {
    SetThreadpoolTimer(WpnQoSLoggerImpl::s_Timer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(WpnQoSLoggerImpl::s_Timer, 1);
    CloseThreadpoolTimer(WpnQoSLoggerImpl::s_Timer);
    WpnQoSLoggerImpl::s_Timer = 0;
  }
  v2 = WpnQoSLoggerImpl::s_TimerData;
  if ( WpnQoSLoggerImpl::s_TimerData )
  {
    v3 = (void *)*((_QWORD *)WpnQoSLoggerImpl::s_TimerData + 3);
    if ( v3 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v3);
      v2 = WpnQoSLoggerImpl::s_TimerData;
      *((_QWORD *)WpnQoSLoggerImpl::s_TimerData + 3) = 0;
    }
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v2);
    WpnQoSLoggerImpl::s_TimerData = 0;
  }
  v6 = WatsonWrapper::s_TempDirectoryPath;
  if ( WatsonWrapper::s_TempDirectoryPath )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
    WatsonWrapper::s_TempDirectoryPath = 0;
  }
  DeleteCriticalSection(&WpnQoSLoggerImpl::s_TimerLock);
  return 0;
}

```

## disassembly

```asm
0x18001e4cc  mov     [rsp+arg_0], rbx
0x18001e4d1  push    rdi
0x18001e4d2  sub     rsp, 20h
0x18001e4d6  mov     rcx, cs:?s_DataConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_DataConnectionLogger
0x18001e4dd  test    rcx, rcx
0x18001e4e0  jnz     short loc_18001E4EE
0x18001e4e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001e4e7  mov     rcx, cs:?s_DataConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_DataConnectionLogger
0x18001e4ee  mov     rdx, cs:?s_TestConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_TestConnectionLogger
0x18001e4f5  test    rdx, rdx
0x18001e4f8  jnz     short loc_18001E50D
0x18001e4fa  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001e4ff  mov     rcx, cs:?s_DataConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_DataConnectionLogger
0x18001e506  mov     rdx, cs:?s_TestConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_TestConnectionLogger
0x18001e50d  test    rcx, rcx
0x18001e510  jz      short loc_18001E530
0x18001e512  mov     rax, [rcx]
0x18001e515  mov     rax, [rax+10h]
0x18001e519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e51e  mov     rdx, cs:?s_TestConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_TestConnectionLogger
0x18001e525  mov     cs:?s_DataConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, 0; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_DataConnectionLogger
0x18001e530  test    rdx, rdx
0x18001e533  jz      short loc_18001E54F
0x18001e535  mov     rax, [rdx]
0x18001e538  mov     rcx, rdx
0x18001e53b  mov     rax, [rax+10h]
0x18001e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e544  mov     cs:?s_TestConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, 0; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_TestConnectionLogger
0x18001e54f  mov     rcx, cs:?s_CleanupGroup@WpnQoSLoggerImpl@@0PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x18001e556  mov     ebx, 1
0x18001e55b  test    rcx, rcx
0x18001e55e  jz      short loc_18001E578
0x18001e560  xor     r8d, r8d; pvCleanupContext
0x18001e563  mov     edx, ebx; fCancelPendingCallbacks
0x18001e565  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18001e56b  mov     rcx, cs:?s_CleanupGroup@WpnQoSLoggerImpl@@0PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x18001e572  call    cs:__imp_CloseThreadpoolCleanupGroup
0x18001e578  mov     rcx, cs:?s_ThreadPool@WpnQoSLoggerImpl@@0PEAU_TP_POOL@@EA; ptpp
0x18001e57f  test    rcx, rcx
0x18001e582  jz      short loc_18001E58A
0x18001e584  call    cs:__imp_CloseThreadpool
0x18001e58a  mov     rcx, cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA; pti
0x18001e591  test    rcx, rcx
0x18001e594  jz      short loc_18001E5CB
0x18001e596  xor     r9d, r9d; msWindowLength
0x18001e599  xor     r8d, r8d; msPeriod
0x18001e59c  xor     edx, edx; pftDueTime
0x18001e59e  call    cs:__imp_SetThreadpoolTimer
0x18001e5a4  mov     rcx, cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA; pti
0x18001e5ab  mov     edx, ebx; fCancelPendingCallbacks
0x18001e5ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001e5b3  mov     rcx, cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA; pti
0x18001e5ba  call    cs:__imp_CloseThreadpoolTimer
0x18001e5c0  mov     cs:?s_Timer@WpnQoSLoggerImpl@@0PEAU_TP_TIMER@@EA, 0; _TP_TIMER * WpnQoSLoggerImpl::s_Timer
0x18001e5cb  mov     rbx, cs:?s_TimerData@WpnQoSLoggerImpl@@0PEAU_QOS_DATA@1@EA; WpnQoSLoggerImpl::_QOS_DATA * WpnQoSLoggerImpl::s_TimerData
0x18001e5d2  test    rbx, rbx
0x18001e5d5  jz      short loc_18001E622
0x18001e5d7  mov     rdi, [rbx+18h]
0x18001e5db  test    rdi, rdi
0x18001e5de  jz      short loc_18001E603
0x18001e5e0  call    cs:__imp_GetProcessHeap
0x18001e5e6  mov     r8, rdi; lpMem
0x18001e5e9  xor     edx, edx; dwFlags
0x18001e5eb  mov     rcx, rax; hHeap
0x18001e5ee  call    cs:__imp_HeapFree
0x18001e5f4  mov     rbx, cs:?s_TimerData@WpnQoSLoggerImpl@@0PEAU_QOS_DATA@1@EA; WpnQoSLoggerImpl::_QOS_DATA * WpnQoSLoggerImpl::s_TimerData
0x18001e5fb  mov     qword ptr [rbx+18h], 0
0x18001e603  call    cs:__imp_GetProcessHeap
0x18001e609  mov     r8, rbx; lpMem
0x18001e60c  xor     edx, edx; dwFlags
0x18001e60e  mov     rcx, rax; hHeap
0x18001e611  call    cs:__imp_HeapFree
0x18001e617  mov     cs:?s_TimerData@WpnQoSLoggerImpl@@0PEAU_QOS_DATA@1@EA, 0; WpnQoSLoggerImpl::_QOS_DATA * WpnQoSLoggerImpl::s_TimerData
0x18001e622  mov     rbx, cs:?s_TempDirectoryPath@WatsonWrapper@@0PEAGEA; ushort * WatsonWrapper::s_TempDirectoryPath
0x18001e629  test    rbx, rbx
0x18001e62c  jz      short loc_18001E64D
0x18001e62e  call    cs:__imp_GetProcessHeap
0x18001e634  mov     r8, rbx; lpMem
0x18001e637  xor     edx, edx; dwFlags
0x18001e639  mov     rcx, rax; hHeap
0x18001e63c  call    cs:__imp_HeapFree
0x18001e642  mov     cs:?s_TempDirectoryPath@WatsonWrapper@@0PEAGEA, 0; ushort * WatsonWrapper::s_TempDirectoryPath
0x18001e64d  lea     rcx, ?s_TimerLock@WpnQoSLoggerImpl@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e654  call    cs:__imp_DeleteCriticalSection
0x18001e65a  mov     rbx, [rsp+28h+arg_0]
0x18001e65f  xor     eax, eax
0x18001e661  add     rsp, 20h
0x18001e665  pop     rdi
0x18001e666  retn
```
