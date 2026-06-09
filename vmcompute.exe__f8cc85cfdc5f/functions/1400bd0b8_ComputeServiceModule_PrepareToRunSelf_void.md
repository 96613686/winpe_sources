# ComputeServiceModule::PrepareToRunSelf(void)

- ea: `0x1400bd0b8`
- end: `0x1400bd95f`
- name: `?PrepareToRunSelf@ComputeServiceModule@@QEAAXXZ`
- size: `2215`
- prototype: `void __fastcall(ComputeServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `46`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14013a928`

## callees

- `0x14001629c`
- `0x14001c898`
- `0x140033a7c`
- `0x140038078`
- `0x140059f84`
- `0x14005fd9c`
- `0x140064c5c`
- `0x14007ef00`
- `0x140080180`
- `0x1400886e4`
- `0x14009b288`
- `0x1400a94b0`
- `0x1400b710c`
- `0x1400bc8f4`
- `0x1400bd0b8`
- `0x1400bd968`
- `0x1400bda34`
- `0x1400bdac0`
- `0x1400bdc70`
- `0x1400bdcd0`
- `0x1400be4dc`
- `0x1400be508`
- `0x1400be594`
- `0x1400be670`
- `0x1400be760`
- `0x1400be808`
- `0x1400be8a8`
- `0x1400bed64`
- `0x1400bef80`
- `0x1400bf024`
- `0x1400bf168`
- `0x1400bf1c4`
- `0x1400c40e0`
- `0x1400fb29c`
- `0x14010f380`
- `0x1401332f0`
- `0x140134048`
- `0x140136d40`
- `0x140137c70`
- `0x14013842c`
- `0x14013a81c`
- `0x140206444`
- `0x140225cfc`
- `0x140233728`
- `0x14025bd9c`
- `0x1402c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400bd629`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400bd629`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400bd642`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400bd642`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400bd6e9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400bd6e9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400bd201`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400bd201`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400bd6ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400bd6ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400bd34c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400bd34c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400bd330`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400bd330`
- `ntdll!NtQuerySystemInformation` at `0x1400bd194`
- `ntdll!NtQuerySystemInformation` at `0x1400bd194`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400bd560`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x1400bd560`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400bd5b4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400bd5b4`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400bd264`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400bd264`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd3bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd8c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd919`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd3bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd411`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd8c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400bd919`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1400bd1b7`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1400bd1b7`
- `api-ms-win-core-libraryloader-l2-1-0!QueryOptionalDelayLoadedAPI` at `0x1400bd662`
- `api-ms-win-core-libraryloader-l2-1-0!QueryOptionalDelayLoadedAPI` at `0x1400bd662`

## string_xrefs

- `0x1400bd364`: `onecore\vm\common\vml\VmSecurity.h`
- `0x1400bd21e`: `onecore\vm\common\vml\VmModules.h`
- `0x1400bd15d`: `BreakOnServiceStart`
- `0x1400bd27f`: `onecore\vm\compute\service\host\main\computeservicemodule.cpp`
- `0x1400bd57b`: `onecore\vm\compute\service\host\main\computeservicemodule.cpp`
- `0x1400bd5cf`: `onecore\vm\compute\service\host\main\computeservicemodule.cpp`
- `0x1400bd609`: `onecore\vm\compute\service\host\main\computeservicemodule.cpp`
- `0x1400bd70f`: `onecore\vm\compute\service\host\main\computeservicemodule.cpp`
- `0x1400bd737`: `onecore\vm\compute\service\host\main\computeservicemodule.cpp`
- `0x1400bd65b`: `ccglaunchpad.dll`
- `0x1400bd622`: `computestorage.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall ComputeServiceModule::PrepareToRunSelf(ComputeServiceModule *this, HKEY a2)
{
  ComputeServiceModule *v2; // r14
  const struct _GUID *v3; // r8
  const char *v4; // r9
  HANDLE EventW; // rax
  __int64 v6; // rdx
  const char *v7; // r9
  int v8; // eax
  __int64 v9; // rcx
  HRESULT v10; // eax
  unsigned int v11; // r8d
  HANDLE CurrentProcess; // rax
  const char *v13; // r9
  Schema::Responses::System::CrashReportProcessDump *Information; // rdi
  Schema::Responses::System::CrashReportProcessDump *v15; // rdi
  const struct _ACL *Dacl; // rax
  const struct _ACL *v17; // rax
  HRESULT v18; // eax
  HRESULT v19; // eax
  int v20; // eax
  Schema::Responses::System::CrashReportProcessDump *Library; // rdi
  HMODULE ModuleHandleW; // rax
  int v23; // esi
  ComputeService *v24; // rcx
  bool v25; // al
  unsigned int v26; // edi
  DmGlobalMemoryBalancer *v27; // rsi
  int v28; // eax
  ComputeService::Vmwp *v29; // rcx
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  std::_Ref_count_base *v33; // rcx
  _QWORD *v34; // rdx
  const struct _GUID *v35; // rdx
  ComputeService::Rpc *v36; // rcx
  const struct _GUID *v37; // r8
  wil *v38; // rcx
  unsigned int v39; // ebx
  __int64 v40; // r9
  const struct _GUID *v41; // r8
  const unsigned int *dwImpLevel; // [rsp+28h] [rbp-290h]
  int dwAuthnLevel; // [rsp+20h] [rbp-298h]
  int dwAuthnLevela; // [rsp+20h] [rbp-298h]
  int dwAuthnLevelb; // [rsp+20h] [rbp-298h]
  const unsigned int *dwImpLevela; // [rsp+28h] [rbp-290h]
  const unsigned int *dwImpLevelb; // [rsp+28h] [rbp-290h]
  _QWORD v49[7]; // [rsp+60h] [rbp-258h] BYREF
  _QWORD *v50; // [rsp+98h] [rbp-220h]
  LPVOID SystemInformation; // [rsp+A0h] [rbp-218h] BYREF
  void *TokenHandle; // [rsp+A8h] [rbp-210h] BYREF
  Schema::Responses::System::CrashReportProcessDump *v53[2]; // [rsp+B0h] [rbp-208h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-1F8h]
  void *v55[10]; // [rsp+D0h] [rbp-1E8h] BYREF
  void *v56[10]; // [rsp+120h] [rbp-198h] BYREF
  void *v57[10]; // [rsp+170h] [rbp-148h] BYREF
  void *v58[10]; // [rsp+1C0h] [rbp-F8h] BYREF
  PSECURITY_DESCRIPTOR pSecDesc[2]; // [rsp+210h] [rbp-A8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v60; // [rsp+220h] [rbp-98h] BYREF
  HLOCAL hMem[4]; // [rsp+230h] [rbp-88h] BYREF
  unsigned __int16 v62[16]; // [rsp+250h] [rbp-68h] BYREF
  ComputeService::Vmwp *retaddr; // [rsp+2B8h] [rbp+0h]

  try
  {
    v2 = this;
    pSecDesc[1] = 0;
    pSecDesc[0] = &ComputeService::ComputeSystemSettingsStore::`vftable';
    if ( ComputeService::MachineLocalSettingsStore::OpenImpl(
           (ComputeService::MachineLocalSettingsStore *)pSecDesc,
           a2,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization\\Containers",
           L"Debug",
           0x20019u) )
    {
      LODWORD(TokenHandle) = 0;
      LODWORD(SystemInformation) = 4;
      ComputeService::MachineLocalSettingsStore::QueryValueImpl(
        (ComputeService::MachineLocalSettingsStore *)pSecDesc,
        L"BreakOnServiceStart",
        0x10u,
        (unsigned __int8 *)&TokenHandle,
        (unsigned int *)&SystemInformation);
      if ( (_DWORD)TokenHandle )
      {
        LOWORD(SystemInformation) = 0;
        NtQuerySystemInformation(SystemKernelDebuggerInformation, &SystemInformation, 2u, 0);
        if ( (_BYTE)SystemInformation || NtCurrentPeb()->BeingDebugged )
          DebugBreak();
      }
    }
    ComputeService::MachineLocalSettingsStore::~MachineLocalSettingsStore((ComputeService::MachineLocalSettingsStore *)pSecDesc);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\computeservicemodule.cpp",
      v4);
    v2 = this;
  }
  try
  {
    VmEventWriteCommon(&MSVCOMP_SERVICE_STARTING, 1u, v3, 0, 0, dwImpLevela);
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)v2 + 11) = EventW;
    if ( !EventW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x744,
        (unsigned int)"onecore\\vm\\common\\vml\\VmModules.h",
        v7);
    LOBYTE(v6) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsSecurityMitigation>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_HcsSecurityMitigation>::GetImpl'::`2'::impl,
      v6);
    v8 = lambda_d9e00ec6da64bf594248ef5e3291f9f4_::operator()();
    if ( v8 == 1 )
    {
      v9 = 5;
    }
    else
    {
      v9 = 1;
      if ( v8 == 2 )
        v9 = 3;
    }
    Vml::EnableStrictSecurityMitigationOptions(v9);
    v10 = CoInitializeEx(0, 0);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x8E,
        (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\computeservicemodule.cpp",
        (const char *)(unsigned int)v10,
        dwAuthnLevel);
    *((_BYTE *)v2 + 264) = 1;
    *(_OWORD *)pSecDesc = 0;
    Vml::VmSecurityDescriptor::VmSecurityDescriptor((Vml::VmSecurityDescriptor *)pSecDesc, L"O:BAG:BA", v11);
    TokenHandle = 0;
    memset_0(v56, 0, sizeof(v56));
    Vml::VmSid::VmSid((Vml::VmSid *)v56, 0);
    memset_0(v55, 0, sizeof(v55));
    Vml::VmSid::VmSid((Vml::VmSid *)v55, 0);
    memset_0(v58, 0, sizeof(v58));
    Vml::VmSid::VmSid((Vml::VmSid *)v58, L"S-1-5-11");
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1CE7,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        v13);
    v53[1] = 0;
    v53[0] = 0;
    Information = (Schema::Responses::System::CrashReportProcessDump *)Vml::VmAccessToken::_GetInformation(
                                                                         (Vml::VmAccessToken *)&TokenHandle,
                                                                         TokenUser);
    v53[0] = Information;
    Vml::VmSid::Assign((Vml::VmSid *)v56, *(PSID *)Information);
    if ( Information )
      LocalFree(Information);
    v53[1] = 0;
    v53[0] = 0;
    v15 = (Schema::Responses::System::CrashReportProcessDump *)Vml::VmAccessToken::_GetInformation(
                                                                 (Vml::VmAccessToken *)&TokenHandle,
                                                                 TokenPrimaryGroup);
    v53[0] = v15;
    Vml::VmSid::Assign((Vml::VmSid *)v55, *(PSID *)v15);
    if ( v15 )
      LocalFree(v15);
    *(_OWORD *)hMem = 0;
    Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)pSecDesc);
    Vml::VmDacl::VmDacl((Vml::VmDacl *)hMem, Dacl);
    v17 = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)pSecDesc);
    Vml::VmAcl::Assign((Vml::VmAcl *)hMem, v17);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)hMem, v56[0], 3u, 0, GRANT_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)hMem, v55[0], 3u, 0, GRANT_ACCESS);
    memset_0(v57, 0, sizeof(v57));
    Vml::VmSid::VmSid(
      (Vml::VmSid *)v57,
      L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704");
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)hMem, v58[0], 3u, 0, GRANT_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)hMem, v57[0], 0x1Fu, 0, GRANT_ACCESS);
    Vml::VmSecurityDescriptor::SetDacl((Vml::VmSecurityDescriptor *)pSecDesc, (const struct _ACL *)hMem[0]);
    Vml::VmSecurityDescriptor::MakeAbsolute((Vml::VmSecurityDescriptor *)pSecDesc);
    v18 = CoInitializeSecurity(pSecDesc[0], -1, 0, 0, 5u, 2u, 0, 0x4040u, 0);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\computeservicemodule.cpp",
        (const char *)(unsigned int)v18,
        dwAuthnLevela);
    SystemInformation = 0;
    v19 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &SystemInformation);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\computeservicemodule.cpp",
        (const char *)(unsigned int)v19,
        dwAuthnLevelb);
    v20 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)SystemInformation + 24LL))(
            SystemInformation,
            1,
            1);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\computeservicemodule.cpp",
        (const char *)(unsigned int)v20,
        dwAuthnLevelb);
    Library = (Schema::Responses::System::CrashReportProcessDump *)LoadLibraryExW(L"computestorage.dll", 0, 0x800u);
    v53[0] = Library;
    ModuleHandleW = GetModuleHandleW(0);
    if ( !(unsigned int)QueryOptionalDelayLoadedAPI(ModuleHandleW, "ccglaunchpad.dll", "CCGLaunch", 0)
      || (v23 = 13, !Library) )
    {
      v23 = 12;
    }
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v53);
    v25 = ComputeService::AreVirtualMachinesEnabled(v24);
    v26 = v23 | (2 * v25);
    if ( (((unsigned __int8)v23 | (unsigned __int8)(2 * v25)) & 2) != 0 )
    {
      EnterCriticalSection(&Vml::VmSingletonObject<DmGlobalMemoryBalancer,DmGlobalMemoryBalancer>::gm_SingletonLock);
      v53[0] = 0;
      if ( (unsigned __int8)Vml::VmSingletonObject<DmGlobalMemoryBalancer,DmGlobalMemoryBalancer>::TryOpenSharedInternal(v53) )
        v27 = v53[0];
      else
        v27 = (DmGlobalMemoryBalancer *)Vml::VmSingletonObject<DmGlobalMemoryBalancer,DmGlobalMemoryBalancer>::OpenSharedInternal();
      LeaveCriticalSection(&Vml::VmSingletonObject<DmGlobalMemoryBalancer,DmGlobalMemoryBalancer>::gm_SingletonLock);
      *((_QWORD *)v2 + 32) = v27;
      if ( !v27 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\computeservicemodule.cpp",
          (const char *)0x8007000ELL,
          dwAuthnLevelb);
      v28 = DmGlobalMemoryBalancer::Initialize(v27);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD7,
          (unsigned int)"onecore\\vm\\compute\\service\\host\\main\\computeservicemodule.cpp",
          (const char *)(unsigned int)v28,
          dwAuthnLevelb);
      ComputeService::Vmwp::CreateVmGroupSidMapping(retaddr);
      ComputeService::Vmwp::AdjustVmGroupPrivileges(v29);
    }
    v30 = (__int64 *)std::make_shared<ComputeService::Management::ComputeSystemManager,std::shared_ptr<ComputeService::Management::ComputeSystem> (&)(unsigned short const *,std::wstring const &,ComputeService::Management::ComputeSystemCreateContext const &,std::function<void (std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo_2 const &)>)>(v53);
    v31 = *v30;
    v32 = v30[1];
    *v30 = 0;
    v30[1] = 0;
    *((_QWORD *)v2 + 30) = v31;
    v33 = (std::_Ref_count_base *)*((_QWORD *)v2 + 31);
    *((_QWORD *)v2 + 31) = v32;
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    if ( v53[1] )
      std::_Ref_count_base::_Decref(v53[1]);
    ComputeService::RegisterSupportedOrchestrators(v26);
    ComputeService::InitializeComputeSystemHost(v26);
    *(_OWORD *)v53 = 0;
    v54 = 0;
    ComputeService::RecoveryStore::EnumerateSystems(v53);
    v49[0] = &std::_Func_impl_no_alloc<std::shared_ptr<ComputeService::Management::ComputeSystem> (*)(unsigned short const *,enum ComputeService::Management::ComputeSystemType,ComputeService::Management::ComputeSystemCreateContext const &,std::function<void (std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo_2 const &)>),std::shared_ptr<ComputeService::Management::ComputeSystem>,unsigned short const *,enum ComputeService::Management::ComputeSystemType,ComputeService::Management::ComputeSystemCreateContext const &,std::function<void (std::wstring const &,ComputeService::Management::ComputeSystemNotificationInfo_2 const &)>>::`vftable';
    v49[1] = &ComputeService::ComputeServiceSystemRecoveryFactory;
    v50 = v49;
    ComputeService::RecoverComputeSystems(v53, (char *)v2 + 240, v49);
    if ( v50 )
    {
      v34 = v49;
      LOBYTE(v34) = v50 != v49;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v50 + 32LL))(v50, v34);
    }
    if ( v53[0] )
    {
      std::_Destroy_range<std::allocator<Resource::Vpci::DeviceInstance>>(v53[0]);
      std::_Deallocate<16>(v53[0], 8 * ((signed __int64)(v54 - (unsigned __int64)v53[0]) >> 3));
    }
    ComputeService::Rpc::SetComputeSystemManager((char *)v2 + 240);
    ComputeService::Rpc::InitializeServer(v36, v35);
    std::function<void (unsigned short,unsigned short const *)>::operator=<void (&)(unsigned short,unsigned short const *),0>(g_HvsTraceFunctions);
    std::function<bool (unsigned short)>::operator=<int (&)(unsigned short),0>(qword_1403DD470);
    Vml::VmComPtr<IVmSimpleTaskEvents>::~VmComPtr<IVmSimpleTaskEvents>(&SystemInformation);
    Vml::VmSid::~VmSid((Vml::VmSid *)v57);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    Vml::VmSid::~VmSid((Vml::VmSid *)v58);
    Vml::VmSid::~VmSid((Vml::VmSid *)v55);
    Vml::VmSid::~VmSid((Vml::VmSid *)v56);
    Vml::VmAccessToken::~VmAccessToken((Vml::VmAccessToken *)&TokenHandle);
    if ( pSecDesc[0] )
      LocalFree(pSecDesc[0]);
    VmEventWriteCommon(&MSVCOMP_SERVICE_START_COMPLETED, 1u, v37, 0, 0, dwImpLevelb);
  }
  catch ( ... )
  {
    v39 = wil::ResultFromCaughtException(v38);
    v40 = v39;
    LODWORD(v40) = v39 & 0xEFFFFFFF;
    _snwprintf_s<16>(v62, 16, L"%%%%%u", v40);
    _snwprintf_s<16>(hMem, 16, L"0x%08X", v39 & 0xEFFFFFFF);
    if ( g_VmlEtwTrace )
    {
      VmCreateDataDescriptor(&v60, (unsigned int *)v53 + 1, (const unsigned __int16 *)hMem);
      VmCreateDataDescriptor((struct _EVENT_DATA_DESCRIPTOR *)pSecDesc, (unsigned int *)v53, v62);
      VmEventWriteCommon(
        &MSVCOMP_SERVICE_START_FAILED,
        1u,
        v41,
        2u,
        (const struct _EVENT_DATA_DESCRIPTOR *)pSecDesc,
        dwImpLevel);
    }
    ComputeServiceModule::CleanUpFromRunSelf(this);
    throw;
  }
}

```

