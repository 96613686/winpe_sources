# CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)

- ea: `0x18008f084`
- end: `0x18008f5ea`
- name: `??$ResolveAndReadEntryWithCustomRankingOld@UComTreatAsClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z`
- size: `1382`
- prototype: `__int64 __fastcall(__int64, HSTRING *, _DWORD *, struct IUserToken *, __int64 *, GUID *, char, PackageFilter *, char)`
- caller_count: `2`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008d6f0`
- `0x18008eff4`

## callees

- `0x18002ba28`
- `0x1800414d0`
- `0x180047990`
- `0x180048090`
- `0x1800483bc`
- `0x18006b064`
- `0x18006da34`
- `0x18007b510`
- `0x180080b44`
- `0x18008f084`
- `0x18008f610`
- `0x180092b48`
- `0x1800b27e0`
- `0x1800d6b10`
- `0x1800d6b5c`
- `0x1800d6c4c`
- `0x1800d9804`
- `0x1800d9a74`
- `0x1800e1f20`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f126`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f3e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f515`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f59c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f126`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f3e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f515`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f555`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f585`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f592`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f59c`

## string_xrefs

- `0x18008f171`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008f460`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008f47f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008f4bb`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008f562`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall Z::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
        __int64 a1,
        HSTRING *a2,
        _DWORD *a3,
        struct IUserToken *a4,
        __int64 *a5,
        GUID *a6,
        char a7,
        PackageFilter *a8,
        char a9)
{
  int InstalledPackagesContaining; // eax
  int v13; // ebx
  char v14; // r12
  __int16 v15; // r13
  unsigned int v16; // esi
  char v17; // r15
  _QWORD *v18; // r10
  __int64 *v19; // rdi
  __int64 v20; // rdx
  int v21; // r14d
  const char *v22; // r9
  char HasMachine; // bl
  __int64 v24; // rcx
  __int64 v25; // rdx
  int v26; // eax
  _DWORD *v27; // rbx
  __int64 v28; // rdx
  _DWORD *v29; // rbx
  const char *v30; // r9
  int v31; // ecx
  _DWORD *v32; // rax
  HSTRING v33; // rcx
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  char v38; // [rsp+44h] [rbp-BCh]
  __int16 v39; // [rsp+45h] [rbp-BBh]
  char v40; // [rsp+47h] [rbp-B9h]
  _BYTE v41[4]; // [rsp+48h] [rbp-B8h] BYREF
  char v42; // [rsp+4Ch] [rbp-B4h]
  HSTRING v43; // [rsp+50h] [rbp-B0h] BYREF
  int v44; // [rsp+58h] [rbp-A8h] BYREF
  GUID *v45; // [rsp+60h] [rbp-A0h]
  __int64 *v46; // [rsp+68h] [rbp-98h]
  __int128 v47; // [rsp+70h] [rbp-90h] BYREF
  char v48; // [rsp+80h] [rbp-80h]
  HSTRING string; // [rsp+88h] [rbp-78h]
  char v50; // [rsp+90h] [rbp-70h]
  __int128 v51; // [rsp+94h] [rbp-6Ch]
  int v52; // [rsp+A4h] [rbp-5Ch]
  char v53; // [rsp+A8h] [rbp-58h]
  int v54; // [rsp+ACh] [rbp-54h]
  char v55; // [rsp+B0h] [rbp-50h]
  int v56; // [rsp+B4h] [rbp-4Ch]
  char v57; // [rsp+B8h] [rbp-48h]
  int v58; // [rsp+BCh] [rbp-44h]
  __int64 v59; // [rsp+C0h] [rbp-40h] BYREF
  int v60[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v61; // [rsp+D0h] [rbp-30h]
  HSTRING *v62; // [rsp+D8h] [rbp-28h]
  _DWORD *v63; // [rsp+E0h] [rbp-20h]
  _BYTE v64[24]; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v65; // [rsp+108h] [rbp+8h]
  char v66; // [rsp+110h] [rbp+10h]
  __int128 v67; // [rsp+114h] [rbp+14h]
  __int16 v68; // [rsp+124h] [rbp+24h]
  char v69; // [rsp+128h] [rbp+28h]
  int v70; // [rsp+12Ch] [rbp+2Ch]
  char v71; // [rsp+130h] [rbp+30h]
  int v72; // [rsp+134h] [rbp+34h]
  char v73; // [rsp+138h] [rbp+38h]
  int v74; // [rsp+13Ch] [rbp+3Ch]
  _BYTE v75[128]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v76; // [rsp+1C0h] [rbp+C0h]
  __int64 v77; // [rsp+1C8h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v61 = a1;
  v62 = a2;
  v48 = 0;
  string = 0;
  v50 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v63 = a3;
  v46 = a5;
  v45 = a6;
  v47 = 0;
  v51 = 0;
  ComTreatAsClassRegistrationEntryProperties::operator=(a1, &v47);
  WindowsDeleteString(string);
  *a2 = 0;
  *a3 = 0;
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v75);
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(
                                  (PackageListBuffer *)v75,
                                  a4,
                                  a5,
                                  a6,
                                  a7,
                                  a8);
  v13 = InstalledPackagesContaining;
  if ( InstalledPackagesContaining < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1083,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)InstalledPackagesContaining,
      v35);
    goto LABEL_45;
  }
  v13 = 0;
  if ( !(_DWORD)v77 )
  {
    v13 = -2147024894;
    goto LABEL_45;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v76,
    (__int64)&v76[4 * (unsigned int)v77],
    (unsigned int)v77,
    (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByUser);
  v14 = HIBYTE(v45);
  v15 = *(_WORD *)((char *)&v45 + 5);
  v16 = 1;
  v51 = 0;
  v17 = 0;
  v48 = 0;
  string = 0;
  v50 = 0;
  LOWORD(v52) = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v43 = 0;
  v38 = 0;
LABEL_6:
  v18 = v76;
  v19 = v76;
  while ( 1 )
  {
    if ( v19 == &v18[4 * (unsigned int)v77] )
      goto LABEL_39;
    if ( (unsigned __int8)PackageInstalledForScope(v19, v16) )
      break;
LABEL_26:
    v19 += 4;
    v28 = (__int64)&v18[4 * (unsigned int)v77];
    if ( v19 == (__int64 *)v28 )
    {
      if ( v16 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v18,
          v28,
          (32LL * (unsigned int)v77) >> 5,
          (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByOneTime);
        v16 = 2;
        goto LABEL_6;
      }
      if ( v16 == 2 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v18,
          v28,
          (32LL * (unsigned int)v77) >> 5,
          (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByMachine);
        v16 = 0;
        goto LABEL_6;
      }
    }
  }
  v20 = *v19;
  v68 = 0;
  v21 = 0;
  *(_QWORD *)v60 = 0;
  v59 = 0;
  v44 = 0;
  v42 = 0;
  v64[16] = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v13 =  IPackagedComCatalogContext::`vcall'{136,{flat}}(v46, v20, v45, v64, v60, &v59);
  v36 = v60[0];
  CPackagedComCatalog::LogReadEntryResult((unsigned int)v13, v64, v19, v45);
  if ( v13 >= 0 )
  {
    HasMachine = RegistrationHasMachineScope<ComTreatAsClassRegistrationEntryProperties>((__int64)v64);
    LOBYTE(v24) = RegistrationHasUserScope<ComTreatAsClassRegistrationEntryProperties>((__int64)v64);
    LOBYTE(v25) = HasMachine;
    v13 = 0;
    if ( !(unsigned __int8)RegistrationScopeMatchesInstallScope(v24, v25, v16)
      || !RegistrationIsSupportedSyntaxVersion<ComTreatAsClassRegistrationEntryProperties>((__int64)v64) )
    {
      goto LABEL_18;
    }
    v26 = `CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability::operator()(
            (unsigned int)&a9,
            (_DWORD)v19,
            v16,
            (unsigned int)v64,
            v36,
            (__int64)&v44,
            (__int64)v41);
    v21 = v44;
    v13 = v26;
  }
  if ( v13 == -2147024894 || (unsigned int)(v13 + 2147221165) <= 1 || v13 == -2147024883 )
  {
    v17 = 1;
LABEL_25:
    WindowsDeleteString(v65);
    v18 = v76;
    v13 = 0;
    goto LABEL_26;
  }
  if ( v13 < 0 )
  {
    WindowsDeleteString(v65);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1114,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v13,
      v36);
    v33 = v43;
    goto LABEL_42;
  }
  v13 = 0;
