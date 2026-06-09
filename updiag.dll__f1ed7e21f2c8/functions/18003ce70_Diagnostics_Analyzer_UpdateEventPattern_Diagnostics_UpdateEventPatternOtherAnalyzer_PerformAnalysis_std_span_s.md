# Diagnostics::Analyzer_UpdateEventPattern<Diagnostics::UpdateEventPatternOtherAnalyzer>::PerformAnalysis(std::span<std::filesystem::path const,-1>)

- ea: `0x18003ce70`
- end: `0x18003dff3`
- name: `?PerformAnalysis@?$Analyzer_UpdateEventPattern@UUpdateEventPatternOtherAnalyzer@Diagnostics@@@Diagnostics@@UEBA?AV?$optional@Vvalue@json@web@@@std@@V?$span@$$CBVpath@filesystem@std@@$0?0@4@@Z`
- size: `4483`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18002a6ac`
- `0x18002d4ac`
- `0x1800380bc`
- `0x1800381f0`
- `0x180038d4c`
- `0x18003ce70`
- `0x18004148c`
- `0x180069148`
- `0x180072de4`
- `0x180072e5c`
- `0x180072eb0`
- `0x180072f30`
- `0x180072fa0`
- `0x1800731f0`
- `0x180073294`
- `0x18008fe00`
- `0x180096170`

## string_xrefs

- `0x18003cf46`: `UPDATEID`
- `0x18003d298`: `COMPLETION`
- `0x18003dc82`: `Completion`

## pseudocode

```c
// Hidden C++ exception states: #wind=85
__int64 __fastcall Diagnostics::Analyzer_UpdateEventPattern<Diagnostics::UpdateEventPatternOtherAnalyzer>::PerformAnalysis(
        __int64 a1,
        __int64 a2,
        __m128i *a3,
        __int64 a4)
{
  __int64 v5; // r14
  char i; // al
  __int64 Attribute; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 *v19; // rbx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 *v23; // rbx
  __int64 *v24; // rax
  __int64 v25; // rcx
  wchar_t *v26; // rax
  unsigned int v27; // eax
  __int64 *v28; // rbx
  __int64 *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 *v32; // rbx
  __int64 *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 *v36; // rbx
  __int64 *v37; // rax
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 *v40; // rbx
  __int64 *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 *v44; // rbx
  __int64 *v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 *v48; // rbx
  __int64 *v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 *v52; // rbx
  __int64 *v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 *v56; // rbx
  __int64 *v57; // rax
  __int64 v58; // rcx
  __int64 *v59; // rcx
  __int64 v60; // rdi
  __int64 v61; // rax
  __int64 *v62; // rbx
  __int64 *v63; // rax
  __int64 v64; // rcx
  __int64 *v65; // rcx
  __int64 v66; // rbx
  __int64 v67; // rax
  __int128 v69; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v70; // [rsp+30h] [rbp-D0h]
  __int128 v71; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v72; // [rsp+50h] [rbp-B0h]
  char v73; // [rsp+60h] [rbp-A0h]
  __int64 v74; // [rsp+68h] [rbp-98h] BYREF
  __int64 v75; // [rsp+70h] [rbp-90h] BYREF
  __int64 v76; // [rsp+78h] [rbp-88h] BYREF
  __int64 v77; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v78[40]; // [rsp+88h] [rbp-78h] BYREF
  __m128i v79; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v80; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v81; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v82; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v83; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v85; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v86; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v87; // [rsp+100h] [rbp+0h] BYREF
  __int64 v88; // [rsp+108h] [rbp+8h] BYREF
  __int64 v89; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v90[40]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v91[40]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v92[40]; // [rsp+168h] [rbp+68h] BYREF
  _BYTE v93[40]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v94[40]; // [rsp+1B8h] [rbp+B8h] BYREF
  _BYTE v95[40]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v96[40]; // [rsp+208h] [rbp+108h] BYREF
  _BYTE v97[40]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v98[40]; // [rsp+258h] [rbp+158h] BYREF
  wchar_t S1[8]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v100; // [rsp+290h] [rbp+190h]
  wchar_t v101[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int128 v102; // [rsp+2B0h] [rbp+1B0h]
  wchar_t v103[8]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int128 v104; // [rsp+2D0h] [rbp+1D0h]
  wchar_t v105[8]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int128 v106; // [rsp+2F0h] [rbp+1F0h]
  __int128 v107; // [rsp+300h] [rbp+200h] BYREF
  __int128 v108; // [rsp+310h] [rbp+210h]
  __int128 v109; // [rsp+320h] [rbp+220h] BYREF
  __int128 v110; // [rsp+330h] [rbp+230h]
  __int128 v111; // [rsp+340h] [rbp+240h] BYREF
  __int128 v112; // [rsp+350h] [rbp+250h]
  __int128 v113; // [rsp+360h] [rbp+260h] BYREF
  __int128 v114; // [rsp+370h] [rbp+270h]
  __int128 v115; // [rsp+380h] [rbp+280h] BYREF
  __int128 v116; // [rsp+390h] [rbp+290h]
  __int128 v117; // [rsp+3A0h] [rbp+2A0h] BYREF
  __int128 v118; // [rsp+3B0h] [rbp+2B0h]
  __int128 v119; // [rsp+3C0h] [rbp+2C0h] BYREF
  __int128 v120; // [rsp+3D0h] [rbp+2D0h]
  _OWORD v121[2]; // [rsp+3E0h] [rbp+2E0h] BYREF
  __int64 v122; // [rsp+400h] [rbp+300h]
  _BYTE v123[336]; // [rsp+410h] [rbp+310h] BYREF
  char v124; // [rsp+560h] [rbp+460h]

  v79.m128i_i64[0] = a2;
  memset(v121, 0, sizeof(v121));
  v122 = 0;
  v69 = 0;
  v79 = *a3;
  Diagnostics::OTelReader::OTelReader((__int64)v121, &v79, (struct std::error_code *)&v69, a4);
  v77 = 0;
  web::json::value::array(&v77);
  v5 = 0;
  Diagnostics::OTelReader::ReadNextEvent(v121, v123);
  for ( i = v124; v124; i = v124 )
  {
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"UPDATEID", 8u);
    Attribute = Diagnostics::OTelLogRecord::GetAttribute(v123, v78, &v69);
    if ( *(_BYTE *)(Attribute + 32) )
    {
      v113 = *(_OWORD *)Attribute;
      v114 = *(_OWORD *)(Attribute + 16);
      *(_WORD *)Attribute = 0;
      *(_QWORD *)(Attribute + 16) = 0;
      *(_QWORD *)(Attribute + 24) = 7;
    }
    else
    {
      v113 = 0;
      v114 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v113, &psz, 0);
    }
    if ( v78[32] )
      std::wstring::~wstring((__int64)v78);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"PROVIDERID", 0xAu);
    v8 = Diagnostics::OTelLogRecord::GetAttribute(v123, &v71, &v69);
    if ( *(_BYTE *)(v8 + 32) )
    {
      v111 = *(_OWORD *)v8;
      v112 = *(_OWORD *)(v8 + 16);
      *(_WORD *)v8 = 0;
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 7;
    }
    else
    {
      v111 = 0;
      v112 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v111, &psz, 0);
    }
    if ( v73 )
      std::wstring::~wstring((__int64)&v71);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"TITLE", 5u);
    v9 = Diagnostics::OTelLogRecord::GetAttribute(v123, v90, &v69);
    if ( *(_BYTE *)(v9 + 32) )
    {
      *(_OWORD *)S1 = *(_OWORD *)v9;
      v100 = *(_OWORD *)(v9 + 16);
      *(_WORD *)v9 = 0;
      *(_QWORD *)(v9 + 16) = 0;
      *(_QWORD *)(v9 + 24) = 7;
    }
    else
    {
      *(_OWORD *)S1 = 0;
      v100 = 0;
      std::wstring::_Construct<1,wchar_t const *>(S1, &psz, 0);
    }
    if ( v90[32] )
      std::wstring::~wstring((__int64)v90);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"CATEGORY", 8u);
    v10 = Diagnostics::OTelLogRecord::GetAttribute(v123, v91, &v69);
    if ( *(_BYTE *)(v10 + 32) )
    {
      *(_OWORD *)v105 = *(_OWORD *)v10;
      v106 = *(_OWORD *)(v10 + 16);
      *(_WORD *)v10 = 0;
      *(_QWORD *)(v10 + 16) = 0;
      *(_QWORD *)(v10 + 24) = 7;
    }
    else
    {
      *(_OWORD *)v105 = 0;
      v106 = 0;
      std::wstring::_Construct<1,wchar_t const *>(v105, &psz, 0);
    }
    if ( v91[32] )
      std::wstring::~wstring((__int64)v91);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"STATE", 5u);
    v11 = Diagnostics::OTelLogRecord::GetAttribute(v123, v92, &v69);
    if ( *(_BYTE *)(v11 + 32) )
    {
      v109 = *(_OWORD *)v11;
      v110 = *(_OWORD *)(v11 + 16);
      *(_WORD *)v11 = 0;
      *(_QWORD *)(v11 + 16) = 0;
      *(_QWORD *)(v11 + 24) = 7;
    }
    else
    {
      v109 = 0;
      v110 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v109, &psz, 0);
    }
    if ( v92[32] )
      std::wstring::~wstring((__int64)v92);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"COMPLETION", 0xAu);
    v12 = Diagnostics::OTelLogRecord::GetAttribute(v123, v93, &v69);
    if ( *(_BYTE *)(v12 + 32) )
    {
      v107 = *(_OWORD *)v12;
      v108 = *(_OWORD *)(v12 + 16);
      *(_WORD *)v12 = 0;
      *(_QWORD *)(v12 + 16) = 0;
      *(_QWORD *)(v12 + 24) = 7;
    }
    else
    {
      v107 = 0;
      v108 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v107, &psz, 0);
    }
    if ( v93[32] )
      std::wstring::~wstring((__int64)v93);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"ISONESHOT", 9u);
    v13 = Diagnostics::OTelLogRecord::GetAttribute(v123, v94, &v69);
    if ( *(_BYTE *)(v13 + 32) )
    {
      v119 = *(_OWORD *)v13;
      v120 = *(_OWORD *)(v13 + 16);
      *(_WORD *)v13 = 0;
      *(_QWORD *)(v13 + 16) = 0;
      *(_QWORD *)(v13 + 24) = 7;
    }
    else
    {
      v119 = 0;
      v120 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v119, &psz, 0);
    }
    if ( v94[32] )
      std::wstring::~wstring((__int64)v94);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"HASLOOPING", 0xAu);
    v14 = Diagnostics::OTelLogRecord::GetAttribute(v123, v95, &v69);
    if ( *(_BYTE *)(v14 + 32) )
    {
      v117 = *(_OWORD *)v14;
      v118 = *(_OWORD *)(v14 + 16);
      *(_WORD *)v14 = 0;
      *(_QWORD *)(v14 + 16) = 0;
      *(_QWORD *)(v14 + 24) = 7;
    }
    else
    {
      v117 = 0;
      v118 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v117, &psz, 0);
    }
    if ( v95[32] )
      std::wstring::~wstring((__int64)v95);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"HASERROR", 8u);
    v15 = Diagnostics::OTelLogRecord::GetAttribute(v123, v96, &v69);
    if ( *(_BYTE *)(v15 + 32) )
    {
      v115 = *(_OWORD *)v15;
      v116 = *(_OWORD *)(v15 + 16);
      *(_WORD *)v15 = 0;
      *(_QWORD *)(v15 + 16) = 0;
      *(_QWORD *)(v15 + 24) = 7;
    }
    else
    {
      v115 = 0;
      v116 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v115, &psz, 0);
    }
    if ( v96[32] )
      std::wstring::~wstring((__int64)v96);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"DETAILS", 7u);
    v16 = Diagnostics::OTelLogRecord::GetAttribute(v123, v97, &v69);
    if ( *(_BYTE *)(v16 + 32) )
    {
      *(_OWORD *)v103 = *(_OWORD *)v16;
      v104 = *(_OWORD *)(v16 + 16);
      *(_WORD *)v16 = 0;
      *(_QWORD *)(v16 + 16) = 0;
      *(_QWORD *)(v16 + 24) = 7;
    }
    else
    {
      *(_OWORD *)v103 = 0;
      v104 = 0;
      std::wstring::_Construct<1,wchar_t const *>(v103, &psz, 0);
    }
    if ( v97[32] )
      std::wstring::~wstring((__int64)v97);
    std::wstring::~wstring((__int64)&v69);
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v69, L"EVENTCOUNT", 0xAu);
    v17 = Diagnostics::OTelLogRecord::GetAttribute(v123, v98, &v69);
    if ( *(_BYTE *)(v17 + 32) )
    {
      *(_OWORD *)v101 = *(_OWORD *)v17;
      v102 = *(_OWORD *)(v17 + 16);
      *(_WORD *)v17 = 0;
      *(_QWORD *)(v17 + 16) = 0;
      *(_QWORD *)(v17 + 24) = 7;
    }
    else
    {
      *(_OWORD *)v101 = 0;
      v102 = 0;
      std::wstring::_Construct<1,wchar_t const *>(v101, &psz, 0);
    }
    if ( v98[32] )
      std::wstring::~wstring((__int64)v98);
    std::wstring::~wstring((__int64)&v69);
    v75 = 0;
    web::json::value::object(&v75, 0);
    if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue(S1) )
    {
      v18 = std::wstring::wstring((__int64)v78, (__int64)S1);
      v19 = (__int64 *)web::json::value::string(&v80, v18);
      v71 = 0;
      v72 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v71, L"Alias", 5u);
      v20 = (__int64 *)web::json::value::operator[](&v75, &v71);
      if ( v20 != v19 )
      {
        v21 = *v20;
        *v20 = *v19;
        *v19 = v21;
      }
      std::wstring::~wstring((__int64)&v71);
      if ( v80 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 192LL))(v80, 1);
    }
    if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue(v105) )
    {
      v22 = std::wstring::wstring((__int64)v78, (__int64)v105);
      v23 = (__int64 *)web::json::value::string(&v81, v22);
      v71 = 0;
      v72 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v71, L"Category", 8u);
      v24 = (__int64 *)web::json::value::operator[](&v75, &v71);
      if ( v24 != v23 )
      {
        v25 = *v24;
        *v24 = *v23;
        *v23 = v25;
      }
      std::wstring::~wstring((__int64)&v71);
      if ( v81 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v81 + 192LL))(v81, 1);
    }
    if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue(v101) )
    {
      v26 = (wchar_t *)std::wstring::wstring((__int64)v78, (__int64)v101);
      v27 = std::stoi(v26);
      v28 = (__int64 *)web::json::value::number(&v82, v27);
      v71 = 0;
      v72 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v71, L"EventCount", 0xAu);
      v29 = (__int64 *)web::json::value::operator[](&v75, &v71);
      if ( v29 != v28 )
      {
        v30 = *v29;
        *v29 = *v28;
        *v28 = v30;
      }
      std::wstring::~wstring((__int64)&v71);
      if ( v82 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 192LL))(v82, 1);
      std::wstring::~wstring((__int64)v78);
    }
    v31 = std::wstring::wstring((__int64)v78, (__int64)&v113);
    v32 = (__int64 *)web::json::value::string(&v83, v31);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"ID", 2u);
    v33 = (__int64 *)web::json::value::operator[](&v75, &v71);
    if ( v33 != v32 )
    {
      v34 = *v33;
      *v33 = *v32;
      *v32 = v34;
    }
    std::wstring::~wstring((__int64)&v71);
    if ( v83 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v83 + 192LL))(v83, 1);
    v35 = std::wstring::wstring((__int64)v78, (__int64)&v111);
    v36 = (__int64 *)web::json::value::string(&v84, v35);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"ProviderID", 0xAu);
    v37 = (__int64 *)web::json::value::operator[](&v75, &v71);
    if ( v37 != v36 )
    {
      v38 = *v37;
      *v37 = *v36;
      *v36 = v38;
    }
    std::wstring::~wstring((__int64)&v71);
    if ( v84 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 192LL))(v84, 1);
    v74 = 0;
    web::json::value::object(&v74, 0);
    if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue(v103) )
    {
      v39 = std::wstring::wstring((__int64)v78, (__int64)v103);
      v40 = (__int64 *)web::json::value::string(&v85, v39);
      v71 = 0;
      v72 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v71, L"Details", 7u);
      v41 = (__int64 *)web::json::value::operator[](&v74, &v71);
      if ( v41 != v40 )
      {
        v42 = *v41;
        *v41 = *v40;
        *v40 = v42;
      }
      std::wstring::~wstring((__int64)&v71);
      if ( v85 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v85 + 192LL))(v85, 1);
    }
    v43 = std::wstring::wstring((__int64)v78, (__int64)&v115);
    v44 = (__int64 *)web::json::value::string(&v86, v43);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"HasError", 8u);
    v45 = (__int64 *)web::json::value::operator[](&v74, &v71);
    if ( v45 != v44 )
    {
      v46 = *v45;
      *v45 = *v44;
      *v44 = v46;
    }
    std::wstring::~wstring((__int64)&v71);
    if ( v86 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v86 + 192LL))(v86, 1);
    v47 = std::wstring::wstring((__int64)v78, (__int64)&v117);
    v48 = (__int64 *)web::json::value::string(&v87, v47);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"HasLooping", 0xAu);
    v49 = (__int64 *)web::json::value::operator[](&v74, &v71);
    if ( v49 != v48 )
    {
      v50 = *v49;
      *v49 = *v48;
      *v48 = v50;
    }
    std::wstring::~wstring((__int64)&v71);
    if ( v87 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 192LL))(v87, 1);
    v51 = std::wstring::wstring((__int64)v78, (__int64)&v119);
    v52 = (__int64 *)web::json::value::string(&v88, v51);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"IsOneshot", 9u);
    v53 = (__int64 *)web::json::value::operator[](&v74, &v71);
    if ( v53 != v52 )
    {
      v54 = *v53;
      *v53 = *v52;
      *v52 = v54;
    }
    std::wstring::~wstring((__int64)&v71);
    if ( v88 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v88 + 192LL))(v88, 1);
    v76 = 0;
    web::json::value::object(&v76, 0);
    v55 = std::wstring::wstring((__int64)v78, (__int64)&v107);
    v56 = (__int64 *)web::json::value::string(&v89, v55);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"Completion", 0xAu);
    v57 = (__int64 *)web::json::value::operator[](&v76, &v71);
    if ( v57 != v56 )
    {
      v58 = *v57;
      *v57 = *v56;
      *v56 = v58;
    }
    std::wstring::~wstring((__int64)&v71);
    if ( v89 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v89 + 192LL))(v89, 1);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"Pattern", 7u);
    v59 = (__int64 *)web::json::value::operator[](&v76, &v71);
    if ( v59 == &v74 )
    {
      v60 = v74;
    }
    else
    {
      v60 = *v59;
      *v59 = v74;
      v74 = v60;
    }
    std::wstring::~wstring((__int64)&v71);
    v61 = std::wstring::wstring((__int64)v78, (__int64)&v109);
    v62 = (__int64 *)web::json::value::string(&v79, v61);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"State", 5u);
    v63 = (__int64 *)web::json::value::operator[](&v76, &v71);
    if ( v63 != v62 )
    {
      v64 = *v63;
      *v63 = *v62;
      *v62 = v64;
    }
    std::wstring::~wstring((__int64)&v71);
    if ( v79.m128i_i64[0] )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v79.m128i_i64[0] + 192LL))(v79.m128i_i64[0], 1);
    v71 = 0;
    v72 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v71, L"Status", 6u);
    v65 = (__int64 *)web::json::value::operator[](&v75, &v71);
    if ( v65 == &v76 )
    {
      v66 = v76;
    }
    else
    {
      v66 = *v65;
      *v65 = v76;
      v76 = v66;
    }
    std::wstring::~wstring((__int64)&v71);
    v67 = web::json::value::operator[](&v77, v5++);
    web::json::value::operator=(v67, &v75);
    if ( v66 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v66 + 192LL))(v66, 1);
    if ( v60 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 192LL))(v60, 1);
    if ( v75 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v75 + 192LL))(v75, 1);
    std::wstring::~wstring((__int64)v101);
    std::wstring::~wstring((__int64)v103);
    std::wstring::~wstring((__int64)&v115);
    std::wstring::~wstring((__int64)&v117);
    std::wstring::~wstring((__int64)&v119);
    std::wstring::~wstring((__int64)&v107);
    std::wstring::~wstring((__int64)&v109);
    std::wstring::~wstring((__int64)v105);
    std::wstring::~wstring((__int64)S1);
    std::wstring::~wstring((__int64)&v111);
    std::wstring::~wstring((__int64)&v113);
    if ( v124 )
      Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v123);
    Diagnostics::OTelReader::ReadNextEvent(v121, v123);
  }
  if ( i )
    Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v123);
  if ( v5 )
  {
    *(_QWORD *)a2 = v77;
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_BYTE *)(a2 + 8) = 0;
    if ( v77 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v77 + 192LL))(v77, 1);
  }
  std::vector<Diagnostics::OTelFile>::~vector<Diagnostics::OTelFile>(v121);
  return a2;
}

