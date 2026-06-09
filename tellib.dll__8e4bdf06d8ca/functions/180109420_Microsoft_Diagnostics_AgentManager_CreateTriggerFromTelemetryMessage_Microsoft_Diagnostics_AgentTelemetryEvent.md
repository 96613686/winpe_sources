# Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(Microsoft::Diagnostics::AgentTelemetryEventMessage const &,JsonBuilder &&,Microsoft::Diagnostics::AgentTransport &,bool)

- ea: `0x180109420`
- end: `0x18010a301`
- name: `?CreateTriggerFromTelemetryMessage@AgentManager@Diagnostics@Microsoft@@CA?AV?$shared_ptr@VETWTriggerInst@Diagnostics@Microsoft@@@std@@AEBUAgentTelemetryEventMessage@23@$$QEAVJsonBuilder@@AEAVAgentTransport@23@_N@Z`
- size: `3809`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c80b4`

## callees

- `0x18001d160`
- `0x180027be0`
- `0x18003f14c`
- `0x180044d20`
- `0x1800470b4`
- `0x1800498f0`
- `0x18004a750`
- `0x18004cf30`
- `0x180052300`
- `0x180053a10`
- `0x180053a84`
- `0x1800552e4`
- `0x180057f58`
- `0x18007cb30`
- `0x18007f0d8`
- `0x180080054`
- `0x1800bc2e0`
- `0x1800d0ebc`
- `0x180109420`
- `0x18010a308`
- `0x18010a42c`
- `0x18010a490`
- `0x18010a4f0`
- `0x18012de40`
- `0x18012de64`
- `0x18012eae4`
- `0x1801c7fbc`
- `0x1801c940c`
- `0x1801ca9b4`
- `0x180299240`
- `0x18029e448`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a28b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18010a28b`

## string_xrefs

