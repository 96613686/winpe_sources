# Microsoft::Diagnostics::SinglePropertyFilterDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x180255080`
- end: `0x180255a07`
- name: `?ParseFromXml@SinglePropertyFilterDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `2439`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::SinglePropertyFilterDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a78c`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x180053a84`
- `0x1800a0d08`
- `0x1800bef30`
- `0x1800de308`
- `0x18012de40`
- `0x1802384e0`
- `0x18023b62c`
- `0x18024ce44`
- `0x18024cf64`
- `0x1802544dc`
- `0x180255080`
- `0x180255a10`
- `0x1802e6744`
- `0x1802e6bec`
- `0x1802e6d88`
- `0x180346010`

## string_xrefs

- `0x1802550e1`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1802551fb`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x18025523a`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802552c4`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180255351`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180255394`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x18025542b`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x18025549c`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802554e9`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180255587`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802555c6`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180255665`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802556ce`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x18025577c`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802557ed`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x18025583a`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802558a1`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802558e0`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180255936`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x180255986`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`
- `0x1802559ca`: `onecore\base\telemetry\utc\service\scenarios\filters\singlepropertyfilter.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::SinglePropertyFilterDef::ParseFromXml(
        Microsoft::Diagnostics::SinglePropertyFilterDef *this,
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
  int v13; // r15d
  int v14; // r12d
  int v15; // r13d
  int v16; // r14d
  unsigned int Element; // eax
  unsigned int v18; // edi
  int v19; // eax
  unsigned int v20; // edi
  int v22; // eax
  unsigned int v23; // edi
  int v24; // eax
  unsigned int v25; // edi
  int v26; // eax
  unsigned int v27; // edi
  int v28; // eax
  unsigned int v29; // edi
  int InnerText; // eax
  unsigned int v31; // edi
  int v32; // eax
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  int v36; // eax
  unsigned int v37; // edi
  int v38; // eax
  unsigned int v39; // edi
  int v40; // eax
  unsigned int v41; // edi
  int v42; // eax
  unsigned int v43; // edi
  int v44; // eax
  unsigned int v45; // edi
  int v46; // eax
  unsigned int v47; // edi
  int v48; // eax
  unsigned int v49; // edi
  int v50; // eax
  unsigned int v51; // edi
  int v52; // [rsp+20h] [rbp-168h]
  __int128 v53; // [rsp+30h] [rbp-158h] BYREF
  __int128 v54; // [rsp+40h] [rbp-148h] BYREF
  struct Microsoft::Diagnostics::ScenarioParsingState *v55; // [rsp+50h] [rbp-138h]
  __int64 v56; // [rsp+58h] [rbp-130h] BYREF
  _BYTE v57[16]; // [rsp+60h] [rbp-128h] BYREF
  _BYTE v58[16]; // [rsp+70h] [rbp-118h] BYREF
  _BYTE v59[16]; // [rsp+80h] [rbp-108h] BYREF
  _BYTE v60[16]; // [rsp+90h] [rbp-F8h] BYREF
  _BYTE v61[16]; // [rsp+A0h] [rbp-E8h] BYREF
  _BYTE v62[16]; // [rsp+B0h] [rbp-D8h] BYREF
  _BYTE v63[16]; // [rsp+C0h] [rbp-C8h] BYREF
  _BYTE v64[16]; // [rsp+D0h] [rbp-B8h] BYREF
  _BYTE v65[16]; // [rsp+E0h] [rbp-A8h] BYREF
  _BYTE v66[16]; // [rsp+F0h] [rbp-98h] BYREF
  _BYTE v67[32]; // [rsp+100h] [rbp-88h] BYREF
  _BYTE v68[32]; // [rsp+120h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v55 = a3;
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
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v56, (char *)a3 + 112, v12);
  v54 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 24, &v53);
  Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(&v56, &v54);
  v13 = 0;
  v14 = 0;
  v52 = 0;
  v15 = 0;
  v16 = 0;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v18 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v67);
    Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v67);
    v54 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, v57);
    v53 = *(_OWORD *)&off_180362A30;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v53, &v54) )
    {
      v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, v58);
      v54 = *(_OWORD *)&off_180362A40;
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v54, &v53) )
      {
        v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, v59);
        v54 = *(_OWORD *)&off_180362A50;
        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v54, &v53) )
        {
          v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, v60);
          v54 = *(_OWORD *)&off_180362A60;
          if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v54, &v53) )
          {
            std::wstring::wstring(v68);
            InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v68);
            v31 = InnerText;
            if ( InnerText < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1E4,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)InnerText,
                v52);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
              return v31;
            }
            v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v68, v61);
            v32 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToMathOperation(&v53, (char *)this + 60);
            v33 = v32;
            if ( v32 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1E5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v32,
                v52);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
              return v33;
            }
            v34 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v35 = v34;
            if ( v34 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1E6,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v34,
                v52);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
              return v35;
            }
            ++v16;
