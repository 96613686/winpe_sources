# InitializeRouter

- ea: `0x14006bb40`
- end: `0x14006bfac`
- name: `InitializeRouter`
- size: `1132`
- prototype: `void __fastcall __noreturn(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004d640`

## callees

- `0x14000d450`
- `0x14000e7f0`
- `0x1400127e0`
- `0x140015290`
- `0x140015378`
- `0x140018a4c`
- `0x1400190a4`
- `0x14002dd20`
- `0x14005c00c`
- `0x140069f00`
- `0x14006afdc`
- `0x14006b500`
- `0x14006b5a4`
- `0x14006b70c`
- `0x14006ba00`
- `0x14006bb40`
- `0x14006c9a0`
- `0x14006ca10`
- `0x14006d50c`
- `0x14006e510`
- `0x1400711b8`
- `0x140071978`
- `0x140073124`
- `0x14007567c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006be27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14006be27`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006bf75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14006bf75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bc3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bc5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bdf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bf3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bc3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bc5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bdf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006be5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006bf3d`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bc79`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bcc4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bd6e`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bdb2`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006be11`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006be7c`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bc79`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bcc4`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bd6e`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006bdb2`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006be11`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x14006be7c`
- `KERNEL32!GetComputerNameW` at `0x14006bc2c`
- `KERNEL32!GetComputerNameW` at `0x14006bc2c`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x14006bf2d`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x14006bf2d`
- `WS2_32!__imp_WSAStartup` at `0x14006bbd8`
- `WS2_32!__imp_WSAStartup` at `0x14006bbd8`

## string_xrefs

- `0x14006bc48`: `Failed to get computer name.  Error %d.`
- `0x14006bc9b`: `Failed initializing the name cache.  Error hr: 0x%x.`
- `0x14006bd89`: `Failed to initialize router cache.  Error hr: 0x%x`
- `0x14006bdc6`: `localspl.dll`

## pseudocode

