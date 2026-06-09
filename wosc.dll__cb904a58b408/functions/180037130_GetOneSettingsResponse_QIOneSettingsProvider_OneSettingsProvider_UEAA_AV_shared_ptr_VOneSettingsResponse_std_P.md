# ?GetOneSettingsResponse@?QIOneSettingsProvider@@OneSettingsProvider@@UEAA?AV?$shared_ptr@VOneSettingsResponse@@@std@@PEAVIOneSettingsConfiguration@@@Z

- ea: `0x180037130`
- end: `0x180037c38`
- name: `?GetOneSettingsResponse@?QIOneSettingsProvider@@OneSettingsProvider@@UEAA?AV?$shared_ptr@VOneSettingsResponse@@@std@@PEAVIOneSettingsConfiguration@@@Z`
- size: `2824`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180003110`
- `0x180005657`
- `0x180005663`
- `0x18000843c`
- `0x180009c0c`
- `0x180009f90`
- `0x18000a7c0`
- `0x18000e5ac`
- `0x1800101fc`
- `0x180010278`
- `0x180013340`
- `0x180013f24`
- `0x180014928`
- `0x180014f30`
- `0x180019e48`
- `0x180019e68`
- `0x180019f58`
- `0x18001a128`
- `0x180020748`
- `0x180021f60`
- `0x180025b28`
- `0x18002bde4`
- `0x18002dc50`
- `0x180032970`
- `0x180032a2c`
- `0x180034134`
- `0x1800342ac`
- `0x180034b9c`
- `0x180034ca4`
- `0x180034de0`
- `0x180034f1c`
- `0x1800353c0`
- `0x180035480`
- `0x180035dac`
- `0x1800363e8`
- `0x180036b68`
- `0x180036d3c`
- `0x1800370bc`
- `0x180037130`
- `0x18003b9c8`
- `0x1800544d8`
- `0x180059010`

## import_xrefs

- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x180037946`
- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x18003798f`
- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x180037946`
- `OneSettingsClient!OneSettingsGetResponseStringProperty` at `0x18003798f`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x1800378a1`
- `OneSettingsClient!OneSettingsGetResponseWideStringProperty` at `0x1800378a1`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x18003766c`
- `OneSettingsClient!OneSettingsStartDownloadSession` at `0x18003766c`
- `OneSettingsClient!OneSettingsEndDownloadSession` at `0x18003763c`

## string_xrefs

