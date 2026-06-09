# Microsoft::Diagnostics::ETWTriggerDef::ParseFromXml(Microsoft::Diagnostics::XMLFacade &,Microsoft::Diagnostics::ScenarioParsingState &)

- ea: `0x18029d220`
- end: `0x18029dcde`
- name: `?ParseFromXml@ETWTriggerDef@Diagnostics@Microsoft@@UEAAJAEAVXMLFacade@23@AEAUScenarioParsingState@23@@Z`
- size: `2750`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::ETWTriggerDef *__hidden this, struct Microsoft::Diagnostics::XMLFacade *, struct Microsoft::Diagnostics::ScenarioParsingState *)`
- caller_count: `0`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007298`
- `0x18001d160`
- `0x180020fbc`
- `0x180026ecc`
- `0x180027be0`
- `0x18005174c`
- `0x180053a84`
- `0x18005d050`
- `0x18007fae8`
- `0x1800a0d08`
- `0x1800b10c8`
- `0x1800bef30`
- `0x1800de308`
- `0x18012de40`
- `0x180191240`
- `0x1802384e0`
- `0x18023b62c`
- `0x18029ce8c`
- `0x18029d220`
- `0x1802e6744`
- `0x1802e6bec`
- `0x1802e6d88`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18029d3fb`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18029d3fb`

## string_xrefs

- `0x18029dccb`: `onecore\base\telemetry\utc\service\include\DiagTrackCommon.h`
- `0x18029d312`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d3a6`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d418`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d4bb`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d509`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d5c0`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d61d`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d6ca`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d727`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d7d4`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d832`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d8e0`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d93d`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029d9de`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029da1d`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029da5c`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029da9b`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029dade`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029db22`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029db61`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029dbb8`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029dc03`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029dc61`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`
- `0x18029dc86`: `onecore\base\telemetry\utc\service\triggers\etwtriggerdef.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall Microsoft::Diagnostics::ETWTriggerDef::ParseFromXml(
        Microsoft::Diagnostics::ETWTriggerDef *this,
        struct Microsoft::Diagnostics::XMLFacade *a2,
        struct Microsoft::Diagnostics::ScenarioParsingState *a3)
{
  int v6; // ecx
  int v7; // ecx
  __int64 v8; // r8
  int v9; // r14d
  int v10; // r13d
  int v11; // r12d
  unsigned int Element; // esi
  int CurrentElementName; // eax
  unsigned int v14; // esi
  int InnerText; // eax
  unsigned int v17; // esi
  const OLECHAR *v18; // rcx
  HRESULT v19; // eax
  unsigned int v20; // esi
  Microsoft::Diagnostics::SettingsManager *SettingsManager; // rax
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  unsigned int v28; // esi
  int v29; // eax
  unsigned int v30; // esi
  int v31; // eax
  unsigned int v32; // esi
  int v33; // eax
  unsigned int v34; // esi
  int v35; // eax
  unsigned int v36; // esi
  int v37; // eax
  unsigned int v38; // esi
  int v39; // eax
  unsigned int v40; // esi
  int v41; // eax
  unsigned int v42; // esi
  int v43; // eax
  unsigned int v44; // esi
  int v45; // eax
  unsigned int v46; // esi
  int v47; // eax
  unsigned int v48; // esi
  int v49; // eax
  unsigned int v50; // esi
  int v51; // eax
  unsigned int v52; // esi
  int v53; // eax
  unsigned int v54; // esi
  unsigned int v55; // [rsp+20h] [rbp-138h]
  int v56; // [rsp+30h] [rbp-128h]
  int v57; // [rsp+34h] [rbp-124h]
  __int128 v58; // [rsp+40h] [rbp-118h] BYREF
  __int128 v59; // [rsp+50h] [rbp-108h] BYREF
  unsigned int v60[2]; // [rsp+60h] [rbp-F8h] BYREF
  struct Microsoft::Diagnostics::ScenarioParsingState *v61; // [rsp+68h] [rbp-F0h]
  _BYTE v62[16]; // [rsp+70h] [rbp-E8h] BYREF
  _BYTE v63[16]; // [rsp+80h] [rbp-D8h] BYREF
  _BYTE v64[16]; // [rsp+90h] [rbp-C8h] BYREF
  _BYTE v65[16]; // [rsp+A0h] [rbp-B8h] BYREF
  _BYTE v66[16]; // [rsp+B0h] [rbp-A8h] BYREF
  _BYTE v67[16]; // [rsp+C0h] [rbp-98h] BYREF
  LPCOLESTR lpsz[4]; // [rsp+D0h] [rbp-88h] BYREF
  _BYTE v69[32]; // [rsp+F0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]

