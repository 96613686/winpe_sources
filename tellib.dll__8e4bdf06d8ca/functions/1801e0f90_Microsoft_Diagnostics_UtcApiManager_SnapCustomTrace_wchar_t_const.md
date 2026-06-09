# Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace(wchar_t const *)

- ea: `0x1801e0f90`
- end: `0x1801e1c88`
- name: `?SnapCustomTrace@UtcApiManager@Diagnostics@Microsoft@@UEBAJPEB_W@Z`
- size: `3320`
- prototype: `int(Microsoft::Diagnostics::UtcApiManager *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `41`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001bf4`
- `0x180002058`
- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x18001ee94`
- `0x18001f1fc`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180030a50`
- `0x180032718`
- `0x180034d94`
- `0x180048ff4`
- `0x18004ab70`
- `0x18004be40`
- `0x1800551b0`
- `0x1800566b0`
- `0x18005d050`
- `0x18006e7e4`
- `0x18007fae8`
- `0x180082b70`
- `0x1800862cc`
- `0x18008630c`
- `0x180086f40`
- `0x180089d90`
- `0x18009d3ec`
- `0x1800a9c80`
- `0x1800d0d9c`
- `0x1800e35e4`
- `0x18012de40`
- `0x18012eae4`
- `0x1801bfc30`
- `0x1801c039c`
- `0x1801cc208`
- `0x1801d2aac`
- `0x1801e0f90`
- `0x18022ca48`
- `0x18026189c`
- `0x180261950`
- `0x1802b4efc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e1111`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801e1111`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801e1090`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801e1090`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801e1987`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x1801e1987`

## string_xrefs

- `0x1801e0fcf`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1020`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e10b0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1165`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e121f`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e12d0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e14b0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e15a1`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e16c9`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e17d6`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1829`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e19a8`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e1b1b`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace(
        Microsoft::Diagnostics::UtcApiManager *this,
        const wchar_t *a2)
{
  WCHAR *v4; // rcx
  const WCHAR *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  PWSTR *v8; // rax
  unsigned int v9; // ebx
  struct Microsoft::Diagnostics::TraceManager *TraceManager; // rdi
  struct _GUID *OwnerScenarioId; // rax
  __int64 UtcTemporaryPath; // rax
  void *appended; // rax
  __int64 v14; // rax
  void *v15; // rbx
  int v16; // eax
  int v17; // eax
  __int128 v18; // xmm6
  int v19; // edx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  __int64 v23; // rcx
  int RpcImpersonationToken; // eax
  __int64 v25; // r8
  Microsoft::Diagnostics::UserManager *v26; // r8
  __int64 UserContextForSid; // rbx
  int UserToken; // eax
  int v29; // eax
  unsigned int v30; // ebx
  unsigned int v31; // [rsp+20h] [rbp-1D8h]
  int v32; // [rsp+20h] [rbp-1D8h]
  int v33; // [rsp+20h] [rbp-1D8h]
  int v34; // [rsp+20h] [rbp-1D8h]
  char v35; // [rsp+40h] [rbp-1B8h] BYREF
  int v36; // [rsp+41h] [rbp-1B7h] BYREF
  PWSTR *v37; // [rsp+48h] [rbp-1B0h] BYREF
  char v38; // [rsp+50h] [rbp-1A8h]
  unsigned int v39[4]; // [rsp+60h] [rbp-198h] BYREF
  struct _GUID v40; // [rsp+70h] [rbp-188h] BYREF
  _QWORD v41[2]; // [rsp+80h] [rbp-178h] BYREF
  __int128 v42; // [rsp+90h] [rbp-168h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-158h] BYREF
  char v44; // [rsp+A8h] [rbp-150h]
  _BYTE v45[16]; // [rsp+B0h] [rbp-148h] BYREF
  WCHAR v46; // [rsp+C0h] [rbp-138h] BYREF
  __int64 v47; // [rsp+C2h] [rbp-136h]
  int v48; // [rsp+CAh] [rbp-12Eh]
  __int16 v49; // [rsp+CEh] [rbp-12Ah]
  __m128i v50; // [rsp+D0h] [rbp-128h]
  PWSTR pszPathOut[3]; // [rsp+E0h] [rbp-118h] BYREF
  unsigned __int64 v52; // [rsp+F8h] [rbp-100h]
  _OWORD v53[2]; // [rsp+100h] [rbp-F8h] BYREF
  _BYTE v54[16]; // [rsp+120h] [rbp-D8h] BYREF
  __int64 v55; // [rsp+130h] [rbp-C8h]
  WCHAR Src; // [rsp+140h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+142h] [rbp-B6h]
  int v58; // [rsp+14Ah] [rbp-AEh]
  __int16 v59; // [rsp+14Eh] [rbp-AAh]
  __m128i si128; // [rsp+150h] [rbp-A8h]
  WCHAR pszPath[16]; // [rsp+170h] [rbp-88h] BYREF
  WCHAR v62[16]; // [rsp+190h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD12,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v31);
    return 2147942487LL;
  }
  std::wstring::wstring(v54);
  if ( std::wstring::find_first_of(v54, 47, 0) != -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD18,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v31);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    return 2147942487LL;
  }
  std::wstring::wstring(pszPathOut, v55, 0);
  v4 = (WCHAR *)pszPathOut;
  if ( v52 > 7 )
    v4 = pszPathOut[0];
  if ( PathCchCanonicalizeEx(v4, (size_t)pszPathOut[2] + 1, a2, 1u) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD1F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v31);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    return 2147942487LL;
  }
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)pszPathOut);
  v5 = (const WCHAR *)pszPathOut;
  if ( v52 > 7 )
    v5 = pszPathOut[0];
  if ( GetFileAttributesW(v5) != -1 )
  {
    if ( (unsigned int)dword_18042D328 > 3 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803C8522);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD2E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      v31);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    return 2147942487LL;
  }
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
  {
    v8 = pszPathOut;
    if ( v52 > 7 )
      v8 = (PWSTR *)pszPathOut[0];
    *(_QWORD *)v39 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_18042D328,
      (unsigned int)&unk_1803C856C,
      v6,
      v7,
      (__int64)v39);
  }
  v37 = pszPathOut;
  v38 = 1;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF60, 0, 0) )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xD45,
           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
           (const char *)0x15,
           v31);
    v38 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
