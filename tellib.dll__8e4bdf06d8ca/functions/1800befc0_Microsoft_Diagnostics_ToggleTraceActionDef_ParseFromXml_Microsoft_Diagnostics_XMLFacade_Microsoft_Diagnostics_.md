# Microsoft::Diagnostics::ToggleTraceActionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800befc0`
- end: `0x1800c00b5`
- name: `?ParseFromXml@ToggleTraceActionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `4341`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::ToggleTraceActionDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180015884`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x1800326cc`
- `0x180038870`
- `0x180053a84`
- `0x180090930`
- `0x180090b68`
- `0x18009163c`
- `0x1800b10c8`
- `0x1800bef30`
- `0x1800befc0`
- `0x1800c00bc`
- `0x1800de308`
- `0x1800f4db8`
- `0x18012de40`
- `0x1801e38fc`
- `0x18022a6b8`
- `0x1802384e0`
- `0x18023b62c`
- `0x18026160c`
- `0x1802e6744`
- `0x1802e6bec`
- `0x1802e6d88`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bf5b4`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800bf5b4`

## string_xrefs

- `0x1800bf29f`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf37d`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf414`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf50b`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf5d5`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf67a`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf77f`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf83f`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bf941`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfa07`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfac6`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfb5d`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfc07`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfc89`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfd0b`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfd8d`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bfe0f`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`
- `0x1800bff07`: `onecore\base\telemetry\utc\service\scenarios\actions\toggletraceaction.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::ToggleTraceActionDef::ParseFromXml(
        Microsoft::Diagnostics::ToggleTraceActionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  int v6; // r13d
  int v7; // r14d
  int v8; // r12d
  unsigned int v9; // r15d
  unsigned int Element; // eax
  __int64 v11; // rdx
  unsigned int v12; // esi
  int CurrentElementName; // eax
  unsigned int v14; // esi
  int v16; // eax
  unsigned int v17; // esi
  int v18; // eax
  unsigned int v19; // esi
  int InnerText; // eax
  unsigned int v21; // esi
  const OLECHAR *v22; // rcx
  HRESULT v23; // eax
  unsigned int v24; // esi
  int v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  unsigned int v28; // esi
  int v29; // eax
  unsigned int v30; // esi
  int v31; // eax
  unsigned int v32; // esi
  __int64 v33; // rdx
  int v34; // eax
  unsigned int v35; // esi
  int v36; // eax
  unsigned int v37; // esi
  __int64 v38; // rax
  std::_Ref_count_base *v39; // rbx
  std::_Ref_count_base *v40; // rsi
  int v41; // eax
  unsigned int v42; // r14d
  char *v43; // rcx
  std::_Ref_count_base **v44; // rdx
  std::_Ref_count_base *v45[2]; // [rsp+20h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v46[2]; // [rsp+30h] [rbp-1B8h] BYREF
  unsigned __int16 v47[8]; // [rsp+40h] [rbp-1A8h] BYREF
  __int128 v48; // [rsp+50h] [rbp-198h] BYREF
  struct Microsoft::Diagnostics::ScenarioParsingState *v49; // [rsp+60h] [rbp-188h]
  __int64 v50; // [rsp+68h] [rbp-180h] BYREF
  _BYTE v51[16]; // [rsp+70h] [rbp-178h] BYREF
  _BYTE v52[16]; // [rsp+80h] [rbp-168h] BYREF
  _BYTE v53[16]; // [rsp+90h] [rbp-158h] BYREF
  LPCOLESTR lpsz[4]; // [rsp+A0h] [rbp-148h] BYREF
  _BYTE v55[32]; // [rsp+C0h] [rbp-128h] BYREF
  _BYTE v56[32]; // [rsp+E0h] [rbp-108h] BYREF
  _BYTE v57[32]; // [rsp+100h] [rbp-E8h] BYREF
  _BYTE v58[32]; // [rsp+120h] [rbp-C8h] BYREF
  _BYTE v59[32]; // [rsp+140h] [rbp-A8h] BYREF
  _BYTE v60[32]; // [rsp+160h] [rbp-88h] BYREF
  _BYTE v61[32]; // [rsp+180h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v49 = a3;
  Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(
    v47,
    *((unsigned __int16 *)this + 60));
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v50, (char *)a3 + 112, v47[0]);
  *(_OWORD *)v45 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 88, &v48);
  Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(&v50, v45);
  std::wstring::wstring(v60);
  *(_OWORD *)v46 = *(_OWORD *)&off_180368DB0;
  v45[0] = (std::_Ref_count_base *)&Src;
  v45[1] = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v45, v46, v60) != 1 )
  {
    *(_OWORD *)v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v60, &v48);
    *((_BYTE *)this + 161) = Microsoft::Diagnostics::Utils::String::ToBool(v46);
  }
  std::wstring::wstring(v59);
  *(_OWORD *)v46 = *(_OWORD *)&off_180368D10;
  v45[0] = (std::_Ref_count_base *)&Src;
  v45[1] = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v45, v46, v59) != 1 )
  {
    *(_OWORD *)v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v59, &v48);
    *((_BYTE *)this + 162) = Microsoft::Diagnostics::Utils::String::ToBool(v46);
  }
  std::wstring::wstring(v58);
  *(_OWORD *)v46 = *(_OWORD *)&off_180368D20;
  v45[0] = (std::_Ref_count_base *)&Src;
  v45[1] = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v45, v46, v58) != 1 )
    *((_QWORD *)this + 21) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v58);
  std::wstring::wstring(v57);
  *(_OWORD *)v46 = *(_OWORD *)&off_180368CF0;
  v45[0] = (std::_Ref_count_base *)&Src;
  v45[1] = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v45, v46, v57) != 1 )
  {
    *(_OWORD *)v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v57, &v48);
    *((_BYTE *)this + 163) = Microsoft::Diagnostics::Utils::String::ToBool(v46);
  }
  std::wstring::wstring(v56);
  *(_OWORD *)v46 = *(_OWORD *)&off_180368D00;
  v45[0] = (std::_Ref_count_base *)&Src;
  v45[1] = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v45, v46, v56) != 1 )
    *((_DWORD *)this + 44) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v56);
  v6 = 0;
  v7 = 0;
  v8 = 0;
  v9 = 0;
  std::wstring::wstring(v55);
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v12 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v61);
    CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v61);
    v14 = CurrentElementName;
    if ( CurrentElementName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
        (const char *)(unsigned int)CurrentElementName,
        (int)v45[0]);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
      return v14;
    }
    *(_OWORD *)v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v61, &v48);
    *(_OWORD *)v45 = *(_OWORD *)off_180368D50;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v45, v46) )
    {
      *(_OWORD *)v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v61, v52);
      *(_OWORD *)v45 = *(_OWORD *)off_180368D60;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v45, v46) )
      {
        std::wstring::wstring(lpsz);
        InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
        v21 = InnerText;
        if ( InnerText < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x169,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)(unsigned int)InnerText,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return v21;
        }
        v22 = (const OLECHAR *)lpsz;
        if ( lpsz[3] > (LPCOLESTR)7 )
          v22 = lpsz[0];
        v23 = CLSIDFromString(v22, (LPCLSID)((char *)this + 136));
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16D,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)(unsigned int)v23,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return v24;
        }
        v25 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v26 = v25;
        if ( v25 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x170,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)(unsigned int)v25,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return v26;
        }
        ++v6;
LABEL_43:
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        goto LABEL_48;
      }
      *(_OWORD *)v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v61, v53);
      *(_OWORD *)v45 = *(_OWORD *)off_180368D30;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v45, v46) )
      {
        std::wstring::wstring(lpsz);
        v27 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
        v28 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x177,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)(unsigned int)v27,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return v28;
        }
        *((_QWORD *)this + 19) = 10000000 * Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
        v29 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v30 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17B,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)(unsigned int)v29,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return v30;
        }
        ++v8;
        goto LABEL_43;
      }
      *(_OWORD *)v46 = *(_OWORD *)std::wstring::operator std::wstring_view(v61, v51);
      *(_OWORD *)v45 = *(_OWORD *)off_180368D40;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v45, v46) )
      {
        std::wstring::wstring(lpsz);
        v31 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
        v32 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)(unsigned int)v31,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return v32;
        }
        LOBYTE(v33) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
        *((_BYTE *)this + 160) = *(_BYTE *)Microsoft::Diagnostics::TracePriority::_from_integral(v47, v33);
        v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v35 = v34;
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x186,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)(unsigned int)v34,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return v35;
        }
        ++v9;
        goto LABEL_43;
      }
      if ( *((_BYTE *)v49 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
          (const char *)0x87C52407LL,
          (int)v45[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
        return 2277843975LL;
      }
      v36 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v37 = v36;
      if ( v36 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x191,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
          (const char *)(unsigned int)v36,
          (int)v45[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
        return v37;
      }
    }
    else
    {
      v16 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v55);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
          (const char *)(unsigned int)v16,
          (int)v45[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
        return v17;
      }
      v18 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x163,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
          (const char *)(unsigned int)v18,
          (int)v45[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
        return v19;
      }
      ++v7;
    }
LABEL_48:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v61);
  }
  if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
  {
    if ( v7 == 1 )
    {
      if ( v6 == 1 )
      {
        if ( v8 == 1 )
        {
          if ( v9 <= 1 )
          {
            LOBYTE(v11) = 0;
            v38 = Microsoft::Diagnostics::ITraceProfileDef::Create(v46, v11);
            v39 = *(std::_Ref_count_base **)v38;
            v45[0] = *(std::_Ref_count_base **)v38;
            v40 = *(std::_Ref_count_base **)(v38 + 8);
            v45[1] = v40;
            *(_QWORD *)v38 = 0;
            *(_QWORD *)(v38 + 8) = 0;
            if ( v46[1] )
              std::_Ref_count_base::_Decref(v46[1]);
            std::string::string(lpsz);
            v48 = *(_OWORD *)std::wstring::operator std::wstring_view(v55, v51);
            v41 = Microsoft::Diagnostics::Utils::String::DecodeBase64ToString(&v48, lpsz);
            v42 = v41;
            if ( v41 >= 0 )
            {
              Microsoft::Diagnostics::ITraceProfileDef::SetProfile(v39, lpsz);
              (*(void (__fastcall **)(std::_Ref_count_base *, _QWORD))(*(_QWORD *)v39 + 16LL))(v39, 0);
              *((_QWORD *)this + 16) = (**(__int64 (__fastcall ***)(std::_Ref_count_base *))v39)(v39);
              std::string::_Tidy_deallocate(lpsz);
              v43 = (char *)v49 + 344;
              v44 = (std::_Ref_count_base **)*((_QWORD *)v49 + 44);
              if ( v44 == *((std::_Ref_count_base ***)v49 + 45) )
              {
                ____Emplace_reallocate_V__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std_____vector_V__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std__V__allocator_V__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___std___2__std__AEAAPEAV__shared_ptr_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___1_QEAV21___QEAV21__Z(
                  v43,
                  v44,
                  v45);
              }
              else
              {
                *v44 = v39;
                v44[1] = v40;
                *(_OWORD *)v45 = 0;
                *((_QWORD *)v43 + 1) += 16LL;
              }
              (*(void (__fastcall **)(Microsoft::Diagnostics::ToggleTraceActionDef *, _QWORD))(*(_QWORD *)this + 16LL))(
                this,
                0);
              std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v50);
              if ( v45[1] )
                std::_Ref_count_base::_Decref(v45[1]);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AF,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
                (const char *)(unsigned int)v41,
                (int)v45[0]);
              std::string::_Tidy_deallocate(lpsz);
              if ( v40 )
                std::_Ref_count_base::_Decref(v40);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
              return v42;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A9,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
              (const char *)0x87C52402LL,
              (int)v45[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
            return 2277843970LL;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A4,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
            (const char *)0x87C52402LL,
            (int)v45[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
          return 2277843970LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x19F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
          (const char *)0x87C52402LL,
          (int)v45[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
        return 2277843970LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
        (const char *)0x87C52402LL,
        (int)v45[0]);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
      return 2277843970LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\actions\\toggletraceaction.cpp",
      (const char *)Element,
      (int)v45[0]);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v55);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v56);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v57);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v58);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v59);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v60);
    return v12;
  }
}

```

