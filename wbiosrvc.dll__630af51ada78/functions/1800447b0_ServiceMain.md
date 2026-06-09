# ServiceMain

- ea: `0x1800447b0`
- end: `0x180044a90`
- name: `ServiceMain`
- size: `736`
- prototype: `int()`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800119c4`
- `0x18001358c`
- `0x180013810`
- `0x1800168cc`
- `0x18001d378`
- `0x180020e2c`
- `0x18002de8c`
- `0x18003576c`
- `0x180036b00`
- `0x180039a8c`
- `0x18003b80c`
- `0x180040240`
- `0x1800447b0`
- `0x180057908`
- `0x18006963c`
- `0x18006e030`
- `0x18006e4c4`
- `0x18006e504`
- `0x18006e540`
- `0x180072448`
- `0x18007327c`
- `0x18007330c`
- `0x180073b8c`
- `0x180073ee4`
- `0x1800751e8`
- `0x180075284`
- `0x1800d2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800447e8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800447e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800448ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800448ec`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180044866`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800448df`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004493e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180044866`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800448df`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18004493e`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18004480f`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18004480f`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1800449a7`
- `RPCRT4!RpcServerInterfaceGroupActivate` at `0x1800449a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
int ServiceMain()
{
  HANDLE EventW; // rax
  SERVICE_STATUS_HANDLE v1; // rax
  __int64 (__fastcall *v2)(SERVICE_STATUS_HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int); // rax
  DWORD v3; // eax
  _QWORD *v4; // rax
  struct CRpcDispatcher *v5; // rax
  CHardwareManager *v6; // rax
  CHardwareManager *v7; // rax
  CHardwareManager *v8; // rax
  CHardwareManager *v9; // rax
  unsigned __int8 v10; // dl
  CHardwareManager *v11; // rax
  CHardwareManager *v12; // rax
  CHardwareManager *v13; // rcx
  _QWORD *v15; // [rsp+60h] [rbp+18h]

  *(_OWORD *)&g_ServiceContext.dwServiceType = 0;
  *(_OWORD *)&g_ServiceContext.dwServiceSpecificExitCode = 0;
  *(_OWORD *)&hServiceStatus = 0;
  hObject = 0;
  g_ControlFlags = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  hObject = EventW;
  if ( EventW )
  {
    v1 = RegisterServiceCtrlHandlerExW(L"wbiosrvc", WbioServiceCtrlHandler, 0);
    hServiceStatus = v1;
    if ( !v1 )
      goto LABEL_8;
    g_ServiceContext.dwServiceType = 32;
    *(_QWORD *)&g_ServiceContext.dwCurrentState = 2;
    *(_QWORD *)&g_ServiceContext.dwWin32ExitCode = 0;
    g_ServiceContext.dwWaitHint = 10000;
    g_ServiceContext.dwCheckPoint = 0;
    if ( !SetServiceStatus(v1, &g_ServiceContext) )
      goto LABEL_8;
    CThread::thread_list(0);
    if ( !qword_1801100F8 )
      goto LABEL_8;
    v2 = *(__int64 (__fastcall **)(SERVICE_STATUS_HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_1801100F8 + 192);
    if ( !v2 )
      goto LABEL_8;
    v3 = v2(&hServiceStatus + 1, L"wbiosrvc", hObject, WbioStopCallback, 0, 24);
    if ( v3 )
    {
      g_ServiceContext.dwWin32ExitCode = v3;
      g_ServiceContext.dwCurrentState = 1;
      SetServiceStatus(hServiceStatus, &g_ServiceContext);
LABEL_8:
      LODWORD(EventW) = CloseHandle(hObject);
      return (int)EventW;
    }
    g_MaxEtwLoggingLevel = 3;
    if ( (unsigned int)McGenEventRegister_EventRegister() )
      goto LABEL_8;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
      CEssStateManager::SetNonVsmState();
    g_ServiceContext.dwControlsAccepted = 1345;
    g_ServiceContext.dwCurrentState = 4;
    SetServiceStatus(hServiceStatus, &g_ServiceContext);
    try
    {
      v15 = operator new(0x10u);
      *v15 = 0;
      v15[1] = 0;
      v4 = operator new(0xA0u);
      *v4 = v4;
      v4[1] = v4;
      v4[2] = v4;
      *((_WORD *)v4 + 12) = 257;
      *v15 = v4;
      g_FUS_Manager = v15;
      CServer::Initialize(hServiceStatus);
      byte_180110100 = 1;
    }
    catch ( std::bad_alloc )
    {
      LODWORD(EventW) = CloseHandle(hObject);
      return (int)EventW;
    }
    catch ( wil::ResultException )
    {
      LODWORD(EventW) = CloseHandle(hObject);
      return (int)EventW;
    }
    v5 = CRpcDispatcher::Instance();
    RpcServerInterfaceGroupActivate(*((_QWORD *)v5 + 2));
    v6 = CHardwareManager::Instance();
    CHardwareManager::EnablePnpNotifications(v6);
    v7 = CHardwareManager::Instance();
    CHardwareManager::RegisterPowerNotifications(v7);
    v8 = CHardwareManager::Instance();
    CHardwareManager::ScanForVirtualSensors(v8);
    v9 = CHardwareManager::Instance();
    ((void (__fastcall *)(CHardwareManager *, unsigned __int8))CHardwareManager::ScanForPhysicalSensors)(v9, v10);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::GetImpl'::`2'::impl) )
    {
      CEventManager::Instance();
      CEventManager::DeleteCorruptedEnrollments();
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
    {
      CEssStateManager::ProcessEssChangeIfDetected();
    }
    else
    {
      CHardwareManager::Instance();
      if ( CHardwareManager::IsPeripheralsWithESSChangeDetected() )
      {
        CHardwareManager::Instance();
        CHardwareManager::ProcessPeripheralsWithESSChange();
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::GetImpl'::`2'::impl) )
      CEssStateManager::MatchRegistryWithEssState();
    v11 = CHardwareManager::Instance();
    CHardwareManager::SetInitializationCompleteEvent(v11);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
      CEssStateManager::LogEssStateEvent();
    v12 = CHardwareManager::Instance();
    if ( CHardwareManager::CountLogonCapableSystemPoolUnits(v12) )
      WbioSetServiceStartupPolicy();
    v13 = CHardwareManager::Instance();
    LODWORD(EventW) = CHardwareManager::WriteAvailableBiometricUnitsToCache(v13);
  }
  return (int)EventW;
}

