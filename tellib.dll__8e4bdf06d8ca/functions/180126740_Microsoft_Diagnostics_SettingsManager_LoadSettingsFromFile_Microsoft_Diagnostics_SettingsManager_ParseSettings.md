# Microsoft::Diagnostics::SettingsManager::LoadSettingsFromFile(Microsoft::Diagnostics::SettingsManager::ParseSettingsState &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,Microsoft::Diagnostics::SettingsPayloadType,Microsoft::Diagnostics::SettingsManager::SettingsFileExistenceCheck,Microsoft::Diagnostics::SettingsManager::SettingsFileBackupOptions)

- ea: `0x180126740`
- end: `0x180127c5d`
- name: `?LoadSettingsFromFile@SettingsManager@Diagnostics@Microsoft@@AEAAJAEAUParseSettingsState@123@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VSettingsPayloadType@23@W4SettingsFileExistenceCheck@123@W4SettingsFileBackupOptions@123@@Z`
- size: `5405`
- prototype: ``
- caller_count: `4`
- callee_count: `49`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801264b0`
- `0x1801266b0`
- `0x18018d830`
- `0x180191d40`

## callees

- `0x180002058`
- `0x180015884`
- `0x18001cf30`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180030a50`
- `0x1800333b0`
- `0x18003352c`
- `0x180034d94`
- `0x180035698`
- `0x180038870`
- `0x18003fd8c`
- `0x180048ff4`
- `0x1800494d0`
- `0x18004ab70`
- `0x18004be98`
- `0x18005178c`
- `0x180053a84`
- `0x1800551b0`
- `0x1800552e4`
- `0x180055fa4`
- `0x180057238`
- `0x180057f58`
- `0x18005b974`
- `0x18005d050`
- `0x180080054`
- `0x180082bcc`
- `0x18009bd80`
- `0x1800a5324`
- `0x1800a60e4`
- `0x1800a8e5c`
- `0x1800a9250`
- `0x1800a9344`
- `0x1800a9f90`
- `0x1800ab10c`
- `0x1800ab394`
- `0x1800af5f0`
- `0x1800b7200`
- `0x1800bc2e0`
- `0x1800d0d9c`
- `0x180126740`
- `0x18012de40`
- `0x180161298`
- `0x18018b2ac`
- `0x18018b53c`
- `0x180199220`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126c6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180127043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012735b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180126c6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180127043`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012735b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801279b8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1801279b8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180126bf0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180126bf0`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801272cc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801279fb`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801272cc`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x1801279fb`

## string_xrefs

- `0x180126ced`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801270bb`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x18012718b`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801273d3`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180127534`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801276e5`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180127a13`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180127a71`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180127b55`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180127c1c`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180127c33`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180127c4a`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Microsoft::Diagnostics::SettingsManager::LoadSettingsFromFile(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int16 a4,
        int a5,
        int a6)
{
  __int64 v8; // r8
  int v9; // r9d
  void *v10; // rax
  _QWORD *v11; // rcx
  void *v12; // r12
  _QWORD *v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // r13
  _QWORD *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rsi
  unsigned __int64 v19; // rbx
  __int128 v20; // xmm6
  __int64 v21; // rsi
  LPCWSTR v22; // rbx
  unsigned __int64 FileTimeAsULL; // rax
  unsigned __int64 v24; // r8
  const char *v25; // r9
  __int64 result; // rax
  int v27; // eax
  int v28; // eax
  int v29; // esi
  __int128 v30; // xmm7
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  wil::details *v35; // rcx
  int v36; // eax
  char IsEnabled; // al
  _QWORD *v38; // rcx
  _QWORD *v39; // rdx
  int v40; // eax
  unsigned int LastErrorFailHr; // ebx
  int CompressedFile; // eax
  unsigned int v43; // esi
  __int128 v44; // xmm0
  __int128 *v45; // rax
  const WCHAR *v46; // rdx
  int v47; // eax
  WCHAR *v48; // rcx
  __int64 v49; // rdx
  int v50; // eax
  unsigned int v51; // ebx
  __int128 v52; // xmm0
  __int128 *v53; // rax
  char v54; // di
  int v55; // r13d
  int v56; // eax
  unsigned int v57; // ebx
  __int128 v58; // xmm0
  __int128 *v59; // rax
  int v60; // ebx
  __int128 v61; // xmm0
  __int128 *v62; // rax
  __int64 v63; // rax
  __int128 v64; // xmm6
  __int64 v65; // rax
  const WCHAR *v66; // rcx
  const WCHAR *v67; // rdx
  const WCHAR *v68; // rcx
  const char *v69; // r9
  __int64 v70; // rdx
  int v71; // eax
  unsigned int v72; // ebx
  __int128 v73; // xmm0
  __int128 *v74; // rax
  int v75; // eax
  unsigned int v76; // ebx
  int dwCreationDisposition; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositiond; // [rsp+20h] [rbp-BF8h]
  int dwCreationDispositione; // [rsp+20h] [rbp-BF8h]
  __int128 v83; // [rsp+40h] [rbp-BD8h] BYREF
  __int128 v84; // [rsp+50h] [rbp-BC8h] BYREF
  __int128 v85; // [rsp+60h] [rbp-BB8h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-BA8h] BYREF
  int v87; // [rsp+78h] [rbp-BA0h]
  __int64 v88; // [rsp+80h] [rbp-B98h]
  __int64 v89; // [rsp+88h] [rbp-B90h]
  _BYTE v90[16]; // [rsp+90h] [rbp-B88h] BYREF
  _BYTE v91[80]; // [rsp+A0h] [rbp-B78h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+F0h] [rbp-B28h] BYREF
  unsigned __int64 v93; // [rsp+108h] [rbp-B10h]
  char *v94[4]; // [rsp+110h] [rbp-B08h] BYREF
  WCHAR v95[16]; // [rsp+130h] [rbp-AE8h] BYREF
  char *v96[4]; // [rsp+150h] [rbp-AC8h] BYREF
  LPCWSTR lpNewFileName[4]; // [rsp+170h] [rbp-AA8h] BYREF
  _BYTE v98[32]; // [rsp+190h] [rbp-A88h] BYREF
  _BYTE v99[32]; // [rsp+1B0h] [rbp-A68h] BYREF
  _QWORD v100[7]; // [rsp+1D0h] [rbp-A48h] BYREF
  _QWORD *v101; // [rsp+208h] [rbp-A10h]
  _QWORD v102[7]; // [rsp+210h] [rbp-A08h] BYREF
  _QWORD *v103; // [rsp+248h] [rbp-9D0h]
  _BYTE Src[32]; // [rsp+250h] [rbp-9C8h] BYREF
  _BYTE v105[1128]; // [rsp+270h] [rbp-9A8h] BYREF
  _BYTE v106[56]; // [rsp+6D8h] [rbp-540h] BYREF
  _BYTE v107[1128]; // [rsp+710h] [rbp-508h] BYREF
  char v108; // [rsp+B78h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C18h] [rbp+0h]

  v89 = a2;
  v88 = a1;
  if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
  {
    if ( *(_QWORD *)(v8 + 24) <= 7u )
      v10 = a3;
    else
      v10 = *(void **)v8;
    hFile = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      (unsigned int)&dword_18042D328,
      (unsigned int)&unk_1803C38C4,
      v8,
      v9,
      (__int64)&hFile);
  }
  if ( a3[3] <= 7u )
    v11 = a3;
  else
    v11 = (_QWORD *)*a3;
  v12 = (void *)std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v11, a3[2], -1, 92);
  hFile = v12;
  if ( a3[3] <= 7u )
    v13 = a3;
  else
    v13 = (_QWORD *)*a3;
  v14 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v13, a3[2], -1, 46);
  try
  {
    v15 = v14;
    if ( v12 == (void *)-1LL )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
    if ( v14 == -1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79B,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
    if ( (unsigned __int64)v12 > v14 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)0x80070057LL,
        dwCreationDisposition);
    LOBYTE(v87) = 0;
    std::wstring::operator std::wstring_view(a3, &v84);
    std::wstring::wstring(v96);
    if ( a3[3] <= 7u )
      v16 = a3;
    else
      v16 = (_QWORD *)*a3;
    v17 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v16, a3[2], v15 - 1, 46);
    v18 = v17;
    if ( v17 == -1 || (v19 = v15 - v17, v15 - v17 < 2) )
    {
      v29 = v88;
    }
    else
    {
      std::wstring_view::substr(&v84, &v83, (char *)hFile + 1, v17 - (_QWORD)v12 - 1);
      std::wstring_view::substr(&v84, &v85, v18 + 1, v19 - 1);
      *(_OWORD *)lpFileName = *(_OWORD *)&off_180349F68;
      v20 = v83;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v83, lpFileName) )
      {
        v21 = v88;
        std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(&v83, v88 + 232);
        std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Diagnostics::IForwarder>,std::less<void>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>,0>>::find<std::wstring_view,std::less<void>,0>(
          v21 + 56,
          lpFileName,
          &v85);
        v22 = lpFileName[0];
        if ( lpFileName[0] != *(LPCWSTR *)(v21 + 56) )
        {
          FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
          if ( *((_QWORD *)v22 + 8) )
          {
            v24 = FileTimeAsULL - *((_QWORD *)v22 + 8);
            if ( v24 > 600000000 * (unsigned __int64)*(unsigned int *)(v21 + 544) )
            {
              v84 = v85;
              v85 = *(_OWORD *)&off_180349F68;
              Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(
                v21,
                (unsigned int)&v85,
                (unsigned int)&v84,
                0,
                3);
              std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v83);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
              return 0;
            }
            v27 = (unsigned __int8)v87;
            if ( v24 > 600000000 * (unsigned __int64)*(unsigned int *)(v21 + 548) )
              v27 = 1;
            v87 = v27;
          }
        }
        std::unique_lock<std::mutex>::~unique_lock<std::mutex>(&v83);
      }
      v83 = *(_OWORD *)&off_18035F3B0;
      *(_OWORD *)lpFileName = v20;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(lpFileName, &v83) )
        std::wstring::_Assign<wchar_t>(v96, (const void *)v85, *((char **)&v85 + 1));
      v83 = *(_OWORD *)&off_18035F3C0;
      v28 = Microsoft::Diagnostics::Utils::String::ICompare(&v85, &v83);
      v29 = v88;
      if ( !v28 )
        std::_Tree<std::_Tset_traits<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>,0>>::insert<0,0>(
          v88 + 1152,
          &v83,
          a3);
    }
    if ( a4 )
    {
      if ( (unsigned __int16)(a4 - 1) > 1u )
      {
LABEL_112:
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
        return 0;
      }
      std::wstring_view::substr(&v84, &v85, (char *)hFile + 1, v15 - (_QWORD)hFile - 1);
      std::string::string(v98);
      v30 = v85;
      v31 = std::wstring::wstring((__int64)v99, &off_18035F0B0);
      v32 = std::operator+<wchar_t>(v94, v31, L"\\");
      v83 = v30;
      v33 = Microsoft::Diagnostics::operator+(lpNewFileName, v32, &v83);
      v83 = *(_OWORD *)&Microsoft::Diagnostics::SettingsDownloader::k_diffBaseFileExtension;
      Microsoft::Diagnostics::operator+(v95, v33, &v83);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpNewFileName);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v94);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v99);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v95);
      v34 = std::wstring::wstring(Src, v95);
      if ( *(_QWORD *)(v34 + 24) > 7u )
        v34 = *(_QWORD *)v34;
      hFile = CreateFileW((LPCWSTR)v34, 0x80000000, 5u, 0, 3u, 0x80u, 0);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      v35 = (wil::details *)hFile;
      if ( (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
        goto LABEL_60;
      *(_QWORD *)&v83 = L"SettingsManager_UseWinSxSStorageFileAsLoadingInboxDiffFileFailed";
      *((_QWORD *)&v83 + 1) = 64;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v107,
        (unsigned int)&v83,
        0x1000000,
        0,
        0,
        0,
        0);
      LODWORD(lpFileName[0]) = GetLastError();
      *(_QWORD *)&v83 = L"LastError";
      *((_QWORD *)&v83 + 1) = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v107, (unsigned int)&v108);
      v83 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
        lpFileName,
        &v83);
      v36 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v107);
      if ( v36 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x834,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)(unsigned int)v36,
          dwCreationDispositiona);
      std::wstring::wstring(v94);
      *(_QWORD *)&v83 = L"utc.allow";
      *((_QWORD *)&v83 + 1) = 9;
      v84 = v85;
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v84, &v83) )
      {
        *(_QWORD *)&v83 = L"utc.privacy";
        *((_QWORD *)&v83 + 1) = 11;
        v84 = v85;
        if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v84, &v83)
          || (*(_QWORD *)&v83 = L"utc.aggregators",
              *((_QWORD *)&v83 + 1) = 15,
              v84 = v85,
              !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v84, &v83)) )
        {
          std::wstring::_Assign<wchar_t>(v94, L"*windowsclient*", (char *)0xF);
        }
      }
      else
      {
        std::wstring::_Assign<wchar_t>(v94, L"*telemetry-client*", (char *)0x12);
      }
      if ( !v94[2] )
      {
        *(_QWORD *)&v83 = L"SettingsManager_NonUtcAllowOrPrivacyHardcodedEndpointEncountered";
        *((_QWORD *)&v83 + 1) = 64;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v105,
          (unsigned int)&v83,
          0x1000000,
          0,
          0,
          0,
          0);
        *(_QWORD *)&v83 = L"endpoint";
        *((_QWORD *)&v83 + 1) = 8;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(
          (unsigned int)v105,
          (unsigned int)v106);
        LODWORD(lpFileName[0]) = GetLastError();
        *(_QWORD *)&v83 = L"LastError";
        *((_QWORD *)&v83 + 1) = 9;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v105, (unsigned int)v106);
        v83 = 0;
        Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
          lpFileName,
          &v83);
        v40 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v105);
        if ( v40 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x87C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)v40,
            dwCreationDispositiona);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v105);
        goto LABEL_59;
      }
      std::wstring::wstring((__int64)lpNewFileName, &off_18035F0A0);
      Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpNewFileName);
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_TvsWarningFixes>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_TvsWarningFixes>::GetImpl'::`2'::impl);
      v91[64] = 0;
      if ( IsEnabled )
      {
        v102[0] = off_180356128;
        v102[1] = v95;
        v102[2] = &v85;
        v102[3] = &hFile;
        v103 = v102;
        v83 = *(_OWORD *)std::wstring::operator std::wstring_view(v94, v90);
        v84 = *(_OWORD *)std::wstring::operator std::wstring_view(lpNewFileName, v99);
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachDirectoryInPattern(&v84, &v83, v102, v91);
        v38 = v103;
        if ( v103 )
        {
          v39 = v102;
          goto LABEL_54;
        }
      }
      else
      {
        v100[0] = off_1803560F8;
        v100[1] = v95;
        v100[2] = &v85;
        v100[3] = &hFile;
        v101 = v100;
        v83 = *(_OWORD *)std::wstring::operator std::wstring_view(v94, lpFileName);
        v84 = *(_OWORD *)std::wstring::operator std::wstring_view(lpNewFileName, v90);
        Microsoft::Diagnostics::Utils::FileSystem::DoForEachDirectoryInPattern(&v84, &v83, v100, v91);
        v38 = v101;
        if ( v101 )
        {
          v39 = v100;
LABEL_54:
          LOBYTE(v39) = v38 != v39;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v38 + 32LL))(v38, v39);
        }
      }
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpNewFileName);
LABEL_59:
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v94);
      Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v107);
      v35 = (wil::details *)hFile;
