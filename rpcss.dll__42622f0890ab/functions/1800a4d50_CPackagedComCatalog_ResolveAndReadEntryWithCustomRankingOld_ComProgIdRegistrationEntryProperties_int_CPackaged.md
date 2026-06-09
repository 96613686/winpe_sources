# CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComProgIdRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)

- ea: `0x1800a4d50`
- end: `0x1800a529f`
- name: `??$ResolveAndReadEntryWithCustomRankingOld@UComProgIdRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU4@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU2@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z`
- size: `1359`
- prototype: `__int64 __fastcall(__int64, HSTRING *, _DWORD *, __int64, __int64, HSTRING, char, __int64, __int64 (__fastcall *)(__int64 *, _QWORD, _BYTE *, char *))`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a4cc4`

## callees

- `0x18002ba28`
- `0x1800414d0`
- `0x180047990`
- `0x180048090`
- `0x1800483bc`
- `0x18007b510`
- `0x180080b44`
- `0x18008f610`
- `0x180092b48`
- `0x1800a4d50`
- `0x1800b27e0`
- `0x1800d4e8c`
- `0x1800d6afc`
- `0x1800d6b40`
- `0x1800d6bec`
- `0x1800d91cc`
- `0x1800d9a5c`
- `0x1800e1af0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4df0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a520b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a522b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a524a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a4df0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5084`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a51fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a520b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a522b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a5241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a524a`

## string_xrefs

