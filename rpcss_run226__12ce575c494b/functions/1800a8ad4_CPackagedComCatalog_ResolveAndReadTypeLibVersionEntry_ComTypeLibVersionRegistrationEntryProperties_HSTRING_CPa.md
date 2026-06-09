# CPackagedComCatalog::ResolveAndReadTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::TypeLibVersion *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,CPackagedComCatalog::TypeLibVersion,ulong,bool,bool,ComRegistrationVisibility,PackageFilter const *,MainPackageFamilyNameFilter *)

- ea: `0x1800a8ad4`
- end: `0x1800a97a3`
- name: `?ResolveAndReadTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAVTypeLibVersion@1@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@V41@K_N7W4ComRegistrationVisibility@@PEBVPackageFilter@@PEAVMainPackageFamilyNameFilter@@@Z`
- size: `3279`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800db5fc`

## callees

- `0x18000bbe8`
- `0x18002ba28`
- `0x1800414d0`
- `0x180047990`
- `0x180048090`
- `0x1800483bc`
- `0x18007b510`
- `0x180080b44`
- `0x18008e98c`
- `0x1800a8ad4`
- `0x1800a9ec0`
- `0x1800b27e0`
- `0x1800d539c`
- `0x1800d6d5c`
- `0x1800d9244`
- `0x1800e1654`
- `0x1800e68a0`
- `0x1800e69ac`
- `0x1800e6fa4`
- `0x1800e7a10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a96d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a96ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a972b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a973d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9752`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8cb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8f43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8fa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8fbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9456`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a96d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a96ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a972b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a973d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9752`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a9012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a8d7f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800a9012`

## string_xrefs

- `0x1800a8c21`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a8ca4`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a8f65`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a8f8c`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a9434`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a96b3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::ResolveAndReadTypeLibVersionEntry(
        __int64 a1,
        HSTRING *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        unsigned int *a7,
        unsigned int a8,
        bool a9,
        char a10,
        int a11,
        PackageFilter *a12,
        struct StateRepository::Cache::Manager_NoThrow *a13)
{
  char v16; // al
  __int64 v17; // rcx
  __int64 v18; // rsi
  int InstalledPackagesContaining; // eax
  unsigned int v20; // ebx
  char v21; // bl
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 v24; // r9
  int v25; // eax
  HSTRING *i; // rsi
  unsigned __int16 *StringRawBuffer; // rax
  int IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet; // eax
  _QWORD *v29; // rbx
  int SupportedAndVisibleTypeLibVersionEntry; // eax
  unsigned int v31; // eax
  ComTypeLibVersionRegistrationEntryProperties *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rdx
  ComTypeLibVersionRegistrationEntryProperties *v35; // rcx
  int v36; // r15d
  int v37; // r12d
  HSTRING *v38; // rsi
  char v39; // r13
  unsigned __int16 *v40; // rax
  _QWORD *v41; // rbx
  __int64 v42; // xmm0_8
  char v43; // bl
  char v44; // bl
  __int64 v45; // r8
  __int64 v46; // r9
  HSTRING *v47; // rcx
  int v48; // r15d
  HSTRING *v49; // rbx
  __int64 v50; // rdx
  int v51; // eax
  unsigned int v52; // esi
  __int64 v53; // xmm6_8
  unsigned int v54; // r15d
  unsigned int v55; // esi
  HSTRING *v56; // r10
  HSTRING *v57; // rbx
  int HighestTypeLibVersionEntryForPackage; // eax
  __int64 v59; // rdx
  __int64 v60; // rcx
  unsigned int v61; // r14d
  HSTRING *v62; // rdx
  HSTRING v63; // rbx
  HSTRING *p_string; // [rsp+28h] [rbp-E0h]
  char v66; // [rsp+48h] [rbp-C0h]
  HSTRING string; // [rsp+50h] [rbp-B8h] BYREF
  char v68; // [rsp+58h] [rbp-B0h]
  __int16 v69; // [rsp+5Ah] [rbp-AEh]
  HSTRING v70; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v71; // [rsp+68h] [rbp-A0h]
  unsigned int v72; // [rsp+70h] [rbp-98h]
  _BYTE v73[4]; // [rsp+78h] [rbp-90h] BYREF
  int v74; // [rsp+7Ch] [rbp-8Ch]
  char v75; // [rsp+80h] [rbp-88h]
  int v76; // [rsp+84h] [rbp-84h]
  char v77; // [rsp+88h] [rbp-80h]
  __int64 v78; // [rsp+90h] [rbp-78h]
  char v79; // [rsp+98h] [rbp-70h]
  __int64 v80; // [rsp+A0h] [rbp-68h]
  char v81; // [rsp+A8h] [rbp-60h]
  __int64 v82; // [rsp+B0h] [rbp-58h]
  char v83; // [rsp+B8h] [rbp-50h]
  __int64 v84; // [rsp+C0h] [rbp-48h]
  int v85; // [rsp+C8h] [rbp-40h]
  char v86; // [rsp+CCh] [rbp-3Ch]
  int v87; // [rsp+D0h] [rbp-38h]
  char v88; // [rsp+D4h] [rbp-34h]
  int v89; // [rsp+D8h] [rbp-30h]
  char v90; // [rsp+DCh] [rbp-2Ch]
  __int64 v91; // [rsp+E0h] [rbp-28h]
  _BYTE v92[4]; // [rsp+E8h] [rbp-20h] BYREF
  int v93; // [rsp+ECh] [rbp-1Ch]
  char v94; // [rsp+F0h] [rbp-18h]
  int v95; // [rsp+F4h] [rbp-14h]
  char v96; // [rsp+F8h] [rbp-10h]
  __int64 v97; // [rsp+100h] [rbp-8h]
  char v98; // [rsp+108h] [rbp+0h]
  __int64 v99; // [rsp+110h] [rbp+8h]
  char v100; // [rsp+118h] [rbp+10h]
  __int64 v101; // [rsp+120h] [rbp+18h]
  char v102; // [rsp+128h] [rbp+20h]
  __int64 v103; // [rsp+130h] [rbp+28h]
  __int16 v104; // [rsp+138h] [rbp+30h]
  char v105; // [rsp+13Ch] [rbp+34h]
  int v106; // [rsp+140h] [rbp+38h]
  char v107; // [rsp+144h] [rbp+3Ch]
  int v108; // [rsp+148h] [rbp+40h]
  char v109; // [rsp+14Ch] [rbp+44h]
  int v110; // [rsp+150h] [rbp+48h]
  __int64 v111; // [rsp+158h] [rbp+50h]
  __int64 v112; // [rsp+160h] [rbp+58h]
  __int64 v113; // [rsp+168h] [rbp+60h]
  unsigned int v114; // [rsp+170h] [rbp+68h]
  HSTRING *v115; // [rsp+178h] [rbp+70h]
  __int128 v116; // [rsp+188h] [rbp+80h] BYREF
  __int64 v117; // [rsp+198h] [rbp+90h]
  __int128 v118; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 v119; // [rsp+1B8h] [rbp+B0h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v120; // [rsp+1C8h] [rbp+C0h]
  _BYTE v121[128]; // [rsp+1D8h] [rbp+D0h] BYREF
  HSTRING *v122; // [rsp+258h] [rbp+150h]
  unsigned int v123; // [rsp+260h] [rbp+158h]
  unsigned __int16 v124[8]; // [rsp+278h] [rbp+170h] BYREF
  int v125; // [rsp+288h] [rbp+180h]
  wil::details::in1diag3 *retaddr; // [rsp+2E0h] [rbp+1D8h]

