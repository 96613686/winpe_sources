# CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(ComClassRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::EffectiveClsctxRanking *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_384cae988b9b93015a87ed243e331da0_)

- ea: `0x18009515c`
- end: `0x18009592c`
- name: `??$ResolveAndReadEntryWithCustomRankingOld@UComClassRegistrationEntryProperties@@VEffectiveClsctxRanking@CPackagedComCatalog@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@CPackagedComCatalog@@CAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAVEffectiveClsctxRanking@0@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@Z`
- size: `2000`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, char, PackageFilter *, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800941bc`

## callees

- `0x1800210f8`
- `0x18002610c`
- `0x180027c20`
- `0x18003b8d0`
- `0x18003b94c`
- `0x18003c024`
- `0x18003c360`
- `0x18004b0f0`
- `0x1800779b4`
- `0x18007aa10`
- `0x18007fbd0`
- `0x180080110`
- `0x180083b88`
- `0x180083ba8`
- `0x1800854fc`
- `0x180094f7c`
- `0x18009515c`
- `0x18009598c`
- `0x1800968fc`
- `0x18009ff3c`
- `0x1800b7ac0`
- `0x1800e166c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009581b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009586c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800958a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800958d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800958f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095474`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009581b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009586c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180095891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800958a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800958d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800958f3`

## string_xrefs

