# Microsoft::Diagnostics::DualPropertyFilterDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x18024e5f0`
- end: `0x18024f521`
- name: `?ParseFromXml@DualPropertyFilterDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `3889`
- prototype: `int(Microsoft::Diagnostics::DualPropertyFilterDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x1800498f0`
- `0x180053a84`
- `0x180090930`
- `0x1800a0d08`
- `0x1800bef30`
- `0x1800de308`
- `0x18012de40`
- `0x1802384e0`
- `0x18023b62c`
- `0x1802472d8`
- `0x18024ce44`
- `0x18024cf64`
- `0x18024e5f0`
- `0x18024f528`
- `0x1802e6744`
- `0x1802e6bec`
- `0x1802e6d88`
- `0x180346010`

## string_xrefs

- `0x18024e64c`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x18024e8d1`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024ea7d`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024eb28`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024ec1e`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024ec9c`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024ed54`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024eddb`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024ee6e`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024eecc`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024ef84`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f01c`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f08a`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f0db`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f12d`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f178`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f22a`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f29e`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f2eb`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f34f`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f392`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f3d6`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f440`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f4a3`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`
- `0x18024f4d6`: `onecore\base\telemetry\utc\service\scenarios\filters\dualpropertyfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::DualPropertyFilterDef::ParseFromXml(
        Microsoft::Diagnostics::DualPropertyFilterDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3,
        const char *a4)
{
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  __int64 v13; // r8
  unsigned int v14; // esi
  int v15; // r12d
  int v16; // r15d
  unsigned int Element; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  unsigned int v20; // edi
  int InnerText; // eax
  unsigned int v22; // edi
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  unsigned int v27; // edi
  int v28; // eax
  unsigned int v29; // edi
  int v30; // eax
  unsigned int v31; // edi
  char *v32; // rcx
  int v33; // eax
  unsigned int v34; // edi
  int v35; // eax
  unsigned int v36; // edi
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
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties *v49; // rcx
  int v50; // eax
  unsigned int v51; // edi
  int v52; // eax
  unsigned int v53; // edi
  int v54; // eax
  unsigned int v55; // edi
  int v56; // eax
  unsigned int v57; // edi
  int v58; // [rsp+20h] [rbp-208h]
  __int128 v59; // [rsp+30h] [rbp-1F8h] BYREF
  __int128 v60; // [rsp+40h] [rbp-1E8h] BYREF
  int v61; // [rsp+50h] [rbp-1D8h]
  char v62; // [rsp+54h] [rbp-1D4h] BYREF
  _BYTE v63[3]; // [rsp+55h] [rbp-1D3h] BYREF
  int v64; // [rsp+58h] [rbp-1D0h]
  int v65; // [rsp+5Ch] [rbp-1CCh]
  _QWORD v66[2]; // [rsp+60h] [rbp-1C8h] BYREF
  __int128 v67; // [rsp+70h] [rbp-1B8h] BYREF
  _BYTE v68[16]; // [rsp+80h] [rbp-1A8h] BYREF
  _BYTE v69[16]; // [rsp+90h] [rbp-198h] BYREF
  _BYTE v70[16]; // [rsp+A0h] [rbp-188h] BYREF
  _BYTE v71[16]; // [rsp+B0h] [rbp-178h] BYREF
  _BYTE v72[16]; // [rsp+C0h] [rbp-168h] BYREF
  _BYTE v73[16]; // [rsp+D0h] [rbp-158h] BYREF
  _BYTE v74[16]; // [rsp+E0h] [rbp-148h] BYREF
  _BYTE v75[16]; // [rsp+F0h] [rbp-138h] BYREF
  _BYTE v76[16]; // [rsp+100h] [rbp-128h] BYREF
  _BYTE v77[16]; // [rsp+110h] [rbp-118h] BYREF
  _BYTE v78[16]; // [rsp+120h] [rbp-108h] BYREF
  _BYTE v79[16]; // [rsp+130h] [rbp-F8h] BYREF
  _BYTE v80[16]; // [rsp+140h] [rbp-E8h] BYREF
  _BYTE v81[16]; // [rsp+150h] [rbp-D8h] BYREF
  _BYTE v82[16]; // [rsp+160h] [rbp-C8h] BYREF
  _BYTE v83[16]; // [rsp+170h] [rbp-B8h] BYREF
  _BYTE v84[32]; // [rsp+180h] [rbp-A8h] BYREF
  _BYTE v85[32]; // [rsp+1A0h] [rbp-88h] BYREF
  _BYTE v86[32]; // [rsp+1C0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v7 = *((unsigned __int16 *)this + 8);
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
            v12 = v11 - 1;
            if ( v12 )
            {
              if ( v12 != 1 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x3B5,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                  a4);
              v13 = 11;
            }
            else
            {
              v13 = 10;
            }
          }
          else
          {
            v13 = 9;
          }
        }
        else
        {
          v13 = 8;
        }
      }
      else
      {
        v13 = 7;
      }
    }
    else
    {
      v13 = 6;
    }
  }
  else
  {
    v13 = 5;
  }
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(v66, (char *)a3 + 112, v13);
  v67 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 24, &v59);
  Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(v66, &v67);
  std::wstring::wstring(v85);
  v14 = 0;
  v65 = 0;
  v61 = 0;
  v15 = 0;
  v16 = 0;
  LOBYTE(v58) = 0;
  LOBYTE(v64) = 0;
  while ( 1 )
  {
LABEL_17:
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v18 = Element;
    if ( Element )
    {
      if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
      {
        if ( v65 == 2 && v61 == 1 )
        {
          if ( (v15 & 0xFFFFFFFD) != 0 || (v16 & 0xFFFFFFFD) != 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x33C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)0x87C52402LL,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return 2277843970LL;
          }
          else if ( *((_BYTE *)this + 57) && *((_BYTE *)this + 201) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x341,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)0x87C52402LL,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return 2277843970LL;
          }
          else
          {
            (*(void (__fastcall **)(Microsoft::Diagnostics::DualPropertyFilterDef *, _QWORD))(*(_QWORD *)this + 16LL))(
              this,
              0);
            std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v66[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return 0;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x336,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
            (const char *)0x87C52402LL,
            v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
          return 2277843970LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x331,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
          (const char *)Element,
          v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
        return v18;
      }
    }
    Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v85);
    v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, v68);
    v59 = *(_OWORD *)&off_180362710;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v59, &v60) )
      break;
    std::wstring::wstring(v86);
    v59 = *(_OWORD *)&off_180362720;
    *(_QWORD *)&v67 = &Src;
    *((_QWORD *)&v67 + 1) = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v67, &v59, v86) != 1 )
    {
      if ( v14 )
      {
        if ( v14 == 1 )
        {
          v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v86, v70);
          v60 = *(_OWORD *)&off_1803626E0;
          if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
            *((_BYTE *)this + 201) = 1;
        }
      }
      else
      {
        v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v86, v69);
        v60 = *(_OWORD *)&off_1803626E0;
        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
          *((_BYTE *)this + 57) = 1;
      }
    }
    while ( 1 )
    {
      v19 = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v20 = v19;
      if ( v19 )
        break;
      Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v85);
      v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, v71);
      v60 = *(_OWORD *)&off_1803626F0;
      if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
      {
        std::wstring::wstring(v84);
        InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v84);
        v22 = InnerText;
        if ( InnerText < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2A5,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
            (const char *)(unsigned int)InnerText,
            v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
          return v22;
        }
        if ( v14 )
        {
          if ( v14 == 1 )
          {
            std::wstring::operator=((char *)this + 216, v84);
            v59 = *(_OWORD *)&Microsoft::Diagnostics::ITriggerFilterDef::k_reservedMetadataTriggerName;
            v60 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 216, v74);
            if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
            {
              v59 = *(_OWORD *)&Microsoft::Diagnostics::ITriggerFilterDef::k_reservedDataModelTriggerName;
              v60 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 216, v75);
              v24 = Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59);
              v25 = (unsigned __int8)v64;
              if ( !v24 )
                v25 = 1;
              v64 = v25;
            }
            else
            {
              *((_BYTE *)this + 200) = 1;
            }
          }
        }
        else
        {
          std::wstring::operator=((char *)this + 72, v84);
          v59 = *(_OWORD *)&Microsoft::Diagnostics::ITriggerFilterDef::k_reservedMetadataTriggerName;
          v60 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 72, v72);
          if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
          {
            v59 = *(_OWORD *)&Microsoft::Diagnostics::ITriggerFilterDef::k_reservedDataModelTriggerName;
            v60 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 72, v73);
            if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
              LOBYTE(v58) = 1;
          }
          else
          {
            *((_BYTE *)this + 56) = 1;
          }
        }
        v26 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v27 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C4,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
            (const char *)(unsigned int)v26,
            v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
          return v27;
        }
        goto LABEL_85;
      }
      v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, v76);
      v60 = *(_OWORD *)&off_180362700;
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
      {
        v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, v77);
        v60 = *(_OWORD *)&off_1803626C0;
        if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
        {
          std::wstring::wstring(v84);
          v30 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v84);
          v31 = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2D8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v30,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return v31;
          }
          if ( !v14 )
          {
            v32 = (char *)this + 104;
            goto LABEL_60;
          }
          if ( v14 == 1 )
          {
            v32 = (char *)this + 248;
LABEL_60:
            std::wstring::operator=(v32, v84);
          }
          v33 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v34 = v33;
          if ( v33 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E3,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v33,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return v34;
          }
          goto LABEL_85;
        }
        v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, v78);
        v60 = *(_OWORD *)&off_1803626D0;
        if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
        {
          std::wstring::wstring(v84);
          v35 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v84);
          v36 = v35;
          if ( v35 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2E8,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v35,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return v36;
          }
          if ( v14 )
          {
            if ( v14 == 1 )
            {
              v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v80);
              v39 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToMathOperation(&v59, (char *)this + 204);
              v40 = v39;
              if ( v39 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2F1,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
                  (const char *)(unsigned int)v39,
                  v58);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
                return v40;
              }
              ++v16;
            }
          }
          else
          {
            v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v79);
            v37 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToMathOperation(&v59, (char *)this + 60);
            v38 = v37;
            if ( v37 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2EC,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
                (const char *)(unsigned int)v37,
                v58);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
              return v38;
            }
            ++v15;
          }
          v41 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v42 = v41;
          if ( v41 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2F5,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v41,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return v42;
          }
          goto LABEL_85;
        }
        v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, v81);
        v60 = *(_OWORD *)&off_180362660;
        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
        {
          if ( *((_BYTE *)a3 + 152) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x30D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)0x87C52407LL,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return 2277843975LL;
          }
          v47 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v48 = v47;
          if ( v47 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x310,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v47,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return v48;
          }
        }
        else
        {
          std::wstring::wstring(v84);
          v43 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v84);
          v44 = v43;
          if ( v43 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2FA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v43,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return v44;
          }
          if ( v14 )
          {
            if ( v14 == 1 )
            {
              std::wstring::operator=((char *)this + 280, v84);
              ++v16;
            }
          }
          else
          {
            std::wstring::operator=((char *)this + 136, v84);
            ++v15;
          }
          v45 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v46 = v45;
          if ( v45 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x307,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
              (const char *)(unsigned int)v45,
              v58);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
            return v46;
          }
