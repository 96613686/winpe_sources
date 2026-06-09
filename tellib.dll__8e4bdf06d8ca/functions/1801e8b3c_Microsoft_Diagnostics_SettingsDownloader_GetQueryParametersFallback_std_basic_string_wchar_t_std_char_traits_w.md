# Microsoft::Diagnostics::SettingsDownloader::GetQueryParametersFallback(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>)

- ea: `0x1801e8b3c`
- end: `0x1801e93ce`
- name: `?GetQueryParametersFallback@SettingsDownloader@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z`
- size: `2194`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1801e87d4`

## callees

- `0x180003a00`
- `0x18001d160`
- `0x18001d200`
- `0x18001d5ac`
- `0x18001e638`
- `0x18001ee94`
- `0x180020fbc`
- `0x180025f70`
- `0x1800277e8`
- `0x180027be0`
- `0x1800495cc`
- `0x1800498f0`
- `0x180056098`
- `0x180080054`
- `0x1800a4068`
- `0x1800aac70`
- `0x1800b2ccc`
- `0x1800d0d9c`
- `0x1800d3f44`
- `0x18012de40`
- `0x1801726f8`
- `0x1801729f0`
- `0x180172d70`
- `0x180173480`
- `0x180173510`
- `0x1801e864c`
- `0x1801e8b3c`
- `0x1801ea114`
- `0x1802ae1e4`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e8f1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801e8f1a`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1801e8f0a`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1801e8f66`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1801e8f0a`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1801e8f66`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801e901a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801e9218`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801e901a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801e9218`

## string_xrefs

