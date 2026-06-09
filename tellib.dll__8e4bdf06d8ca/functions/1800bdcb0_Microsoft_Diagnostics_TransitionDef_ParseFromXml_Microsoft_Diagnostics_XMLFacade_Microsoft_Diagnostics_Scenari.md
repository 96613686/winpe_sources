# Microsoft::Diagnostics::TransitionDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x1800bdcb0`
- end: `0x1800bef29`
- name: `?ParseFromXml@TransitionDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `4729`
- prototype: `int(Microsoft::Diagnostics::TransitionDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x1800326cc`
- `0x1800340c0`
- `0x18004f774`
- `0x180053a84`
- `0x18007b808`
- `0x18007d034`
- `0x180090930`
- `0x1800a0d08`
- `0x1800bdcb0`
- `0x1800bef30`
- `0x1800bef80`
- `0x1800de308`
- `0x18012de40`
- `0x1801e38fc`
- `0x1801ffb84`
- `0x1802384e0`
- `0x180238bbc`
- `0x18023a834`
- `0x18023b62c`
- `0x18023bf90`
- `0x1802e6744`
- `0x1802e6bec`
- `0x1802e6d88`
- `0x1802e725c`
- `0x180346010`

## string_xrefs

- `0x1800bdd64`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bdf96`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be03e`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be0b4`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be0fe`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be217`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be2ae`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be2f8`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be421`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be486`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be51e`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be7cf`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be96d`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be9ed`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800beab4`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bebe3`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bec5e`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bed1f`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bed7a`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bedd5`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bee47`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800bee92`: `onecore\base\telemetry\utc\service\scenarios\base\transition.cpp`
- `0x1800be502`: `onecore\base\telemetry\utc\service\triggers\timetriggerdef.cpp`
- `0x1800bdebb`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1800be5b2`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1800be8d8`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x1800beb9b`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::TransitionDef::ParseFromXml(
        Microsoft::Diagnostics::TransitionDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  struct Microsoft::Diagnostics::ScenarioParsingState *v3; // rsi
  _QWORD *v7; // rbx
  _QWORD *v8; // r15
  __int128 *v9; // r8
  int v10; // r15d
  __int64 v11; // r8
  const char *v12; // r9
  __int16 v13; // r15
  __int16 v14; // ax
  __int64 *v15; // rax
  __int64 v16; // r13
  std::_Ref_count_base *v17; // rbx
  int AttributeFromCurrentElement; // eax
  __int64 v19; // r8
  int v20; // eax
  unsigned int v21; // esi
  __int64 v22; // r8
  __int64 v23; // rsi
  _OWORD *v24; // rcx
  __int64 v25; // rdx
  char v26; // al
  __int64 v27; // r13
  __int64 v28; // r8
  const char *v29; // r9
  void *v30; // rcx
  __int64 v31; // r9
  void *v32; // rcx
  __int64 v33; // r9
  unsigned int Element; // eax
  unsigned int v35; // esi
  bool v36; // r15
  int InnerText; // eax
  __int64 v38; // rsi
  __int64 v39; // r12
  __int128 *v40; // r8
  __int64 (__fastcall ***v41)(_QWORD); // rcx
  int v42; // esi
  __int64 v43; // rax
  const char *v44; // r9
  __int16 v45; // cx
  __int64 v46; // rdx
  int v47; // eax
  int v48; // eax
  __int64 v49; // rsi
  __int64 v50; // r15
  __int128 *v51; // r8
  __int64 (__fastcall ***v52)(_QWORD); // rcx
  char v53; // si
  __int64 v54; // rax
  const char *v55; // r9
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59[4]; // [rsp+20h] [rbp-1B8h] BYREF
  std::_Ref_count_base *v60[2]; // [rsp+30h] [rbp-1A8h] BYREF
  char v61; // [rsp+40h] [rbp-198h]
  __int128 v62; // [rsp+50h] [rbp-188h] BYREF
  __int128 v63; // [rsp+60h] [rbp-178h] BYREF
  __int128 v64; // [rsp+70h] [rbp-168h] BYREF
  __int128 v65; // [rsp+80h] [rbp-158h] BYREF
  __int128 v66; // [rsp+90h] [rbp-148h] BYREF
  __int128 v67; // [rsp+A0h] [rbp-138h] BYREF
  _QWORD v68[2]; // [rsp+B0h] [rbp-128h] BYREF
  __int128 v69; // [rsp+C0h] [rbp-118h] BYREF
  char v70[16]; // [rsp+D0h] [rbp-108h] BYREF
  char v71[16]; // [rsp+E0h] [rbp-F8h] BYREF
  char v72[16]; // [rsp+F0h] [rbp-E8h] BYREF
  char v73[16]; // [rsp+100h] [rbp-D8h] BYREF
  char v74[16]; // [rsp+110h] [rbp-C8h] BYREF
  char v75[16]; // [rsp+120h] [rbp-B8h] BYREF
  _BYTE v76[32]; // [rsp+130h] [rbp-A8h] BYREF
  _BYTE v77[32]; // [rsp+150h] [rbp-88h] BYREF
  _BYTE v78[32]; // [rsp+170h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v3 = a3;
  *(_QWORD *)&v64 = a3;
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(v68, (char *)a3 + 112, 42);
  std::wstring::wstring(v76);
  v65 = 0;
  v63 = *(_OWORD *)&off_1803616D0;
  *(_QWORD *)&v62 = &Src;
  *((_QWORD *)&v62 + 1) = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v62, &v63, v76) == 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52423LL,
      v59[0]);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277844003LL;
  }
  v63 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
  Microsoft::Diagnostics::TransitionDef::SetTransitionName(this, &v63);
  v63 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
  Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(v68, &v63);
  v63 = *(_OWORD *)&off_1803616E0;
  *(_QWORD *)&v62 = &Src;
  *((_QWORD *)&v62 + 1) = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v62, &v63, v76) == 1 )
  {
    LOBYTE(v59[0]) = 1;
    v13 = 4;
    v17 = (std::_Ref_count_base *)*((_QWORD *)&v65 + 1);
    v16 = v65;
    goto LABEL_25;
  }
  v7 = (_QWORD *)*((_QWORD *)v3 + 34);
  v8 = (_QWORD *)*((_QWORD *)v3 + 35);
  while ( 1 )
  {
    if ( v7 == v8 )
    {
      v13 = 4;
      v17 = (std::_Ref_count_base *)*((_QWORD *)&v65 + 1);
      v16 = v65;
      goto LABEL_19;
    }
    std::wstring::operator std::wstring_view(v76, &v67);
    std::wstring::operator std::wstring_view(*v7 + 16LL, &v63);
    v62 = *v9;
    *(_OWORD *)v60 = v63;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v60, &v62) )
      break;
    v7 += 2;
  }
  v10 = *(unsigned __int8 *)(*v7 + 48LL);
  v11 = (**(__int64 (__fastcall ***)(_QWORD))*v7)(*v7);
  if ( !(_BYTE)v10 )
  {
    v14 = 2;
    goto LABEL_14;
  }
  if ( v10 == 1 )
  {
    v14 = 3;
LABEL_14:
    v13 = 4;
    goto LABEL_15;
  }
  if ( v10 != 2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
      v12);
  v13 = 4;
  v14 = 4;
LABEL_15:
  *((_WORD *)this + 28) = v14;
  *(_DWORD *)((char *)this + 58) = *(_DWORD *)((char *)v60 + 2);
  *((_WORD *)this + 31) = HIWORD(v60[0]);
  *((_QWORD *)this + 8) = v11;
  std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
    v60,
    v7);
  v16 = *v15;
  *v15 = v65;
  *(_QWORD *)&v65 = v16;
  v17 = (std::_Ref_count_base *)v15[1];
  v15[1] = *((_QWORD *)&v65 + 1);
  *((_QWORD *)&v65 + 1) = v17;
  if ( v60[1] )
    std::_Ref_count_base::_Decref(v60[1]);
LABEL_19:
  if ( !v16 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52424LL,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277844004LL;
  }
  LOBYTE(v59[0]) = 0;
LABEL_25:
  *(_OWORD *)v60 = *(_OWORD *)&off_1803616A0;
  *(_QWORD *)&v62 = &Src;
  *((_QWORD *)&v62 + 1) = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v62, v60, v76) == 1 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52425LL,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277844005LL;
  }
  *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
  if ( (int)Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(v60, (char *)this + 120) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C5241FLL,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277843999LL;
  }
  if ( *((_BYTE *)this + 120) == 0xFA )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52426LL,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277844006LL;
  }
  *(_OWORD *)v60 = *(_OWORD *)&off_1803616B0;
  *(_QWORD *)&v62 = &Src;
  *((_QWORD *)&v62 + 1) = 0;
  AttributeFromCurrentElement = Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v62, v60, v76);
  v19 = 0;
  if ( !AttributeFromCurrentElement )
  {
    *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
    *((_BYTE *)this + 152) = Microsoft::Diagnostics::Utils::String::ToBool(v60);
  }
  *(_OWORD *)v60 = *(_OWORD *)&off_1803616C0;
  *(_QWORD *)&v62 = &Src;
  *((_QWORD *)&v62 + 1) = v19;
  if ( !(unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v62, v60, v76) )
  {
    *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
    v20 = Microsoft::Diagnostics::TransitionDef::ParseSelectFieldsAttribute(this, v60);
    v21 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x264,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)(unsigned int)v20,
        v59[0]);
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
      return v21;
    }
    v3 = (struct Microsoft::Diagnostics::ScenarioParsingState *)v64;
  }
  *(_OWORD *)v60 = *(_OWORD *)&off_180361680;
  *(_QWORD *)&v62 = &Src;
  *((_QWORD *)&v62 + 1) = 0;
  if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v62, v60, v76) )
    goto LABEL_64;
  if ( !*((_WORD *)this + 28) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x270,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52427LL,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277844007LL;
  }
  if ( *(_BYTE *)(v16 + 48) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C52428LL,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277844008LL;
  }
  *(_OWORD *)v60 = *(_OWORD *)&off_180361690;
  v63 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
  if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v63, v60) )
    goto LABEL_63;
  *(_OWORD *)v60 = *(_OWORD *)&off_180361660;
  v63 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
  if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v63, v60) )
  {
    *(_OWORD *)v60 = *(_OWORD *)&off_180361670;
    v63 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, &v67);
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v63, v60) )
    {
      *((_BYTE *)this + 153) = 2;
      goto LABEL_64;
    }
    if ( *((_BYTE *)v3 + 152) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
        (const char *)0x87C5244DLL,
        v59[0]);
      if ( v17 )
        std::_Ref_count_base::_Decref(v17);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
      return 2277844045LL;
    }
LABEL_63:
    *((_BYTE *)this + 153) = 0;
    goto LABEL_64;
  }
  *((_BYTE *)this + 153) = 1;
LABEL_64:
  if ( v16 )
  {
    if ( *(_BYTE *)(v16 + 48) == 1 )
    {
      if ( *((_BYTE *)this + 121) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29B,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C51030LL,
          v59[0]);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
        return 2277838896LL;
      }
      v23 = *(_QWORD *)std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                         v60,
                         &v65,
                         v22,
                         0);
      if ( v60[1] )
        std::_Ref_count_base::_Decref(v60[1]);
      if ( !(unsigned int)InlineIsEqualGUID((const struct _GUID *)(v23 + 80), &GUID_NULL) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\timetriggerdef.cpp",
          (const char *)0x87C51031LL,
          v59[0]);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C51031LL,
          v59[0]);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
        return 2277838897LL;
      }
      v25 = *((_QWORD *)this + 6);
      v26 = *((_BYTE *)this + 120);
      v27 = v64;
      *v24 = *(_OWORD *)v64;
      *(_BYTE *)(v23 + 57) = v26;
      *(_QWORD *)(v23 + 64) = v25;
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 16LL))(v23, 0);
      v61 = *(_BYTE *)(v23 + 48);
      v28 = (**(__int64 (__fastcall ***)(__int64))v23)(v23);
      if ( v61 )
      {
        if ( v61 == 1 )
        {
          v13 = 3;
        }
        else if ( v61 != 2 )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3A4,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v29);
        }
      }
      else
      {
        v13 = 2;
      }
      *((_WORD *)this + 28) = v13;
      *(_DWORD *)((char *)this + 58) = *(_DWORD *)((char *)v60 + 2);
      *((_WORD *)this + 31) = HIWORD(v60[0]);
      *((_QWORD *)this + 8) = v28;
    }
    else
    {
      v27 = v64;
    }
    if ( (*((_BYTE *)this + 153) & 0xFD) == 0 )
    {
      v30 = *(void **)(v27 + 232);
      if ( v30 == *(void **)(v27 + 240) )
      {
        std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const> const &>(
          v27 + 224,
          *(_QWORD *)(v27 + 232),
          &v65);
      }
      else
      {
        std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
          v30,
          &v65);
        *(_QWORD *)(v31 + 8) += 16LL;
      }
    }
    if ( (unsigned __int8)(*((_BYTE *)this + 153) - 1) <= 1u )
    {
      v32 = *(void **)(v27 + 256);
      if ( v32 == *(void **)(v27 + 264) )
      {
        std::vector<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const>>::_Emplace_reallocate<std::shared_ptr<Microsoft::Diagnostics::ITriggerDef const> const &>(
          v27 + 248,
          *(_QWORD *)(v27 + 256),
          &v65);
      }
      else
      {
        std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(
          v32,
          &v65);
        *(_QWORD *)(v33 + 8) += 16LL;
      }
    }
  }
  else
  {
    v27 = v64;
  }
  if ( Microsoft::Diagnostics::XMLFacade::IsEmptyElement(a2) )
    goto LABEL_175;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    v35 = Element;
    if ( Element )
      break;
    std::wstring::wstring(v77);
    Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v77);
    *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v77, v70);
    v66 = *(_OWORD *)&off_180361640;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v66, v60) )
    {
      v36 = 1;
      LOBYTE(v59[0]) = 1;
      v66 = *(_OWORD *)&off_180361650;
      *(_QWORD *)&v62 = &Src;
      *((_QWORD *)&v62 + 1) = 0;
      if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, &v62, &v66, v76) != 1 )
      {
        v66 = *(_OWORD *)&off_180361630;
        *(_OWORD *)v60 = *(_OWORD *)std::wstring::operator std::wstring_view(v76, v71);
        v36 = (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v60, &v66) != 0;
        LOBYTE(v59[0]) = v36;
      }
      std::wstring::wstring(v78);
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v78);
      v35 = InnerText;
      if ( InnerText >= 0 )
      {
        v38 = *(_QWORD *)(v27 + 200);
        v39 = *(_QWORD *)(v27 + 208);
        while ( 1 )
        {
          if ( v38 == v39 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2EA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52429LL,
              v59[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
            if ( v17 )
              std::_Ref_count_base::_Decref(v17);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
            return 2277844009LL;
          }
          std::wstring::operator std::wstring_view(v78, v72);
          std::wstring::operator std::wstring_view(*(_QWORD *)v38 + 24LL, &v69);
          v66 = *v40;
          *(_OWORD *)v60 = v69;
          if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v60, &v66) )
            break;
          v38 += 16;
        }
        v41 = *(__int64 (__fastcall ****)(_QWORD))v38;
        v42 = *(unsigned __int16 *)(*(_QWORD *)v38 + 16LL);
        v43 = (**v41)(v41);
        if ( v42 )
        {
          switch ( v42 )
          {
            case 1:
              v45 = 6;
              break;
            case 2:
              v45 = 7;
              break;
            case 3:
              v45 = 8;
              break;
            case 4:
              v45 = 9;
              break;
            case 5:
              v45 = 10;
              break;
            case 6:
              v45 = 11;
              break;
            default:
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x3B5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                v44);
          }
        }
        else
        {
          v45 = 5;
        }
        LOWORD(v64) = v45;
        *((_QWORD *)&v64 + 1) = v43;
        v46 = *((_QWORD *)this + 10);
        if ( v46 == *((_QWORD *)this + 11) )
        {
          std::vector<std::pair<bool,Microsoft::Diagnostics::ScenarioDbLookupPair>>::_Emplace_reallocate<bool &,Microsoft::Diagnostics::ScenarioDbLookupPair>(
            (char *)this + 72,
            v46,
            v59,
            &v64);
        }
        else
        {
          *(_BYTE *)v46 = v36;
          *(_OWORD *)(v46 + 8) = v64;
          *((_QWORD *)this + 10) += 24LL;
        }
        v47 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v35 = v47;
        if ( v47 >= 0 )
        {
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
          LOBYTE(v59[0]) = 0;
          goto LABEL_165;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2ED,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v47,
          v59[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2D7,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)InnerText,
          v59[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
      }
      goto LABEL_170;
    }
    v66 = *(_OWORD *)std::wstring::operator std::wstring_view(v77, v73);
    *(_OWORD *)v60 = *(_OWORD *)&off_180361620;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v60, &v66) )
    {
      std::wstring::wstring(v78);
      v48 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, v78);
      v35 = v48;
      if ( v48 >= 0 )
      {
        v49 = *(_QWORD *)(v27 + 392);
        v50 = *(_QWORD *)(v27 + 400);
        while ( 1 )
        {
          if ( v49 == v50 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x304,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
              (const char *)0x87C52607LL,
              v59[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
            if ( v17 )
              std::_Ref_count_base::_Decref(v17);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
            return 2277844487LL;
          }
          std::wstring::operator std::wstring_view(v78, v74);
          std::wstring::operator std::wstring_view(*(_QWORD *)v49 + 16LL, &v67);
          v66 = *v51;
          *(_OWORD *)v60 = v67;
          if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v60, &v66) )
            break;
          v49 += 16;
        }
        v52 = *(__int64 (__fastcall ****)(_QWORD))v49;
        v53 = *(_BYTE *)(*(_QWORD *)v49 + 80LL);
        v54 = (**v52)(v52);
        if ( v53 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3D8,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v55);
        LOWORD(v63) = 52;
        *((_QWORD *)&v63 + 1) = v54;
        std::vector<Microsoft::Diagnostics::ScenarioDbLookupPair>::_Emplace_one_at_back<Microsoft::Diagnostics::ScenarioDbLookupPair>(
          (char *)this + 96,
          &v63);
        v56 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
        v35 = v56;
        if ( v56 >= 0 )
        {
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
          goto LABEL_165;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x307,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v56,
          v59[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2F2,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v48,
          v59[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v78);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
      }
      goto LABEL_170;
    }
    v66 = *(_OWORD *)std::wstring::operator std::wstring_view(v77, v75);
    *(_OWORD *)v60 = *(_OWORD *)&off_180361610;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v60, &v66) )
    {
      if ( *(_BYTE *)(v27 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x315,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)0x87C52407LL,
          v59[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
        return 2277843975LL;
      }
      v58 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v35 = v58;
      if ( v58 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x318,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v58,
          v59[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
        goto LABEL_170;
      }
    }
    else if ( !Microsoft::Diagnostics::XMLFacade::IsEmptyElement(a2) )
    {
      v57 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v35 = v57;
      if ( v57 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
          (const char *)(unsigned int)v57,
          v59[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
        if ( v17 )
          std::_Ref_count_base::_Decref(v17);
LABEL_170:
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
        return v35;
      }
    }
LABEL_165:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v77);
  }
  if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)Element,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    goto LABEL_170;
  }
  if ( !LOBYTE(v59[0]) )
  {
LABEL_175:
    (*(void (__fastcall **)(Microsoft::Diagnostics::TransitionDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
    std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v68[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x325,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\transition.cpp",
      (const char *)0x87C5242ALL,
      v59[0]);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
    return 2277844010LL;
  }
}

```

## disassembly

```asm
0x1800bdcb0  push    rbx
0x1800bdcb2  push    rsi
0x1800bdcb3  push    rdi
0x1800bdcb4  push    r12
0x1800bdcb6  push    r13
0x1800bdcb8  push    r14
0x1800bdcba  push    r15
0x1800bdcbc  sub     rsp, 1A0h
0x1800bdcc3  mov     rax, cs:__security_cookie
0x1800bdcca  xor     rax, rsp
0x1800bdccd  mov     [rsp+1D8h+var_48], rax
0x1800bdcd5  mov     rsi, r8
0x1800bdcd8  mov     qword ptr [rsp+1D8h+var_168], r8
0x1800bdcdd  mov     r14, rdx
0x1800bdce0  mov     rdi, rcx
0x1800bdce3  mov     r8d, 2Ah ; '*'
0x1800bdce9  lea     rdx, [rsi+70h]
0x1800bdced  lea     rcx, [rsp+1D8h+var_128]
0x1800bdcf5  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x1800bdcfa  lea     rcx, [rsp+1D8h+var_A8]; void *
0x1800bdd02  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800bdd07  nop
0x1800bdd08  xorps   xmm0, xmm0
0x1800bdd0b  movdqu  [rsp+1D8h+var_158], xmm0
0x1800bdd14  movups  xmm0, xmmword ptr cs:off_1803616D0; "name"
0x1800bdd1b  movdqu  [rsp+1D8h+var_178], xmm0
0x1800bdd21  lea     rbx, Src
0x1800bdd28  mov     qword ptr [rsp+1D8h+var_188], rbx
0x1800bdd2d  xor     r12d, r12d
0x1800bdd30  mov     qword ptr [rsp+1D8h+var_188+8], r12
0x1800bdd35  lea     r9, [rsp+1D8h+var_A8]
0x1800bdd3d  lea     r8, [rsp+1D8h+var_178]
0x1800bdd42  lea     rdx, [rsp+1D8h+var_188]
0x1800bdd47  mov     rcx, r14
0x1800bdd4a  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800bdd4f  cmp     eax, 1
0x1800bdd52  jnz     short loc_1800BDD8A
0x1800bdd54  mov     rcx, [rsp+1D8h]; this
0x1800bdd5c  mov     ebx, 87C52423h
0x1800bdd61  mov     r9d, ebx; char *
0x1800bdd64  lea     r8, aOnecoreBaseTel_135; "onecore\\base\\telemetry\\utc\\service"...
0x1800bdd6b  mov     edx, 223h; void *
0x1800bdd70  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdd75  nop
0x1800bdd76  lea     rcx, [rsp+1D8h+var_A8]; this
0x1800bdd7e  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bdd83  mov     eax, ebx
0x1800bdd85  jmp     loc_1800BEF05
0x1800bdd8a  lea     rdx, [rsp+1D8h+var_138]
0x1800bdd92  lea     rcx, [rsp+1D8h+var_A8]
0x1800bdd9a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bdd9f  movups  xmm0, xmmword ptr [rax]
0x1800bdda2  movdqu  [rsp+1D8h+var_178], xmm0
0x1800bdda8  lea     rdx, [rsp+1D8h+var_178]
0x1800bddad  mov     rcx, rdi
0x1800bddb0  call    ?SetTransitionName@TransitionDef@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::TransitionDef::SetTransitionName(std::wstring_view)
0x1800bddb5  lea     rdx, [rsp+1D8h+var_138]
0x1800bddbd  lea     rcx, [rsp+1D8h+var_A8]
0x1800bddc5  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bddca  movups  xmm0, xmmword ptr [rax]
0x1800bddcd  movdqu  [rsp+1D8h+var_178], xmm0
0x1800bddd3  lea     rdx, [rsp+1D8h+var_178]
0x1800bddd8  lea     rcx, [rsp+1D8h+var_128]
0x1800bdde0  call    ?AddDetailToCurrentFrame@ParsingDomain@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(std::wstring_view)
0x1800bdde5  movups  xmm0, xmmword ptr cs:off_1803616E0; "event"
0x1800bddec  movdqu  [rsp+1D8h+var_178], xmm0
0x1800bddf2  mov     qword ptr [rsp+1D8h+var_188], rbx
0x1800bddf7  mov     qword ptr [rsp+1D8h+var_188+8], r12
0x1800bddfc  lea     r9, [rsp+1D8h+var_A8]
0x1800bde04  lea     r8, [rsp+1D8h+var_178]
0x1800bde09  lea     rdx, [rsp+1D8h+var_188]
0x1800bde0e  mov     rcx, r14
0x1800bde11  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800bde16  cmp     eax, 1
0x1800bde19  jz      loc_1800BDFD0
0x1800bde1f  mov     rbx, [rsi+110h]
0x1800bde26  mov     r15, [rsi+118h]
0x1800bde2d  cmp     rbx, r15
0x1800bde30  jz      loc_1800BDF65
0x1800bde36  lea     rdx, [rsp+1D8h+var_138]
0x1800bde3e  lea     rcx, [rsp+1D8h+var_A8]
0x1800bde46  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bde4b  mov     r8, rax
0x1800bde4e  mov     rcx, [rbx]
0x1800bde51  add     rcx, 10h
0x1800bde55  lea     rdx, [rsp+1D8h+var_178]
0x1800bde5a  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800bde5f  movups  xmm0, xmmword ptr [r8]
0x1800bde63  movdqu  [rsp+1D8h+var_188], xmm0
0x1800bde69  movaps  xmm1, [rsp+1D8h+var_178]
0x1800bde6e  movdqa  xmmword ptr [rsp+1D8h+var_1A8], xmm1
0x1800bde74  lea     rdx, [rsp+1D8h+var_188]
0x1800bde79  lea     rcx, [rsp+1D8h+var_1A8]
0x1800bde7e  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x1800bde83  test    eax, eax
0x1800bde85  jnz     loc_1800BDF5C
0x1800bde8b  mov     rcx, [rbx]
0x1800bde8e  movzx   r15d, byte ptr [rcx+30h]
0x1800bde93  mov     rax, [rcx]
0x1800bde96  mov     rax, [rax]
0x1800bde99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bde9e  mov     r8, rax
0x1800bdea1  mov     edx, r15d
0x1800bdea4  test    r15b, r15b
0x1800bdea7  jz      short loc_1800BDEE8
0x1800bdea9  sub     edx, 1
0x1800bdeac  jz      short loc_1800BDEDD
0x1800bdeae  cmp     edx, 1
0x1800bdeb1  jz      short loc_1800BDECD
0x1800bdeb3  mov     rcx, [rsp+1D8h]; this
0x1800bdebb  lea     r8, aOnecoreBaseTel_14; "onecore\\base\\telemetry\\utc\\service"...
0x1800bdec2  mov     edx, 3A4h; void *
0x1800bdec7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800bdecd  mov     r15d, 4
0x1800bded3  movzx   eax, r15w
0x1800bded7  lea     r12d, [r15-2]
0x1800bdedb  jmp     short loc_1800BDEF8
0x1800bdedd  mov     eax, 3
0x1800bdee2  lea     r12d, [rax-1]
0x1800bdee6  jmp     short loc_1800BDEF2
0x1800bdee8  mov     r12d, 2
0x1800bdeee  movzx   eax, r12w
0x1800bdef2  mov     r15d, 4
0x1800bdef8  mov     [rdi+38h], ax
0x1800bdefc  mov     eax, dword ptr [rsp+1D8h+var_1A8+2]
0x1800bdf00  mov     [rdi+3Ah], eax
0x1800bdf03  movzx   eax, word ptr [rsp+1D8h+var_1A8+6]
0x1800bdf08  mov     [rdi+3Eh], ax
0x1800bdf0c  mov     [rdi+40h], r8
0x1800bdf10  mov     rdx, rbx; void *
0x1800bdf13  lea     rcx, [rsp+1D8h+var_1A8]; void *
0x1800bdf18  call    ??0?$shared_ptr@$$CBVIScenarioDef@Diagnostics@Microsoft@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>::shared_ptr<Microsoft::Diagnostics::IScenarioDef const>(std::shared_ptr<Microsoft::Diagnostics::IScenarioDef const> const &)
0x1800bdf1d  mov     r13, [rax]
0x1800bdf20  mov     rcx, qword ptr [rsp+1D8h+var_158]
0x1800bdf28  mov     [rax], rcx
0x1800bdf2b  mov     qword ptr [rsp+1D8h+var_158], r13
0x1800bdf33  mov     rbx, [rax+8]
0x1800bdf37  mov     rcx, qword ptr [rsp+1D8h+var_158+8]
0x1800bdf3f  mov     [rax+8], rcx
0x1800bdf43  mov     qword ptr [rsp+1D8h+var_158+8], rbx
0x1800bdf4b  mov     rcx, [rsp+1D8h+var_1A8+8]; this
0x1800bdf50  test    rcx, rcx
0x1800bdf53  jz      short loc_1800BDF7F
0x1800bdf55  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdf5a  jmp     short loc_1800BDF7F
0x1800bdf5c  add     rbx, 10h
0x1800bdf60  jmp     loc_1800BDE2D
0x1800bdf65  mov     r15d, 4
0x1800bdf6b  lea     r12d, [r15-2]
0x1800bdf6f  mov     rbx, qword ptr [rsp+1D8h+var_158+8]
0x1800bdf77  mov     r13, qword ptr [rsp+1D8h+var_158]
0x1800bdf7f  xor     ecx, ecx
0x1800bdf81  test    r13, r13
0x1800bdf84  jnz     short loc_1800BDFCA
0x1800bdf86  mov     rcx, [rsp+1D8h]; this
0x1800bdf8e  mov     edi, 87C52424h
0x1800bdf93  mov     r9d, edi; char *
0x1800bdf96  lea     r8, aOnecoreBaseTel_135; "onecore\\base\\telemetry\\utc\\service"...
0x1800bdf9d  mov     edx, 23Dh; void *
0x1800bdfa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bdfa7  nop
0x1800bdfa8  test    rbx, rbx
0x1800bdfab  jz      short loc_1800BDFB6
0x1800bdfad  mov     rcx, rbx; this
0x1800bdfb0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800bdfb5  nop
0x1800bdfb6  lea     rcx, [rsp+1D8h+var_A8]; this
0x1800bdfbe  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800bdfc3  mov     eax, edi
0x1800bdfc5  jmp     loc_1800BEF05
0x1800bdfca  mov     byte ptr [rsp+1D8h+var_1B8], cl
0x1800bdfce  jmp     short loc_1800BDFF1
0x1800bdfd0  mov     byte ptr [rsp+1D8h+var_1B8], 1; int
0x1800bdfd5  mov     r15d, 4
0x1800bdfdb  lea     r12d, [r15-2]
0x1800bdfdf  mov     rbx, qword ptr [rsp+1D8h+var_158+8]
0x1800bdfe7  mov     r13, qword ptr [rsp+1D8h+var_158]
0x1800bdfef  xor     ecx, ecx
0x1800bdff1  movups  xmm0, xmmword ptr cs:off_1803616A0; "target"
0x1800bdff8  movdqu  xmmword ptr [rsp+1D8h+var_1A8], xmm0
0x1800bdffe  lea     rax, Src
0x1800be005  mov     qword ptr [rsp+1D8h+var_188], rax
0x1800be00a  mov     qword ptr [rsp+1D8h+var_188+8], rcx
0x1800be00f  lea     r9, [rsp+1D8h+var_A8]
0x1800be017  lea     r8, [rsp+1D8h+var_1A8]
0x1800be01c  lea     rdx, [rsp+1D8h+var_188]
0x1800be021  mov     rcx, r14
0x1800be024  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800be029  cmp     eax, 1
0x1800be02c  jnz     short loc_1800BE072
0x1800be02e  mov     rcx, [rsp+1D8h]; this
0x1800be036  mov     edi, 87C52425h
0x1800be03b  mov     r9d, edi; char *
0x1800be03e  lea     r8, aOnecoreBaseTel_135; "onecore\\base\\telemetry\\utc\\service"...
0x1800be045  mov     edx, 249h; void *
0x1800be04a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be04f  nop
0x1800be050  test    rbx, rbx
0x1800be053  jz      short loc_1800BE05E
0x1800be055  mov     rcx, rbx; this
0x1800be058  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be05d  nop
0x1800be05e  lea     rcx, [rsp+1D8h+var_A8]; this
0x1800be066  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800be06b  mov     eax, edi
0x1800be06d  jmp     loc_1800BEF05
0x1800be072  lea     rdx, [rsp+1D8h+var_138]
0x1800be07a  lea     rcx, [rsp+1D8h+var_A8]
0x1800be082  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800be087  movups  xmm0, xmmword ptr [rax]
0x1800be08a  movdqu  xmmword ptr [rsp+1D8h+var_1A8], xmm0
0x1800be090  lea     rdx, [rdi+78h]
0x1800be094  lea     rcx, [rsp+1D8h+var_1A8]
0x1800be099  call    ?ConvertStringToStateOrdinal@StateDef@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAE@Z; Microsoft::Diagnostics::StateDef::ConvertStringToStateOrdinal(std::wstring_view,uchar &)
0x1800be09e  xor     ecx, ecx
0x1800be0a0  test    eax, eax
0x1800be0a2  jns     short loc_1800BE0E8
0x1800be0a4  mov     rcx, [rsp+1D8h]; this
0x1800be0ac  mov     edi, 87C5241Fh
0x1800be0b1  mov     r9d, edi; char *
0x1800be0b4  lea     r8, aOnecoreBaseTel_135; "onecore\\base\\telemetry\\utc\\service"...
0x1800be0bb  mov     edx, 24Fh; void *
0x1800be0c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be0c5  nop
0x1800be0c6  test    rbx, rbx
0x1800be0c9  jz      short loc_1800BE0D4
0x1800be0cb  mov     rcx, rbx; this
0x1800be0ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be0d3  nop
0x1800be0d4  lea     rcx, [rsp+1D8h+var_A8]; this
0x1800be0dc  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800be0e1  mov     eax, edi
0x1800be0e3  jmp     loc_1800BEF05
0x1800be0e8  cmp     byte ptr [rdi+78h], 0FAh
0x1800be0ec  jnz     short loc_1800BE132
0x1800be0ee  mov     rcx, [rsp+1D8h]; this
0x1800be0f6  mov     edi, 87C52426h
0x1800be0fb  mov     r9d, edi; char *
0x1800be0fe  lea     r8, aOnecoreBaseTel_135; "onecore\\base\\telemetry\\utc\\service"...
0x1800be105  mov     edx, 255h; void *
0x1800be10a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800be10f  nop
0x1800be110  test    rbx, rbx
0x1800be113  jz      short loc_1800BE11E
0x1800be115  mov     rcx, rbx; this
0x1800be118  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800be11d  nop
0x1800be11e  lea     rcx, [rsp+1D8h+var_A8]; this
0x1800be126  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x1800be12b  mov     eax, edi
0x1800be12d  jmp     loc_1800BEF05
0x1800be132  movups  xmm0, xmmword ptr cs:off_1803616B0; "uploadtrigger"
0x1800be139  movdqu  xmmword ptr [rsp+1D8h+var_1A8], xmm0
0x1800be13f  lea     rax, Src
0x1800be146  mov     qword ptr [rsp+1D8h+var_188], rax
0x1800be14b  mov     qword ptr [rsp+1D8h+var_188+8], rcx
0x1800be150  lea     r9, [rsp+1D8h+var_A8]
0x1800be158  lea     r8, [rsp+1D8h+var_1A8]
0x1800be15d  lea     rdx, [rsp+1D8h+var_188]
0x1800be162  mov     rcx, r14
0x1800be165  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800be16a  xor     r8d, r8d
0x1800be16d  test    eax, eax
0x1800be16f  jnz     short loc_1800BE19F
0x1800be171  lea     rdx, [rsp+1D8h+var_138]
0x1800be179  lea     rcx, [rsp+1D8h+var_A8]
0x1800be181  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800be186  movups  xmm0, xmmword ptr [rax]
0x1800be189  movdqu  xmmword ptr [rsp+1D8h+var_1A8], xmm0
0x1800be18f  lea     rcx, [rsp+1D8h+var_1A8]
0x1800be194  call    ?ToBool@String@Utils@Diagnostics@Microsoft@@SA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToBool(std::wstring_view)
0x1800be199  mov     [rdi+98h], al
0x1800be19f  movups  xmm0, xmmword ptr cs:off_1803616C0; "triggerfields"
0x1800be1a6  movdqu  xmmword ptr [rsp+1D8h+var_1A8], xmm0
0x1800be1ac  lea     rax, Src
0x1800be1b3  mov     qword ptr [rsp+1D8h+var_188], rax
0x1800be1b8  mov     qword ptr [rsp+1D8h+var_188+8], r8
0x1800be1bd  lea     r9, [rsp+1D8h+var_A8]
0x1800be1c5  lea     r8, [rsp+1D8h+var_1A8]
0x1800be1ca  lea     rdx, [rsp+1D8h+var_188]
0x1800be1cf  mov     rcx, r14
0x1800be1d2  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x1800be1d7  test    eax, eax
0x1800be1d9  jnz     short loc_1800BE250
0x1800be1db  lea     rdx, [rsp+1D8h+var_138]
0x1800be1e3  lea     rcx, [rsp+1D8h+var_A8]
0x1800be1eb  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1800be1f0  movups  xmm0, xmmword ptr [rax]
0x1800be1f3  movdqu  xmmword ptr [rsp+1D8h+var_1A8], xmm0
0x1800be1f9  lea     rdx, [rsp+1D8h+var_1A8]
0x1800be1fe  mov     rcx, rdi
0x1800be201  call    ?ParseSelectFieldsAttribute@TransitionDef@Diagnostics@Microsoft@@AEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::TransitionDef::ParseSelectFieldsAttribute(std::wstring_view)
0x1800be206  mov     esi, eax
0x1800be208  test    eax, eax
0x1800be20a  jns     short loc_1800BE24B
0x1800be20c  mov     rcx, [rsp+1D8h]; this
0x1800be214  mov     r9d, eax; char *
0x1800be217  lea     r8, aOnecoreBaseTel_135; "onecore\\base\\telemetry\\utc\\service"...
0x1800be21e  mov     edx, 264h; void *
0x1800be223  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