- `0x1800a4e32`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a4eb0`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall Z::ResolveAndReadEntryWithCustomRankingOld<ComProgIdRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,AEAU1 *,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(
        __int64 a1,
        HSTRING *a2,
        _DWORD *a3,
        __int64 a4,
        __int64 a5,
        HSTRING a6,
        char a7,
        __int64 a8,
        __int64 (__fastcall *a9)(__int64 *, _QWORD, _BYTE *, char *))
{
  HSTRING v9; // r15
  int InstalledPackagesContaining; // eax
  unsigned int v13; // ebx
  HSTRING v14; // r9
  HSTRING v15; // rbx
  unsigned int v16; // r12d
  char v17; // di
  _QWORD *v18; // r10
  __int64 *v19; // r14
  __int64 v20; // rdx
  int v21; // r13d
  __int64 v22; // rdi
  __int64 v23; // rdx
  const char *v24; // r9
  char HasMachine; // di
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  _DWORD *v30; // rbx
  const char *v31; // r9
  int v32; // ecx
  _DWORD *v33; // rax
  int v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  char v37; // [rsp+30h] [rbp-D0h]
  char v38[7]; // [rsp+31h] [rbp-CFh] BYREF
  int v39; // [rsp+38h] [rbp-C8h] BYREF
  char v40; // [rsp+3Ch] [rbp-C4h]
  __int16 v41; // [rsp+3Dh] [rbp-C3h]
  char v42; // [rsp+3Fh] [rbp-C1h]
  int v43; // [rsp+40h] [rbp-C0h] BYREF
  char v44; // [rsp+44h] [rbp-BCh]
  __int16 v45; // [rsp+45h] [rbp-BBh]
  char v46; // [rsp+47h] [rbp-B9h]
  __int64 v47; // [rsp+48h] [rbp-B8h]
  HSTRING v48; // [rsp+50h] [rbp-B0h] BYREF
  int v49[2]; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v50; // [rsp+60h] [rbp-A0h]
  HSTRING v51; // [rsp+68h] [rbp-98h] BYREF
  __int64 v52; // [rsp+70h] [rbp-90h]
  HSTRING *v53; // [rsp+78h] [rbp-88h]
  _DWORD *v54; // [rsp+80h] [rbp-80h]
  _BYTE v55[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v56; // [rsp+94h] [rbp-6Ch]
  char v57; // [rsp+A8h] [rbp-58h]
  HSTRING v58; // [rsp+B0h] [rbp-50h]
  __int16 v59; // [rsp+B8h] [rbp-48h]
  char v60; // [rsp+BCh] [rbp-44h]
  int v61; // [rsp+C0h] [rbp-40h]
  char v62; // [rsp+C4h] [rbp-3Ch]
  int v63; // [rsp+C8h] [rbp-38h]
  char v64; // [rsp+CCh] [rbp-34h]
  int v65; // [rsp+D0h] [rbp-30h]
  _BYTE v66[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v67; // [rsp+E4h] [rbp-1Ch]
  int v68; // [rsp+F4h] [rbp-Ch]
  char v69; // [rsp+F8h] [rbp-8h]
  HSTRING string; // [rsp+100h] [rbp+0h]
  int v71; // [rsp+108h] [rbp+8h]
  char v72; // [rsp+10Ch] [rbp+Ch]
  int v73; // [rsp+110h] [rbp+10h]
  char v74; // [rsp+114h] [rbp+14h]
  int v75; // [rsp+118h] [rbp+18h]
  char v76; // [rsp+11Ch] [rbp+1Ch]
  __int64 v77; // [rsp+120h] [rbp+20h]
  _BYTE v78[128]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD *v79; // [rsp+1B0h] [rbp+B0h]
  __int64 v80; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v9 = 0;
  v53 = a2;
  v47 = a5;
  v50 = a6;
  v66[0] = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  string = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v54 = a3;
  v52 = a1;
  ComProgIdRegistrationEntryProperties::operator=(a1, v66);
  WindowsDeleteString(string);
  *a2 = 0;
  *a3 = 0;
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v78);
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(
                                  (PackageListBuffer *)v78,
                                  0,
                                  a5,
                                  a6,
                                  a7,
                                  0);
  v13 = InstalledPackagesContaining;
  if ( InstalledPackagesContaining < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1083,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)InstalledPackagesContaining,
      v35);
    goto LABEL_41;
  }
  if ( !(_DWORD)v80 )
  {
    v13 = -2147024894;
    goto LABEL_41;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v79,
    (__int64)&v79[4 * (unsigned int)v80],
    (unsigned int)v80,
    (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByUser);
  LOBYTE(v14) = 0;
  v58 = 0;
  v15 = 0;
  v37 = 0;
  v51 = 0;
  v16 = 1;
  v55[0] = 0;
  v17 = 0;
  v57 = 0;
  v56 = 0;
  v59 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v40 = 0;
LABEL_6:
  v18 = v79;
  v19 = v79;
  while ( v19 != &v18[4 * (unsigned int)v80] )
  {
    if ( !(unsigned __int8)PackageInstalledForScope(v19, v16) )
      goto LABEL_24;
    v20 = *v19;
    v21 = (int)v14;
    LOWORD(v71) = 0;
    *(_QWORD *)v49 = v14;
    v48 = v14;
    v44 = (char)v14;
    v66[0] = (_BYTE)v14;
    v69 = (char)v14;
    string = v14;
    v72 = (char)v14;
    v73 = (int)v14;
    v74 = (char)v14;
    v75 = (int)v14;
    v76 = (char)v14;
    LODWORD(v77) = (_DWORD)v14;
    v67 = 0;
    v22 = (unsigned int) IPackagedComCatalogContext::`vcall'{128,{flat}}(v47, v20, v50, v66, v49, &v48);
    v36 = v49[0];
    CPackagedComCatalog::LogReadEntryResult(v22, v23, v19, v50);
    if ( (int)v22 >= 0 )
    {
      HasMachine = RegistrationHasMachineScope<ComProgIdRegistrationEntryProperties>((__int64)v66);
      LOBYTE(v26) = RegistrationHasUserScope<ComProgIdRegistrationEntryProperties>((__int64)v66);
      LOBYTE(v27) = HasMachine;
      if ( !(unsigned __int8)RegistrationScopeMatchesInstallScope(v26, v27, v16)
        || !RegistrationIsSupportedSyntaxVersion<ComProgIdRegistrationEntryProperties>((__int64)v66) )
      {
        goto LABEL_22;
      }
      v38[0] = 0;
      v28 = a9(v19, v16, v66, v38);
      LODWORD(v22) = v28;
      if ( v28 >= 0 )
      {
        v21 = v38[0] != 0 ? 2 : 0;
        if ( v38[0] )
        {
          v45 = *(_WORD *)((char *)&v47 + 5);
          v46 = HIBYTE(v47);
          v43 = 0;
          v44 = 1;
        }
        LODWORD(v22) = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1050,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v28,
          v36);
      }
    }
    if ( (_DWORD)v22 == -2147024894 || (unsigned int)(v22 + 2147221165) <= 1 || (_DWORD)v22 == -2147024883 )
    {
      v17 = 1;
      v37 = 1;
      goto LABEL_23;
    }
    if ( (int)v22 < 0 )
    {
      WindowsDeleteString(string);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1114,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)v22,
        v36);
      WindowsDeleteString(0);
      WindowsDeleteString(0);
      v13 = v22;
      goto LABEL_41;
    }
    if ( v21 == 2 )
    {
      if ( !v44 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x10E0,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          v24);
      if ( v40 )
      {
        v30 = (_DWORD *)std::optional<int>::value(&v43);
        if ( *(_DWORD *)std::optional<int>::value(&v39) >= *v30 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x10E4,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            v31);
      }
      ComProgIdRegistrationEntryProperties::operator=(v55, v66);
      OpaqueString::operator=(&v51, v19);
      v32 = *(_DWORD *)std::optional<int>::value(&v43);
      v41 = *(_WORD *)((char *)&v47 + 5);
      v39 = v32;
      v42 = HIBYTE(v47);
      v40 = 1;
      WindowsDeleteString(string);
      v9 = v58;
      LOBYTE(v14) = 0;
      v15 = v51;
      v17 = v37;
      break;
    }