LABEL_18:
  if ( v21 != 2 )
  {
    if ( v21 == 1 )
    {
      if ( !v42 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x10EF,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          v22);
      if ( !v38 || (v27 = (_DWORD *)std::optional<int>::value(v41), *(_DWORD *)std::optional<int>::value(&v37) < *v27) )
      {
        ComTreatAsClassRegistrationEntryProperties::operator=(&v47, v64);
        OpaqueString::operator=(&v43, v19);
        v37 = *(_DWORD *)std::optional<int>::value(v41);
        v38 = 1;
        v39 = v15;
        v40 = v14;
      }
    }
    goto LABEL_25;
  }
  if ( !v42 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x10E0,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      v22);
  if ( v38 )
  {
    v29 = (_DWORD *)std::optional<int>::value(v41);
    if ( *(_DWORD *)std::optional<int>::value(&v37) >= *v29 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x10E4,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        v30);
    v13 = 0;
  }
  ComTreatAsClassRegistrationEntryProperties::operator=(&v47, v64);
  OpaqueString::operator=(&v43, v19);
  v31 = *(_DWORD *)std::optional<int>::value(v41);
  v39 = *(_WORD *)((char *)&v46 + 5);
  v37 = v31;
  v40 = HIBYTE(v46);
  v38 = 1;
  WindowsDeleteString(v65);