LABEL_60:
      if ( a4 == 1 && (((unsigned __int64)v35 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v35);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v95);
        std::string::_Tidy_deallocate(v98);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
        return LastErrorFailHr;
      }
      if ( (unsigned __int64)v35 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        CompressedFile = Microsoft::Diagnostics::Utils::FileSystem::ReadCompressedFile(v35);
        v43 = CompressedFile;
        if ( CompressedFile < 0 && a4 == 1 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x88C,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)CompressedFile,
            dwCreationDispositiona);
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v95);
          std::string::_Tidy_deallocate(v98);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
          return v43;
        }
      }
      v44 = *(_OWORD *)std::wstring::operator std::wstring_view(v96, v99);
      v45 = (__int128 *)std::wstring::operator std::wstring_view(a3, v90);
      v83 = v44;
      v84 = *v45;
      *(_OWORD *)lpFileName = *(_OWORD *)std::string::operator std::string_view(v98, v94);
      LOBYTE(dwCreationDispositiona) = v87;
      if ( (int)Microsoft::Diagnostics::SettingsManager::ParseSettings(
                  v88,
                  v89,
                  (unsigned int)lpFileName,
                  (unsigned int)&v84,
                  dwCreationDispositiona,
                  (__int64)&v83,
                  a4) >= 0
        && !a6 )
      {
        v83 = *(_OWORD *)&Microsoft::Diagnostics::SettingsDownloader::k_backupFileExtension;
        Microsoft::Diagnostics::operator+(lpNewFileName);
        v46 = (const WCHAR *)lpNewFileName;
        if ( lpNewFileName[3] > (LPCWSTR)7 )
          v46 = lpNewFileName[0];
        if ( a3[3] > 7u )
          a3 = (_QWORD *)*a3;
        if ( !CopyFileW((LPCWSTR)a3, v46, 0) )
        {
          *(_QWORD *)&v83 = L"SettingsManager_SavePatchSettingsBackupFailed";
          *((_QWORD *)&v83 + 1) = 45;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
            (unsigned int)v105,
            (unsigned int)&v83,
            0x1000000,
            0,
            0,
            0,
            0);
          *(_QWORD *)&v83 = L"fileName";
          *((_QWORD *)&v83 + 1) = 8;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(
            (unsigned int)v105,
            (unsigned int)v106);
          LODWORD(lpFileName[0]) = GetLastError();
          *(_QWORD *)&v83 = L"LastError";
          *((_QWORD *)&v83 + 1) = 9;
          Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v105, (unsigned int)v106);
          v83 = 0;
          Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
            lpFileName,
            &v83);
          v47 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v105);
          if ( v47 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x89D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)(unsigned int)v47,
              dwCreationDispositionb);
          Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v105);
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpNewFileName);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v95);
      v48 = (WCHAR *)v98;
      goto LABEL_111;
    }
    std::string::string(v95);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)a3);
    v83 = *(_OWORD *)std::wstring::operator std::wstring_view(a3, v94);
    v50 = Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(&v83, v49, 0xFFFFFFFFLL, v95);
    v51 = v50;
    LODWORD(lpFileName[0]) = v50;
    if ( v50 < 0 )
    {
      if ( a6 == 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7F0,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)(unsigned int)v50,
          dwCreationDisposition);
        std::string::_Tidy_deallocate(v95);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
        return v51;
      }
      if ( a5 == 1 && v50 == -2147024894 )
      {
        std::string::_Tidy_deallocate(v95);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
        return 0;
      }
      *(_QWORD *)&v83 = L"SettingsManager_RevertToPreviousSettingsBecauseFailedParse";
      *((_QWORD *)&v83 + 1) = 58;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v105,
        (unsigned int)&v83,
        0x1000000,
        0,
        0,
        0,
        0);
      *(_QWORD *)&v83 = L"ErrorCode";
      *((_QWORD *)&v83 + 1) = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v105, (unsigned int)v106);
      *(_QWORD *)&v83 = L"FileName";
      *((_QWORD *)&v83 + 1) = 8;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v105, (unsigned int)v106);
      v83 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
        lpFileName,
        &v83);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v105);
      v61 = *(_OWORD *)std::wstring::operator std::wstring_view(v96, v94);
      v62 = (__int128 *)std::wstring::operator std::wstring_view(a3, v99);
      v83 = v61;
      v84 = *v62;
      v85 = *(_OWORD *)std::string::operator std::string_view(&unk_18043B490, v90);
      v54 = v87;
      v55 = v89;
      v60 = Microsoft::Diagnostics::SettingsManager::RetryParseWithBackupSettings(
              v29,
              v89,
              (unsigned int)&v85,
              (unsigned int)&v84,
              v87,
              (__int64)&v83,
              0);
    }
    else
    {
      v52 = *(_OWORD *)std::wstring::operator std::wstring_view(v96, v94);
      v53 = (__int128 *)std::wstring::operator std::wstring_view(&unk_18043B470, v99);
      v83 = v52;
      v84 = *v53;
      v85 = *(_OWORD *)std::string::operator std::string_view(v95, v90);
      v54 = v87;
      LOBYTE(dwCreationDisposition) = v87;
      v55 = v89;
      v56 = Microsoft::Diagnostics::SettingsManager::ParseSettings(
              v29,
              v89,
              (unsigned int)&v85,
              (unsigned int)&v84,
              dwCreationDisposition,
              (__int64)&v83,
              0);
      v57 = v56;
      LODWORD(lpFileName[0]) = v56;
      if ( a6 == 1 )
      {
        if ( v56 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7DC,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)v56,
            dwCreationDispositionc);
        std::string::_Tidy_deallocate(v95);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
        return v57;
      }
      if ( v56 >= 0 )
      {
LABEL_110:
        v48 = v95;
LABEL_111:
        std::string::_Tidy_deallocate(v48);
        goto LABEL_112;
      }
      *(_QWORD *)&v83 = L"SettingsManager_RevertToPreviousSettingsBecauseFailedParse";
      *((_QWORD *)&v83 + 1) = 58;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
        (unsigned int)v105,
        (unsigned int)&v83,
        0x1000000,
        0,
        0,
        0,
        0);
      *(_QWORD *)&v83 = L"ErrorCode";
      *((_QWORD *)&v83 + 1) = 9;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v105, (unsigned int)v106);
      *(_QWORD *)&v83 = L"FileName";
      *((_QWORD *)&v83 + 1) = 8;
      Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v105, (unsigned int)v106);
      v83 = 0;
      Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(
        lpFileName,
        &v83);
      Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v105);
      v58 = *(_OWORD *)std::wstring::operator std::wstring_view(v96, v94);
      v59 = (__int128 *)std::wstring::operator std::wstring_view(a3, v99);
      v83 = v58;
      v84 = *v59;
      v85 = *(_OWORD *)std::string::operator std::string_view(&unk_18043B490, v90);
      v60 = Microsoft::Diagnostics::SettingsManager::RetryParseWithBackupSettings(
              v29,
              v55,
              (unsigned int)&v85,
              (unsigned int)&v84,
              v54,
              (__int64)&v83,
              0);
    }
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v105);
    if ( v60 < 0 )
    {
      std::wstring::operator std::wstring_view(a3, &v84);
      v63 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(v84, *((_QWORD *)&v84 + 1), -1, 92);
      if ( v63 != -1 )
      {
        v64 = *(_OWORD *)std::wstring_view::substr(&v84, v94, v63 + 1, -1);
        std::wstring::wstring(lpNewFileName);
        v83 = *(_OWORD *)&off_18035F290;
        v65 = Microsoft::Diagnostics::operator+(Src);
        v83 = v64;
        Microsoft::Diagnostics::operator+(lpFileName, v65, &v83);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpNewFileName);
        Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpFileName);
        v66 = (const WCHAR *)lpFileName;
        if ( v93 > 7 )
          v66 = lpFileName[0];
        if ( GetFileAttributesW(v66) != -1 )
        {
          if ( a3[3] <= 7u )
            v67 = (const WCHAR *)a3;
          else
            v67 = (const WCHAR *)*a3;
          v68 = (const WCHAR *)lpFileName;
          if ( v93 > 7 )
            v68 = lpFileName[0];
          if ( !CopyFileW(v68, v67, 0) )
            wil::details::in1diag3::_Log_GetLastError(
              retaddr,
              (void *)0x812,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              v69);
          std::string::string(v98);
          v83 = *(_OWORD *)std::wstring::operator std::wstring_view(a3, v94);
          v71 = Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(&v83, v70, 0xFFFFFFFFLL, v98);
          v72 = v71;
          if ( v71 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x816,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)(unsigned int)v71,
              dwCreationDispositiond);
            std::string::_Tidy_deallocate(v98);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
            std::string::_Tidy_deallocate(v95);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
            return v72;
          }
          v73 = *(_OWORD *)std::wstring::operator std::wstring_view(v96, v94);
          v74 = (__int128 *)std::wstring::operator std::wstring_view(&unk_18043B470, v99);
          v83 = v73;
          v84 = *v74;
          v85 = *(_OWORD *)std::string::operator std::string_view(v98, v90);
          LOBYTE(dwCreationDispositiond) = v54;
          v75 = Microsoft::Diagnostics::SettingsManager::ParseSettings(
                  v29,
                  v55,
                  (unsigned int)&v85,
                  (unsigned int)&v84,
                  dwCreationDispositiond,
                  (__int64)&v83,
                  0);
          v76 = v75;
          if ( v75 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x817,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)(unsigned int)v75,
              dwCreationDispositione);
            std::string::_Tidy_deallocate(v98);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
            std::string::_Tidy_deallocate(v95);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v96);
            return v76;
          }
          std::string::_Tidy_deallocate(v98);
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      }
    }
    goto LABEL_110;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8A4,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x180126740  mov     rax, rsp
