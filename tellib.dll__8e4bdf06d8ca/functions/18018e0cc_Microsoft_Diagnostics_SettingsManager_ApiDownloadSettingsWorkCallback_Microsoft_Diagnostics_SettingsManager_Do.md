# Microsoft::Diagnostics::SettingsManager::ApiDownloadSettingsWorkCallback(Microsoft::Diagnostics::SettingsManager::DownloadLatestSettingsData &)

- ea: `0x18018e0cc`
- end: `0x18018ea29`
- name: `?ApiDownloadSettingsWorkCallback@SettingsManager@Diagnostics@Microsoft@@AEAAXAEAUDownloadLatestSettingsData@123@@Z`
- size: `2397`
- prototype: `void __fastcall(Microsoft::Diagnostics::SettingsManager *__hidden this, struct Microsoft::Diagnostics::SettingsManager::DownloadLatestSettingsData *)`
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801e4470`

## callees

- `0x180001bf4`
- `0x180001d28`
- `0x1800021e4`
- `0x1800035ec`
- `0x180004b04`
- `0x18001d160`
- `0x18001d200`
- `0x18001e638`
- `0x18001ee94`
- `0x180020fbc`
- `0x180027be0`
- `0x180048ff4`
- `0x18004ab70`
- `0x1800551b0`
- `0x1800552e4`
- `0x180055fa4`
- `0x180057f58`
- `0x1800587c8`
- `0x18005d050`
- `0x180067c68`
- `0x1800aac70`
- `0x1800d0d9c`
- `0x1800e22dc`
- `0x1800ef644`
- `0x18011298c`
- `0x18012de40`
- `0x180161298`
- `0x180177b0c`
- `0x18018bbe8`
- `0x18018cda0`
- `0x18018ce68`
- `0x18018e0cc`
- `0x18018ed78`
- `0x180190820`
- `0x180190dd4`
- `0x180191044`
- `0x1801911a8`
- `0x18019139c`
- `0x180194dac`
- `0x180199220`
- `0x1801c70ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18018e9af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18018e9af`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018e52b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018e634`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018e800`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018e52b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018e634`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18018e800`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18018e664`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x18018e664`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x18018e75a`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x18018e75a`

## string_xrefs

- `0x18018e247`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18018e682`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18018e6b7`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18018e777`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18018e7d8`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Microsoft::Diagnostics::SettingsManager::ApiDownloadSettingsWorkCallback(
        Microsoft::Diagnostics::SettingsManager *this,
        struct Microsoft::Diagnostics::SettingsManager::DownloadLatestSettingsData *a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  _QWORD *v7; // rax
  struct Microsoft::Diagnostics::SettingsManager::DownloadLatestSettingsData *v8; // rax
  Microsoft::Diagnostics::UtcApiManagerBase *ApiManager; // rax
  int Ticket; // eax
  struct _GUID *v11; // rax
  int v12; // r9d
  __int64 v13; // rax
  int v14; // ecx
  int v15; // r8d
  __int64 v16; // r9
  void *appended; // rax
  void *v18; // r8
  char IsEndpointActive; // r15
  const WCHAR *v20; // rcx
  unsigned __int64 v21; // rsi
  __int64 v22; // rax
  const WCHAR *v23; // rcx
  wil::details::in1diag3 *v24; // rcx
  const WCHAR *v25; // rdx
  const WCHAR *v26; // rcx
  BOOL v27; // eax
  const char *v28; // r9
  const char *v29; // r9
  _QWORD *v30; // rcx
  int started; // eax
  int v32; // eax
  const WCHAR *v33; // rcx
  int v34; // r9d
  int v35; // eax
  int v36; // r8d
  int v37; // r9d
  int v38; // r8d
  int v39; // r9d
  struct Microsoft::Diagnostics::ScenarioManager *ScenarioManager; // rax
  int v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  int v44[4]; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID v45; // [rsp+90h] [rbp-70h] BYREF
  int v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  struct _GUID v48; // [rsp+B0h] [rbp-50h] BYREF
  char v49; // [rsp+C1h] [rbp-3Fh]
  int v50; // [rsp+C4h] [rbp-3Ch] BYREF
  unsigned __int64 FileTimeAsULL; // [rsp+C8h] [rbp-38h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v53; // [rsp+E8h] [rbp-18h]
  LPCWSTR lpExistingFileName[3]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v55; // [rsp+108h] [rbp+8h]
  __int64 v56[4]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v57[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE Src[48]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v59[6]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v60; // [rsp+186h] [rbp+86h]
  _BYTE v61[32]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v62[104]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v63[208]; // [rsp+270h] [rbp+170h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+288h]

  v49 = 1;
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8704) )
  {
    v50 = *((unsigned __int8 *)a2 + 65);
    v46 = *((unsigned __int8 *)a2 + 64);
    v7 = (_QWORD *)((char *)a2 + 32);
    if ( *((_QWORD *)a2 + 7) > 7u )
      v7 = (_QWORD *)*v7;
    *(_QWORD *)&v48.Data1 = v7;
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v8 = a2;
    else
      v8 = *(struct Microsoft::Diagnostics::SettingsManager::DownloadLatestSettingsData **)a2;
    *(_QWORD *)v44 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&unk_1803C425F,
      v5,
      v6,
      (__int64)v44,
      (__int64)&v48,
      (__int64)&v46,
      (__int64)&v50);
  }
  if ( (qword_18043C080 & 4) == 0 )
  {
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803C4212);
    *((_DWORD *)a2 + 19) = -2017123067;
    goto LABEL_14;
  }
  FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  std::wstring::wstring(v56);
  *(struct _GUID *)((char *)this + 616) = *Microsoft::Diagnostics::SettingsManager::GetMsaTokenClientIdGuid(&v45);
  Ticket = Microsoft::Diagnostics::DeviceTicket::GetTicket((char *)this + 552, v56);
  if ( Ticket < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1DA,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)Ticket,
      v41);
  v11 = (struct _GUID *)std::wstring::operator std::wstring_view((char *)a2 + 32, v57);
  *(_QWORD *)v44 = &::Src;
  *(_QWORD *)&v44[2] = 0;
  v48 = *v11;
  v45 = *(struct _GUID *)std::wstring::operator std::wstring_view(a2, lpExistingFileName);
  Microsoft::Diagnostics::SettingsEndpoint::SettingsEndpoint(
    (unsigned int)v59,
    (unsigned int)&v45,
    (unsigned int)&v48,
    v12,
    2,
    4,
    0,
    0,
    (__int64)v44,
    0,
    0,
    0);
  if ( !Microsoft::Diagnostics::SettingsEndpoint::HasValidPartnerFeature((Microsoft::Diagnostics::SettingsEndpoint *)v59) )
  {
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
    {
      std::wstring::operator std::wstring_view(v62, &v45);
      std::wstring::operator std::wstring_view(v62, v44);
      _tlgWrapBinary<wchar_t,2>(lpExistingFileName, *(_QWORD *)v44, *(unsigned int *)v45.Data4);
      std::wstring::operator std::wstring_view(v61, &v45);
      std::wstring::operator std::wstring_view(v61, v44);
      v13 = _tlgWrapBinary<wchar_t,2>(v57, *(_QWORD *)v44, *(unsigned int *)v45.Data4);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>>(
        v14,
        (unsigned int)&unk_1803C41AB,
        v15,
        v16,
        v13,
        v16);
    }
    *((_DWORD *)a2 + 19) = -2147024773;
LABEL_23:
    Microsoft::Diagnostics::SettingsEndpoint::~SettingsEndpoint((Microsoft::Diagnostics::SettingsEndpoint *)v59);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
LABEL_14:
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BFC0 + 1, 0, 0) )
    {
      ApiManager = Microsoft::Diagnostics::LifetimeManager::GetApiManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::UtcApiManagerBase::SetReloadSettingsCompleteEvent(ApiManager);
    }
    return;
  }
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)Src);
  std::wstring::operator std::wstring_view(v61, &v45);
  appended = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(Src);
  Microsoft::Diagnostics::WideStringStream::operator<<(appended);
  std::wstring::operator std::wstring_view(v62, &v45);
  Microsoft::Diagnostics::WideStringStream::AppendString(v18);
  v45 = *(struct _GUID *)std::wstring::operator std::wstring_view(Src, lpExistingFileName);
  IsEndpointActive = Microsoft::Diagnostics::SettingsManager::IsEndpointActive(this, &v45);
  Microsoft::Diagnostics::SettingsEndpoint::GetUnexpandedSettingsFilePath(v59, lpFileName);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  LOBYTE(v43) = 0;
  if ( IsEndpointActive )
  {
    Microsoft::Diagnostics::SettingsEndpoint::LoadFromRegistry(v59, 1, 15);
  }
  else
  {
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803C4170);
    std::wstring::operator std::wstring_view(v62, &v45);
    std::wstring::operator std::wstring_view(v61, &v48);
    *(_QWORD *)v44 = &::Src;
    *(_QWORD *)&v44[2] = 0;
    Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(
      (_DWORD)this,
      (unsigned int)&v48,
      (unsigned int)&v45,
      v60,
      2,
      4,
      0,
      0,
      0,
      (__int64)v44);
    v20 = (const WCHAR *)lpFileName;
    if ( v53 > 7 )
      v20 = lpFileName[0];
    if ( GetFileAttributesW(v20) == -1 )
    {
      std::wstring::operator std::wstring_view(lpFileName, v44);
      v21 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(*(_QWORD *)v44, *(_QWORD *)&v44[2], -1, 92);
      v22 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(*(_QWORD *)v44, *(_QWORD *)&v44[2], -1, 46);
      if ( v21 != -1 && v22 != -1 && v21 < v22 - 1 )
      {
        std::wstring_view::substr(v44, &v48, v21 + 1, v22 - v21 - 1);
        std::wstring::wstring(v57);
        v45 = *(struct _GUID *)&off_18035F260;
        Microsoft::Diagnostics::operator+(lpExistingFileName);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
        std::wstring::_Append<wchar_t>(lpExistingFileName);
        std::wstring::_Append<wchar_t>(lpExistingFileName);
        Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpExistingFileName, 1, 0);
        v23 = (const WCHAR *)lpExistingFileName;
        if ( v55 > 7 )
          v23 = lpExistingFileName[0];
        if ( GetFileAttributesW(v23) != -1 )
        {
          v25 = (const WCHAR *)lpFileName;
          if ( v53 > 7 )
            v25 = lpFileName[0];
          v26 = (const WCHAR *)lpExistingFileName;
          if ( v55 > 7 )
            v26 = lpExistingFileName[0];
          v27 = CopyFileW(v26, v25, 0);
          LOBYTE(v43) = v27;
          v24 = retaddr;
          if ( v27 )
            goto LABEL_44;
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x226,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            v28);
        }
        if ( !(_BYTE)v43 )
        {
LABEL_46:
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpExistingFileName);
          goto LABEL_48;
        }
LABEL_44:
        v45 = v48;
        if ( !(unsigned __int8)Microsoft::Diagnostics::SettingsManager::CopyInboxSettingsForNamespaceToMutableDirectory(
                                 v24,
                                 &v45) )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0x22C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            v29);
        goto LABEL_46;
      }
    }
  }
LABEL_48:
  v59[1] = 1;
  v59[2] = *((_BYTE *)a2 + 64);
  *(_QWORD *)v44 = L"ApiManager";
  *(_QWORD *)&v44[2] = 10;
  Microsoft::Diagnostics::PdcNetworkActivation::PdcNetworkActivation((Microsoft::Diagnostics::PdcNetworkActivation *)v63);
  v30 = (_QWORD *)((char *)this + 424);
  *((_QWORD *)this + 55) = 0;
  if ( *((_QWORD *)this + 56) > 7u )
    v30 = (_QWORD *)*v30;
  *(_WORD *)v30 = 0;
  v47 = 0;
  started = OneSettingsStartDownloadSession(Microsoft::Diagnostics::SettingsDownloader::k_OneSettingsClientIdUtc, &v47);
  *((_DWORD *)a2 + 19) = started;
  if ( started < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x243,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)started,
      v42);
  v32 = *((_DWORD *)a2 + 19);
  if ( v32 >= 0 )
  {
    v32 = Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload(
            this,
            (struct Microsoft::Diagnostics::SettingsEndpoint *)v59,
            v47,
            &FileTimeAsULL,
            (__int64)v56,
            1,
            *(_QWORD *)((char *)a2 + 68),
            &v43);
    *((_DWORD *)a2 + 19) = v32;
  }
  if ( v32 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)v32,
      v42);
  if ( !IsEndpointActive )
  {
    v33 = (const WCHAR *)lpFileName;
    if ( v53 > 7 )
      v33 = lpFileName[0];
    if ( GetFileAttributesW(v33) == -1 )
    {
      if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803C4135);
      std::wstring::operator std::wstring_view(v62, &v45);
      std::wstring::operator std::wstring_view(v61, v44);
      LOBYTE(v34) = *((_BYTE *)a2 + 65);
      Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(
        (_DWORD)this,
        (unsigned int)v44,
        (unsigned int)&v45,
        v34,
        8);
    }
  }
  v35 = *((_DWORD *)a2 + 19);
  if ( !(_BYTE)v43 )
  {
    if ( v35 >= 0 )
    {
      *((_DWORD *)a2 + 19) = 1;
      if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8704) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803C3FCD);
    }
    else if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8704) )
    {
      v46 = *((_DWORD *)a2 + 19);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C4020,
        v36,
        v37,
        (__int64)&v46);
    }
    wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadSession *,long (OneSettingsDownloadSession *),&long OneSettingsEndDownloadSession(OneSettingsDownloadSession *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadSession *,OneSettingsDownloadSession *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<OneSettingsDownloadSession *,long (OneSettingsDownloadSession *),&long OneSettingsEndDownloadSession(OneSettingsDownloadSession *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadSession *,OneSettingsDownloadSession *,0,std::nullptr_t>>(&v47);
    Microsoft::Diagnostics::PdcNetworkActivation::~PdcNetworkActivation((Microsoft::Diagnostics::PdcNetworkActivation *)v63);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    goto LABEL_23;
  }
  if ( v35 < 0 && (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8704) )
  {
    v46 = *((_DWORD *)a2 + 19);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18042D328,
      (unsigned int)&unk_1803C40C7,
      v38,
      v39,
      (__int64)&v46);
  }
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8704) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18042D328,
      &unk_1803C4083);
  ScenarioManager = Microsoft::Diagnostics::LifetimeManager::GetScenarioManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  SetEvent(*((HANDLE *)ScenarioManager + 12));
  wil::details::unique_storage<wil::details::resource_policy<OneSettingsDownloadSession *,long (OneSettingsDownloadSession *),&long OneSettingsEndDownloadSession(OneSettingsDownloadSession *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadSession *,OneSettingsDownloadSession *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<OneSettingsDownloadSession *,long (OneSettingsDownloadSession *),&long OneSettingsEndDownloadSession(OneSettingsDownloadSession *),wistd::integral_constant<unsigned __int64,0>,OneSettingsDownloadSession *,OneSettingsDownloadSession *,0,std::nullptr_t>>(&v47);
  Microsoft::Diagnostics::PdcNetworkActivation::~PdcNetworkActivation((Microsoft::Diagnostics::PdcNetworkActivation *)v63);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  Microsoft::Diagnostics::SettingsEndpoint::~SettingsEndpoint((Microsoft::Diagnostics::SettingsEndpoint *)v59);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
}

```

