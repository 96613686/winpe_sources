# ServiceMain

- ea: `0x180003150`
- end: `0x180003311`
- name: `ServiceMain`
- size: `449`
- prototype: `void()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800045d0`

## callees

- `0x180003150`
- `0x180003320`
- `0x180003450`
- `0x1800041e0`
- `0x1800042d4`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032d8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000328e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000328e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800031a3`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800031a3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003304`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180003304`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800031e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800031e2`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800031c2`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800031c2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800032c7`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180003170`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x180003170`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000321d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000321d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800032aa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x1800032aa`

## pseudocode

```c
void ServiceMain()
{
  DWORD inited; // eax
  DWORD v1; // ecx
  DWORD LastError; // eax
  int v3; // [rsp+50h] [rbp+8h] BYREF

  v3 = 1;
  SetProcessMitigationPolicy(16, &v3, 4);
  *(_OWORD *)&g_state.dwServiceType = 0;
  *(_OWORD *)&g_state.dwServiceSpecificExitCode = 0;
  *(_OWORD *)&hServiceStatus = 0;
  *(_OWORD *)&AuthenticationPackage = 0;
  xmmword_1800096E0 = 0;
  InitializeCriticalSection(&csForProcessCount);
  g_fIsCsInitialized = 1;
  g_hIOCP = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
  if ( g_hIOCP )
  {
    g_stopServiceEvent = CreateEventW(0, 0, 0, 0);
    if ( !g_stopServiceEvent )
    {
      GetLastError();
      goto LABEL_12;
    }
    inited = InitGlobalState();
    if ( !inited )
    {
      hServiceStatus = RegisterServiceCtrlHandlerExW(L"seclogon", ServiceHandler, 0);
      if ( !hServiceStatus )
      {
        v1 = 0;
LABEL_11:
        SetLastError(v1);
        goto LABEL_12;
      }
      inited = SeclStartRpcServer();
      if ( !inited )
      {
        inited = MySetServiceStatus(4, 0);
        if ( !inited )
          inited = (*(__int64 (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, _DWORD))(GlobalData + 192))(
                     &g_waitObject,
                     L"seclogon",
                     g_stopServiceEvent,
                     StopServiceCallback,
                     0,
                     0);
      }
    }
    v1 = inited;
    goto LABEL_11;
  }
LABEL_12:
  if ( GetLastError() )
  {
    if ( g_waitObject )
    {
      UnregisterWait(g_waitObject);
      g_waitObject = 0;
    }
    if ( g_stopServiceEvent )
    {
      CloseHandle(g_stopServiceEvent);
      g_stopServiceEvent = 0;
    }
    LastError = GetLastError();
    ServiceStop(1, LastError);
    if ( g_fIsCsInitialized )
    {
      g_fIsCsInitialized = 0;
      DeleteCriticalSection(&csForProcessCount);
    }
  }
}