0x180126743  push    rbx
0x180126744  push    rsi
0x180126745  push    rdi
0x180126746  push    r12
0x180126748  push    r13
0x18012674a  push    r14
0x18012674c  push    r15
0x18012674e  sub     rsp, 0BE0h
0x180126755  movaps  xmmword ptr [rax-48h], xmm6
0x180126759  movaps  xmmword ptr [rax-58h], xmm7
0x18012675d  mov     rax, cs:__security_cookie
0x180126764  xor     rax, rsp
0x180126767  mov     [rsp+0C18h+var_68], rax
0x18012676f  movzx   edi, r9w
0x180126773  mov     r15, r8
0x180126776  mov     [rsp+0C18h+var_B90], rdx
0x18012677e  mov     [rsp+0C18h+var_B98], rcx
0x180126786  mov     eax, cs:dword_18042D328
0x18012678c  cmp     eax, 5
0x18012678f  jbe     short loc_1801267DC
0x180126791  mov     edx, 200h
0x180126796  lea     rcx, dword_18042D328
0x18012679d  call    _tlgKeywordOn
0x1801267a2  xor     r14d, r14d
0x1801267a5  test    al, al
0x1801267a7  jz      short loc_1801267DF
0x1801267a9  cmp     qword ptr [r8+18h], 7
0x1801267ae  jbe     short loc_1801267B5
0x1801267b0  mov     rax, [r8]
0x1801267b3  jmp     short loc_1801267B8
0x1801267b5  mov     rax, r15
0x1801267b8  mov     [rsp+0C18h+hFile], rax
0x1801267bd  lea     rax, [rsp+0C18h+hFile]
0x1801267c2  mov     qword ptr [rsp+0C18h+dwCreationDisposition], rax
0x1801267c7  lea     rdx, unk_1803C38C4
0x1801267ce  lea     rcx, dword_18042D328
0x1801267d5  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1801267da  jmp     short loc_1801267DF
0x1801267dc  xor     r14d, r14d
0x1801267df  cmp     qword ptr [r15+18h], 7
0x1801267e4  jbe     short loc_1801267EB
0x1801267e6  mov     rcx, [r15]
0x1801267e9  jmp     short loc_1801267EE
0x1801267eb  mov     rcx, r15
0x1801267ee  mov     r9d, 5Ch ; '\'
0x1801267f4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801267f8  mov     r8, rbx
0x1801267fb  mov     rdx, [r15+10h]
0x1801267ff  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x180126804  mov     r12, rax
0x180126807  mov     [rsp+0C18h+hFile], rax
0x18012680c  cmp     qword ptr [r15+18h], 7
0x180126811  jbe     short loc_180126818
0x180126813  mov     rcx, [r15]
0x180126816  jmp     short loc_18012681B
0x180126818  mov     rcx, r15
0x18012681b  mov     esi, 2Eh ; '.'
0x180126820  mov     r9d, esi
0x180126823  mov     r8, rbx
0x180126826  mov     rdx, [r15+10h]
0x18012682a  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x18012682f  mov     r13, rax
0x180126832  mov     rcx, [rsp+0C18h]; this
0x18012683a  cmp     r12, rbx
0x18012683d  jz      loc_180127C16
0x180126843  mov     rcx, [rsp+0C18h]; this
0x18012684b  cmp     r13, rbx
0x18012684e  jz      loc_180127C2D
0x180126854  mov     rcx, [rsp+0C18h]; this
0x18012685c  cmp     r12, r13
0x18012685f  ja      loc_180127C44
0x180126865  mov     byte ptr [rsp+0C18h+var_BA0], r14b
0x18012686a  lea     rdx, [rsp+0C18h+var_BC8]
0x18012686f  mov     rcx, r15
0x180126872  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180126877  lea     rcx, [rsp+0C18h+var_AC8]; void *
0x18012687f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180126884  nop
0x180126885  cmp     qword ptr [r15+18h], 7
0x18012688a  jbe     short loc_180126891
0x18012688c  mov     rcx, [r15]
0x18012688f  jmp     short loc_180126894
0x180126891  mov     rcx, r15
0x180126894  mov     r9d, esi
0x180126897  lea     r8, [r13-1]
0x18012689b  mov     rdx, [r15+10h]
0x18012689f  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1801268a4  mov     rsi, rax
0x1801268a7  cmp     rax, rbx
0x1801268aa  jz      loc_180126AA9
0x1801268b0  mov     rbx, r13
0x1801268b3  sub     rbx, rax
0x1801268b6  cmp     rbx, 2
0x1801268ba  jb      loc_180126AA9
0x1801268c0  mov     r9, rax
0x1801268c3  sub     r9, r12
0x1801268c6  mov     r12d, 1
0x1801268cc  sub     r9, r12
0x1801268cf  mov     r8, [rsp+0C18h+hFile]
0x1801268d4  inc     r8
0x1801268d7  lea     rdx, [rsp+0C18h+var_BD8]
0x1801268dc  lea     rcx, [rsp+0C18h+var_BC8]
0x1801268e1  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801268e6  lea     r9, [rbx-1]
0x1801268ea  lea     r8, [rsi+1]
0x1801268ee  lea     rdx, [rsp+0C18h+var_BB8]
0x1801268f3  lea     rcx, [rsp+0C18h+var_BC8]
0x1801268f8  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x1801268fd  movups  xmm0, xmmword ptr cs:off_180349F68; "telemetry"
0x180126904  movdqu  xmmword ptr [rsp+0C18h+lpFileName], xmm0
0x18012690d  movaps  xmm6, [rsp+0C18h+var_BD8]
0x180126912  movdqa  [rsp+0C18h+var_BD8], xmm6
0x180126918  lea     rdx, [rsp+0C18h+lpFileName]
0x180126920  lea     rcx, [rsp+0C18h+var_BD8]
0x180126925  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18012692a  test    eax, eax
0x18012692c  jnz     loc_180126A1D
0x180126932  mov     rsi, [rsp+0C18h+var_B98]
0x18012693a  lea     rdx, [rsi+0E8h]
0x180126941  lea     rcx, [rsp+0C18h+var_BD8]
0x180126946  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18012694b  nop
0x18012694c  lea     r8, [rsp+0C18h+var_BB8]
0x180126951  lea     rdx, [rsp+0C18h+lpFileName]
0x180126959  lea     rcx, [rsi+38h]
0x18012695d  call    ??$find@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@U?$less@X@2@$0A@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$shared_ptr@VIForwarder@Diagnostics@Microsoft@@@2@@std@@@std@@@std@@@1@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::shared_ptr<Microsoft::Diagnostics::IForwarder>,std::less<void>,std::allocator<std::pair<std::wstring const,std::shared_ptr<Microsoft::Diagnostics::IForwarder>>>,0>>::find<std::wstring_view,std::less<void>,0>(std::wstring_view const &)
0x180126962  mov     rbx, [rsp+0C18h+lpFileName]
0x18012696a  cmp     rbx, [rsi+38h]
0x18012696e  jz      loc_180126A13
0x180126974  call    ?GetFileTimeAsULL@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL(void)
0x180126979  mov     r8, rax
0x18012697c  cmp     [rbx+40h], r14
0x180126980  jz      loc_180126A13
0x180126986  sub     r8, [rbx+40h]
0x18012698a  mov     rax, rsi
0x18012698d  mov     ecx, [rax+220h]
0x180126993  imul    rdx, rcx, 23C34600h
0x18012699a  cmp     r8, rdx
0x18012699d  jbe     short loc_1801269F4
0x18012699f  movaps  xmm0, [rsp+0C18h+var_BB8]
0x1801269a4  movdqa  [rsp+0C18h+var_BC8], xmm0
0x1801269aa  movups  xmm1, xmmword ptr cs:off_180349F68; "telemetry"
0x1801269b1  movdqu  [rsp+0C18h+var_BB8], xmm1
0x1801269b7  mov     [rsp+0C18h+dwCreationDisposition], 3
0x1801269bf  xor     r9d, r9d
0x1801269c2  lea     r8, [rsp+0C18h+var_BC8]
0x1801269c7  lea     rdx, [rsp+0C18h+var_BB8]
0x1801269cc  mov     rcx, rax
0x1801269cf  call    ?UnregisterSettingsEndpoint@SettingsManager@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NVEndpointUnregistrationReason@23@@Z; Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(std::wstring_view,std::wstring_view,bool,Microsoft::Diagnostics::EndpointUnregistrationReason)
0x1801269d4  nop
0x1801269d5  lea     rcx, [rsp+0C18h+var_BD8]
0x1801269da  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801269df  nop
0x1801269e0  lea     rcx, [rsp+0C18h+var_AC8]; this
0x1801269e8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801269ed  xor     eax, eax
0x1801269ef  jmp     loc_180127BE4
0x1801269f4  mov     eax, [rax+224h]
0x1801269fa  imul    rcx, rax, 23C34600h
0x180126a01  mov     eax, [rsp+0C18h+var_BA0]
0x180126a05  movzx   eax, al
0x180126a08  cmp     r8, rcx
0x180126a0b  cmova   eax, r12d
0x180126a0f  mov     [rsp+0C18h+var_BA0], eax
0x180126a13  lea     rcx, [rsp+0C18h+var_BD8]
0x180126a18  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180126a1d  movups  xmm0, xmmword ptr cs:off_18035F3B0; "telemetry"
0x180126a24  movdqu  [rsp+0C18h+var_BD8], xmm0
0x180126a2a  movdqa  xmmword ptr [rsp+0C18h+lpFileName], xmm6
0x180126a33  lea     rdx, [rsp+0C18h+var_BD8]
0x180126a38  lea     rcx, [rsp+0C18h+lpFileName]
0x180126a40  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180126a45  test    eax, eax
0x180126a47  jnz     short loc_180126A60
0x180126a49  mov     r8, qword ptr [rsp+0C18h+var_BB8+8]
0x180126a4e  mov     rdx, qword ptr [rsp+0C18h+var_BB8]
0x180126a53  lea     rcx, [rsp+0C18h+var_AC8]
0x180126a5b  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180126a60  movups  xmm0, xmmword ptr cs:off_18035F3C0; "aggregators"
0x180126a67  movdqu  [rsp+0C18h+var_BD8], xmm0
0x180126a6d  movaps  xmm0, [rsp+0C18h+var_BB8]
0x180126a72  movdqa  [rsp+0C18h+var_BB8], xmm0
0x180126a78  lea     rdx, [rsp+0C18h+var_BD8]
0x180126a7d  lea     rcx, [rsp+0C18h+var_BB8]
0x180126a82  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180126a87  mov     rsi, [rsp+0C18h+var_B98]
0x180126a8f  test    eax, eax
0x180126a91  jnz     short loc_180126AB7
0x180126a93  lea     rcx, [rsi+480h]
0x180126a9a  mov     r8, r15
0x180126a9d  lea     rdx, [rsp+0C18h+var_BD8]
0x180126aa2  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UCaseInsensitiveLessThanPredicate@String@Utils@Diagnostics@Microsoft@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,Microsoft::Diagnostics::Utils::String::CaseInsensitiveLessThanPredicate,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x180126aa7  jmp     short loc_180126AB7
0x180126aa9  mov     r12d, 1
0x180126aaf  mov     rsi, [rsp+0C18h+var_B98]
0x180126ab7  test    di, di
0x180126aba  jz      loc_180127427
0x180126ac0  movzx   eax, di
0x180126ac3  sub     ax, r12w
0x180126ac7  cmp     ax, r12w
0x180126acb  ja      loc_180127BCC
0x180126ad1  mov     rax, [rsp+0C18h+hFile]
0x180126ad6  sub     r13, rax
0x180126ad9  sub     r13, r12
0x180126adc  lea     r8, [rax+1]
0x180126ae0  mov     r9, r13
0x180126ae3  lea     rdx, [rsp+0C18h+var_BB8]
0x180126ae8  lea     rcx, [rsp+0C18h+var_BC8]
0x180126aed  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x180126af2  lea     rcx, [rsp+0C18h+var_A88]
0x180126afa  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x180126aff  nop
0x180126b00  movups  xmm6, xmmword ptr cs:?k_diffBaseFileExtension@SettingsDownloader@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::SettingsDownloader::k_diffBaseFileExtension
0x180126b07  movaps  xmm7, [rsp+0C18h+var_BB8]
0x180126b0c  lea     rdx, off_18035F0B0; "%WinDir%\\DiagTrack"
0x180126b13  lea     rcx, [rsp+0C18h+var_A68]
0x180126b1b  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x180126b20  nop
0x180126b21  lea     r8, asc_1803772C8; "\\"
0x180126b28  mov     rdx, rax
0x180126b2b  lea     rcx, [rsp+0C18h+var_B08]
0x180126b33  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180126b38  nop
0x180126b39  movdqu  [rsp+0C18h+var_BD8], xmm7
0x180126b3f  lea     r8, [rsp+0C18h+var_BD8]
0x180126b44  mov     rdx, rax
0x180126b47  lea     rcx, [rsp+0C18h+lpNewFileName]
0x180126b4f  call    ??HDiagnostics@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV23@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; Microsoft::Diagnostics::operator+(std::wstring &&,std::wstring_view)
0x180126b54  nop
0x180126b55  movdqu  [rsp+0C18h+var_BD8], xmm6
0x180126b5b  lea     r8, [rsp+0C18h+var_BD8]
0x180126b60  mov     rdx, rax
0x180126b63  lea     rcx, [rsp+0C18h+var_AE8]
0x180126b6b  call    ??HDiagnostics@Microsoft@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$QEAV23@V?$basic_string_view@_WU?$char_traits@_W@std@@@3@@Z; Microsoft::Diagnostics::operator+(std::wstring &&,std::wstring_view)
0x180126b70  nop
0x180126b71  lea     rcx, [rsp+0C18h+lpNewFileName]; this
0x180126b79  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180126b7e  nop
0x180126b7f  lea     rcx, [rsp+0C18h+var_B08]; this
0x180126b87  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180126b8c  nop
0x180126b8d  lea     rcx, [rsp+0C18h+var_A68]; this
0x180126b95  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180126b9a  xor     r8d, r8d
0x180126b9d  mov     dl, r12b
0x180126ba0  lea     rcx, [rsp+0C18h+var_AE8]; lpSrc
0x180126ba8  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180126bad  lea     rdx, [rsp+0C18h+var_AE8]
0x180126bb5  lea     rcx, [rsp+0C18h+Src]
0x180126bbd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180126bc2  cmp     qword ptr [rax+18h], 7
0x180126bc7  jbe     short loc_180126BCC
0x180126bc9  mov     rax, [rax]
0x180126bcc  mov     [rsp+0C18h+hTemplateFile], r14; hTemplateFile
0x180126bd1  mov     [rsp+0C18h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180126bd9  mov     [rsp+0C18h+dwCreationDisposition], 3; int
0x180126be1  xor     r9d, r9d; lpSecurityAttributes
0x180126be4  mov     edx, 80000000h; dwDesiredAccess
0x180126be9  lea     r8d, [r9+5]; dwShareMode
0x180126bed  mov     rcx, rax; lpFileName
0x180126bf0  call    cs:__imp_CreateFileW
0x180126bf7  nop     dword ptr [rax+rax+00h]
0x180126bfc  mov     [rsp+0C18h+hFile], rax
0x180126c01  lea     rcx, [rsp+0C18h+Src]; this
0x180126c09  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180126c0e  mov     rcx, [rsp+0C18h+hFile]; hFile
0x180126c13  lea     rax, [rcx+1]
0x180126c17  test    rax, 0FFFFFFFFFFFFFFFEh
0x180126c1d  jnz     loc_1801270FD
0x180126c23  lea     rax, aSettingsmanage_9; "SettingsManager_UseWinSxSStorageFileAsL"...
0x180126c2a  mov     qword ptr [rsp+0C18h+var_BD8], rax
0x180126c2f  mov     esi, 40h ; '@'
0x180126c34  mov     qword ptr [rsp+0C18h+var_BD8+8], rsi
0x180126c39  mov     r8d, 1000000h
0x180126c3f  mov     byte ptr [rsp+0C18h+hTemplateFile], r14b
0x180126c44  mov     byte ptr [rsp+0C18h+dwFlagsAndAttributes], r14b
0x180126c49  mov     byte ptr [rsp+0C18h+dwCreationDisposition], r14b; int
0x180126c4e  mov     r9, 400000000000h
0x180126c58  lea     rdx, [rsp+0C18h+var_BD8]
0x180126c5d  lea     rcx, [rsp+0C18h+var_508]
0x180126c65  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x180126c6a  nop
0x180126c6b  call    cs:__imp_GetLastError
0x180126c72  nop     dword ptr [rax+rax+00h]
0x180126c77  mov     dword ptr [rsp+0C18h+lpFileName], eax
0x180126c7e  lea     r13, aLasterror; "LastError"
0x180126c85  mov     qword ptr [rsp+0C18h+var_BD8], r13
0x180126c8a  lea     ebx, [rsi-37h]
0x180126c8d  mov     qword ptr [rsp+0C18h+var_BD8+8], rbx
0x180126c92  lea     r9, [rsp+0C18h+lpFileName]
0x180126c9a  lea     r8, [rsp+0C18h+var_BD8]
0x180126c9f  lea     rdx, [rsp+0C18h+var_A0]
0x180126ca7  lea     rcx, [rsp+0C18h+var_508]
0x180126caf  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x180126cb4  xorps   xmm0, xmm0
0x180126cb7  movdqa  [rsp+0C18h+var_BD8], xmm0
0x180126cbd  lea     rdx, [rsp+0C18h+var_BD8]
0x180126cc2  lea     rcx, [rsp+0C18h+lpFileName]
0x180126cca  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
  ... truncated ...
```
