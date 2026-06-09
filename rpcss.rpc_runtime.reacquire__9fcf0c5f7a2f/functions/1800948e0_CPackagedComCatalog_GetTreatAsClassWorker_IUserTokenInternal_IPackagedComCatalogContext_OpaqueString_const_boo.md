# CPackagedComCatalog::GetTreatAsClassWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID *,HSTRING__ * *,ComRegistrationVisibility,bool *,ComRegistrationVisibility *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x1800948e0`
- end: `0x180094f76`
- name: `?GetTreatAsClassWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@3PEAU5@PEAPEAUHSTRING__@@W4ComRegistrationVisibility@@PEA_NPEAW47@PEBGIQEBQEAU6@IQEBQEAU6@@Z`
- size: `1686`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800941bc`
- `0x1800e6ff0`

## callees

- `0x1800065a4`
- `0x180012e10`
- `0x18001a374`
- `0x18001c624`
- `0x1800210f8`
- `0x180034260`
- `0x180081400`
- `0x180085b3c`
- `0x1800948e0`
- `0x180095c0c`
- `0x1800962a8`
- `0x18009633c`
- `0x1800968fc`
- `0x18009846c`
- `0x1800989a0`
- `0x180098b34`
- `0x1800a74d0`
- `0x1800b7ac0`
- `0x1800dacec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094ddb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180094ddb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094bab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094d9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094a0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094bab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094c64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094cb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094d9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094deb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094e77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094e89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094f24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094b39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094b39`

## string_xrefs

- `0x180094db5`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180094e4a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180094f64`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x180094e51`: `While resolving CLSID %ws, exceeded maximum TreatAs hops %d`
- `0x180094e3e`: `CPackagedComCatalog::GetTreatAsClassWorker`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetTreatAsClassWorker(
        struct IUserTokenInternal *a1,
        __int64 a2,
        const struct OpaqueString *a3,
        char a4,
        struct _GUID *a5,
        char a6,
        struct _GUID *a7,
        HSTRING *a8,
        int a9,
        char *a10,
        _DWORD *a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16)
{
  char v16; // bl
  char v18; // r14
  int v19; // esi
  int v20; // r15d
  int v21; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int MainAndRelatedSetOptionalPackagesForMainPackage; // eax
  int v24; // ebx
  unsigned __int64 v25; // rbx
  const char *v26; // r9
  __int64 v27; // rcx
  __int64 v28; // rcx
  CGuidStr *v29; // rax
  int v30; // edx
  int v31; // r8d
  int v32; // r9d
  CGuidStr *v33; // rax
  int *v35; // [rsp+20h] [rbp-100h]
  PackageFilter *v36; // [rsp+38h] [rbp-E8h]
  char v37; // [rsp+A0h] [rbp-80h]
  char v38; // [rsp+A1h] [rbp-7Fh]
  HSTRING string; // [rsp+A8h] [rbp-78h] BYREF
  int v40; // [rsp+B0h] [rbp-70h] BYREF
  int v41; // [rsp+B4h] [rbp-6Ch]
  __int64 v42; // [rsp+B8h] [rbp-68h]
  LPVOID lpMem; // [rsp+C0h] [rbp-60h] BYREF
  unsigned __int64 v44; // [rsp+C8h] [rbp-58h] BYREF
  void **v45; // [rsp+D0h] [rbp-50h] BYREF
  struct _GUID *v46; // [rsp+D8h] [rbp-48h]
  _QWORD v47[4]; // [rsp+E0h] [rbp-40h] BYREF
  void **v48; // [rsp+100h] [rbp-20h] BYREF
  struct _GUID *v49; // [rsp+108h] [rbp-18h]
  char *v50; // [rsp+110h] [rbp-10h]
  _DWORD *v51; // [rsp+118h] [rbp-8h]
  void **v52; // [rsp+120h] [rbp+0h]
  _QWORD *v53; // [rsp+128h] [rbp+8h]
  void ***v54; // [rsp+130h] [rbp+10h]
  struct _GUID *v55; // [rsp+138h] [rbp+18h]
  struct _GUID v56; // [rsp+140h] [rbp+20h] BYREF
  int v57[4]; // [rsp+150h] [rbp+30h] BYREF
  char v58; // [rsp+160h] [rbp+40h]
  HSTRING v59; // [rsp+168h] [rbp+48h]
  char v60; // [rsp+170h] [rbp+50h]
  __int128 v61; // [rsp+174h] [rbp+54h]
  __int16 v62; // [rsp+184h] [rbp+64h]
  char v63; // [rsp+188h] [rbp+68h]
  int v64; // [rsp+18Ch] [rbp+6Ch]
  char v65; // [rsp+190h] [rbp+70h]
  int v66; // [rsp+194h] [rbp+74h]
  char v67; // [rsp+198h] [rbp+78h]
  int v68; // [rsp+19Ch] [rbp+7Ch]
  HSTRING v69; // [rsp+1A0h] [rbp+80h] BYREF
  _QWORD v70[2]; // [rsp+1A8h] [rbp+88h] BYREF
  __int128 v71[3]; // [rsp+1B8h] [rbp+98h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+118h]

  v16 = a4;
  v49 = a7;
  v50 = a10;
  v51 = a11;
  v47[3] = a12;
  v47[2] = a14;
  v47[1] = a16;
  v38 = a4;
  v42 = a2;
  v46 = a5;
  if ( a8 )
    *a8 = 0;
  OpaqueString::OpaqueString(&string, a3);
  v18 = 0;
  v19 = 0;
  v37 = 0;
  v56 = *a5;
  v41 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    v19 = a9;
    v18 = a6;
    v41 = a9;
    v37 = a6;
  }
  v20 = 0;
  while ( 1 )
  {
    v58 = 0;
    v62 = 0;
    v61 = 0;
    v59 = 0;
    v60 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      WindowsDeleteString(string);
      string = 0;
      v47[0] = CPackagedComCatalog::AlwaysApplicable<ComProgIdRegistrationEntryProperties>;
      v40 = 0;
      v45 = &CPackagedComCatalog::EntryLookup::EntryType<ComTreatAsClassRegistrationEntryProperties>::`vftable';
      v48 = &CPackagedComCatalog::EntryLookup::RankingType<int>::`vftable';
      v52 = &CPackagedComCatalog::EntryLookup::CheckApplicabilityCallbackFromCheckIfApplicableCallback<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &)>::`vftable';
      v53 = v47;
      v54 = &v45;
      v55 = &v56;
      HIDWORD(v36) = HIDWORD(a1);
      v35 = &v40;
      v21 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookupWithCustomRanking(&v45, &v48, v57, &string);
      v18 = v37;
      v19 = v41;
