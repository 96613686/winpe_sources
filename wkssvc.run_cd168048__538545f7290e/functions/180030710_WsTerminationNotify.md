# WsTerminationNotify

- ea: `0x180030710`
- end: `0x1800308d8`
- name: `WsTerminationNotify`
- size: `456`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002fe70`

## callees

- `0x18000da34`
- `0x180030544`
- `0x180030710`

## import_xrefs

- `ntdll!RtlDeregisterWait` at `0x180030728`
- `ntdll!RtlDeregisterWait` at `0x180030728`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030789`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030789`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800307fb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800307fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800307e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800307e8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800308ab`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800307d9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800307d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180030811`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180030811`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030820`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030751`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180030820`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800308ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800308ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030891`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030891`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18003085e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18003085e`
- `netutils!NetApiBufferFree` at `0x1800307a7`
- `netutils!NetApiBufferFree` at `0x1800307a7`
- `USERENV!UnregisterGPNotification` at `0x180030879`
- `USERENV!UnregisterGPNotification` at `0x180030879`

## pseudocode

```c
void WsTerminationNotify()
{
  HANDLE v0; // rcx

  if ( TerminateWorkItem )
  {
    RtlDeregisterWait(TerminateWorkItem);
    TerminateWorkItem = 0;
  }
  if ( WsWorkerCriticalSectionInitialized )
  {
    EnterCriticalSection(&WsWorkerCriticalSection);
    WsIsTerminationHandlerRunning = 1;
    if ( WitnessClientEngineInitialized )
    {
      WitnessTerminate();
      WitnessClientEngineInitialized = 0;
    }
    if ( ConfigHandleOpened )
    {
      RegCloseKey(ConfigHandle);
      ConfigHandleOpened = 0;
    }
    if ( RegPathToWatch )
    {
      NetApiBufferFree((LPVOID)RegPathToWatch);
      RegPathToWatch = 0;
    }
    v0 = RegistryChangeEvent;
    if ( RegistryChangeEvent )
    {
      if ( WsNumWorkerThreads )
      {
        ResetEvent(hHandle);
        LeaveCriticalSection(&WsWorkerCriticalSection);
        SetEvent(RegistryChangeEvent);
        WaitForSingleObject(hHandle, 0xFFFFFFFF);
        EnterCriticalSection(&WsWorkerCriticalSection);
        v0 = RegistryChangeEvent;
      }
      if ( v0 )
      {
        CloseHandle(v0);
        RegistryChangeEvent = 0;
      }
    }
    if ( WaitingForMachineGroupPolicyChanges )
      UnregisterWaitEx(MachineGroupPolicyChangeWaitObject, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    if ( RegisteredForMachineGroupPolicyChangeNotifications )
      UnregisterGPNotification(MachineGroupPolicyChangeEvent);
    if ( MachineGroupPolicyChangeEvent )
      CloseHandle(MachineGroupPolicyChangeEvent);
    WsShutdownWorkstation();
    WsIsTerminationHandlerRunning = 0;
    LeaveCriticalSection(&WsWorkerCriticalSection);
    DeleteCriticalSection(&WsWorkerCriticalSection);
    WsWorkerCriticalSectionInitialized = 0;
  }
}

```

## disassembly

