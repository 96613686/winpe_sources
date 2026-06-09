# _lambda_35696a5ea3ec76acae5d3e2770fb84e0_::operator()(archive *,archive_entry *)

- ea: `0x180062d2c`
- end: `0x180063e5d`
- name: `??R_lambda_35696a5ea3ec76acae5d3e2770fb84e0_@@QEBA@PEAUarchive@@PEAUarchive_entry@@@Z`
- size: `4401`
- prototype: ``
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
// Hidden C++ exception states: #wind=13
char __fastcall _lambda_35696a5ea3ec76acae5d3e2770fb84e0_::operator()(char **a1, void *a2, struct archive_entry *a3)
{
  const WCHAR *v5; // rax
  const WCHAR *v6; // r9
  char v7; // r15
  __int64 v8; // r8
  __int64 v9; // rax
  const unsigned __int16 *v10; // r9
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rsi
  unsigned __int64 v15; // r14
  __int64 v16; // rbx
  __int64 not_ch_2; // rax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rbx
  char v20; // si
  __int64 v21; // rax
  __int64 v22; // rdx
  unsigned __int64 v23; // r9
  char *v24; // rcx
  char *v25; // r12
  char *v26; // r15
  char *v27; // rbx
  char *v28; // r13
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdx
  char *v33; // rax
  __int64 v34; // r8
  int v35; // eax
  const WCHAR *v36; // rax
  const struct _GUID *v37; // rdx
  int v38; // eax
  __int64 v39; // rdx
  __int64 ArchiveEntry; // rax
  __int64 v41; // rdx
  _QWORD *v42; // rax
  HRESULT v43; // eax
  const WCHAR *v44; // rax
  const struct _GUID *v45; // rdx
  int v46; // eax
  char v47; // cl
  const WCHAR *v48; // rax
  const struct _GUID *v49; // rdx
  int v50; // eax
  char v51; // bl
  unsigned __int8 Response; // r15
  __int64 v53; // rbx
  int v54; // eax
  unsigned __int8 v55; // al
  __int64 v56; // r8
  int v57; // ecx
  int v58; // ecx
  char v59; // r15
  const WCHAR *v60; // rax
  DWORD FileAttributesW; // eax
  bool v62; // bl
  unsigned __int8 v63; // cl
  char v64; // cl
  __int128 v65; // xmm0
  int v66; // edx
  void *v67; // rcx
  char v68; // cl
  __int128 v69; // xmm0
  const WCHAR *v70; // rax
  WCHAR v71; // bx
  const WCHAR *v72; // rax
  const struct _GUID *v73; // rdx
  int v74; // eax
  const WCHAR *v75; // rax
  const struct _GUID *v76; // rdx
  int v77; // eax
  int v78; // eax
  __int64 v79; // r8
  char *v80; // rcx
  __int64 v81; // rdx
  int v82; // eax
  char *v84; // rbx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rbx
  _WORD *v88; // rax
  _WORD *i; // rdx
  __int64 v90; // rax
  int v91; // ebx
  const char *v92; // r9
  unsigned int v93; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID *ppvb; // [rsp+20h] [rbp-E0h]
  char v97; // [rsp+50h] [rbp-B0h]
  char *v98; // [rsp+58h] [rbp-A8h]
  char *v99; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v101; // [rsp+70h] [rbp-90h] BYREF
  __int64 v102; // [rsp+78h] [rbp-88h]
  _QWORD v103[6]; // [rsp+80h] [rbp-80h] BYREF
  char v104; // [rsp+B0h] [rbp-50h]
  PCWSTR ppszRootEnd[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v106; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v107; // [rsp+D8h] [rbp-28h]
  _DWORD v108[3]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v109; // [rsp+FCh] [rbp-4h]
  int v110; // [rsp+114h] [rbp+14h]
  void *v111; // [rsp+118h] [rbp+18h]
  int v112; // [rsp+128h] [rbp+28h]
  __int64 v113; // [rsp+130h] [rbp+30h]
  __int64 v114; // [rsp+140h] [rbp+40h]
  _QWORD v115[3]; // [rsp+150h] [rbp+50h] BYREF
  void *v116; // [rsp+168h] [rbp+68h] BYREF
  void *v117; // [rsp+170h] [rbp+70h] BYREF
  LPVOID v118; // [rsp+178h] [rbp+78h] BYREF
  int v119; // [rsp+180h] [rbp+80h] BYREF
  char v120; // [rsp+184h] [rbp+84h]
  __int128 v121; // [rsp+188h] [rbp+88h] BYREF
  __m128i si128; // [rsp+198h] [rbp+98h]
  __int64 v123; // [rsp+1A8h] [rbp+A8h] BYREF
  int v124; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v125; // [rsp+1B8h] [rbp+B8h] BYREF
  void *v126[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v127[16]; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v128; // [rsp+1E0h] [rbp+E0h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v118 = a2;
  v5 = (const WCHAR *)archive_entry_pathname_w(a3);
  v6 = v5;
  v7 = 0;
  if ( !v5 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x7B0,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      0);
  ppszRootEnd[0] = v5;
  v8 = -1;
  do
    ++v8;
  while ( v5[v8] );
  ppszRootEnd[1] = (PCWSTR)v8;
  v97 = **a1;
  if ( v97 )
  {
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[1] + 8);
    v101 = v10;
    v102 = v11;
    v103[0] = v9;
    v103[1] = *(_QWORD *)(v12 + 24);
    *(_OWORD *)ppszRootEnd = *(_OWORD *)check_rename(v126, a2, v103, &v101);
    **a1 = 0;
  }
  LOBYTE(v8) = 0;
  std::filesystem::_Convert_Source_to_wide<std::basic_string_view<unsigned short>,std::filesystem::_Normal_conversion>(
    &v106,
    ppszRootEnd,
    v8,
    v6);
  std::filesystem::path::lexically_normal(&v106, v127);
  std::wstring::_Tidy_deallocate(&v106);
  v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v127);
  v14 = v13;
  v15 = v128;
  if ( !v128
    || ((v16 = v13 + 2 * v128, not_ch_2 = _std_find_not_ch_2(v13, v16, 92), not_ch_2 == v16)
      ? (v18 = -1)
      : (v18 = (not_ch_2 - v14) >> 1),
        v15 < v18) )
  {
    v18 = v15;
  }
  v19 = v14 + 2 * v18;
  v20 = 1;
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v19, v15 - v18, L".", 1) )
    goto LABEL_67;
  std::wstring::_Append<unsigned short>(a1[2]);
  v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[2]);
  replace_invalid_path_chars((PCWSTR)(v21 + 2 * v22), v23, 0);
  v24 = a1[2];
  if ( *((_QWORD *)v24 + 2) < *(_QWORD *)a1[3] )
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
  std::wstring::_Append<unsigned short>(a1[4]);
  v25 = a1[5];
  v26 = a1[4];
  v98 = v26;
  v27 = a1[3];
  v99 = v27;
  v28 = a1[2];
  v103[2] = v28;
  v103[3] = v27;
  v103[4] = v26;
  v103[5] = v25;
  v104 = 1;
  v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
  v30 = *((_QWORD *)v28 + 2);
  if ( *(_WORD *)(v29 + 2 * v30 - 2) == 47 || *(_WORD *)(v29 + 2 * v30 - 2) == 92 )
  {
    *((_QWORD *)v28 + 2) = v30 - 1;
    v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v28);
    *(_WORD *)(v31 + 2 * v32) = 0;
  }
  v33 = a1[6];
  v34 = *((_QWORD *)v33 + 1);
  if ( *(_QWORD *)v33 == v34
    || (std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,_lambda_15cb89a6428307ca39b0c99fab0e8cdb_>(
          v126,
          *(_QWORD *)v33,
          v34,
          a1[2]),
        v126[0] == *((void **)a1[6] + 1)) )
  {
    *(_QWORD *)a1[7] += archive_entry_size(a3);
    if ( *(_QWORD *)a1[7] >= *(_QWORD *)a1[8] )
    {
      v124 = 0;
      v35 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)a1[9] + 104LL))(*(_QWORD *)a1[9], &v124);
      if ( v35 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7F5,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v35,
          ppv);
      if ( v124 == 3 )
      {
        *(_DWORD *)a1[10] = -2147023673;
        std::wstring::resize(v28, *(_QWORD *)v27);
        std::wstring::resize(v26, *(_QWORD *)v25);
LABEL_190:
        std::wstring::_Tidy_deallocate(v127);
        return v20;
      }
      if ( v124 != 1 )
      {
        v93 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x7FE,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)v93,
          ppv);
      }
      v126[0] = 0;
      v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[4]);
      if ( (int)ShellItemFromFileSystemPath(v36, v37, v126, 0) >= 0 )
      {
        v38 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, void *))(**(_QWORD **)a1[9] + 64LL))(
                *(_QWORD *)a1[9],
                0,
                0,
                v126[0]);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x806,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v38,
            ppv);
        *(_QWORD *)a1[8] = *(_QWORD *)a1[7] + 1000000LL;
      }
      if ( v126[0] )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(v126);
    }
    v119 = 0;
    v120 = 0;
    v121 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v121) = 0;
    v115[0] = *(_QWORD *)a1[9];
    v115[1] = a1[11];
    v115[2] = a1[12];
    v101 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[13]);
    v102 = *(_QWORD *)(v39 + 16);
    ArchiveEntry = ExtractArchiveEntry(
                     (unsigned int)&v106,
                     (_DWORD)v118,
                     (_DWORD)a3,
                     (unsigned int)a1[2],
                     (__int64)&v101,
                     *a1[14],
                     (__int64)a1[15],
                     (__int64)a1[16],
                     (__int64)v115);
    v119 = *(_DWORD *)ArchiveEntry;
    v120 = *(_BYTE *)(ArchiveEntry + 4);
    std::wstring::operator=(&v121, ArchiveEntry + 8);
    std::wstring::_Tidy_deallocate((char *)&v106 + 8);
    if ( v119 >= 0 )
    {
      v101 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[2]);
      v102 = *(_QWORD *)(v41 + 16);
      v42 = (_QWORD *)split_filename(&v106, &v101);
      std::wstring::_Assign<unsigned short>(a1[13], *v42, v42[1]);
      ++*(_QWORD *)a1[12];
