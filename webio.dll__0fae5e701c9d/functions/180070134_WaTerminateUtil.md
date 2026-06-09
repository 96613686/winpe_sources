# WaTerminateUtil

- ea: `0x180070134`
- end: `0x1800702ec`
- name: `WaTerminateUtil`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800434c0`

## callees

- `0x180013820`
- `0x1800201dc`
- `0x18002187c`
- `0x180059150`
- `0x180064864`
- `0x180066ce0`
- `0x18006a610`
- `0x180070134`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800701e4`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x1800701e4`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180070274`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180070274`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800701f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800701f7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18007015e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180070229`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18007015e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180070229`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180070171`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18007023c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180070171`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x18007023c`
- `WS2_32!__imp_WSACleanup` at `0x180070184`
- `WS2_32!__imp_WSACleanup` at `0x180070184`

## pseudocode

```c
__int64 WaTerminateUtil()
{
  PSLIST_ENTRY v0; // rax
  __int64 result; // rax
  __int64 v2; // [rsp+30h] [rbp+8h] BYREF

  if ( WaDecompInitialized )
    WaDecompInitialized = 0;
  if ( WaDnsModuleInitialized )
  {
    CloseThreadpoolCleanupGroupMembers(WaDnsCacheCleanupGroup, 0, 0);
    CloseThreadpoolCleanupGroup(WaDnsCacheCleanupGroup);
    WaDnsCacheCleanupGroup = 0;
    WSACleanup();
    WaDnsModuleInitialized = 0;
  }
  if ( WaNetworkChangeInitialized )
  {
    WapTerminateNetworkChange();
    WaNetworkChangeInitialized = 0;
  }
  if ( WaTwTimerInitialized )
  {
    WaDeleteTimer(WaTwExpiryTimer);
    WapTerminateTimerWheel();
    WaTwTimerInitialized = 0;
  }
  if ( WaTimerInitialized )
    WaTimerInitialized = 0;
  if ( WaCallbackQueueInitialized )
  {
    TlsFree(WaCallbackQueueTlsIndex);
    DeleteCriticalSection(&WaGlobalCallbackQueueLock);
    WaTpTerminateWorkItem(&WaCallbackWorkItem);
    WaCallbackQueueInitialized = 0;
  }
  if ( WaTpInitialized )
  {
    CloseThreadpoolCleanupGroupMembers(WaTpCleanupGroup, 0, 0);
    CloseThreadpoolCleanupGroup(WaTpCleanupGroup);
    WaTpCleanupGroup = 0;
    WaTpInitialized = 0;
  }
  WaTerminateHandleTable();
  if ( WaEventCacheInitialized )
  {
    while ( 1 )
    {
      v0 = InterlockedPopEntrySList(&WaEventCacheSListHead);
      if ( !v0 )
        break;
      WapCleanupEventCacheEntry(&v0[-1]);
    }
    WaEventCacheInitialized = 0;
  }
  if ( dword_1800AE6C4 && !g_HeapExtensionSet )
    dword_1800AE6C4 = 0;
  if ( g_pwszProcessName )
  {
    v2 = g_pwszProcessName;
    WxFreeHeapEx(&v2);
    g_pwszProcessName = 0;
  }
  result = g_pwszProcessPath;
  if ( g_pwszProcessPath )
  {
    v2 = g_pwszProcessPath;
    result = WxFreeHeapEx(&v2);
    g_pwszProcessPath = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180070134  push    rbx
0x180070136  sub     rsp, 20h
0x18007013a  xor     ebx, ebx
0x18007013c  cmp     cs:WaDecompInitialized, bl
0x180070142  jz      short loc_18007014A
0x180070144  mov     cs:WaDecompInitialized, bl
0x18007014a  cmp     cs:WaDnsModuleInitialized, bl
0x180070150  jz      short loc_180070196
0x180070152  mov     rcx, cs:WaDnsCacheCleanupGroup; ptpcg
0x180070159  xor     r8d, r8d; pvCleanupContext
0x18007015c  xor     edx, edx; fCancelPendingCallbacks
0x18007015e  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180070165  nop     dword ptr [rax+rax+00h]
0x18007016a  mov     rcx, cs:WaDnsCacheCleanupGroup; ptpcg
0x180070171  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180070178  nop     dword ptr [rax+rax+00h]
0x18007017d  mov     cs:WaDnsCacheCleanupGroup, rbx
0x180070184  call    cs:__imp_WSACleanup
0x18007018b  nop     dword ptr [rax+rax+00h]
0x180070190  mov     cs:WaDnsModuleInitialized, bl
0x180070196  cmp     cs:WaNetworkChangeInitialized, bl
0x18007019c  jz      short loc_1800701A9
0x18007019e  call    WapTerminateNetworkChange
0x1800701a3  mov     cs:WaNetworkChangeInitialized, bl
0x1800701a9  cmp     cs:WaTwTimerInitialized, bl
0x1800701af  jz      short loc_1800701C8
0x1800701b1  lea     rcx, WaTwExpiryTimer
0x1800701b8  call    WaDeleteTimer
0x1800701bd  call    WapTerminateTimerWheel
0x1800701c2  mov     cs:WaTwTimerInitialized, bl
0x1800701c8  cmp     cs:WaTimerInitialized, bl
0x1800701ce  jz      short loc_1800701D6
0x1800701d0  mov     cs:WaTimerInitialized, bl
0x1800701d6  cmp     cs:WaCallbackQueueInitialized, bl
0x1800701dc  jz      short loc_180070215
0x1800701de  mov     ecx, cs:WaCallbackQueueTlsIndex; dwTlsIndex
0x1800701e4  call    cs:__imp_TlsFree
0x1800701eb  nop     dword ptr [rax+rax+00h]
0x1800701f0  lea     rcx, WaGlobalCallbackQueueLock; lpCriticalSection
0x1800701f7  call    cs:__imp_DeleteCriticalSection
0x1800701fe  nop     dword ptr [rax+rax+00h]
0x180070203  lea     rcx, WaCallbackWorkItem
0x18007020a  call    WaTpTerminateWorkItem
0x18007020f  mov     cs:WaCallbackQueueInitialized, bl
0x180070215  cmp     cs:WaTpInitialized, bl
0x18007021b  jz      short loc_180070255
0x18007021d  mov     rcx, cs:WaTpCleanupGroup; ptpcg
0x180070224  xor     r8d, r8d; pvCleanupContext
0x180070227  xor     edx, edx; fCancelPendingCallbacks
0x180070229  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180070230  nop     dword ptr [rax+rax+00h]
0x180070235  mov     rcx, cs:WaTpCleanupGroup; ptpcg
0x18007023c  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180070243  nop     dword ptr [rax+rax+00h]
0x180070248  mov     cs:WaTpCleanupGroup, rbx
0x18007024f  mov     cs:WaTpInitialized, bl
0x180070255  call    WaTerminateHandleTable
0x18007025a  cmp     cs:WaEventCacheInitialized, bl
0x180070260  jz      short loc_18007028B
0x180070262  jmp     short loc_18007026D
0x180070264  lea     rcx, [rax-10h]
0x180070268  call    WapCleanupEventCacheEntry
0x18007026d  lea     rcx, WaEventCacheSListHead; ListHead
0x180070274  call    cs:__imp_InterlockedPopEntrySList
0x18007027b  nop     dword ptr [rax+rax+00h]
0x180070280  test    rax, rax
0x180070283  jnz     short loc_180070264
0x180070285  mov     cs:WaEventCacheInitialized, bl
0x18007028b  cmp     cs:dword_1800AE6C4, ebx
0x180070291  jz      short loc_1800702A1
0x180070293  cmp     cs:g_HeapExtensionSet, ebx
0x180070299  jnz     short loc_1800702A1
0x18007029b  mov     cs:dword_1800AE6C4, ebx
0x1800702a1  mov     rax, cs:g_pwszProcessName
0x1800702a8  test    rax, rax
0x1800702ab  jz      short loc_1800702C3
0x1800702ad  lea     rcx, [rsp+28h+arg_0]
0x1800702b2  mov     [rsp+28h+arg_0], rax
0x1800702b7  call    WxFreeHeapEx
0x1800702bc  mov     cs:g_pwszProcessName, rbx
0x1800702c3  mov     rax, cs:g_pwszProcessPath
0x1800702ca  test    rax, rax
0x1800702cd  jz      short loc_1800702E5
0x1800702cf  lea     rcx, [rsp+28h+arg_0]
0x1800702d4  mov     [rsp+28h+arg_0], rax
0x1800702d9  call    WxFreeHeapEx
0x1800702de  mov     cs:g_pwszProcessPath, rbx
0x1800702e5  add     rsp, 20h
0x1800702e9  pop     rbx
0x1800702ea  retn
```
