# Microsoft::Diagnostics::EventTranscriptManager::InitializeStore(void)

- ea: `0x1802d4fb4`
- end: `0x1802d5982`
- name: `?InitializeStore@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJXZ`
- size: `2510`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::EventTranscriptManager *__hidden this)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1802d1af4`

## callees

- `0x180001bf4`
- `0x180001e90`
- `0x180003a00`
- `0x180015030`
- `0x18001c5b0`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180035698`
- `0x18003f14c`
- `0x18004dcf0`
- `0x18005d050`
- `0x1800a0188`
- `0x1800a04c8`
- `0x1800ba6c0`
- `0x1800bab28`
- `0x1800babec`
- `0x1800bac14`
- `0x1800bac3c`
- `0x1800bae3c`
- `0x1800bc0a0`
- `0x1800d0d9c`
- `0x1800e0e94`
- `0x1800e28dc`
- `0x18011d000`
- `0x18012de40`
- `0x180172d70`
- `0x180173510`
- `0x18021d2f4`
- `0x18021db28`
- `0x18021df88`
- `0x18022312c`
- `0x1802ae1e4`
- `0x1802cd920`
- `0x1802cde1c`
- `0x1802ce334`
- `0x1802d1c38`
- `0x1802d4458`
- `0x1802d4fb4`
- `0x1802d6bb4`
- `0x1802d6e88`
- `0x1802d7c1c`
- `0x1802d8314`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1802d51b1`
- `msvcp_win!_Mtx_unlock` at `0x1802d531a`
- `msvcp_win!_Mtx_unlock` at `0x1802d51b1`
- `msvcp_win!_Mtx_unlock` at `0x1802d531a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1802d5150`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1802d5150`

## string_xrefs

- `0x1802d5017`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d50ed`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d5229`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d5266`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d5340`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d5381`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d5444`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d581e`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d585d`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d5899`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d58d8`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d5914`: `onecore\base\telemetry\utc\service\analysis\eventtranscriptmanager.cpp`
- `0x1802d57c9`: `CREATE TABLE IF NOT EXISTS events_persisted (\n                        sid                             TEXT,\n                        timestamp                       INTEGER,\n                        payload                         TEXT,\n                        full_event_name                 TEXT,\n                        full_event_name_hash            INTEGER,\n                        event_keywords                  INTEGER,\n                        is_core                         INTEGER,\n`
- `0x1802d57d0`: `CREATE TABLE IF NOT EXISTS events_persisted (\n                        sid                             TEXT,\n                        timestamp                       INTEGER,\n                        payload                         TEXT,\n                        full_event_name                 TEXT,\n                        full_event_name_hash            INTEGER,\n                        event_keywords                  INTEGER,\n                        is_core                         INTEGER,\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::Diagnostics::EventTranscriptManager::InitializeStore(
        Microsoft::Diagnostics::EventTranscriptManager *this,
        __int64 a2,
        int a3,
        int a4)
{
  Microsoft::Diagnostics::EventTranscriptManager *v4; // rdi
  __int64 result; // rax
  Microsoft::Diagnostics::SqlConnection **v7; // rsi
  Microsoft::Diagnostics::LifetimeManager *v8; // rcx
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rcx
  const char *v10; // r9
  _QWORD *TranscriptFilePathExpanded; // rax
  const WCHAR *v12; // rcx
  __int64 v13; // r15
  __int64 *v14; // rax
  wil *v15; // rcx
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r14d
  char v19; // r13
  __int64 *v20; // rax
  int v21; // eax
  unsigned int v22; // r14d
  int v23; // eax
  unsigned int v24; // r14d
  __int64 v25; // rax
  __int128 *v26; // rax
  __int64 v27; // rax
  __int64 v28; // r15
  __int64 v29; // rax
  unsigned int v30; // eax
  unsigned __int64 v31; // r14
  const char *v32; // r9
  unsigned __int64 v33; // r12
  double v34; // xmm1_8
  double v35; // xmm0_8
  __int64 v36; // r15
  float v37; // xmm1_4
  float v38; // xmm0_4
  int v39; // ecx
  int v40; // r8d
  char IsEnabled; // al
  const char *v42; // rcx
  __int64 v43; // rax
  int v44; // eax
  unsigned int v45; // esi
  int v46; // eax
  unsigned int v47; // esi
  int v48; // eax
  unsigned int v49; // esi
  int v50; // eax
  unsigned int v51; // esi
  int v52; // eax
  unsigned int v53; // edi
  int v54; // ebx
  Microsoft::Diagnostics::EventTranscriptManager *v55; // rdi
  int v56; // eax
  unsigned int v57; // edi
  int v58; // [rsp+20h] [rbp-1A8h]
  int v59; // [rsp+20h] [rbp-1A8h]
  unsigned int v60; // [rsp+30h] [rbp-198h] BYREF
  char v61; // [rsp+34h] [rbp-194h]
  const char *v62; // [rsp+40h] [rbp-188h] BYREF
  __int64 v63; // [rsp+48h] [rbp-180h]
  __int128 v64; // [rsp+60h] [rbp-168h] BYREF
  unsigned __int64 v65[2]; // [rsp+70h] [rbp-158h] BYREF
  const char *v66; // [rsp+80h] [rbp-148h] BYREF
  Microsoft::Diagnostics::EventTranscriptManager *v67; // [rsp+88h] [rbp-140h]
  _BYTE v68[32]; // [rsp+90h] [rbp-138h] BYREF
  _BYTE v69[32]; // [rsp+B0h] [rbp-118h] BYREF
  _BYTE v70[16]; // [rsp+D0h] [rbp-F8h] BYREF
  LPCWSTR pszPath[4]; // [rsp+E0h] [rbp-E8h] BYREF
  _BYTE v72[48]; // [rsp+100h] [rbp-C8h] BYREF
  _BYTE v73[48]; // [rsp+130h] [rbp-98h] BYREF
  _BYTE v74[48]; // [rsp+160h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v4 = this;
  v67 = this;
  if ( *((_BYTE *)this + 1981) )
  {
    gsl::details::terminate(this);
    JUMPOUT(0x1802D5980LL);
  }
  if ( !*((_BYTE *)this + 1980) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8F8,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
      (const char *)0x80070426LL,
      v59);
    return 2147943462LL;
  }
  try
  {
    v7 = (Microsoft::Diagnostics::SqlConnection **)((char *)this + 2272);
    if ( *((_QWORD *)this + 284) )
    {
      if ( (unsigned int)dword_18042D328 > 2 )
      {
        v66 = "InitializeStore";
        v65[0] = (unsigned __int64)"m_dbPersistConnection == nullptr";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (_DWORD)this,
          (unsigned int)&unk_1803DDB0E,
          a3,
          a4,
          (__int64)v65,
          (__int64)&v66);
      }
      if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
      {
        TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v8);
        Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
      }
      if ( *v7 )
      {
        if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x100000) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803DD9C1);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x902,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)0x8000FFFFLL,
          v59);
        return 2147549183LL;
      }
    }
    TranscriptFilePathExpanded = (_QWORD *)Microsoft::Diagnostics::EventTranscriptManager::GetTranscriptFilePathExpanded(
                                             v4,
                                             v70);
    std::wstring::wstring((__int64)pszPath, TranscriptFilePathExpanded);
    v12 = (const WCHAR *)pszPath;
    if ( pszPath[3] > (LPCWSTR)7 )
      v12 = pszPath[0];
    v66 = (const char *)v7;
    v13 = (__int64)v7;
    *(_QWORD *)&v64 = v7;
    if ( PathFileExistsW(v12) )
    {
      try
      {
        v60 = 65792;
        v62 = (char *)v4 + 2192;
        std::_Mutex_base::lock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
        v14 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(
                           v65,
                           pszPath,
                           &v60);
        std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(
          (__int64)v7,
          v14);
        std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(v65);
        _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
      }
      catch ( ... )
      {
        v54 = wil::ResultFromCaughtException(v15);
        v60 = v54;
        v55 = v67;
        std::_Mutex_base::lock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v67 + 2192));
        std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::reset((char *)v55 + 2272, 0);
        _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v55 + 2192));
        v56 = Microsoft::Diagnostics::EventTranscriptManager::TryDeleteStoreFiles(v55);
        v57 = v56;
        if ( v56 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x91D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)v56,
            v58);
          v60 = v57;
          goto LABEL_74;
        }
        if ( v54 >= 0 )
        {
          v13 = v64;
          v7 = (Microsoft::Diagnostics::SqlConnection **)v64;
          v4 = v67;
          goto LABEL_18;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x91F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v54,
          v58);
