# Diagnostics::Analyzer_UpdateEventHistory<Diagnostics::UpdateEventHistoryOther>::PerformAnalysis(std::span<std::filesystem::path const,-1>)

- ea: `0x18003e240`
- end: `0x18003fdd8`
- name: `?PerformAnalysis@?$Analyzer_UpdateEventHistory@UUpdateEventHistoryOther@Diagnostics@@@Diagnostics@@UEBA?AV?$optional@Vvalue@json@web@@@std@@V?$span@$$CBVpath@filesystem@std@@$0?0@4@@Z`
- size: `7064`
- prototype: ``
- caller_count: `0`
- callee_count: `40`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180015360`
- `0x180018b04`
- `0x180018eec`
- `0x180019080`
- `0x18001abd4`
- `0x18001e99c`
- `0x180029ba4`
- `0x18002a6ac`
- `0x18002d4ac`
- `0x1800380bc`
- `0x1800381f0`
- `0x180038d4c`
- `0x18003afd4`
- `0x18003c324`
- `0x18003e240`
- `0x18003fde0`
- `0x18004148c`
- `0x180041624`
- `0x180048608`
- `0x180049510`
- `0x180049db8`
- `0x180052a04`
- `0x180052d48`
- `0x1800549c0`
- `0x180056014`
- `0x180056dc4`
- `0x180059d60`
- `0x180059de0`
- `0x18005cd1c`
- `0x180068e68`
- `0x180072de4`
- `0x180072eb0`
- `0x180072f30`
- `0x180072fa0`
- `0x1800731f0`
- `0x180073294`
- `0x18008fe00`
- `0x180095af0`
- `0x180096170`
- `0x1800961f0`

## string_xrefs

- `0x18003e479`: `UPDATEID`
- `0x18003e805`: `UPDATEMETADATA`
- `0x18003f51f`: `UpdateMetadata`
- `0x18003fab8`: `UpdateApprovals`
- `0x18003fc79`: `UpdateEvents`
- `0x18003fbee`: `UpdateEventCount`

## pseudocode

```c
// Hidden C++ exception states: #wind=72
__int64 __fastcall Diagnostics::Analyzer_UpdateEventHistory<Diagnostics::UpdateEventHistoryOther>::PerformAnalysis(
        __int64 a1,
        __int64 a2,
        __m128i *a3,
        __int64 a4)
{
  __int64 v4; // r15
  int v5; // ebx
  _QWORD *v6; // rax
  __int64 Attribute; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  char v23; // al
  __int128 *v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __m128i v34; // xmm6
  __int128 v35; // xmm7
  __int64 v36; // rax
  __m128i v37; // xmm6
  __int128 v38; // xmm7
  __int64 v39; // rcx
  __int64 v40; // r9
  __int128 v41; // rcx
  __int64 **v42; // rsi
  __int64 *v43; // r14
  __int64 v44; // rbx
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 *v47; // rbx
  __int64 *v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 *v51; // rbx
  __int64 *v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 *v55; // rbx
  __int64 *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rax
  __int64 *v59; // rbx
  __int64 *v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rax
  __int64 *v63; // rbx
  __int64 *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rax
  __int64 *v67; // rbx
  __int64 *v68; // rax
  __int64 v69; // rdx
  __int64 v70; // rax
  __int64 *v71; // rbx
  __int64 *v72; // rax
  __int64 v73; // rdx
  unsigned __int64 v74; // r13
  __int64 v75; // r15
  __int64 v76; // rbx
  __int64 v77; // r12
  __int64 v78; // rax
  __int64 *v79; // r15
  __int64 *v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rax
  __int64 *v83; // r15
  __int64 *v84; // rax
  __int64 v85; // rdx
  __int64 v86; // rax
  __int64 *v87; // r15
  __int64 *v88; // rax
  __int64 v89; // rdx
  __int64 v90; // rax
  __int64 *v91; // r15
  __int64 *v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rax
  __int64 *v95; // r15
  __int64 *v96; // rax
  __int64 v97; // rdx
  __int64 v98; // rax
  __int64 *v99; // r15
  __int64 *v100; // rax
  __int64 v101; // rdx
  __int64 v102; // rax
  __int64 *v103; // rbx
  __int64 *v104; // rax
  __int64 v105; // rdx
  __int64 v106; // rax
  __int64 v107; // r15
  _QWORD *v108; // rbx
  void **v109; // rax
  _QWORD *v110; // r15
  __int64 v111; // rax
  __int64 *v112; // rdx
  __int64 v113; // rax
  __m128i v115; // [rsp+20h] [rbp-558h] BYREF
  __int128 v116; // [rsp+30h] [rbp-548h]
  char v117; // [rsp+40h] [rbp-538h]
  _BYTE v118[32]; // [rsp+48h] [rbp-530h] BYREF
  char v119; // [rsp+68h] [rbp-510h]
  _BYTE v120[32]; // [rsp+70h] [rbp-508h] BYREF
  char v121; // [rsp+90h] [rbp-4E8h]
  __int128 v122; // [rsp+A0h] [rbp-4D8h] BYREF
  __int64 *v123; // [rsp+B0h] [rbp-4C8h]
  __int128 v124; // [rsp+B8h] [rbp-4C0h] BYREF
  __int64 v125; // [rsp+C8h] [rbp-4B0h]
  __int64 v126; // [rsp+D0h] [rbp-4A8h]
  __int64 v127; // [rsp+D8h] [rbp-4A0h]
  __int64 v128; // [rsp+E0h] [rbp-498h] BYREF
  __int64 v129; // [rsp+E8h] [rbp-490h] BYREF
  __int64 v130; // [rsp+F0h] [rbp-488h] BYREF
  __int64 v131; // [rsp+F8h] [rbp-480h] BYREF
  __int64 v132; // [rsp+100h] [rbp-478h] BYREF
  __int64 v133; // [rsp+108h] [rbp-470h] BYREF
  __int64 v134; // [rsp+110h] [rbp-468h] BYREF
  __int64 v135; // [rsp+118h] [rbp-460h] BYREF
  __int64 v136; // [rsp+120h] [rbp-458h] BYREF
  __int64 v137; // [rsp+128h] [rbp-450h] BYREF
  __int64 v138; // [rsp+130h] [rbp-448h] BYREF
  __int64 v139; // [rsp+138h] [rbp-440h] BYREF
  __int64 v140; // [rsp+140h] [rbp-438h] BYREF
  __int64 v141; // [rsp+148h] [rbp-430h] BYREF
  _QWORD *v142; // [rsp+150h] [rbp-428h] BYREF
  int v143; // [rsp+158h] [rbp-420h]
  __int128 v144; // [rsp+160h] [rbp-418h] BYREF
  __int64 v145; // [rsp+170h] [rbp-408h]
  __int64 v146; // [rsp+178h] [rbp-400h]
  __int64 v147; // [rsp+180h] [rbp-3F8h] BYREF
  __int64 v148; // [rsp+188h] [rbp-3F0h] BYREF
  __int64 v149; // [rsp+190h] [rbp-3E8h] BYREF
  __int64 v150; // [rsp+198h] [rbp-3E0h] BYREF
  __int128 v151; // [rsp+1A0h] [rbp-3D8h] BYREF
  __int64 v152; // [rsp+1B0h] [rbp-3C8h]
  __int128 v153; // [rsp+1B8h] [rbp-3C0h] BYREF
  __int128 v154; // [rsp+1C8h] [rbp-3B0h]
  __int128 v155; // [rsp+1D8h] [rbp-3A0h] BYREF
  __int128 v156; // [rsp+1E8h] [rbp-390h]
  _OWORD v157[4]; // [rsp+200h] [rbp-378h] BYREF
  _OWORD v158[2]; // [rsp+240h] [rbp-338h] BYREF
  __int64 v159; // [rsp+260h] [rbp-318h]
  wchar_t String[8]; // [rsp+268h] [rbp-310h] BYREF
  __int64 v161; // [rsp+278h] [rbp-300h]
  _BYTE v162[40]; // [rsp+288h] [rbp-2F0h] BYREF
  __int64 v163; // [rsp+2B0h] [rbp-2C8h] BYREF
  _BYTE v164[32]; // [rsp+2B8h] [rbp-2C0h] BYREF
  _BYTE v165[32]; // [rsp+2D8h] [rbp-2A0h] BYREF
  _BYTE v166[32]; // [rsp+2F8h] [rbp-280h] BYREF
  _BYTE v167[32]; // [rsp+318h] [rbp-260h] BYREF
  _BYTE v168[32]; // [rsp+338h] [rbp-240h] BYREF
  _OWORD v169[2]; // [rsp+358h] [rbp-220h] BYREF
  _OWORD v170[2]; // [rsp+378h] [rbp-200h] BYREF
  _QWORD v171[4]; // [rsp+3A0h] [rbp-1D8h] BYREF
  _BYTE v172[128]; // [rsp+3C0h] [rbp-1B8h] BYREF
  __int64 v173; // [rsp+440h] [rbp-138h]
  char v174; // [rsp+510h] [rbp-68h]

  v4 = a2;
  v127 = a2;
  v150 = a2;
  v5 = 0;
  v143 = 0;
  memset(v158, 0, sizeof(v158));
  v159 = 0;
  v122 = 0u;
  v115 = *a3;
  Diagnostics::OTelReader::OTelReader((__int64)v158, &v115, (struct std::error_code *)&v122, a4);
  memset(v157, 0, sizeof(v157));
  LODWORD(v157[0]) = 0;
  *((_QWORD *)&v157[0] + 1) = 0;
  *(_QWORD *)&v157[1] = 0;
  v6 = operator new(0x128u);
  *v6 = v6;
  v6[1] = v6;
  *((_QWORD *)&v157[0] + 1) = v6;
  *((_QWORD *)&v157[1] + 1) = 0;
  v157[2] = 0;
  *(_QWORD *)&v157[3] = 7;
  *((_QWORD *)&v157[3] + 1) = 8;
  LODWORD(v157[0]) = 1065353216;
  __Assign_grow____Hash_vec_V__allocator_V___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___std___std___std__QEAAX_KV___List_unchecked_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UEventStats__1__ClassifyPattern___Connector_UpdateEventPattern_UUpdateEventPatternWU_Diagnostics___Diagnostics__CA_AUPatternResult_56_AEBUUpdateGroup_56__Z__std___std___std___2__Z(
    (char *)&v157[1] + 8,
    16,
    v6);
  while ( 1 )
  {
    Diagnostics::OTelReader::ReadNextEvent(v158, v172);
    if ( !v174 )
      break;
    v115 = 0;
    v116 = 0u;
    std::wstring::_Construct<1,wchar_t const *>(&v115, L"PROVIDERID", 0xAu);
    Attribute = Diagnostics::OTelLogRecord::GetAttribute(v172, v118, &v115);
    if ( *(_BYTE *)(Attribute + 32) )
    {
      v155 = *(_OWORD *)Attribute;
      v156 = *(_OWORD *)(Attribute + 16);
      *(_QWORD *)(Attribute + 16) = 0;
      *(_QWORD *)(Attribute + 24) = 7;
      *(_WORD *)Attribute = 0;
    }
    else
    {
      v155 = 0;
      v156 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v155, &psz, 0);
    }
    if ( v119 )
      std::wstring::~wstring((__int64)v118);
    std::wstring::~wstring((__int64)&v115);
    v115 = 0;
    v116 = 0u;
    std::wstring::_Construct<1,wchar_t const *>(&v115, L"UPDATEID", 8u);
    v8 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
    v5 |= 0x18u;
    if ( *(_BYTE *)(v8 + 32) )
    {
      v153 = *(_OWORD *)v8;
      v154 = *(_OWORD *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = 0;
      *(_QWORD *)(v8 + 24) = 7;
      *(_WORD *)v8 = 0;
    }
    else
    {
      v153 = 0;
      v154 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v153, &psz, 0);
    }
    LODWORD(v147) = v5;
    if ( v121 )
      std::wstring::~wstring((__int64)v120);
    std::wstring::~wstring((__int64)&v115);
    if ( (_QWORD)v156 && (_QWORD)v154 )
    {
      v9 = std::operator+<wchar_t>(&v124);
      std::operator+<wchar_t>(v171, v9, &v153);
      std::wstring::~wstring((__int64)&v124);
      v10 = (__int64 *)(*(_QWORD *)____Try_emplace_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std____V____Hash_V___Umap_traits_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z_V___Uhash_compare_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__U__hash_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_U__equal_to_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2__2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std___2__0A__std___std__IEAA_AU__pair_PEAU___List_node_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std__PEAX_std___N_1_AEBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__1__Z(
                                     (float *)v157,
                                     (__int64)&v122,
                                     v171)
                      + 48LL);
      v123 = v10;
      if ( !v10[2] )
      {
        std::wstring::operator=(v10);
        std::wstring::operator=(v10 + 4);
        v115 = 0;
        v116 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v115, L"CATEGORY", 8u);
        v11 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
        v12 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v11, v118);
        std::wstring::operator=(v10 + 8, v12);
        std::wstring::~wstring((__int64)v118);
        if ( v121 )
          std::wstring::~wstring((__int64)v120);
        std::wstring::~wstring((__int64)&v115);
        v115 = 0;
        v116 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v115, L"TITLE", 5u);
        v13 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
        v14 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v13, v118);
        std::wstring::operator=(v10 + 12, v14);
        std::wstring::~wstring((__int64)v118);
        if ( v121 )
          std::wstring::~wstring((__int64)v120);
        std::wstring::~wstring((__int64)&v115);
        v115 = 0;
        v116 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v115, L"ISSEEKER", 8u);
        v15 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
        v16 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v15, v118);
        std::wstring::operator=(v10 + 16, v16);
        std::wstring::~wstring((__int64)v118);
        if ( v121 )
          std::wstring::~wstring((__int64)v120);
        std::wstring::~wstring((__int64)&v115);
        v115 = 0;
        v116 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v115, L"FLIGHTID", 8u);
        v17 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
        v18 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v17, v118);
        std::wstring::operator=(v10 + 20, v18);
        std::wstring::~wstring((__int64)v118);
        if ( v121 )
          std::wstring::~wstring((__int64)v120);
        std::wstring::~wstring((__int64)&v115);
        v115 = 0;
        v116 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v115, L"UPDATEMETADATA", 0xEu);
        v19 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
        v20 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v19, v118);
        std::wstring::operator=(v10 + 24, v20);
        std::wstring::~wstring((__int64)v118);
        if ( v121 )
          std::wstring::~wstring((__int64)v120);
        std::wstring::~wstring((__int64)&v115);
      }
      `Diagnostics::Analyzer_UpdateEventHistory<Diagnostics::UpdateEventHistoryWuProviders>::PerformAnalysis'::`2'::UpdateGroup::EventEntry::EventEntry((__int64)&v163);
      v115 = 0;
      v116 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v115, L"ENDTIME", 7u);
      v21 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
      std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v21, &v144);
      if ( v121 )
        std::wstring::~wstring((__int64)v120);
      std::wstring::~wstring((__int64)&v115);
      v115 = 0;
      v116 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v115, L"STARTTIME", 9u);
      v22 = Diagnostics::OTelLogRecord::GetAttribute(v172, v118, &v115);
      std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v22, v162);
      if ( v119 )
        std::wstring::~wstring((__int64)v118);
      std::wstring::~wstring((__int64)&v115);
      if ( !v145 || (v23 = std::operator==<wchar_t>(&v144, L"NULL"), v24 = &v144, v23) )
        v24 = (__int128 *)v162;
      std::wstring::wstring((__int64)String, (__int64)v24);
      if ( v161 && !(unsigned __int8)std::operator==<wchar_t>(String, L"NULL") )
      {
        try
        {
          v163 = std::stoll(String);
        }
        catch ( ... )
        {
          v163 = 100 * v173 / 1000000;
          v10 = v123;
          v5 = v147;
          v4 = v150;
          v127 = v150;
        }
      }
      else
      {
        v163 = 100 * v173 / 1000000;
      }
      v25 = Diagnostics::DataStyles::MillisecondsSinceEpoch(v118, v162);
      std::wstring::operator=(v164, v25);
      std::wstring::~wstring((__int64)v118);
      v26 = Diagnostics::DataStyles::MillisecondsSinceEpoch(v118, &v144);
      std::wstring::operator=(v165, v26);
      std::wstring::~wstring((__int64)v118);
      v115 = 0;
      v116 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v115, L"EVENT", 5u);
      v27 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
      v28 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v27, v118);
      std::wstring::operator=(v166, v28);
      std::wstring::~wstring((__int64)v118);
      if ( v121 )
        std::wstring::~wstring((__int64)v120);
      std::wstring::~wstring((__int64)&v115);
      v115 = 0;
      v116 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v115, L"RESULT", 6u);
      v29 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
      v30 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v29, v118);
      std::wstring::operator=(v167, v30);
      std::wstring::~wstring((__int64)v118);
      if ( v121 )
        std::wstring::~wstring((__int64)v120);
      std::wstring::~wstring((__int64)&v115);
      v115 = 0;
      v116 = 0u;
      std::wstring::_Construct<1,wchar_t const *>(&v115, L"REASON", 6u);
      v31 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v115);
      v32 = std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(v31, v118);
      std::wstring::operator=(v168, v32);
      std::wstring::~wstring((__int64)v118);
      if ( v121 )
        std::wstring::~wstring((__int64)v120);
      std::wstring::~wstring((__int64)&v115);
      v124 = 0;
      v125 = 0;
      v126 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v124, L"APPROVALS", 9u);
      v33 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v124);
      if ( *(_BYTE *)(v33 + 32) )
      {
        v34 = *(__m128i *)v33;
        v115 = *(__m128i *)v33;
        v35 = *(_OWORD *)(v33 + 16);
        v116 = v35;
        *(_QWORD *)(v33 + 16) = 0;
        *(_QWORD *)(v33 + 24) = 7;
        *(_WORD *)v33 = 0;
      }
      else
      {
        v115 = 0;
        v116 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v115, &psz, 0);
        v35 = v116;
        v34 = v115;
      }
      std::wstring::~wstring((__int64)v169);
      v169[0] = v34;
      v169[1] = v35;
      *(_QWORD *)&v116 = 0;
      *((_QWORD *)&v116 + 1) = 7;
      v115.m128i_i16[0] = 0;
      std::wstring::~wstring((__int64)&v115);
      if ( v121 )
        std::wstring::~wstring((__int64)v120);
      std::wstring::~wstring((__int64)&v124);
      v124 = 0;
      v125 = 0;
      v126 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v124, L"OTHER", 5u);
      v36 = Diagnostics::OTelLogRecord::GetAttribute(v172, v120, &v124);
      v5 |= 0x60u;
      if ( *(_BYTE *)(v36 + 32) )
      {
        v37 = *(__m128i *)v36;
        v115 = *(__m128i *)v36;
        v38 = *(_OWORD *)(v36 + 16);
        v116 = v38;
        *(_QWORD *)(v36 + 16) = 0;
        *(_QWORD *)(v36 + 24) = 7;
        *(_WORD *)v36 = 0;
      }
      else
      {
        v115 = 0;
        v116 = 0u;
        std::wstring::_Construct<1,wchar_t const *>(&v115, &psz, 0);
        v38 = v116;
        v37 = v115;
      }
      std::wstring::~wstring((__int64)v170);
      v170[0] = v37;
      v170[1] = v38;
      *(_QWORD *)&v116 = 0;
      *((_QWORD *)&v116 + 1) = 7;
      v115.m128i_i16[0] = 0;
      std::wstring::~wstring((__int64)&v115);
      if ( v121 )
        std::wstring::~wstring((__int64)v120);
      std::wstring::~wstring((__int64)&v124);
      v39 = v10[29];
      if ( v39 == v10[30] )
      {
        ____Emplace_reallocate_UEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___std__V__span___CBVpath_filesystem_std___0_0_7__Z____vector_UEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___std__V__span___CBVpath_filesystem_std___0_0_7__Z_V__allocator_UEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___std__V__span___CBVpath_filesystem_std___0_0_7__Z__7__std__AEAAPEAUEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___1_V__span___CBVpath_filesystem_std___0_0_1__Z_QEAU23_1__456_UEBA_AV71_0_Z___QEAU23_1__456_UEBA_AV71_0_Z__Z(
          v10 + 28,
          v10[29],
          (__int64)&v163);
      }
      else
      {
        `Diagnostics::Analyzer_UpdateEventHistory<Diagnostics::UpdateEventHistoryWuProviders>::PerformAnalysis'::`2'::UpdateGroup::EventEntry::EventEntry(
          v39,
          (__int64)&v163);
        *(_QWORD *)(v40 + 8) += 232LL;
      }
      std::wstring::~wstring((__int64)String);
      std::wstring::~wstring((__int64)v162);
      std::wstring::~wstring((__int64)&v144);
      std::wstring::~wstring((__int64)v170);
      std::wstring::~wstring((__int64)v169);
      std::wstring::~wstring((__int64)v168);
      std::wstring::~wstring((__int64)v167);
      std::wstring::~wstring((__int64)v166);
      std::wstring::~wstring((__int64)v165);
      std::wstring::~wstring((__int64)v164);
      std::wstring::~wstring((__int64)v171);
    }
    std::wstring::~wstring((__int64)&v153);
    std::wstring::~wstring((__int64)&v155);
    if ( v174 )
      Diagnostics::OTelLogRecord::~OTelLogRecord((Diagnostics::OTelLogRecord *)v172);
  }
  if ( *(_QWORD *)&v157[1] )
  {
    v151 = 0;
    v152 = 0;
    ____0V__move_iterator_V___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std___std___std___std___std___0A____vector_U__pair_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std__V__allocator_U__pair_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std___2__std__QEAA_V__move_iterator_V___List_iterator_V___List_val_U___List_simple_types_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std___std___std___std___1_0AEBV__allocator_U__pair_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std___1__Z(
      (__int64 *)&v151,
      **((_QWORD ***)&v157[0] + 1),
      *((_QWORD **)&v157[0] + 1));
    v41 = v151;
    if ( (_QWORD)v151 != *((_QWORD *)&v151 + 1) )
    {
      v42 = (__int64 **)(v151 + 256);
      do
      {
        ____Sort_unchecked_PEAUEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryOther_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___std__V__span___CBVpath_filesystem_std___0_0_7__Z_V_lambda_1___BD___345_UEBA_AV67_0_Z__std__YAXPEAUEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryOther_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___0_V__span___CBVpath_filesystem_std___0_0_0__Z_1_JV_lambda_1___BD___345_UEBA_AV60_0_Z__Z(
          *v42,
          v42[1],
          0x34F72C234F72C235LL * (v42[1] - *v42),
          v117);
        v42 += 35;
      }
      while ( v42 - 32 != *((__int64 ***)&v41 + 1) );
      v41 = v151;
    }
    ____Sort_unchecked_PEAU__pair_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std__V_lambda_2___1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std__YAXPEAU__pair_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__0_0_JV_lambda_2___1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___0_V__span___CBVpath_filesystem_std___0_0_0__Z__Z(
      v41,
      *((__int128 **)&v41 + 1),
      0xAF8AF8AF8AF8AF8BuLL * ((__int64)(*((_QWORD *)&v41 + 1) - v41) >> 3),
      v117);
    v150 = 0;
    web::json::value::array(&v150);
    v123 = 0;
    v115.m128i_i64[0] = *((_QWORD *)&v151 + 1);
    if ( (_QWORD)v151 != *((_QWORD *)&v151 + 1) )
    {
      v43 = (__int64 *)(v151 + 264);
      do
      {
        v44 = *(v43 - 1);
        if ( (unsigned __int64)(0x34F72C234F72C235LL * ((*v43 - v44) >> 3)) > 0x64 )
        {
          v45 = v44 + 23200;
          ____Destroy_range_V__allocator_UEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryOther_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___std__V__span___CBVpath_filesystem_std___0_0_7__Z__std___std__YAXPEAUEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryOther_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___0_V__span___CBVpath_filesystem_std___0_0_0__Z_QEAU12_1__345_UEBA_AV60_0_Z_AEAV__allocator_UEventEntry_UpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryOther_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___std__V__span___CBVpath_filesystem_std___0_0_7__Z__0__Z(
            v45,
            *v43);
          *v43 = v45;
        }
        v147 = 0;
        web::json::value::object(&v147, 0);
        if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)v43 - 68) )
        {
          v46 = std::wstring::wstring((__int64)v118, (__int64)(v43 - 17));
          v47 = (__int64 *)web::json::value::string(&v128, v46);
          v144 = 0;
          v145 = 0;
          v146 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v144, L"Alias", 5u);
          v48 = (__int64 *)web::json::value::operator[](&v147, &v144);
          if ( v48 != v47 )
          {
            v49 = *v48;
            *v48 = *v47;
            *v47 = v49;
          }
          std::wstring::~wstring((__int64)&v144);
          if ( v128 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v128 + 192LL))(v128, 1);
        }
        if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)v43 - 84) )
        {
          v50 = std::wstring::wstring((__int64)v118, (__int64)(v43 - 21));
          v51 = (__int64 *)web::json::value::string(&v129, v50);
          v144 = 0;
          v145 = 0;
          v146 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v144, L"Category", 8u);
          v52 = (__int64 *)web::json::value::operator[](&v147, &v144);
          if ( v52 != v51 )
          {
            v53 = *v52;
            *v52 = *v51;
            *v51 = v53;
          }
          std::wstring::~wstring((__int64)&v144);
          if ( v129 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v129 + 192LL))(v129, 1);
        }
        v54 = std::wstring::wstring((__int64)v118, (__int64)(v43 - 25));
        v55 = (__int64 *)web::json::value::string(&v130, v54);
        v144 = 0;
        v145 = 0;
        v146 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v144, L"ID", 2u);
        v56 = (__int64 *)web::json::value::operator[](&v147, &v144);
        if ( v56 != v55 )
        {
          v57 = *v56;
          *v56 = *v55;
          *v55 = v57;
        }
        std::wstring::~wstring((__int64)&v144);
        if ( v130 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v130 + 192LL))(v130, 1);
        v58 = std::wstring::wstring((__int64)v118, (__int64)(v43 - 29));
        v59 = (__int64 *)web::json::value::string(&v131, v58);
        v144 = 0;
        v145 = 0;
        v146 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v144, L"ProviderID", 0xAu);
        v60 = (__int64 *)web::json::value::operator[](&v147, &v144);
        if ( v60 != v59 )
        {
          v61 = *v60;
          *v60 = *v59;
          *v59 = v61;
        }
        std::wstring::~wstring((__int64)&v144);
        if ( v131 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v131 + 192LL))(v131, 1);
        if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)v43 - 36) )
        {
          v62 = std::wstring::wstring((__int64)v118, (__int64)(v43 - 9));
          v63 = (__int64 *)web::json::value::string(&v132, v62);
          v144 = 0;
          v145 = 0;
          v146 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v144, L"FlightID", 8u);
          v64 = (__int64 *)web::json::value::operator[](&v147, &v144);
          if ( v64 != v63 )
          {
            v65 = *v64;
            *v64 = *v63;
            *v63 = v65;
          }
          std::wstring::~wstring((__int64)&v144);
          if ( v132 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v132 + 192LL))(v132, 1);
        }
        if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)v43 - 52) )
        {
          v66 = std::wstring::wstring((__int64)v118, (__int64)(v43 - 13));
          v67 = (__int64 *)web::json::value::string(&v133, v66);
          v144 = 0;
          v145 = 0;
          v146 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v144, L"IsSeeker", 8u);
          v68 = (__int64 *)web::json::value::operator[](&v147, &v144);
          if ( v68 != v67 )
          {
            v69 = *v68;
            *v68 = *v67;
            *v67 = v69;
          }
          std::wstring::~wstring((__int64)&v144);
          if ( v133 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v133 + 192LL))(v133, 1);
        }
        if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)v43 - 20) )
        {
          v70 = std::wstring::wstring((__int64)v118, (__int64)(v43 - 5));
          v71 = (__int64 *)web::json::value::string(&v134, v70);
          v144 = 0;
          v145 = 0;
          v146 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v144, L"UpdateMetadata", 0xEu);
          v72 = (__int64 *)web::json::value::operator[](&v147, &v144);
          if ( v72 != v71 )
          {
            v73 = *v72;
            *v72 = *v71;
            *v71 = v73;
          }
          std::wstring::~wstring((__int64)&v144);
          if ( v134 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v134 + 192LL))(v134, 1);
        }
        v148 = 0;
        web::json::value::array(&v148);
        v74 = 0;
        v75 = *v43;
        v76 = *(v43 - 1);
        if ( 0x34F72C234F72C235LL * ((*v43 - v76) >> 3) )
        {
          v77 = 0;
          do
          {
            v149 = 0;
            web::json::value::object(&v149, 0);
            if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)(v76 + v77 + 72)) )
            {
              v78 = std::wstring::wstring((__int64)v118, v76 + v77 + 72);
              v79 = (__int64 *)web::json::value::string(&v135, v78);
              v144 = 0;
              v145 = 0;
              v146 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v144, L"Action", 6u);
              v80 = (__int64 *)web::json::value::operator[](&v149, &v144);
              if ( v80 != v79 )
              {
                v81 = *v80;
                *v80 = *v79;
                *v79 = v81;
              }
              std::wstring::~wstring((__int64)&v144);
              if ( v135 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v135 + 192LL))(v135, 1);
            }
            if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)(v76 + v77 + 8)) )
            {
              v82 = std::wstring::wstring((__int64)v118, v76 + v77 + 8);
              v83 = (__int64 *)web::json::value::string(&v136, v82);
              v144 = 0;
              v145 = 0;
              v146 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v144, L"BeginTime", 9u);
              v84 = (__int64 *)web::json::value::operator[](&v149, &v144);
              if ( v84 != v83 )
              {
                v85 = *v84;
                *v84 = *v83;
                *v83 = v85;
              }
              std::wstring::~wstring((__int64)&v144);
              if ( v136 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v136 + 192LL))(v136, 1);
            }
            if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)(v76 + v77 + 40)) )
            {
              v86 = std::wstring::wstring((__int64)v118, v76 + v77 + 40);
              v87 = (__int64 *)web::json::value::string(&v137, v86);
              v144 = 0;
              v145 = 0;
              v146 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v144, L"EndTime", 7u);
              v88 = (__int64 *)web::json::value::operator[](&v149, &v144);
              if ( v88 != v87 )
              {
                v89 = *v88;
                *v88 = *v87;
                *v87 = v89;
              }
              std::wstring::~wstring((__int64)&v144);
              if ( v137 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v137 + 192LL))(v137, 1);
            }
            if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)(v76 + v77 + 104)) )
            {
              v90 = std::wstring::wstring((__int64)v118, v76 + v77 + 104);
              v91 = (__int64 *)web::json::value::string(&v138, v90);
              v144 = 0;
              v145 = 0;
              v146 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v144, L"Result", 6u);
              v92 = (__int64 *)web::json::value::operator[](&v149, &v144);
              if ( v92 != v91 )
              {
                v93 = *v92;
                *v92 = *v91;
                *v91 = v93;
              }
              std::wstring::~wstring((__int64)&v144);
              if ( v138 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v138 + 192LL))(v138, 1);
            }
            if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)(v76 + v77 + 136)) )
            {
              v94 = std::wstring::wstring((__int64)v118, v76 + v77 + 136);
              v95 = (__int64 *)web::json::value::string(&v139, v94);
              v144 = 0;
              v145 = 0;
              v146 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v144, L"Reason", 6u);
              v96 = (__int64 *)web::json::value::operator[](&v149, &v144);
              if ( v96 != v95 )
              {
                v97 = *v96;
                *v96 = *v95;
                *v95 = v97;
              }
              std::wstring::~wstring((__int64)&v144);
              if ( v139 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v139 + 192LL))(v139, 1);
            }
            if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)(v76 + v77 + 200)) )
            {
              v98 = std::wstring::wstring((__int64)v118, v76 + v77 + 200);
              v99 = (__int64 *)web::json::value::string(&v140, v98);
              v144 = 0;
              v145 = 0;
              v146 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v144, L"Other", 5u);
              v100 = (__int64 *)web::json::value::operator[](&v149, &v144);
              if ( v100 != v99 )
              {
                v101 = *v100;
                *v100 = *v99;
                *v99 = v101;
              }
              std::wstring::~wstring((__int64)&v144);
              if ( v140 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v140 + 192LL))(v140, 1);
            }
            if ( !(unsigned __int8)Diagnostics::ShouldOmitPatternValue((wchar_t *)(v76 + v77 + 168)) )
            {
              v102 = std::wstring::wstring((__int64)v118, v77 + v76 + 168);
              v103 = (__int64 *)web::json::value::string(&v141, v102);
              v144 = 0;
              v145 = 0;
              v146 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v144, L"UpdateApprovals", 0xFu);
              v104 = (__int64 *)web::json::value::operator[](&v149, &v144);
              if ( v104 != v103 )
              {
                v105 = *v104;
                *v104 = *v103;
                *v103 = v105;
              }
              std::wstring::~wstring((__int64)&v144);
              if ( v141 )
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v141 + 192LL))(v141, 1);
            }
            v106 = web::json::value::operator[](&v148, v74);
            web::json::value::operator=(v106, &v149);
            if ( v149 )
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v149 + 192LL))(v149, 1);
            ++v74;
            v77 += 232;
            v75 = *v43;
            v76 = *(v43 - 1);
          }
          while ( v74 < 0x34F72C234F72C235LL * ((*v43 - v76) >> 3) );
        }
        v107 = 0x34F72C234F72C235LL * ((v75 - *(v43 - 1)) >> 3);
        v108 = operator new(0x18u);
        *(_QWORD *)&v122 = v108;
        *v108 = &web::json::details::_Number::`vftable';
        v108[1] = v107;
        *((_DWORD *)v108 + 4) = 1;
        v142 = v108;
        v144 = 0;
        v145 = 0;
        v146 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v144, L"UpdateEventCount", 0x10u);
        v109 = (void **)web::json::value::operator[](&v147, &v144);
        v110 = v108;
        if ( v109 != (void **)&v142 )
        {
          v110 = *v109;
          *v109 = v108;
          v108 = v110;
        }
        std::wstring::~wstring((__int64)&v144);
        if ( v110 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v108 + 192LL))(v108, 1);
        v144 = 0;
        v145 = 0;
        v146 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v144, L"UpdateEvents", 0xCu);
        v111 = web::json::value::operator[](&v147, &v144);
        web::json::value::operator=(v111, &v148);
        std::wstring::~wstring((__int64)&v144);
        v112 = v123;
        v123 = (__int64 *)((char *)v123 + 1);
        v113 = web::json::value::operator[](&v150, v112);
        web::json::value::operator=(v113, &v147);
        if ( v148 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v148 + 192LL))(v148, 1);
        if ( v147 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v147 + 192LL))(v147, 1);
        v43 += 35;
      }
      while ( v43 - 33 != (__int64 *)v115.m128i_i64[0] );
      v4 = v127;
    }
    *(_QWORD *)v4 = v150;
    *(_BYTE *)(v4 + 8) = 1;
    __Tidy___vector_U__pair_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryOther_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std__V__allocator_U__pair_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryOther_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std___2__std__AEAAXXZ(&v151);
  }
  else
  {
    *(_BYTE *)(v4 + 8) = 0;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,Diagnostics::EtwFileProcessor::SpanStartData>>>>>>((__int64)&v157[1] + 8);
  __1__list_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std__V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std__UUpdateGroup__1__PerformAnalysis___Analyzer_UpdateEventHistory_UUpdateEventHistoryWuProviders_Diagnostics___Diagnostics__UEBA_AV__optional_Vvalue_json_web___2_V__span___CBVpath_filesystem_std___0_0_2__Z__std___2__std__QEAA_XZ((void **)v157 + 1);
  std::vector<Diagnostics::OTelFile>::~vector<Diagnostics::OTelFile>(v158);
  return v4;
}

```

