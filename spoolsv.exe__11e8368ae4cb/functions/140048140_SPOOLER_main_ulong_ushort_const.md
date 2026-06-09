# SPOOLER_main(ulong,ushort * * const)

- ea: `0x140048140`
- end: `0x1400483af`
- name: `?SPOOLER_main@@YAXKQEAPEAG@Z`
- size: `623`
- prototype: `void __fastcall(unsigned int, unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14002f198`

## callees

- `0x1400160a0`
- `0x14002f030`
- `0x14003ae08`
- `0x14003b7dc`
- `0x14003cf44`
- `0x140048140`
- `0x1400483b8`
- `0x140048cac`
- `0x140048d9c`
- `0x140048dd4`
- `0x1400490bc`
- `0x140056430`
- `0x1400568dc`
- `0x14005693c`
- `0x14005765c`
- `0x140057720`
- `0x1400590f0`
- `0x1400679f4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140048285`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140048285`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400482ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400482ee`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400481f9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400481f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400481ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004837b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400481ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004837b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x14004830b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x14004830b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14004819f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14004819f`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x14004839e`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x14004839e`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140048179`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400481c9`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004827c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140048179`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400481c9`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14004827c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400482fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048314`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048326`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400482fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048314`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140048326`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140048373`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140048373`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140048258`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140048258`

## string_xrefs

- `0x14004820f`: `Spooler service starting...`
- `0x1400481b3`: `Failed to create IPC processing thread %d`
- `0x1400481de`: `Failed to create the Restricted Spooler Worker virtual service account %d`
- `0x1400482b6`: `Spooler shutdown during initialization`
- `0x140048336`: `Spooler service stopped`
- `0x140048381`: `Failed to create termination event, LE: %d`

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
    Thread = CreateThread(0, 0, SPOOLER_ProcessIpcMessages, 0, 0, 0);
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
0x140048140  push    rbx
0x140048142  push    rsi
0x140048143  push    rdi
0x140048144  push    r14
0x140048146  sub     rsp, 38h
0x14004814a  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, 0; bool g_bSpoolerIsChildProcess
0x140048151  lea     r14, aSpoolerMain; "SPOOLER_main"
0x140048158  jz      short loc_1400481D0
0x14004815a  call    ?SplIpcInitialize@@YAJXZ; SplIpcInitialize(void)
0x14004815f  mov     ebx, eax
0x140048161  test    eax, eax
0x140048163  jz      short loc_140048180
0x140048165  mov     r8d, eax
0x140048168  lea     rdx, aSplipcinitiali_0; "SplIpcInitialize failed %d"
0x14004816f  mov     rcx, r14; char *
0x140048172  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140048177  mov     ecx, ebx; uExitCode
0x140048179  call    cs:__imp_ExitProcess
0x140048180  mov     [rsp+58h+lpThreadId], 0; lpThreadId
0x140048189  lea     r8, ?SPOOLER_ProcessIpcMessages@@YAKPEAX@Z; lpStartAddress
0x140048190  xor     r9d, r9d; lpParameter
0x140048193  mov     [rsp+58h+dwCreationFlags], 0; dwCreationFlags
0x14004819b  xor     edx, edx; dwStackSize
0x14004819d  xor     ecx, ecx; lpThreadAttributes
0x14004819f  call    cs:__imp_CreateThread
0x1400481a5  mov     rbx, rax
0x1400481a8  test    rax, rax
0x1400481ab  jnz     short loc_1400481ED
0x1400481ad  call    cs:__imp_GetLastError
0x1400481b3  lea     rdx, aFailedToCreate_11; "Failed to create IPC processing thread "...
0x1400481ba  mov     rcx, r14; char *
0x1400481bd  mov     r8d, eax
0x1400481c0  mov     ebx, eax
0x1400481c2  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400481c7  mov     ecx, ebx; uExitCode
0x1400481c9  call    cs:__imp_ExitProcess
0x1400481d0  xor     ebx, ebx
0x1400481d2  call    ?SpoolerCreateServiceAccount@@YAJXZ; SpoolerCreateServiceAccount(void)
0x1400481d7  test    eax, eax
0x1400481d9  jns     short loc_1400481ED
0x1400481db  mov     r8d, eax
0x1400481de  lea     rdx, aFailedToCreate_12; "Failed to create the Restricted Spooler"...
0x1400481e5  mov     rcx, r14; char *
0x1400481e8  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400481ed  xor     r9d, r9d; lpName
0x1400481f0  xor     r8d, r8d; bInitialState
0x1400481f3  xor     ecx, ecx; lpEventAttributes
0x1400481f5  lea     edx, [r9+1]; bManualReset
0x1400481f9  call    cs:__imp_CreateEventW
0x1400481ff  mov     cs:?TerminateEvent@@3PEAXEA, rax; void * TerminateEvent
0x140048206  test    rax, rax
0x140048209  jz      loc_14004837B
0x14004820f  lea     rdx, aSpoolerService; "Spooler service starting..."
0x140048216  mov     rcx, r14; char *
0x140048219  xor     dil, dil
0x14004821c  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140048221  call    ?SplEventLogRegister@@YAKXZ; SplEventLogRegister(void)
0x140048226  call    RegisterSplVectoredHandler
0x14004822b  call    McGenEventRegister_EtwEventRegister
0x140048230  call    UalOpenSession
0x140048235  test    eax, eax
0x140048237  js      short loc_140048240
0x140048239  mov     esi, 1
0x14004823e  jmp     short loc_140048254
0x140048240  xor     esi, esi
0x140048242  lea     rdx, aUalSessionForT; "UAL session for the Print Server role c"...
0x140048249  mov     r8d, eax
0x14004824c  mov     rcx, r14; char *
0x14004824f  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140048254  xor     edx, edx; dwCoInit
0x140048256  xor     ecx, ecx; pvReserved
0x140048258  call    cs:__imp_CoInitializeEx
0x14004825e  test    eax, eax
0x140048260  js      short loc_140048283
0x140048262  mov     dil, 1
0x140048265  call    SetCOMGlobalOptions
0x14004826a  test    eax, eax
0x14004826c  jns     short loc_140048283
0x14004826e  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x140048273  test    eax, eax
0x140048275  jz      short loc_140048283
0x140048277  mov     ecx, 1; uExitCode
0x14004827c  call    cs:__imp_ExitProcess
0x140048283  xor     ecx, ecx; lpModuleName
0x140048285  call    cs:__imp_GetModuleHandleW
0x14004828b  mov     rcx, rax; hLibModule
0x14004828e  call    ?PrvSpoolssInit@@YAHPEAUHINSTANCE__@@@Z; PrvSpoolssInit(HINSTANCE__ *)
0x140048293  test    eax, eax
0x140048295  jnz     short loc_1400482A6
0x140048297  lea     rdx, aRouterInitiali; "Router initialization failed"
0x14004829e  mov     rcx, r14; char *
0x1400482a1  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400482a6  call    ?SpoolerInitializeSpooler@@YAKKPEAPEAG@Z; SpoolerInitializeSpooler(ulong,ushort * *)
0x1400482ab  mov     cs:?SpoolerState@@3KA, eax; ulong SpoolerState
0x1400482b1  cmp     eax, 2
0x1400482b4  jz      short loc_1400482CB
0x1400482b6  lea     rdx, aSpoolerShutdow_0; "Spooler shutdown during initialization"
0x1400482bd  mov     rcx, r14; char *
0x1400482c0  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400482c5  mov     eax, cs:?SpoolerState@@3KA; ulong SpoolerState
0x1400482cb  cmp     eax, 3
0x1400482ce  jnz     short loc_1400482D5
0x1400482d0  call    ?SpoolerShutdown@@YAXXZ; SpoolerShutdown(void)
0x1400482d5  lea     rdx, aWaitingForTerm; "Waiting for termination event..."
0x1400482dc  mov     rcx, r14; char *
0x1400482df  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400482e4  mov     rcx, cs:?TerminateEvent@@3PEAXEA; hHandle
0x1400482eb  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1400482ee  call    cs:__imp_WaitForSingleObject
0x1400482f4  mov     rcx, cs:?TerminateEvent@@3PEAXEA; hObject
0x1400482fb  call    cs:__imp_CloseHandle
0x140048301  test    rbx, rbx
0x140048304  jz      short loc_14004831A
0x140048306  xor     edx, edx; dwExitCode
0x140048308  mov     rcx, rbx; hThread
0x14004830b  call    cs:__imp_TerminateThread
0x140048311  mov     rcx, rbx; hObject
0x140048314  call    cs:__imp_CloseHandle
0x14004831a  mov     rcx, cs:?hPhase2Init@@3PEAXEA; hObject
0x140048321  test    rcx, rcx
0x140048324  jz      short loc_14004832C
0x140048326  call    cs:__imp_CloseHandle
0x14004832c  mov     ecx, 4; unsigned int
0x140048331  call    ?SpoolerStatusUpdate@@YAKK@Z; SpoolerStatusUpdate(ulong)
0x140048336  lea     rdx, aSpoolerService_0; "Spooler service stopped"
0x14004833d  mov     rcx, r14; char *
0x140048340  call    ?WriteDbgTraceInfo@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140048345  test    esi, esi
0x140048347  jz      short loc_140048364
0x140048349  call    UalCloseSession
0x14004834e  test    eax, eax
0x140048350  jns     short loc_140048364
0x140048352  mov     r8d, eax
0x140048355  lea     rdx, aUalSessionForT_0; "UAL session for the Print Server role c"...
0x14004835c  mov     rcx, r14; char *
0x14004835f  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140048364  call    McGenEventUnregister_EtwEventUnregister
0x140048369  call    ?SplEventLogUnregister@@YAKXZ; SplEventLogUnregister(void)
0x14004836e  test    dil, dil
0x140048371  jz      short loc_140048393
0x140048373  call    cs:__imp_CoUninitialize
0x140048379  jmp     short loc_140048393
0x14004837b  call    cs:__imp_GetLastError
0x140048381  lea     rdx, aFailedToCreate_6; "Failed to create termination event, LE:"...
0x140048388  mov     rcx, r14; char *
0x14004838b  mov     r8d, eax
0x14004838e  call    ?WriteDbgTraceError@SpoolerServiceTelemetry@@SAXPEADPEAGZZ; SpoolerServiceTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140048393  cmp     cs:?g_bSpoolerIsChildProcess@@3_NA, 0; bool g_bSpoolerIsChildProcess
0x14004839a  jnz     short loc_1400483A5
0x14004839c  xor     ecx, ecx; dwExitCode
0x14004839e  call    cs:__imp_ExitThread
0x1400483a5  add     rsp, 38h
0x1400483a9  pop     r14
0x1400483ab  pop     rdi
0x1400483ac  pop     rsi
0x1400483ad  pop     rbx
0x1400483ae  retn
```