- `0x1801094c5`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801094f7`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109551`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109582`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801095e6`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109667`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801096bc`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x18010970f`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109740`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x1801098f1`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109981`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109a2a`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109aae`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109b3d`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109bcc`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109c6b`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109d03`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109d95`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109e0c`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109e89`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109f0d`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x180109fc2`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`
- `0x18010a052`: `onecore\base\telemetry\utc\service\engine\agentmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
Microsoft::Diagnostics::IAsimovEvent **__fastcall Microsoft::Diagnostics::AgentManager::CreateTriggerFromTelemetryMessage(
        Microsoft::Diagnostics::IAsimovEvent **a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        char a5)
{
  JsonValue *v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rbx
  JsonValue *v12; // rcx
  _DWORD *v13; // rax
  __m128i v14; // xmm6
  int v15; // r12d
  struct _GUID *v16; // r8
  Performance *v17; // rcx
  _DWORD *v18; // rdi
  __int64 v19; // r8
  __int64 v20; // r9
  JsonValue *v21; // rcx
  void *v22; // rdx
  unsigned __int64 v23; // r8
  char v24; // al
  __int64 v25; // rax
  JsonValue *v26; // rcx
  const void *v27; // rdx
  char *v28; // r8
  char v29; // al
  char Unchecked; // dl
  char v31; // al
  char v32; // dl
  char v33; // al
  char v34; // dl
  char v35; // al
  unsigned __int64 v36; // r10
  unsigned int v37; // ecx
  char v38; // al
  unsigned int v39; // ecx
  char v40; // al
  char v41; // cl
  char v42; // al
  wil::details::in1diag3 *v43; // r10
  wil::details::in1diag3 *v44; // r10
  char v45; // dl
  char v46; // al
  unsigned __int16 v47; // ax
  char v48; // cl
  unsigned __int16 v49; // ax
  char v50; // cl
  int v51; // r9d
  __int64 v52; // rbx
  __int128 v53; // xmm6
  int v54; // r9d
  int v55; // r9d
  int v56; // r9d
  int v57; // r9d
  int v58; // r9d
  int v59; // r9d
  char v60; // bl
  __int64 EventTimestampFromJson; // rax
  Microsoft::Diagnostics::IAsimovEvent *v62; // rcx
  ULONGLONG TickCount64; // rax
  int v65; // [rsp+28h] [rbp-E0h]
  unsigned int v66[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 Buf1; // [rsp+40h] [rbp-C8h]
  __int128 Buf1_8; // [rsp+48h] [rbp-C0h] BYREF
  int v69; // [rsp+58h] [rbp-B0h]
  __int128 v70; // [rsp+68h] [rbp-A0h] BYREF
  Microsoft::Diagnostics::IAsimovEvent **v71; // [rsp+78h] [rbp-90h]
  wchar_t v72[8]; // [rsp+88h] [rbp-80h] BYREF
  Performance *v73[2]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v74; // [rsp+B0h] [rbp-58h]
  _OWORD v75[2]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v76[32]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v77[144]; // [rsp+F8h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E0h] [rbp+D8h]

  v71 = a1;
  v69 = 0;
  *(_QWORD *)v66 = L"a";
  Buf1 = 1;
  *(_QWORD *)&Buf1_8 = a3;
  DWORD2(Buf1_8) = 0;
  HIDWORD(Buf1_8) = HIDWORD(v75[0]);
  JsonBuilder::find<>(a3, &v70, &Buf1_8, v66);
  if ( !DWORD2(v70) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x514,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v65);
  if ( *(_BYTE *)(*(_QWORD *)v70 + 4LL * DWORD2(v70) + 7) != 0xFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x515,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007070CLL,
      v65);
  *(_QWORD *)&Buf1_8 = L"name";
  *((_QWORD *)&Buf1_8 + 1) = 4;
  JsonBuilder::find<>(a3, v66, &v70, &Buf1_8);
  if ( !(_DWORD)Buf1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x519,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v65);
  v9 = (JsonValue *)(**(_QWORD **)v66 + 4LL * (unsigned int)Buf1);
  if ( *((_BYTE *)v9 + 7) != 0xF5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51A,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007070CLL,
      v65);
  v66[0] = 0;
  *(_QWORD *)&Buf1_8 = JsonValue::Data(v9, v66);
  *((_QWORD *)&Buf1_8 + 1) = (unsigned __int64)v66[0] >> 1;
  v10 = std::_Traits_rfind_ch<std::char_traits<wchar_t>>(Buf1_8, *((_QWORD *)&Buf1_8 + 1), -1, 46);
  v11 = v10;
  if ( v10 == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x521,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v65);
  std::wstring_view::substr(&Buf1_8, v73, 0, v10);
  std::wstring_view::substr(&Buf1_8, v75, v11 + 1, -1);
  *(_QWORD *)&Buf1_8 = L"ext";
  *((_QWORD *)&Buf1_8 + 1) = 3;
  JsonBuilder::find<>(a3, v66, &v70, &Buf1_8);
  if ( !(_DWORD)Buf1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x527,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v65);
  *(_QWORD *)&Buf1_8 = L"container";
  *((_QWORD *)&Buf1_8 + 1) = 9;
  JsonBuilder::find<>(a3, v72, v66, &Buf1_8);
  if ( !*(_DWORD *)&v72[4] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52B,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v65);
  *(_QWORD *)&Buf1_8 = L"type";
  *((_QWORD *)&Buf1_8 + 1) = 4;
  JsonBuilder::find<>(a3, v66, v72, &Buf1_8);
  if ( !(_DWORD)Buf1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007000DLL,
      v65);
  v12 = (JsonValue *)(**(_QWORD **)v66 + 4LL * (unsigned int)Buf1);
  if ( *((_BYTE *)v12 + 7) != 0xF6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x52F,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
      (const char *)0x8007070CLL,
      v65);
  v13 = JsonValue::Data(v12, 0);
  *v13 |= *(_DWORD *)(a4 + 344) << 8;
  *(_OWORD *)v72 = *(_OWORD *)&Microsoft::Diagnostics::SyntheticTriggerDef::k_telClientSyntheticProviderName;
  v14 = *(__m128i *)v73;
  v15 = Microsoft::Diagnostics::Utils::String::ICompare(v73, v72);
  Buf1_8 = *(_OWORD *)(a2 + 48);
  if ( !memcmp_0(&Buf1_8, &GUID_NULL, 0x10u) )
  {
    *(GUID *)v72 = GUID_NULL;
    std::wstring::wstring(v73, v14.m128i_i64[0], _mm_srli_si128(v14, 8).m128i_u64[0]);
    v17 = (Performance *)v73;
    if ( v74 > 7 )
      v17 = v73[0];
    if ( (int)Performance::NameToGuid(v17, v72, v16) >= 0 )
      Buf1_8 = *(_OWORD *)v72;
    Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v73);
  }
  *(__m128i *)v73 = v14;
  Microsoft::Diagnostics::ETWTriggerDef::ETWTriggerDef(v77, &Buf1_8, v73, v75);
  v18 = operator new(0x450u);
  *(_QWORD *)v66 = v18;
  *(_OWORD *)v18 = 0;
  v18[2] = 1;
  v18[3] = 1;
  *(_QWORD *)v18 = &std::_Ref_count_obj2<Microsoft::Diagnostics::TimeTriggerInst>::`vftable';
  Microsoft::Diagnostics::ETWTriggerInst::ETWTriggerInst(
    (Microsoft::Diagnostics::ETWTriggerInst *)(v18 + 4),
    (const struct Microsoft::Diagnostics::ETWTriggerDef *)v77);
  *a1 = (Microsoft::Diagnostics::IAsimovEvent *)(v18 + 4);
  a1[1] = (Microsoft::Diagnostics::IAsimovEvent *)v18;
  v69 = 3;
  std::wstring::wstring(v76);
  *(_QWORD *)v72 = L"ag";
  *(_QWORD *)&v72[4] = 2;
  *(_QWORD *)v66 = a3;
  LODWORD(Buf1) = 0;
  HIDWORD(Buf1) = HIDWORD(v75[0]);
  JsonBuilder::find<>(a3, &Buf1_8, v66, v72);
  if ( DWORD2(Buf1_8) )
  {
    if ( *(_BYTE *)(*(_QWORD *)Buf1_8 + 4LL * DWORD2(Buf1_8) + 7) != 0xFF )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x551,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
        (const char *)0x8007070CLL,
        v65);
    *(_QWORD *)v72 = L"ikey";
    *(_QWORD *)&v72[4] = 4;
    JsonBuilder::find<>(a3, v66, &Buf1_8, v72);
    if ( (_DWORD)Buf1 )
    {
      v21 = (JsonValue *)(**(_QWORD **)v66 + 4LL * (unsigned int)Buf1);
      if ( *((_BYTE *)v21 + 7) == 0xF5 )
      {
        v66[0] = 0;
        v22 = JsonValue::Data(v21, v66);
        v23 = (unsigned __int64)v66[0] >> 1;
        v24 = 0;
      }
      else
      {
        v22 = 0;
        v23 = 0;
        v24 = 1;
      }
      if ( v24 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x557,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      v25 = std::wstring::wstring(v75, v22, v23);
      std::wstring::operator=(v76, v25);
      Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v75);
    }
    *(_QWORD *)v72 = L"usid";
    *(_QWORD *)&v72[4] = 4;
    JsonBuilder::find<>(a3, v66, &Buf1_8, v72);
    if ( (_DWORD)Buf1 )
    {
      v26 = (JsonValue *)(**(_QWORD **)v66 + 4LL * (unsigned int)Buf1);
      if ( *((_BYTE *)v26 + 7) == 0xF5 )
      {
        v66[0] = 0;
        v27 = JsonValue::Data(v26, v66);
        v28 = (char *)((unsigned __int64)v66[0] >> 1);
        v29 = 0;
      }
      else
      {
        v27 = 0;
        v28 = 0;
        v29 = 1;
      }
      if ( v29 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x55F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      std::wstring::_Assign<wchar_t>((char **)*a1 + 92, v27, v28);
    }
    *(_QWORD *)v72 = L"irpc";
    *(_QWORD *)&v72[4] = 4;
    JsonBuilder::find<>(a3, v66, &Buf1_8, v72);
    if ( (_DWORD)Buf1 )
    {
      if ( *(_BYTE *)(**(_QWORD **)v66 + 4LL * (unsigned int)Buf1 + 7) == 0xF9 )
      {
        Unchecked = JsonImplementType<bool>::GetUnchecked();
        v31 = 0;
      }
      else
      {
        Unchecked = 0;
        v31 = 1;
      }
      if ( v31 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x567,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_BYTE *)*a1 + 698) = (16 * Unchecked) | *((_BYTE *)*a1 + 698) & 0xEF;
    }
    *(_QWORD *)v72 = L"ita";
    *(_QWORD *)&v72[4] = 3;
    JsonBuilder::find<>(a3, v66, &Buf1_8, v72);
    if ( (_DWORD)Buf1 )
    {
      if ( *(_BYTE *)(**(_QWORD **)v66 + 4LL * (unsigned int)Buf1 + 7) == 0xF9 )
      {
        v32 = JsonImplementType<bool>::GetUnchecked();
        v33 = 0;
      }
      else
      {
        v32 = 0;
        v33 = 1;
      }
      if ( v33 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x56F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_BYTE *)*a1 + 697) = *((_BYTE *)*a1 + 697) & 0x7F | (v32 << 7);
    }
    *(_QWORD *)v72 = L"rxt";
    *(_QWORD *)&v72[4] = 3;
    JsonBuilder::find<>(a3, v66, &Buf1_8, v72);
    if ( (_DWORD)Buf1 )
    {
      if ( *(_BYTE *)(**(_QWORD **)v66 + 4LL * (unsigned int)Buf1 + 7) == 0xF9 )
      {
        v34 = JsonImplementType<bool>::GetUnchecked();
        v35 = 0;
      }
      else
      {
        v34 = 0;
        v35 = 1;
      }
      if ( v35 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x577,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_BYTE *)*a1 + 1064) = v34 | *((_BYTE *)*a1 + 1064) & 0xFE;
    }
    *(_QWORD *)v72 = L"ei";
    *(_QWORD *)&v72[4] = 2;
    JsonBuilder::find<>(a3, v73, &Buf1_8, v72);
    if ( LODWORD(v73[1]) )
    {
      *(_QWORD *)v66 = 0;
      if ( (unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                              *(_QWORD *)v73[0] + 4LL * LODWORD(v73[1]),
                              v66)
        && (v37 = v66[0], *(_QWORD *)v66 < v36) )
      {
        v38 = 0;
      }
      else
      {
        v37 = 0;
        v38 = 1;
      }
      if ( v38 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x57F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_DWORD *)*a1 + 250) = v37;
    }
    v73[0] = (Performance *)L"ev";
    v73[1] = (Performance *)2;
    JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
    if ( *(_DWORD *)&v72[4] )
    {
      *(_QWORD *)v66 = 0;
      if ( (unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                              **(_QWORD **)v72 + 4LL * *(unsigned int *)&v72[4],
                              v66)
        && (v39 = v66[0], *(_QWORD *)v66 < 0x100000000uLL) )
      {
        v40 = 0;
      }
      else
      {
        v39 = 0;
        v40 = 1;
      }
      if ( v40 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x587,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_DWORD *)*a1 + 251) = v39;
    }
    v73[0] = (Performance *)L"el";
    v73[1] = (Performance *)2;
    JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
    if ( *(_DWORD *)&v72[4] )
    {
      *(_QWORD *)v66 = 0;
      if ( (unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                              **(_QWORD **)v72 + 4LL * *(unsigned int *)&v72[4],
                              v66)
        && (v41 = v66[0], *(_QWORD *)v66 < 0x100u) )
      {
        v42 = 0;
      }
      else
      {
        v41 = 0;
        v42 = 1;
      }
      if ( v42 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_BYTE *)*a1 + 1016) = v41;
    }
    v73[0] = (Performance *)L"ek";
    v73[1] = (Performance *)2;
    JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
    if ( *(_DWORD *)&v72[4] )
    {
      *(_QWORD *)v66 = 0;
      if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                               **(_QWORD **)v72 + 4LL * *(unsigned int *)&v72[4],
                               v66) )
        wil::details::in1diag3::Throw_Hr(
          v43,
          (void *)0x597,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_QWORD *)*a1 + 96) = *(_QWORD *)v66;
    }
    v73[0] = (Performance *)L"kw";
    v73[1] = (Performance *)2;
    JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
    if ( *(_DWORD *)&v72[4] )
    {
      *(_QWORD *)v66 = 0;
      if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                               **(_QWORD **)v72 + 4LL * *(unsigned int *)&v72[4],
                               v66) )
        wil::details::in1diag3::Throw_Hr(
          v44,
          (void *)0x59F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_QWORD *)*a1 + 126) = *(_QWORD *)v66;
    }
    v73[0] = (Performance *)L"nw";
    v73[1] = (Performance *)2;
    JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
    if ( *(_DWORD *)&v72[4] )
    {
      if ( *(_BYTE *)(**(_QWORD **)v72 + 4LL * *(unsigned int *)&v72[4] + 7) == 0xF9 )
      {
        v45 = JsonImplementType<bool>::GetUnchecked();
        v46 = 0;
      }
      else
      {
        v45 = 0;
        v46 = 1;
      }
      if ( v46 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5A7,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
          (const char *)0x8007000DLL,
          v65);
      *((_BYTE *)*a1 + 698) = *((_BYTE *)*a1 + 698) & 0xFB | (4 * v45);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaUtcUpdate>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_DmaUtcUpdate>::GetImpl'::`2'::impl) )
    {
      v73[0] = (Performance *)L"tpp";
      v73[1] = (Performance *)3;
      JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
      if ( *(_DWORD *)&v72[4] )
      {
        *(_QWORD *)v66 = 0;
        if ( (unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                                **(_QWORD **)v72 + 4LL * *(unsigned int *)&v72[4],
                                v66)
          && (v47 = v66[0], *(_QWORD *)v66 < 0x10000u) )
        {
          v48 = 0;
        }
        else
        {
          v47 = 0;
          v48 = 1;
        }
        if ( v48 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5B1,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v65);
        Microsoft::Diagnostics::IAsimovEvent::SetProduct(*a1, v47);
      }
      v73[0] = (Performance *)L"tpdc";
      v73[1] = (Performance *)4;
      JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
      if ( *(_DWORD *)&v72[4] )
      {
        *(_QWORD *)v66 = 0;
        if ( (unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                                **(_QWORD **)v72 + 4LL * *(unsigned int *)&v72[4],
                                v66)
          && (v49 = v66[0], *(_QWORD *)v66 < 0x10000u) )
        {
          v50 = 0;
        }
        else
        {
          v49 = 0;
          v50 = 1;
        }
        if ( v50 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x5B9,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\agentmanager.cpp",
            (const char *)0x8007000DLL,
            v65);
        Microsoft::Diagnostics::IAsimovEvent::SetDataCategory(*a1, v49);
      }
    }
    v73[0] = (Performance *)L"vmd";
    v73[1] = (Performance *)3;
    JsonBuilder::find<>(a3, v72, &Buf1_8, v73);
    if ( *(_DWORD *)&v72[4] )
    {
      v52 = (__int64)*a1 + 40;
      v75[0] = *(_OWORD *)&off_18035FF88;
      v53 = *(_OWORD *)v72;
      *(_OWORD *)v73 = *(_OWORD *)v72;
      LOBYTE(v51) = 1;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(a3, (unsigned int)v73, (unsigned int)v75, v51, v52);
      v75[0] = *(_OWORD *)&off_18035FF98;
      *(_OWORD *)v73 = v53;
      LOBYTE(v54) = 1;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
        a3,
        (unsigned int)v73,
        (unsigned int)v75,
        v54,
        v52 + 32);
      v75[0] = *(_OWORD *)&off_18035FF48;
      *(_OWORD *)v73 = v53;
      LOBYTE(v55) = 1;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
        a3,
        (unsigned int)v73,
        (unsigned int)v75,
        v55,
        v52 + 64);
      v75[0] = *(_OWORD *)&off_18035FF58;
      *(_OWORD *)v73 = v53;
      LOBYTE(v56) = 1;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
        a3,
        (unsigned int)v73,
        (unsigned int)v75,
        v56,
        v52 + 96);
      v75[0] = *(_OWORD *)&off_18035FF68;
      *(_OWORD *)v73 = v53;
      LOBYTE(v57) = 1;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
        a3,
        (unsigned int)v73,
        (unsigned int)v75,
        v57,
        v52 + 128);
      v75[0] = *(_OWORD *)&off_18035FF78;
      *(_OWORD *)v73 = v53;
      LOBYTE(v58) = 1;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
        a3,
        (unsigned int)v73,
        (unsigned int)v75,
        v58,
        v52 + 160);
      v75[0] = *(_OWORD *)&off_18035FF38;
      *(_OWORD *)v73 = v53;
      LOBYTE(v59) = 1;
      Microsoft::Diagnostics::ScenarioObjectCache::DeserializeString(
        a3,
        (unsigned int)v73,
        (unsigned int)v75,
        v59,
        v52 + 192);
    }
    v75[0] = Buf1_8;
    JsonBuilder::erase(a3, v73, v75);
  }
  if ( (*(_BYTE *)a2 & 0x10) != 0 )
  {
    v60 = 1;
    if ( a5 || !v15 )
    {
      LOBYTE(v20) = 1;
      goto LABEL_128;
    }
  }
  else
  {
    v60 = 0;
  }
  LOBYTE(v20) = 0;
