# Microsoft::Diagnostics::AppIdMetadata::InlineUpdate(Microsoft::Diagnostics::ITriggerInst const &)

- ea: `0x18007e20c`
- end: `0x18007f0d1`
- name: `?InlineUpdate@AppIdMetadata@Diagnostics@Microsoft@@QEAAXAEBVITriggerInst@23@@Z`
- size: `3781`
- prototype: `void __fastcall(Microsoft::Diagnostics::AppIdMetadata *__hidden this, const struct Microsoft::Diagnostics::ITriggerInst *)`
- caller_count: `2`
- callee_count: `30`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d03a8`
- `0x18029b5f0`

## callees

- `0x18001cf30`
- `0x18001d160`
- `0x180020fbc`
- `0x1800326cc`
- `0x18003fd8c`
- `0x1800498f0`
- `0x18004a750`
- `0x18004cf30`
- `0x180053740`
- `0x180057d34`
- `0x1800717ec`
- `0x18007e20c`
- `0x18007f0d8`
- `0x180080054`
- `0x1800bc2e0`
- `0x1800dd528`
- `0x1800dd99c`
- `0x1800dd9d4`
- `0x180123a58`
- `0x18012de40`
- `0x18012de64`
- `0x1801991a4`
- `0x1801f8478`
- `0x1801f8a90`
- `0x1801f8c5c`
- `0x1801f907c`
- `0x1801f91ec`
- `0x1801f9f1c`
- `0x1801fcf98`
- `0x180346010`

## string_xrefs

- `0x18007e55c`: `SessionCreateTime`
- `0x18007e69c`: `CommandLine`
- `0x18007e792`: `UserSid`
- `0x18007e2c3`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e387`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e3c0`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e42a`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e463`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e502`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e53b`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e5a5`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e5de`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e645`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e67e`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e6e6`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e74a`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e7da`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e836`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e8b3`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e90f`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e996`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007e9f2`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ea55`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007eaac`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007eb13`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007eb4c`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ebb8`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ebf1`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ed01`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ed3c`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007eda9`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ede5`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ee4e`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ee8a`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007ef94`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`
- `0x18007eff6`: `onecore\base\telemetry\utc\service\metadata\appidmetadata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Microsoft::Diagnostics::AppIdMetadata::InlineUpdate(
        Microsoft::Diagnostics::AppIdMetadata *this,
        const struct Microsoft::Diagnostics::ITriggerInst *a2)
{
  char *v4; // rsi
  _QWORD *v5; // rax
  __int64 v6; // rcx
  __int64 *v7; // rax
  __int64 v8; // rdi
  __int64 v9; // rbx
  _QWORD *v10; // rax
  wil::details::in1diag3 *v11; // r10
  unsigned int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rdx
  wil::details::in1diag3 *v15; // r10
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  wil::details::in1diag3 *v19; // r10
  __int64 v20; // rax
  __int64 v21; // rdx
  wil::details::in1diag3 *v22; // r10
  __int64 v23; // rax
  __int64 v24; // rdx
  wil::details::in1diag3 *v25; // r10
  __int64 v26; // rax
  __int64 v27; // rdx
  JsonValue *v28; // rcx
  char v29; // bl
  void *v30; // rdx
  unsigned __int64 v31; // r8
  char v32; // al
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rdx
  JsonValue *v36; // rcx
  void *v37; // rdx
  unsigned __int64 v38; // r8
  char v39; // al
  __int64 v40; // rax
  __int64 v41; // rdx
  JsonValue *v42; // rcx
  void *v43; // rdx
  unsigned __int64 v44; // r8
  char v45; // al
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 v48; // rdx
  JsonValue *v49; // rcx
  const void *v50; // rdx
  char *v51; // r8
  char v52; // al
  __int64 v53; // rax
  __int64 v54; // rdx
  JsonValue *v55; // rcx
  const void *v56; // rax
  char *v57; // r8
  __int64 v58; // rax
  __int64 v59; // rdx
  wil::details::in1diag3 *v60; // r10
  __int64 v61; // rax
  __int64 v62; // rdx
  wil::details::in1diag3 *v63; // r10
  __int64 CacheEntry; // rax
  __int64 *v65; // rax
  __int64 v66; // rdi
  __int64 v67; // rbx
  _QWORD *v68; // rax
  wil::details::in1diag3 *v69; // r10
  __int64 v70; // rax
  __int64 v71; // rdx
  wil::details::in1diag3 *v72; // r10
  __int64 v73; // rax
  __int64 v74; // rdx
  wil::details::in1diag3 *v75; // r10
  _QWORD *v76; // rax
  __int64 v77; // rcx
  __int64 *v78; // rax
  __int64 v79; // rdi
  __int64 v80; // rbx
  _QWORD *FullyQualifiedName; // rax
  JsonValue *v82; // rcx
  void *v83; // r12
  unsigned __int64 v84; // rsi
  char v85; // al
  _DWORD *v86; // rdi
  __int64 v87; // rax
  std::_Ref_count_base *v88; // rcx
  int v89[4]; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v90[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v91; // [rsp+38h] [rbp-C8h]
  char v92[8]; // [rsp+40h] [rbp-C0h] BYREF
  int v93; // [rsp+48h] [rbp-B8h]
  _BYTE v94[16]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v95[2]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v96[16]; // [rsp+70h] [rbp-90h] BYREF
  const char *v97; // [rsp+80h] [rbp-80h] BYREF
  __int64 v98; // [rsp+88h] [rbp-78h]
  _BYTE v99[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v100[4]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v101; // [rsp+C4h] [rbp-3Ch]
  unsigned int v102; // [rsp+C8h] [rbp-38h]
  int v103; // [rsp+CCh] [rbp-34h]
  __int64 v104; // [rsp+D0h] [rbp-30h]
  __int64 v105; // [rsp+D8h] [rbp-28h]
  __int64 v106; // [rsp+E0h] [rbp-20h]
  char v107[16]; // [rsp+E8h] [rbp-18h] BYREF
  char v108[56]; // [rsp+F8h] [rbp-8h] BYREF
  char *v109[4]; // [rsp+130h] [rbp+30h] BYREF
  char *v110; // [rsp+150h] [rbp+50h] BYREF
  char *v111; // [rsp+170h] [rbp+70h] BYREF
  unsigned int v112; // [rsp+190h] [rbp+90h]
  unsigned int v113; // [rsp+194h] [rbp+94h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v96, (char *)this + 408);
  if ( !*(_BYTE *)((*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2)
                 + 48) )
  {
    v4 = (char *)a2 + 16;
    v95[0] = L"data";
    v95[1] = 4;
    *(_QWORD *)v90 = (char *)a2 + 16;
    v91 = 0;
    JsonBuilder::find<>((char *)a2 + 16, v92, v90, v95);
    if ( !v93 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11A,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
        (const char *)0x80070490LL,
        v89[0]);
    v5 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 80LL))(a2);
    v6 = *v5 - *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1;
    if ( *v5 == *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1 )
      v6 = v5[1] - *(_QWORD *)Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data4;
    if ( v6 )
    {
      v76 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 80LL))(a2);
      v77 = *v76 - *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid.Data1;
      if ( *v76 == *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid.Data1 )
        v77 = v76[1] - *(_QWORD *)Microsoft::Diagnostics::EventBasedMetadata::k_appTelemetryMetadataProviderGuid.Data4;
      if ( !v77 )
      {
        v78 = (__int64 *)std::wstring::operator std::wstring_view((char *)this + 128, v94);
        v79 = *v78;
        v80 = v78[1];
        FullyQualifiedName = (_QWORD *)Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(a2, v89);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(
                                *FullyQualifiedName,
                                FullyQualifiedName[1],
                                v79,
                                v80) )
        {
          *(_QWORD *)v89 = L"AccountId";
          *(_QWORD *)&v89[2] = 9;
          JsonBuilder::find<>((char *)a2 + 16, &v97, v92, v89);
          if ( !(_DWORD)v98 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1A9,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          v82 = (JsonValue *)(*(_QWORD *)v97 + 4LL * (unsigned int)v98);
          if ( *((_BYTE *)v82 + 7) == 0xF5 )
          {
            v90[0] = 0;
            v83 = JsonValue::Data(v82, v90);
            v84 = (unsigned __int64)v90[0] >> 1;
            v85 = 0;
          }
          else
          {
            v83 = 0;
            v84 = 0;
            v85 = 1;
          }
          if ( v85 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1AA,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          v89[0] = *((_DWORD *)a2 + 170);
          *(_QWORD *)&v89[2] = *((_QWORD *)a2 + 84);
          Microsoft::Diagnostics::AppIdMetadata::FindProcess(this, v95, v89);
          if ( v95[0] != *((_QWORD *)this + 40) )
          {
            v86 = operator new(0x30u);
            *(_QWORD *)v90 = v86;
            *(_OWORD *)v86 = 0;
            v86[2] = 1;
            v86[3] = 1;
            *(_QWORD *)v86 = &std::_Ref_count_obj2<std::wstring const>::`vftable';
            std::wstring::wstring(v86 + 4, v83, v84);
            v87 = v95[0];
            *(_QWORD *)(v95[0] + 120LL) = v86 + 4;
            v88 = *(std::_Ref_count_base **)(v87 + 128);
            *(_QWORD *)(v87 + 128) = v86;
            if ( v88 )
              std::_Ref_count_base::_Decref(v88);
          }
        }
      }
    }
    else
    {
      v7 = (__int64 *)std::wstring::operator std::wstring_view((char *)this + 64, v89);
      v8 = *v7;
      v9 = v7[1];
      v10 = (_QWORD *)Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(a2, &v97);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(*v10, v10[1], v8, v9) )
      {
        *(_QWORD *)v90 = 0;
        v97 = L"InstanceId";
        v98 = 10;
        JsonBuilder::find<>((char *)a2 + 16, v89, v92, &v97);
        if ( !v89[2] )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x124,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x80070490LL,
            v89[0]);
        if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                                 **(_QWORD **)v89 + 4LL * (unsigned int)v89[2],
                                 v90) )
          wil::details::in1diag3::Throw_Hr(
            v11,
            (void *)0x125,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x8007070CLL,
            v89[0]);
        v12 = v90[0];
        LODWORD(v97) = v90[0];
        *(_QWORD *)v90 = 0;
        *(_QWORD *)v89 = L"ProcessStartKey";
        *(_QWORD *)&v89[2] = 15;
        v13 = JsonBuilder::find<>((char *)a2 + 16, v94, v92, v89);
        v14 = *(unsigned int *)(v13 + 8);
        if ( !(_DWORD)v14 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x12A,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x80070490LL,
            v89[0]);
        if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v13 + 4 * v14, v90) )
          wil::details::in1diag3::Throw_Hr(
            v15,
            (void *)0x12B,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
            (const char *)0x8007070CLL,
            v89[0]);
        v16 = *(_QWORD *)v90;
        v98 = *(_QWORD *)v90;
        Microsoft::Diagnostics::AppIdMetadata::FindProcess(this, v95, &v97);
        if ( v95[0] == *((_QWORD *)this + 40) )
        {
          Microsoft::Diagnostics::AppIdMetadata::ProcessInfo::ProcessInfo((Microsoft::Diagnostics::AppIdMetadata::ProcessInfo *)v100);
          v101 = v12;
          v105 = v16;
          *(_QWORD *)v90 = 0;
          *(_QWORD *)v89 = L"SessionId";
          *(_QWORD *)&v89[2] = 9;
          v17 = JsonBuilder::find<>((char *)a2 + 16, v94, v92, v89);
          v18 = *(unsigned int *)(v17 + 8);
          if ( !(_DWORD)v18 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x13A,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v17 + 4 * v18, v90) )
            wil::details::in1diag3::Throw_Hr(
              v19,
              (void *)0x13B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          v102 = v90[0];
          *(_QWORD *)v90 = 0;
          *(_QWORD *)v89 = L"SessionCreateTime";
          *(_QWORD *)&v89[2] = 17;
          v20 = JsonBuilder::find<>((char *)a2 + 16, v94, v92, v89);
          v21 = *(unsigned int *)(v20 + 8);
          if ( !(_DWORD)v21 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x140,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v20 + 4 * v21, v90) )
            wil::details::in1diag3::Throw_Hr(
              v22,
              (void *)0x141,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          v104 = *(_QWORD *)v90;
          *(_QWORD *)v90 = 0;
          *(_QWORD *)v89 = L"InstanceStartTime";
          *(_QWORD *)&v89[2] = 17;
          v23 = JsonBuilder::find<>((char *)a2 + 16, v94, v92, v89);
          v24 = *(unsigned int *)(v23 + 8);
          if ( !(_DWORD)v24 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x146,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v23 + 4 * v24, v90) )
            wil::details::in1diag3::Throw_Hr(
              v25,
              (void *)0x147,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          v106 = *(_QWORD *)v90;
          *(_QWORD *)v89 = L"CommandLine";
          *(_QWORD *)&v89[2] = 11;
          v26 = JsonBuilder::find<>(v4, v94, v92, v89);
          v27 = *(unsigned int *)(v26 + 8);
          if ( !(_DWORD)v27 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x14C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          v28 = (JsonValue *)(**(_QWORD **)v26 + 4 * v27);
          v29 = 1;
          if ( *((_BYTE *)v28 + 7) == 0xF5 )
          {
            v90[0] = 0;
            v30 = JsonValue::Data(v28, v90);
            v31 = (unsigned __int64)v90[0] >> 1;
            v32 = 0;
          }
          else
          {
            v30 = 0;
            v31 = 0;
            v32 = 1;
          }
          if ( v32 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x14D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          v33 = std::wstring::wstring(v99, v30, v31);
          *(_OWORD *)v89 = *(_OWORD *)std::wstring::operator std::wstring_view(v33, v94);
          v103 = Microsoft::Diagnostics::AppIdMetadata::CalculateCommandLineHash(v89);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v99);
          *(_QWORD *)v89 = L"UserSid";
          *(_QWORD *)&v89[2] = 7;
          v34 = JsonBuilder::find<>(v4, v94, v92, v89);
          v35 = *(unsigned int *)(v34 + 8);
          if ( !(_DWORD)v35 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x152,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          v36 = (JsonValue *)(**(_QWORD **)v34 + 4 * v35);
          if ( *((_BYTE *)v36 + 7) == 0xF5 )
          {
            v90[0] = 0;
            v37 = JsonValue::Data(v36, v90);
            v38 = (unsigned __int64)v90[0] >> 1;
            v39 = 0;
          }
          else
          {
            v37 = 0;
            v38 = 0;
            v39 = 1;
          }
          if ( v39 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x153,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          std::wstring::wstring(v99, v37, v38);
          std::wstring::operator=(v108, v99);
          Microsoft::Diagnostics::AppIdKey::AppIdKey((Microsoft::Diagnostics::AppIdKey *)v109);
          *(_QWORD *)v89 = L"ImageFileName";
          *(_QWORD *)&v89[2] = 13;
          v40 = JsonBuilder::find<>(v4, v94, v92, v89);
          v41 = *(unsigned int *)(v40 + 8);
          if ( !(_DWORD)v41 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x15C,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          v42 = (JsonValue *)(**(_QWORD **)v40 + 4 * v41);
          if ( *((_BYTE *)v42 + 7) == 0xF5 )
          {
            v90[0] = 0;
            v43 = JsonValue::Data(v42, v90);
            v44 = (unsigned __int64)v90[0] >> 1;
            v45 = 0;
          }
          else
          {
            v43 = 0;
            v44 = 0;
            v45 = 1;
          }
          if ( v45 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x15D,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          std::wstring::wstring(&v97, v43, v44);
          Microsoft::Diagnostics::Utils::String::ToLowercase(&v97);
          v46 = std::wstring::operator std::wstring_view(&v97, v94);
          std::wstring::_Assign<wchar_t>(v109, *(const void **)v46, *(char **)(v46 + 8));
          *(_QWORD *)v89 = L"PackageName";
          *(_QWORD *)&v89[2] = 11;
          v47 = JsonBuilder::find<>(v4, v94, v92, v89);
          v48 = *(unsigned int *)(v47 + 8);
          if ( !(_DWORD)v48 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x164,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          v49 = (JsonValue *)(**(_QWORD **)v47 + 4 * v48);
          if ( *((_BYTE *)v49 + 7) == 0xF5 )
          {
            v90[0] = 0;
            v50 = JsonValue::Data(v49, v90);
            v51 = (char *)((unsigned __int64)v90[0] >> 1);
            v52 = 0;
          }
          else
          {
            v50 = 0;
            v51 = 0;
            v52 = 1;
          }
          if ( v52 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x165,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          std::wstring::_Assign<wchar_t>(&v110, v50, v51);
          *(_QWORD *)v89 = L"PRAID";
          *(_QWORD *)&v89[2] = 5;
          v53 = JsonBuilder::find<>(v4, v94, v92, v89);
          v54 = *(unsigned int *)(v53 + 8);
          if ( !(_DWORD)v54 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x16A,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          v55 = (JsonValue *)(**(_QWORD **)v53 + 4 * v54);
          if ( *((_BYTE *)v55 + 7) == 0xF5 )
          {
            v90[0] = 0;
            v56 = JsonValue::Data(v55, v90);
            v57 = (char *)((unsigned __int64)v90[0] >> 1);
            v29 = 0;
          }
          else
          {
            v56 = 0;
            v57 = 0;
          }
          if ( v29 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x16B,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          std::wstring::_Assign<wchar_t>(&v111, v56, v57);
          *(_QWORD *)v90 = 0;
          *(_QWORD *)v89 = L"ImageChecksum";
          *(_QWORD *)&v89[2] = 13;
          v58 = JsonBuilder::find<>(v4, v94, v92, v89);
          v59 = *(unsigned int *)(v58 + 8);
          if ( !(_DWORD)v59 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x170,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v58 + 4 * v59, v90) )
            wil::details::in1diag3::Throw_Hr(
              v60,
              (void *)0x171,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          v112 = v90[0];
          *(_QWORD *)v90 = 0;
          *(_QWORD *)v89 = L"ImageTimeDateStamp";
          *(_QWORD *)&v89[2] = 18;
          v61 = JsonBuilder::find<>(v4, v94, v92, v89);
          v62 = *(unsigned int *)(v61 + 8);
          if ( !(_DWORD)v62 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x176,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v61 + 4 * v62, v90) )
            wil::details::in1diag3::Throw_Hr(
              v63,
              (void *)0x177,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          v113 = v90[0];
          CacheEntry = Microsoft::Diagnostics::AppIdCache::GetCacheEntry((char *)this + 168, v89, v109);
          Microsoft::Diagnostics::IteratorSmartRef<Microsoft::Diagnostics::AppIdCache,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Microsoft::Diagnostics::AppIdCache::AppIdCacheEntry>>>>>::operator=(
            v107,
            CacheEntry);
          Microsoft::Diagnostics::IteratorSmartRef<Microsoft::Diagnostics::AppIdCache,std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned __int64 const,Microsoft::Diagnostics::AppIdCache::AppIdCacheEntry>>>>>::Clear(v89);
          Microsoft::Diagnostics::AppIdMetadata::AddProcess(this);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)&v97);
          Microsoft::Diagnostics::EscalationWorkItem::DetailedResults::ActionRecord::~ActionRecord((Microsoft::Diagnostics::EscalationWorkItem::DetailedResults::ActionRecord *)v109);
          Microsoft::Diagnostics::ScenarioDef::EscalationProperties::~EscalationProperties((Microsoft::Diagnostics::ScenarioDef::EscalationProperties *)v99);
          Microsoft::Diagnostics::AppIdMetadata::ProcessInfo::~ProcessInfo((Microsoft::Diagnostics::AppIdMetadata::ProcessInfo *)v100);
        }
      }
      else
      {
        v65 = (__int64 *)std::wstring::operator std::wstring_view((char *)this + 96, v94);
        v66 = *v65;
        v67 = v65[1];
        v68 = (_QWORD *)Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(a2, v89);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(*v68, v68[1], v66, v67) )
        {
          *(_QWORD *)v90 = 0;
          *(_QWORD *)v89 = L"AppStateChange";
          *(_QWORD *)&v89[2] = 14;
          JsonBuilder::find<>((char *)a2 + 16, &v97, v92, v89);
          if ( !(_DWORD)v98 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x185,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x80070490LL,
              v89[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                                   *(_QWORD *)v97 + 4LL * (unsigned int)v98,
                                   v90) )
            wil::details::in1diag3::Throw_Hr(
              v69,
              (void *)0x186,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
              (const char *)0x8007070CLL,
              v89[0]);
          if ( v90[0] == 3 )
          {
            *(_QWORD *)v90 = 0;
            *(_QWORD *)v89 = L"InstanceId";
            *(_QWORD *)&v89[2] = 10;
            v70 = JsonBuilder::find<>((char *)a2 + 16, v94, v92, v89);
            v71 = *(unsigned int *)(v70 + 8);
            if ( !(_DWORD)v71 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x18E,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x80070490LL,
                v89[0]);
            if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v70 + 4 * v71, v90) )
              wil::details::in1diag3::Throw_Hr(
                v72,
                (void *)0x18F,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x8007070CLL,
                v89[0]);
            LODWORD(v97) = v90[0];
            *(_QWORD *)v90 = 0;
            *(_QWORD *)v89 = L"ProcessStartKey";
            *(_QWORD *)&v89[2] = 15;
            v73 = JsonBuilder::find<>((char *)a2 + 16, v94, v92, v89);
            v74 = *(unsigned int *)(v73 + 8);
            if ( !(_DWORD)v74 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x194,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x80070490LL,
                v89[0]);
            if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v73 + 4 * v74, v90) )
              wil::details::in1diag3::Throw_Hr(
                v75,
                (void *)0x195,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\metadata\\appidmetadata.cpp",
                (const char *)0x8007070CLL,
                v89[0]);
            v98 = *(_QWORD *)v90;
            Microsoft::Diagnostics::AppIdMetadata::FindProcess(this, v95, &v97);
            if ( v95[0] != *((_QWORD *)this + 40) && !*(_BYTE *)(v95[0] + 24LL) )
              Microsoft::Diagnostics::AppIdMetadata::MarkProcessEnded(this);
          }
        }
      }
    }
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v96);
}

```

## disassembly

```asm
0x18007e20c  mov     [rsp-8+arg_10], rbx
0x18007e211  push    rbp
0x18007e212  push    rsi
0x18007e213  push    rdi
0x18007e214  push    r12
0x18007e216  push    r13
0x18007e218  push    r14
0x18007e21a  push    r15
0x18007e21c  lea     rbp, [rsp-0B0h]
0x18007e224  sub     rsp, 1B0h
0x18007e22b  mov     rax, cs:__security_cookie
0x18007e232  xor     rax, rsp
0x18007e235  mov     [rbp+0E0h+var_40], rax
0x18007e23c  mov     r14, rdx
0x18007e23f  mov     r15, rcx
0x18007e242  xor     r13d, r13d
0x18007e245  lea     rdx, [rcx+198h]
0x18007e24c  lea     rcx, [rsp+1E0h+var_170]
0x18007e251  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x18007e256  nop
0x18007e257  mov     rax, [r14]
0x18007e25a  mov     rcx, r14
0x18007e25d  mov     rax, [rax+78h]
0x18007e261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e266  cmp     [rax+30h], r13b
0x18007e26a  jnz     loc_18007F09C
0x18007e270  lea     rsi, [r14+10h]
0x18007e274  lea     rax, aData_0; "data"
0x18007e27b  mov     [rsp+1E0h+var_180], rax
0x18007e280  mov     [rsp+1E0h+var_178], 4
0x18007e289  mov     qword ptr [rsp+1E0h+var_1B0], rsi
0x18007e28e  mov     [rsp+1E0h+var_1A8], r13d
0x18007e293  lea     r9, [rsp+1E0h+var_180]
0x18007e298  lea     r8, [rsp+1E0h+var_1B0]
0x18007e29d  lea     rdx, [rsp+1E0h+var_1A0]
0x18007e2a2  mov     rcx, rsi
0x18007e2a5  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e2aa  cmp     [rsp+1E0h+var_198], r13d
0x18007e2af  setz    al
0x18007e2b2  mov     rcx, [rbp+0E8h]; this
0x18007e2b9  test    al, al
0x18007e2bb  jz      short loc_18007E2D5
0x18007e2bd  mov     r9d, 80070490h; char *
0x18007e2c3  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e2ca  mov     edx, 11Ah; void *
0x18007e2cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e2d5  mov     rax, [r14]
0x18007e2d8  mov     rcx, r14
0x18007e2db  mov     rax, [rax+50h]
0x18007e2df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e2e4  mov     rcx, [rax]
0x18007e2e7  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data1; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x18007e2ee  jnz     short loc_18007E2FB
0x18007e2f0  mov     rcx, [rax+8]
0x18007e2f4  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data4; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x18007e2fb  test    rcx, rcx
0x18007e2fe  jnz     loc_18007EEE2
0x18007e304  lea     rcx, [r15+40h]
0x18007e308  lea     rdx, [rsp+1E0h+var_1C0]
0x18007e30d  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18007e312  mov     rdi, [rax]
0x18007e315  mov     rbx, [rax+8]
0x18007e319  lea     rdx, [rbp+0E0h+var_160]
0x18007e31d  mov     rcx, r14
0x18007e320  call    ?GetFullyQualifiedName@ITriggerInst@Diagnostics@Microsoft@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@XZ; Microsoft::Diagnostics::ITriggerInst::GetFullyQualifiedName(void)
0x18007e325  mov     r9, rbx
0x18007e328  mov     r8, rdi
0x18007e32b  mov     rdx, [rax+8]
0x18007e32f  mov     rcx, [rax]
0x18007e332  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x18007e337  test    al, al
0x18007e339  jz      loc_18007EC7C
0x18007e33f  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007e344  lea     rax, aInstanceid_0; "InstanceId"
0x18007e34b  mov     [rbp+0E0h+var_160], rax
0x18007e34f  mov     [rbp+0E0h+var_158], 0Ah
0x18007e357  lea     r9, [rbp+0E0h+var_160]
0x18007e35b  lea     r8, [rsp+1E0h+var_1A0]
0x18007e360  lea     rdx, [rsp+1E0h+var_1C0]
0x18007e365  mov     rcx, rsi
0x18007e368  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e36d  mov     edx, [rsp+1E0h+var_1C0+8]
0x18007e371  test    edx, edx
0x18007e373  setz    al
0x18007e376  mov     rcx, [rbp+0E8h]; this
0x18007e37d  test    al, al
0x18007e37f  jz      short loc_18007E399
0x18007e381  mov     r9d, 80070490h; char *
0x18007e387  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e38e  mov     edx, 124h; void *
0x18007e393  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e399  mov     r10, [rbp+0E8h]
0x18007e3a0  mov     rax, qword ptr [rsp+1E0h+var_1C0]
0x18007e3a5  mov     rcx, [rax]
0x18007e3a8  lea     rcx, [rcx+rdx*4]
0x18007e3ac  lea     rdx, [rsp+1E0h+var_1B0]
0x18007e3b1  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007e3b6  test    al, al
0x18007e3b8  jnz     short loc_18007E3D5
0x18007e3ba  mov     r9d, 8007070Ch; char *
0x18007e3c0  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e3c7  mov     edx, 125h; void *
0x18007e3cc  mov     rcx, r10; this
0x18007e3cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e3d5  mov     rdi, qword ptr [rsp+1E0h+var_1B0]
0x18007e3da  mov     dword ptr [rbp+0E0h+var_160], edi
0x18007e3dd  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007e3e2  lea     rax, aProcessstartke; "ProcessStartKey"
0x18007e3e9  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007e3ee  mov     qword ptr [rsp+1E0h+var_1C0+8], 0Fh
0x18007e3f7  lea     r9, [rsp+1E0h+var_1C0]
0x18007e3fc  lea     r8, [rsp+1E0h+var_1A0]
0x18007e401  lea     rdx, [rsp+1E0h+var_190]
0x18007e406  mov     rcx, rsi
0x18007e409  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e40e  movups  xmm1, xmmword ptr [rax]
0x18007e411  mov     edx, [rax+8]
0x18007e414  test    edx, edx
0x18007e416  setz    al
0x18007e419  mov     rcx, [rbp+0E8h]; this
0x18007e420  test    al, al
0x18007e422  jz      short loc_18007E43C
0x18007e424  mov     r9d, 80070490h; char *
0x18007e42a  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e431  mov     edx, 12Ah; void *
0x18007e436  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e43c  mov     r10, [rbp+0E8h]
0x18007e443  movq    rax, xmm1
0x18007e448  mov     rcx, [rax]
0x18007e44b  lea     rcx, [rcx+rdx*4]
0x18007e44f  lea     rdx, [rsp+1E0h+var_1B0]
0x18007e454  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007e459  test    al, al
0x18007e45b  jnz     short loc_18007E478
0x18007e45d  mov     r9d, 8007070Ch; char *
0x18007e463  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e46a  mov     edx, 12Bh; void *
0x18007e46f  mov     rcx, r10; this
0x18007e472  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e478  mov     rbx, qword ptr [rsp+1E0h+var_1B0]
0x18007e47d  mov     [rbp+0E0h+var_158], rbx
0x18007e481  lea     r8, [rbp+0E0h+var_160]
0x18007e485  lea     rdx, [rsp+1E0h+var_180]
0x18007e48a  mov     rcx, r15
0x18007e48d  call    ?FindProcess@AppIdMetadata@Diagnostics@Microsoft@@AEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBKUProcessInfo@AppIdMetadata@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@AEBUProcessKey@@@Z; Microsoft::Diagnostics::AppIdMetadata::FindProcess(ProcessKey const &)
0x18007e492  mov     rax, [r15+140h]
0x18007e499  cmp     [rsp+1E0h+var_180], rax
0x18007e49e  jnz     loc_18007F09C
0x18007e4a4  lea     rcx, [rbp+0E0h+var_120]; this
0x18007e4a8  call    ??0ProcessInfo@AppIdMetadata@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::AppIdMetadata::ProcessInfo::ProcessInfo(void)
0x18007e4ad  nop
0x18007e4ae  mov     [rbp+0E0h+var_11C], edi
0x18007e4b1  mov     [rbp+0E0h+var_108], rbx
0x18007e4b5  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007e4ba  lea     rax, aSessionid; "SessionId"
0x18007e4c1  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007e4c6  mov     qword ptr [rsp+1E0h+var_1C0+8], 9
0x18007e4cf  lea     r9, [rsp+1E0h+var_1C0]
0x18007e4d4  lea     r8, [rsp+1E0h+var_1A0]
0x18007e4d9  lea     rdx, [rsp+1E0h+var_190]
0x18007e4de  mov     rcx, rsi
0x18007e4e1  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e4e6  movups  xmm1, xmmword ptr [rax]
0x18007e4e9  mov     edx, [rax+8]
0x18007e4ec  test    edx, edx
0x18007e4ee  setz    al
0x18007e4f1  mov     rcx, [rbp+0E8h]; this
0x18007e4f8  test    al, al
0x18007e4fa  jz      short loc_18007E514
0x18007e4fc  mov     r9d, 80070490h; char *
0x18007e502  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e509  mov     edx, 13Ah; void *
0x18007e50e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e514  mov     r10, [rbp+0E8h]
0x18007e51b  movq    rax, xmm1
0x18007e520  mov     rcx, [rax]
0x18007e523  lea     rcx, [rcx+rdx*4]
0x18007e527  lea     rdx, [rsp+1E0h+var_1B0]
0x18007e52c  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007e531  test    al, al
0x18007e533  jnz     short loc_18007E550
0x18007e535  mov     r9d, 8007070Ch; char *
0x18007e53b  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e542  mov     edx, 13Bh; void *
0x18007e547  mov     rcx, r10; this
0x18007e54a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e550  mov     eax, [rsp+1E0h+var_1B0]
0x18007e554  mov     [rbp+0E0h+var_118], eax
0x18007e557  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007e55c  lea     rax, aSessioncreatet; "SessionCreateTime"
0x18007e563  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007e568  mov     ebx, 11h
0x18007e56d  mov     qword ptr [rsp+1E0h+var_1C0+8], rbx
0x18007e572  lea     r9, [rsp+1E0h+var_1C0]
0x18007e577  lea     r8, [rsp+1E0h+var_1A0]
0x18007e57c  lea     rdx, [rsp+1E0h+var_190]
0x18007e581  mov     rcx, rsi
0x18007e584  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e589  movups  xmm1, xmmword ptr [rax]
0x18007e58c  mov     edx, [rax+8]
0x18007e58f  test    edx, edx
0x18007e591  setz    al
0x18007e594  mov     rcx, [rbp+0E8h]; this
0x18007e59b  test    al, al
0x18007e59d  jz      short loc_18007E5B7
0x18007e59f  mov     r9d, 80070490h; char *
0x18007e5a5  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e5ac  mov     edx, 140h; void *
0x18007e5b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e5b7  mov     r10, [rbp+0E8h]
0x18007e5be  movq    rax, xmm1
0x18007e5c3  mov     rcx, [rax]
0x18007e5c6  lea     rcx, [rcx+rdx*4]
0x18007e5ca  lea     rdx, [rsp+1E0h+var_1B0]
0x18007e5cf  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007e5d4  test    al, al
0x18007e5d6  jnz     short loc_18007E5F3
0x18007e5d8  mov     r9d, 8007070Ch; char *
0x18007e5de  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e5e5  mov     edx, 141h; void *
0x18007e5ea  mov     rcx, r10; this
0x18007e5ed  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e5f3  mov     rax, qword ptr [rsp+1E0h+var_1B0]
0x18007e5f8  mov     [rbp+0E0h+var_110], rax
0x18007e5fc  mov     qword ptr [rsp+1E0h+var_1B0], r13
0x18007e601  lea     rax, aInstancestartt; "InstanceStartTime"
0x18007e608  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007e60d  mov     qword ptr [rsp+1E0h+var_1C0+8], rbx
0x18007e612  lea     r9, [rsp+1E0h+var_1C0]
0x18007e617  lea     r8, [rsp+1E0h+var_1A0]
0x18007e61c  lea     rdx, [rsp+1E0h+var_190]
0x18007e621  mov     rcx, rsi
0x18007e624  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e629  movups  xmm1, xmmword ptr [rax]
0x18007e62c  mov     edx, [rax+8]
0x18007e62f  test    edx, edx
0x18007e631  setz    al
0x18007e634  mov     rcx, [rbp+0E8h]; this
0x18007e63b  test    al, al
0x18007e63d  jz      short loc_18007E657
0x18007e63f  mov     r9d, 80070490h; char *
0x18007e645  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e64c  mov     edx, 146h; void *
0x18007e651  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e657  mov     r10, [rbp+0E8h]
0x18007e65e  movq    rax, xmm1
0x18007e663  mov     rcx, [rax]
0x18007e666  lea     rcx, [rcx+rdx*4]
0x18007e66a  lea     rdx, [rsp+1E0h+var_1B0]
0x18007e66f  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18007e674  test    al, al
0x18007e676  jnz     short loc_18007E693
0x18007e678  mov     r9d, 8007070Ch; char *
0x18007e67e  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e685  mov     edx, 147h; void *
0x18007e68a  mov     rcx, r10; this
0x18007e68d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e693  mov     rax, qword ptr [rsp+1E0h+var_1B0]
0x18007e698  mov     [rbp+0E0h+var_100], rax
0x18007e69c  lea     rax, aCommandline; "CommandLine"
0x18007e6a3  mov     qword ptr [rsp+1E0h+var_1C0], rax; int
0x18007e6a8  mov     r14d, 0Bh
0x18007e6ae  mov     qword ptr [rsp+1E0h+var_1C0+8], r14
0x18007e6b3  lea     r9, [rsp+1E0h+var_1C0]
0x18007e6b8  lea     r8, [rsp+1E0h+var_1A0]
0x18007e6bd  lea     rdx, [rsp+1E0h+var_190]
0x18007e6c2  mov     rcx, rsi
0x18007e6c5  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18007e6ca  movups  xmm1, xmmword ptr [rax]
0x18007e6cd  mov     edx, [rax+8]
0x18007e6d0  test    edx, edx
0x18007e6d2  setz    al
0x18007e6d5  mov     rcx, [rbp+0E8h]; this
0x18007e6dc  test    al, al
0x18007e6de  jz      short loc_18007E6F8
0x18007e6e0  mov     r9d, 80070490h; char *
0x18007e6e6  lea     r8, aOnecoreBaseTel_71; "onecore\\base\\telemetry\\utc\\service"...
0x18007e6ed  mov     edx, 14Ch; void *
0x18007e6f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007e6f8  movq    rax, xmm1
0x18007e6fd  mov     rcx, [rax]
0x18007e700  lea     rcx, [rcx+rdx*4]; this
0x18007e704  mov     ebx, 1
0x18007e709  mov     dil, 0F5h
0x18007e70c  cmp     [rcx+7], dil
0x18007e710  jnz     short loc_18007E731
0x18007e712  mov     [rsp+1E0h+var_1B0], r13d
0x18007e717  lea     rdx, [rsp+1E0h+var_1B0]; unsigned int *
0x18007e71c  call    ?Data@JsonValue@@QEAAPEAXPEAI@Z; JsonValue::Data(uint *)
0x18007e721  mov     rdx, rax
0x18007e724  mov     r8d, [rsp+1E0h+var_1B0]
0x18007e729  shr     r8, 1
0x18007e72c  mov     al, r13b
0x18007e72f  jmp     short loc_18007E739
0x18007e731  mov     rdx, r13
0x18007e734  mov     r8, r13
0x18007e737  mov     al, bl
0x18007e739  mov     rcx, [rbp+0E8h]; this
0x18007e740  test    al, al
0x18007e742  jz      short loc_18007E75C
  ... truncated ...
```