- `0x1801e9233`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`
- `0x1801e92b8`: `onecore\base\telemetry\utc\service\engine\settingsdownloader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SettingsDownloader::GetQueryParametersFallback(__int64 a1, _OWORD *a2)
{
  void *v4; // r8
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  Microsoft::Diagnostics::LifetimeManager *v8; // rcx
  Microsoft::Diagnostics::TelemetryAssert *TelemetryAssert; // rax
  void *v10; // rax
  void *v11; // r8
  __int64 v12; // rax
  void *v13; // r8
  __int64 v14; // rax
  void *v15; // r8
  WCHAR *v16; // r8
  void *v17; // r8
  HRESULT v18; // ebx
  __int64 v19; // rax
  void *v20; // rax
  __int64 v21; // rax
  void *v22; // rax
  __int64 v23; // rax
  void *v24; // rax
  HRESULT Instance; // eax
  __int64 v26; // rax
  int v27; // eax
  wil::details::in1diag3 *v28; // rcx
  __int64 v29; // rdx
  void *v30; // rax
  int ppv; // [rsp+20h] [rbp-138h]
  ULONG pcchLanguagesBuffer; // [rsp+30h] [rbp-128h] BYREF
  ULONG pulNumLanguages; // [rsp+34h] [rbp-124h] BYREF
  int v35; // [rsp+38h] [rbp-120h]
  __int128 v36; // [rsp+40h] [rbp-118h] BYREF
  LPVOID v37[2]; // [rsp+50h] [rbp-108h] BYREF
  LPVOID v38; // [rsp+60h] [rbp-F8h] BYREF
  int v39; // [rsp+68h] [rbp-F0h] BYREF
  _OWORD *v40; // [rsp+70h] [rbp-E8h]
  __int64 v41; // [rsp+80h] [rbp-D8h]
  PZZWSTR v42[2]; // [rsp+88h] [rbp-D0h] BYREF
  PZZWSTR pwszLanguagesBuffer[2]; // [rsp+B8h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-90h]
  unsigned __int64 v45; // [rsp+D0h] [rbp-88h]
  _QWORD v46[4]; // [rsp+D8h] [rbp-80h] BYREF
  _BYTE v47[16]; // [rsp+F8h] [rbp-60h] BYREF
  __int64 v48; // [rsp+108h] [rbp-50h]
  _BYTE Src[32]; // [rsp+118h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v41 = a1;
  v40 = a2;
  v35 = 0;
  std::wstring::wstring(Src);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v42);
  *(_OWORD *)v37 = *a2;
  Microsoft::Diagnostics::WideStringStream::AppendString(v42);
  Microsoft::Diagnostics::Utils::Os::GetCallingModuleVersion(v46);
  Microsoft::Diagnostics::WideStringStream::operator<<(v42);
  *(_OWORD *)v37 = *(_OWORD *)std::wstring::operator std::wstring_view(v46, &v36);
  Microsoft::Diagnostics::WideStringStream::AppendString(v4);
  LOWORD(pcchLanguagesBuffer) = 0;
  Microsoft::Diagnostics::Utils::General::GetDeviceId(pwszLanguagesBuffer, &pcchLanguagesBuffer);
  if ( !(_BYTE)pcchLanguagesBuffer )
  {
    if ( (unsigned int)dword_18042D328 > 2 )
    {
      v37[0] = "GetQueryParametersFallback";
      *(_QWORD *)&v36 = "deviceIdType";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v5,
        (unsigned int)&unk_1803C9BE9,
        v6,
        v7,
        (__int64)&v36,
        (__int64)v37);
    }
    if ( Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager) )
    {
      TelemetryAssert = Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(v8);
      Microsoft::Diagnostics::TelemetryAssert::Assert(TelemetryAssert);
    }
  }
  if ( (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(pwszLanguagesBuffer) >= 0 )
  {
    v10 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v42);
    Microsoft::Diagnostics::WideStringStream::operator<<(v10);
    *(_OWORD *)v37 = *(_OWORD *)std::wstring::operator std::wstring_view(pwszLanguagesBuffer, &v36);
    Microsoft::Diagnostics::WideStringStream::AppendString(v11);
  }
  pulNumLanguages = 0;
  *(_OWORD *)v37 = *(_OWORD *)&off_1803603B0;
  v36 = *(_OWORD *)&off_1803603A0;
  if ( (int)Microsoft::Diagnostics::Utils::Registry::GetDword(-2147483646, &v36, v37, &pulNumLanguages) >= 0 )
  {
    v12 = Microsoft::Diagnostics::WideStringStream::operator<<(v42);
    Microsoft::Diagnostics::WideStringStream::operator<<(v12, pulNumLanguages);
  }
  std::wstring::wstring(v47);
  if ( (int)Microsoft::Diagnostics::Utils::Os::GetDeviceClass(v47) >= 0
    && (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(v47) >= 0 )
  {
    Microsoft::Diagnostics::WideStringStream::operator<<(v42);
    *(_OWORD *)v37 = *(_OWORD *)std::wstring::operator std::wstring_view(v47, &v36);
    Microsoft::Diagnostics::WideStringStream::AppendString(v13);
  }
  pcchLanguagesBuffer = 0;
  if ( (int)Microsoft::Diagnostics::Utils::Os::GetCorrectedEditionId(&pcchLanguagesBuffer) >= 0 )
  {
    v14 = Microsoft::Diagnostics::WideStringStream::operator<<(v42);
    Microsoft::Diagnostics::WideStringStream::operator<<(v14, pcchLanguagesBuffer);
  }
  if ( Microsoft::Diagnostics::Utils::Os::IsRunningInContainer() )
    Microsoft::Diagnostics::WideStringStream::operator<<(v42);
  std::wstring::operator=(Src, v42);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v47);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pwszLanguagesBuffer);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v46);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v42);
  Microsoft::Diagnostics::WideStringStream::WideStringStream((Microsoft::Diagnostics::WideStringStream *)v42);
  std::wstring::wstring(v47);
  Microsoft::Diagnostics::Utils::Os::GetBuildString(v47);
  if ( v48 && (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(v47) >= 0 )
  {
    Microsoft::Diagnostics::WideStringStream::operator<<(v42);
    v36 = *(_OWORD *)std::wstring::operator std::wstring_view(v47, v46);
    Microsoft::Diagnostics::WideStringStream::AppendString(v15);
  }
  std::wstring::wstring(pwszLanguagesBuffer);
  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) || GetLastError() == 122 )
  {
    std::wstring::resize(pwszLanguagesBuffer, pcchLanguagesBuffer);
    v16 = (WCHAR *)pwszLanguagesBuffer;
    if ( v45 > 7 )
      v16 = pwszLanguagesBuffer[0];
    if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, v16, &pcchLanguagesBuffer) )
    {
      std::wstring::resize(pwszLanguagesBuffer, v44);
      if ( v44 )
      {
        if ( (int)Microsoft::Diagnostics::Utils::String::UtcUrlEscape(pwszLanguagesBuffer) >= 0 )
        {
          Microsoft::Diagnostics::WideStringStream::operator<<(v42);
          v36 = *(_OWORD *)std::wstring::operator std::wstring_view(pwszLanguagesBuffer, v46);
          Microsoft::Diagnostics::WideStringStream::AppendString(v17);
        }
      }
    }
  }
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pwszLanguagesBuffer);
  v38 = 0;
  v18 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &v38);
  v35 = v18;
  if ( v18 >= 0 )
  {
    *(_QWORD *)&v36 = 0;
    v35 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)v38 + 48LL))(v38, &v36);
    if ( v35 >= 0 )
    {
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)(v36 + 2 * v19) );
      if ( v19 )
      {
        v20 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v42);
        Microsoft::Diagnostics::WideStringStream::operator<<(v20);
      }
      else
      {
        v35 = -2147024664;
      }
    }
    v46[0] = 0;
    v35 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)v38 + 80LL))(v38, v46);
    if ( v35 >= 0 )
    {
      v21 = -1;
      do
        ++v21;
      while ( *(_WORD *)(v46[0] + 2 * v21) );
      if ( v21 )
      {
        v22 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v42);
        Microsoft::Diagnostics::WideStringStream::operator<<(v22);
      }
      else
      {
        v35 = -2147024664;
      }
    }
    pulNumLanguages = 0;
    v39 = 4;
    v35 = (*(__int64 (__fastcall **)(LPVOID, ULONG *, int *))(*(_QWORD *)v38 + 96LL))(v38, &pulNumLanguages, &v39);
    if ( v35 >= 0 && pulNumLanguages )
    {
      v23 = Microsoft::Diagnostics::WideStringStream::operator<<(v42);
      Microsoft::Diagnostics::WideStringStream::operator<<(v23, pulNumLanguages);
    }
    LOWORD(pcchLanguagesBuffer) = 0;
    v18 = (*(__int64 (__fastcall **)(LPVOID, ULONG *))(*(_QWORD *)v38 + 112LL))(v38, &pcchLanguagesBuffer);
    v35 = v18;
    if ( v18 >= 0 )
    {
      v24 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v42);
      Microsoft::Diagnostics::WideStringStream::operator<<(v24);
    }
    __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(v46);
    __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&v36);
  }
  if ( Microsoft::Diagnostics::Utils::Os::IsMsftInternalMachine() )
    Microsoft::Diagnostics::WideStringStream::operator<<(v42);
  v37[0] = 0;
  Instance = CoCreateInstance(&CLSID_FlightClientAPI, 0, 1u, &GUID_79588f37_5be1_4a35_b23d_29832257cada, v37);
  if ( Instance >= 0 )
  {
    *(_QWORD *)&v36 = 0;
    v26 = *(_QWORD *)v37[0];
    *(_QWORD *)&v36 = 0;
    v27 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(v26 + 32))(v37[0], &v36);
    v28 = retaddr;
    if ( v27 >= 0 )
    {
      v46[0] = 0;
      pulNumLanguages = 0;
      v27 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, ULONG *))(*(_QWORD *)v36 + 32LL))(v36, v46, &pulNumLanguages);
      v28 = retaddr;
      if ( v27 >= 0 )
      {
        if ( v46[0] && pulNumLanguages )
        {
          v30 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v42);
          Microsoft::Diagnostics::WideStringStream::operator<<(v30);
        }
        goto LABEL_59;
      }
      v29 = 481;
    }
    else
    {
      v29 = 474;
    }
    wil::details::in1diag3::_Log_Hr(
      v28,
      (void *)v29,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
      (const char *)(unsigned int)v27,
      ppv);