```

## disassembly

```asm
0x180003150  mov     [rsp+arg_0], ecx
0x180003154  sub     rsp, 48h
0x180003158  mov     [rsp+48h+arg_0], 1
0x180003160  mov     r8d, 4
0x180003166  lea     rdx, [rsp+48h+arg_0]
0x18000316b  mov     ecx, 10h
0x180003170  call    cs:__imp_SetProcessMitigationPolicy
0x180003176  xorps   xmm0, xmm0
0x180003179  movups  xmmword ptr cs:g_state.dwServiceType, xmm0
0x180003180  movups  xmmword ptr cs:g_state.dwServiceSpecificExitCode, xmm0
0x180003187  movups  cs:hServiceStatus, xmm0
0x18000318e  movups  cs:AuthenticationPackage, xmm0
0x180003195  movups  cs:xmmword_1800096E0, xmm0
0x18000319c  lea     rcx, csForProcessCount; lpCriticalSection
0x1800031a3  call    cs:__imp_InitializeCriticalSection
0x1800031a9  mov     cs:g_fIsCsInitialized, 1
0x1800031b3  xor     r9d, r9d; NumberOfConcurrentThreads
0x1800031b6  xor     r8d, r8d; CompletionKey
0x1800031b9  xor     edx, edx; ExistingCompletionPort
0x1800031bb  mov     rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x1800031c2  call    cs:__imp_CreateIoCompletionPort
0x1800031c8  mov     cs:g_hIOCP, rax
0x1800031cf  test    rax, rax
0x1800031d2  jz      loc_180003294
0x1800031d8  xor     r9d, r9d; lpName
0x1800031db  xor     r8d, r8d; bInitialState
0x1800031de  xor     edx, edx; bManualReset
0x1800031e0  xor     ecx, ecx; lpEventAttributes
0x1800031e2  call    cs:__imp_CreateEventW
0x1800031e8  mov     cs:g_stopServiceEvent, rax
0x1800031ef  test    rax, rax
0x1800031f2  jnz     short loc_1800031FF
0x1800031f4  call    cs:__imp_GetLastError
0x1800031fa  jmp     loc_180003294
0x1800031ff  call    InitGlobalState
0x180003204  test    eax, eax
0x180003206  jnz     loc_18000328C
0x18000320c  xor     r8d, r8d; lpContext
0x18000320f  lea     rdx, ServiceHandler; lpHandlerProc
0x180003216  lea     rcx, ServiceName; "seclogon"
0x18000321d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180003223  mov     qword ptr cs:hServiceStatus, rax
0x18000322a  test    rax, rax
0x18000322d  jnz     short loc_180003233
0x18000322f  xor     ecx, ecx
0x180003231  jmp     short loc_18000328E
0x180003233  call    SeclStartRpcServer
0x180003238  test    eax, eax
0x18000323a  jnz     short loc_18000328C
0x18000323c  xor     edx, edx
0x18000323e  mov     ecx, 4
0x180003243  call    MySetServiceStatus
0x180003248  test    eax, eax
0x18000324a  jnz     short loc_18000328C
0x18000324c  mov     rax, cs:GlobalData
0x180003253  mov     [rsp+48h+var_20], 0
0x18000325b  mov     [rsp+48h+var_28], 0
0x180003264  lea     r9, StopServiceCallback
0x18000326b  mov     r8, cs:g_stopServiceEvent
0x180003272  lea     rdx, ServiceName; "seclogon"
0x180003279  lea     rcx, g_waitObject
0x180003280  mov     rax, [rax+0C0h]
0x180003287  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000328c  mov     ecx, eax; dwErrCode
0x18000328e  call    cs:__imp_SetLastError
0x180003294  call    cs:__imp_GetLastError
0x18000329a  test    eax, eax
0x18000329c  jz      short loc_18000330C
0x18000329e  mov     rcx, cs:g_waitObject; WaitHandle
0x1800032a5  test    rcx, rcx
0x1800032a8  jz      short loc_1800032BB
0x1800032aa  call    cs:__imp_UnregisterWait
0x1800032b0  mov     cs:g_waitObject, 0
0x1800032bb  mov     rcx, cs:g_stopServiceEvent; hObject
0x1800032c2  test    rcx, rcx
0x1800032c5  jz      short loc_1800032D8
0x1800032c7  call    cs:__imp_CloseHandle
0x1800032cd  mov     cs:g_stopServiceEvent, 0
0x1800032d8  call    cs:__imp_GetLastError
0x1800032de  mov     edx, eax
0x1800032e0  mov     ecx, 1
0x1800032e5  call    ServiceStop
0x1800032ea  cmp     cs:g_fIsCsInitialized, 0
0x1800032f1  jz      short loc_18000330C
0x1800032f3  mov     cs:g_fIsCsInitialized, 0
0x1800032fd  lea     rcx, csForProcessCount; lpCriticalSection
0x180003304  call    cs:__imp_DeleteCriticalSection
0x18000330a  jmp     short $+2
0x18000330c  add     rsp, 48h
0x180003310  retn
```