```c
void __fastcall __noreturn InitializeRouter(_QWORD *lpMem, __int64 a2, int a3)
{
  unsigned int v4; // eax
  DWORD LastError; // eax
  DWORD v6; // eax
  unsigned int DnsOnWirePolicy; // eax
  int inited; // eax
  int v9; // ebx
  unsigned int v10; // eax
  DWORD v11; // eax
  NRouter *v12; // rcx
  int v13; // eax
  NRouter *v14; // rcx
  int v15; // ebx
  unsigned int v16; // eax
  int v17; // eax
  int v18; // ebx
  unsigned int v19; // eax
  struct _PROVIDOR *v20; // rax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  struct NCoreLibrary::TAutoHandle *v24; // rdx
  DWORD v25; // eax
  int v26; // ecx
  int v27; // r8d
  unsigned int v28; // [rsp+30h] [rbp-1E8h] BYREF
  DWORD nSize; // [rsp+38h] [rbp-1E0h] BYREF
  struct WSAData WSAData; // [rsp+40h] [rbp-1D8h] BYREF
  _BYTE v31[16]; // [rsp+1E0h] [rbp-38h] BYREF

  v28 = 0;
  if ( (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer((_DWORD)lpMem, (unsigned int)DocPerf_PhaseTwoInit_Start, a3, 1, (__int64)v31);
  gpServerExports = (struct PrintSpoolerServerExports *)lpMem[1];
  ghSplHandle = (HANDLE)*lpMem;
  gbWindowsProtectedPrintSpoolerWorkerEnabled = *((_DWORD *)lpMem + 5);
  SetSpoolerPriorityClass();
  memset_0(&WSAData, 0, sizeof(WSAData));
  v4 = WSAStartup(0x202u, &WSAData);
  if ( v4 )
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeRouter",
      L"WSAStartup durring phase two initialization failed.  Error %d.",
      v4);
  else
    gbWSASucceeded = 1;
  SplIsUpgrade();
  *(_DWORD *)&szMachineName = 6029404;
  nSize = 16;
  if ( !GetComputerNameW(&Buffer, &nSize) )
  {
    LastError = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError("InitializeRouter", L"Failed to get computer name.  Error %d.", LastError);
    v6 = GetLastError();
    SplLogRouterEvent(&MSG_ROUTER_COMPUTER_NAME_FAILED, v6, 0);
    ExitProcess(0);
  }
  DnsOnWirePolicy = GetDnsOnWirePolicy();
  inited = CacheInitNameCache(DnsOnWirePolicy);
  v9 = inited;
  if ( inited < 0 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeRouter",
      L"Failed initializing the name cache.  Error hr: 0x%x.",
      (unsigned int)inited);
    v10 = WIN32_FROM_HRESULT(v9);
    SplLogRouterEvent(&MSG_ROUTER_NAME_CACHE_FAILED, v10, 0);
    ExitProcess(0);
  }
  if ( (unsigned int)BuildOtherNamesFromMachineName((__int64)&ppszOtherNames, &cOtherNames) )
  {
    LODWORD(szMachineFullDNSName) = 6029404;
    StringCchCopyW(&dword_1400D27E4, 0x102u, ppszOtherNames[1]);
  }
  else
  {
    v11 = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeRouter",
      L"Failed to determine other machine names.  Error %d.",
      v11);
    LOWORD(szMachineFullDNSName) = 0;
  }
  v13 = NRouter::InitializeRouterWorkCrew(v12);
  v15 = v13;
  if ( v13 < 0 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeRouter",
      L"Failed to initialize router work crew.  Error hr: 0x%x.",
      (unsigned int)v13);
    v16 = WIN32_FROM_HRESULT(v15);
    SplLogRouterEvent(&MSG_ROUTER_WORKCREW_FAILED, v16, 0);
    ExitProcess(0);
  }
  v17 = NRouter::InitializeRouterCache(v14);
  v18 = v17;
  if ( v17 < 0 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeRouter",
      L"Failed to initialize router cache.  Error hr: 0x%x",
      (unsigned int)v17);
    v19 = WIN32_FROM_HRESULT(v18);
    SplLogRouterEvent(&MSG_ROUTER_CACHE_FAILED, v19, 0);
    ExitProcess(0);
  }
  v20 = InitializeProvidor(L"localspl.dll", 0, &v28);
  pLocalProvidor = v20;
  if ( !v20 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeRouter",
      L"Failed to initialize local print provider.  Error %d.",
      v28);
    v21 = GetLastError();
    SplLogRouterEvent(&MSG_ROUTER_LOCALSPL_FAILED, v21, 0);
    ExitProcess(0);
  }
  g_pfnSplGetSandboxManagerByServerName = (void *(*)(const unsigned __int16 *))GetProcAddress(
                                                                                 *((HMODULE *)v20 + 2),
                                                                                 (LPCSTR)0x190);
  if ( !g_pfnSplGetSandboxManagerByServerName )
  {
    v22 = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "InitializeRouter",
      L"Failed to initialize local print provider.  Error %d.",
      v22);
    v23 = GetLastError();
    SplLogRouterEvent(&MSG_ROUTER_LOCALSPL_FAILED, v23, 0);
    ExitProcess(0);
  }
  InitializeProvidersInProviderOrder();
  NCoreLibrary::SetAutoEventHandle(pEventInit, v24);
  Initialized = 1;
  PrvSpoolssTelemetry::WriteDbgTraceInfo("RegisterForPerMachineConnectionUserEvents", L"Entered");
  if ( _InterlockedCompareExchange64(
         &qword_1400D2DC0,
         SplRegisterForSessionEvents(
           0,
           (unsigned int (*)(void *, unsigned int, unsigned __int64, __int64))PerMachineConnectionProcessUserEvents),
         0) )
  {
    SplUnregisterForSessionEvents();
  }
  PrvSpoolssTelemetry::WriteDbgTraceInfo("RegisterForPolicyConnectionUserEvents", L"Entered.");
  if ( _InterlockedCompareExchange64(
         &qword_1400D2CE8,
         SplRegisterForSessionEvents(
           0,
           (unsigned int (*)(void *, unsigned int, unsigned __int64, __int64))PolicyConnectionProcessUserEvents),
         0) )
  {
    SplUnregisterForSessionEvents();
  }
  RegisterForPnPEvents();
  PrvSpoolssTelemetry::WriteDbgTraceInfo("RegisterForUserEvents", L"Entered.");
  if ( !SetConsoleCtrlHandler(SpoolerConsoleCtrlHandler, 1) )
  {
    v25 = GetLastError();
    PrvSpoolssTelemetry::WriteDbgTraceInfo("RegisterForUserEvents", L"SetConsoleCtrlHandler failed.  Error %d.", v25);
  }
  SpoolerInitAll();
  InitializeSessionIDGenerator();
  HeapFree(g_hSpoolssHeap, 0, lpMem);
  if ( (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
    McGenEventWrite_EtwEventWriteTransfer(v26, (unsigned int)DocPerf_PhaseTwoInit_Stop, v27, 1, (__int64)v31);
  HandlePollNotifications();
  JUMPOUT(0x14006BFABLL);
}

```