  v112 = a5;
  v111 = a6;
  v16 = *((_BYTE *)a7 + 8);
  v117 = a1;
  v115 = a2;
  v120 = a13;
  LOBYTE(v69) = v16;
  if ( !v16 && a9 )
    MicrosoftTelemetryAssertTriggeredNoArgs(0);
  v73[0] = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v85 = 0;
  v91 = 0;
  ComTypeLibVersionRegistrationEntryProperties::operator=(a1, v73);
  ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v73);
  *a2 = 0;
  if ( a13 && !a10 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v17);
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v121);
  v18 = v112;
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(
                                  (PackageListBuffer *)v121,
                                  a10,
                                  a12);
  v20 = InstalledPackagesContaining;
  if ( InstalledPackagesContaining < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x215C,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)InstalledPackagesContaining,
      (int)p_string);
    goto LABEL_98;
  }
  if ( !v123 )
  {
LABEL_97:
    v20 = -2147319779;
    goto LABEL_98;
  }
  v21 = *((_BYTE *)a7 + 8);
  string = 0;
  if ( v21 )
  {
    v22 = *a7;
    v125 = 0;
    LODWORD(p_string) = a7[1];
    *(_OWORD *)v124 = 0;
    if ( (int)StringCchPrintfW(v124, 0xAu, L"%x.%x", v22) < 0 )
    {
      v20 = -2147024809;
      v23 = 8565;
      v24 = 2147942487LL;
      goto LABEL_13;
    }
    v25 = Microsoft::WRL::Wrappers::HString::Set<10>(&string, v124);
    v20 = v25;
    if ( v25 < 0 )
    {
      v24 = (unsigned int)v25;
      v23 = 8567;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)v24,
        (int)p_string);