```

## disassembly

```asm
0x18003ce70  mov     [rsp-8+arg_0], rbx
0x18003ce75  push    rbp
0x18003ce76  push    rsi
0x18003ce77  push    rdi
0x18003ce78  push    r12
0x18003ce7a  push    r13
0x18003ce7c  push    r14
0x18003ce7e  push    r15
0x18003ce80  lea     rbp, [rsp-480h]
0x18003ce88  sub     rsp, 580h
0x18003ce8f  mov     rax, cs:__security_cookie
0x18003ce96  xor     rax, rsp
0x18003ce99  mov     [rbp+4B0h+var_40], rax
0x18003cea0  mov     rsi, rdx
0x18003cea3  mov     qword ptr [rbp+4B0h+var_500], rdx
0x18003cea7  xor     r15d, r15d
0x18003ceaa  xorps   xmm0, xmm0
0x18003cead  xor     eax, eax
0x18003ceaf  movups  [rbp+4B0h+var_1D0], xmm0
0x18003ceb6  movups  [rbp+4B0h+var_1C0], xmm0
0x18003cebd  mov     [rbp+4B0h+var_1B0], rax
0x18003cec4  movdqa  [rsp+5B0h+var_590], xmm0
0x18003ceca  movups  xmm1, xmmword ptr [r8]
0x18003cece  movdqu  [rbp+4B0h+var_500], xmm1
0x18003ced3  lea     r8, [rsp+5B0h+var_590]
0x18003ced8  lea     rdx, [rbp+4B0h+var_500]
0x18003cedc  lea     rcx, [rbp+4B0h+var_1D0]
0x18003cee3  call    ??0OTelReader@Diagnostics@@QEAA@V?$span@$$CBVpath@filesystem@std@@$0?0@std@@V?$span@$$CBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@2@@std@@$0?0@2@@std@@$0?0@3@@Z; Diagnostics::OTelReader::OTelReader(std::span<std::filesystem::path const,-1>,std::span<std::pair<std::wstring_view,std::span<std::pair<std::wstring_view,std::span<std::wstring_view const,-1>> const,-1>> const,-1>)
0x18003cee8  nop
0x18003cee9  mov     [rbp+4B0h+var_530], r15
0x18003ceed  lea     rcx, [rbp+4B0h+var_530]
0x18003cef1  call    ?array@value@json@web@@SA?AV123@XZ; web::json::value::array(void)
0x18003cef6  nop
0x18003cef7  mov     r14d, r15d
0x18003cefa  lea     rdx, [rbp+4B0h+var_1A0]
0x18003cf01  lea     rcx, [rbp+4B0h+var_1D0]
0x18003cf08  call    ?ReadNextEvent@OTelReader@Diagnostics@@QEAA?AV?$optional@VOTelLogRecord@Diagnostics@@@std@@XZ; Diagnostics::OTelReader::ReadNextEvent(void)
0x18003cf0d  nop
0x18003cf0e  lea     r12d, [r15+1]
0x18003cf12  mov     al, [rbp+4B0h+var_50]
0x18003cf18  test    al, al
0x18003cf1a  jz      loc_18003DF79
0x18003cf20  lea     r13d, [r15+7]
0x18003cf24  lea     rbx, psz
0x18003cf2b  lea     edi, [r15+0Ah]
0x18003cf2f  xorps   xmm0, xmm0
0x18003cf32  movups  [rsp+5B0h+var_590], xmm0
0x18003cf37  xorps   xmm1, xmm1
0x18003cf3a  movdqu  [rsp+5B0h+var_580], xmm1
0x18003cf40  mov     r8d, 8
0x18003cf46  lea     rdx, aUpdateid_0; "UPDATEID"
0x18003cf4d  lea     rcx, [rsp+5B0h+var_590]
0x18003cf52  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003cf57  nop
0x18003cf58  lea     r8, [rsp+5B0h+var_590]
0x18003cf5d  lea     rdx, [rbp+4B0h+var_528]
0x18003cf61  lea     rcx, [rbp+4B0h+var_1A0]
0x18003cf68  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003cf6d  nop
0x18003cf6e  cmp     [rax+20h], r15b
0x18003cf72  jz      short loc_18003CF97
0x18003cf74  movups  xmm0, xmmword ptr [rax]
0x18003cf77  movups  [rbp+4B0h+var_250], xmm0
0x18003cf7e  movups  xmm1, xmmword ptr [rax+10h]
0x18003cf82  movups  [rbp+4B0h+var_240], xmm1
0x18003cf89  mov     [rax], r15w
0x18003cf8d  mov     [rax+10h], r15
0x18003cf91  mov     [rax+18h], r13
0x18003cf95  jmp     short loc_18003CFBF
0x18003cf97  xorps   xmm0, xmm0
0x18003cf9a  movups  [rbp+4B0h+var_250], xmm0
0x18003cfa1  xorps   xmm1, xmm1
0x18003cfa4  movdqu  [rbp+4B0h+var_240], xmm1
0x18003cfac  xor     r8d, r8d
0x18003cfaf  mov     rdx, rbx
0x18003cfb2  lea     rcx, [rbp+4B0h+var_250]
0x18003cfb9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003cfbe  nop
0x18003cfbf  cmp     [rbp+4B0h+var_508], r15b
0x18003cfc3  jz      short loc_18003CFCF
0x18003cfc5  lea     rcx, [rbp+4B0h+var_528]
0x18003cfc9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cfce  nop
0x18003cfcf  lea     rcx, [rsp+5B0h+var_590]
0x18003cfd4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cfd9  xorps   xmm0, xmm0
0x18003cfdc  movups  [rsp+5B0h+var_590], xmm0
0x18003cfe1  xorps   xmm1, xmm1
0x18003cfe4  movdqu  [rsp+5B0h+var_580], xmm1
0x18003cfea  mov     r8, rdi
0x18003cfed  lea     rdx, aProviderid; "PROVIDERID"
0x18003cff4  lea     rcx, [rsp+5B0h+var_590]
0x18003cff9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003cffe  nop
0x18003cfff  lea     r8, [rsp+5B0h+var_590]
0x18003d004  lea     rdx, [rsp+5B0h+var_570]
0x18003d009  lea     rcx, [rbp+4B0h+var_1A0]
0x18003d010  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003d015  nop
0x18003d016  cmp     [rax+20h], r15b
0x18003d01a  jz      short loc_18003D03F
0x18003d01c  movups  xmm0, xmmword ptr [rax]
0x18003d01f  movups  [rbp+4B0h+var_270], xmm0
0x18003d026  movups  xmm1, xmmword ptr [rax+10h]
0x18003d02a  movups  [rbp+4B0h+var_260], xmm1
0x18003d031  mov     [rax], r15w
0x18003d035  mov     [rax+10h], r15
0x18003d039  mov     [rax+18h], r13
0x18003d03d  jmp     short loc_18003D067
0x18003d03f  xorps   xmm0, xmm0
0x18003d042  movups  [rbp+4B0h+var_270], xmm0
0x18003d049  xorps   xmm1, xmm1
0x18003d04c  movdqu  [rbp+4B0h+var_260], xmm1
0x18003d054  xor     r8d, r8d
0x18003d057  mov     rdx, rbx
0x18003d05a  lea     rcx, [rbp+4B0h+var_270]
0x18003d061  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d066  nop
0x18003d067  cmp     [rsp+5B0h+var_550], r15b
0x18003d06c  jz      short loc_18003D079
0x18003d06e  lea     rcx, [rsp+5B0h+var_570]
0x18003d073  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d078  nop
0x18003d079  lea     rcx, [rsp+5B0h+var_590]
0x18003d07e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d083  xorps   xmm0, xmm0
0x18003d086  movups  [rsp+5B0h+var_590], xmm0
0x18003d08b  xorps   xmm1, xmm1
0x18003d08e  movdqu  [rsp+5B0h+var_580], xmm1
0x18003d094  mov     r8d, 5
0x18003d09a  lea     rdx, aTitle; "TITLE"
0x18003d0a1  lea     rcx, [rsp+5B0h+var_590]
0x18003d0a6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d0ab  nop
0x18003d0ac  lea     r8, [rsp+5B0h+var_590]
0x18003d0b1  lea     rdx, [rbp+4B0h+var_498]
0x18003d0b5  lea     rcx, [rbp+4B0h+var_1A0]
0x18003d0bc  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003d0c1  nop
0x18003d0c2  cmp     [rax+20h], r15b
0x18003d0c6  jz      short loc_18003D0EB
0x18003d0c8  movups  xmm0, xmmword ptr [rax]
0x18003d0cb  movups  xmmword ptr [rbp+4B0h+S1], xmm0
0x18003d0d2  movups  xmm1, xmmword ptr [rax+10h]
0x18003d0d6  movups  [rbp+4B0h+var_320], xmm1
0x18003d0dd  mov     [rax], r15w
0x18003d0e1  mov     [rax+10h], r15
0x18003d0e5  mov     [rax+18h], r13
0x18003d0e9  jmp     short loc_18003D113
0x18003d0eb  xorps   xmm0, xmm0
0x18003d0ee  movups  xmmword ptr [rbp+4B0h+S1], xmm0
0x18003d0f5  xorps   xmm1, xmm1
0x18003d0f8  movdqu  [rbp+4B0h+var_320], xmm1
0x18003d100  xor     r8d, r8d
0x18003d103  mov     rdx, rbx
0x18003d106  lea     rcx, [rbp+4B0h+S1]
0x18003d10d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d112  nop
0x18003d113  cmp     [rbp+4B0h+var_478], r15b
0x18003d117  jz      short loc_18003D123
0x18003d119  lea     rcx, [rbp+4B0h+var_498]
0x18003d11d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d122  nop
0x18003d123  lea     rcx, [rsp+5B0h+var_590]
0x18003d128  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d12d  xorps   xmm0, xmm0
0x18003d130  movups  [rsp+5B0h+var_590], xmm0
0x18003d135  xorps   xmm1, xmm1
0x18003d138  movdqu  [rsp+5B0h+var_580], xmm1
0x18003d13e  mov     r8d, 8
0x18003d144  lea     rdx, aCategory_0; "CATEGORY"
0x18003d14b  lea     rcx, [rsp+5B0h+var_590]
0x18003d150  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d155  nop
0x18003d156  lea     r8, [rsp+5B0h+var_590]
0x18003d15b  lea     rdx, [rbp+4B0h+var_470]
0x18003d15f  lea     rcx, [rbp+4B0h+var_1A0]
0x18003d166  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003d16b  nop
0x18003d16c  cmp     [rax+20h], r15b
0x18003d170  jz      short loc_18003D195
0x18003d172  movups  xmm0, xmmword ptr [rax]
0x18003d175  movups  xmmword ptr [rbp+4B0h+var_2D0], xmm0
0x18003d17c  movups  xmm1, xmmword ptr [rax+10h]
0x18003d180  movups  [rbp+4B0h+var_2C0], xmm1
0x18003d187  mov     [rax], r15w
0x18003d18b  mov     [rax+10h], r15
0x18003d18f  mov     [rax+18h], r13
0x18003d193  jmp     short loc_18003D1BD
0x18003d195  xorps   xmm0, xmm0
0x18003d198  movups  xmmword ptr [rbp+4B0h+var_2D0], xmm0
0x18003d19f  xorps   xmm1, xmm1
0x18003d1a2  movdqu  [rbp+4B0h+var_2C0], xmm1
0x18003d1aa  xor     r8d, r8d
0x18003d1ad  mov     rdx, rbx
0x18003d1b0  lea     rcx, [rbp+4B0h+var_2D0]
0x18003d1b7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d1bc  nop
0x18003d1bd  cmp     [rbp+4B0h+var_450], r15b
0x18003d1c1  jz      short loc_18003D1CD
0x18003d1c3  lea     rcx, [rbp+4B0h+var_470]
0x18003d1c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d1cc  nop
0x18003d1cd  lea     rcx, [rsp+5B0h+var_590]
0x18003d1d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d1d7  xorps   xmm0, xmm0
0x18003d1da  movups  [rsp+5B0h+var_590], xmm0
0x18003d1df  xorps   xmm1, xmm1
0x18003d1e2  movdqu  [rsp+5B0h+var_580], xmm1
0x18003d1e8  mov     r8d, 5
0x18003d1ee  lea     rdx, aState; "STATE"
0x18003d1f5  lea     rcx, [rsp+5B0h+var_590]
0x18003d1fa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d1ff  nop
0x18003d200  lea     r8, [rsp+5B0h+var_590]
0x18003d205  lea     rdx, [rbp+4B0h+var_448]
0x18003d209  lea     rcx, [rbp+4B0h+var_1A0]
0x18003d210  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003d215  nop
0x18003d216  cmp     [rax+20h], r15b
0x18003d21a  jz      short loc_18003D23F
0x18003d21c  movups  xmm0, xmmword ptr [rax]
0x18003d21f  movups  [rbp+4B0h+var_290], xmm0
0x18003d226  movups  xmm1, xmmword ptr [rax+10h]
0x18003d22a  movups  [rbp+4B0h+var_280], xmm1
0x18003d231  mov     [rax], r15w
0x18003d235  mov     [rax+10h], r15
0x18003d239  mov     [rax+18h], r13
0x18003d23d  jmp     short loc_18003D267
0x18003d23f  xorps   xmm0, xmm0
0x18003d242  movups  [rbp+4B0h+var_290], xmm0
0x18003d249  xorps   xmm1, xmm1
0x18003d24c  movdqu  [rbp+4B0h+var_280], xmm1
0x18003d254  xor     r8d, r8d
0x18003d257  mov     rdx, rbx
0x18003d25a  lea     rcx, [rbp+4B0h+var_290]
0x18003d261  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d266  nop
0x18003d267  cmp     [rbp+4B0h+var_428], r15b
0x18003d26e  jz      short loc_18003D27A
0x18003d270  lea     rcx, [rbp+4B0h+var_448]
0x18003d274  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d279  nop
0x18003d27a  lea     rcx, [rsp+5B0h+var_590]
0x18003d27f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d284  xorps   xmm0, xmm0
0x18003d287  movups  [rsp+5B0h+var_590], xmm0
0x18003d28c  xorps   xmm1, xmm1
0x18003d28f  movdqu  [rsp+5B0h+var_580], xmm1
0x18003d295  mov     r8, rdi
0x18003d298  lea     rdx, aCompletion_0; "COMPLETION"
0x18003d29f  lea     rcx, [rsp+5B0h+var_590]
0x18003d2a4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d2a9  nop
0x18003d2aa  lea     r8, [rsp+5B0h+var_590]
0x18003d2af  lea     rdx, [rbp+4B0h+var_420]
0x18003d2b6  lea     rcx, [rbp+4B0h+var_1A0]
0x18003d2bd  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003d2c2  nop
0x18003d2c3  cmp     [rax+20h], r15b
0x18003d2c7  jz      short loc_18003D2EC
0x18003d2c9  movups  xmm0, xmmword ptr [rax]
0x18003d2cc  movups  [rbp+4B0h+var_2B0], xmm0
0x18003d2d3  movups  xmm1, xmmword ptr [rax+10h]
0x18003d2d7  movups  [rbp+4B0h+var_2A0], xmm1
0x18003d2de  mov     [rax], r15w
0x18003d2e2  mov     [rax+10h], r15
0x18003d2e6  mov     [rax+18h], r13
0x18003d2ea  jmp     short loc_18003D314
0x18003d2ec  xorps   xmm0, xmm0
0x18003d2ef  movups  [rbp+4B0h+var_2B0], xmm0
0x18003d2f6  xorps   xmm1, xmm1
0x18003d2f9  movdqu  [rbp+4B0h+var_2A0], xmm1
0x18003d301  xor     r8d, r8d
0x18003d304  mov     rdx, rbx
0x18003d307  lea     rcx, [rbp+4B0h+var_2B0]
0x18003d30e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d313  nop
0x18003d314  cmp     [rbp+4B0h+var_400], r15b
0x18003d31b  jz      short loc_18003D32A
0x18003d31d  lea     rcx, [rbp+4B0h+var_420]
0x18003d324  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d329  nop
0x18003d32a  lea     rcx, [rsp+5B0h+var_590]
0x18003d32f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d334  xorps   xmm0, xmm0
0x18003d337  movups  [rsp+5B0h+var_590], xmm0
0x18003d33c  xorps   xmm1, xmm1
0x18003d33f  movdqu  [rsp+5B0h+var_580], xmm1
0x18003d345  mov     r8d, 9
0x18003d34b  lea     rdx, aIsoneshot_0; "ISONESHOT"
0x18003d352  lea     rcx, [rsp+5B0h+var_590]
0x18003d357  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003d35c  nop
0x18003d35d  lea     r8, [rsp+5B0h+var_590]
0x18003d362  lea     rdx, [rbp+4B0h+var_3F8]
0x18003d369  lea     rcx, [rbp+4B0h+var_1A0]
0x18003d370  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003d375  nop
0x18003d376  cmp     [rax+20h], r15b
  ... truncated ...
```
