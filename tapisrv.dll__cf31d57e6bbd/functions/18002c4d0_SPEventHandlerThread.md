# SPEventHandlerThread

- ea: `0x18002c4d0`
- end: `0x18002c8ce`
- name: `SPEventHandlerThread`
- size: `1022`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180017be0`
- `0x180024fc8`
- `0x1800281f0`
- `0x18002c448`
- `0x18002c4d0`
- `0x18002c8d4`
- `0x18003dc84`
- `0x18003e15c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c7fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c7fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c79f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002c79f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c7d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002c7d7`
- `RPCRT4!RpcCancelThread` at `0x18002c6ec`
- `RPCRT4!RpcCancelThread` at `0x18002c6ec`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002c88e`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002c88e`
- `KERNEL32!ResetEvent` at `0x18002c572`
- `KERNEL32!ResetEvent` at `0x18002c572`
- `KERNEL32!GetCurrentThread` at `0x18002c4ff`
- `KERNEL32!GetCurrentThread` at `0x18002c4ff`
- `KERNEL32!ExitThread` at `0x18002c8c7`
- `KERNEL32!ExitThread` at `0x18002c8c7`
- `KERNEL32!SetThreadPriority` at `0x18002c511`
- `KERNEL32!SetThreadPriority` at `0x18002c511`
- `KERNEL32!GetTickCount` at `0x18002c67c`
- `KERNEL32!GetTickCount` at `0x18002c67c`
- `KERNEL32!SetEvent` at `0x18002c8a0`
- `KERNEL32!SetEvent` at `0x18002c8a0`
- `KERNEL32!Sleep` at `0x18002c827`
- `KERNEL32!Sleep` at `0x18002c827`
- `KERNEL32!GetCurrentThreadId` at `0x18002c4e5`
- `KERNEL32!GetCurrentThreadId` at `0x18002c8a6`
- `KERNEL32!GetCurrentThreadId` at `0x18002c4e5`
- `KERNEL32!GetCurrentThreadId` at `0x18002c8a6`
- `KERNEL32!WaitForSingleObject` at `0x18002c538`
- `KERNEL32!WaitForSingleObject` at `0x18002c725`
- `KERNEL32!WaitForSingleObject` at `0x18002c538`
- `KERNEL32!WaitForSingleObject` at `0x18002c725`
- `KERNEL32!LeaveCriticalSection` at `0x18002c57c`
- `KERNEL32!LeaveCriticalSection` at `0x18002c57c`
- `KERNEL32!EnterCriticalSection` at `0x18002c542`
- `KERNEL32!EnterCriticalSection` at `0x18002c542`

## string_xrefs

- `0x18002c4eb`: `SPEventHandlerThread: enter (tid=%d)`
- `0x18002c51b`: `Could not raise priority of SPEventHandlerThread`
- `0x18002c5a5`: `Got an async completion event, requestID = 0x%x, htXxx = 0x%x, lResult = 0x%x`
- `0x18002c6bc`: `Calling RpcCancelThread on thread #%lx`
- `0x18002c873`: `SPEventHandlerThread: calling RpcServerUnregisterIf`
- `0x18002c8ac`: `SPEventHandlerThread: exit (pid=%d)`

## pseudocode