LABEL_85:
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
        }
      }
      else
      {
        v28 = Microsoft::Diagnostics::DualPropertyFilterDef::ParsePropertySelector(this, a2, a3, v14);
        v29 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2C8,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
            (const char *)(unsigned int)v28,
            v58);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
          return v29;
        }
        if ( v14 )
        {
          if ( v14 == 1 && (_BYTE)v64 )
            *((_BYTE *)this + 212) = *(_BYTE *)Microsoft::Diagnostics::ITriggerFilterDef::ParseTriggerPropertyName(
                                                 v63,
                                                 (char *)this + 312);
        }
        else if ( (_BYTE)v58 )
        {
          *((_BYTE *)this + 68) = *(_BYTE *)Microsoft::Diagnostics::ITriggerFilterDef::ParseTriggerPropertyName(
                                              &v62,
                                              (char *)this + 168);
        }
        ++v65;
      }
    }
    if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147024270 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x314,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
        (const char *)v19,
        v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
      return v20;
    }
    if ( ++v14 > 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x319,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
        (const char *)0x87C52402LL,
        v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
      return 2277843970LL;
    }
    v49 = (Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v86;
LABEL_104:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(v49);
  }
  v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v85, v82);
  v60 = *(_OWORD *)&off_180362670;
  if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v60, &v59) )
  {
    if ( *((_BYTE *)a3 + 152) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x329,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
        (const char *)0x87C52407LL,
        v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
      return 2277843975LL;
    }
    else
    {
      v56 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v57 = v56;
      if ( v56 >= 0 )
        goto LABEL_17;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32C,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
        (const char *)(unsigned int)v56,
        v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
      return v57;
    }
  }
  else
  {
    std::wstring::wstring(v84);
    v50 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v84);
    v51 = v50;
    if ( v50 >= 0 )
    {
      v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v84, v83);
      v52 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToOperation(&v59, (char *)this + 192);
      v53 = v52;
      if ( v52 >= 0 )
      {
        v54 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v55 = v54;
        if ( v54 >= 0 )
        {
          ++v61;
          v49 = (Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84;
          goto LABEL_104;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x321,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
          (const char *)(unsigned int)v54,
          v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
        return v55;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x320,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
          (const char *)(unsigned int)v52,
          v58);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
        return v53;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x31F,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\dualpropertyfilter.cpp",
        (const char *)(unsigned int)v50,
        v58);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v84);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v85);
      return v51;
    }
  }
}