- `0x1800371b7`: `settings-win.data.microsoft.com`
- `0x1800371b0`: `settings-win-ppe.data.microsoft.com`
- `0x1800376a5`: `settings-win-ppe.data.microsoft.com`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall _GetOneSettingsResponse__QIOneSettingsProvider__OneSettingsProvider__UEAA_AV__shared_ptr_VOneSettingsResponse___std__PEAVIOneSettingsConfiguration___Z(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // eax
  const wchar_t *v5; // rcx
  _QWORD *v6; // rdx
  _QWORD *v7; // rcx
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  _QWORD *v10; // rdx
  _QWORD *v11; // rax
  _WORD *v12; // rax
  _WORD *v13; // rbx
  __int64 v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r14
  unsigned __int64 v21; // rcx
  void *v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  _WORD *v25; // rax
  _WORD *v26; // r14
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rbx
  int started; // eax
  int v33; // ebx
  bool v34; // bl
  __int64 v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rcx
  int v44; // ebx
  __int64 v45; // rcx
  const unsigned __int16 *v46; // rbx
  const unsigned __int16 *v47; // rax
  int v48; // eax
  int v49; // ebx
  __int64 v50; // r8
  int ResponseWideStringProperty; // eax
  __int64 v52; // rdx
  __int64 v53; // r8
  size_t v54; // rdi
  int ResponseStringProperty; // eax
  struct OneSettingsDownloadSession *v56; // r9
  int v57; // eax
  void *v58; // rbx
  const void *v59; // r9
  const unsigned __int16 *v61; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+20h] [rbp-E0h]
  __int64 v63; // [rsp+40h] [rbp-C0h] BYREF
  struct OneSettingsDownloadSession *v64; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  int v66; // [rsp+58h] [rbp-A8h] BYREF
  int v67; // [rsp+60h] [rbp-A0h] BYREF
  int v68; // [rsp+64h] [rbp-9Ch] BYREF
  const wchar_t *v69; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v70[4]; // [rsp+70h] [rbp-90h] BYREF
  struct OneSettingsDownloadSession *v71[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v72; // [rsp+A0h] [rbp-60h]
  __int64 v73; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v74[4]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v75[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v76; // [rsp+E8h] [rbp-18h] BYREF
  char v77; // [rsp+ECh] [rbp-14h]
  int v78; // [rsp+F0h] [rbp-10h] BYREF
  char v79; // [rsp+F4h] [rbp-Ch]
  struct OneSettingsDownloadSession *v80; // [rsp+110h] [rbp+10h]
  size_t v81; // [rsp+118h] [rbp+18h]
  __int64 v82; // [rsp+120h] [rbp+20h]
  __int64 v83; // [rsp+128h] [rbp+28h]
  void *Src[2]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int64 v85; // [rsp+170h] [rbp+70h]
  __int64 v86; // [rsp+178h] [rbp+78h]
  _QWORD v87[4]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v88; // [rsp+1A0h] [rbp+A0h] BYREF
  size_t v89; // [rsp+1B0h] [rbp+B0h]
  unsigned __int64 v90; // [rsp+1B8h] [rbp+B8h]
  _QWORD v91[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v92; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v93; // [rsp+1F0h] [rbp+F0h]
  __int64 v94; // [rsp+1F8h] [rbp+F8h]
  __int128 v95; // [rsp+200h] [rbp+100h] BYREF
  __m128i si128; // [rsp+210h] [rbp+110h]
  _BYTE v97[32]; // [rsp+220h] [rbp+120h] BYREF
  _OWORD v98[2]; // [rsp+240h] [rbp+140h] BYREF
  _QWORD v99[7]; // [rsp+260h] [rbp+160h] BYREF
  _QWORD *v100; // [rsp+298h] [rbp+198h]
  _QWORD v101[7]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _QWORD *v102; // [rsp+2D8h] [rbp+1D8h]
  _QWORD v103[7]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _QWORD *v104; // [rsp+318h] [rbp+218h]
  _QWORD v105[7]; // [rsp+320h] [rbp+220h] BYREF
  _QWORD *v106; // [rsp+358h] [rbp+258h]
  _BYTE v107[32]; // [rsp+360h] [rbp+260h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v87[0] = a2;
  v65 = a3;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v70);
  v95 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v95) = 0;
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 48LL))(v65);
  v5 = L"settings-win.data.microsoft.com";
  if ( v4 )
    v5 = L"settings-win-ppe.data.microsoft.com";
  v69 = v5;
  v103[0] = &std::_Func_impl_no_alloc<bool (*)(long),bool,long>::`vftable';
  v103[1] = OneSettingsProvider::ShouldRetry;
  v104 = v103;
  v99[0] = off_18005B418;
  v99[1] = &v65;
  v99[2] = &v69;
  v99[3] = &v95;
  v100 = v99;
  v68 = OneSettingsUtilities::DoRetriableOperation(v5, v99, v103);
  if ( v100 )
  {
    v6 = v99;
    LOBYTE(v6) = v100 != v99;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v100 + 32LL))(v100, v6);
    v100 = 0;
  }
  v7 = v104;
  if ( v104 )
  {
    v8 = v103;
    LOBYTE(v8) = v104 != v103;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v104 + 32LL))(v104, v8);
  }
  v105[0] = &std::_Func_impl_no_alloc<bool (*)(long),bool,long>::`vftable';
  v105[1] = OneSettingsProvider::ShouldRetry;
  v106 = v105;
  v101[0] = off_18005B448;
  v101[1] = &v65;
  v101[2] = &v95;
  v102 = v101;
  v67 = OneSettingsUtilities::DoRetriableOperation(v7, v101, v105);
  if ( v102 )
  {
    v9 = v101;
    LOBYTE(v9) = v102 != v101;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v102 + 32LL))(v102, v9);
    v102 = 0;
  }
  if ( v106 )
  {
    v10 = v105;
    LOBYTE(v10) = v106 != v105;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v106 + 32LL))(v106, v10);
  }
  if ( si128.m128i_i64[0] )
  {
    std::wstring::wstring((__int64)v91, (__int64)L"Authorization");
    v11 = (_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(v70, v87, v91);
    std::wstring::operator=(*v11 + 64LL);
    std::wstring::_Tidy_deallocate(v91);
  }
  v12 = (_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 56LL))(v65);
  v13 = v12;
  v14 = -1;
  if ( v12 && *v12 )
  {
    std::wstring::wstring((__int64)v91, (__int64)L"If-None-Match");
    v15 = *(_QWORD *)std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(v70, v87, v91) + 64LL;
    v16 = -1;
    do
      ++v16;
    while ( v13[v16] );
    std::wstring::_Assign<unsigned short>(v15, v13);
    std::wstring::_Tidy_deallocate(v91);
  }
  *(_OWORD *)Src = 0;
  v17 = 0;
  v85 = 0;
  v18 = 7;
  v86 = 7;
  LOWORD(Src[0]) = 0;
  v19 = *(_QWORD *)v70[0];
  v63 = *(_QWORD *)v70[0];
  while ( !*(_BYTE *)(v19 + 25) )
  {
    v20 = v19 + 32;
    v21 = v17 + *(_QWORD *)(v19 + 80) + *(_QWORD *)(v19 + 48) + 4LL;
    if ( v17 <= v21 && v18 != v21 )
    {
      if ( v18 >= v21 )
      {
        if ( v21 <= 7 && v18 > 7 )
        {
          v22 = Src[0];
          memcpy_0(Src, Src[0], 2 * v17 + 2);
          std::_Deallocate<16>(v22, 2 * v86 + 2);
          v86 = 7;
        }
      }
      else
      {
        std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(Src);
        v85 = v17;
      }
    }
    v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
    std::wstring::_Append<unsigned short>(Src, v23, *(_QWORD *)(v20 + 16));
    std::wstring::append(Src, L": ");
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20 + 32);
    std::wstring::_Append<unsigned short>(Src, v24, *(_QWORD *)(v20 + 48));
    std::wstring::append(Src, L"\r\n");
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(&v63);
    v18 = v86;
    v17 = v85;
    v19 = v63;
  }
  v98[0] = 0;
  v98[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v98[0]) = 0;
  v25 = (_WORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 24LL))(v65);
  v26 = v25;
  if ( v25 && *v25 )
  {
    v27 = std::wstring::wstring((__int64)v87, (__int64)L"?");
    v28 = std::operator+<unsigned short>(v97, v27, v26);
    std::wstring::operator=(v98, v28);
    std::wstring::_Tidy_deallocate(v97);
    std::wstring::_Tidy_deallocate(v87);
  }
  v29 = (**(__int64 (__fastcall ***)(__int64))v65)(v65);
  v30 = std::wstring::wstring((__int64)v97, (__int64)L"wosc_");
  std::operator+<unsigned short>(v107, v30, v29);
  std::wstring::_Tidy_deallocate(v97);
  Microsoft::Diagnostics::OneSettingsClientWrapper::OneSettingsClientWrapper((Microsoft::Diagnostics::OneSettingsClientWrapper *)v71);
  v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v107);
  if ( v71[0] )
  {
    v64 = v71[0];
    wil::last_error_context::last_error_context((wil::last_error_context *)&v66);
    v63 = OneSettingsEndDownloadSession;
    wistd::invoke<long (*)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &>(&v63, &v64);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v66);
  }
  v71[0] = 0;
  started = OneSettingsStartDownloadSession(v31, v71);
  v33 = started;
  if ( started < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
      (const char *)(unsigned int)started,
      (int)v61);
  if ( v33 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\onesettingsprovider\\onesettingsprovider.cpp",
      (const char *)(unsigned int)v33,
      (int)v61);
  v34 = v69 == L"settings-win-ppe.data.microsoft.com";
  LODWORD(v63) = 1;
  v35 = *(_QWORD *)std::map<enum OneSettingsDownloadConfigBoolProperty,std::optional<bool>>::_Try_emplace<enum OneSettingsDownloadConfigBoolProperty,>(
                     &v73,
                     (__int64)v87,
                     &v63);
  *(_BYTE *)(v35 + 32) = v34;
  *(_BYTE *)(v35 + 33) = 1;
  v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v98);
  v37 = v36;
  v38 = -1;
  do
    ++v38;
  while ( *(_WORD *)(v36 + 2 * v38) );
  LODWORD(v63) = 0;
  v39 = *(_QWORD *)std::map<enum OneSettingsDownloadConfigWideStringProperty,std::basic_string_view<unsigned short>>::_Try_emplace<enum OneSettingsDownloadConfigWideStringProperty,>(
                     v75,
                     (__int64)v87,
                     &v63);
  *(_QWORD *)(v39 + 40) = v37;
  *(_QWORD *)(v39 + 48) = v38;
  v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
  v41 = v40;
  v42 = -1;
  do
    ++v42;
  while ( *(_WORD *)(v40 + 2 * v42) );
  v66 = 1;
  v43 = *(_QWORD *)std::map<enum OneSettingsDownloadConfigWideStringProperty,std::basic_string_view<unsigned short>>::_Try_emplace<enum OneSettingsDownloadConfigWideStringProperty,>(
                     v75,
                     (__int64)v91,
                     &v66);
  *(_QWORD *)(v43 + 40) = v41;
  *(_QWORD *)(v43 + 48) = v42;
  v44 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 40LL))(v65);
  LODWORD(v63) = 0;
  v45 = *(_QWORD *)std::map<enum OneSettingsDownloadConfigDwordProperty,std::optional<unsigned long>>::_Try_emplace<enum OneSettingsDownloadConfigDwordProperty,>(
                     v74,
                     (__int64)v87,
                     &v63);
  *(_DWORD *)(v45 + 32) = v44;
  *(_BYTE *)(v45 + 36) = 1;
  *(_WORD *)(v45 + 37) = *(_WORD *)((char *)&v64 + 5);
  *(_BYTE *)(v45 + 39) = HIBYTE(v64);
  v46 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  v47 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
  v48 = Microsoft::Diagnostics::OneSettingsClientWrapper::Download(
          (Microsoft::Diagnostics::OneSettingsClientWrapper *)v71,
          v71[0],
          v47,
          v46,
          v61);
  v49 = v48;
  if ( v48 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
      (const char *)(unsigned int)v48,
      v62);
  if ( v49 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\onesettingsprovider\\onesettingsprovider.cpp",
      (const char *)(unsigned int)v49,
      v62);
  Microsoft::Diagnostics::OneSettingsClientWrapper::GetDwordResponseProperty(v71, 0, &v76);
  if ( !v77 )
    std::_Throw_bad_optional_access();
  v66 = v76;
  LODWORD(v63) = 1440;
  v92 = 0;
  v93 = 0;
  v94 = 7;
  LOWORD(v92) = 0;
  v88 = 0;
  v89 = 0;
  v90 = 15;
  LOBYTE(v88) = 0;
  if ( v76 == 200 || v76 == 304 )
  {
    if ( v83 )
    {
      v52 = v82;
    }
    else
    {
      v63 = 0;
      ResponseWideStringProperty = OneSettingsGetResponseWideStringProperty(v72, 0, &v63);
      if ( ResponseWideStringProperty < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x120,
          (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
          (const char *)(unsigned int)ResponseWideStringProperty,
          v62);
      v52 = v63;
      v53 = -1;
      do
        ++v53;
      while ( *(_WORD *)(v63 + 2 * v53) );
      v82 = v63;
      v83 = v53;
    }
    std::wstring::_Assign<unsigned short>(&v92, v52);
    if ( !v93 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x69,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\onesettingsprovider\\onesettingsprovider.cpp",
        (const char *)0x83760002LL,
        v62);
    Microsoft::Diagnostics::OneSettingsClientWrapper::GetDwordResponseProperty(v71, 1, &v78);
    if ( !v79 )
      std::_Throw_bad_optional_access();
    LODWORD(v63) = v78;
    if ( !v78 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\onesettingsprovider\\onesettingsprovider.cpp",
        (const char *)0x83760002LL,
        v62);
  }
  v54 = v81;
  if ( v81 )
  {
    v56 = v80;
  }
  else
  {
    v64 = 0;
    ResponseStringProperty = OneSettingsGetResponseStringProperty(v72, 0, &v64);
    if ( ResponseStringProperty < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
        (const char *)(unsigned int)ResponseStringProperty,
        v62);
    v56 = v64;
    v54 = -1;
    do
      ++v54;
    while ( *((_BYTE *)v64 + v54) );
    v80 = v64;
    v81 = v54;
  }
  if ( !v54 )
  {
    v64 = 0;
    v57 = OneSettingsGetResponseStringProperty(v72, 0, &v64);
    if ( v57 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\internal\\base\\inc\\OneSettingsClientWrapper.h",
        (const char *)(unsigned int)v57,
        v62);
    v56 = v64;
    do
      ++v14;
    while ( *((_BYTE *)v64 + v14) );
    v80 = v64;
    v81 = v14;
  }
  if ( v54 > v90 )
  {
    std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(&v88, v54, v50, v56);
  }
  else
  {
    v58 = (void *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v88);
    v89 = v54;
    memmove_0(v58, v59, v54);
    *((_BYTE *)v58 + v54) = 0;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_WoscNoQueryRegex>::GetImpl'::`2'::impl) )
  {
    v91[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 32LL))(v65);
    v64 = (struct OneSettingsDownloadSession *)std::_String_val<std::_Simple_types<char>>::_Myptr(&v88);
    v87[0] = (**(__int64 (__fastcall ***)(__int64))v65)(v65);
    OneSettingsClientTelemetryCore::OneSettingsPayloadDownload2<unsigned short const *,unsigned int &,unsigned short const * &,char const *>(
      v87,
      &v66,
      v91,
      &v64);
  }
  else
  {
    OneSettingsProvider::CleanQueryForLogging(v97, v26);
    v87[0] = std::_String_val<std::_Simple_types<char>>::_Myptr(&v88);
    v91[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v97);
    v64 = (struct OneSettingsDownloadSession *)(**(__int64 (__fastcall ***)(__int64))v65)(v65);
    OneSettingsClientTelemetryCore::OneSettingsPayloadDownload2<unsigned short const *,unsigned int &,unsigned short const *,char const *>(
      &v64,
      &v66,
      v91,
      v87);
    std::wstring::_Tidy_deallocate(v97);
  }
  std::make_shared<OneSettingsResponse,unsigned int &,long const &,long &,std::string &,std::wstring &,unsigned int &>(
    a2,
    (unsigned int)&v66,
    (unsigned int)&v68,
    (unsigned int)&v67,
    (__int64)&v88,
    (__int64)&v92,
    (__int64)&v63);
  std::string::_Tidy_deallocate(&v88);
  std::wstring::_Tidy_deallocate(&v92);
  Microsoft::Diagnostics::OneSettingsClientWrapper::~OneSettingsClientWrapper((Microsoft::Diagnostics::OneSettingsClientWrapper *)v71);
  std::wstring::_Tidy_deallocate(v107);
  std::wstring::_Tidy_deallocate(v98);
  std::wstring::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(&v95);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v70);
  return a2;
}

