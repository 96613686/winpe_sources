# SPOOLER_main(ulong,ushort * * const)

- ea: `0x14004c580`
- end: `0x14004c854`
- name: `?SPOOLER_main@@YAXKQEAPEAG@Z`
- size: `724`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140031894`

## callees

- `0x14001748c`
- `0x140031720`
- `0x14003e46c`
- `0x14003ef6c`
- `0x1400408b4`
- `0x14004c580`
- `0x14004c85c`
- `0x14004d2d4`
- `0x14004d3e0`
- `0x14004d420`
- `0x14004d74c`
- `0x14005b8a4`
- `0x14005bdb8`
- `0x14005be1c`
- `0x14005cc80`
- `0x14005cd4c`
- `0x14005e898`
- `0x14006e138`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004c6f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14004c6f3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004c762`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14004c762`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004c655`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14004c655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c5fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c5fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004c813`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x14004c78b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x14004c78b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14004c5e9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14004c5e9`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x14004c83c`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x14004c83c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004c5bd`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004c61f`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004c6e4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004c5bd`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004c61f`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004c6e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004c775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004c79a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004c7b2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004c775`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004c79a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14004c7b2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004c805`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14004c805`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14004c6ba`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14004c6ba`

## string_xrefs

- `0x14004c671`: `Spooler service starting...`
- `0x14004c609`: `Failed to create IPC processing thread %d`
- `0x14004c63a`: `Failed to create the Restricted Spooler Worker virtual service account %d`
- `0x14004c72a`: `Spooler shutdown during initialization`
- `0x14004c7c8`: `Spooler service stopped`
- `0x14004c81f`: `Failed to create termination event, LE: %d`

## pseudocode

```c
void __fastcall SPOOLER_main(__int64 a1, unsigned __int16 **const a2)
{
  UINT v2; // eax
  UINT v3; // ebx
  HANDLE Thread; // rbx
  __int64 LastError; // rbx
  int ServiceAccount; // eax
  char v7; // di
  int v8; // eax
  int v9; // esi
  HMODULE ModuleHandleW; // rax
  unsigned __int16 **v11; // rdx
  int v12; // ecx
  int v13; // r8d
  unsigned int v14; // eax
  int v15; // eax
  DWORD v16; // eax

  if ( g_bSpoolerIsChildProcess )
  {
    v2 = SplIpcInitialize();
    v3 = v2;
    if ( v2 )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError("SPOOLER_main", L"SplIpcInitialize failed %d", v2);
      ExitProcess(v3);
    }
    Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SPOOLER_ProcessIpcMessages, 0, 0, 0);
    if ( !Thread )
    {
      LastError = GetLastError();
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SPOOLER_main",
        L"Failed to create IPC processing thread %d",
        LastError);
      ExitProcess(LastError);
    }
  }
  else
  {
    Thread = 0;
    ServiceAccount = SpoolerCreateServiceAccount();
    if ( ServiceAccount < 0 )
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SPOOLER_main",
        L"Failed to create the Restricted Spooler Worker virtual service account %d",
        (unsigned int)ServiceAccount);
  }
  TerminateEvent = CreateEventW(0, 1, 0, 0);
  if ( TerminateEvent )
  {
    v7 = 0;
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SPOOLER_main", L"Spooler service starting...");
    SplEventLogRegister();
    RegisterSplVectoredHandler();
    McGenEventRegister_EtwEventRegister();
    v8 = UalOpenSession();
    if ( v8 < 0 )
    {
      v9 = 0;
      SpoolerServiceTelemetry::WriteDbgTraceError(
        "SPOOLER_main",
        L"UAL session for the Print Server role cannot be started: 0x%x",
        (unsigned int)v8);
    }
    else
    {
      v9 = 1;
    }
    if ( CoInitializeEx(0, 0) >= 0 )
    {
      v7 = 1;
      if ( (int)SetCOMGlobalOptions() < 0 )
      {
        if ( (unsigned int)IsWindowsProtectedPrintEnabled() )
          ExitProcess(1u);
      }
    }
    ModuleHandleW = GetModuleHandleW(0);
    if ( !(unsigned int)PrvSpoolssInit(ModuleHandleW) )
      SpoolerServiceTelemetry::WriteDbgTraceError("SPOOLER_main", L"Router initialization failed");
    v14 = SpoolerInitializeSpooler(v12, v11, v13);
    SpoolerState = v14;
    if ( v14 != 2 )
    {
      SpoolerServiceTelemetry::WriteDbgTraceError("SPOOLER_main", L"Spooler shutdown during initialization");
      v14 = SpoolerState;
    }
    if ( v14 == 3 )
      SpoolerShutdown();
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SPOOLER_main", L"Waiting for termination event...");
    WaitForSingleObject(TerminateEvent, 0xFFFFFFFF);
    CloseHandle(TerminateEvent);
    if ( Thread )
    {
      TerminateThread(Thread, 0);
      CloseHandle(Thread);
    }
    if ( hPhase2Init )
      CloseHandle(hPhase2Init);
    SpoolerStatusUpdate(4u);
    SpoolerServiceTelemetry::WriteDbgTraceInfo("SPOOLER_main", L"Spooler service stopped");
    if ( v9 )
    {
      v15 = UalCloseSession();
      if ( v15 < 0 )
        SpoolerServiceTelemetry::WriteDbgTraceError(
          "SPOOLER_main",
          L"UAL session for the Print Server role cannot be stopped: 0x%x",
          (unsigned int)v15);
    }
    McGenEventUnregister_EtwEventUnregister();
    SplEventLogUnregister();
    if ( v7 )
      CoUninitialize();
  }
  else
  {
    v16 = GetLastError();
    SpoolerServiceTelemetry::WriteDbgTraceError("SPOOLER_main", L"Failed to create termination event, LE: %d", v16);
  }
  if ( !g_bSpoolerIsChildProcess )
    ExitThread(0);
}

```

