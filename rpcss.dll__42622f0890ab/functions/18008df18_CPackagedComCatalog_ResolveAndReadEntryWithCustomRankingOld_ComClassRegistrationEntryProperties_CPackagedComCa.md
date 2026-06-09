# CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(ComClassRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::EffectiveClsctxRanking *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_384cae988b9b93015a87ed243e331da0_)

- ea: `0x18008df18`
- end: `0x18008e6bd`
- name: `??$ResolveAndReadEntryWithCustomRankingOld@UComClassRegistrationEntryProperties@@VEffectiveClsctxRanking@CPackagedComCatalog@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@CPackagedComCatalog@@CAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAVEffectiveClsctxRanking@0@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@Z`
- size: `1957`
- prototype: `__int64 __fastcall(__int64, HSTRING *, _DWORD *, __int64, __int64 *, GUID *, char, PackageFilter *, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008d028`

## callees

- `0x18000e148`
- `0x18002ba28`
- `0x1800414d0`
- `0x180047990`
- `0x180047a08`
- `0x180048090`
- `0x1800483bc`
- `0x1800732b4`
- `0x1800764b4`
- `0x18007b510`
- `0x18007b73c`
- `0x18007f24c`
- `0x18007f2ac`
- `0x180080b44`
- `0x180080b78`
- `0x18008dd38`
- `0x18008df18`
- `0x18008e71c`
- `0x18008f610`
- `0x18009a8dc`
- `0x1800b27e0`
- `0x1800da8e8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e5d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e61c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e64a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e66e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e68b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e230`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e5d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e61c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e63b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e64a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e66e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008e68b`

## string_xrefs

- `0x18008e20c`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008e4ef`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008e50f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008e555`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008e5b8`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(
        __int64 a1,
        HSTRING *a2,
        _DWORD *a3,
        __int64 a4,
        __int64 *a5,
        GUID *a6,
        char a7,
        PackageFilter *a8,
        __int64 a9)
{
  int InstalledPackagesContaining; // eax
  __int64 v13; // rbx
  __int64 result; // rax
  char v15; // r15
  unsigned int v16; // r14d
  _QWORD *v17; // r10
  _QWORD *v18; // rdi
  const char *v19; // r9
  bool HasAnyImplementationWithMachineScope; // bl
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // rbx
  __int64 v27; // rax
  const char *v28; // r9
  _DWORD *v29; // rax
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+40h] [rbp-C0h] BYREF
  char v33; // [rsp+44h] [rbp-BCh]
  int v34; // [rsp+48h] [rbp-B8h]
  _BYTE v35[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v36; // [rsp+54h] [rbp-ACh]
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h]
  HSTRING *v41; // [rsp+78h] [rbp-88h]
  _DWORD *v42; // [rsp+80h] [rbp-80h]
  _BYTE v43[576]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v44[4]; // [rsp+2D0h] [rbp+1D0h] BYREF
  int v45; // [rsp+2D4h] [rbp+1D4h]
  char v46; // [rsp+2D8h] [rbp+1D8h]
  __int64 v47; // [rsp+2E0h] [rbp+1E0h]
  char v48; // [rsp+2E8h] [rbp+1E8h]
  __int64 v49; // [rsp+2F0h] [rbp+1F0h]
  char v50; // [rsp+2F8h] [rbp+1F8h]
  __int64 v51; // [rsp+300h] [rbp+200h]
  char v52; // [rsp+308h] [rbp+208h]
  __int64 v53; // [rsp+310h] [rbp+210h]
  __int64 v54; // [rsp+318h] [rbp+218h]
  __int64 v55; // [rsp+320h] [rbp+220h]
  char v56; // [rsp+328h] [rbp+228h]
  __int128 v57; // [rsp+32Ch] [rbp+22Ch]
  int v58; // [rsp+33Ch] [rbp+23Ch]
  char v59; // [rsp+340h] [rbp+240h]
  __int64 v60; // [rsp+348h] [rbp+248h]
  char v61; // [rsp+350h] [rbp+250h]
  __int64 v62; // [rsp+358h] [rbp+258h]
  char v63; // [rsp+360h] [rbp+260h]
  __int64 v64; // [rsp+368h] [rbp+268h]
  char v65; // [rsp+370h] [rbp+270h]
  __int64 v66; // [rsp+378h] [rbp+278h]
  char v67; // [rsp+380h] [rbp+280h]
  __int64 v68; // [rsp+388h] [rbp+288h]
  __int64 v69; // [rsp+390h] [rbp+290h]
  char v70; // [rsp+398h] [rbp+298h]
  __int128 v71; // [rsp+3A0h] [rbp+2A0h]
  char v72; // [rsp+3B0h] [rbp+2B0h]
  __int64 v73; // [rsp+3B8h] [rbp+2B8h]
  char v74; // [rsp+3C0h] [rbp+2C0h]
  __int64 v75; // [rsp+3C8h] [rbp+2C8h]
  char v76; // [rsp+3D0h] [rbp+2D0h]
  int v77; // [rsp+3D4h] [rbp+2D4h]
  __int16 v78; // [rsp+3D8h] [rbp+2D8h]
  int v79; // [rsp+3DAh] [rbp+2DAh]
  __int16 v80; // [rsp+3DEh] [rbp+2DEh]
  char v81; // [rsp+3E0h] [rbp+2E0h]
  __int64 v82; // [rsp+3E8h] [rbp+2E8h]
  char v83; // [rsp+3F0h] [rbp+2F0h]
  __int64 v84; // [rsp+3F8h] [rbp+2F8h]
  char v85; // [rsp+400h] [rbp+300h]
  __int64 v86; // [rsp+408h] [rbp+308h]
  char v87; // [rsp+410h] [rbp+310h]
  __int64 v88; // [rsp+418h] [rbp+318h]
  __int64 v89; // [rsp+420h] [rbp+320h]
  char v90; // [rsp+428h] [rbp+328h]
  __int64 v91; // [rsp+430h] [rbp+330h]
  char v92; // [rsp+438h] [rbp+338h]
  __int64 v93; // [rsp+440h] [rbp+340h]
  char v94; // [rsp+448h] [rbp+348h]
  __int64 v95; // [rsp+450h] [rbp+350h]
  char v96; // [rsp+458h] [rbp+358h]
  __int64 v97; // [rsp+460h] [rbp+360h]
  __int64 v98; // [rsp+468h] [rbp+368h]
  __int64 v99; // [rsp+470h] [rbp+370h]
  char v100; // [rsp+478h] [rbp+378h]
  __int128 v101; // [rsp+47Ch] [rbp+37Ch]
  int v102; // [rsp+48Ch] [rbp+38Ch]
  char v103; // [rsp+490h] [rbp+390h]
  __int64 v104; // [rsp+498h] [rbp+398h]
  char v105; // [rsp+4A0h] [rbp+3A0h]
  int v106; // [rsp+4A4h] [rbp+3A4h]
  char v107; // [rsp+4A8h] [rbp+3A8h]
  int v108; // [rsp+4ACh] [rbp+3ACh]
  char v109; // [rsp+4B0h] [rbp+3B0h]
  int v110; // [rsp+4B4h] [rbp+3B4h]
  __int16 v111; // [rsp+4B8h] [rbp+3B8h]
  int v112; // [rsp+4BAh] [rbp+3BAh]
  __int16 v113; // [rsp+4BEh] [rbp+3BEh]
  char v114; // [rsp+4C0h] [rbp+3C0h]
  __int128 v115; // [rsp+4C8h] [rbp+3C8h]
  char v116; // [rsp+4D8h] [rbp+3D8h]
  int v117; // [rsp+4DCh] [rbp+3DCh]
  char v118; // [rsp+4E0h] [rbp+3E0h]
  __int64 v119; // [rsp+4E8h] [rbp+3E8h]
  char v120; // [rsp+4F0h] [rbp+3F0h]
  int v121; // [rsp+4F4h] [rbp+3F4h]
  char v122; // [rsp+4F8h] [rbp+3F8h]
  int v123; // [rsp+4FCh] [rbp+3FCh]
  char v124; // [rsp+500h] [rbp+400h]
  int v125; // [rsp+504h] [rbp+404h]
  char v126; // [rsp+508h] [rbp+408h]
  int v127; // [rsp+50Ch] [rbp+40Ch]
  _BYTE v128[128]; // [rsp+510h] [rbp+410h] BYREF
  _QWORD *v129; // [rsp+590h] [rbp+490h]
  __int64 v130; // [rsp+598h] [rbp+498h]
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+508h]

  v41 = a2;
  v42 = a3;
  v58 = 0;
  v79 = 0;
  v80 = 0;
  v102 = 0;
  v40 = a1;
  v44[0] = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v100 = 0;
  v101 = 0;
  v103 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v115 = 0u;
  v114 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  v122 = 0;
  v123 = 0;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  v127 = 0;
  v112 = 0;
  v113 = 0;
  ComClassRegistrationEntryProperties::operator=(a1, v44);
  ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v44);
  *a2 = 0;
  *a3 = 0;
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v128);
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComClassRegistrationEntryProperties>(
                                  (PackageListBuffer *)v128,
                                  a4,
                                  a5,
                                  a6,
                                  a7,
                                  a8);
  LODWORD(v13) = InstalledPackagesContaining;
  if ( InstalledPackagesContaining < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1083,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)InstalledPackagesContaining,
      v30);
