# Microsoft::Diagnostics::LifetimeManager::InitializeInProc(Microsoft::Diagnostics::LifetimeManager::InProcInitConfig const &)

- ea: `0x18006d4d4`
- end: `0x18006dd06`
- name: `?InitializeInProc@LifetimeManager@Diagnostics@Microsoft@@QEAAXAEBUInProcInitConfig@123@@Z`
- size: `2098`
- prototype: `void __fastcall(Microsoft::Diagnostics::LifetimeManager *__hidden this, const struct Microsoft::Diagnostics::LifetimeManager::InProcInitConfig *)`
- caller_count: `1`
- callee_count: `62`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a2b98`

## callees

- `0x18001d160`
- `0x180020fbc`
- `0x180035698`
- `0x1800363b4`
- `0x180048ff4`
- `0x180052d3c`
- `0x180052d7c`
- `0x180053218`
- `0x18005479c`
- `0x180065dec`
- `0x18006cff0`
- `0x18006d4d4`
- `0x18006dd10`
- `0x18006dd38`
- `0x18006dd98`
- `0x18006ddbc`
- `0x18006de18`
- `0x18006de38`
- `0x18006eec8`
- `0x18006ef00`
- `0x18006f018`
- `0x18006f088`
- `0x18006f0c0`
- `0x18006f0e4`
- `0x18006f140`
- `0x18006f178`
- `0x18006f24c`
- `0x18006f26c`
- `0x18006f2a4`
- `0x18006f2d4`
- `0x18006f334`
- `0x18006f6c8`
- `0x18006f6f8`
- `0x18006f718`
- `0x18006f73c`
- `0x18006f79c`
- `0x18006f91c`
- `0x180094c8c`
- `0x180098d5c`
- `0x1800a0d08`
- `0x1800bc2e0`
- `0x1800d0d9c`
- `0x1800d6620`
- `0x1800e024c`
- `0x1800f5954`
- `0x18010621c`
- `0x18012de40`
- `0x18012de64`
- `0x1801680a0`
- `0x180169c14`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006d5af`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006d5af`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x18006d847`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x18006d847`

## string_xrefs

- `0x18006d58e`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d5cd`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d653`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d69e`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d6e9`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d734`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d76f`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d802`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006d861`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`
- `0x18006da08`: `onecore\base\telemetry\utc\service\engine\lifetimemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Microsoft::Diagnostics::LifetimeManager::InitializeInProc(
        Microsoft::Diagnostics::LifetimeManager *this,
        const struct Microsoft::Diagnostics::LifetimeManager::InProcInitConfig *a2)
{
  const WCHAR *v4; // rdi
  const WCHAR *v5; // rcx
  int Key; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  _QWORD *v13; // rax
  __int64 *v14; // rax
  __int64 v15; // rcx
  __int64 *v16; // rax
  __int64 v17; // rcx
  __int64 *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 *v21; // rax
  __int64 v22; // rcx
  __int64 *v23; // rax
  __int64 v24; // rcx
  __int64 *v25; // rax
  __int64 v26; // rcx
  const char *v27; // r9
  __int64 v28; // rdi
  __int64 v29; // rbx
  struct Microsoft::Diagnostics::HeartbeatManager *HeartbeatManager; // rax
  __int64 *v31; // rax
  __int64 v32; // rcx
  __int64 v33; // rdx
  __int64 *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 *v39; // rax
  __int64 v40; // rcx
  __int64 *v41; // rax
  __int64 v42; // rcx
  __int64 *v43; // rax
  __int64 v44; // rcx
  __int64 *v45; // rax
  __int64 v46; // rcx
  struct Microsoft::Diagnostics::SystemStateManager *SystemStateManager; // rax
  struct Microsoft::Diagnostics::SystemStateManager *v48; // rax
  struct Microsoft::Diagnostics::SystemStateManager *v49; // rax
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  int v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  char v56; // [rsp+50h] [rbp-B0h] BYREF
  char v57; // [rsp+51h] [rbp-AFh] BYREF
  __int128 v58; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v59; // [rsp+70h] [rbp-90h]
  int v60; // [rsp+80h] [rbp-80h] BYREF
  __int64 v61; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v62[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v63[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v64[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v65; // [rsp+C0h] [rbp-40h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v67[3]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v68; // [rsp+E8h] [rbp-18h]
  __int64 v69; // [rsp+F8h] [rbp-8h]
  _BYTE v70[32]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v71; // [rsp+120h] [rbp+20h] BYREF
  int v72; // [rsp+130h] [rbp+30h]
  char v73; // [rsp+134h] [rbp+34h] BYREF
  _QWORD Src[4]; // [rsp+140h] [rbp+40h] BYREF
  Microsoft::Diagnostics::LifetimeManager *retaddr; // [rsp+198h] [rbp+98h]

  v4 = (const WCHAR *)((char *)a2 + 32);
  v58 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)a2 + 32, v63);
  v71 = *(_OWORD *)std::wstring::operator std::wstring_view(a2, v64);
  Microsoft::Diagnostics::Utils::Os::SetUTCInProcEnvironmentVariables(&v71, &v58);
  *((_BYTE *)this + 2287) = 1;
  v61 = 0;
  v58 = *(_OWORD *)&off_180348A48;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::OpenKey(HKEY_LOCAL_MACHINE) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)0x80070057LL,
      v50);
  if ( *((_QWORD *)v4 + 3) <= 7u )
    v5 = v4;
  else
    v5 = *(const WCHAR **)v4;
  if ( GetFileAttributesW(v5) == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x431,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)0x80070057LL,
      v50);
  v65 = 0;
  v58 = *(_OWORD *)&off_18035EE40;
  v71 = *(_OWORD *)&off_180348A48;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, &v71, &v58, &v65) >= 0 )
    _InterlockedExchange((volatile __int32 *)this, v65);
  v58 = *(_OWORD *)&off_180347638;
  Key = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( Key < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)Key,
      v51);
  v58 = *(_OWORD *)&off_180347648;
  v7 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v7,
      v52);
  v58 = *(_OWORD *)&off_1803475F8;
  v8 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v8,
      v53);
  v58 = *(_OWORD *)&off_180347628;
  v9 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v9,
      v54);
  v58 = *(_OWORD *)&off_180347608;
  v10 = Microsoft::Diagnostics::Utils::Registry::CreateGuaranteedVolatileKey(retaddr, &v58, &v61);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x43F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v10,
      v54);
  v58 = *(_OWORD *)&off_1803475B8;
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&SecurityDescriptor);
  *(_QWORD *)&v58 = 24;
  *((_QWORD *)&v58 + 1) = SecurityDescriptor;
  v59 = 0;
  v68 = v58;
  v69 = 0;
  v58 = *(_OWORD *)&off_180347618;
  v11 = Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY_LOCAL_MACHINE, 0xF003Fu, 0);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x444,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v11,
      v55);
  v67[0] = 1;
  v67[1] = &Microsoft::Diagnostics::PdcNetworkActivation::PdcActivatorCallback;
  v67[2] = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)this + 2264,
    0);
  v12 = Pdcv2ActivationClientRegister(77, v67, (char *)this + 2264);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_NtStatus(
      retaddr,
      (void *)0x44C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      (const char *)(unsigned int)v12,
      v55);
  v13 = operator new(8u);
  *v13 = 0;
  *(_QWORD *)&v71 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 272, (__int64)v13);
  std::unique_ptr<Microsoft::Diagnostics::LifetimeManager::InProcConfiguration>::~unique_ptr<Microsoft::Diagnostics::LifetimeManager::InProcConfiguration>(&v71);
  v60 = 0x10000;
  v14 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SettingsManager,Microsoft::Diagnostics::SettingsManagerConfig &,0>(
                     &v71,
                     &v60);
  v15 = *v14;
  *v14 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 235, v15);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v71);
  Microsoft::Diagnostics::LifetimeManager::SetAreInitialSettingsReady(this, 1);
  v16 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SevilleEventlogManager,,0>(&v71);
  v17 = *v16;
  *v16 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 271, v17);
  std::unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>::~unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>(&v71);
  v18 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SyntheticAggregationManager,,0>(&v71);
  v19 = *v18;
  *v18 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 278, v19);
  std::unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>::~unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>(&v71);
  LODWORD(v71) = 0;
  *(_QWORD *)((char *)&v71 + 4) = 0x300000001LL;
  HIDWORD(v71) = 5;
  v72 = 7;
  *(_QWORD *)&v58 = &v71;
  *((_QWORD *)&v58 + 1) = &v73;
  Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::EnumDetails::HeartBeatSectionFlags>(
    v62,
    &v58);
  v20 = std::make_unique<Microsoft::Diagnostics::ProxySourceMutable,std::wstring const &,0>(v63, (char *)a2 + 80);
  v21 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SystemStateManager,std::unique_ptr<Microsoft::Diagnostics::ProxySourceMutable>,0>(
                     &v71,
                     v20);
  v22 = *v21;
  *v21 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 258, v22);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v71);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v63);
  v56 = 0;
  v23 = (__int64 *)std::make_unique<Microsoft::Diagnostics::HeartbeatManager,bool,wil::basic_zstring_view<wchar_t> const &,std::bitset<9> const &,0>(
                     &v71,
                     &v56,
                     &Microsoft::Diagnostics::SevilleTenant::k_heartBeatName,
                     v62);
  v24 = *v23;
  *v23 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 254, v24);
  std::unique_ptr<Microsoft::Diagnostics::HeartbeatManager>::~unique_ptr<Microsoft::Diagnostics::HeartbeatManager>(&v71);
  v25 = (__int64 *)std::make_unique<Microsoft::Diagnostics::PrivacyKeyManager,,0>(&v71);
  v26 = *v25;
  *v25 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 246, v26);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v71);
  std::wstring::wstring((__int64)Src, &off_180347658);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src, 1, 0);
  if ( (unsigned __int8)std::operator!=<wchar_t>(Src, v4) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x46F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\lifetimemanager.cpp",
      v27);
  Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultEventStoreSize(retaddr);
  v28 = std::make_unique<Microsoft::Diagnostics::SevilleEventStoreUsageCallback,,0>(&v58);
  v56 = 2;
  v63[0] = &v56;
  v63[1] = &v57;
  v29 = std::vector<Microsoft::Diagnostics::StorageBufferType>::vector<Microsoft::Diagnostics::StorageBufferType>(
          v70,
          v63);
  LODWORD(v62[0]) = Microsoft::Diagnostics::AsimovEventBuffer::GetEventBufferMaxBytes();
  LODWORD(v64[0]) = Microsoft::Diagnostics::AsimovEventBuffer::GetCriticalEventBufferMaxEvents();
  LODWORD(v63[0]) = Microsoft::Diagnostics::AsimovEventBuffer::GetNormalEventBufferMaxEvents();
  HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager(this);
  v31 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqliteEventStore,Microsoft::Diagnostics::HeartBeat &,std::wstring &,unsigned long &,unsigned long,unsigned long,unsigned long,std::vector<Microsoft::Diagnostics::StorageBufferType> &,std::unique_ptr<Microsoft::Diagnostics::SevilleEventStoreUsageCallback>,0>(
                     &v71,
                     HeartbeatManager,
                     Src,
                     (char *)a2 + 72,
                     v63,
                     v64,
                     v62,
                     v29,
                     v28);
  v32 = *v31;
  *v31 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 244, v32);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v71);
  std::vector<unsigned char>::_Tidy(v70, v33);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v58);
  v34 = (__int64 *)std::make_unique<Microsoft::Diagnostics::LatencyData,,0>(&v58);
  v35 = *v34;
  *v34 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 255, v35);
  std::unique_ptr<Microsoft::Diagnostics::LatencyData>::~unique_ptr<Microsoft::Diagnostics::LatencyData>(&v58);
  *(_QWORD *)&v58 = L"None";
  *((_QWORD *)&v58 + 1) = 4;
  v71 = *(_OWORD *)&off_180347668;
  Microsoft::Diagnostics::BandwidthMonitor::Build<Microsoft::Diagnostics::SevilleBandwidthMonitor>(
    (unsigned int)v64,
    (unsigned int)&v71,
    (unsigned int)&v58,
    *((_DWORD *)a2 + 17),
    1);
  std::make_unique<Microsoft::Diagnostics::AsimovEndpointConfigInProc,std::wstring const &,std::wstring const &,0>(
    v63,
    (char *)a2 + 112,
    (char *)a2 + 144);
  *(_QWORD *)&v58 = operator new(0x330u);
  v36 = v64[0];
  v64[0] = 0;
  v62[0] = v36;
  v37 = v63[0];
  v63[0] = 0;
  *(_QWORD *)&v71 = v37;
  v38 = Microsoft::Diagnostics::AsimovUploadQueue::AsimovUploadQueue(v58, &v71, v62, 0);
  *(_QWORD *)&v58 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 252, v38);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v58);
  v39 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AsimovEventSerializer,,0>(&v58);
  v40 = *v39;
  *v39 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 253, v40);
  std::unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>::~unique_ptr<Microsoft::Diagnostics::AsimovEventSerializer>(&v58);
  Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::AsimovEventSerializer::DrainQueuedSyntheticEvents();
  v41 = (__int64 *)std::make_unique<Microsoft::Diagnostics::KillSwitchManager,,0>(&v58);
  v42 = *v41;
  *v41 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 270, v42);
  std::unique_ptr<Microsoft::Diagnostics::KillSwitchManager>::~unique_ptr<Microsoft::Diagnostics::KillSwitchManager>(&v58);
  v43 = (__int64 *)std::make_unique<Microsoft::Diagnostics::UtcWatchdog,,0>(&v58);
  v44 = *v43;
  *v43 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 269, v44);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v58);
  v45 = (__int64 *)std::make_unique<Microsoft::Diagnostics::AgentManager,,0>(&v58);
  v46 = *v45;
  *v45 = 0;
  _InterlockedExchange64((volatile __int64 *)this + 265, v46);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(&v58);
  Microsoft::Diagnostics::AsimovUploadQueue::StartTimers(*((Microsoft::Diagnostics::AsimovUploadQueue **)this + 252));
  SystemStateManager = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::SystemStateManager::AddTimerApiOverride(SystemStateManager, 0, *((unsigned int *)a2 + 44));
  v48 = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::SystemStateManager::AddTimerApiOverride(v48, 1, *((unsigned int *)a2 + 45));
  v49 = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  Microsoft::Diagnostics::SystemStateManager::AddTimerApiOverride(v49, 2, *((unsigned int *)a2 + 46));
  Microsoft::Diagnostics::HeartbeatManager::OnHeartbeatTimerFired(*((Microsoft::Diagnostics::HeartbeatManager **)this
                                                                  + 254));
  Microsoft::Diagnostics::UtcWatchdog::StartTimer(*((Microsoft::Diagnostics::UtcWatchdog **)this + 269));
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v63);
  std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(v64);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v61);
}

```