LABEL_22:
    v17 = v37;
LABEL_23:
    WindowsDeleteString(string);
    v18 = v79;
    LOBYTE(v14) = 0;
LABEL_24:
    v19 += 4;
    v29 = (__int64)&v18[4 * (unsigned int)v80];
    if ( v19 == (__int64 *)v29 )
    {
      if ( v16 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v18,
          v29,
          (32LL * (unsigned int)v80) >> 5,
          (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByOneTime);
        LOBYTE(v14) = 0;
        v16 = 2;
        goto LABEL_6;
      }
      if ( v16 == 2 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v18,
          v29,
          (32LL * (unsigned int)v80) >> 5,
          (unsigned __int8 (__fastcall *)(__int64, __int64))MoreRecentlyInstalledByMachine);
        LOBYTE(v14) = 0;
        v16 = 0;
        goto LABEL_6;
      }
    }
  }
  if ( v40 != (_BYTE)v14 )
  {
    ComProgIdRegistrationEntryProperties::operator=(v52, v55);
    *v53 = v15;
    v33 = (_DWORD *)std::optional<int>::value(&v39);
    *v54 = *v33;
    WindowsDeleteString(0);
    WindowsDeleteString(v58);
    v13 = 0;
    goto LABEL_41;
  }
  WindowsDeleteString(v15);
  WindowsDeleteString(v9);
  if ( v17 )
  {
    v13 = -2147024883;
LABEL_41:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v78);
    return v13;
  }
  else
  {
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v78);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x1800a4d50  mov     [rsp-8+arg_18], rbx
0x1800a4d55  push    rbp
0x1800a4d56  push    rsi
0x1800a4d57  push    rdi
0x1800a4d58  push    r12
0x1800a4d5a  push    r13
0x1800a4d5c  push    r14
0x1800a4d5e  push    r15
0x1800a4d60  lea     rbp, [rsp-0E0h]
0x1800a4d68  sub     rsp, 1E0h
0x1800a4d6f  mov     rax, cs:__security_cookie
0x1800a4d76  xor     rax, rsp
0x1800a4d79  mov     [rbp+110h+var_40], rax
0x1800a4d80  mov     r14, [rbp+110h+arg_20]
0x1800a4d87  xor     r15d, r15d
0x1800a4d8a  mov     rsi, [rbp+110h+arg_28]
0x1800a4d91  mov     rbx, rdx
0x1800a4d94  mov     [rsp+210h+var_198], rdx
0x1800a4d99  xorps   xmm0, xmm0
0x1800a4d9c  xor     eax, eax
0x1800a4d9e  mov     [rsp+210h+var_1C8], r14
0x1800a4da3  lea     rdx, [rbp+110h+var_130]
0x1800a4da7  mov     [rsp+210h+var_1B0], rsi
0x1800a4dac  mov     [rbp+110h+var_130], r15b
0x1800a4db0  mov     rdi, r8
0x1800a4db3  movups  [rbp+110h+var_12C], xmm0
0x1800a4db7  mov     [rbp+110h+var_11C], eax
0x1800a4dba  mov     [rbp+110h+var_118], r15b
0x1800a4dbe  mov     [rbp+110h+string], r15
0x1800a4dc2  mov     [rbp+110h+var_108], r15d
0x1800a4dc6  mov     [rbp+110h+var_104], r15b
0x1800a4dca  mov     [rbp+110h+var_100], r15d
0x1800a4dce  mov     [rbp+110h+var_FC], r15b
0x1800a4dd2  mov     [rbp+110h+var_F8], r15d
0x1800a4dd6  mov     [rbp+110h+var_F4], r15b
0x1800a4dda  mov     [rbp+110h+var_F0], r15
0x1800a4dde  mov     [rbp+110h+var_190], r8
0x1800a4de2  mov     [rsp+210h+var_1A0], rcx
0x1800a4de7  call    ??4ComProgIdRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComProgIdRegistrationEntryProperties::operator=(ComProgIdRegistrationEntryProperties &&)
0x1800a4dec  mov     rcx, [rbp+110h+string]; string
0x1800a4df0  call    cs:__imp_WindowsDeleteString
0x1800a4df6  mov     [rbx], r15
0x1800a4df9  lea     rcx, [rbp+110h+var_E0]; this
0x1800a4dfd  mov     [rdi], r15d
0x1800a4e00  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x1800a4e05  mov     al, [rbp+110h+arg_30]
0x1800a4e0b  lea     rcx, [rbp+110h+var_E0]; this
0x1800a4e0f  mov     [rsp+210h+var_1E8], r15; PackageFilter *
0x1800a4e14  mov     r9, rsi
0x1800a4e17  mov     r8, r14
0x1800a4e1a  mov     [rsp+210h+var_1F0], al; int
0x1800a4e1e  xor     edx, edx
0x1800a4e20  call    ??$GetInstalledPackagesContainingEntry@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAUHSTRING__@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *)
0x1800a4e25  mov     ebx, eax
0x1800a4e27  test    eax, eax
0x1800a4e29  jns     short loc_1800A4E4B
0x1800a4e2b  mov     rcx, [rbp+118h]; this
0x1800a4e32  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a4e39  mov     r9d, eax; char *
0x1800a4e3c  mov     edx, 1083h; void *
0x1800a4e41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4e46  jmp     loc_1800A525A
0x1800a4e4b  mov     rax, [rbp+110h+var_58]
0x1800a4e52  test    eax, eax
0x1800a4e54  jnz     short loc_1800A4E60
0x1800a4e56  mov     ebx, 80070002h
0x1800a4e5b  jmp     loc_1800A525A
0x1800a4e60  mov     rcx, [rbp+110h+var_60]
0x1800a4e67  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a4e6e  mov     edx, eax
0x1800a4e70  shl     rdx, 5
0x1800a4e74  add     rdx, rcx
0x1800a4e77  mov     r8d, eax
0x1800a4e7a  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a4e7f  xor     r9d, r9d
0x1800a4e82  mov     [rbp+110h+var_160], r15
0x1800a4e86  mov     ebx, r9d
0x1800a4e89  mov     [rsp+210h+var_1E0], r9b
0x1800a4e8e  xorps   xmm0, xmm0
0x1800a4e91  mov     [rsp+210h+var_1A8], rbx
0x1800a4e96  mov     r12d, 1
0x1800a4e9c  mov     [rbp+110h+var_180], r9b
0x1800a4ea0  mov     dil, r9b
0x1800a4ea3  mov     [rbp+110h+var_168], r9b
0x1800a4ea7  movups  [rbp+110h+var_17C], xmm0
0x1800a4eab  mov     [rbp+110h+var_158], r9w
0x1800a4eb0  lea     rsi, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a4eb7  mov     [rbp+110h+var_154], r9b
0x1800a4ebb  mov     [rbp+110h+var_150], r9d
0x1800a4ebf  mov     [rbp+110h+var_14C], r9b
0x1800a4ec3  mov     [rbp+110h+var_148], r9d
0x1800a4ec7  mov     [rbp+110h+var_144], r9b
0x1800a4ecb  mov     [rbp+110h+var_140], r9d
0x1800a4ecf  mov     [rsp+210h+var_1D4], r9b
0x1800a4ed4  mov     r10, [rbp+110h+var_60]
0x1800a4edb  mov     r14, r10
0x1800a4ede  mov     eax, dword ptr [rbp+110h+var_58]
0x1800a4ee4  shl     rax, 5
0x1800a4ee8  add     rax, r10
0x1800a4eeb  cmp     r14, rax
0x1800a4eee  jz      loc_1800A51C2
0x1800a4ef4  mov     edx, r12d
0x1800a4ef7  mov     rcx, r14
0x1800a4efa  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x1800a4eff  test    al, al
0x1800a4f01  jz      loc_1800A5094
0x1800a4f07  mov     r8, [rsp+210h+var_1B0]
0x1800a4f0c  xor     eax, eax
0x1800a4f0e  mov     rdx, [r14]
0x1800a4f11  mov     r13d, r9d
0x1800a4f14  mov     rcx, [rsp+210h+var_1C8]
0x1800a4f19  xorps   xmm0, xmm0
0x1800a4f1c  mov     word ptr [rbp+110h+var_108], ax
0x1800a4f20  lea     rax, [rsp+210h+var_1C0]
0x1800a4f25  mov     [rsp+210h+var_1E8], rax
0x1800a4f2a  lea     rax, [rsp+210h+var_1B8]
0x1800a4f2f  mov     qword ptr [rsp+210h+var_1B8], r9
0x1800a4f34  mov     [rsp+210h+var_1C0], r9
0x1800a4f39  mov     [rsp+210h+var_1CC], r9b
0x1800a4f3e  mov     [rbp+110h+var_130], r9b
0x1800a4f42  mov     [rbp+110h+var_118], r9b
0x1800a4f46  mov     [rbp+110h+string], r9
0x1800a4f4a  mov     [rbp+110h+var_104], r9b
0x1800a4f4e  mov     [rbp+110h+var_100], r9d
0x1800a4f52  mov     [rbp+110h+var_FC], r9b
0x1800a4f56  mov     [rbp+110h+var_F8], r9d
0x1800a4f5a  mov     [rbp+110h+var_F4], r9b
0x1800a4f5e  mov     dword ptr [rbp+110h+var_F0], r9d
0x1800a4f62  lea     r9, [rbp+110h+var_130]
0x1800a4f66  mov     qword ptr [rsp+210h+var_1F0], rax
0x1800a4f6b  movups  [rbp+110h+var_12C], xmm0
0x1800a4f6f  call    ??_9IPackagedComCatalogContext@@$BIA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{128,{flat}}
0x1800a4f74  mov     rcx, [rsp+210h+var_1C0]
0x1800a4f79  mov     r8, r14
0x1800a4f7c  mov     r9, [rsp+210h+var_1B0]
0x1800a4f81  mov     edi, eax
0x1800a4f83  mov     [rsp+210h+var_1E8], rcx
0x1800a4f88  mov     rcx, qword ptr [rsp+210h+var_1B8]
0x1800a4f8d  mov     qword ptr [rsp+210h+var_1F0], rcx; int
0x1800a4f92  mov     ecx, eax
0x1800a4f94  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComProgIdRegistrationEntryProperties@@AEBVOpaqueString@@PEAUHSTRING__@@W4ComProgIdRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComProgIdRegistrationEntryProperties const &,OpaqueString const &,HSTRING__ *,ComProgIdRegistrationEntryPropertyFlags,ComProgIdRegistrationEntryPropertyFlags)
0x1800a4f99  test    edi, edi
0x1800a4f9b  js      loc_1800A504A
0x1800a4fa1  lea     rcx, [rbp+110h+var_130]
0x1800a4fa5  call    ??$RegistrationHasMachineScope@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationHasMachineScope<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800a4faa  lea     rcx, [rbp+110h+var_130]
0x1800a4fae  mov     dil, al
0x1800a4fb1  call    ??$RegistrationHasUserScope@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationHasUserScope<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800a4fb6  mov     cl, al
0x1800a4fb8  mov     r8d, r12d
0x1800a4fbb  mov     dl, dil
0x1800a4fbe  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x1800a4fc3  test    al, al
0x1800a4fc5  jz      loc_1800A507B
0x1800a4fcb  lea     rcx, [rbp+110h+var_130]
0x1800a4fcf  call    ??$RegistrationIsSupportedSyntaxVersion@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationIsSupportedSyntaxVersion<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800a4fd4  test    al, al
0x1800a4fd6  jz      loc_1800A507B
0x1800a4fdc  mov     rax, [rbp+110h+arg_40]
0x1800a4fe3  lea     r9, [rsp+210h+var_1DF]
0x1800a4fe8  lea     r8, [rbp+110h+var_130]
0x1800a4fec  mov     [rsp+210h+var_1DF], bl
0x1800a4ff0  mov     edx, r12d
0x1800a4ff3  mov     rcx, r14
0x1800a4ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4ffb  mov     edi, eax
0x1800a4ffd  test    eax, eax
0x1800a4fff  jns     short loc_1800A501A
0x1800a5001  mov     rcx, [rbp+118h]; this
0x1800a5008  mov     r9d, eax; char *
0x1800a500b  mov     r8, rsi; unsigned int
0x1800a500e  mov     edx, 1050h; void *
0x1800a5013  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a5018  jmp     short loc_1800A504A
0x1800a501a  mov     cl, [rsp+210h+var_1DF]
0x1800a501e  mov     al, cl
0x1800a5020  neg     al
0x1800a5022  sbb     r13d, r13d
0x1800a5025  and     r13d, 2
0x1800a5029  test    cl, cl
0x1800a502b  jz      short loc_1800A5048
0x1800a502d  movzx   eax, word ptr [rsp+210h+var_1C8+5]
0x1800a5032  mov     [rsp+210h+var_1CB], ax
0x1800a5037  mov     al, byte ptr [rsp+210h+var_1C8+7]
0x1800a503b  mov     [rsp+210h+var_1C9], al
0x1800a503f  mov     [rsp+210h+var_1D0], ebx
0x1800a5043  mov     [rsp+210h+var_1CC], 1
0x1800a5048  xor     edi, edi
0x1800a504a  cmp     edi, 80070002h
0x1800a5050  jz      loc_1800A50DB
0x1800a5056  lea     eax, [rdi+7FFBFEADh]
0x1800a505c  cmp     eax, 1
0x1800a505f  jbe     short loc_1800A50DB
0x1800a5061  cmp     edi, 8007000Dh
0x1800a5067  jz      short loc_1800A50DB
0x1800a5069  test    edi, edi
0x1800a506b  js      loc_1800A5207
0x1800a5071  cmp     r13d, 2
0x1800a5075  jz      loc_1800A5113
0x1800a507b  mov     dil, [rsp+210h+var_1E0]
0x1800a5080  mov     rcx, [rbp+110h+string]; string
0x1800a5084  call    cs:__imp_WindowsDeleteString
0x1800a508a  mov     r10, [rbp+110h+var_60]
0x1800a5091  xor     r9d, r9d
0x1800a5094  mov     edx, dword ptr [rbp+110h+var_58]
0x1800a509a  add     r14, 20h ; ' '
0x1800a509e  shl     rdx, 5
0x1800a50a2  add     rdx, r10
0x1800a50a5  cmp     r14, rdx
0x1800a50a8  jnz     loc_1800A4EDE
0x1800a50ae  cmp     r12d, 1
0x1800a50b2  jnz     short loc_1800A50E5
0x1800a50b4  mov     r8, rdx
0x1800a50b7  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a50be  sub     r8, r10
0x1800a50c1  mov     rcx, r10
0x1800a50c4  sar     r8, 5
0x1800a50c8  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a50cd  xor     r9d, r9d
0x1800a50d0  mov     r12d, 2
0x1800a50d6  jmp     loc_1800A4ED4
0x1800a50db  mov     dil, 1
0x1800a50de  mov     [rsp+210h+var_1E0], dil
0x1800a50e3  jmp     short loc_1800A5080
0x1800a50e5  cmp     r12d, 2
0x1800a50e9  jnz     loc_1800A4EDE
0x1800a50ef  mov     r8, rdx
0x1800a50f2  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a50f9  sub     r8, r10
0x1800a50fc  mov     rcx, r10
0x1800a50ff  sar     r8, 5
0x1800a5103  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a5108  xor     r9d, r9d
0x1800a510b  mov     r12d, r9d
0x1800a510e  jmp     loc_1800A4ED4
0x1800a5113  cmp     [rsp+210h+var_1CC], bl
0x1800a5117  jnz     short loc_1800A512E
0x1800a5119  mov     rcx, [rbp+118h]; this
0x1800a5120  mov     r8, rsi; unsigned int
0x1800a5123  mov     edx, 10E0h; void *
0x1800a5128  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800a512e  cmp     [rsp+210h+var_1D4], bl
0x1800a5132  jz      short loc_1800A5166
0x1800a5134  lea     rcx, [rsp+210h+var_1D0]
0x1800a5139  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800a513e  lea     rcx, [rsp+210h+var_1D8]
0x1800a5143  mov     rbx, rax
0x1800a5146  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800a514b  mov     ecx, [rbx]
0x1800a514d  cmp     [rax], ecx
0x1800a514f  jl      short loc_1800A5166
0x1800a5151  mov     rcx, [rbp+118h]; this
0x1800a5158  mov     r8, rsi; unsigned int
0x1800a515b  mov     edx, 10E4h; void *
0x1800a5160  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800a5166  lea     rdx, [rbp+110h+var_130]
0x1800a516a  lea     rcx, [rbp+110h+var_180]
0x1800a516e  call    ??4ComProgIdRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComProgIdRegistrationEntryProperties::operator=(ComProgIdRegistrationEntryProperties &&)
0x1800a5173  mov     rdx, r14
0x1800a5176  lea     rcx, [rsp+210h+var_1A8]
0x1800a517b  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800a5180  lea     rcx, [rsp+210h+var_1D0]
0x1800a5185  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800a518a  mov     ecx, [rax]
0x1800a518c  movzx   eax, word ptr [rsp+210h+var_1C8+5]
0x1800a5191  mov     [rsp+210h+var_1D3], ax
0x1800a5196  mov     al, byte ptr [rsp+210h+var_1C8+7]
0x1800a519a  mov     [rsp+210h+var_1D8], ecx
0x1800a519e  mov     rcx, [rbp+110h+string]; string
0x1800a51a2  mov     [rsp+210h+var_1D1], al
0x1800a51a6  mov     [rsp+210h+var_1D4], 1
0x1800a51ab  call    cs:__imp_WindowsDeleteString
0x1800a51b1  mov     r15, [rbp+110h+var_160]
0x1800a51b5  xor     r9d, r9d
0x1800a51b8  mov     rbx, [rsp+210h+var_1A8]
0x1800a51bd  mov     dil, [rsp+210h+var_1E0]
0x1800a51c2  cmp     [rsp+210h+var_1D4], r9b
0x1800a51c7  jz      short loc_1800A523E
0x1800a51c9  mov     rcx, [rsp+210h+var_1A0]
0x1800a51ce  lea     rdx, [rbp+110h+var_180]
0x1800a51d2  call    ??4ComProgIdRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComProgIdRegistrationEntryProperties::operator=(ComProgIdRegistrationEntryProperties &&)
0x1800a51d7  mov     rax, [rsp+210h+var_198]
0x1800a51dc  lea     rcx, [rsp+210h+var_1D8]
0x1800a51e1  mov     [rax], rbx
0x1800a51e4  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800a51e9  mov     ecx, [rax]
0x1800a51eb  mov     rax, [rbp+110h+var_190]
0x1800a51ef  mov     [rax], ecx
0x1800a51f1  xor     ecx, ecx; string
0x1800a51f3  call    cs:__imp_WindowsDeleteString
0x1800a51f9  mov     rcx, [rbp+110h+var_160]; string
0x1800a51fd  call    cs:__imp_WindowsDeleteString
0x1800a5203  xor     ebx, ebx
0x1800a5205  jmp     short loc_1800A525A
0x1800a5207  mov     rcx, [rbp+110h+string]; string
0x1800a520b  call    cs:__imp_WindowsDeleteString
0x1800a5211  mov     rcx, [rbp+118h]; this
0x1800a5218  mov     r9d, edi; char *
0x1800a521b  mov     r8, rsi; unsigned int
0x1800a521e  mov     edx, 1114h; void *
  ... truncated ...
```
