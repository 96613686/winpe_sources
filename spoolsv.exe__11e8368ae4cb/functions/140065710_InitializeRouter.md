# InitializeRouter

- ea: `0x140065710`
- end: `0x140065b10`
- name: `InitializeRouter`
- size: `1024`
- prototype: `void __fastcall __noreturn(LPVOID lpMem)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140048fc0`

## callees

- `0x14000c490`
- `0x14000d5e4`
- `0x1400114e0`
- `0x140013fe8`
- `0x1400140cc`
- `0x140017674`
- `0x140017bc0`
- `0x14002b810`
- `0x140056b18`
- `0x140063d10`
- `0x140064c78`
- `0x140065144`
- `0x1400651d4`
- `0x14006533c`
- `0x1400655d8`
- `0x140065710`
- `0x140066400`
- `0x140066460`
- `0x140066e50`
- `0x140067d6c`
- `0x14006a688`
- `0x14006adb8`
- `0x14006c474`
- `0x14006e928`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400659b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400659b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140065adf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140065adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006598c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400659c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400659df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065aad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065818`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006598c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400659c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400659df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140065aad`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065831`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065876`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065914`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065952`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400659a5`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400659f8`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065831`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065876`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065914`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x140065952`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400659a5`
- `api-ms-win-core-processthreads-l1-1-0!ExitProcess` at `0x1400659f8`
- `KERNEL32!GetComputerNameW` at `0x1400657f6`
- `KERNEL32!GetComputerNameW` at `0x1400657f6`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x140065aa3`
- `api-ms-win-core-console-l1-1-0!SetConsoleCtrlHandler` at `0x140065aa3`
- `WS2_32!__imp_WSAStartup` at `0x1400657a8`
- `WS2_32!__imp_WSAStartup` at `0x1400657a8`

## string_xrefs