```

## disassembly

```asm
0x18024e5f0  push    rbx
0x18024e5f2  push    rsi
0x18024e5f3  push    rdi
0x18024e5f4  push    r12
0x18024e5f6  push    r13
0x18024e5f8  push    r14
0x18024e5fa  push    r15
0x18024e5fc  sub     rsp, 1F0h
0x18024e603  mov     rax, cs:__security_cookie
0x18024e60a  xor     rax, rsp
0x18024e60d  mov     [rsp+228h+var_48], rax
0x18024e615  mov     r13, r8
0x18024e618  mov     r14, rdx
0x18024e61b  mov     rbx, rcx
0x18024e61e  movzx   ecx, word ptr [rcx+10h]
0x18024e622  test    ecx, ecx
0x18024e624  jz      short loc_18024E68E
0x18024e626  sub     ecx, 1
0x18024e629  jz      short loc_18024E686
0x18024e62b  sub     ecx, 1
0x18024e62e  jz      short loc_18024E67E
0x18024e630  sub     ecx, 1
0x18024e633  jz      short loc_18024E676
0x18024e635  sub     ecx, 1
0x18024e638  jz      short loc_18024E66E
0x18024e63a  sub     ecx, 1
0x18024e63d  jz      short loc_18024E666
0x18024e63f  cmp     ecx, 1
0x18024e642  jz      short loc_18024E65E
0x18024e644  mov     rcx, [rsp+228h]; this
0x18024e64c  lea     r8, aOnecoreBaseTel_14; "onecore\\base\\telemetry\\utc\\service"...
0x18024e653  mov     edx, 3B5h; void *
0x18024e658  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18024e65e  mov     r8d, 0Bh
0x18024e664  jmp     short loc_18024E694
0x18024e666  mov     r8d, 0Ah
0x18024e66c  jmp     short loc_18024E694
0x18024e66e  mov     r8d, 9
0x18024e674  jmp     short loc_18024E694
0x18024e676  mov     r8d, 8
0x18024e67c  jmp     short loc_18024E694
0x18024e67e  mov     r8d, 7
0x18024e684  jmp     short loc_18024E694
0x18024e686  mov     r8d, 6
0x18024e68c  jmp     short loc_18024E694
0x18024e68e  mov     r8d, 5
0x18024e694  lea     rdx, [r13+70h]
0x18024e698  lea     rcx, [rsp+228h+var_1C8]
0x18024e69d  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x18024e6a2  lea     rcx, [rbx+18h]
0x18024e6a6  lea     rdx, [rsp+228h+var_1F8]
0x18024e6ab  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e6b0  movups  xmm0, xmmword ptr [rax]
0x18024e6b3  movdqu  [rsp+228h+var_1B8], xmm0
0x18024e6b9  lea     rdx, [rsp+228h+var_1B8]
0x18024e6be  lea     rcx, [rsp+228h+var_1C8]
0x18024e6c3  call    ?AddDetailToCurrentFrame@ParsingDomain@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(std::wstring_view)
0x18024e6c8  lea     rcx, [rsp+228h+var_88]; void *
0x18024e6d0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18024e6d5  nop
0x18024e6d6  xor     esi, esi
0x18024e6d8  xor     eax, eax
0x18024e6da  mov     [rsp+228h+var_1CC], eax
0x18024e6de  xor     ecx, ecx
0x18024e6e0  mov     [rsp+228h+var_1D8], ecx
0x18024e6e4  xor     r12d, r12d
0x18024e6e7  xor     r15d, r15d
0x18024e6ea  mov     byte ptr [rsp+228h+var_208], al; int
0x18024e6ee  mov     byte ptr [rsp+228h+var_1D0], al
0x18024e6f2  mov     rcx, r14; this
0x18024e6f5  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x18024e6fa  mov     edi, eax
0x18024e6fc  test    eax, eax
0x18024e6fe  jnz     loc_18024F3B8
0x18024e704  lea     rdx, [rsp+228h+var_88]
0x18024e70c  mov     rcx, r14
0x18024e70f  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18024e714  lea     rdx, [rsp+228h+var_1A8]
0x18024e71c  lea     rcx, [rsp+228h+var_88]
0x18024e724  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e729  movups  xmm0, xmmword ptr [rax]
0x18024e72c  movdqu  [rsp+228h+var_1E8], xmm0
0x18024e732  movups  xmm1, xmmword ptr cs:off_180362710; "triggercriterion"
0x18024e739  movdqu  [rsp+228h+var_1F8], xmm1
0x18024e73f  lea     rdx, [rsp+228h+var_1E8]
0x18024e744  lea     rcx, [rsp+228h+var_1F8]
0x18024e749  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024e74e  test    eax, eax
0x18024e750  jnz     loc_18024F1B9
0x18024e756  lea     rcx, [rsp+228h+var_68]; void *
0x18024e75e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18024e763  nop
0x18024e764  movups  xmm0, xmmword ptr cs:off_180362720; "strict"
0x18024e76b  movdqu  [rsp+228h+var_1F8], xmm0
0x18024e771  lea     rax, Src
0x18024e778  mov     qword ptr [rsp+228h+var_1B8], rax
0x18024e77d  mov     qword ptr [rsp+228h+var_1B8+8], 0
0x18024e786  lea     r9, [rsp+228h+var_68]
0x18024e78e  lea     r8, [rsp+228h+var_1F8]
0x18024e793  lea     rdx, [rsp+228h+var_1B8]
0x18024e798  mov     rcx, r14
0x18024e79b  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18024e7a0  mov     edi, 1
0x18024e7a5  cmp     eax, edi
0x18024e7a7  jz      loc_18024E83E
0x18024e7ad  test    esi, esi
0x18024e7af  jnz     short loc_18024E7F5
0x18024e7b1  lea     rdx, [rsp+228h+var_198]
0x18024e7b9  lea     rcx, [rsp+228h+var_68]
0x18024e7c1  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e7c6  movups  xmm0, xmmword ptr [rax]
0x18024e7c9  movdqu  [rsp+228h+var_1F8], xmm0
0x18024e7cf  movups  xmm1, xmmword ptr cs:off_1803626E0; "false"
0x18024e7d6  movdqu  [rsp+228h+var_1E8], xmm1
0x18024e7dc  lea     rdx, [rsp+228h+var_1F8]
0x18024e7e1  lea     rcx, [rsp+228h+var_1E8]
0x18024e7e6  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024e7eb  test    eax, eax
0x18024e7ed  jz      short loc_18024E83E
0x18024e7ef  mov     [rbx+39h], dil
0x18024e7f3  jmp     short loc_18024E83E
0x18024e7f5  cmp     esi, edi
0x18024e7f7  jnz     short loc_18024E83E
0x18024e7f9  lea     rdx, [rsp+228h+var_188]
0x18024e801  lea     rcx, [rsp+228h+var_68]
0x18024e809  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e80e  movups  xmm0, xmmword ptr [rax]
0x18024e811  movdqu  [rsp+228h+var_1F8], xmm0
0x18024e817  movups  xmm1, xmmword ptr cs:off_1803626E0; "false"
0x18024e81e  movdqu  [rsp+228h+var_1E8], xmm1
0x18024e824  lea     rdx, [rsp+228h+var_1F8]
0x18024e829  lea     rcx, [rsp+228h+var_1E8]
0x18024e82e  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024e833  test    eax, eax
0x18024e835  jz      short loc_18024E83E
0x18024e837  mov     [rbx+0C9h], dil
0x18024e83e  mov     rcx, r14; this
0x18024e841  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x18024e846  mov     edi, eax
0x18024e848  test    eax, eax
0x18024e84a  jnz     loc_18024F10F
0x18024e850  lea     rdx, [rsp+228h+var_88]
0x18024e858  mov     rcx, r14
0x18024e85b  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18024e860  lea     rdx, [rsp+228h+var_178]
0x18024e868  lea     rcx, [rsp+228h+var_88]
0x18024e870  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e875  movups  xmm0, xmmword ptr [rax]
0x18024e878  movdqu  [rsp+228h+var_1F8], xmm0
0x18024e87e  movups  xmm1, xmmword ptr cs:off_1803626F0; "triggername"
0x18024e885  movdqu  [rsp+228h+var_1E8], xmm1
0x18024e88b  lea     rdx, [rsp+228h+var_1F8]
0x18024e890  lea     rcx, [rsp+228h+var_1E8]
0x18024e895  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024e89a  test    eax, eax
0x18024e89c  jnz     loc_18024EAC4
0x18024e8a2  lea     rcx, [rsp+228h+var_A8]; void *
0x18024e8aa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18024e8af  nop
0x18024e8b0  lea     rdx, [rsp+228h+var_A8]
0x18024e8b8  mov     rcx, r14
0x18024e8bb  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18024e8c0  mov     edi, eax
0x18024e8c2  test    eax, eax
0x18024e8c4  jns     short loc_18024E913
0x18024e8c6  mov     rcx, [rsp+228h]; this
0x18024e8ce  mov     r9d, eax; char *
0x18024e8d1  lea     r8, aOnecoreBaseTel_166; "onecore\\base\\telemetry\\utc\\service"...
0x18024e8d8  mov     edx, 2A5h; void *
0x18024e8dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18024e8e2  nop
0x18024e8e3  lea     rcx, [rsp+228h+var_A8]; this
0x18024e8eb  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18024e8f0  nop
0x18024e8f1  lea     rcx, [rsp+228h+var_68]; this
0x18024e8f9  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18024e8fe  nop
0x18024e8ff  lea     rcx, [rsp+228h+var_88]; this
0x18024e907  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18024e90c  mov     eax, edi
0x18024e90e  jmp     loc_18024F4FD
0x18024e913  test    esi, esi
0x18024e915  jnz     loc_18024E9B8
0x18024e91b  lea     rdi, [rbx+48h]
0x18024e91f  lea     rdx, [rsp+228h+var_A8]
0x18024e927  mov     rcx, rdi
0x18024e92a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18024e92f  movups  xmm0, xmmword ptr cs:?k_reservedMetadataTriggerName@ITriggerFilterDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::ITriggerFilterDef::k_reservedMetadataTriggerName
0x18024e936  movdqu  [rsp+228h+var_1F8], xmm0
0x18024e93c  lea     rdx, [rsp+228h+var_168]
0x18024e944  mov     rcx, rdi
0x18024e947  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e94c  movups  xmm0, xmmword ptr [rax]
0x18024e94f  movdqu  [rsp+228h+var_1E8], xmm0
0x18024e955  lea     rdx, [rsp+228h+var_1F8]
0x18024e95a  lea     rcx, [rsp+228h+var_1E8]
0x18024e95f  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024e964  test    eax, eax
0x18024e966  jnz     short loc_18024E971
0x18024e968  mov     byte ptr [rbx+38h], 1
0x18024e96c  jmp     loc_18024EA64
0x18024e971  movups  xmm0, xmmword ptr cs:?k_reservedDataModelTriggerName@ITriggerFilterDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::ITriggerFilterDef::k_reservedDataModelTriggerName
0x18024e978  movdqu  [rsp+228h+var_1F8], xmm0
0x18024e97e  lea     rdx, [rsp+228h+var_158]
0x18024e986  mov     rcx, rdi
0x18024e989  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e98e  movups  xmm0, xmmword ptr [rax]
0x18024e991  movdqu  [rsp+228h+var_1E8], xmm0
0x18024e997  lea     rdx, [rsp+228h+var_1F8]
0x18024e99c  lea     rcx, [rsp+228h+var_1E8]
0x18024e9a1  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024e9a6  test    eax, eax
0x18024e9a8  jnz     loc_18024EA64
0x18024e9ae  mov     byte ptr [rsp+228h+var_208], 1
0x18024e9b3  jmp     loc_18024EA64
0x18024e9b8  cmp     esi, 1
0x18024e9bb  jnz     loc_18024EA64
0x18024e9c1  lea     rdi, [rbx+0D8h]
0x18024e9c8  lea     rdx, [rsp+228h+var_A8]
0x18024e9d0  mov     rcx, rdi
0x18024e9d3  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18024e9d8  movups  xmm0, xmmword ptr cs:?k_reservedMetadataTriggerName@ITriggerFilterDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::ITriggerFilterDef::k_reservedMetadataTriggerName
0x18024e9df  movdqu  [rsp+228h+var_1F8], xmm0
0x18024e9e5  lea     rdx, [rsp+228h+var_148]
0x18024e9ed  mov     rcx, rdi
0x18024e9f0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024e9f5  movups  xmm0, xmmword ptr [rax]
0x18024e9f8  movdqu  [rsp+228h+var_1E8], xmm0
0x18024e9fe  lea     rdx, [rsp+228h+var_1F8]
0x18024ea03  lea     rcx, [rsp+228h+var_1E8]
0x18024ea08  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024ea0d  test    eax, eax
0x18024ea0f  jnz     short loc_18024EA1A
0x18024ea11  mov     [rbx+0C8h], sil
0x18024ea18  jmp     short loc_18024EA64
0x18024ea1a  movups  xmm0, xmmword ptr cs:?k_reservedDataModelTriggerName@ITriggerFilterDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::ITriggerFilterDef::k_reservedDataModelTriggerName
0x18024ea21  movdqu  [rsp+228h+var_1F8], xmm0
0x18024ea27  lea     rdx, [rsp+228h+var_138]
0x18024ea2f  mov     rcx, rdi
0x18024ea32  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024ea37  movups  xmm0, xmmword ptr [rax]
0x18024ea3a  movdqu  [rsp+228h+var_1E8], xmm0
0x18024ea40  lea     rdx, [rsp+228h+var_1F8]
0x18024ea45  lea     rcx, [rsp+228h+var_1E8]
0x18024ea4a  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024ea4f  mov     ecx, [rsp+228h+var_1D0]
0x18024ea53  movzx   ecx, cl
0x18024ea56  test    eax, eax
0x18024ea58  mov     eax, 1
0x18024ea5d  cmovz   ecx, eax
0x18024ea60  mov     [rsp+228h+var_1D0], ecx
0x18024ea64  mov     rcx, r14; this
0x18024ea67  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18024ea6c  mov     edi, eax
0x18024ea6e  test    eax, eax
0x18024ea70  jns     short loc_18024EABF
0x18024ea72  mov     rcx, [rsp+228h]; this
0x18024ea7a  mov     r9d, eax; char *
0x18024ea7d  lea     r8, aOnecoreBaseTel_166; "onecore\\base\\telemetry\\utc\\service"...
0x18024ea84  mov     edx, 2C4h; void *
0x18024ea89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18024ea8e  nop
0x18024ea8f  lea     rcx, [rsp+228h+var_A8]; this
0x18024ea97  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18024ea9c  nop
0x18024ea9d  lea     rcx, [rsp+228h+var_68]; this
0x18024eaa5  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18024eaaa  nop
0x18024eaab  lea     rcx, [rsp+228h+var_88]; this
0x18024eab3  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18024eab8  mov     eax, edi
0x18024eaba  jmp     loc_18024F4FD
0x18024eabf  jmp     loc_18024F05E
0x18024eac4  lea     rdx, [rsp+228h+var_128]
0x18024eacc  lea     rcx, [rsp+228h+var_88]
0x18024ead4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18024ead9  movups  xmm0, xmmword ptr [rax]
0x18024eadc  movdqu  [rsp+228h+var_1F8], xmm0
0x18024eae2  movups  xmm1, xmmword ptr cs:off_180362700; "propertyselector"
0x18024eae9  movdqu  [rsp+228h+var_1E8], xmm1
0x18024eaef  lea     rdx, [rsp+228h+var_1F8]
0x18024eaf4  lea     rcx, [rsp+228h+var_1E8]
0x18024eaf9  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18024eafe  test    eax, eax
0x18024eb00  jnz     loc_18024EBAD
0x18024eb06  mov     r9d, esi; unsigned int
0x18024eb09  mov     r8, r13; struct Microsoft::Diagnostics::ScenarioParsingState *
0x18024eb0c  mov     rdx, r14; struct Microsoft::Diagnostics::XMLFacade *
0x18024eb0f  mov     rcx, rbx; this
0x18024eb12  call    ?ParsePropertySelector@DualPropertyFilterDef@Diagnostics@Microsoft@@AEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@K@Z; Microsoft::Diagnostics::DualPropertyFilterDef::ParsePropertySelector(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &,ulong)
0x18024eb17  mov     edi, eax
0x18024eb19  test    eax, eax
0x18024eb1b  jns     short loc_18024EB5C
0x18024eb1d  mov     rcx, [rsp+228h]; this
0x18024eb25  mov     r9d, eax; char *
0x18024eb28  lea     r8, aOnecoreBaseTel_166; "onecore\\base\\telemetry\\utc\\service"...
0x18024eb2f  mov     edx, 2C8h; void *
0x18024eb34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18024eb39  nop
0x18024eb3a  lea     rcx, [rsp+228h+var_68]; this
  ... truncated ...
```
