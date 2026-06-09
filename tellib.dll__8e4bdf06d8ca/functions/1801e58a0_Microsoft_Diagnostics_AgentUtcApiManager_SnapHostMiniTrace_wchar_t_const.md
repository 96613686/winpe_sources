# Microsoft::Diagnostics::AgentUtcApiManager::SnapHostMiniTrace(wchar_t const *)

- ea: `0x1801e58a0`
- end: `0x1801e6688`
- name: `?SnapHostMiniTrace@AgentUtcApiManager@Diagnostics@Microsoft@@UEAAJPEB_W@Z`
- size: `3560`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::AgentUtcApiManager *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180030a50`
- `0x1800326cc`
- `0x180032ae8`
- `0x1800340c0`
- `0x180034d94`
- `0x18003f600`
- `0x180054198`
- `0x180054ca4`
- `0x18006e7e4`
- `0x180082b70`
- `0x180083b1c`
- `0x18008453c`
- `0x180086f40`
- `0x180089d90`
- `0x18009d3ec`
- `0x1800a9c80`
- `0x1800b0628`
- `0x1800cea6c`
- `0x180105038`
- `0x18011bdb4`
- `0x18012de40`
- `0x18012de64`
- `0x1801bfc30`
- `0x1801c039c`
- `0x1801e58a0`
- `0x1801eae48`
- `0x1801eb558`
- `0x18022ca48`
- `0x1802b4efc`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801e635e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801e635e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801e598e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801e598e`

## string_xrefs

