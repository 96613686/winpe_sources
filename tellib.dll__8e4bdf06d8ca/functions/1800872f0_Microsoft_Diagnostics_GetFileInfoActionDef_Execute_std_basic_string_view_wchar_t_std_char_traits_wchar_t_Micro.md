# Microsoft::Diagnostics::GetFileInfoActionDef::Execute(std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,Microsoft::Diagnostics::EscalationWorkItemState &,Microsoft::Diagnostics::ScenarioInst const &)

- ea: `0x1800872f0`
- end: `0x1800882fe`
- name: `?Execute@GetFileInfoActionDef@Diagnostics@Microsoft@@UEBAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAVEscalationWorkItemState@23@AEBVScenarioInst@23@@Z`
- size: `4110`
- prototype: ``
- caller_count: `0`
- callee_count: `53`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18001d0ec`
- `0x18001d160`
- `0x18001d200`
- `0x18001d5ac`
- `0x18001e638`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180030a50`
- `0x180031c08`
- `0x180035698`
- `0x180048ff4`
- `0x1800498f0`
- `0x18004a750`
- `0x18004be40`
- `0x18004f7a4`
- `0x180053a84`
- `0x1800707e0`
- `0x18008171c`
- `0x180082538`
- `0x180086c3c`
- `0x180086e78`
- `0x180086f40`
- `0x180087044`
- `0x1800872f0`
- `0x180088304`
- `0x18009c71c`
- `0x1800aac70`
- `0x1800af45c`
- `0x1800b1a08`
- `0x1800b2d34`
- `0x1800b2d68`
- `0x1800bc300`
- `0x1800daaac`
- `0x1800e9034`
- `0x1800f7680`
- `0x180108668`
- `0x180108864`
- `0x180112c8c`
- `0x18012de40`
- `0x18012fc24`
- `0x1801873a8`
- `0x18018d1b4`
- `0x180204fb0`
- `0x1802e61b8`
- `0x1802ed16c`
- `0x1802ed1c0`
- `0x1802ee9ac`
- `0x1802ef958`
- `0x180308b68`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x180087f8e`
- `msvcp_win!??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z` at `0x180087f8e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180087e45`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180087e45`

## string_xrefs

