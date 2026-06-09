# Microsoft::Diagnostics::UtcApiManager::StartCustomTrace(wchar_t const *,unsigned __int64)

- ea: `0x1801e2640`
- end: `0x1801e3067`
- name: `?StartCustomTrace@UtcApiManager@Diagnostics@Microsoft@@UEBAJPEB_W_K@Z`
- size: `2599`
- prototype: `int(Microsoft::Diagnostics::UtcApiManager *__hidden this, const wchar_t *, unsigned __int64)`
- caller_count: `0`
- callee_count: `44`
- tags: `reparse_path, service_task, broker_com_uri`

## callees

- `0x180001e90`
- `0x18000409c`
- `0x18000434c`
- `0x180015884`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x1800326cc`
- `0x180032718`
- `0x180038870`
- `0x180048ff4`
- `0x1800494d0`
- `0x1800498f0`
- `0x18004ab70`
- `0x18004be40`
- `0x18004fb30`
- `0x18005d050`
- `0x18007fae8`
- `0x1800862cc`
- `0x18008630c`
- `0x18008637c`
- `0x18008fe88`
- `0x1800906f0`
- `0x1800907a8`
- `0x1800908f0`
- `0x180091524`
- `0x1800a0d08`
- `0x1800bef80`
- `0x1800d0d9c`
- `0x1800f4db8`
- `0x18012de40`
- `0x18012eae4`
- `0x1801cfb18`
- `0x1801d1518`
- `0x1801d2b74`
- `0x1801d3194`
- `0x1801e0758`
- `0x1801e240c`
- `0x1801e2640`
- `0x1801e3070`
- `0x18022a6b8`
- `0x18026189c`
- `0x180261b50`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801e27a1`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x1801e27a1`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801e2b5f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1801e2b5f`

## string_xrefs

