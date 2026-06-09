# Microsoft::Diagnostics::ScenarioDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x18008e020`
- end: `0x18008fe7f`
- name: `?ParseFromXml@ScenarioDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `7775`
- prototype: `int(Microsoft::Diagnostics::ScenarioDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `42`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x1800326cc`
- `0x180033f3c`
- `0x180053a84`
- `0x18005a554`
- `0x18008e020`
- `0x18008fe88`
- `0x180090930`
- `0x180090aa8`
- `0x180090b68`
- `0x1800a0d08`
- `0x1800b10c8`
- `0x1800b1108`
- `0x1800bef30`
- `0x1800bef80`
- `0x1800cc510`
- `0x1800d43a8`
- `0x1800de308`
- `0x1800e5ee0`
- `0x1800f457c`
- `0x180111a10`
- `0x18012de40`
- `0x1801cfc44`
- `0x1801e38fc`
- `0x18020c2ac`
- `0x1802384e0`
- `0x18024222c`
- `0x1802427a4`
- `0x1802437d8`
- `0x180243fa8`
- `0x180244088`
- `0x1802440c4`
- `0x180244190`
- `0x180244670`
- `0x180244d34`
- `0x1802e6744`
- `0x1802e6bec`
- `0x1802e725c`
- `0x180346010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18008e231`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x18008e231`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18008eb80`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18008eb80`

## string_xrefs

- `0x18008e106`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008e18c`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008e35f`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008e93e`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008ebc1`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f026`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f0be`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f1f7`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f2b2`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f350`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f3ee`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f488`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f52e`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f5cc`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f61c`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f66c`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f6d3`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f711`: `onecore\base\telemetry\utc\service\scenarios\base\scenariodef.cpp`
- `0x18008f7a6`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x18008f87f`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x18008f974`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x18008fbca`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x18008fdce`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Microsoft::Diagnostics::ScenarioDef::ParseFromXml(
        Microsoft::Diagnostics::ScenarioDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  const char *v6; // r9
  __int64 result; // rax
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // ebx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // rcx
  char v23; // al
  _QWORD *v24; // rdx
  _QWORD *v25; // rax
  unsigned __int16 v26; // ax
  std::_Ref_count_base *v27; // rcx
  int v28; // r15d
  unsigned int Element; // eax
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned int v32; // ebx
  Microsoft::Diagnostics::ScenarioDef *v33; // rcx
  int v34; // eax
  unsigned int v35; // ebx
  Microsoft::Diagnostics::ScenarioDef *v36; // rcx
  struct Microsoft::Diagnostics::ScenarioParsingState *v37; // r8
  int v38; // eax
  unsigned int v39; // ebx
  bool v40; // bl
  __int64 v41; // r9
  int v42; // eax
  unsigned int v43; // ebx
  int v44; // eax
  unsigned int v45; // ebx
  int v46; // eax
  unsigned int v47; // ebx
  int v48; // eax
  unsigned int v49; // ebx
  int v50; // eax
  unsigned int v51; // ebx
  int v52; // eax
  unsigned int v53; // ebx
  int v54; // eax
  unsigned int v55; // ebx
  int v56; // eax
  unsigned int v57; // ebx
  std::_Ref_count_base **v58; // rbx
  std::_Ref_count_base **v59; // r12
  char *v60; // r15
  std::_Ref_count_base *v61; // rcx
  std::_Ref_count_base *v62; // rax
  int v63; // r14d
  std::_Ref_count_base *v64; // rax
  const char *v65; // r9
  __int16 v66; // cx
  _QWORD *v67; // rbx
  _QWORD *v68; // r12
  int v69; // r14d
  std::_Ref_count_base *v70; // rax
  const char *v71; // r9
  __int16 v72; // cx
  _QWORD *v73; // rbx
  _QWORD *v74; // r12
  __int64 v75; // r13
  int v76; // r14d
  std::_Ref_count_base *v77; // rax
  const char *v78; // r9
  __int16 v79; // cx
  std::_Ref_count_base **v80; // r14
  std::_Ref_count_base **v81; // r12
  std::_Ref_count_base *v82; // rcx
  std::_Ref_count_base *v83; // rax
  unsigned __int16 v84; // bx
  std::_Ref_count_base *v85; // r13
  std::_Ref_count_base **v86; // rbx
  std::_Ref_count_base **v87; // r14
  std::_Ref_count_base *v88; // rcx
  std::_Ref_count_base *v89; // rax
  std::_Ref_count_base *v90; // rax
  _QWORD *v91; // rbx
  _QWORD *v92; // r14
  __int64 v93; // r12
  std::_Ref_count_base *v94; // rax
  std::_Ref_count_base **v95; // rbx
  std::_Ref_count_base **v96; // r12
  std::_Ref_count_base *v97; // rcx
  std::_Ref_count_base *v98; // rax
  char v99; // r14
  std::_Ref_count_base *v100; // rax
  const char *v101; // r9
  __int64 v102; // rbx
  _QWORD *v103; // rdx
  std::_Ref_count_base *v104; // rax
  __int64 v105; // rbx
  _QWORD *v106; // rdx
  std::_Ref_count_base *v107; // rax
  std::_Ref_count_base *v108; // rcx
  __int64 v109; // rax
  std::_Ref_count_base *v110; // rax
  std::_Ref_count_base **v111; // rbx
  std::_Ref_count_base **v112; // r14
  std::_Ref_count_base *v113; // rcx
  std::_Ref_count_base *v114; // rax
  char v115; // si
  std::_Ref_count_base *v116; // rax
  const char *v117; // r9
  std::_Ref_count_base *v118[2]; // [rsp+20h] [rbp-358h] BYREF
  std::_Ref_count_base *v119[2]; // [rsp+30h] [rbp-348h] BYREF
  Microsoft::Diagnostics::ScenarioDef *v120; // [rsp+40h] [rbp-338h] BYREF
  char v121; // [rsp+48h] [rbp-330h]
  __int128 v122; // [rsp+50h] [rbp-328h] BYREF
  char v123[8]; // [rsp+60h] [rbp-318h] BYREF
  __int64 v124; // [rsp+68h] [rbp-310h] BYREF
  _BYTE v125[16]; // [rsp+70h] [rbp-308h] BYREF
  _BYTE v126[16]; // [rsp+80h] [rbp-2F8h] BYREF
  _BYTE v127[16]; // [rsp+90h] [rbp-2E8h] BYREF
  std::_Ref_count_base *v128[2]; // [rsp+A0h] [rbp-2D8h] BYREF
  wchar_t *String[4]; // [rsp+B0h] [rbp-2C8h] BYREF
  _QWORD v130[4]; // [rsp+D0h] [rbp-2A8h] BYREF
  _BYTE v131[32]; // [rsp+F0h] [rbp-288h] BYREF
  _BYTE v132[32]; // [rsp+110h] [rbp-268h] BYREF
  _BYTE v133[32]; // [rsp+130h] [rbp-248h] BYREF
  _BYTE v134[32]; // [rsp+150h] [rbp-228h] BYREF
  _BYTE v135[32]; // [rsp+170h] [rbp-208h] BYREF
  _BYTE v136[32]; // [rsp+190h] [rbp-1E8h] BYREF
  _BYTE v137[32]; // [rsp+1B0h] [rbp-1C8h] BYREF
  _BYTE v138[32]; // [rsp+1D0h] [rbp-1A8h] BYREF
  _BYTE v139[32]; // [rsp+1F0h] [rbp-188h] BYREF
  _BYTE v140[32]; // [rsp+210h] [rbp-168h] BYREF
  _BYTE v141[32]; // [rsp+230h] [rbp-148h] BYREF
  _BYTE v142[32]; // [rsp+250h] [rbp-128h] BYREF
  _BYTE v143[32]; // [rsp+270h] [rbp-108h] BYREF
  _BYTE v144[32]; // [rsp+290h] [rbp-E8h] BYREF
  _BYTE v145[32]; // [rsp+2B0h] [rbp-C8h] BYREF
  _BYTE v146[32]; // [rsp+2D0h] [rbp-A8h] BYREF
  _BYTE v147[32]; // [rsp+2F0h] [rbp-88h] BYREF
  _BYTE v148[32]; // [rsp+310h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+378h] [rbp+0h]

  try
  {
    Microsoft::Diagnostics::ParsingDomain::ParsingDomain(&v124, (char *)a3 + 112, 1);
    v120 = this;
    v121 = 1;
    *(_OWORD *)((char *)this + 20) = *(_OWORD *)a3;
    std::wstring::operator=((char *)this + 40, (char *)a3 + 16);
    std::wstring::operator=((char *)this + 72, (char *)a3 + 80);
    std::wstring::wstring(v135);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E60;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v135) != 1 )
      *((_DWORD *)this + 4) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v135);
    if ( *((_DWORD *)this + 4) != 2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x283,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
        (const char *)0x87C51018LL,
        (int)v118[0]);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
      v121 = 0;
      Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
      return 2277838872LL;
    }
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v135);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E70;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(
                         a2,
                         v118,
                         v119,
                         (char *)this + 104) == 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
        (const char *)0x87C52402LL,
        (int)v118[0]);
      v121 = 0;
      Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
      return 2277843970LL;
    }
    std::wstring::operator=((char *)a3 + 48, (char *)this + 104);
    std::wstring::wstring(String);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E40;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, String) != 1 )
    {
      v8 = (const wchar_t *)String;
      if ( String[3] > (wchar_t *)7 )
        v8 = String[0];
      *((_DWORD *)this + 34) = _wcstoi64(v8, 0, 0);
    }
    std::wstring::wstring(v133);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E50;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v133) != 1 )
      *((_DWORD *)this + 35) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v133);
    std::wstring::wstring(v134);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E30;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v134) != 1 )
    {
      *(_OWORD *)v118 = *(_OWORD *)std::wstring::operator std::wstring_view(v134, v128);
      *((_OWORD *)this + 9) = *(_OWORD *)Microsoft::Diagnostics::Utils::String::GUIDFromString(&v122, v118);
    }
    if ( *((_DWORD *)this + 34) )
    {
      if ( !*((_DWORD *)this + 35) )
        goto LABEL_21;
      v9 = *((_QWORD *)this + 18) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v9 )
        v9 = *((_QWORD *)this + 19) - *(_QWORD *)GUID_NULL.Data4;
      if ( !v9 )
      {
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A9,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
          (const char *)0x87C52402LL,
          (int)v118[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v133);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
        v121 = 0;
        Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
        return 2277843970LL;
      }
    }
    std::wstring::wstring(v146);
    *(_OWORD *)v119 = *(_OWORD *)&off_180347F30;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v146) != 1 )
      *((_DWORD *)this + 116) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v146);
    std::wstring::wstring(v145);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E20;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v145) != 1 )
    {
      v10 = Microsoft::Diagnostics::Utils::String::ToIntT<long>(v145);
      LOBYTE(v11) = -3;
      *((_DWORD *)this
      + 12
      * (unsigned int)Microsoft::Diagnostics::ScenarioDef::ReservedStateOrdinalToEscalationPropertiesIndex(v12, v11)
      + 100) = v10;
    }
    std::wstring::wstring(v144);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E00;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v144) != 1 )
    {
      v13 = Microsoft::Diagnostics::Utils::String::ToIntT<long>(v144);
      LOBYTE(v14) = -4;
      *((_DWORD *)this
      + 12
      * (unsigned int)Microsoft::Diagnostics::ScenarioDef::ReservedStateOrdinalToEscalationPropertiesIndex(v15, v14)
      + 100) = v13;
    }
    std::wstring::wstring(v143);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361E10;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v143) != 1 )
      *((_DWORD *)this + 117) = Microsoft::Diagnostics::Utils::String::ToIntT<long>(v143);
    std::wstring::wstring(v142);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361DE0;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v142) != 1 )
      *((_DWORD *)this + 118) = Microsoft::Diagnostics::Utils::String::ToIntT<long>(v142);
    std::wstring::wstring(v141);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361DF0;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v141) != 1 )
      *((_DWORD *)this + 119) = Microsoft::Diagnostics::Utils::String::ToIntT<long>(v141);
    std::wstring::wstring(v140);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361DC0;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v140) != 1 )
    {
      v16 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v140);
      *((_DWORD *)this + 120) = v16;
      if ( !v16 )
        *((_DWORD *)this + 120) = 1;
    }
    std::wstring::wstring(v139);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361DD0;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v139) != 1 )
    {
      v17 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v139);
      LOBYTE(v18) = -3;
      *((_DWORD *)this
      + 12
      * (unsigned int)Microsoft::Diagnostics::ScenarioDef::ReservedStateOrdinalToEscalationPropertiesIndex(v19, v18)
      + 101) = v17;
    }
    std::wstring::wstring(v138);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361DA0;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v138) != 1 )
    {
      v20 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v138);
      LOBYTE(v21) = -4;
      *((_DWORD *)this
      + 12
      * (unsigned int)Microsoft::Diagnostics::ScenarioDef::ReservedStateOrdinalToEscalationPropertiesIndex(v22, v21)
      + 101) = v20;
    }
    std::wstring::wstring(v137);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361DB0;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v137) != 1 )
      *((_BYTE *)this + 484) = (unsigned int)Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v137) == 1;
    std::wstring::wstring(v136);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361D80;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v136) != 1 )
    {
      *(_OWORD *)v118 = *(_OWORD *)std::wstring::operator std::wstring_view(v136, v128);
      *((_BYTE *)this + 485) = Microsoft::Diagnostics::Utils::String::ToBool(v118);
    }
    std::wstring::wstring(v132);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361D90;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v132) != 1 )
    {
      *(_OWORD *)v118 = *(_OWORD *)&off_180361D60;
      *(_OWORD *)v119 = *(_OWORD *)std::wstring::operator std::wstring_view(v132, v128);
      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v119, v118) )
      {
        *(_OWORD *)v118 = *(_OWORD *)&off_180361D70;
        *(_OWORD *)v119 = *(_OWORD *)std::wstring::operator std::wstring_view(v132, v128);
        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v119, v118) )
        {
          *(_OWORD *)v118 = *(_OWORD *)off_180361D30;
          *(_OWORD *)v119 = *(_OWORD *)std::wstring::operator std::wstring_view(v132, v128);
          if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(v119, v118) && *((_BYTE *)a3 + 152) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x31F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
              (const char *)0x87C52407LL,
              (int)v118[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v132);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v136);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v137);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v138);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v139);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v140);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v141);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v142);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v143);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v144);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v145);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v146);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v133);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
            v121 = 0;
            Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
            return 2277843975LL;
          }
          *((_BYTE *)this + 486) = 0;
        }
        else
        {
          *((_BYTE *)this + 486) = 1;
        }
      }
      else
      {
        *((_BYTE *)this + 486) = 2;
      }
    }
    std::wstring::wstring(v131);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361D40;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v131) != 1 )
    {
      v23 = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v131);
      *((_BYTE *)this + 487) = v23;
      if ( !v23 )
        *((_BYTE *)this + 487) = 1;
    }
    *(_OWORD *)v119 = *(_OWORD *)&off_180361D50;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, (char *)this + 224);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361D10;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, (char *)this + 256);
    std::wstring::wstring(v130);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361D20;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v130) != 1 )
    {
      v24 = v130;
      if ( v130[3] > 7u )
        v24 = (_QWORD *)v130[0];
      v25 = (_QWORD *)wil::basic_zstring_view<wchar_t>::basic_zstring_view<wchar_t>(v128, v24, v130[2]);
      v26 = _o__wcstoui64(*v25, 0, 0);
      Microsoft::Diagnostics::CategoryIdType::_from_integral_nothrow(v119, v26);
      if ( !LOBYTE(v119[0]) && *((_BYTE *)a3 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x342,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
          (const char *)0x87C52404LL,
          (int)v118[0]);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v130);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v131);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v132);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v136);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v137);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v138);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v139);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v140);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v141);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v142);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v143);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v144);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v145);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v146);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v133);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
        v121 = 0;
        Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
        return 2277843972LL;
      }
      *((_WORD *)this + 182) = WORD1(v119[0]);
    }
    WORD1(v119[0]) = *((_WORD *)this + 182);
    *((_BYTE *)a3 + 448) = 1;
    *(_WORD *)((char *)a3 + 449) = *(_WORD *)((char *)v119 + 1);
    *((_BYTE *)a3 + 451) = BYTE3(v119[0]);
    std::wstring::wstring(v148);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361CF0;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v148) != 1 )
      *((_QWORD *)this + 36) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(v148);
    std::wstring::wstring(v147);
    *(_OWORD *)v119 = *(_OWORD *)&off_180361D00;
    v118[0] = (std::_Ref_count_base *)&Src;
    v118[1] = 0;
    if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v119, v147) != 1 )
    {
      v119[0] = (std::_Ref_count_base *)L",";
      v119[1] = (std::_Ref_count_base *)1;
      v122 = *(_OWORD *)std::wstring::operator std::wstring_view(v147, v125);
      Microsoft::Diagnostics::Utils::String::SplitToSet<std::wstring,std::less<void>>(v118, &v122, v119);
      v27 = *(std::_Ref_count_base **)v118[0];
      v119[0] = *(std::_Ref_count_base **)v118[0];
      while ( !*((_BYTE *)v27 + 25) )
      {
        v122 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)v27 + 32, v126);
        *(_OWORD *)v128 = *(_OWORD *)Microsoft::Diagnostics::Utils::String::GUIDFromString(v127, &v122);
        std::_Hash<std::_Uset_traits<_GUID,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<_GUID>,0>>::emplace<_GUID const &>(
          (char *)this + 296,
          v135,
          v128);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,std::shared_ptr<Microsoft::Diagnostics::ProviderGroupInfo const>>>>,std::_Iterator_base0>::operator++(v119);
        v27 = v119[0];
      }
      std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
        v118,
        v118);
    }
    v28 = 0;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v147);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v148);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v130);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v131);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v132);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v136);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v137);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v138);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v139);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v140);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v141);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v142);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v143);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v144);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v145);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v146);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v134);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v133);
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
    if ( !Microsoft::Diagnostics::XMLFacade::IsEmptyElement(a2) )
    {
      while ( 1 )
      {
        Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
        v32 = Element;
        if ( Element )
          break;
        std::wstring::wstring(String);
        Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, String);
        *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v135);
        v122 = *(_OWORD *)&off_180361CD0;
        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
        {
          *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v127);
          v122 = *(_OWORD *)&off_180361CE0;
          if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
          {
            *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v126);
            v122 = *(_OWORD *)&off_180361CA0;
            if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
            {
              *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v119);
              v122 = *(_OWORD *)&off_180361C80;
              if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
              {
                *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v136);
                v122 = *(_OWORD *)&off_180361C90;
                if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
                {
                  *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v133);
                  v122 = *(_OWORD *)&off_180361C60;
                  if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
                  {
                    *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v134);
                    v122 = *(_OWORD *)&off_180361C70;
                    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
                    {
                      *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v132);
                      v122 = *(_OWORD *)&off_180361C40;
                      if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
                      {
                        *(_OWORD *)v128 = *(_OWORD *)std::wstring::operator std::wstring_view(String, v130);
                        v122 = *(_OWORD *)&off_180361C50;
                        if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) )
                        {
                          if ( *((_BYTE *)a3 + 152) )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x39D,
                              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                              (const char *)0x87C52407LL,
                              (int)v118[0]);
                            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                            v121 = 0;
                            Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                            return 2277843975LL;
                          }
                          v56 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
                          v57 = v56;
                          if ( v56 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x3A1,
                              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                              (const char *)(unsigned int)v56,
                              (int)v118[0]);
                            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                            v121 = 0;
                            Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                            return v57;
                          }
                        }
                        else
                        {
                          v54 = Microsoft::Diagnostics::ScenarioDef::ParseConfigurations(this, a2, a3);
                          v55 = v54;
                          if ( v54 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x397,
                              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                              (const char *)(unsigned int)v54,
                              (int)v118[0]);
                            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                            v121 = 0;
                            Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                            return v55;
                          }
                        }
                      }
                      else
                      {
                        v52 = Microsoft::Diagnostics::ScenarioDef::ParseSelfDiagnosis(this, a2, a3);
                        v53 = v52;
                        if ( v52 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x393,
                            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                            (const char *)(unsigned int)v52,
                            (int)v118[0]);
                          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                          v121 = 0;
                          Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                          return v53;
                        }
                      }
                    }
                    else
                    {
                      v50 = Microsoft::Diagnostics::ScenarioDef::ParseStateModel(this, a2, a3);
                      v51 = v50;
                      if ( v50 < 0 )
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x38E,
                          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                          (const char *)(unsigned int)v50,
                          (int)v118[0]);
                        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                        v121 = 0;
                        Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                        return v51;
                      }
                      ++v28;
                    }
                  }
                  else
                  {
                    v48 = Microsoft::Diagnostics::ScenarioDef::ParseAlwaysOnTrace(this, a2, a3);
                    v49 = v48;
                    if ( v48 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x38A,
                        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                        (const char *)(unsigned int)v48,
                        (int)v118[0]);
                      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                      v121 = 0;
                      Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                      return v49;
                    }
                  }
                }
                else
                {
                  v46 = Microsoft::Diagnostics::ScenarioDef::ParseFilters(this, a2, a3);
                  v47 = v46;
                  if ( v46 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x386,
                      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                      (const char *)(unsigned int)v46,
                      (int)v118[0]);
                    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                    v121 = 0;
                    Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                    return v47;
                  }
                }
              }
              else
              {
                v44 = Microsoft::Diagnostics::ScenarioDef::ParseTelemetryEvents(this, a2, a3);
                v45 = v44;
                if ( v44 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x382,
                    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                    (const char *)(unsigned int)v44,
                    (int)v118[0]);
                  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                  v121 = 0;
                  Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                  return v45;
                }
              }
            }
            else
            {
              std::wstring::wstring(v131);
              v40 = 0;
              *(_OWORD *)v128 = *(_OWORD *)&off_180361CB0;
              v118[0] = (std::_Ref_count_base *)&Src;
              v118[1] = 0;
              if ( (unsigned int)Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(a2, v118, v128, v131) != 1 )
              {
                *(_OWORD *)v128 = *(_OWORD *)&off_180361CC0;
                v122 = *(_OWORD *)std::wstring::operator std::wstring_view(v131, v125);
                v40 = (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v122, v128) == 0;
              }
              LOBYTE(v41) = v40;
              v42 = Microsoft::Diagnostics::ScenarioDef::ParseEscalationActions(this, a2, a3, v41);
              v43 = v42;
              if ( v42 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x37E,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                  (const char *)(unsigned int)v42,
                  (int)v118[0]);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v131);
                Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
                v121 = 0;
                Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
                return v43;
              }
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v131);
            }
          }
          else
          {
            v38 = Microsoft::Diagnostics::ScenarioDef::ParseSetupActions(v36, a2, v37);
            v39 = v38;
            if ( v38 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x370,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                (const char *)(unsigned int)v38,
                (int)v118[0]);
              Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
              v121 = 0;
              Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
              return v39;
            }
          }
        }
        else
        {
          v34 = Microsoft::Diagnostics::ScenarioDef::ParseTriggers(v33, a2, a3);
          v35 = v34;
          if ( v34 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x36C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
              (const char *)(unsigned int)v34,
              (int)v118[0]);
            Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
            v121 = 0;
            Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
            return v35;
          }
        }
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)String);
      }
      if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3A8,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
          (const char *)Element,
          (int)v118[0]);
        v121 = 0;
        Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
        return v32;
      }
      if ( !v28 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3AD,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
          (const char *)0x87C52402LL,
          (int)v118[0]);
        v121 = 0;
        Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
        return 2277843970LL;
      }
      v58 = (std::_Ref_count_base **)*((_QWORD *)a3 + 34);
      v59 = (std::_Ref_count_base **)*((_QWORD *)a3 + 35);
      v60 = (char *)a3 + 456;
      while ( v58 != v59 )
      {
        v61 = *v58;
        v62 = v58[1];
        if ( v62 )
          _InterlockedIncrement((volatile signed __int32 *)v62 + 2);
        v119[0] = v61;
        v119[1] = v58[1];
        v63 = *((unsigned __int8 *)*v58 + 48);
        v64 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(std::_Ref_count_base *))*v58)(*v58);
        if ( (_BYTE)v63 )
        {
          if ( v63 == 1 )
          {
            v66 = 3;
          }
          else
          {
            if ( v63 != 2 )
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x3A4,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                v65);
            v66 = 4;
          }
        }
        else
        {
          v66 = 2;
        }
        LOWORD(v118[0]) = v66;
        v60 = (char *)a3 + 456;
        v118[1] = v64;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, std::_Ref_count_base **))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          (char *)a3 + 456,
          v130,
          v118,
          v119);
        if ( v119[1] )
          std::_Ref_count_base::_Decref(v119[1]);
        v58 += 2;
      }
      v67 = (_QWORD *)*((_QWORD *)a3 + 40);
      v68 = (_QWORD *)*((_QWORD *)a3 + 41);
      while ( v67 != v68 )
      {
        v119[0] = (std::_Ref_count_base *)std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                                            v128,
                                            v67,
                                            v30,
                                            v31);
        v69 = *(unsigned __int16 *)(*v67 + 16LL);
        v70 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(_QWORD))*v67)(*v67);
        if ( v69 )
        {
          switch ( v69 )
          {
            case 1:
              v72 = 6;
              break;
            case 2:
              v72 = 7;
              break;
            case 3:
              v72 = 8;
              break;
            case 4:
              v72 = 9;
              break;
            case 5:
              v72 = 10;
              break;
            case 6:
              v72 = 11;
              break;
            default:
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x3B5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                v71);
          }
        }
        else
        {
          v72 = 5;
        }
        LOWORD(v118[0]) = v72;
        v118[1] = v70;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, std::_Ref_count_base *))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v118,
          v119[0]);
        if ( v128[1] )
          std::_Ref_count_base::_Decref(v128[1]);
        v67 += 2;
        v60 = (char *)a3 + 456;
      }
      v73 = (_QWORD *)*((_QWORD *)a3 + 25);
      v74 = (_QWORD *)*((_QWORD *)a3 + 26);
      while ( v73 != v74 )
      {
        v75 = std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                v128,
                v73,
                v30,
                v31);
        v76 = *(unsigned __int16 *)(*v73 + 16LL);
        v77 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(_QWORD))*v73)(*v73);
        if ( v76 )
        {
          switch ( v76 )
          {
            case 1:
              v79 = 6;
              break;
            case 2:
              v79 = 7;
              break;
            case 3:
              v79 = 8;
              break;
            case 4:
              v79 = 9;
              break;
            case 5:
              v79 = 10;
              break;
            case 6:
              v79 = 11;
              break;
            default:
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0x3B5,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
                v78);
          }
        }
        else
        {
          v79 = 5;
        }
        LOWORD(v118[0]) = v79;
        v118[1] = v77;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, __int64))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v118,
          v75);
        if ( v128[1] )
          std::_Ref_count_base::_Decref(v128[1]);
        v73 += 2;
      }
      v80 = (std::_Ref_count_base **)*((_QWORD *)a3 + 37);
      v81 = (std::_Ref_count_base **)*((_QWORD *)a3 + 38);
      while ( v80 != v81 )
      {
        v82 = *v80;
        v83 = v80[1];
        if ( v83 )
          _InterlockedIncrement((volatile signed __int32 *)v83 + 2);
        v118[0] = v82;
        v118[1] = v80[1];
        v84 = *((_WORD *)*v80 + 60);
        v85 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(std::_Ref_count_base *))*v80)(*v80);
        Microsoft::Diagnostics::TypeToScenarioDbObjectTypeConverter::ConvertActionTypeToScenarioDbObjectType(v119, v84);
        v119[1] = v85;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, std::_Ref_count_base **))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v119,
          v118);
        if ( v118[1] )
          std::_Ref_count_base::_Decref(v118[1]);
        v80 += 2;
      }
      v86 = (std::_Ref_count_base **)*((_QWORD *)a3 + 22);
      v87 = (std::_Ref_count_base **)*((_QWORD *)a3 + 23);
      while ( v86 != v87 )
      {
        v88 = *v86;
        v89 = v86[1];
        if ( v89 )
          _InterlockedIncrement((volatile signed __int32 *)v89 + 2);
        v118[0] = v88;
        v118[1] = v86[1];
        v90 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(std::_Ref_count_base *))*v86)(*v86);
        LOWORD(v119[0]) = 42;
        v119[1] = v90;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, std::_Ref_count_base **))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v119,
          v118);
        if ( v118[1] )
          std::_Ref_count_base::_Decref(v118[1]);
        v86 += 2;
      }
      v91 = (_QWORD *)*((_QWORD *)a3 + 43);
      v92 = (_QWORD *)*((_QWORD *)a3 + 44);
      while ( v91 != v92 )
      {
        v93 = std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                v128,
                v91,
                v30,
                v31);
        v94 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(_QWORD))*v91)(*v91);
        LOWORD(v118[0]) = 43;
        v118[1] = v94;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, __int64))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v118,
          v93);
        if ( v128[1] )
          std::_Ref_count_base::_Decref(v128[1]);
        v91 += 2;
      }
      v95 = (std::_Ref_count_base **)*((_QWORD *)a3 + 49);
      v96 = (std::_Ref_count_base **)*((_QWORD *)a3 + 50);
      while ( v95 != v96 )
      {
        v97 = *v95;
        v98 = v95[1];
        if ( v98 )
          _InterlockedIncrement((volatile signed __int32 *)v98 + 2);
        v118[0] = v97;
        v118[1] = v95[1];
        v99 = *((_BYTE *)*v95 + 80);
        v100 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(std::_Ref_count_base *))*v95)(*v95);
        if ( v99 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3D8,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v101);
        LOWORD(v119[0]) = 52;
        v119[1] = v100;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, std::_Ref_count_base **))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v119,
          v118);
        if ( v118[1] )
          std::_Ref_count_base::_Decref(v118[1]);
        v95 += 2;
      }
      if ( *((_QWORD *)a3 + 52) )
      {
        v102 = std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                 v128,
                 (char *)a3 + 416,
                 v30,
                 v31);
        v104 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(_QWORD))*v103)(*v103);
        LOWORD(v118[0]) = 43;
        v118[1] = v104;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, __int64))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v118,
          v102);
        if ( v128[1] )
          std::_Ref_count_base::_Decref(v128[1]);
      }
      if ( *((_QWORD *)a3 + 54) )
      {
        v105 = std::static_pointer_cast<Microsoft::Diagnostics::ITriggerDef const,Microsoft::Diagnostics::IScenarioSerializable const>(
                 v128,
                 (char *)a3 + 432,
                 v30,
                 v31);
        v107 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(_QWORD))*v106)(*v106);
        LOWORD(v118[0]) = 44;
        v118[1] = v107;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, __int64))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v118,
          v105);
        if ( v128[1] )
          std::_Ref_count_base::_Decref(v128[1]);
      }
      v108 = (std::_Ref_count_base *)*((_QWORD *)a3 + 20);
      v109 = *((_QWORD *)a3 + 21);
      if ( v109 )
        _InterlockedAdd((volatile signed __int32 *)(v109 + 8), 1u);
      v118[0] = v108;
      v118[1] = *((std::_Ref_count_base **)a3 + 21);
      v110 = (std::_Ref_count_base *)(***((__int64 (__fastcall ****)(_QWORD))a3 + 20))(*((_QWORD *)a3 + 20));
      LOWORD(v119[0]) = 41;
      v119[1] = v110;
      ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, std::_Ref_count_base **))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
        v60,
        v130,
        v119,
        v118);
      if ( v118[1] )
        std::_Ref_count_base::_Decref(v118[1]);
      v111 = (std::_Ref_count_base **)*((_QWORD *)a3 + 46);
      v112 = (std::_Ref_count_base **)*((_QWORD *)a3 + 47);
      while ( v111 != v112 )
      {
        v113 = *v111;
        v114 = v111[1];
        if ( v114 )
          _InterlockedAdd((volatile signed __int32 *)v114 + 2, 1u);
        v118[0] = v113;
        v118[1] = v111[1];
        v115 = *(_BYTE *)(*(__int64 (__fastcall **)(std::_Ref_count_base *, char *))(*(_QWORD *)*v111 + 80LL))(
                           *v111,
                           v123);
        v116 = (std::_Ref_count_base *)(**(__int64 (__fastcall ***)(std::_Ref_count_base *))*v111)(*v111);
        if ( v115 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x3CD,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
            v117);
        LOWORD(v119[0]) = 49;
        v119[1] = v116;
        ((void (__fastcall *)(char *, _QWORD *, std::_Ref_count_base **, std::_Ref_count_base **))std::_Tree<std::_Tmap_traits<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>,Microsoft::Diagnostics::ScenarioDbLookupPairLessPred,std::allocator<std::pair<Microsoft::Diagnostics::ScenarioDbLookupPair const,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>>,0>>::emplace<Microsoft::Diagnostics::ScenarioDbLookupPair,std::shared_ptr<Microsoft::Diagnostics::IScenarioSerializable const>>)(
          v60,
          v130,
          v119,
          v118);
        if ( v118[1] )
          std::_Ref_count_base::_Decref(v118[1]);
        v111 += 2;
      }
    }
    (*(void (__fastcall **)(Microsoft::Diagnostics::ScenarioDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
    std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(v124);
    v121 = 0;
    Microsoft::Diagnostics::ScenarioDef::ParseFromXml_::_3_::_lambda_1_::operator()(&v120);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3F4,
                           (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\scenariodef.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x18008e020  push    rbx
0x18008e022  push    rsi
0x18008e023  push    rdi
0x18008e024  push    r12
0x18008e026  push    r13
0x18008e028  push    r14
0x18008e02a  push    r15
0x18008e02c  sub     rsp, 340h
0x18008e033  mov     rax, cs:__security_cookie
0x18008e03a  xor     rax, rsp
0x18008e03d  mov     [rsp+378h+var_48], rax
0x18008e045  mov     rsi, r8
0x18008e048  mov     r14, rdx
0x18008e04b  mov     rdi, rcx
0x18008e04e  mov     r12d, 1
0x18008e054  lea     rdx, [r8+70h]
0x18008e058  movzx   r8d, r12w
0x18008e05c  lea     rcx, [rsp+378h+var_310]
0x18008e061  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x18008e066  mov     [rsp+378h+var_338], rdi
0x18008e06b  mov     [rsp+378h+var_330], r12b
0x18008e070  movups  xmm0, xmmword ptr [rsi]
0x18008e073  movdqu  xmmword ptr [rdi+14h], xmm0
0x18008e078  lea     rdx, [rsi+10h]
0x18008e07c  lea     rcx, [rdi+28h]
0x18008e080  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008e085  lea     rdx, [rsi+50h]
0x18008e089  lea     rcx, [rdi+48h]
0x18008e08d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008e092  lea     rcx, [rsp+378h+var_208]; void *
0x18008e09a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e09f  nop
0x18008e0a0  movups  xmm0, xmmword ptr cs:off_180361E60; "schemaversion"
0x18008e0a7  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e0ad  lea     rbx, Src
0x18008e0b4  mov     [rsp+378h+var_358], rbx; int
0x18008e0b9  xor     r13d, r13d
0x18008e0bc  mov     [rsp+378h+var_358+8], r13
0x18008e0c1  lea     r9, [rsp+378h+var_208]
0x18008e0c9  lea     r8, [rsp+378h+var_348]
0x18008e0ce  lea     rdx, [rsp+378h+var_358]
0x18008e0d3  mov     rcx, r14
0x18008e0d6  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e0db  cmp     eax, r12d
0x18008e0de  jz      short loc_18008E0F0
0x18008e0e0  lea     rcx, [rsp+378h+var_208]
0x18008e0e8  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x18008e0ed  mov     [rdi+10h], eax
0x18008e0f0  cmp     dword ptr [rdi+10h], 2
0x18008e0f4  jz      short loc_18008E13D
0x18008e0f6  mov     rcx, [rsp+378h]; this
0x18008e0fe  mov     ebx, 87C51018h
0x18008e103  mov     r9d, ebx; char *
0x18008e106  lea     r8, aOnecoreBaseTel_231; "onecore\\base\\telemetry\\utc\\service"...
0x18008e10d  mov     edx, 283h; void *
0x18008e112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e117  nop
0x18008e118  lea     rcx, [rsp+378h+var_208]; this
0x18008e120  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008e125  nop
0x18008e126  mov     [rsp+378h+var_330], r13b
0x18008e12b  lea     rcx, [rsp+378h+var_338]
0x18008e130  call    _Microsoft__Diagnostics__ScenarioDef__ParseFromXml____3____lambda_1___operator__
0x18008e135  nop
0x18008e136  mov     eax, ebx
0x18008e138  jmp     loc_18008FE5B
0x18008e13d  lea     rcx, [rsp+378h+var_208]; this
0x18008e145  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008e14a  movups  xmm0, xmmword ptr cs:off_180361E70; "scenarioname"
0x18008e151  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e157  mov     [rsp+378h+var_358], rbx; int
0x18008e15c  mov     [rsp+378h+var_358+8], r13
0x18008e161  lea     r9, [rdi+68h]
0x18008e165  lea     r8, [rsp+378h+var_348]
0x18008e16a  lea     rdx, [rsp+378h+var_358]
0x18008e16f  mov     rcx, r14
0x18008e172  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e177  cmp     eax, r12d
0x18008e17a  jnz     short loc_18008E1B5
0x18008e17c  mov     rcx, [rsp+378h]; this
0x18008e184  mov     ebx, 87C52402h
0x18008e189  mov     r9d, ebx; char *
0x18008e18c  lea     r8, aOnecoreBaseTel_231; "onecore\\base\\telemetry\\utc\\service"...
0x18008e193  mov     edx, 28Ah; void *
0x18008e198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e19d  nop
0x18008e19e  mov     [rsp+378h+var_330], r13b
0x18008e1a3  lea     rcx, [rsp+378h+var_338]
0x18008e1a8  call    _Microsoft__Diagnostics__ScenarioDef__ParseFromXml____3____lambda_1___operator__
0x18008e1ad  nop
0x18008e1ae  mov     eax, ebx
0x18008e1b0  jmp     loc_18008FE5B
0x18008e1b5  lea     rcx, [rsi+30h]
0x18008e1b9  lea     rdx, [rdi+68h]
0x18008e1bd  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18008e1c2  lea     rcx, [rsp+378h+String]; void *
0x18008e1ca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e1cf  nop
0x18008e1d0  movups  xmm0, xmmword ptr cs:off_180361E40; "measureid"
0x18008e1d7  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e1dd  lea     rbx, Src
0x18008e1e4  mov     [rsp+378h+var_358], rbx
0x18008e1e9  mov     [rsp+378h+var_358+8], r13
0x18008e1ee  lea     r9, [rsp+378h+String]
0x18008e1f6  lea     r8, [rsp+378h+var_348]
0x18008e1fb  lea     rdx, [rsp+378h+var_358]
0x18008e200  mov     rcx, r14
0x18008e203  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e208  mov     r15d, 7
0x18008e20e  cmp     eax, r12d
0x18008e211  jz      short loc_18008E243
0x18008e213  lea     rcx, [rsp+378h+String]
0x18008e21b  cmp     [rsp+378h+var_2B0], r15
0x18008e223  cmova   rcx, [rsp+378h+String]; String
0x18008e22c  xor     r8d, r8d; Radix
0x18008e22f  xor     edx, edx; EndPtr
0x18008e231  call    cs:__imp__wcstoi64
0x18008e238  nop     dword ptr [rax+rax+00h]
0x18008e23d  mov     [rdi+88h], eax
0x18008e243  lea     rcx, [rsp+378h+var_248]; void *
0x18008e24b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e250  nop
0x18008e251  movups  xmm0, xmmword ptr cs:off_180361E50; "measureversion"
0x18008e258  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e25e  mov     [rsp+378h+var_358], rbx
0x18008e263  mov     [rsp+378h+var_358+8], r13
0x18008e268  lea     r9, [rsp+378h+var_248]
0x18008e270  lea     r8, [rsp+378h+var_348]
0x18008e275  lea     rdx, [rsp+378h+var_358]
0x18008e27a  mov     rcx, r14
0x18008e27d  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e282  cmp     eax, r12d
0x18008e285  jz      short loc_18008E29A
0x18008e287  lea     rcx, [rsp+378h+var_248]
0x18008e28f  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x18008e294  mov     [rdi+8Ch], eax
0x18008e29a  lea     rcx, [rsp+378h+var_228]; void *
0x18008e2a2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e2a7  nop
0x18008e2a8  movups  xmm0, xmmword ptr cs:off_180361E30; "measureversionguid"
0x18008e2af  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e2b5  mov     [rsp+378h+var_358], rbx
0x18008e2ba  mov     [rsp+378h+var_358+8], r13
0x18008e2bf  lea     r9, [rsp+378h+var_228]
0x18008e2c7  lea     r8, [rsp+378h+var_348]
0x18008e2cc  lea     rdx, [rsp+378h+var_358]
0x18008e2d1  mov     rcx, r14
0x18008e2d4  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e2d9  cmp     eax, r12d
0x18008e2dc  jz      short loc_18008E316
0x18008e2de  lea     rdx, [rsp+378h+var_2D8]
0x18008e2e6  lea     rcx, [rsp+378h+var_228]
0x18008e2ee  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18008e2f3  movups  xmm0, xmmword ptr [rax]
0x18008e2f6  movdqu  xmmword ptr [rsp+378h+var_358], xmm0; int
0x18008e2fc  lea     rdx, [rsp+378h+var_358]
0x18008e301  lea     rcx, [rsp+378h+var_328]
0x18008e306  call    ?GUIDFromString@String@Utils@Diagnostics@Microsoft@@SA?AU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::String::GUIDFromString(std::wstring_view)
0x18008e30b  movups  xmm0, xmmword ptr [rax]
0x18008e30e  movdqu  xmmword ptr [rdi+90h], xmm0
0x18008e316  cmp     [rdi+88h], r13d
0x18008e31d  jz      loc_18008E3B2
0x18008e323  cmp     [rdi+8Ch], r13d
0x18008e32a  jbe     short loc_18008E34F
0x18008e32c  mov     rax, [rdi+90h]
0x18008e333  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18008e33a  jnz     short loc_18008E34A
0x18008e33c  mov     rax, [rdi+98h]
0x18008e343  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18008e34a  test    rax, rax
0x18008e34d  jnz     short loc_18008E3B2
0x18008e34f  mov     rcx, [rsp+378h]; this
0x18008e357  mov     ebx, 87C52402h
0x18008e35c  mov     r9d, ebx; char *
0x18008e35f  lea     r8, aOnecoreBaseTel_231; "onecore\\base\\telemetry\\utc\\service"...
0x18008e366  mov     edx, 2A9h; void *
0x18008e36b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e370  nop
0x18008e371  lea     rcx, [rsp+378h+var_228]; this
0x18008e379  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008e37e  nop
0x18008e37f  lea     rcx, [rsp+378h+var_248]; this
0x18008e387  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008e38c  nop
0x18008e38d  lea     rcx, [rsp+378h+String]; this
0x18008e395  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18008e39a  nop
0x18008e39b  mov     [rsp+378h+var_330], r13b
0x18008e3a0  lea     rcx, [rsp+378h+var_338]
0x18008e3a5  call    _Microsoft__Diagnostics__ScenarioDef__ParseFromXml____3____lambda_1___operator__
0x18008e3aa  nop
0x18008e3ab  mov     eax, ebx
0x18008e3ad  jmp     loc_18008FE5B
0x18008e3b2  lea     rcx, [rsp+378h+var_A8]; void *
0x18008e3ba  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e3bf  nop
0x18008e3c0  movups  xmm0, xmmword ptr cs:off_180347F30; "maxdurationms"
0x18008e3c7  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e3cd  mov     [rsp+378h+var_358], rbx
0x18008e3d2  mov     [rsp+378h+var_358+8], r13
0x18008e3d7  lea     r9, [rsp+378h+var_A8]
0x18008e3df  lea     r8, [rsp+378h+var_348]
0x18008e3e4  lea     rdx, [rsp+378h+var_358]
0x18008e3e9  mov     rcx, r14
0x18008e3ec  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e3f1  cmp     eax, r12d
0x18008e3f4  jz      short loc_18008E409
0x18008e3f6  lea     rcx, [rsp+378h+var_A8]
0x18008e3fe  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x18008e403  mov     [rdi+1D0h], eax
0x18008e409  lea     rcx, [rsp+378h+var_C8]; void *
0x18008e411  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e416  nop
0x18008e417  movups  xmm0, xmmword ptr cs:off_180361E20; "maxcompletionescalations"
0x18008e41e  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e424  mov     [rsp+378h+var_358], rbx
0x18008e429  mov     [rsp+378h+var_358+8], r13
0x18008e42e  lea     r9, [rsp+378h+var_C8]
0x18008e436  lea     r8, [rsp+378h+var_348]
0x18008e43b  lea     rdx, [rsp+378h+var_358]
0x18008e440  mov     rcx, r14
0x18008e443  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e448  cmp     eax, r12d
0x18008e44b  jz      short loc_18008E47A
0x18008e44d  lea     rcx, [rsp+378h+var_C8]
0x18008e455  call    ??$ToIntT@J@String@Utils@Diagnostics@Microsoft@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToIntT<long>(std::wstring const &)
0x18008e45a  mov     ebx, eax
0x18008e45c  mov     dl, 0FDh
0x18008e45e  call    ?ReservedStateOrdinalToEscalationPropertiesIndex@ScenarioDef@Diagnostics@Microsoft@@AEBAKVReservedStateOrdinal@23@@Z; Microsoft::Diagnostics::ScenarioDef::ReservedStateOrdinalToEscalationPropertiesIndex(Microsoft::Diagnostics::ReservedStateOrdinal)
0x18008e463  mov     ecx, eax
0x18008e465  lea     rdx, [rcx+rcx*2]
0x18008e469  add     rdx, rdx
0x18008e46c  mov     [rdi+rdx*8+190h], ebx
0x18008e473  lea     rbx, Src
0x18008e47a  lea     rcx, [rsp+378h+var_E8]; void *
0x18008e482  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e487  nop
0x18008e488  movups  xmm0, xmmword ptr cs:off_180361E00; "maxfailureescalations"
0x18008e48f  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e495  mov     [rsp+378h+var_358], rbx
0x18008e49a  mov     [rsp+378h+var_358+8], r13
0x18008e49f  lea     r9, [rsp+378h+var_E8]
0x18008e4a7  lea     r8, [rsp+378h+var_348]
0x18008e4ac  lea     rdx, [rsp+378h+var_358]
0x18008e4b1  mov     rcx, r14
0x18008e4b4  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e4b9  cmp     eax, r12d
0x18008e4bc  jz      short loc_18008E4EB
0x18008e4be  lea     rcx, [rsp+378h+var_E8]
0x18008e4c6  call    ??$ToIntT@J@String@Utils@Diagnostics@Microsoft@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToIntT<long>(std::wstring const &)
0x18008e4cb  mov     ebx, eax
0x18008e4cd  mov     dl, 0FCh
0x18008e4cf  call    ?ReservedStateOrdinalToEscalationPropertiesIndex@ScenarioDef@Diagnostics@Microsoft@@AEBAKVReservedStateOrdinal@23@@Z; Microsoft::Diagnostics::ScenarioDef::ReservedStateOrdinalToEscalationPropertiesIndex(Microsoft::Diagnostics::ReservedStateOrdinal)
0x18008e4d4  mov     ecx, eax
0x18008e4d6  lea     rdx, [rcx+rcx*2]
0x18008e4da  add     rdx, rdx
0x18008e4dd  mov     [rdi+rdx*8+190h], ebx
0x18008e4e4  lea     rbx, Src
0x18008e4eb  lea     rcx, [rsp+378h+var_108]; void *
0x18008e4f3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e4f8  nop
0x18008e4f9  movups  xmm0, xmmword ptr cs:off_180361E10; "maxcompletionreports"
0x18008e500  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e506  mov     [rsp+378h+var_358], rbx
0x18008e50b  mov     [rsp+378h+var_358+8], r13
0x18008e510  lea     r9, [rsp+378h+var_108]
0x18008e518  lea     r8, [rsp+378h+var_348]
0x18008e51d  lea     rdx, [rsp+378h+var_358]
0x18008e522  mov     rcx, r14
0x18008e525  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e52a  cmp     eax, r12d
0x18008e52d  jz      short loc_18008E542
0x18008e52f  lea     rcx, [rsp+378h+var_108]
0x18008e537  call    ??$ToIntT@J@String@Utils@Diagnostics@Microsoft@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToIntT<long>(std::wstring const &)
0x18008e53c  mov     [rdi+1D4h], eax
0x18008e542  lea     rcx, [rsp+378h+var_128]; void *
0x18008e54a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e54f  nop
0x18008e550  movups  xmm0, xmmword ptr cs:off_180361DE0; "maxcancelreports"
0x18008e557  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e55d  mov     [rsp+378h+var_358], rbx
0x18008e562  mov     [rsp+378h+var_358+8], r13
0x18008e567  lea     r9, [rsp+378h+var_128]
0x18008e56f  lea     r8, [rsp+378h+var_348]
0x18008e574  lea     rdx, [rsp+378h+var_358]
0x18008e579  mov     rcx, r14
0x18008e57c  call    ?GetAttributeFromCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@5@@Z; Microsoft::Diagnostics::XMLFacade::GetAttributeFromCurrentElement(std::wstring_view,std::wstring_view,std::wstring &)
0x18008e581  cmp     eax, r12d
0x18008e584  jz      short loc_18008E599
0x18008e586  lea     rcx, [rsp+378h+var_128]
0x18008e58e  call    ??$ToIntT@J@String@Utils@Diagnostics@Microsoft@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToIntT<long>(std::wstring const &)
0x18008e593  mov     [rdi+1D8h], eax
0x18008e599  lea     rcx, [rsp+378h+var_148]; void *
0x18008e5a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18008e5a6  nop
0x18008e5a7  movups  xmm0, xmmword ptr cs:off_180361DF0; "maxfailurereports"
0x18008e5ae  movdqu  xmmword ptr [rsp+378h+var_348], xmm0
0x18008e5b4  mov     [rsp+378h+var_358], rbx
0x18008e5b9  mov     [rsp+378h+var_358+8], r13
0x18008e5be  lea     r9, [rsp+378h+var_148]
  ... truncated ...
```