- `0x1801e58ea`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e5921`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e595e`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e59ab`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e5a4d`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e5ad1`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e5b69`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e5c9e`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e5e9e`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e5f6a`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e604a`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e610d`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e61ff`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e637f`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`
- `0x1801e64fb`: `onecore\base\telemetry\utc\service\engine\agentutcapimanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::AgentUtcApiManager::SnapHostMiniTrace(
        Microsoft::Diagnostics::AgentUtcApiManager *this,
        const wchar_t *a2)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // r8
  int appended; // eax
  unsigned int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  unsigned int v13; // ebx
  char *v14; // rdi
  __int64 v15; // rax
  __int64 v16; // r10
  struct Microsoft::Diagnostics::Agent *Agent; // rbx
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // ebx
  struct Microsoft::Diagnostics::Agent *v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  struct Microsoft::Diagnostics::Agent *v25; // rax
  void **v26; // rax
  void *v27; // rcx
  struct Microsoft::Diagnostics::Agent *v28; // rax
  int v29; // ebx
  struct Microsoft::Diagnostics::Agent *v30; // rax
  __int64 v31; // rcx
  int RpcImpersonationToken; // eax
  unsigned int v33; // ebx
  struct Microsoft::Diagnostics::Agent *v34; // rax
  __int64 v35; // r8
  Microsoft::Diagnostics::UserManager *v36; // r8
  __int64 UserContextForSid; // rbx
  int UserToken; // eax
  unsigned int v39; // ebx
  struct Microsoft::Diagnostics::Agent *v40; // rax
  __int64 v41; // rax
  int v42; // eax
  unsigned int v43; // ebx
  struct Microsoft::Diagnostics::Agent *v44; // rax
  struct Microsoft::Diagnostics::Agent *v45; // rax
  int v46; // [rsp+20h] [rbp-188h]
  int v47; // [rsp+20h] [rbp-188h]
  int v48; // [rsp+20h] [rbp-188h]
  __int128 v49; // [rsp+40h] [rbp-168h] BYREF
  char Src; // [rsp+50h] [rbp-158h] BYREF
  char v51; // [rsp+51h] [rbp-157h] BYREF
  int v52[3]; // [rsp+52h] [rbp-156h] BYREF
  __int64 v53[2]; // [rsp+60h] [rbp-148h] BYREF
  _QWORD v54[2]; // [rsp+70h] [rbp-138h] BYREF
  int v55[4]; // [rsp+80h] [rbp-128h] BYREF
  int v56[4]; // [rsp+90h] [rbp-118h] BYREF
  void *lpMem; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-100h]
  char v59; // [rsp+B0h] [rbp-F8h]
  __int128 v60; // [rsp+C0h] [rbp-E8h]
  __int128 v61; // [rsp+D0h] [rbp-D8h] BYREF
  GUID pguid; // [rsp+E0h] [rbp-C8h] BYREF
  WCHAR pszPath[16]; // [rsp+F0h] [rbp-B8h] BYREF
  _BYTE v64[32]; // [rsp+110h] [rbp-98h] BYREF
  WCHAR v65[16]; // [rsp+130h] [rbp-78h] BYREF
  _BYTE v66[32]; // [rsp+150h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  if ( a2 )
  {
    if ( _InterlockedCompareExchange64((_QWORD *)&xmmword_18043BFF0 + 1, 0, 0) )
    {
      if ( *((_BYTE *)Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager)
           + 192) )
      {
        pguid = GUID_NULL;
        v5 = CoCreateGuid(&pguid);
        v6 = v5;
        if ( v5 >= 0 )
        {
          Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(pszPath);
          v7 = Microsoft::Diagnostics::Utils::String::StringFromGuidW(v66, &pguid, 0);
          std::operator+<wchar_t>(v64, L"hostminitrace_", v7);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v66);
          *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v64, &v49);
          appended = Microsoft::Diagnostics::Utils::String::AppendPath(pszPath);
          v9 = appended;
          if ( appended >= 0 )
          {
            *(_OWORD *)v53 = *(_OWORD *)&off_180360360;
            v61 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, &v49);
            v10 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(&v61, 0, v53);
            v11 = v10;
            if ( v10 >= 0 )
            {
              *(_QWORD *)&v60 = pszPath;
              BYTE8(v60) = 1;
              std::wstring::wstring(v65, pszPath);
              *(_OWORD *)v53 = *(_OWORD *)&off_180347DD0;
              v12 = Microsoft::Diagnostics::Utils::String::AppendPath(v65);
              v13 = v12;
              if ( v12 >= 0 )
              {
                v14 = (char *)operator new(0x58u);
                *(_QWORD *)v55 = v14;
                *((_DWORD *)v14 + 2) = 1;
                *((_DWORD *)v14 + 3) = 1;
                *(_QWORD *)v14 = &std::_Ref_count_obj2<Microsoft::Diagnostics::EscalationDataRequest>::`vftable';
                *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, &v49);
                Microsoft::Diagnostics::EscalationDataRequest::EscalationDataRequest(v14 + 16, v53);
                *(_QWORD *)&v61 = v14 + 16;
                *((_QWORD *)&v61 + 1) = v14;
                Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
                  v53,
                  &v61);
                *(_OWORD *)v55 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                if ( (unsigned __int8)Microsoft::Diagnostics::IAgentIoReceiver::RegisterEscalationDataRequest(
                                        v16,
                                        &pguid,
                                        v55,
                                        v15) )
                {
                  *(_QWORD *)&v49 = &pguid;
                  BYTE8(v49) = 1;
                  lpMem = 0;
                  v58 = 0;
                  v59 = 1;
                  Src = 2;
                  v53[0] = (__int64)L"tslty";
                  v53[1] = 5;
                  *(_QWORD *)v55 = &lpMem;
                  v55[2] = 0;
                  v55[3] = HIDWORD(v49);
                  JsonBuilder::AddValue((int)&lpMem, (int)v56, 0, (int)v55, (__int64)v53, 246, 1, &Src);
                  v53[0] = (__int64)L"trid";
                  v53[1] = 4;
                  *(_QWORD *)v55 = &lpMem;
                  v55[2] = 0;
                  v55[3] = v56[3];
                  JsonBuilder::AddValue((int)&lpMem, (int)v56, 0, (int)v55, (__int64)v53, 251, 16, &pguid);
                  Agent = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                  gsl::span<enum gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(
                    v53,
                    lpMem,
                    4LL * (unsigned int)v58);
                  LOBYTE(v18) = 13;
                  v19 = Microsoft::Diagnostics::Agent::SendAgentMessage(Agent, v18, v53);
                  v21 = v19;
                  if ( v19 >= 0 )
                  {
                    LOBYTE(v20) = 13;
                    v23 = Microsoft::Diagnostics::AgentUtcApiManager::WaitForHostEvent(this, v20);
                    v24 = v23;
                    if ( v23 >= 0 )
                    {
                      v26 = (void **)*((_QWORD *)v14 + 6);
                      if ( v26 )
                        v27 = *v26;
                      else
                        v27 = 0;
                      if ( Microsoft::Diagnostics::Utils::Os::WaitOrTimeout(v27, 0xEA60u) )
                      {
                        v29 = *((_DWORD *)v14 + 16);
                        if ( v29 >= 0 )
                        {
                          v54[0] = 0;
                          std::wstring::wstring(v66);
                          *(_QWORD *)v55 = 0;
                          RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(
                                                    v31,
                                                    v55,
                                                    v66);
                          v33 = RpcImpersonationToken;
                          if ( RpcImpersonationToken >= 0 )
                          {
                            Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                            *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v66, v56);
                            if ( (unsigned __int8)Microsoft::Diagnostics::UserManager::IsSidALoggedInUser(v35, v53)
                              && (Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager),
                                  *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v66, v56),
                                  UserContextForSid = Microsoft::Diagnostics::UserManager::GetUserContextForSid(v36),
                                  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
                                    v54,
                                    0),
                                  UserToken = UMgrQueryUserToken(UserContextForSid, v54),
                                  v39 = UserToken,
                                  UserToken < 0) )
                            {
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)0x55,
                                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                                (const char *)(unsigned int)UserToken,
                                v47);
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v55);
                              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v66);
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v54);
                              JsonInternal::PodVectorBase::Deallocate(lpMem);
                              v40 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                              v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                              Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                v40,
                                &pguid,
                                &v49);
                              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                              v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                              Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                              return v39;
                            }
                            else
                            {
                              wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v55);
                              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v66);
                              LOWORD(v52[0]) = 0;
                              v51 = 0;
                              v41 = -1;
                              do
                                ++v41;
                              while ( a2[v41] );
                              v53[0] = (__int64)a2;
                              v53[1] = v41;
                              *(_OWORD *)v55 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                              v42 = Microsoft::Diagnostics::EscalationWorkItem::CopyDiagnosticDirectory(
                                      (unsigned int)v55,
                                      (unsigned int)v53,
                                      (unsigned int)v54,
                                      (unsigned int)v52 + 1,
                                      (__int64)v52,
                                      (__int64)&v51);
                              v43 = v42;
                              if ( v42 >= 0 )
                              {
                                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v54);
                                JsonInternal::PodVectorBase::Deallocate(lpMem);
                                v45 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                                v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                                Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                  v45,
                                  &pguid,
                                  &v49);
                                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                                v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                                return 0;
                              }
                              else
                              {
                                wil::details::in1diag3::Return_Hr(
                                  retaddr,
                                  (void *)0x61,
                                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                                  (const char *)(unsigned int)v42,
                                  v48);
                                wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v54);
                                JsonInternal::PodVectorBase::Deallocate(lpMem);
                                v44 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                                v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                                Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(
                                  v44,
                                  &pguid,
                                  &v49);
                                std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                                v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                                return v43;
                              }
                            }
                          }
                          else
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x50,
                              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                              (const char *)(unsigned int)RpcImpersonationToken,
                              v47);
                            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v55);
                            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v66);
                            wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v54);
                            JsonInternal::PodVectorBase::Deallocate(lpMem);
                            v34 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                            v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                            Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v34, &pguid, &v49);
                            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                            v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                            Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                            return v33;
                          }
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x49,
                            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                            (const char *)(unsigned int)v29,
                            v47);
                          JsonInternal::PodVectorBase::Deallocate(lpMem);
                          v30 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                          v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                          Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v30, &pguid, &v49);
                          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                          v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                          Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                          return (unsigned int)v29;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x47,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                          (const char *)0x800705B4LL,
                          v47);
                        JsonInternal::PodVectorBase::Deallocate(lpMem);
                        v28 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                        v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                        Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v28, &pguid, &v49);
                        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                        v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                        Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                        return 2147943860LL;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x43,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                        (const char *)(unsigned int)v23,
                        v47);
                      JsonInternal::PodVectorBase::Deallocate(lpMem);
                      v25 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                      v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                      Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v25, &pguid, &v49);
                      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                      v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                      Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                      return v24;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x40,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                      (const char *)(unsigned int)v19,
                      v47);
                    JsonInternal::PodVectorBase::Deallocate(lpMem);
                    v22 = Microsoft::Diagnostics::LifetimeManager::GetAgent((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
                    v49 = *(_OWORD *)&Microsoft::Diagnostics::Agent::k_hostAgentTransportId;
                    Microsoft::Diagnostics::IAgentIoReceiver::UnregisterEscalationDataRequest(v22, &pguid, &v49);
                    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                    v49 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v56);
                    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                    return v21;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2E,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                    (const char *)0x800700B7LL,
                    v46);
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v14);
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                  v60 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, &v49);
                  Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                  return 2147942583LL;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x29,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                  (const char *)(unsigned int)v12,
                  v46);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
                v60 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, &v49);
                Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
                return v13;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x20,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
                (const char *)(unsigned int)v10,
                v46);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
              return v11;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
              (const char *)(unsigned int)appended,
              v46);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v64);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
            return v9;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
            (const char *)(unsigned int)v5,
            v46);
          return v6;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
          (const char *)0x80070032LL,
          v46);
        return 2147942450LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
        (const char *)0x80070015LL,
        v46);
      return 2147942421LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentutcapimanager.cpp",
      (const char *)0x80070057LL,
      v46);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1801e58a0  mov     [rsp+arg_8], rbx
