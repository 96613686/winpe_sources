# ArchiveExtractWizard::ExtractToDestination(HWND__ *,bool)

- ea: `0x18006644c`
- end: `0x180067758`
- name: `?ExtractToDestination@ArchiveExtractWizard@@AEAAJPEAUHWND__@@_N@Z`
- size: `4876`
- prototype: `int(ArchiveExtractWizard *__hidden this, HWND, bool)`
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180028d64`

## callees

- `0x180020cbc`
- `0x1800210b0`
- `0x18002abd0`
- `0x180030a3c`
- `0x180031e94`
- `0x1800332f4`
- `0x180033e78`
- `0x180034760`
- `0x180034fbc`
- `0x180035508`
- `0x1800355ec`
- `0x180036f50`
- `0x18003edd4`
- `0x180046ee0`
- `0x18004f358`
- `0x180057d74`
- `0x180057fbc`
- `0x18005b3b8`
- `0x18005ff00`
- `0x18005ff38`
- `0x180060a00`
- `0x180061088`
- `0x1800613a0`
- `0x1800626dc`
- `0x1800629f4`
- `0x180063ff4`
- `0x18006465c`
- `0x18006644c`
- `0x180067cfc`
- `0x180068798`
- `0x180071010`

## import_xrefs

- `SHELL32!__imp_SHCreateDirectory` at `0x1800665b1`
- `SHELL32!__imp_SHCreateDirectory` at `0x1800665b1`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800665e6`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x1800665e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800666a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800666a1`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall ArchiveExtractWizard::ExtractToDestination(ArchiveExtractWizard *this, HWND a2, __int64 a3)
{
  char *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 v8; // rdx
  __int64 v9; // r8
  int ExtendedLengthPath; // eax
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int v13; // esi
  const char *v14; // r9
  __int64 result; // rax
  const WCHAR *v16; // rdx
  int v17; // eax
  unsigned int v18; // ebx
  HRESULT v19; // eax
  unsigned int v20; // esi
  int v21; // eax
  __int64 v22; // rbx
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // eax
  const WCHAR *v31; // rax
  const struct _GUID *v32; // rdx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  const WCHAR *v36; // rax
  const struct _GUID *v37; // rdx
  int v38; // eax
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r8
  int v42; // eax
  unsigned __int16 *v43; // rcx
  int v44; // eax
  int v45; // eax
  __int64 v46; // rdx
  int v47; // eax
  int v48; // eax
  __int64 v49; // rdx
  __int64 v50; // r8
  int v51; // eax
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // r8
  unsigned __int16 *v55; // rax
  int v56; // eax
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // r8
  unsigned __int16 *v60; // rcx
  unsigned int v61; // edi
  int v62; // eax
  int v63; // eax
  unsigned int fuStyle; // [rsp+20h] [rbp-428h]
  int fuStylea; // [rsp+20h] [rbp-428h]
  int fuStyleb; // [rsp+20h] [rbp-428h]
  int fuStylec; // [rsp+20h] [rbp-428h]
  int fuStyled; // [rsp+20h] [rbp-428h]
  int fuStylee; // [rsp+20h] [rbp-428h]
  int fuStylef; // [rsp+20h] [rbp-428h]
  int fuStyleg; // [rsp+20h] [rbp-428h]
  int fuStyleh; // [rsp+20h] [rbp-428h]
  int fuStylei; // [rsp+20h] [rbp-428h]
  int fuStylej; // [rsp+20h] [rbp-428h]
  _QWORD v75[2]; // [rsp+40h] [rbp-408h] BYREF
  char v76; // [rsp+50h] [rbp-3F8h]
  char *v77[22]; // [rsp+60h] [rbp-3E8h] BYREF
  char v78; // [rsp+110h] [rbp-338h]
  __int128 v79; // [rsp+120h] [rbp-328h] BYREF
  HWND v80; // [rsp+130h] [rbp-318h] BYREF
  LPVOID ppv; // [rsp+138h] [rbp-310h] BYREF
  void *v82; // [rsp+140h] [rbp-308h] BYREF
  void *v83; // [rsp+148h] [rbp-300h] BYREF
  char v84; // [rsp+150h] [rbp-2F8h] BYREF
  char v85; // [rsp+151h] [rbp-2F7h] BYREF
  int v86; // [rsp+154h] [rbp-2F4h] BYREF
  __int128 v87; // [rsp+158h] [rbp-2F0h] BYREF
  __int64 v88; // [rsp+168h] [rbp-2E0h]
  __int128 v89; // [rsp+170h] [rbp-2D8h] BYREF
  __int64 v90; // [rsp+180h] [rbp-2C8h]
  _OWORD v91[2]; // [rsp+188h] [rbp-2C0h] BYREF
  __int64 v92; // [rsp+1A8h] [rbp-2A0h] BYREF
  int v93[2]; // [rsp+1B0h] [rbp-298h]
  unsigned __int64 v94; // [rsp+1B8h] [rbp-290h] BYREF
  __int128 v95; // [rsp+1C0h] [rbp-288h] BYREF
  __int64 v96; // [rsp+1D0h] [rbp-278h]
  __int64 v97; // [rsp+1D8h] [rbp-270h]
  __int64 v98; // [rsp+1E0h] [rbp-268h] BYREF
  __int64 v99; // [rsp+1E8h] [rbp-260h] BYREF
  __int64 v100; // [rsp+1F0h] [rbp-258h] BYREF
  __int64 v101; // [rsp+1F8h] [rbp-250h] BYREF
  _OWORD v102[2]; // [rsp+200h] [rbp-248h] BYREF
  _BYTE v103[16]; // [rsp+220h] [rbp-228h] BYREF
  __int64 v104; // [rsp+230h] [rbp-218h]
  _QWORD v105[2]; // [rsp+240h] [rbp-208h] BYREF
  _BYTE v106[32]; // [rsp+250h] [rbp-1F8h] BYREF
  _QWORD v107[42]; // [rsp+270h] [rbp-1D8h] BYREF
  _BYTE v108[8]; // [rsp+3C0h] [rbp-88h] BYREF
  _BYTE v109[72]; // [rsp+3C8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+0h]
  char v111; // [rsp+460h] [rbp+18h] BYREF

  v111 = a3;
  v5 = (char *)this + 8;
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8, a2, a3);
  *(_QWORD *)&v79 = v6;
  *((_QWORD *)&v79 + 1) = *((_QWORD *)v5 + 2);
  try
  {
    v7 = split_extension((__int64)v75, (__int64 *)&v79);
    wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
      v107,
      "ExtractArchive");
    v107[0] = &ArchiveFolderTelemetry::ExtractArchive::`vftable';
    v79 = *(_OWORD *)(v7 + 16);
    ArchiveFolderTelemetry::ExtractArchive::StartActivity(v107, &v79);
    v91[0] = 0;
    v91[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v91[0]) = 0;
    *(_QWORD *)&v79 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40, v8, v9);
    *((_QWORD *)&v79 + 1) = *((_QWORD *)this + 7);
    ExtendedLengthPath = MakeExtendedLengthPath(&v79, v91);
    v13 = ExtendedLengthPath;
    if ( ExtendedLengthPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x724,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)ExtendedLengthPath,
        fuStyle);
      std::wstring::_Tidy_deallocate(v91);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v107);
      return v13;
    }
    if ( v111 )
    {
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v91, v11, v12);
      v17 = SHCreateDirectory(0, v16);
      if ( v17 )
      {
        if ( v17 == 1223 )
        {
          v18 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x733,
                  (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                  (const char *)0x4C7,
                  fuStyle);
          std::wstring::_Tidy_deallocate(v91);
          ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v107);
          return v18;
        }
        else
        {
          ShellMessageBoxW(&_ImageBase, a2, (LPCWSTR)0x2942, (LPCWSTR)0x2941, 0x30u);
          wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v107,
            1);
          std::wstring::_Tidy_deallocate(v91);
          ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v107);
          return 1;
        }
      }
    }
    v75[0] = &v111;
    v75[1] = this;
    v76 = 1;
    ppv = 0;
    v19 = CoCreateInstance(&CLSID_ProgressDialog, 0, 3u, &GUID_0c9fb851_e5c9_43eb_a370_f0677b13874c, &ppv);
    v20 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x744,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v19,
        fuStylea);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