```asm
0x180030710  mov     [rsp+arg_0], rbx
0x180030715  push    rdi
0x180030716  sub     rsp, 20h
0x18003071a  mov     rcx, cs:TerminateWorkItem; hWaitHandle
0x180030721  xor     ebx, ebx
0x180030723  test    rcx, rcx
0x180030726  jz      short loc_18003073B
0x180030728  call    cs:__imp_RtlDeregisterWait
0x18003072f  nop     dword ptr [rax+rax+00h]
0x180030734  mov     cs:TerminateWorkItem, rbx
0x18003073b  cmp     cs:WsWorkerCriticalSectionInitialized, ebx
0x180030741  jz      loc_1800308CC
0x180030747  lea     rdi, WsWorkerCriticalSection
0x18003074e  mov     rcx, rdi; lpCriticalSection
0x180030751  call    cs:__imp_EnterCriticalSection
0x180030758  nop     dword ptr [rax+rax+00h]
0x18003075d  cmp     cs:WitnessClientEngineInitialized, ebx
0x180030763  mov     cs:WsIsTerminationHandlerRunning, 1
0x18003076d  jz      short loc_18003077A
0x18003076f  call    WitnessTerminate
0x180030774  mov     cs:WitnessClientEngineInitialized, ebx
0x18003077a  cmp     cs:ConfigHandleOpened, ebx
0x180030780  jz      short loc_18003079B
0x180030782  mov     rcx, cs:ConfigHandle; hKey
0x180030789  call    cs:__imp_RegCloseKey
0x180030790  nop     dword ptr [rax+rax+00h]
0x180030795  mov     cs:ConfigHandleOpened, ebx
0x18003079b  mov     rcx, cs:RegPathToWatch; Buffer
0x1800307a2  test    rcx, rcx
0x1800307a5  jz      short loc_1800307BA
0x1800307a7  call    cs:__imp_NetApiBufferFree
0x1800307ae  nop     dword ptr [rax+rax+00h]
0x1800307b3  mov     cs:RegPathToWatch, rbx
0x1800307ba  mov     rcx, cs:RegistryChangeEvent
0x1800307c1  test    rcx, rcx
0x1800307c4  jz      loc_18003084B
0x1800307ca  cmp     cs:WsNumWorkerThreads, ebx
0x1800307d0  jz      short loc_180030833
0x1800307d2  mov     rcx, cs:hHandle; hEvent
0x1800307d9  call    cs:__imp_ResetEvent
0x1800307e0  nop     dword ptr [rax+rax+00h]
0x1800307e5  mov     rcx, rdi; lpCriticalSection
0x1800307e8  call    cs:__imp_LeaveCriticalSection
0x1800307ef  nop     dword ptr [rax+rax+00h]
0x1800307f4  mov     rcx, cs:RegistryChangeEvent; hEvent
0x1800307fb  call    cs:__imp_SetEvent
0x180030802  nop     dword ptr [rax+rax+00h]
0x180030807  mov     rcx, cs:hHandle; hHandle
0x18003080e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180030811  call    cs:__imp_WaitForSingleObject
0x180030818  nop     dword ptr [rax+rax+00h]
0x18003081d  mov     rcx, rdi; lpCriticalSection
0x180030820  call    cs:__imp_EnterCriticalSection
0x180030827  nop     dword ptr [rax+rax+00h]
0x18003082c  mov     rcx, cs:RegistryChangeEvent; hObject
0x180030833  test    rcx, rcx
0x180030836  jz      short loc_18003084B
0x180030838  call    cs:__imp_CloseHandle
0x18003083f  nop     dword ptr [rax+rax+00h]
0x180030844  mov     cs:RegistryChangeEvent, rbx
0x18003084b  cmp     cs:WaitingForMachineGroupPolicyChanges, ebx
0x180030851  jz      short loc_18003086A
0x180030853  mov     rcx, cs:MachineGroupPolicyChangeWaitObject; WaitHandle
0x18003085a  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003085e  call    cs:__imp_UnregisterWaitEx
0x180030865  nop     dword ptr [rax+rax+00h]
0x18003086a  cmp     cs:RegisteredForMachineGroupPolicyChangeNotifications, ebx
0x180030870  jz      short loc_180030885
0x180030872  mov     rcx, cs:MachineGroupPolicyChangeEvent; hEvent
0x180030879  call    cs:__imp_UnregisterGPNotification
0x180030880  nop     dword ptr [rax+rax+00h]
0x180030885  mov     rcx, cs:MachineGroupPolicyChangeEvent; hObject
0x18003088c  test    rcx, rcx
0x18003088f  jz      short loc_18003089D
0x180030891  call    cs:__imp_CloseHandle
0x180030898  nop     dword ptr [rax+rax+00h]
0x18003089d  call    WsShutdownWorkstation
0x1800308a2  mov     rcx, rdi; lpCriticalSection
0x1800308a5  mov     cs:WsIsTerminationHandlerRunning, ebx
0x1800308ab  call    cs:__imp_LeaveCriticalSection
0x1800308b2  nop     dword ptr [rax+rax+00h]
0x1800308b7  mov     rcx, rdi; lpCriticalSection
0x1800308ba  call    cs:__imp_DeleteCriticalSection
0x1800308c1  nop     dword ptr [rax+rax+00h]
0x1800308c6  mov     cs:WsWorkerCriticalSectionInitialized, ebx
0x1800308cc  mov     rbx, [rsp+28h+arg_0]
0x1800308d1  add     rsp, 20h
0x1800308d5  pop     rdi
0x1800308d6  retn
```
