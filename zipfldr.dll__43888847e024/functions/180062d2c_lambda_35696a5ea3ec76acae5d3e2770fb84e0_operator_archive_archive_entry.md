# _lambda_35696a5ea3ec76acae5d3e2770fb84e0_::operator()(archive *,archive_entry *)

- ea: `0x180062d2c`
- end: `0x180063e5d`
- name: `??R_lambda_35696a5ea3ec76acae5d3e2770fb84e0_@@QEBA@PEAUarchive@@PEAUarchive_entry@@@Z`
- size: `4401`
- prototype: `char __fastcall(char **, void *, struct archive_entry *)`
- caller_count: `1`
- callee_count: `40`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180061088`

## callees

- `0x1800207f8`
- `0x180020cbc`
- `0x180020cdc`
- `0x180024a7c`
- `0x18002abd0`
- `0x18002ec00`
- `0x18002ed2c`
- `0x180030a3c`
- `0x180033404`
- `0x1800354bc`
- `0x1800354e0`
- `0x180036f50`
- `0x180037958`
- `0x180038d60`
- `0x18003edd4`
- `0x180048d3c`
- `0x180048dac`
- `0x180052e7c`
- `0x180055f7c`
- `0x1800561ec`
- `0x180056208`
- `0x180057fbc`
- `0x1800581dc`
- `0x1800583ec`
- `0x18005de08`
- `0x18005fb64`
- `0x1800600d4`
- `0x180061f40`
- `0x180061fbc`
- `0x180062ad8`
- `0x180062d2c`
- `0x180064734`
- `0x180064a5c`
- `0x180064ae4`
- `0x180064b4c`
- `0x180064cec`
- `0x180067a40`
- `0x180068740`
- `0x180068ad4`
- `0x180071010`

## import_xrefs

- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180063cfb`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x180063cfb`
- `archiveint!archive_entry_hardlink_w` at `0x180063705`
- `archiveint!archive_entry_hardlink_w` at `0x180063705`
- `archiveint!archive_entry_size` at `0x180062fab`
- `archiveint!archive_entry_size` at `0x180062fc3`
- `archiveint!archive_entry_size` at `0x1800639bb`
- `archiveint!archive_entry_size` at `0x180062fab`
- `archiveint!archive_entry_size` at `0x180062fc3`
- `archiveint!archive_entry_size` at `0x1800639bb`
- `archiveint!archive_entry_pathname_w` at `0x180062d6e`
- `archiveint!archive_entry_pathname_w` at `0x180062d6e`
- `archiveint!archive_entry_symlink_w` at `0x1800636ef`
- `archiveint!archive_entry_symlink_w` at `0x1800636ef`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006327c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006327c`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18006378c`
- `api-ms-win-core-path-l1-1-0!PathCchSkipRoot` at `0x18006378c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006361b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18006361b`

## pseudocode

```c
char __fastcall _lambda_35696a5ea3ec76acae5d3e2770fb84e0_::operator()(char **a1, void *a2, struct archive_entry *a3)
{
  const WCHAR *v5; // rax
  char v6; // r15
  __int64 v7; // r8
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rsi
  unsigned __int64 v16; // r14
  __int64 v17; // rbx
  __int64 not_ch_2; // rax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r14
  char v22; // si
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 v25; // rdx
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // rdx
  char *v28; // rcx
  unsigned __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  char *v35; // r12
  char *v36; // r15
  char *v37; // rbx
  char *v38; // r13
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rax
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rdx
  char *v47; // rax
  __int64 v48; // r8
  __int64 v49; // r8
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  const WCHAR *v53; // rax
  const struct _GUID *v54; // rdx
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rdx
  _QWORD *v60; // rax
  HRESULT v61; // eax
  __int64 v62; // rdx
  __int64 v63; // r8
  const WCHAR *v64; // rax
  const struct _GUID *v65; // rdx
  int v66; // eax
  __int64 v67; // rdx
  __int64 v68; // r8
  char v69; // cl
  const WCHAR *v70; // rax
  const struct _GUID *v71; // rdx
  int v72; // eax
  __int64 v73; // rdx
  __int64 v74; // r8
  char v75; // bl
  unsigned __int8 Response; // r15
  __int64 v77; // rbx
  int v78; // eax
  unsigned __int8 v79; // al
  __int64 v80; // r8
  int v81; // ecx
  int v82; // ecx
  __int64 v83; // rdx
  __int64 v84; // r8
  char v85; // r15
  const WCHAR *v86; // rax
  DWORD FileAttributesW; // eax
  bool v88; // bl
  __int64 v89; // rdx
  __int64 v90; // r8
  unsigned __int8 v91; // cl
  char v92; // cl
  __int128 v93; // xmm0
  void *v94; // rcx
  char v95; // cl
  __int128 v96; // xmm0
  const WCHAR *v97; // rax
  __int64 v98; // rdx
  __int64 v99; // r8
  WCHAR v100; // bx
  const WCHAR *v101; // rax
  const struct _GUID *v102; // rdx
  int v103; // eax
  const WCHAR *v104; // rax
  const struct _GUID *v105; // rdx
  int v106; // eax
  int v107; // eax
  __int64 v108; // r8
  char *v109; // rcx
  __int64 v110; // rdx
  int v111; // eax
  char *v113; // rbx
  __int64 v114; // r8
  __int64 v115; // rbx
  __int64 v116; // rdx
  __int64 v117; // r8
  _WORD *v118; // rax
  __int64 v119; // r8
  _WORD *i; // rdx
  __int64 v121; // rax
  int v122; // ebx
  const char *v123; // r9
  unsigned int v124; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+20h] [rbp-E0h]
  char v128; // [rsp+50h] [rbp-B0h]
  char *v129; // [rsp+58h] [rbp-A8h]
  char *v130; // [rsp+60h] [rbp-A0h]
  __int128 v132; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v133[6]; // [rsp+80h] [rbp-80h] BYREF
  char v134; // [rsp+B0h] [rbp-50h]
  PCWSTR ppszRootEnd[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v136; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v137; // [rsp+D8h] [rbp-28h]
  _DWORD v138[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v139; // [rsp+FCh] [rbp-4h]
  int v140; // [rsp+114h] [rbp+14h]
  void *v141; // [rsp+118h] [rbp+18h]
  int v142; // [rsp+128h] [rbp+28h]
  __int64 v143; // [rsp+130h] [rbp+30h]
  __int64 v144; // [rsp+140h] [rbp+40h]
  _QWORD v145[3]; // [rsp+150h] [rbp+50h] BYREF
  void *v146; // [rsp+168h] [rbp+68h] BYREF
  void *v147; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v148; // [rsp+178h] [rbp+78h] BYREF
  int v149; // [rsp+180h] [rbp+80h] BYREF
  char v150; // [rsp+184h] [rbp+84h]
  __int128 v151; // [rsp+188h] [rbp+88h] BYREF
  __m128i si128; // [rsp+198h] [rbp+98h]
  __int64 v153; // [rsp+1A8h] [rbp+A8h] BYREF
  int v154; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v155; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v156[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v157[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v158; // [rsp+1E0h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v148 = a2;
  v5 = (const WCHAR *)archive_entry_pathname_w(a3);
  v6 = 0;
  if ( !v5 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x7B0,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      0);
  ppszRootEnd[0] = v5;
  v7 = -1;
  do
    ++v7;
  while ( v5[v7] );
  ppszRootEnd[1] = (PCWSTR)v7;
  v128 = **a1;
  if ( v128 )
  {
    v8 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[1] + 8, a1[1], v7);
    *(_QWORD *)&v132 = v9;
    *((_QWORD *)&v132 + 1) = v10;
    v133[0] = v8;
    v133[1] = *(_QWORD *)(v11 + 24);
    *(_OWORD *)ppszRootEnd = *(_OWORD *)check_rename(v156, a2, v133, &v132);
    **a1 = 0;
  }
  LOBYTE(v7) = 0;
  std::filesystem::_Convert_Source_to_wide<std::basic_string_view<unsigned short>,std::filesystem::_Normal_conversion>(
    &v136,
    ppszRootEnd,
    v7);
  std::filesystem::path::lexically_normal(&v136, v157);
  std::wstring::_Tidy_deallocate(&v136);
  v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v157, v12, v13);
  v15 = v14;
  v16 = v158;
  if ( !v158
    || ((v17 = v14 + 2 * v158, not_ch_2 = _std_find_not_ch_2(v14, v17, 92), not_ch_2 == v17)
      ? (v19 = -1)
      : (v19 = (not_ch_2 - v15) >> 1),
        v16 < v19) )
  {
    v19 = v16;
  }
  v20 = v15 + 2 * v19;
  v21 = v16 - v19;
  v22 = 1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v20, v21, L".", 1) )
    goto LABEL_69;
  std::wstring::_Append<unsigned short>(a1[2], v20, v21);
  v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[2], *(_QWORD *)a1[3], v23);
  replace_invalid_path_chars((WCHAR *)(v24 + 2 * v25), v26, 0);
  v27 = *(_QWORD *)a1[3];
  v28 = a1[2];
  v29 = *((_QWORD *)v28 + 2);
  if ( v29 < v27 )
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  v30 = v29 - v27;
  v31 = -1;
  if ( v30 != -1 )
    v31 = v30;
  v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28, v27, v31);
  std::wstring::_Append<unsigned short>(a1[4], v32 + 2 * v33, v34);
  v35 = a1[5];
  v36 = a1[4];
  v129 = v36;
  v37 = a1[3];
  v130 = v37;
  v38 = a1[2];
  v133[2] = v38;
  v133[3] = v37;
  v133[4] = v36;
  v133[5] = v35;
  v134 = 1;
  v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38, v39, v40);
  v43 = *((_QWORD *)v38 + 2);
  if ( *(_WORD *)(v41 + 2 * v43 - 2) == 47 || *(_WORD *)(v41 + 2 * v43 - 2) == 92 )
  {
    v44 = v43 - 1;
    *((_QWORD *)v38 + 2) = v44;
    v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v38, v44, v42);
    *(_WORD *)(v45 + 2 * v46) = 0;
  }
  v47 = a1[6];
  v48 = *((_QWORD *)v47 + 1);
  if ( *(_QWORD *)v47 == v48
    || (std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,_lambda_15cb89a6428307ca39b0c99fab0e8cdb_>(
          v156,
          *(_QWORD *)v47,
          v48,
          a1[2]),
        v156[0] == *((void **)a1[6] + 1)) )
  {
    *(_QWORD *)a1[7] += archive_entry_size(a3);
    if ( *(_QWORD *)a1[7] >= *(_QWORD *)a1[8] )
    {
      v154 = 0;
      v50 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)a1[9] + 104LL))(*(_QWORD *)a1[9], &v154);
      if ( v50 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7F5,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v50,
          ppv);
      if ( v154 == 3 )
      {
        *(_DWORD *)a1[10] = -2147023673;
        std::wstring::resize(v38, *(_QWORD *)v37);
        std::wstring::resize(v36, *(_QWORD *)v35);
LABEL_192:
        std::wstring::_Tidy_deallocate(v157);
        return v22;
      }
      if ( v154 != 1 )
      {
        v124 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7FE,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)v124,
          ppv);
      }
      v156[0] = 0;
      v53 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[4], v51, v52);
      if ( (int)ShellItemFromFileSystemPath(v53, v54, v156, 0) >= 0 )
      {
        v55 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *))(**(_QWORD **)a1[9] + 64LL))(
                *(_QWORD *)a1[9],
                0,
                0,
                v156[0]);
        if ( v55 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x806,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v55,
            ppv);
        *(_QWORD *)a1[8] = *(_QWORD *)a1[7] + 1000000LL;
      }
      if ( v156[0] )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v156);
    }
    v149 = 0;
    v150 = 0;
    v151 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v151) = 0;
    v145[0] = *(_QWORD *)a1[9];
    v145[1] = a1[11];
    v145[2] = a1[12];
    *(_QWORD *)&v132 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[13], a1[13], v49);
    *((_QWORD *)&v132 + 1) = *(_QWORD *)(v56 + 16);
    v57 = ExtractArchiveEntry(
            (__int64)&v136,
            (int)v148,
            (__int64)a3,
            (__int64)a1[2],
            &v132,
            *a1[14],
            (__int64)a1[15],
            a1[16],
            (__int64)v145);
    v149 = *(_DWORD *)v57;
    v150 = *(_BYTE *)(v57 + 4);
    std::wstring::operator=(&v151, v57 + 8);
    std::wstring::_Tidy_deallocate((char *)&v136 + 8);
    if ( v149 >= 0 )
    {
      *(_QWORD *)&v132 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[2], a1[2], v58);
      *((_QWORD *)&v132 + 1) = *(_QWORD *)(v59 + 16);
      v60 = (_QWORD *)split_filename((__int64)&v136, (__int64 *)&v132);
      std::wstring::_Assign<unsigned short>(a1[13], *v60, v60[1]);
      ++*(_QWORD *)a1[12];
