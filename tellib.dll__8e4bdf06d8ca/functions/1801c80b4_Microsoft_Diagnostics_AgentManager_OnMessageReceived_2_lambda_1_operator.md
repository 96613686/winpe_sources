# _Microsoft::Diagnostics::AgentManager::OnMessageReceived_::_2_::_lambda_1_::operator()

- ea: `0x1801c80b4`
- end: `0x1801c9082`
- name: `_Microsoft::Diagnostics::AgentManager::OnMessageReceived_::_2_::_lambda_1_::operator()`
- size: `4046`
- prototype: ``
- caller_count: `1`
- callee_count: `60`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801cac20`

## callees

- `0x180001d28`
- `0x1800023fc`
- `0x180002b94`
- `0x180006d64`
- `0x180006e00`
- `0x18001cf30`
- `0x180020fbc`
- `0x180026ecc`
- `0x180031d0c`
- `0x1800326cc`
- `0x180032ae8`
- `0x1800333b0`
- `0x18003fd8c`
- `0x180053218`
- `0x18005b974`
- `0x18005d050`
- `0x18006d190`
- `0x180071110`
- `0x1800717ec`
- `0x18007fae8`
- `0x180080054`
- `0x1800862cc`
- `0x1800a60e4`
- `0x1800a8e5c`
- `0x1800ad148`
- `0x1800af5f0`
- `0x1800bc2e0`
- `0x1800c5f38`
- `0x1800ccebc`
- `0x1800cd4dc`
- `0x1800d0d9c`
- `0x1800e3310`
- `0x1800e6664`
- `0x1800fd6f4`
- `0x1800fda74`
- `0x18010513c`
- `0x180109420`
- `0x180114278`
- `0x18011a3b0`
- `0x18012de40`
- `0x18012eae4`
- `0x180161064`
- `0x180177cf8`
- `0x1801a270c`
- `0x1801a2788`
- `0x1801c80b4`
- `0x1801c973c`
- `0x1801c9d28`
- `0x1801ca2a8`
- `0x1801cb284`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801c81a4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801c81a4`

## string_xrefs

