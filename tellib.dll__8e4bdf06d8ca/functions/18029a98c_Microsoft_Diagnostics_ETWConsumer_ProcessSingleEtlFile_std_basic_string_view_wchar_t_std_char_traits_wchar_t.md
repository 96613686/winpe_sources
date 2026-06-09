# Microsoft::Diagnostics::ETWConsumer::ProcessSingleEtlFile(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x18029a98c`
- end: `0x18029b588`
- name: `?ProcessSingleEtlFile@ETWConsumer@Diagnostics@Microsoft@@AEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z`
- size: `3068`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800eb718`

## callees

- `0x180001d28`
- `0x180002b94`
- `0x180003874`
- `0x180015884`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180031e2c`
- `0x180032688`
- `0x1800333b0`
- `0x180035698`
- `0x180038870`
- `0x180040b90`
- `0x180049380`
- `0x1800494d0`
- `0x1800498f0`
- `0x180057238`
- `0x180057f58`
- `0x18005b974`
- `0x18005d050`
- `0x18009c71c`
- `0x1800a6020`
- `0x1800a60e4`
- `0x1800a8324`
- `0x1800a8e5c`
- `0x1800a9250`
- `0x1800a9344`
- `0x1800aac70`
- `0x1800af5f0`
- `0x1800d0d9c`
- `0x1800e1a54`
- `0x18012de40`
- `0x18012eb08`
- `0x180161298`
- `0x180179610`
- `0x18021ab58`
- `0x18028fd48`
- `0x180291844`
- `0x180297d6c`
- `0x1802982bc`
- `0x1802997f0`
- `0x18029a98c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029ab89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18029ab89`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18029ad23`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18029b4ee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18029ad23`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18029b4ee`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18029b004`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18029b004`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18029b49b`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18029b49b`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18029ab62`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18029ab62`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18029af2f`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18029af2f`

## string_xrefs

- `0x18029ace9`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x18029ad3b`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x18029ad5f`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x18029b01c`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x18029b3a7`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x18029b4b3`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x18029b506`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`
- `0x18029b526`: `onecore\base\telemetry\utc\service\triggers\etwconsumer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
__int64 __fastcall Microsoft::Diagnostics::ETWConsumer::ProcessSingleEtlFile(__int64 a1, _QWORD *a2)
{
  __int64 last_of; // rax
  __int64 v5; // rbx
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // rax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  WCHAR *v12; // rax
  TRACEHANDLE v13; // rax
  ULONG64 v14; // rbx
  signed int v15; // esi
  signed int LastError; // eax
  __int64 v17; // rax
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // eax
  const WCHAR *v22; // rcx
  const char *v23; // r9
  unsigned int v24; // ebx
  _WORD *v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // rax
  unsigned __int64 UbiTime; // rsi
  signed int v31; // eax
  __int64 v32; // rax
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  const WCHAR *v36; // rcx
  const char *v37; // r9
  int v38; // eax
  const WCHAR *v39; // rdx
  const WCHAR *v40; // rcx
  const char *v41; // r9
  const WCHAR *v42; // rcx
  const char *v43; // r9
  int v44; // [rsp+20h] [rbp-C88h]
  int v45; // [rsp+20h] [rbp-C88h]
  __int128 v46; // [rsp+40h] [rbp-C68h] BYREF
  _QWORD v47[2]; // [rsp+50h] [rbp-C58h] BYREF
  __int128 v48; // [rsp+60h] [rbp-C48h] BYREF
  char *v49; // [rsp+70h] [rbp-C38h]
  __int64 v50; // [rsp+78h] [rbp-C30h] BYREF
  ULONG64 HandleArray[2]; // [rsp+80h] [rbp-C28h] BYREF
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+90h] [rbp-C18h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+250h] [rbp-A58h] BYREF
  unsigned __int64 v54; // [rsp+268h] [rbp-A40h]
  LPCWSTR lpNewFileName[3]; // [rsp+270h] [rbp-A38h] BYREF
  unsigned __int64 v56; // [rsp+288h] [rbp-A20h]
  __int128 FileInformation; // [rsp+290h] [rbp-A18h] BYREF
  __int128 v58; // [rsp+2A0h] [rbp-A08h]
  int v59; // [rsp+2B0h] [rbp-9F8h]
  _BYTE v60[16]; // [rsp+2B8h] [rbp-9F0h] BYREF
  __int64 v61; // [rsp+2C8h] [rbp-9E0h]
  _BYTE Src[32]; // [rsp+2D8h] [rbp-9D0h] BYREF
  _BYTE v63[24]; // [rsp+2F8h] [rbp-9B0h] BYREF
  __int64 v64; // [rsp+310h] [rbp-998h]
  __int64 v65; // [rsp+320h] [rbp-988h]
  int v66[282]; // [rsp+340h] [rbp-968h] BYREF
  int v67[14]; // [rsp+7A8h] [rbp-500h] BYREF
  _BYTE v68[1128]; // [rsp+7E0h] [rbp-4C8h] BYREF
  _BYTE v69[56]; // [rsp+C48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+CA8h] [rbp+0h]

  std::wstring::wstring(lpFileName);
  *(_QWORD *)&v48 = L"Unknown";
  *((_QWORD *)&v48 + 1) = 7;
  last_of = std::wstring_view::find_last_of(a2, L"\\", -1);
  v5 = last_of;
  if ( last_of == -1 )
  {
    *(_OWORD *)lpNewFileName = *(_OWORD *)a2;
  }
  else
  {
    *(_OWORD *)lpNewFileName = *(_OWORD *)std::wstring_view::substr(a2, &v46, last_of + 1, -1);
    v6 = std::wstring_view::find_last_of(a2, L"\\", v5 - 1);
    if ( v6 != -1 )
      v48 = *(_OWORD *)std::wstring_view::substr(a2, &v46, v6 + 1, v5 - v6 - 1);
  }
  v46 = *(_OWORD *)&off_180363A90;
  if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v46) )
  {
    v7 = 0;
    if ( (unsigned int)dword_18042D328 > 3 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 3) )
    {
      v8 = _tlgWrapBinary<wchar_t,2>(&v46, *a2, *((unsigned int *)a2 + 2));
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(
        v9,
        (unsigned int)&unk_1803DA510,
        v10,
        v11,
        v8);
    }
LABEL_47:
    v46 = *(_OWORD *)&off_180363A80;
    if ( (unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v46) )
    {
      std::wstring::wstring(lpNewFileName);
      *(_QWORD *)&v46 = L".bk";
      *((_QWORD *)&v46 + 1) = 3;
      *(_QWORD *)&v48 = L".etl";
      *((_QWORD *)&v48 + 1) = 4;
      Microsoft::Diagnostics::Utils::String::ReplaceAllImpl<wchar_t>(lpNewFileName);
      v39 = (const WCHAR *)lpNewFileName;
      if ( v56 > 7 )
        v39 = lpNewFileName[0];
      v40 = (const WCHAR *)lpFileName;
      if ( v54 > 7 )
        v40 = lpFileName[0];
      if ( !MoveFileExW(v40, v39, 1u) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x856,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
          v41);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpNewFileName);
    }
    else
    {
      v42 = (const WCHAR *)lpFileName;
      if ( v54 > 7 )
        v42 = lpFileName[0];
      if ( !DeleteFileW(v42) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x85A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
          v43);
    }
    if ( (v7 & 0x80000000) == 0 )
    {
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
        (const char *)v7,
        v44);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
      return v7;
    }
  }
  Microsoft::Diagnostics::BlackBox::LogEvent(&qword_18043B830, 5, 0, 0, 0);
  memset_0(&Logfile, 0, sizeof(Logfile));
  v12 = (WCHAR *)lpFileName;
  if ( v54 > 7 )
    v12 = (WCHAR *)lpFileName[0];
  Logfile.LogFileName = v12;
  Logfile.EventCallback = (PEVENT_CALLBACK)Microsoft::Diagnostics::ETWConsumer::StaticEtlEtwEventCallback;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)Microsoft::Diagnostics::ETWConsumer::StaticEtwBufferCallback;
  Logfile.LogFileMode = 0x10000000;
  Logfile.Context = (PVOID)a1;
  v50 = -1;
  v13 = OpenTraceW(&Logfile);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::reset(
    &v50,
    v13);
  v14 = v50;
  if ( v50 == -1 )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v15 = 0;
  }
  LODWORD(v49) = v15;
  if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 3) )
  {
    v17 = _tlgWrapBinary<wchar_t,2>(&v46, *a2, *((unsigned int *)a2 + 2));
    LODWORD(v47[0]) = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
      v18,
      (unsigned int)&unk_1803DA4C6,
      v19,
      v20,
      (__int64)v47,
      v17);
  }
  if ( v15 >= 0 )
  {
    *(_QWORD *)(a1 + 2184) = 0;
    if ( *(_QWORD *)(a1 + 2192) <= 7u )
      v26 = (_WORD *)(a1 + 2168);
    else
      v26 = *(_WORD **)(a1 + 2168);
    *v26 = 0;
    std::wstring::wstring(Src);
    std::wstring::_Append<wchar_t>(Src);
    std::string::string(v60);
    v46 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v47);
    Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(&v46, v27, 0xFFFFFFFFLL, v60);
    if ( v61 )
    {
      v46 = *(_OWORD *)std::string::operator std::string_view(v60, v47);
      v28 = Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(v63, &v46);
      std::wstring::operator=(a1 + 2168, v28);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v63);
    }
    memset_0(v63, 0, 0x40u);
    v29 = Microsoft::Diagnostics::ETWConsumer::EtlLogStats::EtlLogStats((Microsoft::Diagnostics::ETWConsumer::EtlLogStats *)v63);
    Microsoft::Diagnostics::ETWConsumer::EtlLogStats::operator=(a1 + 536, v29);
    if ( v64 )
      std::_Deallocate<16>(v64, 20 * ((v65 - v64) / 20));
    UbiTime = Microsoft::Diagnostics::Utils::Time::QueryUbiTime();
    *(_WORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 52LL) = -1;
    HandleArray[0] = v14;
    v31 = ProcessTrace(HandleArray, 1u, 0, 0);
    v7 = v31;
    if ( v31 > 0 )
      v7 = (unsigned __int16)v31 | 0x80070000;
    if ( (unsigned int)dword_18042D328 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18042D328, 3) )
    {
      v32 = _tlgWrapBinary<wchar_t,2>(&v46, *a2, *((unsigned int *)a2 + 2));
      LODWORD(v47[0]) = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(
        v33,
        (unsigned int)&unk_1803DA554,
        v34,
        v35,
        (__int64)v47,
        v32);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::reset(
      &v50,
      -1);
    Microsoft::Diagnostics::BlackBox::LogEvent(&qword_18043B830, 6, 0, 0, 0);
    FileInformation = 0;
    v58 = 0;
    v59 = 0;
    v36 = (const WCHAR *)lpFileName;
    if ( v54 > 7 )
      v36 = lpFileName[0];
    if ( !GetFileAttributesExW(v36, GetFileExInfoStandard, &FileInformation) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x83A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
        v37);
    v47[0] = L"ETWConsumer_EtlSingleFileSummary_1";
    v47[1] = 34;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
      (unsigned int)v66,
      (unsigned int)v47,
      0x1000000,
      0,
      0,
      0,
      0);
    LODWORD(v47[0]) = v59;
    HIDWORD(v47[0]) = HIDWORD(v58);
    *(_QWORD *)&v46 = L"FileName";
    *((_QWORD *)&v46 + 1) = 8;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v66, (unsigned int)v67);
    *(_QWORD *)&v46 = L"FileSizeBytes";
    *((_QWORD *)&v46 + 1) = 13;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v66, (unsigned int)v67);
    *(_QWORD *)&v46 = L"NumberOfEvents";
    *((_QWORD *)&v46 + 1) = 14;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v66, (unsigned int)v67);
    v47[0] = Microsoft::Diagnostics::Utils::Time::QueryUbiTime() / 0x2710 - UbiTime / 0x2710;
    *(_QWORD *)&v46 = L"ProcessingTimeMs";
    *((_QWORD *)&v46 + 1) = 16;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned __int64>((unsigned int)v66, (unsigned int)v67);
    *(_QWORD *)&v46 = L"NumberOfBuffers";
    *((_QWORD *)&v46 + 1) = 15;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v66, (unsigned int)v67);
    *(_QWORD *)&v46 = L"EventsLost";
    *((_QWORD *)&v46 + 1) = 10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v66, (unsigned int)v67);
    *(_QWORD *)&v46 = L"DroppedBuffers";
    *((_QWORD *)&v46 + 1) = 14;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v66, (unsigned int)v67);
    Microsoft::Diagnostics::ModeEstimator<_GUID>::GetTopResult(a1 + 544);
    *(_QWORD *)&v46 = L"TopProvider";
    *((_QWORD *)&v46 + 1) = 11;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_GUID>((unsigned int)v66, (unsigned int)v67);
    *(_QWORD *)&v46 = L"TopProviderCount";
    *((_QWORD *)&v46 + 1) = 16;
    Microsoft::Diagnostics::ModeEstimator<_GUID>::GetTopResult(a1 + 544);
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<unsigned long>((unsigned int)v66, (unsigned int)v67);
    v47[0] = *(_QWORD *)(a1 + 584);
    *(_QWORD *)&v46 = L"LogBeginTime";
    *((_QWORD *)&v46 + 1) = 12;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_FILETIME>((int)v66, (int)v67);
    v47[0] = *(_QWORD *)(a1 + 592);
    *(_QWORD *)&v46 = L"LogEndTime";
    *((_QWORD *)&v46 + 1) = 10;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<_FILETIME>((int)v66, (int)v67);
    *(_QWORD *)&v46 = L"Type";
    *((_QWORD *)&v46 + 1) = 4;
    Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v66, (unsigned int)v67);
    v38 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v66);
    if ( v38 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x84F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
        (const char *)(unsigned int)v38,
        v44);
    Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v66);
    std::string::_Tidy_deallocate(v60);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>(&v50);
    goto LABEL_47;
  }
  *(_QWORD *)&v48 = L"ETWConsumer_FailedToProcessETLFile_0";
  *((_QWORD *)&v48 + 1) = 36;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(
    (unsigned int)v68,
    (unsigned int)&v48,
    0x1000000,
    0,
    0,
    0,
    0);
  *(_QWORD *)&v48 = L"ErrorCode";
  *((_QWORD *)&v48 + 1) = 9;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>((unsigned int)v68, (unsigned int)v69);
  *(_QWORD *)&v48 = L"Filename";
  *((_QWORD *)&v48 + 1) = 8;
  Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>((unsigned int)v68, (unsigned int)v69);
  v46 = 0;
  Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(v47, &v46);
  v21 = Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent((Microsoft::Diagnostics::IAsimovEvent *)v68);
  if ( v21 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x80B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
      (const char *)(unsigned int)v21,
      v45);
  *(_WORD *)(a1 + 600) = 5;
  ++*(_DWORD *)(a1 + 604);
  v22 = (const WCHAR *)lpFileName;
  if ( v54 > 7 )
    v22 = lpFileName[0];
  if ( !DeleteFileW(v22) )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x80E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
      v23);
  v24 = (unsigned int)v49;
  if ( (int)v49 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwconsumer.cpp",
      (const char *)(unsigned int)v49,
      v45);
  Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent((Microsoft::Diagnostics::AsimovSyntheticEvent *)v68);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,unsigned long (unsigned __int64),&unsigned long CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>(&v50);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpFileName);
  return v24;
}

```