## disassembly

```asm
0x18006d4d4  mov     [rsp-8+arg_10], rbx
0x18006d4d9  mov     [rsp-8+arg_18], rsi
0x18006d4de  push    rbp
0x18006d4df  push    rdi
0x18006d4e0  push    r12
0x18006d4e2  push    r14
0x18006d4e4  push    r15
0x18006d4e6  lea     rbp, [rsp-70h]
0x18006d4eb  sub     rsp, 170h
0x18006d4f2  mov     rax, cs:__security_cookie
0x18006d4f9  xor     rax, rsp
0x18006d4fc  mov     [rbp+90h+var_30], rax
0x18006d500  mov     r14, rdx
0x18006d503  mov     rsi, rcx
0x18006d506  xor     r15d, r15d
0x18006d509  lea     rdi, [rdx+20h]
0x18006d50d  lea     rdx, [rbp+90h+var_F0]
0x18006d511  mov     rcx, rdi
0x18006d514  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18006d519  movups  xmm0, xmmword ptr [rax]
0x18006d51c  movdqu  [rsp+190h+var_130], xmm0
0x18006d522  lea     rdx, [rbp+90h+var_E0]
0x18006d526  mov     rcx, r14
0x18006d529  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18006d52e  movups  xmm0, xmmword ptr [rax]
0x18006d531  movdqu  [rbp+90h+var_70], xmm0
0x18006d536  lea     rdx, [rsp+190h+var_130]
0x18006d53b  lea     rcx, [rbp+90h+var_70]
0x18006d53f  call    ?SetUTCInProcEnvironmentVariables@Os@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::Os::SetUTCInProcEnvironmentVariables(std::wstring_view,std::wstring_view)
0x18006d544  mov     byte ptr [rsi+8EFh], 1
0x18006d54b  mov     [rbp+90h+var_108], r15
0x18006d54f  movups  xmm0, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x18006d556  movdqu  [rsp+190h+var_130], xmm0
0x18006d55c  mov     r12d, 0F003Fh
0x18006d562  mov     r9d, r12d
0x18006d565  lea     r8, [rbp+90h+var_108]
0x18006d569  lea     rdx, [rsp+190h+var_130]
0x18006d56e  mov     rbx, 0FFFFFFFF80000002h
0x18006d575  mov     rcx, rbx; hKey
0x18006d578  call    ?OpenKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z; Microsoft::Diagnostics::Utils::Registry::OpenKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,ulong)
0x18006d57d  test    eax, eax
0x18006d57f  jns     short loc_18006D5A0
0x18006d581  mov     rcx, [rbp+98h]; this
0x18006d588  mov     r9d, 80070057h; char *
0x18006d58e  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d595  mov     edx, 42Bh; void *
0x18006d59a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d5a0  cmp     qword ptr [rdi+18h], 7
0x18006d5a5  jbe     short loc_18006D5AC
0x18006d5a7  mov     rcx, [rdi]
0x18006d5aa  jmp     short loc_18006D5AF
0x18006d5ac  mov     rcx, rdi; lpFileName
0x18006d5af  call    cs:__imp_GetFileAttributesW
0x18006d5b6  nop     dword ptr [rax+rax+00h]
0x18006d5bb  cmp     eax, 0FFFFFFFFh
0x18006d5be  jnz     short loc_18006D5DF
0x18006d5c0  mov     rcx, [rbp+98h]; this
0x18006d5c7  mov     r9d, 80070057h; char *
0x18006d5cd  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d5d4  mov     edx, 431h; void *
0x18006d5d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d5df  mov     [rbp+90h+var_D0], r15
0x18006d5e3  movups  xmm0, xmmword ptr cs:off_18035EE40; "SubsystemShutdownTimeoutMillis"
0x18006d5ea  movdqu  [rsp+190h+var_130], xmm0
0x18006d5f0  movups  xmm1, xmmword ptr cs:off_180348A48; "%DiagtrackRegistryRoot%"
0x18006d5f7  movdqu  [rbp+90h+var_70], xmm1
0x18006d5fc  lea     r9, [rbp+90h+var_D0]
0x18006d600  lea     r8, [rsp+190h+var_130]
0x18006d605  lea     rdx, [rbp+90h+var_70]
0x18006d609  mov     rcx, rbx
0x18006d60c  call    ?GetQword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEA_K@Z; Microsoft::Diagnostics::Utils::Registry::GetQword(HKEY__ *,std::wstring_view,std::wstring_view,unsigned __int64 &)
0x18006d611  test    eax, eax
0x18006d613  js      short loc_18006D61A
0x18006d615  mov     eax, dword ptr [rbp+90h+var_D0]
0x18006d618  xchg    eax, [rsi]
0x18006d61a  movups  xmm0, xmmword ptr cs:off_180347638; "%DiagtrackRegistryRoot%\\FailFastCounte"...
0x18006d621  movdqu  [rsp+190h+var_130], xmm0
0x18006d627  mov     [rsp+190h+var_168], r15d; DWORD
0x18006d62c  mov     [rsp+190h+var_170], r12d; int
0x18006d631  xor     r9d, r9d
0x18006d634  lea     r8, [rbp+90h+var_108]
0x18006d638  lea     rdx, [rsp+190h+var_130]
0x18006d63d  mov     rcx, rbx; hKey
0x18006d640  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18006d645  mov     rcx, [rbp+98h]; this
0x18006d64c  test    eax, eax
0x18006d64e  jns     short loc_18006D665
0x18006d650  mov     r9d, eax; char *
0x18006d653  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d65a  mov     edx, 43Bh; void *
0x18006d65f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d665  movups  xmm0, xmmword ptr cs:off_180347648; "%DiagtrackRegistryRoot%\\HeartBeats"
0x18006d66c  movdqu  [rsp+190h+var_130], xmm0
0x18006d672  mov     [rsp+190h+var_168], r15d; DWORD
0x18006d677  mov     [rsp+190h+var_170], r12d; int
0x18006d67c  xor     r9d, r9d
0x18006d67f  lea     r8, [rbp+90h+var_108]
0x18006d683  lea     rdx, [rsp+190h+var_130]
0x18006d688  mov     rcx, rbx; hKey
0x18006d68b  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18006d690  mov     rcx, [rbp+98h]; this
0x18006d697  test    eax, eax
0x18006d699  jns     short loc_18006D6B0
0x18006d69b  mov     r9d, eax; char *
0x18006d69e  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d6a5  mov     edx, 43Ch; void *
0x18006d6aa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d6b0  movups  xmm0, xmmword ptr cs:off_1803475F8; "%DiagtrackRegistryRoot%\\SevilleEventlo"...
0x18006d6b7  movdqu  [rsp+190h+var_130], xmm0
0x18006d6bd  mov     [rsp+190h+var_168], r15d; DWORD
0x18006d6c2  mov     [rsp+190h+var_170], r12d; int
0x18006d6c7  xor     r9d, r9d
0x18006d6ca  lea     r8, [rbp+90h+var_108]
0x18006d6ce  lea     rdx, [rsp+190h+var_130]
0x18006d6d3  mov     rcx, rbx; hKey
0x18006d6d6  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18006d6db  mov     rcx, [rbp+98h]; this
0x18006d6e2  test    eax, eax
0x18006d6e4  jns     short loc_18006D6FB
0x18006d6e6  mov     r9d, eax; char *
0x18006d6e9  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d6f0  mov     edx, 43Dh; void *
0x18006d6f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d6fb  movups  xmm0, xmmword ptr cs:off_180347628; "%DiagtrackRegistryRoot%\\TestHooks"
0x18006d702  movdqu  [rsp+190h+var_130], xmm0
0x18006d708  mov     [rsp+190h+var_168], r15d; DWORD
0x18006d70d  mov     [rsp+190h+var_170], r12d; int
0x18006d712  xor     r9d, r9d
0x18006d715  lea     r8, [rbp+90h+var_108]
0x18006d719  lea     rdx, [rsp+190h+var_130]
0x18006d71e  mov     rcx, rbx; hKey
0x18006d721  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18006d726  mov     rcx, [rbp+98h]; this
0x18006d72d  test    eax, eax
0x18006d72f  jns     short loc_18006D746
0x18006d731  mov     r9d, eax; char *
0x18006d734  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d73b  mov     edx, 43Eh; void *
0x18006d740  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d746  movups  xmm0, xmmword ptr cs:off_180347608; "%DiagtrackRegistryRoot%\\TestHooks\\Vol"...
0x18006d74d  movdqu  [rsp+190h+var_130], xmm0
0x18006d753  lea     r8, [rbp+90h+var_108]
0x18006d757  lea     rdx, [rsp+190h+var_130]
0x18006d75c  call    ?CreateGuaranteedVolatileKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateGuaranteedVolatileKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18006d761  mov     rcx, [rbp+98h]; this
0x18006d768  test    eax, eax
0x18006d76a  jns     short loc_18006D781
0x18006d76c  mov     r9d, eax; char *
0x18006d76f  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d776  mov     edx, 43Fh; void *
0x18006d77b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006d781  movups  xmm0, xmmword ptr cs:off_1803475B8; "O:S-1-5-80-2620808479-2171380039-319135"...
0x18006d788  movdqu  [rsp+190h+var_130], xmm0
0x18006d78e  lea     rdx, [rsp+190h+var_130]
0x18006d793  lea     rcx, [rbp+90h+SecurityDescriptor]; SecurityDescriptor
0x18006d797  call    ?CreateSecurityDecriptorFromSddl@Os@Utils@Diagnostics@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(std::wstring_view)
0x18006d79c  nop
0x18006d79d  mov     qword ptr [rsp+190h+var_130], 18h
0x18006d7a6  mov     rax, [rbp+90h+SecurityDescriptor]
0x18006d7aa  mov     qword ptr [rsp+190h+var_130+8], rax
0x18006d7af  mov     [rsp+190h+var_120], r15
0x18006d7b4  movups  xmm0, [rsp+190h+var_130]
0x18006d7b9  movups  [rbp+90h+var_A8], xmm0
0x18006d7bd  movsd   xmm1, [rsp+190h+var_120]
0x18006d7c3  movsd   [rbp+90h+var_98], xmm1
0x18006d7c8  movups  xmm0, xmmword ptr cs:off_180347618; "%DiagtrackRegistryRoot%\\LocalSettings"
0x18006d7cf  movdqu  [rsp+190h+var_130], xmm0
0x18006d7d5  mov     [rsp+190h+var_168], r15d; DWORD
0x18006d7da  mov     [rsp+190h+var_170], r12d; int
0x18006d7df  lea     r9, [rbp+90h+var_A8]
0x18006d7e3  lea     r8, [rbp+90h+var_108]
0x18006d7e7  lea     rdx, [rsp+190h+var_130]
0x18006d7ec  mov     rcx, rbx; hKey
0x18006d7ef  call    ?CreateKey@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAU_SECURITY_ATTRIBUTES@@KK@Z; Microsoft::Diagnostics::Utils::Registry::CreateKey(HKEY__ *,std::wstring_view,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18006d7f4  mov     rcx, [rbp+98h]; this
0x18006d7fb  test    eax, eax
0x18006d7fd  jns     short loc_18006D813
0x18006d7ff  mov     r9d, eax; char *
0x18006d802  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d809  mov     edx, 444h; void *
0x18006d80e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006d813  mov     [rbp+90h+var_C0], 1
0x18006d81b  lea     rax, ?PdcActivatorCallback@PdcNetworkActivation@Diagnostics@Microsoft@@SAXPEAXW4_PDC_ACTIVATOR_ERROR_DETAIL@@00@Z; Microsoft::Diagnostics::PdcNetworkActivation::PdcActivatorCallback(void *,_PDC_ACTIVATOR_ERROR_DETAIL,void *,void *)
0x18006d822  mov     [rbp+90h+var_B8], rax
0x18006d826  mov     [rbp+90h+var_B0], r15
0x18006d82a  lea     rbx, [rsi+8D8h]
0x18006d831  xor     edx, edx
0x18006d833  mov     rcx, rbx
0x18006d836  call    ?reset@?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?Pdcv2ActivationClientUnregister@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&Pdcv2ActivationClientUnregister(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18006d83b  mov     r8, rbx
0x18006d83e  lea     rdx, [rbp+90h+var_C0]
0x18006d842  mov     ecx, 4Dh ; 'M'
0x18006d847  call    cs:__imp_Pdcv2ActivationClientRegister
0x18006d84e  nop     dword ptr [rax+rax+00h]
0x18006d853  mov     rcx, [rbp+98h]; this
0x18006d85a  test    eax, eax
0x18006d85c  jns     short loc_18006D872
0x18006d85e  mov     r9d, eax; char *
0x18006d861  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006d868  mov     edx, 44Ch; void *
0x18006d86d  call    ?_Log_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_NtStatus(void *,uint,char const *,long)
0x18006d872  mov     ecx, 8; Size
0x18006d877  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d87c  mov     [rax], r15
0x18006d87f  mov     qword ptr [rbp+90h+var_70], r15
0x18006d883  xchg    rax, [rsi+880h]
0x18006d88a  lea     rcx, [rbp+90h+var_70]
0x18006d88e  call    ??1?$unique_ptr@VInProcConfiguration@LifetimeManager@Diagnostics@Microsoft@@U?$default_delete@VInProcConfiguration@LifetimeManager@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::LifetimeManager::InProcConfiguration>::~unique_ptr<Microsoft::Diagnostics::LifetimeManager::InProcConfiguration>(void)
0x18006d893  mov     [rbp+90h+var_110], 10000h
0x18006d89a  lea     rdx, [rbp+90h+var_110]
0x18006d89e  lea     rcx, [rbp+90h+var_70]
0x18006d8a2  call    ??$make_unique@VSettingsManager@Diagnostics@Microsoft@@AEAUSettingsManagerConfig@23@$0A@@std@@YA?AV?$unique_ptr@VSettingsManager@Diagnostics@Microsoft@@U?$default_delete@VSettingsManager@Diagnostics@Microsoft@@@std@@@0@AEAUSettingsManagerConfig@Diagnostics@Microsoft@@@Z; std::make_unique<Microsoft::Diagnostics::SettingsManager,Microsoft::Diagnostics::SettingsManagerConfig &,0>(Microsoft::Diagnostics::SettingsManagerConfig &)
0x18006d8a7  mov     rcx, [rax]
0x18006d8aa  mov     [rax], r15
0x18006d8ad  xchg    rcx, [rsi+758h]
0x18006d8b4  lea     rcx, [rbp+90h+var_70]; void *
0x18006d8b8  call    ??1?$unique_ptr@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@U?$default_delete@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(void)
0x18006d8bd  mov     dl, 1; bool
0x18006d8bf  mov     rcx, rsi; this
0x18006d8c2  call    ?SetAreInitialSettingsReady@LifetimeManager@Diagnostics@Microsoft@@QEAAX_N@Z; Microsoft::Diagnostics::LifetimeManager::SetAreInitialSettingsReady(bool)
0x18006d8c7  lea     rcx, [rbp+90h+var_70]
0x18006d8cb  call    ??$make_unique@VSevilleEventlogManager@Diagnostics@Microsoft@@$$V$0A@@std@@YA?AV?$unique_ptr@VSevilleEventlogManager@Diagnostics@Microsoft@@U?$default_delete@VSevilleEventlogManager@Diagnostics@Microsoft@@@std@@@0@XZ; std::make_unique<Microsoft::Diagnostics::SevilleEventlogManager,,0>(void)
0x18006d8d0  mov     rcx, [rax]
0x18006d8d3  mov     [rax], r15
0x18006d8d6  xchg    rcx, [rsi+878h]
0x18006d8dd  lea     rcx, [rbp+90h+var_70]
0x18006d8e1  call    ??1?$unique_ptr@VSevilleEventlogManager@Diagnostics@Microsoft@@U?$default_delete@VSevilleEventlogManager@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>::~unique_ptr<Microsoft::Diagnostics::SevilleEventlogManager>(void)
0x18006d8e6  lea     rcx, [rbp+90h+var_70]
0x18006d8ea  call    ??$make_unique@VSyntheticAggregationManager@Diagnostics@Microsoft@@$$V$0A@@std@@YA?AV?$unique_ptr@VSyntheticAggregationManager@Diagnostics@Microsoft@@U?$default_delete@VSyntheticAggregationManager@Diagnostics@Microsoft@@@std@@@0@XZ; std::make_unique<Microsoft::Diagnostics::SyntheticAggregationManager,,0>(void)
0x18006d8ef  mov     rcx, [rax]
0x18006d8f2  mov     [rax], r15
0x18006d8f5  xchg    rcx, [rsi+8B0h]
0x18006d8fc  lea     rcx, [rbp+90h+var_70]
0x18006d900  call    ??1?$unique_ptr@VSyntheticAggregationManager@Diagnostics@Microsoft@@U?$default_delete@VSyntheticAggregationManager@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>::~unique_ptr<Microsoft::Diagnostics::SyntheticAggregationManager>(void)
0x18006d905  mov     dword ptr [rbp+90h+var_70], r15d
0x18006d909  mov     dword ptr [rbp+90h+var_70+4], 1
0x18006d910  mov     dword ptr [rbp+90h+var_70+8], 3
0x18006d917  mov     dword ptr [rbp+90h+var_70+0Ch], 5
0x18006d91e  mov     [rbp+90h+var_60], 7
0x18006d925  lea     rax, [rbp+90h+var_70]
0x18006d929  mov     qword ptr [rsp+190h+var_130], rax
0x18006d92e  lea     rax, [rbp+90h+var_5C]
0x18006d932  mov     qword ptr [rsp+190h+var_130+8], rax
0x18006d937  lea     rdx, [rsp+190h+var_130]
0x18006d93c  lea     rcx, [rbp+90h+var_100]
0x18006d940  call    ??$MakeEnumSet@VHeartBeatSectionFlags@EnumDetails@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$08@std@@V?$initializer_list@VHeartBeatSectionFlags@EnumDetails@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::EnumDetails::HeartBeatSectionFlags>(std::initializer_list<Microsoft::Diagnostics::EnumDetails::HeartBeatSectionFlags>)
0x18006d945  lea     rdx, [r14+50h]
0x18006d949  lea     rcx, [rbp+90h+var_F0]
0x18006d94d  call    ??$make_unique@VProxySourceMutable@Diagnostics@Microsoft@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0A@@std@@YA?AV?$unique_ptr@VProxySourceMutable@Diagnostics@Microsoft@@U?$default_delete@VProxySourceMutable@Diagnostics@Microsoft@@@std@@@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@@Z; std::make_unique<Microsoft::Diagnostics::ProxySourceMutable,std::wstring const &,0>(std::wstring const &)
0x18006d952  nop
0x18006d953  mov     rdx, rax
0x18006d956  lea     rcx, [rbp+90h+var_70]
0x18006d95a  call    ??$make_unique@VSystemStateManager@Diagnostics@Microsoft@@V?$unique_ptr@VProxySourceMutable@Diagnostics@Microsoft@@U?$default_delete@VProxySourceMutable@Diagnostics@Microsoft@@@std@@@std@@$0A@@std@@YA?AV?$unique_ptr@VSystemStateManager@Diagnostics@Microsoft@@U?$default_delete@VSystemStateManager@Diagnostics@Microsoft@@@std@@@0@$$QEAV?$unique_ptr@VProxySourceMutable@Diagnostics@Microsoft@@U?$default_delete@VProxySourceMutable@Diagnostics@Microsoft@@@std@@@0@@Z; std::make_unique<Microsoft::Diagnostics::SystemStateManager,std::unique_ptr<Microsoft::Diagnostics::ProxySourceMutable>,0>(std::unique_ptr<Microsoft::Diagnostics::ProxySourceMutable> &&)
0x18006d95f  mov     rcx, [rax]
0x18006d962  mov     [rax], r15
0x18006d965  xchg    rcx, [rsi+810h]
0x18006d96c  lea     rcx, [rbp+90h+var_70]; void *
0x18006d970  call    ??1?$unique_ptr@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@U?$default_delete@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(void)
0x18006d975  nop
0x18006d976  lea     rcx, [rbp+90h+var_F0]; void *
0x18006d97a  call    ??1?$unique_ptr@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@U?$default_delete@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(void)
0x18006d97f  mov     [rsp+190h+var_140], r15b
0x18006d984  lea     r9, [rbp+90h+var_100]
0x18006d988  lea     r8, ?k_heartBeatName@SevilleTenant@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::SevilleTenant::k_heartBeatName
0x18006d98f  lea     rdx, [rsp+190h+var_140]
0x18006d994  lea     rcx, [rbp+90h+var_70]
0x18006d998  call    ??$make_unique@VHeartbeatManager@Diagnostics@Microsoft@@_NAEBV?$basic_zstring_view@_W@wil@@AEBV?$bitset@$08@std@@$0A@@std@@YA?AV?$unique_ptr@VHeartbeatManager@Diagnostics@Microsoft@@U?$default_delete@VHeartbeatManager@Diagnostics@Microsoft@@@std@@@0@$$QEA_NAEBV?$basic_zstring_view@_W@wil@@AEBV?$bitset@$08@0@@Z; std::make_unique<Microsoft::Diagnostics::HeartbeatManager,bool,wil::basic_zstring_view<wchar_t> const &,std::bitset<9> const &,0>(bool &&,wil::basic_zstring_view<wchar_t> const &,std::bitset<9> const &)
0x18006d99d  mov     rcx, [rax]
0x18006d9a0  mov     [rax], r15
0x18006d9a3  xchg    rcx, [rsi+7F0h]
0x18006d9aa  lea     rcx, [rbp+90h+var_70]
0x18006d9ae  call    ??1?$unique_ptr@VHeartbeatManager@Diagnostics@Microsoft@@U?$default_delete@VHeartbeatManager@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::HeartbeatManager>::~unique_ptr<Microsoft::Diagnostics::HeartbeatManager>(void)
0x18006d9b3  lea     rcx, [rbp+90h+var_70]
0x18006d9b7  call    ??$make_unique@VPrivacyKeyManager@Diagnostics@Microsoft@@$$V$0A@@std@@YA?AV?$unique_ptr@VPrivacyKeyManager@Diagnostics@Microsoft@@U?$default_delete@VPrivacyKeyManager@Diagnostics@Microsoft@@@std@@@0@XZ; std::make_unique<Microsoft::Diagnostics::PrivacyKeyManager,,0>(void)
0x18006d9bc  mov     rcx, [rax]
0x18006d9bf  mov     [rax], r15
0x18006d9c2  xchg    rcx, [rsi+7B0h]
0x18006d9c9  lea     rcx, [rbp+90h+var_70]; void *
0x18006d9cd  call    ??1?$unique_ptr@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@U?$default_delete@VAgentScenarioObjectStorage@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>::~unique_ptr<Microsoft::Diagnostics::AgentScenarioObjectStorage>(void)
0x18006d9d2  lea     rdx, off_180347658; "%DiagtrackStorageRoot%"
0x18006d9d9  lea     rcx, [rbp+90h+Src]
0x18006d9dd  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18006d9e2  nop
0x18006d9e3  xor     r8d, r8d
0x18006d9e6  mov     dl, 1
0x18006d9e8  lea     rcx, [rbp+90h+Src]; lpSrc
0x18006d9ec  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18006d9f1  mov     rdx, rdi
0x18006d9f4  lea     rcx, [rbp+90h+Src]
0x18006d9f8  call    ??$?9_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator!=<wchar_t>(std::wstring const &,std::wstring const &)
0x18006d9fd  mov     rcx, [rbp+98h]; this
0x18006da04  test    al, al
0x18006da06  jz      short loc_18006DA1A
0x18006da08  lea     r8, aOnecoreBaseTel_210; "onecore\\base\\telemetry\\utc\\service"...
0x18006da0f  mov     edx, 46Fh; void *
0x18006da14  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18006da1a  call    ?GetUtcDefaultEventStoreSize@LifetimeManager@Diagnostics@Microsoft@@QEAAKXZ; Microsoft::Diagnostics::LifetimeManager::GetUtcDefaultEventStoreSize(void)
0x18006da1f  lea     rcx, [rsp+190h+var_130]
0x18006da24  call    ??$make_unique@VSevilleEventStoreUsageCallback@Diagnostics@Microsoft@@$$V$0A@@std@@YA?AV?$unique_ptr@VSevilleEventStoreUsageCallback@Diagnostics@Microsoft@@U?$default_delete@VSevilleEventStoreUsageCallback@Diagnostics@Microsoft@@@std@@@0@XZ; std::make_unique<Microsoft::Diagnostics::SevilleEventStoreUsageCallback,,0>(void)
0x18006da29  mov     rdi, rax
  ... truncated ...
```