```

## disassembly

```asm
0x1800447b0  push    rbx
0x1800447b2  sub     rsp, 40h
0x1800447b6  xorps   xmm0, xmm0
0x1800447b9  xor     eax, eax
0x1800447bb  movups  xmmword ptr cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwServiceType, xmm0; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x1800447c2  movups  xmmword ptr cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwServiceSpecificExitCode, xmm0; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x1800447c9  movups  cs:hServiceStatus, xmm0
0x1800447d0  mov     cs:hObject, rax
0x1800447d7  mov     cs:?g_ControlFlags@@3JC, eax; long volatile g_ControlFlags
0x1800447dd  xor     r9d, r9d; lpName
0x1800447e0  xor     r8d, r8d; bInitialState
0x1800447e3  lea     edx, [rax+1]; bManualReset
0x1800447e6  xor     ecx, ecx; lpEventAttributes
0x1800447e8  call    cs:__imp_CreateEventW
0x1800447ee  mov     cs:hObject, rax
0x1800447f5  test    rax, rax
0x1800447f8  jz      loc_1800448F2
0x1800447fe  xor     r8d, r8d; lpContext
0x180044801  lea     rdx, WbioServiceCtrlHandler; lpHandlerProc
0x180044808  lea     rcx, ServiceName; "wbiosrvc"
0x18004480f  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180044815  mov     qword ptr cs:hServiceStatus, rax
0x18004481c  test    rax, rax
0x18004481f  jz      loc_1800448E5
0x180044825  mov     cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwServiceType, 20h ; ' '; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x18004482f  mov     qword ptr cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwCurrentState, 2; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x18004483a  mov     qword ptr cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwWin32ExitCode, 0; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x180044845  mov     cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwWaitHint, 2710h; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x18004484f  mov     cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwCheckPoint, 0; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x180044859  lea     rbx, ?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A; _unnamed_type_g_ServiceContext_ g_ServiceContext
0x180044860  mov     rdx, rbx; lpServiceStatus
0x180044863  mov     rcx, rax; hServiceStatus
0x180044866  call    cs:__imp_SetServiceStatus
0x18004486c  test    eax, eax
0x18004486e  jz      short loc_1800448E5
0x180044870  xor     ecx, ecx
0x180044872  call    ?thread_list@CThread@@CAJPEAV?$locked_pointer@V?$list@PEAVCThread@@V?$allocator@PEAVCThread@@@std@@@std@@@@@Z; CThread::thread_list(locked_pointer<std::list<CThread *>> *)
0x180044877  mov     rax, cs:qword_1801100F8
0x18004487e  test    rax, rax
0x180044881  jz      short loc_1800448E5
0x180044883  mov     rax, [rax+0C0h]
0x18004488a  test    rax, rax
0x18004488d  jz      short loc_1800448E5
0x18004488f  mov     [rsp+48h+var_20], 18h
0x180044897  mov     [rsp+48h+var_28], 0
0x1800448a0  lea     r9, WbioStopCallback
0x1800448a7  mov     r8, cs:hObject
0x1800448ae  lea     rdx, ServiceName; "wbiosrvc"
0x1800448b5  lea     rcx, hServiceStatus+8
0x1800448bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800448c1  test    eax, eax
0x1800448c3  jz      short loc_1800448F8
0x1800448c5  mov     cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwWin32ExitCode, eax; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x1800448cb  mov     cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwCurrentState, 1; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x1800448d5  mov     rdx, rbx; lpServiceStatus
0x1800448d8  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x1800448df  call    cs:__imp_SetServiceStatus
0x1800448e5  mov     rcx, cs:hObject; hObject
0x1800448ec  call    cs:__imp_CloseHandle
0x1800448f2  add     rsp, 40h
0x1800448f6  pop     rbx
0x1800448f7  retn
0x1800448f8  mov     cs:?g_MaxEtwLoggingLevel@@3W4WBioEventLevel@@A, 3; WBioEventLevel g_MaxEtwLoggingLevel
0x180044902  call    McGenEventRegister_EventRegister
0x180044907  test    eax, eax
0x180044909  jnz     short loc_1800448E5
0x18004490b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180044912  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180044917  test    al, al
0x180044919  jz      short loc_180044920
0x18004491b  call    ?SetNonVsmState@CEssStateManager@@SAXXZ; CEssStateManager::SetNonVsmState(void)
0x180044920  mov     cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwControlsAccepted, 541h; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x18004492a  mov     cs:?g_ServiceContext@@3U_unnamed_type_g_ServiceContext_@@A.dwCurrentState, 4; _unnamed_type_g_ServiceContext_ g_ServiceContext ...
0x180044934  mov     rdx, rbx; lpServiceStatus
0x180044937  mov     rcx, qword ptr cs:hServiceStatus; hServiceStatus
0x18004493e  call    cs:__imp_SetServiceStatus
0x180044944  nop
0x180044945  mov     ecx, 10h; Size
0x18004494a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004494f  mov     rbx, rax
0x180044952  mov     [rsp+48h+arg_10], rax
0x180044957  mov     qword ptr [rax], 0
0x18004495e  mov     qword ptr [rax+8], 0
0x180044966  mov     ecx, 0A0h; Size
0x18004496b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180044970  mov     [rax], rax
0x180044973  mov     [rax+8], rax
0x180044977  mov     [rax+10h], rax
0x18004497b  mov     word ptr [rax+18h], 101h
0x180044981  mov     [rbx], rax
0x180044984  mov     cs:?g_FUS_Manager@@3PEAVCFUSManager@@EA, rbx; CFUSManager * g_FUS_Manager
0x18004498b  mov     rcx, qword ptr cs:hServiceStatus; struct SERVICE_STATUS_HANDLE__ *
0x180044992  call    ?Initialize@CServer@@SAXPEAUSERVICE_STATUS_HANDLE__@@@Z; CServer::Initialize(SERVICE_STATUS_HANDLE__ *)
0x180044997  mov     cs:byte_180110100, 1
0x18004499e  call    ?Instance@CRpcDispatcher@@SAAEAV1@XZ; CRpcDispatcher::Instance(void)
0x1800449a3  mov     rcx, [rax+10h]
0x1800449a7  call    cs:__imp_RpcServerInterfaceGroupActivate
0x1800449ad  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800449b2  mov     rcx, rax; this
0x1800449b5  call    ?EnablePnpNotifications@CHardwareManager@@QEAAJXZ; CHardwareManager::EnablePnpNotifications(void)
0x1800449ba  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800449bf  mov     rcx, rax; this
0x1800449c2  call    ?RegisterPowerNotifications@CHardwareManager@@QEAAJXZ; CHardwareManager::RegisterPowerNotifications(void)
0x1800449c7  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800449cc  mov     rcx, rax; this
0x1800449cf  call    ?ScanForVirtualSensors@CHardwareManager@@QEAAJXZ; CHardwareManager::ScanForVirtualSensors(void)
0x1800449d4  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x1800449d9  mov     rcx, rax; this
0x1800449dc  call    ?ScanForPhysicalSensors@CHardwareManager@@QEAAJE@Z; CHardwareManager::ScanForPhysicalSensors(uchar)
0x1800449e1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments> `wil::Feature<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::GetImpl(void)'::`2'::impl
0x1800449e8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2DeleteCorruptedEssEnrollments>::__private_IsEnabled(void)
0x1800449ed  test    al, al
0x1800449ef  jz      short loc_1800449FB
0x1800449f1  call    ?Instance@CEventManager@@SAAEAV1@XZ; CEventManager::Instance(void)
0x1800449f6  call    ?DeleteCorruptedEnrollments@CEventManager@@SAXXZ; CEventManager::DeleteCorruptedEnrollments(void)
0x1800449fb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180044a02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180044a07  test    al, al
0x180044a09  jz      short loc_180044A12
0x180044a0b  call    ?ProcessEssChangeIfDetected@CEssStateManager@@SAXXZ; CEssStateManager::ProcessEssChangeIfDetected(void)
0x180044a10  jmp     short loc_180044A2A
0x180044a12  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180044a17  call    ?IsPeripheralsWithESSChangeDetected@CHardwareManager@@SA_NXZ; CHardwareManager::IsPeripheralsWithESSChangeDetected(void)
0x180044a1c  test    al, al
0x180044a1e  jz      short loc_180044A2A
0x180044a20  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180044a25  call    ?ProcessPeripheralsWithESSChange@CHardwareManager@@SAXXZ; CHardwareManager::ProcessPeripheralsWithESSChange(void)
0x180044a2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_K2EnrollmentCorruption@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_K2EnrollmentCorruption@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2EnrollmentCorruption> `wil::Feature<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::GetImpl(void)'::`2'::impl
0x180044a31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_K2EnrollmentCorruption@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_K2EnrollmentCorruption>::__private_IsEnabled(void)
0x180044a36  test    al, al
0x180044a38  jz      short loc_180044A3F
0x180044a3a  call    ?MatchRegistryWithEssState@CEssStateManager@@SAXXZ; CEssStateManager::MatchRegistryWithEssState(void)
0x180044a3f  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180044a44  mov     rcx, rax; this
0x180044a47  call    ?SetInitializationCompleteEvent@CHardwareManager@@QEAAXXZ; CHardwareManager::SetInitializationCompleteEvent(void)
0x180044a4c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180044a53  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180044a58  test    al, al
0x180044a5a  jz      short loc_180044A61
0x180044a5c  call    ?LogEssStateEvent@CEssStateManager@@SAXXZ; CEssStateManager::LogEssStateEvent(void)
0x180044a61  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180044a66  mov     rcx, rax; this
0x180044a69  call    ?CountLogonCapableSystemPoolUnits@CHardwareManager@@QEAA_KXZ; CHardwareManager::CountLogonCapableSystemPoolUnits(void)
0x180044a6e  test    rax, rax
0x180044a71  jz      short loc_180044A78
0x180044a73  call    WbioSetServiceStartupPolicy
0x180044a78  call    ?Instance@CHardwareManager@@SAAEAV1@XZ; CHardwareManager::Instance(void)
0x180044a7d  mov     rcx, rax; this
0x180044a80  add     rsp, 40h
0x180044a84  pop     rbx
0x180044a85  jmp     ?WriteAvailableBiometricUnitsToCache@CHardwareManager@@QEBAJXZ; CHardwareManager::WriteAvailableBiometricUnitsToCache(void)
0x180044a8a  add     rsp, 40h
0x180044a8e  pop     rbx
0x180044a8f  retn
```