LABEL_59:
    wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v36);
    goto LABEL_60;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x1D4,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\settingsdownloader.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_60:
  std::wstring::_Append<wchar_t>(Src);
  wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(v37);
  wil::com_ptr_t<IFlightData,wil::err_exception_policy>::~com_ptr_t<IFlightData,wil::err_exception_policy>(&v38);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v47);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v42);
  std::wstring::operator=(a1, Src);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1801e8b3c  mov     r11, rsp
0x1801e8b3f  mov     [r11+18h], rbx
0x1801e8b43  push    rsi
0x1801e8b44  push    rdi
0x1801e8b45  push    r14
0x1801e8b47  sub     rsp, 140h
0x1801e8b4e  mov     rax, cs:__security_cookie
0x1801e8b55  xor     rax, rsp
0x1801e8b58  mov     [rsp+158h+var_20], rax
0x1801e8b60  mov     rbx, rdx
0x1801e8b63  mov     rsi, rcx
0x1801e8b66  mov     [rsp+158h+var_D8], rcx
0x1801e8b6e  mov     [rsp+158h+var_E8], rdx
0x1801e8b73  xor     r14d, r14d
0x1801e8b76  mov     [rsp+158h+var_120], r14d
0x1801e8b7b  lea     rcx, [r11-40h]; void *
0x1801e8b7f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801e8b84  nop
0x1801e8b85  lea     rcx, [rsp+158h+var_D0]; this
0x1801e8b8d  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x1801e8b92  nop
0x1801e8b93  movups  xmm0, xmmword ptr [rbx]
0x1801e8b96  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x1801e8b9c  lea     rdx, [rsp+158h+var_108]
0x1801e8ba1  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8ba9  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801e8bae  lea     rcx, [rsp+158h+var_80]
0x1801e8bb6  call    ?GetCallingModuleVersion@Os@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Microsoft::Diagnostics::Utils::Os::GetCallingModuleVersion(void)
0x1801e8bbb  nop
0x1801e8bbc  lea     rdx, aAppver_1; "&appVer="
0x1801e8bc3  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8bcb  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8bd0  mov     r8, rax
0x1801e8bd3  lea     rdx, [rsp+158h+var_118]
0x1801e8bd8  lea     rcx, [rsp+158h+var_80]
0x1801e8be0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e8be5  movups  xmm0, xmmword ptr [rax]
0x1801e8be8  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x1801e8bee  lea     rdx, [rsp+158h+var_108]
0x1801e8bf3  mov     rcx, r8; Src
0x1801e8bf6  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801e8bfb  mov     word ptr [rsp+158h+pcchLanguagesBuffer], r14w
0x1801e8c01  lea     rdx, [rsp+158h+pcchLanguagesBuffer]
0x1801e8c06  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x1801e8c0e  call    ?GetDeviceId@General@Utils@Diagnostics@Microsoft@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAU?$optional@VDeviceIdType@EnumDetails@Utils@Diagnostics@Microsoft@@@better_enums@@@Z; Microsoft::Diagnostics::Utils::General::GetDeviceId(better_enums::optional<Microsoft::Diagnostics::Utils::EnumDetails::DeviceIdType> &)
0x1801e8c13  nop
0x1801e8c14  cmp     byte ptr [rsp+158h+pcchLanguagesBuffer], r14b
0x1801e8c19  jnz     short loc_1801E8C7B
0x1801e8c1b  mov     eax, cs:dword_18042D328
0x1801e8c21  cmp     eax, 2
0x1801e8c24  jbe     short loc_1801E8C5E
0x1801e8c26  lea     rax, aGetqueryparame; "GetQueryParametersFallback"
0x1801e8c2d  mov     [rsp+158h+var_108], rax
0x1801e8c32  lea     rax, aDeviceidtype; "deviceIdType"
0x1801e8c39  mov     qword ptr [rsp+158h+var_118], rax
0x1801e8c3e  lea     rax, [rsp+158h+var_108]
0x1801e8c43  mov     [rsp+158h+var_130], rax
0x1801e8c48  lea     rax, [rsp+158h+var_118]
0x1801e8c4d  mov     [rsp+158h+ppv], rax
0x1801e8c52  lea     rdx, unk_1803C9BE9
0x1801e8c59  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1801e8c5e  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x1801e8c65  call    ?IsTelemetryAssertReady@LifetimeManager@Diagnostics@Microsoft@@QEAA_NXZ; Microsoft::Diagnostics::LifetimeManager::IsTelemetryAssertReady(void)
0x1801e8c6a  test    al, al
0x1801e8c6c  jz      short loc_1801E8C7B
0x1801e8c6e  call    ?GetTelemetryAssert@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVTelemetryAssert@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetTelemetryAssert(void)
0x1801e8c73  mov     rcx, rax; this
0x1801e8c76  call    ?Assert@TelemetryAssert@Diagnostics@Microsoft@@QEAAXXZ; Microsoft::Diagnostics::TelemetryAssert::Assert(void)
0x1801e8c7b  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x1801e8c83  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x1801e8c88  test    eax, eax
0x1801e8c8a  js      short loc_1801E8CEF
0x1801e8c8c  lea     rdx, aDeviceid; "&deviceId="
0x1801e8c93  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8c9b  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8ca0  cmp     byte ptr [rsp+158h+pcchLanguagesBuffer+1], 1
0x1801e8ca5  setz    cl
0x1801e8ca8  lea     r8, aS_7; "s:"
0x1801e8caf  lea     rdx, asc_180386360; "x:"
0x1801e8cb6  test    cl, cl
0x1801e8cb8  cmovz   rdx, r8
0x1801e8cbc  mov     rcx, rax; Src
0x1801e8cbf  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8cc4  mov     r8, rax
0x1801e8cc7  lea     rdx, [rsp+158h+var_118]
0x1801e8ccc  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x1801e8cd4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e8cd9  movups  xmm0, xmmword ptr [rax]
0x1801e8cdc  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x1801e8ce2  lea     rdx, [rsp+158h+var_108]
0x1801e8ce7  mov     rcx, r8; Src
0x1801e8cea  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801e8cef  mov     [rsp+158h+pulNumLanguages], r14d
0x1801e8cf4  movups  xmm0, xmmword ptr cs:off_1803603B0; "RacSampleNumber"
0x1801e8cfb  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x1801e8d01  movups  xmm1, xmmword ptr cs:off_1803603A0; "SOFTWARE\\Microsoft\\Reliability Analys"...
0x1801e8d08  movdqu  [rsp+158h+var_118], xmm1
0x1801e8d0e  lea     r9, [rsp+158h+pulNumLanguages]
0x1801e8d13  lea     r8, [rsp+158h+var_108]
0x1801e8d18  lea     rdx, [rsp+158h+var_118]
0x1801e8d1d  mov     rcx, 0FFFFFFFF80000002h
0x1801e8d24  call    ?GetDword@Registry@Utils@Diagnostics@Microsoft@@SAJPEAUHKEY__@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1AEAK@Z; Microsoft::Diagnostics::Utils::Registry::GetDword(HKEY__ *,std::wstring_view,std::wstring_view,ulong &)
0x1801e8d29  test    eax, eax
0x1801e8d2b  js      short loc_1801E8D4D
0x1801e8d2d  lea     rdx, aSampleid; "&sampleId="
0x1801e8d34  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8d3c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8d41  mov     edx, [rsp+158h+pulNumLanguages]
0x1801e8d45  mov     rcx, rax
0x1801e8d48  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1801e8d4d  lea     rcx, [rsp+158h+var_60]; void *
0x1801e8d55  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801e8d5a  nop
0x1801e8d5b  lea     rcx, [rsp+158h+var_60]
0x1801e8d63  call    ?GetDeviceClass@Os@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::Os::GetDeviceClass(std::wstring &)
0x1801e8d68  test    eax, eax
0x1801e8d6a  js      short loc_1801E8DBC
0x1801e8d6c  lea     rcx, [rsp+158h+var_60]
0x1801e8d74  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x1801e8d79  test    eax, eax
0x1801e8d7b  js      short loc_1801E8DBC
0x1801e8d7d  lea     rdx, aDeviceclass_0; "&deviceClass="
0x1801e8d84  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8d8c  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8d91  mov     r8, rax
0x1801e8d94  lea     rdx, [rsp+158h+var_118]
0x1801e8d99  lea     rcx, [rsp+158h+var_60]
0x1801e8da1  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e8da6  movups  xmm0, xmmword ptr [rax]
0x1801e8da9  movdqu  xmmword ptr [rsp+158h+var_108], xmm0
0x1801e8daf  lea     rdx, [rsp+158h+var_108]
0x1801e8db4  mov     rcx, r8; Src
0x1801e8db7  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801e8dbc  mov     [rsp+158h+pcchLanguagesBuffer], r14d
0x1801e8dc1  lea     rcx, [rsp+158h+pcchLanguagesBuffer]; unsigned int *
0x1801e8dc6  call    ?GetCorrectedEditionId@Os@Utils@Diagnostics@Microsoft@@SAJAEAK@Z; Microsoft::Diagnostics::Utils::Os::GetCorrectedEditionId(ulong &)
0x1801e8dcb  test    eax, eax
0x1801e8dcd  js      short loc_1801E8DEF
0x1801e8dcf  lea     rdx, aSku; "&sku="
0x1801e8dd6  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8dde  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8de3  mov     edx, [rsp+158h+pcchLanguagesBuffer]
0x1801e8de7  mov     rcx, rax
0x1801e8dea  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@K@Z; Microsoft::Diagnostics::WideStringStream::operator<<(ulong)
0x1801e8def  call    ?IsRunningInContainer@Os@Utils@Diagnostics@Microsoft@@SA_NXZ; Microsoft::Diagnostics::Utils::Os::IsRunningInContainer(void)
0x1801e8df4  test    al, al
0x1801e8df6  jz      short loc_1801E8E0C
0x1801e8df8  lea     rdx, aIscontainer1; "&isContainer=1"
0x1801e8dff  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8e07  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8e0c  lea     rdx, [rsp+158h+var_D0]
0x1801e8e14  lea     rcx, [rsp+158h+Src]
0x1801e8e1c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801e8e21  nop
0x1801e8e22  lea     rcx, [rsp+158h+var_60]; this
0x1801e8e2a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e8e2f  nop
0x1801e8e30  lea     rcx, [rsp+158h+pwszLanguagesBuffer]; this
0x1801e8e38  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e8e3d  nop
0x1801e8e3e  lea     rcx, [rsp+158h+var_80]; this
0x1801e8e46  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e8e4b  nop
0x1801e8e4c  lea     rcx, [rsp+158h+var_D0]; this
0x1801e8e54  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e8e59  lea     rcx, [rsp+158h+var_D0]; this
0x1801e8e61  call    ??0WideStringStream@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::WideStringStream::WideStringStream(void)
0x1801e8e66  nop
0x1801e8e67  lea     rcx, [rsp+158h+var_60]; void *
0x1801e8e6f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801e8e74  nop
0x1801e8e75  lea     rcx, [rsp+158h+var_60]
0x1801e8e7d  call    ?GetBuildString@Os@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::Os::GetBuildString(std::wstring &)
0x1801e8e82  cmp     [rsp+158h+var_50], r14
0x1801e8e8a  jz      short loc_1801E8EDF
0x1801e8e8c  lea     rcx, [rsp+158h+var_60]
0x1801e8e94  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x1801e8e99  test    eax, eax
0x1801e8e9b  js      short loc_1801E8EDF
0x1801e8e9d  lea     rdx, aOsver; "&osVer="
0x1801e8ea4  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8eac  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8eb1  mov     r8, rax
0x1801e8eb4  lea     rdx, [rsp+158h+var_80]
0x1801e8ebc  lea     rcx, [rsp+158h+var_60]
0x1801e8ec4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e8ec9  movups  xmm0, xmmword ptr [rax]
0x1801e8ecc  movdqu  [rsp+158h+var_118], xmm0
0x1801e8ed2  lea     rdx, [rsp+158h+var_118]
0x1801e8ed7  mov     rcx, r8; Src
0x1801e8eda  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801e8edf  lea     rcx, [rsp+158h+pwszLanguagesBuffer]; void *
0x1801e8ee7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1801e8eec  nop
0x1801e8eed  mov     [rsp+158h+pulNumLanguages], r14d
0x1801e8ef2  mov     [rsp+158h+pcchLanguagesBuffer], r14d
0x1801e8ef7  lea     r9, [rsp+158h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1801e8efc  xor     r8d, r8d; pwszLanguagesBuffer
0x1801e8eff  lea     rdx, [rsp+158h+pulNumLanguages]; pulNumLanguages
0x1801e8f04  lea     ebx, [r8+8]
0x1801e8f08  mov     ecx, ebx; dwFlags
0x1801e8f0a  call    cs:__imp_GetSystemPreferredUILanguages
0x1801e8f11  nop     dword ptr [rax+rax+00h]
0x1801e8f16  test    eax, eax
0x1801e8f18  jnz     short loc_1801E8F2F
0x1801e8f1a  call    cs:__imp_GetLastError
0x1801e8f21  nop     dword ptr [rax+rax+00h]
0x1801e8f26  cmp     eax, 7Ah ; 'z'
0x1801e8f29  jnz     loc_1801E8FE9
0x1801e8f2f  mov     edx, [rsp+158h+pcchLanguagesBuffer]
0x1801e8f33  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x1801e8f3b  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1801e8f40  lea     r8, [rsp+158h+pwszLanguagesBuffer]
0x1801e8f48  cmp     [rsp+158h+var_88], 7
0x1801e8f51  cmova   r8, [rsp+158h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x1801e8f5a  lea     r9, [rsp+158h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1801e8f5f  lea     rdx, [rsp+158h+pulNumLanguages]; pulNumLanguages
0x1801e8f64  mov     ecx, ebx; dwFlags
0x1801e8f66  call    cs:__imp_GetSystemPreferredUILanguages
0x1801e8f6d  nop     dword ptr [rax+rax+00h]
0x1801e8f72  test    eax, eax
0x1801e8f74  jz      short loc_1801E8FE9
0x1801e8f76  mov     rdx, [rsp+158h+var_90]
0x1801e8f7e  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x1801e8f86  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1801e8f8b  cmp     [rsp+158h+var_90], r14
0x1801e8f93  jz      short loc_1801E8FE9
0x1801e8f95  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x1801e8f9d  call    ?UtcUrlEscape@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::UtcUrlEscape(std::wstring &)
0x1801e8fa2  test    eax, eax
0x1801e8fa4  js      short loc_1801E8FE9
0x1801e8fa6  lea     rdx, aLocale; "&locale="
0x1801e8fad  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e8fb5  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e8fba  mov     r8, rax
0x1801e8fbd  lea     rdx, [rsp+158h+var_80]
0x1801e8fc5  lea     rcx, [rsp+158h+pwszLanguagesBuffer]
0x1801e8fcd  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1801e8fd2  movups  xmm0, xmmword ptr [rax]
0x1801e8fd5  movdqu  [rsp+158h+var_118], xmm0
0x1801e8fdb  lea     rdx, [rsp+158h+var_118]
0x1801e8fe0  mov     rcx, r8; Src
0x1801e8fe3  call    ?AppendString@WideStringStream@Diagnostics@Microsoft@@AEAAAEAV123@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::WideStringStream::AppendString(std::wstring_view)
0x1801e8fe8  nop
0x1801e8fe9  lea     rcx, [rsp+158h+pwszLanguagesBuffer]; this
0x1801e8ff1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1801e8ff6  nop
0x1801e8ff7  mov     [rsp+158h+var_F8], r14
0x1801e8ffc  lea     rax, [rsp+158h+var_F8]
0x1801e9001  mov     [rsp+158h+ppv], rax; ppv
0x1801e9006  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x1801e900d  xor     edx, edx; pUnkOuter
0x1801e900f  lea     r8d, [rdx+1]; dwClsContext
0x1801e9013  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x1801e901a  call    cs:__imp_CoCreateInstance
0x1801e9021  nop     dword ptr [rax+rax+00h]
0x1801e9026  mov     ebx, eax
0x1801e9028  mov     [rsp+158h+var_120], eax
0x1801e902c  test    eax, eax
0x1801e902e  js      loc_1801E91D7
0x1801e9034  mov     qword ptr [rsp+158h+var_118], r14
0x1801e9039  mov     rcx, [rsp+158h+var_F8]
0x1801e903e  mov     rax, [rcx]
0x1801e9041  lea     rdx, [rsp+158h+var_118]
0x1801e9046  mov     rax, [rax+30h]
0x1801e904a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e904f  mov     [rsp+158h+var_120], eax
0x1801e9053  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801e9057  test    eax, eax
0x1801e9059  js      short loc_1801E909D
0x1801e905b  mov     rcx, qword ptr [rsp+158h+var_118]
0x1801e9060  mov     rax, rdi
0x1801e9063  inc     rax
0x1801e9066  cmp     [rcx+rax*2], r14w
0x1801e906b  jnz     short loc_1801E9063
0x1801e906d  test    rax, rax
0x1801e9070  jz      short loc_1801E9095
0x1801e9072  lea     rdx, aRing_0; "&ring="
0x1801e9079  lea     rcx, [rsp+158h+var_D0]; Src
0x1801e9081  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e9086  mov     rdx, qword ptr [rsp+158h+var_118]
0x1801e908b  mov     rcx, rax; Src
0x1801e908e  call    ??6WideStringStream@Diagnostics@Microsoft@@QEAAAEAV012@PEB_W@Z; Microsoft::Diagnostics::WideStringStream::operator<<(wchar_t const *)
0x1801e9093  jmp     short loc_1801E909D
0x1801e9095  mov     [rsp+158h+var_120], 800700E8h
0x1801e909d  mov     [rsp+158h+var_80], r14
0x1801e90a5  mov     rcx, [rsp+158h+var_F8]
0x1801e90aa  mov     rax, [rcx]
0x1801e90ad  lea     rdx, [rsp+158h+var_80]
0x1801e90b5  mov     rax, [rax+50h]
0x1801e90b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e90be  mov     [rsp+158h+var_120], eax
0x1801e90c2  test    eax, eax
0x1801e90c4  js      short loc_1801E910E
0x1801e90c6  mov     rcx, [rsp+158h+var_80]
0x1801e90ce  mov     rax, rdi
0x1801e90d1  inc     rax
0x1801e90d4  cmp     [rcx+rax*2], r14w
0x1801e90d9  jnz     short loc_1801E90D1
0x1801e90db  test    rax, rax
  ... truncated ...
```