- `0x180095450`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180095739`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180095759`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18009579f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180095802`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
  __int64 v17; // r8
  __int64 v18; // r9
  _QWORD *v19; // r10
  _QWORD *v20; // rdi
  const char *v21; // r9
  bool HasAnyImplementationWithMachineScope; // bl
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rbx
  __int64 v26; // rax
  _QWORD *v27; // rdx
  __int64 v28; // rbx
  __int64 v29; // rax
  const char *v30; // r9
  _DWORD *v31; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+40h] [rbp-C0h] BYREF
  char v35; // [rsp+44h] [rbp-BCh]
  int v36; // [rsp+48h] [rbp-B8h]
  _BYTE v37[4]; // [rsp+50h] [rbp-B0h] BYREF
  char v38; // [rsp+54h] [rbp-ACh]
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h] BYREF
  __int64 v42; // [rsp+70h] [rbp-90h]
  HSTRING *v43; // [rsp+78h] [rbp-88h]
  _DWORD *v44; // [rsp+80h] [rbp-80h]
  HSTRING v45[72]; // [rsp+90h] [rbp-70h] BYREF
  HSTRING v46; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v47; // [rsp+2D8h] [rbp+1D8h]
  __int64 v48; // [rsp+2E0h] [rbp+1E0h]
  char v49; // [rsp+2E8h] [rbp+1E8h]
  __int64 v50; // [rsp+2F0h] [rbp+1F0h]
  char v51; // [rsp+2F8h] [rbp+1F8h]
  __int64 v52; // [rsp+300h] [rbp+200h]
  char v53; // [rsp+308h] [rbp+208h]
  __int64 v54; // [rsp+310h] [rbp+210h]
  __int64 v55; // [rsp+318h] [rbp+218h]
  __int64 v56; // [rsp+320h] [rbp+220h]
  char v57; // [rsp+328h] [rbp+228h]
  __int128 v58; // [rsp+32Ch] [rbp+22Ch]
  int v59; // [rsp+33Ch] [rbp+23Ch]
  char v60; // [rsp+340h] [rbp+240h]
  __int64 v61; // [rsp+348h] [rbp+248h]
  char v62; // [rsp+350h] [rbp+250h]
  __int64 v63; // [rsp+358h] [rbp+258h]
  char v64; // [rsp+360h] [rbp+260h]
  __int64 v65; // [rsp+368h] [rbp+268h]
  char v66; // [rsp+370h] [rbp+270h]
  __int64 v67; // [rsp+378h] [rbp+278h]
  char v68; // [rsp+380h] [rbp+280h]
  __int64 v69; // [rsp+388h] [rbp+288h]
  __int64 v70; // [rsp+390h] [rbp+290h]
  char v71; // [rsp+398h] [rbp+298h]
  __int128 v72; // [rsp+3A0h] [rbp+2A0h]
  char v73; // [rsp+3B0h] [rbp+2B0h]
  __int64 v74; // [rsp+3B8h] [rbp+2B8h]
  char v75; // [rsp+3C0h] [rbp+2C0h]
  __int64 v76; // [rsp+3C8h] [rbp+2C8h]
  char v77; // [rsp+3D0h] [rbp+2D0h]
  int v78; // [rsp+3D4h] [rbp+2D4h]
  __int16 v79; // [rsp+3D8h] [rbp+2D8h]
  int v80; // [rsp+3DAh] [rbp+2DAh]
  __int16 v81; // [rsp+3DEh] [rbp+2DEh]
  char v82; // [rsp+3E0h] [rbp+2E0h]
  __int64 v83; // [rsp+3E8h] [rbp+2E8h]
  char v84; // [rsp+3F0h] [rbp+2F0h]
  __int64 v85; // [rsp+3F8h] [rbp+2F8h]
  char v86; // [rsp+400h] [rbp+300h]
  __int64 v87; // [rsp+408h] [rbp+308h]
  char v88; // [rsp+410h] [rbp+310h]
  __int64 v89; // [rsp+418h] [rbp+318h]
  __int64 v90; // [rsp+420h] [rbp+320h]
  char v91; // [rsp+428h] [rbp+328h]
  __int64 v92; // [rsp+430h] [rbp+330h]
  char v93; // [rsp+438h] [rbp+338h]
  __int64 v94; // [rsp+440h] [rbp+340h]
  char v95; // [rsp+448h] [rbp+348h]
  __int64 v96; // [rsp+450h] [rbp+350h]
  char v97; // [rsp+458h] [rbp+358h]
  __int64 v98; // [rsp+460h] [rbp+360h]
  __int64 v99; // [rsp+468h] [rbp+368h]
  __int64 v100; // [rsp+470h] [rbp+370h]
  char v101; // [rsp+478h] [rbp+378h]
  __int128 v102; // [rsp+47Ch] [rbp+37Ch]
  int v103; // [rsp+48Ch] [rbp+38Ch]
  char v104; // [rsp+490h] [rbp+390h]
  __int64 v105; // [rsp+498h] [rbp+398h]
  char v106; // [rsp+4A0h] [rbp+3A0h]
  int v107; // [rsp+4A4h] [rbp+3A4h]
  char v108; // [rsp+4A8h] [rbp+3A8h]
  int v109; // [rsp+4ACh] [rbp+3ACh]
  char v110; // [rsp+4B0h] [rbp+3B0h]
  int v111; // [rsp+4B4h] [rbp+3B4h]
  __int16 v112; // [rsp+4B8h] [rbp+3B8h]
  int v113; // [rsp+4BAh] [rbp+3BAh]
  __int16 v114; // [rsp+4BEh] [rbp+3BEh]
  char v115; // [rsp+4C0h] [rbp+3C0h]
  __int128 v116; // [rsp+4C8h] [rbp+3C8h]
  char v117; // [rsp+4D8h] [rbp+3D8h]
  int v118; // [rsp+4DCh] [rbp+3DCh]
  char v119; // [rsp+4E0h] [rbp+3E0h]
  __int64 v120; // [rsp+4E8h] [rbp+3E8h]
  char v121; // [rsp+4F0h] [rbp+3F0h]
  int v122; // [rsp+4F4h] [rbp+3F4h]
  char v123; // [rsp+4F8h] [rbp+3F8h]
  int v124; // [rsp+4FCh] [rbp+3FCh]
  char v125; // [rsp+500h] [rbp+400h]
  int v126; // [rsp+504h] [rbp+404h]
  char v127; // [rsp+508h] [rbp+408h]
  int v128; // [rsp+50Ch] [rbp+40Ch]
  _BYTE v129[128]; // [rsp+510h] [rbp+410h] BYREF
  _QWORD *v130; // [rsp+590h] [rbp+490h]
  __int64 v131; // [rsp+598h] [rbp+498h]
  wil::details::in1diag3 *retaddr; // [rsp+608h] [rbp+508h]

  v43 = a2;
  v44 = a3;
  v59 = 0;
  v80 = 0;
  v81 = 0;
  v103 = 0;
  v42 = a1;
  LOBYTE(v46) = 0;
  HIDWORD(v46) = 0;
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
  v58 = 0;
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
  v79 = 0;
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
  v102 = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v109 = 0;
  v110 = 0;
  v111 = 0;
  v112 = 0;
  v116 = 0u;
  v115 = 0;
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
  v128 = 0;
  v113 = 0;
  v114 = 0;
  ComClassRegistrationEntryProperties::operator=(a1, (__int64)&v46);
  ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(&v46);
  *a2 = 0;
  *a3 = 0;
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v129);
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComClassRegistrationEntryProperties>(
                                  (PackageListBuffer *)v129,
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
      v32);
LABEL_3:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v129);
    WindowsDeleteString(*(HSTRING *)(a9 + 8));
    result = (unsigned int)v13;
    *(_QWORD *)(a9 + 8) = 0;
    return result;
  }
  if ( !(_DWORD)v131 )
    goto LABEL_45;
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v130,
    &v130[4 * (unsigned int)v131],
    (unsigned int)v131,
    MoreRecentlyInstalledByUser);
  v15 = 0;
  v16 = 1;
  ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v45);
  string = 0;
  v35 = 0;
LABEL_6:
  v19 = v130;
  v20 = v130;
  while ( v20 != &v19[4 * (unsigned int)v131] )
  {
    if ( !(unsigned __int8)PackageInstalledForScope(v20, v16, v17, v18) )
      goto LABEL_26;
    v41 = 0;
    v40 = 0;
    v36 = 0;
    v38 = 0;
    ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)&v46);
    v13 = (unsigned int) IPackagedComCatalogContext::`vcall'{72,{flat}}(a5, *v20, a6, &v46, &v41, &v40);
    v33 = v41;
    CPackagedComCatalog::LogReadEntryResult(v13, &v46, v20, a6);
    if ( (int)v13 >= 0 )
    {
      HasAnyImplementationWithMachineScope = ClassRegistrationHasAnyImplementationWithMachineScope((const struct ComClassRegistrationEntryProperties *)&v46);
      LOBYTE(v23) = ClassRegistrationHasAnyImplementationWithUserScope((const struct ComClassRegistrationEntryProperties *)&v46);
      LOBYTE(v24) = HasAnyImplementationWithMachineScope;
      if ( !(unsigned __int8)RegistrationScopeMatchesInstallScope(v23, v24, v16)
        || !ClassRegistrationHasAnyImplementationWithSupportedSyntaxVersion((const struct ComClassRegistrationEntryProperties *)&v46) )
      {
        goto LABEL_17;
      }
      v33 = v34;
      LODWORD(v13) = _lambda_384cae988b9b93015a87ed243e331da0_::operator()(a9, v20, v16, &v46);
    }
    if ( (_DWORD)v13 != -2147024894 && (unsigned int)(v13 + 2147221165) > 1 && (_DWORD)v13 != -2147024883 )
    {
      if ( (int)v13 < 0 )
        goto LABEL_39;
LABEL_17:
      if ( v36 == 2 )
      {
        if ( !v38 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x10E0,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            v21);
        if ( v35 )
        {
          v28 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(&v34);
          v29 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v37);
          if ( !(unsigned __int8)CPackagedComCatalog::EffectiveClsctxRanking::operator<(v28, v29) )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x10E4,
              (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
              v30);
        }
        LODWORD(v13) = 0;
        ComClassRegistrationEntryProperties::operator=((__int64)v45, (__int64)&v46);
        OpaqueString::operator=(&string, v20);
        v34 = *(_DWORD *)std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v37);
        if ( !v35 )
          v35 = 1;
