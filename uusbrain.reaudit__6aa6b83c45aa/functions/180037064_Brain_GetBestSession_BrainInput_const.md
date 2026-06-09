# Brain::GetBestSession(BrainInput const &)

- ea: `0x180037064`
- end: `0x18003882f`
- name: `?GetBestSession@Brain@@SAPEAXAEBVBrainInput@@@Z`
- size: `6091`
- prototype: `void *__fastcall(const struct BrainInput *this)`
- caller_count: `2`
- callee_count: `59`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180036ca8`
- `0x180036e60`

## callees

- `0x180009c50`
- `0x180009e1c`
- `0x18000ab24`
- `0x18000ae24`
- `0x18000aea8`
- `0x18000af10`
- `0x18000deb8`
- `0x18000f610`
- `0x180010428`
- `0x18001052c`
- `0x18001be84`
- `0x180024a44`
- `0x180027184`
- `0x180027618`
- `0x180028728`
- `0x180028a44`
- `0x180029344`
- `0x1800295e8`
- `0x180029644`
- `0x1800296c0`
- `0x180032308`
- `0x180033e38`
- `0x180034504`
- `0x180035910`
- `0x18003593c`
- `0x180035954`
- `0x1800359ec`
- `0x180035b30`
- `0x180036948`
- `0x180036ab4`
- `0x180037064`
- `0x180038884`
- `0x180039398`
- `0x1800393d4`
- `0x1800394b8`
- `0x1800396d4`
- `0x180039904`
- `0x180039ee0`
- `0x18003a00c`
- `0x18003a204`
- `0x18003a2cc`
- `0x18003a7a8`
- `0x18003a884`
- `0x18003a910`
- `0x18003aa98`
- `0x18003c2c0`
- `0x18003c348`
- `0x18003c480`
- `0x18003c4e4`
- `0x18003c794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037507`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037507`

## string_xrefs

