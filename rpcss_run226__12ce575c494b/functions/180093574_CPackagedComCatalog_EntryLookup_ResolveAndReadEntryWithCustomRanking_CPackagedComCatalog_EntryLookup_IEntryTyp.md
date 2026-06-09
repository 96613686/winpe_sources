# CPackagedComCatalog::EntryLookup::ResolveAndReadEntryWithCustomRanking(CPackagedComCatalog::EntryLookup::IEntryTypeGeneric &,CPackagedComCatalog::EntryLookup::IRankingTypeGeneric &,CPackagedComCatalog::EntryLookup::EntryPropertiesPointerGeneric,HSTRING__ * *,CPackagedComCatalog::EntryLookup::RankingPointerGeneric,IUserTokenInternal *,IPackagedComCatalogContext *,CPackagedComCatalog::EntryLookup::EntryIdGeneric,bool,ComRegistrationVisibility,PackageFilter const *,MainPackageFamilyNameFilter *,CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric &)

- ea: `0x180093574`
- end: `0x18009416b`
- name: `?ResolveAndReadEntryWithCustomRanking@EntryLookup@CPackagedComCatalog@@CAJAEAUIEntryTypeGeneric@12@AEAUIRankingTypeGeneric@12@UEntryPropertiesPointerGeneric@12@PEAPEAUHSTRING__@@URankingPointerGeneric@12@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@UEntryIdGeneric@12@_NW4ComRegistrationVisibility@@PEBVPackageFilter@@PEAVMainPackageFamilyNameFilter@@AEAUICheckApplicabilityCallbackGeneric@12@@Z`
- size: `3063`
- prototype: `static int __high(struct CPackagedComCatalog::EntryLookup::IEntryTypeGeneric *, struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, struct CPackagedComCatalog::EntryLookup::EntryPropertiesPointerGeneric, HSTRING *, struct CPackagedComCatalog::EntryLookup::RankingPointerGeneric, struct IUserTokenInternal *, struct IPackagedComCatalogContext *, struct CPackagedComCatalog::EntryLookup::EntryIdGeneric, bool, enum ComRegistrationVisibility, const struct PackageFilter *, struct MainPackageFamilyNameFilter *, struct CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric *)`
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180092e8c`
- `0x1800d6ca4`

## callees

- `0x18002ba28`
- `0x1800414d0`
- `0x180047990`
- `0x180048090`
- `0x1800483bc`
- `0x18007b510`
- `0x180080b44`
- `0x18008e98c`
- `0x180092b48`
- `0x180093574`
- `0x1800b27e0`
- `0x1800d8a30`
- `0x1800d8f5c`
- `0x1800d94f8`
- `0x1800da778`
- `0x1800e7a10`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800940b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800940f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094119`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093a67`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093c93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800940b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800940f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094119`

## string_xrefs