LABEL_39:
        ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(&v46);
        if ( (int)v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1114,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v13,
            v33);
          WindowsDeleteString(string);
          ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v45);
          goto LABEL_3;
        }
        break;
      }
      if ( v36 == 1 )
      {
        if ( !v38 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x10EF,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            v21);
        if ( v35 == (v38 == 0)
          || (v25 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(&v34),
              v26 = std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v37),
              (unsigned __int8)CPackagedComCatalog::EffectiveClsctxRanking::operator<(v25, v26)) )
        {
          ComClassRegistrationEntryProperties::operator=((__int64)v45, (__int64)&v46);
          OpaqueString::operator=(&string, v20);
          v34 = *(_DWORD *)std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(v37);
          if ( !v35 )
            v35 = 1;
        }
      }
      goto LABEL_25;
    }
    v15 = 1;
LABEL_25:
    ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(&v46);
    v19 = v130;
LABEL_26:
    v20 += 4;
    v27 = &v19[4 * (unsigned int)v131];
    if ( v20 == v27 )
    {
      if ( v16 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v19,
          v27,
          (32LL * (unsigned int)v131) >> 5,
          MoreRecentlyInstalledByOneTime);
        v16 = 2;
        goto LABEL_6;
      }
      if ( v16 == 2 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v19,
          v27,
          (32LL * (unsigned int)v131) >> 5,
          MoreRecentlyInstalledByMachine);
        v16 = 0;
        goto LABEL_6;
      }
    }
  }
  if ( v35 )
  {
    ComClassRegistrationEntryProperties::operator=(v42, (__int64)v45);
    *v43 = string;
    v31 = (_DWORD *)std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(&v34);
    *v44 = *v31;
    WindowsDeleteString(0);
    ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v45);
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v129);
    WindowsDeleteString(*(HSTRING *)(a9 + 8));
    result = 0;
    goto LABEL_46;
  }
  WindowsDeleteString(string);
  ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v45);
  if ( v15 )
  {
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v129);
    WindowsDeleteString(*(HSTRING *)(a9 + 8));
    result = 2147942413LL;
    goto LABEL_46;
  }