## disassembly

```asm
0x1800befc0  push    rbx
0x1800befc2  push    rsi
0x1800befc3  push    rdi
0x1800befc4  push    r12
0x1800befc6  push    r13
0x1800befc8  push    r14
0x1800befca  push    r15
0x1800befcc  sub     rsp, 1B0h
0x1800befd3  mov     rax, cs:__security_cookie
0x1800befda  xor     rax, rsp
0x1800befdd  mov     [rsp+1E8h+var_48], rax
0x1800befe5  mov     rsi, r8
0x1800befe8  mov     [rsp+1E8h+var_188], r8
0x1800befed  mov     rbx, rdx
0x1800beff0  mov     rdi, rcx
0x1800beff3  movzx   edx, word ptr [rcx+78h]
0x1800beff7  lea     rcx, [rsp+1E8h+var_1A8]
0x1800beffc  call    ?ConvertActionTypeToScenarioDbObjectType@TypeToScenarioDbObjectTypeConverter@Diagnostics@Microsoft@@SA?AVScenarioDbObjectType@23@VActionType@23@@Z; Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(Microsoft::Diagnostics::ActionType)
0x1800bf001  lea     rdx, [rsi+70h]
0x1800bf005  movzx   r8d, [rsp+1E8h+var_1A8]
0x1800bf00b  lea     rcx, [rsp+1E8h+var_180]
0x1800bf010  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800bf015  lea     rcx, [rdi+58h]
0x1800bf019  lea     rdx, [rsp+1E8h+var_198]
0x1800bf01e  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bf023  movups  xmm0, xmmword ptr [rax]
0x1800bf026  movdqu  xmmword ptr [rsp+1E8h+var_1C8], xmm0
0x1800bf02c  lea     rdx, [rsp+1E8h+var_1C8]
0x1800bf031  lea     rcx, [rsp+1E8h+var_180]
0x1800bf036  call    ?AddDetailToCurrentFrame@ParsingDomain@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(std::wstring_view)
0x1800bf03b  lea     rcx, [rsp+1E8h+var_88]; void *
0x1800bf043  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf048  nop
0x1800bf049  movups  xmm0, xmmword ptr cs:off_180368DB0; "isautologger"
0x1800bf050  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf056  lea     r14, Src
0x1800bf05d  mov     [rsp+1E8h+var_1C8], r14
0x1800bf062  xor     esi, esi
0x1800bf064  mov     [rsp+1E8h+var_1C8+8], rsi
0x1800bf069  lea     r9, [rsp+1E8h+var_88]
0x1800bf071  lea     r8, [rsp+1E8h+var_1B8]
0x1800bf076  lea     rdx, [rsp+1E8h+var_1C8]
0x1800bf07b  mov     rcx, rbx
0x1800bf07e  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800bf083  cmp     eax, 1
0x1800bf086  jz      short loc_1800BF0B3
0x1800bf088  lea     rdx, [rsp+1E8h+var_198]
0x1800bf08d  lea     rcx, [rsp+1E8h+var_88]
0x1800bf095  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bf09a  movups  xmm0, xmmword ptr [rax]
0x1800bf09d  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf0a3  lea     rcx, [rsp+1E8h+var_1B8]
0x1800bf0a8  call    ?ToBool@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToBool(std::wstring_view)
0x1800bf0ad  mov     [rdi+0A1h], al
0x1800bf0b3  lea     rcx, [rsp+1E8h+var_A8]; void *
0x1800bf0bb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf0c0  nop
0x1800bf0c1  movups  xmm0, xmmword ptr cs:off_180368D10; "requireexclusive"
0x1800bf0c8  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf0ce  mov     [rsp+1E8h+var_1C8], r14
0x1800bf0d3  mov     [rsp+1E8h+var_1C8+8], rsi
0x1800bf0d8  lea     r9, [rsp+1E8h+var_A8]
0x1800bf0e0  lea     r8, [rsp+1E8h+var_1B8]
0x1800bf0e5  lea     rdx, [rsp+1E8h+var_1C8]
0x1800bf0ea  mov     rcx, rbx
0x1800bf0ed  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800bf0f2  cmp     eax, 1
0x1800bf0f5  jz      short loc_1800BF122
0x1800bf0f7  lea     rdx, [rsp+1E8h+var_198]
0x1800bf0fc  lea     rcx, [rsp+1E8h+var_A8]
0x1800bf104  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bf109  movups  xmm0, xmmword ptr [rax]
0x1800bf10c  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf112  lea     rcx, [rsp+1E8h+var_1B8]
0x1800bf117  call    ?ToBool@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToBool(std::wstring_view)
0x1800bf11c  mov     [rdi+0A2h], al
0x1800bf122  lea     rcx, [rsp+1E8h+var_C8]; void *
0x1800bf12a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf12f  nop
0x1800bf130  movups  xmm0, xmmword ptr cs:off_180368D20; "minimumviabletracedurationfiletime"
0x1800bf137  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf13d  mov     [rsp+1E8h+var_1C8], r14
0x1800bf142  mov     [rsp+1E8h+var_1C8+8], rsi
0x1800bf147  lea     r9, [rsp+1E8h+var_C8]
0x1800bf14f  lea     r8, [rsp+1E8h+var_1B8]
0x1800bf154  lea     rdx, [rsp+1E8h+var_1C8]
0x1800bf159  mov     rcx, rbx
0x1800bf15c  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800bf161  cmp     eax, 1
0x1800bf164  jz      short loc_1800BF17A
0x1800bf166  lea     rcx, [rsp+1E8h+var_C8]
0x1800bf16e  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x1800bf173  mov     [rdi+0A8h], rax
0x1800bf17a  lea     rcx, [rsp+1E8h+var_E8]; void *
0x1800bf182  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf187  nop
0x1800bf188  movups  xmm0, xmmword ptr cs:off_180368CF0; "requirengenpdbs"
0x1800bf18f  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf195  mov     [rsp+1E8h+var_1C8], r14
0x1800bf19a  mov     [rsp+1E8h+var_1C8+8], rsi
0x1800bf19f  lea     r9, [rsp+1E8h+var_E8]
0x1800bf1a7  lea     r8, [rsp+1E8h+var_1B8]
0x1800bf1ac  lea     rdx, [rsp+1E8h+var_1C8]
0x1800bf1b1  mov     rcx, rbx
0x1800bf1b4  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800bf1b9  cmp     eax, 1
0x1800bf1bc  jz      short loc_1800BF1E9
0x1800bf1be  lea     rdx, [rsp+1E8h+var_198]
0x1800bf1c3  lea     rcx, [rsp+1E8h+var_E8]
0x1800bf1cb  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bf1d0  movups  xmm0, xmmword ptr [rax]
0x1800bf1d3  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf1d9  lea     rcx, [rsp+1E8h+var_1B8]
0x1800bf1de  call    ?ToBool@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToBool(std::wstring_view)
0x1800bf1e3  mov     [rdi+0A3h], al
0x1800bf1e9  lea     rcx, [rsp+1E8h+var_108]; void *
0x1800bf1f1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf1f6  nop
0x1800bf1f7  movups  xmm0, xmmword ptr cs:off_180368D00; "overridebuffercappermil"
0x1800bf1fe  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf204  mov     [rsp+1E8h+var_1C8], r14; int
0x1800bf209  mov     [rsp+1E8h+var_1C8+8], rsi
0x1800bf20e  lea     r9, [rsp+1E8h+var_108]
0x1800bf216  lea     r8, [rsp+1E8h+var_1B8]
0x1800bf21b  lea     rdx, [rsp+1E8h+var_1C8]
0x1800bf220  mov     rcx, rbx
0x1800bf223  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800bf228  cmp     eax, 1
0x1800bf22b  jz      short loc_1800BF240
0x1800bf22d  lea     rcx, [rsp+1E8h+var_108]
0x1800bf235  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x1800bf23a  mov     [rdi+0B0h], eax
0x1800bf240  mov     r13d, esi
0x1800bf243  mov     r14d, esi
0x1800bf246  mov     r12d, esi
0x1800bf249  mov     r15d, esi
0x1800bf24c  lea     rcx, [rsp+1E8h+var_128]; void *
0x1800bf254  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf259  nop
0x1800bf25a  mov     rcx, rbx; this
0x1800bf25d  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x1800bf262  mov     esi, eax
0x1800bf264  test    eax, eax
0x1800bf266  jnz     loc_1800BFBE9
0x1800bf26c  lea     rcx, [rsp+1E8h+var_68]; void *
0x1800bf274  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf279  nop
0x1800bf27a  lea     rdx, [rsp+1E8h+var_68]
0x1800bf282  mov     rcx, rbx
0x1800bf285  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1800bf28a  mov     esi, eax
0x1800bf28c  test    eax, eax
0x1800bf28e  jns     loc_1800BF319
0x1800bf294  mov     rcx, [rsp+1E8h]; this
0x1800bf29c  mov     r9d, eax; char *
0x1800bf29f  lea     r8, aOnecoreBaseTel_75; "onecore\\base\\telemetry\\utc\\service"...
0x1800bf2a6  mov     edx, 15Eh; void *
0x1800bf2ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf2b0  nop
0x1800bf2b1  lea     rcx, [rsp+1E8h+var_68]; this
0x1800bf2b9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf2be  nop
0x1800bf2bf  lea     rcx, [rsp+1E8h+var_128]; this
0x1800bf2c7  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf2cc  nop
0x1800bf2cd  lea     rcx, [rsp+1E8h+var_108]; this
0x1800bf2d5  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf2da  nop
0x1800bf2db  lea     rcx, [rsp+1E8h+var_E8]; this
0x1800bf2e3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf2e8  nop
0x1800bf2e9  lea     rcx, [rsp+1E8h+var_C8]; this
0x1800bf2f1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf2f6  nop
0x1800bf2f7  lea     rcx, [rsp+1E8h+var_A8]; this
0x1800bf2ff  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf304  nop
0x1800bf305  lea     rcx, [rsp+1E8h+var_88]; this
0x1800bf30d  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf312  mov     eax, esi
0x1800bf314  jmp     loc_1800C0091
0x1800bf319  lea     rdx, [rsp+1E8h+var_198]
0x1800bf31e  lea     rcx, [rsp+1E8h+var_68]
0x1800bf326  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bf32b  movups  xmm0, xmmword ptr [rax]
0x1800bf32e  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf334  movups  xmm1, xmmword ptr cs:off_180368D50; "traceprofile"
0x1800bf33b  movdqu  xmmword ptr [rsp+1E8h+var_1C8], xmm1; int
0x1800bf341  lea     rdx, [rsp+1E8h+var_1B8]
0x1800bf346  lea     rcx, [rsp+1E8h+var_1C8]
0x1800bf34b  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800bf350  test    eax, eax
0x1800bf352  jnz     loc_1800BF496
0x1800bf358  lea     rdx, [rsp+1E8h+var_128]
0x1800bf360  mov     rcx, rbx
0x1800bf363  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800bf368  mov     esi, eax
0x1800bf36a  test    eax, eax
0x1800bf36c  jns     loc_1800BF3F7
0x1800bf372  mov     rcx, [rsp+1E8h]; this
0x1800bf37a  mov     r9d, eax; char *
0x1800bf37d  lea     r8, aOnecoreBaseTel_75; "onecore\\base\\telemetry\\utc\\service"...
0x1800bf384  mov     edx, 162h; void *
0x1800bf389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf38e  nop
0x1800bf38f  lea     rcx, [rsp+1E8h+var_68]; this
0x1800bf397  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf39c  nop
0x1800bf39d  lea     rcx, [rsp+1E8h+var_128]; this
0x1800bf3a5  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf3aa  nop
0x1800bf3ab  lea     rcx, [rsp+1E8h+var_108]; this
0x1800bf3b3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf3b8  nop
0x1800bf3b9  lea     rcx, [rsp+1E8h+var_E8]; this
0x1800bf3c1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf3c6  nop
0x1800bf3c7  lea     rcx, [rsp+1E8h+var_C8]; this
0x1800bf3cf  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf3d4  nop
0x1800bf3d5  lea     rcx, [rsp+1E8h+var_A8]; this
0x1800bf3dd  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf3e2  nop
0x1800bf3e3  lea     rcx, [rsp+1E8h+var_88]; this
0x1800bf3eb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf3f0  mov     eax, esi
0x1800bf3f2  jmp     loc_1800C0091
0x1800bf3f7  mov     rcx, rbx; this
0x1800bf3fa  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1800bf3ff  mov     esi, eax
0x1800bf401  test    eax, eax
0x1800bf403  jns     loc_1800BF48E
0x1800bf409  mov     rcx, [rsp+1E8h]; this
0x1800bf411  mov     r9d, eax; char *
0x1800bf414  lea     r8, aOnecoreBaseTel_75; "onecore\\base\\telemetry\\utc\\service"...
0x1800bf41b  mov     edx, 163h; void *
0x1800bf420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf425  nop
0x1800bf426  lea     rcx, [rsp+1E8h+var_68]; this
0x1800bf42e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf433  nop
0x1800bf434  lea     rcx, [rsp+1E8h+var_128]; this
0x1800bf43c  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf441  nop
0x1800bf442  lea     rcx, [rsp+1E8h+var_108]; this
0x1800bf44a  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf44f  nop
0x1800bf450  lea     rcx, [rsp+1E8h+var_E8]; this
0x1800bf458  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf45d  nop
0x1800bf45e  lea     rcx, [rsp+1E8h+var_C8]; this
0x1800bf466  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf46b  nop
0x1800bf46c  lea     rcx, [rsp+1E8h+var_A8]; this
0x1800bf474  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf479  nop
0x1800bf47a  lea     rcx, [rsp+1E8h+var_88]; this
0x1800bf482  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf487  mov     eax, esi
0x1800bf489  jmp     loc_1800C0091
0x1800bf48e  inc     r14d
0x1800bf491  jmp     loc_1800BFBD7
0x1800bf496  lea     rdx, [rsp+1E8h+var_168]
0x1800bf49e  lea     rcx, [rsp+1E8h+var_68]
0x1800bf4a6  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bf4ab  movups  xmm0, xmmword ptr [rax]
0x1800bf4ae  movdqu  xmmword ptr [rsp+1E8h+var_1B8], xmm0
0x1800bf4b4  movups  xmm1, xmmword ptr cs:off_180368D60; "traceprofilescenarioid"
0x1800bf4bb  movdqu  xmmword ptr [rsp+1E8h+var_1C8], xmm1; int
0x1800bf4c1  lea     rdx, [rsp+1E8h+var_1B8]
0x1800bf4c6  lea     rcx, [rsp+1E8h+var_1C8]
0x1800bf4cb  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800bf4d0  test    eax, eax
0x1800bf4d2  jnz     loc_1800BF70A
0x1800bf4d8  lea     rcx, [rsp+1E8h+lpsz]; void *
0x1800bf4e0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bf4e5  nop
0x1800bf4e6  lea     rdx, [rsp+1E8h+lpsz]
0x1800bf4ee  mov     rcx, rbx
0x1800bf4f1  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1800bf4f6  mov     esi, eax
0x1800bf4f8  test    eax, eax
0x1800bf4fa  jns     loc_1800BF593
0x1800bf500  mov     rcx, [rsp+1E8h]; this
0x1800bf508  mov     r9d, eax; char *
0x1800bf50b  lea     r8, aOnecoreBaseTel_75; "onecore\\base\\telemetry\\utc\\service"...
0x1800bf512  mov     edx, 169h; void *
0x1800bf517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bf51c  nop
0x1800bf51d  lea     rcx, [rsp+1E8h+lpsz]; this
0x1800bf525  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf52a  nop
0x1800bf52b  lea     rcx, [rsp+1E8h+var_68]; this
0x1800bf533  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf538  nop
0x1800bf539  lea     rcx, [rsp+1E8h+var_128]; this
0x1800bf541  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bf546  nop
0x1800bf547  lea     rcx, [rsp+1E8h+var_108]; this
0x1800bf54f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
  ... truncated ...
```