LABEL_3:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v128);
    WindowsDeleteString(*(HSTRING *)(a9 + 8));
    result = (unsigned int)v13;
    *(_QWORD *)(a9 + 8) = 0;
    return result;
  }
  if ( !(_DWORD)v130 )
    goto LABEL_45;
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v129,
    (__int64)&v129[4 * (unsigned int)v130],
    (unsigned int)v130,
    (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByUser);
  v15 = 0;
  v16 = 1;
  ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v43);
  string = 0;
  v33 = 0;
LABEL_6:
  v17 = v129;
  v18 = v129;
  while ( v18 != &v17[4 * (unsigned int)v130] )
  {
    if ( !(unsigned __int8)PackageInstalledForScope(v18, v16) )
      goto LABEL_26;
    v39 = 0;
    v38 = 0;
    v34 = 0;
    v36 = 0;
    ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v44);
    v13 = (unsigned int) IPackagedComCatalogContext::`vcall'{72,{flat}}(a5, *v18, a6, v44, &v39, &v38);
    v31 = v39;
    CPackagedComCatalog::LogReadEntryResult(v13, v44, v18, a6);
    if ( (int)v13 >= 0 )
    {
      HasAnyImplementationWithMachineScope = ClassRegistrationHasAnyImplementationWithMachineScope((const struct ComClassRegistrationEntryProperties *)v44);
      LOBYTE(v21) = ClassRegistrationHasAnyImplementationWithUserScope((const struct ComClassRegistrationEntryProperties *)v44);
      LOBYTE(v22) = HasAnyImplementationWithMachineScope;
      if ( !(unsigned __int8)RegistrationScopeMatchesInstallScope(v21, v22, v16)
        || !ClassRegistrationHasAnyImplementationWithSupportedSyntaxVersion((const struct ComClassRegistrationEntryProperties *)v44) )
      {
        goto LABEL_17;
      }
      v31 = v32;
      LODWORD(v13) = _lambda_384cae988b9b93015a87ed243e331da0_::operator()(a9, v18, v16, v44);
    }
    if ( (_DWORD)v13 != -2147024894 && (unsigned int)(v13 + 2147221165) > 1 && (_DWORD)v13 != -2147024883 )
    {
      if ( (int)v13 < 0 )
        goto LABEL_39;
LABEL_17:
      if ( v34 == 2 )
      {
        if ( !v36 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x10E0,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            v19);
        if ( v33 )
        {
          v26 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(&v32);
          v27 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v35);
          if ( !(unsigned __int8)CPackagedComCatalog::EffectiveClsctxRanking::operator<(v26, v27) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x10E4,
              (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
              v28);
        }
        LODWORD(v13) = 0;
        ComClassRegistrationEntryProperties::operator=(v43, v44);
        OpaqueString::operator=(&string, v18);
        v32 = *(_DWORD *)std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v35);
        if ( !v33 )
          v33 = 1;
LABEL_39:
        ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v44);
        if ( (int)v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1114,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v13,
            v31);
          WindowsDeleteString(string);
          ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v43);
          goto LABEL_3;
        }
        break;
      }
      if ( v34 == 1 )
      {
        if ( !v36 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x10EF,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            v19);
        if ( v33 == (v36 == 0)
          || (v23 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(&v32),
              v24 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v35),
              (unsigned __int8)CPackagedComCatalog::EffectiveClsctxRanking::operator<(v23, v24)) )
        {
          ComClassRegistrationEntryProperties::operator=(v43, v44);
          OpaqueString::operator=(&string, v18);
          v32 = *(_DWORD *)std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v35);
          if ( !v33 )
            v33 = 1;
        }
      }
      goto LABEL_25;
    }
    v15 = 1;
LABEL_25:
    ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v44);
    v17 = v129;
LABEL_26:
    v18 += 4;
    v25 = (__int64)&v17[4 * (unsigned int)v130];
    if ( v18 == (_QWORD *)v25 )
    {
      if ( v16 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v17,
          v25,
          (32LL * (unsigned int)v130) >> 5,
          (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByOneTime);
        v16 = 2;
        goto LABEL_6;
      }
      if ( v16 == 2 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v17,
          v25,
          (32LL * (unsigned int)v130) >> 5,
          (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByMachine);
        v16 = 0;
        goto LABEL_6;
      }
    }
  }
  if ( v33 )
  {
    ComClassRegistrationEntryProperties::operator=(v40, v43);
    *v41 = string;
    v29 = (_DWORD *)std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(&v32);
    *v42 = *v29;
    WindowsDeleteString(0);
    ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v43);
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v128);
    WindowsDeleteString(*(HSTRING *)(a9 + 8));
    result = 0;
    goto LABEL_46;
  }
  WindowsDeleteString(string);
  ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v43);
  if ( v15 )
  {
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v128);
    WindowsDeleteString(*(HSTRING *)(a9 + 8));
    result = 2147942413LL;
    goto LABEL_46;
  }
LABEL_45:
  PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v128);
  WindowsDeleteString(*(HSTRING *)(a9 + 8));
  result = 2147942402LL;
LABEL_46:
  *(_QWORD *)(a9 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x18008df18  push    rbp
0x18008df1a  push    rbx
0x18008df1b  push    rsi
0x18008df1c  push    rdi
0x18008df1d  push    r12
0x18008df1f  push    r13
0x18008df21  push    r14
0x18008df23  push    r15
0x18008df25  lea     rbp, [rsp-4C8h]
0x18008df2d  sub     rsp, 5C8h
0x18008df34  mov     rax, cs:__security_cookie
0x18008df3b  xor     rax, rsp
0x18008df3e  mov     [rbp+500h+var_50], rax
0x18008df45  mov     r13, [rbp+500h+arg_20]
0x18008df4c  xorps   xmm0, xmm0
0x18008df4f  mov     r12, [rbp+500h+arg_28]
0x18008df56  mov     r14, rdx
0x18008df59  mov     rbx, [rbp+500h+arg_38]
0x18008df60  mov     rdi, r9
0x18008df63  mov     rsi, [rbp+500h+arg_40]
0x18008df6a  mov     r15, r8
0x18008df6d  mov     [rsp+600h+var_588], rdx
0x18008df72  xor     edx, edx
0x18008df74  xor     eax, eax
0x18008df76  mov     [rbp+500h+var_580], r8
0x18008df7a  mov     [rbp+500h+var_2C4], eax
0x18008df80  mov     [rbp+500h+var_226], eax
0x18008df86  mov     [rbp+500h+var_222], ax
0x18008df8d  mov     [rbp+500h+var_174], eax
0x18008df93  mov     [rsp+600h+var_590], rcx
0x18008df98  mov     [rbp+500h+var_330], dl
0x18008df9e  mov     [rbp+500h+var_32C], edx
0x18008dfa4  mov     [rbp+500h+var_328], dl
0x18008dfaa  mov     [rbp+500h+var_320], rdx
0x18008dfb1  mov     [rbp+500h+var_318], dl
0x18008dfb7  mov     [rbp+500h+var_310], rdx
0x18008dfbe  mov     [rbp+500h+var_308], dl
0x18008dfc4  mov     [rbp+500h+var_300], rdx
0x18008dfcb  mov     [rbp+500h+var_2F8], dl
0x18008dfd1  mov     [rbp+500h+var_2F0], rdx
0x18008dfd8  mov     [rbp+500h+var_2E8], rdx
0x18008dfdf  mov     [rbp+500h+var_2E0], rdx
0x18008dfe6  mov     [rbp+500h+var_2D8], dl
0x18008dfec  movups  [rbp+500h+var_2D4], xmm0
0x18008dff3  mov     [rbp+500h+var_2C0], dl
0x18008dff9  mov     [rbp+500h+var_2B8], rdx
0x18008e000  mov     [rbp+500h+var_2B0], dl
0x18008e006  mov     [rbp+500h+var_2A8], rdx
0x18008e00d  mov     [rbp+500h+var_2A0], dl
0x18008e013  mov     [rbp+500h+var_298], rdx
0x18008e01a  mov     [rbp+500h+var_290], dl
0x18008e020  mov     [rbp+500h+var_288], rdx
0x18008e027  mov     [rbp+500h+var_280], dl
0x18008e02d  mov     [rbp+500h+var_278], rdx
0x18008e034  mov     [rbp+500h+var_270], rdx
0x18008e03b  mov     [rbp+500h+var_268], dl
0x18008e041  movdqa  [rbp+500h+var_260], xmm0
0x18008e049  mov     [rbp+500h+var_250], dl
0x18008e04f  mov     [rbp+500h+var_248], rdx
0x18008e056  mov     [rbp+500h+var_240], dl
0x18008e05c  mov     [rbp+500h+var_238], rdx
0x18008e063  mov     [rbp+500h+var_230], dl
0x18008e069  mov     [rbp+500h+var_22C], edx
0x18008e06f  mov     [rbp+500h+var_228], dx
0x18008e076  mov     [rbp+500h+var_220], dl
0x18008e07c  mov     [rbp+500h+var_218], rdx
0x18008e083  mov     [rbp+500h+var_210], dl
0x18008e089  mov     [rbp+500h+var_208], rdx
0x18008e090  mov     [rbp+500h+var_200], dl
0x18008e096  mov     [rbp+500h+var_1F8], rdx
0x18008e09d  mov     [rbp+500h+var_1F0], dl
0x18008e0a3  mov     [rbp+500h+var_1E8], rdx
0x18008e0aa  mov     [rbp+500h+var_1E0], rdx
0x18008e0b1  mov     [rbp+500h+var_1D8], dl
0x18008e0b7  mov     [rbp+500h+var_1D0], rdx
0x18008e0be  mov     [rbp+500h+var_1C8], dl
0x18008e0c4  mov     [rbp+500h+var_1C0], rdx
0x18008e0cb  mov     [rbp+500h+var_1B8], dl
0x18008e0d1  mov     [rbp+500h+var_1B0], rdx
0x18008e0d8  mov     [rbp+500h+var_1A8], dl
0x18008e0de  mov     [rbp+500h+var_1A0], rdx
0x18008e0e5  mov     [rbp+500h+var_198], rdx
0x18008e0ec  mov     [rbp+500h+var_190], rdx
0x18008e0f3  mov     [rbp+500h+var_188], dl
0x18008e0f9  movups  [rbp+500h+var_184], xmm0
0x18008e100  mov     [rbp+500h+var_170], dl
0x18008e106  mov     [rbp+500h+var_168], rdx
0x18008e10d  mov     [rbp+500h+var_160], dl
0x18008e113  mov     [rbp+500h+var_15C], edx
0x18008e119  mov     [rbp+500h+var_158], dl
0x18008e11f  mov     [rbp+500h+var_154], edx
0x18008e125  mov     [rbp+500h+var_150], dl
0x18008e12b  mov     [rbp+500h+var_14C], edx
0x18008e131  mov     [rbp+500h+var_148], dx
0x18008e138  movups  [rbp+500h+var_138], xmm0
0x18008e13f  mov     qword ptr [rbp+500h+var_138], rdx
0x18008e146  mov     word ptr [rbp+500h+var_138+8], dx
0x18008e14d  mov     [rbp+500h+var_140], dl
0x18008e153  mov     [rbp+500h+var_128], dl
0x18008e159  mov     [rbp+500h+var_124], edx
0x18008e15f  mov     [rbp+500h+var_120], dl
0x18008e165  mov     [rbp+500h+var_118], rdx
0x18008e16c  mov     [rbp+500h+var_110], dl
0x18008e172  mov     [rbp+500h+var_10C], edx
0x18008e178  mov     [rbp+500h+var_108], dl
0x18008e17e  mov     [rbp+500h+var_104], edx
0x18008e184  mov     [rbp+500h+var_100], dl
0x18008e18a  mov     [rbp+500h+var_FC], edx
0x18008e190  mov     [rbp+500h+var_F8], dl
0x18008e196  mov     [rbp+500h+var_F4], edx
0x18008e19c  lea     rdx, [rbp+500h+var_330]
0x18008e1a3  mov     [rbp+500h+var_146], eax
0x18008e1a9  mov     [rbp+500h+var_142], ax
0x18008e1b0  call    ??4ComClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComClassRegistrationEntryProperties::operator=(ComClassRegistrationEntryProperties &&)
0x18008e1b5  lea     rcx, [rbp+500h+var_330]; this
0x18008e1bc  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x18008e1c1  mov     qword ptr [r14], 0
0x18008e1c8  lea     rcx, [rbp+500h+var_F0]; this
0x18008e1cf  mov     dword ptr [r15], 0
0x18008e1d6  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x18008e1db  mov     al, [rbp+500h+arg_30]
0x18008e1e1  lea     rcx, [rbp+500h+var_F0]; this
0x18008e1e8  mov     [rsp+600h+var_5D8], rbx; PackageFilter *
0x18008e1ed  mov     r9, r12
0x18008e1f0  mov     r8, r13
0x18008e1f3  mov     [rsp+600h+var_5E0], al; int
0x18008e1f7  mov     rdx, rdi
0x18008e1fa  call    ??$GetInstalledPackagesContainingEntry@UComClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)
0x18008e1ff  mov     ebx, eax
0x18008e201  test    eax, eax
0x18008e203  jns     short loc_18008E245
0x18008e205  mov     rcx, [rbp+508h]; this
0x18008e20c  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008e213  mov     r9d, eax; char *
0x18008e216  mov     edx, 1083h; void *
0x18008e21b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e220  lea     rcx, [rbp+500h+var_F0]; this
0x18008e227  call    ??1PackageListBuffer@@QEAA@XZ; PackageListBuffer::~PackageListBuffer(void)
0x18008e22c  mov     rcx, [rsi+8]; string
0x18008e230  call    cs:__imp_WindowsDeleteString
0x18008e236  mov     eax, ebx
0x18008e238  mov     qword ptr [rsi+8], 0
0x18008e240  jmp     loc_18008E69A
0x18008e245  mov     rax, [rbp+500h+var_68]
0x18008e24c  xor     ebx, ebx
0x18008e24e  test    eax, eax
0x18008e250  jz      loc_18008E67B
0x18008e256  mov     rcx, [rbp+500h+var_70]
0x18008e25d  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18008e264  mov     edx, eax
0x18008e266  shl     rdx, 5
0x18008e26a  add     rdx, rcx
0x18008e26d  mov     r8d, eax
0x18008e270  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18008e275  lea     rcx, [rbp+500h+var_570]; this
0x18008e279  mov     r15b, bl
0x18008e27c  lea     r14d, [rbx+1]
0x18008e280  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x18008e285  mov     [rsp+600h+string], rbx
0x18008e28a  mov     [rsp+600h+var_5BC], bl
0x18008e28e  mov     r10, [rbp+500h+var_70]
0x18008e295  mov     rdi, r10
0x18008e298  mov     eax, dword ptr [rbp+500h+var_68]
0x18008e29e  shl     rax, 5
0x18008e2a2  add     rax, r10
0x18008e2a5  cmp     rdi, rax
0x18008e2a8  jz      loc_18008E5E7
0x18008e2ae  mov     edx, r14d
0x18008e2b1  mov     rcx, rdi
0x18008e2b4  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x18008e2b9  test    al, al
0x18008e2bb  jz      loc_18008E480
0x18008e2c1  lea     rcx, [rbp+500h+var_330]; this
0x18008e2c8  mov     [rsp+600h+var_598], rbx
0x18008e2cd  mov     [rsp+600h+var_5A0], rbx
0x18008e2d2  mov     [rsp+600h+var_5B8], ebx
0x18008e2d6  mov     [rsp+600h+var_5AC], bl
0x18008e2da  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x18008e2df  mov     rdx, [rdi]
0x18008e2e2  lea     rcx, [rsp+600h+var_5A0]
0x18008e2e7  mov     [rsp+600h+var_5D8], rcx
0x18008e2ec  lea     rax, [rsp+600h+var_598]
0x18008e2f1  mov     rcx, r13
0x18008e2f4  mov     qword ptr [rsp+600h+var_5E0], rax
0x18008e2f9  lea     r9, [rbp+500h+var_330]
0x18008e300  mov     r8, r12
0x18008e303  call    ??_9IPackagedComCatalogContext@@$BEI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{72,{flat}}
0x18008e308  mov     ebx, eax
0x18008e30a  lea     rdx, [rbp+500h+var_330]
0x18008e311  mov     rax, [rsp+600h+var_5A0]
0x18008e316  mov     r9, r12
0x18008e319  mov     [rsp+600h+var_5D8], rax
0x18008e31e  mov     r8, rdi
0x18008e321  mov     rax, [rsp+600h+var_598]
0x18008e326  mov     ecx, ebx
0x18008e328  mov     qword ptr [rsp+600h+var_5E0], rax
0x18008e32d  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComClassRegistrationEntryProperties@@AEBVOpaqueString@@AEBU_GUID@@W4ComClassRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComClassRegistrationEntryProperties const &,OpaqueString const &,_GUID const &,ComClassRegistrationEntryPropertyFlags,ComClassRegistrationEntryPropertyFlags)
0x18008e332  test    ebx, ebx
0x18008e334  js      short loc_18008E3A5
0x18008e336  lea     rcx, [rbp+500h+var_330]; struct ComClassRegistrationEntryProperties *
0x18008e33d  call    ?ClassRegistrationHasAnyImplementationWithMachineScope@@YA_NAEBUComClassRegistrationEntryProperties@@@Z; ClassRegistrationHasAnyImplementationWithMachineScope(ComClassRegistrationEntryProperties const &)
0x18008e342  lea     rcx, [rbp+500h+var_330]; struct ComClassRegistrationEntryProperties *
0x18008e349  mov     bl, al
0x18008e34b  call    ?ClassRegistrationHasAnyImplementationWithUserScope@@YA_NAEBUComClassRegistrationEntryProperties@@@Z; ClassRegistrationHasAnyImplementationWithUserScope(ComClassRegistrationEntryProperties const &)
0x18008e350  mov     cl, al
0x18008e352  mov     r8d, r14d
0x18008e355  mov     dl, bl
0x18008e357  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x18008e35c  test    al, al
0x18008e35e  jz      short loc_18008E3D4
0x18008e360  lea     rcx, [rbp+500h+var_330]; struct ComClassRegistrationEntryProperties *
0x18008e367  call    ?ClassRegistrationHasAnyImplementationWithSupportedSyntaxVersion@@YA_NAEBUComClassRegistrationEntryProperties@@@Z; ClassRegistrationHasAnyImplementationWithSupportedSyntaxVersion(ComClassRegistrationEntryProperties const &)
0x18008e36c  test    al, al
0x18008e36e  jz      short loc_18008E3D4
0x18008e370  lea     rax, [rsp+600h+var_5B0]
0x18008e375  mov     r8d, r14d
0x18008e378  mov     [rsp+600h+var_5D0], rax
0x18008e37d  lea     r9, [rbp+500h+var_330]
0x18008e384  lea     rax, [rsp+600h+var_5B8]
0x18008e389  mov     rdx, rdi
0x18008e38c  mov     [rsp+600h+var_5D8], rax
0x18008e391  mov     rcx, rsi
0x18008e394  mov     rax, [rsp+40h]
0x18008e399  mov     qword ptr [rsp+600h+var_5E0], rax; int
0x18008e39e  call    ??R_lambda_384cae988b9b93015a87ed243e331da0_@@QEBA@AEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComClassRegistrationEntryProperties@@V?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@PEAW4RegistrationApplicability@CPackagedComCatalog@@PEAV56@@Z; _lambda_384cae988b9b93015a87ed243e331da0_::operator()(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,std::optional<CPackagedComCatalog::EffectiveClsctxRanking>,CPackagedComCatalog::RegistrationApplicability *,std::optional<CPackagedComCatalog::EffectiveClsctxRanking> *)
0x18008e3a3  mov     ebx, eax
0x18008e3a5  cmp     ebx, 80070002h
0x18008e3ab  jz      loc_18008E468
0x18008e3b1  lea     eax, [rbx+7FFBFEADh]
0x18008e3b7  cmp     eax, 1
0x18008e3ba  jbe     loc_18008E468
0x18008e3c0  cmp     ebx, 8007000Dh
0x18008e3c6  jz      loc_18008E468
0x18008e3cc  test    ebx, ebx
0x18008e3ce  js      loc_18008E5A1
0x18008e3d4  cmp     [rsp+600h+var_5B8], 2
0x18008e3d9  jz      loc_18008E501
0x18008e3df  cmp     [rsp+600h+var_5B8], 1
0x18008e3e4  jnz     loc_18008E46B
0x18008e3ea  cmp     [rsp+600h+var_5AC], 0
0x18008e3ef  mov     rcx, [rbp+508h]; this
0x18008e3f6  setz    al
0x18008e3f9  test    al, al
0x18008e3fb  jnz     loc_18008E4EF
0x18008e401  cmp     [rsp+600h+var_5BC], al
0x18008e405  jz      short loc_18008E42D
0x18008e407  lea     rcx, [rsp+600h+var_5C0]
0x18008e40c  call    ?value@?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@QEGAAAEAVEffectiveClsctxRanking@CPackagedComCatalog@@XZ; std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(void)
0x18008e411  lea     rcx, [rsp+600h+var_5B0]
0x18008e416  mov     rbx, rax
0x18008e419  call    ?value@?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@QEGAAAEAVEffectiveClsctxRanking@CPackagedComCatalog@@XZ; std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(void)
0x18008e41e  mov     rdx, rax
0x18008e421  mov     rcx, rbx
0x18008e424  call    ??MEffectiveClsctxRanking@CPackagedComCatalog@@QEBA_NAEBV01@@Z; CPackagedComCatalog::EffectiveClsctxRanking::operator<(CPackagedComCatalog::EffectiveClsctxRanking const &)
0x18008e429  test    al, al
0x18008e42b  jz      short loc_18008E46B
0x18008e42d  lea     rdx, [rbp+500h+var_330]
0x18008e434  lea     rcx, [rbp+500h+var_570]
0x18008e438  call    ??4ComClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComClassRegistrationEntryProperties::operator=(ComClassRegistrationEntryProperties &&)
0x18008e43d  mov     rdx, rdi
0x18008e440  lea     rcx, [rsp+600h+string]
0x18008e445  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x18008e44a  lea     rcx, [rsp+600h+var_5B0]
0x18008e44f  call    ?value@?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@QEGAAAEAVEffectiveClsctxRanking@CPackagedComCatalog@@XZ; std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(void)
0x18008e454  cmp     [rsp+600h+var_5BC], 0
0x18008e459  mov     ecx, [rax]
0x18008e45b  mov     [rsp+600h+var_5C0], ecx
0x18008e45f  jnz     short loc_18008E46B
0x18008e461  mov     [rsp+600h+var_5BC], 1
0x18008e466  jmp     short loc_18008E46B
0x18008e468  mov     r15b, 1
0x18008e46b  lea     rcx, [rbp+500h+var_330]; this
0x18008e472  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x18008e477  mov     r10, [rbp+500h+var_70]
0x18008e47e  xor     ebx, ebx
0x18008e480  mov     edx, dword ptr [rbp+500h+var_68]
0x18008e486  add     rdi, 20h ; ' '
0x18008e48a  shl     rdx, 5
0x18008e48e  add     rdx, r10
0x18008e491  cmp     rdi, rdx
0x18008e494  jnz     loc_18008E298
0x18008e49a  cmp     r14d, 1
0x18008e49e  jnz     short loc_18008E4C4
0x18008e4a0  mov     r8, rdx
0x18008e4a3  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18008e4aa  sub     r8, r10
0x18008e4ad  mov     rcx, r10
0x18008e4b0  sar     r8, 5
0x18008e4b4  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18008e4b9  mov     r14d, 2
0x18008e4bf  jmp     loc_18008E28E
0x18008e4c4  cmp     r14d, 2
0x18008e4c8  jnz     loc_18008E298
0x18008e4ce  mov     r8, rdx
0x18008e4d1  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18008e4d8  sub     r8, r10
0x18008e4db  mov     rcx, r10
0x18008e4de  sar     r8, 5
0x18008e4e2  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18008e4e7  mov     r14d, ebx
  ... truncated ...
```