0x1801e58a5  mov     [rsp+arg_10], rsi
0x1801e58aa  push    rdi
0x1801e58ab  push    r12
0x1801e58ad  push    r13
0x1801e58af  push    r14
0x1801e58b1  push    r15
0x1801e58b3  sub     rsp, 180h
0x1801e58ba  mov     rax, cs:__security_cookie
0x1801e58c1  xor     rax, rsp
0x1801e58c4  mov     [rsp+1A8h+var_38], rax
0x1801e58cc  mov     r14, rdx
0x1801e58cf  mov     r15, rcx
0x1801e58d2  xor     r12d, r12d
0x1801e58d5  test    rdx, rdx
0x1801e58d8  jnz     short loc_1801E5901
0x1801e58da  mov     rcx, [rsp+1A8h]; this
0x1801e58e2  mov     ebx, 80070057h
0x1801e58e7  mov     r9d, ebx; char *
0x1801e58ea  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e58f1  lea     edx, [r14+12h]; void *
0x1801e58f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e58fa  mov     eax, ebx
0x1801e58fc  jmp     loc_1801E665A
0x1801e5901  mov     rcx, r12
0x1801e5904  xor     eax, eax
0x1801e5906  lock cmpxchg qword ptr cs:xmmword_18043BFF0+8, rcx
0x1801e590f  jnz     short loc_1801E5939
0x1801e5911  mov     rcx, [rsp+1A8h]; this
0x1801e5919  mov     ebx, 80070015h
0x1801e591e  mov     r9d, ebx; char *
0x1801e5921  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e5928  mov     edx, 13h; void *
0x1801e592d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e5932  mov     eax, ebx
0x1801e5934  jmp     loc_1801E665A
0x1801e5939  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801e5940  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x1801e5945  cmp     [rax+0C0h], r12b
0x1801e594c  jnz     short loc_1801E5976
0x1801e594e  mov     rcx, [rsp+1A8h]; this
0x1801e5956  mov     ebx, 80070032h
0x1801e595b  mov     r9d, ebx; char *
0x1801e595e  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e5965  mov     edx, 16h; void *
0x1801e596a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e596f  mov     eax, ebx
0x1801e5971  jmp     loc_1801E665A
0x1801e5976  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801e597d  movdqu  xmmword ptr [rsp+1A8h+pguid.Data1], xmm0
0x1801e5986  lea     rcx, [rsp+1A8h+pguid]; pguid
0x1801e598e  call    cs:__imp_CoCreateGuid
0x1801e5995  nop     dword ptr [rax+rax+00h]
0x1801e599a  mov     ebx, eax
0x1801e599c  test    eax, eax
0x1801e599e  jns     short loc_1801E59C3
0x1801e59a0  mov     rcx, [rsp+1A8h]; this
0x1801e59a8  mov     r9d, eax; char *
0x1801e59ab  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e59b2  mov     edx, 1Ah; void *
0x1801e59b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e59bc  mov     eax, ebx
0x1801e59be  jmp     loc_1801E665A
0x1801e59c3  lea     rcx, [rsp+1A8h+pszPath]; lpSrc
0x1801e59cb  call    ?GetUtcTemporaryPath@FileSystem@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(void)
0x1801e59d0  nop
0x1801e59d1  xor     r8d, r8d
0x1801e59d4  lea     rdx, [rsp+1A8h+pguid]
0x1801e59dc  lea     rcx, [rsp+1A8h+var_58]
0x1801e59e4  call    ?StringFromGuidW@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@_N@Z; Microsoft::Diagnostics::Utils::String::StringFromGuidW(_GUID const &,bool)
0x1801e59e9  nop
0x1801e59ea  mov     r8, rax
0x1801e59ed  lea     rdx, aHostminitrace; "hostminitrace_"
0x1801e59f4  lea     rcx, [rsp+1A8h+var_98]
0x1801e59fc  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x1801e5a01  nop
0x1801e5a02  lea     rcx, [rsp+1A8h+var_58]; this
0x1801e5a0a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5a0f  lea     rdx, [rsp+1A8h+var_168]
0x1801e5a14  lea     rcx, [rsp+1A8h+var_98]
0x1801e5a1c  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e5a21  movups  xmm0, xmmword ptr [rax]
0x1801e5a24  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x1801e5a2a  lea     rdx, [rsp+1A8h+var_148]
0x1801e5a2f  lea     rcx, [rsp+1A8h+pszPath]; pszPath
0x1801e5a37  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1801e5a3c  mov     ebx, eax
0x1801e5a3e  test    eax, eax
0x1801e5a40  jns     short loc_1801E5A81
0x1801e5a42  mov     rcx, [rsp+1A8h]; this
0x1801e5a4a  mov     r9d, eax; char *
0x1801e5a4d  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e5a54  mov     edx, 1Fh; void *
0x1801e5a59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e5a5e  nop
0x1801e5a5f  lea     rcx, [rsp+1A8h+var_98]; this
0x1801e5a67  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5a6c  nop
0x1801e5a6d  lea     rcx, [rsp+1A8h+pszPath]; this
0x1801e5a75  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5a7a  mov     eax, ebx
0x1801e5a7c  jmp     loc_1801E665A
0x1801e5a81  movups  xmm0, xmmword ptr cs:off_180360360; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x1801e5a88  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x1801e5a8e  lea     rdx, [rsp+1A8h+var_168]
0x1801e5a93  lea     rcx, [rsp+1A8h+pszPath]
0x1801e5a9b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e5aa0  movups  xmm0, xmmword ptr [rax]
0x1801e5aa3  movdqu  [rsp+1A8h+var_D8], xmm0
0x1801e5aac  lea     r8, [rsp+1A8h+var_148]
0x1801e5ab1  xor     edx, edx
0x1801e5ab3  lea     rcx, [rsp+1A8h+var_D8]
0x1801e5abb  call    ?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z; Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::wstring_view,bool,std::wstring_view)
0x1801e5ac0  mov     ebx, eax
0x1801e5ac2  test    eax, eax
0x1801e5ac4  jns     short loc_1801E5B05
0x1801e5ac6  mov     rcx, [rsp+1A8h]; this
0x1801e5ace  mov     r9d, eax; char *
0x1801e5ad1  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e5ad8  mov     edx, 20h ; ' '; void *
0x1801e5add  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e5ae2  nop
0x1801e5ae3  lea     rcx, [rsp+1A8h+var_98]; this
0x1801e5aeb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5af0  nop
0x1801e5af1  lea     rcx, [rsp+1A8h+pszPath]; this
0x1801e5af9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5afe  mov     eax, ebx
0x1801e5b00  jmp     loc_1801E665A
0x1801e5b05  lea     rax, [rsp+1A8h+pszPath]
0x1801e5b0d  mov     qword ptr [rsp+1A8h+var_E8], rax
0x1801e5b15  mov     r13d, 1
0x1801e5b1b  mov     byte ptr [rsp+1A8h+var_E8+8], r13b
0x1801e5b23  lea     rdx, [rsp+1A8h+pszPath]
0x1801e5b2b  lea     rcx, [rsp+1A8h+var_78]
0x1801e5b33  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801e5b38  nop
0x1801e5b39  movaps  xmm0, xmmword ptr cs:off_180347DD0; "minitrace.etl"
0x1801e5b40  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x1801e5b46  lea     rdx, [rsp+1A8h+var_148]
0x1801e5b4b  lea     rcx, [rsp+1A8h+var_78]; pszPath
0x1801e5b53  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1801e5b58  mov     ebx, eax
0x1801e5b5a  test    eax, eax
0x1801e5b5c  jns     short loc_1801E5BD6
0x1801e5b5e  mov     rcx, [rsp+1A8h]; this
0x1801e5b66  mov     r9d, eax; char *
0x1801e5b69  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e5b70  lea     edx, [r13+28h]; void *
0x1801e5b74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e5b79  nop
0x1801e5b7a  lea     rcx, [rsp+1A8h+var_78]; this
0x1801e5b82  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5b87  nop
0x1801e5b88  lea     rdx, [rsp+1A8h+var_168]
0x1801e5b8d  lea     rcx, [rsp+1A8h+pszPath]
0x1801e5b95  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e5b9a  movups  xmm0, xmmword ptr [rax]
0x1801e5b9d  movdqu  [rsp+1A8h+var_E8], xmm0
0x1801e5ba6  lea     rcx, [rsp+1A8h+var_E8]
0x1801e5bae  call    ?RecursivelyDeleteDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(std::wstring_view)
0x1801e5bb3  nop
0x1801e5bb4  lea     rcx, [rsp+1A8h+var_98]; this
0x1801e5bbc  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5bc1  nop
0x1801e5bc2  lea     rcx, [rsp+1A8h+pszPath]; this
0x1801e5bca  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5bcf  mov     eax, ebx
0x1801e5bd1  jmp     loc_1801E665A
0x1801e5bd6  mov     ecx, 58h ; 'X'; Size
0x1801e5bdb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801e5be0  mov     rdi, rax
0x1801e5be3  mov     qword ptr [rsp+1A8h+var_128], rax
0x1801e5beb  mov     [rax+8], r13d
0x1801e5bef  mov     [rax+0Ch], r13d
0x1801e5bf3  lea     rax, ??_7?$_Ref_count_obj2@UEscalationDataRequest@Diagnostics@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Diagnostics::EscalationDataRequest>::`vftable'
0x1801e5bfa  mov     [rdi], rax
0x1801e5bfd  lea     rsi, [rdi+10h]
0x1801e5c01  lea     rdx, [rsp+1A8h+var_168]
0x1801e5c06  lea     rcx, [rsp+1A8h+var_78]
0x1801e5c0e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e5c13  movups  xmm0, xmmword ptr [rax]
0x1801e5c16  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x1801e5c1c  lea     rdx, [rsp+1A8h+var_148]
0x1801e5c21  mov     rcx, rsi
0x1801e5c24  call    ??0EscalationDataRequest@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::EscalationDataRequest::EscalationDataRequest(std::wstring_view)
0x1801e5c29  nop
0x1801e5c2a  mov     qword ptr [rsp+1A8h+var_D8], rsi
0x1801e5c32  mov     qword ptr [rsp+1A8h+var_D8+8], rdi
0x1801e5c3a  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801e5c41  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x1801e5c46  mov     r10, rax
0x1801e5c49  lea     rdx, [rsp+1A8h+var_D8]; void *
0x1801e5c51  lea     rcx, [rsp+1A8h+var_148]; void *
0x1801e5c56  call    ??0?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const> const &)
0x1801e5c5b  movups  xmm0, xmmword ptr cs:?k_hostAgentTransportId@Agent@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::Agent::k_hostAgentTransportId
0x1801e5c62  movdqu  xmmword ptr [rsp+1A8h+var_128], xmm0
0x1801e5c6b  mov     r9, rax
0x1801e5c6e  lea     r8, [rsp+1A8h+var_128]
0x1801e5c76  lea     rdx, [rsp+1A8h+pguid]
0x1801e5c7e  mov     rcx, r10
0x1801e5c81  call    ?RegisterEscalationDataRequest@IAgentIoReceiver@Diagnostics@Microsoft@@QEAA_NAEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$shared_ptr@UEscalationDataRequest@Diagnostics@Microsoft@@@6@@Z; Microsoft::Diagnostics::IAgentIoReceiver::RegisterEscalationDataRequest(_GUID const &,std::wstring_view,std::shared_ptr<Microsoft::Diagnostics::EscalationDataRequest>)
0x1801e5c86  test    al, al
0x1801e5c88  jnz     loc_1801E5D15
0x1801e5c8e  mov     rcx, [rsp+1A8h]; this
0x1801e5c96  mov     ebx, 800700B7h
0x1801e5c9b  mov     r9d, ebx; char *
0x1801e5c9e  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e5ca5  mov     edx, 2Eh ; '.'; void *
0x1801e5caa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e5caf  nop
0x1801e5cb0  mov     rcx, rdi; this
0x1801e5cb3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801e5cb8  nop
0x1801e5cb9  lea     rcx, [rsp+1A8h+var_78]; this
0x1801e5cc1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5cc6  nop
0x1801e5cc7  lea     rdx, [rsp+1A8h+var_168]
0x1801e5ccc  lea     rcx, [rsp+1A8h+pszPath]
0x1801e5cd4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e5cd9  movups  xmm0, xmmword ptr [rax]
0x1801e5cdc  movdqu  [rsp+1A8h+var_E8], xmm0
0x1801e5ce5  lea     rcx, [rsp+1A8h+var_E8]
0x1801e5ced  call    ?RecursivelyDeleteDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory(std::wstring_view)
0x1801e5cf2  nop
0x1801e5cf3  lea     rcx, [rsp+1A8h+var_98]; this
0x1801e5cfb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5d00  nop
0x1801e5d01  lea     rcx, [rsp+1A8h+pszPath]; this
0x1801e5d09  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e5d0e  mov     eax, ebx
0x1801e5d10  jmp     loc_1801E665A
0x1801e5d15  lea     rax, [rsp+1A8h+pguid]
0x1801e5d1d  mov     qword ptr [rsp+1A8h+var_168], rax
0x1801e5d22  mov     byte ptr [rsp+1A8h+var_168+8], r13b
0x1801e5d27  mov     [rsp+1A8h+lpMem], r12
0x1801e5d2f  mov     [rsp+1A8h+var_100], r12
0x1801e5d37  mov     [rsp+1A8h+var_F8], r13b
0x1801e5d3f  mov     [rsp+1A8h+var_158], 2
0x1801e5d44  mov     rax, cs:off_180360320; "tslty"
0x1801e5d4b  mov     [rsp+1A8h+var_148], rax
0x1801e5d50  mov     [rsp+1A8h+var_148+8], 5
0x1801e5d59  lea     rax, [rsp+1A8h+lpMem]
0x1801e5d61  mov     qword ptr [rsp+1A8h+var_128], rax
0x1801e5d69  mov     [rsp+1A8h+var_128+8], r12d
0x1801e5d71  mov     eax, dword ptr [rsp+1A8h+var_168+0Ch]
0x1801e5d75  mov     [rsp+1A8h+var_128+0Ch], eax
0x1801e5d7c  lea     rax, [rsp+1A8h+var_158]
0x1801e5d81  mov     [rsp+1A8h+Src], rax; Src
0x1801e5d86  mov     [rsp+1A8h+var_178], r13d; int
0x1801e5d8b  mov     [rsp+1A8h+var_180], 0F6h; int
0x1801e5d93  lea     rax, [rsp+1A8h+var_148]
0x1801e5d98  mov     [rsp+1A8h+var_188], rax; __int64
0x1801e5d9d  lea     r9, [rsp+1A8h+var_128]; int
0x1801e5da5  xor     r8d, r8d; int
0x1801e5da8  lea     rdx, [rsp+1A8h+var_118]; int
0x1801e5db0  lea     rcx, [rsp+1A8h+lpMem]; int
0x1801e5db8  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1801e5dbd  mov     rax, cs:off_180360330; "trid"
0x1801e5dc4  mov     [rsp+1A8h+var_148], rax
0x1801e5dc9  mov     [rsp+1A8h+var_148+8], 4
0x1801e5dd2  lea     rax, [rsp+1A8h+lpMem]
0x1801e5dda  mov     qword ptr [rsp+1A8h+var_128], rax
0x1801e5de2  mov     [rsp+1A8h+var_128+8], r12d
0x1801e5dea  mov     eax, [rsp+1A8h+var_10C]
0x1801e5df1  mov     [rsp+1A8h+var_128+0Ch], eax
0x1801e5df8  lea     rax, [rsp+1A8h+pguid]
0x1801e5e00  mov     [rsp+1A8h+Src], rax; Src
0x1801e5e05  mov     [rsp+1A8h+var_178], 10h; int
0x1801e5e0d  mov     [rsp+1A8h+var_180], 0FBh; int
0x1801e5e15  lea     rax, [rsp+1A8h+var_148]
0x1801e5e1a  mov     [rsp+1A8h+var_188], rax; int
0x1801e5e1f  lea     r9, [rsp+1A8h+var_128]; int
0x1801e5e27  xor     r8d, r8d; int
0x1801e5e2a  lea     rdx, [rsp+1A8h+var_118]; int
0x1801e5e32  lea     rcx, [rsp+1A8h+lpMem]; int
0x1801e5e3a  call    ?AddValue@JsonBuilder@@QEAA?AVJsonIterator@@_NAEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@W4JsonType@@IPEBX@Z; JsonBuilder::AddValue(bool,JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &,JsonType,uint,void const *)
0x1801e5e3f  lea     r13, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; Microsoft::Diagnostics::LifetimeManager gs_lifetimeManager
0x1801e5e46  mov     rcx, r13; this
0x1801e5e49  call    ?GetAgent@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAgent@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAgent(void)
0x1801e5e4e  mov     rbx, rax
0x1801e5e51  mov     r8d, dword ptr [rsp+1A8h+var_100]
0x1801e5e59  shl     r8, 2
0x1801e5e5d  mov     rdx, [rsp+1A8h+lpMem]
0x1801e5e65  lea     rcx, [rsp+1A8h+var_148]
0x1801e5e6a  call    ??$?0_K@?$storage_type@V?$extent_type@$0?0@details@gsl@@@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEAA@PEBW4byte@2@_K@Z; gsl::span<gsl::byte const,-1>::storage_type<gsl::details::extent_type<-1>>::storage_type<gsl::details::extent_type<-1>>(gsl::byte const *,unsigned __int64)
0x1801e5e6f  movups  xmm0, xmmword ptr [rsp+1A8h+var_148]
0x1801e5e74  movdqu  xmmword ptr [rsp+1A8h+var_148], xmm0
0x1801e5e7a  lea     r8, [rsp+1A8h+var_148]
0x1801e5e7f  mov     dl, 0Dh
0x1801e5e81  mov     rcx, rbx
0x1801e5e84  call    ?SendAgentMessage@Agent@Diagnostics@Microsoft@@QEAAJVAgentMessageType@23@V?$span@$$CBW4byte@gsl@@$0?0@gsl@@@Z; Microsoft::Diagnostics::Agent::SendAgentMessage(Microsoft::Diagnostics::AgentMessageType,gsl::span<gsl::byte const,-1>)
0x1801e5e89  mov     ebx, eax
0x1801e5e8b  test    eax, eax
0x1801e5e8d  jns     loc_1801E5F4B
0x1801e5e93  mov     rcx, [rsp+1A8h]; this
0x1801e5e9b  mov     r9d, eax; char *
0x1801e5e9e  lea     r8, aOnecoreBaseTel_189; "onecore\\base\\telemetry\\utc\\service"...
0x1801e5ea5  mov     edx, 40h ; '@'; void *
0x1801e5eaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