LABEL_128:
  *(_QWORD *)v66 = 0;
  v75[0] = v70;
  LOBYTE(v19) = v60;
  EventTimestampFromJson = Microsoft::Diagnostics::ETWConsumer::GetEventTimestampFromJson(a3, v75, v19, v20, v66);
  v62 = *a1;
  *((_QWORD *)v62 + 33) = EventTimestampFromJson;
  *((_BYTE *)v62 + 697) &= ~8u;
  *((_BYTE *)v62 + 697) |= 8 * (v60 ^ 1);
  Microsoft::Diagnostics::ETWTriggerInst::PopulateAgentData(*a1);
  if ( *(_QWORD *)v66 )
    TickCount64 = Microsoft::Diagnostics::TimeStampManager::ConvertQpcToTicks(
                    (Microsoft::Diagnostics::TimeStampManager *)qword_18043C120,
                    *(__int64 *)v66);
  else
    TickCount64 = GetTickCount64();
  Microsoft::Diagnostics::IAsimovEvent::RecordSystemStateFlags(*a1, 1, TickCount64);
  Microsoft::Diagnostics::ETWTriggerInst::PopulateOsVersion(*a1);
  Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v76);
  Microsoft::Diagnostics::ETWTriggerDef::~ETWTriggerDef((Microsoft::Diagnostics::ETWTriggerDef *)v77);
  return a1;
}

