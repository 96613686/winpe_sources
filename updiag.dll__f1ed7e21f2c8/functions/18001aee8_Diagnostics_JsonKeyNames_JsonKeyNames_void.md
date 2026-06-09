# Diagnostics::JsonKeyNames::JsonKeyNames(void)

- ea: `0x18001aee8`
- end: `0x18001b5db`
- name: `??0JsonKeyNames@Diagnostics@@AEAA@XZ`
- size: `1779`
- prototype: `__int128 *__fastcall(Diagnostics::JsonKeyNames *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18001ae44`

## callees

- `0x180018e9c`
- `0x180018eec`
- `0x180019080`
- `0x18001aee8`
- `0x18001bf7c`
- `0x18001c0c0`
- `0x18001c274`
- `0x18001c3c0`
- `0x18001c50c`
- `0x18001c5c8`
- `0x18001c6d8`
- `0x18001ca80`
- `0x18008ffd4`
- `0x180095af0`

## string_xrefs

- `0x18001b572`: `14_InstallLanguage`

## pseudocode

```c
__int128 *__fastcall Diagnostics::JsonKeyNames::JsonKeyNames(Diagnostics::JsonKeyNames *this)
{
  _QWORD *v1; // rax
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rbx
  _OWORD *v19; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax
  __int128 v22; // xmm6
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rbx
  _OWORD *v27; // rsi
  __int64 v28; // rcx
  __int64 v29; // rax
  __int128 v30; // xmm6
  __int64 v31; // rcx
  __int64 v32; // rbx
  _OWORD *v33; // rsi
  __int64 v34; // rcx
  __int64 v35; // rax
  __int128 v36; // xmm6
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rbx
  _OWORD *v41; // rsi
  __int64 v42; // rcx
  __int64 v43; // rax
  __int128 v44; // xmm6
  __int64 v45; // rcx
  __int64 v46; // rcx
  __int64 v47; // rbx
  _OWORD *v48; // rsi
  __int64 v49; // rcx
  __int64 v50; // rax
  __int128 v51; // xmm6
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // r8
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // r8
  __int128 v59; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v60[16]; // [rsp+30h] [rbp-30h] BYREF
  __int64 v61; // [rsp+40h] [rbp-20h]
  __int128 *v62; // [rsp+48h] [rbp-18h]

  v62 = &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  `Diagnostics::JsonKeyNames::getInstance'::`2'::instance = 0u;
  v1 = operator new(0x48u);
  *v1 = v1;
  v1[1] = v1;
  v1[2] = v1;
  *((_WORD *)v1 + 12) = 257;
  *(_QWORD *)&`Diagnostics::JsonKeyNames::getInstance'::`2'::instance = v1;
  LODWORD(v59) = 1004;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v2,
    v60,
    &Diagnostics::JsonKeys::Is_Scanning,
    &v59);
  LODWORD(v59) = 1005;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v3,
    v60,
    &Diagnostics::JsonKeys::Is_Working,
    &v59);
  LODWORD(v59) = 1006;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v4,
    v60,
    &Diagnostics::JsonKeys::Last_Scan_Error,
    &v59);
  LODWORD(v59) = 1007;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v5,
    v60,
    &Diagnostics::JsonKeys::Attention_Required,
    &v59);
  LODWORD(v59) = 1015;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v6,
    v60,
    &Diagnostics::JsonKeys::Last_Successful_Scan,
    &v59);
  LODWORD(v59) = 1016;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v7,
    v60,
    &Diagnostics::JsonKeys::Alias,
    &v59);
  LODWORD(v59) = 1009;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v8,
    v60,
    &Diagnostics::JsonKeys::Description,
    &v59);
  LODWORD(v59) = 1017;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v9,
    v60,
    &Diagnostics::JsonKeys::ID,
    &v59);
  LODWORD(v59) = 1008;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v10,
    v60,
    &Diagnostics::JsonKeys::UpdateId,
    &v59);
  LODWORD(v59) = 1010;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v11,
    v60,
    &Diagnostics::JsonKeys::Date,
    &v59);
  LODWORD(v59) = 1011;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v12,
    v60,
    &Diagnostics::JsonKeys::LastInstallDate,
    &v59);
  LODWORD(v59) = 1012;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v13,
    v60,
    &Diagnostics::JsonKeys::LastFailDate,
    &v59);
  LODWORD(v59) = 1013;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v14,
    v60,
    &Diagnostics::JsonKeys::InstallTimeUtc,
    &v59);
  LODWORD(v59) = 1014;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *const *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const * const &,int>)(
    v15,
    v60,
    &Diagnostics::JsonKeys::Result,
    &v59);
  LODWORD(v59) = 1018;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v16,
    v60,
    L"01_DeviceName",
    &v59);
  LODWORD(v59) = 1023;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v17,
    v60,
    L"02_OSVersionFull",
    &v59);
  v18 = `Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *(_QWORD *)&v59 = &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *((_QWORD *)&v59 + 1) = 0;
  v19 = operator new(0x48u);
  *((_QWORD *)&v59 + 1) = v19;
  v19[2] = 0;
  *((_QWORD *)v19 + 6) = 0;
  *((_QWORD *)v19 + 7) = 0;
  std::wstring::_Construct<1,wchar_t const *>((_QWORD *)v19 + 4, L"03_LCUVer", 9u);
  *((_DWORD *)v19 + 16) = 1024;
  *(_QWORD *)v19 = v18;
  *((_QWORD *)v19 + 1) = v18;
  *((_QWORD *)v19 + 2) = v18;
  *((_WORD *)v19 + 12) = 0;
  v21 = std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Find_lower_bound<std::wstring>(
          v20,
          v60,
          v19 + 2);
  v22 = *(_OWORD *)v21;
  v61 = *(_QWORD *)(v21 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v23,
                          v61,
                          v19 + 2) )
  {
    if ( v19 )
      std::wstring::~wstring(v19 + 2);
    operator delete(v19, 0x48u);
  }
  else
  {
    if ( *((_QWORD *)&`Diagnostics::JsonKeyNames::getInstance'::`2'::instance + 1) == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v59 = v22;
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned int>>>::_Insert_node(
      &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance,
      &v59,
      v19);
  }
  LODWORD(v59) = 1025;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v24,
    v60,
    L"04_UUSVersion",
    &v59);
  LODWORD(v59) = 1028;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v25,
    v60,
    L"05_CurrentBranch",
    &v59);
  v26 = `Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *(_QWORD *)&v59 = &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *((_QWORD *)&v59 + 1) = 0;
  v27 = operator new(0x48u);
  *((_QWORD *)&v59 + 1) = v27;
  v27[2] = 0;
  *((_QWORD *)v27 + 6) = 0;
  *((_QWORD *)v27 + 7) = 0;
  std::wstring::_Construct<1,wchar_t const *>((_QWORD *)v27 + 4, L"06_IsFlightingEnabled", 0x15u);
  *((_DWORD *)v27 + 16) = 1030;
  *(_QWORD *)v27 = v26;
  *((_QWORD *)v27 + 1) = v26;
  *((_QWORD *)v27 + 2) = v26;
  *((_WORD *)v27 + 12) = 0;
  v29 = std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Find_lower_bound<std::wstring>(
          v28,
          v60,
          v27 + 2);
  v30 = *(_OWORD *)v29;
  v61 = *(_QWORD *)(v29 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v31,
                          v61,
                          v27 + 2) )
  {
    if ( v27 )
      std::wstring::~wstring(v27 + 2);
    operator delete(v27, 0x48u);
  }
  else
  {
    if ( *((_QWORD *)&`Diagnostics::JsonKeyNames::getInstance'::`2'::instance + 1) == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v59 = v30;
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned int>>>::_Insert_node(
      &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance,
      &v59,
      v27);
  }
  v32 = `Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *(_QWORD *)&v59 = &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *((_QWORD *)&v59 + 1) = 0;
  v33 = operator new(0x48u);
  *((_QWORD *)&v59 + 1) = v33;
  v33[2] = 0;
  *((_QWORD *)v33 + 6) = 0;
  *((_QWORD *)v33 + 7) = 0;
  std::wstring::_Construct<1,wchar_t const *>((_QWORD *)v33 + 4, L"07_FlightingBranchName", 0x16u);
  *((_DWORD *)v33 + 16) = 1031;
  *(_QWORD *)v33 = v32;
  *((_QWORD *)v33 + 1) = v32;
  *((_QWORD *)v33 + 2) = v32;
  *((_WORD *)v33 + 12) = 0;
  v35 = std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Find_lower_bound<std::wstring>(
          v34,
          v60,
          v33 + 2);
  v36 = *(_OWORD *)v35;
  v61 = *(_QWORD *)(v35 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v37,
                          v61,
                          v33 + 2) )
  {
    if ( v33 )
      std::wstring::~wstring(v33 + 2);
    operator delete(v33, 0x48u);
  }
  else
  {
    if ( *((_QWORD *)&`Diagnostics::JsonKeyNames::getInstance'::`2'::instance + 1) == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v59 = v36;
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned int>>>::_Insert_node(
      &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance,
      &v59,
      v33);
  }
  LODWORD(v59) = 1032;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v38,
    v60,
    L"08_FlightRing",
    &v59);
  LODWORD(v59) = 1033;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v39,
    v60,
    L"09_FlightContent",
    &v59);
  v40 = `Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *(_QWORD *)&v59 = &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *((_QWORD *)&v59 + 1) = 0;
  v41 = operator new(0x48u);
  *((_QWORD *)&v59 + 1) = v41;
  v41[2] = 0;
  *((_QWORD *)v41 + 6) = 0;
  *((_QWORD *)v41 + 7) = 0;
  std::wstring::_Construct<1,wchar_t const *>((_QWORD *)v41 + 4, L"10_OEMModel", 0xBu);
  *((_DWORD *)v41 + 16) = 1020;
  *(_QWORD *)v41 = v40;
  *((_QWORD *)v41 + 1) = v40;
  *((_QWORD *)v41 + 2) = v40;
  *((_WORD *)v41 + 12) = 0;
  v43 = std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Find_lower_bound<std::wstring>(
          v42,
          v60,
          v41 + 2);
  v44 = *(_OWORD *)v43;
  v61 = *(_QWORD *)(v43 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v45,
                          v61,
                          v41 + 2) )
  {
    if ( v41 )
      std::wstring::~wstring(v41 + 2);
    operator delete(v41, 0x48u);
  }
  else
  {
    if ( *((_QWORD *)&`Diagnostics::JsonKeyNames::getInstance'::`2'::instance + 1) == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v59 = v44;
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned int>>>::_Insert_node(
      &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance,
      &v59,
      v41);
  }
  LODWORD(v59) = 1029;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v46,
    v60,
    L"11_IsVirtualDevice",
    &v59);
  v47 = `Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *(_QWORD *)&v59 = &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
  *((_QWORD *)&v59 + 1) = 0;
  v48 = operator new(0x48u);
  *((_QWORD *)&v59 + 1) = v48;
  v48[2] = 0;
  *((_QWORD *)v48 + 6) = 0;
  *((_QWORD *)v48 + 7) = 0;
  std::wstring::_Construct<1,wchar_t const *>((_QWORD *)v48 + 4, L"12_OSSkuId", 0xAu);
  *((_DWORD *)v48 + 16) = 1022;
  *(_QWORD *)v48 = v47;
  *((_QWORD *)v48 + 1) = v47;
  *((_QWORD *)v48 + 2) = v47;
  *((_WORD *)v48 + 12) = 0;
  v50 = std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Find_lower_bound<std::wstring>(
          v49,
          v60,
          v48 + 2);
  v51 = *(_OWORD *)v50;
  v61 = *(_QWORD *)(v50 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v52,
                          v61,
                          v48 + 2) )
  {
    if ( v48 )
      std::wstring::~wstring(v48 + 2);
    std::_Deallocate<16>(v48, 72);
  }
  else
  {
    if ( *((_QWORD *)&`Diagnostics::JsonKeyNames::getInstance'::`2'::instance + 1) == 0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v59 = v51;
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,unsigned int>>>::_Insert_node(
      &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance,
      &v59,
      v48);
  }
  LODWORD(v59) = 1019;
  ((void (__fastcall *)(__int64, _BYTE *, __int64, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Emplace<wchar_t const (&)[16],int>)(
    v53,
    v60,
    v54,
    &v59);
  LODWORD(v59) = 1026;
  ((void (__fastcall *)(__int64, _BYTE *, const wchar_t *, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::emplace<wchar_t const (&)[19],int>)(
    v55,
    v60,
    L"14_InstallLanguage",
    &v59);
  LODWORD(v59) = 1027;
  ((void (__fastcall *)(__int64, _BYTE *, __int64, __int128 *))std::_Tree<std::_Tmap_traits<std::wstring,unsigned int,std::less<void>,std::allocator<std::pair<std::wstring const,unsigned int>>,0>>::_Emplace<wchar_t const (&)[21],int>)(
    v56,
    v60,
    v57,
    &v59);
  return &`Diagnostics::JsonKeyNames::getInstance'::`2'::instance;
}

```

## disassembly

```asm
0x18001aee8  mov     rax, rsp
0x18001aeeb  mov     [rax+8], rbx
0x18001aeef  mov     [rax+10h], rsi
0x18001aef3  mov     [rax+18h], rdi
0x18001aef7  push    rbp
0x18001aef8  push    r12
0x18001aefa  push    r13
0x18001aefc  push    r14
0x18001aefe  push    r15
0x18001af00  mov     rbp, rsp
0x18001af03  sub     rsp, 60h
0x18001af07  movaps  xmmword ptr [rax-38h], xmm6
0x18001af0b  mov     rax, [rbp+var_18]
0x18001af0f  mov     [rbp+var_18], rax
0x18001af13  lea     r15, ?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001af1a  mov     [rbp+var_18], r15
0x18001af1e  xor     r14d, r14d
0x18001af21  mov     qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A, r14; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001af28  mov     qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A+8, r14; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001af2f  lea     r12d, [r14+48h]
0x18001af33  mov     ecx, r12d; Size
0x18001af36  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001af3b  mov     [rax], rax
0x18001af3e  mov     [rax+8], rax
0x18001af42  mov     [rax+10h], rax
0x18001af46  mov     word ptr [rax+18h], 101h
0x18001af4c  mov     qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A, rax; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001af53  mov     dword ptr [rbp+var_40], 3ECh
0x18001af5a  lea     r9, [rbp+var_40]
0x18001af5e  lea     r8, ?Is_Scanning@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Is_Scanning
0x18001af65  lea     rdx, [rbp+var_30]
0x18001af69  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001af6e  mov     dword ptr [rbp+var_40], 3EDh
0x18001af75  lea     r9, [rbp+var_40]
0x18001af79  lea     r8, ?Is_Working@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Is_Working
0x18001af80  lea     rdx, [rbp+var_30]
0x18001af84  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001af89  mov     dword ptr [rbp+var_40], 3EEh
0x18001af90  lea     r9, [rbp+var_40]
0x18001af94  lea     r8, ?Last_Scan_Error@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Last_Scan_Error
0x18001af9b  lea     rdx, [rbp+var_30]
0x18001af9f  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001afa4  mov     dword ptr [rbp+var_40], 3EFh
0x18001afab  lea     r9, [rbp+var_40]
0x18001afaf  lea     r8, ?Attention_Required@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Attention_Required
0x18001afb6  lea     rdx, [rbp+var_30]
0x18001afba  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001afbf  mov     dword ptr [rbp+var_40], 3F7h
0x18001afc6  lea     r9, [rbp+var_40]
0x18001afca  lea     r8, ?Last_Successful_Scan@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Last_Successful_Scan
0x18001afd1  lea     rdx, [rbp+var_30]
0x18001afd5  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001afda  mov     dword ptr [rbp+var_40], 3F8h
0x18001afe1  lea     r9, [rbp+var_40]
0x18001afe5  lea     r8, ?Alias@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Alias
0x18001afec  lea     rdx, [rbp+var_30]
0x18001aff0  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001aff5  mov     dword ptr [rbp+var_40], 3F1h
0x18001affc  lea     r9, [rbp+var_40]
0x18001b000  lea     r8, ?Description@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Description
0x18001b007  lea     rdx, [rbp+var_30]
0x18001b00b  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b010  mov     dword ptr [rbp+var_40], 3F9h
0x18001b017  lea     r9, [rbp+var_40]
0x18001b01b  lea     r8, ?ID@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::ID
0x18001b022  lea     rdx, [rbp+var_30]
0x18001b026  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b02b  mov     dword ptr [rbp+var_40], 3F0h
0x18001b032  lea     r9, [rbp+var_40]
0x18001b036  lea     r8, ?UpdateId@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::UpdateId
0x18001b03d  lea     rdx, [rbp+var_30]
0x18001b041  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b046  mov     dword ptr [rbp+var_40], 3F2h
0x18001b04d  lea     r9, [rbp+var_40]
0x18001b051  lea     r8, ?Date@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Date
0x18001b058  lea     rdx, [rbp+var_30]
0x18001b05c  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b061  mov     dword ptr [rbp+var_40], 3F3h
0x18001b068  lea     r9, [rbp+var_40]
0x18001b06c  lea     r8, ?LastInstallDate@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::LastInstallDate
0x18001b073  lea     rdx, [rbp+var_30]
0x18001b077  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b07c  mov     dword ptr [rbp+var_40], 3F4h
0x18001b083  lea     r9, [rbp+var_40]
0x18001b087  lea     r8, ?LastFailDate@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::LastFailDate
0x18001b08e  lea     rdx, [rbp+var_30]
0x18001b092  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b097  mov     dword ptr [rbp+var_40], 3F5h
0x18001b09e  lea     r9, [rbp+var_40]
0x18001b0a2  lea     r8, ?InstallTimeUtc@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::InstallTimeUtc
0x18001b0a9  lea     rdx, [rbp+var_30]
0x18001b0ad  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b0b2  mov     dword ptr [rbp+var_40], 3F6h
0x18001b0b9  lea     r9, [rbp+var_40]
0x18001b0bd  lea     r8, ?Result@JsonKeys@Diagnostics@@2QEB_WEB; wchar_t const * const Diagnostics::JsonKeys::Result
0x18001b0c4  lea     rdx, [rbp+var_30]
0x18001b0c8  call    ??$emplace@AEBQEB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEBQEB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const * const &,int>(wchar_t const * const &,int &&)
0x18001b0cd  mov     dword ptr [rbp+var_40], 3FAh
0x18001b0d4  lea     r9, [rbp+var_40]
0x18001b0d8  lea     r8, a01Devicename; "01_DeviceName"
0x18001b0df  lea     rdx, [rbp+var_30]
0x18001b0e3  call    ??$emplace@AEAY0BD@$$CB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const (&)[19],int>(wchar_t const (&)[19],int &&)
0x18001b0e8  mov     dword ptr [rbp+var_40], 3FFh
0x18001b0ef  lea     r9, [rbp+var_40]
0x18001b0f3  lea     r8, a02Osversionful; "02_OSVersionFull"
0x18001b0fa  lea     rdx, [rbp+var_30]
0x18001b0fe  call    ??$emplace@AEAY0BD@$$CB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const (&)[19],int>(wchar_t const (&)[19],int &&)
0x18001b103  mov     rbx, qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001b10a  mov     qword ptr [rbp+var_40], r15
0x18001b10e  mov     qword ptr [rbp+var_40+8], r14
0x18001b112  mov     ecx, r12d; Size
0x18001b115  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b11a  mov     rsi, rax
0x18001b11d  mov     qword ptr [rbp+var_40+8], rax
0x18001b121  lea     rdi, [rax+20h]
0x18001b125  xorps   xmm0, xmm0
0x18001b128  movups  xmmword ptr [rdi], xmm0
0x18001b12b  mov     [rdi+10h], r14
0x18001b12f  mov     [rdi+18h], r14
0x18001b133  lea     r8d, [r14+9]
0x18001b137  lea     rdx, a03Lcuver; "03_LCUVer"
0x18001b13e  mov     rcx, rdi
0x18001b141  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001b146  mov     dword ptr [rdi+20h], 400h
0x18001b14d  mov     [rsi], rbx
0x18001b150  mov     [rsi+8], rbx
0x18001b154  mov     [rsi+10h], rbx
0x18001b158  mov     [rsi+18h], r14w
0x18001b15d  mov     r8, rdi
0x18001b160  lea     rdx, [rbp+var_30]
0x18001b164  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001b169  movups  xmm6, xmmword ptr [rax]
0x18001b16c  movsd   xmm0, qword ptr [rax+10h]
0x18001b171  movsd   [rbp+var_20], xmm0
0x18001b176  mov     r8, rdi
0x18001b179  mov     rdx, [rbp+var_20]
0x18001b17d  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const,std::wstring const &)
0x18001b182  mov     r13, 38E38E38E38E38Eh
0x18001b18c  test    al, al
0x18001b18e  jz      short loc_18001B1AB
0x18001b190  test    rsi, rsi
0x18001b193  jz      short loc_18001B19E
0x18001b195  lea     rcx, [rsi+20h]
0x18001b199  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b19e  mov     rdx, r12; unsigned __int64
0x18001b1a1  mov     rcx, rsi; void *
0x18001b1a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b1a9  jmp     short loc_18001B1CC
0x18001b1ab  cmp     qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A+8, r13; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001b1b2  jz      loc_18001B5C3
0x18001b1b8  movdqu  [rbp+var_40], xmm6
0x18001b1bd  mov     r8, rsi
0x18001b1c0  lea     rdx, [rbp+var_40]
0x18001b1c4  mov     rcx, r15
0x18001b1c7  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,uint>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,uint>,void *> *>,std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const)
0x18001b1cc  mov     dword ptr [rbp+var_40], 401h
0x18001b1d3  lea     r9, [rbp+var_40]
0x18001b1d7  lea     r8, a04Uusversion; "04_UUSVersion"
0x18001b1de  lea     rdx, [rbp+var_30]
0x18001b1e2  call    ??$emplace@AEAY0BD@$$CB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const (&)[19],int>(wchar_t const (&)[19],int &&)
0x18001b1e7  mov     dword ptr [rbp+var_40], 404h
0x18001b1ee  lea     r9, [rbp+var_40]
0x18001b1f2  lea     r8, a05Currentbranc; "05_CurrentBranch"
0x18001b1f9  lea     rdx, [rbp+var_30]
0x18001b1fd  call    ??$emplace@AEAY0BD@$$CB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const (&)[19],int>(wchar_t const (&)[19],int &&)
0x18001b202  mov     rbx, qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001b209  mov     qword ptr [rbp+var_40], r15
0x18001b20d  mov     qword ptr [rbp+var_40+8], r14
0x18001b211  mov     rcx, r12; Size
0x18001b214  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b219  mov     rsi, rax
0x18001b21c  mov     qword ptr [rbp+var_40+8], rax
0x18001b220  lea     rdi, [rax+20h]
0x18001b224  xorps   xmm0, xmm0
0x18001b227  movups  xmmword ptr [rdi], xmm0
0x18001b22a  mov     [rdi+10h], r14
0x18001b22e  mov     [rdi+18h], r14
0x18001b232  mov     r8d, 15h
0x18001b238  lea     rdx, a06Isflightinge; "06_IsFlightingEnabled"
0x18001b23f  mov     rcx, rdi
0x18001b242  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001b247  mov     dword ptr [rdi+20h], 406h
0x18001b24e  mov     [rsi], rbx
0x18001b251  mov     [rsi+8], rbx
0x18001b255  mov     [rsi+10h], rbx
0x18001b259  mov     [rsi+18h], r14w
0x18001b25e  mov     r8, rdi
0x18001b261  lea     rdx, [rbp+var_30]
0x18001b265  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001b26a  movups  xmm6, xmmword ptr [rax]
0x18001b26d  movsd   xmm0, qword ptr [rax+10h]
0x18001b272  movsd   [rbp+var_20], xmm0
0x18001b277  mov     r8, rdi
0x18001b27a  mov     rdx, [rbp+var_20]
0x18001b27e  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const,std::wstring const &)
0x18001b283  test    al, al
0x18001b285  jz      short loc_18001B2A2
0x18001b287  test    rsi, rsi
0x18001b28a  jz      short loc_18001B295
0x18001b28c  lea     rcx, [rsi+20h]
0x18001b290  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b295  mov     rdx, r12; unsigned __int64
0x18001b298  mov     rcx, rsi; void *
0x18001b29b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b2a0  jmp     short loc_18001B2C3
0x18001b2a2  cmp     qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A+8, r13; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001b2a9  jz      loc_18001B5C9
0x18001b2af  movdqu  [rbp+var_40], xmm6
0x18001b2b4  mov     r8, rsi
0x18001b2b7  lea     rdx, [rbp+var_40]
0x18001b2bb  mov     rcx, r15
0x18001b2be  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,uint>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,uint>,void *> *>,std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const)
0x18001b2c3  mov     rbx, qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001b2ca  mov     qword ptr [rbp+var_40], r15
0x18001b2ce  mov     qword ptr [rbp+var_40+8], r14
0x18001b2d2  mov     rcx, r12; Size
0x18001b2d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b2da  mov     rsi, rax
0x18001b2dd  mov     qword ptr [rbp+var_40+8], rax
0x18001b2e1  lea     rdi, [rax+20h]
0x18001b2e5  xorps   xmm0, xmm0
0x18001b2e8  movups  xmmword ptr [rdi], xmm0
0x18001b2eb  mov     [rdi+10h], r14
0x18001b2ef  mov     [rdi+18h], r14
0x18001b2f3  mov     r8d, 16h
0x18001b2f9  lea     rdx, a07Flightingbra; "07_FlightingBranchName"
0x18001b300  mov     rcx, rdi
0x18001b303  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001b308  mov     dword ptr [rdi+20h], 407h
0x18001b30f  mov     [rsi], rbx
0x18001b312  mov     [rsi+8], rbx
0x18001b316  mov     [rsi+10h], rbx
0x18001b31a  mov     [rsi+18h], r14w
0x18001b31f  mov     r8, rdi
0x18001b322  lea     rdx, [rbp+var_30]
0x18001b326  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001b32b  movups  xmm6, xmmword ptr [rax]
0x18001b32e  movsd   xmm0, qword ptr [rax+10h]
0x18001b333  movsd   [rbp+var_20], xmm0
0x18001b338  mov     r8, rdi
0x18001b33b  mov     rdx, [rbp+var_20]
0x18001b33f  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const,std::wstring const &)
0x18001b344  test    al, al
0x18001b346  jz      short loc_18001B363
0x18001b348  test    rsi, rsi
0x18001b34b  jz      short loc_18001B356
0x18001b34d  lea     rcx, [rsi+20h]
0x18001b351  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b356  mov     rdx, r12; unsigned __int64
0x18001b359  mov     rcx, rsi; void *
0x18001b35c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b361  jmp     short loc_18001B384
0x18001b363  cmp     qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A+8, r13; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001b36a  jz      loc_18001B5CF
0x18001b370  movdqu  [rbp+var_40], xmm6
0x18001b375  mov     r8, rsi
0x18001b378  lea     rdx, [rbp+var_40]
0x18001b37c  mov     rcx, r15
0x18001b37f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,uint>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,uint>,void *> *>,std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const)
0x18001b384  mov     dword ptr [rbp+var_40], 408h
0x18001b38b  lea     r9, [rbp+var_40]
0x18001b38f  lea     r8, a08Flightring; "08_FlightRing"
0x18001b396  lea     rdx, [rbp+var_30]
0x18001b39a  call    ??$emplace@AEAY0BD@$$CB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const (&)[19],int>(wchar_t const (&)[19],int &&)
0x18001b39f  mov     dword ptr [rbp+var_40], 409h
0x18001b3a6  lea     r9, [rbp+var_40]
0x18001b3aa  lea     r8, a09Flightconten; "09_FlightContent"
0x18001b3b1  lea     rdx, [rbp+var_30]
0x18001b3b5  call    ??$emplace@AEAY0BD@$$CB_WH@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@std@@@std@@@std@@_N@1@AEAY0BD@$$CB_W$$QEAH@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::emplace<wchar_t const (&)[19],int>(wchar_t const (&)[19],int &&)
0x18001b3ba  mov     rbx, qword ptr cs:?instance@?1??getInstance@JsonKeyNames@Diagnostics@@CAAEAV23@XZ@4V23@A; Diagnostics::JsonKeyNames `Diagnostics::JsonKeyNames::getInstance(void)'::`2'::instance
0x18001b3c1  mov     qword ptr [rbp+var_40], r15
0x18001b3c5  mov     qword ptr [rbp+var_40+8], r14
0x18001b3c9  mov     rcx, r12; Size
0x18001b3cc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b3d1  mov     rsi, rax
0x18001b3d4  mov     qword ptr [rbp+var_40+8], rax
0x18001b3d8  lea     rdi, [rax+20h]
0x18001b3dc  xorps   xmm0, xmm0
0x18001b3df  movups  xmmword ptr [rdi], xmm0
0x18001b3e2  mov     [rdi+10h], r14
0x18001b3e6  mov     [rdi+18h], r14
0x18001b3ea  mov     r8d, 0Bh
0x18001b3f0  lea     rdx, a10Oemmodel; "10_OEMModel"
0x18001b3f7  mov     rcx, rdi
0x18001b3fa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18001b3ff  mov     dword ptr [rdi+20h], 3FCh
0x18001b406  mov     [rsi], rbx
0x18001b409  mov     [rsi+8], rbx
0x18001b40d  mov     [rsi+10h], rbx
0x18001b411  mov     [rsi+18h], r14w
0x18001b416  mov     r8, rdi
0x18001b419  lea     rdx, [rbp+var_30]
0x18001b41d  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001b422  movups  xmm6, xmmword ptr [rax]
0x18001b425  movsd   xmm0, qword ptr [rax+10h]
0x18001b42a  movsd   [rbp+var_20], xmm0
0x18001b42f  mov     r8, rdi
0x18001b432  mov     rdx, [rbp+var_20]
0x18001b436  call    ??$_Lower_bound_duplicate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@IU?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@I@std@@PEAX@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,uint,std::less<void>,std::allocator<std::pair<std::wstring const,uint>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,uint>,void *> * const,std::wstring const &)
0x18001b43b  test    al, al
  ... truncated ...
```
