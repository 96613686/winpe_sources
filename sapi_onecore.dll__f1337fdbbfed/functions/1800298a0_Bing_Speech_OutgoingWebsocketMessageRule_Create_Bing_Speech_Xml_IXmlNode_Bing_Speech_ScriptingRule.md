# Bing::Speech::OutgoingWebsocketMessageRule::Create(Bing::Speech::Xml::IXmlNode *,Bing::Speech::ScriptingRule * *)

- ea: `0x1800298a0`
- end: `0x18002a5f6`
- name: `?Create@OutgoingWebsocketMessageRule@Speech@Bing@@SAJPEAVIXmlNode@Xml@23@PEAPEAVScriptingRule@23@@Z`
- size: `3414`
- prototype: `__int64 __fastcall(struct Bing::Speech::Xml::IXmlNode *, struct Bing::Speech::ScriptingRule **)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config`

## callers

- `0x18027ae20`

## callees

- `0x180023de8`
- `0x18002637c`
- `0x180026508`
- `0x18002895c`
- `0x180029860`
- `0x1800298a0`
- `0x18002ad5c`
- `0x18002b244`
- `0x18002b750`
- `0x18002d404`
- `0x180030738`
- `0x1800316ac`
- `0x1800316e0`
- `0x180032ab0`
- `0x18004040c`
- `0x1800509b0`
- `0x18005be88`
- `0x180079e30`
- `0x18007aae4`
- `0x18007d31c`
- `0x18010ac24`
- `0x18011c830`
- `0x1801602e4`
- `0x1801603d8`
- `0x180272aa4`
- `0x180277728`
- `0x18027ae64`
- `0x18027aef8`
- `0x18028b010`

## import_xrefs

- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a105`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a21d`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a105`
- `msvcp_win!?setstate@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a21d`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a12f`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a1a3`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a1be`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a1e7`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a12f`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a1a3`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a1be`
- `msvcp_win!?tellg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAA?AV?$fpos@U_Mbstatet@@@2@XZ` at `0x18002a1e7`
- `msvcp_win!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18002a121`
- `msvcp_win!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18002a145`
- `msvcp_win!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18002a121`
- `msvcp_win!?seekg@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@_JH@Z` at `0x18002a145`
- `msvcp_win!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18002a1d6`
- `msvcp_win!?read@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEAD_J@Z` at `0x18002a1d6`
- `msvcp_win!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a0f8`
- `msvcp_win!?clear@?$basic_ios@DU?$char_traits@D@std@@@std@@QEAAXH_N@Z` at `0x18002a0f8`

## string_xrefs