LABEL_61:
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
            goto LABEL_66;
          }
          v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, v62);
          v54 = *(_OWORD *)&off_180362A00;
          if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v54, &v53) )
          {
            v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, v63);
            v54 = *(_OWORD *)&off_180362A10;
            if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v54, &v53) )
            {
              std::wstring::wstring(v68);
              v40 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v68);
              v41 = v40;
              if ( v40 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1F4,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v40,
                  v52);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
                return v41;
              }
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
                (char *)this + 200,
                v64,
                v68);
              v42 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
              v43 = v42;
              if ( v42 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1F8,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v42,
                  v52);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
                return v43;
              }
              ++v52;
              goto LABEL_61;
            }
            v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v67, v65);
            v54 = *(_OWORD *)&off_180362A20;
            if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v54, &v53) )
            {
              std::wstring::wstring(v68);
              v44 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v68);
              v45 = v44;
              if ( v44 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1FF,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v44,
                  v52);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
                return v45;
              }
              v53 = *(_OWORD *)std::wstring::operator std::wstring_view(v68, v66);
              v46 = Microsoft::Diagnostics::Utils::Xml::ConvertStringToOperation(&v53, (char *)this + 68);
              v47 = v46;
              if ( v46 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x200,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v46,
                  v52);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
                return v47;
              }
              v48 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
              v49 = v48;
              if ( v48 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x201,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                  (const char *)(unsigned int)v48,
                  v52);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v68);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
                return v49;
              }
              ++v15;
              goto LABEL_61;
            }
            if ( *((_BYTE *)v55 + 152) )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x209,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)0x87C52407LL,
                v52);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
              return 2277843975LL;
            }
            v50 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v51 = v50;
            if ( v50 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x20C,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v50,
                v52);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
              return v51;
            }
          }
          else
          {
            v36 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 144);
            v37 = v36;
            if ( v36 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1EC,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v36,
                v52);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
              return v37;
            }
            v38 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
            v39 = v38;
            if ( v38 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1ED,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
                (const char *)(unsigned int)v38,
                v52);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
              return v39;
            }
            ++v16;
          }
        }
        else
        {
          v26 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 112);
          v27 = v26;
          if ( v26 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DE,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
              (const char *)(unsigned int)v26,
              v52);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
            return v27;
          }
          v28 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
          v29 = v28;
          if ( v28 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1DF,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
              (const char *)(unsigned int)v28,
              v52);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
            return v29;
          }
        }
      }
      else
      {
        v24 = Microsoft::Diagnostics::SinglePropertyFilterDef::ParsePropertySelector(this, a2, v55);
        v25 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1D9,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
            (const char *)(unsigned int)v24,
            v52);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
          return v25;
        }
        ++v14;
      }
    }
    else
    {
      v19 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, (char *)this + 80);
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D3,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)(unsigned int)v19,
          v52);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
        return v20;
      }
      v22 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D4,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)(unsigned int)v22,
          v52);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
        return v23;
      }
      ++v13;
    }
