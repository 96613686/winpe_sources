# Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::Create(ushort const *,std::shared_ptr<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180028994`
- end: `0x1800297f5`
- name: `?Create@ClientContextCreator@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJPEBGAEAV?$shared_ptr@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `3681`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027418`

## callees

- `0x180021944`
- `0x180026508`
- `0x18002895c`
- `0x180028994`
- `0x180029860`
- `0x18002ae70`
- `0x18002b750`
- `0x18002d314`
- `0x18002d404`
- `0x180030738`
- `0x1800316e0`
- `0x180031e20`
- `0x180034084`
- `0x180039c98`
- `0x18003c550`
- `0x18005caa0`
- `0x180065410`
- `0x180065fc4`
- `0x18006e710`
- `0x18007146c`
- `0x180079e30`
- `0x18007a374`
- `0x18007aae4`
- `0x1801835dc`
- `0x1801a658c`
- `0x1801d50a4`
- `0x1801d58dc`
- `0x1801d6450`
- `0x1801d70a8`
- `0x1801d7330`
- `0x1801d7c64`
- `0x180268698`
- `0x1802687e8`
- `0x18028b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180029624`
- `api-ms-win-crt-private-l1-1-0!_o__ultow_s` at `0x180029624`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180028cf6`
- `api-ms-win-crt-private-l1-1-0!_o_iswspace` at `0x180028cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029335`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002947d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029335`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029414`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002947d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800294f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180029560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002943d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180029361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002943d`

## string_xrefs