LABEL_38:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    return v9;
  }
  TraceManager = Microsoft::Diagnostics::LifetimeManager::GetTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  *(_QWORD *)&v53[0] = *((_QWORD *)TraceManager + 2);
  *((_QWORD *)&v53[0] + 1) = (char *)TraceManager + 272;
  OwnerScenarioId = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerScenarioId(
                      (Microsoft::Diagnostics::TraceSlotSafeWrapper *)v53,
                      &v40);
  if ( memcmp_0(OwnerScenarioId, &Microsoft::Diagnostics::UtcApiManager::k_customTraceId, 0x10u) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD4D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C5100DLL,
      v31);
    v38 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    return 2277838861LL;
  }
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)&Src);
  UtcTemporaryPath = Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(v62);
  v42 = *(_OWORD *)std::wstring::operator std::wstring_view(UtcTemporaryPath, &v40);
  appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(&Src);
  v14 = Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  WORD1(v42) = 0;
  LOBYTE(v39[0]) = 1;
  *(_WORD *)((char *)v39 + 1) = BYTE1(v42);
  HIBYTE(v39[0]) = 0;
  v39[1] = 2097153;
  *(_QWORD *)&v39[2] = 0;
  v15 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v14, v39);
  Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  Microsoft::Diagnostics::WideStringStream::operator<<(v15);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v62);
  v46 = Src;
  v47 = v57;
  v48 = v58;
  v49 = v59;
  v50 = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  Src = 0;
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(&v46);
  v42 = *(_OWORD *)&off_1803602D0;
  *(_OWORD *)v39 = *(_OWORD *)std::wstring::operator std::wstring_view(&v46, &v40);
  v16 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v39, 0, &v42);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v16,
      v31);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&Src);
    v38 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
    goto LABEL_38;
  }
  *(_QWORD *)&v42 = &v46;
  BYTE8(v42) = 1;
  v43 = 0;
  v44 = 0;
  BYTE3(v43) = (unsigned int)Microsoft::Diagnostics::TraceSlotSafeWrapper::GetRunningWprTraceProfileType(v53) == 2;
  std::wstring::wstring(pszPath, &v46);
  *(_OWORD *)v39 = *(_OWORD *)&Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames;
  v17 = Microsoft::Diagnostics::Utils::String::AppendPath(pszPath);
  v9 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD67,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v17,
      v31);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    v42 = *(_OWORD *)std::wstring::operator std::wstring_view(&v46, &v40);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&Src);
    v38 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
    goto LABEL_38;
  }
  v18 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, &v40);
  *(_QWORD *)v39 = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash((Microsoft::Diagnostics::TraceSlotSafeWrapper *)v53);
  LOBYTE(v19) = 0;
  v53[0] = v18;
  v20 = Microsoft::Diagnostics::TraceManager::SnapSlotTrace(
          (_DWORD)TraceManager,
          v19,
          (unsigned int)&Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
          (unsigned int)&GUID_NULL,
          (__int64)v39,
          (__int64)v53,
          0,
          (__int64)&v43);
  v9 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v20,
      v32);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    v42 = *(_OWORD *)std::wstring::operator std::wstring_view(&v46, &v40);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&Src);
    v38 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
    goto LABEL_38;
  }
  LOWORD(v39[0]) = 1;
  v53[0] = *(_OWORD *)&off_180360160;
  v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(&v46, v45);
  v22 = Microsoft::Diagnostics::UtcApiManager::SnapAgentTraces(
          v21,
          (unsigned int)&v40,
          (unsigned int)v53,
          (unsigned int)&Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
          1,
          v39[0]);
  if ( v22 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xD72,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v22,
      v33);
  v41[0] = 0;
  std::wstring::wstring(v53);
  *(_QWORD *)v39 = 0;
  RpcImpersonationToken = Microsoft::Diagnostics::ApiServer::GetRpcImpersonationToken(v23, v39, v53);
  v9 = RpcImpersonationToken;
  if ( RpcImpersonationToken < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD79,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)RpcImpersonationToken,
      v33);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v39);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v53);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v41);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(&v46, v45);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&Src);
    v38 = 0;
    Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
    goto LABEL_38;
  }
  Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(v53, v45);
  if ( (unsigned __int8)Microsoft::Diagnostics::UserManager::IsSidALoggedInUser(v25, &v40) )
  {
    Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(v53, v45);
    UserContextForSid = Microsoft::Diagnostics::UserManager::GetUserContextForSid(v26);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v41,
      0);
    UserToken = UMgrQueryUserToken(UserContextForSid, v41);
    v9 = UserToken;
    if ( UserToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD7E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)UserToken,
        v33);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v39);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v53);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v41);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
      v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(&v46, v45);
      Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v46);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&Src);
      v38 = 0;
      Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
      goto LABEL_38;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v39);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v53);
  LOWORD(v36) = 0;
  v35 = 0;
  v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(pszPathOut, v45);
  v53[0] = *(_OWORD *)std::wstring::operator std::wstring_view(&v46, v62);
  v29 = Microsoft::Diagnostics::EscalationWorkItem::CopyDiagnosticDirectory(
          (unsigned int)v53,
          (unsigned int)&v40,
          (unsigned int)v41,
          (unsigned int)&v36 + 1,
          (__int64)&v36,
          (__int64)&v35);
  v30 = v29;
  if ( v29 >= 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v41);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(&v46, v62);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&Src);
    if ( v38 )
    {
      v38 = 0;
      Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v29,
      v34);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v41);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    v40 = *(struct _GUID *)std::wstring::operator std::wstring_view(&v46, v62);
    Microsoft::Diagnostics::Utils::FileSystem::RecursivelyDeleteDirectory();
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&Src);
    if ( v38 )
    {
      v38 = 0;
      Microsoft::Diagnostics::UtcApiManager::SnapCustomTrace_::_3_::_lambda_1_::operator()(&v37);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    return v30;
  }
}