- `0x1801c8217`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c82d2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c87a3`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8816`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8898`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c88fe`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8961`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8a98`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8ae2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8b6b`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8cb2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8da4`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8e99`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8efd`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8f9c`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8fe9`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c9070`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801c8e26`: `AgentId`
- `0x1801c8dcf`: `AgentConnectionEstablished_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::AgentManager::OnMessageReceived_::_2_::_lambda_1_::operator()(
        struct Microsoft::Diagnostics::ITriggerInst *a1)
{
  struct Microsoft::Diagnostics::ITriggerInst *v1; // r14
  std::_Ref_count_base *v2; // rsi
  Microsoft::Diagnostics::AgentManager *v3; // rcx
  __int64 v4; // r8
  __int64 v5; // rdx
  __int64 v7; // rdx
  unsigned int v8; // r8d
  int JsonBuilderFromBufferOrString; // eax
  unsigned int v10; // ebx
  Microsoft::Diagnostics::AsimovEventSerializer *AsimovEventSerializer; // rax
  struct Microsoft::Diagnostics::ETWTriggerInst *v12; // rcx
  const void *v13; // rax
  const char *v14; // r9
  struct Microsoft::Diagnostics::TriggerListener *TriggerListener; // rax
  __int64 *Consumer; // rax
  __int64 v17; // r8
  __int64 v18; // r12
  std::_Ref_count_base *v19; // r15
  __int64 v20; // rbx
  _QWORD *FullyQualifiedName; // rax
  __int64 v22; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // rcx
  __int64 v29; // r15
  __int64 v30; // rdx
  __int64 v31; // rbx
  int v32; // eax
  wil::details::in1diag3 *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rcx
  _OWORD *v36; // rdx
  Microsoft::Diagnostics::TraceManager *TraceManager; // rax
  __int64 v38; // rcx
  int v39; // eax
  int v40; // ebx
  struct Microsoft::Diagnostics::TenantManager *TenantManager; // rbx
  int v42; // eax
  int v43; // eax
  struct Microsoft::Diagnostics::TenantManager *v44; // rbx
  int v45; // eax
  int v46; // eax
  int v47; // ebx
  Microsoft::Diagnostics::AgentManager *v48; // rbx
  __int64 v49; // rcx
  __int64 *v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r15
  Microsoft::Diagnostics::AgentManager *v53; // rbx
  __int64 v54; // r15
  Microsoft::Diagnostics::AgentManager *v55; // rbx
  __int64 v56; // rcx
  _OWORD *v57; // rdx
  char *v58; // rcx
  __int64 v59; // rax
  int v60; // r8d
  int v61; // r9d
  __int64 v62; // rcx
  __int64 v63; // rdx
  int v64; // r8d
  int v65; // r9d
  __int64 v66; // rcx
  Microsoft::Diagnostics::AgentManager *v67; // rcx
  int v68; // eax
  int v69; // eax
  __int64 v70; // rdx
  char v71; // al
  Microsoft::Diagnostics::AgentManager *v72; // rcx
  int v73; // r12d
  __int64 v74; // rdx
  Microsoft::Diagnostics::AgentManager *v75; // rcx
  int v76; // r8d
  int v77; // r9d
  int active; // eax
  struct Microsoft::Diagnostics::DTraceManager *DTraceManager; // rax
  Microsoft::Diagnostics::AgentManager *v80; // rcx
  int v81; // eax
  unsigned int v82; // [rsp+20h] [rbp-6F8h]
  char v83; // [rsp+40h] [rbp-6D8h] BYREF
  char v84[15]; // [rsp+41h] [rbp-6D7h] BYREF
  struct Microsoft::Diagnostics::ITriggerInst *v85; // [rsp+50h] [rbp-6C8h] BYREF
  std::_Ref_count_base *v86; // [rsp+58h] [rbp-6C0h]
  std::_Ref_count_base *v87[2]; // [rsp+60h] [rbp-6B8h] BYREF
  struct Microsoft::Diagnostics::ETWTriggerInst *v88[2]; // [rsp+70h] [rbp-6A8h] BYREF
  __int128 v89; // [rsp+80h] [rbp-698h] BYREF
  _QWORD v90[2]; // [rsp+90h] [rbp-688h] BYREF
  void *lpMem[2]; // [rsp+A0h] [rbp-678h] BYREF
  __int128 v92; // [rsp+B0h] [rbp-668h]
  __int128 v93; // [rsp+C0h] [rbp-658h]
  _OWORD v94[4]; // [rsp+D0h] [rbp-648h] BYREF
  __int64 v95; // [rsp+110h] [rbp-608h]
  char v96; // [rsp+120h] [rbp-5F8h] BYREF
  wchar_t v97[135]; // [rsp+122h] [rbp-5F6h] BYREF
  _BYTE v98[1128]; // [rsp+230h] [rbp-4E8h] BYREF
  char v99; // [rsp+698h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+718h] [rbp+0h]

  v1 = a1;
  v85 = a1;
  *(_OWORD *)v87 = 0;
  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v89, *(_QWORD *)a1 + 128LL);
  v90[0] = *(_QWORD *)(**((_QWORD **)v1 + 1) + 8LL);
  std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::find(
    *(_QWORD *)v1 + 208LL,
    v88,
    v90);
  if ( v88[0] == *(struct Microsoft::Diagnostics::ETWTriggerInst **)(*(_QWORD *)v1 + 208LL) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x342,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x80070490LL,
      v82);
  std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(v87, (char *)v88[0] + 40);
  v2 = v87[0];
  if ( *((_BYTE *)v87[0] + 249) )
  {
    std::wstring::operator std::wstring_view((char *)v87[0] + 264, v90);
    if ( v90[1] )
    {
      if ( *((_BYTE *)v2 + 329) )
        Microsoft::Diagnostics::AgentManager::LogIdleAgentEvent(v3, v2, 0);
    }
  }
  *((_QWORD *)v2 + 42) = GetTickCount64();
  *((_BYTE *)v2 + 329) = 0;
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v89);
  if ( !**((_BYTE **)v1 + 2) )
  {
    v56 = **((_QWORD **)v1 + 1);
    v57 = *(_OWORD **)(v56 + 24);
    if ( *(_DWORD *)(v56 + 32) - (_DWORD)v57 != 258 )
      goto LABEL_102;
    v58 = &v96;
    v59 = 2;
    do
    {
      *(_OWORD *)v58 = *v57;
      *((_OWORD *)v58 + 1) = v57[1];
      *((_OWORD *)v58 + 2) = v57[2];
      *((_OWORD *)v58 + 3) = v57[3];
      *((_OWORD *)v58 + 4) = v57[4];
      *((_OWORD *)v58 + 5) = v57[5];
      *((_OWORD *)v58 + 6) = v57[6];
      *((_OWORD *)v58 + 7) = v57[7];
      v58 += 128;
      v57 += 8;
      --v59;
    }
    while ( v59 );
    *(_WORD *)v58 = *(_WORD *)v57;
    if ( (unsigned __int8)v96 < 7u )
    {
      if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x8000) )
      {
        v84[0] = 7;
        v83 = 9;
        LOBYTE(v88[0]) = v96;
        v62 = **((_QWORD **)v1 + 1);
        v85 = *(struct Microsoft::Diagnostics::ITriggerInst **)(v62 + 8);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
          v62,
          (unsigned int)&unk_1803C7B0B,
          v60,
          v61,
          (__int64)&v85,
          (__int64)v88,
          (__int64)&v83,
          (__int64)v84);
      }
      v40 = -2147024809;
      v63 = 870;
      goto LABEL_112;
    }
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x8000) )
    {
      LOBYTE(v88[0]) = v96;
      v83 = 9;
      v66 = **((_QWORD **)v1 + 1);
      v85 = *(struct Microsoft::Diagnostics::ITriggerInst **)(v66 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v66,
        (unsigned int)&unk_1803C7B7C,
        v64,
        v65,
        (__int64)&v85,
        (__int64)&v83,
        (__int64)v88);
    }
    v88[0] = 0;
    v40 = StringCchLengthW(v97, 0x80u, (unsigned __int64 *)v88);
    if ( v40 < 0 )
    {
      v63 = 883;
LABEL_112:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v63,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v40,
        v82);
      goto LABEL_113;
    }
    std::wstring::_Assign<wchar_t>((char **)v2 + 33, v97, (char *)v88[0]);
    v68 = Microsoft::Diagnostics::AgentManager::SetAgentContainerTelemetryId(v67, v2);
    if ( v68 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x377,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v68,
        v82);
    *((_BYTE *)v2 + 348) = v96;
    *((_BYTE *)v2 + 249) = 1;
    v85 = (struct Microsoft::Diagnostics::ITriggerInst *)L"AgentConnectionEstablished_0";
    v86 = (std::_Ref_count_base *)28;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v98,
      (unsigned int)&v85,
      0x1000000,
      0,
      0,
      0,
      0);
    std::wstring::operator std::wstring_view((char *)v2 + 264, &v89);
    v85 = (struct Microsoft::Diagnostics::ITriggerInst *)L"AgentId";
    v86 = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v98, (unsigned int)&v99);
    v89 = 0;
    Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v88, &v89);
    v69 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v98);
    if ( v69 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v69,
        v82);
    v71 = v96;
    if ( (unsigned __int8)v96 > 9u )
      v71 = 9;
    LOBYTE(v90[0]) = v71;
    v85 = (struct Microsoft::Diagnostics::ITriggerInst *)1;
    v86 = (std::_Ref_count_base *)v90;
    LOBYTE(v70) = 1;
    v73 = Microsoft::Diagnostics::AgentTransport::SendAgentMessage(v2, v70, &v85);
    if ( v73 < 0 )
    {
      v74 = 906;
LABEL_129:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v74,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v73,
        v82);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v98);
      if ( v87[1] )
        std::_Ref_count_base::_Decref(v87[1]);
      return (unsigned int)v73;
    }
    if ( (unsigned __int16)(qword_18043C08A - 3) > 1u )
    {
      v73 = Microsoft::Diagnostics::AgentManager::SendAuthorizationInfoToAgent(v72, v2);
      if ( v73 < 0 )
      {
        v74 = 910;
        goto LABEL_129;
      }
      v73 = Microsoft::Diagnostics::AgentManager::SendTriggerSettingsToAgent(v75, v2);
      if ( v73 < 0 )
      {
        v74 = 912;
        goto LABEL_129;
      }
      LOWORD(v88[0]) = 0;
      LOBYTE(v77) = 1;
      LOBYTE(v76) = 9;
      active = Microsoft::Diagnostics::AgentManager::SendActiveTracesToAgents(*(_QWORD *)v1, (_DWORD)v2, v76, v77, 0);
      if ( active < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x391,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)active,
          v82);
      DTraceManager = Microsoft::Diagnostics::LifetimeManager::GetDTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::DTraceManager::CreateAgentMessage(DTraceManager, lpMem);
      v81 = Microsoft::Diagnostics::AgentManager::SendUpdatedDTraceRequestsToAgent(
              v80,
              v2,
              (const struct JsonBuilder *)lpMem);
      if ( v81 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x394,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v81,
          v82);
      JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
    }
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v98);
    goto LABEL_143;
  }
  if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 4 )
  {
    v4 = *((_QWORD *)v1 + 1);
    v5 = *(_QWORD *)(*(_QWORD *)v4 + 24LL);
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v4 + 32LL) - v5) <= 0x48 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)0x8007000DLL,
        v82);
      if ( v87[1] )
        std::_Ref_count_base::_Decref(v87[1]);
      return 2147942413LL;
    }
    v94[0] = *(_OWORD *)v5;
    v94[1] = *(_OWORD *)(v5 + 16);
    v94[2] = *(_OWORD *)(v5 + 32);
    v94[3] = *(_OWORD *)(v5 + 48);
    v95 = *(_QWORD *)(v5 + 64);
    v7 = *(_QWORD *)(*(_QWORD *)v4 + 24LL);
    v8 = *(_DWORD *)(*(_QWORD *)v4 + 32LL) - v7 - 72;
    lpMem[0] = 0;
    lpMem[1] = 0;
    LOBYTE(v92) = 0;
    JsonBuilderFromBufferOrString = Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(
                                      *((_BYTE *)v2 + 250),
                                      (const void *)(v7 + 72),
                                      v8,
                                      (struct JsonBuilder *)lpMem);
    v10 = JsonBuilderFromBufferOrString;
    if ( JsonBuilderFromBufferOrString < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3A4,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)JsonBuilderFromBufferOrString,
        v82);
      JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
      if ( v87[1] )
        std::_Ref_count_base::_Decref(v87[1]);
      return v10;
    }
    if ( (unsigned __int16)(qword_18043C08A - 3) > 1u )
    {
      Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(
        v88,
        (__int64)v94,
        (__int64)lpMem,
        (__int64)v2,
        0);
      if ( *((_BYTE *)v2 + 251) )
      {
        v13 = (const void *)(*(__int64 (__fastcall **)(struct Microsoft::Diagnostics::ETWTriggerInst *))(*(_QWORD *)v88[0] + 80LL))(v88[0]);
        if ( memcmp_0(v13, &GUID_NULL, 0x10u) )
          Microsoft::Diagnostics::TraceLoggingDynamicRelogger::RelogEvent(
            (Microsoft::Diagnostics::TraceLoggingDynamicRelogger *)(*(_QWORD *)v1 + 744LL),
            v88[0]);
      }
      if ( !*((_BYTE *)v2 + 349) )
      {
        try
        {
          *((_BYTE *)v2 + 349) = (Microsoft::Diagnostics::IAsimovEvent::NeedsCommonSchemaTranslation(v88[0], 0) ^ 1) + 1;
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x3C5,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            v14);
          v2 = v87[0];
          v1 = v85;
        }
      }
      if ( byte_18043B7A8 )
      {
        TriggerListener = Microsoft::Diagnostics::LifetimeManager::GetTriggerListener((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
        LOWORD(v90[0]) = 1;
        Consumer = (__int64 *)Microsoft::Diagnostics::TriggerListener::GetConsumer(TriggerListener, &v85, 1);
        v18 = *Consumer;
        *(_QWORD *)&v89 = *Consumer;
        v19 = (std::_Ref_count_base *)Consumer[1];
        *((_QWORD *)&v89 + 1) = v19;
        *Consumer = 0;
        Consumer[1] = 0;
        if ( v86 )
          std::_Ref_count_base::_Decref(v86);
        LOBYTE(v17) = *((_BYTE *)v2 + 349) == 1;
        Microsoft::Diagnostics::ETWConsumer::AgentEventCallback(v18, v88, v17);
        if ( v19 )
          std::_Ref_count_base::_Decref(v19);
      }
      else if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 17) )
      {
        v20 = *(_QWORD *)(Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(v88[0], &v89) + 8);
        FullyQualifiedName = (_QWORD *)Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(v88[0], &v85);
        v22 = _tlgWrapBinary<wchar_t,2>(v90, *FullyQualifiedName, (unsigned int)v20);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
          v23,
          (unsigned int)&unk_1803C7A74,
          v24,
          v25,
          v22);
      }
      v12 = v88[1];
    }
    else
    {
      Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(
        &v85,
        (__int64)v94,
        (__int64)lpMem,
        (__int64)v2,
        1);
      *((_QWORD *)v85 + 37) = 0x4059000000000000LL;
      AsimovEventSerializer = Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistTrigger(AsimovEventSerializer, v85, 0);
      v12 = v86;
    }
    if ( v12 )
      std::_Ref_count_base::_Decref(v12);
    goto LABEL_34;
  }
  if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 5 )
  {
    if ( *(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - (unsigned int)*(_QWORD *)(**((_QWORD **)v1 + 1) + 24LL) == 4 )
    {
      if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 32784) )
      {
        LODWORD(v90[0]) = v26;
        v28 = **((_QWORD **)v1 + 1);
        v85 = *(struct Microsoft::Diagnostics::ITriggerInst **)(v28 + 8);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
          v28,
          (unsigned int)&unk_1803C7AB4,
          v26,
          v27,
          (__int64)&v85,
          (__int64)v90);
      }
      **((_BYTE **)v1 + 3) = 1;
      goto LABEL_143;
    }
LABEL_102:
    if ( v87[1] )
      std::_Ref_count_base::_Decref(v87[1]);
    return 13;
  }
  if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 8 )
  {
    v29 = *((_QWORD *)v1 + 1);
    if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v29 + 32LL) - *(_DWORD *)(*(_QWORD *)v29 + 24LL)) < 0x18 )
    {
      v30 = 1004;
LABEL_95:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)0x8007000DLL,
        v82);
      if ( v87[1] )
        std::_Ref_count_base::_Decref(v87[1]);
      return 2147942413LL;
    }
    v31 = *(_QWORD *)v1;
    v89 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v2, &v85);
    v32 = Microsoft::Diagnostics::IAgentIoReceiver::ProcessEscalationDataMessage(v31, &v89, v29);
    v33 = retaddr;
    if ( v32 < 0 )
    {
      v34 = 1005;
LABEL_90:
      wil::details::in1diag3::_Log_Hr(
        v33,
        (void *)v34,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)(unsigned int)v32,
        v82);
      goto LABEL_143;
    }
    goto LABEL_143;
  }
  if ( !*((_BYTE *)v2 + 249) || **((_BYTE **)v1 + 2) != 10 )
  {
    if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 11 )
    {
      v38 = (unsigned int)(*(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - *(_DWORD *)(**((_QWORD **)v1 + 1) + 24LL));
      if ( (_DWORD)v38 != 16 )
        goto LABEL_102;
      Microsoft::Diagnostics::AgentManager::FulfillScenarioObjectRequest(v38, v87);
      v2 = v87[0];
      goto LABEL_143;
    }
    if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 12 )
      goto LABEL_143;
    if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 15 )
    {
      lpMem[0] = 0;
      lpMem[1] = 0;
      LOBYTE(v92) = 0;
      v39 = Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(
              *((_BYTE *)v2 + 250),
              *(const void **)(**((_QWORD **)v1 + 1) + 24LL),
              *(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - *(_QWORD *)(**((_QWORD **)v1 + 1) + 24LL),
              (struct JsonBuilder *)lpMem);
      v40 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x405,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v39,
          v82);
LABEL_63:
        JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
        goto LABEL_113;
      }
      TenantManager = Microsoft::Diagnostics::LifetimeManager::GetTenantManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v89 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v2, &v85);
      v42 = Microsoft::Diagnostics::TenantManager::RegisterTenant(TenantManager, &v89, lpMem);
      if ( v42 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x408,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v42,
          v82);
    }
    else
    {
      if ( !*((_BYTE *)v2 + 249) || **((_BYTE **)v1 + 2) != 16 )
      {
        if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 13 )
        {
          v46 = Microsoft::Diagnostics::AgentManager::SnapHostTrace(
                  *(Microsoft::Diagnostics::AgentManager **)v1,
                  v2,
                  **((struct Microsoft::Diagnostics::IoRequest ***)v1 + 1));
          v47 = v46;
          if ( v46 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x416,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
              (const char *)(unsigned int)v46,
              v82);
          LOBYTE(v90[0]) = 13;
          HIDWORD(v90[0]) = v47;
          v48 = *(Microsoft::Diagnostics::AgentManager **)v1;
          v89 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v2, &v85);
          v32 = Microsoft::Diagnostics::AgentManager::SendApiCompletionMessage(v48, &v89, v90);
          v33 = retaddr;
          if ( v32 >= 0 )
            goto LABEL_143;
          v34 = 1050;
          goto LABEL_90;
        }
        if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 18 )
        {
          v49 = **((_QWORD **)v1 + 1);
          v50 = *(__int64 **)(v49 + 24);
          if ( (unsigned int)(*(_DWORD *)(v49 + 32) - (_DWORD)v50) < 0x20 )
          {
            v30 = 1054;
            goto LABEL_95;
          }
          v51 = *v50;
          *((_BYTE *)v2 + 250) = *v50 & 1;
          *((_BYTE *)v2 + 251) = (v51 & 2) != 0;
          goto LABEL_143;
        }
        if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 19 )
        {
          v52 = *((_QWORD *)v1 + 1);
          if ( *(_DWORD *)(*(_QWORD *)v52 + 32LL) - *(_DWORD *)(*(_QWORD *)v52 + 24LL) != 100 )
            goto LABEL_102;
          v53 = *(Microsoft::Diagnostics::AgentManager **)v1;
          v89 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v2, &v85);
          v32 = Microsoft::Diagnostics::AgentWatsonCrashManager::RegisterWatsonCrashRequest(
                  (char *)v53 + 808,
                  &v89,
                  v52);
          v33 = retaddr;
          if ( v32 < 0 )
          {
            v34 = 1062;
            goto LABEL_90;
          }
          goto LABEL_143;
        }
        if ( *((_BYTE *)v2 + 249) && **((_BYTE **)v1 + 2) == 20 )
        {
          v54 = *((_QWORD *)v1 + 1);
          if ( (unsigned int)(*(_DWORD *)(*(_QWORD *)v54 + 32LL) - *(_DWORD *)(*(_QWORD *)v54 + 24LL)) < 0x64 )
          {
            v30 = 1067;
            goto LABEL_95;
          }
          v55 = *(Microsoft::Diagnostics::AgentManager **)v1;
          v89 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v2, &v85);
          v32 = Microsoft::Diagnostics::AgentWatsonCrashManager::ProcessWatsonCrash((char *)v55 + 808, &v89, v54);
          v33 = retaddr;
          if ( v32 < 0 )
          {
            v34 = 1068;
            goto LABEL_90;
          }
          goto LABEL_143;
        }
        v40 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x431,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
                (const char *)0xD,
                v82);
LABEL_113:
        if ( v87[1] )
          std::_Ref_count_base::_Decref(v87[1]);
        return (unsigned int)v40;
      }
      lpMem[0] = 0;
      lpMem[1] = 0;
      LOBYTE(v92) = 0;
      v43 = Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(
              *((_BYTE *)v2 + 250),
              *(const void **)(**((_QWORD **)v1 + 1) + 24LL),
              *(_DWORD *)(**((_QWORD **)v1 + 1) + 32LL) - *(_QWORD *)(**((_QWORD **)v1 + 1) + 24LL),
              (struct JsonBuilder *)lpMem);
      v40 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x40E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v43,
          v82);
        goto LABEL_63;
      }
      v44 = Microsoft::Diagnostics::LifetimeManager::GetTenantManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      v89 = *(_OWORD *)Microsoft::Diagnostics::AgentTransport::GetNonPrefixedAgentIdString(v2, &v85);
      v45 = Microsoft::Diagnostics::TenantManager::UnregisterTenant(v44, &v89, lpMem);
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x411,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)(unsigned int)v45,
          v82);
    }
LABEL_34:
    JsonInternal::PodVectorBase::Deallocate(lpMem[0]);
    goto LABEL_143;
  }
  v35 = **((_QWORD **)v1 + 1);
  v36 = *(_OWORD **)(v35 + 24);
  if ( *(_DWORD *)(v35 + 32) - (_DWORD)v36 != 48 )
    goto LABEL_102;
  *(_OWORD *)lpMem = *v36;
  v92 = v36[1];
  v93 = v36[2];
  TraceManager = Microsoft::Diagnostics::LifetimeManager::GetTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  v32 = Microsoft::Diagnostics::TraceManager::StopInactiveAgentTrace(
          TraceManager,
          v2,
          (const struct Microsoft::Diagnostics::TraceIdMessage *)lpMem);
  v33 = retaddr;
  if ( v32 < 0 )
  {
    v34 = 1013;
    goto LABEL_90;
  }
LABEL_143:
  if ( !**((_BYTE **)v1 + 3) )
  {
    v40 = Microsoft::Diagnostics::AgentTransport::ReceiveAgentMessage(v2);
    if ( v40 < 0 )
    {
      v63 = 1079;
      goto LABEL_112;
    }
  }
  if ( v87[1] )
    std::_Ref_count_base::_Decref(v87[1]);
  return 0;
}

```