## disassembly

```asm
0x1400bd0b8  push    rbx
0x1400bd0ba  push    rsi
0x1400bd0bb  push    rdi
0x1400bd0bc  push    r12
0x1400bd0be  push    r14
0x1400bd0c0  push    r15
0x1400bd0c2  sub     rsp, 288h
0x1400bd0c9  mov     rax, cs:__security_cookie
0x1400bd0d0  xor     rax, rsp
0x1400bd0d3  mov     [rsp+2B8h+var_48], rax
0x1400bd0db  mov     r14, rcx
0x1400bd0de  mov     [rsp+2B8h+var_268], rcx
0x1400bd0e3  xorps   xmm0, xmm0
0x1400bd0e6  movups  xmmword ptr [rsp+2B8h+pSecDesc], xmm0
0x1400bd0ee  xor     ebx, ebx
0x1400bd0f0  mov     [rsp+2B8h+pSecDesc+8], rbx
0x1400bd0f8  lea     rax, ??_7ComputeSystemSettingsStore@ComputeService@@6B@; const ComputeService::ComputeSystemSettingsStore::`vftable'
0x1400bd0ff  mov     [rsp+2B8h+pSecDesc], rax
0x1400bd107  mov     [rsp+2B8h+dwAuthnLevel], 20019h; samDesired
0x1400bd10f  lea     r9, aDebug; "Debug"
0x1400bd116  lea     r8, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400bd11d  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd125  call    ?OpenImpl@MachineLocalSettingsStore@ComputeService@@IEAA_NPEAUHKEY__@@PEBG1K@Z; ComputeService::MachineLocalSettingsStore::OpenImpl(HKEY__ *,ushort const *,ushort const *,ulong)
0x1400bd12a  test    al, al
0x1400bd12c  jz      loc_1400BD1C4
0x1400bd132  mov     dword ptr [rsp+2B8h+TokenHandle], ebx
0x1400bd139  mov     dword ptr [rsp+2B8h+SystemInformation], 4
0x1400bd144  lea     rax, [rsp+2B8h+SystemInformation]
0x1400bd14c  mov     qword ptr [rsp+2B8h+dwAuthnLevel], rax; unsigned int *
0x1400bd151  lea     r9, [rsp+2B8h+TokenHandle]; unsigned __int8 *
0x1400bd159  lea     r8d, [rbx+10h]; unsigned int
0x1400bd15d  lea     rdx, aBreakonservice; "BreakOnServiceStart"
0x1400bd164  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd16c  call    ?QueryValueImpl@MachineLocalSettingsStore@ComputeService@@AEBA_NPEBGKPEAEPEAK@Z; ComputeService::MachineLocalSettingsStore::QueryValueImpl(ushort const *,ulong,uchar *,ulong *)
0x1400bd171  cmp     dword ptr [rsp+2B8h+TokenHandle], ebx
0x1400bd178  jz      short loc_1400BD1C4
0x1400bd17a  mov     word ptr [rsp+2B8h+SystemInformation], bx
0x1400bd182  xor     r9d, r9d; ReturnLength
0x1400bd185  lea     r8d, [rbx+2]; SystemInformationLength
0x1400bd189  lea     rdx, [rsp+2B8h+SystemInformation]; SystemInformation
0x1400bd191  lea     ecx, [rbx+23h]; SystemInformationClass
0x1400bd194  call    cs:__imp_NtQuerySystemInformation
0x1400bd19b  nop     dword ptr [rax+rax+00h]
0x1400bd1a0  cmp     byte ptr [rsp+2B8h+SystemInformation], bl
0x1400bd1a7  jnz     short loc_1400BD1B7
0x1400bd1a9  mov     rax, gs:60h
0x1400bd1b2  cmp     [rax+2], bl
0x1400bd1b5  jz      short loc_1400BD1C4
0x1400bd1b7  call    cs:__imp_DebugBreak
0x1400bd1be  nop     dword ptr [rax+rax+00h]
0x1400bd1c3  nop
0x1400bd1c4  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd1cc  call    ??1MachineLocalSettingsStore@ComputeService@@UEAA@XZ; ComputeService::MachineLocalSettingsStore::~MachineLocalSettingsStore(void)
0x1400bd1d1  nop
0x1400bd1d2  jmp     short loc_1400BD1DB
0x1400bd1d4  xor     ebx, ebx
0x1400bd1d6  mov     r14, [rsp+2B8h+var_268]
0x1400bd1db  mov     qword ptr [rsp+2B8h+dwAuthnLevel], rbx; int
0x1400bd1e0  xor     r9d, r9d; unsigned int
0x1400bd1e3  lea     r15d, [r9+1]
0x1400bd1e7  mov     edx, r15d; unsigned int
0x1400bd1ea  lea     rcx, MSVCOMP_SERVICE_STARTING; EventDescriptor
0x1400bd1f1  call    ?VmEventWriteCommon@@YAXPEBU_EVENT_DESCRIPTOR@@IAEBU_GUID@@KPEBU_EVENT_DATA_DESCRIPTOR@@PEBI@Z; VmEventWriteCommon(_EVENT_DESCRIPTOR const *,uint,_GUID const &,ulong,_EVENT_DATA_DESCRIPTOR const *,uint const *)
0x1400bd1f6  nop
0x1400bd1f7  xor     r9d, r9d; lpName
0x1400bd1fa  xor     r8d, r8d; bInitialState
0x1400bd1fd  xor     edx, edx; bManualReset
0x1400bd1ff  xor     ecx, ecx; lpEventAttributes
0x1400bd201  call    cs:__imp_CreateEventW
0x1400bd208  nop     dword ptr [rax+rax+00h]
0x1400bd20d  mov     [r14+58h], rax
0x1400bd211  test    rax, rax
0x1400bd214  jnz     short loc_1400BD22F
0x1400bd216  mov     rcx, [rsp+2B8h]; this
0x1400bd21e  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmModules.h"
0x1400bd225  mov     edx, 744h; void *
0x1400bd22a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400bd22f  mov     dl, r15b
0x1400bd232  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HcsSecurityMitigation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HcsSecurityMitigation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsSecurityMitigation> `wil::Feature<__WilFeatureTraits_Feature_HcsSecurityMitigation>::GetImpl(void)'::`2'::impl
0x1400bd239  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HcsSecurityMitigation@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HcsSecurityMitigation>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1400bd23e  call    _lambda_d9e00ec6da64bf594248ef5e3291f9f4___operator__
0x1400bd243  mov     esi, 3
0x1400bd248  cmp     eax, r15d
0x1400bd24b  jnz     short loc_1400BD252
0x1400bd24d  lea     ecx, [rsi+2]
0x1400bd250  jmp     short loc_1400BD25B
0x1400bd252  mov     ecx, r15d
0x1400bd255  cmp     eax, 2
0x1400bd258  cmovz   ecx, esi
0x1400bd25b  call    ?EnableStrictSecurityMitigationOptions@Vml@@YAXW4MitigationOptions@1@@Z; Vml::EnableStrictSecurityMitigationOptions(Vml::MitigationOptions)
0x1400bd260  xor     edx, edx; dwCoInit
0x1400bd262  xor     ecx, ecx; pvReserved
0x1400bd264  call    cs:__imp_CoInitializeEx
0x1400bd26b  nop     dword ptr [rax+rax+00h]
0x1400bd270  mov     rcx, [rsp+2B8h]; this
0x1400bd278  test    eax, eax
0x1400bd27a  jns     short loc_1400BD290
0x1400bd27c  mov     r9d, eax; char *
0x1400bd27f  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\service\\host\\ma"...
0x1400bd286  mov     edx, 8Eh; void *
0x1400bd28b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400bd290  mov     [r14+108h], r15b
0x1400bd297  xorps   xmm0, xmm0
0x1400bd29a  movups  xmmword ptr [rsp+2B8h+pSecDesc], xmm0
0x1400bd2a2  lea     rdx, aOBagBa; "O:BAG:BA"
0x1400bd2a9  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd2b1  call    ??0VmSecurityDescriptor@Vml@@QEAA@PEBGK@Z; Vml::VmSecurityDescriptor::VmSecurityDescriptor(ushort const *,ulong)
0x1400bd2b6  nop
0x1400bd2b7  mov     [rsp+2B8h+TokenHandle], rbx
0x1400bd2bf  mov     r12d, 50h ; 'P'
0x1400bd2c5  mov     r8d, r12d; Size
0x1400bd2c8  xor     edx, edx; Val
0x1400bd2ca  lea     rcx, [rsp+2B8h+var_198]; void *
0x1400bd2d2  call    memset_0
0x1400bd2d7  xor     edx, edx; pSourceSid
0x1400bd2d9  lea     rcx, [rsp+2B8h+var_198]; this
0x1400bd2e1  call    ??0VmSid@Vml@@QEAA@PEAX@Z; Vml::VmSid::VmSid(void *)
0x1400bd2e6  nop
0x1400bd2e7  mov     r8d, r12d; Size
0x1400bd2ea  xor     edx, edx; Val
0x1400bd2ec  lea     rcx, [rsp+2B8h+var_1E8]; void *
0x1400bd2f4  call    memset_0
0x1400bd2f9  xor     edx, edx; pSourceSid
0x1400bd2fb  lea     rcx, [rsp+2B8h+var_1E8]; this
0x1400bd303  call    ??0VmSid@Vml@@QEAA@PEAX@Z; Vml::VmSid::VmSid(void *)
0x1400bd308  nop
0x1400bd309  mov     r8d, r12d; Size
0x1400bd30c  xor     edx, edx; Val
0x1400bd30e  lea     rcx, [rsp+2B8h+var_F8]; void *
0x1400bd316  call    memset_0
0x1400bd31b  lea     rdx, aS1511; "S-1-5-11"
0x1400bd322  lea     rcx, [rsp+2B8h+var_F8]; this
0x1400bd32a  call    ??0VmSid@Vml@@QEAA@PEBG@Z; Vml::VmSid::VmSid(ushort const *)
0x1400bd32f  nop
0x1400bd330  call    cs:__imp_GetCurrentProcess
0x1400bd337  nop     dword ptr [rax+rax+00h]
0x1400bd33c  lea     r8, [rsp+2B8h+TokenHandle]; TokenHandle
0x1400bd344  lea     edx, [r12-48h]; DesiredAccess
0x1400bd349  mov     rcx, rax; ProcessHandle
0x1400bd34c  call    cs:__imp_OpenProcessToken
0x1400bd353  nop     dword ptr [rax+rax+00h]
0x1400bd358  mov     rcx, [rsp+2B8h]; this
0x1400bd360  test    eax, eax
0x1400bd362  jnz     short loc_1400BD375
0x1400bd364  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x1400bd36b  mov     edx, 1CE7h; void *
0x1400bd370  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400bd375  xorps   xmm0, xmm0
0x1400bd378  movups  xmmword ptr [rsp+2B8h+var_208], xmm0
0x1400bd380  mov     [rsp+2B8h+var_208], rbx
0x1400bd388  mov     edx, r15d; enum _TOKEN_INFORMATION_CLASS
0x1400bd38b  lea     rcx, [rsp+2B8h+TokenHandle]; this
0x1400bd393  call    ?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)
0x1400bd398  mov     rdi, rax
0x1400bd39b  mov     [rsp+2B8h+var_208], rax
0x1400bd3a3  mov     rdx, [rax]; pSourceSid
0x1400bd3a6  lea     rcx, [rsp+2B8h+var_198]; this
0x1400bd3ae  call    ?Assign@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Assign(void *)
0x1400bd3b3  nop
0x1400bd3b4  test    rdi, rdi
0x1400bd3b7  jz      short loc_1400BD3C8
0x1400bd3b9  mov     rcx, rdi; hMem
0x1400bd3bc  call    cs:__imp_LocalFree
0x1400bd3c3  nop     dword ptr [rax+rax+00h]
0x1400bd3c8  xorps   xmm0, xmm0
0x1400bd3cb  movups  xmmword ptr [rsp+2B8h+var_208], xmm0
0x1400bd3d3  mov     [rsp+2B8h+var_208], rbx
0x1400bd3db  mov     edx, 5; enum _TOKEN_INFORMATION_CLASS
0x1400bd3e0  lea     rcx, [rsp+2B8h+TokenHandle]; this
0x1400bd3e8  call    ?_GetInformation@VmAccessToken@Vml@@AEBAPEAXW4_TOKEN_INFORMATION_CLASS@@@Z; Vml::VmAccessToken::_GetInformation(_TOKEN_INFORMATION_CLASS)
0x1400bd3ed  mov     rdi, rax
0x1400bd3f0  mov     [rsp+2B8h+var_208], rax
0x1400bd3f8  mov     rdx, [rax]; pSourceSid
0x1400bd3fb  lea     rcx, [rsp+2B8h+var_1E8]; this
0x1400bd403  call    ?Assign@VmSid@Vml@@QEAAXPEAX@Z; Vml::VmSid::Assign(void *)
0x1400bd408  nop
0x1400bd409  test    rdi, rdi
0x1400bd40c  jz      short loc_1400BD41D
0x1400bd40e  mov     rcx, rdi; hMem
0x1400bd411  call    cs:__imp_LocalFree
0x1400bd418  nop     dword ptr [rax+rax+00h]
0x1400bd41d  xorps   xmm0, xmm0
0x1400bd420  movups  xmmword ptr [rsp+2B8h+hMem], xmm0
0x1400bd428  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd430  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400bd435  mov     rdx, rax; struct _ACL *
0x1400bd438  lea     rcx, [rsp+2B8h+hMem]; this
0x1400bd440  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x1400bd445  nop
0x1400bd446  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd44e  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x1400bd453  mov     rdx, rax; struct _ACL *
0x1400bd456  lea     rcx, [rsp+2B8h+hMem]; this
0x1400bd45e  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x1400bd463  mov     [rsp+2B8h+dwAuthnLevel], r15d; enum _ACCESS_MODE
0x1400bd468  xor     r9d, r9d; unsigned int
0x1400bd46b  mov     r8d, esi; unsigned int
0x1400bd46e  mov     rdx, [rsp+2B8h+var_198]; void *
0x1400bd476  lea     rcx, [rsp+2B8h+hMem]; this
0x1400bd47e  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400bd483  mov     [rsp+2B8h+dwAuthnLevel], r15d; enum _ACCESS_MODE
0x1400bd488  xor     r9d, r9d; unsigned int
0x1400bd48b  mov     r8d, esi; unsigned int
0x1400bd48e  mov     rdx, [rsp+2B8h+var_1E8]; void *
0x1400bd496  lea     rcx, [rsp+2B8h+hMem]; this
0x1400bd49e  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400bd4a3  mov     r8, r12; Size
0x1400bd4a6  xor     edx, edx; Val
0x1400bd4a8  lea     rcx, [rsp+2B8h+var_148]; void *
0x1400bd4b0  call    memset_0
0x1400bd4b5  lea     rdx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x1400bd4bc  lea     rcx, [rsp+2B8h+var_148]; this
0x1400bd4c4  call    ??0VmSid@Vml@@QEAA@PEBG@Z; Vml::VmSid::VmSid(ushort const *)
0x1400bd4c9  nop
0x1400bd4ca  mov     [rsp+2B8h+dwAuthnLevel], r15d; enum _ACCESS_MODE
0x1400bd4cf  xor     r9d, r9d; unsigned int
0x1400bd4d2  mov     r8d, esi; unsigned int
0x1400bd4d5  mov     rdx, [rsp+2B8h+var_F8]; void *
0x1400bd4dd  lea     rcx, [rsp+2B8h+hMem]; this
0x1400bd4e5  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400bd4ea  mov     [rsp+2B8h+dwAuthnLevel], r15d; enum _ACCESS_MODE
0x1400bd4ef  xor     r9d, r9d; unsigned int
0x1400bd4f2  lea     r8d, [r9+1Fh]; unsigned int
0x1400bd4f6  mov     rdx, [rsp+2B8h+var_148]; void *
0x1400bd4fe  lea     rcx, [rsp+2B8h+hMem]; this
0x1400bd506  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x1400bd50b  mov     rdx, [rsp+2B8h+hMem]; struct _ACL *
0x1400bd513  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd51b  call    ?SetDacl@VmSecurityDescriptor@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmSecurityDescriptor::SetDacl(_ACL const *)
0x1400bd520  lea     rcx, [rsp+2B8h+pSecDesc]; this
0x1400bd528  call    ?MakeAbsolute@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeAbsolute(void)
0x1400bd52d  mov     [rsp+2B8h+pReserved3], rbx; pReserved3
0x1400bd532  mov     [rsp+2B8h+dwCapabilities], 4040h; dwCapabilities
0x1400bd53a  mov     [rsp+2B8h+pAuthList], rbx; pAuthList
0x1400bd53f  mov     dword ptr [rsp+2B8h+dwImpLevel], 2; unsigned int *
0x1400bd547  mov     [rsp+2B8h+dwAuthnLevel], 5; int
0x1400bd54f  xor     r9d, r9d; pReserved1
0x1400bd552  xor     r8d, r8d; asAuthSvc
0x1400bd555  or      edx, 0FFFFFFFFh; cAuthSvc
0x1400bd558  mov     rcx, [rsp+2B8h+pSecDesc]; pSecDesc
0x1400bd560  call    cs:__imp_CoInitializeSecurity
0x1400bd567  nop     dword ptr [rax+rax+00h]
0x1400bd56c  mov     rcx, [rsp+2B8h]; this
0x1400bd574  test    eax, eax
0x1400bd576  jns     short loc_1400BD58C
0x1400bd578  mov     r9d, eax; char *
0x1400bd57b  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\service\\host\\ma"...
0x1400bd582  mov     edx, 0B9h; void *
0x1400bd587  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400bd58c  mov     [rsp+2B8h+SystemInformation], rbx
0x1400bd594  lea     rax, [rsp+2B8h+SystemInformation]
0x1400bd59c  mov     qword ptr [rsp+2B8h+dwAuthnLevel], rax; int
0x1400bd5a1  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1400bd5a8  mov     r8d, r15d; dwClsContext
0x1400bd5ab  xor     edx, edx; pUnkOuter
0x1400bd5ad  lea     rcx, CLSID_GlobalOptions; rclsid
0x1400bd5b4  call    cs:__imp_CoCreateInstance
0x1400bd5bb  nop     dword ptr [rax+rax+00h]
0x1400bd5c0  mov     rcx, [rsp+2B8h]; this
0x1400bd5c8  test    eax, eax
0x1400bd5ca  jns     short loc_1400BD5E0
0x1400bd5cc  mov     r9d, eax; char *
0x1400bd5cf  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\service\\host\\ma"...
0x1400bd5d6  mov     edx, 0C4h; void *
0x1400bd5db  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400bd5e0  mov     rcx, [rsp+2B8h+SystemInformation]
0x1400bd5e8  mov     rax, [rcx]
0x1400bd5eb  mov     r8, r15
0x1400bd5ee  mov     edx, r15d
0x1400bd5f1  mov     rax, [rax+18h]
0x1400bd5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400bd5fa  mov     rcx, [rsp+2B8h]; this
0x1400bd602  test    eax, eax
0x1400bd604  jns     short loc_1400BD61A
0x1400bd606  mov     r9d, eax; char *
0x1400bd609  lea     r8, aOnecoreVmCompu_41; "onecore\\vm\\compute\\service\\host\\ma"...
0x1400bd610  mov     edx, 0C8h; void *
0x1400bd615  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400bd61a  xor     edx, edx; hFile
0x1400bd61c  mov     r8d, 800h; dwFlags
0x1400bd622  lea     rcx, LibFileName; "computestorage.dll"
0x1400bd629  call    cs:__imp_LoadLibraryExW
0x1400bd630  nop     dword ptr [rax+rax+00h]
0x1400bd635  mov     rdi, rax
0x1400bd638  mov     [rsp+2B8h+var_208], rax
0x1400bd640  xor     ecx, ecx; lpModuleName
0x1400bd642  call    cs:__imp_GetModuleHandleW
0x1400bd649  nop     dword ptr [rax+rax+00h]
0x1400bd64e  mov     rcx, rax
0x1400bd651  xor     r9d, r9d
0x1400bd654  lea     r8, aCcglaunch_0; "CCGLaunch"
0x1400bd65b  lea     rdx, aCcglaunchpadDl_0; "ccglaunchpad.dll"
0x1400bd662  call    cs:__imp_QueryOptionalDelayLoadedAPI
0x1400bd669  nop     dword ptr [rax+rax+00h]
0x1400bd66e  test    eax, eax
0x1400bd670  jz      short loc_1400BD67C
0x1400bd672  test    rdi, rdi
0x1400bd675  mov     esi, 0Dh
0x1400bd67a  jnz     short loc_1400BD681
0x1400bd67c  mov     esi, 0Ch
  ... truncated ...
```