## disassembly

```asm
0x18003e240  mov     r11, rsp
0x18003e243  mov     [r11+8], rbx
0x18003e247  mov     [r11+20h], rsi
0x18003e24b  push    rdi
0x18003e24c  push    r12
0x18003e24e  push    r13
0x18003e250  push    r14
0x18003e252  push    r15
0x18003e254  sub     rsp, 550h
0x18003e25b  movaps  xmmword ptr [r11-38h], xmm6
0x18003e260  movaps  xmmword ptr [r11-48h], xmm7
0x18003e265  mov     rax, cs:__security_cookie
0x18003e26c  xor     rax, rsp
0x18003e26f  mov     [rsp+578h+var_58], rax
0x18003e277  mov     r15, rdx
0x18003e27a  mov     [rsp+578h+var_4A0], rdx
0x18003e282  mov     [rsp+578h+var_3E0], rdx
0x18003e28a  xor     edi, edi
0x18003e28c  mov     ebx, edi
0x18003e28e  mov     [rsp+578h+var_420], ebx
0x18003e295  xorps   xmm0, xmm0
0x18003e298  xor     eax, eax
0x18003e29a  movups  [rsp+578h+var_338], xmm0
0x18003e2a2  movups  [rsp+578h+var_328], xmm0
0x18003e2aa  mov     [r11-318h], rax
0x18003e2b1  mov     [r11-4D8h], rdi
0x18003e2b8  mov     [r11-4D0h], rdi
0x18003e2bf  movaps  xmm0, [rsp+578h+var_4D8]
0x18003e2c7  movdqa  [rsp+578h+var_4D8], xmm0
0x18003e2d0  movups  xmm1, xmmword ptr [r8]
0x18003e2d4  movdqu  [rsp+578h+var_558], xmm1
0x18003e2da  lea     r8, [r11-4D8h]
0x18003e2e1  lea     rdx, [rsp+578h+var_558]
0x18003e2e6  lea     rcx, [r11-338h]
0x18003e2ed  call    ??0OTelReader@Diagnostics@@QEAA@V?$span@$$CBVpath@filesystem@std@@$0?0@std@@V?$span@$$CBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBU?$pair@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@V?$span@$$CBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$0?0@2@@std@@$0?0@2@@std@@$0?0@3@@Z; Diagnostics::OTelReader::OTelReader(std::span<std::filesystem::path const,-1>,std::span<std::pair<std::wstring_view,std::span<std::pair<std::wstring_view,std::span<std::wstring_view const,-1>> const,-1>> const,-1>)
0x18003e2f2  nop
0x18003e2f3  xor     edx, edx; Val
0x18003e2f5  lea     r8d, [rdi+40h]; Size
0x18003e2f9  lea     rcx, [rsp+578h+var_378]; void *
0x18003e301  call    memset
0x18003e306  mov     [rsp+578h+var_378], edi
0x18003e30d  mov     [rsp+578h+var_370], rdi
0x18003e315  mov     [rsp+578h+var_368], rdi
0x18003e31d  mov     ecx, 128h; Size
0x18003e322  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e327  mov     [rax], rax
0x18003e32a  mov     [rax+8], rax
0x18003e32e  mov     [rsp+578h+var_370], rax
0x18003e336  mov     [rsp+578h+var_360], rdi
0x18003e33e  xorps   xmm0, xmm0
0x18003e341  movdqa  [rsp+578h+var_358], xmm0
0x18003e34a  lea     r14d, [rdi+7]
0x18003e34e  mov     [rsp+578h+var_348], r14
0x18003e356  lea     r13d, [rdi+8]
0x18003e35a  mov     [rsp+578h+var_340], r13
0x18003e362  mov     [rsp+578h+var_378], 3F800000h
0x18003e36d  mov     r8, rax
0x18003e370  lea     edx, [rdi+10h]
0x18003e373  lea     rcx, [rsp+578h+var_360]
0x18003e37b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UEventStats@?1??ClassifyPattern@?$Connector_UpdateEventPattern@UUpdateEventPatternWU@Diagnostics@@@Diagnostics@@CA?AUPatternResult@56@AEBUUpdateGroup@56@@Z@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,`Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::ClassifyPattern(Diagnostics::Connector_UpdateEventPattern<Diagnostics::UpdateEventPatternWU>::UpdateGroup const &)'::`2'::EventStats>>>>)
0x18003e380  nop
0x18003e381  lea     r12d, [rdi+5]
0x18003e385  lea     rdx, [rsp+578h+var_1B8]
0x18003e38d  lea     rcx, [rsp+578h+var_338]
0x18003e395  call    ?ReadNextEvent@OTelReader@Diagnostics@@QEAA?AV?$optional@VOTelLogRecord@Diagnostics@@@std@@XZ; Diagnostics::OTelReader::ReadNextEvent(void)
0x18003e39a  nop
0x18003e39b  cmp     [rsp+578h+var_68], dil
0x18003e3a3  jz      loc_18003EF2D
0x18003e3a9  xorps   xmm0, xmm0
0x18003e3ac  movups  [rsp+578h+var_558], xmm0
0x18003e3b1  mov     qword ptr [rsp+578h+var_548], rdi
0x18003e3b6  mov     qword ptr [rsp+578h+var_548+8], rdi
0x18003e3bb  mov     r8d, 0Ah
0x18003e3c1  lea     rdx, aProviderid; "PROVIDERID"
0x18003e3c8  lea     rcx, [rsp+578h+var_558]
0x18003e3cd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e3d2  nop
0x18003e3d3  lea     r8, [rsp+578h+var_558]
0x18003e3d8  lea     rdx, [rsp+578h+var_530]
0x18003e3dd  lea     rcx, [rsp+578h+var_1B8]
0x18003e3e5  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003e3ea  nop
0x18003e3eb  cmp     [rax+20h], dil
0x18003e3ef  jz      short loc_18003E415
0x18003e3f1  movups  xmm0, xmmword ptr [rax]
0x18003e3f4  movups  [rsp+578h+var_3A0], xmm0
0x18003e3fc  movups  xmm1, xmmword ptr [rax+10h]
0x18003e400  movups  [rsp+578h+var_390], xmm1
0x18003e408  mov     [rax+10h], rdi
0x18003e40c  mov     [rax+18h], r14
0x18003e410  mov     [rax], di
0x18003e413  jmp     short loc_18003E448
0x18003e415  xorps   xmm0, xmm0
0x18003e418  movups  [rsp+578h+var_3A0], xmm0
0x18003e420  mov     qword ptr [rsp+578h+var_390], rdi
0x18003e428  mov     qword ptr [rsp+578h+var_390+8], rdi
0x18003e430  xor     r8d, r8d
0x18003e433  lea     rdx, psz
0x18003e43a  lea     rcx, [rsp+578h+var_3A0]
0x18003e442  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e447  nop
0x18003e448  cmp     [rsp+578h+var_510], dil
0x18003e44d  jz      short loc_18003E45A
0x18003e44f  lea     rcx, [rsp+578h+var_530]
0x18003e454  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e459  nop
0x18003e45a  lea     rcx, [rsp+578h+var_558]
0x18003e45f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e464  xorps   xmm0, xmm0
0x18003e467  movups  [rsp+578h+var_558], xmm0
0x18003e46c  mov     qword ptr [rsp+578h+var_548], rdi
0x18003e471  mov     qword ptr [rsp+578h+var_548+8], rdi
0x18003e476  mov     r8, r13
0x18003e479  lea     rdx, aUpdateid_0; "UPDATEID"
0x18003e480  lea     rcx, [rsp+578h+var_558]
0x18003e485  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e48a  nop
0x18003e48b  lea     r8, [rsp+578h+var_558]
0x18003e490  lea     rdx, [rsp+578h+var_508]
0x18003e495  lea     rcx, [rsp+578h+var_1B8]
0x18003e49d  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003e4a2  nop
0x18003e4a3  or      ebx, 18h
0x18003e4a6  cmp     [rax+20h], dil
0x18003e4aa  jz      short loc_18003E4D0
0x18003e4ac  movups  xmm0, xmmword ptr [rax]
0x18003e4af  movups  [rsp+578h+var_3C0], xmm0
0x18003e4b7  movups  xmm1, xmmword ptr [rax+10h]
0x18003e4bb  movups  [rsp+578h+var_3B0], xmm1
0x18003e4c3  mov     [rax+10h], rdi
0x18003e4c7  mov     [rax+18h], r14
0x18003e4cb  mov     [rax], di
0x18003e4ce  jmp     short loc_18003E503
0x18003e4d0  xorps   xmm0, xmm0
0x18003e4d3  movups  [rsp+578h+var_3C0], xmm0
0x18003e4db  mov     qword ptr [rsp+578h+var_3B0], rdi
0x18003e4e3  mov     qword ptr [rsp+578h+var_3B0+8], rdi
0x18003e4eb  xor     r8d, r8d
0x18003e4ee  lea     rdx, psz
0x18003e4f5  lea     rcx, [rsp+578h+var_3C0]
0x18003e4fd  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e502  nop
0x18003e503  mov     dword ptr [rsp+578h+var_3F8], ebx
0x18003e50a  cmp     [rsp+578h+var_4E8], dil
0x18003e512  jz      short loc_18003E51F
0x18003e514  lea     rcx, [rsp+578h+var_508]
0x18003e519  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e51e  nop
0x18003e51f  lea     rcx, [rsp+578h+var_558]
0x18003e524  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e529  cmp     qword ptr [rsp+578h+var_390], rdi
0x18003e531  jz      loc_18003EEF1
0x18003e537  cmp     qword ptr [rsp+578h+var_3B0], rdi
0x18003e53f  jz      loc_18003EEF1
0x18003e545  lea     r8, asc_1800AA2E0; "|"
0x18003e54c  lea     rdx, [rsp+578h+var_3A0]
0x18003e554  lea     rcx, [rsp+578h+var_4C0]; void *
0x18003e55c  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x18003e561  nop
0x18003e562  lea     r8, [rsp+578h+var_3C0]
0x18003e56a  mov     rdx, rax
0x18003e56d  lea     rcx, [rsp+578h+var_1D8]
0x18003e575  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<wchar_t>(std::wstring &&,std::wstring const &)
0x18003e57a  nop
0x18003e57b  lea     rcx, [rsp+578h+var_4C0]
0x18003e583  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e588  lea     r8, [rsp+578h+var_1D8]
0x18003e590  lea     rdx, [rsp+578h+var_4D8]
0x18003e598  lea     rcx, [rsp+578h+var_378]
0x18003e5a0  call    ??$_Try_emplace@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$V@?$_Hash@V?$_Umap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?1??PerformAnalysis@?$Analyzer_UpdateEventHistory@UUpdateEventHistoryWuProviders@Diagnostics@@@Diagnostics@@UEBA?AV?$optional@Vvalue@json@web@@@2@V?$span@$$CBVpath@filesystem@std@@$0?0@2@@Z@V?$_Uhash_compare@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$hash@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@U?$equal_to@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?1??PerformAnalysis@?$Analyzer_UpdateEventHistory@UUpdateEventHistoryWuProviders@Diagnostics@@@Diagnostics@@UEBA?AV?$optional@Vvalue@json@web@@@2@V?$span@$$CBVpath@filesystem@std@@$0?0@2@@Z@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UUpdateGroup@?1??PerformAnalysis@?$Analyzer_UpdateEventHistory@UUpdateEventHistoryWuProviders@Diagnostics@@@Diagnostics@@UEBA?AV?$optional@Vvalue@json@web@@@2@V?$span@$$CBVpath@filesystem@std@@$0?0@2@@Z@@std@@PEAX@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Hash<std::_Umap_traits<std::wstring,`Diagnostics::Analyzer_UpdateEventHistory<Diagnostics::UpdateEventHistoryWuProviders>::PerformAnalysis(std::span<std::filesystem::path const,-1>)'::`2'::UpdateGroup,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,`Diagnostics::Analyzer_UpdateEventHistory<Diagnostics::UpdateEventHistoryWuProviders>::PerformAnalysis(std::span<std::filesystem::path const,-1>)'::`2'::UpdateGroup>>,0>>::_Try_emplace<std::wstring const &,>(std::wstring const &)
0x18003e5a5  mov     rsi, [rax]
0x18003e5a8  add     rsi, 30h ; '0'
0x18003e5ac  mov     [rsp+578h+var_4C8], rsi
0x18003e5b4  cmp     [rsi+10h], rdi
0x18003e5b8  jnz     loc_18003E875
0x18003e5be  lea     rdx, [rsp+578h+var_3A0]
0x18003e5c6  mov     rcx, rsi; void *
0x18003e5c9  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003e5ce  lea     rcx, [rsi+20h]; void *
0x18003e5d2  lea     rdx, [rsp+578h+var_3C0]
0x18003e5da  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003e5df  xorps   xmm0, xmm0
0x18003e5e2  movups  [rsp+578h+var_558], xmm0
0x18003e5e7  mov     qword ptr [rsp+578h+var_548], rdi
0x18003e5ec  mov     qword ptr [rsp+578h+var_548+8], rdi
0x18003e5f1  mov     r8, r13
0x18003e5f4  lea     rdx, aCategory_0; "CATEGORY"
0x18003e5fb  lea     rcx, [rsp+578h+var_558]
0x18003e600  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e605  nop
0x18003e606  lea     r8, [rsp+578h+var_558]
0x18003e60b  lea     rdx, [rsp+578h+var_508]
0x18003e610  lea     rcx, [rsp+578h+var_1B8]
0x18003e618  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003e61d  nop
0x18003e61e  lea     rdx, [rsp+578h+var_530]
0x18003e623  mov     rcx, rax
0x18003e626  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18003e62b  lea     rcx, [rsi+40h]
0x18003e62f  mov     rdx, rax
0x18003e632  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e637  lea     rcx, [rsp+578h+var_530]
0x18003e63c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e641  nop
0x18003e642  cmp     [rsp+578h+var_4E8], dil
0x18003e64a  jz      short loc_18003E657
0x18003e64c  lea     rcx, [rsp+578h+var_508]
0x18003e651  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e656  nop
0x18003e657  lea     rcx, [rsp+578h+var_558]
0x18003e65c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e661  xorps   xmm0, xmm0
0x18003e664  movups  [rsp+578h+var_558], xmm0
0x18003e669  mov     qword ptr [rsp+578h+var_548], rdi
0x18003e66e  mov     qword ptr [rsp+578h+var_548+8], rdi
0x18003e673  mov     r8, r12
0x18003e676  lea     rdx, aTitle; "TITLE"
0x18003e67d  lea     rcx, [rsp+578h+var_558]
0x18003e682  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e687  nop
0x18003e688  lea     r8, [rsp+578h+var_558]
0x18003e68d  lea     rdx, [rsp+578h+var_508]
0x18003e692  lea     rcx, [rsp+578h+var_1B8]
0x18003e69a  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003e69f  nop
0x18003e6a0  lea     rdx, [rsp+578h+var_530]
0x18003e6a5  mov     rcx, rax
0x18003e6a8  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18003e6ad  lea     rcx, [rsi+60h]
0x18003e6b1  mov     rdx, rax
0x18003e6b4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e6b9  lea     rcx, [rsp+578h+var_530]
0x18003e6be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e6c3  nop
0x18003e6c4  cmp     [rsp+578h+var_4E8], dil
0x18003e6cc  jz      short loc_18003E6D9
0x18003e6ce  lea     rcx, [rsp+578h+var_508]
0x18003e6d3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e6d8  nop
0x18003e6d9  lea     rcx, [rsp+578h+var_558]
0x18003e6de  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e6e3  xorps   xmm0, xmm0
0x18003e6e6  movups  [rsp+578h+var_558], xmm0
0x18003e6eb  mov     qword ptr [rsp+578h+var_548], rdi
0x18003e6f0  mov     qword ptr [rsp+578h+var_548+8], rdi
0x18003e6f5  mov     r8, r13
0x18003e6f8  lea     rdx, aIsseeker; "ISSEEKER"
0x18003e6ff  lea     rcx, [rsp+578h+var_558]
0x18003e704  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e709  nop
0x18003e70a  lea     r8, [rsp+578h+var_558]
0x18003e70f  lea     rdx, [rsp+578h+var_508]
0x18003e714  lea     rcx, [rsp+578h+var_1B8]
0x18003e71c  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003e721  nop
0x18003e722  lea     rdx, [rsp+578h+var_530]
0x18003e727  mov     rcx, rax
0x18003e72a  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18003e72f  lea     rcx, [rsi+80h]
0x18003e736  mov     rdx, rax
0x18003e739  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e73e  lea     rcx, [rsp+578h+var_530]
0x18003e743  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e748  nop
0x18003e749  cmp     [rsp+578h+var_4E8], dil
0x18003e751  jz      short loc_18003E75E
0x18003e753  lea     rcx, [rsp+578h+var_508]
0x18003e758  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e75d  nop
0x18003e75e  lea     rcx, [rsp+578h+var_558]
0x18003e763  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e768  xorps   xmm0, xmm0
0x18003e76b  movups  [rsp+578h+var_558], xmm0
0x18003e770  mov     qword ptr [rsp+578h+var_548], rdi
0x18003e775  mov     qword ptr [rsp+578h+var_548+8], rdi
0x18003e77a  mov     r8, r13
0x18003e77d  lea     rdx, aFlightid_0; "FLIGHTID"
0x18003e784  lea     rcx, [rsp+578h+var_558]
0x18003e789  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003e78e  nop
0x18003e78f  lea     r8, [rsp+578h+var_558]
0x18003e794  lea     rdx, [rsp+578h+var_508]
0x18003e799  lea     rcx, [rsp+578h+var_1B8]
0x18003e7a1  call    ?GetAttribute@OTelLogRecord@Diagnostics@@QEBA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@@Z; Diagnostics::OTelLogRecord::GetAttribute(std::wstring const &)
0x18003e7a6  nop
0x18003e7a7  lea     rdx, [rsp+578h+var_530]
0x18003e7ac  mov     rcx, rax
0x18003e7af  call    ??$value_or@AEAY00$$CB_W@?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@QEHAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@AEAY00$$CB_W@Z; std::optional<std::wstring>::value_or<wchar_t const (&)[1]>(wchar_t const (&)[1])
0x18003e7b4  lea     rcx, [rsi+0A0h]
0x18003e7bb  mov     rdx, rax
0x18003e7be  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003e7c3  lea     rcx, [rsp+578h+var_530]
0x18003e7c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e7cd  nop
0x18003e7ce  cmp     [rsp+578h+var_4E8], dil
0x18003e7d6  jz      short loc_18003E7E3
0x18003e7d8  lea     rcx, [rsp+578h+var_508]
0x18003e7dd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e7e2  nop
0x18003e7e3  lea     rcx, [rsp+578h+var_558]
  ... truncated ...
```