```

## disassembly

```asm
0x1801e0f90  mov     rax, rsp
0x1801e0f93  push    rbx
0x1801e0f94  push    rsi
0x1801e0f95  push    rdi
0x1801e0f96  push    r14
0x1801e0f98  sub     rsp, 1D8h
0x1801e0f9f  movaps  xmmword ptr [rax-38h], xmm6
0x1801e0fa3  mov     rax, cs:__security_cookie
0x1801e0faa  xor     rax, rsp
0x1801e0fad  mov     [rsp+1F8h+var_48], rax
0x1801e0fb5  mov     rbx, rdx
0x1801e0fb8  xor     esi, esi
0x1801e0fba  test    rdx, rdx
0x1801e0fbd  jnz     short loc_1801E0FE7
0x1801e0fbf  mov     rcx, [rsp+1F8h]; this
0x1801e0fc7  mov     ebx, 80070057h
0x1801e0fcc  mov     r9d, ebx; char *
0x1801e0fcf  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e0fd6  mov     edx, 0D12h; void *
0x1801e0fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e0fe0  mov     eax, ebx
0x1801e0fe2  jmp     loc_1801E1C62
0x1801e0fe7  lea     rcx, [rsp+1F8h+var_D8]
0x1801e0fef  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801e0ff4  nop
0x1801e0ff5  mov     edx, 2Fh ; '/'
0x1801e0ffa  xor     r8d, r8d
0x1801e0ffd  lea     rcx, [rsp+1F8h+var_D8]
0x1801e1005  call    ?find_first_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_first_of(wchar_t,unsigned __int64)
0x1801e100a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801e100e  jz      short loc_1801E1046
0x1801e1010  mov     rcx, [rsp+1F8h]; this
0x1801e1018  mov     ebx, 80070057h
0x1801e101d  mov     r9d, ebx; char *
0x1801e1020  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e1027  mov     edx, 0D18h; void *
0x1801e102c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e1031  nop
0x1801e1032  lea     rcx, [rsp+1F8h+var_D8]; this
0x1801e103a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e103f  mov     eax, ebx
0x1801e1041  jmp     loc_1801E1C62
0x1801e1046  xor     r8d, r8d
0x1801e1049  mov     rdx, [rsp+1F8h+var_C8]
0x1801e1051  lea     rcx, [rsp+1F8h+pszPathOut]
0x1801e1059  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801e105e  nop
0x1801e105f  mov     rdx, [rsp+1F8h+var_108]
0x1801e1067  lea     rcx, [rsp+1F8h+pszPathOut]
0x1801e106f  cmp     [rsp+1F8h+var_100], 7
0x1801e1078  cmova   rcx, [rsp+1F8h+pszPathOut]; pszPathOut
0x1801e1081  inc     rdx; cchPathOut
0x1801e1084  mov     r14d, 1
0x1801e108a  mov     r9d, r14d; dwFlags
0x1801e108d  mov     r8, rbx; pszPathIn
0x1801e1090  call    cs:__imp_PathCchCanonicalizeEx
0x1801e1097  nop     dword ptr [rax+rax+00h]
0x1801e109c  test    eax, eax
0x1801e109e  jns     short loc_1801E10E4
0x1801e10a0  mov     rcx, [rsp+1F8h]; this
0x1801e10a8  mov     ebx, 80070057h
0x1801e10ad  mov     r9d, ebx; char *
0x1801e10b0  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e10b7  mov     edx, 0D1Fh; void *
0x1801e10bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e10c1  nop
0x1801e10c2  lea     rcx, [rsp+1F8h+pszPathOut]; this
0x1801e10ca  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e10cf  nop
0x1801e10d0  lea     rcx, [rsp+1F8h+var_D8]; this
0x1801e10d8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e10dd  mov     eax, ebx
0x1801e10df  jmp     loc_1801E1C62
0x1801e10e4  xor     r8d, r8d
0x1801e10e7  mov     dl, r14b
0x1801e10ea  lea     rcx, [rsp+1F8h+pszPathOut]; lpSrc
0x1801e10f2  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801e10f7  lea     rcx, [rsp+1F8h+pszPathOut]
0x1801e10ff  cmp     [rsp+1F8h+var_100], 7
0x1801e1108  cmova   rcx, [rsp+1F8h+pszPathOut]; lpFileName
0x1801e1111  call    cs:__imp_GetFileAttributesW
0x1801e1118  nop     dword ptr [rax+rax+00h]
0x1801e111d  cmp     eax, 0FFFFFFFFh
0x1801e1120  mov     eax, cs:dword_18042D328
0x1801e1126  jz      short loc_1801E1199
0x1801e1128  cmp     eax, 3
0x1801e112b  jbe     short loc_1801E1155
0x1801e112d  mov     edx, 2000h
0x1801e1132  lea     rcx, dword_18042D328
0x1801e1139  call    _tlgKeywordOn
0x1801e113e  test    al, al
0x1801e1140  jz      short loc_1801E1155
0x1801e1142  lea     rdx, unk_1803C8522
0x1801e1149  lea     rcx, dword_18042D328
0x1801e1150  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1801e1155  mov     rcx, [rsp+1F8h]; this
0x1801e115d  mov     ebx, 80070057h
0x1801e1162  mov     r9d, ebx; char *
0x1801e1165  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e116c  mov     edx, 0D2Eh; void *
0x1801e1171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e1176  nop
0x1801e1177  lea     rcx, [rsp+1F8h+pszPathOut]; this
0x1801e117f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1184  nop
0x1801e1185  lea     rcx, [rsp+1F8h+var_D8]; this
0x1801e118d  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1192  mov     eax, ebx
0x1801e1194  jmp     loc_1801E1C62
0x1801e1199  cmp     eax, 4
0x1801e119c  jbe     short loc_1801E11EF
0x1801e119e  mov     edx, 2000h
0x1801e11a3  lea     rcx, dword_18042D328
0x1801e11aa  call    _tlgKeywordOn
0x1801e11af  test    al, al
0x1801e11b1  jz      short loc_1801E11EF
0x1801e11b3  lea     rax, [rsp+1F8h+pszPathOut]
0x1801e11bb  cmp     [rsp+1F8h+var_100], 7
0x1801e11c4  cmova   rax, [rsp+1F8h+pszPathOut]
0x1801e11cd  mov     qword ptr [rsp+1F8h+var_198], rax
0x1801e11d2  lea     rax, [rsp+1F8h+var_198]
0x1801e11d7  mov     qword ptr [rsp+1F8h+var_1D8], rax; int
0x1801e11dc  lea     rdx, unk_1803C856C
0x1801e11e3  lea     rcx, dword_18042D328
0x1801e11ea  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1801e11ef  lea     rax, [rsp+1F8h+pszPathOut]
0x1801e11f7  mov     [rsp+1F8h+var_1B0], rax
0x1801e11fc  mov     [rsp+1F8h+var_1A8], r14b
0x1801e1201  mov     rcx, rsi
0x1801e1204  xor     eax, eax
0x1801e1206  lock cmpxchg qword ptr cs:xmmword_18043BF60, rcx
0x1801e120f  jnz     short loc_1801E126B
0x1801e1211  mov     rcx, [rsp+1F8h]; this
0x1801e1219  mov     r9d, 15h; char *
0x1801e121f  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e1226  mov     edx, 0D45h; void *
0x1801e122b  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e1230  mov     ebx, eax
0x1801e1232  cmp     [rsp+1F8h+var_1A8], sil
0x1801e1237  jz      short loc_1801E1249
0x1801e1239  mov     [rsp+1F8h+var_1A8], sil
0x1801e123e  lea     rcx, [rsp+1F8h+var_1B0]
0x1801e1243  call    _Microsoft__Diagnostics__UtcApiManager__SnapCustomTrace____3____lambda_1___operator__
0x1801e1248  nop
0x1801e1249  lea     rcx, [rsp+1F8h+pszPathOut]; this
0x1801e1251  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1256  nop
0x1801e1257  lea     rcx, [rsp+1F8h+var_D8]; this
0x1801e125f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1264  mov     eax, ebx
0x1801e1266  jmp     loc_1801E1C62
0x1801e126b  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801e1272  call    ?GetTraceManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTraceManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTraceManager(void)
0x1801e1277  mov     rdi, rax
0x1801e127a  mov     rcx, [rax+10h]
0x1801e127e  mov     qword ptr [rsp+1F8h+var_F8], rcx
0x1801e1286  lea     rcx, [rax+110h]
0x1801e128d  mov     qword ptr [rsp+1F8h+var_F8+8], rcx
0x1801e1295  lea     rdx, [rsp+1F8h+var_188]; retstr
0x1801e129a  lea     rcx, [rsp+1F8h+var_F8]; this
0x1801e12a2  call    ?GetOwnerScenarioId@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA?AU_GUID@@XZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerScenarioId(void)
0x1801e12a7  mov     r8d, 10h; Size
0x1801e12ad  lea     rdx, ?k_customTraceId@UtcApiManager@Diagnostics@Microsoft@@2U_GUID@@B; Buf2
0x1801e12b4  mov     rcx, rax; Buf1
0x1801e12b7  call    memcmp_0
0x1801e12bc  test    eax, eax
0x1801e12be  jz      short loc_1801E131B
0x1801e12c0  mov     rcx, [rsp+1F8h]; this
0x1801e12c8  mov     ebx, 87C5100Dh
0x1801e12cd  mov     r9d, ebx; char *
0x1801e12d0  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e12d7  mov     edx, 0D4Dh; void *
0x1801e12dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e12e1  nop
0x1801e12e2  cmp     [rsp+1F8h+var_1A8], sil
0x1801e12e7  jz      short loc_1801E12F9
0x1801e12e9  mov     [rsp+1F8h+var_1A8], sil
0x1801e12ee  lea     rcx, [rsp+1F8h+var_1B0]
0x1801e12f3  call    _Microsoft__Diagnostics__UtcApiManager__SnapCustomTrace____3____lambda_1___operator__
0x1801e12f8  nop
0x1801e12f9  lea     rcx, [rsp+1F8h+pszPathOut]; this
0x1801e1301  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1306  nop
0x1801e1307  lea     rcx, [rsp+1F8h+var_D8]; this
0x1801e130f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1314  mov     eax, ebx
0x1801e1316  jmp     loc_1801E1C62
0x1801e131b  lea     rcx, [rsp+1F8h+Src]; this
0x1801e1323  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x1801e1328  nop
0x1801e1329  lea     rcx, [rsp+1F8h+var_68]; lpSrc
0x1801e1331  call    ?GetUtcTemporaryPath@FileSystem@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::FileSystem::GetUtcTemporaryPath(void)
0x1801e1336  nop
0x1801e1337  lea     rdx, [rsp+1F8h+var_188]
0x1801e133c  mov     rcx, rax
0x1801e133f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e1344  movups  xmm0, xmmword ptr [rax]
0x1801e1347  movdqu  [rsp+1F8h+var_168], xmm0
0x1801e1350  lea     rdx, [rsp+1F8h+var_168]
0x1801e1358  lea     rcx, [rsp+1F8h+Src]; Src
0x1801e1360  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801e1365  lea     rdx, aDiagtrackCusto; "DiagTrack_CustomTrace_"
0x1801e136c  mov     rcx, rax; Src
0x1801e136f  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e1374  mov     word ptr [rsp+1F8h+var_168+2], si
0x1801e137c  mov     byte ptr [rsp+1F8h+var_198], r14b
0x1801e1381  movzx   ecx, word ptr [rsp+1F8h+var_168+1]
0x1801e1389  mov     word ptr [rsp+1F8h+var_198+1], cx
0x1801e138e  mov     cl, byte ptr [rsp+1F8h+var_168+3]
0x1801e1395  mov     byte ptr [rsp+1F8h+var_198+3], cl
0x1801e1399  mov     [rsp+1F8h+var_198+4], 200001h
0x1801e13a1  mov     qword ptr [rsp+1F8h+var_198+8], rsi
0x1801e13a6  lea     rdx, [rsp+1F8h+var_198]
0x1801e13ab  mov     rcx, rax
0x1801e13ae  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@UStreamManipulator@12@@Z; Microsoft::Diagnostics::WideStringStream::operator<<(Microsoft::Diagnostics::StreamManipulator)
0x1801e13b3  mov     rbx, rax
0x1801e13b6  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x1801e13bb  mov     rdx, rax
0x1801e13be  mov     rcx, rbx; Src
0x1801e13c1  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@_K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(unsigned __int64)
0x1801e13c6  nop
0x1801e13c7  lea     rcx, [rsp+1F8h+var_68]; this
0x1801e13cf  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e13d4  movzx   eax, [rsp+1F8h+Src]
0x1801e13dc  mov     [rsp+1F8h+var_138], ax
0x1801e13e4  movsd   xmm0, [rsp+1F8h+var_B6]
0x1801e13ed  movsd   [rsp+1F8h+var_136], xmm0
0x1801e13f6  mov     eax, [rsp+1F8h+var_AE]
0x1801e13fd  mov     [rsp+1F8h+var_12E], eax
0x1801e1404  movzx   eax, [rsp+1F8h+var_AA]
0x1801e140c  mov     [rsp+1F8h+var_12A], ax
0x1801e1414  mov     rax, qword ptr [rsp+1F8h+var_A8]
0x1801e141c  mov     qword ptr [rsp+1F8h+var_128], rax
0x1801e1424  mov     rax, qword ptr [rsp+1F8h+var_A8+8]
0x1801e142c  mov     qword ptr [rsp+1F8h+var_128+8], rax
0x1801e1434  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1801e143c  movdqu  [rsp+1F8h+var_A8], xmm0
0x1801e1445  mov     [rsp+1F8h+Src], si
0x1801e144d  xor     r8d, r8d
0x1801e1450  mov     dl, r14b
0x1801e1453  lea     rcx, [rsp+1F8h+var_138]; lpSrc
0x1801e145b  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801e1460  movups  xmm0, xmmword ptr cs:off_1803602D0; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x1801e1467  movdqu  [rsp+1F8h+var_168], xmm0
0x1801e1470  lea     rdx, [rsp+1F8h+var_188]
0x1801e1475  lea     rcx, [rsp+1F8h+var_138]
0x1801e147d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e1482  movups  xmm0, xmmword ptr [rax]
0x1801e1485  movdqu  xmmword ptr [rsp+1F8h+var_198], xmm0
0x1801e148b  lea     r8, [rsp+1F8h+var_168]
0x1801e1493  xor     edx, edx
0x1801e1495  lea     rcx, [rsp+1F8h+var_198]
0x1801e149a  call    ?ExpandAndCreateDirectory@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N0@Z; Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(std::wstring_view,bool,std::wstring_view)
0x1801e149f  mov     ebx, eax
0x1801e14a1  test    eax, eax
0x1801e14a3  jns     short loc_1801E1517
0x1801e14a5  mov     rcx, [rsp+1F8h]; this
0x1801e14ad  mov     r9d, eax; char *
0x1801e14b0  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e14b7  mov     edx, 0D5Bh; void *
0x1801e14bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e14c1  nop
0x1801e14c2  lea     rcx, [rsp+1F8h+var_138]; this
0x1801e14ca  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e14cf  nop
0x1801e14d0  lea     rcx, [rsp+1F8h+Src]; this
0x1801e14d8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e14dd  nop
0x1801e14de  cmp     [rsp+1F8h+var_1A8], sil
0x1801e14e3  jz      short loc_1801E14F5
0x1801e14e5  mov     [rsp+1F8h+var_1A8], sil
0x1801e14ea  lea     rcx, [rsp+1F8h+var_1B0]
0x1801e14ef  call    _Microsoft__Diagnostics__UtcApiManager__SnapCustomTrace____3____lambda_1___operator__
0x1801e14f4  nop
0x1801e14f5  lea     rcx, [rsp+1F8h+pszPathOut]; this
0x1801e14fd  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1502  nop
0x1801e1503  lea     rcx, [rsp+1F8h+var_D8]; this
0x1801e150b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e1510  mov     eax, ebx
0x1801e1512  jmp     loc_1801E1C62
0x1801e1517  lea     rax, [rsp+1F8h+var_138]
0x1801e151f  mov     qword ptr [rsp+1F8h+var_168], rax
0x1801e1527  mov     byte ptr [rsp+1F8h+var_168+8], r14b
0x1801e152f  mov     [rsp+1F8h+var_158], rsi
0x1801e1537  mov     [rsp+1F8h+var_150], sil
0x1801e153f  lea     rcx, [rsp+1F8h+var_F8]
0x1801e1547  call    ?GetRunningWprTraceProfileType@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA?AW4__MIDL_IProfile_0001@@XZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetRunningWprTraceProfileType(void)
0x1801e154c  cmp     eax, 2
0x1801e154f  setz    byte ptr [rsp+1F8h+var_158+3]
0x1801e1557  lea     rdx, [rsp+1F8h+var_138]
0x1801e155f  lea     rcx, [rsp+1F8h+pszPath]
0x1801e1567  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801e156c  nop
0x1801e156d  movaps  xmm0, xmmword ptr cs:?k_traceSlotOutputNames@TraceSlot@Diagnostics@Microsoft@@2QBV?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const near * const Microsoft::Diagnostics::TraceSlot::k_traceSlotOutputNames
0x1801e1574  movdqu  xmmword ptr [rsp+1F8h+var_198], xmm0
0x1801e157a  lea     rdx, [rsp+1F8h+var_198]
0x1801e157f  lea     rcx, [rsp+1F8h+pszPath]; pszPath
0x1801e1587  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1801e158c  mov     ebx, eax
  ... truncated ...
```