```

## disassembly

```asm
0x180109420  mov     rax, rsp
0x180109423  mov     [rax+20h], rbx
0x180109427  push    rbp
0x180109428  push    rsi
0x180109429  push    rdi
0x18010942a  push    r12
0x18010942c  push    r13
0x18010942e  push    r14
0x180109430  push    r15
0x180109432  lea     rbp, [rax-0D8h]
0x180109439  sub     rsp, 1A0h
0x180109440  movaps  xmmword ptr [rax-48h], xmm6
0x180109444  mov     rax, cs:__security_cookie
0x18010944b  xor     rax, rsp
0x18010944e  mov     [rbp+0D0h+var_50], rax
0x180109455  mov     rdi, r9
0x180109458  mov     rsi, r8
0x18010945b  mov     r15, rdx
0x18010945e  mov     r14, rcx
0x180109461  mov     [rsp+1D0h+var_160], rcx
0x180109466  xor     r13d, r13d
0x180109469  mov     [rsp+1D0h+var_180], r13d
0x18010946e  lea     rax, aA_1; "a"
0x180109475  mov     qword ptr [rsp+1D0h+var_1A0], rax
0x18010947a  mov     qword ptr [rsp+1D0h+Buf1], 1
0x180109483  mov     qword ptr [rsp+1D0h+Buf1+8], r8
0x180109488  mov     [rsp+1D0h+var_188], r13d
0x18010948d  mov     eax, dword ptr [rbp+0D0h+var_120+0Ch]
0x180109490  mov     [rsp+1D0h+var_184], eax
0x180109494  lea     r9, [rsp+1D0h+var_1A0]
0x180109499  lea     r8, [rsp+1D0h+Buf1+8]
0x18010949e  lea     rdx, [rsp+1D0h+var_178+8]
0x1801094a3  mov     rcx, rsi
0x1801094a6  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1801094ab  mov     edx, dword ptr [rsp+1D0h+var_168]
0x1801094af  test    edx, edx
0x1801094b1  setz    al
0x1801094b4  mov     rcx, [rbp+0D8h]; this
0x1801094bb  test    al, al
0x1801094bd  jz      short loc_1801094D7
0x1801094bf  mov     r9d, 8007000Dh; char *
0x1801094c5  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801094cc  mov     edx, 514h; void *
0x1801094d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801094d7  mov     rcx, [rbp+0D8h]; this
0x1801094de  mov     r8, rdx
0x1801094e1  mov     rax, qword ptr [rsp+1D0h+var_178+8]
0x1801094e6  mov     rdx, [rax]
0x1801094e9  cmp     byte ptr [rdx+r8*4+7], 0FFh
0x1801094ef  jz      short loc_180109509
0x1801094f1  mov     r9d, 8007070Ch; char *
0x1801094f7  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801094fe  mov     edx, 515h; void *
0x180109503  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180109509  lea     rax, aName_3; "name"
0x180109510  mov     qword ptr [rsp+1D0h+Buf1+8], rax
0x180109515  mov     r12d, 4
0x18010951b  mov     qword ptr [rsp+1D0h+var_188], r12
0x180109520  lea     r9, [rsp+1D0h+Buf1+8]
0x180109525  lea     r8, [rsp+1D0h+var_178+8]
0x18010952a  lea     rdx, [rsp+1D0h+var_1A0]
0x18010952f  mov     rcx, rsi
0x180109532  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180109537  mov     edx, dword ptr [rsp+1D0h+Buf1]
0x18010953b  test    edx, edx
0x18010953d  setz    al
0x180109540  mov     rcx, [rbp+0D8h]; this
0x180109547  test    al, al
0x180109549  jz      short loc_180109563
0x18010954b  mov     r9d, 8007000Dh; char *
0x180109551  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180109558  mov     edx, 519h; void *
0x18010955d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180109563  mov     rax, qword ptr [rsp+1D0h+var_1A0]
0x180109568  mov     rcx, [rax]
0x18010956b  lea     rcx, [rcx+rdx*4]; this
0x18010956f  mov     rax, [rbp+0D8h]
0x180109576  cmp     byte ptr [rcx+7], 0F5h
0x18010957a  jz      short loc_180109597
0x18010957c  mov     r9d, 8007070Ch; char *
0x180109582  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180109589  mov     edx, 51Ah; void *
0x18010958e  mov     rcx, rax; this
0x180109591  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180109597  mov     [rsp+1D0h+var_1A0], r13d
0x18010959c  lea     rdx, [rsp+1D0h+var_1A0]; unsigned int *
0x1801095a1  call    ?Data@JsonValue@@QEAAPEAXPEAI@Z; JsonValue::Data(uint *)
0x1801095a6  mov     rcx, rax
0x1801095a9  mov     edx, [rsp+1D0h+var_1A0]
0x1801095ad  shr     rdx, 1
0x1801095b0  mov     rax, [rbp+0D8h]
0x1801095b7  mov     qword ptr [rsp+1D0h+Buf1+8], rcx
0x1801095bc  mov     qword ptr [rsp+1D0h+var_188], rdx
0x1801095c1  mov     r9d, 2Eh ; '.'
0x1801095c7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1801095cb  call    ??$_Traits_rfind_ch@U?$char_traits@_W@std@@@std@@YA_KQEB_W_K1_W@Z; std::_Traits_rfind_ch<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,unsigned __int64,wchar_t)
0x1801095d0  mov     rbx, rax
0x1801095d3  mov     rcx, [rbp+0D8h]; this
0x1801095da  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801095de  jnz     short loc_1801095F8
0x1801095e0  mov     r9d, 8007000Dh; char *
0x1801095e6  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801095ed  mov     edx, 521h; void *
0x1801095f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801095f8  mov     r9, rbx
0x1801095fb  xor     r8d, r8d
0x1801095fe  lea     rdx, [rbp+0D0h+var_140]
0x180109602  lea     rcx, [rsp+1D0h+Buf1+8]
0x180109607  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x18010960c  lea     r8, [rbx+1]
0x180109610  or      r9, 0FFFFFFFFFFFFFFFFh
0x180109614  lea     rdx, [rbp+0D0h+var_120]
0x180109618  lea     rcx, [rsp+1D0h+Buf1+8]
0x18010961d  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@std@@@std@@QEBA?AV12@_K_K@Z; std::wstring_view::substr(unsigned __int64,unsigned __int64)
0x180109622  lea     rax, aExt; "ext"
0x180109629  mov     qword ptr [rsp+1D0h+Buf1+8], rax
0x18010962e  mov     qword ptr [rsp+1D0h+var_188], 3
0x180109637  lea     r9, [rsp+1D0h+Buf1+8]
0x18010963c  lea     r8, [rsp+1D0h+var_178+8]
0x180109641  lea     rdx, [rsp+1D0h+var_1A0]
0x180109646  mov     rcx, rsi
0x180109649  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18010964e  cmp     dword ptr [rsp+1D0h+Buf1], r13d
0x180109653  setz    al
0x180109656  mov     rcx, [rbp+0D8h]; this
0x18010965d  test    al, al
0x18010965f  jz      short loc_180109679
0x180109661  mov     r9d, 8007000Dh; char *
0x180109667  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x18010966e  mov     edx, 527h; void *
0x180109673  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180109679  lea     rax, aContainer; "container"
0x180109680  mov     qword ptr [rsp+1D0h+Buf1+8], rax
0x180109685  mov     qword ptr [rsp+1D0h+var_188], 9
0x18010968e  lea     r9, [rsp+1D0h+Buf1+8]
0x180109693  lea     r8, [rsp+1D0h+var_1A0]
0x180109698  lea     rdx, [rbp+0D0h+var_150]
0x18010969c  mov     rcx, rsi
0x18010969f  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1801096a4  cmp     dword ptr [rbp+0D0h+var_150+8], r13d
0x1801096a8  setz    al
0x1801096ab  mov     rcx, [rbp+0D8h]; this
0x1801096b2  test    al, al
0x1801096b4  jz      short loc_1801096CE
0x1801096b6  mov     r9d, 8007000Dh; char *
0x1801096bc  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801096c3  mov     edx, 52Bh; void *
0x1801096c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801096ce  lea     rax, aType; "type"
0x1801096d5  mov     qword ptr [rsp+1D0h+Buf1+8], rax
0x1801096da  mov     qword ptr [rsp+1D0h+var_188], r12
0x1801096df  lea     r9, [rsp+1D0h+Buf1+8]
0x1801096e4  lea     r8, [rbp+0D0h+var_150]
0x1801096e8  lea     rdx, [rsp+1D0h+var_1A0]
0x1801096ed  mov     rcx, rsi
0x1801096f0  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1801096f5  mov     edx, dword ptr [rsp+1D0h+Buf1]
0x1801096f9  test    edx, edx
0x1801096fb  setz    al
0x1801096fe  mov     rcx, [rbp+0D8h]; this
0x180109705  test    al, al
0x180109707  jz      short loc_180109721
0x180109709  mov     r9d, 8007000Dh; char *
0x18010970f  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180109716  mov     edx, 52Eh; void *
0x18010971b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180109721  mov     rax, qword ptr [rsp+1D0h+var_1A0]
0x180109726  mov     rcx, [rax]
0x180109729  lea     rcx, [rcx+rdx*4]; this
0x18010972d  mov     rax, [rbp+0D8h]
0x180109734  cmp     byte ptr [rcx+7], 0F6h
0x180109738  jz      short loc_180109755
0x18010973a  mov     r9d, 8007070Ch; char *
0x180109740  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x180109747  mov     edx, 52Fh; void *
0x18010974c  mov     rcx, rax; this
0x18010974f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180109755  xor     edx, edx; unsigned int *
0x180109757  call    ?Data@JsonValue@@QEAAPEAXPEAI@Z; JsonValue::Data(uint *)
0x18010975c  mov     rcx, rax
0x18010975f  mov     eax, [rdi+158h]
0x180109765  shl     eax, 8
0x180109768  or      [rcx], eax
0x18010976a  movups  xmm0, xmmword ptr cs:?k_telClientSyntheticProviderName@SyntheticTriggerDef@Diagnostics@Microsoft@@2V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::SyntheticTriggerDef::k_telClientSyntheticProviderName
0x180109771  movdqu  xmmword ptr [rbp+0D0h+var_150], xmm0
0x180109776  movaps  xmm6, xmmword ptr [rbp+0D0h+var_140]
0x18010977a  movdqa  xmmword ptr [rbp+0D0h+var_140], xmm6
0x18010977f  lea     rdx, [rbp+0D0h+var_150]
0x180109783  lea     rcx, [rbp+0D0h+var_140]
0x180109787  call    ?ICompare@String@Utils@Diagnostics@Microsoft@@SAJV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; Microsoft::Diagnostics::Utils::String::ICompare(std::wstring_view,std::wstring_view)
0x18010978c  mov     r12d, eax
0x18010978f  movups  xmm0, xmmword ptr [r15+30h]
0x180109794  movdqu  [rsp+1D0h+Buf1+8], xmm0
0x18010979a  mov     r8d, 10h; Size
0x1801097a0  lea     rdx, GUID_NULL; Buf2
0x1801097a7  lea     rcx, [rsp+1D0h+Buf1+8]; Buf1
0x1801097ac  call    memcmp_0
0x1801097b1  test    eax, eax
0x1801097b3  jnz     short loc_18010980B
0x1801097b5  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801097bc  movdqu  xmmword ptr [rbp+0D0h+var_150], xmm0
0x1801097c1  movdqa  xmm1, xmm6
0x1801097c5  psrldq  xmm1, 8
0x1801097ca  movq    r8, xmm1
0x1801097cf  movq    rdx, xmm6
0x1801097d4  lea     rcx, [rbp+0D0h+var_140]
0x1801097d8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W_K@Z; std::wstring::wstring(wchar_t const * const,unsigned __int64)
0x1801097dd  lea     rcx, [rbp+0D0h+var_140]
0x1801097e1  cmp     [rbp+0D0h+var_128], 7
0x1801097e6  cmova   rcx, [rbp+0D0h+var_140]; this
0x1801097eb  lea     rdx, [rbp+0D0h+var_150]; wchar_t *
0x1801097ef  call    ?NameToGuid@Performance@@YAJPEB_WAEAU_GUID@@@Z; Performance::NameToGuid(wchar_t const *,_GUID &)
0x1801097f4  test    eax, eax
0x1801097f6  js      short loc_180109802
0x1801097f8  movaps  xmm0, xmmword ptr [rbp+0D0h+var_150]
0x1801097fc  movdqa  [rsp+1D0h+Buf1+8], xmm0
0x180109802  lea     rcx, [rbp+0D0h+var_140]; this
0x180109806  call    ??1EscalationProperties@ScenarioDef@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties(void)
0x18010980b  movaps  xmm0, [rbp+0D0h+var_120]
0x18010980f  movdqa  [rbp+0D0h+var_120], xmm0
0x180109814  movdqa  xmmword ptr [rbp+0D0h+var_140], xmm6
0x180109819  lea     r9, [rbp+0D0h+var_120]
0x18010981d  lea     r8, [rbp+0D0h+var_140]
0x180109821  lea     rdx, [rsp+1D0h+Buf1+8]
0x180109826  lea     rcx, [rbp+0D0h+var_E0]
0x18010982a  call    ??0ETWTriggerDef@Diagnostics@Microsoft@@QEAA@AEBU_GUID@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@1@Z; Microsoft::Diagnostics::ETWTriggerDef::ETWTriggerDef(_GUID const &,std::wstring_view,std::wstring_view)
0x18010982f  nop
0x180109830  mov     ecx, 450h; Size
0x180109835  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010983a  mov     rdi, rax
0x18010983d  mov     qword ptr [rsp+1D0h+var_1A0], rax
0x180109842  xorps   xmm0, xmm0
0x180109845  movups  xmmword ptr [rax], xmm0
0x180109848  mov     dword ptr [rax+8], 1
0x18010984f  mov     dword ptr [rax+0Ch], 1
0x180109856  lea     rax, ??_7?$_Ref_count_obj2@VTimeTriggerInst@Diagnostics@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Diagnostics::TimeTriggerInst>::`vftable'
0x18010985d  mov     [rdi], rax
0x180109860  lea     rbx, [rdi+10h]
0x180109864  lea     rdx, [rbp+0D0h+var_E0]; struct Microsoft::Diagnostics::ETWTriggerDef *
0x180109868  mov     rcx, rbx; this
0x18010986b  call    ??0ETWTriggerInst@Diagnostics@Microsoft@@QEAA@AEBVETWTriggerDef@12@@Z; Microsoft::Diagnostics::ETWTriggerInst::ETWTriggerInst(Microsoft::Diagnostics::ETWTriggerDef const &)
0x180109870  nop
0x180109871  mov     [r14], rbx
0x180109874  mov     [r14+8], rdi
0x180109878  mov     [rsp+1D0h+var_180], 3
0x180109880  lea     rcx, [rbp+0D0h+var_100]; void *
0x180109884  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180109889  nop
0x18010988a  mov     rax, cs:off_18034A710; "ag"
0x180109891  mov     qword ptr [rbp+0D0h+var_150], rax
0x180109895  mov     ebx, 2
0x18010989a  mov     qword ptr [rbp+0D0h+var_150+8], rbx
0x18010989e  mov     qword ptr [rsp+1D0h+var_1A0], rsi
0x1801098a3  mov     dword ptr [rsp+1D0h+Buf1], r13d
0x1801098a8  mov     eax, dword ptr [rbp+0D0h+var_120+0Ch]
0x1801098ab  mov     dword ptr [rsp+1D0h+Buf1+4], eax
0x1801098af  lea     r9, [rbp+0D0h+var_150]
0x1801098b3  lea     r8, [rsp+1D0h+var_1A0]
0x1801098b8  lea     rdx, [rsp+1D0h+Buf1+8]
0x1801098bd  mov     rcx, rsi
0x1801098c0  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1801098c5  mov     eax, [rsp+1D0h+var_188]
0x1801098c9  test    eax, eax
0x1801098cb  jz      loc_18010A209
0x1801098d1  mov     rcx, [rbp+0D8h]; this
0x1801098d8  mov     r8d, eax
0x1801098db  mov     rax, qword ptr [rsp+1D0h+Buf1+8]
0x1801098e0  mov     rdx, [rax]
0x1801098e3  cmp     byte ptr [rdx+r8*4+7], 0FFh
0x1801098e9  jz      short loc_180109903
0x1801098eb  mov     r9d, 8007070Ch; char *
0x1801098f1  lea     r8, aOnecoreBaseTel_7; "onecore\\base\\telemetry\\utc\\service"...
0x1801098f8  mov     edx, 551h; void *
0x1801098fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180109903  mov     rax, cs:off_18034A720; "ikey"
0x18010990a  mov     qword ptr [rbp+0D0h+var_150], rax
0x18010990e  mov     edi, 4
0x180109913  mov     qword ptr [rbp+0D0h+var_150+8], rdi
0x180109917  lea     r9, [rbp+0D0h+var_150]
0x18010991b  lea     r8, [rsp+1D0h+Buf1+8]
0x180109920  lea     rdx, [rsp+1D0h+var_1A0]
0x180109925  mov     rcx, rsi
0x180109928  call    ??$find@$$V@JsonBuilder@@QEAA?AVJsonIterator@@AEBVJsonConstIterator@@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18010992d  mov     eax, dword ptr [rsp+1D0h+Buf1]
0x180109931  test    eax, eax
0x180109933  jz      short loc_1801099B1
0x180109935  mov     edx, eax
0x180109937  mov     rax, qword ptr [rsp+1D0h+var_1A0]
0x18010993c  mov     rcx, [rax]
0x18010993f  lea     rcx, [rcx+rdx*4]; this
0x180109943  cmp     byte ptr [rcx+7], 0F5h
0x180109947  jnz     short loc_180109968
0x180109949  mov     [rsp+1D0h+var_1A0], r13d
0x18010994e  lea     rdx, [rsp+1D0h+var_1A0]; unsigned int *
0x180109953  call    ?Data@JsonValue@@QEAAPEAXPEAI@Z; JsonValue::Data(uint *)
0x180109958  mov     rdx, rax
0x18010995b  mov     r8d, [rsp+1D0h+var_1A0]
0x180109960  shr     r8, 1
0x180109963  mov     al, r13b
0x180109966  jmp     short loc_180109970
  ... truncated ...
```