  v61 = a3;
  v6 = *((unsigned __int8 *)this + 48);
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 != 1 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x3A4,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\DiagTrackCommon.h",
          (const char *)a3);
      v8 = 4;
    }
    else
    {
      v8 = 3;
    }
  }
  else
  {
    v8 = 2;
  }
  Microsoft::Diagnostics::ParsingDomain::ParsingDomain(v60, (char *)a3 + 112, v8);
  v58 = *(_OWORD *)std::wstring::operator std::wstring_view((char *)this + 16, &v59);
  Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(v60, &v58);
  v9 = 0;
  v56 = 0;
  v10 = 0;
  v11 = 0;
  v57 = 0;
  while ( 1 )
  {
    Element = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
    if ( Element )
      break;
    std::wstring::wstring(v69);
    CurrentElementName = Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(a2, v69);
    v14 = CurrentElementName;
    if ( CurrentElementName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
        (const char *)(unsigned int)CurrentElementName,
        v55);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
      return v14;
    }
    v58 = *(_OWORD *)std::wstring::operator std::wstring_view(v69, v62);
    v59 = *(_OWORD *)&off_180363BD0;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v59, &v58) )
    {
      std::wstring::wstring(lpsz);
      InnerText = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v17 = InnerText;
      if ( InnerText < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x109,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)InnerText,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v17;
      }
      v18 = (const OLECHAR *)lpsz;
      if ( lpsz[3] > (LPCOLESTR)7 )
        v18 = lpsz[0];
      v19 = CLSIDFromString(v18, (LPCLSID)((char *)this + 56));
      v20 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v19,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v20;
      }
      SettingsManager = Microsoft::Diagnostics::LifetimeManager::GetSettingsManager((Microsoft::Diagnostics::LifetimeManager *)&gs_lifetimeManager);
      if ( Microsoft::Diagnostics::SettingsManager::IsRecognizedProviderGroupId(
             SettingsManager,
             (const struct _GUID *)((char *)this + 56)) )
      {
        if ( (unsigned int)dword_18042D328 > 2 )
        {
          if ( (unsigned __int8)tlgKeywordOn(&dword_18042D328, 8) )
          {
            *(_QWORD *)v60 = (char *)this + 56;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
              (unsigned int)&dword_18042D328,
              (unsigned int)&unk_1803DAB7F,
              v22,
              v23,
              (__int64)v60);
          }
        }
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x11A,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
                (const char *)0x7DE,
                v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v24;
      }
      v25 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v26 = v25;
      if ( v25 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11D,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v25,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v26;
      }
      v9 = ++v56;
      goto LABEL_49;
    }
    v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v69, v63);
    v58 = *(_OWORD *)&off_180363B70;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v58, &v59) )
    {
      std::wstring::wstring(lpsz);
      v27 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v28 = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x124,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v27,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v28;
      }
      *((_DWORD *)this + 18) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
      v29 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v30 = v29;
      if ( v29 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x128,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v29,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v30;
      }
      ++v10;