LABEL_39:
  if ( v38 )
  {
    ComTreatAsClassRegistrationEntryProperties::operator=(v61, &v47);
    *v62 = v43;
    v32 = (_DWORD *)std::optional<int>::value(&v37);
    *v63 = *v32;
    v33 = 0;
LABEL_42:
    WindowsDeleteString(v33);
    WindowsDeleteString(string);
    goto LABEL_45;
  }
  WindowsDeleteString(v43);
  WindowsDeleteString(string);
  if ( v17 )
  {
    v13 = -2147024883;
LABEL_45:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v75);
    return (unsigned int)v13;
  }
  else
  {
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v75);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x18008f084  push    rbp
0x18008f086  push    rbx
0x18008f087  push    rsi
0x18008f088  push    rdi
0x18008f089  push    r12
0x18008f08b  push    r13
0x18008f08d  push    r14
0x18008f08f  push    r15
0x18008f091  lea     rbp, [rsp-0F8h]
0x18008f099  sub     rsp, 1F8h
0x18008f0a0  mov     rax, cs:__security_cookie
0x18008f0a7  xor     rax, rsp
0x18008f0aa  mov     [rbp+130h+var_50], rax
0x18008f0b1  mov     r13, [rbp+130h+arg_20]
0x18008f0b8  mov     r14, rcx
0x18008f0bb  mov     r12, [rbp+130h+arg_28]
0x18008f0c2  xorps   xmm0, xmm0
0x18008f0c5  mov     rbx, [rbp+130h+arg_38]
0x18008f0cc  mov     rsi, rdx
0x18008f0cf  mov     [rbp+130h+var_160], rcx
0x18008f0d3  mov     rdi, r9
0x18008f0d6  xor     ecx, ecx
0x18008f0d8  mov     [rbp+130h+var_158], rdx
0x18008f0dc  mov     [rbp+130h+var_1B0], cl
0x18008f0df  lea     rdx, [rsp+230h+var_1C0]
0x18008f0e4  mov     [rbp+130h+string], rcx
0x18008f0e8  mov     r15, r8
0x18008f0eb  mov     [rbp+130h+var_1A0], cl
0x18008f0ee  mov     [rbp+130h+var_18C], ecx
0x18008f0f1  mov     [rbp+130h+var_188], cl
0x18008f0f4  mov     [rbp+130h+var_184], ecx
0x18008f0f7  mov     [rbp+130h+var_180], cl
0x18008f0fa  mov     [rbp+130h+var_17C], ecx
0x18008f0fd  mov     [rbp+130h+var_178], cl
0x18008f100  mov     [rbp+130h+var_174], ecx
0x18008f103  mov     rcx, r14
0x18008f106  mov     [rbp+130h+var_150], r8
0x18008f10a  mov     [rsp+230h+var_1C8], r13
0x18008f10f  mov     [rsp+230h+var_1D0], r12
0x18008f114  movups  [rsp+230h+var_1C0], xmm0
0x18008f119  movups  [rbp+130h+var_19C], xmm0
0x18008f11d  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x18008f122  mov     rcx, [rbp+130h+string]; string
0x18008f126  call    cs:__imp_WindowsDeleteString
0x18008f12c  mov     qword ptr [rsi], 0
0x18008f133  lea     rcx, [rbp+130h+var_F0]; this
0x18008f137  mov     dword ptr [r15], 0
0x18008f13e  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x18008f143  mov     al, [rbp+130h+arg_30]
0x18008f149  lea     rcx, [rbp+130h+var_F0]; this
0x18008f14d  mov     [rsp+230h+var_208], rbx; PackageFilter *
0x18008f152  mov     r9, r12
0x18008f155  mov     r8, r13
0x18008f158  mov     [rsp+230h+var_210], al; int
0x18008f15c  mov     rdx, rdi
0x18008f15f  call    ??$GetInstalledPackagesContainingEntry@UComTreatAsClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)
0x18008f164  mov     ebx, eax
0x18008f166  test    eax, eax
0x18008f168  jns     short loc_18008F18A
0x18008f16a  mov     rcx, [rbp+138h]; this
0x18008f171  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008f178  mov     r9d, eax; char *
0x18008f17b  mov     edx, 1083h; void *
0x18008f180  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f185  jmp     loc_18008F5AC
0x18008f18a  mov     rax, [rbp+130h+var_68]
0x18008f191  xor     ebx, ebx
0x18008f193  test    eax, eax
0x18008f195  jnz     short loc_18008F1A1
0x18008f197  mov     ebx, 80070002h
0x18008f19c  jmp     loc_18008F5AC
0x18008f1a1  mov     rcx, [rbp+130h+var_70]
0x18008f1a8  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18008f1af  mov     edx, eax
0x18008f1b1  shl     rdx, 5
0x18008f1b5  add     rdx, rcx
0x18008f1b8  mov     r8d, eax
0x18008f1bb  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18008f1c0  mov     r12b, byte ptr [rsp+230h+var_1D0+7]
0x18008f1c5  xorps   xmm0, xmm0
0x18008f1c8  movzx   r13d, word ptr [rsp+230h+var_1D0+5]
0x18008f1ce  mov     esi, 1
0x18008f1d3  movups  [rbp+130h+var_19C], xmm0
0x18008f1d7  mov     r15b, bl
0x18008f1da  mov     [rbp+130h+var_1B0], bl
0x18008f1dd  mov     [rbp+130h+string], rbx
0x18008f1e1  mov     [rbp+130h+var_1A0], bl
0x18008f1e4  mov     word ptr [rbp+130h+var_18C], bx
0x18008f1e8  mov     [rbp+130h+var_188], bl
0x18008f1eb  mov     [rbp+130h+var_184], ebx
0x18008f1ee  mov     [rbp+130h+var_180], bl
0x18008f1f1  mov     [rbp+130h+var_17C], ebx
0x18008f1f4  mov     [rbp+130h+var_178], bl
0x18008f1f7  mov     [rbp+130h+var_174], ebx
0x18008f1fa  mov     [rsp+230h+var_1E0], rbx
0x18008f1ff  mov     [rsp+230h+var_1EC], bl
0x18008f203  mov     r10, [rbp+130h+var_70]
0x18008f20a  mov     rdi, r10
0x18008f20d  mov     eax, dword ptr [rbp+130h+var_68]
0x18008f213  shl     rax, 5
0x18008f217  add     rax, r10
0x18008f21a  cmp     rdi, rax
0x18008f21d  jz      loc_18008F51B
0x18008f223  mov     edx, esi
0x18008f225  mov     rcx, rdi
0x18008f228  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x18008f22d  test    al, al
0x18008f22f  jz      loc_18008F3F5
0x18008f235  mov     r8, [rsp+230h+var_1D0]
0x18008f23a  lea     r9, [rbp+130h+var_140]
0x18008f23e  mov     rdx, [rdi]
0x18008f241  xor     eax, eax
0x18008f243  mov     rcx, [rsp+230h+var_1C8]
0x18008f248  xorps   xmm0, xmm0
0x18008f24b  mov     [rbp+130h+var_10C], ax
0x18008f24f  mov     r14d, ebx
0x18008f252  lea     rax, [rbp+130h+var_170]
0x18008f256  mov     qword ptr [rbp+130h+var_168], rbx
0x18008f25a  mov     [rsp+230h+var_208], rax
0x18008f25f  lea     rax, [rbp+130h+var_168]
0x18008f263  mov     qword ptr [rsp+230h+var_210], rax
0x18008f268  mov     [rbp+130h+var_170], rbx
0x18008f26c  mov     [rsp+230h+var_1D8], ebx
0x18008f270  mov     [rsp+230h+var_1E4], bl
0x18008f274  mov     [rbp+130h+var_130], bl
0x18008f277  mov     [rbp+130h+var_128], rbx
0x18008f27b  mov     [rbp+130h+var_120], bl
0x18008f27e  movups  [rbp+130h+var_11C], xmm0
0x18008f282  mov     [rbp+130h+var_108], bl
0x18008f285  mov     [rbp+130h+var_104], ebx
0x18008f288  mov     [rbp+130h+var_100], bl
0x18008f28b  mov     [rbp+130h+var_FC], ebx
0x18008f28e  mov     [rbp+130h+var_F8], bl
0x18008f291  mov     [rbp+130h+var_F4], ebx
0x18008f294  call    ??_9IPackagedComCatalogContext@@$BII@AA; [thunk]: IPackagedComCatalogContext::`vcall'{136,{flat}}
0x18008f299  mov     rcx, [rbp+130h+var_170]
0x18008f29d  lea     rdx, [rbp+130h+var_140]
0x18008f2a1  mov     r9, [rsp+230h+var_1D0]
0x18008f2a6  mov     r8, rdi
0x18008f2a9  mov     [rsp+230h+var_208], rcx
0x18008f2ae  mov     ebx, eax
0x18008f2b0  mov     rcx, qword ptr [rbp+130h+var_168]
0x18008f2b4  mov     qword ptr [rsp+230h+var_210], rcx; int
0x18008f2b9  mov     ecx, eax
0x18008f2bb  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComTreatAsClassRegistrationEntryProperties@@AEBVOpaqueString@@AEBU_GUID@@W4ComTreatAsClassRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComTreatAsClassRegistrationEntryProperties const &,OpaqueString const &,_GUID const &,ComTreatAsClassRegistrationEntryPropertyFlags,ComTreatAsClassRegistrationEntryPropertyFlags)
0x18008f2c0  test    ebx, ebx
0x18008f2c2  js      short loc_18008F328
0x18008f2c4  lea     rcx, [rbp+130h+var_140]
0x18008f2c8  call    ??$RegistrationHasMachineScope@UComTreatAsClassRegistrationEntryProperties@@@@YA_NAEBUComTreatAsClassRegistrationEntryProperties@@@Z; RegistrationHasMachineScope<ComTreatAsClassRegistrationEntryProperties>(ComTreatAsClassRegistrationEntryProperties const &)
0x18008f2cd  lea     rcx, [rbp+130h+var_140]
0x18008f2d1  mov     bl, al
0x18008f2d3  call    ??$RegistrationHasUserScope@UComTreatAsClassRegistrationEntryProperties@@@@YA_NAEBUComTreatAsClassRegistrationEntryProperties@@@Z; RegistrationHasUserScope<ComTreatAsClassRegistrationEntryProperties>(ComTreatAsClassRegistrationEntryProperties const &)
0x18008f2d8  mov     cl, al
0x18008f2da  mov     r8d, esi
0x18008f2dd  mov     dl, bl
0x18008f2df  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x18008f2e4  xor     ebx, ebx
0x18008f2e6  test    al, al
0x18008f2e8  jz      short loc_18008F359
0x18008f2ea  lea     rcx, [rbp+130h+var_140]
0x18008f2ee  call    ??$RegistrationIsSupportedSyntaxVersion@UComTreatAsClassRegistrationEntryProperties@@@@YA_NAEBUComTreatAsClassRegistrationEntryProperties@@@Z; RegistrationIsSupportedSyntaxVersion<ComTreatAsClassRegistrationEntryProperties>(ComTreatAsClassRegistrationEntryProperties const &)
0x18008f2f3  test    al, al
0x18008f2f5  jz      short loc_18008F359
0x18008f2f7  lea     rax, [rsp+230h+var_1E8]
0x18008f2fc  mov     r8d, esi
0x18008f2ff  mov     [rsp+230h+var_200], rax
0x18008f304  lea     r9, [rbp+130h+var_140]
0x18008f308  lea     rax, [rsp+230h+var_1D8]
0x18008f30d  mov     rdx, rdi
0x18008f310  lea     rcx, [rbp+130h+arg_40]
0x18008f317  mov     [rsp+230h+var_208], rax
0x18008f31c  call    ??RCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU2@PEA_N@Z@Z@QEAAJ789V?$optional@H@std@@PEAW4RegistrationApplicability@1@PEAV?$optional@H@std@@@Z; `CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability::operator()(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,std::optional<int>,CPackagedComCatalog::RegistrationApplicability *,std::optional<int> *)
0x18008f321  mov     r14d, [rsp+230h+var_1D8]
0x18008f326  mov     ebx, eax
0x18008f328  cmp     ebx, 80070002h
0x18008f32e  jz      loc_18008F3DF
0x18008f334  lea     eax, [rbx+7FFBFEADh]
0x18008f33a  cmp     eax, 1
0x18008f33d  jbe     loc_18008F3DF
0x18008f343  cmp     ebx, 8007000Dh
0x18008f349  jz      loc_18008F3DF
0x18008f34f  test    ebx, ebx
0x18008f351  js      loc_18008F551
0x18008f357  xor     ebx, ebx
0x18008f359  cmp     r14d, 2
0x18008f35d  jz      loc_18008F472
0x18008f363  cmp     r14d, 1
0x18008f367  jnz     short loc_18008F3E2
0x18008f369  cmp     [rsp+230h+var_1E4], bl
0x18008f36d  mov     rcx, [rbp+138h]; this
0x18008f374  setz    al
0x18008f377  test    al, al
0x18008f379  jnz     loc_18008F460
0x18008f37f  cmp     [rsp+230h+var_1EC], bl
0x18008f383  jz      short loc_18008F3A2
0x18008f385  lea     rcx, [rsp+230h+var_1E8]
0x18008f38a  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18008f38f  lea     rcx, [rsp+230h+var_1F0]
0x18008f394  mov     rbx, rax
0x18008f397  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18008f39c  mov     ecx, [rbx]
0x18008f39e  cmp     [rax], ecx
0x18008f3a0  jge     short loc_18008F3E2
0x18008f3a2  lea     rdx, [rbp+130h+var_140]
0x18008f3a6  lea     rcx, [rsp+230h+var_1C0]
0x18008f3ab  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x18008f3b0  mov     rdx, rdi
0x18008f3b3  lea     rcx, [rsp+230h+var_1E0]
0x18008f3b8  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x18008f3bd  lea     rcx, [rsp+230h+var_1E8]
0x18008f3c2  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18008f3c7  mov     ecx, [rax]
0x18008f3c9  mov     [rsp+230h+var_1F0], ecx
0x18008f3cd  mov     [rsp+230h+var_1EC], 1
0x18008f3d2  mov     [rsp+230h+var_1EB], r13w
0x18008f3d8  mov     [rsp+230h+var_1E9], r12b
0x18008f3dd  jmp     short loc_18008F3E2
0x18008f3df  mov     r15b, 1
0x18008f3e2  mov     rcx, [rbp+130h+var_128]; string
0x18008f3e6  call    cs:__imp_WindowsDeleteString
0x18008f3ec  mov     r10, [rbp+130h+var_70]
0x18008f3f3  xor     ebx, ebx
0x18008f3f5  mov     edx, dword ptr [rbp+130h+var_68]
0x18008f3fb  add     rdi, 20h ; ' '
0x18008f3ff  shl     rdx, 5
0x18008f403  add     rdx, r10
0x18008f406  cmp     rdi, rdx
0x18008f409  jnz     loc_18008F20D
0x18008f40f  cmp     esi, 1
0x18008f412  jnz     short loc_18008F437
0x18008f414  mov     r8, rdx
0x18008f417  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18008f41e  sub     r8, r10
0x18008f421  mov     rcx, r10
0x18008f424  sar     r8, 5
0x18008f428  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18008f42d  mov     esi, 2
0x18008f432  jmp     loc_18008F203
0x18008f437  cmp     esi, 2
0x18008f43a  jnz     loc_18008F20D
0x18008f440  mov     r8, rdx
0x18008f443  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18008f44a  sub     r8, r10
0x18008f44d  mov     rcx, r10
0x18008f450  sar     r8, 5
0x18008f454  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18008f459  mov     esi, ebx
0x18008f45b  jmp     loc_18008F203
0x18008f460  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008f467  mov     edx, 10EFh; void *
0x18008f46c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008f472  cmp     [rsp+230h+var_1E4], bl
0x18008f476  jnz     short loc_18008F491
0x18008f478  mov     rcx, [rbp+138h]; this
0x18008f47f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008f486  mov     edx, 10E0h; void *
0x18008f48b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008f491  cmp     [rsp+230h+var_1EC], bl
0x18008f495  jz      short loc_18008F4CF
0x18008f497  lea     rcx, [rsp+230h+var_1E8]
0x18008f49c  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18008f4a1  lea     rcx, [rsp+230h+var_1F0]
0x18008f4a6  mov     rbx, rax
0x18008f4a9  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18008f4ae  mov     ecx, [rbx]
0x18008f4b0  cmp     [rax], ecx
0x18008f4b2  jl      short loc_18008F4CD
0x18008f4b4  mov     rcx, [rbp+138h]; this
0x18008f4bb  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008f4c2  mov     edx, 10E4h; void *
0x18008f4c7  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008f4cd  xor     ebx, ebx
0x18008f4cf  lea     rdx, [rbp+130h+var_140]
0x18008f4d3  lea     rcx, [rsp+230h+var_1C0]
0x18008f4d8  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x18008f4dd  mov     rdx, rdi
0x18008f4e0  lea     rcx, [rsp+230h+var_1E0]
0x18008f4e5  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x18008f4ea  lea     rcx, [rsp+230h+var_1E8]
0x18008f4ef  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18008f4f4  mov     ecx, [rax]
0x18008f4f6  movzx   eax, word ptr [rsp+230h+var_1C8+5]
0x18008f4fb  mov     [rsp+230h+var_1EB], ax
0x18008f500  mov     al, byte ptr [rsp+230h+var_1C8+7]
0x18008f504  mov     [rsp+230h+var_1F0], ecx
0x18008f508  mov     rcx, [rbp+130h+var_128]; string
0x18008f50c  mov     [rsp+230h+var_1E9], al
0x18008f510  mov     [rsp+230h+var_1EC], 1
0x18008f515  call    cs:__imp_WindowsDeleteString
0x18008f51b  cmp     [rsp+230h+var_1EC], bl
0x18008f51f  jz      short loc_18008F58D
0x18008f521  mov     rcx, [rbp+130h+var_160]
0x18008f525  lea     rdx, [rsp+230h+var_1C0]
0x18008f52a  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x18008f52f  mov     rcx, [rbp+130h+var_158]
0x18008f533  mov     rax, [rsp+230h+var_1E0]
0x18008f538  mov     [rcx], rax
0x18008f53b  lea     rcx, [rsp+230h+var_1F0]
0x18008f540  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18008f545  mov     ecx, [rax]
  ... truncated ...
```