LABEL_105:
      v76 = 0;
      _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(v75);
      std::wstring::_Tidy_deallocate(v91);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v107);
      return v20;
    }
    v21 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0, 0);
    v20 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x745,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v21,
        fuStylea);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v77[21] = (char *)&ppv;
    v78 = 1;
    v80 = a2;
    *(_QWORD *)&v79 = 0;
    if ( ppv )
    {
      (**(void (__fastcall ***)(LPVOID, __int64 *, __int128 *))ppv)(ppv, winrt::impl::guid_v<IOleWindow>, &v79);
      v22 = v79;
    }
    else
    {
      v22 = 0;
    }
    if ( v22 )
    {
      v23 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v22 + 24LL))(v22, &v80);
      v20 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74E,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v23,
          fuStylea);
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v79);
        v24 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
        if ( v24 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x747,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v24,
            fuStyleb);
        if ( ppv )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
        goto LABEL_105;
      }
    }
    if ( v22 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v79);
    v25 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 48LL))(ppv, 2);
    v20 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x752,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v25,
        fuStylea);
      v26 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v26 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v26,
          fuStylec);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v27 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 2);
    v20 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x753,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v27,
        fuStylea);
      v30 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v30 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v30,
          fuStyled);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v83 = 0;
    v82 = 0;
    v31 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5, v28, v29);
    v33 = ShellItemFromFileSystemPath(v31, v32, &v83, 0);
    if ( v33 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x758,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v33,
        fuStylea);
    if ( v82 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
    v36 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v91, v34, v35);
    v38 = ShellItemFromFileSystemPath(v36, v37, &v82, 0);
    if ( v38 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x759,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v38,
        fuStylea);
    v39 = (*(__int64 (__fastcall **)(LPVOID, void *, void *, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, v83, v82, 0);
    v20 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75A,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v39,
        fuStylea);
      if ( v82 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
      if ( v83 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v83);
      v42 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v42 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v42,
          fuStylee);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v92 = 0;
    *(_QWORD *)v93 = 0;
    v94 = 0;
    *(_QWORD *)&v79 = &v92;
    *((_QWORD *)&v79 + 1) = &v94;
    v43 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5, v40, v41);
    enumerate_archive<_lambda_68a5e7536d1cd7d4dc30d39e1e7eeabe_>(v43, (_QWORD **)&v79);
    v105[0] = 0;
    v105[1] = 0;
    fuStylef = v93[0];
    v44 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, 0, *(_QWORD *)v93, 0);
    v20 = v44;
    if ( v44 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x772,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v44,
        fuStylef);
      if ( v82 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
      if ( v83 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v83);
      v45 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v45 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v45,
          fuStyleg);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v46 = 1;
    if ( !*(_QWORD *)v93 )
      v46 = 17;
    v47 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 48LL))(ppv, v46);
    v20 = v47;
    if ( v47 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77B,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v47,
        fuStylef);
      if ( v82 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
      if ( v83 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v83);
      v48 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v48 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v48,
          fuStyleh);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    std::wstring::wstring(v103, v91);
    v98 = v104;
    std::wstring::wstring(v106, v91);
    v95 = 0;
    v96 = 0;
    v97 = 7;
    LOWORD(v95) = 0;
    *(_QWORD *)&v79 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5, v49, v50);
    *((_QWORD *)&v79 + 1) = *((_QWORD *)v5 + 2);
    v51 = MakeExtendedLengthPath(&v79, &v95);
    v20 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78A,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v51,
        fuStylef);
      std::wstring::_Tidy_deallocate(&v95);
      std::wstring::_Tidy_deallocate(v106);
      std::wstring::_Tidy_deallocate(v103);
      if ( v82 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
      if ( v83 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v83);
      v52 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v52 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v52,
          fuStylei);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    std::wstring::push_back(&v95, 92);
    v99 = v96;
    v101 = 0;
    v100 = 0;
    v89 = 0;
    v90 = 0;
    v87 = 0;
    v88 = 0;
    *(_QWORD *)&v79 = v94;
    if ( v94 )
    {
      if ( v94 > 0x38E38E38E38E38ELL )
        std::vector<std::basic_string_view<unsigned short>>::_Xlength();
      std::vector<DeferredPropertyUpdates>::_Reallocate<0>(&v87, &v79);
    }
    v102[0] = 0;
    v102[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v102[0]) = 0;
    v55 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5, v53, v54);
    v56 = PrepareZoneIdentifierString(v55, (__int64)v102);
    v20 = v56;
    if ( v56 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A8,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v56,
        fuStylef);
      std::string::_Tidy_deallocate(v102);
      if ( (_QWORD)v87 )
      {
        std::_Destroy_range<std::allocator<DeferredPropertyUpdates>>(v87, *((_QWORD *)&v87 + 1));
        std::_Deallocate<16>(v87, 8 * ((v88 - (__int64)v87) >> 3));
        v87 = 0;
        v88 = 0;
      }
      if ( (_QWORD)v89 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v89, *((_QWORD *)&v89 + 1));
        std::_Deallocate<16>(v89, (v90 - v89) & 0xFFFFFFFFFFFFFFE0uLL);
        v89 = 0;
        v90 = 0;
      }
      std::wstring::_Tidy_deallocate(&v95);
      std::wstring::_Tidy_deallocate(v106);
      std::wstring::_Tidy_deallocate(v103);
      if ( v82 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
      if ( v83 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v83);
      v57 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v57 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v57,
          fuStylej);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v86 = 0;
    v84 = 1;
    v85 = 0;
    UserConfirmations::UserConfirmations((UserConfirmations *)v108);
    v77[0] = &v84;
    v77[1] = (char *)this;
    v77[2] = v103;
    v77[3] = (char *)&v98;
    v77[4] = (char *)&v95;
    v77[5] = (char *)&v99;
    v77[6] = (char *)&v89;
    v77[7] = (char *)&v100;
    v77[8] = (char *)&v101;
    v77[9] = (char *)&ppv;
    v77[10] = (char *)&v86;
    v77[11] = (char *)&v92;
    v77[12] = (char *)v105;
    v77[13] = v106;
    v77[14] = &v85;
    v77[15] = (char *)&v87;
    v77[16] = (char *)v102;
    v77[17] = v108;
    v77[18] = (char *)&v80;
    v77[19] = (char *)v107;
    v77[20] = (char *)v91;
    v60 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5, v58, v59);
    enumerate_archive<_lambda_35696a5ea3ec76acae5d3e2770fb84e0_>(v60, v77);
    wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v107,
      (unsigned int)v86);
    v61 = v86;
    if ( v86 >= 0 )
    {
      ApplyDeferredUpdates(&v87);
      v76 = 0;
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v109);
      std::string::_Tidy_deallocate(v102);
      if ( (_QWORD)v87 )
      {
        std::_Destroy_range<std::allocator<DeferredPropertyUpdates>>(v87, *((_QWORD *)&v87 + 1));
        std::_Deallocate<16>(v87, 8 * ((v88 - (__int64)v87) >> 3));
        v87 = 0;
        v88 = 0;
      }
      if ( (_QWORD)v89 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v89, *((_QWORD *)&v89 + 1));
        std::_Deallocate<16>(v89, (v90 - v89) & 0xFFFFFFFFFFFFFFE0uLL);
        v89 = 0;
        v90 = 0;
      }
      std::wstring::_Tidy_deallocate(&v95);
      std::wstring::_Tidy_deallocate(v106);
      std::wstring::_Tidy_deallocate(v103);
      if ( v82 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
      if ( v83 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v83);
      v63 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v63 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v63,
          fuStylef);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      std::wstring::_Tidy_deallocate(v91);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v107);
      result = 0;
    }
    else
    {
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v109);
      std::string::_Tidy_deallocate(v102);
      if ( (_QWORD)v87 )
      {
        std::_Destroy_range<std::allocator<DeferredPropertyUpdates>>(v87, *((_QWORD *)&v87 + 1));
        std::_Deallocate<16>(v87, 8 * ((v88 - (__int64)v87) >> 3));
        v87 = 0;
        v88 = 0;
      }
      if ( (_QWORD)v89 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v89, *((_QWORD *)&v89 + 1));
        std::_Deallocate<16>(v89, (v90 - v89) & 0xFFFFFFFFFFFFFFE0uLL);
        v89 = 0;
        v90 = 0;
      }
      std::wstring::_Tidy_deallocate(&v95);
      std::wstring::_Tidy_deallocate(v106);
      std::wstring::_Tidy_deallocate(v103);
      if ( v82 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v82);
      if ( v83 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v83);
      v62 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v62 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v62,
          fuStylef);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      v76 = 0;
      _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(v75);
      std::wstring::_Tidy_deallocate(v91);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v107);
      result = v61;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x98A,
                           (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18006644c  mov     [rsp+arg_10], r8b
0x180066451  push    rbx
0x180066452  push    rsi
0x180066453  push    rdi
0x180066454  push    r14
0x180066456  push    r15
0x180066458  sub     rsp, 420h
0x18006645f  mov     rax, cs:__security_cookie
0x180066466  xor     rax, rsp
0x180066469  mov     [rsp+448h+var_38], rax
0x180066471  mov     rbx, rdx
0x180066474  mov     r14, rcx
0x180066477  lea     rdi, [rcx+8]
0x18006647b  mov     rcx, rdi
0x18006647e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180066483  mov     qword ptr [rsp+448h+var_328], rax
0x18006648b  mov     rax, [rdi+10h]
0x18006648f  mov     qword ptr [rsp+448h+var_328+8], rax
0x180066497  lea     rdx, [rsp+448h+var_328]
0x18006649f  lea     rcx, [rsp+448h+var_408]
0x1800664a4  call    ?split_extension@@YA?AU?$pair@V?$basic_string_view@GU?$char_traits@G@std@@@std@@V12@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; split_extension(std::basic_string_view<ushort>)
0x1800664a9  mov     rsi, rax
0x1800664ac  lea     rdx, aExtractarchive; "ExtractArchive"
0x1800664b3  lea     rcx, [rsp+448h+var_1D8]
0x1800664bb  call    ??0?$ActivityBase@VArchiveFolderTelemetry@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800664c0  lea     rax, ??_7ExtractArchive@ArchiveFolderTelemetry@@6B@; const ArchiveFolderTelemetry::ExtractArchive::`vftable'
0x1800664c7  mov     [rsp+448h+var_1D8], rax
0x1800664cf  movups  xmm0, xmmword ptr [rsi+10h]
0x1800664d3  movdqu  [rsp+448h+var_328], xmm0
0x1800664dc  lea     rdx, [rsp+448h+var_328]
0x1800664e4  lea     rcx, [rsp+448h+var_1D8]
0x1800664ec  call    ?StartActivity@ExtractArchive@ArchiveFolderTelemetry@@QEAAXV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; ArchiveFolderTelemetry::ExtractArchive::StartActivity(std::basic_string_view<ushort>)
0x1800664f1  nop
0x1800664f2  xorps   xmm0, xmm0
0x1800664f5  movups  [rsp+448h+var_2C0], xmm0
0x1800664fd  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180066505  movdqu  [rsp+448h+var_2B0], xmm1
0x18006650e  xor     r15d, r15d
0x180066511  mov     word ptr [rsp+448h+var_2C0], r15w
0x18006651a  lea     rcx, [r14+28h]
0x18006651e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180066523  mov     qword ptr [rsp+448h+var_328], rax
0x18006652b  mov     rax, [r14+38h]
0x18006652f  mov     qword ptr [rsp+448h+var_328+8], rax
0x180066537  lea     rdx, [rsp+448h+var_2C0]
0x18006653f  lea     rcx, [rsp+448h+var_328]
0x180066547  call    ?MakeExtendedLengthPath@@YAJV?$basic_zstring_view@G@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MakeExtendedLengthPath(wil::basic_zstring_view<ushort>,std::wstring &)
0x18006654c  mov     esi, eax
0x18006654e  test    eax, eax
0x180066550  jns     short loc_180066591
0x180066552  mov     rcx, [rsp+448h]; this
0x18006655a  mov     r9d, eax; char *
0x18006655d  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180066564  mov     edx, 724h; void *
0x180066569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006656e  nop
0x18006656f  lea     rcx, [rsp+448h+var_2C0]
0x180066577  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006657c  nop
0x18006657d  lea     rcx, [rsp+448h+var_1D8]; this
0x180066585  call    ??1ExtractArchive@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive(void)
0x18006658a  mov     eax, esi
0x18006658c  jmp     loc_180067732
0x180066591  cmp     [rsp+448h+arg_10], r15b
0x180066599  jz      loc_180066661
0x18006659f  lea     rcx, [rsp+448h+var_2C0]
0x1800665a7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800665ac  mov     rdx, rax; pszPath
0x1800665af  xor     ecx, ecx; hwnd
0x1800665b1  call    cs:__imp_SHCreateDirectory
0x1800665b7  test    eax, eax
0x1800665b9  jz      loc_180066661
0x1800665bf  mov     r9d, 4C7h; char *
0x1800665c5  cmp     eax, r9d
0x1800665c8  jz      short loc_180066624
0x1800665ca  mov     [rsp+448h+fuStyle], 30h ; '0'; fuStyle
0x1800665d2  mov     r9d, 2941h; lpcTitle
0x1800665d8  lea     r8d, [r9+1]; lpcText
0x1800665dc  mov     rdx, rbx; hWnd
0x1800665df  lea     rcx, __ImageBase; hAppInst
0x1800665e6  call    cs:__imp_ShellMessageBoxW
0x1800665ec  mov     edx, 1
0x1800665f1  lea     rcx, [rsp+448h+var_1D8]
0x1800665f9  call    ?Stop@?$ActivityBase@VArchiveFolderTelemetry@@$00$0CAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800665fe  nop
0x1800665ff  lea     rcx, [rsp+448h+var_2C0]
0x180066607  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006660c  nop
0x18006660d  lea     rcx, [rsp+448h+var_1D8]; this
0x180066615  call    ??1ExtractArchive@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive(void)
0x18006661a  mov     eax, 1
0x18006661f  jmp     loc_180067732
0x180066624  mov     rcx, [rsp+448h]; this
0x18006662c  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180066633  mov     edx, 733h; void *
0x180066638  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18006663d  mov     ebx, eax
0x18006663f  lea     rcx, [rsp+448h+var_2C0]
0x180066647  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006664c  nop
0x18006664d  lea     rcx, [rsp+448h+var_1D8]; this
0x180066655  call    ??1ExtractArchive@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive(void)
0x18006665a  mov     eax, ebx
0x18006665c  jmp     loc_180067732
0x180066661  lea     rax, [rsp+448h+arg_10]
0x180066669  mov     [rsp+448h+var_408], rax
0x18006666e  mov     [rsp+448h+var_400], r14
0x180066673  mov     [rsp+448h+var_3F8], 1
0x180066678  mov     [rsp+448h+ppv], r15
0x180066680  lea     rax, [rsp+448h+ppv]
0x180066688  mov     qword ptr [rsp+448h+fuStyle], rax; int
0x18006668d  lea     r9, _GUID_0c9fb851_e5c9_43eb_a370_f0677b13874c; riid
0x180066694  xor     edx, edx; pUnkOuter
0x180066696  lea     r8d, [rdx+3]; dwClsContext
0x18006669a  lea     rcx, CLSID_ProgressDialog; rclsid
0x1800666a1  call    cs:__imp_CoCreateInstance
0x1800666a7  mov     esi, eax
0x1800666a9  test    eax, eax
0x1800666ab  jns     short loc_180066714
0x1800666ad  mov     rcx, [rsp+448h]; this
0x1800666b5  mov     r9d, eax; char *
0x1800666b8  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800666bf  mov     edx, 744h; void *
0x1800666c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800666c9  nop
0x1800666ca  cmp     [rsp+448h+ppv], r15
0x1800666d2  jz      short loc_1800666E2
0x1800666d4  lea     rcx, [rsp+448h+ppv]
0x1800666dc  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800666e1  nop
0x1800666e2  mov     [rsp+448h+var_3F8], r15b
0x1800666e7  lea     rcx, [rsp+448h+var_408]
0x1800666ec  call    ??R_lambda_a43f877cf21f9886dbe379087b0ce961_@@QEBA@XZ; _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(void)
0x1800666f1  nop
0x1800666f2  lea     rcx, [rsp+448h+var_2C0]
0x1800666fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800666ff  nop
0x180066700  lea     rcx, [rsp+448h+var_1D8]; this
0x180066708  call    ??1ExtractArchive@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive(void)
0x18006670d  mov     eax, esi
0x18006670f  jmp     loc_180067732
0x180066714  mov     rcx, [rsp+448h+ppv]
0x18006671c  mov     rax, [rcx]
0x18006671f  xor     r8d, r8d
0x180066722  xor     edx, edx
0x180066724  mov     rax, [rax+18h]
0x180066728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006672d  mov     esi, eax
0x18006672f  test    eax, eax
0x180066731  jns     short loc_18006679A
0x180066733  mov     rcx, [rsp+448h]; this
0x18006673b  mov     r9d, eax; char *
0x18006673e  lea     r8, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x180066745  mov     edx, 745h; void *
0x18006674a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006674f  nop
0x180066750  cmp     [rsp+448h+ppv], r15
0x180066758  jz      short loc_180066768
0x18006675a  lea     rcx, [rsp+448h+ppv]
0x180066762  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180066767  nop
0x180066768  mov     [rsp+448h+var_3F8], r15b
0x18006676d  lea     rcx, [rsp+448h+var_408]
0x180066772  call    ??R_lambda_a43f877cf21f9886dbe379087b0ce961_@@QEBA@XZ; _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(void)
0x180066777  nop
0x180066778  lea     rcx, [rsp+448h+var_2C0]
0x180066780  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180066785  nop
0x180066786  lea     rcx, [rsp+448h+var_1D8]; this
0x18006678e  call    ??1ExtractArchive@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive(void)
0x180066793  mov     eax, esi
0x180066795  jmp     loc_180067732
0x18006679a  lea     rax, [rsp+448h+ppv]
0x1800667a2  mov     [rsp+448h+var_340], rax
0x1800667aa  mov     [rsp+448h+var_338], 1
0x1800667b2  mov     [rsp+448h+var_318], rbx
0x1800667ba  mov     rcx, [rsp+448h+ppv]
0x1800667c2  mov     qword ptr [rsp+448h+var_328], r15
0x1800667ca  test    rcx, rcx
0x1800667cd  jnz     short loc_1800667D4
0x1800667cf  mov     rbx, r15
0x1800667d2  jmp     short loc_1800667FE
0x1800667d4  mov     rax, [rcx]
0x1800667d7  lea     r8, [rsp+448h+var_328]
0x1800667df  lea     rdx, ??$guid_v@UIOleWindow@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<IOleWindow>
0x1800667e6  mov     rax, [rax]
0x1800667e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667ee  mov     rbx, qword ptr [rsp+448h+var_328]
0x1800667f6  mov     qword ptr [rsp+448h+var_328], rbx
0x1800667fe  test    rbx, rbx
0x180066801  jz      loc_1800668D1
0x180066807  mov     rax, [rbx]
0x18006680a  lea     rdx, [rsp+448h+var_318]
0x180066812  mov     rcx, rbx
0x180066815  mov     rax, [rax+18h]
0x180066819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006681e  mov     esi, eax
0x180066820  test    eax, eax
0x180066822  jns     loc_1800668D1
0x180066828  mov     rcx, [rsp+448h]; this
0x180066830  mov     r9d, eax; char *
0x180066833  lea     rbx, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x18006683a  mov     r8, rbx; unsigned int
0x18006683d  mov     edx, 74Eh; void *
0x180066842  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066847  nop
0x180066848  lea     rcx, [rsp+448h+var_328]
0x180066850  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180066855  nop
0x180066856  mov     rcx, [rsp+448h+ppv]
0x18006685e  mov     rax, [rcx]
0x180066861  mov     rax, [rax+20h]
0x180066865  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006686a  mov     rcx, [rsp+448h]; this
0x180066872  test    eax, eax
0x180066874  jns     short loc_180066887
0x180066876  mov     r9d, eax; char *
0x180066879  mov     r8, rbx; unsigned int
0x18006687c  mov     edx, 747h; void *
0x180066881  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180066886  nop
0x180066887  cmp     [rsp+448h+ppv], r15
0x18006688f  jz      short loc_18006689F
0x180066891  lea     rcx, [rsp+448h+ppv]
0x180066899  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x18006689e  nop
0x18006689f  mov     [rsp+448h+var_3F8], r15b
0x1800668a4  lea     rcx, [rsp+448h+var_408]
0x1800668a9  call    ??R_lambda_a43f877cf21f9886dbe379087b0ce961_@@QEBA@XZ; _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(void)
0x1800668ae  nop
0x1800668af  lea     rcx, [rsp+448h+var_2C0]
0x1800668b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800668bc  nop
0x1800668bd  lea     rcx, [rsp+448h+var_1D8]; this
0x1800668c5  call    ??1ExtractArchive@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive(void)
0x1800668ca  mov     eax, esi
0x1800668cc  jmp     loc_180067732
0x1800668d1  test    rbx, rbx
0x1800668d4  jz      short loc_1800668E3
0x1800668d6  lea     rcx, [rsp+448h+var_328]
0x1800668de  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x1800668e3  mov     rcx, [rsp+448h+ppv]
0x1800668eb  mov     rax, [rcx]
0x1800668ee  mov     ebx, 2
0x1800668f3  mov     edx, ebx
0x1800668f5  mov     rax, [rax+30h]
0x1800668f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800668fe  mov     esi, eax
0x180066900  test    eax, eax
0x180066902  jns     loc_1800669A3
0x180066908  mov     rcx, [rsp+448h]; this
0x180066910  mov     r9d, eax; char *
0x180066913  lea     rbx, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x18006691a  mov     r8, rbx; unsigned int
0x18006691d  mov     edx, 752h; void *
0x180066922  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180066927  nop
0x180066928  mov     rcx, [rsp+448h+ppv]
0x180066930  mov     rax, [rcx]
0x180066933  mov     rax, [rax+20h]
0x180066937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006693c  mov     rcx, [rsp+448h]; this
0x180066944  test    eax, eax
0x180066946  jns     short loc_180066959
0x180066948  mov     r9d, eax; char *
0x18006694b  mov     r8, rbx; unsigned int
0x18006694e  mov     edx, 747h; void *
0x180066953  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180066958  nop
0x180066959  cmp     [rsp+448h+ppv], r15
0x180066961  jz      short loc_180066971
0x180066963  lea     rcx, [rsp+448h+ppv]
0x18006696b  call    ?unconditional_release_ref@?$com_ptr@UIShellFolder2@@@winrt@@AEAAXXZ; winrt::com_ptr<IShellFolder2>::unconditional_release_ref(void)
0x180066970  nop
0x180066971  mov     [rsp+448h+var_3F8], r15b
0x180066976  lea     rcx, [rsp+448h+var_408]
0x18006697b  call    ??R_lambda_a43f877cf21f9886dbe379087b0ce961_@@QEBA@XZ; _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(void)
0x180066980  nop
0x180066981  lea     rcx, [rsp+448h+var_2C0]
0x180066989  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006698e  nop
0x18006698f  lea     rcx, [rsp+448h+var_1D8]; this
0x180066997  call    ??1ExtractArchive@ArchiveFolderTelemetry@@QEAA@XZ; ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive(void)
0x18006699c  mov     eax, esi
0x18006699e  jmp     loc_180067732
0x1800669a3  mov     rcx, [rsp+448h+ppv]
0x1800669ab  mov     rax, [rcx]
0x1800669ae  mov     edx, ebx
0x1800669b0  mov     rax, [rax+28h]
0x1800669b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669b9  mov     esi, eax
0x1800669bb  test    eax, eax
0x1800669bd  jns     loc_180066A5E
0x1800669c3  mov     rcx, [rsp+448h]; this
0x1800669cb  mov     r9d, eax; char *
0x1800669ce  lea     rbx, aShellExtZipArc_8; "shell\\ext\\zip\\archive\\archiveextrac"...
0x1800669d5  mov     r8, rbx; unsigned int
0x1800669d8  mov     edx, 753h; void *
0x1800669dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800669e2  nop
  ... truncated ...
```