- `0x1801e26b2`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2727`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e27c1`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e28fd`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2983`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2b7c`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2e90`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2f3a`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e2fdd`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1801e303a`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1801e3054`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::StartCustomTrace(
        Microsoft::Diagnostics::UtcApiManager *this,
        const wchar_t *a2,
        __int64 a3)
{
  WCHAR *v6; // rcx
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // r8d
  int v10; // r9d
  WCHAR *v11; // rax
  unsigned int v12; // ebx
  struct Microsoft::Diagnostics::TraceManager *TraceManager; // r13
  __int64 v14; // rdx
  const struct _GUID *v15; // rdx
  struct _GUID *OwnerScenarioId; // rax
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdx
  unsigned __int64 OwnerTraceProfileHash; // rax
  __int64 v21; // rdx
  HRESULT v22; // eax
  unsigned int v23; // ebx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  unsigned int v27; // ebx
  __int64 v28; // r8
  const char *v29; // r9
  __int64 v30; // rdx
  __int16 v31; // ax
  unsigned __int8 *v32; // r15
  std::_Ref_count_base *v33; // rbx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // r12d
  __int64 v37; // rax
  const char *v38; // r9
  __int64 NamespaceHash; // rax
  __int64 v40; // rcx
  __int64 v41; // rdx
  int started; // eax
  Microsoft::Diagnostics::UtcApiManager *v43; // rcx
  unsigned int v44; // edi
  int v45; // eax
  unsigned __int64 *v46; // [rsp+20h] [rbp-158h]
  __int64 v47; // [rsp+28h] [rbp-150h]
  __int64 v48; // [rsp+50h] [rbp-128h] BYREF
  char *v49; // [rsp+58h] [rbp-120h]
  unsigned __int64 v50[2]; // [rsp+60h] [rbp-118h] BYREF
  unsigned __int8 *v51; // [rsp+70h] [rbp-108h] BYREF
  std::_Ref_count_base *v52; // [rsp+78h] [rbp-100h]
  _BYTE v53[16]; // [rsp+80h] [rbp-F8h] BYREF
  __int64 v54; // [rsp+90h] [rbp-E8h] BYREF
  _BYTE v55[24]; // [rsp+98h] [rbp-E0h] BYREF
  __int128 v56; // [rsp+B0h] [rbp-C8h] BYREF
  struct _GUID v57; // [rsp+C0h] [rbp-B8h] BYREF
  _QWORD v58[3]; // [rsp+D0h] [rbp-A8h] BYREF
  char v59; // [rsp+E8h] [rbp-90h]
  WCHAR Src[8]; // [rsp+F0h] [rbp-88h] BYREF
  __int64 v61; // [rsp+100h] [rbp-78h]
  unsigned __int64 v62; // [rsp+108h] [rbp-70h]
  PWSTR pszPathOut[4]; // [rsp+110h] [rbp-68h] BYREF
  GUID pguid; // [rsp+130h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  v48 = 60000;
  std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(v53, (char *)this + 384, &v48);
  if ( !v53[8] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC48,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x87C5102BLL,
      (int)v46);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return 2277838891LL;
  }
  if ( !a2 || !*a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      (int)v46);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return 2147942487LL;
  }
  std::wstring::wstring(Src);
  if ( std::wstring::find_first_of(Src, 47, 0) != -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC54,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      (int)v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return 2147942487LL;
  }
  std::wstring::wstring(pszPathOut, v61, 0);
  v6 = (WCHAR *)pszPathOut;
  if ( pszPathOut[3] > (PWSTR)7 )
    v6 = pszPathOut[0];
  if ( PathCchCanonicalizeEx(v6, (size_t)pszPathOut[2] + 1, a2, 1u) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)0x80070057LL,
      (int)v46);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return 2147942487LL;
  }
  std::wstring::operator=(Src, pszPathOut);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(Src);
  std::string::string(pszPathOut);
  v56 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, &v57);
  v8 = Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(&v56, v7, 0xFFFFFFFFLL, pszPathOut);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_18042D328 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
    {
      LODWORD(v48) = v8;
      v11 = Src;
      if ( v62 > 7 )
        v11 = *(WCHAR **)Src;
      v50[0] = (unsigned __int64)v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C8699,
        v9,
        v10,
        (__int64)v50,
        (__int64)&v48);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC70,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v8,
      (int)v46);
    std::string::_Tidy_deallocate(pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return (unsigned int)v8;
  }
  v54 = 10000000 * a3;
  if ( (unsigned __int64)(10000000 * a3) > 0x58028E44000LL )
    v54 = 6048000000000LL;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BF60, 0, 0) )
  {
    v12 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0xC7B,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
            (const char *)0x15,
            (unsigned int)v46);
    std::string::_Tidy_deallocate(pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return v12;
  }
  TraceManager = Microsoft::Diagnostics::LifetimeManager::GetTraceManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
  LOBYTE(v14) = 0;
  Microsoft::Diagnostics::ITraceProfileDef::Create(&v51, v14);
  Microsoft::Diagnostics::ITraceProfileDef::SetProfile(v51, pszPathOut);
  (*(void (__fastcall **)(unsigned __int8 *, _QWORD))(*(_QWORD *)v51 + 16LL))(v51, 0);
  v48 = *((_QWORD *)TraceManager + 2);
  v49 = (char *)TraceManager + 272;
  v50[0] = (**(__int64 (__fastcall ***)(unsigned __int8 *))v51)(v51);
  if ( Microsoft::Diagnostics::TraceSlotSafeWrapper::IsSlotOwned(
         (Microsoft::Diagnostics::TraceSlotSafeWrapper *)&v48,
         v15,
         v50) )
  {
    if ( v52 )
      std::_Ref_count_base::_Decref(v52);
LABEL_25:
    std::string::_Tidy_deallocate(pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return 0;
  }
  OwnerScenarioId = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerScenarioId(
                      (Microsoft::Diagnostics::TraceSlotSafeWrapper *)&v48,
                      &v57);
  if ( !memcmp_0(OwnerScenarioId, &Microsoft::Diagnostics::UtcApiManager::k_customTraceId, 0x10u) )
  {
    if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
    {
      v50[0] = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash((Microsoft::Diagnostics::TraceSlotSafeWrapper *)&v48);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(
        (unsigned int)&dword_18042D328,
        (unsigned int)&unk_1803C863F,
        v17,
        v18,
        (__int64)v50);
    }
    v50[0] = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash((Microsoft::Diagnostics::TraceSlotSafeWrapper *)&v48);
    LOBYTE(v19) = 0;
    v46 = v50;
    Microsoft::Diagnostics::TraceManager::StopSlotTrace(
      TraceManager,
      v19,
      &Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
      &GUID_NULL);
    OwnerTraceProfileHash = Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash((Microsoft::Diagnostics::TraceSlotSafeWrapper *)&v48);
    LOBYTE(v21) = 0;
    Microsoft::Diagnostics::TraceManager::RemoveTrace(
      TraceManager,
      v21,
      &Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
      OwnerTraceProfileHash);
  }
  pguid = 0;
  v22 = CoCreateGuid(&pguid);
  v23 = v22;
  if ( v22 >= 0 )
  {
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 0x2000) )
    {
      v50[0] = v54;
      v48 = (**(__int64 (__fastcall ***)(unsigned __int8 *))v51)(v51);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v24,
        (unsigned int)&unk_1803C85E8,
        v25,
        v26,
        (__int64)&v48,
        (__int64)v50);
    }
    v58[0] = &pguid;
    v58[1] = &v51;
    v58[2] = &v54;
    v59 = 1;
    LOWORD(v50[0]) = 0;
    BYTE2(v50[0]) = 0;
    WORD2(v50[0]) = 0;
    LODWORD(v50[1]) = 0;
    v27 = v51[16];
    v28 = (**(__int64 (__fastcall ***)(unsigned __int8 *))v51)(v51);
    v30 = v27;
    if ( (_BYTE)v27 )
    {
      v30 = v27 - 1;
      if ( v27 == 1 )
      {
        v31 = 44;
      }
      else
      {
        if ( v27 != 2 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3C2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v29);
        v31 = 45;
      }
    }
    else
    {
      v31 = 43;
    }
    LOBYTE(v30) = 0;
    LOWORD(v48) = v31;
    *(_DWORD *)((char *)&v48 + 2) = *(_DWORD *)((char *)&v56 + 2);
    HIWORD(v48) = WORD3(v56);
    v49 = (char *)v28;
    LOBYTE(v47) = 1;
    Microsoft::Diagnostics::TraceManager::AddTrace(
      TraceManager,
      v30,
      &Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
      &v48);
    v32 = v51;
    v33 = v52;
    if ( v52 )
    {
      _InterlockedIncrement((volatile signed __int32 *)v52 + 2);
      v33 = v52;
    }
    *(_QWORD *)&v56 = v32;
    *((_QWORD *)&v56 + 1) = v33;
    std::_Tree<std::_Tset_traits<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>,0>>::_Tree<std::_Tset_traits<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>,0>>(v55);
    v50[0] = std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
               &v57,
               &v56,
               v34,
               v35);
    v36 = v32[16];
    v37 = (**(__int64 (__fastcall ***)(unsigned __int8 *))v32)(v32);
    if ( (_BYTE)v36 )
    {
      if ( v36 == 1 )
      {
        LOWORD(v48) = 44;
      }
      else
      {
        if ( v36 != 2 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3C2,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v38);
        LOWORD(v48) = 45;
      }
    }
    else
    {
      LOWORD(v48) = 43;
    }
    v49 = (char *)v37;
    std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>(
      v55,
      v50,
      &v48,
      v50[0],
      6048000000000LL,
      v47);
    if ( *(_QWORD *)v57.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v57.Data4);
    Microsoft::Diagnostics::LifetimeManager::GetScenarioObjectCache((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    v57 = *(struct _GUID *)&Microsoft::Diagnostics::ScenarioStorageSql::k_reservedSqlNamespaceApiTraceProfilesFeature;
    *(_OWORD *)v50 = *(_OWORD *)&Microsoft::Diagnostics::ScenarioStorageSql::k_reservedSqlNamespaceInternalPartner;
    NamespaceHash = Microsoft::Diagnostics::ScenarioStorageSql::GetNamespaceHash(v50, &v57);
    Microsoft::Diagnostics::ScenarioObjectCache::FlushParsedObjectsToDb(v40, NamespaceHash, v55);
    v50[0] = (**(__int64 (__fastcall ***)(unsigned __int8 *))v51)(v51);
    LOBYTE(v41) = 0;
    started = Microsoft::Diagnostics::TraceManager::StartSlotTrace(
                TraceManager,
                v41,
                &Microsoft::Diagnostics::UtcApiManager::k_customTraceId,
                &pguid);
    v44 = started;
    if ( started >= 0 )
    {
      v45 = Microsoft::Diagnostics::UtcApiManager::StartAgentCustomTraces(v43);
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xCDC,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
          (const char *)(unsigned int)v45,
          (int)v50);
      std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>,void *>>>(
        v55,
        v55);
      if ( v33 )
        std::_Ref_count_base::_Decref(v33);
      if ( v59 )
      {
        v59 = 0;
        Microsoft::Diagnostics::UtcApiManager::StartCustomTrace_::_3_::_lambda_1_::operator()(v58);
      }
      if ( v52 )
        std::_Ref_count_base::_Decref(v52);
      goto LABEL_25;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCD9,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)started,
      (int)v50);
    std::_Tree_val<std::_Tree_simple_types<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>,void *>>>(
      v55,
      v55);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    if ( v59 )
    {
      v59 = 0;
      Microsoft::Diagnostics::UtcApiManager::StartCustomTrace_::_3_::_lambda_1_::operator()(v58);
    }
    if ( v52 )
      std::_Ref_count_base::_Decref(v52);
    std::string::_Tidy_deallocate(pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return v44;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA7,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)(unsigned int)v22,
      (int)v46);
    if ( v52 )
      std::_Ref_count_base::_Decref(v52);
    std::string::_Tidy_deallocate(pszPathOut);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v53);
    return v23;
  }
}