LABEL_49:
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
      goto LABEL_65;
    }
    v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v69, v64);
    v58 = *(_OWORD *)&off_180363B60;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v58, &v59) )
    {
      std::wstring::wstring(lpsz);
      v31 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v31,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v32;
      }
      *((_DWORD *)this + 19) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
      v33 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v34 = v33;
      if ( v33 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x133,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v33,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v34;
      }
      ++v11;
      goto LABEL_49;
    }
    v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v69, v65);
    v58 = *(_OWORD *)&off_180363B50;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v58, &v59) )
    {
      std::wstring::wstring(lpsz);
      v35 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v36 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13A,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v35,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v36;
      }
      *((_QWORD *)this + 10) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
      v37 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v38 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13E,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v37,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v38;
      }
      ++v57;
      goto LABEL_49;
    }
    v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v69, v66);
    v58 = *(_OWORD *)&off_180363B90;
    if ( !(unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v58, &v59) )
    {
      std::wstring::wstring(lpsz);
      v39 = Microsoft::Diagnostics::XMLFacade::GetInnerText(a2, lpsz);
      v40 = v39;
      if ( v39 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x145,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v39,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v40;
      }
      *((_BYTE *)this + 88) = Microsoft::Diagnostics::Utils::String::ToUIntT<unsigned long>(lpsz);
      v41 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v42 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x149,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v41,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)lpsz);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v42;
      }
      goto LABEL_49;
    }
    v59 = *(_OWORD *)std::wstring::operator std::wstring_view(v69, v67);
    v58 = *(_OWORD *)&off_180363B80;
    if ( (unsigned int)Microsoft::Diagnostics::Utils::String::ICompare(&v58, &v59) )
    {
      if ( *((_BYTE *)v61 + 152) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)0x87C52407LL,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return 2277843975LL;
      }
      v53 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v54 = v53;
      if ( v53 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x162,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v53,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v54;
      }
    }
    else
    {
      v43 = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v44 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x153,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v43,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v44;
      }
      v45 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v46 = v45;
      if ( v45 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x154,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v45,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v46;
      }
      v47 = Microsoft::Diagnostics::XMLFacade::EnterNextElement(a2);
      v48 = v47;
      if ( v47 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x155,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v47,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v48;
      }
      v49 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v50 = v49;
      if ( v49 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x156,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v49,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v50;
      }
      v51 = Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(a2);
      v52 = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x159,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)(unsigned int)v51,
          v55);
        Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
        return v52;
      }
    }
LABEL_65:
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v69);
  }
  if ( (int)(Element + 0x80000000) >= 0 && Element != -2147024270 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
      (const char *)Element,
      v55);
    return Element;
  }
  if ( v9 == 1 && v57 == 1 )
  {
    if ( v10 )
    {
      *((_BYTE *)this + 89) = 0;
      if ( v10 != 1 || v11 != 1 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x181,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)0x87C52402LL,
          v55);
        return 2277843970LL;
      }
    }
    else
    {
      *((_BYTE *)this + 89) = 1;
      if ( v11 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
          (const char *)0x87C52402LL,
          v55);
        return 2277843970LL;
      }
    }
    Microsoft::Diagnostics::ETWTriggerDef::EstablishParseDynamicMembers(this);
    (*(void (__fastcall **)(Microsoft::Diagnostics::ETWTriggerDef *, _QWORD))(*(_QWORD *)this + 16LL))(this, 0);
    std::deque<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>>::pop_back(*(_QWORD *)v60);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16F,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\triggers\\etwtriggerdef.cpp",
    (const char *)0x87C52402LL,
    v55);
  return 2277843970LL;
}

