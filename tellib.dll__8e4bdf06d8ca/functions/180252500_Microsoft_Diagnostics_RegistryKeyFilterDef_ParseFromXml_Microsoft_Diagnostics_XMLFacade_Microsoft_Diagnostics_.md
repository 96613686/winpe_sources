# Microsoft::Diagnostics::RegistryKeyFilterDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x180252500`
- end: `0x18025309f`
- name: `?ParseFromXml@RegistryKeyFilterDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `2975`
- prototype: `int(Microsoft::Diagnostics::RegistryKeyFilterDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a78c`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180053a84`
- `0x180090930`
- `0x1800a0d08`
- `0x1800bef30`
- `0x1800de308`
- `0x18012de40`
- `0x1801e38fc`
- `0x180206238`
- `0x1802384e0`
- `0x18023b62c`
- `0x18024cf64`
- `0x180251fec`
- `0x180252500`
- `0x1802e6744`
- `0x1802e6bec`
- `0x1802e6d88`
- `0x180346010`

## string_xrefs

- `0x180252561`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x18025271e`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x18025279f`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1802527fa`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1802528a4`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1802528f1`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x18025298c`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x1802529d9`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252a86`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252b0b`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252b68`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252bc3`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252c91`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252cec`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252dc4`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252e46`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252ea1`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252f1b`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252f68`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180252fcc`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`
- `0x180253054`: `onecore\base\telemetry\utc\service\scenarios\filters\registrykeyfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::RegistryKeyFilterDef::ParseFromXml(
        Microsoft::Diagnostics::RegistryKeyFilterDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // r8
  char v13; // al
  int v14; // r12d
  int v15; // r13d
  int v16; // r15d
  unsigned int Element; // eax
  unsigned int v18; // edi
  int InnerText; // eax
  unsigned int v20; // edi
  int HiveFromString; // eax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // edi
  int v26; // eax
  unsigned int v27; // edi
  int v28; // eax
  unsigned int v29; // edi
  int v30; // eax
  unsigned int v31; // edi
  int v32; // eax
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  _DWORD *v36; // r15
  int v37; // eax
  unsigned int v38; // edi
  int v39; // eax
  unsigned int v40; // edi
  int v41; // eax
  unsigned int v42; // edi
  int v43; // eax
  unsigned int v44; // edi
  int v45; // eax
  unsigned int v46; // edi
  int v47; // eax
  unsigned int v48; // edi
  int v49; // eax
  unsigned int v50; // edi
  int v51; // eax
  unsigned int v52; // edi
  int v53[4]; // [rsp+20h] [rbp-198h] BYREF
  int v54; // [rsp+30h] [rbp-188h]
  __int128 v55; // [rsp+40h] [rbp-178h] BYREF
  int v56; // [rsp+50h] [rbp-168h]
  int v57; // [rsp+54h] [rbp-164h]
  int v58; // [rsp+58h] [rbp-160h]
  __int64 v59; // [rsp+60h] [rbp-158h] BYREF
  struct Microsoft::Diagnostics::ScenarioParsingState *v60; // [rsp+68h] [rbp-150h]
  _BYTE v61[16]; // [rsp+70h] [rbp-148h] BYREF
  _BYTE v62[16]; // [rsp+80h] [rbp-138h] BYREF
  _BYTE v63[16]; // [rsp+90h] [rbp-128h] BYREF
  _BYTE v64[16]; // [rsp+A0h] [rbp-118h] BYREF
  _BYTE v65[16]; // [rsp+B0h] [rbp-108h] BYREF
  _BYTE v66[16]; // [rsp+C0h] [rbp-F8h] BYREF
  _BYTE v67[16]; // [rsp+D0h] [rbp-E8h] BYREF
  _BYTE v68[16]; // [rsp+E0h] [rbp-D8h] BYREF
  _BYTE v69[16]; // [rsp+F0h] [rbp-C8h] BYREF
  _BYTE v70[16]; // [rsp+100h] [rbp-B8h] BYREF
  _BYTE v71[32]; // [rsp+110h] [rbp-A8h] BYREF
  _BYTE v72[32]; // [rsp+130h] [rbp-88h] BYREF
  _BYTE v73[32]; // [rsp+150h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v60 = a3;
  v6 = *((unsigned __int16 *)this + 8);
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 != 1 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x3B5,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                  (const char *)a3);
              v12 = 11;
            }
            else
            {
              v12 = 10;
            }
          }
          else
          {
            v12 = 9;
          }
        }
        else
        {
          v12 = 8;
        }
      }
      else
      {
        v12 = 7;
      }
    }
    else
    {
      v12 = 6;
    }
  }
  else
  {
    v12 = 5;
  }
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v59, (char *)a3 + 112, v12);
  v55 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 24, v53);
  Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(&v59, &v55);
  std::wstring::wstring(v73);
  *(_OWORD *)v53 = *(_OWORD *)off_180362980;
  *(_QWORD *)&v55 = &Src;
  *((_QWORD *)&v55 + 1) = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v55, v53, v73) == 1 )
  {
    v13 = 0;
  }
  else
  {
    *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v73, &v55);
    v13 = Microsoft::Diagnostics::Utils::String::ToBool(v53);
  }
  v56 = 0;
  v14 = 0;
  v15 = 0;
  v57 = 0;
  v58 = 0;
  v16 = 0;
  v54 = 0;
  *((_BYTE *)this + 160) = v13;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v18 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v72);
    Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v72);
    *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v72, v61);
    v55 = *(_OWORD *)&off_180362990;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v55, v53) )
    {
      std::wstring::wstring(v71);
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v71);
      v20 = InnerText;
      if ( InnerText < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x180,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
          (const char *)(unsigned int)InnerText,
          v53[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
        return v20;
      }
      *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v62);
      HiveFromString = Microsoft::Diagnostics::Utils::Xml::GetHiveFromString(v53, 0, (char *)this + 56);
      v23 = HiveFromString;
      if ( HiveFromString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
          (const char *)(unsigned int)HiveFromString,
          v53[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
        return v23;
      }
      v24 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x182,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
          (const char *)(unsigned int)v24,
          v53[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
        return v25;
      }
      ++v56;
LABEL_66:
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
      goto LABEL_71;
    }
    *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v72, v63);
    v55 = *(_OWORD *)&off_180362960;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v55, v53) )
    {
      *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v72, v64);
      v55 = *(_OWORD *)&off_180362970;
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v55, v53) )
      {
        *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v72, v65);
        v55 = *(_OWORD *)&off_180362950;
        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v55, v53) )
        {
          *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v72, v67);
          v55 = *(_OWORD *)&off_1803628D0;
          if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v55, v53) )
          {
            std::wstring::wstring(v71);
            v41 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v71);
            v42 = v41;
            if ( v41 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A4,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v41,
                v53[0]);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
              return v42;
            }
            v43 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v44 = v43;
            if ( v43 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1A5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v43,
                v53[0]);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
              return v44;
            }
            std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
              (char *)this + 144,
              v68,
              v71);
            ++v58;
            goto LABEL_66;
          }
          *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v72, v69);
          v55 = *(_OWORD *)&off_1803628A0;
          if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v55, v53) )
          {
            std::wstring::wstring(v71);
            v45 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v71);
            v46 = v45;
            if ( v45 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AE,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v45,
                v53[0]);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
              return v46;
            }
            *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v70);
            v47 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToOperation(v53, (char *)this + 132);
            v48 = v47;
            if ( v47 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AF,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v47,
                v53[0]);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
              return v48;
            }
            v49 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v50 = v49;
            if ( v49 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1B0,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
                (const char *)(unsigned int)v49,
                v53[0]);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
              return v50;
            }
            v54 = ++v16;
            goto LABEL_66;
          }
          if ( *((_BYTE *)v60 + 152) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)0x87C52407LL,
              v53[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
            return 2277843975LL;
          }
          v51 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v52 = v51;
          if ( v51 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1BB,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)(unsigned int)v51,
              v53[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
            return v52;
          }
        }
        else
        {
          std::wstring::wstring(v71);
          v34 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v71);
          v35 = v34;
          if ( v34 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x197,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)(unsigned int)v34,
              v53[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
            return v35;
          }
          *(_OWORD *)v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v71, v66);
          v36 = (_DWORD *)((char *)this + 128);
          v37 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToRegistryType(v53, (char *)this + 128);
          v38 = v37;
          if ( v37 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x198,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)(unsigned int)v37,
              v53[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
            return v38;
          }
          if ( *v36 > 4u && *v36 != 11 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x19B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)0x87C5243FLL,
              v53[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
            return 2277844031LL;
          }
          v39 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v40 = v39;
          if ( v39 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x19D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
              (const char *)(unsigned int)v39,
              v53[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
            return v40;
          }
          ++v57;
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v71);
          v16 = v54;
        }
      }
      else
      {
        v30 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 96);
        v31 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18F,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
            (const char *)(unsigned int)v30,
            v53[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
          return v31;
        }
        v32 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v33 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x190,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
            (const char *)(unsigned int)v32,
            v53[0]);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
          return v33;
        }
        ++v15;
      }
    }
    else
    {
      v26 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 64);
      v27 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x188,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
          (const char *)(unsigned int)v26,
          v53[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
        return v27;
      }
      v28 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v29 = v28;
      if ( v28 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x189,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
          (const char *)(unsigned int)v28,
          v53[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
        return v29;
      }
      ++v14;
    }
LABEL_71:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v72);
  }
  if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
  {
    if ( v56 == 1 && v14 == 1 && v15 == 1 && v57 == 1 && v58 && v16 == 1 )
    {
      (*(void (__fastcall **)(Microsoft::Diagnostics::RegistryKeyFilterDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
      std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v59);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C6,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
        (const char *)0x87C52402LL,
        v53[0]);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
      return 2277843970LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C0,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\registrykeyfilter.cpp",
      (const char *)Element,
      v53[0]);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
    return v18;
  }
}

```

## disassembly

```asm
0x180252500  push    rbx
0x180252502  push    rsi
0x180252503  push    rdi
0x180252504  push    r12
0x180252506  push    r13
0x180252508  push    r14
0x18025250a  push    r15
0x18025250c  sub     rsp, 180h
0x180252513  mov     rax, cs:__security_cookie
0x18025251a  xor     rax, rsp
0x18025251d  mov     [rsp+1B8h+var_48], rax
0x180252525  mov     r9, r8; char *
0x180252528  mov     [rsp+1B8h+var_150], r8
0x18025252d  mov     rbx, rdx
0x180252530  mov     r14, rcx
0x180252533  movzx   ecx, word ptr [rcx+10h]
0x180252537  test    ecx, ecx
0x180252539  jz      short loc_1802525A6
0x18025253b  sub     ecx, 1
0x18025253e  jz      short loc_18025259E
0x180252540  sub     ecx, 1
0x180252543  jz      short loc_180252596
0x180252545  sub     ecx, 1
0x180252548  jz      short loc_18025258E
0x18025254a  sub     ecx, 1
0x18025254d  jz      short loc_180252586
0x18025254f  sub     ecx, 1
0x180252552  jz      short loc_18025257E
0x180252554  cmp     ecx, 1
0x180252557  jz      short loc_180252573
0x180252559  mov     rcx, [rsp+1B8h]; this
0x180252561  lea     r8, aOnecoreBaseTel_14; "onecore\\base\\telemetry\\utc\\service"...
0x180252568  mov     edx, 3B5h; void *
0x18025256d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180252573  mov     esi, 0Bh
0x180252578  movzx   r8d, si
0x18025257c  jmp     short loc_1802525B1
0x18025257e  mov     r8d, 0Ah
0x180252584  jmp     short loc_1802525AC
0x180252586  mov     r8d, 9
0x18025258c  jmp     short loc_1802525AC
0x18025258e  mov     r8d, 8
0x180252594  jmp     short loc_1802525AC
0x180252596  mov     r8d, 7
0x18025259c  jmp     short loc_1802525AC
0x18025259e  mov     r8d, 6
0x1802525a4  jmp     short loc_1802525AC
0x1802525a6  mov     r8d, 5
0x1802525ac  mov     esi, 0Bh
0x1802525b1  lea     rdx, [r9+70h]
0x1802525b5  lea     rcx, [rsp+1B8h+var_158]
0x1802525ba  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1802525bf  lea     rcx, [r14+18h]
0x1802525c3  lea     rdx, [rsp+1B8h+var_198]
0x1802525c8  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802525cd  movups  xmm0, xmmword ptr [rax]
0x1802525d0  movdqu  [rsp+1B8h+var_178], xmm0
0x1802525d6  lea     rdx, [rsp+1B8h+var_178]
0x1802525db  lea     rcx, [rsp+1B8h+var_158]
0x1802525e0  call    ?AddDetailToCurrentFrame@ParsingDomain@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(std::wstring_view)
0x1802525e5  lea     rcx, [rsp+1B8h+var_68]; void *
0x1802525ed  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1802525f2  nop
0x1802525f3  movups  xmm0, xmmword ptr cs:off_180362980; "treatnotexistsassuccess"
0x1802525fa  movdqu  xmmword ptr [rsp+1B8h+var_198], xmm0; int
0x180252600  lea     rax, Src
0x180252607  mov     qword ptr [rsp+1B8h+var_178], rax
0x18025260c  mov     qword ptr [rsp+1B8h+var_178+8], 0
0x180252615  lea     r9, [rsp+1B8h+var_68]
0x18025261d  lea     r8, [rsp+1B8h+var_198]
0x180252622  lea     rdx, [rsp+1B8h+var_178]
0x180252627  mov     rcx, rbx
0x18025262a  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18025262f  cmp     eax, 1
0x180252632  jz      short loc_18025265B
0x180252634  lea     rdx, [rsp+1B8h+var_178]
0x180252639  lea     rcx, [rsp+1B8h+var_68]
0x180252641  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180252646  movups  xmm0, xmmword ptr [rax]
0x180252649  movdqu  xmmword ptr [rsp+1B8h+var_198], xmm0
0x18025264f  lea     rcx, [rsp+1B8h+var_198]
0x180252654  call    ?ToBool@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToBool(std::wstring_view)
0x180252659  jmp     short loc_18025265D
0x18025265b  xor     al, al
0x18025265d  xor     ecx, ecx
0x18025265f  mov     [rsp+1B8h+var_168], ecx
0x180252663  xor     r12d, r12d
0x180252666  xor     r13d, r13d
0x180252669  mov     [rsp+1B8h+var_164], ecx
0x18025266d  mov     [rsp+1B8h+var_160], ecx
0x180252671  xor     r15d, r15d
0x180252674  mov     [rsp+1B8h+var_188], r15d
0x180252679  mov     [r14+0A0h], al
0x180252680  mov     rcx, rbx; this
0x180252683  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x180252688  mov     edi, eax
0x18025268a  test    eax, eax
0x18025268c  jnz     loc_180252FAE
0x180252692  lea     rcx, [rsp+1B8h+var_88]; void *
0x18025269a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18025269f  nop
0x1802526a0  lea     rdx, [rsp+1B8h+var_88]
0x1802526a8  mov     rcx, rbx
0x1802526ab  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x1802526b0  lea     rdx, [rsp+1B8h+var_148]
0x1802526b5  lea     rcx, [rsp+1B8h+var_88]
0x1802526bd  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802526c2  movups  xmm0, xmmword ptr [rax]
0x1802526c5  movdqu  xmmword ptr [rsp+1B8h+var_198], xmm0; int
0x1802526cb  movups  xmm1, xmmword ptr cs:off_180362990; "hive"
0x1802526d2  movdqu  [rsp+1B8h+var_178], xmm1
0x1802526d8  lea     rdx, [rsp+1B8h+var_198]
0x1802526dd  lea     rcx, [rsp+1B8h+var_178]
0x1802526e2  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802526e7  test    eax, eax
0x1802526e9  jnz     loc_180252845
0x1802526ef  lea     rcx, [rsp+1B8h+var_A8]; void *
0x1802526f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1802526fc  nop
0x1802526fd  lea     rdx, [rsp+1B8h+var_A8]
0x180252705  mov     rcx, rbx
0x180252708  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18025270d  mov     edi, eax
0x18025270f  test    eax, eax
0x180252711  jns     short loc_180252760
0x180252713  mov     rcx, [rsp+1B8h]; this
0x18025271b  mov     r9d, eax; char *
0x18025271e  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x180252725  mov     edx, 180h; void *
0x18025272a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025272f  nop
0x180252730  lea     rcx, [rsp+1B8h+var_A8]; this
0x180252738  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18025273d  nop
0x18025273e  lea     rcx, [rsp+1B8h+var_88]; this
0x180252746  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18025274b  nop
0x18025274c  lea     rcx, [rsp+1B8h+var_68]; this
0x180252754  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180252759  mov     eax, edi
0x18025275b  jmp     loc_18025307B
0x180252760  lea     rdx, [rsp+1B8h+var_138]
0x180252768  lea     rcx, [rsp+1B8h+var_A8]
0x180252770  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180252775  movups  xmm0, xmmword ptr [rax]
0x180252778  movdqu  xmmword ptr [rsp+1B8h+var_198], xmm0; int
0x18025277e  lea     r8, [r14+38h]
0x180252782  xor     edx, edx
0x180252784  lea     rcx, [rsp+1B8h+var_198]
0x180252789  call    ?GetHiveFromString@Xml@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@_NAEAPEAUHKEY__@@@Z; Microsoft::Diagnostics::Utils::Xml::GetHiveFromString(std::wstring_view,bool,HKEY__ * &)
0x18025278e  mov     edi, eax
0x180252790  test    eax, eax
0x180252792  jns     short loc_1802527E1
0x180252794  mov     rcx, [rsp+1B8h]; this
0x18025279c  mov     r9d, eax; char *
0x18025279f  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x1802527a6  mov     edx, 181h; void *
0x1802527ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802527b0  nop
0x1802527b1  lea     rcx, [rsp+1B8h+var_A8]; this
0x1802527b9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802527be  nop
0x1802527bf  lea     rcx, [rsp+1B8h+var_88]; this
0x1802527c7  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802527cc  nop
0x1802527cd  lea     rcx, [rsp+1B8h+var_68]; this
0x1802527d5  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802527da  mov     eax, edi
0x1802527dc  jmp     loc_18025307B
0x1802527e1  mov     rcx, rbx; this
0x1802527e4  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1802527e9  mov     edi, eax
0x1802527eb  test    eax, eax
0x1802527ed  jns     short loc_18025283C
0x1802527ef  mov     rcx, [rsp+1B8h]; this
0x1802527f7  mov     r9d, eax; char *
0x1802527fa  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x180252801  mov     edx, 182h; void *
0x180252806  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025280b  nop
0x18025280c  lea     rcx, [rsp+1B8h+var_A8]; this
0x180252814  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180252819  nop
0x18025281a  lea     rcx, [rsp+1B8h+var_88]; this
0x180252822  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180252827  nop
0x180252828  lea     rcx, [rsp+1B8h+var_68]; this
0x180252830  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180252835  mov     eax, edi
0x180252837  jmp     loc_18025307B
0x18025283c  inc     [rsp+1B8h+var_168]
0x180252840  jmp     loc_180252EEB
0x180252845  lea     rdx, [rsp+1B8h+var_128]
0x18025284d  lea     rcx, [rsp+1B8h+var_88]
0x180252855  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18025285a  movups  xmm0, xmmword ptr [rax]
0x18025285d  movdqu  xmmword ptr [rsp+1B8h+var_198], xmm0; int
0x180252863  movups  xmm1, xmmword ptr cs:off_180362960; "keyname"
0x18025286a  movdqu  [rsp+1B8h+var_178], xmm1
0x180252870  lea     rdx, [rsp+1B8h+var_198]
0x180252875  lea     rcx, [rsp+1B8h+var_178]
0x18025287a  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18025287f  test    eax, eax
0x180252881  jnz     loc_18025292D
0x180252887  lea     rdx, [r14+40h]
0x18025288b  mov     rcx, rbx
0x18025288e  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x180252893  mov     edi, eax
0x180252895  test    eax, eax
0x180252897  jns     short loc_1802528D8
0x180252899  mov     rcx, [rsp+1B8h]; this
0x1802528a1  mov     r9d, eax; char *
0x1802528a4  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x1802528ab  mov     edx, 188h; void *
0x1802528b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802528b5  nop
0x1802528b6  lea     rcx, [rsp+1B8h+var_88]; this
0x1802528be  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802528c3  nop
0x1802528c4  lea     rcx, [rsp+1B8h+var_68]; this
0x1802528cc  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802528d1  mov     eax, edi
0x1802528d3  jmp     loc_18025307B
0x1802528d8  mov     rcx, rbx; this
0x1802528db  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1802528e0  mov     edi, eax
0x1802528e2  test    eax, eax
0x1802528e4  jns     short loc_180252925
0x1802528e6  mov     rcx, [rsp+1B8h]; this
0x1802528ee  mov     r9d, eax; char *
0x1802528f1  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x1802528f8  mov     edx, 189h; void *
0x1802528fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180252902  nop
0x180252903  lea     rcx, [rsp+1B8h+var_88]; this
0x18025290b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180252910  nop
0x180252911  lea     rcx, [rsp+1B8h+var_68]; this
0x180252919  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18025291e  mov     eax, edi
0x180252920  jmp     loc_18025307B
0x180252925  inc     r12d
0x180252928  jmp     loc_180252F9C
0x18025292d  lea     rdx, [rsp+1B8h+var_118]
0x180252935  lea     rcx, [rsp+1B8h+var_88]
0x18025293d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180252942  movups  xmm0, xmmword ptr [rax]
0x180252945  movdqu  xmmword ptr [rsp+1B8h+var_198], xmm0; int
0x18025294b  movups  xmm1, xmmword ptr cs:off_180362970; "valuename"
0x180252952  movdqu  [rsp+1B8h+var_178], xmm1
0x180252958  lea     rdx, [rsp+1B8h+var_198]
0x18025295d  lea     rcx, [rsp+1B8h+var_178]
0x180252962  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x180252967  test    eax, eax
0x180252969  jnz     loc_180252A15
0x18025296f  lea     rdx, [r14+60h]
0x180252973  mov     rcx, rbx
0x180252976  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18025297b  mov     edi, eax
0x18025297d  test    eax, eax
0x18025297f  jns     short loc_1802529C0
0x180252981  mov     rcx, [rsp+1B8h]; this
0x180252989  mov     r9d, eax; char *
0x18025298c  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x180252993  mov     edx, 18Fh; void *
0x180252998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025299d  nop
0x18025299e  lea     rcx, [rsp+1B8h+var_88]; this
0x1802529a6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802529ab  nop
0x1802529ac  lea     rcx, [rsp+1B8h+var_68]; this
0x1802529b4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802529b9  mov     eax, edi
0x1802529bb  jmp     loc_18025307B
0x1802529c0  mov     rcx, rbx; this
0x1802529c3  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1802529c8  mov     edi, eax
0x1802529ca  test    eax, eax
0x1802529cc  jns     short loc_180252A0D
0x1802529ce  mov     rcx, [rsp+1B8h]; this
0x1802529d6  mov     r9d, eax; char *
0x1802529d9  lea     r8, aOnecoreBaseTel_10; "onecore\\base\\telemetry\\utc\\service"...
0x1802529e0  mov     edx, 190h; void *
0x1802529e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802529ea  nop
0x1802529eb  lea     rcx, [rsp+1B8h+var_88]; this
0x1802529f3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802529f8  nop
0x1802529f9  lea     rcx, [rsp+1B8h+var_68]; this
0x180252a01  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180252a06  mov     eax, edi
0x180252a08  jmp     loc_18025307B
0x180252a0d  inc     r13d
0x180252a10  jmp     loc_180252F9C
0x180252a15  lea     rdx, [rsp+1B8h+var_108]
0x180252a1d  lea     rcx, [rsp+1B8h+var_88]
0x180252a25  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180252a2a  movups  xmm0, xmmword ptr [rax]
0x180252a2d  movdqu  xmmword ptr [rsp+1B8h+var_198], xmm0; int
0x180252a33  movups  xmm1, xmmword ptr cs:off_180362950; "valuetype"
  ... truncated ...
```
