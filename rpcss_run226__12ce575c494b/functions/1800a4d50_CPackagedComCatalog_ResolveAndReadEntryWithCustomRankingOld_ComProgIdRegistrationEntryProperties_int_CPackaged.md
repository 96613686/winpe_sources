# CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComProgIdRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)

- ea: `0x1800a4d50`
- end: `0x1800a529f`
- name: `??$ResolveAndReadEntryWithCustomRankingOld@UComProgIdRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU4@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU2@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z`
- size: `1359`
- prototype: ``
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
        __int64 a6,
        char a7,
        int a8,
        __int64 (__fastcall *a9)(__int64 *, _QWORD, _BYTE *, char *))
{
  HSTRING v9; // r15
  int InstalledPackagesContaining; // eax
  unsigned int v13; // ebx
  __int64 v14; // r8
  HSTRING v15; // r9
  HSTRING v16; // rbx
  unsigned int v17; // r12d
  char v18; // di
  _QWORD *v19; // r10
  __int64 *v20; // r14
  __int64 v21; // rdx
  int v22; // r13d
  __int64 v23; // rdi
  __int64 v24; // rdx
  const char *v25; // r9
  char HasMachine; // di
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // eax
  __int64 *v30; // rdx
  _DWORD *v31; // rbx
  const char *v32; // r9
  int v33; // ecx
  _DWORD *v34; // rax
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  char v38; // [rsp+30h] [rbp-D0h]
  char v39[7]; // [rsp+31h] [rbp-CFh] BYREF
  int v40; // [rsp+38h] [rbp-C8h] BYREF
  char v41; // [rsp+3Ch] [rbp-C4h]
  __int16 v42; // [rsp+3Dh] [rbp-C3h]
  char v43; // [rsp+3Fh] [rbp-C1h]
  int v44; // [rsp+40h] [rbp-C0h] BYREF
  char v45; // [rsp+44h] [rbp-BCh]
  __int16 v46; // [rsp+45h] [rbp-BBh]
  char v47; // [rsp+47h] [rbp-B9h]
  __int64 v48; // [rsp+48h] [rbp-B8h]
  HSTRING v49; // [rsp+50h] [rbp-B0h] BYREF
  int v50[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A0h]
  HSTRING v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h]
  HSTRING *v54; // [rsp+78h] [rbp-88h]
  _DWORD *v55; // [rsp+80h] [rbp-80h]
  _BYTE v56[4]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v57; // [rsp+94h] [rbp-6Ch]
  char v58; // [rsp+A8h] [rbp-58h]
  HSTRING v59; // [rsp+B0h] [rbp-50h]
  __int16 v60; // [rsp+B8h] [rbp-48h]
  char v61; // [rsp+BCh] [rbp-44h]
  int v62; // [rsp+C0h] [rbp-40h]
  char v63; // [rsp+C4h] [rbp-3Ch]
  int v64; // [rsp+C8h] [rbp-38h]
  char v65; // [rsp+CCh] [rbp-34h]
  int v66; // [rsp+D0h] [rbp-30h]
  _BYTE v67[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v68; // [rsp+E4h] [rbp-1Ch]
  int v69; // [rsp+F4h] [rbp-Ch]
  char v70; // [rsp+F8h] [rbp-8h]
  HSTRING string; // [rsp+100h] [rbp+0h]
  int v72; // [rsp+108h] [rbp+8h]
  char v73; // [rsp+10Ch] [rbp+Ch]
  int v74; // [rsp+110h] [rbp+10h]
  char v75; // [rsp+114h] [rbp+14h]
  int v76; // [rsp+118h] [rbp+18h]
  char v77; // [rsp+11Ch] [rbp+1Ch]
  __int64 v78; // [rsp+120h] [rbp+20h]
  _BYTE v79[128]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD *v80; // [rsp+1B0h] [rbp+B0h]
  __int64 v81; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v9 = 0;
  v54 = a2;
  v48 = a5;
  v51 = a6;
  v67[0] = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  string = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  v78 = 0;
  v55 = a3;
  v53 = a1;
  ComProgIdRegistrationEntryProperties::operator=(a1, v67);
  WindowsDeleteString(string);
  *a2 = 0;
  *a3 = 0;
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v79);
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(
                                  (PackageListBuffer *)v79,
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
      v36);
    goto LABEL_41;
  }
  if ( !(_DWORD)v81 )
  {
    v13 = -2147024894;
    goto LABEL_41;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v80,
    &v80[4 * (unsigned int)v81],
    (unsigned int)v81,
    MoreRecentlyInstalledByUser);
  v15 = 0;
  v59 = 0;
  v16 = 0;
  v38 = 0;
  v52 = 0;
  v17 = 1;
  v56[0] = 0;
  v18 = 0;
  v58 = 0;
  v57 = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v41 = 0;