## disassembly

```asm
0x18029a98c  mov     [rsp+arg_10], rbx
0x18029a991  mov     [rsp+arg_18], rsi
0x18029a996  push    rdi
0x18029a997  push    r12
0x18029a999  push    r14
0x18029a99b  sub     rsp, 0C90h
0x18029a9a2  mov     rax, cs:__security_cookie
0x18029a9a9  xor     rax, rsp
0x18029a9ac  mov     [rsp+0CA8h+var_28], rax
0x18029a9b4  mov     rdi, rdx
0x18029a9b7  mov     r14, rcx
0x18029a9ba  lea     rcx, [rsp+0CA8h+lpFileName]
0x18029a9c2  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18029a9c7  nop
0x18029a9c8  lea     rax, aUnknown_2; "Unknown"
0x18029a9cf  mov     qword ptr [rsp+0CA8h+var_C48], rax
0x18029a9d4  mov     qword ptr [rsp+0CA8h+var_C48+8], 7
0x18029a9dd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18029a9e1  mov     r8, rsi
0x18029a9e4  lea     rdx, asc_1803772C8; "\\"
0x18029a9eb  mov     rcx, rdi
0x18029a9ee  call    ?find_last_of@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA_KQEB_W_K@Z; std::wstring_view::find_last_of(wchar_t const * const,unsigned __int64)
0x18029a9f3  mov     rbx, rax
0x18029a9f6  cmp     rax, rsi
0x18029a9f9  jnz     short loc_18029AA09
0x18029a9fb  movups  xmm0, xmmword ptr [rdi]
0x18029a9fe  movdqu  xmmword ptr [rsp+0CA8h+lpNewFileName], xmm0
0x18029aa07  jmp     short loc_18029AA62
0x18029aa09  lea     r8, [rax+1]
0x18029aa0d  mov     r9, rsi
0x18029aa10  lea     rdx, [rsp+0CA8h+var_C68]
0x18029aa15  mov     rcx, rdi
0x18029aa18  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x18029aa1d  movups  xmm0, xmmword ptr [rax]
0x18029aa20  movdqu  xmmword ptr [rsp+0CA8h+lpNewFileName], xmm0
0x18029aa29  lea     r8, [rbx-1]
0x18029aa2d  lea     rdx, asc_1803772C8; "\\"
0x18029aa34  mov     rcx, rdi
0x18029aa37  call    ?find_last_of@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA_KQEB_W_K@Z; std::wstring_view::find_last_of(wchar_t const * const,unsigned __int64)
0x18029aa3c  cmp     rax, rsi
0x18029aa3f  jz      short loc_18029AA62
0x18029aa41  sub     rbx, rax
0x18029aa44  lea     r9, [rbx-1]
0x18029aa48  lea     r8, [rax+1]
0x18029aa4c  lea     rdx, [rsp+0CA8h+var_C68]
0x18029aa51  mov     rcx, rdi
0x18029aa54  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x18029aa59  movups  xmm0, xmmword ptr [rax]
0x18029aa5c  movdqu  [rsp+0CA8h+var_C48], xmm0
0x18029aa62  movups  xmm0, xmmword ptr cs:off_180363A90; "DeleteEtlFilesWithoutProcessing"
0x18029aa69  movdqu  [rsp+0CA8h+var_C68], xmm0
0x18029aa6f  lea     rcx, [rsp+0CA8h+var_C68]
0x18029aa74  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x18029aa79  test    al, al
0x18029aa7b  jz      short loc_18029AACC
0x18029aa7d  xor     ebx, ebx
0x18029aa7f  mov     eax, cs:dword_18042D328
0x18029aa85  cmp     eax, 3
0x18029aa88  jbe     loc_18029B3ED
0x18029aa8e  lea     edx, [rbx+3]
0x18029aa91  lea     rcx, dword_18042D328
0x18029aa98  call    _tlgKeywordOn
0x18029aa9d  test    al, al
0x18029aa9f  jz      loc_18029B3ED
0x18029aaa5  mov     r8d, [rdi+8]
0x18029aaa9  mov     rdx, [rdi]
0x18029aaac  lea     rcx, [rsp+0CA8h+var_C68]
0x18029aab1  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18029aab6  mov     qword ptr [rsp+0CA8h+var_C88], rax
0x18029aabb  lea     rdx, unk_1803DA510
0x18029aac2  call    ??$Write@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperArray<1> const &)
0x18029aac7  jmp     loc_18029B3ED
0x18029aacc  mov     r12d, 5
0x18029aad2  xor     r8d, r8d
0x18029aad5  mov     qword ptr [rsp+0CA8h+var_C88], r8
0x18029aada  xor     r9d, r9d
0x18029aadd  movzx   edx, r12w
0x18029aae1  lea     rcx, qword_18043B830
0x18029aae8  call    ?LogEvent@BlackBox@Diagnostics@Microsoft@@QEAAXVBBTrace@23@G_K1@Z; Microsoft::Diagnostics::BlackBox::LogEvent(Microsoft::Diagnostics::BBTrace,ushort,unsigned __int64,unsigned __int64)
0x18029aaed  xor     edx, edx; Val
0x18029aaef  mov     r8d, 1C0h; Size
0x18029aaf5  lea     rcx, [rsp+0CA8h+Logfile]; void *
0x18029aafd  call    memset_0
0x18029ab02  lea     rax, [rsp+0CA8h+lpFileName]
0x18029ab0a  cmp     [rsp+0CA8h+var_A40], 7
0x18029ab13  cmova   rax, [rsp+0CA8h+lpFileName]
0x18029ab1c  mov     [rsp+0CA8h+Logfile.LogFileName], rax
0x18029ab24  lea     rax, ?StaticEtlEtwEventCallback@ETWConsumer@Diagnostics@Microsoft@@CAXPEAU_EVENT_RECORD@@@Z; Microsoft::Diagnostics::ETWConsumer::StaticEtlEtwEventCallback(_EVENT_RECORD *)
0x18029ab2b  mov     qword ptr [rsp+0CA8h+Logfile.1A8h], rax
0x18029ab33  lea     rax, ?StaticEtwBufferCallback@ETWConsumer@Diagnostics@Microsoft@@CAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; Microsoft::Diagnostics::ETWConsumer::StaticEtwBufferCallback(_EVENT_TRACE_LOGFILEW *)
0x18029ab3a  mov     [rsp+0CA8h+Logfile.BufferCallback], rax
0x18029ab42  mov     dword ptr [rsp+0CA8h+Logfile.1Ch], 10000000h
0x18029ab4d  mov     [rsp+0CA8h+Logfile.Context], r14
0x18029ab55  mov     [rsp+0CA8h+var_C30], rsi
0x18029ab5a  lea     rcx, [rsp+0CA8h+Logfile]; Logfile
0x18029ab62  call    cs:__imp_OpenTraceW
0x18029ab69  nop     dword ptr [rax+rax+00h]
0x18029ab6e  mov     rdx, rax
0x18029ab71  lea     rcx, [rsp+0CA8h+var_C30]
0x18029ab76  call    ?reset@?$unique_storage@U?$resource_policy@_K$$A6AK_K@Z$1?CloseTrace@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,ulong (unsigned __int64),&CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::reset(unsigned __int64)
0x18029ab7b  mov     rbx, [rsp+0CA8h+var_C30]
0x18029ab80  cmp     rbx, rsi
0x18029ab83  jz      short loc_18029AB89
0x18029ab85  xor     esi, esi
0x18029ab87  jmp     short loc_18029ABA4
0x18029ab89  call    cs:__imp_GetLastError
0x18029ab90  nop     dword ptr [rax+rax+00h]
0x18029ab95  mov     esi, eax
0x18029ab97  test    eax, eax
0x18029ab99  jle     short loc_18029ABA4
0x18029ab9b  movzx   esi, ax
0x18029ab9e  or      esi, 80070000h
0x18029aba4  mov     dword ptr [rsp+0CA8h+var_C38], esi
0x18029aba8  mov     eax, cs:dword_18042D328
0x18029abae  cmp     eax, 4
0x18029abb1  jbe     short loc_18029ABF8
0x18029abb3  mov     edx, 3
0x18029abb8  lea     rcx, dword_18042D328
0x18029abbf  call    _tlgKeywordOn
0x18029abc4  test    al, al
0x18029abc6  jz      short loc_18029ABF8
0x18029abc8  mov     r8d, [rdi+8]
0x18029abcc  mov     rdx, [rdi]
0x18029abcf  lea     rcx, [rsp+0CA8h+var_C68]
0x18029abd4  call    ??$_tlgWrapBinary@_W$01@@YA?AU?$_tlgWrapperArray@$00@@PEB_W_K@Z; _tlgWrapBinary<wchar_t,2>(wchar_t const *,unsigned __int64)
0x18029abd9  mov     dword ptr [rsp+0CA8h+var_C58], esi
0x18029abdd  mov     [rsp+0CA8h+var_C80], rax
0x18029abe2  lea     rax, [rsp+0CA8h+var_C58]
0x18029abe7  mov     qword ptr [rsp+0CA8h+var_C88], rax
0x18029abec  lea     rdx, unk_1803DA4C6
0x18029abf3  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperArray@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperArray@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperArray<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperArray<1> const &)
0x18029abf8  test    esi, esi
0x18029abfa  jns     loc_18029AD9E
0x18029ac00  xor     al, al
0x18029ac02  xor     cl, cl
0x18029ac04  lea     rdx, aEtwconsumerFai; "ETWConsumer_FailedToProcessETLFile_0"
0x18029ac0b  mov     qword ptr [rsp+0CA8h+var_C48], rdx
0x18029ac10  mov     qword ptr [rsp+0CA8h+var_C48+8], 24h ; '$'
0x18029ac19  mov     r8d, 1000000h
0x18029ac1f  mov     [rsp+0CA8h+var_C78], al
0x18029ac23  mov     byte ptr [rsp+0CA8h+var_C80], al
0x18029ac27  mov     byte ptr [rsp+0CA8h+var_C88], cl; int
0x18029ac2b  mov     r9, 400000000000h
0x18029ac35  lea     rdx, [rsp+0CA8h+var_C48]
0x18029ac3a  lea     rcx, [rsp+0CA8h+var_4C8]
0x18029ac42  call    ??0AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAA@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@UPrivacyDataType@@_KVTriggerPersistence@12@VTriggerLatency@12@_N@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AsimovSyntheticEvent(std::wstring_view,PrivacyDataType,unsigned __int64,Microsoft::Diagnostics::TriggerPersistence,Microsoft::Diagnostics::TriggerLatency,bool)
0x18029ac47  nop
0x18029ac48  lea     rax, aErrorcode; "ErrorCode"
0x18029ac4f  mov     qword ptr [rsp+0CA8h+var_C48], rax
0x18029ac54  mov     qword ptr [rsp+0CA8h+var_C48+8], 9
0x18029ac5d  lea     r9, [rsp+0CA8h+var_C38]
0x18029ac62  lea     r8, [rsp+0CA8h+var_C48]
0x18029ac67  lea     rdx, [rsp+0CA8h+var_60]
0x18029ac6f  lea     rcx, [rsp+0CA8h+var_4C8]
0x18029ac77  call    ??$AddField@J@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBJ@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<long>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,long const &)
0x18029ac7c  lea     rax, aFilename; "Filename"
0x18029ac83  mov     qword ptr [rsp+0CA8h+var_C48], rax
0x18029ac88  mov     qword ptr [rsp+0CA8h+var_C48+8], 8
0x18029ac91  lea     r9, [rsp+0CA8h+lpNewFileName]
0x18029ac99  lea     r8, [rsp+0CA8h+var_C48]
0x18029ac9e  lea     rdx, [rsp+0CA8h+var_60]
0x18029aca6  lea     rcx, [rsp+0CA8h+var_4C8]
0x18029acae  call    ??$AddField@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@AsimovSyntheticEvent@Diagnostics@Microsoft@@QEAAXAEAUObjectIterator@012@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBV45@@Z; Microsoft::Diagnostics::AsimovSyntheticEvent::AddField<std::wstring_view>(Microsoft::Diagnostics::AsimovSyntheticEvent::ObjectIterator &,std::wstring_view,std::wstring_view const &)
0x18029acb3  xorps   xmm0, xmm0
0x18029acb6  movdqa  [rsp+0CA8h+var_C68], xmm0
0x18029acbc  lea     rdx, [rsp+0CA8h+var_C68]
0x18029acc1  lea     rcx, [rsp+0CA8h+var_C58]
0x18029acc6  call    ??$MakeEnumSet@VPersistSyntheticOptions@Diagnostics@Microsoft@@@Enum@Utils@Diagnostics@Microsoft@@SA?AV?$bitset@$01@std@@V?$initializer_list@VPersistSyntheticOptions@Diagnostics@Microsoft@@@5@@Z; Microsoft::Diagnostics::Utils::Enum::MakeEnumSet<Microsoft::Diagnostics::PersistSyntheticOptions>(std::initializer_list<Microsoft::Diagnostics::PersistSyntheticOptions>)
0x18029accb  mov     edx, [rax]
0x18029accd  lea     rcx, [rsp+0CA8h+var_4C8]; this
0x18029acd5  call    ?PersistSyntheticEvent@AsimovEventSerializer@Diagnostics@Microsoft@@SAJAEAVAsimovSyntheticEvent@23@V?$bitset@$01@std@@@Z; Microsoft::Diagnostics::AsimovEventSerializer::PersistSyntheticEvent(Microsoft::Diagnostics::AsimovSyntheticEvent &,std::bitset<2>)
0x18029acda  mov     rcx, [rsp+0CA8h]; this
0x18029ace2  test    eax, eax
0x18029ace4  jns     short loc_18029ACFA
0x18029ace6  mov     r9d, eax; char *
0x18029ace9  lea     r8, aOnecoreBaseTel_277; "onecore\\base\\telemetry\\utc\\service"...
0x18029acf0  mov     edx, 80Bh; void *
0x18029acf5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18029acfa  mov     [r14+258h], r12w
0x18029ad02  inc     dword ptr [r14+25Ch]
0x18029ad09  lea     rcx, [rsp+0CA8h+lpFileName]
0x18029ad11  cmp     [rsp+0CA8h+var_A40], 7
0x18029ad1a  cmova   rcx, [rsp+0CA8h+lpFileName]; lpFileName
0x18029ad23  call    cs:__imp_DeleteFileW
0x18029ad2a  nop     dword ptr [rax+rax+00h]
0x18029ad2f  mov     rcx, [rsp+0CA8h]; this
0x18029ad37  test    eax, eax
0x18029ad39  jnz     short loc_18029AD4C
0x18029ad3b  lea     r8, aOnecoreBaseTel_277; "onecore\\base\\telemetry\\utc\\service"...
0x18029ad42  mov     edx, 80Eh; void *
0x18029ad47  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18029ad4c  mov     ebx, dword ptr [rsp+0CA8h+var_C38]
0x18029ad50  test    ebx, ebx
0x18029ad52  jns     short loc_18029AD71
0x18029ad54  mov     rcx, [rsp+0CA8h]; this
0x18029ad5c  mov     r9d, ebx; char *
0x18029ad5f  lea     r8, aOnecoreBaseTel_277; "onecore\\base\\telemetry\\utc\\service"...
0x18029ad66  mov     edx, 80Fh; void *
0x18029ad6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029ad70  nop
0x18029ad71  lea     rcx, [rsp+0CA8h+var_4C8]; this
0x18029ad79  call    ??1AsimovSyntheticEvent@Diagnostics@Microsoft@@UEAA@XZ; Microsoft::Diagnostics::AsimovSyntheticEvent::~AsimovSyntheticEvent(void)
0x18029ad7e  nop
0x18029ad7f  lea     rcx, [rsp+0CA8h+var_C30]
0x18029ad84  call    ??1?$unique_storage@U?$resource_policy@_K$$A6AK_K@Z$1?CloseTrace@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0?0$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,ulong (unsigned __int64),&CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,ulong (unsigned __int64),&CloseTrace(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,-1,std::nullptr_t>>(void)
0x18029ad89  nop
0x18029ad8a  lea     rcx, [rsp+0CA8h+lpFileName]; this
0x18029ad92  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029ad97  mov     eax, ebx
0x18029ad99  jmp     loc_18029B55E
0x18029ad9e  lea     rsi, [r14+878h]
0x18029ada5  mov     qword ptr [rsi+10h], 0
0x18029adad  cmp     qword ptr [rsi+18h], 7
0x18029adb2  jbe     short loc_18029ADB9
0x18029adb4  mov     rcx, [rsi]
0x18029adb7  jmp     short loc_18029ADBC
0x18029adb9  mov     rcx, rsi
0x18029adbc  xor     eax, eax
0x18029adbe  mov     [rcx], ax
0x18029adc1  mov     rdx, rdi
0x18029adc4  lea     rcx, [rsp+0CA8h+Src]
0x18029adcc  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18029add1  nop
0x18029add2  mov     r8d, 11h
0x18029add8  mov     rdx, cs:?k_alternateStreamCVName@ETWConsumer@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::ETWConsumer::k_alternateStreamCVName
0x18029addf  lea     rcx, [rsp+0CA8h+Src]; Src
0x18029ade7  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18029adec  lea     rcx, [rsp+0CA8h+var_9F0]
0x18029adf4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18029adf9  nop
0x18029adfa  lea     rdx, [rsp+0CA8h+var_C58]
0x18029adff  lea     rcx, [rsp+0CA8h+Src]
0x18029ae07  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029ae0c  movups  xmm0, xmmword ptr [rax]
0x18029ae0f  movdqu  [rsp+0CA8h+var_C68], xmm0
0x18029ae15  lea     r9, [rsp+0CA8h+var_9F0]
0x18029ae1d  or      r8d, 0FFFFFFFFh
0x18029ae21  lea     rcx, [rsp+0CA8h+var_C68]
0x18029ae26  call    ?ReadStringFromFile@FileSystem@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@KKAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::ReadStringFromFile(std::wstring_view,ulong,ulong,std::string &)
0x18029ae2b  cmp     [rsp+0CA8h+var_9E0], 0
0x18029ae34  jz      short loc_18029AE7B
0x18029ae36  lea     rdx, [rsp+0CA8h+var_C58]
0x18029ae3b  lea     rcx, [rsp+0CA8h+var_9F0]
0x18029ae43  call    ??B?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string_view@DU?$char_traits@D@std@@@1@XZ; std::string::operator std::string_view(void)
0x18029ae48  movups  xmm0, xmmword ptr [rax]
0x18029ae4b  movdqu  [rsp+0CA8h+var_C68], xmm0
0x18029ae51  lea     rdx, [rsp+0CA8h+var_C68]
0x18029ae56  lea     rcx, [rsp+0CA8h+var_9B0]
0x18029ae5e  call    ?MultiByteStringToWideString@String@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::MultiByteStringToWideString(std::string_view,ulong)
0x18029ae63  mov     rdx, rax
0x18029ae66  mov     rcx, rsi
0x18029ae69  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18029ae6e  lea     rcx, [rsp+0CA8h+var_9B0]; this
0x18029ae76  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029ae7b  xor     edx, edx; Val
0x18029ae7d  lea     r8d, [rdx+40h]; Size
0x18029ae81  lea     rcx, [rsp+0CA8h+var_9B0]; void *
0x18029ae89  call    memset_0
0x18029ae8e  lea     rcx, [rsp+0CA8h+var_9B0]; this
0x18029ae96  call    ??0EtlLogStats@ETWConsumer@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ETWConsumer::EtlLogStats::EtlLogStats(void)
0x18029ae9b  nop
0x18029ae9c  lea     r12, [r14+218h]
0x18029aea3  mov     rdx, rax
0x18029aea6  mov     rcx, r12
0x18029aea9  call    ??4EtlLogStats@ETWConsumer@Diagnostics@Microsoft@@QEAAAEAU0123@$$QEAU0123@@Z; Microsoft::Diagnostics::ETWConsumer::EtlLogStats::operator=(Microsoft::Diagnostics::ETWConsumer::EtlLogStats &&)
0x18029aeae  nop
0x18029aeaf  mov     rcx, [rsp+0CA8h+var_998]
0x18029aeb7  test    rcx, rcx
0x18029aeba  jz      short loc_18029AEEF
0x18029aebc  mov     rdx, [rsp+0CA8h+var_988]
0x18029aec4  sub     rdx, rcx
0x18029aec7  mov     rax, 6666666666666667h
0x18029aed1  imul    rdx
0x18029aed4  sar     rdx, 3
0x18029aed8  mov     rax, rdx
0x18029aedb  shr     rax, 3Fh
0x18029aedf  add     rdx, rax
0x18029aee2  lea     rdx, [rdx+rdx*4]
0x18029aee6  shl     rdx, 2
0x18029aeea  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18029aeef  call    ?QueryUbiTime@Time@Utils@Diagnostics@Microsoft@@SA_KXZ; Microsoft::Diagnostics::Utils::Time::QueryUbiTime(void)
0x18029aef4  mov     rsi, rax
0x18029aef7  mov     edx, cs:_tls_index
0x18029aefd  mov     rcx, gs:58h
0x18029af06  mov     eax, 34h ; '4'
0x18029af0b  mov     rdx, [rcx+rdx*8]
0x18029af0f  mov     word ptr [rax+rdx], 0FFFFh
0x18029af15  mov     [rsp+0CA8h+HandleArray], rbx
0x18029af1d  xor     r9d, r9d; EndTime
0x18029af20  xor     r8d, r8d; StartTime
0x18029af23  lea     edx, [r9+1]; HandleCount
0x18029af27  lea     rcx, [rsp+0CA8h+HandleArray]; HandleArray
0x18029af2f  call    cs:__imp_ProcessTrace
0x18029af36  nop     dword ptr [rax+rax+00h]
0x18029af3b  mov     ebx, eax
0x18029af3d  test    eax, eax
0x18029af3f  jle     short loc_18029AF4A
0x18029af41  movzx   ebx, ax
0x18029af44  or      ebx, 80070000h
0x18029af4a  mov     eax, cs:dword_18042D328
  ... truncated ...
```