LABEL_20:
      v24 = v21;
      goto LABEL_21;
    }
    if ( !string )
    {
      WindowsDeleteString(0);
      string = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v28);
      v40 = 0;
      v21 = Z::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
              (int)v57,
              (int)&string,
              (int)&v40,
              (int)a1,
              v42,
              (__int64)&v56,
              a6,
              0,
              (char)CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>);
      goto LABEL_20;
    }
    if ( !v16 )
    {
      PackageFilter::PackageFilter((PackageFilter *)&v69, (const struct OpaqueString *)&string);
      WindowsDeleteString(string);
      string = 0;
      v24 = CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
              (unsigned int)v57,
              (unsigned int)&string,
              (_DWORD)a1,
              v42,
              (__int64)&v56,
              a6,
              (PackageFilter *)&v69);
      PackageFilter::~PackageFilter((PackageFilter *)&v69);
      goto LABEL_21;
    }
    lpMem = 0;
    v44 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    MainAndRelatedSetOptionalPackagesForMainPackage = GetMainAndRelatedSetOptionalPackagesForMainPackage(
                                                        a1,
                                                        StringRawBuffer,
                                                        &v44,
                                                        (struct PACKAGE_INFO **)&lpMem);
    v24 = MainAndRelatedSetOptionalPackagesForMainPackage;
    if ( MainAndRelatedSetOptionalPackagesForMainPackage < 0 )
      break;
    v25 = v44;
    v70[0] = lpMem;
    v70[1] = v44;
    v71[0] = 0;
    v69 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
      && !v25 )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xCB,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        v26);
    }
    WindowsDeleteString(string);
    string = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v27);
    v40 = 0;
    v24 = Z::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
            (int)v57,
            (int)&string,
            (int)&v40,
            (int)a1,
            v42,
            (__int64)&v56,
            a6,
            (PackageFilter *)&v69,
            (char)CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>);
    wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(v71);
    wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(v70);
    WindowsDeleteString(v69);