- `0x18009367f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800936ca`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180093711`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180093bcf`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180093c2e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180093c6b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180093fea`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180094055`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180094086`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::EntryLookup::ResolveAndReadEntryWithCustomRanking(
        void (__fastcall ***a1)(__int64, __int64 *),
        const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *a2,
        __int64 *a3,
        HSTRING *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _OWORD *a8,
        char a9,
        int a10,
        __int64 a11,
        __int64 a12,
        __int64 a13)
{
  void (__fastcall **v17)(__int64, __int64 *); // rax
  __int64 v18; // rcx
  __int64 v19; // r14
  void (__fastcall **v20)(__int64, __int64 *); // rax
  int v21; // eax
  unsigned int v22; // ebx
  void (__fastcall **v23)(__int64, __int64 *); // rax
  _QWORD *v24; // rcx
  int v25; // ebx
  __int64 *v26; // r14
  __int128 v27; // xmm0
  void (__fastcall *v28)(__int64, __int64 *); // rax
  int v29; // edi
  __int64 v30; // r8
  void (__fastcall *v31)(__int64, __int64 *); // rax
  int v32; // eax
  __int64 v33; // rcx
  _QWORD *v34; // rdi
  __int64 v35; // rcx
  __int64 v36; // rcx
  int *v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // rdx
  _QWORD *v40; // rdi
  __int64 v41; // rcx
  int *v42; // rdx
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rbx
  __int64 v46; // r9
  __int64 v47; // rdi
  _QWORD *v48; // r10
  _QWORD *v49; // r13
  void (__fastcall *v50)(__int64, __int64 *); // rax
  int v51; // eax
  unsigned int v52; // r14d
  char v53; // r14
  __int64 v54; // rcx
  __int64 v55; // rdx
  int v56; // eax
  _QWORD *v57; // rdx
  __int64 v58; // rcx
  void (__fastcall *v59)(_QWORD, _QWORD *); // rax
  int *v61; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+20h] [rbp-E0h]
  int v63; // [rsp+20h] [rbp-E0h]
  char v64; // [rsp+60h] [rbp-A0h] BYREF
  char v65; // [rsp+61h] [rbp-9Fh]
  char v66; // [rsp+62h] [rbp-9Eh]
  int v67; // [rsp+68h] [rbp-98h] BYREF
  char v68; // [rsp+6Ch] [rbp-94h]
  __int16 v69; // [rsp+6Dh] [rbp-93h]
  char v70; // [rsp+6Fh] [rbp-91h]
  unsigned int v71; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v73[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74[3]; // [rsp+98h] [rbp-68h] BYREF
  int v75[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v76[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v77; // [rsp+D0h] [rbp-30h]
  int v78; // [rsp+D8h] [rbp-28h] BYREF
  char v79; // [rsp+DCh] [rbp-24h]
  __int16 v80; // [rsp+DDh] [rbp-23h]
  char v81; // [rsp+DFh] [rbp-21h]
  int v82[4]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v83[3]; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD *v84; // [rsp+108h] [rbp+8h]
  int v85[8]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v86; // [rsp+130h] [rbp+30h]
  __int64 v87; // [rsp+138h] [rbp+38h]
  HSTRING *v88; // [rsp+140h] [rbp+40h]
  int v89[4]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v90[128]; // [rsp+160h] [rbp+60h] BYREF
  _QWORD *v91; // [rsp+1E0h] [rbp+E0h]
  unsigned int v92; // [rsp+1E8h] [rbp+E8h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]

  v86 = a7;
  v84 = a8;
  v87 = a13;
  v17 = *a1;
  v88 = a4;
  v77 = a12;
  v17[2]((__int64)a1, a3);
  *a4 = 0;
  (**(void (__fastcall ***)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, __int64))a2)(a2, a5);
  if ( a12 && !a9 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v18);
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v90);
  v19 = v86;
  v20 = *a1;
  *(_OWORD *)v75 = *v84;
  v21 = ((__int64 (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), _BYTE *, __int64, __int64))v20[6])(
          a1,
          v90,
          a6,
          v86);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16EF,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v21,
      (int)v75);
    goto LABEL_88;
  }
  if ( !v92 )
    goto LABEL_87;
  v23 = *a1;
  v64 = 0;
  (*v23)((__int64)a1, v76);
  if ( !v76[0] )
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1700,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)0x8007000ELL,
      (int)v75);
    goto LABEL_9;
  }
  (**a1)((__int64)a1, v74);
  if ( !v74[0] )
  {
    v22 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1702,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)0x8007000ELL,
      (int)v75);
    goto LABEL_12;
  }
  string = 0;
  CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::OptionalRankingGeneric(
    (CPackagedComCatalog::EntryLookup::OptionalRankingGeneric *)v73,
    a2);
  v24 = v91;
  if ( !a12 )
  {
    std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
      v91,
      &v91[4 * v92],
      v92,
      MoreRecentlyInstalledByUser);
    v45 = *(_QWORD *)v75;
    v46 = 1;
    v47 = *(_QWORD *)v75;
    while ( 1 )
    {
      v48 = v91;
      v49 = v91;
      v71 = v46;
      do
      {
LABEL_59:
        if ( v49 == &v48[4 * v92] )
          goto LABEL_34;
        if ( (unsigned __int8)PackageInstalledForScope(v49, (unsigned int)v46, v44, v46) )
        {
          (*a1)[2]((__int64)a1, (__int64 *)v74[0]);
          v66 = 0;
          v50 = (*a1)[7];
          *(_OWORD *)v89 = *v84;
          v51 = ((__int64 (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), __int64, __int64, _QWORD *))v50)(
                  a1,
                  v74[0],
                  v19,
                  v49);
          v52 = v51;
          if ( v51 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x179B,
              (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
              (const char *)(unsigned int)v51,
              (int)v89);
            goto LABEL_83;
          }
          if ( v66 )
          {
            v53 = ((__int64 (__fastcall *)(__int64, __int64))(*a1)[5])((__int64)a1, v74[0]);
            LOBYTE(v54) = ((__int64 (__fastcall *)(__int64, __int64))(*a1)[4])((__int64)a1, v74[0]);
            LOBYTE(v55) = v53;
            if ( (unsigned __int8)RegistrationScopeMatchesInstallScope(v54, v55, v71) )
            {
              v78 = 0;
              CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::OptionalRankingGeneric(
                (CPackagedComCatalog::EntryLookup::OptionalRankingGeneric *)v85,
                a2);
              v67 = v71;
              v69 = *(_WORD *)((char *)&v77 + 5);
              v70 = HIBYTE(v77);
              *(int *)((char *)&v82[2] + 1) = *(int *)((char *)&v75[2] + 1);
              *(_WORD *)((char *)&v82[3] + 1) = *(_WORD *)((char *)&v75[3] + 1);
              HIBYTE(v82[3]) = HIBYTE(v75[3]);
              v68 = 1;
              *(_QWORD *)v75 = v45;
              LOBYTE(v75[2]) = 0;
              *(_QWORD *)v82 = v47;
              LOBYTE(v82[2]) = 0;
              v56 = CPackagedComCatalog::EntryLookup::CheckEntryApplicability(
                      (_DWORD)a2,
                      (_DWORD)v49,
                      v71,
                      a10,
                      (__int64)v82,
                      v74[0],
                      (__int64)v73,
                      (__int64)v75,
                      (__int64)&v78,
                      (__int64)v85,
                      v87,
                      (__int64)&v64);
              v52 = v56;
              if ( v56 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x17A7,
                  (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
                  (const char *)(unsigned int)v56,
                  v63);
                (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)v85 + 48LL))(*(_QWORD *)v85, v85);
LABEL_83:
                (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 48LL))(v73[0], v73);
                WindowsDeleteString(string);
                CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v74);
                CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v76);
                v22 = v52;
                goto LABEL_88;
              }
              if ( v78 == 2 )
              {
                if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 56LL))(v73[0], v73)
                  && !(*(unsigned __int8 (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, _QWORD *, int *))(*(_QWORD *)a2 + 72LL))(
                        a2,
                        v73,
                        v85) )
                {
                  MicrosoftTelemetryAssertTriggeredNoArgs(v58);
                  v22 = -2147418113;
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x17AE,
                    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
                    (const char *)0x8000FFFFLL,
                    v63);
                  v41 = *(_QWORD *)v85;
                  v42 = v85;
LABEL_50:
                  (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 48LL))(v41, v42);
                  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 48LL))(v73[0], v73);
                  WindowsDeleteString(string);
LABEL_12:
                  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v74);
LABEL_9:
                  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v76);
                  goto LABEL_88;
                }
                ((void (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), _QWORD, __int64))(*a1)[3])(
                  a1,
                  v76[0],
                  v74[0]);
                OpaqueString::operator=(&string, v49);
                CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::operator=(v73, v85);
                v36 = *(_QWORD *)v85;
                v37 = v85;
LABEL_33:
                (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 48LL))(v36, v37);
LABEL_34:
                if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 56LL))(v73[0], v73) )
                {
                  ((void (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), __int64 *, _QWORD))(*a1)[3])(
                    a1,
                    a3,
                    v76[0]);
                  *v88 = string;
                  (*(void (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, __int64, _QWORD *))(*(_QWORD *)a2 + 64LL))(
                    a2,
                    a5,
                    v73);
                  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 48LL))(v73[0], v73);
                  WindowsDeleteString(0);
                  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v74);
                  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v76);
                  v22 = 0;
                  goto LABEL_88;
                }
                v59 = *(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 48LL);
                if ( v64 )
                {
                  v59(v73[0], v73);
                  WindowsDeleteString(string);
                  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v74);
                  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v76);
                  v22 = -2147024883;
                  goto LABEL_88;
                }
                v59(v73[0], v73);
                WindowsDeleteString(string);
                CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v74);
                CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v76);
LABEL_87:
                v22 = -2147024894;
                goto LABEL_88;
              }
              if ( v78 == 1
                && (!(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 56LL))(v73[0], v73)
                 || (*(unsigned __int8 (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, _QWORD *, int *))(*(_QWORD *)a2 + 72LL))(
                      a2,
                      v73,
                      v85)) )
              {
                ((void (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), _QWORD, __int64))(*a1)[3])(
                  a1,
                  v76[0],
                  v74[0]);
                OpaqueString::operator=(&string, v49);
                CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::operator=(v73, v85);
              }
              (*(void (__fastcall **)(_QWORD, int *))(**(_QWORD **)v85 + 48LL))(*(_QWORD *)v85, v85);
            }
          }
          v19 = v86;
          v46 = v71;
          v48 = v91;
        }
        v49 += 4;
        v57 = &v48[4 * v92];
      }
      while ( v49 != v57 );
      if ( (_DWORD)v46 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v48,
          v57,
          (32LL * v92) >> 5,
          MoreRecentlyInstalledByOneTime);
        v46 = 2;
      }
      else
      {
        if ( (_DWORD)v46 != 2 )
          goto LABEL_59;
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v48,
          v57,
          (32LL * v92) >> 5,
          MoreRecentlyInstalledByMachine);
        v46 = 0;
      }
    }
  }
  v25 = (int)v84;
  v26 = v91;
  LOBYTE(v75[2]) = 0;
  v68 = 0;
  while ( 1 )
  {
    if ( v26 == &v24[4 * v92] )
      goto LABEL_34;
    (*a1)[2]((__int64)a1, (__int64 *)v74[0]);
    v27 = *v84;
    v28 = (*a1)[7];
    v61 = v85;
    v65 = 0;
    *(_OWORD *)v85 = v27;
    v29 = ((__int64 (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), __int64, __int64, __int64 *))v28)(
            a1,
            v74[0],
            v86,
            v26);
    if ( v29 < 0 )
      break;
    if ( v65 )
    {
      v30 = *v26;
      v31 = (*a1)[8];
      v61 = v82;
      LOBYTE(v82[2]) = 0;
      v29 = ((__int64 (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), __int64, __int64, __int64))v31)(
              a1,
              v77,
              v30,
              v74[0]);
      if ( v29 < 0 )
      {
        v43 = 5923;
        goto LABEL_55;
      }
      if ( LOBYTE(v82[2]) )
      {
        v71 = 0;
        CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::OptionalRankingGeneric(
          (CPackagedComCatalog::EntryLookup::OptionalRankingGeneric *)v83,
          a2);
        v80 = *(_WORD *)((char *)&v84 + 5);
        v81 = HIBYTE(v84);
        v78 = v25;
        v79 = 0;
        *(_OWORD *)v85 = *(_OWORD *)v75;
        *(_OWORD *)v89 = *(_OWORD *)v82;
        v32 = CPackagedComCatalog::EntryLookup::CheckEntryApplicability(
                (_DWORD)a2,
                (_DWORD)v26,
                v25,
                a10,
                (__int64)v89,
                v74[0],
                (__int64)v73,
                (__int64)v85,
                (__int64)&v71,
                (__int64)v83,
                v87,
                (__int64)&v64);
        v29 = v32;
        if ( v32 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x172D,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)v32,
            v62);
          (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v83[0] + 48LL))(v83[0], v83);
          goto LABEL_56;
        }
        if ( v71 == 2 )
        {
          if ( v68 )
          {
            if ( *(_DWORD *)std::optional<int>::value(&v67) == 2 )
            {
              if ( !(*(unsigned __int8 (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, _QWORD *, _QWORD *))(*(_QWORD *)a2 + 80LL))(
                      a2,
                      v73,
                      v83) )
              {
                MicrosoftTelemetryAssertTriggeredNoArgs(v33);
                v39 = 5944;
                goto LABEL_49;
              }
              v34 = (_QWORD *)std::optional<unsigned __int64>::value(v82);
              if ( *v34 >= *(_QWORD *)std::optional<unsigned __int64>::value(v75) )
              {
LABEL_31:
                if ( !*(_QWORD *)std::optional<unsigned __int64>::value(v75) )
                {
                  v36 = v83[0];
                  v37 = (int *)v83;
                  goto LABEL_33;
                }
LABEL_46:
                (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v83[0] + 48LL))(v83[0], v83);
                goto LABEL_47;
              }
            }
            else if ( v68
                   && *(_DWORD *)std::optional<int>::value(&v67) == 1
                   && !(*(unsigned __int8 (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, _QWORD *, _QWORD *))(*(_QWORD *)a2 + 72LL))(
                         a2,
                         v73,
                         v83) )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v35);
              v39 = 5964;
              goto LABEL_49;
            }
          }
          ((void (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), _QWORD, __int64))(*a1)[3])(
            a1,
            v76[0],
            v74[0]);
          OpaqueString::operator=(&string, v26);
          CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::operator=(v73, v83);
          v69 = *(_WORD *)((char *)&v77 + 5);
          v70 = HIBYTE(v77);
          v68 = 1;
          v67 = 2;
          *(_OWORD *)v75 = *(_OWORD *)v82;
          goto LABEL_31;
        }
        if ( v71 == 1 )
        {
          if ( v68 && *(_DWORD *)std::optional<int>::value(&v67) == 2 )
          {
            if ( !(*(unsigned __int8 (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, _QWORD *, _QWORD *))(*(_QWORD *)a2 + 72LL))(
                    a2,
                    v83,
                    v73) )
            {
              MicrosoftTelemetryAssertTriggeredNoArgs(v38);
              v39 = 5994;
LABEL_49:
              v22 = -2147418113;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v39,
                (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
                (const char *)0x8000FFFFLL,
                v62);
              v41 = v83[0];
              v42 = (int *)v83;
              goto LABEL_50;
            }
          }
          else if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 56LL))(v73[0], v73)
                 || (*(unsigned __int8 (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, _QWORD *, _QWORD *))(*(_QWORD *)a2 + 72LL))(
                      a2,
                      v73,
                      v83)
                 || (*(unsigned __int8 (__fastcall **)(const struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, _QWORD *, _QWORD *))(*(_QWORD *)a2 + 80LL))(
                      a2,
                      v73,
                      v83)
                 && (v40 = (_QWORD *)std::optional<unsigned __int64>::value(v82),
                     *v40 < *(_QWORD *)std::optional<unsigned __int64>::value(v75)) )
          {
            ((void (__fastcall *)(void (__fastcall ***)(__int64, __int64 *), _QWORD, __int64))(*a1)[3])(
              a1,
              v76[0],
              v74[0]);
            OpaqueString::operator=(&string, v26);
            CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::operator=(v73, v83);
            v69 = *(_WORD *)((char *)&v77 + 5);
            v70 = HIBYTE(v77);
            *(_OWORD *)v75 = *(_OWORD *)v82;
            v67 = 1;
            v68 = 1;
          }
        }
        goto LABEL_46;
      }
    }
LABEL_47:
    v24 = v91;
    v26 += 4;
  }
  v43 = 5917;
LABEL_55:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v43,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)v29,
    (int)v61);
LABEL_56:
  (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v73[0] + 48LL))(v73[0], v73);
  WindowsDeleteString(string);
  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v74);
  CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric((CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric *)v76);
  v22 = v29;
LABEL_88:
  PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v90);
  return v22;
}

```

