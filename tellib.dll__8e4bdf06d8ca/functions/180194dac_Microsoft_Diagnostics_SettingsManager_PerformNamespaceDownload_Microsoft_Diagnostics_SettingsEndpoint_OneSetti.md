# Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload(Microsoft::Diagnostics::SettingsEndpoint &,OneSettingsDownloadSession *,unsigned __int64 const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,bool,std::optional<ulong>,bool &)

- ea: `0x180194dac`
- end: `0x18019752c`
- name: `?PerformNamespaceDownload@SettingsManager@Diagnostics@Microsoft@@AEAAJAEAVSettingsEndpoint@23@PEAUOneSettingsDownloadSession@@AEB_KAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NV?$optional@K@7@AEA_N@Z`
- size: `10112`
- prototype: `__int64 __usercall@<rax>(Microsoft::Diagnostics::SettingsManager *this@<rcx>, struct Microsoft::Diagnostics::SettingsEndpoint *@<rdx>, __int64, char, __int64, __int64)`
- caller_count: `2`
- callee_count: `69`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18018e0cc`
- `0x18018fc70`

## callees

- `0x180001bf4`
- `0x180001d28`
- `0x180005034`
- `0x1800055b8`
- `0x18001d160`
- `0x18001ee94`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180030a50`
- `0x1800326cc`
- `0x180032718`
- `0x1800333b0`
- `0x180033f3c`
- `0x180034d94`
- `0x180035698`
- `0x18003fe04`
- `0x180040454`
- `0x180048ff4`
- `0x1800498f0`
- `0x18004ab70`
- `0x180052d3c`
- `0x18005479c`
- `0x1800551b0`
- `0x1800562b8`
- `0x18005d050`
- `0x180067c68`
- `0x180068068`
- `0x18007fae8`
- `0x180080054`
- `0x180089d90`
- `0x18008b178`
- `0x18008d848`
- `0x18009c71c`
- `0x1800a0654`
- `0x1800a5324`
- `0x1800a60e4`
- `0x1800a69c8`
- `0x1800a8324`
- `0x1800a9250`
- `0x1800a9344`
- `0x1800aac70`
- `0x1800af5f0`
- `0x1800d0d9c`
- `0x1800d6e10`
- `0x1800e0df8`
- `0x1800f5954`
- `0x1800f7680`
- `0x18012de40`
- `0x180168fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180194feb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180194fd6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180194fd6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180195536`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180195536`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18019546f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18019546f`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180195584`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureContext` at `0x180195584`

## string_xrefs