```

## disassembly

```asm
0x1801e2640  mov     [rsp+arg_10], rbx
0x1801e2645  mov     [rsp+arg_18], rsi
0x1801e264a  push    rdi
0x1801e264b  push    r12
0x1801e264d  push    r13
0x1801e264f  push    r14
0x1801e2651  push    r15
0x1801e2653  sub     rsp, 150h
0x1801e265a  mov     rax, cs:__security_cookie
0x1801e2661  xor     rax, rsp
0x1801e2664  mov     [rsp+178h+var_38], rax
0x1801e266c  mov     rdi, r8
0x1801e266f  mov     rbx, rdx
0x1801e2672  mov     [rsp+178h+var_128], 0EA60h
0x1801e267b  lea     rdx, [rcx+180h]
0x1801e2682  lea     r8, [rsp+178h+var_128]
0x1801e2687  lea     rcx, [rsp+178h+var_F8]
0x1801e268f  call    ??$?0_JU?$ratio@$00$0DOI@@std@@@?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@AEAVrecursive_timed_mutex@1@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(std::recursive_timed_mutex &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1801e2694  nop
0x1801e2695  xor     r12d, r12d
0x1801e2698  cmp     [rsp+178h+var_F0], r12b
0x1801e26a0  jnz     short loc_1801E26D8
0x1801e26a2  mov     rcx, [rsp+178h]; this
0x1801e26aa  mov     ebx, 87C5102Bh
0x1801e26af  mov     r9d, ebx; char *
0x1801e26b2  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e26b9  mov     edx, 0C48h; void *
0x1801e26be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e26c3  nop
0x1801e26c4  lea     rcx, [rsp+178h+var_F8]
0x1801e26cc  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801e26d1  mov     eax, ebx
0x1801e26d3  jmp     loc_1801E3004
0x1801e26d8  test    rbx, rbx
0x1801e26db  jz      loc_1801E2FCD
0x1801e26e1  cmp     [rbx], r12w
0x1801e26e5  jz      loc_1801E2FCD
0x1801e26eb  mov     rdx, rbx
0x1801e26ee  lea     rcx, [rsp+178h+Src]
0x1801e26f6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1801e26fb  nop
0x1801e26fc  mov     edx, 2Fh ; '/'
0x1801e2701  xor     r8d, r8d
0x1801e2704  lea     rcx, [rsp+178h+Src]
0x1801e270c  call    ?find_first_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_first_of(wchar_t,unsigned __int64)
0x1801e2711  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801e2715  jz      short loc_1801E275B
0x1801e2717  mov     rcx, [rsp+178h]; this
0x1801e271f  mov     ebx, 80070057h
0x1801e2724  mov     r9d, ebx; char *
0x1801e2727  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e272e  mov     edx, 0C54h; void *
0x1801e2733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2738  nop
0x1801e2739  lea     rcx, [rsp+178h+Src]; this
0x1801e2741  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2746  nop
0x1801e2747  lea     rcx, [rsp+178h+var_F8]
0x1801e274f  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801e2754  mov     eax, ebx
0x1801e2756  jmp     loc_1801E3004
0x1801e275b  xor     r8d, r8d
0x1801e275e  mov     rdx, [rsp+178h+var_78]
0x1801e2766  lea     rcx, [rsp+178h+pszPathOut]
0x1801e276e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1801e2773  mov     rdx, [rsp+178h+var_58]
0x1801e277b  lea     rcx, [rsp+178h+pszPathOut]
0x1801e2783  cmp     [rsp+178h+var_50], 7
0x1801e278c  cmova   rcx, [rsp+178h+pszPathOut]; pszPathOut
0x1801e2795  inc     rdx; cchPathOut
0x1801e2798  mov     r9d, 1; dwFlags
0x1801e279e  mov     r8, rbx; pszPathIn
0x1801e27a1  call    cs:__imp_PathCchCanonicalizeEx
0x1801e27a8  nop     dword ptr [rax+rax+00h]
0x1801e27ad  test    eax, eax
0x1801e27af  jns     short loc_1801E2802
0x1801e27b1  mov     rcx, [rsp+178h]; this
0x1801e27b9  mov     ebx, 80070057h
0x1801e27be  mov     r9d, ebx; char *
0x1801e27c1  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e27c8  mov     edx, 0C5Bh; void *
0x1801e27cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e27d2  lea     rcx, [rsp+178h+pszPathOut]; this
0x1801e27da  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e27df  nop
0x1801e27e0  lea     rcx, [rsp+178h+Src]; this
0x1801e27e8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e27ed  nop
0x1801e27ee  lea     rcx, [rsp+178h+var_F8]
0x1801e27f6  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801e27fb  mov     eax, ebx
0x1801e27fd  jmp     loc_1801E3004
0x1801e2802  lea     rdx, [rsp+178h+pszPathOut]
0x1801e280a  lea     rcx, [rsp+178h+Src]
0x1801e2812  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801e2817  lea     rcx, [rsp+178h+pszPathOut]; this
0x1801e281f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2824  xor     r8d, r8d
0x1801e2827  mov     dl, 1
0x1801e2829  lea     rcx, [rsp+178h+Src]; lpSrc
0x1801e2831  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x1801e2836  lea     rcx, [rsp+178h+pszPathOut]
0x1801e283e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x1801e2843  nop
0x1801e2844  lea     rdx, [rsp+178h+var_B8]
0x1801e284c  lea     rcx, [rsp+178h+Src]
0x1801e2854  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e2859  movups  xmm0, xmmword ptr [rax]
0x1801e285c  movdqu  [rsp+178h+var_C8], xmm0
0x1801e2865  lea     r9, [rsp+178h+pszPathOut]
0x1801e286d  or      r8d, 0FFFFFFFFh
0x1801e2871  lea     rcx, [rsp+178h+var_C8]
0x1801e2879  call    ?ReadStringFromFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@KKAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(std::wstring_view,ulong,ulong,std::string &)
0x1801e287e  mov     ebx, eax
0x1801e2880  test    eax, eax
0x1801e2882  jns     loc_1801E293F
0x1801e2888  mov     ecx, cs:dword_18042D328
0x1801e288e  cmp     ecx, 3
0x1801e2891  jbe     short loc_1801E28F2
0x1801e2893  mov     edx, 2000h
0x1801e2898  lea     rcx, dword_18042D328
0x1801e289f  call    _tlgKeywordOn
0x1801e28a4  test    al, al
0x1801e28a6  jz      short loc_1801E28F2
0x1801e28a8  mov     dword ptr [rsp+178h+var_128], ebx
0x1801e28ac  lea     rax, [rsp+178h+Src]
0x1801e28b4  cmp     [rsp+178h+var_70], 7
0x1801e28bd  cmova   rax, qword ptr [rsp+178h+Src]
0x1801e28c6  mov     [rsp+178h+var_118], rax
0x1801e28cb  lea     rax, [rsp+178h+var_128]
0x1801e28d0  mov     [rsp+178h+var_150], rax
0x1801e28d5  lea     rax, [rsp+178h+var_118]
0x1801e28da  mov     qword ptr [rsp+178h+var_158], rax; int
0x1801e28df  lea     rdx, unk_1803C8699
0x1801e28e6  lea     rcx, dword_18042D328
0x1801e28ed  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x1801e28f2  mov     rcx, [rsp+178h]; this
0x1801e28fa  mov     r9d, ebx; char *
0x1801e28fd  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e2904  mov     edx, 0C70h; void *
0x1801e2909  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e290e  nop
0x1801e290f  lea     rcx, [rsp+178h+pszPathOut]; void *
0x1801e2917  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801e291c  nop
0x1801e291d  lea     rcx, [rsp+178h+Src]; this
0x1801e2925  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e292a  nop
0x1801e292b  lea     rcx, [rsp+178h+var_F8]
0x1801e2933  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801e2938  mov     eax, ebx
0x1801e293a  jmp     loc_1801E3004
0x1801e293f  imul    rax, rdi, 989680h
0x1801e2946  mov     [rsp+178h+var_E8], rax
0x1801e294e  mov     r15, 58028E44000h
0x1801e2958  cmp     rax, r15
0x1801e295b  jbe     short loc_1801E2965
0x1801e295d  mov     [rsp+178h+var_E8], r15
0x1801e2965  mov     rcx, r12
0x1801e2968  xor     eax, eax
0x1801e296a  lock cmpxchg qword ptr cs:xmmword_18043BF60, rcx
0x1801e2973  jnz     short loc_1801E29C6
0x1801e2975  mov     rcx, [rsp+178h]; this
0x1801e297d  mov     r9d, 15h; char *
0x1801e2983  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e298a  mov     edx, 0C7Bh; void *
0x1801e298f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1801e2994  mov     ebx, eax
0x1801e2996  lea     rcx, [rsp+178h+pszPathOut]; void *
0x1801e299e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801e29a3  nop
0x1801e29a4  lea     rcx, [rsp+178h+Src]; this
0x1801e29ac  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e29b1  nop
0x1801e29b2  lea     rcx, [rsp+178h+var_F8]
0x1801e29ba  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801e29bf  mov     eax, ebx
0x1801e29c1  jmp     loc_1801E3004
0x1801e29c6  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801e29cd  call    ?GetTraceManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTraceManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTraceManager(void)
0x1801e29d2  mov     r13, rax
0x1801e29d5  mov     dl, r12b
0x1801e29d8  lea     rcx, [rsp+178h+var_108]
0x1801e29dd  call    ?Create@ITraceProfileDef@Diagnostics@Microsoft@@SA?AV?$shared_ptr@VITraceProfileDef@Diagnostics@Microsoft@@@std@@VTraceProfileType@23@@Z; Microsoft::Diagnostics::ITraceProfileDef::Create(Microsoft::Diagnostics::TraceProfileType)
0x1801e29e2  nop
0x1801e29e3  lea     rdx, [rsp+178h+pszPathOut]
0x1801e29eb  mov     rcx, [rsp+178h+var_108]
0x1801e29f0  call    ?SetProfile@ITraceProfileDef@Diagnostics@Microsoft@@QEAAX$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Diagnostics::ITraceProfileDef::SetProfile(std::string &&)
0x1801e29f5  mov     rcx, [rsp+178h+var_108]
0x1801e29fa  mov     rdx, [rcx]
0x1801e29fd  mov     rax, [rdx+10h]
0x1801e2a01  xor     edx, edx
0x1801e2a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2a08  mov     rax, [r13+10h]
0x1801e2a0c  mov     [rsp+178h+var_128], rax
0x1801e2a11  lea     rax, [r13+110h]
0x1801e2a18  mov     [rsp+178h+var_120], rax
0x1801e2a1d  mov     rcx, [rsp+178h+var_108]
0x1801e2a22  mov     rax, [rcx]
0x1801e2a25  mov     rax, [rax]
0x1801e2a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e2a2d  mov     [rsp+178h+var_118], rax
0x1801e2a32  lea     r8, [rsp+178h+var_118]; unsigned __int64 *
0x1801e2a37  lea     rcx, [rsp+178h+var_128]; this
0x1801e2a3c  call    ?IsSlotOwned@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA_NAEBU_GUID@@AEB_K@Z; Microsoft::Diagnostics::TraceSlotSafeWrapper::IsSlotOwned(_GUID const &,unsigned __int64 const &)
0x1801e2a41  test    al, al
0x1801e2a43  jz      short loc_1801E2A85
0x1801e2a45  mov     rcx, [rsp+178h+var_100]; this
0x1801e2a4a  test    rcx, rcx
0x1801e2a4d  jz      short loc_1801E2A55
0x1801e2a4f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801e2a54  nop
0x1801e2a55  lea     rcx, [rsp+178h+pszPathOut]; void *
0x1801e2a5d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801e2a62  nop
0x1801e2a63  lea     rcx, [rsp+178h+Src]; this
0x1801e2a6b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2a70  nop
0x1801e2a71  lea     rcx, [rsp+178h+var_F8]
0x1801e2a79  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801e2a7e  xor     eax, eax
0x1801e2a80  jmp     loc_1801E3004
0x1801e2a85  lea     rdx, [rsp+178h+var_B8]; retstr
0x1801e2a8d  lea     rcx, [rsp+178h+var_128]; this
0x1801e2a92  call    ?GetOwnerScenarioId@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA?AU_GUID@@XZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerScenarioId(void)
0x1801e2a97  mov     r8d, 10h; Size
0x1801e2a9d  lea     rbx, ?k_customTraceId@UtcApiManager@Diagnostics@Microsoft@@2U_GUID@@B; _GUID const Microsoft::Diagnostics::UtcApiManager::k_customTraceId
0x1801e2aa4  mov     rdx, rbx; Buf2
0x1801e2aa7  mov     rcx, rax; Buf1
0x1801e2aaa  call    memcmp_0
0x1801e2aaf  test    eax, eax
0x1801e2ab1  jnz     loc_1801E2B4C
0x1801e2ab7  mov     eax, cs:dword_18042D328
0x1801e2abd  cmp     eax, 2
0x1801e2ac0  jbe     short loc_1801E2B03
0x1801e2ac2  mov     edx, 2000h
0x1801e2ac7  lea     rcx, dword_18042D328
0x1801e2ace  call    _tlgKeywordOn
0x1801e2ad3  test    al, al
0x1801e2ad5  jz      short loc_1801E2B03
0x1801e2ad7  lea     rcx, [rsp+178h+var_128]; this
0x1801e2adc  call    ?GetOwnerTraceProfileHash@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA_KXZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash(void)
0x1801e2ae1  mov     [rsp+178h+var_118], rax
0x1801e2ae6  lea     rax, [rsp+178h+var_118]
0x1801e2aeb  mov     qword ptr [rsp+178h+var_158], rax
0x1801e2af0  lea     rdx, unk_1803C863F
0x1801e2af7  lea     rcx, dword_18042D328
0x1801e2afe  call    ??$Write@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &)
0x1801e2b03  lea     rcx, [rsp+178h+var_128]; this
0x1801e2b08  call    ?GetOwnerTraceProfileHash@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA_KXZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash(void)
0x1801e2b0d  mov     [rsp+178h+var_118], rax
0x1801e2b12  mov     dl, r12b
0x1801e2b15  lea     rax, [rsp+178h+var_118]
0x1801e2b1a  mov     qword ptr [rsp+178h+var_158], rax; int
0x1801e2b1f  lea     r9, GUID_NULL
0x1801e2b26  mov     r8, rbx
0x1801e2b29  mov     rcx, r13
0x1801e2b2c  call    ?StopSlotTrace@TraceManager@Diagnostics@Microsoft@@QEAAJVTraceSlotType@23@AEBU_GUID@@1AEB_K@Z; Microsoft::Diagnostics::TraceManager::StopSlotTrace(Microsoft::Diagnostics::TraceSlotType,_GUID const &,_GUID const &,unsigned __int64 const &)
0x1801e2b31  lea     rcx, [rsp+178h+var_128]; this
0x1801e2b36  call    ?GetOwnerTraceProfileHash@TraceSlotSafeWrapper@Diagnostics@Microsoft@@QEBA_KXZ; Microsoft::Diagnostics::TraceSlotSafeWrapper::GetOwnerTraceProfileHash(void)
0x1801e2b3b  mov     dl, r12b
0x1801e2b3e  mov     r9, rax
0x1801e2b41  mov     r8, rbx
0x1801e2b44  mov     rcx, r13
0x1801e2b47  call    ?RemoveTrace@TraceManager@Diagnostics@Microsoft@@QEAAXVTraceSlotType@23@AEBU_GUID@@_K_N@Z; Microsoft::Diagnostics::TraceManager::RemoveTrace(Microsoft::Diagnostics::TraceSlotType,_GUID const &,unsigned __int64,bool)
0x1801e2b4c  xorps   xmm0, xmm0
0x1801e2b4f  movups  xmmword ptr [rsp+178h+pguid.Data1], xmm0
0x1801e2b57  lea     rcx, [rsp+178h+pguid]; pguid
0x1801e2b5f  call    cs:__imp_CoCreateGuid
0x1801e2b66  nop     dword ptr [rax+rax+00h]
0x1801e2b6b  mov     ebx, eax
0x1801e2b6d  test    eax, eax
0x1801e2b6f  jns     short loc_1801E2BCE
0x1801e2b71  mov     rcx, [rsp+178h]; this
0x1801e2b79  mov     r9d, eax; char *
0x1801e2b7c  lea     r8, aOnecoreBaseTel_272; "onecore\\base\\telemetry\\utc\\service"...
0x1801e2b83  mov     edx, 0CA7h; void *
0x1801e2b88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801e2b8d  nop
0x1801e2b8e  mov     rcx, [rsp+178h+var_100]; this
0x1801e2b93  test    rcx, rcx
0x1801e2b96  jz      short loc_1801E2B9E
0x1801e2b98  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801e2b9d  nop
0x1801e2b9e  lea     rcx, [rsp+178h+pszPathOut]; void *
0x1801e2ba6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801e2bab  nop
0x1801e2bac  lea     rcx, [rsp+178h+Src]; this
0x1801e2bb4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e2bb9  nop
0x1801e2bba  lea     rcx, [rsp+178h+var_F8]
0x1801e2bc2  call    ??1?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@XZ; std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(void)
0x1801e2bc7  mov     eax, ebx
0x1801e2bc9  jmp     loc_1801E3004
0x1801e2bce  mov     eax, cs:dword_18042D328
0x1801e2bd4  cmp     eax, 4
0x1801e2bd7  jbe     short loc_1801E2C30
0x1801e2bd9  mov     edx, 2000h
0x1801e2bde  lea     rcx, dword_18042D328
0x1801e2be5  call    _tlgKeywordOn
  ... truncated ...
```
