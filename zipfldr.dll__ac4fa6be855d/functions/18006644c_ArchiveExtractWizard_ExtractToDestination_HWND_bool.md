# ArchiveExtractWizard::ExtractToDestination(HWND__ *,bool)

- ea: `0x18006644c`
- end: `0x180067758`
- name: `?ExtractToDestination@ArchiveExtractWizard@@AEAAJPEAUHWND__@@_N@Z`
- size: `4876`
- prototype: `__int64 __fastcall(ArchiveExtractWizard *this, HWND, char)`
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
// Hidden C++ exception states: #wind=1
__int64 __fastcall ArchiveExtractWizard::ExtractToDestination(ArchiveExtractWizard *this, HWND a2, char a3)
{
  char *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rsi
  int ExtendedLengthPath; // eax
  unsigned int v9; // esi
  const char *v10; // r9
  __int64 result; // rax
  const WCHAR *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  HRESULT v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  __int64 v18; // rbx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  const WCHAR *v25; // rax
  const struct _GUID *v26; // rdx
  int v27; // eax
  const WCHAR *v28; // rax
  const struct _GUID *v29; // rdx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  unsigned __int16 *v33; // rcx
  int v34; // eax
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  unsigned __int16 *v41; // rax
  int v42; // eax
  int v43; // eax
  unsigned __int16 *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // r9
  unsigned int v48; // edi
  int v49; // eax
  int v50; // eax
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
  _QWORD v62[2]; // [rsp+40h] [rbp-408h] BYREF
  char v63; // [rsp+50h] [rbp-3F8h]
  char *v64; // [rsp+60h] [rbp-3E8h]
  ArchiveExtractWizard *v65; // [rsp+68h] [rbp-3E0h]
  _BYTE *v66; // [rsp+70h] [rbp-3D8h]
  __int64 *v67; // [rsp+78h] [rbp-3D0h]
  __int128 *v68; // [rsp+80h] [rbp-3C8h]
  __int64 *v69; // [rsp+88h] [rbp-3C0h]
  __int128 *v70; // [rsp+90h] [rbp-3B8h]
  __int64 *v71; // [rsp+98h] [rbp-3B0h]
  __int64 *v72; // [rsp+A0h] [rbp-3A8h]
  LPVOID *v73; // [rsp+A8h] [rbp-3A0h]
  int *v74; // [rsp+B0h] [rbp-398h]
  __int64 *v75; // [rsp+B8h] [rbp-390h]
  _QWORD *v76; // [rsp+C0h] [rbp-388h]
  _BYTE *v77; // [rsp+C8h] [rbp-380h]
  char *v78; // [rsp+D0h] [rbp-378h]
  __int128 *v79; // [rsp+D8h] [rbp-370h]
  _OWORD *v80; // [rsp+E0h] [rbp-368h]
  _BYTE *v81; // [rsp+E8h] [rbp-360h]
  HWND *v82; // [rsp+F0h] [rbp-358h]
  _QWORD *v83; // [rsp+F8h] [rbp-350h]
  _OWORD *v84; // [rsp+100h] [rbp-348h]
  LPVOID *p_ppv; // [rsp+108h] [rbp-340h]
  char v86; // [rsp+110h] [rbp-338h]
  __int128 v87; // [rsp+120h] [rbp-328h] BYREF
  HWND v88; // [rsp+130h] [rbp-318h] BYREF
  LPVOID ppv; // [rsp+138h] [rbp-310h] BYREF
  void *v90; // [rsp+140h] [rbp-308h] BYREF
  void *v91; // [rsp+148h] [rbp-300h] BYREF
  char v92; // [rsp+150h] [rbp-2F8h] BYREF
  char v93; // [rsp+151h] [rbp-2F7h] BYREF
  int v94; // [rsp+154h] [rbp-2F4h] BYREF
  __int128 v95; // [rsp+158h] [rbp-2F0h] BYREF
  __int64 v96; // [rsp+168h] [rbp-2E0h]
  __int128 v97; // [rsp+170h] [rbp-2D8h] BYREF
  __int64 v98; // [rsp+180h] [rbp-2C8h]
  _OWORD v99[2]; // [rsp+188h] [rbp-2C0h] BYREF
  __int64 v100; // [rsp+1A8h] [rbp-2A0h] BYREF
  int v101[2]; // [rsp+1B0h] [rbp-298h]
  unsigned __int64 v102; // [rsp+1B8h] [rbp-290h] BYREF
  __int128 v103; // [rsp+1C0h] [rbp-288h] BYREF
  __int64 v104; // [rsp+1D0h] [rbp-278h]
  __int64 v105; // [rsp+1D8h] [rbp-270h]
  __int64 v106; // [rsp+1E0h] [rbp-268h] BYREF
  __int64 v107; // [rsp+1E8h] [rbp-260h] BYREF
  __int64 v108; // [rsp+1F0h] [rbp-258h] BYREF
  __int64 v109; // [rsp+1F8h] [rbp-250h] BYREF
  _OWORD v110[2]; // [rsp+200h] [rbp-248h] BYREF
  _BYTE v111[16]; // [rsp+220h] [rbp-228h] BYREF
  __int64 v112; // [rsp+230h] [rbp-218h]
  _QWORD v113[2]; // [rsp+240h] [rbp-208h] BYREF
  _BYTE v114[32]; // [rsp+250h] [rbp-1F8h] BYREF
  _QWORD v115[42]; // [rsp+270h] [rbp-1D8h] BYREF
  _BYTE v116[8]; // [rsp+3C0h] [rbp-88h] BYREF
  _BYTE v117[72]; // [rsp+3C8h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+0h]
  char v119; // [rsp+460h] [rbp+18h] BYREF

  v119 = a3;
  v5 = (char *)this + 8;
  v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 8);
  *(_QWORD *)&v87 = v6;
  *((_QWORD *)&v87 + 1) = *((_QWORD *)v5 + 2);
  try
  {
    v7 = split_extension(v62, &v87);
    wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
      v115,
      "ExtractArchive");
    v115[0] = &ArchiveFolderTelemetry::ExtractArchive::`vftable';
    v87 = *(_OWORD *)(v7 + 16);
    ArchiveFolderTelemetry::ExtractArchive::StartActivity(v115, &v87);
    v99[0] = 0;
    v99[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v99[0]) = 0;
    *(_QWORD *)&v87 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40);
    *((_QWORD *)&v87 + 1) = *((_QWORD *)this + 7);
    ExtendedLengthPath = MakeExtendedLengthPath(&v87, v99);
    v9 = ExtendedLengthPath;
    if ( ExtendedLengthPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x724,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)ExtendedLengthPath,
        fuStyle);
      std::wstring::_Tidy_deallocate(v99);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v115);
      return v9;
    }
    if ( v119 )
    {
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v99);
      v13 = SHCreateDirectory(0, v12);
      if ( v13 )
      {
        if ( v13 == 1223 )
        {
          v14 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x733,
                  (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                  (const char *)0x4C7,
                  fuStyle);
          std::wstring::_Tidy_deallocate(v99);
          ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v115);
          return v14;
        }
        else
        {
          ShellMessageBoxW(&_ImageBase, a2, (LPCWSTR)0x2942, (LPCWSTR)0x2941, 0x30u);
          wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
            v115,
            1);
          std::wstring::_Tidy_deallocate(v99);
          ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v115);
          return 1;
        }
      }
    }
    v62[0] = &v119;
    v62[1] = this;
    v63 = 1;
    ppv = 0;
    v15 = CoCreateInstance(&CLSID_ProgressDialog, 0, 3u, &GUID_0c9fb851_e5c9_43eb_a370_f0677b13874c, &ppv);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x744,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v15,
        fuStylea);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
LABEL_105:
      v63 = 0;
      _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(v62);
      std::wstring::_Tidy_deallocate(v99);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v115);
      return v16;
    }
    v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0, 0);
    v16 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x745,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v17,
        fuStylea);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    p_ppv = &ppv;
    v86 = 1;
    v88 = a2;
    *(_QWORD *)&v87 = 0;
    if ( ppv )
    {
      (**(void (__fastcall ***)(LPVOID, __int64 *, __int128 *))ppv)(ppv, winrt::impl::guid_v<IOleWindow>, &v87);
      v18 = v87;
    }
    else
    {
      v18 = 0;
    }
    if ( v18 )
    {
      v19 = (*(__int64 (__fastcall **)(__int64, HWND *))(*(_QWORD *)v18 + 24LL))(v18, &v88);
      v16 = v19;
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74E,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v19,
          fuStylea);
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v87);
        v20 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
        if ( v20 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x747,
            (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
            (const char *)(unsigned int)v20,
            fuStyleb);
        if ( ppv )
          winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
        goto LABEL_105;
      }
    }
    if ( v18 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v87);
    v21 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 48LL))(ppv, 2);
    v16 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x752,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v21,
        fuStylea);
      v22 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v22,
          fuStylec);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v23 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 2);
    v16 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x753,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v23,
        fuStylea);
      v24 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v24,
          fuStyled);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v91 = 0;
    v90 = 0;
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    v27 = ShellItemFromFileSystemPath(v25, v26, &v91, 0);
    if ( v27 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x758,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v27,
        fuStylea);
    if ( v90 )
      winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
    v28 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v99);
    v30 = ShellItemFromFileSystemPath(v28, v29, &v90, 0);
    if ( v30 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x759,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v30,
        fuStylea);
    v31 = (*(__int64 (__fastcall **)(LPVOID, void *, void *, _QWORD))(*(_QWORD *)ppv + 64LL))(ppv, v91, v90, 0);
    v16 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75A,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v31,
        fuStylea);
      if ( v90 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
      if ( v91 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v91);
      v32 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v32 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v32,
          fuStylee);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v100 = 0;
    *(_QWORD *)v101 = 0;
    v102 = 0;
    *(_QWORD *)&v87 = &v100;
    *((_QWORD *)&v87 + 1) = &v102;
    v33 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    enumerate_archive<_lambda_68a5e7536d1cd7d4dc30d39e1e7eeabe_>(v33);
    v113[0] = 0;
    v113[1] = 0;
    fuStylef = v101[0];
    v34 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppv + 56LL))(
            ppv,
            0,
            *(_QWORD *)v101,
            0);
    v16 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x772,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v34,
        fuStylef);
      if ( v90 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
      if ( v91 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v91);
      v35 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v35 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v35,
          fuStyleg);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v36 = 1;
    if ( !*(_QWORD *)v101 )
      v36 = 17;
    v37 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 48LL))(ppv, v36);
    v16 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77B,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v37,
        fuStylef);
      if ( v90 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
      if ( v91 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v91);
      v38 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v38 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v38,
          fuStyleh);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    std::wstring::wstring(v111, v99);
    v106 = v112;
    std::wstring::wstring(v114, v99);
    v103 = 0;
    v104 = 0;
    v105 = 7;
    LOWORD(v103) = 0;
    *(_QWORD *)&v87 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    *((_QWORD *)&v87 + 1) = *((_QWORD *)v5 + 2);
    v39 = MakeExtendedLengthPath(&v87, &v103);
    v16 = v39;
    if ( v39 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x78A,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v39,
        fuStylef);
      std::wstring::_Tidy_deallocate(&v103);
      std::wstring::_Tidy_deallocate(v114);
      std::wstring::_Tidy_deallocate(v111);
      if ( v90 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
      if ( v91 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v91);
      v40 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v40 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v40,
          fuStylei);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    std::wstring::push_back(&v103);
    v107 = v104;
    v109 = 0;
    v108 = 0;
    v97 = 0;
    v98 = 0;
    v95 = 0;
    v96 = 0;
    *(_QWORD *)&v87 = v102;
    if ( v102 )
    {
      if ( v102 > 0x38E38E38E38E38ELL )
        std::vector<std::basic_string_view<unsigned short>>::_Xlength();
      std::vector<DeferredPropertyUpdates>::_Reallocate<0>(&v95, &v87);
    }
    v110[0] = 0;
    v110[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v110[0]) = 0;
    v41 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    v42 = PrepareZoneIdentifierString(v41, (__int64)v110);
    v16 = v42;
    if ( v42 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7A8,
        (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
        (const char *)(unsigned int)v42,
        fuStylef);
      std::string::_Tidy_deallocate(v110);
      if ( (_QWORD)v95 )
      {
        std::_Destroy_range<std::allocator<DeferredPropertyUpdates>>(v95, *((_QWORD *)&v95 + 1));
        std::_Deallocate<16>(v95, 8 * ((v96 - (__int64)v95) >> 3));
        v95 = 0;
        v96 = 0;
      }
      if ( (_QWORD)v97 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v97, *((_QWORD *)&v97 + 1));
        std::_Deallocate<16>(v97, (v98 - v97) & 0xFFFFFFFFFFFFFFE0uLL);
        v97 = 0;
        v98 = 0;
      }
      std::wstring::_Tidy_deallocate(&v103);
      std::wstring::_Tidy_deallocate(v114);
      std::wstring::_Tidy_deallocate(v111);
      if ( v90 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
      if ( v91 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v91);
      v43 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v43 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v43,
          fuStylej);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      goto LABEL_105;
    }
    v94 = 0;
    v92 = 1;
    v93 = 0;
    UserConfirmations::UserConfirmations((UserConfirmations *)v116);
    v64 = &v92;
    v65 = this;
    v66 = v111;
    v67 = &v106;
    v68 = &v103;
    v69 = &v107;
    v70 = &v97;
    v71 = &v108;
    v72 = &v109;
    v73 = &ppv;
    v74 = &v94;
    v75 = &v100;
    v76 = v113;
    v77 = v114;
    v78 = &v93;
    v79 = &v95;
    v80 = v110;
    v81 = v116;
    v82 = &v88;
    v83 = v115;
    v84 = v99;
    v44 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
    enumerate_archive<_lambda_35696a5ea3ec76acae5d3e2770fb84e0_>(v44);
    wil::ActivityBase<ArchiveFolderTelemetry,1,35184372088832,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v115,
      (unsigned int)v94);
    v48 = v94;
    if ( v94 >= 0 )
    {
      ApplyDeferredUpdates(&v95, v45, v46, v47);
      v63 = 0;
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v117);
      std::string::_Tidy_deallocate(v110);
      if ( (_QWORD)v95 )
      {
        std::_Destroy_range<std::allocator<DeferredPropertyUpdates>>(v95, *((_QWORD *)&v95 + 1));
        std::_Deallocate<16>(v95, 8 * ((v96 - (__int64)v95) >> 3));
        v95 = 0;
        v96 = 0;
      }
      if ( (_QWORD)v97 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v97, *((_QWORD *)&v97 + 1));
        std::_Deallocate<16>(v97, (v98 - v97) & 0xFFFFFFFFFFFFFFE0uLL);
        v97 = 0;
        v98 = 0;
      }
      std::wstring::_Tidy_deallocate(&v103);
      std::wstring::_Tidy_deallocate(v114);
      std::wstring::_Tidy_deallocate(v111);
      if ( v90 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
      if ( v91 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v91);
      v50 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v50 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v50,
          fuStylef);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      std::wstring::_Tidy_deallocate(v99);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v115);
      result = 0;
    }
    else
    {
      std::_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>::~_Hash<std::_Uset_traits<long,std::_Uhash_compare<long,std::hash<long>,std::equal_to<long>>,std::allocator<long>,0>>(v117);
      std::string::_Tidy_deallocate(v110);
      if ( (_QWORD)v95 )
      {
        std::_Destroy_range<std::allocator<DeferredPropertyUpdates>>(v95, *((_QWORD *)&v95 + 1));
        std::_Deallocate<16>(v95, 8 * ((v96 - (__int64)v95) >> 3));
        v95 = 0;
        v96 = 0;
      }
      if ( (_QWORD)v97 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v97, *((_QWORD *)&v97 + 1));
        std::_Deallocate<16>(v97, (v98 - v97) & 0xFFFFFFFFFFFFFFE0uLL);
        v97 = 0;
        v98 = 0;
      }
      std::wstring::_Tidy_deallocate(&v103);
      std::wstring::_Tidy_deallocate(v114);
      std::wstring::_Tidy_deallocate(v111);
      if ( v90 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v90);
      if ( v91 )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&v91);
      v49 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv);
      if ( v49 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x747,
          (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
          (const char *)(unsigned int)v49,
          fuStylef);
      if ( ppv )
        winrt::com_ptr<IShellFolder2>::unconditional_release_ref(&ppv);
      v63 = 0;
      _lambda_a43f877cf21f9886dbe379087b0ce961_::operator()(v62);
      std::wstring::_Tidy_deallocate(v99);
      ArchiveFolderTelemetry::ExtractArchive::~ExtractArchive((ArchiveFolderTelemetry::ExtractArchive *)v115);
      result = v48;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x98A,
                           (unsigned int)"shell\\ext\\zip\\archive\\archiveextract.cpp",
                           v10);
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