LABEL_14:
      WindowsDeleteString(string);
      string = 0;
      goto LABEL_98;
    }
    v21 = *((_BYTE *)a7 + 8);
  }
  if ( a13 )
  {
    v92[0] = 0;
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
    v103 = 0;
    v104 = 0;
    v105 = 0;
    v106 = 0;
    v107 = 0;
    v108 = 0;
    v109 = 0;
    v110 = 0;
    v70 = 0;
    BYTE8(v116) = 0;
    if ( !v21 )
      goto LABEL_41;
    for ( i = v122; i != &v122[4 * v123]; i += 4 )
    {
      BYTE8(v118) = 0;
      StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(*i, 0);
      IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet = MainPackageFamilyNameFilter::TryGetIndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet(
                                                                  a13,
                                                                  StringRawBuffer);
      v20 = IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet;
      if ( IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet < 0 )
      {
        v34 = 8605;
LABEL_37:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v34,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet,
          (int)p_string);
        goto LABEL_38;
      }
      if ( BYTE8(v118) )
      {
        if ( !BYTE8(v116)
          || (v29 = (_QWORD *)std::optional<unsigned __int64>::value(&v118),
              *v29 < *(_QWORD *)std::optional<unsigned __int64>::value(&v116)) )
        {
          LOWORD(v85) = 0;
          v73[0] = 0;
          v74 = 0;
          v75 = 0;
          v76 = 0;
          v77 = 0;
          v78 = 0;
          v79 = 0;
          v80 = 0;
          v81 = 0;
          v82 = 0;
          v83 = 0;
          v84 = 0;
          v86 = 0;
          v87 = 0;
          v88 = 0;
          v89 = 0;
          v90 = 0;
          LODWORD(v91) = 0;
          v68 = 0;
          p_string = &string;
          SupportedAndVisibleTypeLibVersionEntry = CPackagedComCatalog::TryReadSupportedAndVisibleTypeLibVersionEntry(
                                                     v73,
                                                     v112,
                                                     i,
                                                     v111);
          v20 = SupportedAndVisibleTypeLibVersionEntry;
          if ( SupportedAndVisibleTypeLibVersionEntry < 0 )
          {
            v33 = 8614;
LABEL_35:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v33,
              (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
              (const char *)(unsigned int)SupportedAndVisibleTypeLibVersionEntry,
              (int)p_string);
            ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v73);
LABEL_38:
            WindowsDeleteString(v70);
            ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v92);
            goto LABEL_14;
          }
          ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v73);
        }
      }
    }
    if ( BYTE8(v116) )
    {
      ComTypeLibVersionRegistrationEntryProperties::operator=(v117, v92);
      *v115 = v70;
      if ( a3 )
      {
        v31 = a7[2];
        *(_QWORD *)a3 = *(_QWORD *)a7;
        *(_DWORD *)(a3 + 8) = v31;
      }
LABEL_32:
      WindowsDeleteString(0);
      v32 = (ComTypeLibVersionRegistrationEntryProperties *)v92;
      goto LABEL_33;
    }
    if ( !a9 )
    {
LABEL_41:
      v36 = 0;
      v37 = 0;
      v38 = v122;
      v39 = 0;
      v66 = HIBYTE(v114);
      v69 = *(_WORD *)((char *)&v114 + 1);
      while ( v38 != &v122[4 * v123] )
      {
        BYTE8(v119) = 0;
        v40 = (unsigned __int16 *)WindowsGetStringRawBuffer(*v38, 0);
        IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet = MainPackageFamilyNameFilter::TryGetIndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet(
                                                                    v120,
                                                                    v40);
        v20 = IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet;
        if ( IndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet < 0 )
        {
          v34 = 8665;
          goto LABEL_37;
        }
        if ( BYTE8(v119) )
        {
          if ( !BYTE8(v116)
            || (v41 = (_QWORD *)std::optional<unsigned __int64>::value(&v119),
                *v41 < *(_QWORD *)std::optional<unsigned __int64>::value(&v116)) )
          {
            v42 = *(_QWORD *)a7;
            LOWORD(v85) = 0;
            v114 = a7[2];
            LOBYTE(v72) = 0;
            v73[0] = 0;
            v74 = 0;
            v75 = 0;
            v76 = 0;
            v77 = 0;
            v78 = 0;
            v79 = 0;
            v80 = 0;
            v81 = 0;
            v82 = 0;
            v83 = 0;
            v84 = 0;
            v86 = 0;
            v87 = 0;
            v88 = 0;
            v89 = 0;
            v90 = 0;
            LODWORD(v91) = 0;
            LODWORD(p_string) = a11;
            v71 = 0;
            v113 = v42;
            SupportedAndVisibleTypeLibVersionEntry = CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage(
                                                       v73,
                                                       v112,
                                                       v38,
                                                       v111);
            v20 = SupportedAndVisibleTypeLibVersionEntry;
            if ( SupportedAndVisibleTypeLibVersionEntry < 0 )
            {
              v33 = 8674;
              goto LABEL_35;
            }
            v43 = v72;
            if ( (_BYTE)v72 )
            {
              if ( CPackagedComCatalog::IsTypeLibLocaleIdAcceptable(v73[0] != 0 ? v74 : 0, a8, a9) )
              {
                ComTypeLibVersionRegistrationEntryProperties::operator=(v92, v73);
                OpaqueString::operator=(&v70, v38);
                v39 = v43;
                v44 = HIBYTE(v72);
                v36 = v71;
                v37 = HIDWORD(v71);
                v116 = v119;
                v69 = *(_WORD *)((char *)&v72 + 1);
                v66 = HIBYTE(v72);
                if ( !*(_QWORD *)std::optional<unsigned __int64>::value(&v119) )
                {
                  ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v73);
                  goto LABEL_57;
                }
              }
            }
            ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v73);
          }
        }
        v38 += 4;
      }
      v44 = v66;