```

## disassembly

```asm
0x18029d220  push    rbx
0x18029d222  push    rsi
0x18029d223  push    rdi
0x18029d224  push    r12
0x18029d226  push    r13
0x18029d228  push    r14
0x18029d22a  push    r15
0x18029d22c  sub     rsp, 120h
0x18029d233  mov     rax, cs:__security_cookie
0x18029d23a  xor     rax, rsp
0x18029d23d  mov     [rsp+158h+var_48], rax
0x18029d245  mov     r9, r8; char *
0x18029d248  mov     [rsp+158h+var_F0], r8
0x18029d24d  mov     rbx, rdx
0x18029d250  mov     rdi, rcx
0x18029d253  movzx   ecx, byte ptr [rcx+30h]
0x18029d257  test    ecx, ecx
0x18029d259  jz      short loc_18029D27F
0x18029d25b  sub     ecx, 1
0x18029d25e  jz      short loc_18029D271
0x18029d260  cmp     ecx, 1
0x18029d263  jnz     loc_18029DCC3
0x18029d269  mov     r8d, 4
0x18029d26f  jmp     short loc_18029D277
0x18029d271  mov     r8d, 3
0x18029d277  mov     r15d, 2
0x18029d27d  jmp     short loc_18029D289
0x18029d27f  mov     r15d, 2
0x18029d285  movzx   r8d, r15w
0x18029d289  lea     rdx, [r9+70h]
0x18029d28d  lea     rcx, [rsp+158h+var_F8]
0x18029d292  call    ??0ParsingDomain@Diagnostics@Microsoft@@QEAA@AEAV?$stack@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$deque@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V?$allocator@U?$pair@VScenarioDbObjectType@Diagnostics@Microsoft@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@2@@2@@std@@VScenarioDbObjectType@12@@Z; Microsoft::Diagnostics::ParsingDomain::ParsingDomain(std::stack<std::pair<Microsoft::Diagnostics::ScenarioDbObjectType,std::wstring>> &,Microsoft::Diagnostics::ScenarioDbObjectType)
0x18029d297  lea     rcx, [rdi+10h]
0x18029d29b  lea     rdx, [rsp+158h+var_108]
0x18029d2a0  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029d2a5  movups  xmm0, xmmword ptr [rax]
0x18029d2a8  movdqu  [rsp+158h+var_118], xmm0
0x18029d2ae  lea     rdx, [rsp+158h+var_118]
0x18029d2b3  lea     rcx, [rsp+158h+var_F8]
0x18029d2b8  call    ?AddDetailToCurrentFrame@ParsingDomain@Diagnostics@Microsoft@@QEAAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::ParsingDomain::AddDetailToCurrentFrame(std::wstring_view)
0x18029d2bd  xor     r14d, r14d
0x18029d2c0  mov     [rsp+158h+var_128], r14d
0x18029d2c5  xor     r13d, r13d
0x18029d2c8  xor     r12d, r12d
0x18029d2cb  xor     eax, eax
0x18029d2cd  mov     [rsp+158h+var_124], eax
0x18029d2d1  mov     rcx, rbx; this
0x18029d2d4  call    ?EnterNextElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::EnterNextElement(void)
0x18029d2d9  mov     esi, eax
0x18029d2db  test    eax, eax
0x18029d2dd  jnz     loc_18029DB99
0x18029d2e3  lea     rcx, [rsp+158h+var_68]; void *
0x18029d2eb  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18029d2f0  nop
0x18029d2f1  lea     rdx, [rsp+158h+var_68]
0x18029d2f9  mov     rcx, rbx
0x18029d2fc  call    ?GetCurrentElementName@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetCurrentElementName(std::wstring &)
0x18029d301  mov     esi, eax
0x18029d303  test    eax, eax
0x18029d305  jns     short loc_18029D338
0x18029d307  mov     rcx, [rsp+158h]; this
0x18029d30f  mov     r9d, eax; char *
0x18029d312  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d319  mov     edx, 104h; void *
0x18029d31e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d323  nop
0x18029d324  lea     rcx, [rsp+158h+var_68]; this
0x18029d32c  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d331  mov     eax, esi
0x18029d333  jmp     loc_18029DC9F
0x18029d338  lea     rdx, [rsp+158h+var_E8]
0x18029d33d  lea     rcx, [rsp+158h+var_68]
0x18029d345  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029d34a  movups  xmm0, xmmword ptr [rax]
0x18029d34d  movdqu  [rsp+158h+var_118], xmm0
0x18029d353  movups  xmm1, xmmword ptr cs:off_180363BD0; "provider"
0x18029d35a  movdqu  [rsp+158h+var_108], xmm1
0x18029d360  lea     rdx, [rsp+158h+var_118]
0x18029d365  lea     rcx, [rsp+158h+var_108]
0x18029d36a  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18029d36f  test    eax, eax
0x18029d371  jnz     loc_18029D54F
0x18029d377  lea     rcx, [rsp+158h+lpsz]; void *
0x18029d37f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18029d384  nop
0x18029d385  lea     rdx, [rsp+158h+lpsz]
0x18029d38d  mov     rcx, rbx
0x18029d390  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18029d395  mov     esi, eax
0x18029d397  test    eax, eax
0x18029d399  jns     short loc_18029D3DA
0x18029d39b  mov     rcx, [rsp+158h]; this
0x18029d3a3  mov     r9d, eax; char *
0x18029d3a6  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d3ad  mov     edx, 109h; void *
0x18029d3b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d3b7  nop
0x18029d3b8  lea     rcx, [rsp+158h+lpsz]; this
0x18029d3c0  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d3c5  nop
0x18029d3c6  lea     rcx, [rsp+158h+var_68]; this
0x18029d3ce  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d3d3  mov     eax, esi
0x18029d3d5  jmp     loc_18029DC9F
0x18029d3da  lea     rcx, [rsp+158h+lpsz]
0x18029d3e2  cmp     [rsp+158h+var_70], 7
0x18029d3eb  cmova   rcx, [rsp+158h+lpsz]; lpsz
0x18029d3f4  lea     r14, [rdi+38h]
0x18029d3f8  mov     rdx, r14; pclsid
0x18029d3fb  call    cs:__imp_CLSIDFromString
0x18029d402  nop     dword ptr [rax+rax+00h]
0x18029d407  mov     esi, eax
0x18029d409  test    eax, eax
0x18029d40b  jns     short loc_18029D44C
0x18029d40d  mov     rcx, [rsp+158h]; this
0x18029d415  mov     r9d, eax; char *
0x18029d418  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d41f  mov     edx, 10Fh; void *
0x18029d424  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d429  nop
0x18029d42a  lea     rcx, [rsp+158h+lpsz]; this
0x18029d432  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d437  nop
0x18029d438  lea     rcx, [rsp+158h+var_68]; this
0x18029d440  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d445  mov     eax, esi
0x18029d447  jmp     loc_18029DC9F
0x18029d44c  lea     rcx, ?gs_lifetimeManager@@3VLifetimeManager@Diagnostics@Microsoft@@A; this
0x18029d453  call    ?GetSettingsManager@LifetimeManager@Diagnostics@Microsoft@@QEAAAEAVSettingsManager@23@XZ; Microsoft::Diagnostics::LifetimeManager::GetSettingsManager(void)
0x18029d458  mov     rdx, r14; struct _GUID *
0x18029d45b  mov     rcx, rax; this
0x18029d45e  call    ?IsRecognizedProviderGroupId@SettingsManager@Diagnostics@Microsoft@@QEAA_NAEBU_GUID@@@Z; Microsoft::Diagnostics::SettingsManager::IsRecognizedProviderGroupId(_GUID const &)
0x18029d463  test    al, al
0x18029d465  jz      loc_18029D4F0
0x18029d46b  mov     eax, cs:dword_18042D328
0x18029d471  cmp     eax, r15d
0x18029d474  jbe     short loc_18029D4AD
0x18029d476  mov     edx, 8
0x18029d47b  lea     rcx, dword_18042D328
0x18029d482  call    _tlgKeywordOn
0x18029d487  test    al, al
0x18029d489  jz      short loc_18029D4AD
0x18029d48b  mov     qword ptr [rsp+158h+var_F8], r14
0x18029d490  lea     rax, [rsp+158h+var_F8]
0x18029d495  mov     qword ptr [rsp+158h+var_138], rax; unsigned int
0x18029d49a  lea     rdx, unk_1803DAB7F
0x18029d4a1  lea     rcx, dword_18042D328
0x18029d4a8  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18029d4ad  mov     rcx, [rsp+158h]; this
0x18029d4b5  mov     r9d, 7DEh; char *
0x18029d4bb  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d4c2  mov     edx, 11Ah; void *
0x18029d4c7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18029d4cc  mov     ebx, eax
0x18029d4ce  lea     rcx, [rsp+158h+lpsz]; this
0x18029d4d6  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d4db  nop
0x18029d4dc  lea     rcx, [rsp+158h+var_68]; this
0x18029d4e4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d4e9  mov     eax, ebx
0x18029d4eb  jmp     loc_18029DC9F
0x18029d4f0  mov     rcx, rbx; this
0x18029d4f3  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18029d4f8  mov     esi, eax
0x18029d4fa  test    eax, eax
0x18029d4fc  jns     short loc_18029D53D
0x18029d4fe  mov     rcx, [rsp+158h]; this
0x18029d506  mov     r9d, eax; char *
0x18029d509  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d510  mov     edx, 11Dh; void *
0x18029d515  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d51a  nop
0x18029d51b  lea     rcx, [rsp+158h+lpsz]; this
0x18029d523  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d528  nop
0x18029d529  lea     rcx, [rsp+158h+var_68]; this
0x18029d531  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d536  mov     eax, esi
0x18029d538  jmp     loc_18029DC9F
0x18029d53d  mov     r14d, [rsp+158h+var_128]
0x18029d542  inc     r14d
0x18029d545  mov     [rsp+158h+var_128], r14d
0x18029d54a  jmp     loc_18029D971
0x18029d54f  lea     rdx, [rsp+158h+var_D8]
0x18029d557  lea     rcx, [rsp+158h+var_68]
0x18029d55f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029d564  movups  xmm0, xmmword ptr [rax]
0x18029d567  movdqu  [rsp+158h+var_108], xmm0
0x18029d56d  movups  xmm1, xmmword ptr cs:off_180363B70; "id"
0x18029d574  movdqu  [rsp+158h+var_118], xmm1
0x18029d57a  lea     rdx, [rsp+158h+var_108]
0x18029d57f  lea     rcx, [rsp+158h+var_118]
0x18029d584  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18029d589  test    eax, eax
0x18029d58b  jnz     loc_18029D659
0x18029d591  lea     rcx, [rsp+158h+lpsz]; void *
0x18029d599  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18029d59e  nop
0x18029d59f  lea     rdx, [rsp+158h+lpsz]
0x18029d5a7  mov     rcx, rbx
0x18029d5aa  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18029d5af  mov     esi, eax
0x18029d5b1  test    eax, eax
0x18029d5b3  jns     short loc_18029D5F4
0x18029d5b5  mov     rcx, [rsp+158h]; this
0x18029d5bd  mov     r9d, eax; char *
0x18029d5c0  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d5c7  mov     edx, 124h; void *
0x18029d5cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d5d1  nop
0x18029d5d2  lea     rcx, [rsp+158h+lpsz]; this
0x18029d5da  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d5df  nop
0x18029d5e0  lea     rcx, [rsp+158h+var_68]; this
0x18029d5e8  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d5ed  mov     eax, esi
0x18029d5ef  jmp     loc_18029DC9F
0x18029d5f4  lea     rcx, [rsp+158h+lpsz]
0x18029d5fc  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x18029d601  mov     [rdi+48h], eax
0x18029d604  mov     rcx, rbx; this
0x18029d607  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18029d60c  mov     esi, eax
0x18029d60e  test    eax, eax
0x18029d610  jns     short loc_18029D651
0x18029d612  mov     rcx, [rsp+158h]; this
0x18029d61a  mov     r9d, eax; char *
0x18029d61d  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d624  mov     edx, 128h; void *
0x18029d629  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d62e  nop
0x18029d62f  lea     rcx, [rsp+158h+lpsz]; this
0x18029d637  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d63c  nop
0x18029d63d  lea     rcx, [rsp+158h+var_68]; this
0x18029d645  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d64a  mov     eax, esi
0x18029d64c  jmp     loc_18029DC9F
0x18029d651  inc     r13d
0x18029d654  jmp     loc_18029D971
0x18029d659  lea     rdx, [rsp+158h+var_C8]
0x18029d661  lea     rcx, [rsp+158h+var_68]
0x18029d669  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18029d66e  movups  xmm0, xmmword ptr [rax]
0x18029d671  movdqu  [rsp+158h+var_108], xmm0
0x18029d677  movups  xmm1, xmmword ptr cs:off_180363B60; "version"
0x18029d67e  movdqu  [rsp+158h+var_118], xmm1
0x18029d684  lea     rdx, [rsp+158h+var_108]
0x18029d689  lea     rcx, [rsp+158h+var_118]
0x18029d68e  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18029d693  test    eax, eax
0x18029d695  jnz     loc_18029D763
0x18029d69b  lea     rcx, [rsp+158h+lpsz]; void *
0x18029d6a3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18029d6a8  nop
0x18029d6a9  lea     rdx, [rsp+158h+lpsz]
0x18029d6b1  mov     rcx, rbx
0x18029d6b4  call    ?GetInnerText@XMLFacade@Diagnostics@Microsoft@@QEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::XMLFacade::GetInnerText(std::wstring &)
0x18029d6b9  mov     esi, eax
0x18029d6bb  test    eax, eax
0x18029d6bd  jns     short loc_18029D6FE
0x18029d6bf  mov     rcx, [rsp+158h]; this
0x18029d6c7  mov     r9d, eax; char *
0x18029d6ca  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d6d1  mov     edx, 12Fh; void *
0x18029d6d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d6db  nop
0x18029d6dc  lea     rcx, [rsp+158h+lpsz]; this
0x18029d6e4  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d6e9  nop
0x18029d6ea  lea     rcx, [rsp+158h+var_68]; this
0x18029d6f2  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d6f7  mov     eax, esi
0x18029d6f9  jmp     loc_18029DC9F
0x18029d6fe  lea     rcx, [rsp+158h+lpsz]
0x18029d706  call    ??$ToUIntT@K@String@Utils@Diagnostics@Microsoft@@SAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Microsoft::Diagnostics::Utils::String::ToUIntT<ulong>(std::wstring const &)
0x18029d70b  mov     [rdi+4Ch], eax
0x18029d70e  mov     rcx, rbx; this
0x18029d711  call    ?ExitCurrentElement@XMLFacade@Diagnostics@Microsoft@@QEAAJXZ; Microsoft::Diagnostics::XMLFacade::ExitCurrentElement(void)
0x18029d716  mov     esi, eax
0x18029d718  test    eax, eax
0x18029d71a  jns     short loc_18029D75B
0x18029d71c  mov     rcx, [rsp+158h]; this
0x18029d724  mov     r9d, eax; char *
0x18029d727  lea     r8, aOnecoreBaseTel_35; "onecore\\base\\telemetry\\utc\\service"...
0x18029d72e  mov     edx, 133h; void *
0x18029d733  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029d738  nop
0x18029d739  lea     rcx, [rsp+158h+lpsz]; this
0x18029d741  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d746  nop
0x18029d747  lea     rcx, [rsp+158h+var_68]; this
0x18029d74f  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18029d754  mov     eax, esi
0x18029d756  jmp     loc_18029DC9F
0x18029d75b  inc     r12d
0x18029d75e  jmp     loc_18029D971
0x18029d763  lea     rdx, [rsp+158h+var_B8]
0x18029d76b  lea     rcx, [rsp+158h+var_68]
0x18029d773  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
  ... truncated ...
```