## disassembly

```asm
0x14006bb40  mov     r11, rsp
0x14006bb43  mov     [r11+10h], rbx
0x14006bb47  mov     [r11+18h], rbp
0x14006bb4b  push    rsi
0x14006bb4c  push    rdi
0x14006bb4d  push    r14
0x14006bb4f  sub     rsp, 200h
0x14006bb56  mov     rax, cs:__security_cookie
0x14006bb5d  xor     rax, rsp
0x14006bb60  mov     [rsp+218h+var_28], rax
0x14006bb68  mov     esi, 1
0x14006bb6d  mov     [rsp+218h+var_1E8], 0
0x14006bb75  test    cs:Microsoft_Windows_DocumentsEnableBits, sil
0x14006bb7c  mov     rdi, rcx
0x14006bb7f  jz      short loc_14006BB99
0x14006bb81  lea     rax, [r11-38h]
0x14006bb85  mov     r9d, esi
0x14006bb88  lea     rdx, DocPerf_PhaseTwoInit_Start
0x14006bb8f  mov     [rsp+218h+var_1F8], rax
0x14006bb94  call    McGenEventWrite_EtwEventWriteTransfer
0x14006bb99  mov     rax, [rdi+8]
0x14006bb9d  mov     cs:?gpServerExports@@3PEAUPrintSpoolerServerExports@@EA, rax; PrintSpoolerServerExports * gpServerExports
0x14006bba4  mov     rax, [rdi]
0x14006bba7  mov     cs:?ghSplHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ghSplHandle
0x14006bbae  mov     eax, [rdi+14h]
0x14006bbb1  mov     cs:?gbWindowsProtectedPrintSpoolerWorkerEnabled@@3HA, eax; int gbWindowsProtectedPrintSpoolerWorkerEnabled
0x14006bbb7  call    ?SetSpoolerPriorityClass@@YAXXZ; SetSpoolerPriorityClass(void)
0x14006bbbc  xor     edx, edx; Val
0x14006bbbe  lea     rcx, [rsp+218h+WSAData]; void *
0x14006bbc3  mov     r8d, 198h; Size
0x14006bbc9  call    memset_0
0x14006bbce  mov     ecx, 202h; wVersionRequested
0x14006bbd3  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x14006bbd8  call    cs:__imp_WSAStartup
0x14006bbdf  nop     dword ptr [rax+rax+00h]
0x14006bbe4  lea     rbp, aInitializerout; "InitializeRouter"
0x14006bbeb  test    eax, eax
0x14006bbed  jz      short loc_14006BC03
0x14006bbef  mov     r8d, eax
0x14006bbf2  lea     rdx, aWsastartupDurr; "WSAStartup durring phase two initializa"...
0x14006bbf9  mov     rcx, rbp; char *
0x14006bbfc  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006bc01  jmp     short loc_14006BC09
0x14006bc03  mov     cs:?gbWSASucceeded@@3HA, esi; int gbWSASucceeded
0x14006bc09  call    SplIsUpgrade
0x14006bc0e  lea     rdx, [rsp+218h+nSize]; nSize
0x14006bc13  mov     cs:?szMachineName@@3PAGA, 5C005Ch; ushort near * szMachineName
0x14006bc1d  lea     rcx, Buffer; lpBuffer
0x14006bc24  mov     [rsp+218h+nSize], 10h
0x14006bc2c  call    cs:__imp_GetComputerNameW
0x14006bc33  nop     dword ptr [rax+rax+00h]
0x14006bc38  test    eax, eax
0x14006bc3a  jnz     short loc_14006BC86
0x14006bc3c  call    cs:__imp_GetLastError
0x14006bc43  nop     dword ptr [rax+rax+00h]
0x14006bc48  lea     rdx, aFailedToGetCom; "Failed to get computer name.  Error %d."
0x14006bc4f  mov     rcx, rbp; char *
0x14006bc52  mov     r8d, eax
0x14006bc55  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006bc5a  call    cs:__imp_GetLastError
0x14006bc61  nop     dword ptr [rax+rax+00h]
0x14006bc66  xor     r8d, r8d; unsigned __int16 *
0x14006bc69  lea     rcx, MSG_ROUTER_COMPUTER_NAME_FAILED; struct _EVENT_DESCRIPTOR *
0x14006bc70  mov     edx, eax; unsigned int
0x14006bc72  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006bc77  xor     ecx, ecx; uExitCode
0x14006bc79  call    cs:__imp_ExitProcess
0x14006bc86  call    ?GetDnsOnWirePolicy@@YAHXZ; GetDnsOnWirePolicy(void)
0x14006bc8b  mov     ecx, eax
0x14006bc8d  call    CacheInitNameCache
0x14006bc92  mov     ebx, eax
0x14006bc94  test    eax, eax
0x14006bc96  jns     short loc_14006BCD1
0x14006bc98  mov     r8d, eax
0x14006bc9b  lea     rdx, aFailedInitiali; "Failed initializing the name cache.  Er"...
0x14006bca2  mov     rcx, rbp; char *
0x14006bca5  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006bcaa  mov     ecx, ebx; int
0x14006bcac  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x14006bcb1  mov     edx, eax; unsigned int
0x14006bcb3  lea     rcx, MSG_ROUTER_NAME_CACHE_FAILED; struct _EVENT_DESCRIPTOR *
0x14006bcba  xor     r8d, r8d; unsigned __int16 *
0x14006bcbd  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006bcc2  xor     ecx, ecx; uExitCode
0x14006bcc4  call    cs:__imp_ExitProcess
0x14006bcd1  lea     rdx, ?cOtherNames@@3KA; ulong cOtherNames
0x14006bcd8  lea     rcx, ?ppszOtherNames@@3PEAPEAGEA; ushort * * ppszOtherNames
0x14006bcdf  call    BuildOtherNamesFromMachineName
0x14006bce4  test    eax, eax
0x14006bce6  jnz     short loc_14006BD11
0x14006bce8  call    cs:__imp_GetLastError
0x14006bcef  nop     dword ptr [rax+rax+00h]
0x14006bcf4  lea     rdx, aFailedToDeterm; "Failed to determine other machine names"...
0x14006bcfb  mov     rcx, rbp; char *
0x14006bcfe  mov     r8d, eax
0x14006bd01  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006bd06  xor     eax, eax
0x14006bd08  mov     word ptr cs:?szMachineFullDNSName@@3PAGA, ax; ushort near * szMachineFullDNSName
0x14006bd0f  jmp     short loc_14006BD37
0x14006bd11  mov     r8, cs:?ppszOtherNames@@3PEAPEAGEA; ushort * * ppszOtherNames
0x14006bd18  lea     rcx, dword_1400D27E4; unsigned __int16 *
0x14006bd1f  mov     cs:?szMachineFullDNSName@@3PAGA, 5C005Ch; ushort near * szMachineFullDNSName
0x14006bd29  mov     edx, 102h; unsigned __int64
0x14006bd2e  mov     r8, [r8+8]; unsigned __int16 *
0x14006bd32  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14006bd37  call    ?InitializeRouterWorkCrew@NRouter@@YAJXZ; NRouter::InitializeRouterWorkCrew(void)
0x14006bd3c  mov     ebx, eax
0x14006bd3e  test    eax, eax
0x14006bd40  jns     short loc_14006BD7B
0x14006bd42  mov     r8d, eax
0x14006bd45  lea     rdx, aFailedToInitia_0; "Failed to initialize router work crew. "...
0x14006bd4c  mov     rcx, rbp; char *
0x14006bd4f  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006bd54  mov     ecx, ebx; int
0x14006bd56  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x14006bd5b  mov     edx, eax; unsigned int
0x14006bd5d  lea     rcx, MSG_ROUTER_WORKCREW_FAILED; struct _EVENT_DESCRIPTOR *
0x14006bd64  xor     r8d, r8d; unsigned __int16 *
0x14006bd67  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006bd6c  xor     ecx, ecx; uExitCode
0x14006bd6e  call    cs:__imp_ExitProcess
0x14006bd7b  call    ?InitializeRouterCache@NRouter@@YAJXZ; NRouter::InitializeRouterCache(void)
0x14006bd80  mov     ebx, eax
0x14006bd82  test    eax, eax
0x14006bd84  jns     short loc_14006BDBF
0x14006bd86  mov     r8d, eax
0x14006bd89  lea     rdx, aFailedToInitia_1; "Failed to initialize router cache.  Err"...
0x14006bd90  mov     rcx, rbp; char *
0x14006bd93  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006bd98  mov     ecx, ebx; int
0x14006bd9a  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x14006bd9f  mov     edx, eax; unsigned int
0x14006bda1  lea     rcx, MSG_ROUTER_CACHE_FAILED; struct _EVENT_DESCRIPTOR *
0x14006bda8  xor     r8d, r8d; unsigned __int16 *
0x14006bdab  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006bdb0  xor     ecx, ecx; uExitCode
0x14006bdb2  call    cs:__imp_ExitProcess
0x14006bdbf  lea     r8, [rsp+218h+var_1E8]; unsigned int *
0x14006bdc4  xor     edx, edx; unsigned __int16 *
0x14006bdc6  lea     rcx, szLocalSplDll; "localspl.dll"
0x14006bdcd  call    ?InitializeProvidor@@YAPEAU_PROVIDOR@@PEAG0PEAK@Z; InitializeProvidor(ushort *,ushort *,ulong *)
0x14006bdd2  mov     cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA, rax; _PROVIDOR * pLocalProvidor
0x14006bdd9  test    rax, rax
0x14006bddc  jnz     short loc_14006BE1E
0x14006bdde  mov     r8d, [rsp+218h+var_1E8]
0x14006bde3  lea     rdx, aFailedToInitia; "Failed to initialize local print provid"...
0x14006bdea  mov     rcx, rbp; char *
0x14006bded  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006bdf2  call    cs:__imp_GetLastError
0x14006bdf9  nop     dword ptr [rax+rax+00h]
0x14006bdfe  xor     r8d, r8d; unsigned __int16 *
0x14006be01  lea     rcx, MSG_ROUTER_LOCALSPL_FAILED; struct _EVENT_DESCRIPTOR *
0x14006be08  mov     edx, eax; unsigned int
0x14006be0a  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006be0f  xor     ecx, ecx; uExitCode
0x14006be11  call    cs:__imp_ExitProcess
0x14006be1e  mov     rcx, [rax+10h]; hModule
0x14006be22  mov     edx, 190h; lpProcName
0x14006be27  call    cs:__imp_GetProcAddress
0x14006be2e  nop     dword ptr [rax+rax+00h]
0x14006be33  mov     cs:?g_pfnSplGetSandboxManagerByServerName@@3P6APEAXPEBG@ZEA, rax; void * (*g_pfnSplGetSandboxManagerByServerName)(ushort const *)
0x14006be3a  test    rax, rax
0x14006be3d  jnz     short loc_14006BE89
0x14006be3f  call    cs:__imp_GetLastError
0x14006be46  nop     dword ptr [rax+rax+00h]
0x14006be4b  lea     rdx, aFailedToInitia; "Failed to initialize local print provid"...
0x14006be52  mov     rcx, rbp; char *
0x14006be55  mov     r8d, eax
0x14006be58  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006be5d  call    cs:__imp_GetLastError
0x14006be64  nop     dword ptr [rax+rax+00h]
0x14006be69  xor     r8d, r8d; unsigned __int16 *
0x14006be6c  lea     rcx, MSG_ROUTER_LOCALSPL_FAILED; struct _EVENT_DESCRIPTOR *
0x14006be73  mov     edx, eax; unsigned int
0x14006be75  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006be7a  xor     ecx, ecx; uExitCode
0x14006be7c  call    cs:__imp_ExitProcess
0x14006be89  call    ?InitializeProvidersInProviderOrder@@YAJXZ; InitializeProvidersInProviderOrder(void)
0x14006be8e  mov     rcx, cs:?pEventInit@@3PEAVTAutoHandle@NCoreLibrary@@EA; this
0x14006be95  call    ?SetAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@@Z; NCoreLibrary::SetAutoEventHandle(NCoreLibrary::TAutoHandle *)
0x14006be9a  lea     rdx, aEntered_0; "Entered"
0x14006bea1  mov     cs:?Initialized@@3HA, esi; int Initialized
0x14006bea7  lea     rcx, aRegisterforper; "RegisterForPerMachineConnectionUserEven"...
0x14006beae  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006beb3  lea     rdx, ?PerMachineConnectionProcessUserEvents@@YAKPEAXI_K_J@Z; unsigned int (*)(void *, unsigned int, unsigned __int64, __int64)
0x14006beba  xor     ecx, ecx; void *
0x14006bebc  call    SplRegisterForSessionEvents
0x14006bec1  mov     rcx, rax
0x14006bec4  xor     eax, eax
0x14006bec6  lock cmpxchg cs:qword_1400D2DC0, rcx
0x14006becf  jz      short loc_14006BED6
0x14006bed1  call    SplUnregisterForSessionEvents
0x14006bed6  lea     rdx, aEntered; "Entered."
0x14006bedd  lea     rcx, aRegisterforpol; "RegisterForPolicyConnectionUserEvents"
0x14006bee4  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006bee9  lea     rdx, ?PolicyConnectionProcessUserEvents@@YAKPEAXI_K_J@Z; unsigned int (*)(void *, unsigned int, unsigned __int64, __int64)
0x14006bef0  xor     ecx, ecx; void *
0x14006bef2  call    SplRegisterForSessionEvents
0x14006bef7  mov     rcx, rax
0x14006befa  xor     eax, eax
0x14006befc  lock cmpxchg cs:qword_1400D2CE8, rcx
0x14006bf05  jz      short loc_14006BF0C
0x14006bf07  call    SplUnregisterForSessionEvents
0x14006bf0c  call    ?RegisterForPnPEvents@@YAXXZ; RegisterForPnPEvents(void)
0x14006bf11  lea     rdx, aEntered; "Entered."
0x14006bf18  lea     rcx, aRegisterforuse; "RegisterForUserEvents"
0x14006bf1f  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006bf24  mov     edx, esi; Add
0x14006bf26  lea     rcx, ?SpoolerConsoleCtrlHandler@@YAHK@Z; HandlerRoutine
0x14006bf2d  call    cs:__imp_SetConsoleCtrlHandler
0x14006bf34  nop     dword ptr [rax+rax+00h]
0x14006bf39  test    eax, eax
0x14006bf3b  jnz     short loc_14006BF5F
0x14006bf3d  call    cs:__imp_GetLastError
0x14006bf44  nop     dword ptr [rax+rax+00h]
0x14006bf49  mov     r8d, eax
0x14006bf4c  lea     rdx, aSetconsolectrl; "SetConsoleCtrlHandler failed.  Error %d"...
0x14006bf53  lea     rcx, aRegisterforuse; "RegisterForUserEvents"
0x14006bf5a  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006bf5f  call    ?SpoolerInitAll@@YAHXZ; SpoolerInitAll(void)
0x14006bf64  call    ?InitializeSessionIDGenerator@@YAXXZ; InitializeSessionIDGenerator(void)
0x14006bf69  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x14006bf70  mov     r8, rdi; lpMem
0x14006bf73  xor     edx, edx; dwFlags
0x14006bf75  call    cs:__imp_HeapFree
0x14006bf7c  nop     dword ptr [rax+rax+00h]
0x14006bf81  test    cs:Microsoft_Windows_DocumentsEnableBits, sil
0x14006bf88  jz      short loc_14006BFA6
0x14006bf8a  lea     rax, [rsp+218h+var_38]
0x14006bf92  mov     r9d, esi
0x14006bf95  lea     rdx, DocPerf_PhaseTwoInit_Stop
0x14006bf9c  mov     [rsp+218h+var_1F8], rax
0x14006bfa1  call    McGenEventWrite_EtwEventWriteTransfer
0x14006bfa6  call    ?HandlePollNotifications@@YAXXZ; HandlePollNotifications(void)
```