- `0x180194e77`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180194ef6`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x180194f0c`: `onecore\base\telemetry\utc\service\engine\settingsmanager.cpp`
- `0x1801951f7`: `LastFileWrittenPath`
- `0x18019519b`: `DestinationFilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=25 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload(
        Microsoft::Diagnostics::SettingsManager *this,
        struct Microsoft::Diagnostics::SettingsEndpoint *a2,
        __int64 a3,
        unsigned __int64 *a4,
        __int64 a5,
        char a6,
        __int64 a7,
        _BYTE *a8)
{
  Microsoft::Diagnostics::SettingsManager *v9; // r14
  int v10; // r15d
  int Ticket; // eax
  bool v13; // al
  struct Microsoft::Diagnostics::EnterpriseData *EnterpriseData; // rax
  __int64 v15; // rdx
  const WCHAR *v16; // rcx
  __int64 v17; // rax
  unsigned __int64 *v18; // r12
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rdx
  const WCHAR *v21; // r8
  WCHAR *v22; // rcx
  HRESULT v23; // eax
  unsigned int v24; // ebx
  const WCHAR *v25; // rcx
  HANDLE FileW; // rax
  CONTEXT *v27; // rbx
  __int64 v28; // r8
  unsigned int v29; // ebx
  int v30; // r14d
  int v31; // r15d
  struct Microsoft::Diagnostics::SystemStateManager *SystemStateManager; // rax
  __int64 v33; // r12
  struct Microsoft::Diagnostics::EnterpriseData *v34; // rax
  __int64 v35; // r8
  _QWORD *AadDeviceToken; // rax
  __int64 v37; // rax
  int v38; // r15d
  __int128 v39; // xmm6
  __int128 v40; // xmm7
  __int128 v41; // xmm8
  struct _GUID v42; // xmm9
  unsigned int MillisToNextDownloadOnCostedNetwork; // eax
  int v44; // edx
  __int64 v45; // r8
  std::_Ref_count_base *v46; // r12
  int Qword; // eax
  unsigned __int64 FileTimeAsULL; // rax
  int v49; // eax
  _QWORD *v50; // rax
  char **v51; // rax
  __int64 v52; // rcx
  _QWORD *v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rax
  int v58; // r8d
  __int64 v59; // r9
  __int64 v60; // r10
  __int64 v61; // r11
  Microsoft::Diagnostics::HeartBeat *v62; // rax
  Microsoft::Diagnostics::HeartBeat *v63; // rax
  Microsoft::Diagnostics::HeartBeat *HeartbeatManager; // rcx
  Microsoft::Diagnostics::HeartBeat *v65; // rax
  unsigned int v66; // ebx
  unsigned int v67; // ebx
  int v68; // r9d
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  __int64 v71; // rax
  __int64 v72; // rax
  struct _GUID v73; // xmm0
  _OWORD *v74; // rax
  BOOL v75; // edx
  int v76; // ecx
  int v77; // eax
  unsigned int v78; // ebx
  __m128i v79; // xmm6
  unsigned __int64 v80; // rax
  char **v81; // rax
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rax
  int v87; // r8d
  __int64 v88; // r9
  __int64 v89; // r10
  __int64 v90; // r11
  __int64 v91; // rax
  __int64 v92; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-838h]
  unsigned int dwCreationDispositiona; // [rsp+20h] [rbp-838h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-838h]
  int dwCreationDispositionc; // [rsp+20h] [rbp-838h]
  std::_Ref_count_base *v97[2]; // [rsp+80h] [rbp-7D8h] BYREF
  DWORD v98[4]; // [rsp+90h] [rbp-7C8h] BYREF
  struct _GUID v99; // [rsp+A0h] [rbp-7B8h] BYREF
  int QueryParameters; // [rsp+B0h] [rbp-7A8h] BYREF
  bool v101; // [rsp+B4h] [rbp-7A4h]
  char v102; // [rsp+B5h] [rbp-7A3h]
  int v103[4]; // [rsp+C0h] [rbp-798h] BYREF
  __int64 v104; // [rsp+D0h] [rbp-788h] BYREF
  __int128 *v105; // [rsp+D8h] [rbp-780h] BYREF
  char v106; // [rsp+E0h] [rbp-778h]
  __int64 v107; // [rsp+E8h] [rbp-770h] BYREF
  __int64 v108; // [rsp+F0h] [rbp-768h] BYREF
  unsigned int v109[2]; // [rsp+F8h] [rbp-760h] BYREF
  __int64 v110[2]; // [rsp+100h] [rbp-758h] BYREF
  unsigned __int64 *v111; // [rsp+110h] [rbp-748h]
  __int64 v112; // [rsp+118h] [rbp-740h] BYREF
  __int128 v113; // [rsp+120h] [rbp-738h] BYREF
  __int64 v114; // [rsp+130h] [rbp-728h]
  __int64 v115; // [rsp+138h] [rbp-720h] BYREF
  Microsoft::Diagnostics::SettingsManager *v116; // [rsp+140h] [rbp-718h]
  _QWORD v117[2]; // [rsp+148h] [rbp-710h] BYREF
  char v118; // [rsp+158h] [rbp-700h]
  _BYTE *v119; // [rsp+160h] [rbp-6F8h]
  __int64 v120[2]; // [rsp+170h] [rbp-6E8h] BYREF
  _BYTE v121[16]; // [rsp+180h] [rbp-6D8h] BYREF
  _BYTE v122[16]; // [rsp+190h] [rbp-6C8h] BYREF
  _BYTE v123[16]; // [rsp+1A0h] [rbp-6B8h] BYREF
  __int64 v124[2]; // [rsp+1B0h] [rbp-6A8h] BYREF
  char *v125[2]; // [rsp+1C0h] [rbp-698h] BYREF
  __int64 v126; // [rsp+1D0h] [rbp-688h]
  unsigned __int64 v127; // [rsp+1D8h] [rbp-680h]
  _QWORD Src[4]; // [rsp+1E0h] [rbp-678h] BYREF
  PWSTR pszPathOut[3]; // [rsp+200h] [rbp-658h] BYREF
  unsigned __int64 v130; // [rsp+218h] [rbp-640h]
  LPCWSTR lpFileName[4]; // [rsp+220h] [rbp-638h] BYREF
  PCWSTR pszPathIn[4]; // [rsp+240h] [rbp-618h] BYREF
  _BYTE v133[32]; // [rsp+260h] [rbp-5F8h] BYREF
  _QWORD v134[3]; // [rsp+280h] [rbp-5D8h] BYREF
  _QWORD v135[6]; // [rsp+2A0h] [rbp-5B8h] BYREF
  int v136[282]; // [rsp+2D0h] [rbp-588h] BYREF
  int v137[14]; // [rsp+738h] [rbp-120h] BYREF
  __int64 v138[4]; // [rsp+770h] [rbp-E8h] BYREF
  _BYTE v139[32]; // [rsp+790h] [rbp-C8h] BYREF
  _BYTE v140[32]; // [rsp+7B0h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+858h] [rbp+0h]

  v111 = a4;
  v112 = a3;
  v9 = this;
  v116 = this;
  v120[0] = a5;
  v119 = a8;
  v10 = 0;
  v98[0] = 0;
  v113 = 0;
  v114 = 0;
  v105 = &v113;
  v106 = 1;
  if ( !Microsoft::Diagnostics::SettingsEndpoint::HasValidPartnerFeature(a2) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)0x8007007BLL,
      dwCreationDisposition);
    v106 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
    return 2147942523LL;
  }
  if ( *((_WORD *)a2 + 4) )
  {
    if ( !*(_QWORD *)(a5 + 16) )
    {
      *(struct _GUID *)((char *)v9 + 616) = *Microsoft::Diagnostics::SettingsManager::GetMsaTokenClientIdGuid(&v99);
      Ticket = Microsoft::Diagnostics::DeviceTicket::GetTicket((char *)v9 + 552, a5);
      if ( Ticket < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x979,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
          (const char *)(unsigned int)Ticket,
          dwCreationDisposition);
    }
  }
  v13 = _InterlockedCompareExchange64((_QWORD *)&xmmword_18043BF70 + 1, 0, 0) != 0;
  v101 = v13;
  if ( *((_BYTE *)a2 + 5) && v13 )
  {
    EnterpriseData = Microsoft::Diagnostics::LifetimeManager::GetEnterpriseData((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    LOBYTE(v15) = 1;
    Microsoft::Diagnostics::EnterpriseData::PopulateAadDeviceToken(EnterpriseData, v15);
  }
  Microsoft::Diagnostics::SettingsEndpoint::GetUnexpandedSettingsFilePath(a2, lpFileName);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString((LPCWSTR)lpFileName);
  *(_OWORD *)v97 = *(_OWORD *)&off_18035F080;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v97) )
  {
    std::wstring::operator std::wstring_view((char *)a2 + 168, v97);
    if ( v97[1] )
    {
      v16 = (const WCHAR *)lpFileName;
      if ( lpFileName[3] > (LPCWSTR)7 )
        v16 = lpFileName[0];
      if ( GetFileAttributesW(v16) == -1 )
      {
        v98[0] = GetLastError();
        v17 = std::wstring::operator std::wstring_view(&unk_18043B470, &v99);
        std::wstring::_Assign<wchar_t>((char **)a2 + 21, *(const void **)v17, *(char **)(v17 + 8));
        v97[0] = (std::_Ref_count_base *)L"SettingsManager_SettingsFileWentMissing_0";
        v97[1] = (std::_Ref_count_base *)41;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
          (unsigned int)v136,
          (unsigned int)v97,
          0x1000000,
          0,
          0,
          0,
          0);
        std::wstring::operator std::wstring_view((char *)a2 + 104, &v107);
        v97[0] = (std::_Ref_count_base *)L"Partner";
        v97[1] = (std::_Ref_count_base *)7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(
          (unsigned int)v136,
          (unsigned int)v137);
        std::wstring::operator std::wstring_view((char *)a2 + 136, &v107);
        v97[0] = (std::_Ref_count_base *)L"Feature";
        v97[1] = (std::_Ref_count_base *)7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(
          (unsigned int)v136,
          (unsigned int)v137);
        std::wstring::operator std::wstring_view((char *)a2 + 72, &v107);
        v97[0] = (std::_Ref_count_base *)L"Version";
        v97[1] = (std::_Ref_count_base *)7;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(
          (unsigned int)v136,
          (unsigned int)v137);
        v97[0] = (std::_Ref_count_base *)L"GetFileAttributesLastError";
        v97[1] = (std::_Ref_count_base *)26;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v136, (unsigned int)v137);
        v97[0] = (std::_Ref_count_base *)L"DestinationFilePath";
        v97[1] = (std::_Ref_count_base *)19;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
        std::wstring::wstring(v134, (char *)a2 + 40);
        v10 = 4;
        v98[0] = 4;
        v97[0] = (std::_Ref_count_base *)L"LastFileWrittenPath";
        v97[1] = (std::_Ref_count_base *)19;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        v102 = *(_BYTE *)a2;
        v97[0] = (std::_Ref_count_base *)L"LastFileWrittenWasThisEpoch";
        v97[1] = (std::_Ref_count_base *)27;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<bool>((unsigned int)v136, (unsigned int)v137);
        v110[0] = *((_QWORD *)a2 + 3);
        v97[0] = (std::_Ref_count_base *)L"LastDownloadTime";
        v97[1] = (std::_Ref_count_base *)16;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v136, (unsigned int)v137);
        v18 = v111;
        if ( *((_QWORD *)a2 + 3) <= *v111 )
          v19 = (*v111 - *((_QWORD *)a2 + 3)) / 0x2710;
        else
          v19 = 0;
        v110[0] = v19;
        v97[0] = (std::_Ref_count_base *)L"LastDownloadDeltaMillis";
        v97[1] = (std::_Ref_count_base *)23;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v136, (unsigned int)v137);
        if ( *((_QWORD *)a2 + 4) <= *v18 )
          v20 = (*v18 - *((_QWORD *)a2 + 4)) / 0x2710;
        else
          v20 = 0;
        v110[0] = v20;
        v97[0] = (std::_Ref_count_base *)L"LastFileWrittenDeltaMillis";
        v97[1] = (std::_Ref_count_base *)26;
        Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v136, (unsigned int)v137);
        std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
          &v113,
          v136);
        Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v136);
        v9 = v116;
      }
    }
  }
  std::operator+<wchar_t>(pszPathIn, lpFileName, L".new");
  LOBYTE(v107) = 0;
  v108 = -1;
  std::wstring::wstring(pszPathOut, pszPathIn[2], 0);
  v21 = (const WCHAR *)pszPathIn;
  if ( pszPathIn[3] > (PCWSTR)7 )
    v21 = pszPathIn[0];
  v22 = (WCHAR *)pszPathOut;
  if ( v130 > 7 )
    v22 = pszPathOut[0];
  v23 = PathCchCanonicalizeEx(v22, (size_t)pszPathOut[2] + 1, v21, 0);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9AD,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)v23,
      dwCreationDisposition);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    v106 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
    return v24;
  }
  v25 = (const WCHAR *)pszPathOut;
  if ( v130 > 7 )
    v25 = pszPathOut[0];
  FileW = CreateFileW(v25, 0xC0010000, 1u, 0, 2u, 0x100u, 0);
  if ( FileW != (HANDLE)-1LL )
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v108,
      FileW);
  std::wstring::wstring(Src);
  v27 = (CONTEXT *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 64LL);
  RtlCaptureContext(v27);
  LOBYTE(v28) = 3;
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::ThreadMonitor(v110, 300000, v28, v27);
  *(_OWORD *)v97 = *(_OWORD *)&off_18035F390;
  QueryParameters = Microsoft::Diagnostics::SettingsDownloader::GetQueryParameters(
                      Src,
                      (__int64)v9 + 464,
                      (__int64)v9 + 496);
  if ( QueryParameters < 0 )
  {
    v97[0] = (std::_Ref_count_base *)L"SettingsManager_FailedToGetTargetingAttributes_0";
    v97[1] = (std::_Ref_count_base *)48;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v136,
      (unsigned int)v97,
      0x1000000,
      0,
      0,
      0,
      0);
    v97[0] = (std::_Ref_count_base *)L"ErrorCode";
    v97[1] = (std::_Ref_count_base *)9;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v136, (unsigned int)v137);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
      &v113,
      v136);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v136);
  }
  *(_OWORD *)v97 = *(_OWORD *)&off_18035F070;
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v97)
    && std::wstring::find(Src, L"&acc-validationmerge=true", 0) == -1 )
  {
    std::wstring::_Append<wchar_t>(Src);
  }
  Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor::~ThreadMonitor((Microsoft::Diagnostics::UtcWatchdog::ThreadMonitor *)v110);
  std::wstring::wstring(v125);
  v29 = 0;
  QueryParameters = 0;
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v135);
  *(_QWORD *)v109 = 0;
  v115 = 0;
  *(_OWORD *)v97 = *(_OWORD *)&off_18035F060;
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(v97) )
  {
    v30 = 0;
    v98[0] = 0;
    v31 = 304;
    std::wstring::operator std::wstring_view((char *)a2 + 168, v97);
    std::wstring::_Assign<wchar_t>(v125, v97[0], (char *)v97[1]);
    v29 = *((_DWORD *)a2 + 4);
    QueryParameters = v29;
LABEL_65:
    Microsoft::Diagnostics::SettingsManager::NotifySuccessfulSettingsDownload(v116, a2, v111);
    goto LABEL_66;
  }
  std::wstring::wstring(v134);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BFB0, 0, 0) )
  {
    SystemStateManager = Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    Microsoft::Diagnostics::ProxyConfig::GetProxyOverrideServer((struct Microsoft::Diagnostics::SystemStateManager *)((char *)SystemStateManager + 696));
    v10 |= 8u;
    v98[0] = v10;
    std::wstring::operator=(v134, v133);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v133);
  }
  Microsoft::Diagnostics::UserManager::GetNetworkImpersonationToken(&v104);
  *(_OWORD *)v97 = 0;
  v110[0] = v104;
  std::wstring::wstring(v138);
  v33 = *((_QWORD *)v9 + 138);
  if ( *((_BYTE *)a2 + 5) && v101 )
  {
    v34 = Microsoft::Diagnostics::LifetimeManager::GetEnterpriseData((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    LOBYTE(v35) = 1;
    AadDeviceToken = (_QWORD *)Microsoft::Diagnostics::EnterpriseData::GetAadDeviceToken(v34, v117, v35);
    v37 = std::wstring::wstring((__int64)v140, AadDeviceToken);
    v38 = v10 | 1;
  }
  else
  {
    v37 = std::wstring::wstring(v139, &unk_18043B470);
    v38 = v10 | 2;
  }
  v98[0] = v38;
  v39 = *(_OWORD *)std::wstring::operator std::wstring_view(v37, v122);
  v40 = *(_OWORD *)std::wstring::operator std::wstring_view(v120[0], v123);
  v41 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPathOut, v121);
  v42 = *(struct _GUID *)std::wstring::operator std::wstring_view(Src, v133);
  MillisToNextDownloadOnCostedNetwork = Microsoft::Diagnostics::SettingsManager::GetMillisToNextDownloadOnCostedNetwork(
                                          v9,
                                          a2);
  *(_OWORD *)v120 = v39;
  *(_OWORD *)v124 = v40;
  *(_OWORD *)v103 = v41;
  v99 = v42;
  LOBYTE(v44) = MillisToNextDownloadOnCostedNetwork == 0;
  v30 = Microsoft::Diagnostics::SettingsDownloader::PerformDownload(
          (int)a2,
          v44,
          (int)&v99,
          (int)v103,
          (__int64)v124,
          (__int64)v120,
          (__int64)&v107,
          v135,
          v112,
          a7,
          v33,
          (__int64)v138,
          v110[0],
          (__int64)v97,
          (__int64)v109,
          (__int64)&v115);
  v98[0] = v30;
  if ( (v38 & 2) != 0 )
  {
    LOBYTE(v38) = v38 & 0xFD;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v139);
  }
  if ( (v38 & 1) != 0 )
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v140);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v138);
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&xmmword_18043BFB0, 0, 0) )
  {
    Microsoft::Diagnostics::LifetimeManager::GetSystemStateManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    v99 = *(struct _GUID *)std::wstring::operator std::wstring_view(v134, v133);
    Microsoft::Diagnostics::ProxyConfig::Update(v45 + 696, &v99, (unsigned int)v30);
  }
  if ( v30 == -2147023673 )
  {
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        &dword_18042D328,
        &unk_1803C37C6);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)0x800704C7LL,
      dwCreationDispositiona);
    if ( v97[1] )
      std::_Ref_count_base::_Decref(v97[1]);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v104);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v125);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    v106 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
    return 2147943623LL;
  }
  v31 = 0;
  if ( v30 >= 0 )
  {
    v46 = v97[0];
    std::wstring::operator=(v125, (char *)v97[0] + 72);
    v31 = *((_DWORD *)v46 + 16);
    if ( v31 == 200 )
    {
      v29 = *((_DWORD *)v46 + 27);
      QueryParameters = v29;
    }
  }
  if ( v97[1] )
    std::_Ref_count_base::_Decref(v97[1]);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v104);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
  if ( v31 == 304 || v31 == 200 )
    goto LABEL_65;
LABEL_66:
  if ( v31 != 304 )
  {
    v97[0] = (std::_Ref_count_base *)L"SettingsManager_DownloadOneSettingsNamespace_0";
    v97[1] = (std::_Ref_count_base *)46;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v136,
      (unsigned int)v97,
      0x1000000,
      0,
      0,
      0,
      0);
    v97[0] = (std::_Ref_count_base *)L"ErrorCode";
    v97[1] = (std::_Ref_count_base *)9;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 72, &v99);
    v97[0] = (std::_Ref_count_base *)L"Version";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 104, &v99);
    v97[0] = (std::_Ref_count_base *)L"Partner";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 136, &v99);
    v97[0] = (std::_Ref_count_base *)L"Feature";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"Parameters";
    v97[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 168, &v99);
    v97[0] = (std::_Ref_count_base *)L"ClientETag";
    v97[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"ServerETag";
    v97[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"RefreshIntervalFromHeader";
    v97[1] = (std::_Ref_count_base *)25;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"Headers";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
    LODWORD(v104) = v31 == 200;
    v97[0] = (std::_Ref_count_base *)L"Changed";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<int>((int)v136, (int)v137);
    v97[0] = (std::_Ref_count_base *)L"DownloadPollTime";
    v97[1] = (std::_Ref_count_base *)16;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"DownloadDurationMs";
    v97[1] = (std::_Ref_count_base *)18;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"DownloadOnDiskFileSizeBytes";
    v97[1] = (std::_Ref_count_base *)27;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<__int64>((int)v136, (int)v137);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
      &v113,
      v136);
LABEL_76:
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v136);
    v30 = v98[0];
    v29 = QueryParameters;
    goto LABEL_77;
  }
  v110[0] = 0;
  v99 = *(struct _GUID *)&off_18035F050;
  *(_OWORD *)v103 = *(_OWORD *)&off_18035F2B0;
  Qword = Microsoft::Diagnostics::Utils::Registry::GetQword(-2147483646, v103, &v99, v110);
  if ( Qword < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA3E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)Qword,
      dwCreationDispositiona);
  FileTimeAsULL = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
  if ( v110[0] > FileTimeAsULL )
  {
    v99 = *(struct _GUID *)&off_18035F050;
    *(_OWORD *)v103 = *(_OWORD *)&off_18035F2B0;
    v49 = Microsoft::Diagnostics::Utils::Registry::SetQword(-2147483646, (int)v103, (int)&v99, v110[0], 0);
    if ( v49 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA44,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
        (const char *)(unsigned int)v49,
        dwCreationDispositionb);
    goto LABEL_75;
  }
  if ( FileTimeAsULL - v110[0] >= 0xC92A69C000LL )
  {
LABEL_75:
    v97[0] = (std::_Ref_count_base *)L"SettingsManager_DownloadOneSettingsNamespace_0";
    v97[1] = (std::_Ref_count_base *)46;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v136,
      (unsigned int)v97,
      0x1000000,
      0,
      0,
      0,
      0);
    v97[0] = (std::_Ref_count_base *)L"ErrorCode";
    v97[1] = (std::_Ref_count_base *)9;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 72, &v99);
    v97[0] = (std::_Ref_count_base *)L"Version";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 104, &v99);
    v97[0] = (std::_Ref_count_base *)L"Partner";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 136, &v99);
    v97[0] = (std::_Ref_count_base *)L"Feature";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"Parameters";
    v97[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
    std::wstring::operator std::wstring_view((char *)a2 + 168, &v99);
    v97[0] = (std::_Ref_count_base *)L"ClientETag";
    v97[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"ServerETag";
    v97[1] = (std::_Ref_count_base *)10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"RefreshIntervalFromHeader";
    v97[1] = (std::_Ref_count_base *)25;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"Headers";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>((unsigned int)v136, (unsigned int)v137);
    LODWORD(v104) = 0;
    v97[0] = (std::_Ref_count_base *)L"Changed";
    v97[1] = (std::_Ref_count_base *)7;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<int>((int)v136, (int)v137);
    v97[0] = (std::_Ref_count_base *)L"DownloadPollTime";
    v97[1] = (std::_Ref_count_base *)16;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"DownloadDurationMs";
    v97[1] = (std::_Ref_count_base *)18;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v136, (unsigned int)v137);
    v97[0] = (std::_Ref_count_base *)L"DownloadOnDiskFileSizeBytes";
    v97[1] = (std::_Ref_count_base *)27;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<__int64>((int)v136, (int)v137);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(
      &v113,
      v136);
    goto LABEL_76;
  }
LABEL_77:
  if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
  {
    LODWORD(v104) = v31;
    v98[0] = v31 == 200;
    v50 = v135;
    if ( v135[3] > 7u )
      v50 = (_QWORD *)v135[0];
    v112 = (__int64)v50;
    QueryParameters = v29;
    v51 = v125;
    if ( v127 > 7 )
      v51 = (char **)v125[0];
    v120[0] = (__int64)v51;
    std::wstring::operator std::wstring_view((char *)a2 + 168, &v99);
    std::wstring::operator std::wstring_view(v52, v103);
    _tlgWrapBinary<wchar_t,2>(v133, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
    v53 = Src;
    if ( Src[3] > 7u )
      v53 = (_QWORD *)Src[0];
    v110[0] = (__int64)v53;
    std::wstring::operator std::wstring_view((char *)a2 + 136, &v99);
    std::wstring::operator std::wstring_view(v54, v103);
    _tlgWrapBinary<wchar_t,2>(v121, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
    std::wstring::operator std::wstring_view((char *)a2 + 104, &v99);
    std::wstring::operator std::wstring_view(v55, v103);
    _tlgWrapBinary<wchar_t,2>(v123, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
    std::wstring::operator std::wstring_view((char *)a2 + 72, &v99);
    std::wstring::operator std::wstring_view(v56, v103);
    v57 = _tlgWrapBinary<wchar_t,2>(v122, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
    v109[0] = v30;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)v110,
      (unsigned int)&unk_1803C3709,
      v58,
      v59,
      (__int64)v109,
      v57,
      v59,
      v60,
      (__int64)v110,
      v61,
      (__int64)v120,
      (__int64)&QueryParameters,
      (__int64)&v112,
      (__int64)v98,
      (__int64)&v104);
  }
  if ( v30 >= 0 )
  {
    HeartbeatManager = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
    Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpAttempts(HeartbeatManager);
    if ( v31 != 304 && v31 != 404 && v31 != 200 && v31 != 204 )
    {
      v65 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpFailures(v65);
      v66 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xA9C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)0x3A,
              dwCreationDispositiona);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v125);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      v106 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
      return v66;
    }
    if ( a6 && v31 == 404 )
    {
      v67 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0xAA6,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
              (const char *)0x43,
              dwCreationDispositiona);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v125);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      v106 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
      return v67;
    }
    if ( v31 == 204 && (unsigned __int16)(*((_WORD *)a2 + 5) - 3) <= 1u )
    {
      if ( (unsigned int)dword_18042D328 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18042D328,
          &unk_1803C36B9);
      std::wstring::operator std::wstring_view((char *)a2 + 136, &v99);
      std::wstring::operator std::wstring_view((char *)a2 + 104, v103);
      LOBYTE(v68) = *((_WORD *)a2 + 3) == 0;
      Microsoft::Diagnostics::SettingsManager::UnregisterSettingsEndpoint(
        (_DWORD)v116,
        (unsigned int)v103,
        (unsigned int)&v99,
        v68,
        6);
      *v119 = 1;
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v125);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      v106 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
      return 0;
    }
    else
    {
      *((_QWORD *)a2 + 3) = *v111;
      *(_WORD *)((char *)a2 + 1) = 0;
      v117[0] = v116;
      v117[1] = a2;
      v118 = 1;
      v69 = *((_DWORD *)v116 + 279);
      if ( v29 )
      {
        if ( v29 < v69 )
          v29 = *((_DWORD *)v116 + 279);
        if ( v29 > 0x1C20 )
          v29 = 7200;
        if ( v29 % v69 )
          v70 = v29 + v69 - v29 % v69;
        else
          v70 = v29;
        *((_DWORD *)a2 + 4) = v70;
      }
      if ( v126 && (v31 == 304 || v31 == 204) )
      {
        v71 = std::wstring::operator std::wstring_view(v125, v133);
        std::wstring::_Assign<wchar_t>((char **)a2 + 21, *(const void **)v71, *(char **)(v71 + 8));
        v72 = std::wstring::operator std::wstring_view(Src, v133);
        std::wstring::_Assign<wchar_t>((char **)a2 + 25, *(const void **)v72, *(char **)(v72 + 8));
      }
      if ( v31 == 200 )
      {
        v73 = *(struct _GUID *)std::wstring::operator std::wstring_view(pszPathIn, v133);
        v74 = (_OWORD *)std::wstring::operator std::wstring_view(lpFileName, v121);
        v75 = *((_BYTE *)a2 + 4) != 0;
        v99 = v73;
        *(_OWORD *)v103 = *v74;
        LOBYTE(v76) = *((_WORD *)a2 + 3) == 0;
        v77 = Microsoft::Diagnostics::SettingsDownloader::PersistDownload(
                v76,
                v75,
                (int)v103,
                (int)&v99,
                (AutoDeleteFile *)&v107);
        v78 = v77;
        if ( v77 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAEF,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
            (const char *)(unsigned int)v77,
            dwCreationDispositionc);
          v118 = 0;
          Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_2_::operator()(v117);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v125);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
          AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
          v106 = 0;
          Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
          std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
          return v78;
        }
        v79 = *(__m128i *)std::wstring::operator std::wstring_view(lpFileName, v133);
        v80 = Microsoft::Diagnostics::Utils::Time::GetFileTimeAsULL();
        *(_BYTE *)a2 = 1;
        *((_QWORD *)a2 + 4) = v80;
        std::wstring::_Assign<wchar_t>(
          (char **)a2 + 5,
          (const void *)v79.m128i_i64[0],
          (char *)_mm_srli_si128(v79, 8).m128i_i64[0]);
        *v119 = 1;
        if ( (unsigned int)dword_18042D328 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 512) )
        {
          v81 = v125;
          if ( v127 > 7 )
            v81 = (char **)v125[0];
          v112 = (__int64)v81;
          std::wstring::operator std::wstring_view((char *)a2 + 168, &v99);
          std::wstring::operator std::wstring_view(v82, v103);
          _tlgWrapBinary<wchar_t,2>(v133, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
          std::wstring::operator std::wstring_view((char *)a2 + 136, &v99);
          std::wstring::operator std::wstring_view(v83, v103);
          _tlgWrapBinary<wchar_t,2>(v121, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
          std::wstring::operator std::wstring_view((char *)a2 + 104, &v99);
          std::wstring::operator std::wstring_view(v84, v103);
          _tlgWrapBinary<wchar_t,2>(v123, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
          std::wstring::operator std::wstring_view((char *)a2 + 72, &v99);
          std::wstring::operator std::wstring_view(v85, v103);
          v86 = _tlgWrapBinary<wchar_t,2>(v122, *(_QWORD *)v103, *(unsigned int *)v99.Data4);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapperArray<1>,_tlgWrapSz<wchar_t>>(
            (unsigned int)&v112,
            (unsigned int)&unk_1803C364D,
            v87,
            v88,
            v86,
            v88,
            v89,
            v90,
            (__int64)&v112);
        }
        if ( v126 )
        {
          v91 = std::wstring::operator std::wstring_view(v125, v133);
          std::wstring::_Assign<wchar_t>((char **)a2 + 21, *(const void **)v91, *(char **)(v91 + 8));
          v92 = std::wstring::operator std::wstring_view(Src, v133);
          std::wstring::_Assign<wchar_t>((char **)a2 + 25, *(const void **)v92, *(char **)(v92 + 8));
        }
      }
      v118 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_2_::operator()(v117);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v125);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
      AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      v106 = 0;
      Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
      std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
      return 0;
    }
  }
  else
  {
    if ( v30 == -2147012894 )
    {
      v62 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpAttempts(v62);
      v63 = Microsoft::Diagnostics::LifetimeManager::GetHeartbeatManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      Microsoft::Diagnostics::HeartBeat::IncreaseSettingsHttpFailures(v63);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA8A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsmanager.cpp",
      (const char *)(unsigned int)v30,
      dwCreationDispositiona);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v125);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathOut);
    AutoDeleteFile::~AutoDeleteFile((AutoDeleteFile *)&v107);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPathIn);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
    v106 = 0;
    Microsoft::Diagnostics::SettingsManager::PerformNamespaceDownload_::_3_::_lambda_1_::operator()(&v105);
    std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(&v113);
    return (unsigned int)v30;
  }
}

```