```

## disassembly

```asm
0x180037130  mov     [rsp-8+arg_0], rbx
0x180037135  push    rbp
0x180037136  push    rsi
0x180037137  push    rdi
0x180037138  push    r12
0x18003713a  push    r13
0x18003713c  push    r14
0x18003713e  push    r15
0x180037140  lea     rbp, [rsp-290h]
0x180037148  sub     rsp, 390h
0x18003714f  mov     rax, cs:__security_cookie
0x180037156  xor     rax, rsp
0x180037159  mov     [rbp+2C0h+var_40], rax
0x180037160  mov     r15, rdx
0x180037163  mov     [rbp+2C0h+var_240], rdx
0x18003716a  mov     [rsp+3C0h+var_370], r8
0x18003716f  xor     r12d, r12d
0x180037172  lea     rcx, [rsp+3C0h+var_350]
0x180037177  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18003717c  nop
0x18003717d  xorps   xmm0, xmm0
0x180037180  movups  [rbp+2C0h+var_1C0], xmm0
0x180037187  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003718f  movdqu  [rbp+2C0h+var_1B0], xmm1
0x180037197  mov     word ptr [rbp+2C0h+var_1C0], r12w
0x18003719f  mov     rcx, [rsp+3C0h+var_370]
0x1800371a4  mov     rax, [rcx]
0x1800371a7  mov     rax, [rax+30h]
0x1800371ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800371b0  lea     rdx, aSettingsWinPpe; "settings-win-ppe.data.microsoft.com"
0x1800371b7  lea     rcx, aSettingsWinDat; "settings-win.data.microsoft.com"
0x1800371be  test    eax, eax
0x1800371c0  cmovnz  rcx, rdx
0x1800371c4  mov     [rsp+3C0h+var_358], rcx
0x1800371c9  lea     rbx, ??_7?$_Func_impl_no_alloc@P6A_NJ@Z_NJ@std@@6B@; const std::_Func_impl_no_alloc<bool (*)(long),bool,long>::`vftable'
0x1800371d0  mov     [rbp+2C0h+var_E0], rbx
0x1800371d7  lea     rdi, ?ShouldRetry@OneSettingsProvider@@CA_NJ@Z; OneSettingsProvider::ShouldRetry(long)
0x1800371de  mov     [rbp+2C0h+var_D8], rdi
0x1800371e5  lea     rax, [rbp+2C0h+var_E0]
0x1800371ec  mov     [rbp+2C0h+var_A8], rax
0x1800371f3  lea     rax, off_18005B418
0x1800371fa  mov     [rbp+2C0h+var_160], rax
0x180037201  lea     rax, [rsp+3C0h+var_370]
0x180037206  mov     [rbp+2C0h+var_158], rax
0x18003720d  lea     rax, [rsp+3C0h+var_358]
0x180037212  mov     [rbp+2C0h+var_150], rax
0x180037219  lea     rax, [rbp+2C0h+var_1C0]
0x180037220  mov     [rbp+2C0h+var_148], rax
0x180037227  lea     rax, [rbp+2C0h+var_160]
0x18003722e  mov     [rbp+2C0h+var_128], rax
0x180037235  lea     r8, [rbp+2C0h+var_E0]
0x18003723c  lea     rdx, [rbp+2C0h+var_160]
0x180037243  call    ?DoRetriableOperation@OneSettingsUtilities@@SAJKAEBV?$function@$$A6AJK@Z@std@@AEBV?$function@$$A6A_NJ@Z@3@@Z; OneSettingsUtilities::DoRetriableOperation(ulong,std::function<long (ulong)> const &,std::function<bool (long)> const &)
0x180037248  mov     [rsp+3C0h+var_35C], eax
0x18003724c  mov     rcx, [rbp+2C0h+var_128]
0x180037253  test    rcx, rcx
0x180037256  jz      short loc_180037278
0x180037258  mov     rax, [rcx]
0x18003725b  lea     rdx, [rbp+2C0h+var_160]
0x180037262  cmp     rcx, rdx
0x180037265  setnz   dl
0x180037268  mov     rax, [rax+20h]
0x18003726c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037271  mov     [rbp+2C0h+var_128], r12
0x180037278  mov     rcx, [rbp+2C0h+var_A8]
0x18003727f  test    rcx, rcx
0x180037282  jz      short loc_18003729D
0x180037284  mov     rax, [rcx]
0x180037287  lea     rdx, [rbp+2C0h+var_E0]
0x18003728e  cmp     rcx, rdx
0x180037291  setnz   dl
0x180037294  mov     rax, [rax+20h]
0x180037298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003729d  mov     [rbp+2C0h+var_A0], rbx
0x1800372a4  mov     [rbp+2C0h+var_98], rdi
0x1800372ab  lea     rax, [rbp+2C0h+var_A0]
0x1800372b2  mov     [rbp+2C0h+var_68], rax
0x1800372b9  lea     rax, off_18005B448
0x1800372c0  mov     [rbp+2C0h+var_120], rax
0x1800372c7  lea     rax, [rsp+3C0h+var_370]
0x1800372cc  mov     [rbp+2C0h+var_118], rax
0x1800372d3  lea     rax, [rbp+2C0h+var_1C0]
0x1800372da  mov     [rbp+2C0h+var_110], rax
0x1800372e1  lea     rax, [rbp+2C0h+var_120]
0x1800372e8  mov     [rbp+2C0h+var_E8], rax
0x1800372ef  lea     r8, [rbp+2C0h+var_A0]
0x1800372f6  lea     rdx, [rbp+2C0h+var_120]
0x1800372fd  call    ?DoRetriableOperation@OneSettingsUtilities@@SAJKAEBV?$function@$$A6AJK@Z@std@@AEBV?$function@$$A6A_NJ@Z@3@@Z; OneSettingsUtilities::DoRetriableOperation(ulong,std::function<long (ulong)> const &,std::function<bool (long)> const &)
0x180037302  mov     [rsp+3C0h+var_360], eax
0x180037306  mov     rcx, [rbp+2C0h+var_E8]
0x18003730d  test    rcx, rcx
0x180037310  jz      short loc_180037332
0x180037312  mov     rax, [rcx]
0x180037315  lea     rdx, [rbp+2C0h+var_120]
0x18003731c  cmp     rcx, rdx
0x18003731f  setnz   dl
0x180037322  mov     rax, [rax+20h]
0x180037326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003732b  mov     [rbp+2C0h+var_E8], r12
0x180037332  mov     rcx, [rbp+2C0h+var_68]
0x180037339  test    rcx, rcx
0x18003733c  jz      short loc_180037357
0x18003733e  mov     rax, [rcx]
0x180037341  lea     rdx, [rbp+2C0h+var_A0]
0x180037348  cmp     rcx, rdx
0x18003734b  setnz   dl
0x18003734e  mov     rax, [rax+20h]
0x180037352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037357  cmp     qword ptr [rbp+2C0h+var_1B0], r12
0x18003735e  jbe     short loc_1800373AC
0x180037360  lea     rdx, aAuthorization; "Authorization"
0x180037367  lea     rcx, [rbp+2C0h+var_200]
0x18003736e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180037373  nop
0x180037374  lea     r8, [rbp+2C0h+var_200]
0x18003737b  lea     rdx, [rbp+2C0h+var_240]
0x180037382  lea     rcx, [rsp+3C0h+var_350]
0x180037387  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x18003738c  mov     rcx, [rax]
0x18003738f  add     rcx, 40h ; '@'
0x180037393  lea     rdx, [rbp+2C0h+var_1C0]
0x18003739a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003739f  nop
0x1800373a0  lea     rcx, [rbp+2C0h+var_200]
0x1800373a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800373ac  mov     rcx, [rsp+3C0h+var_370]
0x1800373b1  mov     rax, [rcx]
0x1800373b4  mov     rax, [rax+38h]
0x1800373b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800373bd  mov     rbx, rax
0x1800373c0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800373c4  test    rax, rax
0x1800373c7  jz      short loc_180037424
0x1800373c9  cmp     [rax], r12w
0x1800373cd  jz      short loc_180037424
0x1800373cf  lea     rdx, aIfNoneMatch; "If-None-Match"
0x1800373d6  lea     rcx, [rbp+2C0h+var_200]
0x1800373dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800373e2  nop
0x1800373e3  lea     r8, [rbp+2C0h+var_200]
0x1800373ea  lea     rdx, [rbp+2C0h+var_240]
0x1800373f1  lea     rcx, [rsp+3C0h+var_350]
0x1800373f6  call    ??$_Try_emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::wstring>::_Try_emplace<std::wstring,>(std::wstring &&)
0x1800373fb  mov     rcx, [rax]
0x1800373fe  add     rcx, 40h ; '@'
0x180037402  mov     r8, rsi
0x180037405  inc     r8
0x180037408  cmp     [rbx+r8*2], r12w
0x18003740d  jnz     short loc_180037405
0x18003740f  mov     rdx, rbx
0x180037412  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180037417  nop
0x180037418  lea     rcx, [rbp+2C0h+var_200]
0x18003741f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037424  xorps   xmm0, xmm0
0x180037427  movups  xmmword ptr [rbp+2C0h+Src], xmm0
0x18003742b  mov     rdi, r12
0x18003742e  mov     [rbp+2C0h+var_250], r12
0x180037432  mov     r13d, 7
0x180037438  mov     edx, r13d
0x18003743b  mov     [rbp+2C0h+var_248], rdx
0x18003743f  mov     word ptr [rbp+2C0h+Src], r12w
0x180037444  mov     rax, [rsp+3C0h+var_350]
0x180037449  mov     rax, [rax]
0x18003744c  mov     [rsp+3C0h+var_380], rax
0x180037451  cmp     [rax+19h], r12b
0x180037455  jnz     loc_180037536
0x18003745b  lea     r14, [rax+20h]
0x18003745f  mov     rcx, [r14+10h]
0x180037463  add     rcx, 4
0x180037467  add     rcx, [r14+30h]
0x18003746b  add     rcx, rdi
0x18003746e  cmp     rdi, rcx
0x180037471  ja      short loc_1800374C9
0x180037473  cmp     rdx, rcx
0x180037476  jz      short loc_1800374C9
0x180037478  jnb     short loc_18003748F
0x18003747a  sub     rcx, rdi
0x18003747d  mov     rdx, rcx
0x180037480  lea     rcx, [rbp+2C0h+Src]; Src
0x180037484  call    ??$_Reallocate_grow_by@V_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_7f96eb1dcf99da5daec8c2467d2d5499_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_7f96eb1dcf99da5daec8c2467d2d5499_,>(unsigned __int64,_lambda_7f96eb1dcf99da5daec8c2467d2d5499_)
0x180037489  mov     [rbp+2C0h+var_250], rdi
0x18003748d  jmp     short loc_1800374C9
0x18003748f  cmp     rcx, r13
0x180037492  ja      short loc_1800374C9
0x180037494  cmp     rdx, r13
0x180037497  jbe     short loc_1800374C9
0x180037499  mov     rbx, [rbp+2C0h+Src]
0x18003749d  lea     r8, ds:2[rdi*2]; Size
0x1800374a5  mov     rdx, rbx; Src
0x1800374a8  lea     rcx, [rbp+2C0h+Src]; void *
0x1800374ac  call    memcpy_0
0x1800374b1  mov     rdx, [rbp+2C0h+var_248]
0x1800374b5  lea     rdx, ds:2[rdx*2]
0x1800374bd  mov     rcx, rbx
0x1800374c0  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800374c5  mov     [rbp+2C0h+var_248], r13
0x1800374c9  mov     rcx, r14
0x1800374cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800374d1  mov     r8, [r14+10h]
0x1800374d5  mov     rdx, rax
0x1800374d8  lea     rcx, [rbp+2C0h+Src]
0x1800374dc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800374e1  lea     rdx, asc_180062418; ": "
0x1800374e8  lea     rcx, [rbp+2C0h+Src]
0x1800374ec  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800374f1  lea     rcx, [r14+20h]
0x1800374f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800374fa  mov     r8, [r14+30h]
0x1800374fe  mov     rdx, rax
0x180037501  lea     rcx, [rbp+2C0h+Src]
0x180037505  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003750a  lea     rdx, asc_180062420; "\r\n"
0x180037511  lea     rcx, [rbp+2C0h+Src]
0x180037515  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18003751a  lea     rcx, [rsp+3C0h+var_380]
0x18003751f  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UCnsFlightState@@@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::shared_ptr<CnsFlightState>>>>,std::_Iterator_base0>::operator++(void)
0x180037524  mov     rdx, [rbp+2C0h+var_248]
0x180037528  mov     rdi, [rbp+2C0h+var_250]
0x18003752c  mov     rax, [rsp+3C0h+var_380]
0x180037531  jmp     loc_180037451
0x180037536  xorps   xmm0, xmm0
0x180037539  movups  [rbp+2C0h+var_180], xmm0
0x180037540  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180037548  movdqu  [rbp+2C0h+var_170], xmm1
0x180037550  mov     word ptr [rbp+2C0h+var_180], r12w
0x180037558  mov     rcx, [rsp+3C0h+var_370]
0x18003755d  mov     rax, [rcx]
0x180037560  mov     rax, [rax+18h]
0x180037564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037569  mov     r14, rax
0x18003756c  test    rax, rax
0x18003756f  jz      short loc_1800375C5
0x180037571  cmp     [rax], r12w
0x180037575  jz      short loc_1800375C5
0x180037577  lea     rdx, asc_180062428; "?"
0x18003757e  lea     rcx, [rbp+2C0h+var_240]
0x180037585  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003758a  nop
0x18003758b  mov     r8, r14
0x18003758e  mov     rdx, rax
0x180037591  lea     rcx, [rbp+2C0h+var_1A0]
0x180037598  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18003759d  mov     rdx, rax
0x1800375a0  lea     rcx, [rbp+2C0h+var_180]
0x1800375a7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800375ac  lea     rcx, [rbp+2C0h+var_1A0]
0x1800375b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800375b8  nop
0x1800375b9  lea     rcx, [rbp+2C0h+var_240]
0x1800375c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800375c5  mov     rcx, [rsp+3C0h+var_370]
0x1800375ca  mov     rax, [rcx]
0x1800375cd  mov     rax, [rax]
0x1800375d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800375d5  mov     rbx, rax
0x1800375d8  lea     rdx, aWosc_0; "wosc_"
0x1800375df  lea     rcx, [rbp+2C0h+var_1A0]
0x1800375e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800375eb  nop
0x1800375ec  mov     r8, rbx
0x1800375ef  mov     rdx, rax
0x1800375f2  lea     rcx, [rbp+2C0h+var_60]
0x1800375f9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800375fe  nop
0x1800375ff  lea     rcx, [rbp+2C0h+var_1A0]
0x180037606  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003760b  lea     rcx, [rbp+2C0h+var_330]; this
0x18003760f  call    ??0OneSettingsClientWrapper@Diagnostics@Microsoft@@QEAA@XZ; Microsoft::Diagnostics::OneSettingsClientWrapper::OneSettingsClientWrapper(void)
0x180037614  nop
0x180037615  lea     rcx, [rbp+2C0h+var_60]
0x18003761c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180037621  mov     rbx, rax
0x180037624  mov     rcx, [rbp+2C0h+var_330]
0x180037628  test    rcx, rcx
0x18003762b  jz      short loc_180037661
0x18003762d  mov     [rsp+3C0h+var_378], rcx
0x180037632  lea     rcx, [rsp+3C0h+var_368]; this
0x180037637  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003763c  mov     rax, cs:__imp_OneSettingsEndDownloadSession
0x180037643  mov     [rsp+3C0h+var_380], rax
0x180037648  lea     rdx, [rsp+3C0h+var_378]
0x18003764d  lea     rcx, [rsp+3C0h+var_380]
0x180037652  call    ??$invoke@P6AJPEAUOneSettingsDownloadSession@@@ZAEAPEAU1@@wistd@@YAJ$$QEAP6AJPEAUOneSettingsDownloadSession@@@ZAEAPEAU1@@Z; wistd::invoke<long (*)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &>(long (*&&)(OneSettingsDownloadSession *),OneSettingsDownloadSession * &)
0x180037657  lea     rcx, [rsp+3C0h+var_368]; this
0x18003765c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180037661  mov     [rbp+2C0h+var_330], r12
0x180037665  lea     rdx, [rbp+2C0h+var_330]
0x180037669  mov     rcx, rbx
0x18003766c  call    cs:__imp_OneSettingsStartDownloadSession
0x180037672  mov     ebx, eax
0x180037674  lea     r13, aOnecoreInterna_7; "onecore\\internal\\base\\inc\\OneSettin"...
0x18003767b  test    eax, eax
0x18003767d  jns     short loc_180037696
0x18003767f  mov     rcx, [rbp+2C8h]; this
0x180037686  mov     r9d, eax; char *
0x180037689  mov     r8, r13; unsigned int
0x18003768c  mov     edx, 1Ah; void *
0x180037691  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037696  mov     rcx, [rbp+2C8h]; this
  ... truncated ...
```