```c
void __fastcall __noreturn SPEventHandlerThread(char *lpThreadParameter)
{
  DWORD CurrentThreadId; // eax
  HANDLE CurrentThread; // rax
  __int64 *v4; // rbx
  __int64 *v5; // rdx
  __int64 *v6; // rax
  __int64 v7; // rcx
  int v8; // esi
  __int64 v9; // rcx
  unsigned int v10; // ebx
  DWORD TickCount; // r15d
  __int64 v12; // r14
  __int64 v13; // rsi
  int v14; // eax
  __int64 v15; // rdx
  unsigned int v16; // esi
  unsigned int i; // ebx
  DWORD v18; // eax
  int Data; // [rsp+70h] [rbp+40h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+48h] BYREF
  DWORD Type; // [rsp+80h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+58h] BYREF

  CurrentThreadId = GetCurrentThreadId();
  TRACELogPrint(262146, "SPEventHandlerThread: enter (tid=%d)", CurrentThreadId);
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 1) )
    TRACELogPrint(65538, "Could not raise priority of SPEventHandlerThread");
  while ( 1 )
  {
LABEL_3:
    v4 = 0;
    WaitForSingleObject(*((HANDLE *)lpThreadParameter + 2), gdwRpcTimeout);
    while ( 1 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 24));
      v5 = *(__int64 **)lpThreadParameter;
      if ( *(char **)lpThreadParameter == lpThreadParameter )
      {
        v8 = 0;
      }
      else
      {
        v6 = (__int64 *)v5[1];
        v4 = v5 - 1;
        v7 = *v5;
        v8 = 1;
        *v6 = *v5;
        *(_QWORD *)(v7 + 8) = v6;
      }
      if ( *(char **)lpThreadParameter == lpThreadParameter )
        ResetEvent(*((HANDLE *)lpThreadParameter + 2));
      LeaveCriticalSection((LPCRITICAL_SECTION)(lpThreadParameter + 24));
      if ( !v8 )
        break;
      switch ( *(_DWORD *)v4 )
      {
        case 1:
          TRACELogPrint(
            262146,
            "Got a line spevent, htLine = 0x%x, htCall = 0x%x, dwMsg = 0x%x",
            v4[3],
            v4[4],
            *((_DWORD *)v4 + 10));
          LineEventProc((void *)v4[3], (void *)v4[4], *((_DWORD *)v4 + 10), v4[6], (_QWORD *)v4[7], v4[8]);
LABEL_16:
          ServerFree(v4);
          break;
        case 3:
          TRACELogPrint(262146, "Got a phone spevent, htPhone = 0x%x, dwMsg = 0x%x", v4[3], *((_DWORD *)v4 + 10));
          PhoneEventProc(v4[3], *((_DWORD *)v4 + 10), v4[6], v4[7], v4[8]);
          goto LABEL_16;
        case 0x43595341:
          TRACELogPrint(
            262146,
            "Got an async completion event, requestID = 0x%x, htXxx = 0x%x, lResult = 0x%x",
            *((_DWORD *)v4 + 18),
            v4[3],
            *((_DWORD *)v4 + 10));
          CompletionProc((__int64)v4, *((_DWORD *)v4 + 10));
          DereferenceObject(v9, *((_DWORD *)v4 + 18), 1);
          break;
      }
    }
    if ( (dword_180051900 & 2) != 0 )
    {
      v10 = dword_180051D08;
      TickCount = GetTickCount();
      if ( v10 )
      {
        v12 = v10;
        do
        {
          --v12;
          --v10;
          v13 = 16 * v12;
          if ( *((_QWORD *)qword_180051D10 + 2 * v12 + 1)
            && TickCount - *(_DWORD *)((char *)qword_180051D10 + v13) > gdwRpcTimeout )
          {
            TRACELogPrint(
              262146,
              "Calling RpcCancelThread on thread #%lx",
              *((_QWORD *)gEventNotificationThreadParams + v12));
            *(_QWORD *)((char *)qword_180051D10 + v13 + 8) = 0;
            RpcCancelThread(*((void **)gEventNotificationThreadParams + v12));
          }
        }
        while ( v10 );
      }
    }
    if ( gbSPEventHandlerThreadExit )
    {
LABEL_47:
      v18 = GetCurrentThreadId();
      TRACELogPrint(524290, "SPEventHandlerThread: exit (pid=%d)", v18);
      _InterlockedDecrement(&glNumActiveSPEventHandlerThreads);
      ExitThread(0);
    }
    v14 = gbAutostartDone;
    if ( !gbAutostartDone && ghSCMAutostartEvent )
    {
      if ( WaitForSingleObject(ghSCMAutostartEvent, 0) )
      {
        v14 = gbAutostartDone;
      }
      else
      {
        v14 = 1;
        gbAutostartDone = 1;
      }
    }
    if ( !qword_180051908 && (dword_180051900 & 2) == 0 && gfWeHadAtLeastOneClient && v14 )
    {
      hKey = 0;
      Data = 120;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Telephony",
              0,
              0xF003Fu,
              &hKey) )
      {
        Type = 0;
        cbData = 4;
        if ( !RegQueryValueExW(hKey, L"DeferredShutdownTimeout", 0, &Type, (LPBYTE)&Data, &cbData) )
          TRACELogPrint(65538, "Overriding Shutdown Timeout: %lu", Data);
        RegCloseKey(hKey);
      }
      LODWORD(v15) = (274877907 * (unsigned __int64)(unsigned int)(1000 * Data)) >> 32;
      v16 = 1000 * Data / 0xFAu;
      for ( i = 0; i < v16; ++i )
      {
        if ( gbSPEventHandlerThreadExit )
          goto LABEL_44;
        Sleep(0xFAu);
        if ( qword_180051908 )
          goto LABEL_3;
      }
      if ( i == v16 )
      {
LABEL_44:
        if ( lpThreadParameter == aSPEventHandlerThreadInfo )
        {
          gdwServiceState = 3;
          gdwCheckPoint = 0;
          ReportStatusToSCMgr(3, v15, 0, *(unsigned int *)&gdwWaitHint);
          TRACELogPrint(524290, "SPEventHandlerThread: calling RpcServerUnregisterIf");
          RpcServerUnregisterIf(qword_180041EE0, 0, 1u);
          if ( ghEventService )
            SetEvent(ghEventService);
        }
        goto LABEL_47;
      }
    }
  }
}

```