- `0x1800881a7`: `XML written to file: `
- `0x180087350`: `onecore\base\telemetry\utc\service\scenarios\actions\getfileinfoaction.cpp`
- `0x18008737e`: `onecore\base\telemetry\utc\service\scenarios\actions\getfileinfoaction.cpp`
- `0x1800873d7`: `onecore\base\telemetry\utc\service\scenarios\actions\getfileinfoaction.cpp`
- `0x180087702`: `onecore\base\telemetry\utc\service\scenarios\actions\getfileinfoaction.cpp`
- `0x180087802`: `onecore\base\telemetry\utc\service\scenarios\actions\getfileinfoaction.cpp`
- `0x180087938`: `onecore\base\telemetry\utc\service\scenarios\actions\getfileinfoaction.cpp`
- `0x180087b1c`: `baseDirectoryPath`
- `0x180087d80`: `directory`
- `0x180087f2b`: `directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=23 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::GetFileInfoActionDef::Execute(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  int appended; // eax
  unsigned int v10; // ebx
  __int64 MostNarrowAllowedRule; // rax
  __int64 v12; // rbx
  __m128i v13; // xmm6
  __int128 v14; // xmm7
  __int64 v15; // rax
  int v16; // r8d
  __int64 last_of; // rax
  _QWORD *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rbx
  unsigned __int8 v21; // bl
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  char v25; // bl
  __int64 first_of; // rdi
  unsigned int v27; // r14d
  WCHAR *v28; // rcx
  int v29; // r8d
  __int64 v30; // rax
  __int128 v31; // xmm0
  __int128 *v32; // rax
  __int64 v33; // r8
  void *v34; // r8
  void *v35; // rax
  __int64 v36; // rax
  void *v37; // rax
  int v38; // [rsp+20h] [rbp-728h]
  __m128i v39; // [rsp+40h] [rbp-708h] BYREF
  _DWORD v40[4]; // [rsp+50h] [rbp-6F8h] BYREF
  const wchar_t *v41; // [rsp+60h] [rbp-6E8h] BYREF
  __int64 v42; // [rsp+68h] [rbp-6E0h]
  __int128 v43; // [rsp+70h] [rbp-6D8h] BYREF
  __int128 v44; // [rsp+80h] [rbp-6C8h] BYREF
  _QWORD v45[2]; // [rsp+90h] [rbp-6B8h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-6A8h] BYREF
  _BYTE v47[16]; // [rsp+B0h] [rbp-698h] BYREF
  _BYTE v48[32]; // [rsp+C0h] [rbp-688h] BYREF
  _BYTE v49[24]; // [rsp+E0h] [rbp-668h] BYREF
  char v50; // [rsp+F8h] [rbp-650h]
  _QWORD v51[2]; // [rsp+100h] [rbp-648h] BYREF
  _BYTE v52[16]; // [rsp+110h] [rbp-638h] BYREF
  _QWORD v53[2]; // [rsp+120h] [rbp-628h] BYREF
  _QWORD v54[2]; // [rsp+130h] [rbp-618h] BYREF
  _BYTE v55[80]; // [rsp+140h] [rbp-608h] BYREF
  _BYTE v56[16]; // [rsp+190h] [rbp-5B8h] BYREF
  _BYTE v57[16]; // [rsp+1A0h] [rbp-5A8h] BYREF
  _BYTE v58[16]; // [rsp+1B0h] [rbp-598h] BYREF
  _BYTE v59[16]; // [rsp+1C0h] [rbp-588h] BYREF
  _BYTE v60[240]; // [rsp+1D0h] [rbp-578h] BYREF
  WCHAR FileName[4]; // [rsp+2C0h] [rbp-488h] BYREF
  unsigned __int64 v62; // [rsp+2D8h] [rbp-470h]
  _QWORD v63[4]; // [rsp+2E0h] [rbp-468h] BYREF
  WCHAR pszPath[16]; // [rsp+300h] [rbp-448h] BYREF
  _QWORD v65[4]; // [rsp+320h] [rbp-428h] BYREF
  _BYTE Src[16]; // [rsp+340h] [rbp-408h] BYREF
  __int64 v67; // [rsp+350h] [rbp-3F8h]
  _BYTE v68[16]; // [rsp+360h] [rbp-3E8h] BYREF
  __int64 v69; // [rsp+370h] [rbp-3D8h]
  _QWORD v70[4]; // [rsp+380h] [rbp-3C8h] BYREF
  _BYTE v71[32]; // [rsp+3A0h] [rbp-3A8h] BYREF
  _BYTE v72[8]; // [rsp+3C0h] [rbp-388h] BYREF
  _BYTE v73[32]; // [rsp+3C8h] [rbp-380h] BYREF
  __int64 v74; // [rsp+3E8h] [rbp-360h]
  _BYTE v75[32]; // [rsp+400h] [rbp-348h] BYREF
  _BYTE v76[32]; // [rsp+420h] [rbp-328h] BYREF
  _BYTE v77[672]; // [rsp+440h] [rbp-308h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+748h] [rbp+0h]

  if ( !*(_BYTE *)(a1 + 164) && !(unsigned __int8)IsPicRetrieveFileInfoPresent() )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x27,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getfileinfoaction.cpp",
      (const char *)0x80004001LL,
      v38);
    return 2147500033LL;
  }
  if ( !a2[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getfileinfoaction.cpp",
      (const char *)0x8007010BLL,
      v38);
    return 2147942667LL;
  }
  std::wstring::wstring((__int64)pszPath, a2);
  v39 = *(__m128i *)&Microsoft::Diagnostics::GetFileInfoActionDef::k_fileInfoOutputFileName;
  appended = Microsoft::Diagnostics::Utils::String::AppendPath(pszPath);
  v10 = appended;
  if ( appended < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getfileinfoaction.cpp",
      (const char *)(unsigned int)appended,
      v38);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    return v10;
  }
  Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(pszPath);
  std::wstring::wstring(v63, a1 + 128);
  Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(v63);
  std::wstring::wstring(v65, v63);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v65, 1, 0);
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(v65, &v43);
  Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a4, v70, &v39);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v70, 1, 0);
  v50 = 0;
  v39 = *(__m128i *)&off_180369180;
  if ( !(unsigned __int8)Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(&v39) )
  {
    v39 = *(__m128i *)std::wstring::operator std::wstring_view(v70, &v43);
    v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, &v44);
    MostNarrowAllowedRule = Microsoft::Diagnostics::FileRulesManager::FindMostNarrowAllowedRule(
                              &Microsoft::Diagnostics::GetFileInfoActionDef::m_fileRulesManager,
                              v72,
                              &v46,
                              &v39);
    if ( *(_BYTE *)(MostNarrowAllowedRule + 56) )
    {
      v12 = MostNarrowAllowedRule + 32;
      if ( v50 )
      {
        std::wstring::operator=(v48, MostNarrowAllowedRule);
        std::vector<std::wstring>::operator=(v49, v12);
      }
      else
      {
        std::wstring::wstring(v48, MostNarrowAllowedRule);
        std::vector<std::pair<unsigned __int64,Microsoft::Diagnostics::TriggerSettings>>::vector<std::pair<unsigned __int64,Microsoft::Diagnostics::TriggerSettings>>(
          v49,
          v12);
        v50 = 1;
      }
    }
    else if ( v50 )
    {
      std::pair<std::wstring,std::vector<std::wstring>>::~pair<std::wstring,std::vector<std::wstring>>((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v48);
      v50 = 0;
    }
    std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(v72);
    if ( !v50
      || (v13 = *(__m128i *)std::wstring::operator std::wstring_view(v70, &v43),
          v14 = *(_OWORD *)std::wstring::operator std::wstring_view(v65, &v44),
          v15 = std::optional<std::pair<std::wstring,std::vector<std::wstring>>>::value(v48),
          v39 = v13,
          v46 = v14,
          !(unsigned __int8)Microsoft::Diagnostics::FileRulesManager::CheckDeniedList(
                              &Microsoft::Diagnostics::GetFileInfoActionDef::m_fileRulesManager,
                              v15 + 32,
                              &v46,
                              &v39)) )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a4 + 56) + 72LL))(*(_QWORD *)(a4 + 56));
      v39 = *(__m128i *)std::wstring::operator std::wstring_view(v65, &v43);
      v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v63, &v44);
      Microsoft::Diagnostics::GetFileActionDef::LogPathNotApprovedEvent(
        (unsigned int)&v46,
        (unsigned int)&v39,
        v16,
        a4 + 12,
        -2017128357);
      std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(v48);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v70);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v63);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
      return 2277838939LL;
    }
  }
  last_of = std::wstring::find_last_of(v63, 92);
  if ( last_of == -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getfileinfoaction.cpp",
      (const char *)0x80004005LL,
      v38);
    std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(v48);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v70);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v63);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    return 2147500037LL;
  }
  std::wstring::substr(v63, v76, 0, last_of);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(v63, 1, 0);
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(v63, &v43);
  v18 = Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(a4, FileName, &v39);
  std::wstring::operator=(v63, v18);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)FileName);
  v19 = std::wstring::find_last_of(v63, 92);
  v20 = v19;
  if ( v19 == -1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getfileinfoaction.cpp",
      (const char *)0x80004005LL,
      v38);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(v48);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v70);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v63);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
    return 2147500037LL;
  }
  std::wstring::substr(v63, v68, 0, v19);
  std::wstring::substr(v63, v71, v20 + 1, -1);
  std::wstring::wstring(v75, v71);
  v21 = 0;
  v45[0] = L"*";
  v45[1] = 1;
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(v71, &v43);
  if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v39, v45) )
  {
    v22 = std::wstring::find_last_of(v68, 92);
    v23 = v22;
    if ( v22 == -1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\getfileinfoaction.cpp",
        (const char *)0x80004005LL,
        v38);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v75);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
      std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(v48);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v70);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v63);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
      return 2147500037LL;
    }
    std::wstring::substr(v68, FileName, v22 + 1, -1);
    if ( std::wstring::find(FileName, L"*", 0) != -1 )
    {
      std::wstring::operator=(v75, FileName);
      v24 = std::wstring::substr(v68, Src, 0, v23);
      std::wstring::operator=(v68, v24);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
    }
    v21 = 1;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)FileName);
  }
  Microsoft::Diagnostics::XmlWriterFacade::XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v55);
  v40[0] = 0;
  std::wstring::wstring(v73);
  v74 = 0;
  v72[0] = *(_BYTE *)(a1 + 164);
  v72[1] = v21;
  v72[2] = *(_BYTE *)(a1 + 165);
  std::wstring::operator=(v73, v76);
  v74 = v69;
  v41 = L"result";
  v42 = 6;
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v55, v45, &v41);
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(v73, &v43);
  v41 = L"baseDirectoryPath";
  v42 = 17;
  Microsoft::Diagnostics::XmlWriterAutoElement::WriteAttributeString(v45, &v41, &v39);
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(v75, &v43);
  v41 = L"searchPatternLevelZero";
  v42 = 22;
  Microsoft::Diagnostics::XmlWriterAutoElement::WriteAttributeString(v45, &v41, &v39);
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(v71, &v43);
  v41 = L"searchPatternLevelN";
  v42 = 19;
  Microsoft::Diagnostics::XmlWriterAutoElement::WriteAttributeString(v45, &v41, &v39);
  std::_Integral_to_string<wchar_t,long>(FileName, *(unsigned __int8 *)(a1 + 164));
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(FileName, &v43);
  v41 = L"lightweightCollection";
  v42 = 21;
  Microsoft::Diagnostics::XmlWriterAutoElement::WriteAttributeString(v45, &v41, &v39);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)FileName);
  std::_Integral_to_string<wchar_t,long>(FileName, v21);
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(FileName, &v43);
  v41 = L"recursiveCollection";
  v42 = 19;
  Microsoft::Diagnostics::XmlWriterAutoElement::WriteAttributeString(v45, &v41, &v39);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)FileName);
  v41 = L"parent";
  v42 = 6;
  Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v55, &v43, &v41);
  v25 = 1;
  std::wstring::wstring(Src, Microsoft::Diagnostics::Utils::String::k_copyFileUnicodePrefix, 4);
  first_of = std::wstring::find_first_of(v63, 92, v67);
  v27 = 1;
  while ( first_of != -1 )
  {
    std::wstring::substr(v63, FileName, v67, first_of - v67);
    std::wstring::_Append<wchar_t>(Src);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)FileName);
    first_of = std::wstring::find_first_of(v63, 92, first_of + 1);
    if ( v25 )
    {
      v41 = L"directory";
      v42 = 9;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v55, v52, &v41);
      v44 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v58);
      v51[0] = L"name";
      v25 = 0;
      v51[1] = 4;
      Microsoft::Diagnostics::XmlWriterAutoElement::WriteAttributeString(v52, v51, &v44);
      std::wstring::substr(Src, FileName, 4, -1);
      v28 = *(WCHAR **)FileName;
      if ( v62 <= 7 )
        v28 = FileName;
      GetFileAttributesW(v28);
      v44 = *(_OWORD *)std::wstring::operator std::wstring_view(FileName, v56);
      Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML((__int64)v55, &v44, 1, 0, 0, v29, v72);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)FileName);
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v52);
    }
    else
    {
      v53[0] = &::Src;
      v53[1] = 0;
      v44 = *(_OWORD *)std::wstring::operator std::wstring_view(Src, v57);
      AutoFindFile::AutoFindFile(v77, &v44, v53);
      AutoFindFile::begin((AutoFindFile *)v77);
      v54[0] = L"directory";
      v54[1] = 9;
      Microsoft::Diagnostics::XmlWriterFacade::CreateElement(v55, &v39, v54);
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v59);
      std::operator<<<wchar_t,std::char_traits<wchar_t>>(v60, L"!parent!.");
      std::wostream::operator<<(v60, v27);
      v30 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(v59, FileName);
      ++v27;
      v44 = *(_OWORD *)std::wstring::operator std::wstring_view(v30, v47);
      *(_QWORD *)&v46 = L"name";
      *((_QWORD *)&v46 + 1) = 4;
      Microsoft::Diagnostics::XmlWriterAutoElement::WriteAttributeString(&v39, &v46, &v44);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)FileName);
      Microsoft::Diagnostics::GetFileInfoActionDef::WriteSingleFileInfoToXML(
        (struct Microsoft::Diagnostics::XmlWriterFacade *)v55,
        (const struct AutoFindFile *)v77,
        (const struct Microsoft::Diagnostics::GetFileInfoActionDef::FileInfoQueryState *)v72);
      std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v59);
      Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v39);
      AutoFindFile::~AutoFindFile((AutoFindFile *)v77);
    }
  }
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)Src);
  Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)&v43);
  std::optional<std::pair<std::wstring,std::vector<std::wstring>>>::value(v48);
  v31 = *(_OWORD *)std::wstring::operator std::wstring_view(v68, v47);
  v32 = (__int128 *)std::wstring::operator std::wstring_view(v71, v57);
  v43 = v31;
  v44 = *v32;
  v39 = *(__m128i *)std::wstring::operator std::wstring_view(v75, v56);
  Microsoft::Diagnostics::GetFileInfoActionDef::WriteFileInfoMatchingQuery(
    (unsigned int)v55,
    (unsigned int)&v39,
    (unsigned int)&v44,
    (unsigned int)&v43,
    (__int64)v72,
    (__int64)v40,
    *(_DWORD *)(a1 + 160),
    v33);
  Microsoft::Diagnostics::XmlWriterAutoElement::~XmlWriterAutoElement((Microsoft::Diagnostics::XmlWriterAutoElement *)v45);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
  v43 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v47);
  Microsoft::Diagnostics::XmlWriterFacade::WriteToFile(v55, &v43);
  v43 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v47);
  Microsoft::Diagnostics::EscalationWorkItemState::AddCollectedFileToBuilder(a3, &v43);
  Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
  v43 = *(_OWORD *)std::wstring::operator std::wstring_view(pszPath, v47);
  v35 = (void *)Microsoft::Diagnostics::WideStringStream::AppendString(v34);
  Microsoft::Diagnostics::WideStringStream::operator<<(v35);
  v36 = Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
  v37 = (void *)Microsoft::Diagnostics::WideStringStream::operator<<(v36, v40[0]);
  Microsoft::Diagnostics::WideStringStream::operator<<(v37);
  if ( v40[0] >= *(_DWORD *)(a1 + 160) )
    Microsoft::Diagnostics::WideStringStream::operator<<((void *)(a3 + 168));
  Microsoft::Diagnostics::XmlWriterFacade::~XmlWriterFacade((Microsoft::Diagnostics::XmlWriterFacade *)v55);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v75);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
  std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(v48);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v70);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v65);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v63);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)pszPath);
  return 0;
}

```

