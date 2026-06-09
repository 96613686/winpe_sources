# CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)

- ea: `0x18009633c`
- end: `0x1800968d3`
- name: `??$ResolveAndReadEntryWithCustomRankingOld@UComTreatAsClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z`
- size: `1431`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, char, PackageFilter *, char)`
- caller_count: `2`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800948e0`
- `0x1800962a8`

## callees

- `0x1800210f8`
- `0x18003b8d0`
- `0x18003c024`
- `0x18003c360`
- `0x18004b0f0`
- `0x1800701e0`
- `0x1800720e0`
- `0x18007fbd0`
- `0x1800854fc`
- `0x18009633c`
- `0x1800968fc`
- `0x180098190`
- `0x1800b7ac0`
- `0x1800dd71c`
- `0x1800dd768`
- `0x1800dd874`
- `0x1800e05dc`
- `0x1800e07dc`
- `0x1800e9240`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800963de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800966a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800967d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009681f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009684b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009685b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009686e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009687e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800963de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800966a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800967d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009681f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009684b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009685b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009686e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009687e`

## string_xrefs

- `0x18009642f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180096724`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180096743`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18009677f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180096832`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall Z::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
        __int64 a1,
        HSTRING *a2,
        _DWORD *a3,
        __int64 a4,
        __int64 *a5,
        GUID *a6,
        char a7,
        PackageFilter *a8,
        char a9)
{
  int InstalledPackagesContaining; // eax
  int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  char v16; // r12
  __int16 v17; // r13
  unsigned int v18; // esi
  char v19; // r15
  _QWORD *v20; // r10
  __int64 *v21; // rdi
  __int64 v22; // rdx
  int v23; // r14d
  const char *v24; // r9
  char HasMachine; // bl
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // eax
  _DWORD *v29; // rbx
  __int64 *v30; // rdx
  _DWORD *v31; // rbx
  const char *v32; // r9
  int v33; // ecx
  _DWORD *v34; // rax
  HSTRING v35; // rcx
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  int v39; // [rsp+40h] [rbp-C0h] BYREF
  char v40; // [rsp+44h] [rbp-BCh]
  __int16 v41; // [rsp+45h] [rbp-BBh]
  char v42; // [rsp+47h] [rbp-B9h]
  _BYTE v43[4]; // [rsp+48h] [rbp-B8h] BYREF
  char v44; // [rsp+4Ch] [rbp-B4h]
  HSTRING v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  GUID *v47; // [rsp+60h] [rbp-A0h]
  __int64 *v48; // [rsp+68h] [rbp-98h]
  __int128 v49; // [rsp+70h] [rbp-90h] BYREF
  char v50; // [rsp+80h] [rbp-80h]
  HSTRING string; // [rsp+88h] [rbp-78h]
  char v52; // [rsp+90h] [rbp-70h]
  __int128 v53; // [rsp+94h] [rbp-6Ch]
  int v54; // [rsp+A4h] [rbp-5Ch]
  char v55; // [rsp+A8h] [rbp-58h]
  int v56; // [rsp+ACh] [rbp-54h]
  char v57; // [rsp+B0h] [rbp-50h]
  int v58; // [rsp+B4h] [rbp-4Ch]
  char v59; // [rsp+B8h] [rbp-48h]
  int v60; // [rsp+BCh] [rbp-44h]
  __int64 v61; // [rsp+C0h] [rbp-40h] BYREF
  int v62[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v63; // [rsp+D0h] [rbp-30h]
  HSTRING *v64; // [rsp+D8h] [rbp-28h]
  _DWORD *v65; // [rsp+E0h] [rbp-20h]
  _BYTE v66[24]; // [rsp+F0h] [rbp-10h] BYREF
  HSTRING v67; // [rsp+108h] [rbp+8h]
  char v68; // [rsp+110h] [rbp+10h]
  __int128 v69; // [rsp+114h] [rbp+14h]
  __int16 v70; // [rsp+124h] [rbp+24h]
  char v71; // [rsp+128h] [rbp+28h]
  int v72; // [rsp+12Ch] [rbp+2Ch]
  char v73; // [rsp+130h] [rbp+30h]
  int v74; // [rsp+134h] [rbp+34h]
  char v75; // [rsp+138h] [rbp+38h]
  int v76; // [rsp+13Ch] [rbp+3Ch]
  _BYTE v77[128]; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v78; // [rsp+1C0h] [rbp+C0h]
  __int64 v79; // [rsp+1C8h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  v63 = a1;
  v64 = a2;
  v50 = 0;
  string = 0;
  v52 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v65 = a3;
  v48 = a5;
  v47 = a6;
  v49 = 0;
  v53 = 0;
  ComTreatAsClassRegistrationEntryProperties::operator=(a1, &v49);
  WindowsDeleteString(string);
  *a2 = 0;
  *a3 = 0;
  PackageListBuffer::PackageListBuffer((PackageListBuffer *)v77);
  InstalledPackagesContaining = CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(
                                  (PackageListBuffer *)v77,
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
      v37);
    goto LABEL_45;
  }
  v13 = 0;
  if ( !(_DWORD)v79 )
  {
    v13 = -2147024894;
    goto LABEL_45;
  }
  std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
    v78,
    &v78[4 * (unsigned int)v79],
    (unsigned int)v79,
    MoreRecentlyInstalledByUser);
  v16 = HIBYTE(v47);
  v17 = *(_WORD *)((char *)&v47 + 5);
  v18 = 1;
  v53 = 0;
  v19 = 0;
  v50 = 0;
  string = 0;
  v52 = 0;
  LOWORD(v54) = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v45 = 0;
  v40 = 0;
LABEL_6:
  v20 = v78;
  v21 = v78;
  while ( 1 )
  {
    if ( v21 == &v20[4 * (unsigned int)v79] )
      goto LABEL_39;
    if ( (unsigned __int8)PackageInstalledForScope(v21, v18, v14, v15) )
      break;
LABEL_26:
    v21 += 4;
    v30 = &v20[4 * (unsigned int)v79];
    if ( v21 == v30 )
    {
      if ( v18 == 1 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v20,
          v30,
          (32LL * (unsigned int)v79) >> 5,
          MoreRecentlyInstalledByOneTime);
        v18 = 2;
        goto LABEL_6;
      }
      if ( v18 == 2 )
      {
        std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(
          v20,
          v30,
          (32LL * (unsigned int)v79) >> 5,
          MoreRecentlyInstalledByMachine);
        v18 = 0;
        goto LABEL_6;
      }
    }
  }
  v22 = *v21;
  v70 = 0;
  v23 = 0;
  *(_QWORD *)v62 = 0;
  v61 = 0;
  v46 = 0;
  v44 = 0;
  v66[16] = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v71 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v75 = 0;
  v76 = 0;
  v13 =  IPackagedComCatalogContext::`vcall'{136,{flat}}(v48, v22, v47, v66, v62, &v61);
  v38 = v62[0];
  CPackagedComCatalog::LogReadEntryResult((unsigned int)v13, v66, v21, v47);
  if ( v13 >= 0 )
  {
    HasMachine = RegistrationHasMachineScope<ComTreatAsClassRegistrationEntryProperties>(v66);
    LOBYTE(v26) = RegistrationHasUserScope<ComTreatAsClassRegistrationEntryProperties>(v66);
    LOBYTE(v27) = HasMachine;
    v13 = 0;
    if ( !(unsigned __int8)RegistrationScopeMatchesInstallScope(v26, v27, v18)
      || !(unsigned __int8)RegistrationIsSupportedSyntaxVersion<ComTreatAsClassRegistrationEntryProperties>(v66) )
    {
      goto LABEL_18;
    }
    v28 = `CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability::operator()(
            (unsigned int)&a9,
            (_DWORD)v21,
            v18,
            (unsigned int)v66,
            v38,
            (__int64)&v46,
            (__int64)v43);
    v23 = v46;
    v13 = v28;
  }
  if ( v13 == -2147024894 || (unsigned int)(v13 + 2147221165) <= 1 || v13 == -2147024883 )
  {
    v19 = 1;
LABEL_25:
    WindowsDeleteString(v67);
    v20 = v78;
    v13 = 0;
    goto LABEL_26;
  }
  if ( v13 < 0 )
  {
    WindowsDeleteString(v67);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1114,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v13,
      v38);
    v35 = v45;
    goto LABEL_42;
  }
  v13 = 0;
LABEL_18:
  if ( v23 != 2 )
  {
    if ( v23 == 1 )
    {
      if ( !v44 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x10EF,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          v24);
      if ( !v40 || (v29 = (_DWORD *)std::optional<int>::value(v43), *(_DWORD *)std::optional<int>::value(&v39) < *v29) )
      {
        ComTreatAsClassRegistrationEntryProperties::operator=(&v49, v66);
        OpaqueString::operator=(&v45, v21);
        v39 = *(_DWORD *)std::optional<int>::value(v43);
        v40 = 1;
        v41 = v17;
        v42 = v16;
      }
    }
    goto LABEL_25;
  }
  if ( !v44 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x10E0,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      v24);
  if ( v40 )
  {
    v31 = (_DWORD *)std::optional<int>::value(v43);
    if ( *(_DWORD *)std::optional<int>::value(&v39) >= *v31 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x10E4,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        v32);
    v13 = 0;
  }
  ComTreatAsClassRegistrationEntryProperties::operator=(&v49, v66);
  OpaqueString::operator=(&v45, v21);
  v33 = *(_DWORD *)std::optional<int>::value(v43);
  v41 = *(_WORD *)((char *)&v48 + 5);
  v39 = v33;
  v42 = HIBYTE(v48);
  v40 = 1;
  WindowsDeleteString(v67);
LABEL_39:
  if ( v40 )
  {
    ComTreatAsClassRegistrationEntryProperties::operator=(v63, &v49);
    *v64 = v45;
    v34 = (_DWORD *)std::optional<int>::value(&v39);
    *v65 = *v34;
    v35 = 0;
LABEL_42:
    WindowsDeleteString(v35);
    WindowsDeleteString(string);
    goto LABEL_45;
  }
  WindowsDeleteString(v45);
  WindowsDeleteString(string);
  if ( v19 )
  {
    v13 = -2147024883;
LABEL_45:
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v77);
    return (unsigned int)v13;
  }
  else
  {
    PackageListBuffer::~PackageListBuffer((PackageListBuffer *)v77);
    return 2147942402LL;
  }
}

```

## disassembly

```asm
0x18009633c  push    rbp
0x18009633e  push    rbx
0x18009633f  push    rsi
0x180096340  push    rdi
0x180096341  push    r12
0x180096343  push    r13
0x180096345  push    r14
0x180096347  push    r15
0x180096349  lea     rbp, [rsp-0F8h]
0x180096351  sub     rsp, 1F8h
0x180096358  mov     rax, cs:__security_cookie
0x18009635f  xor     rax, rsp
0x180096362  mov     [rbp+130h+var_50], rax
0x180096369  mov     r13, [rbp+130h+arg_20]
0x180096370  mov     r14, rcx
0x180096373  mov     r12, [rbp+130h+arg_28]
0x18009637a  xorps   xmm0, xmm0
0x18009637d  mov     rbx, [rbp+130h+arg_38]
0x180096384  mov     rsi, rdx
0x180096387  mov     [rbp+130h+var_160], rcx
0x18009638b  mov     rdi, r9
0x18009638e  xor     ecx, ecx
0x180096390  mov     [rbp+130h+var_158], rdx
0x180096394  mov     [rbp+130h+var_1B0], cl
0x180096397  lea     rdx, [rsp+230h+var_1C0]
0x18009639c  mov     [rbp+130h+string], rcx
0x1800963a0  mov     r15, r8
0x1800963a3  mov     [rbp+130h+var_1A0], cl
0x1800963a6  mov     [rbp+130h+var_18C], ecx
0x1800963a9  mov     [rbp+130h+var_188], cl
0x1800963ac  mov     [rbp+130h+var_184], ecx
0x1800963af  mov     [rbp+130h+var_180], cl
0x1800963b2  mov     [rbp+130h+var_17C], ecx
0x1800963b5  mov     [rbp+130h+var_178], cl
0x1800963b8  mov     [rbp+130h+var_174], ecx
0x1800963bb  mov     rcx, r14
0x1800963be  mov     [rbp+130h+var_150], r8
0x1800963c2  mov     [rsp+230h+var_1C8], r13
0x1800963c7  mov     [rsp+230h+var_1D0], r12
0x1800963cc  movups  [rsp+230h+var_1C0], xmm0
0x1800963d1  movups  [rbp+130h+var_19C], xmm0
0x1800963d5  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x1800963da  mov     rcx, [rbp+130h+string]; string
0x1800963de  call    cs:__imp_WindowsDeleteString
0x1800963e5  nop     dword ptr [rax+rax+00h]
0x1800963ea  mov     qword ptr [rsi], 0
0x1800963f1  lea     rcx, [rbp+130h+var_F0]; this
0x1800963f5  mov     dword ptr [r15], 0
0x1800963fc  call    ??0PackageListBuffer@@QEAA@XZ; PackageListBuffer::PackageListBuffer(void)
0x180096401  mov     al, [rbp+130h+arg_30]
0x180096407  lea     rcx, [rbp+130h+var_F0]; this
0x18009640b  mov     [rsp+230h+var_208], rbx; PackageFilter *
0x180096410  mov     r9, r12
0x180096413  mov     r8, r13
0x180096416  mov     [rsp+230h+var_210], al; int
0x18009641a  mov     rdx, rdi
0x18009641d  call    ??$GetInstalledPackagesContainingEntry@UComTreatAsClassRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEAVPackageListBuffer@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@@Z; CPackagedComCatalog::GetInstalledPackagesContainingEntry<ComTreatAsClassRegistrationEntryProperties>(PackageListBuffer &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *)
0x180096422  mov     ebx, eax
0x180096424  test    eax, eax
0x180096426  jns     short loc_180096448
0x180096428  mov     rcx, [rbp+138h]; this
0x18009642f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180096436  mov     r9d, eax; char *
0x180096439  mov     edx, 1083h; void *
0x18009643e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096443  jmp     loc_180096894
0x180096448  mov     rax, [rbp+130h+var_68]
0x18009644f  xor     ebx, ebx
0x180096451  test    eax, eax
0x180096453  jnz     short loc_18009645F
0x180096455  mov     ebx, 80070002h
0x18009645a  jmp     loc_180096894
0x18009645f  mov     rcx, [rbp+130h+var_70]
0x180096466  lea     r9, ?MoreRecentlyInstalledByUser@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByUser(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18009646d  mov     edx, eax
0x18009646f  shl     rdx, 5
0x180096473  add     rdx, rcx
0x180096476  mov     r8d, eax
0x180096479  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18009647e  mov     r12b, byte ptr [rsp+230h+var_1D0+7]
0x180096483  xorps   xmm0, xmm0
0x180096486  movzx   r13d, word ptr [rsp+230h+var_1D0+5]
0x18009648c  mov     esi, 1
0x180096491  movups  [rbp+130h+var_19C], xmm0
0x180096495  mov     r15b, bl
0x180096498  mov     [rbp+130h+var_1B0], bl
0x18009649b  mov     [rbp+130h+string], rbx
0x18009649f  mov     [rbp+130h+var_1A0], bl
0x1800964a2  mov     word ptr [rbp+130h+var_18C], bx
0x1800964a6  mov     [rbp+130h+var_188], bl
0x1800964a9  mov     [rbp+130h+var_184], ebx
0x1800964ac  mov     [rbp+130h+var_180], bl
0x1800964af  mov     [rbp+130h+var_17C], ebx
0x1800964b2  mov     [rbp+130h+var_178], bl
0x1800964b5  mov     [rbp+130h+var_174], ebx
0x1800964b8  mov     [rsp+230h+var_1E0], rbx
0x1800964bd  mov     [rsp+230h+var_1EC], bl
0x1800964c1  mov     r10, [rbp+130h+var_70]
0x1800964c8  mov     rdi, r10
0x1800964cb  mov     eax, dword ptr [rbp+130h+var_68]
0x1800964d1  shl     rax, 5
0x1800964d5  add     rax, r10
0x1800964d8  cmp     rdi, rax
0x1800964db  jz      loc_1800967E5
0x1800964e1  mov     edx, esi
0x1800964e3  mov     rcx, rdi
0x1800964e6  call    ?PackageInstalledForScope@@YA_NAEBUPackageIdAndInstallOrders@@W4InstallScope@RegistrationStoreContext@@@Z; PackageInstalledForScope(PackageIdAndInstallOrders const &,RegistrationStoreContext::InstallScope)
0x1800964eb  test    al, al
0x1800964ed  jz      loc_1800966B9
0x1800964f3  mov     r8, [rsp+230h+var_1D0]
0x1800964f8  lea     r9, [rbp+130h+var_140]
0x1800964fc  mov     rdx, [rdi]
0x1800964ff  xor     eax, eax
0x180096501  mov     rcx, [rsp+230h+var_1C8]
0x180096506  xorps   xmm0, xmm0
0x180096509  mov     [rbp+130h+var_10C], ax
0x18009650d  mov     r14d, ebx
0x180096510  lea     rax, [rbp+130h+var_170]
0x180096514  mov     qword ptr [rbp+130h+var_168], rbx
0x180096518  mov     [rsp+230h+var_208], rax
0x18009651d  lea     rax, [rbp+130h+var_168]
0x180096521  mov     qword ptr [rsp+230h+var_210], rax
0x180096526  mov     [rbp+130h+var_170], rbx
0x18009652a  mov     [rsp+230h+var_1D8], ebx
0x18009652e  mov     [rsp+230h+var_1E4], bl
0x180096532  mov     [rbp+130h+var_130], bl
0x180096535  mov     [rbp+130h+var_128], rbx
0x180096539  mov     [rbp+130h+var_120], bl
0x18009653c  movups  [rbp+130h+var_11C], xmm0
0x180096540  mov     [rbp+130h+var_108], bl
0x180096543  mov     [rbp+130h+var_104], ebx
0x180096546  mov     [rbp+130h+var_100], bl
0x180096549  mov     [rbp+130h+var_FC], ebx
0x18009654c  mov     [rbp+130h+var_F8], bl
0x18009654f  mov     [rbp+130h+var_F4], ebx
0x180096552  call    ??_9IPackagedComCatalogContext@@$BII@AA; [thunk]: IPackagedComCatalogContext::`vcall'{136,{flat}}
0x180096557  mov     rcx, [rbp+130h+var_170]
0x18009655b  lea     rdx, [rbp+130h+var_140]
0x18009655f  mov     r9, [rsp+230h+var_1D0]
0x180096564  mov     r8, rdi
0x180096567  mov     [rsp+230h+var_208], rcx
0x18009656c  mov     ebx, eax
0x18009656e  mov     rcx, qword ptr [rbp+130h+var_168]
0x180096572  mov     qword ptr [rsp+230h+var_210], rcx; int
0x180096577  mov     ecx, eax
0x180096579  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComTreatAsClassRegistrationEntryProperties@@AEBVOpaqueString@@AEBU_GUID@@W4ComTreatAsClassRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComTreatAsClassRegistrationEntryProperties const &,OpaqueString const &,_GUID const &,ComTreatAsClassRegistrationEntryPropertyFlags,ComTreatAsClassRegistrationEntryPropertyFlags)
0x18009657e  test    ebx, ebx
0x180096580  js      short loc_1800965E6
0x180096582  lea     rcx, [rbp+130h+var_140]
0x180096586  call    ??$RegistrationHasMachineScope@UComTreatAsClassRegistrationEntryProperties@@@@YA_NAEBUComTreatAsClassRegistrationEntryProperties@@@Z; RegistrationHasMachineScope<ComTreatAsClassRegistrationEntryProperties>(ComTreatAsClassRegistrationEntryProperties const &)
0x18009658b  lea     rcx, [rbp+130h+var_140]
0x18009658f  mov     bl, al
0x180096591  call    ??$RegistrationHasUserScope@UComTreatAsClassRegistrationEntryProperties@@@@YA_NAEBUComTreatAsClassRegistrationEntryProperties@@@Z; RegistrationHasUserScope<ComTreatAsClassRegistrationEntryProperties>(ComTreatAsClassRegistrationEntryProperties const &)
0x180096596  mov     cl, al
0x180096598  mov     r8d, esi
0x18009659b  mov     dl, bl
0x18009659d  call    ?RegistrationScopeMatchesInstallScope@@YA_N_N0W4InstallScope@RegistrationStoreContext@@@Z; RegistrationScopeMatchesInstallScope(bool,bool,RegistrationStoreContext::InstallScope)
0x1800965a2  xor     ebx, ebx
0x1800965a4  test    al, al
0x1800965a6  jz      short loc_180096617
0x1800965a8  lea     rcx, [rbp+130h+var_140]
0x1800965ac  call    ??$RegistrationIsSupportedSyntaxVersion@UComTreatAsClassRegistrationEntryProperties@@@@YA_NAEBUComTreatAsClassRegistrationEntryProperties@@@Z; RegistrationIsSupportedSyntaxVersion<ComTreatAsClassRegistrationEntryProperties>(ComTreatAsClassRegistrationEntryProperties const &)
0x1800965b1  test    al, al
0x1800965b3  jz      short loc_180096617
0x1800965b5  lea     rax, [rsp+230h+var_1E8]
0x1800965ba  mov     r8d, esi
0x1800965bd  mov     [rsp+230h+var_200], rax
0x1800965c2  lea     r9, [rbp+130h+var_140]
0x1800965c6  lea     rax, [rsp+230h+var_1D8]
0x1800965cb  mov     rdx, rdi
0x1800965ce  lea     rcx, [rbp+130h+arg_40]
0x1800965d5  mov     [rsp+230h+var_208], rax
0x1800965da  call    ??RCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU2@PEA_N@Z@Z@QEAAJ789V?$optional@H@std@@PEAW4RegistrationApplicability@1@PEAV?$optional@H@std@@@Z; `CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability::operator()(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,std::optional<int>,CPackagedComCatalog::RegistrationApplicability *,std::optional<int> *)
0x1800965df  mov     r14d, [rsp+230h+var_1D8]
0x1800965e4  mov     ebx, eax
0x1800965e6  cmp     ebx, 80070002h
0x1800965ec  jz      loc_18009669D
0x1800965f2  lea     eax, [rbx+7FFBFEADh]
0x1800965f8  cmp     eax, 1
0x1800965fb  jbe     loc_18009669D
0x180096601  cmp     ebx, 8007000Dh
0x180096607  jz      loc_18009669D
0x18009660d  test    ebx, ebx
0x18009660f  js      loc_18009681B
0x180096615  xor     ebx, ebx
0x180096617  cmp     r14d, 2
0x18009661b  jz      loc_180096736
0x180096621  cmp     r14d, 1
0x180096625  jnz     short loc_1800966A0
0x180096627  cmp     [rsp+230h+var_1E4], bl
0x18009662b  mov     rcx, [rbp+138h]; this
0x180096632  setz    al
0x180096635  test    al, al
0x180096637  jnz     loc_180096724
0x18009663d  cmp     [rsp+230h+var_1EC], bl
0x180096641  jz      short loc_180096660
0x180096643  lea     rcx, [rsp+230h+var_1E8]
0x180096648  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18009664d  lea     rcx, [rsp+230h+var_1F0]
0x180096652  mov     rbx, rax
0x180096655  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x18009665a  mov     ecx, [rbx]
0x18009665c  cmp     [rax], ecx
0x18009665e  jge     short loc_1800966A0
0x180096660  lea     rdx, [rbp+130h+var_140]
0x180096664  lea     rcx, [rsp+230h+var_1C0]
0x180096669  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x18009666e  mov     rdx, rdi
0x180096671  lea     rcx, [rsp+230h+var_1E0]
0x180096676  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x18009667b  lea     rcx, [rsp+230h+var_1E8]
0x180096680  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x180096685  mov     ecx, [rax]
0x180096687  mov     [rsp+230h+var_1F0], ecx
0x18009668b  mov     [rsp+230h+var_1EC], 1
0x180096690  mov     [rsp+230h+var_1EB], r13w
0x180096696  mov     [rsp+230h+var_1E9], r12b
0x18009669b  jmp     short loc_1800966A0
0x18009669d  mov     r15b, 1
0x1800966a0  mov     rcx, [rbp+130h+var_128]; string
0x1800966a4  call    cs:__imp_WindowsDeleteString
0x1800966ab  nop     dword ptr [rax+rax+00h]
0x1800966b0  mov     r10, [rbp+130h+var_70]
0x1800966b7  xor     ebx, ebx
0x1800966b9  mov     edx, dword ptr [rbp+130h+var_68]
0x1800966bf  add     rdi, 20h ; ' '
0x1800966c3  shl     rdx, 5
0x1800966c7  add     rdx, r10
0x1800966ca  cmp     rdi, rdx
0x1800966cd  jnz     loc_1800964CB
0x1800966d3  cmp     esi, 1
0x1800966d6  jnz     short loc_1800966FB
0x1800966d8  mov     r8, rdx
0x1800966db  lea     r9, ?MoreRecentlyInstalledByOneTime@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByOneTime(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x1800966e2  sub     r8, r10
0x1800966e5  mov     rcx, r10
0x1800966e8  sar     r8, 5
0x1800966ec  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x1800966f1  mov     esi, 2
0x1800966f6  jmp     loc_1800964C1
0x1800966fb  cmp     esi, 2
0x1800966fe  jnz     loc_1800964CB
0x180096704  mov     r8, rdx
0x180096707  lea     r9, ?MoreRecentlyInstalledByMachine@@YA_NAEBUPackageIdAndInstallOrders@@0@Z; MoreRecentlyInstalledByMachine(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)
0x18009670e  sub     r8, r10
0x180096711  mov     rcx, r10
0x180096714  sar     r8, 5
0x180096718  call    ??$_Sort_unchecked@PEAUPackageIdAndInstallOrders@@P6A_NAEBU1@0@Z@std@@YAXPEAUPackageIdAndInstallOrders@@0_JP6A_NAEBU1@2@Z@Z; std::_Sort_unchecked<PackageIdAndInstallOrders *,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &)>(PackageIdAndInstallOrders *,PackageIdAndInstallOrders *,__int64,bool (*)(PackageIdAndInstallOrders const &,PackageIdAndInstallOrders const &))
0x18009671d  mov     esi, ebx
0x18009671f  jmp     loc_1800964C1
0x180096724  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18009672b  mov     edx, 10EFh; void *
0x180096730  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180096736  cmp     [rsp+230h+var_1E4], bl
0x18009673a  jnz     short loc_180096755
0x18009673c  mov     rcx, [rbp+138h]; this
0x180096743  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18009674a  mov     edx, 10E0h; void *
0x18009674f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180096755  cmp     [rsp+230h+var_1EC], bl
0x180096759  jz      short loc_180096793
0x18009675b  lea     rcx, [rsp+230h+var_1E8]
0x180096760  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x180096765  lea     rcx, [rsp+230h+var_1F0]
0x18009676a  mov     rbx, rax
0x18009676d  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x180096772  mov     ecx, [rbx]
0x180096774  cmp     [rax], ecx
0x180096776  jl      short loc_180096791
0x180096778  mov     rcx, [rbp+138h]; this
0x18009677f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180096786  mov     edx, 10E4h; void *
0x18009678b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180096791  xor     ebx, ebx
0x180096793  lea     rdx, [rbp+130h+var_140]
0x180096797  lea     rcx, [rsp+230h+var_1C0]
0x18009679c  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x1800967a1  mov     rdx, rdi
0x1800967a4  lea     rcx, [rsp+230h+var_1E0]
0x1800967a9  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800967ae  lea     rcx, [rsp+230h+var_1E8]
0x1800967b3  call    ?value@?$optional@H@std@@QEGAAAEAHXZ; std::optional<int>::value(void)
0x1800967b8  mov     ecx, [rax]
0x1800967ba  movzx   eax, word ptr [rsp+230h+var_1C8+5]
0x1800967bf  mov     [rsp+230h+var_1EB], ax
0x1800967c4  mov     al, byte ptr [rsp+230h+var_1C8+7]
0x1800967c8  mov     [rsp+230h+var_1F0], ecx
0x1800967cc  mov     rcx, [rbp+130h+var_128]; string
0x1800967d0  mov     [rsp+230h+var_1E9], al
0x1800967d4  mov     [rsp+230h+var_1EC], 1
0x1800967d9  call    cs:__imp_WindowsDeleteString
0x1800967e0  nop     dword ptr [rax+rax+00h]
0x1800967e5  cmp     [rsp+230h+var_1EC], bl
0x1800967e9  jz      short loc_180096869
0x1800967eb  mov     rcx, [rbp+130h+var_160]
0x1800967ef  lea     rdx, [rsp+230h+var_1C0]
0x1800967f4  call    ??4ComTreatAsClassRegistrationEntryProperties@@QEAAAEAU0@$$QEAU0@@Z; ComTreatAsClassRegistrationEntryProperties::operator=(ComTreatAsClassRegistrationEntryProperties &&)
0x1800967f9  mov     rcx, [rbp+130h+var_158]
0x1800967fd  mov     rax, [rsp+230h+var_1E0]
0x180096802  mov     [rcx], rax
  ... truncated ...
```