- `0x140065806`: `Failed to get computer name.  Error %d.`
- `0x140065929`: `Failed to initialize router cache.  Error hr: 0x%x`
- `0x14006584d`: `Failed initializing the name cache.  Error hr: 0x%x.`
- `0x140065960`: `localspl.dll`

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
    StringCchCopyW(&dword_1400CB674, 0x102u, ppszOtherNames[1]);
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
         &qword_1400CBC40,
         SplRegisterForSessionEvents(
           0,
           (unsigned int (*)(void *, unsigned int, unsigned __int64, __int64))PerMachineConnectionProcessUserEvents),
         0) )
  {
    SplUnregisterForSessionEvents();
  }
  PrvSpoolssTelemetry::WriteDbgTraceInfo("RegisterForPolicyConnectionUserEvents", L"Entered.");
  if ( _InterlockedCompareExchange64(
         &qword_1400CBB70,
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
  JUMPOUT(0x140065B0FLL);
}

```

## disassembly

```asm
0x140065710  mov     r11, rsp
0x140065713  mov     [r11+10h], rbx
0x140065717  mov     [r11+18h], rbp
0x14006571b  push    rsi
0x14006571c  push    rdi
0x14006571d  push    r14
0x14006571f  sub     rsp, 200h
0x140065726  mov     rax, cs:__security_cookie
0x14006572d  xor     rax, rsp
0x140065730  mov     [rsp+218h+var_28], rax
0x140065738  mov     esi, 1
0x14006573d  mov     [rsp+218h+var_1E8], 0
0x140065745  test    cs:Microsoft_Windows_DocumentsEnableBits, sil
0x14006574c  mov     rdi, rcx
0x14006574f  jz      short loc_140065769
0x140065751  lea     rax, [r11-38h]
0x140065755  mov     r9d, esi
0x140065758  lea     rdx, DocPerf_PhaseTwoInit_Start
0x14006575f  mov     [rsp+218h+var_1F8], rax
0x140065764  call    McGenEventWrite_EtwEventWriteTransfer
0x140065769  mov     rax, [rdi+8]
0x14006576d  mov     cs:?gpServerExports@@3PEAUPrintSpoolerServerExports@@EA, rax; PrintSpoolerServerExports * gpServerExports
0x140065774  mov     rax, [rdi]
0x140065777  mov     cs:?ghSplHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * ghSplHandle
0x14006577e  mov     eax, [rdi+14h]
0x140065781  mov     cs:?gbWindowsProtectedPrintSpoolerWorkerEnabled@@3HA, eax; int gbWindowsProtectedPrintSpoolerWorkerEnabled
0x140065787  call    ?SetSpoolerPriorityClass@@YAXXZ; SetSpoolerPriorityClass(void)
0x14006578c  xor     edx, edx; Val
0x14006578e  lea     rcx, [rsp+218h+WSAData]; void *
0x140065793  mov     r8d, 198h; Size
0x140065799  call    memset_0
0x14006579e  mov     ecx, 202h; wVersionRequested
0x1400657a3  lea     rdx, [rsp+218h+WSAData]; lpWSAData
0x1400657a8  call    cs:__imp_WSAStartup
0x1400657ae  lea     rbp, aInitializerout; "InitializeRouter"
0x1400657b5  test    eax, eax
0x1400657b7  jz      short loc_1400657CD
0x1400657b9  mov     r8d, eax
0x1400657bc  lea     rdx, aWsastartupDurr; "WSAStartup durring phase two initializa"...
0x1400657c3  mov     rcx, rbp; char *
0x1400657c6  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400657cb  jmp     short loc_1400657D3
0x1400657cd  mov     cs:?gbWSASucceeded@@3HA, esi; int gbWSASucceeded
0x1400657d3  call    SplIsUpgrade
0x1400657d8  lea     rdx, [rsp+218h+nSize]; nSize
0x1400657dd  mov     cs:?szMachineName@@3PAGA, 5C005Ch; ushort near * szMachineName
0x1400657e7  lea     rcx, Buffer; lpBuffer
0x1400657ee  mov     [rsp+218h+nSize], 10h
0x1400657f6  call    cs:__imp_GetComputerNameW
0x1400657fc  test    eax, eax
0x1400657fe  jnz     short loc_140065838
0x140065800  call    cs:__imp_GetLastError
0x140065806  lea     rdx, aFailedToGetCom; "Failed to get computer name.  Error %d."
0x14006580d  mov     rcx, rbp; char *
0x140065810  mov     r8d, eax
0x140065813  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065818  call    cs:__imp_GetLastError
0x14006581e  xor     r8d, r8d; unsigned __int16 *
0x140065821  lea     rcx, MSG_ROUTER_COMPUTER_NAME_FAILED; struct _EVENT_DESCRIPTOR *
0x140065828  mov     edx, eax; unsigned int
0x14006582a  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x14006582f  xor     ecx, ecx; uExitCode
0x140065831  call    cs:__imp_ExitProcess
0x140065838  call    ?GetDnsOnWirePolicy@@YAHXZ; GetDnsOnWirePolicy(void)
0x14006583d  mov     ecx, eax
0x14006583f  call    CacheInitNameCache
0x140065844  mov     ebx, eax
0x140065846  test    eax, eax
0x140065848  jns     short loc_14006587D
0x14006584a  mov     r8d, eax
0x14006584d  lea     rdx, aFailedInitiali; "Failed initializing the name cache.  Er"...
0x140065854  mov     rcx, rbp; char *
0x140065857  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006585c  mov     ecx, ebx; int
0x14006585e  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x140065863  mov     edx, eax; unsigned int
0x140065865  lea     rcx, MSG_ROUTER_NAME_CACHE_FAILED; struct _EVENT_DESCRIPTOR *
0x14006586c  xor     r8d, r8d; unsigned __int16 *
0x14006586f  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x140065874  xor     ecx, ecx; uExitCode
0x140065876  call    cs:__imp_ExitProcess
0x14006587d  lea     rdx, ?cOtherNames@@3KA; ulong cOtherNames
0x140065884  lea     rcx, ?ppszOtherNames@@3PEAPEAGEA; ushort * * ppszOtherNames
0x14006588b  call    BuildOtherNamesFromMachineName
0x140065890  test    eax, eax
0x140065892  jnz     short loc_1400658B7
0x140065894  call    cs:__imp_GetLastError
0x14006589a  lea     rdx, aFailedToDeterm; "Failed to determine other machine names"...
0x1400658a1  mov     rcx, rbp; char *
0x1400658a4  mov     r8d, eax
0x1400658a7  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400658ac  xor     eax, eax
0x1400658ae  mov     word ptr cs:?szMachineFullDNSName@@3PAGA, ax; ushort near * szMachineFullDNSName
0x1400658b5  jmp     short loc_1400658DD
0x1400658b7  mov     r8, cs:?ppszOtherNames@@3PEAPEAGEA; ushort * * ppszOtherNames
0x1400658be  lea     rcx, dword_1400CB674; unsigned __int16 *
0x1400658c5  mov     cs:?szMachineFullDNSName@@3PAGA, 5C005Ch; ushort near * szMachineFullDNSName
0x1400658cf  mov     edx, 102h; unsigned __int64
0x1400658d4  mov     r8, [r8+8]; unsigned __int16 *
0x1400658d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400658dd  call    ?InitializeRouterWorkCrew@NRouter@@YAJXZ; NRouter::InitializeRouterWorkCrew(void)
0x1400658e2  mov     ebx, eax
0x1400658e4  test    eax, eax
0x1400658e6  jns     short loc_14006591B
0x1400658e8  mov     r8d, eax
0x1400658eb  lea     rdx, aFailedToInitia_0; "Failed to initialize router work crew. "...
0x1400658f2  mov     rcx, rbp; char *
0x1400658f5  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400658fa  mov     ecx, ebx; int
0x1400658fc  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x140065901  mov     edx, eax; unsigned int
0x140065903  lea     rcx, MSG_ROUTER_WORKCREW_FAILED; struct _EVENT_DESCRIPTOR *
0x14006590a  xor     r8d, r8d; unsigned __int16 *
0x14006590d  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x140065912  xor     ecx, ecx; uExitCode
0x140065914  call    cs:__imp_ExitProcess
0x14006591b  call    ?InitializeRouterCache@NRouter@@YAJXZ; NRouter::InitializeRouterCache(void)
0x140065920  mov     ebx, eax
0x140065922  test    eax, eax
0x140065924  jns     short loc_140065959
0x140065926  mov     r8d, eax
0x140065929  lea     rdx, aFailedToInitia_1; "Failed to initialize router cache.  Err"...
0x140065930  mov     rcx, rbp; char *
0x140065933  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140065938  mov     ecx, ebx; int
0x14006593a  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x14006593f  mov     edx, eax; unsigned int
0x140065941  lea     rcx, MSG_ROUTER_CACHE_FAILED; struct _EVENT_DESCRIPTOR *
0x140065948  xor     r8d, r8d; unsigned __int16 *
0x14006594b  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x140065950  xor     ecx, ecx; uExitCode
0x140065952  call    cs:__imp_ExitProcess
0x140065959  lea     r8, [rsp+218h+var_1E8]; unsigned int *
0x14006595e  xor     edx, edx; unsigned __int16 *
0x140065960  lea     rcx, szLocalSplDll; "localspl.dll"
0x140065967  call    ?InitializeProvidor@@YAPEAU_PROVIDOR@@PEAG0PEAK@Z; InitializeProvidor(ushort *,ushort *,ulong *)
0x14006596c  mov     cs:?pLocalProvidor@@3PEAU_PROVIDOR@@EA, rax; _PROVIDOR * pLocalProvidor
0x140065973  test    rax, rax
0x140065976  jnz     short loc_1400659AC
0x140065978  mov     r8d, [rsp+218h+var_1E8]
0x14006597d  lea     rdx, aFailedToInitia; "Failed to initialize local print provid"...
0x140065984  mov     rcx, rbp; char *
0x140065987  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006598c  call    cs:__imp_GetLastError
0x140065992  xor     r8d, r8d; unsigned __int16 *
0x140065995  lea     rcx, MSG_ROUTER_LOCALSPL_FAILED; struct _EVENT_DESCRIPTOR *
0x14006599c  mov     edx, eax; unsigned int
0x14006599e  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x1400659a3  xor     ecx, ecx; uExitCode
0x1400659a5  call    cs:__imp_ExitProcess
0x1400659ac  mov     rcx, [rax+10h]; hModule
0x1400659b0  mov     edx, 190h; lpProcName
0x1400659b5  call    cs:__imp_GetProcAddress
0x1400659bb  mov     cs:?g_pfnSplGetSandboxManagerByServerName@@3P6APEAXPEBG@ZEA, rax; void * (*g_pfnSplGetSandboxManagerByServerName)(ushort const *)
0x1400659c2  test    rax, rax
0x1400659c5  jnz     short loc_1400659FF
0x1400659c7  call    cs:__imp_GetLastError
0x1400659cd  lea     rdx, aFailedToInitia; "Failed to initialize local print provid"...
0x1400659d4  mov     rcx, rbp; char *
0x1400659d7  mov     r8d, eax
0x1400659da  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400659df  call    cs:__imp_GetLastError
0x1400659e5  xor     r8d, r8d; unsigned __int16 *
0x1400659e8  lea     rcx, MSG_ROUTER_LOCALSPL_FAILED; struct _EVENT_DESCRIPTOR *
0x1400659ef  mov     edx, eax; unsigned int
0x1400659f1  call    ?SplLogRouterEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBG@Z; SplLogRouterEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *)
0x1400659f6  xor     ecx, ecx; uExitCode
0x1400659f8  call    cs:__imp_ExitProcess
0x1400659ff  call    ?InitializeProvidersInProviderOrder@@YAJXZ; InitializeProvidersInProviderOrder(void)
0x140065a04  mov     rcx, cs:?pEventInit@@3PEAVTAutoHandle@NCoreLibrary@@EA; this
0x140065a0b  call    ?SetAutoEventHandle@NCoreLibrary@@YAJPEAVTAutoHandle@1@@Z; NCoreLibrary::SetAutoEventHandle(NCoreLibrary::TAutoHandle *)
0x140065a10  lea     rdx, aEntered_0; "Entered"
0x140065a17  mov     cs:?Initialized@@3HA, esi; int Initialized
0x140065a1d  lea     rcx, aRegisterforper; "RegisterForPerMachineConnectionUserEven"...
0x140065a24  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065a29  lea     rdx, ?PerMachineConnectionProcessUserEvents@@YAKPEAXI_K_J@Z; unsigned int (*)(void *, unsigned int, unsigned __int64, __int64)
0x140065a30  xor     ecx, ecx; void *
0x140065a32  call    SplRegisterForSessionEvents
0x140065a37  mov     rcx, rax
0x140065a3a  xor     eax, eax
0x140065a3c  lock cmpxchg cs:qword_1400CBC40, rcx
0x140065a45  jz      short loc_140065A4C
0x140065a47  call    SplUnregisterForSessionEvents
0x140065a4c  lea     rdx, aEntered; "Entered."
0x140065a53  lea     rcx, aRegisterforpol; "RegisterForPolicyConnectionUserEvents"
0x140065a5a  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065a5f  lea     rdx, ?PolicyConnectionProcessUserEvents@@YAKPEAXI_K_J@Z; unsigned int (*)(void *, unsigned int, unsigned __int64, __int64)
0x140065a66  xor     ecx, ecx; void *
0x140065a68  call    SplRegisterForSessionEvents
0x140065a6d  mov     rcx, rax
0x140065a70  xor     eax, eax
0x140065a72  lock cmpxchg cs:qword_1400CBB70, rcx
0x140065a7b  jz      short loc_140065A82
0x140065a7d  call    SplUnregisterForSessionEvents
0x140065a82  call    ?RegisterForPnPEvents@@YAXXZ; RegisterForPnPEvents(void)
0x140065a87  lea     rdx, aEntered; "Entered."
0x140065a8e  lea     rcx, aRegisterforuse; "RegisterForUserEvents"
0x140065a95  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065a9a  mov     edx, esi; Add
0x140065a9c  lea     rcx, ?SpoolerConsoleCtrlHandler@@YAHK@Z; HandlerRoutine
0x140065aa3  call    cs:__imp_SetConsoleCtrlHandler
0x140065aa9  test    eax, eax
0x140065aab  jnz     short loc_140065AC9
0x140065aad  call    cs:__imp_GetLastError
0x140065ab3  mov     r8d, eax
0x140065ab6  lea     rdx, aSetconsolectrl; "SetConsoleCtrlHandler failed.  Error %d"...
0x140065abd  lea     rcx, aRegisterforuse; "RegisterForUserEvents"
0x140065ac4  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140065ac9  call    ?SpoolerInitAll@@YAHXZ; SpoolerInitAll(void)
0x140065ace  call    ?InitializeSessionIDGenerator@@YAXXZ; InitializeSessionIDGenerator(void)
0x140065ad3  mov     rcx, cs:?g_hSpoolssHeap@@3PEAXEA; hHeap
0x140065ada  mov     r8, rdi; lpMem
0x140065add  xor     edx, edx; dwFlags
0x140065adf  call    cs:__imp_HeapFree
0x140065ae5  test    cs:Microsoft_Windows_DocumentsEnableBits, sil
0x140065aec  jz      short loc_140065B0A
0x140065aee  lea     rax, [rsp+218h+var_38]
0x140065af6  mov     r9d, esi
0x140065af9  lea     rdx, DocPerf_PhaseTwoInit_Stop
0x140065b00  mov     [rsp+218h+var_1F8], rax
0x140065b05  call    McGenEventWrite_EtwEventWriteTransfer
0x140065b0a  call    ?HandlePollNotifications@@YAXXZ; HandlePollNotifications(void)
```