LABEL_21:
    if ( v24 < 0 )
    {
      WindowsDeleteString(v59);
      if ( v24 == -2147024894 )
      {
        if ( v20 <= 0 )
        {
          v24 = -2147221164;
        }
        else
        {
          v24 = 0;
          *v49 = v56;
        }
      }
      else if ( v24 == -2147024883 )
      {
        v24 = -2147221165;
      }
      goto LABEL_41;
    }
    ++v20;
    v38 &= -((unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) != 0);
    v16 = v38;
    if ( v20 > 50 )
    {
      v24 = -2147221164;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v33 = CGuidStr::CGuidStr((CGuidStr *)&v69, v46);
        LODWORD(v36) = 50;
        LODWORD(v35) = 0;
        ComTraceMessage(
          0xFFFFFFFFLL,
          "onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          "CPackagedComCatalog::GetTreatAsClassWorker",
          7850,
          v35,
          L"While resolving CLSID %ws, exceeded maximum TreatAs hops %d",
          v33,
          v36);
      }
      WindowsDeleteString(v59);
LABEL_41:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
      {
        if ( v24 >= 0 )
        {
          if ( a8 )
          {
            *a8 = string;
            string = 0;
          }
          if ( v50 )
            *v50 = v18;
          if ( v51 )
            *v51 = v19;
        }
      }
      else if ( v24 >= 0 && a8 )
      {
        *a8 = string;
        string = 0;
      }
      goto LABEL_52;
    }
    if ( gfEnableTracing )
    {
      if ( (unsigned __int8)IsWppLevelEnabled(3) )
      {
        v29 = CGuidStr::CGuidStr((CGuidStr *)&v69, &v56);
        ComTraceMessageT<_GUID const *,unsigned short *,_GUID *>(
          (unsigned int)v57,
          v30,
          v31,
          v32,
          (_DWORD)v35,
          (__int64)v46,
          (__int64)v29,
          (__int64)v57);
      }
    }
    v56 = *(struct _GUID *)v57;
    WindowsDeleteString(v59);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E7F,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)MainAndRelatedSetOptionalPackagesForMainPackage,
    (int)v35);
  if ( lpMem )
    HeapFree(g_hHeap, 0, lpMem);
  WindowsDeleteString(v59);
  v59 = 0;
LABEL_52:
  WindowsDeleteString(string);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x1800948e0  mov     [rsp-8+arg_18], rbx