- `0x1800386af`: `Requesting specific brain when we already did on the previous call.`
- `0x180037242`: `attempting to load package that isn't in a versioned folder`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
const struct BrainInput *__fastcall Brain::GetBestSession(const struct BrainInput *this)
{
  __int64 ThisFolder; // rbx
  char v3; // al
  int v4; // r13d
  int v5; // r13d
  const wchar_t *v6; // rsi
  int v7; // edi
  __int64 v8; // r8
  int v9; // r13d
  Brain *v10; // rbx
  const wchar_t *v11; // r8
  const wchar_t *v12; // rcx
  const struct BrainInput *result; // rax
  int v14; // r13d
  char v15; // cl
  __int64 *v16; // rax
  int v17; // r13d
  char v18; // bl
  __int64 v19; // rdx
  __int64 v20; // rcx
  int v21; // r13d
  __int64 v22; // r9
  int v23; // r13d
  __int64 v24; // r8
  char v25; // dl
  const wchar_t *v26; // rsi
  const wchar_t *v27; // rax
  const void *p_Src; // r9
  __int64 v29; // rbx
  int v30; // r13d
  int v31; // eax
  Brain *v32; // rbx
  char v33; // cl
  __int64 v34; // rax
  char v35; // dl
  unsigned int v36; // r8d
  int v37; // r13d
  Brain *v38; // rbx
  PackageActivationData *v39; // r13
  int BaseLockFileName; // eax
  int v41; // edx
  Brain *v42; // rcx
  void *Interface; // rbx
  const wchar_t *v44; // rcx
  unsigned int v45; // eax
  PackageActivationData *v46; // r13
  int v47; // eax
  int v48; // edx
  Brain *v49; // rcx
  __int64 v50; // r9
  __int64 v51; // rcx
  __int64 v52; // rbx
  __int64 (__fastcall ***v53)(_QWORD, __int64 *, __int64, void **); // rbx
  __int64 (__fastcall *v54)(_QWORD, __int64 *, __int64, void **); // r13
  __int64 v55; // rsi
  int v56; // ebx
  PackageActivationData *v57; // r13
  int v58; // eax
  int v59; // edx
  Brain *v60; // rcx
  const wchar_t *v61; // rax
  int v62; // ebx
  PackageActivationData *v63; // rdi
  int v64; // eax
  int v65; // edx
  Brain *v66; // rcx
  const struct BrainInput *activeBrainSession; // rbx
  Brain *v68; // rbx
  PackageActivationData *v69; // rdi
  __int64 v70; // rax
  Brain *v71; // rcx
  const wchar_t *v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rax
  __int64 v77; // rax
  __int64 v78; // rax
  __int64 VersionString; // rax
  const wchar_t *v80; // rbx
  __int64 v81; // rax
  const wchar_t *v82; // rax
  __int64 v83; // rax
  const wchar_t *v84; // rbx
  __int64 v85; // rax
  const wchar_t *v86; // rax
  __int64 v87; // rbx
  const wchar_t *idCallerRaw; // rdi
  __int64 v89; // rcx
  __int64 pathCaller; // rax
  const struct BrainInput *v91; // rbx
  Brain *v92; // rcx
  struct UusPackage *v93; // [rsp+20h] [rbp-418h]
  char v94; // [rsp+40h] [rbp-3F8h]
  char v95; // [rsp+40h] [rbp-3F8h]
  LPVOID pv; // [rsp+48h] [rbp-3F0h] BYREF
  void *Src; // [rsp+50h] [rbp-3E8h] BYREF
  __int64 v98; // [rsp+58h] [rbp-3E0h]
  unsigned __int64 v99; // [rsp+60h] [rbp-3D8h]
  unsigned __int64 v100; // [rsp+68h] [rbp-3D0h]
  const struct BrainInput *v101; // [rsp+70h] [rbp-3C8h]
  __int64 *v102; // [rsp+80h] [rbp-3B8h] BYREF
  char v103; // [rsp+88h] [rbp-3B0h]
  int v104; // [rsp+89h] [rbp-3AFh]
  __int16 v105; // [rsp+8Dh] [rbp-3ABh]
  char v106; // [rsp+8Fh] [rbp-3A9h]
  _BYTE v107[40]; // [rsp+A0h] [rbp-398h] BYREF
  _BYTE v108[24]; // [rsp+C8h] [rbp-370h] BYREF
  _BYTE v109[24]; // [rsp+E0h] [rbp-358h] BYREF
  _BYTE v110[24]; // [rsp+F8h] [rbp-340h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+110h] [rbp-328h] BYREF
  Brain *v112; // [rsp+128h] [rbp-310h] BYREF
  void **v113; // [rsp+130h] [rbp-308h] BYREF
  _BYTE v114[32]; // [rsp+138h] [rbp-300h] BYREF
  __int64 v115; // [rsp+158h] [rbp-2E0h]
  void **v116; // [rsp+160h] [rbp-2D8h]
  _QWORD v117[2]; // [rsp+170h] [rbp-2C8h] BYREF
  char v118; // [rsp+180h] [rbp-2B8h]
  __int64 v119[2]; // [rsp+190h] [rbp-2A8h] BYREF
  _BYTE v120[24]; // [rsp+1B0h] [rbp-288h] BYREF
  __int64 *v121; // [rsp+1C8h] [rbp-270h]
  void (__fastcall **v122)(_QWORD, _QWORD); // [rsp+1E0h] [rbp-258h] BYREF
  char v123[48]; // [rsp+1E8h] [rbp-250h] BYREF
  __int64 v124; // [rsp+218h] [rbp-220h]
  char v125; // [rsp+238h] [rbp-200h]
  _QWORD v126[11]; // [rsp+240h] [rbp-1F8h] BYREF
  char v127; // [rsp+298h] [rbp-1A0h]
  const wchar_t *v128; // [rsp+2A0h] [rbp-198h] BYREF
  char v129; // [rsp+2A8h] [rbp-190h]
  char v130; // [rsp+2A9h] [rbp-18Fh]
  _QWORD v131[2]; // [rsp+2B0h] [rbp-188h] BYREF
  __int128 v132; // [rsp+2C0h] [rbp-178h] BYREF
  __int64 v133; // [rsp+2D0h] [rbp-168h]
  __int64 v134; // [rsp+2D8h] [rbp-160h]
  __int64 v135; // [rsp+2E0h] [rbp-158h]
  __int128 v136; // [rsp+2E8h] [rbp-150h] BYREF
  unsigned __int64 v137; // [rsp+2F8h] [rbp-140h]
  __int64 v138; // [rsp+300h] [rbp-138h]
  void (__fastcall **v139)(_QWORD, _QWORD); // [rsp+308h] [rbp-130h] BYREF
  char v140; // [rsp+318h] [rbp-120h]
  char v141[8]; // [rsp+3A0h] [rbp-98h] BYREF
  char v142[88]; // [rsp+3A8h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+0h]

  v101 = this;
  LODWORD(pv) = 0;
  ThisFolder = BrainUtils::GetThisFolder(&Src);
  UusPackage::FindRootPackageFolder(v119, ThisFolder, 1);
  if ( v120[0] )
  {
    UusPackage::UusPackage((UusPackage *)v126, (const struct std::filesystem::path *)v119);
    v3 = 1;
    v127 = 1;
    v4 = 48;
    if ( v120[0] )
    {
      std::wstring::_Tidy_deallocate(v119);
      v3 = v127;
    }
  }
  else
  {
    v3 = 0;
    v127 = 0;
    v4 = 16;
  }
  if ( !v3 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::__autoclassinit2(&v128);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(&v128);
    v73 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v131, L"Unable to locate package within ");
    v74 = std::wostream::operator<<(v73);
    v75 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v74, " parent folders of ");
    std::filesystem::operator<<<wchar_t,std::char_traits<wchar_t>>(v75, ThisFolder);
    v76 = std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::str(&v128, v119);
    v77 = UnicodeToMultiByte(&v102, v76);
    std::runtime_error::runtime_error(pExceptionObject, v77);
    throw (std::runtime_error *)pExceptionObject;
  }
  UusPackage::UusPackage((UusPackage *)&v113, (const struct UusPackage *)v126);
  v5 = v4 | 8;
  if ( v127 )
    (*(void (__fastcall **)(_QWORD *, _QWORD))v126[0])(v126, 0);
  std::wstring::_Tidy_deallocate(&Src);
  v112 = 0;
  v6 = &qword_180050DC0;
  if ( *((_QWORD *)this + 6) )
    v6 = (const wchar_t *)*((_QWORD *)this + 6);
  v7 = *((_DWORD *)this + 8);
  pv = operator new(0x1A0u);
  memset(pv, 0, 0x1A0u);
  v112 = Brain::Brain((Brain *)pv, v7, v8, v6, (const struct UusPackage *)&v113);
  v9 = v5 | 0x40;
  uus::UUSTracing::TraceLoggingInfo("Brain entered GetBestSession method. Recursion: %d", *((_DWORD *)this + 14));
  v10 = v112;
  if ( !*((_BYTE *)v112 + 216) && !*((_BYTE *)v112 + 217) && *((_DWORD *)this + 14) && !v118 )
  {
    v11 = (const wchar_t *)((char *)v112 + 104);
    if ( *((_QWORD *)v112 + 16) > 7u )
      v11 = *(const wchar_t **)v11;
    v12 = (const wchar_t *)((char *)v112 + 256);
    if ( *((_QWORD *)v112 + 35) > 7u )
      v12 = *(const wchar_t **)v12;
    uus::UndockedUpdateTelemetry::UusInvalidPackageIgnored(
      v12,
      0,
      v11,
      "attempting to load package that isn't in a versioned folder");
    if ( v112 )
      (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
    v113 = &UusPackage::`vftable';
    if ( v118 )
      (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
    v116 = &UusVersion::`vftable';
    if ( v115 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
    std::wstring::_Tidy_deallocate(v114);
    return 0;
  }
  try
  {
    (*(void (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2), v119);
    (*(void (__fastcall **)(_QWORD, void **, _QWORD))(**((_QWORD **)this + 2) + 16LL))(
      *((_QWORD *)this + 2),
      &Src,
      *((_QWORD *)this + 5));
    v14 = v9 | 0x180;
    v15 = 0;
    if ( (_BYTE)v99 )
    {
      v16 = (__int64 *)v98;
      v15 = 1;
    }
    else
    {
      v16 = (__int64 *)v101;
    }
    v102 = v16;
    v103 = v15;
    v104 = *(_DWORD *)((char *)&v119[1] + 1);
    v105 = *(_WORD *)((char *)&v119[1] + 5);
    v106 = HIBYTE(v119[1]);
    (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
      *((_QWORD *)this + 2),
      v107,
      *((_QWORD *)this + 5));
    v17 = v14 | 0x200;
    v18 = Brain::AllComponentsSupportedByPackage(v10, v107, &v102, v119);
    if ( (_BYTE)v99 )
      (*(void (__fastcall **)(void **, _QWORD))Src)(&Src, 0);
    std::_Tree<std::_Tmap_traits<std::wstring const,UusComponent,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,UusComponent>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,UusComponent,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,UusComponent>>,0>>(v119);
    if ( !v18 && !*((_BYTE *)v112 + 216) && *((_DWORD *)this + 14) )
    {
      (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
      v113 = &UusPackage::`vftable';
      if ( v118 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
      v116 = &UusVersion::`vftable';
      if ( v115 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
      std::wstring::_Tidy_deallocate(v114);
      return 0;
    }
    pv = 0;
    wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(
      &pv,
      v19,
      &_ImageBase);
    v119[0] = (__int64)pv;
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)pv + v20) );
    v119[1] = v20;
    std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(&Src, v119);
    v21 = v17 | 0x1800;
    if ( pv )
      CoTaskMemFree(pv);
    v22 = (*(__int64 (__fastcall **)(Brain *))(*(_QWORD *)v112 + 8LL))(v112);
    v119[0] = (__int64)&UusVersion::`vftable';
    v119[1] = v22;
    v23 = v21 | 0x403;
    LODWORD(pv) = v23;
    LOBYTE(v24) = *((_BYTE *)v112 + 217);
    v25 = *((_BYTE *)v112 + 216);
    v26 = &qword_180050DC0;
    v27 = &qword_180050DC0;
    if ( *((_QWORD *)this + 6) )
      v27 = (const wchar_t *)*((_QWORD *)this + 6);
    v128 = v27;
    v129 = v25;
    v130 = v24;
    v131[0] = &UusVersion::`vftable';
    v131[1] = v22;
    v132 = 0;
    v133 = 0;
    v134 = 7;
    LOWORD(v132) = 0;
    LODWORD(v135) = 0;
    v136 = 0;
    v137 = 0;
    v138 = 7;
    LOWORD(v136) = 0;
    v140 = 0;
    p_Src = &Src;
    if ( v100 > 7 )
      p_Src = Src;
    if ( v99 > 7 )
    {
      std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(&v136, v99, v24, p_Src);
    }
    else
    {
      v137 = v99;
      v29 = 2 * v99;
      memmove(&v136, p_Src, 2 * v99);
      *(_WORD *)((char *)&v136 + v29) = 0;
    }
    v30 = v23 | 4;
    LODWORD(pv) = v30;
    v31 = PayloadLoader::ValidateBinaryIfEnabled((PayloadLoader *)&v128);
    v32 = v112;
    if ( !v31 || *((_BYTE *)v112 + 216) || (v94 = 1, *((_BYTE *)v112 + 217)) )
      v94 = 0;
    if ( (v30 & 4) != 0 )
    {
      LOBYTE(v30) = v30 & 0xFB;
      if ( v140 )
        (*v139)(&v139, 0);
      std::wstring::_Tidy_deallocate(&v136);
      std::wstring::_Tidy_deallocate(&v132);
      v131[0] = &UusVersion::`vftable';
      v32 = v112;
    }
    if ( (v30 & 2) != 0 )
      LOBYTE(v30) = v30 & 0xFD;
    if ( (v30 & 1) != 0 )
    {
      std::wstring::_Tidy_deallocate(&Src);
      v32 = v112;
    }
    if ( v94 )
    {
      if ( v32 )
        (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v32 + 88LL))(v32, 1);
      v113 = &UusPackage::`vftable';
      if ( v118 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
      v116 = &UusVersion::`vftable';
      if ( v115 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
LABEL_107:
      std::wstring::_Tidy_deallocate(v114);
      return 0;
    }
    v102 = (__int64 *)&v128;
    LOBYTE(v136) = 0;
    if ( *((_BYTE *)this + 144) )
    {
      pv = &v128;
      std::wstring::wstring(&v128, (char *)this + 72);
      std::vector<enum UusCapability>::vector<enum UusCapability>(&v132, (char *)this + 104);
      LODWORD(v134) = *((_DWORD *)this + 32);
      v135 = *((_QWORD *)this + 17);
      LOBYTE(v136) = 1;
    }
    (*(void (__fastcall **)(_QWORD, void **, _QWORD))(**((_QWORD **)this + 2) + 16LL))(
      *((_QWORD *)this + 2),
      &Src,
      *((_QWORD *)this + 5));
    v33 = 0;
    if ( (_BYTE)v99 )
    {
      v34 = v98;
      v33 = 1;
    }
    else
    {
      v34 = (__int64)v102;
    }
    v119[0] = v34;
    LOBYTE(v119[1]) = v33;
    (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
      *((_QWORD *)this + 2),
      v107,
      *((_QWORD *)this + 5));
    v35 = Brain::ComponentSupportedByPackage(v32, v107, v119, &v128);
    v95 = v35;
    if ( (_BYTE)v99 )
    {
      (*(void (__fastcall **)(void **, _QWORD))Src)(&Src, 0);
      v35 = v95;
    }
    v37 = *((_DWORD *)this + 9);
    v38 = v112;
    if ( (v37 & 8) != 0 )
    {
      if ( *((_QWORD *)this + 6) )
        v26 = (const wchar_t *)*((_QWORD *)this + 6);
      v39 = PackageActivationData::PackageActivationData(
              (PackageActivationData *)v119,
              *((_BYTE *)v112 + 216),
              (const struct UusPackage *)&v113);
      v102 = (__int64 *)v107;
      (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
        *((_QWORD *)this + 2),
        v107,
        *((_QWORD *)this + 5));
      BaseLockFileName = BrainInput::get_BaseLockFileName(this, &Src);
      LOBYTE(v41) = v95;
      Brain::AcquireLock_OnlyIfUsAndSupported(
        (_DWORD)v38,
        v41,
        BaseLockFileName,
        (unsigned int)v107,
        (__int64)v39,
        (__int64)"FlagCallerInPackage",
        (__int64)v26);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(v120);
      std::wstring::_Tidy_deallocate(v119);
      v42 = v112;
      v112 = 0;
      Interface = Brain::GetInterface(v42);
      if ( v112 )
        (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
      v113 = &UusPackage::`vftable';
      if ( v118 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
      v116 = &UusVersion::`vftable';
      if ( v115 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
LABEL_156:
      std::wstring::_Tidy_deallocate(v114);
      return (const struct BrainInput *)Interface;
    }
    if ( *((_DWORD *)this + 14) )
    {
      v44 = (const wchar_t *)((char *)v112 + 104);
      if ( *((_QWORD *)v112 + 16) > 7u )
        v44 = *(const wchar_t **)v44;
      v45 = *((_DWORD *)this + 16);
      if ( v45 > 0x903 )
      {
        if ( v44 )
        {
          uus::UndockedUpdateTelemetry::UusIgnoringOlderPatchedPackage(v44, v45, v36);
          v38 = v112;
        }
        if ( v38 )
          (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v38 + 88LL))(v38, 1);
        v113 = &UusPackage::`vftable';
        if ( v118 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
        v116 = &UusVersion::`vftable';
        if ( v115 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
        goto LABEL_107;
      }
    }
    if ( v35 )
    {
      if ( *((int *)this + 14) < 0 )
      {
        if ( *((_QWORD *)this + 6) )
          v26 = (const wchar_t *)*((_QWORD *)this + 6);
        v46 = PackageActivationData::PackageActivationData(
                (PackageActivationData *)v119,
                *((_BYTE *)v112 + 216),
                (const struct UusPackage *)&v113);
        v102 = (__int64 *)v107;
        (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
          *((_QWORD *)this + 2),
          v107,
          *((_QWORD *)this + 5));
        v47 = BrainInput::get_BaseLockFileName(this, &Src);
        LOBYTE(v48) = v95;
        Brain::AcquireLock_OnlyIfUsAndSupported(
          (_DWORD)v38,
          v48,
          v47,
          (unsigned int)v107,
          (__int64)v46,
          (__int64)"SpecificVerRequired",
          (__int64)v26);
        std::wstring::_Tidy_deallocate(&Src);
        std::wstring::_Tidy_deallocate(v120);
        std::wstring::_Tidy_deallocate(v119);
        v49 = v112;
        v112 = 0;
        Interface = Brain::GetInterface(v49);
        if ( v112 )
          (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
        v113 = &UusPackage::`vftable';
        if ( v118 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
        v116 = &UusVersion::`vftable';
        if ( v115 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
        goto LABEL_156;
      }
    }
    else if ( *((_DWORD *)this + 14) )
    {
      if ( v112 )
        (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
      v113 = &UusPackage::`vftable';
      if ( v118 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
      v116 = &UusVersion::`vftable';
      if ( v115 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
      goto LABEL_107;
    }
    (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
      *((_QWORD *)this + 2),
      v107,
      *((_QWORD *)this + 5));
    LOBYTE(v50) = (v37 & 2) != 0;
    Brain::FindRequiredPackage(v51, &v122, v107, v50);
    if ( v125 )
    {
      v52 = v124;
      if ( (*(__int64 (__fastcall **)(Brain *))(*(_QWORD *)v112 + 8LL))(v112) == v52 )
      {
        v56 = (int)v112;
        if ( *((_QWORD *)this + 6) )
          v26 = (const wchar_t *)*((_QWORD *)this + 6);
        v57 = PackageActivationData::PackageActivationData(
                (PackageActivationData *)&v128,
                *((_BYTE *)v112 + 216),
                (const struct UusPackage *)&v113);
        v102 = v119;
        (*(void (__fastcall **)(_QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
          *((_QWORD *)this + 2),
          v119,
          *((_QWORD *)this + 5));
        v58 = BrainInput::get_BaseLockFileName(this, &Src);
        LOBYTE(v59) = v95;
        Brain::AcquireLock_OnlyIfUsAndSupported(
          v56,
          v59,
          v58,
          (unsigned int)v119,
          (__int64)v57,
          (__int64)"CallerFromRequiredPackage",
          (__int64)v26);
        std::wstring::_Tidy_deallocate(&Src);
        std::wstring::_Tidy_deallocate(&v132);
        std::wstring::_Tidy_deallocate(&v128);
        v60 = v112;
        v112 = 0;
        Interface = Brain::GetInterface(v60);
        if ( v125 )
          (*v122)(&v122, 0);
        if ( v112 )
          (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
        v113 = &UusPackage::`vftable';
        if ( v118 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
        v116 = &UusVersion::`vftable';
        if ( v115 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
      }
      else
      {
        if ( !v125 )
          std::_Throw_bad_optional_access();
        v53 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64, void **))*((_QWORD *)this + 2);
        v54 = **v53;
        if ( *((int *)this + 14) < 0 )
        {
          std::runtime_error::runtime_error(
            (std::runtime_error *)v108,
            "Requesting specific brain when we already did on the previous call.");
          throw (std::runtime_error *)v108;
        }
        v99 = 2307;
        Src = (void *)24;
        v98 = 0x2FFFFFFFFLL;
        v55 = *((_QWORD *)this + 3);
        std::wstring::wstring(v119, v123);
        Interface = (void *)v54(v53, v119, v55, &Src);
        std::wstring::_Tidy_deallocate(v119);
        if ( !Interface )
        {
          v78 = std::wstreambuf::setbuf(&v122);
          VersionString = UusPackage::GetVersionString(v78, &Src);
          v80 = (const wchar_t *)std::wstring::c_str(VersionString);
          v81 = std::chrono::duration<__int64,std::ratio<1,1000>>::count(&v112);
          v82 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v81 + 32LL))(v81);
          uus::UndockedUpdateTelemetry::UusFailedToLoadRequiredPackage(v82, v80);
          std::filesystem::path::~path((std::filesystem::path *)&Src);
          uus::UUSTracing::TraceLoggingError("Unable to load brain from required package.");
          std::runtime_error::runtime_error((std::runtime_error *)v109, "Unable to load brain from required package.");
          throw (std::runtime_error *)v109;
        }
        if ( v125 )
          (*v122)(&v122, 0);
        if ( v112 )
          (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
        v113 = &UusPackage::`vftable';
        if ( v118 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
        v116 = &UusVersion::`vftable';
        if ( v115 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
      }
      goto LABEL_156;
    }
    v119[0] = (__int64)off_1800507C8;
    v119[1] = (__int64)&v112;
    v121 = v119;
    Brain::FindBetterPackage((UusPackage *)v126, (__int64)v119);
    if ( v127 )
    {
      v61 = (const wchar_t *)(*(__int64 (__fastcall **)(Brain *))(*(_QWORD *)v112 + 32LL))(v112);
      if ( !v127 )
        std::_Throw_bad_optional_access();
      Interface = BrainInput::get_betterBrainSession(this, (const struct UusPackage *)v126, v61);
      if ( Interface )
      {
        if ( v127 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v126[0])(v126, 0);
        if ( v125 )
          (*v122)(&v122, 0);
        if ( v112 )
          (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
        v113 = &UusPackage::`vftable';
        if ( v118 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v117[0])(v117, 0);
        v116 = &UusVersion::`vftable';
        if ( v115 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v115 + 192LL))(v115, 1);
        goto LABEL_156;
      }
      v62 = (int)v112;
      if ( *((_QWORD *)this + 6) )
        v26 = (const wchar_t *)*((_QWORD *)this + 6);
      v63 = PackageActivationData::PackageActivationData(
              (PackageActivationData *)&v128,
              *((_BYTE *)v112 + 216),
              (const struct UusPackage *)&v113);
      v102 = (__int64 *)v107;
      (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD))(**((_QWORD **)this + 2) + 8LL))(
        *((_QWORD *)this + 2),
        v107,
        *((_QWORD *)this + 5));
      v64 = BrainInput::get_BaseLockFileName(this, &Src);
      LOBYTE(v65) = v95;
      Brain::AcquireLock_OnlyIfUsAndSupported(
        v62,
        v65,
        v64,
        (unsigned int)v107,
        (__int64)v63,
        (__int64)"BetterBrainNotSupported",
        (__int64)v26);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(&v132);
      std::wstring::_Tidy_deallocate(&v128);
      v66 = v112;
      v112 = 0;
      activeBrainSession = (const struct BrainInput *)Brain::GetInterface(v66);
      if ( v127 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))v126[0])(v126, 0);
      if ( v125 )
        (*v122)(&v122, 0);
      if ( v112 )
        (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
    }
    else
    {
      v68 = v112;
      v69 = PackageActivationData::PackageActivationData(
              (PackageActivationData *)&v128,
              *((_BYTE *)v112 + 216),
              (const struct UusPackage *)&v113);
      v70 = BrainInput::get_BaseLockFileName(this, &Src);
      LOBYTE(v68) = Brain::AcquireLock_CheckIfUs(v68, v70, v69);
      std::wstring::_Tidy_deallocate(&Src);
      std::wstring::_Tidy_deallocate(&v132);
      std::wstring::_Tidy_deallocate(&v128);
      v71 = v112;
      if ( (_BYTE)v68 )
      {
        v112 = 0;
        activeBrainSession = (const struct BrainInput *)Brain::GetInterface(v71);
        if ( v127 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v126[0])(v126, 0);
        if ( v125 )
          (*v122)(&v122, 0);
        if ( v112 )
          (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
      }
      else
      {
        if ( !*((_QWORD *)v112 + 48) )
        {
          v72 = (const wchar_t *)(*(__int64 (**)(void))(*(_QWORD *)v112 + 32LL))();
          uus::UndockedUpdateTelemetry::UusIgnoringActivePackageVersionIfZero(v72);
          if ( v127 )
            (*(void (__fastcall **)(_QWORD *, _QWORD))v126[0])(v126, 0);
          if ( v125 )
            (*v122)(&v122, 0);
          if ( v112 )
            (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
          UusPackage::~UusPackage((UusPackage *)&v113);
          return 0;
        }
        Brain::GetActivePackage(v112, v141);
        std::wstring::wstring(&Src, v142);
        UusPackage::UusPackage((UusPackage *)&v128, (const struct std::filesystem::path *)&Src);
        activeBrainSession = (const struct BrainInput *)BrainInput::get_activeBrainSession(
                                                          this,
                                                          (const struct UusPackage *)&v128);
        UusPackage::~UusPackage((UusPackage *)&v128);
        std::wstring::_Tidy_deallocate(&Src);
        if ( !activeBrainSession )
        {
          v83 = UusPackage::GetVersionString(v141, &Src);
          v84 = (const wchar_t *)std::wstring::c_str(v83);
          v85 = std::chrono::duration<__int64,std::ratio<1,1000>>::count(&v112);
          v86 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v85 + 32LL))(v85);
          uus::UndockedUpdateTelemetry::UusFailedToLoadActivePackage(v86, v84);
          std::filesystem::path::~path((std::filesystem::path *)&Src);
          uus::UUSTracing::TraceLoggingError("Unable to load brain from active locked package.");
          v87 = std::chrono::duration<__int64,std::ratio<1,1000>>::count(&v112);
          idCallerRaw = BrainInput::get_idCallerRaw(this);
          pathCaller = BrainInput::get_pathCaller(v89, v107);
          Brain::AbandonLock(v87, pathCaller, "ActiveFailedLoad", idCallerRaw);
          std::runtime_error::runtime_error(
            (std::runtime_error *)v110,
            "Unable to load brain from active locked package.");
          throw (std::runtime_error *)v110;
        }
        UusPackage::~UusPackage((UusPackage *)v141);
        if ( v127 )
          (*(void (__fastcall **)(_QWORD *, _QWORD))v126[0])(v126, 0);
        if ( v125 )
          (*v122)(&v122, 0);
        if ( v112 )
          (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
      }
    }
    UusPackage::~UusPackage((UusPackage *)&v113);
    result = activeBrainSession;
  }
  catch ( ... )
  {
    v91 = v101;
    LODWORD(v93) = *((_DWORD *)v101 + 14);
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0xE2,
      (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\Brain.cpp",
      "Failed to determine if this was the correct brain (recursion=%d)",
      (const char *)v93);
    if ( *((_DWORD *)v91 + 14) )
      throw;
    v92 = v112;
    v112 = 0;
    v101 = (const struct BrainInput *)Brain::GetInterface(v92);
    if ( v112 )
      (*(void (__fastcall **)(Brain *, __int64))(*(_QWORD *)v112 + 88LL))(v112, 1);
    UusPackage::~UusPackage((UusPackage *)&v113);
    return v101;
  }
  return result;
}

```

## disassembly

```asm
0x180037064  mov     [rsp+arg_8], rbx
0x180037069  mov     [rsp+arg_10], rsi
0x18003706e  push    rdi
0x18003706f  push    r12
0x180037071  push    r13
0x180037073  push    r14
0x180037075  push    r15
0x180037077  sub     rsp, 410h
0x18003707e  mov     rax, cs:__security_cookie
0x180037085  xor     rax, rsp
0x180037088  mov     [rsp+438h+var_38], rax
0x180037090  mov     r15, rcx
0x180037093  mov     [rsp+438h+var_3C8], rcx
0x180037098  xor     r14d, r14d
0x18003709b  mov     dword ptr [rsp+438h+pv], r14d
0x1800370a0  lea     rcx, [rsp+438h+Src]
0x1800370a5  call    ?GetThisFolder@BrainUtils@@SA?AVpath@filesystem@std@@XZ; BrainUtils::GetThisFolder(void)
0x1800370aa  mov     rbx, rax
0x1800370ad  lea     r12d, [r14+1]
0x1800370b1  mov     r8d, r12d
0x1800370b4  mov     rdx, rax
0x1800370b7  lea     rcx, [rsp+438h+var_2A8]
0x1800370bf  call    ?FindRootPackageFolder@UusPackage@@CA?AV?$optional@Vpath@filesystem@std@@@std@@AEBVpath@filesystem@3@I@Z; UusPackage::FindRootPackageFolder(std::filesystem::path const &,uint)
0x1800370c4  nop
0x1800370c5  cmp     [rsp+438h+var_288], r14b
0x1800370cd  jnz     short loc_1800370DF
0x1800370cf  mov     al, r14b
0x1800370d2  mov     [rsp+438h+var_1A0], al
0x1800370d9  lea     r13d, [r14+10h]
0x1800370dd  jmp     short loc_180037122
0x1800370df  lea     rdx, [rsp+438h+var_2A8]; struct std::filesystem::path *
0x1800370e7  lea     rcx, [rsp+438h+var_1F8]; this
0x1800370ef  call    ??0UusPackage@@QEAA@AEBVpath@filesystem@std@@@Z; UusPackage::UusPackage(std::filesystem::path const &)
0x1800370f4  mov     al, r12b
0x1800370f7  mov     [rsp+438h+var_1A0], al
0x1800370fe  mov     r13d, 30h ; '0'
0x180037104  cmp     [rsp+438h+var_288], r14b
0x18003710c  jz      short loc_180037122
0x18003710e  lea     rcx, [rsp+438h+var_2A8]
0x180037116  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003711b  mov     al, [rsp+438h+var_1A0]
0x180037122  test    al, al
0x180037124  jz      loc_18003860D
0x18003712a  lea     rdx, [rsp+438h+var_1F8]; struct UusPackage *
0x180037132  lea     rcx, [rsp+438h+var_308]; this
0x18003713a  call    ??0UusPackage@@QEAA@AEBV0@@Z; UusPackage::UusPackage(UusPackage const &)
0x18003713f  or      r13d, 8
0x180037143  cmp     [rsp+438h+var_1A0], r14b
0x18003714b  jz      short loc_180037168
0x18003714d  mov     rax, [rsp+438h+var_1F8]
0x180037155  xor     edx, edx
0x180037157  lea     rcx, [rsp+438h+var_1F8]
0x18003715f  mov     rax, [rax]
0x180037162  call    _guard_dispatch_icall
0x180037167  nop
0x180037168  lea     rcx, [rsp+438h+Src]
0x18003716d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037172  mov     [rsp+438h+var_310], r14
0x18003717a  lea     rsi, qword_180050DC0
0x180037181  cmp     [r15+30h], r14
0x180037185  cmovnz  rsi, [r15+30h]
0x18003718a  mov     edi, [r15+20h]
0x18003718e  mov     ecx, 1A0h; Size
0x180037193  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180037198  mov     rbx, rax
0x18003719b  mov     [rsp+438h+pv], rax
0x1800371a0  xor     edx, edx; Val
0x1800371a2  mov     r8d, 1A0h; Size
0x1800371a8  mov     rcx, rax; void *
0x1800371ab  call    memset
0x1800371b0  lea     rax, [rsp+438h+var_308]
0x1800371b8  mov     [rsp+438h+var_418], rax; struct UusPackage *
0x1800371bd  mov     r9, rsi; wchar_t *
0x1800371c0  mov     edx, edi; unsigned int
0x1800371c2  mov     rcx, rbx; this
0x1800371c5  call    ??0Brain@@QEAA@I_NPEB_WAEBVUusPackage@@@Z; Brain::Brain(uint,bool,wchar_t const *,UusPackage const &)
0x1800371ca  nop
0x1800371cb  mov     [rsp+438h+var_310], rax
0x1800371d3  or      r13d, 40h
0x1800371d7  mov     edx, [r15+38h]
0x1800371db  lea     rcx, aBrainEnteredGe; "Brain entered GetBestSession method. Re"...
0x1800371e2  call    ?TraceLoggingInfo@UUSTracing@uus@@SAXPEBDZZ; uus::UUSTracing::TraceLoggingInfo(char const *,...)
0x1800371e7  nop
0x1800371e8  mov     rbx, [rsp+438h+var_310]
0x1800371f0  mov     dl, [rbx+0D8h]; bool
0x1800371f6  test    dl, dl
0x1800371f8  jnz     loc_1800372E1
0x1800371fe  cmp     [rbx+0D9h], r14b
0x180037205  jnz     loc_1800372E1
0x18003720b  cmp     [r15+38h], r14d
0x18003720f  jz      loc_1800372E1
0x180037215  cmp     [rsp+438h+var_2B8], r14b
0x18003721d  jnz     loc_1800372E1
0x180037223  lea     r8, [rbx+68h]
0x180037227  cmp     qword ptr [r8+18h], 7
0x18003722c  jbe     short loc_180037231
0x18003722e  mov     r8, [r8]; wchar_t *
0x180037231  lea     rcx, [rbx+100h]
0x180037238  cmp     qword ptr [rcx+18h], 7
0x18003723d  jbe     short loc_180037242
0x18003723f  mov     rcx, [rcx]; wchar_t *
0x180037242  lea     r9, aAttemptingToLo; "attempting to load package that isn't i"...
0x180037249  call    ?UusInvalidPackageIgnored@UndockedUpdateTelemetry@uus@@SAXPEB_W_N0PEBD@Z; uus::UndockedUpdateTelemetry::UusInvalidPackageIgnored(wchar_t const *,bool,wchar_t const *,char const *)
0x18003724e  nop
0x18003724f  mov     rcx, [rsp+438h+var_310]
0x180037257  test    rcx, rcx
0x18003725a  jz      short loc_18003726C
0x18003725c  mov     rax, [rcx]
0x18003725f  mov     edx, r12d
0x180037262  mov     rax, [rax+58h]
0x180037266  call    _guard_dispatch_icall
0x18003726b  nop
0x18003726c  lea     rax, ??_7UusPackage@@6B@; const UusPackage::`vftable'
0x180037273  mov     [rsp+438h+var_308], rax
0x18003727b  cmp     [rsp+438h+var_2B8], r14b
0x180037283  jz      short loc_18003729F
0x180037285  mov     rax, [rsp+438h+var_2C8]
0x18003728d  xor     edx, edx
0x18003728f  lea     rcx, [rsp+438h+var_2C8]
0x180037297  mov     rax, [rax]
0x18003729a  call    _guard_dispatch_icall
0x18003729f  lea     rdi, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x1800372a6  mov     [rsp+438h+var_2D8], rdi
0x1800372ae  mov     rcx, [rsp+438h+var_2E0]
0x1800372b6  test    rcx, rcx
0x1800372b9  jz      short loc_1800372CD
0x1800372bb  mov     rax, [rcx]
0x1800372be  mov     edx, r12d
0x1800372c1  mov     rax, [rax+0C0h]
0x1800372c8  call    _guard_dispatch_icall
0x1800372cd  lea     rcx, [rsp+438h+var_300]
0x1800372d5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800372da  xor     eax, eax
0x1800372dc  jmp     loc_1800385E0
0x1800372e1  mov     rcx, [r15+10h]
0x1800372e5  mov     rax, [rcx]
0x1800372e8  lea     rdx, [rsp+438h+var_2A8]
0x1800372f0  mov     rax, [rax+20h]
0x1800372f4  call    _guard_dispatch_icall
0x1800372f9  bts     r13d, 8
0x1800372fe  mov     rcx, [r15+10h]
0x180037302  mov     rax, [rcx]
0x180037305  mov     r8, [r15+28h]
0x180037309  lea     rdx, [rsp+438h+Src]
0x18003730e  mov     rax, [rax+10h]
0x180037312  call    _guard_dispatch_icall
0x180037317  bts     r13d, 7
0x18003731c  mov     cl, r14b
0x18003731f  cmp     byte ptr [rsp+438h+var_3D8], r14b
0x180037324  jz      short loc_180037330
0x180037326  mov     rax, [rsp+438h+var_3E0]
0x18003732b  mov     cl, r12b
0x18003732e  jmp     short loc_180037335
0x180037330  mov     rax, [rsp+438h+var_3C8]
0x180037335  mov     qword ptr [rsp+438h+var_3B8], rax
0x18003733d  mov     byte ptr [rsp+438h+var_3B8+8], cl
0x180037344  mov     eax, dword ptr [rsp+438h+var_2A8+9]
0x18003734b  mov     dword ptr [rsp+438h+var_3B8+9], eax
0x180037352  movzx   eax, word ptr [rsp+438h+var_2A8+0Dh]
0x18003735a  mov     word ptr [rsp+438h+var_3B8+0Dh], ax
0x180037362  mov     al, byte ptr [rsp+438h+var_2A8+0Fh]
0x180037369  mov     byte ptr [rsp+438h+var_3B8+0Fh], al
0x180037370  mov     rcx, [r15+10h]
0x180037374  mov     rax, [rcx]
0x180037377  mov     r8, [r15+28h]
0x18003737b  lea     rdx, [rsp+438h+var_398]
0x180037383  mov     rax, [rax+8]
0x180037387  call    _guard_dispatch_icall
0x18003738c  bts     r13d, 9
0x180037391  movups  xmm0, [rsp+438h+var_3B8]
0x180037399  movdqu  [rsp+438h+var_3B8], xmm0
0x1800373a2  lea     r9, [rsp+438h+var_2A8]
0x1800373aa  lea     r8, [rsp+438h+var_3B8]
0x1800373b2  lea     rdx, [rsp+438h+var_398]
0x1800373ba  mov     rcx, rbx
0x1800373bd  call    ?AllComponentsSupportedByPackage@Brain@@AEAA_NV?$optional@Vpath@filesystem@std@@@std@@V?$optional@_K@3@AEBV?$map@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@2@@3@@Z; Brain::AllComponentsSupportedByPackage(std::optional<std::filesystem::path>,std::optional<unsigned __int64>,std::map<std::wstring const,UusComponent> const &)
0x1800373c2  mov     bl, al
0x1800373c4  cmp     byte ptr [rsp+438h+var_3D8], r14b
0x1800373c9  jz      short loc_1800373E0
0x1800373cb  mov     rcx, [rsp+438h+Src]
0x1800373d0  mov     rax, [rcx]
0x1800373d3  xor     edx, edx
0x1800373d5  lea     rcx, [rsp+438h+Src]
0x1800373da  call    _guard_dispatch_icall
0x1800373df  nop
0x1800373e0  lea     rcx, [rsp+438h+var_2A8]
0x1800373e8  call    ??1?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@U?$less@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring const,UusComponent,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,UusComponent>>,0>>::~_Tree<std::_Tmap_traits<std::wstring const,UusComponent,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,UusComponent>>,0>>(void)
0x1800373ed  test    bl, bl
0x1800373ef  jnz     loc_180037499
0x1800373f5  mov     rcx, [rsp+438h+var_310]
0x1800373fd  cmp     [rcx+0D8h], r14b
0x180037404  jnz     loc_180037499
0x18003740a  cmp     [r15+38h], r14d
0x18003740e  jz      loc_180037499
0x180037414  mov     rax, [rcx]
0x180037417  mov     edx, r12d
0x18003741a  mov     rax, [rax+58h]
0x18003741e  call    _guard_dispatch_icall
0x180037423  nop
0x180037424  lea     rax, ??_7UusPackage@@6B@; const UusPackage::`vftable'
0x18003742b  mov     [rsp+438h+var_308], rax
0x180037433  cmp     [rsp+438h+var_2B8], r14b
0x18003743b  jz      short loc_180037457
0x18003743d  mov     rax, [rsp+438h+var_2C8]
0x180037445  xor     edx, edx
0x180037447  lea     rcx, [rsp+438h+var_2C8]
0x18003744f  mov     rax, [rax]
0x180037452  call    _guard_dispatch_icall
0x180037457  lea     rdi, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x18003745e  mov     [rsp+438h+var_2D8], rdi
0x180037466  mov     rcx, [rsp+438h+var_2E0]
0x18003746e  test    rcx, rcx
0x180037471  jz      short loc_180037485
0x180037473  mov     rax, [rcx]
0x180037476  mov     edx, r12d
0x180037479  mov     rax, [rax+0C0h]
0x180037480  call    _guard_dispatch_icall
0x180037485  lea     rcx, [rsp+438h+var_300]
0x18003748d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037492  xor     eax, eax
0x180037494  jmp     loc_1800385E0
0x180037499  mov     [rsp+438h+pv], r14
0x18003749e  lea     r8, __ImageBase
0x1800374a5  lea     rcx, [rsp+438h+pv]
0x1800374aa  call    ??$K32GetModuleFileNameExW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEAXPEAUHINSTANCE__@@@Z; wil::K32GetModuleFileNameExW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,128>(void *,HINSTANCE__ *)
0x1800374af  nop
0x1800374b0  mov     rax, [rsp+438h+pv]
0x1800374b5  mov     [rsp+438h+var_2A8], rax
0x1800374bd  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800374c1  inc     rcx
0x1800374c4  cmp     [rax+rcx*2], r14w
0x1800374c9  jnz     short loc_1800374C1
0x1800374cb  mov     [rsp+438h+var_2A8+8], rcx
0x1800374d3  movaps  xmm0, xmmword ptr [rsp+438h+var_2A8]
0x1800374db  movdqa  xmmword ptr [rsp+438h+var_2A8], xmm0
0x1800374e4  lea     rdx, [rsp+438h+var_2A8]
0x1800374ec  lea     rcx, [rsp+438h+Src]
0x1800374f1  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x1800374f6  or      r13d, 1800h
0x1800374fd  mov     rcx, [rsp+438h+pv]; pv
0x180037502  test    rcx, rcx
0x180037505  jz      short loc_18003750D
0x180037507  call    cs:__imp_CoTaskMemFree
0x18003750d  bts     r13d, 0Ah
0x180037512  or      r13d, r12d
0x180037515  mov     rcx, [rsp+438h+var_310]
0x18003751d  mov     rax, [rcx]
0x180037520  mov     rax, [rax+8]
0x180037524  call    _guard_dispatch_icall
0x180037529  mov     r9, rax
0x18003752c  lea     rdi, ??_7UusVersion@@6B@; const UusVersion::`vftable'
0x180037533  mov     [rsp+438h+var_2A8], rdi
0x18003753b  mov     [rsp+438h+var_2A8+8], rax
0x180037543  or      r13d, 2
0x180037547  mov     dword ptr [rsp+438h+pv], r13d
0x18003754c  mov     rcx, [rsp+438h+var_310]
0x180037554  mov     r8b, [rcx+0D9h]
0x18003755b  mov     dl, [rcx+0D8h]
0x180037561  lea     rsi, qword_180050DC0
0x180037568  mov     rax, rsi
0x18003756b  cmp     [r15+30h], r14
0x18003756f  cmovnz  rax, [r15+30h]
0x180037574  mov     [rsp+438h+var_198], rax
0x18003757c  mov     [rsp+438h+var_190], dl
0x180037583  mov     [rsp+438h+var_18F], r8b
0x18003758b  mov     [rsp+438h+var_188], rdi
0x180037593  mov     [rsp+438h+var_180], r9
0x18003759b  xorps   xmm0, xmm0
0x18003759e  movups  [rsp+438h+var_178], xmm0
0x1800375a6  mov     [rsp+438h+var_168], r14
0x1800375ae  mov     eax, 7
0x1800375b3  mov     [rsp+438h+var_160], rax
0x1800375bb  mov     word ptr [rsp+438h+var_178], r14w
0x1800375c4  mov     dword ptr [rsp+438h+var_158], r14d
0x1800375cc  movups  [rsp+438h+var_150], xmm0
0x1800375d4  mov     [rsp+438h+var_140], r14
0x1800375dc  mov     [rsp+438h+var_138], rax
0x1800375e4  mov     word ptr [rsp+438h+var_150], r14w
0x1800375ed  mov     [rsp+438h+var_120], r14b
0x1800375f5  lea     r9, [rsp+438h+Src]
0x1800375fa  cmp     [rsp+438h+var_3D0], rax
0x1800375ff  cmova   r9, [rsp+438h+Src]
0x180037605  mov     rdx, [rsp+438h+var_3D8]
0x18003760a  lea     rcx, [rsp+438h+var_150]; void *
0x180037612  cmp     rdx, rax
0x180037615  ja      short loc_180037639
0x180037617  mov     [rsp+438h+var_140], rdx
0x18003761f  lea     rbx, [rdx+rdx]
0x180037623  mov     r8, rbx; Size
0x180037626  mov     rdx, r9; Src
0x180037629  call    memmove
0x18003762e  mov     word ptr [rsp+rbx+438h+var_150], r14w
0x180037637  jmp     short loc_18003763F
0x180037639  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x18003763e  nop
0x18003763f  or      r13d, 4
0x180037643  mov     dword ptr [rsp+438h+pv], r13d
0x180037648  lea     rcx, [rsp+438h+var_198]; this
0x180037650  call    ?ValidateBinaryIfEnabled@PayloadLoader@@AEAAJXZ; PayloadLoader::ValidateBinaryIfEnabled(void)
0x180037655  mov     rbx, [rsp+438h+var_310]
  ... truncated ...
```