LABEL_57:
      if ( BYTE8(v116) )
      {
        ComTypeLibVersionRegistrationEntryProperties::operator=(v117, v92);
        *v115 = v70;
        if ( a3 )
        {
          *(_WORD *)(a3 + 9) = v69;
          *(_BYTE *)(a3 + 11) = v44;
          *(_DWORD *)a3 = v36;
          *(_DWORD *)(a3 + 4) = v37;
          *(_BYTE *)(a3 + 8) = v39;
        }
        goto LABEL_32;
      }
    }
    WindowsDeleteString(v70);
    v35 = (ComTypeLibVersionRegistrationEntryProperties *)v92;
    goto LABEL_95;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v122,
    &v122[4 * v123],
    v123,
    MoreRecentlyInstalledByUser);
  v46 = 0;
  if ( !v21 )
    goto LABEL_74;
  v47 = v122;
  v48 = 1;
  v49 = v122;
  while ( 1 )
  {
    v50 = 4LL * v123;
    if ( v49 == &v47[v50] )
      break;
    v92[0] = 0;
    v104 = 0;
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
    v103 = 0;
    v105 = 0;
    v106 = 0;
    v107 = 0;
    v108 = 0;
    v109 = 0;
    v110 = 0;
    v68 = 0;
    v51 = CPackagedComCatalog::TryReadSupportedAndVisibleTypeLibVersionEntry(v92, v18, v49, v111);
    v52 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221C,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)v51,
        (int)&string);
      ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v92);
      WindowsDeleteString(string);
      string = 0;
      v20 = v52;
      goto LABEL_98;
    }
    v49 += 4;
    if ( v49 == &v122[4 * v123] )
    {
      if ( v48 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v122,
          &v122[4 * v123],
          (32LL * v123) >> 5,
          MoreRecentlyInstalledByOneTime);
        v48 = 2;
      }
      else
      {
        if ( v48 != 2 )
          goto LABEL_70;
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v122,
          &v122[4 * v123],
          (32LL * v123) >> 5,
          MoreRecentlyInstalledByMachine);
        v48 = 0;
      }
      v49 = v122;
    }
LABEL_70:
    ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v92);
    v47 = v122;
    v18 = v112;
  }
  if ( a9 )
  {
LABEL_96:
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_97;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v47,
    &v47[v50],
    v123,
    MoreRecentlyInstalledByUser);
  v46 = 0;
LABEL_74:
  v53 = *(_QWORD *)a7;
  v54 = a7[2];
  v73[0] = 0;
  v74 = 0;
  v55 = 1;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v84 = 0;
  LOWORD(v85) = 0;
  v86 = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  LODWORD(v91) = 0;
  v70 = 0;
LABEL_75:
  v56 = v122;
  v57 = v122;
  while ( v57 != &v56[4 * v123] )
  {
    if ( (unsigned __int8)PackageInstalledForScope(v57, v55, v45, v46) )
    {
      LOBYTE(v72) = v46;
      v104 = 0;
      v92[0] = v46;
      v93 = v46;
      v94 = v46;
      v95 = v46;
      v96 = v46;
      v97 = v46;
      v98 = v46;
      v99 = v46;
      v100 = v46;
      v101 = v46;
      v102 = v46;
      v103 = v46;
      v105 = v46;
      v106 = v46;
      v107 = v46;
      v108 = v46;
      v109 = v46;
      v110 = v46;
      v71 = 0;
      v113 = v53;
      v114 = v54;
      HighestTypeLibVersionEntryForPackage = CPackagedComCatalog::TryReadHighestTypeLibVersionEntryForPackage(
                                               v92,
                                               v112,
                                               v57,
                                               v111);
      v61 = HighestTypeLibVersionEntryForPackage;
      if ( HighestTypeLibVersionEntryForPackage < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x225F,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)HighestTypeLibVersionEntryForPackage,
          a11);
        ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v92);
        WindowsDeleteString(v70);
        ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v73);
        WindowsDeleteString(string);
        string = 0;
        v20 = v61;
        goto LABEL_98;
      }
      if ( (_BYTE)v72 )
      {
        LOBYTE(v59) = (_BYTE)v104 != 0 ? HIBYTE(v104) : 0;
        LOBYTE(v60) = (_BYTE)v59 == 0;
        if ( (unsigned __int8)RegistrationScopeMatchesInstallScope(v60, v59, v55) )
        {
          if ( CPackagedComCatalog::IsTypeLibLocaleIdAcceptable(v92[0] != 0 ? v93 : 0, a8, a9) )
          {
            v53 = v71;
            v54 = v72;
            ComTypeLibVersionRegistrationEntryProperties::operator=(v73, v92);
            OpaqueString::operator=(&v70, v57);
          }
        }
      }
      ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties((ComTypeLibVersionRegistrationEntryProperties *)v92);
      v56 = v122;
      v46 = 0;
    }
    v57 += 4;
    v62 = &v56[4 * v123];
    if ( v57 == v62 )
    {
      if ( v55 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v56,
          v62,
          (32LL * v123) >> 5,
          MoreRecentlyInstalledByOneTime);
        v46 = 0;
        v55 = 2;
        goto LABEL_75;
      }
      if ( v55 == 2 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v56,
          v62,
          (32LL * v123) >> 5,
          MoreRecentlyInstalledByMachine);
        v46 = 0;
        v55 = 0;
        goto LABEL_75;
      }
    }
  }
  v63 = v70;
  if ( !v70 )
  {
    WindowsDeleteString(0);
    v35 = (ComTypeLibVersionRegistrationEntryProperties *)v73;
LABEL_95:
    ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(v35);
    goto LABEL_96;
  }
  ComTypeLibVersionRegistrationEntryProperties::operator=(a1, v73);
  *v115 = v63;
  if ( a3 )
  {
    *(_QWORD *)a3 = v53;
    *(_DWORD *)(a3 + 8) = v54;
  }
  WindowsDeleteString(0);
  v32 = (ComTypeLibVersionRegistrationEntryProperties *)v73;