## disassembly

```asm
0x180093574  mov     [rsp-8+arg_10], rbx
0x180093579  push    rbp
0x18009357a  push    rsi
0x18009357b  push    rdi
0x18009357c  push    r12
0x18009357e  push    r13
0x180093580  push    r14
0x180093582  push    r15
0x180093584  lea     rbp, [rsp-110h]
0x18009358c  sub     rsp, 210h
0x180093593  mov     rax, cs:__security_cookie
0x18009359a  xor     rax, rsp
0x18009359d  mov     [rbp+140h+var_40], rax
0x1800935a4  mov     rax, [rbp+140h+arg_30]
0x1800935ab  mov     rbx, r9
0x1800935ae  mov     r13, [rbp+140h+arg_58]
0x1800935b5  mov     r12, rdx
0x1800935b8  mov     rdi, [rbp+140h+arg_28]
0x1800935bf  mov     rdx, r8
0x1800935c2  mov     r14, [rbp+140h+arg_50]
0x1800935c9  mov     rsi, r8
0x1800935cc  mov     [rbp+140h+var_110], rax
0x1800935d0  mov     r15, rcx
0x1800935d3  mov     rax, [rbp+140h+arg_38]
0x1800935da  mov     [rbp+140h+var_138], rax
0x1800935de  mov     rax, [rbp+140h+arg_60]
0x1800935e5  mov     [rbp+140h+var_108], rax
0x1800935e9  mov     rax, [rcx]
0x1800935ec  mov     [rbp+140h+var_100], rbx
0x1800935f0  mov     [rbp+140h+var_170], r13
0x1800935f4  mov     rax, [rax+10h]
0x1800935f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800935fd  mov     rdx, [rbp+140h+arg_20]
0x180093604  mov     rcx, r12
0x180093607  mov     qword ptr [rbx], 0
0x18009360e  mov     rax, [r12]
0x180093612  mov     rax, [rax]
0x180093615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009361a  mov     bl, [rbp+140h+arg_40]
0x180093620  test    r13, r13
0x180093623  jz      short loc_18009362E
0x180093625  test    bl, bl
0x180093627  jnz     short loc_18009362E
0x180093629  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18009362e  lea     rcx, [rbp+140h+var_E0]; this
0x180093632  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x180093637  mov     rax, [rbp+140h+var_138]
0x18009363b  lea     rcx, [rbp+140h+var_190]
0x18009363f  mov     [rsp+240h+var_210], r14
0x180093644  lea     rdx, [rbp+140h+var_E0]
0x180093648  mov     r14, [rbp+140h+var_110]
0x18009364c  mov     r8, rdi
0x18009364f  mov     byte ptr [rsp+240h+var_218], bl
0x180093653  mov     r9, r14
0x180093656  movaps  xmm0, xmmword ptr [rax]
0x180093659  mov     rax, [r15]
0x18009365c  mov     qword ptr [rsp+240h+var_220], rcx; int
0x180093661  mov     rcx, r15
0x180093664  movdqa  xmmword ptr [rbp+140h+var_190], xmm0
0x180093669  mov     rax, [rax+30h]
0x18009366d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093672  mov     ebx, eax
0x180093674  test    eax, eax
0x180093676  jns     short loc_180093698
0x180093678  mov     rcx, [rbp+148h]; this
0x18009367f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180093686  mov     r9d, eax; char *
0x180093689  mov     edx, 16EFh; void *
0x18009368e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093693  jmp     loc_180094136
0x180093698  cmp     [rbp+140h+var_58], 0
0x18009369f  jz      loc_180094131
0x1800936a5  mov     rax, [r15]
0x1800936a8  lea     rdx, [rbp+140h+var_180]
0x1800936ac  mov     rcx, r15
0x1800936af  mov     [rsp+240h+var_1E0], 0
0x1800936b4  mov     rax, [rax]
0x1800936b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800936bc  cmp     [rbp+140h+var_180], 0
0x1800936c1  jnz     short loc_1800936F1
0x1800936c3  mov     rcx, [rbp+148h]; this
0x1800936ca  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800936d1  mov     ebx, 8007000Eh
0x1800936d6  mov     edx, 1700h; void *
0x1800936db  mov     r9d, ebx; char *
0x1800936de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800936e3  lea     rcx, [rbp+140h+var_180]; this
0x1800936e7  call    ??1UniqueEntryPropertiesGeneric@EntryLookup@CPackagedComCatalog@@QEAA@XZ; CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric(void)
0x1800936ec  jmp     loc_180094136
0x1800936f1  mov     rax, [r15]
0x1800936f4  lea     rdx, [rbp+140h+var_1A8]
0x1800936f8  mov     rcx, r15
0x1800936fb  mov     rax, [rax]
0x1800936fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093703  cmp     [rbp+140h+var_1A8], 0
0x180093708  jnz     short loc_180093735
0x18009370a  mov     rcx, [rbp+148h]; this
0x180093711  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180093718  mov     ebx, 8007000Eh
0x18009371d  mov     edx, 1702h; void *
0x180093722  mov     r9d, ebx; char *
0x180093725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009372a  lea     rcx, [rbp+140h+var_1A8]; this
0x18009372e  call    ??1UniqueEntryPropertiesGeneric@EntryLookup@CPackagedComCatalog@@QEAA@XZ; CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric(void)
0x180093733  jmp     short loc_1800936E3
0x180093735  mov     rdx, r12; struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *
0x180093738  mov     [rsp+240h+string], 0
0x180093741  lea     rcx, [rbp+140h+var_1C0]; this
0x180093745  call    ??0OptionalRankingGeneric@EntryLookup@CPackagedComCatalog@@QEAA@AEBUIRankingTypeGeneric@12@@Z; CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::OptionalRankingGeneric(CPackagedComCatalog::EntryLookup::IRankingTypeGeneric const &)
0x18009374a  mov     rcx, [rbp+140h+var_60]
0x180093751  test    r13, r13
0x180093754  jz      loc_180093CB2
0x18009375a  mov     rbx, [rbp+140h+var_138]
0x18009375e  mov     r14, rcx
0x180093761  mov     byte ptr [rbp+140h+var_190+8], 0
0x180093765  mov     r13d, 2
0x18009376b  mov     byte ptr [rsp+240h+var_1D8+4], 0
0x180093770  mov     eax, [rbp+140h+var_58]
0x180093776  shl     rax, 5
0x18009377a  add     rax, rcx
0x18009377d  cmp     r14, rax
0x180093780  jz      loc_1800939F8
0x180093786  mov     rax, [r15]
0x180093789  mov     rcx, r15
0x18009378c  mov     rdx, [rbp+140h+var_1A8]
0x180093790  mov     rax, [rax+10h]
0x180093794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093799  mov     rax, [rbp+140h+var_138]
0x18009379d  lea     rcx, [rsp+240h+var_1DF]
0x1800937a2  mov     r8, [rbp+140h+var_110]
0x1800937a6  mov     r9, r14
0x1800937a9  mov     rdx, [rbp+140h+var_1A8]
0x1800937ad  mov     [rsp+240h+var_208], rcx
0x1800937b2  lea     rcx, [rsp+240h+var_1E0]
0x1800937b7  movaps  xmm0, xmmword ptr [rax]
0x1800937ba  mov     rax, [r15]
0x1800937bd  mov     [rsp+240h+var_210], rcx
0x1800937c2  mov     ecx, [rbp+140h+arg_48]
0x1800937c8  mov     dword ptr [rsp+240h+var_218], ecx
0x1800937cc  lea     rcx, [rbp+140h+var_130]
0x1800937d0  mov     rax, [rax+38h]
0x1800937d4  mov     qword ptr [rsp+240h+var_220], rcx; int
0x1800937d9  mov     rcx, r15
0x1800937dc  mov     [rsp+240h+var_1DF], 0
0x1800937e1  movdqa  xmmword ptr [rbp+140h+var_130], xmm0
0x1800937e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800937eb  mov     edi, eax
0x1800937ed  test    eax, eax
0x1800937ef  js      loc_180093C5F
0x1800937f5  cmp     [rsp+240h+var_1DF], 0
0x1800937fa  jz      loc_180093BAE
0x180093800  mov     rax, [r15]
0x180093803  lea     rcx, [rbp+140h+var_160]
0x180093807  mov     r9, [rbp+140h+var_1A8]
0x18009380b  mov     r8, [r14]
0x18009380e  mov     rdx, [rbp+140h+var_170]
0x180093812  mov     rax, [rax+40h]
0x180093816  mov     qword ptr [rsp+240h+var_220], rcx
0x18009381b  mov     rcx, r15
0x18009381e  mov     byte ptr [rbp+140h+var_160+8], 0
0x180093822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093827  mov     edi, eax
0x180093829  test    eax, eax
0x18009382b  js      loc_180093C58
0x180093831  cmp     byte ptr [rbp+140h+var_160+8], 0
0x180093835  jz      loc_180093BAE
0x18009383b  mov     rdx, r12; struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *
0x18009383e  mov     [rsp+240h+var_1D0], 0
0x180093846  lea     rcx, [rbp+140h+var_150]; this
0x18009384a  call    ??0OptionalRankingGeneric@EntryLookup@CPackagedComCatalog@@QEAA@AEBUIRankingTypeGeneric@12@@Z; CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::OptionalRankingGeneric(CPackagedComCatalog::EntryLookup::IRankingTypeGeneric const &)
0x18009384f  movzx   eax, word ptr [rbp+140h+var_138+5]
0x180093853  mov     rdx, r14
0x180093856  movaps  xmm0, xmmword ptr [rbp+140h+var_190]
0x18009385a  mov     rcx, r12
0x18009385d  movaps  xmm1, xmmword ptr [rbp+140h+var_160]
0x180093861  mov     r9d, [rbp+140h+arg_48]
0x180093868  mov     word ptr [rbp+140h+var_168+5], ax
0x18009386c  mov     al, byte ptr [rbp+140h+var_138+7]
0x18009386f  mov     byte ptr [rbp+140h+var_168+7], al
0x180093872  lea     rax, [rsp+240h+var_1E0]
0x180093877  mov     [rsp+240h+var_1E8], rax
0x18009387c  mov     rax, [rbp+140h+var_108]
0x180093880  mov     [rsp+240h+var_1F0], rax
0x180093885  lea     rax, [rbp+140h+var_150]
0x180093889  mov     [rsp+240h+var_1F8], rax
0x18009388e  lea     rax, [rsp+240h+var_1D0]
0x180093893  mov     [rsp+240h+var_200], rax
0x180093898  lea     rax, [rbp+140h+var_130]
0x18009389c  mov     [rsp+240h+var_208], rax
0x1800938a1  lea     rax, [rbp+140h+var_1C0]
0x1800938a5  mov     [rsp+240h+var_210], rax
0x1800938aa  mov     rax, [rbp+140h+var_1A8]
0x1800938ae  mov     [rsp+240h+var_218], rax
0x1800938b3  lea     rax, [rbp+140h+var_F0]
0x1800938b7  mov     dword ptr [rbp+140h+var_168], ebx
0x1800938ba  mov     byte ptr [rbp+140h+var_168+4], 0
0x1800938be  mov     r8, [rbp+140h+var_168]
0x1800938c2  mov     qword ptr [rsp+240h+var_220], rax; int
0x1800938c7  movdqa  xmmword ptr [rbp+140h+var_130], xmm0
0x1800938cc  movdqa  xmmword ptr [rbp+140h+var_F0], xmm1
0x1800938d1  call    ?CheckEntryApplicability@EntryLookup@CPackagedComCatalog@@CAJAEAUIRankingTypeGeneric@12@AEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@W4ComRegistrationVisibility@@V?$optional@_K@6@UEntryPropertiesConstPointerGeneric@12@AEBUOptionalRankingGeneric@12@4AEAW4RegistrationApplicability@2@AEAUOptionalRankingGeneric@12@AEAUICheckApplicabilityCallbackGeneric@12@AEA_N@Z; CPackagedComCatalog::EntryLookup::CheckEntryApplicability(CPackagedComCatalog::EntryLookup::IRankingTypeGeneric &,OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComRegistrationVisibility,std::optional<unsigned __int64>,CPackagedComCatalog::EntryLookup::EntryPropertiesConstPointerGeneric,CPackagedComCatalog::EntryLookup::OptionalRankingGeneric const &,std::optional<unsigned __int64>,CPackagedComCatalog::RegistrationApplicability &,CPackagedComCatalog::EntryLookup::OptionalRankingGeneric &,CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric &,bool &)
0x1800938d6  mov     edi, eax
0x1800938d8  test    eax, eax
0x1800938da  js      loc_180093C27
0x1800938e0  cmp     [rsp+240h+var_1D0], r13d
0x1800938e5  jnz     loc_180093A86
0x1800938eb  cmp     byte ptr [rsp+240h+var_1D8+4], 0
0x1800938f0  jz      loc_18009397D
0x1800938f6  lea     rcx, [rsp+240h+var_1D8]
0x1800938fb  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x180093900  cmp     [rax], r13d
0x180093903  jnz     short loc_180093947
0x180093905  mov     rax, [r12]
0x180093909  lea     r8, [rbp+140h+var_150]
0x18009390d  lea     rdx, [rbp+140h+var_1C0]
0x180093911  mov     rcx, r12
0x180093914  mov     rax, [rax+50h]
0x180093918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009391d  test    al, al
0x18009391f  jz      loc_180093BBE
0x180093925  lea     rcx, [rbp+140h+var_160]
0x180093929  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x18009392e  lea     rcx, [rbp+140h+var_190]
0x180093932  mov     rdi, rax
0x180093935  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x18009393a  mov     rcx, [rax]
0x18009393d  cmp     [rdi], rcx
0x180093940  jb      short loc_18009397D
0x180093942  jmp     loc_1800939D1
0x180093947  cmp     byte ptr [rsp+240h+var_1D8+4], 0
0x18009394c  jz      short loc_18009397D
0x18009394e  lea     rcx, [rsp+240h+var_1D8]
0x180093953  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x180093958  cmp     dword ptr [rax], 1
0x18009395b  jnz     short loc_18009397D
0x18009395d  mov     rax, [r12]
0x180093961  lea     r8, [rbp+140h+var_150]
0x180093965  lea     rdx, [rbp+140h+var_1C0]
0x180093969  mov     rcx, r12
0x18009396c  mov     rax, [rax+48h]
0x180093970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093975  test    al, al
0x180093977  jz      loc_180093C1B
0x18009397d  mov     rax, [r15]
0x180093980  mov     rcx, r15
0x180093983  mov     r8, [rbp+140h+var_1A8]
0x180093987  mov     rdx, [rbp+140h+var_180]
0x18009398b  mov     rax, [rax+18h]
0x18009398f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093994  mov     rdx, r14
0x180093997  lea     rcx, [rsp+240h+string]
0x18009399c  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800939a1  lea     rdx, [rbp+140h+var_150]
0x1800939a5  lea     rcx, [rbp+140h+var_1C0]
0x1800939a9  call    ??4OptionalRankingGeneric@EntryLookup@CPackagedComCatalog@@QEAAAEAU012@$$QEAU012@@Z; CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::operator=(CPackagedComCatalog::EntryLookup::OptionalRankingGeneric &&)
0x1800939ae  movzx   eax, word ptr [rbp+140h+var_170+5]
0x1800939b2  movaps  xmm0, xmmword ptr [rbp+140h+var_160]
0x1800939b6  mov     word ptr [rsp+240h+var_1D8+5], ax
0x1800939bb  mov     al, byte ptr [rbp+140h+var_170+7]
0x1800939be  mov     byte ptr [rsp+240h+var_1D8+7], al
0x1800939c2  mov     byte ptr [rsp+240h+var_1D8+4], 1
0x1800939c7  mov     dword ptr [rsp+240h+var_1D8], r13d
0x1800939cc  movdqa  xmmword ptr [rbp+140h+var_190], xmm0
0x1800939d1  lea     rcx, [rbp+140h+var_190]
0x1800939d5  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x1800939da  cmp     qword ptr [rax], 0
0x1800939de  jnz     loc_180093B9A
0x1800939e4  mov     rcx, [rbp+140h+var_150]
0x1800939e8  lea     rdx, [rbp+140h+var_150]
0x1800939ec  mov     rax, [rcx]
0x1800939ef  mov     rax, [rax+30h]
0x1800939f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800939f8  mov     rcx, [rbp+140h+var_1C0]
0x1800939fc  lea     rdx, [rbp+140h+var_1C0]
0x180093a00  mov     rax, [rcx]
0x180093a03  mov     rax, [rax+38h]
0x180093a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a0c  test    al, al
0x180093a0e  jz      loc_1800940D0
0x180093a14  mov     rax, [r15]
0x180093a17  mov     rdx, rsi
0x180093a1a  mov     r8, [rbp+140h+var_180]
0x180093a1e  mov     rcx, r15
0x180093a21  mov     rax, [rax+18h]
0x180093a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a2a  mov     rcx, [rbp+140h+var_100]
0x180093a2e  lea     r8, [rbp+140h+var_1C0]
0x180093a32  mov     rax, [rsp+240h+string]
0x180093a37  mov     rdx, [rbp+140h+arg_20]
0x180093a3e  mov     [rcx], rax
0x180093a41  mov     rcx, r12
0x180093a44  mov     rax, [r12]
0x180093a48  mov     rax, [rax+40h]
0x180093a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a51  mov     rcx, [rbp+140h+var_1C0]
0x180093a55  lea     rdx, [rbp+140h+var_1C0]
0x180093a59  mov     rax, [rcx]
0x180093a5c  mov     rax, [rax+30h]
0x180093a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a65  xor     ecx, ecx; string
  ... truncated ...
```