- `0x180029090`: `CompleteTimeout`
- `0x1800290ed`: `IncompleteTimeout`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::Create(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4)
{
  HSTRING v8; // rsi
  __int64 v9; // rdx
  __int64 v10; // r8
  int v11; // eax
  int v12; // ebx
  _DWORD *v13; // rdi
  __int64 (__fastcall *v14)(_DWORD *, __int64 *); // rbx
  int v15; // eax
  std::_Ref_count_base *v16; // rcx
  int v18; // eax
  __int64 v19; // rax
  const wchar_t *v20; // r12
  const wchar_t *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rsi
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // r8
  const unsigned __int16 *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // r8
  const unsigned __int16 *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  const unsigned __int16 *v33; // r15
  const wchar_t *v34; // rbx
  __int64 v35; // rax
  __int64 v36; // r8
  CEntityStore *v37; // rax
  int v38; // eax
  __int64 v39; // rax
  _QWORD *v40; // rbx
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // rcx
  Halsey::swstring *v44; // rcx
  const unsigned __int16 *v45; // rbx
  __int64 v46; // rax
  __int64 v47; // r8
  Halsey::swstring *v48; // rcx
  const unsigned __int16 *v49; // rbx
  __int64 v50; // rax
  __int64 v51; // r8
  Halsey::swstring *v52; // rcx
  const unsigned __int16 *v53; // rbx
  __int64 v54; // rax
  __int64 v55; // r8
  int v56; // eax
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rbx
  __int64 v60; // rax
  __int64 v61; // rbx
  __int64 v62; // rax
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rdi
  const unsigned __int16 *v66; // rbx
  __int64 v67; // rax
  __int64 v68; // r8
  __int64 (__fastcall *v69)(__int64, __int64 *); // rbx
  __int64 v70; // rdx
  int v71; // eax
  __int64 v72; // rdx
  __int64 v73; // rdi
  __int64 (__fastcall *v74)(__int64, __int64 *); // rbx
  int v75; // eax
  __int64 v76; // rdi
  __int64 (__fastcall *v77)(__int64, HSTRING *); // rbx
  int v78; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v80; // rdi
  __int64 (__fastcall *v81)(__int64, HSTRING *); // rbx
  __int64 v82; // rdx
  __int64 v83; // rdi
  __int64 (__fastcall *v84)(__int64, HSTRING *); // rbx
  int v85; // eax
  PCWSTR v86; // rbx
  __int64 v87; // rcx
  __int64 v88; // r8
  HSTRING v89; // rdi
  _QWORD *v90; // rax
  __int64 v91; // rbx
  __int64 v92; // rax
  __int64 v93; // r8
  __int64 v94; // rbx
  __int64 v95; // rax
  bool v96[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v97; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v98; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  int v100; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v101; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v102; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v103; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v104; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING v105; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v106; // [rsp+70h] [rbp-90h]
  _DWORD *v107; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v108; // [rsp+80h] [rbp-80h]
  _BYTE v109[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v110[32]; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING v111[4]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v112[5]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v113[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v114[48]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v115[32]; // [rsp+160h] [rbp+60h] BYREF
  _WORD v116[32]; // [rsp+180h] [rbp+80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v100 = 0;
  v8 = (HSTRING)operator new(0x48u);
  v111[0] = v8;
  *(_OWORD *)v8 = 0;
  *((_DWORD *)v8 + 2) = 1;
  *((_DWORD *)v8 + 3) = 1;
  *(_QWORD *)v8 = &std::_Ref_count_obj2<Bing::Speech::ClientContext>::`vftable';
  v104 = v8 + 4;
  *((_QWORD *)v8 + 2) = 0;
  *((_QWORD *)v8 + 3) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,Bing::Speech::ClientContextGroup,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Bing::Speech::ClientContextGroup>>,0>>::_Alloc_sentinel_and_proxy(v8 + 4);
  std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(v8 + 8, v9, v10);
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v8 + 14);
  v105 = v8 + 4;
  v106 = (std::_Ref_count_base *)v8;
  std::make_shared<Halsey::SystemProperties,>(&v107);
  v11 = Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::Create(a1, a3, &v107);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
      (const char *)(unsigned int)v11,
      *(int *)v96);
LABEL_5:
    if ( v108 )
      std::_Ref_count_base::_Decref(v108);
    v16 = (std::_Ref_count_base *)v8;
LABEL_8:
    std::_Ref_count_base::_Decref(v16);
    return (unsigned int)v12;
  }
  std::wstring::wstring(v110, L"LocalProperties");
  v97 = 0;
  v13 = v107;
  v14 = *(__int64 (__fastcall **)(_DWORD *, __int64 *))(*(_QWORD *)v107 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
  v15 = v14(v13, &v97);
  v12 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
      (const char *)(unsigned int)v15,
      *(int *)v96);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
    std::wstring::_Tidy_deallocate(v110);
    goto LABEL_5;
  }
  v18 = Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::SetClientContextGroup(
          &v105,
          (__int64)v110,
          v97);
  v12 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3E,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
      (const char *)(unsigned int)v18,
      *(int *)v96);
    goto LABEL_12;
  }
  std::wstring::wstring(v109, L"RecoProperties");
  Bing::Speech::ClientContextGroup::ClientContextGroup(v113);
  std::wstring::_Tidy_deallocate(v109);
  std::wstring::wstring(v109, L"OptIn");
  v19 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
  v20 = L"true";
  std::wstring::_Assign<unsigned short>(v19, L"true", 4);
  std::wstring::_Tidy_deallocate(v109);
  v21 = L"true";
  if ( v13[58] != 2048 )
    v21 = L"false";
  std::wstring::wstring(v109, L"KeywordStreamed");
  v22 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
  v23 = -1;
  v24 = -1;
  do
    ++v24;
  while ( v21[v24] );
  std::wstring::_Assign<unsigned short>(v22, v21, v24);
  std::wstring::_Tidy_deallocate(v109);
  std::wstring::wstring(v109, L"Scenario");
  v25 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
  v26 = -1;
  do
    ++v26;
  while ( *(_WORD *)(a2 + 2 * v26) );
  std::wstring::_Assign<unsigned short>(v25, a2, v26);
  std::wstring::_Tidy_deallocate(v109);
  v27 = Halsey::swstring::c_strsafe((Halsey::swstring *)(v13 + 76));
  std::wstring::wstring(v109, L"UserAgeClass");
  v28 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
  v29 = -1;
  do
    ++v29;
  while ( v27[v29] );
  std::wstring::_Assign<unsigned short>(v28, v27, v29);
  std::wstring::_Tidy_deallocate(v109);
  v30 = Halsey::swstring::c_str((Halsey::swstring *)(v13 + 72));
  v31 = *((_QWORD *)v13 + 36);
  if ( v31 )
    v32 = *(_QWORD *)(v31 + 16);
  else
    v32 = 0;
  v33 = &v30[v32];
  while ( v30 != v33 )
  {
    if ( !(unsigned int)_o_iswspace(*v30) )
    {
      v34 = Halsey::swstring::c_strsafe((Halsey::swstring *)(v13 + 72));
      goto LABEL_33;
    }
    ++v30;
  }
  v34 = L"default";
LABEL_33:
  std::wstring::wstring(v109, L"ModelRevision");
  v35 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
  v36 = -1;
  do
    ++v36;
  while ( v34[v36] );
  std::wstring::_Assign<unsigned short>(v35, v34, v36);
  std::wstring::_Tidy_deallocate(v109);
  v96[0] = 0;
  v37 = CEntityStore::Instance();
  v38 = CEntityStore::AreDGIAlternatesEnabled(v37, v96);
  v12 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
      (const char *)(unsigned int)v38,
      *(int *)v96);
LABEL_37:
    Bing::Speech::ClientContextGroup::~ClientContextGroup((Bing::Speech::ClientContextGroup *)v113);
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
    std::wstring::_Tidy_deallocate(v110);
    if ( v108 )
      std::_Ref_count_base::_Decref(v108);
    v16 = v106;
    if ( !v106 )
      return (unsigned int)v12;
    goto LABEL_8;
  }
  if ( v96[0] )
  {
    std::wstring::wstring(v109, L"GenerateAlternates");
    v39 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
    std::wstring::_Assign<unsigned short>(v39, L"true", 4);
    std::wstring::_Tidy_deallocate(v109);
  }
  Microsoft::Bing::LanguageUnderstanding::Client::UserScenarioStringFromEnum(v112, *(unsigned int *)(*a3 + 552));
  v40 = v112;
  if ( v112[3] > 7u )
    v40 = (_QWORD *)v112[0];
  std::wstring::wstring(v109, L"ClientType");
  v41 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
  v42 = -1;
  do
    ++v42;
  while ( *((_WORD *)v40 + v42) );
  std::wstring::_Assign<unsigned short>(v41, v40, v42);
  std::wstring::_Tidy_deallocate(v109);
  v43 = *(_QWORD *)(*a3 + 328);
  if ( v43 )
  {
    v44 = (Halsey::swstring *)(v43 + 200);
    if ( *(_QWORD *)v44 && *(_QWORD *)(*(_QWORD *)v44 + 16LL) )
    {
      v45 = Halsey::swstring::c_str(v44);
      std::wstring::wstring(v109, L"Topic");
      v46 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
      v47 = -1;
      do
        ++v47;
      while ( v45[v47] );
      std::wstring::_Assign<unsigned short>(v46, v45, v47);
      std::wstring::_Tidy_deallocate(v109);
    }
    v48 = (Halsey::swstring *)(*(_QWORD *)(*a3 + 328) + 224LL);
    if ( *(_QWORD *)v48 && *(_QWORD *)(*(_QWORD *)v48 + 16LL) )
    {
      v49 = Halsey::swstring::c_str(v48);
      std::wstring::wstring(v109, L"PrecedingContext");
      v50 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
      v51 = -1;
      do
        ++v51;
      while ( v49[v51] );
      std::wstring::_Assign<unsigned short>(v50, v49, v51);
      std::wstring::_Tidy_deallocate(v109);
    }
    v52 = (Halsey::swstring *)(*(_QWORD *)(*a3 + 328) + 240LL);
    if ( *(_QWORD *)v52 && *(_QWORD *)(*(_QWORD *)v52 + 16LL) )
    {
      v53 = Halsey::swstring::c_str(v52);
      std::wstring::wstring(v109, L"FollowingContext");
      v54 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
      v55 = -1;
      do
        ++v55;
      while ( v53[v55] );
      std::wstring::_Assign<unsigned short>(v54, v53, v55);
      std::wstring::_Tidy_deallocate(v109);
    }
    v56 = *(_DWORD *)(*(_QWORD *)(*a3 + 328) + 216LL);
    if ( v56 )
    {
      if ( v56 != 2 )
      {
LABEL_65:
        if ( *(int *)(*(_QWORD *)(*a3 + 328) + 288LL) > 0 )
        {
          v59 = std::to_wstring(v115);
          std::wstring::wstring(v109, L"InitialSilenceTimeout");
          v60 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
          std::wstring::operator=(v60, v59);
          std::wstring::_Tidy_deallocate(v109);
          std::wstring::_Tidy_deallocate(v115);
        }
        if ( *(int *)(*(_QWORD *)(*a3 + 328) + 292LL) > 0 )
        {
          v61 = std::to_wstring(v115);
          std::wstring::wstring(v109, L"CompleteTimeout");
          v62 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
          std::wstring::operator=(v62, v61);
          std::wstring::_Tidy_deallocate(v109);
          std::wstring::_Tidy_deallocate(v115);
        }
        if ( *(int *)(*(_QWORD *)(*a3 + 328) + 296LL) > 0 )
        {
          v63 = std::to_wstring(v115);
          std::wstring::wstring(v109, L"IncompleteTimeout");
          v64 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
          std::wstring::operator=(v64, v63);
          std::wstring::_Tidy_deallocate(v109);
          std::wstring::_Tidy_deallocate(v115);
        }
        goto LABEL_71;
      }
      std::wstring::wstring(v109, L"Mode");
      v58 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
      std::wstring::_Assign<unsigned short>(v58, L"OneShot", 7);
    }
    else
    {
      std::wstring::wstring(v109, L"Mode");
      v57 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
      std::wstring::_Assign<unsigned short>(v57, L"Continuous", 10);
    }
    std::wstring::_Tidy_deallocate(v109);
    goto LABEL_65;
  }
LABEL_71:
  v65 = *a3;
  if ( *(_DWORD *)(*a3 + 360) == 3 )
  {
    v66 = Halsey::swstring::c_strsafe((Halsey::swstring *)(v65 + 368));
    std::wstring::wstring(v109, L"PronunciationText");
    v67 = std::map<std::wstring,std::wstring>::operator[](v114, v109);
    v68 = -1;
    do
      ++v68;
    while ( v66[v68] );
    std::wstring::_Assign<unsigned short>(v67, v66, v68);
    std::wstring::_Tidy_deallocate(v109);
LABEL_118:
    v89 = v105;
    std::wstring::wstring(v109, L"RecoProperties");
    v90 = (_QWORD *)std::map<std::wstring,Bing::Speech::ClientContextGroup>::_Try_emplace<std::wstring,>(
                      v89,
                      v115,
                      v109);
    Bing::Speech::ClientContextGroup::operator=(*v90 + 64LL, v113);
    std::wstring::_Tidy_deallocate(v109);
    memset_0(v116, 0, sizeof(v116));
    _o__ultow_s(*(unsigned int *)(*a3 + 232), v116, 32);
    std::wstring::wstring(v111, L"ConversationContext");
    v91 = *(_QWORD *)std::map<std::wstring,Bing::Speech::ClientContextGroup>::_Try_emplace<std::wstring,>(
                       v89,
                       v115,
                       v111);
    std::wstring::wstring(v109, L"TurnId");
    v92 = std::map<std::wstring,std::wstring>::operator[](v91 + 96, v109);
    v93 = -1;
    do
      ++v93;
    while ( v116[v93] );
    std::wstring::_Assign<unsigned short>(v92, v116, v93);
    std::wstring::_Tidy_deallocate(v109);
    std::wstring::_Tidy_deallocate(v111);
    if ( !*(_BYTE *)(*a3 + 407) )
      v20 = L"false";
    std::wstring::wstring(v111, L"ConversationContext");
    v94 = *(_QWORD *)std::map<std::wstring,Bing::Speech::ClientContextGroup>::_Try_emplace<std::wstring,>(
                       v89,
                       v115,
                       v111);
    std::wstring::wstring(v109, L"PreferClientReco");
    v95 = std::map<std::wstring,std::wstring>::operator[](v94 + 96, v109);
    do
      ++v23;
    while ( v20[v23] );
    std::wstring::_Assign<unsigned short>(v95, v20, v23);
    std::wstring::_Tidy_deallocate(v109);
    std::wstring::_Tidy_deallocate(v111);
    std::wstring::wstring(v109);
    v100 = 3;
    *(_OWORD *)v111 = 0;
    if ( (int)Bing::Speech::ClientContextHelper::ConvertToJson(v89, v111) >= 0 )
      (**(void (__fastcall ***)(HSTRING, _BYTE *))v111[0])(v111[0], v109);
    if ( v111[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)v111[1]);
    std::wstring::operator=(a4, v109);
    std::wstring::_Tidy_deallocate(v109);
    goto LABEL_129;
  }
  v98 = 0;
  v69 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
  v12 = v69(v65, &v98);
  if ( v12 < 0 )
  {
    v70 = 133;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v70,
      (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
      (const char *)(unsigned int)v12,
      *(int *)v96);
    goto LABEL_78;
  }
  v100 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v98 + 48LL))(v98, &v100);
  if ( v12 < 0 )
  {
    v70 = 136;
    goto LABEL_77;
  }
  if ( v100 == 5 )
  {
    v102 = 0;
    v71 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonValue>::As<Windows::Data::Json::IJsonObject>(&v98, &v102);
    v12 = v71;
    if ( v71 >= 0 )
    {
      v101 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
      v12 = Speech::JsonHelpers::Iterator(v102, &v101);
      if ( v12 >= 0 )
      {
        v96[0] = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)v101 + 56LL))(v101, v96);
        if ( v12 >= 0 )
        {
          while ( v96[0] )
          {
            v103 = 0;
            v73 = v101;
            v74 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v101 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
            v75 = v74(v73, &v103);
            v12 = v75;
            if ( v75 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x96,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
                (const char *)(unsigned int)v75,
                *(int *)v96);
              goto LABEL_116;
            }
            string = 0;
            v76 = v103;
            v77 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v103 + 48LL);
            WindowsDeleteString(0);
            string = 0;
            v78 = v77(v76, &string);
            v12 = v78;
            if ( v78 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x99,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
                (const char *)(unsigned int)v78,
                *(int *)v96);
              goto LABEL_114;
            }
            StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
            std::wstring::wstring(v109, StringRawBuffer);
            v104 = 0;
            v80 = v103;
            v81 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v103 + 56LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
            v12 = v81(v80, &v104);
            if ( v12 < 0 )
            {
              v82 = 157;
              goto LABEL_111;
            }
            v12 = (*(__int64 (__fastcall **)(HSTRING, int *))(*(_QWORD *)v104 + 48LL))(v104, &v100);
            if ( v12 < 0 )
            {
              v82 = 159;
LABEL_111:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v82,
                (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
                (const char *)(unsigned int)v12,
                *(int *)v96);
LABEL_112:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
              std::wstring::_Tidy_deallocate(v109);
LABEL_114:
              WindowsDeleteString(string);
              string = 0;
LABEL_116:
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
              goto LABEL_89;
            }
            if ( v100 == 5 )
            {
              v12 = Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::SetClientContextGroup(
                      &v105,
                      (__int64)v109,
                      (__int64)v104);
              if ( v12 < 0 )
              {
                v82 = 163;
                goto LABEL_111;
              }
            }
            else if ( v100 == 3 )
            {
              v111[0] = 0;
              v83 = (__int64)v104;
              v84 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v104 + 64LL);
              WindowsDeleteString(0);
              v111[0] = 0;
              v85 = v84(v83, v111);
              v12 = v85;
              if ( v85 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xA8,
                  (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
                  (const char *)(unsigned int)v85,
                  *(int *)v96);
                WindowsDeleteString(v111[0]);
                v111[0] = 0;
                goto LABEL_112;
              }
              v86 = WindowsGetStringRawBuffer(v111[0], 0);
              v87 = *(_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring const &,>(
                                 v105 + 10,
                                 v115,
                                 v109)
                  + 64LL;
              v88 = -1;
              do
                ++v88;
              while ( v86[v88] );
              std::wstring::_Assign<unsigned short>(v87, v86, v88);
              WindowsDeleteString(v111[0]);
            }
            v12 = (*(__int64 (__fastcall **)(__int64, bool *))(*(_QWORD *)v101 + 64LL))(v101, v96);
            if ( v12 < 0 )
            {
              v82 = 172;
              goto LABEL_111;
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v104);
            std::wstring::_Tidy_deallocate(v109);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v103);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
          goto LABEL_118;
        }
        v72 = 145;
      }
      else
      {
        v72 = 143;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v72,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
        (const char *)(unsigned int)v12,
        *(int *)v96);
LABEL_89:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\rnl\\src\\clientcontextcreator.cpp",
        (const char *)(unsigned int)v71,
        *(int *)v96);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
LABEL_78:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
    std::wstring::_Tidy_deallocate(v112);
    goto LABEL_37;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v98);
LABEL_129:
  std::wstring::_Tidy_deallocate(v112);
  Bing::Speech::ClientContextGroup::~ClientContextGroup((Bing::Speech::ClientContextGroup *)v113);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v97);
  std::wstring::_Tidy_deallocate(v110);
  if ( v108 )
    std::_Ref_count_base::_Decref(v108);
  if ( v106 )
    std::_Ref_count_base::_Decref(v106);
  return 0;
}

```

## disassembly

```asm
0x180028994  push    rbp
0x180028996  push    rbx
0x180028997  push    rsi
0x180028998  push    rdi
0x180028999  push    r12
0x18002899b  push    r13
0x18002899d  push    r14
0x18002899f  push    r15
0x1800289a1  lea     rbp, [rsp-0D8h]
0x1800289a9  sub     rsp, 1D8h
0x1800289b0  mov     rax, cs:__security_cookie
0x1800289b7  xor     rax, rsp
0x1800289ba  mov     [rbp+110h+var_50], rax
0x1800289c1  mov     r13, r9
0x1800289c4  mov     r14, r8
0x1800289c7  mov     r15, rdx
0x1800289ca  mov     rdi, rcx
0x1800289cd  xor     r12d, r12d
0x1800289d0  mov     [rsp+210h+var_1D0], r12d
0x1800289d5  lea     ecx, [r12+48h]; Size
0x1800289da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800289df  mov     rsi, rax
0x1800289e2  mov     [rbp+110h+var_148], rax
0x1800289e6  xorps   xmm0, xmm0
0x1800289e9  movups  xmmword ptr [rax], xmm0
0x1800289ec  lea     eax, [r12+1]
0x1800289f1  mov     [rsi+8], eax
0x1800289f4  mov     [rsi+0Ch], eax
0x1800289f7  lea     rax, ??_7?$_Ref_count_obj2@VClientContext@Speech@Bing@@@std@@6B@; const std::_Ref_count_obj2<Bing::Speech::ClientContext>::`vftable'
0x1800289fe  mov     [rsi], rax
0x180028a01  lea     rbx, [rsi+10h]
0x180028a05  mov     [rsp+210h+var_1B0], rbx
0x180028a0a  mov     [rbx], r12
0x180028a0d  mov     [rbx+8], r12
0x180028a11  mov     rcx, rbx
0x180028a14  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VClientContextGroup@Speech@Bing@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VClientContextGroup@Speech@Bing@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,Bing::Speech::ClientContextGroup,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Bing::Speech::ClientContextGroup>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180028a19  nop
0x180028a1a  lea     rcx, [rbx+10h]
0x180028a1e  call    ??0?$vector@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@USPDGGITEM@DGGInfo@@U?$default_delete@USPDGGITEM@DGGInfo@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>::vector<std::unique_ptr<DGGInfo::SPDGGITEM>>(void)
0x180028a23  nop
0x180028a24  lea     rcx, [rbx+28h]
0x180028a28  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x180028a2d  nop
0x180028a2e  mov     [rsp+210h+var_1A8], rbx
0x180028a33  mov     [rsp+210h+var_1A0], rsi
0x180028a38  lea     rcx, [rsp+210h+var_198]
0x180028a3d  call    ??$make_shared@VSystemProperties@Halsey@@$$V@std@@YA?AV?$shared_ptr@VSystemProperties@Halsey@@@0@XZ; std::make_shared<Halsey::SystemProperties,>(void)
0x180028a42  nop
0x180028a43  lea     r8, [rsp+210h+var_198]
0x180028a48  mov     rdx, r14
0x180028a4b  mov     rcx, rdi
0x180028a4e  call    ?Create@SystemPropertiesFactory@Client@LanguageUnderstanding@Bing@Microsoft@@QEAAJAEAV?$shared_ptr@VCuInputSapiInternal@Client@LanguageUnderstanding@Bing@Microsoft@@@std@@AEAV?$shared_ptr@VSystemProperties@Halsey@@@7@@Z; Microsoft::Bing::LanguageUnderstanding::Client::SystemPropertiesFactory::Create(std::shared_ptr<Microsoft::Bing::LanguageUnderstanding::Client::CuInputSapiInternal> &,std::shared_ptr<Halsey::SystemProperties> &)
0x180028a53  mov     ebx, eax
0x180028a55  test    eax, eax
0x180028a57  jns     short loc_180028A76
0x180028a59  mov     rcx, [rbp+118h]; this
0x180028a60  mov     r9d, eax; char *
0x180028a63  lea     r8, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180028a6a  lea     edx, [r12+3Ah]; void *
0x180028a6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028a74  jmp     short loc_180028AE9
0x180028a76  lea     rdx, aLocalpropertie; "LocalProperties"
0x180028a7d  lea     rcx, [rbp+110h+var_168]
0x180028a81  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028a86  nop
0x180028a87  mov     [rsp+210h+var_1E8], r12
0x180028a8c  mov     rdi, [rsp+210h+var_198]
0x180028a91  mov     rax, [rdi]
0x180028a94  mov     rbx, [rax+20h]
0x180028a98  lea     rcx, [rsp+210h+var_1E8]
0x180028a9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028aa2  lea     rdx, [rsp+210h+var_1E8]
0x180028aa7  mov     rcx, rdi
0x180028aaa  mov     rax, rbx
0x180028aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028ab2  mov     ebx, eax
0x180028ab4  test    eax, eax
0x180028ab6  jns     short loc_180028B07
0x180028ab8  mov     rcx, [rbp+118h]; this
0x180028abf  mov     r9d, eax; char *
0x180028ac2  lea     r8, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180028ac9  mov     edx, 3Dh ; '='; void *
0x180028ace  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ad3  nop
0x180028ad4  lea     rcx, [rsp+210h+var_1E8]
0x180028ad9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028ade  nop
0x180028adf  lea     rcx, [rbp+110h+var_168]
0x180028ae3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028ae8  nop
0x180028ae9  mov     rcx, [rbp+110h+var_190]; this
0x180028aed  test    rcx, rcx
0x180028af0  jz      short loc_180028AF8
0x180028af2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028af7  nop
0x180028af8  mov     rcx, rsi; this
0x180028afb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028b00  mov     eax, ebx
0x180028b02  jmp     loc_1800297D2
0x180028b07  mov     r8, [rsp+210h+var_1E8]
0x180028b0c  lea     rdx, [rbp+110h+var_168]
0x180028b10  lea     rcx, [rsp+210h+var_1A8]
0x180028b15  call    ?SetClientContextGroup@ClientContextCreator@Client@LanguageUnderstanding@Bing@Microsoft@@CAJAEAV?$shared_ptr@VClientContext@Speech@Bing@@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@PEAUIJsonValue@Json@Data@Windows@@@Z; Microsoft::Bing::LanguageUnderstanding::Client::ClientContextCreator::SetClientContextGroup(std::shared_ptr<Bing::Speech::ClientContext> &,std::wstring &,Windows::Data::Json::IJsonValue *)
0x180028b1a  mov     ebx, eax
0x180028b1c  test    eax, eax
0x180028b1e  jns     short loc_180028B6C
0x180028b20  mov     rcx, [rbp+118h]; this
0x180028b27  mov     r9d, eax; char *
0x180028b2a  lea     r8, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180028b31  mov     edx, 3Eh ; '>'; void *
0x180028b36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028b3b  nop
0x180028b3c  lea     rcx, [rsp+210h+var_1E8]
0x180028b41  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180028b46  nop
0x180028b47  lea     rcx, [rbp+110h+var_168]
0x180028b4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028b50  nop
0x180028b51  mov     rcx, [rbp+110h+var_190]; this
0x180028b55  test    rcx, rcx
0x180028b58  jz      short loc_180028B60
0x180028b5a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180028b5f  nop
0x180028b60  mov     rcx, [rsp+210h+var_1A0]
0x180028b65  test    rcx, rcx
0x180028b68  jz      short loc_180028B00
0x180028b6a  jmp     short loc_180028AFB
0x180028b6c  lea     rdx, aRecoproperties; "RecoProperties"
0x180028b73  lea     rcx, [rbp+110h+var_188]
0x180028b77  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028b7c  nop
0x180028b7d  lea     rdx, [rbp+110h+var_188]
0x180028b81  lea     rcx, [rbp+110h+var_100]
0x180028b85  call    ??0ClientContextGroup@Speech@Bing@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Bing::Speech::ClientContextGroup::ClientContextGroup(std::wstring const &)
0x180028b8a  nop
0x180028b8b  lea     rcx, [rbp+110h+var_188]
0x180028b8f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028b94  lea     rdx, aOptin; "OptIn"
0x180028b9b  lea     rcx, [rbp+110h+var_188]
0x180028b9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028ba4  nop
0x180028ba5  lea     rdx, [rbp+110h+var_188]
0x180028ba9  lea     rcx, [rbp+110h+var_E0]
0x180028bad  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180028bb2  mov     r8d, 4
0x180028bb8  lea     r12, aTrue; "true"
0x180028bbf  mov     rdx, r12
0x180028bc2  mov     rcx, rax
0x180028bc5  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028bca  nop
0x180028bcb  lea     rcx, [rbp+110h+var_188]
0x180028bcf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028bd4  lea     rax, aFalse; "false"
0x180028bdb  mov     rbx, r12
0x180028bde  cmp     dword ptr [rdi+0E8h], 800h
0x180028be8  cmovnz  rbx, rax
0x180028bec  lea     rdx, aKeywordstreame; "KeywordStreamed"
0x180028bf3  lea     rcx, [rbp+110h+var_188]
0x180028bf7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028bfc  nop
0x180028bfd  lea     rdx, [rbp+110h+var_188]
0x180028c01  lea     rcx, [rbp+110h+var_E0]
0x180028c05  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180028c0a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028c0e  mov     r8, rsi
0x180028c11  xor     ecx, ecx
0x180028c13  inc     r8
0x180028c16  cmp     [rbx+r8*2], cx
0x180028c1b  jnz     short loc_180028C13
0x180028c1d  mov     rdx, rbx
0x180028c20  mov     rcx, rax
0x180028c23  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028c28  nop
0x180028c29  lea     rcx, [rbp+110h+var_188]
0x180028c2d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028c32  lea     rdx, aScenario; "Scenario"
0x180028c39  lea     rcx, [rbp+110h+var_188]
0x180028c3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028c42  nop
0x180028c43  lea     rdx, [rbp+110h+var_188]
0x180028c47  lea     rcx, [rbp+110h+var_E0]
0x180028c4b  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180028c50  mov     r8, rsi
0x180028c53  xor     ecx, ecx
0x180028c55  inc     r8
0x180028c58  cmp     [r15+r8*2], cx
0x180028c5d  jnz     short loc_180028C55
0x180028c5f  mov     rdx, r15
0x180028c62  mov     rcx, rax
0x180028c65  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028c6a  nop
0x180028c6b  lea     rcx, [rbp+110h+var_188]
0x180028c6f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028c74  lea     rcx, [rdi+130h]; this
0x180028c7b  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x180028c80  mov     rbx, rax
0x180028c83  lea     rdx, aUserageclass_0; "UserAgeClass"
0x180028c8a  lea     rcx, [rbp+110h+var_188]
0x180028c8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028c93  nop
0x180028c94  lea     rdx, [rbp+110h+var_188]
0x180028c98  lea     rcx, [rbp+110h+var_E0]
0x180028c9c  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180028ca1  mov     r8, rsi
0x180028ca4  xor     r15d, r15d
0x180028ca7  inc     r8
0x180028caa  cmp     [rbx+r8*2], r15w
0x180028caf  jnz     short loc_180028CA7
0x180028cb1  mov     rdx, rbx
0x180028cb4  mov     rcx, rax
0x180028cb7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028cbc  nop
0x180028cbd  lea     rcx, [rbp+110h+var_188]
0x180028cc1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028cc6  lea     rcx, [rdi+120h]; this
0x180028ccd  call    ?c_str@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_str(void)
0x180028cd2  mov     rbx, rax
0x180028cd5  mov     rax, [rdi+120h]
0x180028cdc  test    rax, rax
0x180028cdf  jz      short loc_180028CE7
0x180028ce1  mov     rax, [rax+10h]
0x180028ce5  jmp     short loc_180028CEA
0x180028ce7  mov     rax, r15
0x180028cea  lea     r15, [rbx+rax*2]
0x180028cee  cmp     rbx, r15
0x180028cf1  jz      short loc_180028D17
0x180028cf3  movzx   ecx, word ptr [rbx]
0x180028cf6  call    cs:__imp__o_iswspace
0x180028cfc  test    eax, eax
0x180028cfe  jz      short loc_180028D06
0x180028d00  add     rbx, 2
0x180028d04  jmp     short loc_180028CEE
0x180028d06  lea     rcx, [rdi+120h]; this
0x180028d0d  call    ?c_strsafe@swstring@Halsey@@QEBAPEBGXZ; Halsey::swstring::c_strsafe(void)
0x180028d12  mov     rbx, rax
0x180028d15  jmp     short loc_180028D1E
0x180028d17  lea     rbx, aDefault; "default"
0x180028d1e  lea     rdx, aModelrevision; "ModelRevision"
0x180028d25  lea     rcx, [rbp+110h+var_188]
0x180028d29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028d2e  nop
0x180028d2f  lea     rdx, [rbp+110h+var_188]
0x180028d33  lea     rcx, [rbp+110h+var_E0]
0x180028d37  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180028d3c  mov     r8, rsi
0x180028d3f  xor     r15d, r15d
0x180028d42  inc     r8
0x180028d45  cmp     [rbx+r8*2], r15w
0x180028d4a  jnz     short loc_180028D42
0x180028d4c  mov     rdx, rbx
0x180028d4f  mov     rcx, rax
0x180028d52  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028d57  nop
0x180028d58  lea     rcx, [rbp+110h+var_188]
0x180028d5c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028d61  mov     [rsp+210h+var_1F0], r15b; int
0x180028d66  call    ?Instance@CEntityStore@@SAAEAV1@XZ; CEntityStore::Instance(void)
0x180028d6b  lea     rdx, [rsp+210h+var_1F0]; bool *
0x180028d70  mov     rcx, rax; this
0x180028d73  call    ?AreDGIAlternatesEnabled@CEntityStore@@QEBAJAEA_N@Z; CEntityStore::AreDGIAlternatesEnabled(bool &)
0x180028d78  mov     ebx, eax
0x180028d7a  test    eax, eax
0x180028d7c  jns     short loc_180028DA8
0x180028d7e  mov     rcx, [rbp+118h]; this
0x180028d85  mov     r9d, eax; char *
0x180028d88  lea     r8, aOnecoreuapEndu_16; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x180028d8f  mov     edx, 4Bh ; 'K'; void *
0x180028d94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028d99  nop
0x180028d9a  lea     rcx, [rbp+110h+var_100]; this
0x180028d9e  call    ??1ClientContextGroup@Speech@Bing@@QEAA@XZ; Bing::Speech::ClientContextGroup::~ClientContextGroup(void)
0x180028da3  jmp     loc_180028B3C
0x180028da8  cmp     [rsp+210h+var_1F0], r15b
0x180028dad  jz      short loc_180028DE8
0x180028daf  lea     rdx, aGeneratealtern; "GenerateAlternates"
0x180028db6  lea     rcx, [rbp+110h+var_188]
0x180028dba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028dbf  nop
0x180028dc0  lea     rdx, [rbp+110h+var_188]
0x180028dc4  lea     rcx, [rbp+110h+var_E0]
0x180028dc8  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180028dcd  mov     r8d, 4
0x180028dd3  mov     rdx, r12
0x180028dd6  mov     rcx, rax
0x180028dd9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180028dde  nop
0x180028ddf  lea     rcx, [rbp+110h+var_188]
0x180028de3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180028de8  mov     rdx, [r14]
0x180028deb  mov     edx, [rdx+228h]
0x180028df1  lea     rcx, [rbp+110h+var_128]
0x180028df5  call    Microsoft__Bing__LanguageUnderstanding__Client__UserScenarioStringFromEnum
0x180028dfa  nop
0x180028dfb  lea     rbx, [rbp+110h+var_128]
0x180028dff  cmp     [rbp+110h+var_110], 7
0x180028e04  cmova   rbx, [rbp+110h+var_128]
0x180028e09  lea     rdx, aClienttype; "ClientType"
0x180028e10  lea     rcx, [rbp+110h+var_188]
0x180028e14  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028e19  nop
  ... truncated ...
```