LABEL_74:
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        return v60;
      }
LABEL_18:
      Microsoft::Diagnostics::SqlConnection::UpdateWalJournalSize(*v7, 0, 0x3E8u);
      v16 = Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(v4);
      if ( v16 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x925,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v16,
          v59);
        Microsoft::Diagnostics::EventTranscriptManager::FinalizeStatements(v4);
        std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::reset(v13, 0);
        v17 = Microsoft::Diagnostics::EventTranscriptManager::TryDeleteStoreFiles(v4);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x92A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
            (const char *)(unsigned int)v17,
            v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
          return v18;
        }
        if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x100000) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803DDA8D);
      }
    }
    if ( *v7 )
    {
      v19 = 0;
    }
    else
    {
      v60 = 65793;
      v62 = (char *)v4 + 2192;
      std::_Mutex_base::lock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
      v20 = (__int64 *)std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(
                         &v64,
                         pszPath,
                         &v60);
      std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(
        v13,
        v20);
      std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(&v64);
      _Mtx_unlock((Microsoft::Diagnostics::EventTranscriptManager *)((char *)v4 + 2192));
      v21 = Microsoft::Diagnostics::EventTranscriptManager::SetNewStoreConfiguration(v4);
      v22 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x941,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v21,
          v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        return v22;
      }
      v23 = Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(v4);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x942,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v23,
          v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        return v24;
      }
      v19 = 1;
    }
    v61 = v19;
    v64 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043C240, v65);
    v62 = "PRAGMA page_size;";
    v63 = 17;
    Microsoft::Diagnostics::SqliteStatement::SqliteStatement((__int64)v72, *v7, (__int64)&v62);
    v25 = Microsoft::Diagnostics::SqliteStatement::Bind<>(v72, &v62);
    Microsoft::Diagnostics::SqliteBoundStatement::Step(v25, v68);
    std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(&v62);
    if ( !v68[24] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x94E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
        (const char *)0x8000FFFFLL,
        v59);
      std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v68);
      Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v72);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
      return 2147549183LL;
    }
    *((_DWORD *)v4 + 384) = Microsoft::Diagnostics::SqliteQueryResult::Next<long>(v68);
    std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v68);
    Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v72);
    if ( !v19 )
    {
      v26 = (__int128 *)std::wstring::operator std::wstring_view(&unk_18043C240, v65);
      try
      {
        v64 = *v26;
        v62 = "PRAGMA page_count;";
        v63 = 18;
        Microsoft::Diagnostics::SqliteStatement::SqliteStatement((__int64)v74, *v7, (__int64)&v62);
        v27 = Microsoft::Diagnostics::SqliteStatement::Bind<>(v74, v68);
        Microsoft::Diagnostics::SqliteBoundStatement::Step(v27, v72);
        std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v68);
        v28 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v72);
        v64 = *(_OWORD *)std::wstring::operator std::wstring_view(&unk_18043C240, v65);
        v62 = "PRAGMA freelist_count;";
        v63 = 22;
        Microsoft::Diagnostics::SqliteStatement::SqliteStatement((__int64)v73, *v7, (__int64)&v62);
        v29 = Microsoft::Diagnostics::SqliteStatement::Bind<>(v73, v68);
        Microsoft::Diagnostics::SqliteBoundStatement::Step(v29, v69);
        std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(v68);
        *(_QWORD *)&v64 = Microsoft::Diagnostics::SqliteQueryResult::Next<unsigned __int64>(v69);
        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v69);
        Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v73);
        std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(v72);
        Microsoft::Diagnostics::SqliteStatement::~SqliteStatement((Microsoft::Diagnostics::SqliteStatement *)v74);
        v60 = *((_DWORD *)v4 + 384);
        v30 = Microsoft::Diagnostics::DynamicConfig<unsigned long>::Get((char *)v4 + 1296);
        if ( v30 < 0x80 )
          v30 = 128;
        v31 = (unsigned __int64)v30 << 20;
        v65[0] = 0;
        Microsoft::Diagnostics::EventTranscriptManager::GetStoreFileSize(v4, v65);
        v33 = v65[0];
        if ( (v65[0] & 0x8000000000000000uLL) != 0LL )
          v34 = (double)(int)(v65[0] & 1 | (v65[0] >> 1)) + (double)(int)(v65[0] & 1 | (v65[0] >> 1));
        else
          v34 = (double)SLODWORD(v65[0]);
        if ( (v31 & 0x8000000000000000uLL) != 0LL )
          v35 = (double)(int)(v31 & 1 | (v31 >> 1)) + (double)(int)(v31 & 1 | (v31 >> 1));
        else
          v35 = (double)(int)v31;
        if ( v34 > v35 * 1.03 )
        {
          v36 = v60 * (v28 - v64);
          v37 = v36 < 0
              ? (float)(v36 & 1 | (unsigned int)((unsigned __int64)v36 >> 1))
              + (float)(v36 & 1 | (unsigned int)((unsigned __int64)v36 >> 1))
              : (float)(int)v36;
          v38 = (v31 & 0x8000000000000000uLL) != 0LL
              ? (float)(int)(v31 & 1 | (v31 >> 1)) + (float)(int)(v31 & 1 | (v31 >> 1))
              : (float)(int)v31;
          if ( (float)((float)(v38 / 100.0) * 80.0) > v37 )
          {
            v62 = "VACUUM;";
            v63 = 7;
            Microsoft::Diagnostics::SqlConnection::Exec(*v7, &v62);
            if ( (unsigned int)dword_18042D328 > 5 )
            {
              if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x100000) )
              {
                *(_QWORD *)&v64 = v31;
                v65[0] = v33;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                  v39,
                  (unsigned int)&unk_1803DD9F3,
                  v40,
                  (_DWORD)v32,
                  (__int64)v65,
                  (__int64)&v64);
              }
            }
          }
        }
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x986,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          v32);
        if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x100000) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            &dword_18042D328,
            &unk_1803DDA5A);
        v19 = v61;
        v7 = (Microsoft::Diagnostics::SqlConnection **)v66;
        v4 = v67;
      }
    }
    v62 = "PRAGMA foreign_keys = ON";
    v63 = 24;
    Microsoft::Diagnostics::SqlConnection::Exec(*v7, &v62);
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl);
    v42 = "CREATE TABLE IF NOT EXISTS events_persisted (\n"
          "                        sid                             TEXT,\n"
          "                        timestamp                       INTEGER,\n"
          "                        payload                         TEXT,\n"
          "                        full_event_name                 TEXT,\n"
          "                        full_event_name_hash            INTEGER,\n"
          "                        event_keywords                  INTEGER,\n"
          "                        is_core                         INTEGER,\n"
          "                        provider_group_id               INTEGER,\n"
          "                        logging_binary_name             TEXT,\n"
          "                        friendly_logging_binary_name    TEXT,\n"
          "                        compressed_payload_size         INTEGER,\n"
          "                        producer_id                     INTEGER,\n"
          "                        extra1                          TEXT,\n"
          "                        extra2                          TEXT,\n"
          "                        extra3                          TEXT,\n"
          "                        FOREIGN KEY(provider_group_id)  REFERENCES provider_groups(group_id),\n"
          "                        CONSTRAINT fk_producer_id\n"
          "                            FOREIGN KEY(producer_id)\n"
          "                            REFERENCES producers(producer_id)\n"
          "                            ON DELETE CASCADE);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_sid ON events_persisted(sid);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_full_event_name_hash ON events_persisted(f"
          "ull_event_name_hash);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_timestamp ON events_persisted(timestamp);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_logging_binary_name ON events_persisted(lo"
          "gging_binary_name);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_producer_id ON events_persisted(producer_i"
          "d);\n"
          "                    CREATE TABLE IF NOT EXISTS provider_groups (\n"
          "                        group_id                        INTEGER PRIMARY KEY AUTOINCREMENT,\n"
          "                        group_guid                      TEXT);\n"
          "                    CREATE TABLE IF NOT EXISTS event_tags (\n"
          "                        full_event_name_hash            INTEGER,\n"
          "                        tag_id                          INTEGER);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_event_tags_full_event_name_hash ON event_tags(full_event_na"
          "me_hash);\n"
          "                    CREATE TABLE IF NOT EXISTS tag_descriptions (\n"
          "                        tag_id                          INTEGER,\n"
          "                        locale_name                     TEXT,\n"
          "                        tag_name                        TEXT,\n"
          "                        description                     TEXT);\n"
          "                    CREATE TABLE IF NOT EXISTS producers (\n"
          "                        producer_id                     INTEGER PRIMARY KEY,\n"
          "                        producer_id_name                TEXT);\n"
          "                    CREATE TABLE IF NOT EXISTS event_categories (\n"
          "                        full_event_name_hash            INTEGER,\n"
          "                        category_id                     INTEGER,\n"
          "                        CONSTRAINT fk_category_id\n"
          "                            FOREIGN KEY(category_id)\n"
          "                            REFERENCES categories(category_id)\n"
          "                            ON DELETE CASCADE);\n"
          "                    CREATE INDEX IF NOT EXISTS idx_event_categories_full_event_name_hash ON event_categories(f"
          "ull_event_name_hash);\n"
          "                    CREATE TABLE IF NOT EXISTS categories (\n"
          "                        category_id                     INTEGER PRIMARY KEY AUTOINCREMENT,\n"
          "                        category_id_text                TEXT,\n"
          "                        producer_id                     INTEGER,\n"
          "                        CONSTRAINT fk_producer_id\n"
          "                            FOREIGN KEY(producer_id)\n"
          "                            REFERENCES producers(producer_id)\n"
          "                            ON DELETE CASCADE);\n"
          "                    ";
    if ( !IsEnabled )
      v42 = "CREATE TABLE IF NOT EXISTS events_persisted (\n"
            "                        sid                             TEXT,\n"
            "                        timestamp                       INTEGER,\n"
            "                        payload                         TEXT,\n"
            "                        full_event_name                 TEXT,\n"
            "                        full_event_name_hash            INTEGER,\n"
            "                        event_keywords                  INTEGER,\n"
            "                        is_core                         INTEGER,\n"
            "                        provider_group_id               INTEGER,\n"
            "                        logging_binary_name             TEXT,\n"
            "                        friendly_logging_binary_name    TEXT,\n"
            "                        compressed_payload_size         INTEGER,\n"
            "                        producer_id                     INTEGER,\n"
            "                        extra1                          TEXT,\n"
            "                        extra2                          TEXT,\n"
            "                        extra3                          TEXT,\n"
            "                        FOREIGN KEY(provider_group_id)  REFERENCES provider_groups(group_id),\n"
            "                        CONSTRAINT fk_producer_id\n"
            "                            FOREIGN KEY(producer_id)\n"
            "                            REFERENCES producers(producer_id)\n"
            "                            ON DELETE CASCADE);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_sid ON events_persisted(sid);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_full_event_name_hash ON events_persisted"
            "(full_event_name_hash);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_timestamp ON events_persisted(timestamp)"
            ";\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_logging_binary_name ON events_persisted("
            "logging_binary_name);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_events_persisted_producer_id ON events_persisted(producer"
            "_id);\n"
            "                    CREATE TABLE IF NOT EXISTS provider_groups (\n"
            "                        group_id                        INTEGER PRIMARY KEY AUTOINCREMENT,\n"
            "                        group_guid                      TEXT);\n"
            "                    CREATE TABLE IF NOT EXISTS event_tags (\n"
            "                        full_event_name_hash            INTEGER,\n"
            "                        tag_id                          INTEGER);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_event_tags_full_event_name_hash ON event_tags(full_event_"
            "name_hash);\n"
            "                    CREATE TABLE IF NOT EXISTS tag_descriptions (\n"
            "                        tag_id                          INTEGER,\n"
            "                        locale_name                     TEXT,\n"
            "                        tag_name                        TEXT,\n"
            "                        description                     TEXT);\n"
            "                    CREATE TABLE IF NOT EXISTS producers (\n"
            "                        producer_id                     INTEGER PRIMARY KEY AUTOINCREMENT,\n"
            "                        producer_id_text                TEXT);\n"
            "                    CREATE TABLE IF NOT EXISTS event_categories (\n"
            "                        full_event_name_hash            INTEGER,\n"
            "                        category_id                     INTEGER,\n"
            "                        CONSTRAINT fk_category_id\n"
            "                            FOREIGN KEY(category_id)\n"
            "                            REFERENCES categories(category_id)\n"
            "                            ON DELETE CASCADE);\n"
            "                    CREATE INDEX IF NOT EXISTS idx_event_categories_full_event_name_hash ON event_categories"
            "(full_event_name_hash);\n"
            "                    CREATE TABLE IF NOT EXISTS categories (\n"
            "                        category_id                     INTEGER PRIMARY KEY AUTOINCREMENT,\n"
            "                        category_id_text                TEXT,\n"
            "                        producer_id                     INTEGER,\n"
            "                        CONSTRAINT fk_producer_id\n"
            "                            FOREIGN KEY(producer_id)\n"
            "                            REFERENCES producers(producer_id)\n"
            "                            ON DELETE CASCADE);\n"
            "                    ";
    v43 = -1;
    do
      ++v43;
    while ( v42[v43] );
    v62 = v42;
    v63 = v43;
    Microsoft::Diagnostics::SqlConnection::Exec(*v7, &v62);
    if ( v19 )
    {
      v44 = Microsoft::Diagnostics::EventTranscriptManager::PrePopulateProviderGroups(v4);
      v45 = v44;
      if ( v44 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0C,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v44,
          v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        return v45;
      }
      v46 = Microsoft::Diagnostics::EventTranscriptManager::PrePopulateProducers(v4);
      v47 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA0D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v46,
          v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        return v47;
      }
    }
    else
    {
      v48 = Microsoft::Diagnostics::EventTranscriptManager::CacheCategoryIds(v4);
      v49 = v48;
      if ( v48 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA12,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v48,
          v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        return v49;
      }
    }
    v50 = Microsoft::Diagnostics::EventTranscriptManager::CacheGroupIds(v4);
    v51 = v50;
    if ( v50 >= 0 )
    {
      v52 = Microsoft::Diagnostics::EventTranscriptManager::CacheProducerIds(v4);
      v53 = v52;
      if ( v52 >= 0 )
      {
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA16,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
          (const char *)(unsigned int)v52,
          v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
        result = v53;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA15,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
        (const char *)(unsigned int)v50,
        v59);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
      result = v51;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA18,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\eventtranscriptmanager.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1802d4fb4  mov     [rsp+arg_8], rbx
0x1802d4fb9  mov     [rsp+arg_10], rsi
0x1802d4fbe  push    rdi
0x1802d4fbf  push    r12
0x1802d4fc1  push    r13
0x1802d4fc3  push    r14
0x1802d4fc5  push    r15
0x1802d4fc7  sub     rsp, 1A0h
0x1802d4fce  mov     rax, cs:__security_cookie
0x1802d4fd5  xor     rax, rsp
0x1802d4fd8  mov     [rsp+1C8h+var_38], rax
0x1802d4fe0  mov     rdi, rcx
0x1802d4fe3  mov     [rsp+1C8h+var_140], rcx
0x1802d4feb  mov     al, [rcx+7BDh]
0x1802d4ff1  nop
0x1802d4ff2  xor     ebx, ebx
0x1802d4ff4  test    al, al
0x1802d4ff6  jnz     loc_1802D597B
0x1802d4ffc  mov     al, [rcx+7BCh]
0x1802d5002  nop
0x1802d5003  test    al, al
0x1802d5005  jnz     short loc_1802D502F
0x1802d5007  mov     rcx, [rsp+1C8h]; this
0x1802d500f  mov     ebx, 80070426h
0x1802d5014  mov     r9d, ebx; char *
0x1802d5017  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d501e  mov     edx, 8F8h; void *
0x1802d5023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d5028  mov     eax, ebx
0x1802d502a  jmp     loc_1802D5947
0x1802d502f  lea     rsi, [rcx+8E0h]
0x1802d5036  cmp     [rsi], rbx
0x1802d5039  jz      loc_1802D5105
0x1802d503f  mov     eax, cs:dword_18042D328
0x1802d5045  cmp     eax, 2
0x1802d5048  jbe     short loc_1802D5088
0x1802d504a  lea     rax, aInitializestor; "InitializeStore"
0x1802d5051  mov     [rsp+1C8h+var_148], rax
0x1802d5059  lea     rax, aMDbpersistconn; "m_dbPersistConnection == nullptr"
0x1802d5060  mov     [rsp+1C8h+var_158], rax
0x1802d5065  lea     rax, [rsp+1C8h+var_148]
0x1802d506d  mov     [rsp+1C8h+var_1A0], rax
0x1802d5072  lea     rax, [rsp+1C8h+var_158]
0x1802d5077  mov     qword ptr [rsp+1C8h+var_1A8], rax; int
0x1802d507c  lea     rdx, unk_1803DDB0E
0x1802d5083  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1802d5088  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1802d508f  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x1802d5094  test    al, al
0x1802d5096  jz      short loc_1802D50A5
0x1802d5098  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x1802d509d  mov     rcx, rax; this
0x1802d50a0  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1802d50a5  cmp     [rsi], rbx
0x1802d50a8  jz      short loc_1802D5105
0x1802d50aa  mov     eax, cs:dword_18042D328
0x1802d50b0  cmp     eax, 5
0x1802d50b3  jbe     short loc_1802D50DD
0x1802d50b5  mov     edx, 100000h
0x1802d50ba  lea     rcx, dword_18042D328
0x1802d50c1  call    _tlgKeywordOn
0x1802d50c6  test    al, al
0x1802d50c8  jz      short loc_1802D50DD
0x1802d50ca  lea     rdx, unk_1803DD9C1
0x1802d50d1  lea     rcx, dword_18042D328
0x1802d50d8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1802d50dd  mov     rcx, [rsp+1C8h]; this
0x1802d50e5  mov     ebx, 8000FFFFh
0x1802d50ea  mov     r9d, ebx; char *
0x1802d50ed  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d50f4  mov     edx, 902h; void *
0x1802d50f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d50fe  mov     eax, ebx
0x1802d5100  jmp     loc_1802D5947
0x1802d5105  lea     rdx, [rsp+1C8h+var_F8]
0x1802d510d  mov     rcx, rdi
0x1802d5110  call    ?GetTranscriptFilePathExpanded@EventTranscriptManager@Diagnostics@Microsoft@@AEAA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::EventTranscriptManager::GetTranscriptFilePathExpanded(void)
0x1802d5115  mov     rdx, rax
0x1802d5118  lea     rcx, [rsp+1C8h+pszPath]
0x1802d5120  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1802d5125  nop
0x1802d5126  lea     rcx, [rsp+1C8h+pszPath]
0x1802d512e  cmp     [rsp+1C8h+var_D0], 7
0x1802d5137  cmova   rcx, [rsp+1C8h+pszPath]; pszPath
0x1802d5140  mov     [rsp+1C8h+var_148], rsi
0x1802d5148  mov     r15, rsi
0x1802d514b  mov     qword ptr [rsp+1C8h+var_168], rsi
0x1802d5150  call    cs:__imp_PathFileExistsW
0x1802d5157  nop     dword ptr [rax+rax+00h]
0x1802d515c  test    eax, eax
0x1802d515e  jz      loc_1802D52C0
0x1802d5164  mov     [rsp+1C8h+var_198], 10100h
0x1802d516c  lea     r14, [rdi+890h]
0x1802d5173  mov     [rsp+1C8h+var_188], r14
0x1802d5178  mov     rcx, r14; this
0x1802d517b  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802d5180  nop
0x1802d5181  lea     r8, [rsp+1C8h+var_198]
0x1802d5186  lea     rdx, [rsp+1C8h+pszPath]
0x1802d518e  lea     rcx, [rsp+1C8h+var_158]
0x1802d5193  call    ??$make_unique@VSqlConnection@Diagnostics@Microsoft@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUOptions@123@$0A@@std@@YA?AV?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAUOptions@SqlConnection@Diagnostics@Microsoft@@@Z; std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &)
0x1802d5198  mov     rdx, rax
0x1802d519b  mov     rcx, rsi
0x1802d519e  call    ??$?4U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@$0A@@?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(std::unique_ptr<Microsoft::Diagnostics::SqlConnection> &&)
0x1802d51a3  lea     rcx, [rsp+1C8h+var_158]
0x1802d51a8  call    ??1?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(void)
0x1802d51ad  nop
0x1802d51ae  mov     rcx, r14; _Mtx_t
0x1802d51b1  call    cs:__imp__Mtx_unlock
0x1802d51b8  nop     dword ptr [rax+rax+00h]
0x1802d51bd  nop
0x1802d51be  jmp     short loc_1802D51FE
0x1802d51c0  lea     rcx, [rsp+1C8h+pszPath]; this
0x1802d51c8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802d51cd  mov     eax, [rsp+1C8h+var_198]
0x1802d51d1  jmp     loc_1802D5947
0x1802d51d6  lea     rcx, [rsp+1C8h+pszPath]; this
0x1802d51de  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802d51e3  mov     eax, [rsp+1C8h+var_198]
0x1802d51e7  jmp     loc_1802D5947
0x1802d51ec  xor     ebx, ebx
0x1802d51ee  mov     r15, qword ptr [rsp+1C8h+var_168]
0x1802d51f3  mov     rsi, r15
0x1802d51f6  mov     rdi, [rsp+1C8h+var_140]
0x1802d51fe  xor     edx, edx; unsigned int
0x1802d5200  mov     r8d, 3E8h; unsigned int
0x1802d5206  mov     rcx, [rsi]; this
0x1802d5209  call    ?UpdateWalJournalSize@SqlConnection@Diagnostics@Microsoft@@QEAAXKK@Z; Microsoft::Diagnostics::SqlConnection::UpdateWalJournalSize(ulong,ulong)
0x1802d520e  mov     rcx, rdi; this
0x1802d5211  call    ?VerifyStoreConfiguration@EventTranscriptManager@Diagnostics@Microsoft@@AEBAJXZ; Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(void)
0x1802d5216  mov     rcx, [rsp+1C8h]; this
0x1802d521e  test    eax, eax
0x1802d5220  jns     loc_1802D52C0
0x1802d5226  mov     r9d, eax; char *
0x1802d5229  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d5230  mov     edx, 925h; void *
0x1802d5235  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1802d523a  mov     rcx, rdi; this
0x1802d523d  call    ?FinalizeStatements@EventTranscriptManager@Diagnostics@Microsoft@@AEAAXXZ; Microsoft::Diagnostics::EventTranscriptManager::FinalizeStatements(void)
0x1802d5242  xor     edx, edx
0x1802d5244  mov     rcx, r15
0x1802d5247  call    ?reset@?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAAXPEAVSqlConnection@Diagnostics@Microsoft@@@Z; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::reset(Microsoft::Diagnostics::SqlConnection *)
0x1802d524c  mov     rcx, rdi; this
0x1802d524f  call    ?TryDeleteStoreFiles@EventTranscriptManager@Diagnostics@Microsoft@@AEAAJXZ; Microsoft::Diagnostics::EventTranscriptManager::TryDeleteStoreFiles(void)
0x1802d5254  mov     r14d, eax
0x1802d5257  test    eax, eax
0x1802d5259  jns     short loc_1802D528D
0x1802d525b  mov     rcx, [rsp+1C8h]; this
0x1802d5263  mov     r9d, eax; char *
0x1802d5266  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d526d  mov     edx, 92Ah; void *
0x1802d5272  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d5277  nop
0x1802d5278  lea     rcx, [rsp+1C8h+pszPath]; this
0x1802d5280  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802d5285  mov     eax, r14d
0x1802d5288  jmp     loc_1802D5947
0x1802d528d  mov     eax, cs:dword_18042D328
0x1802d5293  cmp     eax, 5
0x1802d5296  jbe     short loc_1802D52C0
0x1802d5298  mov     edx, 100000h
0x1802d529d  lea     rcx, dword_18042D328
0x1802d52a4  call    _tlgKeywordOn
0x1802d52a9  test    al, al
0x1802d52ab  jz      short loc_1802D52C0
0x1802d52ad  lea     rdx, unk_1803DDA8D
0x1802d52b4  lea     rcx, dword_18042D328
0x1802d52bb  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1802d52c0  cmp     [rsi], rbx
0x1802d52c3  jz      short loc_1802D52CD
0x1802d52c5  mov     r13b, bl
0x1802d52c8  jmp     loc_1802D53AB
0x1802d52cd  mov     [rsp+1C8h+var_198], 10101h
0x1802d52d5  lea     r14, [rdi+890h]
0x1802d52dc  mov     [rsp+1C8h+var_188], r14
0x1802d52e1  mov     rcx, r14; this
0x1802d52e4  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1802d52e9  nop
0x1802d52ea  lea     r8, [rsp+1C8h+var_198]
0x1802d52ef  lea     rdx, [rsp+1C8h+pszPath]
0x1802d52f7  lea     rcx, [rsp+1C8h+var_168]
0x1802d52fc  call    ??$make_unique@VSqlConnection@Diagnostics@Microsoft@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAUOptions@123@$0A@@std@@YA?AV?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@0@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEAUOptions@SqlConnection@Diagnostics@Microsoft@@@Z; std::make_unique<Microsoft::Diagnostics::SqlConnection,std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &,0>(std::wstring &,Microsoft::Diagnostics::SqlConnection::Options &)
0x1802d5301  mov     rdx, rax
0x1802d5304  mov     rcx, r15
0x1802d5307  call    ??$?4U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@$0A@@?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::operator=<std::default_delete<Microsoft::Diagnostics::SqlConnection>,0>(std::unique_ptr<Microsoft::Diagnostics::SqlConnection> &&)
0x1802d530c  lea     rcx, [rsp+1C8h+var_168]
0x1802d5311  call    ??1?$unique_ptr@VSqlConnection@Diagnostics@Microsoft@@U?$default_delete@VSqlConnection@Diagnostics@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Diagnostics::SqlConnection>::~unique_ptr<Microsoft::Diagnostics::SqlConnection>(void)
0x1802d5316  nop
0x1802d5317  mov     rcx, r14; _Mtx_t
0x1802d531a  call    cs:__imp__Mtx_unlock
0x1802d5321  nop     dword ptr [rax+rax+00h]
0x1802d5326  mov     rcx, rdi; this
0x1802d5329  call    ?SetNewStoreConfiguration@EventTranscriptManager@Diagnostics@Microsoft@@AEBAJXZ; Microsoft::Diagnostics::EventTranscriptManager::SetNewStoreConfiguration(void)
0x1802d532e  mov     r14d, eax
0x1802d5331  test    eax, eax
0x1802d5333  jns     short loc_1802D5367
0x1802d5335  mov     rcx, [rsp+1C8h]; this
0x1802d533d  mov     r9d, eax; char *
0x1802d5340  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d5347  mov     edx, 941h; void *
0x1802d534c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d5351  nop
0x1802d5352  lea     rcx, [rsp+1C8h+pszPath]; this
0x1802d535a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802d535f  mov     eax, r14d
0x1802d5362  jmp     loc_1802D5947
0x1802d5367  mov     rcx, rdi; this
0x1802d536a  call    ?VerifyStoreConfiguration@EventTranscriptManager@Diagnostics@Microsoft@@AEBAJXZ; Microsoft::Diagnostics::EventTranscriptManager::VerifyStoreConfiguration(void)
0x1802d536f  mov     r14d, eax
0x1802d5372  test    eax, eax
0x1802d5374  jns     short loc_1802D53A8
0x1802d5376  mov     rcx, [rsp+1C8h]; this
0x1802d537e  mov     r9d, eax; char *
0x1802d5381  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d5388  mov     edx, 942h; void *
0x1802d538d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d5392  nop
0x1802d5393  lea     rcx, [rsp+1C8h+pszPath]; this
0x1802d539b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802d53a0  mov     eax, r14d
0x1802d53a3  jmp     loc_1802D5947
0x1802d53a8  mov     r13b, 1
0x1802d53ab  mov     [rsp+1C8h+var_194], r13b
0x1802d53b0  lea     rdx, [rsp+1C8h+var_158]
0x1802d53b5  lea     r14, unk_18043C240
0x1802d53bc  mov     rcx, r14
0x1802d53bf  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802d53c4  movups  xmm0, xmmword ptr [rax]
0x1802d53c7  movdqu  [rsp+1C8h+var_168], xmm0
0x1802d53cd  lea     rax, aPragmaPageSize; "PRAGMA page_size;"
0x1802d53d4  mov     [rsp+1C8h+var_188], rax
0x1802d53d9  mov     [rsp+1C8h+var_180], 11h
0x1802d53e2  lea     r9, [rsp+1C8h+var_168]
0x1802d53e7  lea     r8, [rsp+1C8h+var_188]
0x1802d53ec  mov     rdx, [rsi]
0x1802d53ef  lea     rcx, [rsp+1C8h+var_C8]
0x1802d53f7  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802d53fc  nop
0x1802d53fd  lea     rdx, [rsp+1C8h+var_188]
0x1802d5402  lea     rcx, [rsp+1C8h+var_C8]
0x1802d540a  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x1802d540f  nop
0x1802d5410  lea     rdx, [rsp+1C8h+var_138]
0x1802d5418  mov     rcx, rax
0x1802d541b  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x1802d5420  nop
0x1802d5421  lea     rcx, [rsp+1C8h+var_188]; void *
0x1802d5426  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
0x1802d542b  cmp     [rsp+1C8h+var_120], bl
0x1802d5432  jnz     short loc_1802D5485
0x1802d5434  mov     rcx, [rsp+1C8h]; this
0x1802d543c  mov     ebx, 8000FFFFh
0x1802d5441  mov     r9d, ebx; char *
0x1802d5444  lea     r8, aOnecoreBaseTel_215; "onecore\\base\\telemetry\\utc\\service"...
0x1802d544b  mov     edx, 94Eh; void *
0x1802d5450  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802d5455  lea     rcx, [rsp+1C8h+var_138]
0x1802d545d  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d5462  nop
0x1802d5463  lea     rcx, [rsp+1C8h+var_C8]; this
0x1802d546b  call    ??1SqliteStatement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::SqliteStatement::~SqliteStatement(void)
0x1802d5470  nop
0x1802d5471  lea     rcx, [rsp+1C8h+pszPath]; this
0x1802d5479  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802d547e  mov     eax, ebx
0x1802d5480  jmp     loc_1802D5947
0x1802d5485  lea     rcx, [rsp+1C8h+var_138]
0x1802d548d  call    ??$Next@J@SqliteQueryResult@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::SqliteQueryResult::Next<long>(void)
0x1802d5492  mov     [rdi+600h], eax
0x1802d5498  lea     rcx, [rsp+1C8h+var_138]
0x1802d54a0  call    ??1?$_Optional_destruct_base@VSqliteQueryResult@Diagnostics@Microsoft@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>::~_Optional_destruct_base<Microsoft::Diagnostics::SqliteQueryResult,0>(void)
0x1802d54a5  nop
0x1802d54a6  lea     rcx, [rsp+1C8h+var_C8]; this
0x1802d54ae  call    ??1SqliteStatement@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::SqliteStatement::~SqliteStatement(void)
0x1802d54b3  test    r13b, r13b
0x1802d54b6  jnz     loc_1802D579B
0x1802d54bc  lea     rdx, [rsp+1C8h+var_158]
0x1802d54c1  mov     rcx, r14
0x1802d54c4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802d54c9  movups  xmm0, xmmword ptr [rax]
0x1802d54cc  movdqu  [rsp+1C8h+var_168], xmm0
0x1802d54d2  lea     rax, aPragmaPageCoun; "PRAGMA page_count;"
0x1802d54d9  mov     [rsp+1C8h+var_188], rax
0x1802d54de  mov     [rsp+1C8h+var_180], 12h
0x1802d54e7  lea     r9, [rsp+1C8h+var_168]
0x1802d54ec  lea     r8, [rsp+1C8h+var_188]
0x1802d54f1  mov     rdx, [rsi]
0x1802d54f4  lea     rcx, [rsp+1C8h+var_68]
0x1802d54fc  call    ??$?0$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUsqlite3@@$$A6AXPEAU1@@Z$1?sqlite_close_wrapper@wilp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@@Z; Microsoft::Diagnostics::SqliteStatement::SqliteStatement(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<sqlite3 *,void (sqlite3 *),&wilp::sqlite_close_wrapper(sqlite3 *),wistd::integral_constant<unsigned __int64,0>,sqlite3 *,sqlite3 *,0,std::nullptr_t>>> const &,std::string_view,std::wstring_view)
0x1802d5501  nop
0x1802d5502  lea     rdx, [rsp+1C8h+var_138]
0x1802d550a  lea     rcx, [rsp+1C8h+var_68]
0x1802d5512  call    ??$Bind@$$V@SqliteStatement@Diagnostics@Microsoft@@QEAA?AVSqliteBoundStatement@12@XZ; Microsoft::Diagnostics::SqliteStatement::Bind<>(void)
0x1802d5517  nop
0x1802d5518  lea     rdx, [rsp+1C8h+var_C8]
0x1802d5520  mov     rcx, rax
0x1802d5523  call    ?Step@SqliteBoundStatement@Diagnostics@Microsoft@@QEAA?AV?$optional@VSqliteQueryResult@Diagnostics@Microsoft@@@std@@XZ; Microsoft::Diagnostics::SqliteBoundStatement::Step(void)
0x1802d5528  nop
0x1802d5529  lea     rcx, [rsp+1C8h+var_138]; void *
0x1802d5531  call    ??1?$shared_ptr@$$CBUProviderGroupInfo@Diagnostics@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>::~shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>(void)
  ... truncated ...
```