LABEL_146:
      std::wstring::_Tidy_deallocate(&v121);
      goto LABEL_147;
    }
    if ( v120 == 1 )
    {
      *(_DWORD *)a1[10] = -2147023673;
      std::wstring::_Tidy_deallocate(&v121);
      std::wstring::resize(v28, *(_QWORD *)v27);
      std::wstring::resize(v26, *(_QWORD *)v25);
      goto LABEL_190;
    }
    std::wstring::resize(a1[4], si128.m128i_i64[0] + *(_QWORD *)a1[5] - *(_QWORD *)a1[3]);
    v118 = 0;
    v43 = CoCreateInstance(&CLSID_TransferConfirmationUI, 0, 3u, &GUID_14cc750c_7b0b_43dc_910e_b687f84e7c3b, &v118);
    if ( v43 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x831,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v43,
        ppva);
    v117 = 0;
    v44 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[4]);
    v46 = ShellItemFromFileSystemPath(v44, v45, &v117, 0);
    if ( v46 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x83B,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v46,
        ppva);
      v47 = v120;
      if ( v120 == 4 )
        v47 = 2;
      v120 = v47;
    }
    v116 = 0;
    v48 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v121);
    v50 = ShellItemFromFileSystemPath(v48, v49, &v116, 0);
    LODWORD(v123) = v50;
    v51 = v120;
    if ( v50 < 0 )
    {
      if ( v120 != 4 )
        goto LABEL_68;
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x84E,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v50,
        ppva);
      v51 = 2;
      v120 = 2;
      v119 = v123;
    }
    if ( v51 == 4 )
    {
      Response = UserConfirmations::GetResponse(a1[17], &v119);
      if ( !Response )
      {
        v106 = 0;
        v107 = 0;
        *(_QWORD *)&v106 = *(_QWORD *)a1[18];
        *((_QWORD *)&v106 + 1) = 0x200000007LL;
        DWORD2(v107) = 0;
        v103[0] = v116;
        v101 = (const unsigned __int16 *)v117;
        winrt::make_self<ArchiveConflictItems,IShellItem *,IShellItem *>(&v125, &v101, v103);
        v123 = 0;
        ppszRootEnd[0] = 0;
        v53 = v125;
        v54 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, __int64, __int64 *))(*(_QWORD *)v118 + 32LL))(
                v118,
                &v106,
                v125,
                &v123);
        if ( v54 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x869,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v54,
            (int)ppszRootEnd);
        v55 = UserConfirmations::TranslateResponse(v123, ppszRootEnd[0]);
        Response = v55;
        if ( HIDWORD(v123) )
        {
          LOBYTE(v56) = v55;
          UserConfirmations::SetResponse(a1[17], &v119, v56);
        }
        if ( ppszRootEnd[0] )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(ppszRootEnd);
        if ( v53 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v125);
      }
      v57 = Response;
      v7 = 2;
      v58 = v57 - 2;
      if ( v58 )
      {
        if ( v58 == 1 )
        {
          *(_DWORD *)a1[10] = -2147023673;
          if ( v116 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
          if ( v117 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
          if ( v118 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
LABEL_59:
          std::wstring::_Tidy_deallocate(&v121);
          std::wstring::resize(v28, *(_QWORD *)v99);
          std::wstring::resize(v98, *(_QWORD *)v25);
          goto LABEL_190;
        }
        goto LABEL_138;
      }
      *a1[14] |= 1u;
      **a1 = v97;
      if ( v116 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
      if ( v117 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
      if ( v118 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
      std::wstring::_Tidy_deallocate(&v121);
      std::wstring::resize(v28, *(_QWORD *)v99);
      std::wstring::resize(v98, *(_QWORD *)v25);
LABEL_67:
      v20 = v7;
      goto LABEL_190;
    }
LABEL_68:
    if ( v51 == 3 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x887,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v119,
        ppva);
      *(_DWORD *)a1[10] = v119;
      if ( v116 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
      if ( v117 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
      if ( v118 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
      goto LABEL_189;
    }
    if ( (unsigned __int8)(v51 - 6) <= 2u )
    {
      v103[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v121) + 2LL * *(_QWORD *)a1[3];
      if ( v51 == 6 )
      {
        ArchiveFolderTelemetry::ExtractArchive::EncounteredReparsePoint((ArchiveFolderTelemetry::ExtractArchive *)a1[19]);
        v87 = 10571;
      }
      else if ( v51 == 7 )
      {
        ArchiveFolderTelemetry::ExtractArchive::EncounteredRelativePath((ArchiveFolderTelemetry::ExtractArchive *)a1[19]);
        v87 = 10572;
      }
      else
      {
        v84 = a1[19];
        v101 = ArchiveEntryTypeLoggingString(a3);
        ArchiveFolderTelemetry::ExtractArchive::EncounteredUnsupportedType<unsigned short const *>(v84, &v101);
        v87 = 10573;
      }
      LOBYTE(v85) = 0;
      std::filesystem::_Convert_Source_to_wide<std::basic_string_view<unsigned short>,std::filesystem::_Normal_conversion>(
        &v106,
        ppszRootEnd,
        v85,
        v86);
      v88 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v106);
      for ( i = &v88[v107]; v88 != i; ++v88 )
      {
        if ( *v88 == 47 )
          *v88 = 92;
      }
      v90 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v106);
      v91 = ShellMessageBoxW(&_ImageBase, *(HWND *)a1[18], (LPCWSTR)v87, (LPCWSTR)0x2941, 0x31u, v90, v103[0]);
      std::wstring::_Tidy_deallocate(&v106);
      if ( !v91 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x8B2,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          v92);
      if ( v91 == 1 )
        goto LABEL_139;
      *(_DWORD *)a1[10] = -2147023673;
      if ( v116 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
      if ( v117 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
      if ( v118 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
LABEL_189:
      std::wstring::_Tidy_deallocate(&v121);
      std::wstring::resize(v28, *(_QWORD *)v99);
      std::wstring::resize(v26, *(_QWORD *)v25);
      goto LABEL_190;
    }
    v59 = UserConfirmations::GetResponse(a1[17], &v119);
    if ( v59 )
    {
LABEL_132:
      if ( v59 )
      {
        if ( v59 != 2 )
        {
          if ( v59 == 3 )
          {
            *(_DWORD *)a1[10] = -2147023673;
            if ( v116 )
              winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
            if ( v117 )
              winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
            if ( v118 )
              winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
            goto LABEL_59;
          }
          if ( v51 == 5 )
          {
            v80 = a1[6];
            v81 = *((_QWORD *)v80 + 1);
            if ( v81 == *((_QWORD *)v80 + 2) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(v80, v81, &v121);
            }
            else
            {
              *(_OWORD *)v81 = 0;
              *(_QWORD *)(v81 + 16) = 0;
              *(_QWORD *)(v81 + 24) = 0;
              *(_OWORD *)v81 = v121;
              *(__m128i *)(v81 + 16) = si128;
              si128 = _mm_load_si128((const __m128i *)&_xmm);
              LOWORD(v121) = 0;
              *((_QWORD *)v80 + 1) += 32LL;
            }
          }
          goto LABEL_138;
        }
        if ( v51 != 9 )
        {
LABEL_138:
          v26 = v98;
LABEL_139:
          --*(_QWORD *)a1[11];
          *((_QWORD *)a1[11] + 1) -= archive_entry_size(a3);
          if ( v116 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
          if ( v117 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
          if ( v118 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
          v27 = v99;
          goto LABEL_146;
        }
        *a1[14] |= 4u;
        **a1 = v97;
        if ( v116 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
        if ( v117 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
        if ( v118 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
      }
      else
      {
        **a1 = v97;
        if ( v116 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
        if ( v117 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
        if ( v118 )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v118);
      }
      std::wstring::_Tidy_deallocate(&v121);
      std::wstring::resize(v28, *(_QWORD *)v99);
      std::wstring::resize(v98, *(_QWORD *)v25);
      v20 = 2;
      goto LABEL_190;
    }
    v60 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v121);
    FileAttributesW = GetFileAttributesW(v60);
    if ( FileAttributesW == -1 )
    {
      v62 = v97;
    }
    else
    {
      v62 = (FileAttributesW & 0x10) != 0;
      v59 = 1;
    }
    LODWORD(ppszRootEnd[0]) = (ArchiveEntryToWindowsAttributes(a3) & 0x10) != 0;
    memset_0(v108, 0, 0x60u);
    v114 = *(_QWORD *)a1[18];
    v108[0] = 40;
    v108[1] = 2;
    v63 = (unsigned __int8)ppszRootEnd[0];
    if ( v59 )
      v63 = v62;
    v108[2] = v63;
    v110 = 0;
    v111 = v117;
    switch ( v120 )
    {
      case 2:
        v66 = v119;
        if ( v119 == -2147024864 )
        {
          v67 = v111;
          if ( v116 )
            v67 = v116;
          v111 = v67;
          v112 = -2144927704;
          v68 = (char)ppszRootEnd[0];
          if ( v59 )
            v68 = v62;
          if ( v68 )
            v69 = STCONFIRM_IN_USE_STORAGE;
          else
            v69 = STCONFIRM_IN_USE_STREAM;
          goto LABEL_112;
        }
        if ( v119 != -2147024784 )
        {
          v74 = -2147024882;
          if ( v119 == -2147024882 )
          {
            v69 = STCONFIRM_OUT_OF_MEMORY;
            goto LABEL_111;
          }
          goto LABEL_109;
        }
        ppszRootEnd[0] = 0;
        v70 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[20]);
        if ( PathCchSkipRoot(v70, ppszRootEnd) >= 0 )
        {
          v71 = *ppszRootEnd[0];
          *ppszRootEnd[0] = 0;
          if ( v116 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v116);
          v72 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[20]);
          if ( (int)ShellItemFromFileSystemPath(v72, v73, &v116, 0) >= 0 )
          {
            v111 = v116;
            v112 = v119;
            v109 = STCONFIRM_UNEXPECTED_ERROR;
            *ppszRootEnd[0] = v71;
            goto LABEL_113;
          }
          *ppszRootEnd[0] = v71;
        }
        break;
      case 5:
LABEL_110:
        v69 = STCONFIRM_UNEXPECTED_ERROR;
        v74 = v119;
LABEL_111:
        v112 = v74;
LABEL_112:
        v109 = v69;
        goto LABEL_113;
      case 9:
        v112 = v119;
        v64 = (char)ppszRootEnd[0];
        if ( v59 )
          v64 = v62;
        if ( v64 )
          v65 = STCONFIRM_ABSOLUTE_LINK_STORAGE;
        else
          v65 = STCONFIRM_ABSOLUTE_LINK_STREAM;
        v109 = v65;
        v113 = archive_entry_symlink_w(a3);
        if ( !v113 )
          v113 = archive_entry_hardlink_w(a3);
LABEL_113:
        if ( !v111 )
        {
          if ( v117 )
            winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v117);
          v75 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1[1] + 8);
          v77 = ShellItemFromFileSystemPath(v75, v76, &v117, 0);
          if ( v77 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x930,
              (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
              (const char *)(unsigned int)v77,
              ppva);
          v111 = v117;
        }
        LODWORD(v125) = 0;
        LODWORD(v123) = 0;
        v78 = (*(__int64 (__fastcall **)(LPVOID, _DWORD *, __int64 *, __int64 *))(*(_QWORD *)v118 + 24LL))(
                v118,
                v108,
                &v125,
                &v123);
        if ( v78 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x936,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v78,
            ppva);
        if ( !(_DWORD)v125 )
        {
          v59 = 2;
          goto LABEL_129;
        }
        if ( (_DWORD)v125 != 1 )
        {
          if ( (_DWORD)v125 == 2 )
          {
            v59 = 0;
            goto LABEL_129;
          }
          if ( (_DWORD)v125 == 4 )
          {
            v59 = 3;
LABEL_129:
            if ( (_DWORD)v123 )
            {
              LOBYTE(v79) = v59;
              UserConfirmations::SetResponse(a1[17], &v119, v79);
            }
            v51 = v120;
            goto LABEL_132;
          }
        }
        v59 = 1;
        goto LABEL_129;
    }
    v66 = v119;
LABEL_109:
    ArchiveFolderTelemetry::ExtractArchive::EncounteredError((ArchiveFolderTelemetry::ExtractArchive *)a1[19], v66);
    goto LABEL_110;
  }
  --*(_QWORD *)a1[11];
  *((_QWORD *)a1[11] + 1) -= archive_entry_size(a3);
LABEL_147:
  ppvb = (LPVOID *)*((_QWORD *)a1[11] + 1);
  v82 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, LPVOID *, _QWORD))(**(_QWORD **)a1[9] + 56LL))(
          *(_QWORD *)a1[9],
          *((_QWORD *)a1[12] + 1),
          ppvb,
          *((_QWORD *)a1[12] + 1));
  if ( v82 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x974,
      (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
      (const char *)(unsigned int)v82,
      (int)ppvb);
  *a1[14] = 0;
  std::wstring::resize(v28, *(_QWORD *)v27);
  std::wstring::resize(v26, *(_QWORD *)v25);
  std::wstring::_Tidy_deallocate(v127);
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
