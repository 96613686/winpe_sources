# ServiceMain(ulong,wchar_t * *,ulong (*)(ulong,ulong,void *,void *))

- ea: `0x180010f84`
- end: `0x1800117c4`
- name: `?ServiceMain@@YAJKPEAPEA_WP6AKKKPEAX1@Z@Z`
- size: `2112`
- prototype: `__int64 __fastcall(unsigned int, wchar_t **, unsigned int (*)(unsigned int, unsigned int, void *, void *))`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180011a40`

## callees

- `0x1800016fc`
- `0x18000def4`
- `0x18000df20`
- `0x1800106d0`
- `0x1800107ec`
- `0x180010918`
- `0x180010a60`
- `0x180010cac`
- `0x180010e88`
- `0x180010f84`
- `0x180011a4c`
- `0x180011a90`
- `0x180011c94`
- `0x180012bb0`
- `0x180012cf0`
- `0x180013b6c`
- `0x1800142a0`
- `0x180017b88`
- `0x180111ab0`
- `0x180112ff0`
- `0x18012b618`
- `0x18012be1c`
- `0x18012c9b4`
- `0x18012cb84`
- `0x18012cc8c`
- `0x18012ce40`
- `0x18012e74c`
- `0x18013c260`
- `0x1801f231c`
- `0x180238960`
- `0x180238984`
- `0x180240cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fc1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180010fc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001178f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001178f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800116cd`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800116cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001123d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001123d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001122b`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001122b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800113b8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800113b8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011655`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180011655`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800112f7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800112f7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800112bd`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800112bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001168f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001168f`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800115d3`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18001160c`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800115d3`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x18001160c`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180011582`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001162a`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180011582`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001162a`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180011637`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180011637`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800116fb`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011716`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011731`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001174c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011767`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011782`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800116fb`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011716`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011731`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18001174c`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011767`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180011782`
- `CRYPT32!CertOpenStore` at `0x1800113d8`
- `CRYPT32!CertOpenStore` at `0x1800113d8`
- `CRYPT32!CertCloseStore` at `0x180011422`
- `CRYPT32!CertCloseStore` at `0x180011422`

## string_xrefs

- `0x1800113e7`: `C:\__w\1\s\src\Client\Engine\Agent\service.cpp`
- `0x180011492`: `C:\__w\1\s\src\Client\Engine\Agent\service.cpp`
- `0x1800110b0`: `* START * Service startup`
- `0x180011149`: `Assert WU event log configuration`
- `0x1800111c6`: `Failed to log service startup startevent`
- `0x18001125b`: `Failed to register service handler`
- `0x1800112a3`: `Blocking service start due to sysprep in progress`
- `0x1800113fc`: `Failed to create enterprise certificate store`
- `0x180011437`: `Service status is now SERVICE_RUNNING`
- `0x1800114a3`: `Exiting Service Main`
- `0x180011535`: `* END * Service exit Exit code = %#lx`
- `0x18001147a`: `C:\__w\1\s\src\Client\Engine\Agent\susclientglobal.cpp`
- `0x180011287`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdateSysprepInProgress`
- `0x1800113aa`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate\OSUpgradeHistory`
- `0x1800113be`: `WindowsServerUpdateServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ServiceMain(
        __int64 a1,
        wchar_t **a2,
        unsigned int (*a3)(unsigned int, unsigned int, void *, void *))
{
  BOOL v3; // r14d
  const struct _tlgProvider_t *v4; // rdx
  Trace *v5; // rcx
  const wchar_t *v6; // rdx
  CWUEtwConsumer *v7; // rcx
  const struct _GUID *v8; // r8
  const struct _GUID *v9; // r9
  CWUEtwConsumer *v10; // rcx
  signed int WUSystemInterface; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r15
  int v16; // eax
  const struct _GUID *v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // ecx
  int v22; // eax
  int v23; // eax
  WUSystemInterfaceHelper *v24; // rcx
  signed int LastError; // eax
  const wchar_t *v26; // rax
  unsigned int v27; // ecx
  HCERTSTORE v28; // rax
  const char *v29; // r9
  int v30; // eax
  int v31; // eax
  CSusClientGlobal *v32; // rdi
  const GUID *v33; // rdi
  const GUID *v34; // rsi
  CWUEtwConsumer *v35; // rcx
  HLOCAL *v36; // rdi
  REGHANDLE v37; // rcx
  REGHANDLE v38; // rcx
  REGHANDLE v39; // rcx
  REGHANDLE v40; // rcx
  REGHANDLE v41; // rcx
  REGHANDLE v42; // rcx
  int ppv; // [rsp+20h] [rbp-60h]
  int ppva; // [rsp+20h] [rbp-60h]
  __int128 v46; // [rsp+40h] [rbp-40h] BYREF
  __int64 v47; // [rsp+50h] [rbp-30h]
  LPVOID v48; // [rsp+58h] [rbp-28h] BYREF
  _QWORD v49[3]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v3 = 0;
  EnterCriticalSection(&gcsServiceMain);
  dword_18033A6C0 = 0;
  dword_18033A6C4 = 0;
  Trace::Register(v5, v4);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::GetImpl'::`2'::impl) )
  {
    v49[0] = &CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::`vftable';
    v49[1] = 0;
    v49[2] = 0;
    v46 = xmmword_1802563E8;
    v47 = -1;
    CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::Add(
      v49,
      &v46,
      0);
    v46 = xmmword_180256378;
    v47 = 5;
    CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::Add(
      v49,
      &v46,
      0);
    v46 = xmmword_180256368;
    v47 = 5;
    CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::Add(
      v49,
      &v46,
      0);
    WUSystemInterface = CWUEtwConsumer::Initialize(v13, v12, v14, v49);
    CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::~CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>(v49);
  }
  else
  {
    WUSystemInterface = CWUEtwConsumer::Initialize(v7, v6, v8, v9);
  }
  v15 = 2;
  if ( WUSystemInterface >= 0 )
  {
    CWUEtwConsumer::BeginTrace(v10);
    WUTrace(0, 0, 2048, 4, 0, L"* START * Service startup");
    v16 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1803309A0);
    if ( v16 < 0
      || (v16 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1803309D8), v16 < 0)
      || (v16 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180330930), v16 < 0)
      || (v16 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_180330968), v16 < 0)
      || (v16 = TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_1803308F8), v16 < 0) )
    {
      WUTrace(0, 0, 2048, 3, v16, L"Register the Asimov ETW provider");
    }
    v18 = CallEvtIntAssertConfig(v17);
    if ( v18 < 0 )
      WUTrace(0, 0, 2048, 3, v18, L"Assert WU event log configuration");
    v20 = McGenEventRegister_EventRegister(
            &WindowsUpdateClientProvider,
            v19,
            &WindowsUpdateClientProvider_Context,
            &WindowsUpdateClientProvider_Context);
    g_hNTEventLog = WindowsUpdateClientProvider_Context;
    if ( WindowsUpdateClientProvider_Context )
    {
      v22 = CVistaNTEventLogWriter::LogSimpleEvent(0x125u);
      if ( v22 < 0 )
        WUTrace(0, 0, 2048, 5, v22, L"Failed to log service startup startevent");
    }
    else
    {
      v21 = (unsigned __int16)v20 | 0x80070000;
      if ( v20 <= 0 )
        v21 = v20;
      WUTrace(0, 0, 2048, 3, v21, L"Failed to register WU event log");
    }
    v23 = EnableMitigations();
    if ( v23 < 0 )
      WUTrace(0, 0, 2048, 3, v23, L"Failed to enable process mitigations");
    g_ServiceStatus.dwServiceType = 32;
    g_hServiceStatus = RegisterServiceCtrlHandlerExW(L"wuauserv", ServiceHandler, 0);
    if ( !g_hServiceStatus )
    {
      LastError = GetLastError();
      WUSystemInterface = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        WUSystemInterface = LastError;
      if ( WUSystemInterface >= 0 )
        WUSystemInterface = -2147418113;
      v26 = L"Failed to register service handler";
      goto LABEL_27;
    }
    WUSystemInterface = WUSystemInterfaceHelper::LoadWUSystemInterface(v24);
    if ( WUSystemInterface < 0 )
    {
      v26 = L"Failed to load system interface module";
LABEL_27:
      WUTrace(0, 0, 2048, 1, WUSystemInterface, v26);
      goto LABEL_51;
    }
    if ( (int)RegKeyExists(-2147483646, L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdateSysprepInProgress") >= 0 )
    {
      WUSystemInterface = -2145124287;
      v26 = L"Blocking service start due to sysprep in progress";
      goto LABEL_27;
    }
    UpdateServiceStatus(2u, 0x7530u);
    WUSystemInterface = CoInitializeEx(0, 0);
    v3 = WUSystemInterface >= 0;
    if ( WUSystemInterface >= 0 )
    {
      v48 = 0;
      WUSystemInterface = CoCreateInstance(
                            &CLSID_GlobalOptions,
                            0,
                            1u,
                            &GUID_0000015b_0000_0000_c000_000000000046,
                            &v48);
      if ( WUSystemInterface >= 0 )
      {
        WUSystemInterface = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v48 + 24LL))(v48, 5, 1);
        if ( WUSystemInterface >= 0 )
        {
          if ( v48 )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v48 + 16LL))(v48);
          ResetClientIfNeeded();
          RegisterProxyStubCLSIDs(v27);
          CreatePlaceholderWindowsUpdateLogFile();
          WUSystemInterface = InitializeSUS();
          if ( WUSystemInterface >= 0 )
          {
            AddOSUpgradeHistoryToDatastore((struct ISusDatastore *)(((unsigned __int64)g_pSusClientGlobal + 1408)
                                                                  & -(__int64)((CSusClientGlobal *)((char *)g_pSusClientGlobal
                                                                                                  + 1400) != 0)));
            RegDeleteTreeW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\OSUpgradeHistory");
            v28 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x20000u, aWindowsserveru);
            if ( v28 )
            {
              CertCloseStore(v28, 0);
            }
            else
            {
              v30 = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x147,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\service.cpp",
                      v29);
              if ( v30 < 0 )
                WUTrace(0, 0, 2048, 3, v30, L"Failed to create enterprise certificate store");
            }
            UpdateServiceStatus(4u, 0x7530u);
            WUTrace(0, 0, 2048, 5, 0, L"Service status is now SERVICE_RUNNING");
            v31 = CSusEventSystem::Run((CSusClientGlobal *)((char *)g_pSusClientGlobal + 216));
            WUSystemInterface = v31;
            if ( v31 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x127,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\susclientglobal.cpp",
                (const char *)(unsigned int)v31,
                ppv);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xC0,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\service.cpp",
                (const char *)(unsigned int)WUSystemInterface,
                ppva);
            }
            WUTrace(0, 0, 2048, 5, 0, L"Exiting Service Main");
          }
        }
        else if ( v48 )
        {
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v48 + 16LL))(v48);
        }
      }
      else if ( v48 )
      {
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v48 + 16LL))(v48);
      }
    }
  }
LABEL_51:
  UpdateServiceStatus(3u, 0x7530u);
  WUTrace(0, 0, 2048, 4, 0, L"UninitializeSUS");
  if ( g_pSusClientGlobal )
  {
    CSusClientGlobal::Uninit(g_pSusClientGlobal);
    v32 = g_pSusClientGlobal;
    if ( g_pSusClientGlobal )
    {
      CSusClientGlobal::~CSusClientGlobal(g_pSusClientGlobal);
      operator delete(v32, (const struct std::nothrow_t *)0x2B80);
    }
  }
  g_pSusClientGlobal = 0;
  WUTrace(0, 0, 2048, 4, 0, L"* END * Service exit Exit code = %#lx", WUSystemInterface);
  if ( TraceHandle != -1 )
  {
    if ( TraceHandle )
      ControlTraceW(TraceHandle, &InstanceName, &Properties, 3u);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::GetImpl'::`2'::impl) )
    {
      v33 = ProviderId;
      v34 = (LPCGUID)((char *)ProviderId + 24 * (unsigned int)dword_180333AFC);
      while ( v33 != v34 )
      {
        EnableTraceEx2(TraceHandle, v33, 0, 4u, 0, 0, 0, 0);
        v33 = (const GUID *)((char *)v33 + 24);
      }
    }
    else
    {
      EnableTraceEx2(TraceHandle, &stru_180333AD4, 0, 4u, 0, 0, 0, 0);
    }
    ControlTraceW(TraceHandle, &InstanceName, &Properties, 1u);
    CloseTrace(TraceHandle);
    CWUEtwConsumer::RotatePastLogsOverLimit(v35, 1);
    TraceHandle = -1;
  }
  if ( v3 )
    CoUninitialize();
  if ( WUSystemInterface < 0 )
  {
    if ( (WUSystemInterface & 0x1FFF0000) == 0x240000 )
    {
      g_ServiceStatus.dwWin32ExitCode = 1066;
      g_ServiceStatus.dwServiceSpecificExitCode = WUSystemInterface;
    }
    else
    {
      g_ServiceStatus.dwWin32ExitCode = WUSystemInterface;
    }
  }
  v36 = (HLOCAL *)qword_18033A760;
  do
  {
    LocalFree(*v36);
    *v36++ = 0;
    --v15;
  }
  while ( v15 );
  dword_18033A758 = 0;
  UpdateServiceStatus(1u, 0x7530u);
  if ( g_hNTEventLog )
  {
    CVistaNTEventLogWriter::LogSimpleEvent(0x128u);
    Sleep(0x3E8u);
    McGenEventUnregister_EventUnregister(&WindowsUpdateClientProvider_Context);
    g_hNTEventLog = 0;
  }
  v37 = qword_1803309C0;
  dword_1803309A0 = 0;
  qword_1803309C0 = 0;
  EventUnregister(v37);
  v38 = qword_1803309F8;
  dword_1803309D8 = 0;
  qword_1803309F8 = 0;
  EventUnregister(v38);
  v39 = qword_180330950;
  dword_180330930 = 0;
  qword_180330950 = 0;
  EventUnregister(v39);
  v40 = qword_180330988;
  dword_180330968 = 0;
  qword_180330988 = 0;
  EventUnregister(v40);
  v41 = qword_180330918;
  dword_1803308F8 = 0;
  qword_180330918 = 0;
  EventUnregister(v41);
  v42 = RegHandle;
  dword_18032BA20 = 0;
  RegHandle = 0;
  EventUnregister(v42);
  LeaveCriticalSection(&gcsServiceMain);
  return (unsigned int)WUSystemInterface;
}

