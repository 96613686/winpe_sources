# CPackagedComCatalog::EntryLookup::ResolveAndReadEntryWithCustomRanking(CPackagedComCatalog::EntryLookup::IEntryTypeGeneric &,CPackagedComCatalog::EntryLookup::IRankingTypeGeneric &,CPackagedComCatalog::EntryLookup::EntryPropertiesPointerGeneric,HSTRING__ * *,CPackagedComCatalog::EntryLookup::RankingPointerGeneric,IUserTokenInternal *,IPackagedComCatalogContext *,CPackagedComCatalog::EntryLookup::EntryIdGeneric,bool,ComRegistrationVisibility,PackageFilter const *,MainPackageFamilyNameFilter *,CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric &)

- ea: `0x180098b78`
- end: `0x180099794`
- name: `?ResolveAndReadEntryWithCustomRanking@EntryLookup@CPackagedComCatalog@@CAJAEAUIEntryTypeGeneric@12@AEAUIRankingTypeGeneric@12@UEntryPropertiesPointerGeneric@12@PEAPEAUHSTRING__@@URankingPointerGeneric@12@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@UEntryIdGeneric@12@_NW4ComRegistrationVisibility@@PEBVPackageFilter@@PEAVMainPackageFamilyNameFilter@@AEAUICheckApplicabilityCallbackGeneric@12@@Z`
- size: `3100`
- prototype: `static int __high(struct CPackagedComCatalog::EntryLookup::IEntryTypeGeneric *, struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *, struct CPackagedComCatalog::EntryLookup::EntryPropertiesPointerGeneric, HSTRING *, struct CPackagedComCatalog::EntryLookup::RankingPointerGeneric, struct IUserTokenInternal *, struct IPackagedComCatalogContext *, struct CPackagedComCatalog::EntryLookup::EntryIdGeneric, bool, enum ComRegistrationVisibility, const struct PackageFilter *, struct MainPackageFamilyNameFilter *, struct CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric *)`
- caller_count: `2`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18009846c`
- `0x1800dd8cc`

## callees

- `0x1800210f8`
- `0x18003b8d0`
- `0x18003c024`
- `0x18003c360`
- `0x18004b0f0`
- `0x18007fbd0`
- `0x1800854fc`
- `0x180095c0c`
- `0x180098190`
- `0x180098b78`
- `0x1800b7ac0`
- `0x1800df6f4`
- `0x1800dfcf8`
- `0x1800e02bc`
- `0x1800e14f8`
- `0x1800ef0a0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009906b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009921a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800992a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800996c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009970c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009973b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009906b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009921a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800992a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800996c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009970c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009973b`

## string_xrefs

- `0x180098c83`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180098cce`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180098d15`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800991d9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18009923e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18009927b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180099600`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18009966b`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18009969c`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
0x180098b78  mov     [rsp-8+arg_10], rbx
0x180098b7d  push    rbp
0x180098b7e  push    rsi
0x180098b7f  push    rdi
0x180098b80  push    r12
0x180098b82  push    r13
0x180098b84  push    r14
0x180098b86  push    r15
0x180098b88  lea     rbp, [rsp-110h]
0x180098b90  sub     rsp, 210h
0x180098b97  mov     rax, cs:__security_cookie
0x180098b9e  xor     rax, rsp
0x180098ba1  mov     [rbp+140h+var_40], rax
0x180098ba8  mov     rax, [rbp+140h+arg_30]
0x180098baf  mov     rbx, r9
0x180098bb2  mov     r13, [rbp+140h+arg_58]
0x180098bb9  mov     r12, rdx
0x180098bbc  mov     rdi, [rbp+140h+arg_28]
0x180098bc3  mov     rdx, r8
0x180098bc6  mov     r14, [rbp+140h+arg_50]
0x180098bcd  mov     rsi, r8
0x180098bd0  mov     [rbp+140h+var_110], rax
0x180098bd4  mov     r15, rcx
0x180098bd7  mov     rax, [rbp+140h+arg_38]
0x180098bde  mov     [rbp+140h+var_138], rax
0x180098be2  mov     rax, [rbp+140h+arg_60]
0x180098be9  mov     [rbp+140h+var_108], rax
0x180098bed  mov     rax, [rcx]
0x180098bf0  mov     [rbp+140h+var_100], rbx
0x180098bf4  mov     [rbp+140h+var_170], r13
0x180098bf8  mov     rax, [rax+10h]
0x180098bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c01  mov     rdx, [rbp+140h+arg_20]
0x180098c08  mov     rcx, r12
0x180098c0b  mov     qword ptr [rbx], 0
0x180098c12  mov     rax, [r12]
0x180098c16  mov     rax, [rax]
0x180098c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c1e  mov     bl, [rbp+140h+arg_40]
0x180098c24  test    r13, r13
0x180098c27  jz      short loc_180098C32
0x180098c29  test    bl, bl
0x180098c2b  jnz     short loc_180098C32
0x180098c2d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180098c32  lea     rcx, [rbp+140h+var_E0]; this
0x180098c36  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x180098c3b  mov     rax, [rbp+140h+var_138]
0x180098c3f  lea     rcx, [rbp+140h+var_190]
0x180098c43  mov     [rsp+240h+var_210], r14
0x180098c48  lea     rdx, [rbp+140h+var_E0]
0x180098c4c  mov     r14, [rbp+140h+var_110]
0x180098c50  mov     r8, rdi
0x180098c53  mov     byte ptr [rsp+240h+var_218], bl
0x180098c57  mov     r9, r14
0x180098c5a  movaps  xmm0, xmmword ptr [rax]
0x180098c5d  mov     rax, [r15]
0x180098c60  mov     qword ptr [rsp+240h+var_220], rcx; int
0x180098c65  mov     rcx, r15
0x180098c68  movdqa  xmmword ptr [rbp+140h+var_190], xmm0
0x180098c6d  mov     rax, [rax+30h]
0x180098c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c76  mov     ebx, eax
0x180098c78  test    eax, eax
0x180098c7a  jns     short loc_180098C9C
0x180098c7c  mov     rcx, [rbp+148h]; this
0x180098c83  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180098c8a  mov     r9d, eax; char *
0x180098c8d  mov     edx, 16EFh; void *
0x180098c92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098c97  jmp     loc_18009975E
0x180098c9c  cmp     [rbp+140h+var_58], 0
0x180098ca3  jz      loc_180099759
0x180098ca9  mov     rax, [r15]
0x180098cac  lea     rdx, [rbp+140h+var_180]
0x180098cb0  mov     rcx, r15
0x180098cb3  mov     [rsp+240h+var_1E0], 0
0x180098cb8  mov     rax, [rax]
0x180098cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098cc0  cmp     [rbp+140h+var_180], 0
0x180098cc5  jnz     short loc_180098CF5
0x180098cc7  mov     rcx, [rbp+148h]; this
0x180098cce  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180098cd5  mov     ebx, 8007000Eh
0x180098cda  mov     edx, 1700h; void *
0x180098cdf  mov     r9d, ebx; char *
0x180098ce2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098ce7  lea     rcx, [rbp+140h+var_180]; this
0x180098ceb  call    ??1UniqueEntryPropertiesGeneric@EntryLookup@CPackagedComCatalog@@QEAA@XZ; CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric(void)
0x180098cf0  jmp     loc_18009975E
0x180098cf5  mov     rax, [r15]
0x180098cf8  lea     rdx, [rbp+140h+var_1A8]
0x180098cfc  mov     rcx, r15
0x180098cff  mov     rax, [rax]
0x180098d02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d07  cmp     [rbp+140h+var_1A8], 0
0x180098d0c  jnz     short loc_180098D39
0x180098d0e  mov     rcx, [rbp+148h]; this
0x180098d15  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180098d1c  mov     ebx, 8007000Eh
0x180098d21  mov     edx, 1702h; void *
0x180098d26  mov     r9d, ebx; char *
0x180098d29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098d2e  lea     rcx, [rbp+140h+var_1A8]; this
0x180098d32  call    ??1UniqueEntryPropertiesGeneric@EntryLookup@CPackagedComCatalog@@QEAA@XZ; CPackagedComCatalog::EntryLookup::UniqueEntryPropertiesGeneric::~UniqueEntryPropertiesGeneric(void)
0x180098d37  jmp     short loc_180098CE7
0x180098d39  mov     rdx, r12; struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *
0x180098d3c  mov     [rsp+240h+string], 0
0x180098d45  lea     rcx, [rbp+140h+var_1C0]; this
0x180098d49  call    ??0OptionalRankingGeneric@EntryLookup@CPackagedComCatalog@@QEAA@AEBUIRankingTypeGeneric@12@@Z; CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::OptionalRankingGeneric(CPackagedComCatalog::EntryLookup::IRankingTypeGeneric const &)
0x180098d4e  mov     rcx, [rbp+140h+var_60]
0x180098d55  test    r13, r13
0x180098d58  jz      loc_1800992C8
0x180098d5e  mov     rbx, [rbp+140h+var_138]
0x180098d62  mov     r14, rcx
0x180098d65  mov     byte ptr [rbp+140h+var_190+8], 0
0x180098d69  mov     r13d, 2
0x180098d6f  mov     byte ptr [rsp+240h+var_1D8+4], 0
0x180098d74  mov     eax, [rbp+140h+var_58]
0x180098d7a  shl     rax, 5
0x180098d7e  add     rax, rcx
0x180098d81  cmp     r14, rax
0x180098d84  jz      loc_180098FFC
0x180098d8a  mov     rax, [r15]
0x180098d8d  mov     rcx, r15
0x180098d90  mov     rdx, [rbp+140h+var_1A8]
0x180098d94  mov     rax, [rax+10h]
0x180098d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098d9d  mov     rax, [rbp+140h+var_138]
0x180098da1  lea     rcx, [rsp+240h+var_1DF]
0x180098da6  mov     r8, [rbp+140h+var_110]
0x180098daa  mov     r9, r14
0x180098dad  mov     rdx, [rbp+140h+var_1A8]
0x180098db1  mov     [rsp+240h+var_208], rcx
0x180098db6  lea     rcx, [rsp+240h+var_1E0]
0x180098dbb  movaps  xmm0, xmmword ptr [rax]
0x180098dbe  mov     rax, [r15]
0x180098dc1  mov     [rsp+240h+var_210], rcx
0x180098dc6  mov     ecx, [rbp+140h+arg_48]
0x180098dcc  mov     dword ptr [rsp+240h+var_218], ecx
0x180098dd0  lea     rcx, [rbp+140h+var_130]
0x180098dd4  mov     rax, [rax+38h]
0x180098dd8  mov     qword ptr [rsp+240h+var_220], rcx; int
0x180098ddd  mov     rcx, r15
0x180098de0  mov     [rsp+240h+var_1DF], 0
0x180098de5  movdqa  xmmword ptr [rbp+140h+var_130], xmm0
0x180098dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098def  mov     edi, eax
0x180098df1  test    eax, eax
0x180098df3  js      loc_18009926F
0x180098df9  cmp     [rsp+240h+var_1DF], 0
0x180098dfe  jz      loc_1800991B8
0x180098e04  mov     rax, [r15]
0x180098e07  lea     rcx, [rbp+140h+var_160]
0x180098e0b  mov     r9, [rbp+140h+var_1A8]
0x180098e0f  mov     r8, [r14]
0x180098e12  mov     rdx, [rbp+140h+var_170]
0x180098e16  mov     rax, [rax+40h]
0x180098e1a  mov     qword ptr [rsp+240h+var_220], rcx
0x180098e1f  mov     rcx, r15
0x180098e22  mov     byte ptr [rbp+140h+var_160+8], 0
0x180098e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098e2b  mov     edi, eax
0x180098e2d  test    eax, eax
0x180098e2f  js      loc_180099268
0x180098e35  cmp     byte ptr [rbp+140h+var_160+8], 0
0x180098e39  jz      loc_1800991B8
0x180098e3f  mov     rdx, r12; struct CPackagedComCatalog::EntryLookup::IRankingTypeGeneric *
0x180098e42  mov     [rsp+240h+var_1D0], 0
0x180098e4a  lea     rcx, [rbp+140h+var_150]; this
0x180098e4e  call    ??0OptionalRankingGeneric@EntryLookup@CPackagedComCatalog@@QEAA@AEBUIRankingTypeGeneric@12@@Z; CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::OptionalRankingGeneric(CPackagedComCatalog::EntryLookup::IRankingTypeGeneric const &)
0x180098e53  movzx   eax, word ptr [rbp+140h+var_138+5]
0x180098e57  mov     rdx, r14
0x180098e5a  movaps  xmm0, xmmword ptr [rbp+140h+var_190]
0x180098e5e  mov     rcx, r12
0x180098e61  movaps  xmm1, xmmword ptr [rbp+140h+var_160]
0x180098e65  mov     r9d, [rbp+140h+arg_48]
0x180098e6c  mov     word ptr [rbp+140h+var_168+5], ax
0x180098e70  mov     al, byte ptr [rbp+140h+var_138+7]
0x180098e73  mov     byte ptr [rbp+140h+var_168+7], al
0x180098e76  lea     rax, [rsp+240h+var_1E0]
0x180098e7b  mov     [rsp+240h+var_1E8], rax
0x180098e80  mov     rax, [rbp+140h+var_108]
0x180098e84  mov     [rsp+240h+var_1F0], rax
0x180098e89  lea     rax, [rbp+140h+var_150]
0x180098e8d  mov     [rsp+240h+var_1F8], rax
0x180098e92  lea     rax, [rsp+240h+var_1D0]
0x180098e97  mov     [rsp+240h+var_200], rax
0x180098e9c  lea     rax, [rbp+140h+var_130]
0x180098ea0  mov     [rsp+240h+var_208], rax
0x180098ea5  lea     rax, [rbp+140h+var_1C0]
0x180098ea9  mov     [rsp+240h+var_210], rax
0x180098eae  mov     rax, [rbp+140h+var_1A8]
0x180098eb2  mov     [rsp+240h+var_218], rax
0x180098eb7  lea     rax, [rbp+140h+var_F0]
0x180098ebb  mov     dword ptr [rbp+140h+var_168], ebx
0x180098ebe  mov     byte ptr [rbp+140h+var_168+4], 0
0x180098ec2  mov     r8, [rbp+140h+var_168]
0x180098ec6  mov     qword ptr [rsp+240h+var_220], rax; int
0x180098ecb  movdqa  xmmword ptr [rbp+140h+var_130], xmm0
0x180098ed0  movdqa  xmmword ptr [rbp+140h+var_F0], xmm1
0x180098ed5  call    ?CheckEntryApplicability@EntryLookup@CPackagedComCatalog@@CAJAEAUIRankingTypeGeneric@12@AEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@W4ComRegistrationVisibility@@V?$optional@_K@6@UEntryPropertiesConstPointerGeneric@12@AEBUOptionalRankingGeneric@12@4AEAW4RegistrationApplicability@2@AEAUOptionalRankingGeneric@12@AEAUICheckApplicabilityCallbackGeneric@12@AEA_N@Z; CPackagedComCatalog::EntryLookup::CheckEntryApplicability(CPackagedComCatalog::EntryLookup::IRankingTypeGeneric &,OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComRegistrationVisibility,std::optional<unsigned __int64>,CPackagedComCatalog::EntryLookup::EntryPropertiesConstPointerGeneric,CPackagedComCatalog::EntryLookup::OptionalRankingGeneric const &,std::optional<unsigned __int64>,CPackagedComCatalog::RegistrationApplicability &,CPackagedComCatalog::EntryLookup::OptionalRankingGeneric &,CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric &,bool &)
0x180098eda  mov     edi, eax
0x180098edc  test    eax, eax
0x180098ede  js      loc_180099237
0x180098ee4  cmp     [rsp+240h+var_1D0], r13d
0x180098ee9  jnz     loc_180099090
0x180098eef  cmp     byte ptr [rsp+240h+var_1D8+4], 0
0x180098ef4  jz      loc_180098F81
0x180098efa  lea     rcx, [rsp+240h+var_1D8]
0x180098eff  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x180098f04  cmp     [rax], r13d
0x180098f07  jnz     short loc_180098F4B
0x180098f09  mov     rax, [r12]
0x180098f0d  lea     r8, [rbp+140h+var_150]
0x180098f11  lea     rdx, [rbp+140h+var_1C0]
0x180098f15  mov     rcx, r12
0x180098f18  mov     rax, [rax+50h]
0x180098f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f21  test    al, al
0x180098f23  jz      loc_1800991C8
0x180098f29  lea     rcx, [rbp+140h+var_160]
0x180098f2d  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x180098f32  lea     rcx, [rbp+140h+var_190]
0x180098f36  mov     rdi, rax
0x180098f39  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x180098f3e  mov     rcx, [rax]
0x180098f41  cmp     [rdi], rcx
0x180098f44  jb      short loc_180098F81
0x180098f46  jmp     loc_180098FD5
0x180098f4b  cmp     byte ptr [rsp+240h+var_1D8+4], 0
0x180098f50  jz      short loc_180098F81
0x180098f52  lea     rcx, [rsp+240h+var_1D8]
0x180098f57  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x180098f5c  cmp     dword ptr [rax], 1
0x180098f5f  jnz     short loc_180098F81
0x180098f61  mov     rax, [r12]
0x180098f65  lea     r8, [rbp+140h+var_150]
0x180098f69  lea     rdx, [rbp+140h+var_1C0]
0x180098f6d  mov     rcx, r12
0x180098f70  mov     rax, [rax+48h]
0x180098f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f79  test    al, al
0x180098f7b  jz      loc_18009922B
0x180098f81  mov     rax, [r15]
0x180098f84  mov     rcx, r15
0x180098f87  mov     r8, [rbp+140h+var_1A8]
0x180098f8b  mov     rdx, [rbp+140h+var_180]
0x180098f8f  mov     rax, [rax+18h]
0x180098f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f98  mov     rdx, r14
0x180098f9b  lea     rcx, [rsp+240h+string]
0x180098fa0  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x180098fa5  lea     rdx, [rbp+140h+var_150]
0x180098fa9  lea     rcx, [rbp+140h+var_1C0]
0x180098fad  call    ??4OptionalRankingGeneric@EntryLookup@CPackagedComCatalog@@QEAAAEAU012@$$QEAU012@@Z; CPackagedComCatalog::EntryLookup::OptionalRankingGeneric::operator=(CPackagedComCatalog::EntryLookup::OptionalRankingGeneric &&)
0x180098fb2  movzx   eax, word ptr [rbp+140h+var_170+5]
0x180098fb6  movaps  xmm0, xmmword ptr [rbp+140h+var_160]
0x180098fba  mov     word ptr [rsp+240h+var_1D8+5], ax
0x180098fbf  mov     al, byte ptr [rbp+140h+var_170+7]
0x180098fc2  mov     byte ptr [rsp+240h+var_1D8+7], al
0x180098fc6  mov     byte ptr [rsp+240h+var_1D8+4], 1
0x180098fcb  mov     dword ptr [rsp+240h+var_1D8], r13d
0x180098fd0  movdqa  xmmword ptr [rbp+140h+var_190], xmm0
0x180098fd5  lea     rcx, [rbp+140h+var_190]
0x180098fd9  call    ?value@?$optional@_K@std@@QEGAAAEA_KXZ; std::optional<unsigned __int64>::value(void)
0x180098fde  cmp     qword ptr [rax], 0
0x180098fe2  jnz     loc_1800991A4
0x180098fe8  mov     rcx, [rbp+140h+var_150]
0x180098fec  lea     rdx, [rbp+140h+var_150]
0x180098ff0  mov     rax, [rcx]
0x180098ff3  mov     rax, [rax+30h]
0x180098ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098ffc  mov     rcx, [rbp+140h+var_1C0]
0x180099000  lea     rdx, [rbp+140h+var_1C0]
0x180099004  mov     rax, [rcx]
0x180099007  mov     rax, [rax+38h]
0x18009900b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099010  test    al, al
0x180099012  jz      loc_1800996EC
0x180099018  mov     rax, [r15]
0x18009901b  mov     rdx, rsi
0x18009901e  mov     r8, [rbp+140h+var_180]
0x180099022  mov     rcx, r15
0x180099025  mov     rax, [rax+18h]
0x180099029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009902e  mov     rcx, [rbp+140h+var_100]
0x180099032  lea     r8, [rbp+140h+var_1C0]
0x180099036  mov     rax, [rsp+240h+string]
0x18009903b  mov     rdx, [rbp+140h+arg_20]
0x180099042  mov     [rcx], rax
0x180099045  mov     rcx, r12
0x180099048  mov     rax, [r12]
0x18009904c  mov     rax, [rax+40h]
0x180099050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099055  mov     rcx, [rbp+140h+var_1C0]
0x180099059  lea     rdx, [rbp+140h+var_1C0]
0x18009905d  mov     rax, [rcx]
0x180099060  mov     rax, [rax+30h]
0x180099064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099069  xor     ecx, ecx; string
  ... truncated ...
```