0x1800948e5  push    rbp
0x1800948e6  push    rsi
0x1800948e7  push    rdi
0x1800948e8  push    r12
0x1800948ea  push    r13
0x1800948ec  push    r14
0x1800948ee  push    r15
0x1800948f0  lea     rbp, [rsp-0E0h]
0x1800948f8  sub     rsp, 200h
0x1800948ff  mov     rax, cs:__security_cookie
0x180094906  xor     rax, rsp
0x180094909  mov     [rbp+110h+var_40], rax
0x180094910  mov     rax, [rbp+110h+arg_30]
0x180094917  mov     bl, r9b
0x18009491a  mov     rdi, [rbp+110h+arg_38]
0x180094921  mov     r13, rcx
0x180094924  mov     rsi, [rbp+110h+arg_20]
0x18009492b  mov     [rbp+110h+var_128], rax
0x18009492f  mov     rax, [rbp+110h+arg_48]
0x180094936  mov     [rbp+110h+var_120], rax
0x18009493a  mov     rax, [rbp+110h+arg_50]
0x180094941  mov     [rbp+110h+var_118], rax
0x180094945  mov     rax, [rbp+110h+arg_58]
0x18009494c  mov     [rbp+110h+var_138], rax
0x180094950  mov     rax, [rbp+110h+arg_68]
0x180094957  mov     [rbp+110h+var_140], rax
0x18009495b  mov     rax, [rbp+110h+arg_78]
0x180094962  mov     [rbp+110h+var_148], rax
0x180094966  mov     [rbp+110h+var_18F], bl
0x180094969  mov     [rbp+110h+var_178], rdx
0x18009496d  mov     [rbp+110h+var_158], rsi
0x180094971  test    rdi, rdi
0x180094974  jz      short loc_18009497D
0x180094976  mov     qword ptr [rdi], 0
0x18009497d  mov     rdx, r8; struct OpaqueString *
0x180094980  lea     rcx, [rbp+110h+string]; newString
0x180094984  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x180094989  movups  xmm0, xmmword ptr [rsi]
0x18009498c  xor     r14b, r14b
0x18009498f  xor     esi, esi
0x180094991  mov     [rbp+110h+var_190], r14b
0x180094995  movdqu  xmmword ptr [rbp+110h+var_F0.Data1], xmm0
0x18009499a  mov     [rbp+110h+var_17C], esi
0x18009499d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800949a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800949a9  mov     r12b, [rbp+110h+arg_28]
0x1800949b0  xor     ecx, ecx
0x1800949b2  test    al, al
0x1800949b4  jz      short loc_1800949C6
0x1800949b6  mov     esi, [rbp+110h+arg_40]
0x1800949bc  mov     r14b, r12b
0x1800949bf  mov     [rbp+110h+var_17C], esi
0x1800949c2  mov     [rbp+110h+var_190], r12b
0x1800949c6  mov     r15d, ecx
0x1800949c9  xor     eax, eax
0x1800949cb  mov     [rbp+110h+var_D0], cl
0x1800949ce  xorps   xmm0, xmm0
0x1800949d1  mov     [rbp+110h+var_AC], ax
0x1800949d5  movups  [rbp+110h+var_BC], xmm0
0x1800949d9  mov     [rbp+110h+var_C8], rcx
0x1800949dd  mov     [rbp+110h+var_C0], cl
0x1800949e0  mov     [rbp+110h+var_A8], cl
0x1800949e3  mov     [rbp+110h+var_A4], ecx
0x1800949e6  mov     [rbp+110h+var_A0], cl
0x1800949e9  mov     [rbp+110h+var_9C], ecx
0x1800949ec  mov     [rbp+110h+var_98], cl
0x1800949ef  mov     [rbp+110h+var_94], ecx
0x1800949f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800949f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800949fe  mov     rcx, [rbp+110h+string]; string
0x180094a02  test    al, al
0x180094a04  jz      loc_180094B16
0x180094a0a  call    cs:__imp_WindowsDeleteString
0x180094a11  nop     dword ptr [rax+rax+00h]
0x180094a16  lea     rax, ??$AlwaysApplicable@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBUComProgIdRegistrationEntryProperties@@AEA_N@Z; CPackagedComCatalog::AlwaysApplicable<ComProgIdRegistrationEntryProperties>(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComProgIdRegistrationEntryProperties const &,bool &)
0x180094a1d  mov     [rbp+110h+string], 0
0x180094a25  mov     [rbp+110h+var_150], rax
0x180094a29  lea     r9, [rbp+110h+string]
0x180094a2d  lea     rax, ??_7?$EntryType@UComTreatAsClassRegistrationEntryProperties@@@EntryLookup@CPackagedComCatalog@@6B@; const CPackagedComCatalog::EntryLookup::EntryType<ComTreatAsClassRegistrationEntryProperties>::`vftable'
0x180094a34  mov     [rbp+110h+var_180], 0
0x180094a3b  mov     [rbp+110h+var_160], rax
0x180094a3f  lea     r8, [rbp+110h+var_E0]
0x180094a43  lea     rax, ??_7?$RankingType@H@EntryLookup@CPackagedComCatalog@@6B@; const CPackagedComCatalog::EntryLookup::RankingType<int>::`vftable'
0x180094a4a  mov     [rbp+110h+var_130], rax
0x180094a4e  lea     rdx, [rbp+110h+var_130]
0x180094a52  lea     rax, ??_7?$CheckApplicabilityCallbackFromCheckIfApplicableCallback@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@6B@; const CPackagedComCatalog::EntryLookup::CheckApplicabilityCallbackFromCheckIfApplicableCallback<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &)>::`vftable'
0x180094a59  mov     [rbp+110h+var_110], rax
0x180094a5d  lea     rcx, [rbp+110h+var_160]
0x180094a61  lea     rax, [rbp+110h+var_150]
0x180094a65  mov     [rbp+110h+var_108], rax
0x180094a69  lea     rax, [rbp+110h+var_160]
0x180094a6d  mov     [rbp+110h+var_100], rax
0x180094a71  lea     rax, [rbp+110h+var_F0]
0x180094a75  mov     [rbp+110h+var_F8], rax
0x180094a79  mov     rax, [rbp+110h+var_148]
0x180094a7d  mov     [rsp+230h+var_198], rax
0x180094a85  mov     eax, [rbp+110h+arg_70]
0x180094a8b  mov     [rsp+230h+var_1A0], eax
0x180094a92  mov     rax, [rbp+110h+var_140]
0x180094a96  mov     [rsp+230h+var_1A8], rax
0x180094a9e  mov     eax, [rbp+110h+arg_60]
0x180094aa4  mov     [rsp+230h+var_1B0], eax
0x180094aab  mov     rax, [rbp+110h+var_138]
0x180094aaf  mov     [rsp+230h+var_1B8], rax
0x180094ab4  lea     rax, [rbp+110h+var_110]
0x180094ab8  mov     [rsp+230h+var_1C0], rax
0x180094abd  lea     rax, [rbp+110h+string]
0x180094ac1  mov     [rsp+230h+var_1C8], esi
0x180094ac5  mov     [rsp+230h+var_1D0], r14b
0x180094aca  mov     [rsp+230h+var_1D8], bl
0x180094ace  mov     [rsp+230h+var_1E0], rax
0x180094ad3  lea     rax, [rbp+110h+var_100]
0x180094ad7  mov     [rsp+230h+var_1E8], rax
0x180094adc  mov     rax, [rbp+110h+var_178]
0x180094ae0  mov     qword ptr [rsp+230h+var_1F0], rax
0x180094ae5  lea     rax, [rbp+110h+var_17C]
0x180094ae9  mov     [rsp+230h+var_1F8], r13
0x180094aee  mov     qword ptr [rsp+230h+var_200], rax
0x180094af3  lea     rax, [rbp+110h+var_190]
0x180094af7  mov     [rsp+230h+var_208], rax
0x180094afc  lea     rax, [rbp+110h+var_180]
0x180094b00  mov     [rsp+230h+var_210], rax
0x180094b05  call    ?DoPackageAwareLookupWithCustomRanking@EntryLookup@CPackagedComCatalog@@CAJAEAUIEntryTypeGeneric@12@AEAUIRankingTypeGeneric@12@UEntryPropertiesPointerGeneric@12@PEAPEAUHSTRING__@@URankingPointerGeneric@12@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@UEntryIdGeneric@12@AEBVOpaqueString@@_N_NW48@AEAUICheckApplicabilityCallbackGeneric@12@PEBGIQEBQEAU6@IQEBQEAU6@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookupWithCustomRanking(CPackagedComCatalog::EntryLookup::IEntryTypeGeneric &,CPackagedComCatalog::EntryLookup::IRankingTypeGeneric &,CPackagedComCatalog::EntryLookup::EntryPropertiesPointerGeneric,HSTRING__ * *,CPackagedComCatalog::EntryLookup::RankingPointerGeneric,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,CPackagedComCatalog::EntryLookup::EntryIdGeneric,OpaqueString const &,bool,bool,ComRegistrationVisibility,CPackagedComCatalog::EntryLookup::ICheckApplicabilityCallbackGeneric &,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x180094b0a  mov     r14b, [rbp+110h+var_190]
0x180094b0e  mov     esi, [rbp+110h+var_17C]
0x180094b11  jmp     loc_180094D1C
0x180094b16  test    rcx, rcx
0x180094b19  jz      loc_180094CB6
0x180094b1f  test    bl, bl
0x180094b21  jz      loc_180094C50
0x180094b27  xor     edx, edx; length
0x180094b29  mov     [rbp+110h+lpMem], 0
0x180094b31  mov     [rbp+110h+var_168], 0
0x180094b39  call    cs:__imp_WindowsGetStringRawBuffer
0x180094b40  nop     dword ptr [rax+rax+00h]
0x180094b45  lea     r9, [rbp+110h+lpMem]; struct PACKAGE_INFO **
0x180094b49  mov     rcx, r13; struct IUserTokenInternal *
0x180094b4c  mov     rdx, rax; unsigned __int16 *
0x180094b4f  lea     r8, [rbp+110h+var_168]; unsigned __int64 *
0x180094b53  call    ?GetMainAndRelatedSetOptionalPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGPEA_KPEAPEAUPACKAGE_INFO@@@Z; GetMainAndRelatedSetOptionalPackagesForMainPackage(IUserTokenInternal *,ushort const *,unsigned __int64 *,PACKAGE_INFO * *)
0x180094b58  mov     ebx, eax
0x180094b5a  test    eax, eax
0x180094b5c  js      loc_180094DAE
0x180094b62  mov     rax, [rbp+110h+lpMem]
0x180094b66  xorps   xmm0, xmm0
0x180094b69  mov     rbx, [rbp+110h+var_168]
0x180094b6d  mov     [rbp+110h+var_88], rax
0x180094b74  mov     [rbp+110h+var_80], rbx
0x180094b7b  movdqu  [rbp+110h+var_78], xmm0
0x180094b83  mov     [rbp+110h+var_90], 0
0x180094b8e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180094b95  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180094b9a  test    al, al
0x180094b9c  jnz     short loc_180094BA7
0x180094b9e  test    rbx, rbx
0x180094ba1  jz      loc_180094F5D
0x180094ba7  mov     rcx, [rbp+110h+string]; string
0x180094bab  call    cs:__imp_WindowsDeleteString
0x180094bb2  nop     dword ptr [rax+rax+00h]
0x180094bb7  mov     [rbp+110h+string], 0
0x180094bbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180094bc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180094bcb  test    al, al
0x180094bcd  jz      short loc_180094BD4
0x180094bcf  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180094bd4  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x180094bdb  mov     [rbp+110h+var_180], 0
0x180094be2  mov     qword ptr [rsp+230h+var_1F0], rax; char
0x180094be7  lea     r8, [rbp+110h+var_180]; int
0x180094beb  lea     rax, [rbp+110h+var_90]
0x180094bf2  mov     r9, r13; int
0x180094bf5  mov     [rsp+230h+var_1F8], rax; PackageFilter *
0x180094bfa  lea     rdx, [rbp+110h+string]; int
0x180094bfe  lea     rax, [rbp+110h+var_F0]
0x180094c02  mov     [rsp+230h+var_200], r12b; char
0x180094c07  mov     [rsp+230h+var_208], rax; __int64
0x180094c0c  lea     rcx, [rbp+110h+var_E0]; int
0x180094c10  mov     rax, [rbp+110h+var_178]
0x180094c14  mov     [rsp+230h+var_210], rax; __int64
0x180094c19  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComTreatAsClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x180094c1e  lea     rcx, [rbp+110h+var_78]
0x180094c25  mov     ebx, eax
0x180094c27  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x180094c2c  lea     rcx, [rbp+110h+var_88]
0x180094c33  call    ?reset@?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x180094c38  mov     rcx, [rbp+110h+var_90]; string
0x180094c3f  call    cs:__imp_WindowsDeleteString
0x180094c46  nop     dword ptr [rax+rax+00h]
0x180094c4b  jmp     loc_180094D1E
0x180094c50  lea     rdx, [rbp+110h+string]; struct OpaqueString *
0x180094c54  lea     rcx, [rbp+110h+var_90]; this
0x180094c5b  call    ??0PackageFilter@@QEAA@AEBVOpaqueString@@@Z; PackageFilter::PackageFilter(OpaqueString const &)
0x180094c60  mov     rcx, [rbp+110h+string]; string
0x180094c64  call    cs:__imp_WindowsDeleteString
0x180094c6b  nop     dword ptr [rax+rax+00h]
0x180094c70  mov     r9, [rbp+110h+var_178]
0x180094c74  lea     rax, [rbp+110h+var_90]
0x180094c7b  mov     qword ptr [rsp+230h+var_200], rax
0x180094c80  lea     rdx, [rbp+110h+string]
0x180094c84  lea     rax, [rbp+110h+var_F0]
0x180094c88  mov     byte ptr [rsp+230h+var_208], r12b
0x180094c8d  mov     r8, r13
0x180094c90  mov     [rsp+230h+var_210], rax
0x180094c95  lea     rcx, [rbp+110h+var_E0]
0x180094c99  mov     [rbp+110h+string], 0
0x180094ca1  call    ??$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))
0x180094ca6  lea     rcx, [rbp+110h+var_90]; this
0x180094cad  mov     ebx, eax
0x180094caf  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x180094cb4  jmp     short loc_180094D1E
0x180094cb6  call    cs:__imp_WindowsDeleteString
0x180094cbd  nop     dword ptr [rax+rax+00h]
0x180094cc2  xor     ebx, ebx
0x180094cc4  mov     [rbp+110h+string], rbx
0x180094cc8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180094ccf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180094cd4  test    al, al
0x180094cd6  jz      short loc_180094CDD
0x180094cd8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180094cdd  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x180094ce4  mov     [rbp+110h+var_180], ebx
0x180094ce7  mov     qword ptr [rsp+230h+var_1F0], rax; char
0x180094cec  lea     r8, [rbp+110h+var_180]; int
0x180094cf0  mov     [rsp+230h+var_1F8], rbx; PackageFilter *
0x180094cf5  lea     rax, [rbp+110h+var_F0]
0x180094cf9  mov     [rsp+230h+var_200], r12b; char
0x180094cfe  lea     rdx, [rbp+110h+string]; int
0x180094d02  mov     [rsp+230h+var_208], rax; __int64
0x180094d07  lea     rcx, [rbp+110h+var_E0]; int
0x180094d0b  mov     rax, [rbp+110h+var_178]
0x180094d0f  mov     r9, r13; int
0x180094d12  mov     [rsp+230h+var_210], rax; __int64
0x180094d17  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComTreatAsClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComTreatAsClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x180094d1c  mov     ebx, eax
0x180094d1e  test    ebx, ebx
0x180094d20  js      loc_180094E85
0x180094d26  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180094d2d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180094d32  neg     al
0x180094d34  sbb     cl, cl
0x180094d36  inc     r15d
0x180094d39  and     cl, [rbp+110h+var_18F]
0x180094d3c  mov     [rbp+110h+var_18F], cl
0x180094d3f  mov     bl, cl
0x180094d41  cmp     r15d, 32h ; '2'
0x180094d45  jg      loc_180094E04
0x180094d4b  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x180094d52  jz      short loc_180094D8E
0x180094d54  mov     ecx, 3
0x180094d59  call    IsWppLevelEnabled
0x180094d5e  test    al, al
0x180094d60  jz      short loc_180094D8E
0x180094d62  lea     rdx, [rbp+110h+var_F0]; struct _GUID *
0x180094d66  lea     rcx, [rbp+110h+var_90]; this
0x180094d6d  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180094d72  lea     rcx, [rbp+110h+var_E0]
0x180094d76  mov     [rsp+230h+var_1F8], rcx
0x180094d7b  mov     qword ptr [rsp+230h+var_200], rax
0x180094d80  mov     rax, [rbp+110h+var_158]
0x180094d84  mov     [rsp+230h+var_208], rax
0x180094d89  call    ??$ComTraceMessageT@PEBU_GUID@@PEAGPEAU1@@@YAXPEBD0HW4TraceLevel@@PEBGPEBU_GUID@@PEAGPEAU1@@Z; ComTraceMessageT<_GUID const *,ushort *,_GUID *>(char const *,char const *,int,TraceLevel,ushort const *,_GUID const *,ushort *,_GUID *)
0x180094d8e  movaps  xmm0, xmmword ptr [rbp+110h+var_E0]
0x180094d92  mov     rcx, [rbp+110h+var_C8]; string
0x180094d96  movdqu  xmmword ptr [rbp+110h+var_F0.Data1], xmm0
0x180094d9b  call    cs:__imp_WindowsDeleteString
0x180094da2  nop     dword ptr [rax+rax+00h]
0x180094da7  xor     ecx, ecx
0x180094da9  jmp     loc_1800949C9
0x180094dae  mov     rcx, [rbp+118h]; this
0x180094db5  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180094dbc  mov     r9d, eax; char *
0x180094dbf  mov     edx, 1E7Fh; void *
0x180094dc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094dc9  mov     r8, [rbp+110h+lpMem]; lpMem
0x180094dcd  test    r8, r8
0x180094dd0  jz      short loc_180094DE7
0x180094dd2  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180094dd9  xor     edx, edx; dwFlags
0x180094ddb  call    cs:__imp_HeapFree
0x180094de2  nop     dword ptr [rax+rax+00h]
0x180094de7  mov     rcx, [rbp+110h+var_C8]; string
0x180094deb  call    cs:__imp_WindowsDeleteString
0x180094df2  nop     dword ptr [rax+rax+00h]
0x180094df7  mov     [rbp+110h+var_C8], 0
0x180094dff  jmp     loc_180094F20
0x180094e04  mov     eax, cs:dword_1801574B8
0x180094e0a  mov     ebx, 80040154h
0x180094e0f  test    eax, eax
0x180094e11  jnz     short loc_180094E26
0x180094e13  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x180094e19  jz      short loc_180094E73
0x180094e1b  xor     ecx, ecx
0x180094e1d  call    IsWppLevelEnabled
0x180094e22  test    al, al
0x180094e24  jz      short loc_180094E73
0x180094e26  mov     rdx, [rbp+110h+var_158]; struct _GUID *
0x180094e2a  lea     rcx, [rbp+110h+var_90]; this
0x180094e31  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180094e36  mov     dword ptr [rsp+230h+var_1F8], 32h ; '2'
  ... truncated ...
```