## disassembly

```asm
0x18018e0cc  mov     [rsp-8+arg_10], rbx
0x18018e0d1  push    rbp
0x18018e0d2  push    rsi
0x18018e0d3  push    rdi
0x18018e0d4  push    r12
0x18018e0d6  push    r13
0x18018e0d8  push    r14
0x18018e0da  push    r15
0x18018e0dc  lea     rbp, [rsp-250h]
0x18018e0e4  sub     rsp, 350h
0x18018e0eb  mov     rax, cs:__security_cookie
0x18018e0f2  xor     rax, rsp
0x18018e0f5  mov     [rbp+280h+var_40], rax
0x18018e0fc  mov     rdi, rdx
0x18018e0ff  mov     r14, rcx
0x18018e102  mov     [rbp+280h+var_2BF], 1
0x18018e106  mov     eax, cs:dword_18042D328
0x18018e10c  lea     r13, dword_18042D328
0x18018e113  xor     r12d, r12d
0x18018e116  lea     esi, [r12+4]
0x18018e11b  cmp     eax, esi
0x18018e11d  jbe     short loc_18018E194
0x18018e11f  mov     edx, 2200h
0x18018e124  mov     rcx, r13
0x18018e127  call    _tlgKeywordOn
0x18018e12c  test    al, al
0x18018e12e  jz      short loc_18018E194
0x18018e130  movzx   eax, byte ptr [rdi+41h]
0x18018e134  mov     [rbp+280h+var_2BC], eax
0x18018e137  movzx   eax, byte ptr [rdi+40h]
0x18018e13b  mov     [rbp+280h+var_2E0], eax
0x18018e13e  lea     rax, [rdi+20h]
0x18018e142  cmp     qword ptr [rax+18h], 7
0x18018e147  jbe     short loc_18018E14C
0x18018e149  mov     rax, [rax]
0x18018e14c  mov     qword ptr [rbp+280h+var_2D0.Data1], rax
0x18018e150  cmp     qword ptr [rdi+18h], 7
0x18018e155  jbe     short loc_18018E15C
0x18018e157  mov     rax, [rdi]
0x18018e15a  jmp     short loc_18018E15F
0x18018e15c  mov     rax, rdi
0x18018e15f  mov     qword ptr [rbp+280h+var_300], rax
0x18018e163  lea     rax, [rbp+280h+var_2BC]
0x18018e167  mov     [rsp+380h+var_348], rax
0x18018e16c  lea     rax, [rbp+280h+var_2E0]
0x18018e170  mov     [rsp+380h+var_350], rax
0x18018e175  lea     rax, [rbp+280h+var_2D0]
0x18018e179  mov     qword ptr [rsp+380h+var_358], rax
0x18018e17e  lea     rax, [rbp+280h+var_300]
0x18018e182  mov     [rsp+380h+var_360], rax; int
0x18018e187  lea     rdx, unk_1803C425F
0x18018e18e  call    ??$Write@U?$_tlgWrapSz@_W@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18018e193  nop
0x18018e194  mov     eax, dword ptr cs:qword_18043C080
0x18018e19a  test    sil, al
0x18018e19d  jnz     short loc_18018E202
0x18018e19f  mov     eax, cs:dword_18042D328
0x18018e1a5  mov     ebx, 2
0x18018e1aa  cmp     eax, ebx
0x18018e1ac  jbe     short loc_18018E1CE
0x18018e1ae  mov     edx, 200h
0x18018e1b3  mov     rcx, r13
0x18018e1b6  call    _tlgKeywordOn
0x18018e1bb  test    al, al
0x18018e1bd  jz      short loc_18018E1CE
0x18018e1bf  lea     rdx, unk_1803C4212
0x18018e1c6  mov     rcx, r13
0x18018e1c9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018e1ce  mov     dword ptr [rdi+4Ch], 87C52505h
0x18018e1d5  mov     rcx, r12
0x18018e1d8  xor     eax, eax
0x18018e1da  lock cmpxchg qword ptr cs:xmmword_18043BFC0+8, rcx
0x18018e1e3  jz      loc_18018E9FE
0x18018e1e9  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18018e1f0  call    ?GetApiManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVUtcApiManagerBase@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetApiManager(void)
0x18018e1f5  mov     rcx, rax; this
0x18018e1f8  call    ?SetReloadSettingsCompleteEvent@UtcApiManagerBase@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::UtcApiManagerBase::SetReloadSettingsCompleteEvent(void)
0x18018e1fd  jmp     loc_18018E9FE
0x18018e202  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x18018e207  mov     [rbp+280h+var_2B8], rax
0x18018e20b  lea     rcx, [rbp+280h+var_270]; void *
0x18018e20f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18018e214  nop
0x18018e215  lea     rbx, [r14+228h]
0x18018e21c  lea     rcx, [rbp+280h+var_2F0]; retstr
0x18018e220  call    ?GetMsaTokenClientIdGuid@SettingsManager@Diagnostics@Microsoft@@SA?AU_GUID@@XZ; Microsoft::Diagnostics::SettingsManager::GetMsaTokenClientIdGuid(void)
0x18018e225  movups  xmm0, xmmword ptr [rax]
0x18018e228  movdqu  xmmword ptr [rbx+40h], xmm0
0x18018e22d  lea     rdx, [rbp+280h+var_270]
0x18018e231  mov     rcx, rbx
0x18018e234  call    ?GetTicket@DeviceTicket@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::DeviceTicket::GetTicket(std::wstring &)
0x18018e239  mov     rcx, [rbp+288h]; this
0x18018e240  test    eax, eax
0x18018e242  jns     short loc_18018E258
0x18018e244  mov     r9d, eax; char *
0x18018e247  lea     r8, aOnecoreBaseTel_84; "onecore\\base\\telemetry\\utc\\service"...
0x18018e24e  mov     edx, 1DAh; void *
0x18018e253  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18018e258  mov     ebx, 2
0x18018e25d  mov     r9d, r12d
0x18018e260  cmp     [rdi+41h], r12b
0x18018e264  setz    r9b
0x18018e268  lea     rcx, [rdi+20h]
0x18018e26c  lea     rdx, [rbp+280h+var_250]
0x18018e270  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e275  lea     rcx, Src
0x18018e27c  mov     qword ptr [rbp+280h+var_300], rcx
0x18018e280  mov     qword ptr [rbp+280h+var_300+8], r12
0x18018e284  movups  xmm0, xmmword ptr [rax]
0x18018e287  movdqu  xmmword ptr [rbp+280h+var_2D0.Data1], xmm0
0x18018e28c  lea     rdx, [rbp+280h+lpExistingFileName]
0x18018e290  mov     rcx, rdi
0x18018e293  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e298  movups  xmm0, xmmword ptr [rax]
0x18018e29b  movdqu  xmmword ptr [rbp+280h+var_2F0.Data1], xmm0
0x18018e2a0  mov     [rsp+380h+var_328], r12b
0x18018e2a5  mov     [rsp+380h+var_330], r12b
0x18018e2aa  mov     byte ptr [rsp+380h+var_338], r12b
0x18018e2af  lea     rax, [rbp+280h+var_300]
0x18018e2b3  mov     [rsp+380h+var_340], rax
0x18018e2b8  mov     word ptr [rsp+380h+var_348], r12w
0x18018e2be  mov     word ptr [rsp+380h+var_350], r12w
0x18018e2c4  mov     word ptr [rsp+380h+var_358], si
0x18018e2c9  mov     word ptr [rsp+380h+var_360], bx
0x18018e2ce  lea     r8, [rbp+280h+var_2D0]
0x18018e2d2  lea     rdx, [rbp+280h+var_2F0]
0x18018e2d6  lea     rcx, [rbp+280h+var_200]
0x18018e2dd  call    ??0SettingsEndpoint@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0VSettingsType@12@VSettingsPriority@12@VSettingsRegistrationType@12@VSettingsPayloadType@12@VSettingsParseType@12@0_N66@Z; Microsoft::Diagnostics::SettingsEndpoint::SettingsEndpoint(std::wstring_view,std::wstring_view,Microsoft::Diagnostics::SettingsType,Microsoft::Diagnostics::SettingsPriority,Microsoft::Diagnostics::SettingsRegistrationType,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsParseType,std::wstring_view,bool,bool,bool)
0x18018e2e2  nop
0x18018e2e3  lea     rcx, [rbp+280h+var_200]; this
0x18018e2ea  call    ?HasValidPartnerFeature@SettingsEndpoint@Diagnostics@Microsoft@@QEBA_NXZ; Microsoft::Diagnostics::SettingsEndpoint::HasValidPartnerFeature(void)
0x18018e2ef  test    al, al
0x18018e2f1  jnz     loc_18018E3B3
0x18018e2f7  mov     eax, cs:dword_18042D328
0x18018e2fd  cmp     eax, ebx
0x18018e2ff  jbe     loc_18018E391
0x18018e305  mov     edx, 200h
0x18018e30a  mov     rcx, r13
0x18018e30d  call    _tlgKeywordOn
0x18018e312  test    al, al
0x18018e314  jz      short loc_18018E391
0x18018e316  lea     rdx, [rbp+280h+var_2F0]
0x18018e31a  lea     rcx, [rbp+280h+var_178]
0x18018e321  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e326  lea     rdx, [rbp+280h+var_300]
0x18018e32a  lea     rcx, [rbp+280h+var_178]
0x18018e331  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e336  mov     r8d, dword ptr [rbp+280h+var_2F0.Data4]
0x18018e33a  mov     rdx, qword ptr [rbp+280h+var_300]
0x18018e33e  lea     rcx, [rbp+280h+lpExistingFileName]
0x18018e342  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18018e347  mov     r9, rax
0x18018e34a  lea     rdx, [rbp+280h+var_2F0]
0x18018e34e  lea     rcx, [rbp+280h+var_198]
0x18018e355  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e35a  lea     rdx, [rbp+280h+var_300]
0x18018e35e  lea     rcx, [rbp+280h+var_198]
0x18018e365  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e36a  mov     r8d, dword ptr [rbp+280h+var_2F0.Data4]
0x18018e36e  mov     rdx, qword ptr [rbp+280h+var_300]
0x18018e372  lea     rcx, [rbp+280h+var_250]
0x18018e376  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18018e37b  mov     qword ptr [rsp+380h+var_358], r9
0x18018e380  mov     [rsp+380h+var_360], rax
0x18018e385  lea     rdx, unk_1803C41AB
0x18018e38c  call    ??$Write@U?$_tlgWrapperArray@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &,_tlgWrapperArray<1> const &)
0x18018e391  mov     dword ptr [rdi+4Ch], 8007007Bh
0x18018e398  lea     rcx, [rbp+280h+var_200]; this
0x18018e39f  call    ??1SettingsEndpoint@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::SettingsEndpoint::~SettingsEndpoint(void)
0x18018e3a4  nop
0x18018e3a5  lea     rcx, [rbp+280h+var_270]; this
0x18018e3a9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18018e3ae  jmp     loc_18018E1D5
0x18018e3b3  lea     rcx, [rbp+280h+Src]; this
0x18018e3b7  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x18018e3bc  nop
0x18018e3bd  lea     rdx, [rbp+280h+var_2F0]
0x18018e3c1  lea     rcx, [rbp+280h+var_198]
0x18018e3c8  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e3cd  movaps  xmm0, xmmword ptr [rbp+280h+var_2F0.Data1]
0x18018e3d1  movdqa  xmmword ptr [rbp+280h+var_2F0.Data1], xmm0
0x18018e3d6  lea     rdx, [rbp+280h+var_2F0]
0x18018e3da  lea     rcx, [rbp+280h+Src]; Src
0x18018e3de  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18018e3e3  lea     rdx, PathName; "."
0x18018e3ea  mov     rcx, rax; Src
0x18018e3ed  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x18018e3f2  mov     r8, rax
0x18018e3f5  lea     rdx, [rbp+280h+var_2F0]
0x18018e3f9  lea     rcx, [rbp+280h+var_178]
0x18018e400  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e405  movaps  xmm0, xmmword ptr [rbp+280h+var_2F0.Data1]
0x18018e409  movdqa  xmmword ptr [rbp+280h+var_2F0.Data1], xmm0
0x18018e40e  lea     rdx, [rbp+280h+var_2F0]
0x18018e412  mov     rcx, r8; Src
0x18018e415  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x18018e41a  lea     rdx, [rbp+280h+lpExistingFileName]
0x18018e41e  lea     rcx, [rbp+280h+Src]
0x18018e422  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e427  movups  xmm0, xmmword ptr [rax]
0x18018e42a  movdqu  xmmword ptr [rbp+280h+var_2F0.Data1], xmm0
0x18018e42f  lea     rdx, [rbp+280h+var_2F0]
0x18018e433  mov     rcx, r14
0x18018e436  call    ?IsEndpointActive@SettingsManager@Diagnostics@Microsoft@@QEAA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::SettingsManager::IsEndpointActive(std::wstring_view)
0x18018e43b  mov     r15b, al
0x18018e43e  lea     rdx, [rbp+280h+lpFileName]
0x18018e442  lea     rcx, [rbp+280h+var_200]
0x18018e449  call    ?GetUnexpandedSettingsFilePath@SettingsEndpoint@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::SettingsEndpoint::GetUnexpandedSettingsFilePath(void)
0x18018e44e  nop
0x18018e44f  xor     r8d, r8d
0x18018e452  mov     dl, 1
0x18018e454  lea     rcx, [rbp+280h+lpFileName]; lpSrc
0x18018e458  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18018e45d  mov     byte ptr [rsp+380h+var_310], r12b
0x18018e462  test    r15b, r15b
0x18018e465  jnz     loc_18018E6DB
0x18018e46b  mov     eax, cs:dword_18042D328
0x18018e471  cmp     eax, esi
0x18018e473  jbe     short loc_18018E495
0x18018e475  mov     edx, 2000h
0x18018e47a  mov     rcx, r13
0x18018e47d  call    _tlgKeywordOn
0x18018e482  test    al, al
0x18018e484  jz      short loc_18018E495
0x18018e486  lea     rdx, unk_1803C4170
0x18018e48d  mov     rcx, r13
0x18018e490  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18018e495  lea     rdx, [rbp+280h+var_2F0]
0x18018e499  lea     rcx, [rbp+280h+var_178]
0x18018e4a0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e4a5  lea     rdx, [rbp+280h+var_2D0]
0x18018e4a9  lea     rcx, [rbp+280h+var_198]
0x18018e4b0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e4b5  lea     rcx, Src
0x18018e4bc  mov     qword ptr [rbp+280h+var_300], rcx
0x18018e4c0  mov     qword ptr [rbp+280h+var_300+8], r12
0x18018e4c4  movaps  xmm0, xmmword ptr [rbp+280h+var_2F0.Data1]
0x18018e4c8  movdqa  xmmword ptr [rbp+280h+var_2F0.Data1], xmm0
0x18018e4cd  movaps  xmm1, xmmword ptr [rbp+280h+var_2D0.Data1]
0x18018e4d1  movdqa  xmmword ptr [rbp+280h+var_2D0.Data1], xmm1
0x18018e4d6  mov     [rsp+380h+var_320], r12b
0x18018e4db  mov     [rsp+380h+var_328], r12b
0x18018e4e0  lea     rax, [rbp+280h+var_300]
0x18018e4e4  mov     [rsp+380h+var_338], rax
0x18018e4e9  mov     word ptr [rsp+380h+var_340], r12w
0x18018e4ef  mov     word ptr [rsp+380h+var_348], r12w
0x18018e4f5  mov     word ptr [rsp+380h+var_350], r12w
0x18018e4fb  mov     word ptr [rsp+380h+var_358], si
0x18018e500  mov     word ptr [rsp+380h+var_360], bx; int
0x18018e505  movzx   r9d, [rbp+280h+var_1FA]
0x18018e50d  lea     r8, [rbp+280h+var_2F0]
0x18018e511  lea     rdx, [rbp+280h+var_2D0]
0x18018e515  mov     rcx, r14
0x18018e518  call    ?RegisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0VSettingsType@23@VSettingsPriority@23@VSettingsRegistrationType@23@VSettingsPayloadType@23@VSettingsParseType@23@VSettingsCreationType@23@0_N77@Z; Microsoft::Diagnostics::SettingsManager::RegisterSettingsEndpoint(std::wstring_view,std::wstring_view,Microsoft::Diagnostics::SettingsType,Microsoft::Diagnostics::SettingsPriority,Microsoft::Diagnostics::SettingsRegistrationType,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsParseType,Microsoft::Diagnostics::SettingsCreationType,std::wstring_view,bool,bool,bool)
0x18018e51d  lea     rcx, [rbp+280h+lpFileName]
0x18018e521  cmp     [rbp+280h+var_298], 7
0x18018e526  cmova   rcx, [rbp+280h+lpFileName]; lpFileName
0x18018e52b  call    cs:__imp_GetFileAttributesW
0x18018e532  nop     dword ptr [rax+rax+00h]
0x18018e537  cmp     eax, 0FFFFFFFFh
0x18018e53a  jnz     loc_18018E6F7
0x18018e540  lea     rdx, [rbp+280h+var_300]
0x18018e544  lea     rcx, [rbp+280h+lpFileName]
0x18018e548  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18018e54d  mov     r9d, 5Ch ; '\'
0x18018e553  or      r8, 0FFFFFFFFFFFFFFFFh
0x18018e557  mov     rdx, qword ptr [rbp+280h+var_300+8]
0x18018e55b  mov     rcx, qword ptr [rbp+280h+var_300]
0x18018e55f  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x18018e564  mov     rsi, rax
0x18018e567  mov     r9d, 2Eh ; '.'
0x18018e56d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18018e571  mov     rdx, qword ptr [rbp+280h+var_300+8]
0x18018e575  mov     rcx, qword ptr [rbp+280h+var_300]
0x18018e579  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x18018e57e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18018e582  jz      loc_18018E6F2
0x18018e588  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18018e58c  jz      loc_18018E6F2
0x18018e592  lea     rcx, [rax-1]
0x18018e596  cmp     rsi, rcx
0x18018e599  jnb     loc_18018E6F2
0x18018e59f  sub     rax, rsi
0x18018e5a2  lea     r9, [rax-1]
0x18018e5a6  lea     r8, [rsi+1]
0x18018e5aa  lea     rdx, [rbp+280h+var_2D0]
0x18018e5ae  lea     rcx, [rbp+280h+var_300]
0x18018e5b2  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x18018e5b7  lea     rdx, asc_1803772C8; "\\"
0x18018e5be  lea     rcx, [rbp+280h+var_250]
0x18018e5c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18018e5c7  nop
0x18018e5c8  movups  xmm0, xmmword ptr cs:off_18035F260; "%WinDir%\\DiagTrack\\Scenarios"
0x18018e5cf  movdqu  xmmword ptr [rbp+280h+var_2F0.Data1], xmm0
0x18018e5d4  lea     r8, [rbp+280h+var_250]
0x18018e5d8  lea     rdx, [rbp+280h+var_2F0]
0x18018e5dc  lea     rcx, [rbp+280h+lpExistingFileName]; Src
0x18018e5e0  call    ??HDiagnostics@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@$$QEAV23@@Z; Microsoft::Diagnostics::operator+(std::wstring_view,std::wstring &&)
0x18018e5e5  nop
0x18018e5e6  lea     rcx, [rbp+280h+var_250]; this
  ... truncated ...
```