LABEL_148:
      std::wstring::_Tidy_deallocate(&v151);
      goto LABEL_149;
    }
    if ( v150 == 1 )
    {
      *(_DWORD *)a1[10] = -2147023673;
      std::wstring::_Tidy_deallocate(&v151);
      std::wstring::resize(v38, *(_QWORD *)v37);
      std::wstring::resize(v36, *(_QWORD *)v35);
      goto LABEL_192;
    }
    std::wstring::resize(a1[4], si128.m128i_i64[0] + *(_QWORD *)a1[5] - *(_QWORD *)a1[3]);
    v148 = 0;
    v61 = CoCreateInstance(&CLSID_TransferConfirmationUI, 0, 3u, &GUID_14cc750c_7b0b_43dc_910e_b687f84e7c3b, &v148);
    if ( v61 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x831,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v61,
        ppva);
    v147 = 0;
    v64 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[4], v62, v63);
    v66 = ShellItemFromFileSystemPath(v64, v65, &v147, 0);
    if ( v66 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x83B,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v66,
        ppva);
      v69 = v150;
      if ( v150 == 4 )
        v69 = 2;
      v150 = v69;
    }
    v146 = 0;
    v70 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v151, v67, v68);
    v72 = ShellItemFromFileSystemPath(v70, v71, &v146, 0);
    LODWORD(v153) = v72;
    v75 = v150;
    if ( v72 < 0 )
    {
      if ( v150 != 4 )
        goto LABEL_70;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x84E,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v72,
        ppva);
      v75 = 2;
      v150 = 2;
      v149 = v153;
    }
    if ( v75 == 4 )
    {
      Response = UserConfirmations::GetResponse(a1[17], &v149);
      if ( !Response )
      {
        v136 = 0;
        v137 = 0;
        *(_QWORD *)&v136 = *(_QWORD *)a1[18];
        *((_QWORD *)&v136 + 1) = 0x200000007LL;
        DWORD2(v137) = 0;
        v133[0] = v146;
        *(_QWORD *)&v132 = v147;
        winrt::make_self<ArchiveConflictItems,IShellItem *,IShellItem *>(&v155, &v132, v133);
        v153 = 0;
        ppszRootEnd[0] = 0;
        v77 = v155;
        v78 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64, __int64 *))(*(_QWORD *)v148 + 32LL))(
                v148,
                &v136,
                v155,
                &v153);
        if ( v78 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x869,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v78,
            (int)ppszRootEnd);
        v79 = UserConfirmations::TranslateResponse(v153, ppszRootEnd[0]);
        Response = v79;
        if ( HIDWORD(v153) )
        {
          LOBYTE(v80) = v79;
          UserConfirmations::SetResponse(a1[17], &v149, v80);
        }
        if ( ppszRootEnd[0] )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppszRootEnd);
        if ( v77 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v155);
      }
      v81 = Response;
      v6 = 2;
      v82 = v81 - 2;
      if ( v82 )
      {
        if ( v82 == 1 )
        {
          *(_DWORD *)a1[10] = -2147023673;
          if ( v146 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
          if ( v147 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
          if ( v148 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
LABEL_61:
          std::wstring::_Tidy_deallocate(&v151);
          std::wstring::resize(v38, *(_QWORD *)v130);
          std::wstring::resize(v129, *(_QWORD *)v35);
          goto LABEL_192;
        }
        goto LABEL_140;
      }
      *a1[14] |= 1u;
      **a1 = v128;
      if ( v146 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
      if ( v147 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
      if ( v148 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
      std::wstring::_Tidy_deallocate(&v151);
      std::wstring::resize(v38, *(_QWORD *)v130);
      std::wstring::resize(v129, *(_QWORD *)v35);
LABEL_69:
      v22 = v6;
      goto LABEL_192;
    }
LABEL_70:
    if ( v75 == 3 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x887,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v149,
        ppva);
      *(_DWORD *)a1[10] = v149;
      if ( v146 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
      if ( v147 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
      if ( v148 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
      goto LABEL_191;
    }
    if ( (unsigned __int8)(v75 - 6) <= 2u )
    {
      v133[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v151, v73, v74) + 2LL * *(_QWORD *)a1[3];
      if ( v75 == 6 )
      {
        ArchiveFolderTelemetry::ExtractArchive::EncounteredReparsePoint((ArchiveFolderTelemetry::ExtractArchive *)a1[19]);
        v115 = 10571;
      }
      else if ( v75 == 7 )
      {
        ArchiveFolderTelemetry::ExtractArchive::EncounteredRelativePath((ArchiveFolderTelemetry::ExtractArchive *)a1[19]);
        v115 = 10572;
      }
      else
      {
        v113 = a1[19];
        *(_QWORD *)&v132 = ArchiveEntryTypeLoggingString(a3);
        ArchiveFolderTelemetry::ExtractArchive::EncounteredUnsupportedType<unsigned short const *>(v113, &v132);
        v115 = 10573;
      }
      LOBYTE(v114) = 0;
      std::filesystem::_Convert_Source_to_wide<std::basic_string_view<unsigned short>,std::filesystem::_Normal_conversion>(
        &v136,
        ppszRootEnd,
        v114);
      v118 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v136, v116, v117);
      for ( i = &v118[v137]; v118 != i; ++v118 )
      {
        if ( *v118 == 47 )
          *v118 = 92;
      }
      v121 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v136, i, v119);
      v122 = ShellMessageBoxW(&_ImageBase, *(HWND *)a1[18], (LPCWSTR)v115, (LPCWSTR)0x2941, 0x31u, v121, v133[0]);
      std::wstring::_Tidy_deallocate(&v136);
      if ( !v122 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x8B2,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          v123);
      if ( v122 == 1 )
        goto LABEL_141;
      *(_DWORD *)a1[10] = -2147023673;
      if ( v146 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
      if ( v147 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
      if ( v148 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
LABEL_191:
      std::wstring::_Tidy_deallocate(&v151);
      std::wstring::resize(v38, *(_QWORD *)v130);
      std::wstring::resize(v36, *(_QWORD *)v35);
      goto LABEL_192;
    }
    v85 = UserConfirmations::GetResponse(a1[17], &v149);
    if ( v85 )
    {
LABEL_134:
      if ( v85 )
      {
        if ( v85 != 2 )
        {
          if ( v85 == 3 )
          {
            *(_DWORD *)a1[10] = -2147023673;
            if ( v146 )
              winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
            if ( v147 )
              winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
            if ( v148 )
              winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
            goto LABEL_61;
          }
          if ( v75 == 5 )
          {
            v109 = a1[6];
            v110 = *((_QWORD *)v109 + 1);
            if ( v110 == *((_QWORD *)v109 + 2) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v109, v110, &v151);
            }
            else
            {
              *(_OWORD *)v110 = 0;
              *(_QWORD *)(v110 + 16) = 0;
              *(_QWORD *)(v110 + 24) = 0;
              *(_OWORD *)v110 = v151;
              *(__m128i *)(v110 + 16) = si128;
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v151) = 0;
              *((_QWORD *)v109 + 1) += 32LL;
            }
          }
          goto LABEL_140;
        }
        if ( v75 != 9 )
        {
LABEL_140:
          v36 = v129;
LABEL_141:
          --*(_QWORD *)a1[11];
          *((_QWORD *)a1[11] + 1) -= archive_entry_size(a3);
          if ( v146 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
          if ( v147 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
          if ( v148 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
          v37 = v130;
          goto LABEL_148;
        }
        *a1[14] |= 4u;
        **a1 = v128;
        if ( v146 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
        if ( v147 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
        if ( v148 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
      }
      else
      {
        **a1 = v128;
        if ( v146 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
        if ( v147 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
        if ( v148 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v148);
      }
      std::wstring::_Tidy_deallocate(&v151);
      std::wstring::resize(v38, *(_QWORD *)v130);
      std::wstring::resize(v129, *(_QWORD *)v35);
      v22 = 2;
      goto LABEL_192;
    }
    v86 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v151, v83, v84);
    FileAttributesW = GetFileAttributesW(v86);
    if ( FileAttributesW == -1 )
    {
      v88 = v128;
    }
    else
    {
      v88 = (FileAttributesW & 0x10) != 0;
      v85 = 1;
    }
    LODWORD(ppszRootEnd[0]) = (ArchiveEntryToWindowsAttributes(a3) & 0x10) != 0;
    memset_0(v138, 0, 0x60u);
    v144 = *(_QWORD *)a1[18];
    v138[0] = 40;
    v89 = 2;
    v138[1] = 2;
    v90 = LODWORD(ppszRootEnd[0]);
    v91 = (unsigned __int8)ppszRootEnd[0];
    if ( v85 )
      v91 = v88;
    v138[2] = v91;
    v140 = 0;
    v141 = v147;
    switch ( v150 )
    {
      case 2:
        v89 = (unsigned int)v149;
        if ( v149 == -2147024864 )
        {
          v94 = v141;
          if ( v146 )
            v94 = v146;
          v141 = v94;
          v142 = -2144927704;
          v95 = (char)ppszRootEnd[0];
          if ( v85 )
            v95 = v88;
          if ( v95 )
            v96 = STCONFIRM_IN_USE_STORAGE;
          else
            v96 = STCONFIRM_IN_USE_STREAM;
          goto LABEL_114;
        }
        if ( v149 != -2147024784 )
        {
          v103 = -2147024882;
          if ( v149 == -2147024882 )
          {
            v96 = STCONFIRM_OUT_OF_MEMORY;
            goto LABEL_113;
          }
          goto LABEL_111;
        }
        ppszRootEnd[0] = 0;
        v97 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[20], 2147942512LL, v90);
        if ( PathCchSkipRoot(v97, ppszRootEnd) >= 0 )
        {
          v100 = *ppszRootEnd[0];
          *ppszRootEnd[0] = 0;
          if ( v146 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v146);
          v101 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[20], v98, v99);
          if ( (int)ShellItemFromFileSystemPath(v101, v102, &v146, 0) >= 0 )
          {
            v141 = v146;
            v142 = v149;
            v139 = STCONFIRM_UNEXPECTED_ERROR;
            *ppszRootEnd[0] = v100;
            goto LABEL_115;
          }
          *ppszRootEnd[0] = v100;
        }
        break;
      case 5:
LABEL_112:
        v96 = STCONFIRM_UNEXPECTED_ERROR;
        v103 = v149;
LABEL_113:
        v142 = v103;
LABEL_114:
        v139 = v96;
        goto LABEL_115;
      case 9:
        v142 = v149;
        v92 = (char)ppszRootEnd[0];
        if ( v85 )
          v92 = v88;
        if ( v92 )
          v93 = STCONFIRM_ABSOLUTE_LINK_STORAGE;
        else
          v93 = STCONFIRM_ABSOLUTE_LINK_STREAM;
        v139 = v93;
        v143 = archive_entry_symlink_w(a3);
        if ( !v143 )
          v143 = archive_entry_hardlink_w(a3);
LABEL_115:
        if ( !v141 )
        {
          if ( v147 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v147);
          v104 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[1] + 8, v89, v90);
          v106 = ShellItemFromFileSystemPath(v104, v105, &v147, 0);
          if ( v106 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x930,
              (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
              (const char *)(unsigned int)v106,
              ppva);
          v141 = v147;
        }
        LODWORD(v155) = 0;
        LODWORD(v153) = 0;
        v107 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *, __int64 *, __int64 *))(*(_QWORD *)v148 + 24LL))(
                 v148,
                 v138,
                 &v155,
                 &v153);
        if ( v107 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x936,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v107,
            ppva);
        if ( !(_DWORD)v155 )
        {
          v85 = 2;
          goto LABEL_131;
        }
        if ( (_DWORD)v155 != 1 )
        {
          if ( (_DWORD)v155 == 2 )
          {
            v85 = 0;
            goto LABEL_131;
          }
          if ( (_DWORD)v155 == 4 )
          {
            v85 = 3;
LABEL_131:
            if ( (_DWORD)v153 )
            {
              LOBYTE(v108) = v85;
              UserConfirmations::SetResponse(a1[17], &v149, v108);
            }
            v75 = v150;
            goto LABEL_134;
          }
        }
        v85 = 1;
        goto LABEL_131;
    }
    LODWORD(v89) = v149;
LABEL_111:
    ArchiveFolderTelemetry::ExtractArchive::EncounteredError((ArchiveFolderTelemetry::ExtractArchive *)a1[19], v89);
    goto LABEL_112;
  }
  --*(_QWORD *)a1[11];
  *((_QWORD *)a1[11] + 1) -= archive_entry_size(a3);
LABEL_149:
  ppvb = (LPVOID *)*((_QWORD *)a1[11] + 1);
  v111 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID *, _QWORD))(**(_QWORD **)a1[9] + 56LL))(
           *(_QWORD *)a1[9],
           *((_QWORD *)a1[12] + 1),
           ppvb,
           *((_QWORD *)a1[12] + 1));
  if ( v111 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x974,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v111,
      (int)ppvb);
  *a1[14] = 0;
  std::wstring::resize(v38, *(_QWORD *)v37);
  std::wstring::resize(v36, *(_QWORD *)v35);
  std::wstring::_Tidy_deallocate(v157);
  return 0;
}

```

## disassembly

```asm
0x180062d2c  mov     [rsp-8+arg_18], rbx
0x180062d31  push    rbp
0x180062d32  push    rsi
0x180062d33  push    rdi
0x180062d34  push    r12
0x180062d36  push    r13
0x180062d38  push    r14
0x180062d3a  push    r15
0x180062d3c  lea     rbp, [rsp-100h]
0x180062d44  sub     rsp, 200h
0x180062d4b  mov     rax, cs:__security_cookie
0x180062d52  xor     rax, rsp
0x180062d55  mov     [rbp+130h+var_40], rax
0x180062d5c  mov     [rsp+230h+var_1C8], r8
0x180062d61  mov     rbx, rdx
0x180062d64  mov     [rbp+130h+var_B8], rdx
0x180062d68  mov     rdi, rcx
0x180062d6b  mov     rcx, r8
0x180062d6e  call    cs:__imp_archive_entry_pathname_w
0x180062d74  mov     r9, rax; char *
0x180062d77  mov     rcx, [rbp+138h]; this
0x180062d7e  xor     r15d, r15d
0x180062d81  test    rax, rax
0x180062d84  jz      loc_180063DAC
0x180062d8a  mov     [rbp+130h+ppszRootEnd], rax
0x180062d8e  or      r12, 0FFFFFFFFFFFFFFFFh
0x180062d92  mov     r8, r12
0x180062d95  inc     r8
0x180062d98  cmp     [rax+r8*2], r15w
0x180062d9d  jnz     short loc_180062D95
0x180062d9f  mov     [rbp+130h+ppszRootEnd+8], r8
0x180062da3  mov     rax, [rdi]
0x180062da6  mov     al, [rax]
0x180062da8  mov     [rsp+230h+var_1E0], al
0x180062dac  test    al, al
0x180062dae  jz      short loc_180062DF9
0x180062db0  mov     rdx, [rdi+8]
0x180062db4  lea     rcx, [rdx+8]
0x180062db8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062dbd  mov     [rsp+230h+var_1C0], r9
0x180062dc2  mov     [rsp+230h+var_1B8], r8
0x180062dc7  mov     [rbp+130h+var_1B0], rax
0x180062dcb  mov     rax, [rdx+18h]
0x180062dcf  mov     [rbp+130h+var_1A8], rax
0x180062dd3  lea     r9, [rsp+230h+var_1C0]
0x180062dd8  lea     r8, [rbp+130h+var_1B0]
0x180062ddc  mov     rdx, rbx
0x180062ddf  lea     rcx, [rbp+130h+var_70]
0x180062de6  call    ?check_rename@@YA?AV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAUarchive@@V12@1@Z; check_rename(archive *,std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180062deb  movups  xmm0, xmmword ptr [rax]
0x180062dee  movdqu  xmmword ptr [rbp+130h+ppszRootEnd], xmm0
0x180062df3  mov     rax, [rdi]
0x180062df6  mov     [rax], r15b
0x180062df9  mov     r8b, r15b
0x180062dfc  lea     rdx, [rbp+130h+ppszRootEnd]
0x180062e00  lea     rcx, [rbp+130h+var_168]
0x180062e04  call    ??$_Convert_Source_to_wide@V?$basic_string_view@GU?$char_traits@G@std@@@std@@U_Normal_conversion@filesystem@2@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEBV?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_Source_to_wide<std::basic_string_view<ushort>,std::filesystem::_Normal_conversion>(std::basic_string_view<ushort> const &,std::filesystem::_Normal_conversion)
0x180062e09  nop
0x180062e0a  lea     rdx, [rbp+130h+var_60]
0x180062e11  lea     rcx, [rbp+130h+var_168]
0x180062e15  call    ?lexically_normal@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::lexically_normal(void)
0x180062e1a  nop
0x180062e1b  lea     rcx, [rbp+130h+var_168]
0x180062e1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180062e24  lea     rcx, [rbp+130h+var_60]
0x180062e2b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062e30  mov     rsi, rax
0x180062e33  mov     r14, [rbp+130h+var_50]
0x180062e3a  test    r14, r14
0x180062e3d  jz      short loc_180062E69
0x180062e3f  lea     rbx, [rax+r14*2]
0x180062e43  mov     r8d, 5Ch ; '\'
0x180062e49  mov     rdx, rbx
0x180062e4c  mov     rcx, rax
0x180062e4f  call    __std_find_not_ch_2
0x180062e54  cmp     rax, rbx
0x180062e57  jz      short loc_180062E61
0x180062e59  sub     rax, rsi
0x180062e5c  sar     rax, 1
0x180062e5f  jmp     short loc_180062E64
0x180062e61  mov     rax, r12
0x180062e64  cmp     r14, rax
0x180062e67  jnb     short loc_180062E6C
0x180062e69  mov     rax, r14
0x180062e6c  lea     rbx, [rsi+rax*2]
0x180062e70  sub     r14, rax
0x180062e73  mov     esi, 1
0x180062e78  mov     r9d, esi
0x180062e7b  lea     r8, asc_18007B44C; "."
0x180062e82  mov     rdx, r14
0x180062e85  mov     rcx, rbx
0x180062e88  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180062e8d  test    al, al
0x180062e8f  jnz     loc_18006354A
0x180062e95  mov     r8, r14
0x180062e98  mov     rdx, rbx
0x180062e9b  mov     rcx, [rdi+10h]
0x180062e9f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180062ea4  mov     rax, [rdi+18h]
0x180062ea8  mov     rdx, [rax]
0x180062eab  mov     rcx, [rdi+10h]
0x180062eaf  mov     r9, [rcx+10h]
0x180062eb3  sub     r9, rdx
0x180062eb6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062ebb  lea     rcx, [rax+rdx*2]; pszPath
0x180062ebf  xor     r8d, r8d; bool
0x180062ec2  mov     rdx, r9; unsigned __int64
0x180062ec5  call    ?replace_invalid_path_chars@@YA_NPEAG_K_N@Z; replace_invalid_path_chars(ushort *,unsigned __int64,bool)
0x180062eca  mov     rax, [rdi+18h]
0x180062ece  mov     rdx, [rax]
0x180062ed1  mov     rcx, [rdi+10h]
0x180062ed5  mov     rax, [rcx+10h]
0x180062ed9  cmp     rax, rdx
0x180062edc  jb      loc_180063DBE
0x180062ee2  sub     rax, rdx
0x180062ee5  mov     r8, r12
0x180062ee8  cmp     rax, r12
0x180062eeb  cmovb   r8, rax
0x180062eef  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062ef4  lea     rdx, [rax+rdx*2]
0x180062ef8  mov     rcx, [rdi+20h]
0x180062efc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180062f01  mov     r12, [rdi+28h]
0x180062f05  mov     r15, [rdi+20h]
0x180062f09  mov     [rsp+230h+var_1D8], r15
0x180062f0e  mov     rbx, [rdi+18h]
0x180062f12  mov     [rsp+230h+var_1D0], rbx
0x180062f17  mov     r13, [rdi+10h]
0x180062f1b  mov     [rbp+130h+var_1A0], r13
0x180062f1f  mov     [rbp+130h+var_198], rbx
0x180062f23  mov     [rbp+130h+var_190], r15
0x180062f27  mov     [rbp+130h+var_188], r12
0x180062f2b  mov     [rbp+130h+var_180], sil
0x180062f2f  mov     rcx, r13
0x180062f32  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062f37  mov     rdx, [r13+10h]
0x180062f3b  cmp     word ptr [rax+rdx*2-2], 2Fh ; '/'
0x180062f41  jz      short loc_180062F4D
0x180062f43  lea     ecx, [rsi+5Bh]
0x180062f46  cmp     [rax+rdx*2-2], cx
0x180062f4b  jnz     short loc_180062F62
0x180062f4d  dec     rdx
0x180062f50  mov     [r13+10h], rdx
0x180062f54  mov     rcx, r13
0x180062f57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180062f5c  xor     ecx, ecx
0x180062f5e  mov     [rax+rdx*2], cx
0x180062f62  mov     rax, [rdi+30h]
0x180062f66  mov     r8, [rax+8]
0x180062f6a  lea     r14, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180062f71  cmp     [rax], r8
0x180062f74  jz      short loc_180062FBE
0x180062f76  mov     r9, [rdi+10h]
0x180062f7a  mov     rdx, [rax]
0x180062f7d  lea     rcx, [rbp+130h+var_70]
0x180062f84  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V_lambda_15cb89a6428307ca39b0c99fab0e8cdb_@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@V10@V10@V_lambda_15cb89a6428307ca39b0c99fab0e8cdb_@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,_lambda_15cb89a6428307ca39b0c99fab0e8cdb_>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,_lambda_15cb89a6428307ca39b0c99fab0e8cdb_)
0x180062f89  mov     rax, [rdi+30h]
0x180062f8d  mov     rdx, [rax+8]
0x180062f91  cmp     [rbp+130h+var_70], rdx
0x180062f98  setnz   al
0x180062f9b  test    al, al
0x180062f9d  jz      short loc_180062FBE
0x180062f9f  mov     rax, [rdi+58h]
0x180062fa3  dec     qword ptr [rax]
0x180062fa6  mov     rcx, [rsp+230h+var_1C8]
0x180062fab  call    cs:__imp_archive_entry_size
0x180062fb1  mov     rcx, [rdi+58h]
0x180062fb5  sub     [rcx+8], rax
0x180062fb9  jmp     loc_180063A0B
0x180062fbe  mov     rcx, [rsp+230h+var_1C8]
0x180062fc3  call    cs:__imp_archive_entry_size
0x180062fc9  mov     rcx, [rdi+38h]
0x180062fcd  add     [rcx], rax
0x180062fd0  mov     rax, [rdi+40h]
0x180062fd4  mov     rdx, [rdi+38h]
0x180062fd8  mov     rcx, [rax]
0x180062fdb  cmp     [rdx], rcx
0x180062fde  jb      loc_1800630D6
0x180062fe4  mov     [rbp+130h+var_80], 0
0x180062fee  mov     rax, [rdi+48h]
0x180062ff2  mov     rcx, [rax]
0x180062ff5  mov     rax, [rcx]
0x180062ff8  lea     rdx, [rbp+130h+var_80]
0x180062fff  mov     rax, [rax+68h]
0x180063003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063008  mov     rcx, [rbp+138h]; this
0x18006300f  test    eax, eax
0x180063011  js      loc_180063DC4
0x180063017  cmp     [rbp+130h+var_80], 3
0x18006301e  jnz     short loc_180063047
0x180063020  mov     rax, [rdi+50h]
0x180063024  mov     dword ptr [rax], 800704C7h
0x18006302a  mov     rdx, [rbx]
0x18006302d  mov     rcx, r13
0x180063030  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180063035  mov     rdx, [r12]
0x180063039  mov     rcx, r15
0x18006303c  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180063041  nop
0x180063042  jmp     loc_180063D8A
0x180063047  cmp     [rbp+130h+var_80], esi
0x18006304d  jnz     loc_180063DD5
0x180063053  mov     [rbp+130h+var_70], 0
0x18006305e  mov     rcx, [rdi+20h]
0x180063062  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063067  xor     r9d, r9d; struct IBindCtx *
0x18006306a  lea     r8, [rbp+130h+var_70]; void **
0x180063071  mov     rcx, rax; pszPath
0x180063074  call    ?ShellItemFromFileSystemPath@@YAJPEBGAEBU_GUID@@PEAPEAXPEAUIBindCtx@@@Z; ShellItemFromFileSystemPath(ushort const *,_GUID const &,void * *,IBindCtx *)
0x180063079  test    eax, eax
0x18006307b  js      short loc_1800630C0
0x18006307d  mov     rax, [rdi+48h]
0x180063081  mov     rcx, [rax]
0x180063084  mov     rax, [rcx]
0x180063087  mov     r9, [rbp+130h+var_70]
0x18006308e  xor     r8d, r8d
0x180063091  xor     edx, edx
0x180063093  mov     rax, [rax+40h]
0x180063097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006309c  mov     rcx, [rbp+138h]; this
0x1800630a3  test    eax, eax
0x1800630a5  js      loc_180063DF7
0x1800630ab  mov     rax, [rdi+38h]
0x1800630af  mov     rcx, [rax]
0x1800630b2  add     rcx, 0F4240h
0x1800630b9  mov     rax, [rdi+40h]
0x1800630bd  mov     [rax], rcx
0x1800630c0  cmp     [rbp+130h+var_70], 0
0x1800630c8  jz      short loc_1800630D6
0x1800630ca  lea     rcx, [rbp+130h+var_70]
0x1800630d1  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800630d6  mov     dword ptr [rbp+130h+var_B0], 0
0x1800630e0  mov     byte ptr [rbp+130h+var_B0+4], 0
0x1800630e7  xorps   xmm0, xmm0
0x1800630ea  movups  [rbp+130h+var_A8], xmm0
0x1800630f1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800630f9  movdqu  [rbp+130h+var_98], xmm1
0x180063101  xor     eax, eax
0x180063103  mov     word ptr [rbp+130h+var_A8], ax
0x18006310a  mov     rax, [rdi+48h]
0x18006310e  mov     rcx, [rax]
0x180063111  mov     [rbp+130h+var_E0], rcx
0x180063115  mov     rax, [rdi+58h]
0x180063119  mov     [rbp+130h+var_D8], rax
0x18006311d  mov     rax, [rdi+60h]
0x180063121  mov     [rbp+130h+var_D0], rax
0x180063125  mov     rdx, [rdi+68h]
0x180063129  mov     rcx, rdx
0x18006312c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180063131  mov     [rsp+230h+var_1C0], rax
0x180063136  mov     rax, [rdx+10h]
0x18006313a  mov     [rsp+230h+var_1B8], rax
0x18006313f  mov     rcx, [rdi+70h]
0x180063143  lea     rax, [rbp+130h+var_E0]
0x180063147  mov     [rsp+230h+var_1F0], rax
0x18006314c  mov     rax, [rdi+80h]
0x180063153  mov     [rsp+230h+var_1F8], rax
0x180063158  mov     rax, [rdi+78h]
0x18006315c  mov     [rsp+230h+var_200], rax
0x180063161  mov     al, [rcx]
0x180063163  mov     byte ptr [rsp+230h+var_208], al
0x180063167  lea     rax, [rsp+230h+var_1C0]
0x18006316c  mov     [rsp+230h+ppv], rax
0x180063171  mov     r9, [rdi+10h]
0x180063175  mov     r8, [rsp+230h+var_1C8]
0x18006317a  mov     rdx, [rbp+130h+var_B8]
0x18006317e  lea     rcx, [rbp+130h+var_168]
0x180063182  call    ExtractArchiveEntry
0x180063187  mov     ecx, [rax]
0x180063189  mov     dword ptr [rbp+130h+var_B0], ecx
0x18006318f  mov     cl, [rax+4]
0x180063192  mov     byte ptr [rbp+130h+var_B0+4], cl
0x180063198  lea     rdx, [rax+8]
0x18006319c  lea     rcx, [rbp+130h+var_A8]
0x1800631a3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800631a8  lea     rcx, [rbp+130h+var_168+8]
0x1800631ac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800631b1  cmp     dword ptr [rbp+130h+var_B0], 0
0x1800631b8  jl      short loc_1800631FE
0x1800631ba  mov     rdx, [rdi+10h]
0x1800631be  mov     rcx, rdx
0x1800631c1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800631c6  mov     [rsp+230h+var_1C0], rax
0x1800631cb  mov     rax, [rdx+10h]
0x1800631cf  mov     [rsp+230h+var_1B8], rax
0x1800631d4  lea     rdx, [rsp+230h+var_1C0]
0x1800631d9  lea     rcx, [rbp+130h+var_168]
0x1800631dd  call    ?split_filename@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_filename(std::basic_string_view<ushort>)
0x1800631e2  mov     r8, [rax+8]
0x1800631e6  mov     rdx, [rax]
0x1800631e9  mov     rcx, [rdi+68h]
0x1800631ed  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800631f2  mov     rax, [rdi+60h]
0x1800631f6  add     [rax], rsi
0x1800631f9  jmp     loc_1800639FF
0x1800631fe  cmp     byte ptr [rbp+130h+var_B0+4], sil
0x180063205  jnz     short loc_18006323B
0x180063207  mov     rax, [rdi+50h]
0x18006320b  mov     dword ptr [rax], 800704C7h
0x180063211  lea     rcx, [rbp+130h+var_A8]
  ... truncated ...
```
