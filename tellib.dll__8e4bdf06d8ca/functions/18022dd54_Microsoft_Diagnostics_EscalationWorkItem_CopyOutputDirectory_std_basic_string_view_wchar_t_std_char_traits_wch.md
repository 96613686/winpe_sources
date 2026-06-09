# Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,bool,unsigned __int64)

- ea: `0x18022dd54`
- end: `0x18022e8b2`
- name: `?CopyOutputDirectory@EscalationWorkItem@Diagnostics@Microsoft@@AEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_N_K@Z`
- size: `2910`
- prototype: ``
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a9910`
- `0x1802313cc`
- `0x1802340c4`

## callees

- `0x180001bf4`
- `0x180001d28`
- `0x180002058`
- `0x18000b0a0`
- `0x18001d0ec`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x1800333b0`
- `0x180034d94`
- `0x180035698`
- `0x18003fe04`
- `0x180040454`
- `0x180048ff4`
- `0x1800498f0`
- `0x180053a4c`
- `0x18005d050`
- `0x18006e7e4`
- `0x180089d90`
- `0x18009d3ec`
- `0x1800a662c`
- `0x1800aac70`
- `0x1800ac770`
- `0x1800ae150`
- `0x1800af524`
- `0x1800b1a08`
- `0x1800bc300`
- `0x18012de40`
- `0x1801bfc30`
- `0x1801c039c`
- `0x18022bd8c`
- `0x18022ca48`
- `0x18022dd54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022e45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18022e45b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18022e098`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18022e098`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18022e597`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18022e597`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18022e562`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x18022e562`

## string_xrefs

- `0x18022e2ba`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18022e3ba`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18022e5bc`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18022e760`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18022de3d`: `CopyOutputDirectory_0`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory(
        __int64 a1,
        __m128i *a2,
        char a3,
        __int64 a4)
{
  __int64 v4; // rbx
  _QWORD *v9; // rax
  int v10; // r8d
  int v11; // r9d
  LPCWSTR *v12; // rax
  const WCHAR *v13; // rcx
  __int64 last_of; // rax
  unsigned int v15; // ebx
  int v16; // eax
  unsigned int v17; // r14d
  __int64 v18; // r8
  Microsoft::Diagnostics::UserManager *v19; // r8
  __int64 UserContextForSid; // rdi
  CONTEXT *v21; // rbx
  __int64 v22; // r8
  int UserToken; // eax
  unsigned int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // r8d
  int v28; // r9d
  int v29; // eax
  unsigned int v30; // ebx
  int v31; // [rsp+20h] [rbp-678h]
  int v32; // [rsp+20h] [rbp-678h]
  char v33; // [rsp+30h] [rbp-668h] BYREF
  char v34; // [rsp+31h] [rbp-667h] BYREF
  char v35; // [rsp+32h] [rbp-666h] BYREF
  char v36; // [rsp+33h] [rbp-665h] BYREF
  char v37; // [rsp+34h] [rbp-664h] BYREF
  __int16 v38; // [rsp+35h] [rbp-663h] BYREF
  int v39; // [rsp+38h] [rbp-660h] BYREF
  _BYTE v40[4]; // [rsp+3Ch] [rbp-65Ch] BYREF
  __m128i v41; // [rsp+40h] [rbp-658h] BYREF
  int v42[4]; // [rsp+50h] [rbp-648h] BYREF
  _QWORD v43[2]; // [rsp+60h] [rbp-638h] BYREF
  char v44; // [rsp+70h] [rbp-628h]
  _QWORD v45[10]; // [rsp+80h] [rbp-618h] BYREF
  char v46; // [rsp+D0h] [rbp-5C8h]
  LPCWSTR lpFileName[3]; // [rsp+E0h] [rbp-5B8h] BYREF
  unsigned __int64 v48; // [rsp+F8h] [rbp-5A0h]
  _OWORD v49[2]; // [rsp+100h] [rbp-598h] BYREF
  _QWORD v50[4]; // [rsp+120h] [rbp-578h] BYREF
  _QWORD v51[4]; // [rsp+140h] [rbp-558h] BYREF
  _BYTE v52[32]; // [rsp+160h] [rbp-538h] BYREF
  _QWORD Src[4]; // [rsp+180h] [rbp-518h] BYREF
  _BYTE v54[32]; // [rsp+1A0h] [rbp-4F8h] BYREF
  _BYTE v55[1184]; // [rsp+1C0h] [rbp-4D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+698h] [rbp+0h]

  v4 = a4;
  v34 = 0;
  LOBYTE(a4) = *(_BYTE *)(a1 + 577);
  Microsoft::Diagnostics::EscalationWorkItemOverrides::GetCopyOutputDirectoryPath(
    *(_QWORD *)(a1 + 584),
    (unsigned int)lpFileName,
    *(_QWORD *)(a1 + 600),
    a4,
    (__int64)&v34);
  if ( !lpFileName[2] )
  {
    if ( (unsigned int)dword_18042D328 > 3 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803D0E8A);
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    return 0;
  }
  std::wstring::wstring(v54);
  v35 = 0;
  v33 = 1;
  v36 = 0;
  v38 = 0;
  v37 = 0;
  v39 = 0;
  *(_QWORD *)v42 = L"CopyOutputDirectory_0";
  *(_QWORD *)&v42[2] = 21;
  Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(
    (unsigned int)v55,
    (unsigned int)v42,
    0x1000000,
    0,
    0);
  v45[0] = lpFileName;
  v45[1] = v55;
  v45[2] = &v34;
  v45[3] = &v35;
  v45[4] = &v33;
  v45[5] = (char *)&v38 + 1;
  v45[6] = &v36;
  v45[7] = &v38;
  v45[8] = &v37;
  v45[9] = &v39;
  v46 = 1;
  std::wstring::wstring(v52);
  v43[0] = &v39;
  v43[1] = v52;
  v44 = 1;
  if ( a3 )
    std::wstring::_Append<wchar_t>(lpFileName);
  if ( *(_BYTE *)(*(_QWORD *)(a1 + 584) + 42LL) )
  {
    std::wstring::_Append<wchar_t>(lpFileName);
    std::to_wstring(v50, v4);
    std::wstring::_Append<wchar_t>(lpFileName);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v50);
  }
  v41 = *(__m128i *)std::wstring::operator std::wstring_view(lpFileName, v49);
  v9 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(*(_QWORD *)(a1 + 600), v50, &v41);
  std::wstring::operator=(lpFileName, v9);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v50);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
  {
    v12 = lpFileName;
    if ( v48 > 7 )
      v12 = (LPCWSTR *)lpFileName[0];
    *(_QWORD *)v42 = v12;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_18042D328,
      (unsigned int)&unk_1803D0E07,
      v10,
      v11,
      (__int64)v42);
  }
  v13 = (const WCHAR *)lpFileName;
  if ( v48 > 7 )
    v13 = lpFileName[0];
  if ( GetFileAttributesW(v13) != -1 )
  {
    if ( (unsigned int)dword_18042D328 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803D0E47);
    v35 = 1;
    v44 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v43);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v52);
    v46 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v45);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v55);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    return 0;
  }
  v39 = -2147467259;
  std::wstring::wstring((__int64)Src, &off_1803612A0);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src, 1, 0);
  std::wstring::wstring((__int64)v51, &off_180361290);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v51, 1, 0);
  v41 = *(__m128i *)std::wstring::operator std::wstring_view(Src, v49);
  *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v50);
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(v42, &v41)
    || (v41 = *(__m128i *)std::wstring::operator std::wstring_view(v51, v50),
        *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v49),
        (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(v42, &v41)) )
  {
    v33 = 0;
  }
  v41 = *(__m128i *)std::wstring::operator std::wstring_view(v51, v50);
  *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v49);
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::String::IStartsWith(v42, &v41) )
  {
    last_of = std::wstring::find_last_of(lpFileName, 92);
    if ( last_of == -1 )
    {
      v15 = v39;
      if ( v39 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x528,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
          (const char *)(unsigned int)v39,
          v31);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v51);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      v44 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v43);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v52);
      v46 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v45);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v55);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return v15;
    }
    std::wstring::substr(lpFileName, v49, 0, last_of);
    v41 = *(__m128i *)&off_180348AF8;
    *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(v49, v50);
    v16 = Microsoft::Diagnostics::Utils::FileSystem::ExpandAndCreateDirectory(v42, 0, &v41);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
        (const char *)(unsigned int)v16,
        v31);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v49);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v51);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      v44 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v43);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v52);
      v46 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v45);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v55);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return v17;
    }
    if ( GetLastError() != 183 )
      std::wstring::operator=(v52, v49);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v49);
  }
  *(_QWORD *)v42 = 0;
  std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v41);
  if ( v41.m128i_i64[1]
    && (Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager),
        std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v41),
        (unsigned __int8)Microsoft::Diagnostics::UserManager::IsSidALoggedInUser(v18, &v41))
    && v33 )
  {
    Microsoft::Diagnostics::LifetimeManager::GetUserManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v41);
    UserContextForSid = Microsoft::Diagnostics::UserManager::GetUserContextForSid(v19);
    v21 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
    RtlCaptureContext(v21);
    LOBYTE(v22) = 2;
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(&v41, 240000, v22, v21);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      v42,
      0);
    UserToken = UMgrQueryUserToken(UserContextForSid, v42);
    v24 = UserToken;
    v39 = UserToken;
    if ( UserToken < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x540,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
        (const char *)(unsigned int)UserToken,
        v31);
      Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&v41);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v42);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v51);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      v44 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v43);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v52);
      v46 = 0;
      Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v45);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v55);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return v24;
    }
    Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)&v41);
    v36 = 1;
  }
  else if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 4) )
  {
    v40[0] = v33;
    std::wstring::operator std::wstring_view(*(_QWORD *)(a1 + 600) + 104LL, &v41);
    std::wstring::operator std::wstring_view(v25, v49);
    v26 = _tlgWrapBinary<wchar_t,2>(v50, *(_QWORD *)&v49[0], v41.m128i_u32[2]);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperByVal<1>>(
      (unsigned int)v40,
      (unsigned int)&unk_1803D0DA0,
      v27,
      v28,
      v26,
      (__int64)v40);
  }
  v49[0] = *(_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v50);
  v41 = *a2;
  v29 = Microsoft::Diagnostics::EscalationWorkItem::CopyDiagnosticDirectory(
          (__int128 *)v41.m128i_i8,
          v49,
          (void **)v42,
          (_BYTE *)&v38 + 1,
          &v38,
          &v37);
  v30 = v29;
  v39 = v29;
  if ( v29 >= 0 )
  {
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v42);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v51);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    v44 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v43);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v52);
    v46 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v45);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v55);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x555,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
      (const char *)(unsigned int)v29,
      v32);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v42);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v51);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    v44 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_2_::operator()(v43);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v52);
    v46 = 0;
    Microsoft::Diagnostics::EscalationWorkItem::CopyOutputDirectory_::_3_::_lambda_1_::operator()(v45);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v55);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v54);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    return v30;
  }
}

```