LABEL_33:
  ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(v32);
  WindowsDeleteString(string);
  v20 = 0;
  string = 0;
LABEL_98:
  PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v121);
  return v20;
}

```

## disassembly

```asm
0x1800a8ad4  mov     rax, rsp
0x1800a8ad7  mov     [rax+20h], rbx
0x1800a8adb  push    rbp
0x1800a8adc  push    rsi
0x1800a8add  push    rdi
0x1800a8ade  push    r12
0x1800a8ae0  push    r13
0x1800a8ae2  push    r14
0x1800a8ae4  push    r15
0x1800a8ae6  lea     rbp, [rax-1D8h]
0x1800a8aed  sub     rsp, 2A0h
0x1800a8af4  movaps  xmmword ptr [rax-48h], xmm6
0x1800a8af8  mov     rax, cs:__security_cookie
0x1800a8aff  xor     rax, rsp
0x1800a8b02  mov     [rbp+1D0h+var_48], rax
0x1800a8b09  mov     rax, [rbp+1D0h+arg_20]
0x1800a8b10  mov     r13, rcx
0x1800a8b13  mov     r14, [rbp+1D0h+arg_30]
0x1800a8b1a  mov     rdi, r8
0x1800a8b1d  mov     r15, [rbp+1D0h+arg_60]
0x1800a8b24  mov     rbx, rdx
0x1800a8b27  mov     rsi, [rbp+1D0h+arg_58]
0x1800a8b2e  mov     r12b, [rbp+1D0h+arg_40]
0x1800a8b35  mov     [rbp+1D0h+var_178], rax
0x1800a8b39  mov     rax, [rbp+1D0h+arg_28]
0x1800a8b40  mov     [rbp+1D0h+var_180], rax
0x1800a8b44  mov     al, [r14+8]
0x1800a8b48  mov     [rbp+1D0h+var_140], rcx
0x1800a8b4f  xor     ecx, ecx
0x1800a8b51  mov     [rbp+1D0h+var_160], rdx
0x1800a8b55  mov     [rbp+1D0h+var_110], r15
0x1800a8b5c  mov     byte ptr [rsp+2D0h+var_280+2], al
0x1800a8b60  test    al, al
0x1800a8b62  jnz     short loc_1800A8B70
0x1800a8b64  test    r12b, r12b
0x1800a8b67  jz      short loc_1800A8B70
0x1800a8b69  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a8b6e  xor     ecx, ecx
0x1800a8b70  xor     eax, eax
0x1800a8b72  mov     [rsp+2D0h+var_260], cl
0x1800a8b76  mov     [rsp+2D0h+var_25C], ecx
0x1800a8b7a  lea     rdx, [rsp+2D0h+var_260]
0x1800a8b7f  mov     [rsp+2D0h+var_258], cl
0x1800a8b83  mov     [rsp+2D0h+var_254], ecx
0x1800a8b87  mov     [rbp+1D0h+var_250], cl
0x1800a8b8a  mov     [rbp+1D0h+var_248], rcx
0x1800a8b8e  mov     [rbp+1D0h+var_240], cl
0x1800a8b91  mov     [rbp+1D0h+var_238], rcx
0x1800a8b95  mov     [rbp+1D0h+var_230], cl
0x1800a8b98  mov     [rbp+1D0h+var_228], rcx
0x1800a8b9c  mov     [rbp+1D0h+var_220], cl
0x1800a8b9f  mov     [rbp+1D0h+var_218], rcx
0x1800a8ba3  mov     [rbp+1D0h+var_20C], cl
0x1800a8ba6  mov     [rbp+1D0h+var_208], ecx
0x1800a8ba9  mov     [rbp+1D0h+var_204], cl
0x1800a8bac  mov     [rbp+1D0h+var_200], ecx
0x1800a8baf  mov     [rbp+1D0h+var_1FC], cl
0x1800a8bb2  mov     rcx, r13
0x1800a8bb5  mov     [rbp+1D0h+var_210], eax
0x1800a8bb8  mov     [rbp+1D0h+var_1F8], rax
0x1800a8bbc  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties &&)
0x1800a8bc1  lea     rcx, [rsp+2D0h+var_260]; this
0x1800a8bc6  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a8bcb  mov     qword ptr [rbx], 0
0x1800a8bd2  mov     bl, [rbp+1D0h+arg_48]
0x1800a8bd8  test    r15, r15
0x1800a8bdb  jz      short loc_1800A8BE6
0x1800a8bdd  test    bl, bl
0x1800a8bdf  jnz     short loc_1800A8BE6
0x1800a8be1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a8be6  lea     rcx, [rbp+1D0h+var_100]; this
0x1800a8bed  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x1800a8bf2  mov     r9, [rbp+1D0h+var_180]
0x1800a8bf6  lea     rcx, [rbp+1D0h+var_100]; this
0x1800a8bfd  mov     [rsp+2D0h+var_2A8], rsi; PackageFilter *
0x1800a8c02  mov     rsi, [rbp+1D0h+var_178]
0x1800a8c06  mov     r8, rsi
0x1800a8c09  mov     [rsp+2D0h+var_2B0], bl; int
0x1800a8c0d  call    ??$GetInstalledPackagesContainingEntry@UComTypeLibVersionRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTypeLibVersionRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)
0x1800a8c12  xor     ecx, ecx
0x1800a8c14  mov     ebx, eax
0x1800a8c16  test    eax, eax
0x1800a8c18  jns     short loc_1800A8C3A
0x1800a8c1a  mov     rcx, [rbp+1D8h]; this
0x1800a8c21  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a8c28  mov     r9d, eax; char *
0x1800a8c2b  mov     edx, 215Ch; void *
0x1800a8c30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8c35  jmp     loc_1800A9766
0x1800a8c3a  cmp     [rbp+1D0h+var_78], ecx
0x1800a8c40  jz      loc_1800A9761
0x1800a8c46  mov     bl, [r14+8]
0x1800a8c4a  mov     [rsp+2D0h+string], rcx
0x1800a8c4f  test    bl, bl
0x1800a8c51  jz      loc_1800A8CF0
0x1800a8c57  mov     r9d, [r14]
0x1800a8c5a  lea     r8, aXX; "%x.%x"
0x1800a8c61  xor     eax, eax
0x1800a8c63  lea     rcx, [rbp+1D0h+var_60]; unsigned __int16 *
0x1800a8c6a  mov     [rbp+1D0h+var_50], eax
0x1800a8c70  xorps   xmm0, xmm0
0x1800a8c73  mov     eax, [r14+4]
0x1800a8c77  mov     edx, 0Ah; unsigned __int64
0x1800a8c7c  mov     dword ptr [rsp+2D0h+var_2B0], eax; int
0x1800a8c80  movups  xmmword ptr [rbp+1D0h+var_60], xmm0
0x1800a8c87  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a8c8c  test    eax, eax
0x1800a8c8e  jns     short loc_1800A8CC9
0x1800a8c90  mov     ebx, 80070057h
0x1800a8c95  mov     edx, 2175h; void *
0x1800a8c9a  mov     r9d, ebx; char *
0x1800a8c9d  mov     rcx, [rbp+1D8h]; this
0x1800a8ca4  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a8cab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8cb0  mov     rcx, [rsp+2D0h+string]; string
0x1800a8cb5  call    cs:__imp_WindowsDeleteString
0x1800a8cbb  mov     [rsp+2D0h+string], 0
0x1800a8cc4  jmp     loc_1800A9766
0x1800a8cc9  lea     rdx, [rbp+1D0h+var_60]
0x1800a8cd0  lea     rcx, [rsp+2D0h+string]
0x1800a8cd5  call    ??$Set@$09@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY09G@Z; Microsoft::WRL::Wrappers::HString::Set<10>(ushort (&)[10])
0x1800a8cda  xor     ecx, ecx
0x1800a8cdc  mov     ebx, eax
0x1800a8cde  test    eax, eax
0x1800a8ce0  jns     short loc_1800A8CEC
0x1800a8ce2  mov     r9d, eax
0x1800a8ce5  mov     edx, 2177h
0x1800a8cea  jmp     short loc_1800A8C9D
0x1800a8cec  mov     bl, [r14+8]
0x1800a8cf0  test    r15, r15
0x1800a8cf3  jz      loc_1800A922A
0x1800a8cf9  xor     eax, eax
0x1800a8cfb  mov     [rbp+1D0h+var_1F0], cl
0x1800a8cfe  mov     [rbp+1D0h+var_1EC], ecx
0x1800a8d01  mov     [rbp+1D0h+var_1E8], cl
0x1800a8d04  mov     [rbp+1D0h+var_1E4], ecx
0x1800a8d07  mov     [rbp+1D0h+var_1E0], cl
0x1800a8d0a  mov     [rbp+1D0h+var_1D8], rcx
0x1800a8d0e  mov     [rbp+1D0h+var_1D0], cl
0x1800a8d11  mov     [rbp+1D0h+var_1C8], rcx
0x1800a8d15  mov     [rbp+1D0h+var_1C0], cl
0x1800a8d18  mov     [rbp+1D0h+var_1B8], rcx
0x1800a8d1c  mov     [rbp+1D0h+var_1B0], cl
0x1800a8d1f  mov     [rbp+1D0h+var_1A8], rcx
0x1800a8d23  mov     [rbp+1D0h+var_1A0], ax
0x1800a8d27  mov     [rbp+1D0h+var_19C], cl
0x1800a8d2a  mov     [rbp+1D0h+var_198], ecx
0x1800a8d2d  mov     [rbp+1D0h+var_194], cl
0x1800a8d30  mov     [rbp+1D0h+var_190], ecx
0x1800a8d33  mov     [rbp+1D0h+var_18C], cl
0x1800a8d36  mov     [rbp+1D0h+var_188], ecx
0x1800a8d39  mov     [rsp+2D0h+var_278], rcx
0x1800a8d3e  mov     byte ptr [rbp+1D0h+var_150+8], cl
0x1800a8d44  test    bl, bl
0x1800a8d46  jz      loc_1800A8FCD
0x1800a8d4c  mov     rsi, [rbp+1D0h+var_80]
0x1800a8d53  mov     r13d, [rbp+1D0h+arg_50]
0x1800a8d5a  mov     eax, [rbp+1D0h+var_78]
0x1800a8d60  shl     rax, 5
0x1800a8d64  add     rax, [rbp+1D0h+var_80]
0x1800a8d6b  cmp     rsi, rax
0x1800a8d6e  jz      loc_1800A8EF0
0x1800a8d74  mov     byte ptr [rbp+1D0h+var_130+8], cl
0x1800a8d7a  xor     edx, edx; length
0x1800a8d7c  mov     rcx, [rsi]; string
0x1800a8d7f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800a8d85  lea     r8, [rbp+1D0h+var_130]
0x1800a8d8c  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x1800a8d8f  mov     rdx, rax; unsigned __int16 *
0x1800a8d92  call    ?TryGetIndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet@MainPackageFamilyNameFilter@@QEAAJPEBGAEAV?$optional@_K@std@@@Z; MainPackageFamilyNameFilter::TryGetIndexOfMainPackageFamilyWithPackageInFamilyOrRelatedSet(ushort const *,std::optional<unsigned __int64> &)
0x1800a8d97  xor     ecx, ecx
0x1800a8d99  mov     ebx, eax
0x1800a8d9b  test    eax, eax
0x1800a8d9d  js      loc_1800A8F80
0x1800a8da3  cmp     byte ptr [rbp+1D0h+var_130+8], cl
0x1800a8da9  jz      loc_1800A8EDB
0x1800a8daf  cmp     byte ptr [rbp+1D0h+var_150+8], cl
0x1800a8db5  jz      short loc_1800A8DE0
0x1800a8db7  lea     rcx, [rbp+1D0h+var_130]
0x1800a8dbe  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x1800a8dc3  lea     rcx, [rbp+1D0h+var_150]
0x1800a8dca  mov     rbx, rax
0x1800a8dcd  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x1800a8dd2  mov     rcx, [rax]
0x1800a8dd5  cmp     [rbx], rcx
0x1800a8dd8  jnb     loc_1800A8ED9
0x1800a8dde  xor     ecx, ecx
0x1800a8de0  mov     r9, [rbp+1D0h+var_180]
0x1800a8de4  xor     eax, eax
0x1800a8de6  mov     rdx, [rbp+1D0h+var_178]
0x1800a8dea  mov     r8, rsi
0x1800a8ded  mov     word ptr [rbp+1D0h+var_210], ax
0x1800a8df1  lea     rax, [rsp+2D0h+var_290]
0x1800a8df6  mov     qword ptr [rsp+2D0h+var_298], rax
0x1800a8dfb  lea     rax, [rsp+2D0h+var_280]
0x1800a8e00  mov     [rsp+2D0h+var_2A0], rax
0x1800a8e05  lea     rax, [rsp+2D0h+string]
0x1800a8e0a  mov     [rsp+2D0h+var_260], cl
0x1800a8e0e  mov     [rsp+2D0h+var_25C], ecx
0x1800a8e12  mov     [rsp+2D0h+var_258], cl
0x1800a8e16  mov     [rsp+2D0h+var_254], ecx
0x1800a8e1a  mov     [rbp+1D0h+var_250], cl
0x1800a8e1d  mov     [rbp+1D0h+var_248], rcx
0x1800a8e21  mov     [rbp+1D0h+var_240], cl
0x1800a8e24  mov     [rbp+1D0h+var_238], rcx
0x1800a8e28  mov     [rbp+1D0h+var_230], cl
0x1800a8e2b  mov     [rbp+1D0h+var_228], rcx
0x1800a8e2f  mov     [rbp+1D0h+var_220], cl
0x1800a8e32  mov     [rbp+1D0h+var_218], rcx
0x1800a8e36  mov     [rbp+1D0h+var_20C], cl
0x1800a8e39  mov     [rbp+1D0h+var_208], ecx
0x1800a8e3c  mov     [rbp+1D0h+var_204], cl
0x1800a8e3f  mov     [rbp+1D0h+var_200], ecx
0x1800a8e42  mov     [rbp+1D0h+var_1FC], cl
0x1800a8e45  mov     dword ptr [rbp+1D0h+var_1F8], ecx
0x1800a8e48  mov     byte ptr [rsp+2D0h+var_280], cl
0x1800a8e4c  mov     byte ptr [rsp+2D0h+var_290], cl
0x1800a8e50  lea     rcx, [rsp+2D0h+var_260]
0x1800a8e55  mov     dword ptr [rsp+2D0h+var_2A8], r13d
0x1800a8e5a  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x1800a8e5f  call    ?TryReadSupportedAndVisibleTypeLibVersionEntry@CPackagedComCatalog@@CAJAEAUComTypeLibVersionRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@AEBU_GUID@@2W4ComRegistrationVisibility@@AEA_N5@Z; CPackagedComCatalog::TryReadSupportedAndVisibleTypeLibVersionEntry(ComTypeLibVersionRegistrationEntryProperties &,IPackagedComCatalogContext *,OpaqueString const &,_GUID const &,OpaqueString const &,ComRegistrationVisibility,bool &,bool &)
0x1800a8e64  mov     ebx, eax
0x1800a8e66  test    eax, eax
0x1800a8e68  js      loc_1800A8F59
0x1800a8e6e  cmp     byte ptr [rsp+2D0h+var_290], 0
0x1800a8e73  jz      short loc_1800A8ECF
0x1800a8e75  mov     al, [rsp+2D0h+var_260]
0x1800a8e79  mov     r8b, r12b; bool
0x1800a8e7c  mov     edx, [rbp+1D0h+arg_38]; unsigned int
0x1800a8e82  neg     al
0x1800a8e84  sbb     ecx, ecx
0x1800a8e86  and     ecx, [rsp+2D0h+var_25C]; unsigned int
0x1800a8e8a  call    ?IsTypeLibLocaleIdAcceptable@CPackagedComCatalog@@CA_NKK_N@Z; CPackagedComCatalog::IsTypeLibLocaleIdAcceptable(ulong,ulong,bool)
0x1800a8e8f  test    al, al
0x1800a8e91  jz      short loc_1800A8ECF
0x1800a8e93  lea     rdx, [rsp+2D0h+var_260]
0x1800a8e98  lea     rcx, [rbp+1D0h+var_1F0]
0x1800a8e9c  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties &&)
0x1800a8ea1  mov     rdx, rsi
0x1800a8ea4  lea     rcx, [rsp+2D0h+var_278]
0x1800a8ea9  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800a8eae  movaps  xmm0, [rbp+1D0h+var_130]
0x1800a8eb5  lea     rcx, [rbp+1D0h+var_130]
0x1800a8ebc  movdqa  [rbp+1D0h+var_150], xmm0
0x1800a8ec4  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x1800a8ec9  cmp     qword ptr [rax], 0
0x1800a8ecd  jz      short loc_1800A8EE4
0x1800a8ecf  lea     rcx, [rsp+2D0h+var_260]; this
0x1800a8ed4  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a8ed9  xor     ecx, ecx
0x1800a8edb  add     rsi, 20h ; ' '
0x1800a8edf  jmp     loc_1800A8D5A
0x1800a8ee4  lea     rcx, [rsp+2D0h+var_260]; this
0x1800a8ee9  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a8eee  xor     ecx, ecx
0x1800a8ef0  cmp     byte ptr [rbp+1D0h+var_150+8], cl
0x1800a8ef6  jz      loc_1800A8FB4
0x1800a8efc  mov     rcx, [rbp+1D0h+var_140]
0x1800a8f03  lea     rdx, [rbp+1D0h+var_1F0]
0x1800a8f07  call    ??4ComTypeLibVersionRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTypeLibVersionRegistrationEntryProperties::operator=(ComTypeLibVersionRegistrationEntryProperties &&)
0x1800a8f0c  mov     rcx, [rbp+1D0h+var_160]
0x1800a8f10  mov     rax, [rsp+2D0h+var_278]
0x1800a8f15  mov     [rcx], rax
0x1800a8f18  test    rdi, rdi
0x1800a8f1b  jz      short loc_1800A8F2D
0x1800a8f1d  movsd   xmm0, qword ptr [r14]
0x1800a8f22  mov     eax, [r14+8]
0x1800a8f26  movsd   qword ptr [rdi], xmm0
0x1800a8f2a  mov     [rdi+8], eax
0x1800a8f2d  xor     ecx, ecx; string
0x1800a8f2f  call    cs:__imp_WindowsDeleteString
0x1800a8f35  lea     rcx, [rbp+1D0h+var_1F0]; this
0x1800a8f39  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a8f3e  mov     rcx, [rsp+2D0h+string]; string
0x1800a8f43  call    cs:__imp_WindowsDeleteString
0x1800a8f49  xor     ebx, ebx
0x1800a8f4b  mov     [rsp+2D0h+string], 0
0x1800a8f54  jmp     loc_1800A9766
0x1800a8f59  mov     edx, 21A6h; void *
0x1800a8f5e  mov     rcx, [rbp+1D8h]; this
0x1800a8f65  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a8f6c  mov     r9d, eax; char *
0x1800a8f6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8f74  lea     rcx, [rsp+2D0h+var_260]; this
0x1800a8f79  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a8f7e  jmp     short loc_1800A8F9B
0x1800a8f80  mov     edx, 219Dh; void *
0x1800a8f85  mov     rcx, [rbp+1D8h]; this
0x1800a8f8c  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a8f93  mov     r9d, eax; char *
0x1800a8f96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8f9b  mov     rcx, [rsp+2D0h+var_278]; string
0x1800a8fa0  call    cs:__imp_WindowsDeleteString
0x1800a8fa6  lea     rcx, [rbp+1D0h+var_1F0]; this
0x1800a8faa  call    ??1ComTypeLibVersionRegistrationEntryProperties@@QEAA@XZ; ComTypeLibVersionRegistrationEntryProperties::~ComTypeLibVersionRegistrationEntryProperties(void)
0x1800a8faf  jmp     loc_1800A8CB0
0x1800a8fb4  test    r12b, r12b
0x1800a8fb7  jz      short loc_1800A8FCD
0x1800a8fb9  mov     rcx, [rsp+2D0h+var_278]; string
0x1800a8fbe  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