LABEL_66:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v67);
  }
  if ( (int)(Element + 0x80000000) < 0 || Element == -2147024270 )
  {
    Microsoft::Diagnostics::SinglePropertyFilterDef::EstablishParseDynamicMembers(this);
    if ( v14 == 1 && v52 && v15 == 1 && v13 == 1 )
    {
      if ( (v16 & 0xFFFFFFFD) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x21B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
          (const char *)0x87C52402LL,
          v52);
        return 2277843970LL;
      }
      else
      {
        (*(void (__fastcall **)(Microsoft::Diagnostics::SinglePropertyFilterDef *, _QWORD))(*(_QWORD *)this + 16LL))(
          this,
          0);
        std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v56);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x216,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
        (const char *)0x87C52402LL,
        v52);
      return 2277843970LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\filters\\singlepropertyfilter.cpp",
      (const char *)Element,
      v52);
    return v18;
  }
}

```

## disassembly

```asm
0x180255080  push    rbx
0x180255082  push    rsi
0x180255083  push    rdi
0x180255084  push    r12
0x180255086  push    r13
0x180255088  push    r14
0x18025508a  push    r15
0x18025508c  sub     rsp, 150h
0x180255093  mov     rax, cs:__security_cookie
0x18025509a  xor     rax, rsp
0x18025509d  mov     [rsp+188h+var_48], rax
0x1802550a5  mov     r9, r8; char *
0x1802550a8  mov     [rsp+188h+var_138], r8
0x1802550ad  mov     rbx, rdx
0x1802550b0  mov     rsi, rcx
0x1802550b3  movzx   ecx, word ptr [rcx+10h]
0x1802550b7  test    ecx, ecx
0x1802550b9  jz      short loc_180255123
0x1802550bb  sub     ecx, 1
0x1802550be  jz      short loc_18025511B
0x1802550c0  sub     ecx, 1
0x1802550c3  jz      short loc_180255113
0x1802550c5  sub     ecx, 1
0x1802550c8  jz      short loc_18025510B
0x1802550ca  sub     ecx, 1
0x1802550cd  jz      short loc_180255103
0x1802550cf  sub     ecx, 1
0x1802550d2  jz      short loc_1802550FB
0x1802550d4  cmp     ecx, 1
0x1802550d7  jz      short loc_1802550F3
0x1802550d9  mov     rcx, [rsp+188h]; this
0x1802550e1  lea     r8, aOnecoreBaseTel_14; "onecore\\base\\telemetry\\utc\\service"...
0x1802550e8  mov     edx, 3B5h; void *
0x1802550ed  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1802550f3  mov     r8d, 0Bh
0x1802550f9  jmp     short loc_180255129
0x1802550fb  mov     r8d, 0Ah
0x180255101  jmp     short loc_180255129
0x180255103  mov     r8d, 9
0x180255109  jmp     short loc_180255129
0x18025510b  mov     r8d, 8
0x180255111  jmp     short loc_180255129
0x180255113  mov     r8d, 7
0x180255119  jmp     short loc_180255129
0x18025511b  mov     r8d, 6
0x180255121  jmp     short loc_180255129
0x180255123  mov     r8d, 5
0x180255129  lea     rdx, [r9+70h]
0x18025512d  lea     rcx, [rsp+188h+var_130]
0x180255132  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x180255137  lea     rcx, [rsi+18h]
0x18025513b  lea     rdx, [rsp+188h+var_158]
0x180255140  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180255145  movups  xmm0, xmmword ptr [rax]
0x180255148  movdqu  [rsp+188h+var_148], xmm0
0x18025514e  lea     rdx, [rsp+188h+var_148]
0x180255153  lea     rcx, [rsp+188h+var_130]
0x180255158  call    ?AddDetailToCurrentFrame@ParsingDomain@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(std::wstring_view)
0x18025515d  xor     r15d, r15d
0x180255160  xor     r12d, r12d
0x180255163  xor     eax, eax
0x180255165  mov     [rsp+188h+var_168], eax; int
0x180255169  xor     r13d, r13d
0x18025516c  xor     r14d, r14d
0x18025516f  mov     rcx, rbx; this
0x180255172  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x180255177  mov     edi, eax
0x180255179  test    eax, eax
0x18025517b  jnz     loc_180255918
0x180255181  lea     rcx, [rsp+188h+var_88]; void *
0x180255189  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18025518e  nop
0x18025518f  lea     rdx, [rsp+188h+var_88]
0x180255197  mov     rcx, rbx
0x18025519a  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18025519f  lea     rdx, [rsp+188h+var_128]
0x1802551a4  lea     rcx, [rsp+188h+var_88]
0x1802551ac  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802551b1  movups  xmm0, xmmword ptr [rax]
0x1802551b4  movdqu  [rsp+188h+var_148], xmm0
0x1802551ba  movups  xmm1, xmmword ptr cs:off_180362A30; "triggername"
0x1802551c1  movdqu  [rsp+188h+var_158], xmm1
0x1802551c7  lea     rdx, [rsp+188h+var_148]
0x1802551cc  lea     rcx, [rsp+188h+var_158]
0x1802551d1  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802551d6  test    eax, eax
0x1802551d8  jnz     loc_180255268
0x1802551de  lea     rdx, [rsi+50h]
0x1802551e2  mov     rcx, rbx
0x1802551e5  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x1802551ea  mov     edi, eax
0x1802551ec  test    eax, eax
0x1802551ee  jns     short loc_180255221
0x1802551f0  mov     rcx, [rsp+188h]; this
0x1802551f8  mov     r9d, eax; char *
0x1802551fb  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x180255202  mov     edx, 1D3h; void *
0x180255207  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025520c  nop
0x18025520d  lea     rcx, [rsp+188h+var_88]; this
0x180255215  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18025521a  mov     eax, edi
0x18025521c  jmp     loc_1802559E3
0x180255221  mov     rcx, rbx; this
0x180255224  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x180255229  mov     edi, eax
0x18025522b  test    eax, eax
0x18025522d  jns     short loc_180255260
0x18025522f  mov     rcx, [rsp+188h]; this
0x180255237  mov     r9d, eax; char *
0x18025523a  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x180255241  mov     edx, 1D4h; void *
0x180255246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025524b  nop
0x18025524c  lea     rcx, [rsp+188h+var_88]; this
0x180255254  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180255259  mov     eax, edi
0x18025525b  jmp     loc_1802559E3
0x180255260  inc     r15d
0x180255263  jmp     loc_180255906
0x180255268  lea     rdx, [rsp+188h+var_118]
0x18025526d  lea     rcx, [rsp+188h+var_88]
0x180255275  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18025527a  movups  xmm0, xmmword ptr [rax]
0x18025527d  movdqu  [rsp+188h+var_158], xmm0
0x180255283  movups  xmm1, xmmword ptr cs:off_180362A40; "propertyselector"
0x18025528a  movdqu  [rsp+188h+var_148], xmm1
0x180255290  lea     rdx, [rsp+188h+var_158]
0x180255295  lea     rcx, [rsp+188h+var_148]
0x18025529a  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18025529f  test    eax, eax
0x1802552a1  jnz     short loc_1802552F2
0x1802552a3  mov     r8, [rsp+188h+var_138]; struct Microsoft::Diagnostics::ScenarioParsingState *
0x1802552a8  mov     rdx, rbx; struct Microsoft::Diagnostics::XMLFacade *
0x1802552ab  mov     rcx, rsi; this
0x1802552ae  call    ?ParsePropertySelector@SinglePropertyFilterDef@Diagnostics@Microsoft@@AEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z; Microsoft::Diagnostics::SinglePropertyFilterDef::ParsePropertySelector(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)
0x1802552b3  mov     edi, eax
0x1802552b5  test    eax, eax
0x1802552b7  jns     short loc_1802552EA
0x1802552b9  mov     rcx, [rsp+188h]; this
0x1802552c1  mov     r9d, eax; char *
0x1802552c4  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x1802552cb  mov     edx, 1D9h; void *
0x1802552d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802552d5  nop
0x1802552d6  lea     rcx, [rsp+188h+var_88]; this
0x1802552de  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802552e3  mov     eax, edi
0x1802552e5  jmp     loc_1802559E3
0x1802552ea  inc     r12d
0x1802552ed  jmp     loc_180255906
0x1802552f2  lea     rdx, [rsp+188h+var_108]
0x1802552fa  lea     rcx, [rsp+188h+var_88]
0x180255302  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180255307  movups  xmm0, xmmword ptr [rax]
0x18025530a  movdqu  [rsp+188h+var_158], xmm0
0x180255310  movups  xmm1, xmmword ptr cs:off_180362A50; "bitmask"
0x180255317  movdqu  [rsp+188h+var_148], xmm1
0x18025531d  lea     rdx, [rsp+188h+var_158]
0x180255322  lea     rcx, [rsp+188h+var_148]
0x180255327  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18025532c  test    eax, eax
0x18025532e  jnz     loc_1802553BA
0x180255334  lea     rdx, [rsi+70h]
0x180255338  mov     rcx, rbx
0x18025533b  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x180255340  mov     edi, eax
0x180255342  test    eax, eax
0x180255344  jns     short loc_180255377
0x180255346  mov     rcx, [rsp+188h]; this
0x18025534e  mov     r9d, eax; char *
0x180255351  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x180255358  mov     edx, 1DEh; void *
0x18025535d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180255362  nop
0x180255363  lea     rcx, [rsp+188h+var_88]; this
0x18025536b  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180255370  mov     eax, edi
0x180255372  jmp     loc_1802559E3
0x180255377  mov     rcx, rbx; this
0x18025537a  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18025537f  mov     edi, eax
0x180255381  test    eax, eax
0x180255383  jns     loc_180255906
0x180255389  mov     rcx, [rsp+188h]; this
0x180255391  mov     r9d, eax; char *
0x180255394  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x18025539b  mov     edx, 1DFh; void *
0x1802553a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802553a5  nop
0x1802553a6  lea     rcx, [rsp+188h+var_88]; this
0x1802553ae  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802553b3  mov     eax, edi
0x1802553b5  jmp     loc_1802559E3
0x1802553ba  lea     rdx, [rsp+188h+var_F8]
0x1802553c2  lea     rcx, [rsp+188h+var_88]
0x1802553ca  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802553cf  movups  xmm0, xmmword ptr [rax]
0x1802553d2  movdqu  [rsp+188h+var_158], xmm0
0x1802553d8  movups  xmm1, xmmword ptr cs:off_180362A60; "mathoperation"
0x1802553df  movdqu  [rsp+188h+var_148], xmm1
0x1802553e5  lea     rdx, [rsp+188h+var_158]
0x1802553ea  lea     rcx, [rsp+188h+var_148]
0x1802553ef  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1802553f4  test    eax, eax
0x1802553f6  jnz     loc_180255525
0x1802553fc  lea     rcx, [rsp+188h+var_68]; void *
0x180255404  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180255409  nop
0x18025540a  lea     rdx, [rsp+188h+var_68]
0x180255412  mov     rcx, rbx
0x180255415  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18025541a  mov     edi, eax
0x18025541c  test    eax, eax
0x18025541e  jns     short loc_18025545F
0x180255420  mov     rcx, [rsp+188h]; this
0x180255428  mov     r9d, eax; char *
0x18025542b  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x180255432  mov     edx, 1E4h; void *
0x180255437  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18025543c  nop
0x18025543d  lea     rcx, [rsp+188h+var_68]; this
0x180255445  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18025544a  nop
0x18025544b  lea     rcx, [rsp+188h+var_88]; this
0x180255453  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180255458  mov     eax, edi
0x18025545a  jmp     loc_1802559E3
0x18025545f  lea     rdx, [rsp+188h+var_E8]
0x180255467  lea     rcx, [rsp+188h+var_68]
0x18025546f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180255474  movups  xmm0, xmmword ptr [rax]
0x180255477  movdqu  [rsp+188h+var_158], xmm0
0x18025547d  lea     rdx, [rsi+3Ch]
0x180255481  lea     rcx, [rsp+188h+var_158]
0x180255486  call    ?ConvertStringToMathOperation@Xml@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAU?$optional@VMathOperator@Filters@Diagnostics@Microsoft@@@better_enums@@@Z; Microsoft::Diagnostics::Utils::Xml::ConvertStringToMathOperation(std::wstring_view,better_enums::optional<Microsoft::Diagnostics::Filters::MathOperator> &)
0x18025548b  mov     edi, eax
0x18025548d  test    eax, eax
0x18025548f  jns     short loc_1802554D0
0x180255491  mov     rcx, [rsp+188h]; this
0x180255499  mov     r9d, eax; char *
0x18025549c  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x1802554a3  mov     edx, 1E5h; void *
0x1802554a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802554ad  nop
0x1802554ae  lea     rcx, [rsp+188h+var_68]; this
0x1802554b6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802554bb  nop
0x1802554bc  lea     rcx, [rsp+188h+var_88]; this
0x1802554c4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802554c9  mov     eax, edi
0x1802554cb  jmp     loc_1802559E3
0x1802554d0  mov     rcx, rbx; this
0x1802554d3  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x1802554d8  mov     edi, eax
0x1802554da  test    eax, eax
0x1802554dc  jns     short loc_18025551D
0x1802554de  mov     rcx, [rsp+188h]; this
0x1802554e6  mov     r9d, eax; char *
0x1802554e9  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x1802554f0  mov     edx, 1E6h; void *
0x1802554f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802554fa  nop
0x1802554fb  lea     rcx, [rsp+188h+var_68]; this
0x180255503  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180255508  nop
0x180255509  lea     rcx, [rsp+188h+var_88]; this
0x180255511  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x180255516  mov     eax, edi
0x180255518  jmp     loc_1802559E3
0x18025551d  inc     r14d
0x180255520  jmp     loc_180255871
0x180255525  lea     rdx, [rsp+188h+var_D8]
0x18025552d  lea     rcx, [rsp+188h+var_88]
0x180255535  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18025553a  movups  xmm0, xmmword ptr [rax]
0x18025553d  movdqu  [rsp+188h+var_158], xmm0
0x180255543  movups  xmm1, xmmword ptr cs:off_180362A00; "constant"
0x18025554a  movdqu  [rsp+188h+var_148], xmm1
0x180255550  lea     rdx, [rsp+188h+var_158]
0x180255555  lea     rcx, [rsp+188h+var_148]
0x18025555a  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18025555f  test    eax, eax
0x180255561  jnz     loc_1802555F4
0x180255567  lea     rdx, [rsi+90h]
0x18025556e  mov     rcx, rbx
0x180255571  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x180255576  mov     edi, eax
0x180255578  test    eax, eax
0x18025557a  jns     short loc_1802555AD
0x18025557c  mov     rcx, [rsp+188h]; this
0x180255584  mov     r9d, eax; char *
0x180255587  lea     r8, aOnecoreBaseTel_255; "onecore\\base\\telemetry\\utc\\service"...
0x18025558e  mov     edx, 1ECh; void *
0x180255593  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180255598  nop
0x180255599  lea     rcx, [rsp+188h+var_88]; this
0x1802555a1  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1802555a6  mov     eax, edi
0x1802555a8  jmp     loc_1802559E3
  ... truncated ...
```
