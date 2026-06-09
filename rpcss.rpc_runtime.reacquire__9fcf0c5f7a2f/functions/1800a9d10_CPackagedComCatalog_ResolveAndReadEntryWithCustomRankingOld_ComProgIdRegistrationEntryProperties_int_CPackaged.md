# CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComProgIdRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)

- ea: `0x1800a9d10`
- end: `0x1800aa2a4`
- name: `??$ResolveAndReadEntryWithCustomRankingOld@UComProgIdRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU4@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU2@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800a9c84`

## callees

- `0x1800210f8`
- `0x18003b8d0`
- `0x18003c024`
- `0x18003c360`
- `0x18004b0f0`
- `0x18007fbd0`
- `0x1800854fc`
- `0x1800968fc`
- `0x180098190`
- `0x1800a9d10`
- `0x1800b7ac0`
- `0x1800db8f0`
- `0x1800dd708`
- `0x1800dd74c`
- `0x1800dd814`
- `0x1800dff74`
- `0x1800e07c4`
- `0x1800e8dc0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9db0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa04e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa17b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa1cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa1dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa217`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa226`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a9db0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa04e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa17b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa1cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa1dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa217`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa226`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aa248`

## string_xrefs

- `0x1800a9df8`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a9e76`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
0x1800a9d10  mov     [rsp-8+arg_18], rbx
0x1800a9d15  push    rbp
0x1800a9d16  push    rsi
0x1800a9d17  push    rdi
0x1800a9d18  push    r12
0x1800a9d1a  push    r13
0x1800a9d1c  push    r14
0x1800a9d1e  push    r15
0x1800a9d20  lea     rbp, [rsp-0E0h]
0x1800a9d28  sub     rsp, 1E0h
0x1800a9d2f  mov     rax, cs:__security_cookie
0x1800a9d36  xor     rax, rsp
0x1800a9d39  mov     [rbp+110h+var_40], rax
0x1800a9d40  mov     r14, [rbp+110h+arg_20]
0x1800a9d47  xor     r15d, r15d
0x1800a9d4a  mov     rsi, [rbp+110h+arg_28]
0x1800a9d51  mov     rbx, rdx
0x1800a9d54  mov     [rsp+210h+var_198], rdx
0x1800a9d59  xorps   xmm0, xmm0
0x1800a9d5c  xor     eax, eax
0x1800a9d5e  mov     [rsp+210h+var_1C8], r14
0x1800a9d63  lea     rdx, [rbp+110h+var_130]
0x1800a9d67  mov     [rsp+210h+var_1B0], rsi
0x1800a9d6c  mov     [rbp+110h+var_130], r15b
0x1800a9d70  mov     rdi, r8
0x1800a9d73  movups  [rbp+110h+var_12C], xmm0
0x1800a9d77  mov     [rbp+110h+var_11C], eax
0x1800a9d7a  mov     [rbp+110h+var_118], r15b
0x1800a9d7e  mov     [rbp+110h+string], r15
0x1800a9d82  mov     [rbp+110h+var_108], r15d
0x1800a9d86  mov     [rbp+110h+var_104], r15b
0x1800a9d8a  mov     [rbp+110h+var_100], r15d
0x1800a9d8e  mov     [rbp+110h+var_FC], r15b
0x1800a9d92  mov     [rbp+110h+var_F8], r15d
0x1800a9d96  mov     [rbp+110h+var_F4], r15b
0x1800a9d9a  mov     [rbp+110h+var_F0], r15
0x1800a9d9e  mov     [rbp+110h+var_190], r8
0x1800a9da2  mov     [rsp+210h+var_1A0], rcx
0x1800a9da7  call    ??4ComProgIdRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComProgIdRegistrationEntryProperties::operator=(ComProgIdRegistrationEntryProperties &&)
0x1800a9dac  mov     rcx, [rbp+110h+string]; string
0x1800a9db0  call    cs:__imp_WindowsDeleteString
0x1800a9db7  nop     dword ptr [rax+rax+00h]
0x1800a9dbc  mov     [rbx], r15
0x1800a9dbf  lea     rcx, [rbp+110h+var_E0]; this
0x1800a9dc3  mov     [rdi], r15d
0x1800a9dc6  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x1800a9dcb  mov     al, [rbp+110h+arg_30]
0x1800a9dd1  lea     rcx, [rbp+110h+var_E0]; this
0x1800a9dd5  mov     [rsp+210h+var_1E8], r15; PackageFilter *
0x1800a9dda  mov     r9, rsi
0x1800a9ddd  mov     r8, r14
0x1800a9de0  mov     [rsp+210h+var_1F0], al; int
0x1800a9de4  xor     edx, edx
0x1800a9de6  call    ??$GetInstalledPackagesContainingEntry@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAUHSTRING__@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComProgIdRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *)
0x1800a9deb  mov     ebx, eax
0x1800a9ded  test    eax, eax
0x1800a9def  jns     short loc_1800A9E11
0x1800a9df1  mov     rcx, [rbp+118h]; this
0x1800a9df8  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a9dff  mov     r9d, eax; char *
0x1800a9e02  mov     edx, 1083h; void *
0x1800a9e07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9e0c  jmp     loc_1800AA25E
0x1800a9e11  mov     rax, [rbp+110h+var_58]
0x1800a9e18  test    eax, eax
0x1800a9e1a  jnz     short loc_1800A9E26
0x1800a9e1c  mov     ebx, 80070002h
0x1800a9e21  jmp     loc_1800AA25E
0x1800a9e26  mov     rcx, [rbp+110h+var_60]
0x1800a9e2d  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800a9e34  mov     edx, eax
0x1800a9e36  shl     rdx, 5
0x1800a9e3a  add     rdx, rcx
0x1800a9e3d  mov     r8d, eax
0x1800a9e40  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800a9e45  xor     r9d, r9d
0x1800a9e48  mov     [rbp+110h+var_160], r15
0x1800a9e4c  mov     ebx, r9d
0x1800a9e4f  mov     [rsp+210h+var_1E0], r9b
0x1800a9e54  xorps   xmm0, xmm0
0x1800a9e57  mov     [rsp+210h+var_1A8], rbx
0x1800a9e5c  mov     r12d, 1
0x1800a9e62  mov     [rbp+110h+var_180], r9b
0x1800a9e66  mov     dil, r9b
0x1800a9e69  mov     [rbp+110h+var_168], r9b
0x1800a9e6d  movups  [rbp+110h+var_17C], xmm0
0x1800a9e71  mov     [rbp+110h+var_158], r9w
0x1800a9e76  lea     rsi, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a9e7d  mov     [rbp+110h+var_154], r9b
0x1800a9e81  mov     [rbp+110h+var_150], r9d
0x1800a9e85  mov     [rbp+110h+var_14C], r9b
0x1800a9e89  mov     [rbp+110h+var_148], r9d
0x1800a9e8d  mov     [rbp+110h+var_144], r9b
0x1800a9e91  mov     [rbp+110h+var_140], r9d
0x1800a9e95  mov     [rsp+210h+var_1D4], r9b
0x1800a9e9a  mov     r10, [rbp+110h+var_60]
0x1800a9ea1  mov     r14, r10
0x1800a9ea4  mov     eax, dword ptr [rbp+110h+var_58]
0x1800a9eaa  shl     rax, 5
0x1800a9eae  add     rax, r10
0x1800a9eb1  cmp     r14, rax
0x1800a9eb4  jz      loc_1800AA198
0x1800a9eba  mov     edx, r12d
0x1800a9ebd  mov     rcx, r14
0x1800a9ec0  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x1800a9ec5  test    al, al
0x1800a9ec7  jz      loc_1800AA064
0x1800a9ecd  mov     r8, [rsp+210h+var_1B0]
0x1800a9ed2  xor     eax, eax
0x1800a9ed4  mov     rdx, [r14]
0x1800a9ed7  mov     r13d, r9d
0x1800a9eda  mov     rcx, [rsp+210h+var_1C8]
0x1800a9edf  xorps   xmm0, xmm0
0x1800a9ee2  mov     word ptr [rbp+110h+var_108], ax
0x1800a9ee6  lea     rax, [rsp+210h+var_1C0]
0x1800a9eeb  mov     [rsp+210h+var_1E8], rax
0x1800a9ef0  lea     rax, [rsp+210h+var_1B8]
0x1800a9ef5  mov     qword ptr [rsp+210h+var_1B8], r9
0x1800a9efa  mov     [rsp+210h+var_1C0], r9
0x1800a9eff  mov     [rsp+210h+var_1CC], r9b
0x1800a9f04  mov     [rbp+110h+var_130], r9b
0x1800a9f08  mov     [rbp+110h+var_118], r9b
0x1800a9f0c  mov     [rbp+110h+string], r9
0x1800a9f10  mov     [rbp+110h+var_104], r9b
0x1800a9f14  mov     [rbp+110h+var_100], r9d
0x1800a9f18  mov     [rbp+110h+var_FC], r9b
0x1800a9f1c  mov     [rbp+110h+var_F8], r9d
0x1800a9f20  mov     [rbp+110h+var_F4], r9b
0x1800a9f24  mov     dword ptr [rbp+110h+var_F0], r9d
0x1800a9f28  lea     r9, [rbp+110h+var_130]
0x1800a9f2c  mov     qword ptr [rsp+210h+var_1F0], rax
0x1800a9f31  movups  [rbp+110h+var_12C], xmm0
0x1800a9f35  call    ??_9IPackagedComCatalogContext@@$BIA@AA; [thunk]: IPackagedComCatalogContext::`vcall'{128,{flat}}
0x1800a9f3a  mov     rcx, [rsp+210h+var_1C0]
0x1800a9f3f  mov     r8, r14
0x1800a9f42  mov     r9, [rsp+210h+var_1B0]
0x1800a9f47  mov     edi, eax
0x1800a9f49  mov     [rsp+210h+var_1E8], rcx
0x1800a9f4e  mov     rcx, qword ptr [rsp+210h+var_1B8]
0x1800a9f53  mov     qword ptr [rsp+210h+var_1F0], rcx; int
0x1800a9f58  mov     ecx, eax
0x1800a9f5a  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComProgIdRegistrationEntryProperties@@AEBVOpaqueString@@PEAUHSTRING__@@W4ComProgIdRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComProgIdRegistrationEntryProperties const &,OpaqueString const &,HSTRING__ *,ComProgIdRegistrationEntryPropertyFlags,ComProgIdRegistrationEntryPropertyFlags)
0x1800a9f5f  test    edi, edi
0x1800a9f61  js      loc_1800AA010
0x1800a9f67  lea     rcx, [rbp+110h+var_130]
0x1800a9f6b  call    ??$RegistrationHasMachineScope@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationHasMachineScope<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800a9f70  lea     rcx, [rbp+110h+var_130]
0x1800a9f74  mov     dil, al
0x1800a9f77  call    ??$RegistrationHasUserScope@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationHasUserScope<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800a9f7c  mov     cl, al
0x1800a9f7e  mov     r8d, r12d
0x1800a9f81  mov     dl, dil
0x1800a9f84  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x1800a9f89  test    al, al
0x1800a9f8b  jz      loc_1800AA045
0x1800a9f91  lea     rcx, [rbp+110h+var_130]
0x1800a9f95  call    ??$RegistrationIsSupportedSyntaxVersion@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationIsSupportedSyntaxVersion<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800a9f9a  test    al, al
0x1800a9f9c  jz      loc_1800AA045
0x1800a9fa2  mov     rax, [rbp+110h+arg_40]
0x1800a9fa9  lea     r9, [rsp+210h+var_1DF]
0x1800a9fae  lea     r8, [rbp+110h+var_130]
0x1800a9fb2  mov     [rsp+210h+var_1DF], bl
0x1800a9fb6  mov     edx, r12d
0x1800a9fb9  mov     rcx, r14
0x1800a9fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9fc1  mov     edi, eax
0x1800a9fc3  test    eax, eax
0x1800a9fc5  jns     short loc_1800A9FE0
0x1800a9fc7  mov     rcx, [rbp+118h]; this
0x1800a9fce  mov     r9d, eax; char *
0x1800a9fd1  mov     r8, rsi; unsigned int
0x1800a9fd4  mov     edx, 1050h; void *
0x1800a9fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a9fde  jmp     short loc_1800AA010
0x1800a9fe0  mov     cl, [rsp+210h+var_1DF]
0x1800a9fe4  mov     al, cl
0x1800a9fe6  neg     al
0x1800a9fe8  sbb     r13d, r13d
0x1800a9feb  and     r13d, 2
0x1800a9fef  test    cl, cl
0x1800a9ff1  jz      short loc_1800AA00E
0x1800a9ff3  movzx   eax, word ptr [rsp+210h+var_1C8+5]
0x1800a9ff8  mov     [rsp+210h+var_1CB], ax
0x1800a9ffd  mov     al, byte ptr [rsp+210h+var_1C8+7]
0x1800aa001  mov     [rsp+210h+var_1C9], al
0x1800aa005  mov     [rsp+210h+var_1D0], ebx
0x1800aa009  mov     [rsp+210h+var_1CC], 1
0x1800aa00e  xor     edi, edi
0x1800aa010  cmp     edi, 80070002h
0x1800aa016  jz      loc_1800AA0AB
0x1800aa01c  lea     eax, [rdi+7FFBFEADh]
0x1800aa022  cmp     eax, 1
0x1800aa025  jbe     loc_1800AA0AB
0x1800aa02b  cmp     edi, 8007000Dh
0x1800aa031  jz      short loc_1800AA0AB
0x1800aa033  test    edi, edi
0x1800aa035  js      loc_1800AA1ED
0x1800aa03b  cmp     r13d, 2
0x1800aa03f  jz      loc_1800AA0E3
0x1800aa045  mov     dil, [rsp+210h+var_1E0]
0x1800aa04a  mov     rcx, [rbp+110h+string]; string
0x1800aa04e  call    cs:__imp_WindowsDeleteString
0x1800aa055  nop     dword ptr [rax+rax+00h]
0x1800aa05a  mov     r10, [rbp+110h+var_60]
0x1800aa061  xor     r9d, r9d
0x1800aa064  mov     edx, dword ptr [rbp+110h+var_58]
0x1800aa06a  add     r14, 20h ; ' '
0x1800aa06e  shl     rdx, 5
0x1800aa072  add     rdx, r10
0x1800aa075  cmp     r14, rdx
0x1800aa078  jnz     loc_1800A9EA4
0x1800aa07e  cmp     r12d, 1
0x1800aa082  jnz     short loc_1800AA0B5
0x1800aa084  mov     r8, rdx
0x1800aa087  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800aa08e  sub     r8, r10
0x1800aa091  mov     rcx, r10
0x1800aa094  sar     r8, 5
0x1800aa098  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800aa09d  xor     r9d, r9d
0x1800aa0a0  mov     r12d, 2
0x1800aa0a6  jmp     loc_1800A9E9A
0x1800aa0ab  mov     dil, 1
0x1800aa0ae  mov     [rsp+210h+var_1E0], dil
0x1800aa0b3  jmp     short loc_1800AA04A
0x1800aa0b5  cmp     r12d, 2
0x1800aa0b9  jnz     loc_1800A9EA4
0x1800aa0bf  mov     r8, rdx
0x1800aa0c2  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800aa0c9  sub     r8, r10
0x1800aa0cc  mov     rcx, r10
0x1800aa0cf  sar     r8, 5
0x1800aa0d3  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800aa0d8  xor     r9d, r9d
0x1800aa0db  mov     r12d, r9d
0x1800aa0de  jmp     loc_1800A9E9A
0x1800aa0e3  cmp     [rsp+210h+var_1CC], bl
0x1800aa0e7  jnz     short loc_1800AA0FE
0x1800aa0e9  mov     rcx, [rbp+118h]; this
0x1800aa0f0  mov     r8, rsi; unsigned int
0x1800aa0f3  mov     edx, 10E0h; void *
0x1800aa0f8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800aa0fe  cmp     [rsp+210h+var_1D4], bl
0x1800aa102  jz      short loc_1800AA136
0x1800aa104  lea     rcx, [rsp+210h+var_1D0]
0x1800aa109  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800aa10e  lea     rcx, [rsp+210h+var_1D8]
0x1800aa113  mov     rbx, rax
0x1800aa116  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800aa11b  mov     ecx, [rbx]
0x1800aa11d  cmp     [rax], ecx
0x1800aa11f  jl      short loc_1800AA136
0x1800aa121  mov     rcx, [rbp+118h]; this
0x1800aa128  mov     r8, rsi; unsigned int
0x1800aa12b  mov     edx, 10E4h; void *
0x1800aa130  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800aa136  lea     rdx, [rbp+110h+var_130]
0x1800aa13a  lea     rcx, [rbp+110h+var_180]
0x1800aa13e  call    ??4ComProgIdRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComProgIdRegistrationEntryProperties::operator=(ComProgIdRegistrationEntryProperties &&)
0x1800aa143  mov     rdx, r14
0x1800aa146  lea     rcx, [rsp+210h+var_1A8]
0x1800aa14b  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800aa150  lea     rcx, [rsp+210h+var_1D0]
0x1800aa155  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800aa15a  mov     ecx, [rax]
0x1800aa15c  movzx   eax, word ptr [rsp+210h+var_1C8+5]
0x1800aa161  mov     [rsp+210h+var_1D3], ax
0x1800aa166  mov     al, byte ptr [rsp+210h+var_1C8+7]
0x1800aa16a  mov     [rsp+210h+var_1D8], ecx
0x1800aa16e  mov     rcx, [rbp+110h+string]; string
0x1800aa172  mov     [rsp+210h+var_1D1], al
0x1800aa176  mov     [rsp+210h+var_1D4], 1
0x1800aa17b  call    cs:__imp_WindowsDeleteString
0x1800aa182  nop     dword ptr [rax+rax+00h]
0x1800aa187  mov     r15, [rbp+110h+var_160]
0x1800aa18b  xor     r9d, r9d
0x1800aa18e  mov     rbx, [rsp+210h+var_1A8]
0x1800aa193  mov     dil, [rsp+210h+var_1E0]
0x1800aa198  cmp     [rsp+210h+var_1D4], r9b
0x1800aa19d  jz      loc_1800AA236
0x1800aa1a3  mov     rcx, [rsp+210h+var_1A0]
0x1800aa1a8  lea     rdx, [rbp+110h+var_180]
0x1800aa1ac  call    ??4ComProgIdRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComProgIdRegistrationEntryProperties::operator=(ComProgIdRegistrationEntryProperties &&)
0x1800aa1b1  mov     rax, [rsp+210h+var_198]
0x1800aa1b6  lea     rcx, [rsp+210h+var_1D8]
0x1800aa1bb  mov     [rax], rbx
0x1800aa1be  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800aa1c3  mov     ecx, [rax]
0x1800aa1c5  mov     rax, [rbp+110h+var_190]
0x1800aa1c9  mov     [rax], ecx
0x1800aa1cb  xor     ecx, ecx; string
0x1800aa1cd  call    cs:__imp_WindowsDeleteString
0x1800aa1d4  nop     dword ptr [rax+rax+00h]
0x1800aa1d9  mov     rcx, [rbp+110h+var_160]; string
0x1800aa1dd  call    cs:__imp_WindowsDeleteString
0x1800aa1e4  nop     dword ptr [rax+rax+00h]
0x1800aa1e9  xor     ebx, ebx
0x1800aa1eb  jmp     short loc_1800AA25E
0x1800aa1ed  mov     rcx, [rbp+110h+string]; string
  ... truncated ...
```