## disassembly

```asm
0x1800872f0  mov     rax, rsp
0x1800872f3  push    rbx
0x1800872f4  push    rsi
0x1800872f5  push    rdi
0x1800872f6  push    r12
0x1800872f8  push    r13
0x1800872fa  push    r14
0x1800872fc  push    r15
0x1800872fe  sub     rsp, 710h
0x180087305  movaps  xmmword ptr [rax-48h], xmm6
0x180087309  movaps  xmmword ptr [rax-58h], xmm7
0x18008730d  mov     rax, cs:__security_cookie
0x180087314  xor     rax, rsp
0x180087317  mov     [rsp+748h+var_68], rax
0x18008731f  mov     rdi, r9
0x180087322  mov     r15, r8
0x180087325  mov     rbx, rdx
0x180087328  mov     rsi, rcx
0x18008732b  xor     r12d, r12d
0x18008732e  cmp     [rcx+0A4h], r12b
0x180087335  jnz     short loc_180087368
0x180087337  call    IsPicRetrieveFileInfoPresent
0x18008733c  test    al, al
0x18008733e  jnz     short loc_180087368
0x180087340  mov     rcx, [rsp+748h]; this
0x180087348  mov     ebx, 80004001h
0x18008734d  mov     r9d, ebx; char *
0x180087350  lea     r8, aOnecoreBaseTel_184; "onecore\\base\\telemetry\\utc\\service"...
0x180087357  lea     edx, [r12+27h]; void *
0x18008735c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087361  mov     eax, ebx
0x180087363  jmp     loc_1800882CC
0x180087368  cmp     [rbx+8], r12
0x18008736c  jnz     short loc_180087396
0x18008736e  mov     rcx, [rsp+748h]; this
0x180087376  mov     ebx, 8007010Bh
0x18008737b  mov     r9d, ebx; char *
0x18008737e  lea     r8, aOnecoreBaseTel_184; "onecore\\base\\telemetry\\utc\\service"...
0x180087385  mov     edx, 2Ah ; '*'; void *
0x18008738a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008738f  mov     eax, ebx
0x180087391  jmp     loc_1800882CC
0x180087396  mov     rdx, rbx
0x180087399  lea     rcx, [rsp+748h+pszPath]
0x1800873a1  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x1800873a6  nop
0x1800873a7  movups  xmm0, xmmword ptr cs:?k_fileInfoOutputFileName@GetFileInfoActionDef@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::GetFileInfoActionDef::k_fileInfoOutputFileName
0x1800873ae  movdqu  [rsp+748h+var_708], xmm0
0x1800873b4  lea     rdx, [rsp+748h+var_708]
0x1800873b9  lea     rcx, [rsp+748h+pszPath]; pszPath
0x1800873c1  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x1800873c6  mov     ebx, eax
0x1800873c8  test    eax, eax
0x1800873ca  jns     short loc_1800873FD
0x1800873cc  mov     rcx, [rsp+748h]; this
0x1800873d4  mov     r9d, eax; char *
0x1800873d7  lea     r8, aOnecoreBaseTel_184; "onecore\\base\\telemetry\\utc\\service"...
0x1800873de  mov     edx, 2Ch ; ','; void *
0x1800873e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800873e8  nop
0x1800873e9  lea     rcx, [rsp+748h+pszPath]; this
0x1800873f1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800873f6  mov     eax, ebx
0x1800873f8  jmp     loc_1800882CC
0x1800873fd  lea     rcx, [rsp+748h+pszPath]; Src
0x180087405  call    ?PrependLongPathUnicodePrefix@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(std::wstring &)
0x18008740a  lea     rdx, [rsi+80h]
0x180087411  lea     rcx, [rsp+748h+var_468]
0x180087419  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18008741e  nop
0x18008741f  lea     rcx, [rsp+748h+var_468]; Src
0x180087427  call    ?PrependLongPathUnicodePrefix@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::PrependLongPathUnicodePrefix(std::wstring &)
0x18008742c  lea     rdx, [rsp+748h+var_468]
0x180087434  lea     rcx, [rsp+748h+var_428]
0x18008743c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180087441  nop
0x180087442  xor     r8d, r8d
0x180087445  lea     r13d, [r8+1]
0x180087449  mov     dl, r13b
0x18008744c  lea     rcx, [rsp+748h+var_428]; lpSrc
0x180087454  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180087459  lea     rdx, [rsp+748h+var_6D8]
0x18008745e  lea     rcx, [rsp+748h+var_428]
0x180087466  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18008746b  movups  xmm0, xmmword ptr [rax]
0x18008746e  movdqu  [rsp+748h+var_708], xmm0
0x180087474  lea     r8, [rsp+748h+var_708]
0x180087479  lea     rdx, [rsp+748h+var_3C8]
0x180087481  mov     rcx, rdi
0x180087484  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x180087489  nop
0x18008748a  xor     r8d, r8d
0x18008748d  mov     dl, r13b
0x180087490  lea     rcx, [rsp+748h+var_3C8]; lpSrc
0x180087498  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18008749d  mov     [rsp+748h+var_650], r12b
0x1800874a5  movups  xmm0, xmmword ptr cs:off_180369180; "DisableAllowedListGetFileInfoCheck"
0x1800874ac  movdqu  [rsp+748h+var_708], xmm0
0x1800874b2  lea     rcx, [rsp+748h+var_708]
0x1800874b7  call    ?IsTestHookEnabled@General@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::General::IsTestHookEnabled(std::wstring_view)
0x1800874bc  test    al, al
0x1800874be  jnz     loc_1800876D5
0x1800874c4  lea     rdx, [rsp+748h+var_6D8]
0x1800874c9  lea     rcx, [rsp+748h+var_3C8]
0x1800874d1  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800874d6  movups  xmm0, xmmword ptr [rax]
0x1800874d9  movdqu  [rsp+748h+var_708], xmm0
0x1800874df  lea     rdx, [rsp+748h+var_6C8]
0x1800874e7  lea     rcx, [rsp+748h+var_428]
0x1800874ef  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800874f4  movups  xmm0, xmmword ptr [rax]
0x1800874f7  movdqu  [rsp+748h+var_6A8], xmm0
0x180087500  lea     r9, [rsp+748h+var_708]
0x180087505  lea     r8, [rsp+748h+var_6A8]
0x18008750d  lea     rdx, [rsp+748h+var_388]
0x180087515  lea     rcx, ?m_fileRulesManager@GetFileInfoActionDef@Diagnostics@Microsoft@@2VFileRulesManager@23@A; Microsoft::Diagnostics::FileRulesManager Microsoft::Diagnostics::GetFileInfoActionDef::m_fileRulesManager
0x18008751c  call    ?FindMostNarrowAllowedRule@FileRulesManager@Diagnostics@Microsoft@@QEAA?AV?$optional@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@0@Z; Microsoft::Diagnostics::FileRulesManager::FindMostNarrowAllowedRule(std::wstring_view,std::wstring_view)
0x180087521  cmp     [rax+38h], r12b
0x180087525  jz      short loc_180087576
0x180087527  lea     rbx, [rax+20h]
0x18008752b  mov     rdx, rax
0x18008752e  lea     rcx, [rsp+748h+var_688]
0x180087536  cmp     [rsp+748h+var_650], r12b
0x18008753e  jz      short loc_180087557
0x180087540  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180087545  mov     rdx, rbx
0x180087548  lea     rcx, [rsp+748h+var_668]
0x180087550  call    ??4?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x180087555  jmp     short loc_180087595
0x180087557  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18008755c  mov     rdx, rbx
0x18008755f  lea     rcx, [rsp+748h+var_668]
0x180087567  call    ??0?$vector@U?$pair@_KUTriggerSettings@Diagnostics@Microsoft@@@std@@V?$allocator@U?$pair@_KUTriggerSettings@Diagnostics@Microsoft@@@std@@@2@@std@@QEAA@$$QEAV01@@Z; std::vector<std::pair<unsigned __int64,Microsoft::Diagnostics::TriggerSettings>>::vector<std::pair<unsigned __int64,Microsoft::Diagnostics::TriggerSettings>>(std::vector<std::pair<unsigned __int64,Microsoft::Diagnostics::TriggerSettings>> &&)
0x18008756c  mov     [rsp+748h+var_650], r13b
0x180087574  jmp     short loc_180087595
0x180087576  cmp     [rsp+748h+var_650], r12b
0x18008757e  jz      short loc_180087595
0x180087580  lea     rcx, [rsp+748h+var_688]; this
0x180087588  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@QEAA@XZ; std::pair<std::wstring,std::vector<std::wstring>>::~pair<std::wstring,std::vector<std::wstring>>(void)
0x18008758d  mov     [rsp+748h+var_650], r12b
0x180087595  lea     rcx, [rsp+748h+var_388]
0x18008759d  call    ??1?$_Optional_destruct_base@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(void)
0x1800875a2  cmp     [rsp+748h+var_650], r12b
0x1800875aa  jz      short loc_18008761A
0x1800875ac  lea     rdx, [rsp+748h+var_6D8]
0x1800875b1  lea     rcx, [rsp+748h+var_3C8]
0x1800875b9  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800875be  movups  xmm6, xmmword ptr [rax]
0x1800875c1  lea     rdx, [rsp+748h+var_6C8]
0x1800875c9  lea     rcx, [rsp+748h+var_428]
0x1800875d1  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800875d6  movups  xmm7, xmmword ptr [rax]
0x1800875d9  lea     rcx, [rsp+748h+var_688]
0x1800875e1  call    ?value@?$optional@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@std@@QEGAAAEAU?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@2@XZ; std::optional<std::pair<std::wstring,std::vector<std::wstring>>>::value(void)
0x1800875e6  movdqu  [rsp+748h+var_708], xmm6
0x1800875ec  movdqu  [rsp+748h+var_6A8], xmm7
0x1800875f5  lea     rdx, [rax+20h]
0x1800875f9  lea     r9, [rsp+748h+var_708]
0x1800875fe  lea     r8, [rsp+748h+var_6A8]
0x180087606  lea     rcx, ?m_fileRulesManager@GetFileInfoActionDef@Diagnostics@Microsoft@@2VFileRulesManager@23@A; Microsoft::Diagnostics::FileRulesManager Microsoft::Diagnostics::GetFileInfoActionDef::m_fileRulesManager
0x18008760d  call    ?CheckDeniedList@FileRulesManager@Diagnostics@Microsoft@@QEAA_NAEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@1@Z; Microsoft::Diagnostics::FileRulesManager::CheckDeniedList(std::vector<std::wstring> const &,std::wstring_view,std::wstring_view)
0x180087612  test    al, al
0x180087614  jnz     loc_1800876D5
0x18008761a  mov     rcx, [rdi+38h]
0x18008761e  mov     rax, [rcx]
0x180087621  mov     rax, [rax+48h]
0x180087625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008762a  mov     r8, rax
0x18008762d  lea     rdx, [rsp+748h+var_6D8]
0x180087632  lea     rcx, [rsp+748h+var_428]
0x18008763a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18008763f  movups  xmm0, xmmword ptr [rax]
0x180087642  movdqu  [rsp+748h+var_708], xmm0
0x180087648  lea     rdx, [rsp+748h+var_6C8]
0x180087650  lea     rcx, [rsp+748h+var_468]
0x180087658  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18008765d  movups  xmm0, xmmword ptr [rax]
0x180087660  movdqu  [rsp+748h+var_6A8], xmm0
0x180087669  lea     r9, [rdi+0Ch]
0x18008766d  mov     ebx, 87C5105Bh
0x180087672  mov     dword ptr [rsp+748h+var_728], ebx
0x180087676  lea     rdx, [rsp+748h+var_708]
0x18008767b  lea     rcx, [rsp+748h+var_6A8]
0x180087683  call    ?LogPathNotApprovedEvent@GetFileActionDef@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBU_GUID@@1J@Z; Microsoft::Diagnostics::GetFileActionDef::LogPathNotApprovedEvent(std::wstring_view,std::wstring_view,_GUID const &,_GUID const &,long)
0x180087688  nop
0x180087689  lea     rcx, [rsp+748h+var_688]
0x180087691  call    ??1?$_Optional_destruct_base@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(void)
0x180087696  nop
0x180087697  lea     rcx, [rsp+748h+var_3C8]; this
0x18008769f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800876a4  nop
0x1800876a5  lea     rcx, [rsp+748h+var_428]; this
0x1800876ad  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800876b2  nop
0x1800876b3  lea     rcx, [rsp+748h+var_468]; this
0x1800876bb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800876c0  nop
0x1800876c1  lea     rcx, [rsp+748h+pszPath]; this
0x1800876c9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800876ce  mov     eax, ebx
0x1800876d0  jmp     loc_1800882CC
0x1800876d5  mov     ebx, 5Ch ; '\'
0x1800876da  mov     edx, ebx
0x1800876dc  lea     rcx, [rsp+748h+var_468]
0x1800876e4  call    ?find_last_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_last_of(wchar_t,unsigned __int64)
0x1800876e9  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800876ed  cmp     rax, r14
0x1800876f0  jnz     short loc_18008775F
0x1800876f2  mov     rcx, [rsp+748h]; this
0x1800876fa  mov     ebx, 80004005h
0x1800876ff  mov     r9d, ebx; char *
0x180087702  lea     r8, aOnecoreBaseTel_184; "onecore\\base\\telemetry\\utc\\service"...
0x180087709  lea     edx, [r14+54h]; void *
0x18008770d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087712  nop
0x180087713  lea     rcx, [rsp+748h+var_688]
0x18008771b  call    ??1?$_Optional_destruct_base@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(void)
0x180087720  nop
0x180087721  lea     rcx, [rsp+748h+var_3C8]; this
0x180087729  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008772e  nop
0x18008772f  lea     rcx, [rsp+748h+var_428]; this
0x180087737  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008773c  nop
0x18008773d  lea     rcx, [rsp+748h+var_468]; this
0x180087745  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008774a  nop
0x18008774b  lea     rcx, [rsp+748h+pszPath]; this
0x180087753  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180087758  mov     eax, ebx
0x18008775a  jmp     loc_1800882CC
0x18008775f  mov     r9, rax
0x180087762  xor     r8d, r8d
0x180087765  lea     rdx, [rsp+748h+var_328]
0x18008776d  lea     rcx, [rsp+748h+var_468]
0x180087775  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18008777a  nop
0x18008777b  xor     r8d, r8d
0x18008777e  mov     dl, r13b
0x180087781  lea     rcx, [rsp+748h+var_468]; lpSrc
0x180087789  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18008778e  lea     rdx, [rsp+748h+var_6D8]
0x180087793  lea     rcx, [rsp+748h+var_468]
0x18008779b  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800877a0  movups  xmm0, xmmword ptr [rax]
0x1800877a3  movdqu  [rsp+748h+var_708], xmm0
0x1800877a9  lea     r8, [rsp+748h+var_708]
0x1800877ae  lea     rdx, [rsp+748h+FileName]
0x1800877b6  mov     rcx, rdi
0x1800877b9  call    ?ExpandPropertyIdentifiers@ScenarioInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@5@@Z; Microsoft::Diagnostics::ScenarioInst::ExpandPropertyIdentifiers(std::wstring_view)
0x1800877be  mov     rdx, rax
0x1800877c1  lea     rcx, [rsp+748h+var_468]
0x1800877c9  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800877ce  lea     rcx, [rsp+748h+FileName]; this
0x1800877d6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800877db  mov     edx, ebx
0x1800877dd  lea     rcx, [rsp+748h+var_468]
0x1800877e5  call    ?find_last_of@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA_K_W_K@Z; std::wstring::find_last_of(wchar_t,unsigned __int64)
0x1800877ea  mov     rbx, rax
0x1800877ed  cmp     rax, r14
0x1800877f0  jnz     short loc_18008786E
0x1800877f2  mov     rcx, [rsp+748h]; this
0x1800877fa  mov     ebx, 80004005h
0x1800877ff  mov     r9d, ebx; char *
0x180087802  lea     r8, aOnecoreBaseTel_184; "onecore\\base\\telemetry\\utc\\service"...
0x180087809  mov     edx, 60h ; '`'; void *
0x18008780e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087813  nop
0x180087814  lea     rcx, [rsp+748h+var_328]; this
0x18008781c  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180087821  nop
0x180087822  lea     rcx, [rsp+748h+var_688]
0x18008782a  call    ??1?$_Optional_destruct_base@U?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@$0A@@std@@QEAA@XZ; std::_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>::~_Optional_destruct_base<std::pair<std::wstring,std::vector<std::wstring>>,0>(void)
0x18008782f  nop
0x180087830  lea     rcx, [rsp+748h+var_3C8]; this
0x180087838  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008783d  nop
0x18008783e  lea     rcx, [rsp+748h+var_428]; this
0x180087846  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008784b  nop
0x18008784c  lea     rcx, [rsp+748h+var_468]; this
0x180087854  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180087859  nop
0x18008785a  lea     rcx, [rsp+748h+pszPath]; this
0x180087862  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180087867  mov     eax, ebx
0x180087869  jmp     loc_1800882CC
0x18008786e  mov     r9, rbx
0x180087871  xor     r8d, r8d
0x180087874  lea     rdx, [rsp+748h+var_3E8]
0x18008787c  lea     rcx, [rsp+748h+var_468]
0x180087884  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180087889  nop
0x18008788a  lea     r8, [rbx+1]
0x18008788e  mov     r9, r14
0x180087891  lea     rdx, [rsp+748h+var_3A8]
0x180087899  lea     rcx, [rsp+748h+var_468]
0x1800878a1  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800878a6  nop
0x1800878a7  lea     rdx, [rsp+748h+var_3A8]
  ... truncated ...
```
