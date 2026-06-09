# WsTerminationNotify

- ea: `0x18002dd20`
- end: `0x18002de89`
- name: `WsTerminationNotify`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002d530`

## callees

- `0x18000ce80`
- `0x18002db4c`
- `0x18002dd20`

## import_xrefs

- `ntdll!RtlDeregisterWait` at `0x18002dd38`
- `ntdll!RtlDeregisterWait` at `0x18002dd38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd8d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002dd8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002dde3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002dde3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ddd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de69`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ddd6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002de69`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002ddcd`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002ddcd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ddf3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18002ddf3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dd5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ddfc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002dd5b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002ddfc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002de72`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002de72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002de55`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002de2e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18002de2e`
- `netutils!NetApiBufferFree` at `0x18002dda5`
- `netutils!NetApiBufferFree` at `0x18002dda5`
- `USERENV!UnregisterGPNotification` at `0x18002de43`
- `USERENV!UnregisterGPNotification` at `0x18002de43`

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
0x18002dd20  mov     [rsp+arg_0], rbx
0x18002dd25  push    rdi
0x18002dd26  sub     rsp, 20h
0x18002dd2a  mov     rcx, cs:TerminateWorkItem; hWaitHandle
0x18002dd31  xor     ebx, ebx
0x18002dd33  test    rcx, rcx
0x18002dd36  jz      short loc_18002DD45
0x18002dd38  call    cs:__imp_RtlDeregisterWait
0x18002dd3e  mov     cs:TerminateWorkItem, rbx
0x18002dd45  cmp     cs:WsWorkerCriticalSectionInitialized, ebx
0x18002dd4b  jz      loc_18002DE7E
0x18002dd51  lea     rdi, WsWorkerCriticalSection
0x18002dd58  mov     rcx, rdi; lpCriticalSection
0x18002dd5b  call    cs:__imp_EnterCriticalSection
0x18002dd61  cmp     cs:WitnessClientEngineInitialized, ebx
0x18002dd67  mov     cs:WsIsTerminationHandlerRunning, 1
0x18002dd71  jz      short loc_18002DD7E
0x18002dd73  call    WitnessTerminate
0x18002dd78  mov     cs:WitnessClientEngineInitialized, ebx
0x18002dd7e  cmp     cs:ConfigHandleOpened, ebx
0x18002dd84  jz      short loc_18002DD99
0x18002dd86  mov     rcx, cs:ConfigHandle; hKey
0x18002dd8d  call    cs:__imp_RegCloseKey
0x18002dd93  mov     cs:ConfigHandleOpened, ebx
0x18002dd99  mov     rcx, cs:RegPathToWatch; Buffer
0x18002dda0  test    rcx, rcx
0x18002dda3  jz      short loc_18002DDB2
0x18002dda5  call    cs:__imp_NetApiBufferFree
0x18002ddab  mov     cs:RegPathToWatch, rbx
0x18002ddb2  mov     rcx, cs:RegistryChangeEvent
0x18002ddb9  test    rcx, rcx
0x18002ddbc  jz      short loc_18002DE1B
0x18002ddbe  cmp     cs:WsNumWorkerThreads, ebx
0x18002ddc4  jz      short loc_18002DE09
0x18002ddc6  mov     rcx, cs:hHandle; hEvent
0x18002ddcd  call    cs:__imp_ResetEvent
0x18002ddd3  mov     rcx, rdi; lpCriticalSection
0x18002ddd6  call    cs:__imp_LeaveCriticalSection
0x18002dddc  mov     rcx, cs:RegistryChangeEvent; hEvent
0x18002dde3  call    cs:__imp_SetEvent
0x18002dde9  mov     rcx, cs:hHandle; hHandle
0x18002ddf0  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18002ddf3  call    cs:__imp_WaitForSingleObject
0x18002ddf9  mov     rcx, rdi; lpCriticalSection
0x18002ddfc  call    cs:__imp_EnterCriticalSection
0x18002de02  mov     rcx, cs:RegistryChangeEvent; hObject
0x18002de09  test    rcx, rcx
0x18002de0c  jz      short loc_18002DE1B
0x18002de0e  call    cs:__imp_CloseHandle
0x18002de14  mov     cs:RegistryChangeEvent, rbx
0x18002de1b  cmp     cs:WaitingForMachineGroupPolicyChanges, ebx
0x18002de21  jz      short loc_18002DE34
0x18002de23  mov     rcx, cs:MachineGroupPolicyChangeWaitObject; WaitHandle
0x18002de2a  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002de2e  call    cs:__imp_UnregisterWaitEx
0x18002de34  cmp     cs:RegisteredForMachineGroupPolicyChangeNotifications, ebx
0x18002de3a  jz      short loc_18002DE49
0x18002de3c  mov     rcx, cs:MachineGroupPolicyChangeEvent; hEvent
0x18002de43  call    cs:__imp_UnregisterGPNotification
0x18002de49  mov     rcx, cs:MachineGroupPolicyChangeEvent; hObject
0x18002de50  test    rcx, rcx
0x18002de53  jz      short loc_18002DE5B
0x18002de55  call    cs:__imp_CloseHandle
0x18002de5b  call    WsShutdownWorkstation
0x18002de60  mov     rcx, rdi; lpCriticalSection
0x18002de63  mov     cs:WsIsTerminationHandlerRunning, ebx
0x18002de69  call    cs:__imp_LeaveCriticalSection
0x18002de6f  mov     rcx, rdi; lpCriticalSection
0x18002de72  call    cs:__imp_DeleteCriticalSection
0x18002de78  mov     cs:WsWorkerCriticalSectionInitialized, ebx
0x18002de7e  mov     rbx, [rsp+28h+arg_0]
0x18002de83  add     rsp, 20h
0x18002de87  pop     rdi
0x18002de88  retn
```