LABEL_45:
  PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v129);
  WindowsDeleteString(*(HSTRING *)(a9 + 8));
  result = 2147942402LL;
LABEL_46:
  *(_QWORD *)(a9 + 8) = 0;
  return result;
}

```

## disassembly

```asm
0x18009515c  push    rbp
0x18009515e  push    rbx
0x18009515f  push    rsi
0x180095160  push    rdi
0x180095161  push    r12
0x180095163  push    r13
0x180095165  push    r14
0x180095167  push    r15
0x180095169  lea     rbp, [rsp-4C8h]
0x180095171  sub     rsp, 5C8h
0x180095178  mov     rax, cs:__security_cookie
0x18009517f  xor     rax, rsp
0x180095182  mov     [rbp+500h+var_50], rax
0x180095189  mov     r13, [rbp+500h+arg_20]
0x180095190  xorps   xmm0, xmm0
0x180095193  mov     r12, [rbp+500h+arg_28]
0x18009519a  mov     r14, rdx
0x18009519d  mov     rbx, [rbp+500h+arg_38]
0x1800951a4  mov     rdi, r9
0x1800951a7  mov     rsi, [rbp+500h+arg_40]
0x1800951ae  mov     r15, r8
0x1800951b1  mov     [rsp+600h+var_588], rdx
0x1800951b6  xor     edx, edx
0x1800951b8  xor     eax, eax
0x1800951ba  mov     [rbp+500h+var_580], r8
0x1800951be  mov     [rbp+500h+var_2C4], eax
0x1800951c4  mov     [rbp+500h+var_226], eax
0x1800951ca  mov     [rbp+500h+var_222], ax
0x1800951d1  mov     [rbp+500h+var_174], eax
0x1800951d7  mov     [rsp+600h+var_590], rcx
0x1800951dc  mov     [rbp+500h+var_330], dl
0x1800951e2  mov     [rbp+500h+var_32C], edx
0x1800951e8  mov     [rbp+500h+var_328], dl
0x1800951ee  mov     [rbp+500h+var_320], rdx
0x1800951f5  mov     [rbp+500h+var_318], dl
0x1800951fb  mov     [rbp+500h+var_310], rdx
0x180095202  mov     [rbp+500h+var_308], dl
0x180095208  mov     [rbp+500h+var_300], rdx
0x18009520f  mov     [rbp+500h+var_2F8], dl
0x180095215  mov     [rbp+500h+var_2F0], rdx
0x18009521c  mov     [rbp+500h+var_2E8], rdx
0x180095223  mov     [rbp+500h+var_2E0], rdx
0x18009522a  mov     [rbp+500h+var_2D8], dl
0x180095230  movups  [rbp+500h+var_2D4], xmm0
0x180095237  mov     [rbp+500h+var_2C0], dl
0x18009523d  mov     [rbp+500h+var_2B8], rdx
0x180095244  mov     [rbp+500h+var_2B0], dl
0x18009524a  mov     [rbp+500h+var_2A8], rdx
0x180095251  mov     [rbp+500h+var_2A0], dl
0x180095257  mov     [rbp+500h+var_298], rdx
0x18009525e  mov     [rbp+500h+var_290], dl
0x180095264  mov     [rbp+500h+var_288], rdx
0x18009526b  mov     [rbp+500h+var_280], dl
0x180095271  mov     [rbp+500h+var_278], rdx
0x180095278  mov     [rbp+500h+var_270], rdx
0x18009527f  mov     [rbp+500h+var_268], dl
0x180095285  movdqa  [rbp+500h+var_260], xmm0
0x18009528d  mov     [rbp+500h+var_250], dl
0x180095293  mov     [rbp+500h+var_248], rdx
0x18009529a  mov     [rbp+500h+var_240], dl
0x1800952a0  mov     [rbp+500h+var_238], rdx
0x1800952a7  mov     [rbp+500h+var_230], dl
0x1800952ad  mov     [rbp+500h+var_22C], edx
0x1800952b3  mov     [rbp+500h+var_228], dx
0x1800952ba  mov     [rbp+500h+var_220], dl
0x1800952c0  mov     [rbp+500h+var_218], rdx
0x1800952c7  mov     [rbp+500h+var_210], dl
0x1800952cd  mov     [rbp+500h+var_208], rdx
0x1800952d4  mov     [rbp+500h+var_200], dl
0x1800952da  mov     [rbp+500h+var_1F8], rdx
0x1800952e1  mov     [rbp+500h+var_1F0], dl
0x1800952e7  mov     [rbp+500h+var_1E8], rdx
0x1800952ee  mov     [rbp+500h+var_1E0], rdx
0x1800952f5  mov     [rbp+500h+var_1D8], dl
0x1800952fb  mov     [rbp+500h+var_1D0], rdx
0x180095302  mov     [rbp+500h+var_1C8], dl
0x180095308  mov     [rbp+500h+var_1C0], rdx
0x18009530f  mov     [rbp+500h+var_1B8], dl
0x180095315  mov     [rbp+500h+var_1B0], rdx
0x18009531c  mov     [rbp+500h+var_1A8], dl
0x180095322  mov     [rbp+500h+var_1A0], rdx
0x180095329  mov     [rbp+500h+var_198], rdx
0x180095330  mov     [rbp+500h+var_190], rdx
0x180095337  mov     [rbp+500h+var_188], dl
0x18009533d  movups  [rbp+500h+var_184], xmm0
0x180095344  mov     [rbp+500h+var_170], dl
0x18009534a  mov     [rbp+500h+var_168], rdx
0x180095351  mov     [rbp+500h+var_160], dl
0x180095357  mov     [rbp+500h+var_15C], edx
0x18009535d  mov     [rbp+500h+var_158], dl
0x180095363  mov     [rbp+500h+var_154], edx
0x180095369  mov     [rbp+500h+var_150], dl
0x18009536f  mov     [rbp+500h+var_14C], edx
0x180095375  mov     [rbp+500h+var_148], dx
0x18009537c  movups  [rbp+500h+var_138], xmm0
0x180095383  mov     qword ptr [rbp+500h+var_138], rdx
0x18009538a  mov     word ptr [rbp+500h+var_138+8], dx
0x180095391  mov     [rbp+500h+var_140], dl
0x180095397  mov     [rbp+500h+var_128], dl
0x18009539d  mov     [rbp+500h+var_124], edx
0x1800953a3  mov     [rbp+500h+var_120], dl
0x1800953a9  mov     [rbp+500h+var_118], rdx
0x1800953b0  mov     [rbp+500h+var_110], dl
0x1800953b6  mov     [rbp+500h+var_10C], edx
0x1800953bc  mov     [rbp+500h+var_108], dl
0x1800953c2  mov     [rbp+500h+var_104], edx
0x1800953c8  mov     [rbp+500h+var_100], dl
0x1800953ce  mov     [rbp+500h+var_FC], edx
0x1800953d4  mov     [rbp+500h+var_F8], dl
0x1800953da  mov     [rbp+500h+var_F4], edx
0x1800953e0  lea     rdx, [rbp+500h+var_330]
0x1800953e7  mov     [rbp+500h+var_146], eax
0x1800953ed  mov     [rbp+500h+var_142], ax
0x1800953f4  call    ??4ComClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComClassRegistrationEntryProperties::operator=(ComClassRegistrationEntryProperties &&)
0x1800953f9  lea     rcx, [rbp+500h+var_330]; this
0x180095400  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x180095405  mov     qword ptr [r14], 0
0x18009540c  lea     rcx, [rbp+500h+var_F0]; this
0x180095413  mov     dword ptr [r15], 0
0x18009541a  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x18009541f  mov     al, [rbp+500h+arg_30]
0x180095425  lea     rcx, [rbp+500h+var_F0]; this
0x18009542c  mov     [rsp+600h+var_5D8], rbx; PackageFilter *
0x180095431  mov     r9, r12
0x180095434  mov     r8, r13
0x180095437  mov     [rsp+600h+var_5E0], al; int
0x18009543b  mov     rdx, rdi
0x18009543e  call    ??$GetInstalledPackagesContainingEntry@UComClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)
0x180095443  mov     ebx, eax
0x180095445  test    eax, eax
0x180095447  jns     short loc_18009548F
0x180095449  mov     rcx, [rbp+508h]; this
0x180095450  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180095457  mov     r9d, eax; char *
0x18009545a  mov     edx, 1083h; void *
0x18009545f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180095464  lea     rcx, [rbp+500h+var_F0]; this
0x18009546b  call    ??1PackageListBuffer@@QEAA@XZ; PackageListBuffer::~PackageListBuffer(void)
0x180095470  mov     rcx, [rsi+8]; string
0x180095474  call    cs:__imp_WindowsDeleteString
0x18009547b  nop     dword ptr [rax+rax+00h]
0x180095480  mov     eax, ebx
0x180095482  mov     qword ptr [rsi+8], 0
0x18009548a  jmp     loc_180095908
0x18009548f  mov     rax, [rbp+500h+var_68]
0x180095496  xor     ebx, ebx
0x180095498  test    eax, eax
0x18009549a  jz      loc_1800958E3
0x1800954a0  mov     rcx, [rbp+500h+var_70]
0x1800954a7  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800954ae  mov     edx, eax
0x1800954b0  shl     rdx, 5
0x1800954b4  add     rdx, rcx
0x1800954b7  mov     r8d, eax
0x1800954ba  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800954bf  lea     rcx, [rbp+500h+var_570]; this
0x1800954c3  mov     r15b, bl
0x1800954c6  lea     r14d, [rbx+1]
0x1800954ca  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x1800954cf  mov     [rsp+600h+string], rbx
0x1800954d4  mov     [rsp+600h+var_5BC], bl
0x1800954d8  mov     r10, [rbp+500h+var_70]
0x1800954df  mov     rdi, r10
0x1800954e2  mov     eax, dword ptr [rbp+500h+var_68]
0x1800954e8  shl     rax, 5
0x1800954ec  add     rax, r10
0x1800954ef  cmp     rdi, rax
0x1800954f2  jz      loc_180095837
0x1800954f8  mov     edx, r14d
0x1800954fb  mov     rcx, rdi
0x1800954fe  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x180095503  test    al, al
0x180095505  jz      loc_1800956CA
0x18009550b  lea     rcx, [rbp+500h+var_330]; this
0x180095512  mov     [rsp+600h+var_598], rbx
0x180095517  mov     [rsp+600h+var_5A0], rbx
0x18009551c  mov     [rsp+600h+var_5B8], ebx
0x180095520  mov     [rsp+600h+var_5AC], bl
0x180095524  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x180095529  mov     rdx, [rdi]
0x18009552c  lea     rcx, [rsp+600h+var_5A0]
0x180095531  mov     [rsp+600h+var_5D8], rcx
0x180095536  lea     rax, [rsp+600h+var_598]
0x18009553b  mov     rcx, r13
0x18009553e  mov     qword ptr [rsp+600h+var_5E0], rax
0x180095543  lea     r9, [rbp+500h+var_330]
0x18009554a  mov     r8, r12
0x18009554d  call    ??_9IPackagedComCatalogContext@@$BEI@AA; [thunk]: IPackagedComCatalogContext::`vcall'{72,{flat}}
0x180095552  mov     ebx, eax
0x180095554  lea     rdx, [rbp+500h+var_330]
0x18009555b  mov     rax, [rsp+600h+var_5A0]
0x180095560  mov     r9, r12
0x180095563  mov     [rsp+600h+var_5D8], rax
0x180095568  mov     r8, rdi
0x18009556b  mov     rax, [rsp+600h+var_598]
0x180095570  mov     ecx, ebx
0x180095572  mov     qword ptr [rsp+600h+var_5E0], rax
0x180095577  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComClassRegistrationEntryProperties@@AEBVOpaqueString@@AEBU_GUID@@W4ComClassRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComClassRegistrationEntryProperties const &,OpaqueString const &,_GUID const &,ComClassRegistrationEntryPropertyFlags,ComClassRegistrationEntryPropertyFlags)
0x18009557c  test    ebx, ebx
0x18009557e  js      short loc_1800955EF
0x180095580  lea     rcx, [rbp+500h+var_330]; struct ComClassRegistrationEntryProperties *
0x180095587  call    ?ClassRegistrationHasAnyImplementationWithMachineScope@@YA_NAEBUComClassRegistrationEntryProperties@@@Z; ClassRegistrationHasAnyImplementationWithMachineScope(ComClassRegistrationEntryProperties const &)
0x18009558c  lea     rcx, [rbp+500h+var_330]; struct ComClassRegistrationEntryProperties *
0x180095593  mov     bl, al
0x180095595  call    ?ClassRegistrationHasAnyImplementationWithUserScope@@YA_NAEBUComClassRegistrationEntryProperties@@@Z; ClassRegistrationHasAnyImplementationWithUserScope(ComClassRegistrationEntryProperties const &)
0x18009559a  mov     cl, al
0x18009559c  mov     r8d, r14d
0x18009559f  mov     dl, bl
0x1800955a1  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x1800955a6  test    al, al
0x1800955a8  jz      short loc_18009561E
0x1800955aa  lea     rcx, [rbp+500h+var_330]; struct ComClassRegistrationEntryProperties *
0x1800955b1  call    ?ClassRegistrationHasAnyImplementationWithSupportedSyntaxVersion@@YA_NAEBUComClassRegistrationEntryProperties@@@Z; ClassRegistrationHasAnyImplementationWithSupportedSyntaxVersion(ComClassRegistrationEntryProperties const &)
0x1800955b6  test    al, al
0x1800955b8  jz      short loc_18009561E
0x1800955ba  lea     rax, [rsp+600h+var_5B0]
0x1800955bf  mov     r8d, r14d
0x1800955c2  mov     [rsp+600h+var_5D0], rax
0x1800955c7  lea     r9, [rbp+500h+var_330]
0x1800955ce  lea     rax, [rsp+600h+var_5B8]
0x1800955d3  mov     rdx, rdi
0x1800955d6  mov     [rsp+600h+var_5D8], rax
0x1800955db  mov     rcx, rsi
0x1800955de  mov     rax, [rsp+40h]
0x1800955e3  mov     qword ptr [rsp+600h+var_5E0], rax; int
0x1800955e8  call    ??R_lambda_384cae988b9b93015a87ed243e331da0_@@QEBA@AEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComClassRegistrationEntryProperties@@V?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@PEAW4RegistrationApplicability@CPackagedComCatalog@@PEAV56@@Z; _lambda_384cae988b9b93015a87ed243e331da0_::operator()(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,std::optional<CPackagedComCatalog::EffectiveClsctxRanking>,CPackagedComCatalog::RegistrationApplicability *,std::optional<CPackagedComCatalog::EffectiveClsctxRanking> *)
0x1800955ed  mov     ebx, eax
0x1800955ef  cmp     ebx, 80070002h
0x1800955f5  jz      loc_1800956B2
0x1800955fb  lea     eax, [rbx+7FFBFEADh]
0x180095601  cmp     eax, 1
0x180095604  jbe     loc_1800956B2
0x18009560a  cmp     ebx, 8007000Dh
0x180095610  jz      loc_1800956B2
0x180095616  test    ebx, ebx
0x180095618  js      loc_1800957EB
0x18009561e  cmp     [rsp+600h+var_5B8], 2
0x180095623  jz      loc_18009574B
0x180095629  cmp     [rsp+600h+var_5B8], 1
0x18009562e  jnz     loc_1800956B5
0x180095634  cmp     [rsp+600h+var_5AC], 0
0x180095639  mov     rcx, [rbp+508h]; this
0x180095640  setz    al
0x180095643  test    al, al
0x180095645  jnz     loc_180095739
0x18009564b  cmp     [rsp+600h+var_5BC], al
0x18009564f  jz      short loc_180095677
0x180095651  lea     rcx, [rsp+600h+var_5C0]
0x180095656  call    ?value@?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@QEGAAAEAVEffectiveClsctxRanking@CPackagedComCatalog@@XZ; std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(void)
0x18009565b  lea     rcx, [rsp+600h+var_5B0]
0x180095660  mov     rbx, rax
0x180095663  call    ?value@?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@QEGAAAEAVEffectiveClsctxRanking@CPackagedComCatalog@@XZ; std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(void)
0x180095668  mov     rdx, rax
0x18009566b  mov     rcx, rbx
0x18009566e  call    ??MEffectiveClsctxRanking@CPackagedComCatalog@@QEBA_NAEBV01@@Z; CPackagedComCatalog::EffectiveClsctxRanking::operator<(CPackagedComCatalog::EffectiveClsctxRanking const &)
0x180095673  test    al, al
0x180095675  jz      short loc_1800956B5
0x180095677  lea     rdx, [rbp+500h+var_330]
0x18009567e  lea     rcx, [rbp+500h+var_570]
0x180095682  call    ??4ComClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComClassRegistrationEntryProperties::operator=(ComClassRegistrationEntryProperties &&)
0x180095687  mov     rdx, rdi
0x18009568a  lea     rcx, [rsp+600h+string]
0x18009568f  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x180095694  lea     rcx, [rsp+600h+var_5B0]
0x180095699  call    ?value@?$optional@VEffectiveClsctxRanking@CPackagedComCatalog@@@std@@QEGAAAEAVEffectiveClsctxRanking@CPackagedComCatalog@@XZ; std::optional<CPackagedComCatalog::EffectiveClsctxRanking>::value(void)
0x18009569e  cmp     [rsp+600h+var_5BC], 0
0x1800956a3  mov     ecx, [rax]
0x1800956a5  mov     [rsp+600h+var_5C0], ecx
0x1800956a9  jnz     short loc_1800956B5
0x1800956ab  mov     [rsp+600h+var_5BC], 1
0x1800956b0  jmp     short loc_1800956B5
0x1800956b2  mov     r15b, 1
0x1800956b5  lea     rcx, [rbp+500h+var_330]; this
0x1800956bc  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800956c1  mov     r10, [rbp+500h+var_70]
0x1800956c8  xor     ebx, ebx
0x1800956ca  mov     edx, dword ptr [rbp+500h+var_68]
0x1800956d0  add     rdi, 20h ; ' '
0x1800956d4  shl     rdx, 5
0x1800956d8  add     rdx, r10
0x1800956db  cmp     rdi, rdx
0x1800956de  jnz     loc_1800954E2
0x1800956e4  cmp     r14d, 1
0x1800956e8  jnz     short loc_18009570E
0x1800956ea  mov     r8, rdx
0x1800956ed  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800956f4  sub     r8, r10
0x1800956f7  mov     rcx, r10
0x1800956fa  sar     r8, 5
0x1800956fe  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x180095703  mov     r14d, 2
0x180095709  jmp     loc_1800954D8
0x18009570e  cmp     r14d, 2
0x180095712  jnz     loc_1800954E2
0x180095718  mov     r8, rdx
0x18009571b  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x180095722  sub     r8, r10
0x180095725  mov     rcx, r10
0x180095728  sar     r8, 5
0x18009572c  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
  ... truncated ...
```