## disassembly

```asm
0x14004c580  push    rbx
0x14004c582  push    rsi
0x14004c583  push    rdi
0x14004c584  push    r14
0x14004c586  sub     rsp, 38h
0x14004c58a  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, 0; bool g_bSpoolerIsChildProcess
0x14004c591  lea     r14, aSpoolerMain; "SPOOLER_main"
0x14004c598  jz      loc_14004C62C
0x14004c59e  call    ?SplIpcInitialize@@YAJXZ; SplIpcInitialize(void)
0x14004c5a3  mov     ebx, eax
0x14004c5a5  test    eax, eax
0x14004c5a7  jz      short loc_14004C5CA
0x14004c5a9  mov     r8d, eax
0x14004c5ac  lea     rdx, aSplipcinitiali_0; "SplIpcInitialize failed %d"
0x14004c5b3  mov     rcx, r14; char *
0x14004c5b6  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c5bb  mov     ecx, ebx; uExitCode
0x14004c5bd  call    cs:__imp_ExitProcess
0x14004c5ca  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x14004c5d3  lea     r8, ?SPOOLER_ProcessIpcMessages@@YAKPEAX@Z; lpStartAddress
0x14004c5da  xor     r9d, r9d; lpParameter
0x14004c5dd  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14004c5e5  xor     edx, edx; dwStackSize
0x14004c5e7  xor     ecx, ecx; lpThreadAttributes
0x14004c5e9  call    cs:__imp_CreateThread
0x14004c5f0  nop     dword ptr [rax+rax+00h]
0x14004c5f5  mov     rbx, rax
0x14004c5f8  test    rax, rax
0x14004c5fb  jnz     short loc_14004C649
0x14004c5fd  call    cs:__imp_GetLastError
0x14004c604  nop     dword ptr [rax+rax+00h]
0x14004c609  lea     rdx, aFailedToCreate_11; "Failed to create IPC processing thread "...
0x14004c610  mov     rcx, r14; char *
0x14004c613  mov     r8d, eax
0x14004c616  mov     ebx, eax
0x14004c618  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c61d  mov     ecx, ebx; uExitCode
0x14004c61f  call    cs:__imp_ExitProcess
0x14004c62c  xor     ebx, ebx
0x14004c62e  call    ?SpoolerCreateServiceAccount@@YAJXZ; SpoolerCreateServiceAccount(void)
0x14004c633  test    eax, eax
0x14004c635  jns     short loc_14004C649
0x14004c637  mov     r8d, eax
0x14004c63a  lea     rdx, aFailedToCreate_12; "Failed to create the Restricted Spooler"...
0x14004c641  mov     rcx, r14; char *
0x14004c644  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c649  xor     r9d, r9d; lpName
0x14004c64c  xor     r8d, r8d; bInitialState
0x14004c64f  xor     ecx, ecx; lpEventAttributes
0x14004c651  lea     edx, [r9+1]; bManualReset
0x14004c655  call    cs:__imp_CreateEventW
0x14004c65c  nop     dword ptr [rax+rax+00h]
0x14004c661  mov     cs:?TerminateEvent@@3PEAXEA, rax; void * TerminateEvent
0x14004c668  test    rax, rax
0x14004c66b  jz      loc_14004C813
0x14004c671  lea     rdx, aSpoolerService; "Spooler service starting..."
0x14004c678  mov     rcx, r14; char *
0x14004c67b  xor     dil, dil
0x14004c67e  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004c683  call    ?SplEventLogRegister@@YAKXZ; SplEventLogRegister(void)
0x14004c688  call    RegisterSplVectoredHandler
0x14004c68d  call    McGenEventRegister_EtwEventRegister
0x14004c692  call    UalOpenSession
0x14004c697  test    eax, eax
0x14004c699  js      short loc_14004C6A2
0x14004c69b  mov     esi, 1
0x14004c6a0  jmp     short loc_14004C6B6
0x14004c6a2  xor     esi, esi
0x14004c6a4  lea     rdx, aUalSessionForT; "UAL session for the Print Server role c"...
0x14004c6ab  mov     r8d, eax
0x14004c6ae  mov     rcx, r14; char *
0x14004c6b1  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c6b6  xor     edx, edx; dwCoInit
0x14004c6b8  xor     ecx, ecx; pvReserved
0x14004c6ba  call    cs:__imp_CoInitializeEx
0x14004c6c1  nop     dword ptr [rax+rax+00h]
0x14004c6c6  test    eax, eax
0x14004c6c8  js      short loc_14004C6F1
0x14004c6ca  mov     dil, 1
0x14004c6cd  call    SetCOMGlobalOptions
0x14004c6d2  test    eax, eax
0x14004c6d4  jns     short loc_14004C6F1
0x14004c6d6  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x14004c6db  test    eax, eax
0x14004c6dd  jz      short loc_14004C6F1
0x14004c6df  mov     ecx, 1; uExitCode
0x14004c6e4  call    cs:__imp_ExitProcess
0x14004c6f1  xor     ecx, ecx; lpModuleName
0x14004c6f3  call    cs:__imp_GetModuleHandleW
0x14004c6fa  nop     dword ptr [rax+rax+00h]
0x14004c6ff  mov     rcx, rax; hLibModule
0x14004c702  call    ?PrvSpoolssInit@@YAHPEAUHINSTANCE__@@@Z; PrvSpoolssInit(HINSTANCE__ *)
0x14004c707  test    eax, eax
0x14004c709  jnz     short loc_14004C71A
0x14004c70b  lea     rdx, aRouterInitiali; "Router initialization failed"
0x14004c712  mov     rcx, r14; char *
0x14004c715  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c71a  call    ?SpoolerInitializeSpooler@@YAKKPEAPEAG@Z; SpoolerInitializeSpooler(ulong,ushort * *)
0x14004c71f  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x14004c725  cmp     eax, 2
0x14004c728  jz      short loc_14004C73F
0x14004c72a  lea     rdx, aSpoolerShutdow_0; "Spooler shutdown during initialization"
0x14004c731  mov     rcx, r14; char *
0x14004c734  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c739  mov     eax, cs:?SpoolerState@@3KA; ulong SpoolerState
0x14004c73f  cmp     eax, 3
0x14004c742  jnz     short loc_14004C749
0x14004c744  call    ?SpoolerShutdown@@YAXXZ; SpoolerShutdown(void)
0x14004c749  lea     rdx, aWaitingForTerm; "Waiting for termination event..."
0x14004c750  mov     rcx, r14; char *
0x14004c753  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004c758  mov     rcx, cs:?TerminateEvent@@3PEAXEA; hHandle
0x14004c75f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14004c762  call    cs:__imp_WaitForSingleObject
0x14004c769  nop     dword ptr [rax+rax+00h]
0x14004c76e  mov     rcx, cs:?TerminateEvent@@3PEAXEA; hObject
0x14004c775  call    cs:__imp_CloseHandle
0x14004c77c  nop     dword ptr [rax+rax+00h]
0x14004c781  test    rbx, rbx
0x14004c784  jz      short loc_14004C7A6
0x14004c786  xor     edx, edx; dwExitCode
0x14004c788  mov     rcx, rbx; hThread
0x14004c78b  call    cs:__imp_TerminateThread
0x14004c792  nop     dword ptr [rax+rax+00h]
0x14004c797  mov     rcx, rbx; hObject
0x14004c79a  call    cs:__imp_CloseHandle
0x14004c7a1  nop     dword ptr [rax+rax+00h]
0x14004c7a6  mov     rcx, cs:?hPhase2Init@@3PEAXEA; hObject
0x14004c7ad  test    rcx, rcx
0x14004c7b0  jz      short loc_14004C7BE
0x14004c7b2  call    cs:__imp_CloseHandle
0x14004c7b9  nop     dword ptr [rax+rax+00h]
0x14004c7be  mov     ecx, 4; unsigned int
0x14004c7c3  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x14004c7c8  lea     rdx, aSpoolerService_0; "Spooler service stopped"
0x14004c7cf  mov     rcx, r14; char *
0x14004c7d2  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14004c7d7  test    esi, esi
0x14004c7d9  jz      short loc_14004C7F6
0x14004c7db  call    UalCloseSession
0x14004c7e0  test    eax, eax
0x14004c7e2  jns     short loc_14004C7F6
0x14004c7e4  mov     r8d, eax
0x14004c7e7  lea     rdx, aUalSessionForT_0; "UAL session for the Print Server role c"...
0x14004c7ee  mov     rcx, r14; char *
0x14004c7f1  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c7f6  call    McGenEventUnregister_EtwEventUnregister
0x14004c7fb  call    ?SplEventLogUnregister@@YAKXZ; SplEventLogUnregister(void)
0x14004c800  test    dil, dil
0x14004c803  jz      short loc_14004C831
0x14004c805  call    cs:__imp_CoUninitialize
0x14004c80c  nop     dword ptr [rax+rax+00h]
0x14004c811  jmp     short loc_14004C831
0x14004c813  call    cs:__imp_GetLastError
0x14004c81a  nop     dword ptr [rax+rax+00h]
0x14004c81f  lea     rdx, aFailedToCreate_6; "Failed to create termination event, LE:"...
0x14004c826  mov     rcx, r14; char *
0x14004c829  mov     r8d, eax
0x14004c82c  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14004c831  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, 0; bool g_bSpoolerIsChildProcess
0x14004c838  jnz     short loc_14004C849
0x14004c83a  xor     ecx, ecx; dwExitCode
0x14004c83c  call    cs:__imp_ExitThread
0x14004c849  add     rsp, 38h
0x14004c84d  pop     r14
0x14004c84f  pop     rdi
0x14004c850  pop     rsi
0x14004c851  pop     rbx
0x14004c852  retn
```