## disassembly

```asm
0x18002c4d0  push    rbp
0x18002c4d2  push    rbx
0x18002c4d3  push    rsi
0x18002c4d4  push    rdi
0x18002c4d5  push    r12
0x18002c4d7  push    r14
0x18002c4d9  push    r15
0x18002c4db  mov     rbp, rsp
0x18002c4de  sub     rsp, 30h
0x18002c4e2  mov     rdi, rcx
0x18002c4e5  call    cs:__imp_GetCurrentThreadId
0x18002c4eb  lea     rdx, aSpeventhandler; "SPEventHandlerThread: enter (tid=%d)"
0x18002c4f2  mov     ecx, 40002h
0x18002c4f7  mov     r8d, eax
0x18002c4fa  call    TRACELogPrint
0x18002c4ff  call    cs:__imp_GetCurrentThread
0x18002c505  mov     r14d, 1
0x18002c50b  mov     rcx, rax; hThread
0x18002c50e  mov     edx, r14d; nPriority
0x18002c511  call    cs:__imp_SetThreadPriority
0x18002c517  test    eax, eax
0x18002c519  jnz     short loc_18002C52C
0x18002c51b  lea     rdx, aCouldNotRaiseP; "Could not raise priority of SPEventHand"...
0x18002c522  mov     ecx, 10002h
0x18002c527  call    TRACELogPrint
0x18002c52c  mov     edx, cs:gdwRpcTimeout; dwMilliseconds
0x18002c532  xor     ebx, ebx
0x18002c534  mov     rcx, [rdi+10h]; hHandle
0x18002c538  call    cs:__imp_WaitForSingleObject
0x18002c53e  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002c542  call    cs:__imp_EnterCriticalSection
0x18002c548  mov     rdx, [rdi]
0x18002c54b  cmp     rdx, rdi
0x18002c54e  jz      short loc_18002C567
0x18002c550  mov     rax, [rdx+8]
0x18002c554  lea     rbx, [rdx-8]
0x18002c558  mov     rcx, [rdx]
0x18002c55b  mov     esi, r14d
0x18002c55e  mov     [rax], rcx
0x18002c561  mov     [rcx+8], rax
0x18002c565  jmp     short loc_18002C569
0x18002c567  xor     esi, esi
0x18002c569  cmp     [rdi], rdi
0x18002c56c  jnz     short loc_18002C578
0x18002c56e  mov     rcx, [rdi+10h]; hEvent
0x18002c572  call    cs:__imp_ResetEvent
0x18002c578  lea     rcx, [rdi+18h]; lpCriticalSection
0x18002c57c  call    cs:__imp_LeaveCriticalSection
0x18002c582  test    esi, esi
0x18002c584  jz      loc_18002C669
0x18002c58a  mov     ecx, [rbx]
0x18002c58c  sub     ecx, 1
0x18002c58f  jz      loc_18002C615
0x18002c595  sub     ecx, 2
0x18002c598  jz      short loc_18002C5DD
0x18002c59a  cmp     ecx, 4359533Eh
0x18002c5a0  jnz     short loc_18002C53E
0x18002c5a2  mov     eax, [rbx+28h]
0x18002c5a5  lea     rdx, aGotAnAsyncComp; "Got an async completion event, requestI"...
0x18002c5ac  mov     r9, [rbx+18h]
0x18002c5b0  mov     ecx, 40002h
0x18002c5b5  mov     r8d, [rbx+48h]
0x18002c5b9  mov     dword ptr [rsp+30h+phkResult], eax
0x18002c5bd  call    TRACELogPrint
0x18002c5c2  mov     edx, [rbx+28h]
0x18002c5c5  mov     rcx, rbx
0x18002c5c8  call    CompletionProc
0x18002c5cd  mov     edx, [rbx+48h]
0x18002c5d0  mov     r8d, r14d
0x18002c5d3  call    DereferenceObject
0x18002c5d8  jmp     loc_18002C53E
0x18002c5dd  mov     r9d, [rbx+28h]
0x18002c5e1  lea     rdx, aGotAPhoneSpeve; "Got a phone spevent, htPhone = 0x%x, dw"...
0x18002c5e8  mov     r8, [rbx+18h]
0x18002c5ec  mov     ecx, 40002h
0x18002c5f1  call    TRACELogPrint
0x18002c5f6  mov     rax, [rbx+40h]
0x18002c5fa  mov     r9, [rbx+38h]
0x18002c5fe  mov     r8, [rbx+30h]
0x18002c602  mov     edx, [rbx+28h]
0x18002c605  mov     rcx, [rbx+18h]
0x18002c609  mov     [rsp+30h+phkResult], rax
0x18002c60e  call    PhoneEventProc
0x18002c613  jmp     short loc_18002C65C
0x18002c615  mov     eax, [rbx+28h]
0x18002c618  lea     rdx, aGotALineSpeven; "Got a line spevent, htLine = 0x%x, htCa"...
0x18002c61f  mov     r9, [rbx+20h]
0x18002c623  mov     ecx, 40002h
0x18002c628  mov     r8, [rbx+18h]
0x18002c62c  mov     dword ptr [rsp+30h+phkResult], eax
0x18002c630  call    TRACELogPrint
0x18002c635  mov     rax, [rbx+40h]
0x18002c639  mov     r9, [rbx+30h]
0x18002c63d  mov     r8d, [rbx+28h]
0x18002c641  mov     rdx, [rbx+20h]
0x18002c645  mov     rcx, [rbx+18h]
0x18002c649  mov     [rsp+30h+lpcbData], rax
0x18002c64e  mov     rax, [rbx+38h]
0x18002c652  mov     [rsp+30h+phkResult], rax
0x18002c657  call    LineEventProc
0x18002c65c  mov     rcx, rbx; lpMem
0x18002c65f  call    ServerFree
0x18002c664  jmp     loc_18002C53E
0x18002c669  test    byte ptr cs:dword_180051900, 2
0x18002c670  jz      loc_18002C6FA
0x18002c676  mov     ebx, cs:dword_180051D08
0x18002c67c  call    cs:__imp_GetTickCount
0x18002c682  mov     r15d, eax
0x18002c685  test    ebx, ebx
0x18002c687  jz      short loc_18002C6FA
0x18002c689  mov     r14d, ebx
0x18002c68c  mov     rcx, cs:qword_180051D10
0x18002c693  dec     r14
0x18002c696  mov     rsi, r14
0x18002c699  dec     ebx
0x18002c69b  shl     rsi, 4
0x18002c69f  cmp     qword ptr [rsi+rcx+8], 0
0x18002c6a5  jz      short loc_18002C6F2
0x18002c6a7  mov     eax, r15d
0x18002c6aa  sub     eax, [rsi+rcx]
0x18002c6ad  cmp     eax, cs:gdwRpcTimeout
0x18002c6b3  jbe     short loc_18002C6F2
0x18002c6b5  mov     r8, cs:gEventNotificationThreadParams
0x18002c6bc  lea     rdx, aCallingRpccanc; "Calling RpcCancelThread on thread #%lx"
0x18002c6c3  mov     ecx, 40002h
0x18002c6c8  mov     r8, [r8+r14*8]
0x18002c6cc  call    TRACELogPrint
0x18002c6d1  mov     rax, cs:qword_180051D10
0x18002c6d8  mov     qword ptr [rsi+rax+8], 0
0x18002c6e1  mov     rcx, cs:gEventNotificationThreadParams
0x18002c6e8  mov     rcx, [rcx+r14*8]; Thread
0x18002c6ec  call    cs:__imp_RpcCancelThread
0x18002c6f2  test    ebx, ebx
0x18002c6f4  jnz     short loc_18002C68C
0x18002c6f6  lea     r14d, [rbx+1]
0x18002c6fa  cmp     cs:gbSPEventHandlerThreadExit, 0
0x18002c701  mov     r15d, 80002h
0x18002c707  jnz     loc_18002C8A6
0x18002c70d  mov     eax, cs:gbAutostartDone
0x18002c713  test    eax, eax
0x18002c715  jnz     short loc_18002C740
0x18002c717  mov     rcx, cs:ghSCMAutostartEvent; hHandle
0x18002c71e  test    rcx, rcx
0x18002c721  jz      short loc_18002C740
0x18002c723  xor     edx, edx; dwMilliseconds
0x18002c725  call    cs:__imp_WaitForSingleObject
0x18002c72b  test    eax, eax
0x18002c72d  jnz     short loc_18002C73A
0x18002c72f  mov     eax, r14d
0x18002c732  mov     cs:gbAutostartDone, eax
0x18002c738  jmp     short loc_18002C740
0x18002c73a  mov     eax, cs:gbAutostartDone
0x18002c740  cmp     cs:qword_180051908, 0
0x18002c748  jnz     loc_18002C52C
0x18002c74e  test    byte ptr cs:dword_180051900, 2
0x18002c755  jnz     loc_18002C52C
0x18002c75b  cmp     cs:gfWeHadAtLeastOneClient, 0
0x18002c762  jz      loc_18002C52C
0x18002c768  test    eax, eax
0x18002c76a  jz      loc_18002C52C
0x18002c770  lea     rax, [rbp+hKey]
0x18002c774  mov     [rbp+hKey], 0
0x18002c77c  mov     r9d, 0F003Fh; samDesired
0x18002c782  mov     [rsp+30h+phkResult], rax; phkResult
0x18002c787  xor     r8d, r8d; ulOptions
0x18002c78a  mov     [rbp+Data], 78h ; 'x'
0x18002c791  lea     rdx, gszRegKeyTelephony; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002c798  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c79f  call    cs:__imp_RegOpenKeyExW
0x18002c7a5  test    eax, eax
0x18002c7a7  jnz     short loc_18002C800
0x18002c7a9  mov     rcx, [rbp+hKey]; hKey
0x18002c7ad  lea     r9, [rbp+Type]; lpType
0x18002c7b1  mov     [rbp+Type], eax
0x18002c7b4  lea     rdx, aDeferredshutdo; "DeferredShutdownTimeout"
0x18002c7bb  lea     rax, [rbp+cbData]
0x18002c7bf  mov     [rbp+cbData], 4
0x18002c7c6  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002c7cb  xor     r8d, r8d; lpReserved
0x18002c7ce  lea     rax, [rbp+Data]
0x18002c7d2  mov     [rsp+30h+phkResult], rax; lpData
0x18002c7d7  call    cs:__imp_RegQueryValueExW
0x18002c7dd  test    eax, eax
0x18002c7df  jnz     short loc_18002C7F6
0x18002c7e1  mov     r8d, [rbp+Data]
0x18002c7e5  lea     rdx, aOverridingShut; "Overriding Shutdown Timeout: %lu"
0x18002c7ec  mov     ecx, 10002h
0x18002c7f1  call    TRACELogPrint
0x18002c7f6  mov     rcx, [rbp+hKey]; hKey
0x18002c7fa  call    cs:__imp_RegCloseKey
0x18002c800  imul    ecx, [rbp+Data], 3E8h
0x18002c807  mov     eax, 10624DD3h
0x18002c80c  mul     ecx
0x18002c80e  mov     esi, edx
0x18002c810  shr     esi, 4
0x18002c813  xor     ebx, ebx
0x18002c815  cmp     ebx, esi
0x18002c817  jnb     short loc_18002C840
0x18002c819  cmp     cs:gbSPEventHandlerThreadExit, 0
0x18002c820  jnz     short loc_18002C846
0x18002c822  mov     ecx, 0FAh; dwMilliseconds
0x18002c827  call    cs:__imp_Sleep
0x18002c82d  cmp     cs:qword_180051908, 0
0x18002c835  jnz     loc_18002C52C
0x18002c83b  add     ebx, r14d
0x18002c83e  jmp     short loc_18002C815
0x18002c840  jnz     loc_18002C52C
0x18002c846  cmp     rdi, cs:aSPEventHandlerThreadInfo
0x18002c84d  jnz     short loc_18002C8A6
0x18002c84f  mov     r9d, cs:gdwWaitHint
0x18002c856  mov     ecx, 3
0x18002c85b  xor     r8d, r8d
0x18002c85e  mov     cs:gdwServiceState, ecx
0x18002c864  mov     cs:gdwCheckPoint, 0
0x18002c86e  call    ReportStatusToSCMgr
0x18002c873  lea     rdx, aSpeventhandler_1; "SPEventHandlerThread: calling RpcServer"...
0x18002c87a  mov     ecx, r15d
0x18002c87d  call    TRACELogPrint
0x18002c882  mov     r8d, r14d; WaitForCallsToComplete
0x18002c885  lea     rcx, qword_180041EE0; IfSpec
0x18002c88c  xor     edx, edx; MgrTypeUuid
0x18002c88e  call    cs:__imp_RpcServerUnregisterIf
0x18002c894  mov     rcx, cs:ghEventService; hEvent
0x18002c89b  test    rcx, rcx
0x18002c89e  jz      short loc_18002C8A6
0x18002c8a0  call    cs:__imp_SetEvent
0x18002c8a6  call    cs:__imp_GetCurrentThreadId
0x18002c8ac  lea     rdx, aSpeventhandler_0; "SPEventHandlerThread: exit (pid=%d)"
0x18002c8b3  mov     ecx, r15d
0x18002c8b6  mov     r8d, eax
0x18002c8b9  call    TRACELogPrint
0x18002c8be  lock dec cs:glNumActiveSPEventHandlerThreads
0x18002c8c5  xor     ecx, ecx; dwExitCode
0x18002c8c7  call    cs:__imp_ExitThread
```