## disassembly

```asm
0x180194dac  mov     r11, rsp
0x180194daf  push    rbx
0x180194db0  push    rsi
0x180194db1  push    rdi
0x180194db2  push    r12
0x180194db4  push    r13
0x180194db6  push    r14
0x180194db8  push    r15
0x180194dba  sub     rsp, 820h
0x180194dc1  movaps  xmmword ptr [r11-48h], xmm6
0x180194dc6  movaps  xmmword ptr [r11-58h], xmm7
0x180194dcb  movaps  xmmword ptr [r11-68h], xmm8
0x180194dd0  movaps  xmmword ptr [r11-78h], xmm9
0x180194dd5  mov     rax, cs:__security_cookie
0x180194ddc  xor     rax, rsp
0x180194ddf  mov     [rsp+858h+var_88], rax
0x180194de7  mov     [rsp+858h+var_748], r9
0x180194def  mov     [rsp+858h+var_740], r8
0x180194df7  mov     rdi, rdx
0x180194dfa  mov     r14, rcx
0x180194dfd  mov     [rsp+858h+var_718], rcx
0x180194e05  mov     rsi, [rsp+858h+arg_20]
0x180194e0d  mov     [rsp+858h+var_6E8], rsi
0x180194e15  mov     rax, [rsp+858h+arg_38]
0x180194e1d  mov     [rsp+858h+var_6F8], rax
0x180194e25  xor     r12d, r12d
0x180194e28  mov     r15d, r12d
0x180194e2b  mov     [r11-7C8h], r12d
0x180194e32  xorps   xmm0, xmm0
0x180194e35  movdqu  [rsp+858h+var_738], xmm0
0x180194e3e  mov     [r11-728h], r12
0x180194e45  lea     rax, [r11-738h]
0x180194e4c  mov     [r11-780h], rax
0x180194e53  mov     [rsp+858h+var_778], 1
0x180194e5b  mov     rcx, rdx; this
0x180194e5e  call    ?HasValidPartnerFeature@SettingsEndpoint@Diagnostics@Microsoft@@QEBA_NXZ; Microsoft::Diagnostics::SettingsEndpoint::HasValidPartnerFeature(void)
0x180194e63  test    al, al
0x180194e65  jnz     short loc_180194EB3
0x180194e67  mov     rcx, [rsp+858h]; this
0x180194e6f  mov     ebx, 8007007Bh
0x180194e74  mov     r9d, ebx; char *
0x180194e77  lea     r8, aOnecoreBaseTel_84; "onecore\\base\\telemetry\\utc\\service"...
0x180194e7e  mov     edx, 96Fh; void *
0x180194e83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180194e88  nop
0x180194e89  mov     [rsp+858h+var_778], r12b
0x180194e91  lea     rcx, [rsp+858h+var_780]
0x180194e99  call    _Microsoft__Diagnostics__SettingsManager__PerformNamespaceDownload____3____lambda_1___operator__
0x180194e9e  nop
0x180194e9f  lea     rcx, [rsp+858h+var_738]
0x180194ea7  call    ?_Tidy@?$vector@VAsimovSyntheticEvent@Diagnostics@Microsoft@@V?$allocator@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Tidy(void)
0x180194eac  mov     eax, ebx
0x180194eae  jmp     loc_1801974F0
0x180194eb3  cmp     [rdi+8], r12w
0x180194eb8  jz      short loc_180194F0C
0x180194eba  cmp     [rsi+10h], r12
0x180194ebe  jnz     short loc_180194F0C
0x180194ec0  lea     rbx, [r14+228h]
0x180194ec7  lea     rcx, [rsp+858h+var_7B8]; retstr
0x180194ecf  call    ?GetMsaTokenClientIdGuid@SettingsManager@Diagnostics@Microsoft@@SA?AU_GUID@@XZ; Microsoft::Diagnostics::SettingsManager::GetMsaTokenClientIdGuid(void)
0x180194ed4  movups  xmm0, xmmword ptr [rax]
0x180194ed7  movdqu  xmmword ptr [rbx+40h], xmm0
0x180194edc  mov     rdx, rsi
0x180194edf  mov     rcx, rbx
0x180194ee2  call    ?GetTicket@DeviceTicket@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::DeviceTicket::GetTicket(std::wstring &)
0x180194ee7  mov     rcx, [rsp+858h]; this
0x180194eef  test    eax, eax
0x180194ef1  jns     short loc_180194F0C
0x180194ef3  mov     r9d, eax; char *
0x180194ef6  lea     r13, aOnecoreBaseTel_84; "onecore\\base\\telemetry\\utc\\service"...
0x180194efd  mov     r8, r13; unsigned int
0x180194f00  mov     edx, 979h; void *
0x180194f05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180194f0a  jmp     short loc_180194F13
0x180194f0c  lea     r13, aOnecoreBaseTel_84; "onecore\\base\\telemetry\\utc\\service"...
0x180194f13  mov     rcx, r12
0x180194f16  xor     eax, eax
0x180194f18  lock cmpxchg qword ptr cs:xmmword_18043BF70+8, rcx
0x180194f21  setnz   al
0x180194f24  mov     [rsp+858h+var_7A4], al
0x180194f2b  cmp     [rdi+5], r12b
0x180194f2f  jz      short loc_180194F4B
0x180194f31  test    al, al
0x180194f33  jz      short loc_180194F4B
0x180194f35  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x180194f3c  call    ?GetEnterpriseData@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVEnterpriseData@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetEnterpriseData(void)
0x180194f41  mov     dl, 1
0x180194f43  mov     rcx, rax
0x180194f46  call    ?PopulateAadDeviceToken@EnterpriseData@Diagnostics@Microsoft@@QEAAXVAadDeviceTokenType@23@@Z; Microsoft::Diagnostics::EnterpriseData::PopulateAadDeviceToken(Microsoft::Diagnostics::AadDeviceTokenType)
0x180194f4b  lea     rdx, [rsp+858h+lpFileName]
0x180194f53  mov     rcx, rdi
0x180194f56  call    ?GetUnexpandedSettingsFilePath@SettingsEndpoint@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::SettingsEndpoint::GetUnexpandedSettingsFilePath(void)
0x180194f5b  nop
0x180194f5c  xor     r8d, r8d
0x180194f5f  mov     dl, 1
0x180194f61  lea     rcx, [rsp+858h+lpFileName]; lpSrc
0x180194f69  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180194f6e  movups  xmm0, xmmword ptr cs:off_18035F080; "SkipMissingSettingsFileDetection"
0x180194f75  movdqu  xmmword ptr [rsp+858h+var_7D8], xmm0
0x180194f7e  lea     rcx, [rsp+858h+var_7D8]
0x180194f86  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x180194f8b  test    al, al
0x180194f8d  jnz     loc_1801953E0
0x180194f93  lea     rbx, [rdi+0A8h]
0x180194f9a  lea     rdx, [rsp+858h+var_7D8]
0x180194fa2  mov     rcx, rbx
0x180194fa5  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180194faa  mov     esi, 7
0x180194faf  cmp     [rsp+858h+var_7D8+8], r12
0x180194fb7  jz      loc_1801953E5
0x180194fbd  lea     rcx, [rsp+858h+lpFileName]
0x180194fc5  cmp     [rsp+858h+var_620], rsi
0x180194fcd  cmova   rcx, [rsp+858h+lpFileName]; lpFileName
0x180194fd6  call    cs:__imp_GetFileAttributesW
0x180194fdd  nop     dword ptr [rax+rax+00h]
0x180194fe2  cmp     eax, 0FFFFFFFFh
0x180194fe5  jnz     loc_1801953E5
0x180194feb  call    cs:__imp_GetLastError
0x180194ff2  nop     dword ptr [rax+rax+00h]
0x180194ff7  mov     [rsp+858h+var_7C8], eax
0x180194ffe  lea     rdx, [rsp+858h+var_7B8]
0x180195006  lea     rcx, unk_18043B470
0x18019500d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180195012  mov     r8, [rax+8]
0x180195016  mov     rdx, [rax]
0x180195019  mov     rcx, rbx
0x18019501c  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180195021  lea     rdx, aSettingsmanage_10; "SettingsManager_SettingsFileWentMissing"...
0x180195028  mov     [rsp+858h+var_7D8], rdx
0x180195030  mov     [rsp+858h+var_7D8+8], 29h ; ')'
0x18019503c  mov     r8d, 1000000h
0x180195042  mov     byte ptr [rsp+858h+hTemplateFile], r12b
0x180195047  mov     byte ptr [rsp+858h+dwFlagsAndAttributes], r12b
0x18019504c  mov     byte ptr [rsp+858h+dwCreationDisposition], r12b
0x180195051  mov     r9, 400000000000h
0x18019505b  lea     rdx, [rsp+858h+var_7D8]
0x180195063  lea     rcx, [rsp+858h+var_588]
0x18019506b  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x180195070  nop
0x180195071  lea     rcx, [rdi+68h]
0x180195075  lea     rdx, [rsp+858h+var_770]
0x18019507d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180195082  lea     r12, aPartner; "Partner"
0x180195089  mov     [rsp+858h+var_7D8], r12
0x180195091  mov     [rsp+858h+var_7D8+8], rsi
0x180195099  lea     r9, [rsp+858h+var_770]
0x1801950a1  lea     r8, [rsp+858h+var_7D8]
0x1801950a9  lea     rdx, [rsp+858h+var_120]
0x1801950b1  lea     rcx, [rsp+858h+var_588]
0x1801950b9  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x1801950be  lea     rcx, [rdi+88h]
0x1801950c5  lea     rdx, [rsp+858h+var_770]
0x1801950cd  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801950d2  lea     r12, aFeature; "Feature"
0x1801950d9  mov     [rsp+858h+var_7D8], r12
0x1801950e1  mov     [rsp+858h+var_7D8+8], rsi
0x1801950e9  lea     r9, [rsp+858h+var_770]
0x1801950f1  lea     r8, [rsp+858h+var_7D8]
0x1801950f9  lea     rdx, [rsp+858h+var_120]
0x180195101  lea     rcx, [rsp+858h+var_588]
0x180195109  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x18019510e  lea     rcx, [rdi+48h]
0x180195112  lea     rdx, [rsp+858h+var_770]
0x18019511a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18019511f  lea     r14, aVersion_0; "Version"
0x180195126  mov     [rsp+858h+var_7D8], r14
0x18019512e  mov     [rsp+858h+var_7D8+8], rsi
0x180195136  lea     r9, [rsp+858h+var_770]
0x18019513e  lea     r8, [rsp+858h+var_7D8]
0x180195146  lea     rdx, [rsp+858h+var_120]
0x18019514e  lea     rcx, [rsp+858h+var_588]
0x180195156  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x18019515b  lea     rax, aGetfileattribu; "GetFileAttributesLastError"
0x180195162  mov     [rsp+858h+var_7D8], rax
0x18019516a  lea     r14d, [rsi+13h]
0x18019516e  mov     [rsp+858h+var_7D8+8], r14
0x180195176  lea     r9, [rsp+858h+var_7C8]
0x18019517e  lea     r8, [rsp+858h+var_7D8]
0x180195186  lea     rdx, [rsp+858h+var_120]
0x18019518e  lea     rcx, [rsp+858h+var_588]
0x180195196  call    ??$AddField@K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBK@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<ulong>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,ulong const &)
0x18019519b  lea     rax, aDestinationfil; "DestinationFilePath"
0x1801951a2  mov     [rsp+858h+var_7D8], rax
0x1801951aa  lea     ebx, [rsi+0Ch]
0x1801951ad  mov     [rsp+858h+var_7D8+8], rbx
0x1801951b5  lea     r9, [rsp+858h+lpFileName]
0x1801951bd  lea     r8, [rsp+858h+var_7D8]
0x1801951c5  lea     rdx, [rsp+858h+var_120]
0x1801951cd  lea     rcx, [rsp+858h+var_588]
0x1801951d5  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x1801951da  lea     rdx, [rdi+28h]
0x1801951de  lea     rcx, [rsp+858h+var_5D8]
0x1801951e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1801951eb  lea     r15d, [rsi-3]
0x1801951ef  mov     [rsp+858h+var_7C8], r15d
0x1801951f7  lea     rax, aLastfilewritte_0; "LastFileWrittenPath"
0x1801951fe  mov     [rsp+858h+var_7D8], rax
0x180195206  mov     [rsp+858h+var_7D8+8], rbx
0x18019520e  lea     r9, [rsp+858h+var_5D8]
0x180195216  lea     r8, [rsp+858h+var_7D8]
0x18019521e  lea     rdx, [rsp+858h+var_120]
0x180195226  lea     rcx, [rsp+858h+var_588]
0x18019522e  call    ??$AddField@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring const &)
0x180195233  nop
0x180195234  lea     rcx, [rsp+858h+var_5D8]; this
0x18019523c  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180195241  mov     al, [rdi]
0x180195243  mov     [rsp+858h+var_7A3], al
0x18019524a  lea     rax, aLastfilewritte; "LastFileWrittenWasThisEpoch"
0x180195251  mov     [rsp+858h+var_7D8], rax
0x180195259  mov     [rsp+858h+var_7D8+8], 1Bh
0x180195265  lea     r9, [rsp+858h+var_7A3]
0x18019526d  lea     r8, [rsp+858h+var_7D8]
0x180195275  lea     rdx, [rsp+858h+var_120]
0x18019527d  lea     rcx, [rsp+858h+var_588]
0x180195285  call    ??$AddField@_N@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<bool>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,bool const &)
0x18019528a  mov     rax, [rdi+18h]
0x18019528e  mov     [rsp+858h+var_758], rax
0x180195296  lea     rax, aLastdownloadti; "LastDownloadTime"
0x18019529d  mov     [rsp+858h+var_7D8], rax
0x1801952a5  mov     [rsp+858h+var_7D8+8], 10h
0x1801952b1  lea     r9, [rsp+858h+var_758]
0x1801952b9  lea     r8, [rsp+858h+var_7D8]
0x1801952c1  lea     rdx, [rsp+858h+var_120]
0x1801952c9  lea     rcx, [rsp+858h+var_588]
0x1801952d1  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x1801952d6  mov     r12, [rsp+858h+var_748]
0x1801952de  mov     rcx, [r12]
0x1801952e2  mov     rbx, 346DC5D63886594Bh
0x1801952ec  cmp     [rdi+18h], rcx
0x1801952f0  jbe     short loc_1801952F6
0x1801952f2  xor     edx, edx
0x1801952f4  jmp     short loc_180195304
0x1801952f6  sub     rcx, [rdi+18h]
0x1801952fa  mov     rax, rbx
0x1801952fd  mul     rcx
0x180195300  shr     rdx, 0Bh
0x180195304  mov     [rsp+858h+var_758], rdx
0x18019530c  lea     rax, aLastdownloadde; "LastDownloadDeltaMillis"
0x180195313  mov     [rsp+858h+var_7D8], rax
0x18019531b  mov     [rsp+858h+var_7D8+8], 17h
0x180195327  lea     r9, [rsp+858h+var_758]
0x18019532f  lea     r8, [rsp+858h+var_7D8]
0x180195337  lea     rdx, [rsp+858h+var_120]
0x18019533f  lea     rcx, [rsp+858h+var_588]
0x180195347  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x18019534c  mov     rcx, [r12]
0x180195350  cmp     [rdi+20h], rcx
0x180195354  jbe     short loc_18019535E
0x180195356  xor     r12d, r12d
0x180195359  mov     edx, r12d
0x18019535c  jmp     short loc_18019536F
0x18019535e  sub     rcx, [rdi+20h]
0x180195362  mov     rax, rbx
0x180195365  mul     rcx
0x180195368  shr     rdx, 0Bh
0x18019536c  xor     r12d, r12d
0x18019536f  mov     [rsp+858h+var_758], rdx
0x180195377  lea     rax, aLastfilewritte_2; "LastFileWrittenDeltaMillis"
0x18019537e  mov     [rsp+858h+var_7D8], rax
0x180195386  mov     [rsp+858h+var_7D8+8], r14
0x18019538e  lea     r9, [rsp+858h+var_758]
0x180195396  lea     r8, [rsp+858h+var_7D8]
0x18019539e  lea     rdx, [rsp+858h+var_120]
0x1801953a6  lea     rcx, [rsp+858h+var_588]
0x1801953ae  call    ??$AddField@_K@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEB_K@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,unsigned __int64 const &)
0x1801953b3  lea     rdx, [rsp+858h+var_588]
0x1801953bb  lea     rcx, [rsp+858h+var_738]
0x1801953c3  call    ??$_Emplace_one_at_back@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@?$vector@VAsimovSyntheticEvent@Diagnostics@Microsoft@@V?$allocator@VAsimovSyntheticEvent@Diagnostics@Microsoft@@@std@@@std@@AEAAAEAVAsimovSyntheticEvent@Diagnostics@Microsoft@@$$QEAV234@@Z; std::vector<Microsoft::Diagnostics::AsimovSyntheticEvent>::_Emplace_one_at_back<Microsoft::Diagnostics::AsimovSyntheticEvent>(Microsoft::Diagnostics::AsimovSyntheticEvent &&)
0x1801953c8  nop
0x1801953c9  lea     rcx, [rsp+858h+var_588]; this
0x1801953d1  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x1801953d6  mov     r14, [rsp+858h+var_718]
0x1801953de  jmp     short loc_1801953E5
0x1801953e0  mov     esi, 7
0x1801953e5  lea     r8, aNew_0; ".new"
0x1801953ec  lea     rdx, [rsp+858h+lpFileName]
0x1801953f4  lea     rcx, [rsp+858h+pszPathIn]
0x1801953fc  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180195401  nop
0x180195402  mov     byte ptr [rsp+858h+var_770], r12b
0x18019540a  mov     [rsp+858h+var_768], 0FFFFFFFFFFFFFFFFh
0x180195416  xor     r8d, r8d
0x180195419  mov     rdx, [rsp+858h+var_608]
0x180195421  lea     rcx, [rsp+858h+pszPathOut]
0x180195429  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x18019542e  nop
0x18019542f  lea     r8, [rsp+858h+pszPathIn]
0x180195437  cmp     [rsp+858h+var_600], rsi
0x18019543f  cmova   r8, [rsp+858h+pszPathIn]; pszPathIn
0x180195448  mov     rdx, [rsp+858h+var_648]
0x180195450  lea     rcx, [rsp+858h+pszPathOut]
0x180195458  cmp     [rsp+858h+var_640], rsi
0x180195460  cmova   rcx, [rsp+858h+pszPathOut]; pszPathOut
0x180195469  inc     rdx; cchPathOut
0x18019546c  xor     r9d, r9d; dwFlags
0x18019546f  call    cs:__imp_PathCchCanonicalizeEx
0x180195476  nop     dword ptr [rax+rax+00h]
0x18019547b  mov     ebx, eax
0x18019547d  test    eax, eax
  ... truncated ...
```