## disassembly

```asm
0x1801c80b4  push    rbx
0x1801c80b6  push    rsi
0x1801c80b7  push    rdi
0x1801c80b8  push    r12
0x1801c80ba  push    r14
0x1801c80bc  push    r15
0x1801c80be  sub     rsp, 6E8h
0x1801c80c5  mov     rax, cs:__security_cookie
0x1801c80cc  xor     rax, rsp
0x1801c80cf  mov     [rsp+718h+var_48], rax
0x1801c80d7  mov     r14, rcx
0x1801c80da  mov     [rsp+718h+var_6C8], rcx
0x1801c80df  xorps   xmm0, xmm0
0x1801c80e2  movdqu  xmmword ptr [rsp+718h+var_6B8], xmm0
0x1801c80e8  mov     rdx, [rcx]
0x1801c80eb  mov     ebx, 80h
0x1801c80f0  add     rdx, rbx
0x1801c80f3  lea     rcx, [rsp+718h+var_698]
0x1801c80fb  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1801c8100  nop
0x1801c8101  mov     rax, [r14+8]
0x1801c8105  mov     rcx, [rax]
0x1801c8108  mov     rax, [rcx+8]
0x1801c810c  mov     [rsp+718h+var_688], rax
0x1801c8114  mov     rcx, [r14]
0x1801c8117  add     rcx, 0D0h
0x1801c811e  lea     r8, [rsp+718h+var_688]
0x1801c8126  lea     rdx, [rsp+718h+var_6A8]
0x1801c812b  call    ?find@?$_Tree@V?$_Tset_traits@_KU?$less@_K@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEBA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@_K@std@@@std@@@2@AEB_K@Z; std::_Tree<std::_Tset_traits<unsigned __int64,std::less<unsigned __int64>,std::allocator<unsigned __int64>,0>>::find(unsigned __int64 const &)
0x1801c8130  mov     r8, [r14]
0x1801c8133  mov     rdx, [rsp+718h+var_6A8]
0x1801c8138  cmp     rdx, [r8+0D0h]
0x1801c813f  setz    al
0x1801c8142  mov     rcx, [rsp+718h]; this
0x1801c814a  xor     edi, edi
0x1801c814c  test    al, al
0x1801c814e  jnz     loc_1801C906A
0x1801c8154  add     rdx, 28h ; '('
0x1801c8158  lea     rcx, [rsp+718h+var_6B8]
0x1801c815d  call    ??4?$shared_ptr@VITriggerInst@Diagnostics@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::ITriggerInst>::operator=(std::shared_ptr<Microsoft::Diagnostics::ITriggerInst> const &)
0x1801c8162  mov     rsi, [rsp+718h+var_6B8]
0x1801c8167  mov     al, [rsi+0F9h]
0x1801c816d  nop
0x1801c816e  test    al, al
0x1801c8170  jz      short loc_1801C81A4
0x1801c8172  lea     rcx, [rsi+108h]
0x1801c8179  lea     rdx, [rsp+718h+var_688]
0x1801c8181  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801c8186  cmp     [rsp+718h+var_680], rdi
0x1801c818e  jz      short loc_1801C81A4
0x1801c8190  cmp     [rsi+149h], dil
0x1801c8197  jz      short loc_1801C81A4
0x1801c8199  xor     r8d, r8d; bool
0x1801c819c  mov     rdx, rsi; struct Microsoft::Diagnostics::AgentTransport *
0x1801c819f  call    ?LogIdleAgentEvent@AgentManager@Diagnostics@Microsoft@@AEAAXAEBVAgentTransport@23@_N@Z; Microsoft::Diagnostics::AgentManager::LogIdleAgentEvent(Microsoft::Diagnostics::AgentTransport const &,bool)
0x1801c81a4  call    cs:__imp_GetTickCount64
0x1801c81ab  nop     dword ptr [rax+rax+00h]
0x1801c81b0  mov     [rsi+150h], rax
0x1801c81b7  mov     [rsi+149h], dil
0x1801c81be  lea     rcx, [rsp+718h+var_698]
0x1801c81c6  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801c81cb  mov     rax, [r14+10h]
0x1801c81cf  cmp     [rax], dil
0x1801c81d2  jz      loc_1801C8B83
0x1801c81d8  mov     al, [rsi+0F9h]
0x1801c81de  nop
0x1801c81df  test    al, al
0x1801c81e1  jz      loc_1801C8541
0x1801c81e7  mov     rax, [r14+10h]
0x1801c81eb  cmp     byte ptr [rax], 4
0x1801c81ee  jnz     loc_1801C8541
0x1801c81f4  mov     r8, [r14+8]
0x1801c81f8  mov     rax, [r8]
0x1801c81fb  mov     rdx, [rax+18h]
0x1801c81ff  mov     ecx, [rax+20h]
0x1801c8202  sub     ecx, edx
0x1801c8204  cmp     ecx, 48h ; 'H'
0x1801c8207  ja      short loc_1801C8242
0x1801c8209  mov     rcx, [rsp+718h]; this
0x1801c8211  mov     r9d, 8007000Dh; char *
0x1801c8217  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801c821e  mov     edx, 39Ch; void *
0x1801c8223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c8228  nop
0x1801c8229  mov     rcx, [rsp+718h+var_6B8+8]; this
0x1801c822e  test    rcx, rcx
0x1801c8231  jz      short loc_1801C8238
0x1801c8233  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c8238  mov     eax, 8007000Dh
0x1801c823d  jmp     loc_1801C9048
0x1801c8242  movups  xmm0, xmmword ptr [rdx]
0x1801c8245  movaps  [rsp+718h+var_648], xmm0
0x1801c824d  movups  xmm1, xmmword ptr [rdx+10h]
0x1801c8251  movaps  [rsp+718h+var_638], xmm1
0x1801c8259  movups  xmm0, xmmword ptr [rdx+20h]
0x1801c825d  movaps  [rsp+718h+var_628], xmm0
0x1801c8265  movups  xmm1, xmmword ptr [rdx+30h]
0x1801c8269  movaps  [rsp+718h+var_618], xmm1
0x1801c8271  movsd   xmm0, qword ptr [rdx+40h]
0x1801c8276  movsd   [rsp+718h+var_608], xmm0
0x1801c827f  mov     rax, [r8]
0x1801c8282  mov     rdx, [rax+18h]
0x1801c8286  mov     r8d, [rax+20h]
0x1801c828a  sub     r8d, edx
0x1801c828d  add     r8d, 0FFFFFFB8h; unsigned int
0x1801c8291  mov     [rsp+718h+lpMem], rdi
0x1801c8299  mov     [rsp+718h+lpMem+8], rdi
0x1801c82a1  mov     byte ptr [rsp+718h+var_668], dil
0x1801c82a9  mov     cl, [rsi+0FAh]; bool
0x1801c82af  nop
0x1801c82b0  add     rdx, 48h ; 'H'; void *
0x1801c82b4  lea     r9, [rsp+718h+lpMem]; struct JsonBuilder *
0x1801c82bc  call    ?CreateJsonBuilderFromBufferOrString@Json@Utils@Diagnostics@Microsoft@@SAJ_NPEBXIAEAVJsonBuilder@@@Z; Microsoft::Diagnostics::Utils::Json::CreateJsonBuilderFromBufferOrString(bool,void const *,uint,JsonBuilder &)
0x1801c82c1  mov     ebx, eax
0x1801c82c3  test    eax, eax
0x1801c82c5  jns     short loc_1801C8308
0x1801c82c7  mov     rcx, [rsp+718h]; this
0x1801c82cf  mov     r9d, eax; char *
0x1801c82d2  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801c82d9  mov     edx, 3A4h; void *
0x1801c82de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c82e3  nop
0x1801c82e4  mov     rcx, [rsp+718h+lpMem]; lpMem
0x1801c82ec  call    ?Deallocate@PodVectorBase@JsonInternal@@KAXPEAX@Z; JsonInternal::PodVectorBase::Deallocate(void *)
0x1801c82f1  nop
0x1801c82f2  mov     rcx, [rsp+718h+var_6B8+8]; this
0x1801c82f7  test    rcx, rcx
0x1801c82fa  jz      short loc_1801C8301
0x1801c82fc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c8301  mov     eax, ebx
0x1801c8303  jmp     loc_1801C9048
0x1801c8308  movzx   eax, word ptr cs:qword_18043C08A
0x1801c830f  sub     ax, 3
0x1801c8313  mov     ebx, 1
0x1801c8318  mov     r9, rsi
0x1801c831b  lea     r8, [rsp+718h+lpMem]
0x1801c8323  lea     rdx, [rsp+718h+var_648]
0x1801c832b  cmp     ax, bx
0x1801c832e  ja      short loc_1801C837C
0x1801c8330  mov     byte ptr [rsp+718h+var_6F8], bl
0x1801c8334  lea     rcx, [rsp+718h+var_6C8]
0x1801c8339  call    ?CreateTriggerFromTelemetryMessage@AgentManager@Diagnostics@Microsoft@@CA?AV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@AEBUAgentTelemetryEventMessage@23@$$QEAVJsonBuilder@@AEAVAgentTransport@23@_N@Z; Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(Microsoft::Diagnostics::AgentTelemetryEventMessage const &,JsonBuilder &&,Microsoft::Diagnostics::AgentTransport &,bool)
0x1801c833e  nop
0x1801c833f  mov     rcx, 4059000000000000h
0x1801c8349  mov     rax, [rsp+718h+var_6C8]
0x1801c834e  mov     [rax+128h], rcx
0x1801c8355  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801c835c  call    ?GetAsimovEventSerializer@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVAsimovEventSerializer@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetAsimovEventSerializer(void)
0x1801c8361  xor     r8d, r8d; struct Microsoft::Diagnostics::IScenarioDef *
0x1801c8364  mov     rdx, [rsp+718h+var_6C8]; struct Microsoft::Diagnostics::ITriggerInst *
0x1801c8369  mov     rcx, rax; this
0x1801c836c  call    ?PersistTrigger@AsimovEventSerializer@Diagnostics@Microsoft@@QEAAJAEAVITriggerInst@23@PEBVIScenarioDef@23@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistTrigger(Microsoft::Diagnostics::ITriggerInst &,Microsoft::Diagnostics::IScenarioDef const *)
0x1801c8371  nop
0x1801c8372  mov     rcx, [rsp+718h+var_6C0]
0x1801c8377  jmp     loc_1801C8508
0x1801c837c  mov     byte ptr [rsp+718h+var_6F8], dil
0x1801c8381  lea     rcx, [rsp+718h+var_6A8]
0x1801c8386  call    ?CreateTriggerFromTelemetryMessage@AgentManager@Diagnostics@Microsoft@@CA?AV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@AEBUAgentTelemetryEventMessage@23@$$QEAVJsonBuilder@@AEAVAgentTransport@23@_N@Z; Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(Microsoft::Diagnostics::AgentTelemetryEventMessage const &,JsonBuilder &&,Microsoft::Diagnostics::AgentTransport &,bool)
0x1801c838b  nop
0x1801c838c  mov     al, [rsi+0FBh]
0x1801c8392  nop
0x1801c8393  test    al, al
0x1801c8395  jz      short loc_1801C83D5
0x1801c8397  mov     rcx, [rsp+718h+var_6A8]
0x1801c839c  mov     rax, [rcx]
0x1801c839f  mov     rax, [rax+50h]
0x1801c83a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c83a8  mov     r8d, 10h; Size
0x1801c83ae  lea     rdx, GUID_NULL; Buf2
0x1801c83b5  mov     rcx, rax; Buf1
0x1801c83b8  call    memcmp_0
0x1801c83bd  test    eax, eax
0x1801c83bf  jz      short loc_1801C83D5
0x1801c83c1  mov     rcx, [r14]
0x1801c83c4  add     rcx, 2E8h; this
0x1801c83cb  mov     rdx, [rsp+718h+var_6A8]; struct Microsoft::Diagnostics::ETWTriggerInst *
0x1801c83d0  call    ?RelogEvent@TraceLoggingDynamicRelogger@Diagnostics@Microsoft@@QEAAXAEBVETWTriggerInst@23@@Z; Microsoft::Diagnostics::TraceLoggingDynamicRelogger::RelogEvent(Microsoft::Diagnostics::ETWTriggerInst const &)
0x1801c83d5  mov     al, [rsi+15Dh]
0x1801c83db  nop
0x1801c83dc  test    al, al
0x1801c83de  jnz     short loc_1801C8407
0x1801c83e0  xor     edx, edx
0x1801c83e2  mov     rcx, [rsp+718h+var_6A8]
0x1801c83e7  call    ?NeedsCommonSchemaTranslation@IAsimovEvent@Diagnostics@Microsoft@@QEAA_NPEAV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::IAsimovEvent::NeedsCommonSchemaTranslation(std::wstring_view *)
0x1801c83ec  xor     al, bl
0x1801c83ee  add     al, bl
0x1801c83f0  xchg    al, [rsi+15Dh]
0x1801c83f6  jmp     short loc_1801C8407
0x1801c83f8  xor     edi, edi
0x1801c83fa  lea     ebx, [rdi+1]
0x1801c83fd  mov     rsi, [rsp+718h+var_6B8]
0x1801c8402  mov     r14, [rsp+718h+var_6C8]
0x1801c8407  mov     al, cs:byte_18043B7A8
0x1801c840d  nop
0x1801c840e  test    al, al
0x1801c8410  jz      loc_1801C8499
0x1801c8416  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801c841d  call    ?GetTriggerListener@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTriggerListener@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTriggerListener(void)
0x1801c8422  mov     word ptr [rsp+718h+var_688], 1
0x1801c842c  movzx   r8d, word ptr [rsp+718h+var_688]
0x1801c8435  lea     rdx, [rsp+718h+var_6C8]
0x1801c843a  mov     rcx, rax
0x1801c843d  call    ?GetConsumer@TriggerListener@Diagnostics@Microsoft@@QEAA?AV?$shared_ptr@VIConsumer@Diagnostics@Microsoft@@@std@@U?$optional@VTriggerType@Diagnostics@Microsoft@@@better_enums@@@Z; Microsoft::Diagnostics::TriggerListener::GetConsumer(better_enums::optional<Microsoft::Diagnostics::TriggerType>)
0x1801c8442  mov     r12, [rax]
0x1801c8445  mov     qword ptr [rsp+718h+var_698], r12
0x1801c844d  mov     r15, [rax+8]
0x1801c8451  mov     qword ptr [rsp+718h+var_698+8], r15
0x1801c8459  mov     [rax], rdi
0x1801c845c  mov     [rax+8], rdi
0x1801c8460  mov     rcx, [rsp+718h+var_6C0]; this
0x1801c8465  test    rcx, rcx
0x1801c8468  jz      short loc_1801C846F
0x1801c846a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c846f  mov     al, [rsi+15Dh]
0x1801c8475  nop
0x1801c8476  cmp     al, bl
0x1801c8478  setz    r8b
0x1801c847c  lea     rdx, [rsp+718h+var_6A8]
0x1801c8481  mov     rcx, r12
0x1801c8484  call    ?AgentEventCallback@ETWConsumer@Diagnostics@Microsoft@@QEAAXAEBV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@_N@Z; Microsoft::Diagnostics::ETWConsumer::AgentEventCallback(std::shared_ptr<Microsoft::Diagnostics::ETWTriggerInst> const &,bool)
0x1801c8489  nop
0x1801c848a  test    r15, r15
0x1801c848d  jz      short loc_1801C8503
0x1801c848f  mov     rcx, r15; this
0x1801c8492  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c8497  jmp     short loc_1801C8503
0x1801c8499  mov     eax, cs:dword_18042D328
0x1801c849f  cmp     eax, 4
0x1801c84a2  jbe     short loc_1801C8503
0x1801c84a4  mov     edx, 11h
0x1801c84a9  lea     rcx, dword_18042D328
0x1801c84b0  call    _tlgKeywordOn
0x1801c84b5  test    al, al
0x1801c84b7  jz      short loc_1801C8503
0x1801c84b9  lea     rdx, [rsp+718h+var_698]
0x1801c84c1  mov     rcx, [rsp+718h+var_6A8]
0x1801c84c6  call    ?GetFullyQualifiedName@ITriggerInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(void)
0x1801c84cb  mov     rbx, [rax+8]
0x1801c84cf  lea     rdx, [rsp+718h+var_6C8]
0x1801c84d4  mov     rcx, [rsp+718h+var_6A8]
0x1801c84d9  call    ?GetFullyQualifiedName@ITriggerInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(void)
0x1801c84de  mov     r8d, ebx
0x1801c84e1  mov     rdx, [rax]
0x1801c84e4  lea     rcx, [rsp+718h+var_688]
0x1801c84ec  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x1801c84f1  mov     qword ptr [rsp+718h+var_6F8], rax
0x1801c84f6  lea     rdx, unk_1803C7A74
0x1801c84fd  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x1801c8502  nop
0x1801c8503  mov     rcx, [rsp+718h+var_6A0]; this
0x1801c8508  test    rcx, rcx
0x1801c850b  jz      short loc_1801C8513
0x1801c850d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c8512  nop
0x1801c8513  mov     rcx, [rsp+718h+lpMem]; lpMem
0x1801c851b  call    ?Deallocate@PodVectorBase@JsonInternal@@KAXPEAX@Z; JsonInternal::PodVectorBase::Deallocate(void *)
0x1801c8520  nop
0x1801c8521  jmp     loc_1801C9016
0x1801c8526  mov     rcx, [rsp+718h+var_6B8+8]; this
0x1801c852b  test    rcx, rcx
0x1801c852e  jz      short loc_1801C8535
0x1801c8530  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801c8535  mov     eax, dword ptr [rsp+718h+var_688]
0x1801c853c  jmp     loc_1801C9048
0x1801c8541  mov     al, [rsi+0F9h]
0x1801c8547  nop
0x1801c8548  test    al, al
0x1801c854a  jz      loc_1801C85E0
0x1801c8550  mov     rax, [r14+10h]
0x1801c8554  cmp     byte ptr [rax], 5
0x1801c8557  jnz     loc_1801C85E0
0x1801c855d  mov     rax, [r14+8]
0x1801c8561  mov     rax, [rax]
0x1801c8564  mov     rcx, [rax+18h]
0x1801c8568  mov     eax, [rax+20h]
0x1801c856b  sub     eax, ecx
0x1801c856d  cmp     eax, 4
0x1801c8570  jnz     loc_1801C8B9A
0x1801c8576  mov     r8d, [rcx]
0x1801c8579  mov     eax, cs:dword_18042D328
0x1801c857f  cmp     eax, 4
0x1801c8582  jbe     short loc_1801C85D4
0x1801c8584  mov     edx, 8010h
0x1801c8589  lea     rcx, dword_18042D328
0x1801c8590  call    _tlgKeywordOn
0x1801c8595  test    al, al
0x1801c8597  jz      short loc_1801C85D4
0x1801c8599  mov     dword ptr [rsp+718h+var_688], r8d
0x1801c85a1  mov     rax, [r14+8]
0x1801c85a5  mov     rcx, [rax]
0x1801c85a8  mov     rax, [rcx+8]
0x1801c85ac  mov     [rsp+718h+var_6C8], rax
0x1801c85b1  lea     rax, [rsp+718h+var_688]
0x1801c85b9  mov     [rsp+718h+var_6F0], rax
0x1801c85be  lea     rax, [rsp+718h+var_6C8]
0x1801c85c3  mov     qword ptr [rsp+718h+var_6F8], rax
0x1801c85c8  lea     rdx, unk_1803C7AB4
0x1801c85cf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1801c85d4  mov     rax, [r14+18h]
0x1801c85d8  mov     byte ptr [rax], 1
  ... truncated ...
```