LABEL_6:
  v19 = v80;
  v20 = v80;
  while ( v20 != &v19[4 * (unsigned int)v81] )
  {
    if ( !(unsigned __int8)PackageInstalledForScope(v20, v17, v14, v15) )
      goto LABEL_24;
    v21 = *v20;
    v22 = (int)v15;
    LOWORD(v72) = 0;
    *(_QWORD *)v50 = v15;
    v49 = v15;
    v45 = (char)v15;
    v67[0] = (_BYTE)v15;
    v70 = (char)v15;
    string = v15;
    v73 = (char)v15;
    v74 = (int)v15;
    v75 = (char)v15;
    v76 = (int)v15;
    v77 = (char)v15;
    LODWORD(v78) = (_DWORD)v15;
    v68 = 0;
    v23 = (unsigned int) IPackagedComCatalogContext::`vcall'{128,{flat}}(v48, v21, v51, v67, v50, &v49);
    v37 = v50[0];
    CPackagedComCatalog::LogReadEntryResult(v23, v24, v20, v51);
    if ( (int)v23 >= 0 )
    {
      HasMachine = RegistrationHasMachineScope<ComProgIdRegistrationEntryProperties>(v67);
      LOBYTE(v27) = RegistrationHasUserScope<ComProgIdRegistrationEntryProperties>(v67);
      LOBYTE(v28) = HasMachine;
      if ( !(unsigned __int8)RegistrationScopeMatchesInstallScope(v27, v28, v17)
        || !(unsigned __int8)RegistrationIsSupportedSyntaxVersion<ComProgIdRegistrationEntryProperties>(v67) )
      {
        goto LABEL_22;
      }
      v39[0] = 0;
      v29 = a9(v20, v17, v67, v39);
      LODWORD(v23) = v29;
      if ( v29 >= 0 )
      {
        v22 = v39[0] != 0 ? 2 : 0;
        if ( v39[0] )
        {
          v46 = *(_WORD *)((char *)&v48 + 5);
          v47 = HIBYTE(v48);
          v44 = 0;
          v45 = 1;
        }
        LODWORD(v23) = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1050,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)(unsigned int)v29,
          v37);
      }
    }
    if ( (_DWORD)v23 == -2147024894 || (unsigned int)(v23 + 2147221165) <= 1 || (_DWORD)v23 == -2147024883 )
    {
      v18 = 1;
      v38 = 1;
      goto LABEL_23;
    }
    if ( (int)v23 < 0 )
    {
      WindowsDeleteString(string);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1114,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)v23,
        v37);
      WindowsDeleteString(0);
      WindowsDeleteString(0);
      v13 = v23;
      goto LABEL_41;
    }
    if ( v22 == 2 )
    {
      if ( !v45 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x10E0,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          v25);
      if ( v41 )
      {
        v31 = (_DWORD *)std::optional<int>::value(&v44);
        if ( *(_DWORD *)std::optional<int>::value(&v40) >= *v31 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x10E4,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            v32);
      }
      ComProgIdRegistrationEntryProperties::operator=(v56, v67);
      OpaqueString::operator=(&v52, v20);
      v33 = *(_DWORD *)std::optional<int>::value(&v44);
      v42 = *(_WORD *)((char *)&v48 + 5);
      v40 = v33;
      v43 = HIBYTE(v48);
      v41 = 1;
      WindowsDeleteString(string);
      v9 = v59;
      LOBYTE(v15) = 0;
      v16 = v52;
      v18 = v38;
      break;
    }
LABEL_22:
    v18 = v38;
LABEL_23:
    WindowsDeleteString(string);
    v19 = v80;
    v15 = 0;
LABEL_24:
    v20 += 4;
    v30 = &v19[4 * (unsigned int)v81];
    if ( v20 == v30 )
    {
      if ( v17 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v19,
          v30,
          (32LL * (unsigned int)v81) >> 5,
          MoreRecentlyInstalledByOneTime);
        v15 = 0;
        v17 = 2;
        goto LABEL_6;
      }
      if ( v17 == 2 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v19,
          v30,
          (32LL * (unsigned int)v81) >> 5,
          MoreRecentlyInstalledByMachine);
        v15 = 0;
        v17 = 0;
        goto LABEL_6;
      }
    }
  }
  if ( v41 != (_BYTE)v15 )
  {
    ComProgIdRegistrationEntryProperties::operator=(v53, v56);
    *v54 = v16;
    v34 = (_DWORD *)std::optional<int>::value(&v40);
    *v55 = *v34;
    WindowsDeleteString(0);
    WindowsDeleteString(v59);
    v13 = 0;
    goto LABEL_41;
  }
  WindowsDeleteString(v16);
  WindowsDeleteString(v9);
  if ( v18 )
  {
    v13 = -2147024883;
LABEL_41:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v79);
    return v13;
  }
  else
  {
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v79);
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