- `0x18002a00a`: `error: failed to read rule attribute`
- `0x180029e13`: `error: failed to read header value`
- `0x180029aeb`: `error: failed to read MessageName value`
- `0x180029fc6`: `error: failed to read rule response filename attributes`
- `0x180029f60`: `error: failed to read ResponseFilename value`
- `0x180029ca8`: `error: failed to read header attributes`
- `0x1800298f3`: `Bing::Speech::OutgoingWebsocketMessageRule::Create`
- `0x1800299ea`: `Bing::Speech::OutgoingWebsocketMessageRule::Create`
- `0x18002a499`: `error: failed to open file %S`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Bing::Speech::OutgoingWebsocketMessageRule::Create(
        struct Bing::Speech::Xml::IXmlNode *a1,
        struct Bing::Speech::ScriptingRule **a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 (__fastcall *v10)(struct Bing::Speech::Xml::IXmlNode *, _BYTE *, std::_Ref_count_base **); // rbx
  int v11; // ebx
  std::_Ref_count_base *v12; // rcx
  __int64 v13; // rdx
  __int64 (__fastcall *v14)(struct Bing::Speech::Xml::IXmlNode *, _BYTE *, std::_Ref_count_base **); // rbx
  __int64 (__fastcall *v15)(struct Bing::Speech::Xml::IXmlNode *, _BYTE *, __int128 *); // rbx
  __int64 v16; // r8
  unsigned __int64 v17; // r12
  std::_Ref_count_base *v18; // rsi
  __int64 v19; // rax
  std::_Ref_count_base *v20; // r15
  std::_Ref_count_base *v21; // rbx
  int v22; // r13d
  int v23; // r15d
  _QWORD *v24; // rax
  __int64 v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rdx
  bool v28; // zf
  __int64 v29; // rcx
  _QWORD *v30; // rax
  char *v31; // r15
  char *v32; // r12
  char *v33; // rcx
  char *v34; // rax
  __int64 v35; // rbx
  _QWORD *v36; // rax
  char *v37; // rbx
  _QWORD *v38; // rax
  _QWORD *v39; // rax
  void *v40; // rax
  __int64 v41; // rax
  const char *v42; // rax
  char *v43; // [rsp+20h] [rbp-E0h]
  int v44; // [rsp+20h] [rbp-E0h]
  int v45; // [rsp+20h] [rbp-E0h]
  __int128 v46; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v47; // [rsp+40h] [rbp-C0h]
  __int128 v48; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h]
  std::_Ref_count_base *v50[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v51[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+80h] [rbp-80h] BYREF
  void *v53; // [rsp+88h] [rbp-78h]
  __int64 v54; // [rsp+90h] [rbp-70h]
  int v55; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v56[32]; // [rsp+A0h] [rbp-60h] BYREF
  std::_Ref_count_base *v57[2]; // [rsp+C0h] [rbp-40h]
  struct Bing::Speech::ScriptingRule **v58; // [rsp+D0h] [rbp-30h]
  void *v59; // [rsp+D8h] [rbp-28h] BYREF
  std::_Ref_count_base *v60; // [rsp+E0h] [rbp-20h]
  _QWORD v61[2]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v62[128]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v63; // [rsp+180h] [rbp+80h]
  _BYTE v64[32]; // [rsp+200h] [rbp+100h] BYREF
  _QWORD v65[2]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v66[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v67[32]; // [rsp+260h] [rbp+160h] BYREF
  _QWORD Src[3]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int64 v69; // [rsp+298h] [rbp+198h]
  _BYTE v70[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v58 = a2;
  if ( !a2 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0x7F,
      (unsigned int)"Invalid argument '%s'\n",
      "ppRule != nullptr");
    return 2147942487LL;
  }
  if ( !a1 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0x80,
      (unsigned int)"Invalid argument '%s'\n",
      "pSerializedRule != nullptr");
    return 2147942487LL;
  }
  std::ifstream::ifstream(v61);
  std::wstring::wstring(v67);
  std::wstring::wstring(v65);
  std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(&v48, v4, v5);
  *(_OWORD *)v57 = 0;
  std::wstring::wstring(v66);
  Bing::Speech::Headers::Headers((Bing::Speech::Headers *)v56);
  *(_OWORD *)v51 = 0;
  *(_OWORD *)v50 = 0;
  std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(&v46, v6, v7);
  v55 = 0;
  std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(&v52, v8, v9);
  std::wstring::wstring(v64);
  v10 = *(__int64 (__fastcall **)(struct Bing::Speech::Xml::IXmlNode *, _BYTE *, std::_Ref_count_base **))(*(_QWORD *)a1 + 48LL);
  std::wstring::wstring(v70, L"MessageName");
  v11 = v10(a1, v70, v51);
  std::wstring::_Tidy_deallocate(v70);
  if ( v11 < 0 || (v12 = v51[0]) == 0 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0x9E,
      (unsigned int)"error: MessageName node is missing from 'SendResponseOnOutgoingMessage' rule",
      v43);
    if ( v11 < 0 )
    {
      v13 = 159;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
        (const char *)(unsigned int)v11,
        (int)v43);
      std::wstring::_Tidy_deallocate(v64);
      std::vector<unsigned char>::_Tidy(&v52);
      if ( (_QWORD)v46 )
      {
        std::_Destroy_range<std::allocator<Halsey::swstring>>(v46, *((_QWORD *)&v46 + 1));
        std::_Deallocate<16>(v46, (v47 - v46) & 0xFFFFFFFFFFFFFFF0uLL);
        v46 = 0;
        v47 = 0;
      }
      if ( v50[1] )
        std::_Ref_count_base::_Decref(v50[1]);
      if ( v51[1] )
        std::_Ref_count_base::_Decref(v51[1]);
      Bing::Speech::Headers::~Headers((Bing::Speech::Headers *)v56);
      std::wstring::_Tidy_deallocate(v66);
LABEL_126:
      if ( (_QWORD)v48 )
      {
        std::_Destroy_range<std::allocator<Halsey::swstring>>(v48, *((_QWORD *)&v48 + 1));
        std::_Deallocate<16>(v48, (v49 - v48) & 0xFFFFFFFFFFFFFFF0uLL);
        v49 = 0;
        v48 = 0;
      }
LABEL_128:
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(v67);
      std::ifstream::`vbase destructor'(v61);
      return (unsigned int)v11;
    }
    v12 = v51[0];
  }
  v11 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v12 + 24LL))(v12, v67);
  if ( v11 < 0 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xA5,
      (unsigned int)"error: failed to read MessageName value",
      v43);
    v13 = 166;
    goto LABEL_10;
  }
  v14 = *(__int64 (__fastcall **)(struct Bing::Speech::Xml::IXmlNode *, _BYTE *, std::_Ref_count_base **))(*(_QWORD *)a1 + 48LL);
  std::wstring::wstring(v70, L"ResponseFile");
  v11 = v14(a1, v70, v50);
  std::wstring::_Tidy_deallocate(v70);
  if ( v11 < 0 || !v50[0] )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xAC,
      (unsigned int)"error: ResponseFile node is missing from 'SendResponseOnOutgoingMessage' rule",
      v43);
    if ( v11 < 0 )
    {
      v13 = 173;
      goto LABEL_10;
    }
  }
  v15 = *(__int64 (__fastcall **)(struct Bing::Speech::Xml::IXmlNode *, _BYTE *, __int128 *))(*(_QWORD *)a1 + 56LL);
  std::wstring::wstring(v70, L"ResponseHeader");
  v11 = v15(a1, v70, &v48);
  std::wstring::_Tidy_deallocate(v70);
  if ( v11 < 0 || (v16 = v48, *((_QWORD *)&v48 + 1) == (_QWORD)v48) )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xB5,
      (unsigned int)"error: no response headers?",
      v43);
    if ( v11 < 0 )
    {
      v13 = 182;
      goto LABEL_10;
    }
    v16 = v48;
  }
  v17 = 0;
  v18 = v57[1];
  while ( v17 < (*((_QWORD *)&v48 + 1) - v16) >> 4 )
  {
    v19 = std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(&v59, v16 + 16 * v17);
    v20 = *(std::_Ref_count_base **)v19;
    *(std::_Ref_count_base **)v19 = v57[0];
    v57[0] = v20;
    v21 = *(std::_Ref_count_base **)(v19 + 8);
    *(_QWORD *)(v19 + 8) = v18;
    v18 = v21;
    v57[1] = v21;
    if ( v60 )
      std::_Ref_count_base::_Decref(v60);
    v22 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _BYTE *))(*(_QWORD *)v20 + 24LL))(v20, v66);
    if ( v22 < 0 )
    {
      DebugUtils::BingSpeechTraceError(
        (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
        "Bing::Speech::OutgoingWebsocketMessageRule::Create",
        (const char *)0xBF,
        (unsigned int)"error: failed to read header value",
        v43);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC0,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
        (const char *)(unsigned int)v22,
        v44);
      std::wstring::_Tidy_deallocate(v64);
      std::vector<unsigned char>::_Tidy(&v52);
      if ( (_QWORD)v46 )
      {
        std::_Destroy_range<std::allocator<Halsey::swstring>>(v46, *((_QWORD *)&v46 + 1));
        std::_Deallocate<16>(v46, (v47 - v46) & 0xFFFFFFFFFFFFFFF0uLL);
        v46 = 0;
        v47 = 0;
      }
      if ( v50[1] )
        std::_Ref_count_base::_Decref(v50[1]);
      if ( v51[1] )
        std::_Ref_count_base::_Decref(v51[1]);
      Bing::Speech::Headers::~Headers((Bing::Speech::Headers *)v56);
      std::wstring::_Tidy_deallocate(v66);
      if ( v21 )
        std::_Ref_count_base::_Decref(v21);
      if ( (_QWORD)v48 )
      {
        std::_Destroy_range<std::allocator<Halsey::swstring>>(v48, *((_QWORD *)&v48 + 1));
        std::_Deallocate<16>(v48, (v49 - v48) & 0xFFFFFFFFFFFFFFF0uLL);
        v48 = 0;
        v49 = 0;
      }
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(v67);
      std::ifstream::`vbase destructor'(v61);
      return (unsigned int)v22;
    }
    std::vector<std::shared_ptr<Halsey::SrResult::Phrase>>::clear(&v46);
    v23 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v20 + 40LL))(v20, &v46);
    if ( v23 < 0 || (v24 = (_QWORD *)v46, *((_QWORD *)&v46 + 1) == (_QWORD)v46) )
    {
      DebugUtils::BingSpeechTraceError(
        (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
        "Bing::Speech::OutgoingWebsocketMessageRule::Create",
        (const char *)0xC7,
        (unsigned int)"error: failed to read header attributes",
        v43);
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC8,
          (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
          (const char *)(unsigned int)v23,
          (int)v43);
        std::wstring::_Tidy_deallocate(v64);
        std::vector<unsigned char>::_Tidy(&v52);
        if ( (_QWORD)v46 )
        {
          std::_Destroy_range<std::allocator<Halsey::swstring>>(v46, *((_QWORD *)&v46 + 1));
          std::_Deallocate<16>(v46, (v47 - v46) & 0xFFFFFFFFFFFFFFF0uLL);
          v46 = 0;
          v47 = 0;
        }
        if ( v50[1] )
          std::_Ref_count_base::_Decref(v50[1]);
        if ( v51[1] )
          std::_Ref_count_base::_Decref(v51[1]);
        Bing::Speech::Headers::~Headers((Bing::Speech::Headers *)v56);
        std::wstring::_Tidy_deallocate(v66);
        if ( v21 )
          std::_Ref_count_base::_Decref(v21);
        if ( (_QWORD)v48 )
        {
          std::_Destroy_range<std::allocator<Halsey::swstring>>(v48, *((_QWORD *)&v48 + 1));
          std::_Deallocate<16>(v48, (v49 - v48) & 0xFFFFFFFFFFFFFFF0uLL);
          v48 = 0;
          v49 = 0;
        }
        std::wstring::_Tidy_deallocate(v65);
        std::wstring::_Tidy_deallocate(v67);
        std::ifstream::`vbase destructor'(v61);
        return (unsigned int)v23;
      }
      v24 = (_QWORD *)v46;
    }
    (*(void (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v24 + 16LL))(*v24, v64);
    Bing::Speech::Headers::Add(v56, v64, v66);
    ++v17;
    v16 = v48;
  }
  v11 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD *))(*(_QWORD *)v50[0] + 24LL))(v50[0], v65);
  if ( v11 < 0 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xD3,
      (unsigned int)"error: failed to read ResponseFilename value",
      v43);
    v25 = 212;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      (const char *)(unsigned int)v11,
      (int)v43);
LABEL_118:
    std::wstring::_Tidy_deallocate(v64);
    std::vector<unsigned char>::_Tidy(&v52);
    if ( (_QWORD)v46 )
    {
      std::_Destroy_range<std::allocator<Halsey::swstring>>(v46, *((_QWORD *)&v46 + 1));
      std::_Deallocate<16>(v46, (v47 - v46) & 0xFFFFFFFFFFFFFFF0uLL);
      v46 = 0;
      v47 = 0;
    }
    if ( v50[1] )
      std::_Ref_count_base::_Decref(v50[1]);
    if ( v51[1] )
      std::_Ref_count_base::_Decref(v51[1]);
    Bing::Speech::Headers::~Headers((Bing::Speech::Headers *)v56);
    std::wstring::_Tidy_deallocate(v66);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    goto LABEL_126;
  }
  std::vector<std::shared_ptr<Halsey::SrResult::Phrase>>::clear(&v46);
  v11 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, __int128 *))(*(_QWORD *)v50[0] + 40LL))(v50[0], &v46);
  if ( v11 < 0 || (v26 = (_QWORD *)v46, *((_QWORD *)&v46 + 1) == (_QWORD)v46) )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xDB,
      (unsigned int)"error: failed to read rule response filename attributes",
      v43);
    if ( v11 < 0 )
    {
      v25 = 220;
      goto LABEL_63;
    }
    v26 = (_QWORD *)v46;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v26 + 16LL))(*v26, v64);
  if ( v11 < 0 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xE2,
      (unsigned int)"error: failed to read rule attribute",
      v43);
    v25 = 227;
    goto LABEL_63;
  }
  v11 = Bing::Speech::OutgoingWebsocketMessageRule::WebsocketMessageFormatFromBSTR(v64, &v55);
  if ( v11 < 0 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xE9,
      (unsigned int)"error: invalid payload type",
      v43);
    v25 = 234;
    goto LABEL_63;
  }
  std::wstring::wstring(Src);
  std::wstring::_Assign<unsigned short>(Src, L"data\\");
  std::wstring::_Append<unsigned short>(Src);
  v27 = Src;
  if ( v69 > 7 )
    v27 = (_QWORD *)Src[0];
  v28 = std::filebuf::open(v62, v27, 33) == 0;
  v29 = *(int *)(v61[0] + 4LL);
  if ( v28 )
    std::ios::setstate((char *)v61 + v29, 2, 0);
  else
    std::ios::clear((char *)v61 + v29, 0, 0);
  if ( !v63 )
  {
    v42 = (const char *)Src;
    if ( v69 > 7 )
      v42 = (const char *)Src[0];
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0xF7,
      (unsigned int)"error: failed to open file %S",
      v42);
    v11 = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF8,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      (const char *)0x80004005LL,
      v45);
    std::wstring::_Tidy_deallocate(Src);
    goto LABEL_118;
  }
  std::istream::seekg(v61, 0, 2);
  v30 = (_QWORD *)std::istream::tellg(v61, &v59);
  v31 = (char *)(*v30 + v30[1]);
  std::istream::seekg(v61, 0, 0);
  v32 = (char *)v53;
  v33 = (char *)v53 - v52;
  if ( v31 >= (char *)v53 - v52 )
  {
    if ( v31 <= (char *)v53 - v52 )
      goto LABEL_86;
    if ( (unsigned __int64)v31 > v54 - v52 )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(&v52, v31);
      goto LABEL_86;
    }
    v35 = v31 - v33;
    memset_0(v53, 0, v31 - v33);
    v34 = &v32[v35];
  }
  else
  {
    v34 = &v31[v52];
  }
  v53 = v34;
  do
  {
LABEL_86:
    v36 = (_QWORD *)std::istream::tellg(v61, &v59);
    v37 = &v31[-v36[1] - *v36];
    v38 = (_QWORD *)std::istream::tellg(v61, v70);
    std::istream::read(v61, *v38 + v52 + v38[1], v37);
    v39 = (_QWORD *)std::istream::tellg(v61, v70);
  }
  while ( v31 != (char *)(*v39 + v39[1]) );
  if ( !std::filebuf::close(v62) )
    std::ios::setstate((char *)v61 + *(int *)(v61[0] + 4LL), 2, 0);
  v40 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v59 = v40;
  if ( v40 )
    v41 = Bing::Speech::OutgoingWebsocketMessageRule::OutgoingWebsocketMessageRule(
            (_DWORD)v40,
            (unsigned int)v67,
            v55,
            (unsigned int)v56,
            (__int64)&v52);
  else
    v41 = 0;
  *v58 = (struct Bing::Speech::ScriptingRule *)v41;
  if ( !v41 )
  {
    DebugUtils::BingSpeechTraceError(
      (DebugUtils *)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\bing\\csp\\unittests\\mocks\\transport\\mockenginerules.cpp",
      "Bing::Speech::OutgoingWebsocketMessageRule::Create",
      (const char *)0x109,
      (unsigned int)"Failed allocate memory for '%s'\n",
      "*ppRule");
    std::wstring::_Tidy_deallocate(Src);
    std::wstring::_Tidy_deallocate(v64);
    std::vector<unsigned char>::_Tidy(&v52);
    if ( (_QWORD)v46 )
    {
      std::_Destroy_range<std::allocator<Halsey::swstring>>(v46, *((_QWORD *)&v46 + 1));
      std::_Deallocate<16>(v46, (v47 - v46) & 0xFFFFFFFFFFFFFFF0uLL);
      v46 = 0;
      v47 = 0;
    }
    if ( v50[1] )
      std::_Ref_count_base::_Decref(v50[1]);
    if ( v51[1] )
      std::_Ref_count_base::_Decref(v51[1]);
    Bing::Speech::Headers::~Headers((Bing::Speech::Headers *)v56);
    std::wstring::_Tidy_deallocate(v66);
    if ( v18 )
      std::_Ref_count_base::_Decref(v18);
    if ( (_QWORD)v48 )
    {
      std::_Destroy_range<std::allocator<Halsey::swstring>>(v48, *((_QWORD *)&v48 + 1));
      std::_Deallocate<16>(v48, (v49 - v48) & 0xFFFFFFFFFFFFFFF0uLL);
      v48 = 0;
      v49 = 0;
    }
    v11 = -2147024882;
    goto LABEL_128;
  }
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v64);
  std::vector<unsigned char>::_Tidy(&v52);
  if ( (_QWORD)v46 )
  {
    std::_Destroy_range<std::allocator<Halsey::swstring>>(v46, *((_QWORD *)&v46 + 1));
    std::_Deallocate<16>(v46, (v47 - v46) & 0xFFFFFFFFFFFFFFF0uLL);
    v46 = 0;
    v47 = 0;
  }
  if ( v50[1] )
    std::_Ref_count_base::_Decref(v50[1]);
  if ( v51[1] )
    std::_Ref_count_base::_Decref(v51[1]);
  Bing::Speech::Headers::~Headers((Bing::Speech::Headers *)v56);
  std::wstring::_Tidy_deallocate(v66);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  if ( (_QWORD)v48 )
  {
    std::_Destroy_range<std::allocator<Halsey::swstring>>(v48, *((_QWORD *)&v48 + 1));
    std::_Deallocate<16>(v48, (v49 - v48) & 0xFFFFFFFFFFFFFFF0uLL);
    v48 = 0;
    v49 = 0;
  }
  std::wstring::_Tidy_deallocate(v65);
  std::wstring::_Tidy_deallocate(v67);
  std::ifstream::`vbase destructor'(v61);
  return 0;
}

```

## disassembly

```asm
0x1800298a0  mov     [rsp-8+arg_10], rbx
0x1800298a5  push    rbp
0x1800298a6  push    rsi
0x1800298a7  push    rdi
0x1800298a8  push    r12
0x1800298aa  push    r13
0x1800298ac  push    r14
0x1800298ae  push    r15
0x1800298b0  lea     rbp, [rsp-1D0h]
0x1800298b8  sub     rsp, 2D0h
0x1800298bf  mov     rax, cs:__security_cookie
0x1800298c6  xor     rax, rsp
0x1800298c9  mov     [rbp+200h+var_40], rax
0x1800298d0  mov     [rbp+200h+var_230], rdx
0x1800298d4  mov     rsi, rcx
0x1800298d7  test    rdx, rdx
0x1800298da  jnz     short loc_180029910
0x1800298dc  lea     rax, aPpruleNullptr; "ppRule != nullptr"
0x1800298e3  lea     r8d, [rdx+7Fh]; char *
0x1800298e7  lea     r9, aInvalidArgumen; "Invalid argument '%s'\n"
0x1800298ee  mov     [rsp+300h+var_2E0], rax; char *
0x1800298f3  lea     rdx, aBingSpeechOutg_0; "Bing::Speech::OutgoingWebsocketMessageR"...
0x1800298fa  lea     rcx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180029901  call    ?BingSpeechTraceError@DebugUtils@@YAXPEBD0I0ZZ; DebugUtils::BingSpeechTraceError(char const *,char const *,uint,char const *,...)
0x180029906  mov     eax, 80070057h
0x18002990b  jmp     loc_18002A5CC
0x180029910  xor     r13d, r13d
0x180029913  test    rsi, rsi
0x180029916  jnz     short loc_180029927
0x180029918  lea     rax, aPserializedrul; "pSerializedRule != nullptr"
0x18002991f  mov     r8d, 80h
0x180029925  jmp     short loc_1800298E7
0x180029927  lea     rcx, [rbp+200h+var_210]
0x18002992b  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@XZ; std::ifstream::ifstream(void)
0x180029930  nop
0x180029931  lea     rcx, [rbp+200h+var_A0]
0x180029938  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002993d  nop
0x18002993e  lea     rcx, [rbp+200h+var_E0]
0x180029945  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002994a  nop
0x18002994b  lea     rcx, [rsp+300h+var_2B8]
0x180029950  call    ??0?$vector@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(void)
0x180029955  nop
0x180029956  xorps   xmm0, xmm0
0x180029959  movdqu  xmmword ptr [rbp+200h+var_240], xmm0
0x18002995e  lea     rcx, [rbp+200h+var_C0]
0x180029965  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002996a  nop
0x18002996b  lea     rcx, [rbp+200h+var_260]; this
0x18002996f  call    ??0Headers@Speech@Bing@@QEAA@XZ; Bing::Speech::Headers::Headers(void)
0x180029974  nop
0x180029975  xorps   xmm0, xmm0
0x180029978  movdqu  xmmword ptr [rsp+300h+var_290], xmm0
0x18002997e  movdqu  xmmword ptr [rsp+300h+var_2A0], xmm0
0x180029984  lea     rcx, [rsp+300h+var_2D0]
0x180029989  call    ??0?$vector@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(void)
0x18002998e  nop
0x18002998f  mov     [rbp+200h+var_268], r13d
0x180029993  lea     rcx, [rbp+200h+var_280]
0x180029997  call    ??0?$vector@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(void)
0x18002999c  nop
0x18002999d  lea     rcx, [rbp+200h+var_100]
0x1800299a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800299a9  nop
0x1800299aa  mov     rax, [rsi]
0x1800299ad  mov     rbx, [rax+30h]
0x1800299b1  lea     rdx, aMessagename; "MessageName"
0x1800299b8  lea     rcx, [rbp+200h+var_60]
0x1800299bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800299c4  nop
0x1800299c5  lea     r8, [rsp+300h+var_290]
0x1800299ca  lea     rdx, [rbp+200h+var_60]
0x1800299d1  mov     rcx, rsi
0x1800299d4  mov     rax, rbx
0x1800299d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299dc  mov     ebx, eax
0x1800299de  lea     rcx, [rbp+200h+var_60]
0x1800299e5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800299ea  lea     r14, aBingSpeechOutg_0; "Bing::Speech::OutgoingWebsocketMessageR"...
0x1800299f1  lea     rdi, aOnecoreuapEndu_11; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x1800299f8  test    ebx, ebx
0x1800299fa  js      short loc_180029A0A
0x1800299fc  mov     rcx, [rsp+300h+var_290]
0x180029a01  test    rcx, rcx
0x180029a04  jnz     loc_180029AD2
0x180029a0a  lea     r9, aErrorMessagena; "error: MessageName node is missing from"...
0x180029a11  mov     r8d, 9Eh; char *
0x180029a17  mov     rdx, r14; char *
0x180029a1a  mov     rcx, rdi; this
0x180029a1d  call    ?BingSpeechTraceError@DebugUtils@@YAXPEBD0I0ZZ; DebugUtils::BingSpeechTraceError(char const *,char const *,uint,char const *,...)
0x180029a22  test    ebx, ebx
0x180029a24  jns     loc_180029ACD
0x180029a2a  mov     edx, 9Fh; void *
0x180029a2f  mov     r9d, ebx; char *
0x180029a32  mov     r8, rdi; unsigned int
0x180029a35  mov     rcx, [rbp+208h]; this
0x180029a3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a41  nop
0x180029a42  lea     rcx, [rbp+200h+var_100]
0x180029a49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029a4e  nop
0x180029a4f  lea     rcx, [rbp+200h+var_280]
0x180029a53  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180029a58  nop
0x180029a59  mov     rcx, qword ptr [rsp+300h+var_2D0]
0x180029a5e  test    rcx, rcx
0x180029a61  jz      short loc_180029A91
0x180029a63  mov     rdx, qword ptr [rsp+300h+var_2D0+8]
0x180029a68  call    ??$_Destroy_range@V?$allocator@Vswstring@Halsey@@@std@@@std@@YAXPEAVswstring@Halsey@@QEAV12@AEAV?$allocator@Vswstring@Halsey@@@0@@Z; std::_Destroy_range<std::allocator<Halsey::swstring>>(Halsey::swstring *,Halsey::swstring * const,std::allocator<Halsey::swstring> &)
0x180029a6d  mov     rcx, qword ptr [rsp+300h+var_2D0]
0x180029a72  mov     rdx, [rsp+300h+var_2C0]
0x180029a77  sub     rdx, rcx
0x180029a7a  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180029a7e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180029a83  xorps   xmm0, xmm0
0x180029a86  movdqu  [rsp+300h+var_2D0], xmm0
0x180029a8c  mov     [rsp+300h+var_2C0], r13
0x180029a91  mov     rcx, [rsp+300h+var_2A0+8]; this
0x180029a96  test    rcx, rcx
0x180029a99  jz      short loc_180029AA1
0x180029a9b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029aa0  nop
0x180029aa1  mov     rcx, [rsp+300h+var_290+8]; this
0x180029aa6  test    rcx, rcx
0x180029aa9  jz      short loc_180029AB1
0x180029aab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029ab0  nop
0x180029ab1  lea     rcx, [rbp+200h+var_260]; this
0x180029ab5  call    ??1Headers@Speech@Bing@@QEAA@XZ; Bing::Speech::Headers::~Headers(void)
0x180029aba  nop
0x180029abb  lea     rcx, [rbp+200h+var_C0]
0x180029ac2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029ac7  nop
0x180029ac8  jmp     loc_18002A56F
0x180029acd  mov     rcx, [rsp+300h+var_290]
0x180029ad2  mov     rax, [rcx]
0x180029ad5  lea     rdx, [rbp+200h+var_A0]
0x180029adc  mov     rax, [rax+18h]
0x180029ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ae5  mov     ebx, eax
0x180029ae7  test    eax, eax
0x180029ae9  jns     short loc_180029B0D
0x180029aeb  lea     r9, aErrorFailedToR_0; "error: failed to read MessageName value"
0x180029af2  mov     r8d, 0A5h; char *
0x180029af8  mov     rdx, r14; char *
0x180029afb  mov     rcx, rdi; this
0x180029afe  call    ?BingSpeechTraceError@DebugUtils@@YAXPEBD0I0ZZ; DebugUtils::BingSpeechTraceError(char const *,char const *,uint,char const *,...)
0x180029b03  mov     edx, 0A6h
0x180029b08  jmp     loc_180029A2F
0x180029b0d  mov     rax, [rsi]
0x180029b10  mov     rbx, [rax+30h]
0x180029b14  lea     rdx, aResponsefile; "ResponseFile"
0x180029b1b  lea     rcx, [rbp+200h+var_60]
0x180029b22  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029b27  nop
0x180029b28  lea     r8, [rsp+300h+var_2A0]
0x180029b2d  lea     rdx, [rbp+200h+var_60]
0x180029b34  mov     rcx, rsi
0x180029b37  mov     rax, rbx
0x180029b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b3f  mov     ebx, eax
0x180029b41  lea     rcx, [rbp+200h+var_60]
0x180029b48  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029b4d  test    ebx, ebx
0x180029b4f  js      short loc_180029B58
0x180029b51  cmp     [rsp+300h+var_2A0], r13
0x180029b56  jnz     short loc_180029B7E
0x180029b58  lea     r9, aErrorResponsef; "error: ResponseFile node is missing fro"...
0x180029b5f  mov     r8d, 0ACh; char *
0x180029b65  mov     rdx, r14; char *
0x180029b68  mov     rcx, rdi; this
0x180029b6b  call    ?BingSpeechTraceError@DebugUtils@@YAXPEBD0I0ZZ; DebugUtils::BingSpeechTraceError(char const *,char const *,uint,char const *,...)
0x180029b70  test    ebx, ebx
0x180029b72  jns     short loc_180029B7E
0x180029b74  mov     edx, 0ADh
0x180029b79  jmp     loc_180029A2F
0x180029b7e  mov     rax, [rsi]
0x180029b81  mov     rbx, [rax+38h]
0x180029b85  lea     rdx, aResponseheader; "ResponseHeader"
0x180029b8c  lea     rcx, [rbp+200h+var_60]
0x180029b93  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180029b98  nop
0x180029b99  lea     r8, [rsp+300h+var_2B8]
0x180029b9e  lea     rdx, [rbp+200h+var_60]
0x180029ba5  mov     rcx, rsi
0x180029ba8  mov     rax, rbx
0x180029bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bb0  mov     ebx, eax
0x180029bb2  lea     rcx, [rbp+200h+var_60]
0x180029bb9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029bbe  test    ebx, ebx
0x180029bc0  js      short loc_180029BCE
0x180029bc2  mov     r8, qword ptr [rsp+300h+var_2B8]
0x180029bc7  cmp     qword ptr [rsp+300h+var_2B8+8], r8
0x180029bcc  jnz     short loc_180029BF9
0x180029bce  lea     r9, aErrorNoRespons; "error: no response headers?"
0x180029bd5  mov     r8d, 0B5h; char *
0x180029bdb  mov     rdx, r14; char *
0x180029bde  mov     rcx, rdi; this
0x180029be1  call    ?BingSpeechTraceError@DebugUtils@@YAXPEBD0I0ZZ; DebugUtils::BingSpeechTraceError(char const *,char const *,uint,char const *,...)
0x180029be6  test    ebx, ebx
0x180029be8  jns     short loc_180029BF4
0x180029bea  mov     edx, 0B6h
0x180029bef  jmp     loc_180029A2F
0x180029bf4  mov     r8, qword ptr [rsp+300h+var_2B8]
0x180029bf9  mov     r12, r13
0x180029bfc  mov     rsi, [rbp+200h+var_240+8]
0x180029c00  mov     rax, qword ptr [rsp+300h+var_2B8+8]
0x180029c05  sub     rax, r8
0x180029c08  sar     rax, 4
0x180029c0c  cmp     r12, rax
0x180029c0f  jnb     loc_180029F42
0x180029c15  mov     rdx, r12
0x180029c18  shl     rdx, 4
0x180029c1c  add     rdx, r8
0x180029c1f  lea     rcx, [rbp+200h+var_228]
0x180029c23  call    ??0?$shared_ptr@UIJsonValue@Speech@Bing@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Bing::Speech::IJsonValue>::shared_ptr<Bing::Speech::IJsonValue>(std::shared_ptr<Bing::Speech::IJsonValue> const &)
0x180029c28  mov     r15, [rax]
0x180029c2b  mov     rcx, [rbp+200h+var_240]
0x180029c2f  mov     [rax], rcx
0x180029c32  mov     [rbp+200h+var_240], r15
0x180029c36  mov     rbx, [rax+8]
0x180029c3a  mov     [rax+8], rsi
0x180029c3e  mov     rsi, rbx
0x180029c41  mov     [rbp+200h+var_240+8], rbx
0x180029c45  mov     rcx, [rbp+200h+var_220]; this
0x180029c49  test    rcx, rcx
0x180029c4c  jz      short loc_180029C53
0x180029c4e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029c53  mov     rax, [r15]
0x180029c56  lea     rdx, [rbp+200h+var_C0]
0x180029c5d  mov     rcx, r15
0x180029c60  mov     rax, [rax+18h]
0x180029c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c69  mov     r13d, eax
0x180029c6c  test    eax, eax
0x180029c6e  js      loc_180029E13
0x180029c74  lea     rcx, [rsp+300h+var_2D0]
0x180029c79  call    ?clear@?$vector@V?$shared_ptr@UPhrase@SrResult@Halsey@@@std@@V?$allocator@V?$shared_ptr@UPhrase@SrResult@Halsey@@@std@@@2@@std@@QEAAXXZ; std::vector<std::shared_ptr<Halsey::SrResult::Phrase>>::clear(void)
0x180029c7e  mov     rax, [r15]
0x180029c81  lea     rdx, [rsp+300h+var_2D0]
0x180029c86  mov     rcx, r15
0x180029c89  mov     rax, [rax+28h]
0x180029c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c92  mov     r15d, eax
0x180029c95  xor     r13d, r13d
0x180029c98  test    eax, eax
0x180029c9a  js      short loc_180029CA8
0x180029c9c  mov     rax, qword ptr [rsp+300h+var_2D0]
0x180029ca1  cmp     qword ptr [rsp+300h+var_2D0+8], rax
0x180029ca6  jnz     short loc_180029CCA
0x180029ca8  lea     r9, aErrorFailedToR_4; "error: failed to read header attributes"
0x180029caf  mov     r8d, 0C7h; char *
0x180029cb5  mov     rdx, r14; char *
0x180029cb8  mov     rcx, rdi; this
0x180029cbb  call    ?BingSpeechTraceError@DebugUtils@@YAXPEBD0I0ZZ; DebugUtils::BingSpeechTraceError(char const *,char const *,uint,char const *,...)
0x180029cc0  test    r15d, r15d
0x180029cc3  js      short loc_180029D04
0x180029cc5  mov     rax, qword ptr [rsp+300h+var_2D0]
0x180029cca  mov     rcx, [rax]
0x180029ccd  mov     rax, [rcx]
0x180029cd0  lea     rdx, [rbp+200h+var_100]
0x180029cd7  mov     rax, [rax+10h]
0x180029cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ce0  lea     r8, [rbp+200h+var_C0]
0x180029ce7  lea     rdx, [rbp+200h+var_100]
0x180029cee  lea     rcx, [rbp+200h+var_260]
0x180029cf2  call    ?Add@Headers@Speech@Bing@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Bing::Speech::Headers::Add(std::wstring const &,std::wstring const &)
0x180029cf7  inc     r12
0x180029cfa  mov     r8, qword ptr [rsp+300h+var_2B8]
0x180029cff  jmp     loc_180029C00
0x180029d04  mov     rcx, [rbp+208h]; this
0x180029d0b  mov     r9d, r15d; char *
0x180029d0e  mov     r8, rdi; unsigned int
0x180029d11  mov     edx, 0C8h; void *
0x180029d16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d1b  nop
0x180029d1c  lea     rcx, [rbp+200h+var_100]
0x180029d23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029d28  nop
0x180029d29  lea     rcx, [rbp+200h+var_280]
0x180029d2d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180029d32  nop
0x180029d33  mov     rcx, qword ptr [rsp+300h+var_2D0]
0x180029d38  test    rcx, rcx
0x180029d3b  jz      short loc_180029D6B
0x180029d3d  mov     rdx, qword ptr [rsp+300h+var_2D0+8]
0x180029d42  call    ??$_Destroy_range@V?$allocator@Vswstring@Halsey@@@std@@@std@@YAXPEAVswstring@Halsey@@QEAV12@AEAV?$allocator@Vswstring@Halsey@@@0@@Z; std::_Destroy_range<std::allocator<Halsey::swstring>>(Halsey::swstring *,Halsey::swstring * const,std::allocator<Halsey::swstring> &)
0x180029d47  mov     rcx, qword ptr [rsp+300h+var_2D0]
0x180029d4c  mov     rdx, [rsp+300h+var_2C0]
0x180029d51  sub     rdx, rcx
0x180029d54  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180029d58  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180029d5d  xorps   xmm0, xmm0
0x180029d60  movdqu  [rsp+300h+var_2D0], xmm0
0x180029d66  mov     [rsp+300h+var_2C0], r13
0x180029d6b  mov     rcx, [rsp+300h+var_2A0+8]; this
0x180029d70  test    rcx, rcx
0x180029d73  jz      short loc_180029D7B
  ... truncated ...
```