```

## disassembly

```asm
0x180010f84  mov     [rsp-28h+arg_0], rbx
0x180010f89  mov     [rsp-28h+arg_8], rsi
0x180010f8e  mov     [rsp-28h+arg_10], rdi
0x180010f93  push    rbp
0x180010f94  push    r12
0x180010f96  push    r13
0x180010f98  push    r14
0x180010f9a  push    r15
0x180010f9c  mov     rbp, rsp
0x180010f9f  sub     rsp, 80h
0x180010fa6  mov     rax, cs:__security_cookie
0x180010fad  xor     rax, rsp
0x180010fb0  mov     [rbp+var_8], rax
0x180010fb4  xor     r12d, r12d
0x180010fb7  mov     r14d, r12d
0x180010fba  lea     rcx, ?gcsServiceMain@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180010fc1  call    cs:__imp_EnterCriticalSection
0x180010fc7  mov     cs:dword_18033A6C0, r12d
0x180010fce  mov     cs:dword_18033A6C4, r12d
0x180010fd5  call    ?Register@Trace@@YAXPEBU_tlgProvider_t@@@Z; Trace::Register(_tlgProvider_t const *)
0x180010fda  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WriteWuTelemetryToLogs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WriteWuTelemetryToLogs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs> `wil::Feature<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::GetImpl(void)'::`2'::impl
0x180010fe1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WriteWuTelemetryToLogs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WriteWuTelemetryToLogs>::__private_IsEnabled(void)
0x180010fe6  test    al, al
0x180010fe8  jnz     short loc_180010FF6
0x180010fea  call    ?Initialize@CWUEtwConsumer@@QEAAJPEB_WAEBU_GUID@@1@Z; CWUEtwConsumer::Initialize(wchar_t const *,_GUID const &,_GUID const &)
0x180010fef  mov     ebx, eax
0x180010ff1  jmp     loc_180011091
0x180010ff6  xorps   xmm0, xmm0
0x180010ff9  movups  [rbp+var_20], xmm0
0x180010ffd  lea     rax, ??_7?$CSusArrayList@UEtwProviderInfo@CWUEtwConsumer@@V?$CSusArrayListItemOpNoop@UEtwProviderInfo@CWUEtwConsumer@@@@@@6B@; const CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::`vftable'
0x180011004  mov     qword ptr [rbp+var_20], rax
0x180011008  mov     qword ptr [rbp+var_20+8], r12
0x18001100c  mov     [rbp+var_10], r12
0x180011010  movups  xmm0, cs:xmmword_1802563E8
0x180011017  movdqu  [rbp+var_40], xmm0
0x18001101c  or      eax, 0FFFFFFFFh
0x18001101f  mov     dword ptr [rbp+var_30], eax
0x180011022  mov     dword ptr [rbp+var_30+4], eax
0x180011025  xor     r8d, r8d
0x180011028  lea     rdx, [rbp+var_40]
0x18001102c  lea     rcx, [rbp+var_20]
0x180011030  call    ?Add@?$CSusArrayList@UEtwProviderInfo@CWUEtwConsumer@@V?$CSusArrayListItemOpNoop@UEtwProviderInfo@CWUEtwConsumer@@@@@@UEAAJAEBUEtwProviderInfo@CWUEtwConsumer@@PEAK@Z; CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::Add(CWUEtwConsumer::EtwProviderInfo const &,ulong *)
0x180011035  movups  xmm0, cs:xmmword_180256378
0x18001103c  movdqu  [rbp+var_40], xmm0
0x180011041  mov     [rbp+var_30], 5
0x180011049  xor     r8d, r8d
0x18001104c  lea     rdx, [rbp+var_40]
0x180011050  lea     rcx, [rbp+var_20]
0x180011054  call    ?Add@?$CSusArrayList@UEtwProviderInfo@CWUEtwConsumer@@V?$CSusArrayListItemOpNoop@UEtwProviderInfo@CWUEtwConsumer@@@@@@UEAAJAEBUEtwProviderInfo@CWUEtwConsumer@@PEAK@Z; CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::Add(CWUEtwConsumer::EtwProviderInfo const &,ulong *)
0x180011059  movups  xmm0, cs:xmmword_180256368
0x180011060  movdqu  [rbp+var_40], xmm0
0x180011065  mov     [rbp+var_30], 5
0x18001106d  xor     r8d, r8d
0x180011070  lea     rdx, [rbp+var_40]
0x180011074  lea     rcx, [rbp+var_20]
0x180011078  call    ?Add@?$CSusArrayList@UEtwProviderInfo@CWUEtwConsumer@@V?$CSusArrayListItemOpNoop@UEtwProviderInfo@CWUEtwConsumer@@@@@@UEAAJAEBUEtwProviderInfo@CWUEtwConsumer@@PEAK@Z; CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::Add(CWUEtwConsumer::EtwProviderInfo const &,ulong *)
0x18001107d  lea     r9, [rbp+var_20]
0x180011081  call    ?Initialize@CWUEtwConsumer@@QEAAJPEB_WAEBU_GUID@@AEBV?$CSusArrayList@UEtwProviderInfo@CWUEtwConsumer@@V?$CSusArrayListItemOpNoop@UEtwProviderInfo@CWUEtwConsumer@@@@@@@Z; CWUEtwConsumer::Initialize(wchar_t const *,_GUID const &,CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>> const &)
0x180011086  mov     ebx, eax
0x180011088  lea     rcx, [rbp+var_20]
0x18001108c  call    ??1?$CSusArrayList@UEtwProviderInfo@CWUEtwConsumer@@V?$CSusArrayListItemOpNoop@UEtwProviderInfo@CWUEtwConsumer@@@@@@UEAA@XZ; CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>::~CSusArrayList<CWUEtwConsumer::EtwProviderInfo,CSusArrayListItemOpNoop<CWUEtwConsumer::EtwProviderInfo>>(void)
0x180011091  mov     esi, 800h
0x180011096  mov     edi, 3
0x18001109b  lea     r15d, [rdi-1]
0x18001109f  lea     r13d, [rdi-2]
0x1800110a3  test    ebx, ebx
0x1800110a5  js      loc_1800114C6
0x1800110ab  call    ?BeginTrace@CWUEtwConsumer@@QEAAJXZ; CWUEtwConsumer::BeginTrace(void)
0x1800110b0  lea     rax, aStartServiceSt; "* START * Service startup"
0x1800110b7  mov     [rsp+80h+MatchAllKeyword], rax
0x1800110bc  mov     [rsp+80h+ppv], r12
0x1800110c1  lea     r9d, [rdi+1]
0x1800110c5  mov     r8d, esi
0x1800110c8  xor     edx, edx
0x1800110ca  xor     ecx, ecx
0x1800110cc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800110d1  lea     rcx, dword_1803309A0; CallbackContext
0x1800110d8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800110dd  test    eax, eax
0x1800110df  js      short loc_180011121
0x1800110e1  lea     rcx, dword_1803309D8; CallbackContext
0x1800110e8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800110ed  test    eax, eax
0x1800110ef  js      short loc_180011121
0x1800110f1  lea     rcx, dword_180330930; CallbackContext
0x1800110f8  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800110fd  test    eax, eax
0x1800110ff  js      short loc_180011121
0x180011101  lea     rcx, dword_180330968; CallbackContext
0x180011108  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001110d  test    eax, eax
0x18001110f  js      short loc_180011121
0x180011111  lea     rcx, dword_1803308F8; CallbackContext
0x180011118  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001111d  test    eax, eax
0x18001111f  jns     short loc_180011140
0x180011121  lea     rcx, aRegisterTheAsi; "Register the Asimov ETW provider"
0x180011128  mov     [rsp+80h+MatchAllKeyword], rcx
0x18001112d  mov     dword ptr [rsp+80h+ppv], eax
0x180011131  mov     r9d, edi
0x180011134  mov     r8d, esi
0x180011137  xor     edx, edx
0x180011139  xor     ecx, ecx
0x18001113b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180011140  call    ?CallEvtIntAssertConfig@@YAJAEBU_GUID@@@Z; CallEvtIntAssertConfig(_GUID const &)
0x180011145  test    eax, eax
0x180011147  jns     short loc_180011168
0x180011149  lea     rcx, aAssertWuEventL; "Assert WU event log configuration"
0x180011150  mov     [rsp+80h+MatchAllKeyword], rcx
0x180011155  mov     dword ptr [rsp+80h+ppv], eax
0x180011159  mov     r9d, edi
0x18001115c  mov     r8d, esi
0x18001115f  xor     edx, edx
0x180011161  xor     ecx, ecx
0x180011163  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180011168  lea     r9, WindowsUpdateClientProvider_Context
0x18001116f  lea     r8, WindowsUpdateClientProvider_Context
0x180011176  lea     rcx, WindowsUpdateClientProvider
0x18001117d  call    McGenEventRegister_EventRegister
0x180011182  mov     rcx, cs:WindowsUpdateClientProvider_Context
0x180011189  mov     cs:?g_hNTEventLog@@3_KA, rcx; unsigned __int64 g_hNTEventLog
0x180011190  test    rcx, rcx
0x180011193  jnz     short loc_1800111B8
0x180011195  movzx   ecx, ax
0x180011198  or      ecx, 80070000h
0x18001119e  test    eax, eax
0x1800111a0  cmovle  ecx, eax
0x1800111a3  lea     rax, aFailedToRegist; "Failed to register WU event log"
0x1800111aa  mov     [rsp+80h+MatchAllKeyword], rax
0x1800111af  mov     dword ptr [rsp+80h+ppv], ecx
0x1800111b3  mov     r9d, edi
0x1800111b6  jmp     short loc_1800111DC
0x1800111b8  mov     ecx, 125h; unsigned int
0x1800111bd  call    ?LogSimpleEvent@CVistaNTEventLogWriter@@SAJK@Z; CVistaNTEventLogWriter::LogSimpleEvent(ulong)
0x1800111c2  test    eax, eax
0x1800111c4  jns     short loc_1800111E8
0x1800111c6  lea     rcx, aFailedToLogSer; "Failed to log service startup starteven"...
0x1800111cd  mov     [rsp+80h+MatchAllKeyword], rcx
0x1800111d2  mov     dword ptr [rsp+80h+ppv], eax
0x1800111d6  mov     r9d, 5
0x1800111dc  mov     r8d, esi
0x1800111df  xor     edx, edx
0x1800111e1  xor     ecx, ecx
0x1800111e3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800111e8  call    EnableMitigations
0x1800111ed  test    eax, eax
0x1800111ef  jns     short loc_180011210
0x1800111f1  lea     rcx, aFailedToEnable_0; "Failed to enable process mitigations"
0x1800111f8  mov     [rsp+80h+MatchAllKeyword], rcx
0x1800111fd  mov     dword ptr [rsp+80h+ppv], eax
0x180011201  mov     r9d, edi
0x180011204  mov     r8d, esi
0x180011207  xor     edx, edx
0x180011209  xor     ecx, ecx
0x18001120b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180011210  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ServiceStatus ...
0x18001121a  xor     r8d, r8d; lpContext
0x18001121d  lea     rdx, ?ServiceHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x180011224  lea     rcx, ?c_szWuauservService@@3QB_WB; "wuauserv"
0x18001122b  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180011231  mov     cs:?g_hServiceStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_hServiceStatus
0x180011238  test    rax, rax
0x18001123b  jnz     short loc_180011273
0x18001123d  call    cs:__imp_GetLastError
0x180011243  movzx   ebx, ax
0x180011246  or      ebx, 80070000h
0x18001124c  test    eax, eax
0x18001124e  cmovle  ebx, eax
0x180011251  mov     eax, 8000FFFFh
0x180011256  test    ebx, ebx
0x180011258  cmovns  ebx, eax
0x18001125b  lea     rax, aFailedToRegist_0; "Failed to register service handler"
0x180011262  mov     [rsp+80h+MatchAllKeyword], rax
0x180011267  mov     dword ptr [rsp+80h+ppv], ebx
0x18001126b  mov     r9d, r13d
0x18001126e  jmp     loc_1800114BA
0x180011273  call    ?LoadWUSystemInterface@WUSystemInterfaceHelper@@YAJXZ; WUSystemInterfaceHelper::LoadWUSystemInterface(void)
0x180011278  mov     ebx, eax
0x18001127a  test    eax, eax
0x18001127c  jns     short loc_180011287
0x18001127e  lea     rax, aFailedToLoadSy; "Failed to load system interface module"
0x180011285  jmp     short loc_180011262
0x180011287  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001128e  mov     rcx, 0FFFFFFFF80000002h
0x180011295  call    ?RegKeyExists@@YAJPEAUHKEY__@@PEB_WW4RegistryHiveType@@@Z; RegKeyExists(HKEY__ *,wchar_t const *,RegistryHiveType)
0x18001129a  test    eax, eax
0x18001129c  js      short loc_1800112AC
0x18001129e  mov     ebx, 80240041h
0x1800112a3  lea     rax, aBlockingServic; "Blocking service start due to sysprep i"...
0x1800112aa  jmp     short loc_180011262
0x1800112ac  mov     edx, 7530h; unsigned int
0x1800112b1  mov     ecx, r15d; unsigned int
0x1800112b4  call    ?UpdateServiceStatus@@YAXKK@Z; UpdateServiceStatus(ulong,ulong)
0x1800112b9  xor     edx, edx; dwCoInit
0x1800112bb  xor     ecx, ecx; pvReserved
0x1800112bd  call    cs:__imp_CoInitializeEx
0x1800112c3  mov     ebx, eax
0x1800112c5  mov     r14d, eax
0x1800112c8  not     r14d
0x1800112cb  shr     r14d, 1Fh
0x1800112cf  test    eax, eax
0x1800112d1  js      loc_1800114C6
0x1800112d7  mov     [rbp+var_28], r12
0x1800112db  lea     rax, [rbp+var_28]
0x1800112df  mov     [rsp+80h+ppv], rax; ppv
0x1800112e4  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1800112eb  mov     r8d, r13d; dwClsContext
0x1800112ee  xor     edx, edx; pUnkOuter
0x1800112f0  lea     rcx, CLSID_GlobalOptions; rclsid
0x1800112f7  call    cs:__imp_CoCreateInstance
0x1800112fd  mov     ebx, eax
0x1800112ff  test    eax, eax
0x180011301  jns     short loc_18001131E
0x180011303  mov     rcx, [rbp+var_28]
0x180011307  test    rcx, rcx
0x18001130a  jz      short loc_180011319
0x18001130c  mov     rax, [rcx]
0x18001130f  mov     rax, [rax+10h]
0x180011313  call    _guard_dispatch_icall
0x180011318  nop
0x180011319  jmp     loc_1800114C6
0x18001131e  mov     rcx, [rbp+var_28]
0x180011322  mov     rax, [rcx]
0x180011325  mov     r8, r13
0x180011328  mov     edx, 5
0x18001132d  mov     rax, [rax+18h]
0x180011331  call    _guard_dispatch_icall
0x180011336  mov     ebx, eax
0x180011338  test    eax, eax
0x18001133a  jns     short loc_180011357
0x18001133c  mov     rcx, [rbp+var_28]
0x180011340  test    rcx, rcx
0x180011343  jz      short loc_180011352
0x180011345  mov     rax, [rcx]
0x180011348  mov     rax, [rax+10h]
0x18001134c  call    _guard_dispatch_icall
0x180011351  nop
0x180011352  jmp     loc_1800114C6
0x180011357  mov     rcx, [rbp+var_28]
0x18001135b  test    rcx, rcx
0x18001135e  jz      short loc_18001136D
0x180011360  mov     rax, [rcx]
0x180011363  mov     rax, [rax+10h]
0x180011367  call    _guard_dispatch_icall
0x18001136c  nop
0x18001136d  call    ?ResetClientIfNeeded@@YAXXZ; ResetClientIfNeeded(void)
0x180011372  call    ?RegisterProxyStubCLSIDs@@YAXK@Z; RegisterProxyStubCLSIDs(ulong)
0x180011377  call    ?CreatePlaceholderWindowsUpdateLogFile@@YAXXZ; CreatePlaceholderWindowsUpdateLogFile(void)
0x18001137c  call    ?InitializeSUS@@YAJXZ; InitializeSUS(void)
0x180011381  mov     ebx, eax
0x180011383  test    eax, eax
0x180011385  js      loc_1800114C6
0x18001138b  mov     rax, cs:?g_pSusClientGlobal@@3PEAVCSusClientGlobal@@EA; CSusClientGlobal * g_pSusClientGlobal
0x180011392  add     rax, 578h
0x180011398  lea     rdx, [rax+8]
0x18001139c  neg     rax
0x18001139f  sbb     rcx, rcx
0x1800113a2  and     rcx, rdx; struct ISusDatastore *
0x1800113a5  call    ?AddOSUpgradeHistoryToDatastore@@YAJPEAUISusDatastore@@@Z; AddOSUpgradeHistoryToDatastore(ISusDatastore *)
0x1800113aa  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800113b1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800113b8  call    cs:__imp_RegDeleteTreeW
0x1800113be  lea     rax, aWindowsserveru; "WindowsServerUpdateServices"
0x1800113c5  mov     [rsp+80h+ppv], rax; pvPara
0x1800113ca  mov     r9d, 20000h; dwFlags
0x1800113d0  xor     r8d, r8d; hCryptProv
0x1800113d3  xor     edx, edx; dwEncodingType
0x1800113d5  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800113d8  call    cs:__imp_CertOpenStore
0x1800113de  test    rax, rax
0x1800113e1  jnz     short loc_18001141D
0x1800113e3  mov     rcx, [rbp+28h]; this
0x1800113e7  lea     r8, aCW1SSrcClientE_78; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x1800113ee  mov     edx, 147h; void *
0x1800113f3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800113f8  test    eax, eax
0x1800113fa  jns     short loc_180011428
0x1800113fc  lea     rcx, aFailedToCreate_2; "Failed to create enterprise certificate"...
0x180011403  mov     [rsp+80h+MatchAllKeyword], rcx
0x180011408  mov     dword ptr [rsp+80h+ppv], eax
0x18001140c  mov     r9d, edi
0x18001140f  mov     r8d, esi
0x180011412  xor     edx, edx
0x180011414  xor     ecx, ecx
0x180011416  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18001141b  jmp     short loc_180011428
0x18001141d  xor     edx, edx; dwFlags
0x18001141f  mov     rcx, rax; hCertStore
0x180011422  call    cs:__imp_CertCloseStore
0x180011428  mov     edx, 7530h; unsigned int
0x18001142d  mov     ecx, 4; unsigned int
0x180011432  call    ?UpdateServiceStatus@@YAXKK@Z; UpdateServiceStatus(ulong,ulong)
0x180011437  lea     rax, aServiceStatusI; "Service status is now SERVICE_RUNNING"
0x18001143e  mov     [rsp+80h+MatchAllKeyword], rax
0x180011443  mov     [rsp+80h+ppv], r12; int
0x180011448  mov     r9d, 5
0x18001144e  mov     r8d, esi
0x180011451  xor     edx, edx
0x180011453  xor     ecx, ecx
0x180011455  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
  ... truncated ...
```