## disassembly

```asm
0x18022dd54  mov     [rsp+arg_10], rbx
0x18022dd59  push    rsi
0x18022dd5a  push    rdi
0x18022dd5b  push    r12
0x18022dd5d  push    r14
0x18022dd5f  push    r15
0x18022dd61  sub     rsp, 670h
0x18022dd68  mov     rax, cs:__security_cookie
0x18022dd6f  xor     rax, rsp
0x18022dd72  mov     [rsp+698h+var_38], rax
0x18022dd7a  mov     rbx, r9
0x18022dd7d  mov     dil, r8b
0x18022dd80  mov     r15, rdx
0x18022dd83  mov     rsi, rcx
0x18022dd86  xor     r12d, r12d
0x18022dd89  mov     [rsp+698h+var_667], r12b
0x18022dd8e  lea     rax, [rsp+698h+var_667]
0x18022dd93  mov     qword ptr [rsp+698h+var_678], rax
0x18022dd98  mov     r9b, [rcx+241h]
0x18022dd9f  mov     r8, [rcx+258h]
0x18022dda6  lea     rdx, [rsp+698h+lpFileName]
0x18022ddae  mov     rcx, [rcx+248h]
0x18022ddb5  call    ?GetCopyOutputDirectoryPath@EscalationWorkItemOverrides@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVScenarioInst@23@VReservedStateOrdinal@23@AEAVCopyOutputDirectorySource@EnumDetails@23@@Z; Microsoft::Diagnostics::EscalationWorkItemOverrides::GetCopyOutputDirectoryPath(Microsoft::Diagnostics::ScenarioInst const &,Microsoft::Diagnostics::ReservedStateOrdinal,Microsoft::Diagnostics::EnumDetails::CopyOutputDirectorySource &)
0x18022ddba  nop
0x18022ddbb  cmp     [rsp+698h+var_5A8], r12
0x18022ddc3  jnz     short loc_18022DE0C
0x18022ddc5  mov     eax, cs:dword_18042D328
0x18022ddcb  cmp     eax, 3
0x18022ddce  jbe     short loc_18022DDF8
0x18022ddd0  lea     edx, [r12+4]
0x18022ddd5  lea     rbx, dword_18042D328
0x18022dddc  mov     rcx, rbx
0x18022dddf  call    _tlgKeywordOn
0x18022dde4  test    al, al
0x18022dde6  jz      short loc_18022DDF8
0x18022dde8  lea     rdx, unk_1803D0E8A
0x18022ddef  mov     rcx, rbx
0x18022ddf2  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18022ddf7  nop
0x18022ddf8  lea     rcx, [rsp+698h+lpFileName]; this
0x18022de00  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022de05  xor     eax, eax
0x18022de07  jmp     loc_18022E889
0x18022de0c  lea     rcx, [rsp+698h+var_4F8]; void *
0x18022de14  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18022de19  nop
0x18022de1a  mov     [rsp+698h+var_666], r12b
0x18022de1f  mov     [rsp+698h+var_668], 1
0x18022de24  mov     byte ptr [rsp+698h+var_663+1], r12b
0x18022de29  mov     [rsp+698h+var_665], r12b
0x18022de2e  mov     byte ptr [rsp+698h+var_663], r12b
0x18022de33  mov     [rsp+698h+var_664], r12b
0x18022de38  mov     dword ptr [rsp+698h+var_663+3], r12d
0x18022de3d  lea     rdx, aCopyoutputdire; "CopyOutputDirectory_0"
0x18022de44  mov     qword ptr [rsp+698h+var_648], rdx
0x18022de49  mov     qword ptr [rsp+698h+var_648+8], 15h
0x18022de52  mov     r8d, 1000000h
0x18022de58  mov     byte ptr [rsp+698h+var_670], r12b
0x18022de5d  mov     byte ptr [rsp+698h+var_678], r12b
0x18022de62  mov     r9, 800000000000h
0x18022de6c  lea     rdx, [rsp+698h+var_648]
0x18022de71  lea     rcx, [rsp+698h+var_4D8]
0x18022de79  call    ?MakeScenarioSyntheticEvent@AsimovSyntheticEvent@Diagnostics@Microsoft@@SA?AV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@23@VTriggerLatency@23@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::MakeScenarioSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency)
0x18022de7e  nop
0x18022de7f  lea     rax, [rsp+698h+lpFileName]
0x18022de87  mov     [rsp+698h+var_618], rax
0x18022de8f  lea     rax, [rsp+698h+var_4D8]
0x18022de97  mov     [rsp+698h+var_610], rax
0x18022de9f  lea     rax, [rsp+698h+var_667]
0x18022dea4  mov     [rsp+698h+var_608], rax
0x18022deac  lea     rax, [rsp+698h+var_666]
0x18022deb1  mov     [rsp+698h+var_600], rax
0x18022deb9  lea     rax, [rsp+698h+var_668]
0x18022debe  mov     [rsp+698h+var_5F8], rax
0x18022dec6  lea     rax, [rsp+698h+var_663+1]
0x18022decb  mov     [rsp+698h+var_5F0], rax
0x18022ded3  lea     rax, [rsp+698h+var_665]
0x18022ded8  mov     [rsp+698h+var_5E8], rax
0x18022dee0  lea     rax, [rsp+698h+var_663]
0x18022dee5  mov     [rsp+698h+var_5E0], rax
0x18022deed  lea     rax, [rsp+698h+var_664]
0x18022def2  mov     [rsp+698h+var_5D8], rax
0x18022defa  lea     rax, [rsp+698h+var_663+3]
0x18022deff  mov     [rsp+698h+var_5D0], rax
0x18022df07  mov     [rsp+698h+var_5C8], 1
0x18022df0f  lea     rcx, [rsp+698h+var_538]; void *
0x18022df17  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18022df1c  nop
0x18022df1d  lea     rax, [rsp+698h+var_663+3]
0x18022df22  mov     [rsp+698h+var_638], rax
0x18022df27  lea     rax, [rsp+698h+var_538]
0x18022df2f  mov     [rsp+698h+var_630], rax
0x18022df34  mov     [rsp+698h+var_628], 1
0x18022df39  test    dil, dil
0x18022df3c  jz      short loc_18022DF58
0x18022df3e  mov     r8d, 0Eh
0x18022df44  lea     rdx, aSelfdiagnosis_0; "_selfdiagnosis"
0x18022df4b  lea     rcx, [rsp+698h+lpFileName]; Src
0x18022df53  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18022df58  mov     rax, [rsi+248h]
0x18022df5f  cmp     [rax+2Ah], r12b
0x18022df63  jz      short loc_18022DFBC
0x18022df65  mov     r8d, 1
0x18022df6b  lea     rdx, asc_180372B38; "_"
0x18022df72  lea     rcx, [rsp+698h+lpFileName]; Src
0x18022df7a  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18022df7f  mov     rdx, rbx
0x18022df82  lea     rcx, [rsp+698h+var_578]
0x18022df8a  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::to_wstring(unsigned __int64)
0x18022df8f  nop
0x18022df90  mov     r8, [rax+10h]
0x18022df94  cmp     qword ptr [rax+18h], 7
0x18022df99  jbe     short loc_18022DF9E
0x18022df9b  mov     rax, [rax]
0x18022df9e  mov     rdx, rax
0x18022dfa1  lea     rcx, [rsp+698h+lpFileName]; Src
0x18022dfa9  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18022dfae  nop
0x18022dfaf  lea     rcx, [rsp+698h+var_578]; this
0x18022dfb7  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022dfbc  lea     rdx, [rsp+698h+var_598]
0x18022dfc4  lea     rcx, [rsp+698h+lpFileName]
0x18022dfcc  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18022dfd1  movups  xmm0, xmmword ptr [rax]
0x18022dfd4  movdqu  [rsp+698h+var_658], xmm0
0x18022dfda  lea     r8, [rsp+698h+var_658]
0x18022dfdf  lea     rdx, [rsp+698h+var_578]
0x18022dfe7  mov     rcx, [rsi+258h]
0x18022dfee  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x18022dff3  mov     rdx, rax
0x18022dff6  lea     rcx, [rsp+698h+lpFileName]
0x18022dffe  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18022e003  lea     rcx, [rsp+698h+var_578]; this
0x18022e00b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e010  xor     r8d, r8d
0x18022e013  mov     dl, 1
0x18022e015  lea     rcx, [rsp+698h+lpFileName]; lpSrc
0x18022e01d  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18022e022  mov     eax, cs:dword_18042D328
0x18022e028  mov     edi, 4
0x18022e02d  lea     rbx, dword_18042D328
0x18022e034  cmp     eax, edi
0x18022e036  jbe     short loc_18022E07E
0x18022e038  mov     edx, edi
0x18022e03a  mov     rcx, rbx
0x18022e03d  call    _tlgKeywordOn
0x18022e042  test    al, al
0x18022e044  jz      short loc_18022E07E
0x18022e046  lea     rax, [rsp+698h+lpFileName]
0x18022e04e  cmp     [rsp+698h+var_5A0], 7
0x18022e057  cmova   rax, [rsp+698h+lpFileName]
0x18022e060  mov     qword ptr [rsp+698h+var_648], rax
0x18022e065  lea     rax, [rsp+698h+var_648]
0x18022e06a  mov     qword ptr [rsp+698h+var_678], rax; int
0x18022e06f  lea     rdx, unk_1803D0E07
0x18022e076  mov     rcx, rbx
0x18022e079  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x18022e07e  lea     rcx, [rsp+698h+lpFileName]
0x18022e086  cmp     [rsp+698h+var_5A0], 7
0x18022e08f  cmova   rcx, [rsp+698h+lpFileName]; lpFileName
0x18022e098  call    cs:__imp_GetFileAttributesW
0x18022e09f  nop     dword ptr [rax+rax+00h]
0x18022e0a4  cmp     eax, 0FFFFFFFFh
0x18022e0a7  jz      loc_18022E13F
0x18022e0ad  mov     eax, cs:dword_18042D328
0x18022e0b3  cmp     eax, 3
0x18022e0b6  jbe     short loc_18022E0D6
0x18022e0b8  mov     rdx, rdi
0x18022e0bb  mov     rcx, rbx
0x18022e0be  call    _tlgKeywordOn
0x18022e0c3  test    al, al
0x18022e0c5  jz      short loc_18022E0D6
0x18022e0c7  lea     rdx, unk_1803D0E47
0x18022e0ce  mov     rcx, rbx
0x18022e0d1  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18022e0d6  mov     [rsp+698h+var_666], 1
0x18022e0db  mov     [rsp+698h+var_628], r12b
0x18022e0e0  lea     rcx, [rsp+698h+var_638]
0x18022e0e5  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_2___operator__
0x18022e0ea  nop
0x18022e0eb  lea     rcx, [rsp+698h+var_538]; this
0x18022e0f3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e0f8  nop
0x18022e0f9  mov     [rsp+698h+var_5C8], r12b
0x18022e101  lea     rcx, [rsp+698h+var_618]
0x18022e109  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_1___operator__
0x18022e10e  nop
0x18022e10f  lea     rcx, [rsp+698h+var_4D8]; this
0x18022e117  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18022e11c  nop
0x18022e11d  lea     rcx, [rsp+698h+var_4F8]; this
0x18022e125  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e12a  nop
0x18022e12b  lea     rcx, [rsp+698h+lpFileName]; this
0x18022e133  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e138  xor     eax, eax
0x18022e13a  jmp     loc_18022E889
0x18022e13f  mov     dword ptr [rsp+698h+var_663+3], 80004005h
0x18022e147  lea     rdx, off_1803612A0; "%DiagtrackStorageRoot%\\FeedbackHub"
0x18022e14e  lea     rcx, [rsp+698h+Src]
0x18022e156  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18022e15b  nop
0x18022e15c  xor     r8d, r8d
0x18022e15f  mov     dl, 1
0x18022e161  lea     rcx, [rsp+698h+Src]; lpSrc
0x18022e169  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18022e16e  lea     rdx, off_180361290; "%DiagtrackStorageRoot%\\FeedbackArchive"
0x18022e175  lea     rcx, [rsp+698h+var_558]
0x18022e17d  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18022e182  nop
0x18022e183  xor     r8d, r8d
0x18022e186  mov     dl, 1
0x18022e188  lea     rcx, [rsp+698h+var_558]; lpSrc
0x18022e190  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18022e195  lea     rdx, [rsp+698h+var_598]
0x18022e19d  lea     rcx, [rsp+698h+Src]
0x18022e1a5  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18022e1aa  movups  xmm0, xmmword ptr [rax]
0x18022e1ad  movdqu  [rsp+698h+var_658], xmm0
0x18022e1b3  lea     rdx, [rsp+698h+var_578]
0x18022e1bb  lea     rcx, [rsp+698h+lpFileName]
0x18022e1c3  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18022e1c8  movups  xmm0, xmmword ptr [rax]
0x18022e1cb  movdqu  xmmword ptr [rsp+698h+var_648], xmm0
0x18022e1d1  lea     rdx, [rsp+698h+var_658]
0x18022e1d6  lea     rcx, [rsp+698h+var_648]
0x18022e1db  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x18022e1e0  test    al, al
0x18022e1e2  jnz     short loc_18022E233
0x18022e1e4  lea     rdx, [rsp+698h+var_578]
0x18022e1ec  lea     rcx, [rsp+698h+var_558]
0x18022e1f4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18022e1f9  movups  xmm0, xmmword ptr [rax]
0x18022e1fc  movdqu  [rsp+698h+var_658], xmm0
0x18022e202  lea     rdx, [rsp+698h+var_598]
0x18022e20a  lea     rcx, [rsp+698h+lpFileName]
0x18022e212  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18022e217  movups  xmm0, xmmword ptr [rax]
0x18022e21a  movdqu  xmmword ptr [rsp+698h+var_648], xmm0
0x18022e220  lea     rdx, [rsp+698h+var_658]
0x18022e225  lea     rcx, [rsp+698h+var_648]
0x18022e22a  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x18022e22f  test    al, al
0x18022e231  jz      short loc_18022E238
0x18022e233  mov     [rsp+698h+var_668], r12b
0x18022e238  lea     rdx, [rsp+698h+var_578]
0x18022e240  lea     rcx, [rsp+698h+var_558]
0x18022e248  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18022e24d  movups  xmm0, xmmword ptr [rax]
0x18022e250  movdqu  [rsp+698h+var_658], xmm0
0x18022e256  lea     rdx, [rsp+698h+var_598]
0x18022e25e  lea     rcx, [rsp+698h+lpFileName]
0x18022e266  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18022e26b  movups  xmm0, xmmword ptr [rax]
0x18022e26e  movdqu  xmmword ptr [rsp+698h+var_648], xmm0
0x18022e274  lea     rdx, [rsp+698h+var_658]
0x18022e279  lea     rcx, [rsp+698h+var_648]
0x18022e27e  call    ?IStartsWith@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::IStartsWith(std::wstring_view,std::wstring_view)
0x18022e283  test    al, al
0x18022e285  jz      loc_18022E491
0x18022e28b  mov     edx, 5Ch ; '\'
0x18022e290  lea     rcx, [rsp+698h+lpFileName]
0x18022e298  call    ?find_last_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_last_of(wchar_t,unsigned __int64)
0x18022e29d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18022e2a1  jnz     loc_18022E34C
0x18022e2a7  mov     ebx, dword ptr [rsp+698h+var_663+3]
0x18022e2ab  test    ebx, ebx
0x18022e2ad  jns     short loc_18022E2CC
0x18022e2af  mov     rcx, [rsp+698h]; this
0x18022e2b7  mov     r9d, ebx; char *
0x18022e2ba  lea     r8, aOnecoreBaseTel_136; "onecore\\base\\telemetry\\utc\\service"...
0x18022e2c1  mov     edx, 528h; void *
0x18022e2c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18022e2cb  nop
0x18022e2cc  lea     rcx, [rsp+698h+var_558]; this
0x18022e2d4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e2d9  nop
0x18022e2da  lea     rcx, [rsp+698h+Src]; this
0x18022e2e2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e2e7  nop
0x18022e2e8  mov     [rsp+698h+var_628], r12b
0x18022e2ed  lea     rcx, [rsp+698h+var_638]
0x18022e2f2  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_2___operator__
0x18022e2f7  nop
0x18022e2f8  lea     rcx, [rsp+698h+var_538]; this
0x18022e300  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e305  nop
0x18022e306  mov     [rsp+698h+var_5C8], r12b
0x18022e30e  lea     rcx, [rsp+698h+var_618]
0x18022e316  call    _Microsoft__Diagnostics__EscalationWorkItem__CopyOutputDirectory____3____lambda_1___operator__
0x18022e31b  nop
0x18022e31c  lea     rcx, [rsp+698h+var_4D8]; this
0x18022e324  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18022e329  nop
0x18022e32a  lea     rcx, [rsp+698h+var_4F8]; this
0x18022e332  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e337  nop
0x18022e338  lea     rcx, [rsp+698h+lpFileName]; this
0x18022e340  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18022e345  mov     eax, ebx
  ... truncated ...
```
