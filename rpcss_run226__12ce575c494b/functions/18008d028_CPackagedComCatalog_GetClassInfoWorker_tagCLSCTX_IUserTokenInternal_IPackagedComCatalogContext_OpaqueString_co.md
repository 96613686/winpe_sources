# CPackagedComCatalog::GetClassInfoWorker(tagCLSCTX,IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID const &,void * *,ComRegistrationVisibility,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x18008d028`
- end: `0x18008d6e9`
- name: `?GetClassInfoWorker@CPackagedComCatalog@@CAJW4tagCLSCTX@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@45PEAPEAXW4ComRegistrationVisibility@@PEBGIQEBQEAUHSTRING__@@I9@Z`
- size: `1729`
- prototype: `__int64 __fastcall(int, struct IUserTokenInternal *, __int64, const struct OpaqueString *, char, _OWORD *, char, __int64, _QWORD *, int, struct PACKAGE_INFO *, int, __int64, int, HSTRING)`
- caller_count: `5`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ca90`
- `0x1800dc1c0`
- `0x1800dc590`
- `0x1800dc8cc`
- `0x1800dcc50`

## callees

- `0x180005c40`
- `0x18000c278`
- `0x18000e148`
- `0x18000eaf4`
- `0x18000eb10`
- `0x18000eb70`
- `0x18000f874`
- `0x18002ba28`
- `0x1800414d0`
- `0x18004c030`
- `0x18005ed2c`
- `0x18007cbf8`
- `0x180081894`
- `0x18008d028`
- `0x18008d6f0`
- `0x18008dd38`
- `0x18008df18`
- `0x18008e6c4`
- `0x18008e98c`
- `0x18008f610`
- `0x1800933b0`
- `0x180093538`
- `0x1800a1fd4`
- `0x1800b27e0`
- `0x1800d47c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d0ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d4ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d4e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d58d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d68b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d0ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d162`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d25f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d3f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d4ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d4e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d549`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d58d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d68b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008d6b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d37d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008d37d`

## string_xrefs

- `0x18008d1f5`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008d3a3`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18008d43a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetClassInfoWorker(
        int a1,
        struct IUserTokenInternal *a2,
        __int64 a3,
        const struct OpaqueString *a4,
        char a5,
        _OWORD *a6,
        char a7,
        __int64 a8,
        _QWORD *a9,
        int a10,
        struct PACKAGE_INFO *a11,
        int a12,
        __int64 a13,
        int a14,
        HSTRING a15)
{
  char v18; // si
  __int64 v19; // r9
  char v20; // r12
  int TreatAsClassWorker; // ebx
  HSTRING v22; // rdi
  __int128 v23; // xmm6
  int v24; // r9d
  int v25; // eax
  int v26; // esi
  const unsigned __int16 *StringRawBuffer; // rax
  int MainAndRelatedSetOptionalPackagesForMainPackage; // eax
  const char *v30; // r9
  _lambda_384cae988b9b93015a87ed243e331da0_ *v31; // rbx
  _lambda_384cae988b9b93015a87ed243e331da0_ *v32; // rbx
  _lambda_384cae988b9b93015a87ed243e331da0_ *v33; // rbx
  HSTRING v34; // rbx
  HSTRING v35; // r8
  int ClassRegistrationFromProperties; // eax
  int v37; // [rsp+28h] [rbp-F0h]
  HSTRING string; // [rsp+98h] [rbp-80h] BYREF
  HSTRING v39; // [rsp+A0h] [rbp-78h] BYREF
  int v40; // [rsp+A8h] [rbp-70h] BYREF
  int v41; // [rsp+ACh] [rbp-6Ch]
  __int64 v42; // [rsp+B0h] [rbp-68h] BYREF
  int v43; // [rsp+B8h] [rbp-60h]
  HSTRING v44; // [rsp+C0h] [rbp-58h] BYREF
  struct PACKAGE_INFO *v45; // [rsp+C8h] [rbp-50h] BYREF
  unsigned __int64 v46; // [rsp+D0h] [rbp-48h] BYREF
  HSTRING v47[2]; // [rsp+D8h] [rbp-40h] BYREF
  _OWORD v48[2]; // [rsp+E8h] [rbp-30h] BYREF
  _QWORD *v49; // [rsp+108h] [rbp-10h]
  __int64 v50; // [rsp+110h] [rbp-8h]
  _BYTE v51[56]; // [rsp+118h] [rbp+0h] BYREF
  __int64 v52[2]; // [rsp+150h] [rbp+38h] BYREF
  HSTRING newString[2]; // [rsp+168h] [rbp+50h] BYREF
  __int128 v54; // [rsp+178h] [rbp+60h]
  _OWORD v55[2]; // [rsp+188h] [rbp+70h]
  int v56[144]; // [rsp+1A8h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+440h] [rbp+328h]

  v43 = a1;
  *a9 = 0;
  v49 = a9;
  v45 = a11;
  v50 = a13;
  v44 = a15;
  *(_OWORD *)v52 = 0;
  v41 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    v41 = a10;
    WindowsDeleteString(0);
    v18 = a5;
    LOBYTE(v19) = a5;
    v39 = 0;
    v37 = (int)a6;
    v20 = a7;
  }
  else
  {
    WindowsDeleteString(0);
    v20 = a7;
    v18 = a5;
    LOBYTE(v19) = a5;
    v37 = (int)a6;
    v39 = 0;
  }
  TreatAsClassWorker = CPackagedComCatalog::GetTreatAsClassWorker(a2, a3, a4, v19);
  if ( TreatAsClassWorker < 0 )
  {
    if ( (unsigned int)(TreatAsClassWorker + 2147221165) > 1 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF3,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)TreatAsClassWorker,
        v37);
      v22 = v39;
LABEL_15:
      WindowsDeleteString(v22);
      return (unsigned int)TreatAsClassWorker;
    }
    OpaqueString::operator=(&v39, a4);
    *(_OWORD *)v52 = *a6;
  }
  else
  {
    v18 &= wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
  }
  v42 = 0;
  ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v56);
  string = 0;
  v40 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
  {
    newString[0] = (HSTRING)&v42;
    OpaqueString::OpaqueString(&newString[1], a4);
    v22 = v39;
    LODWORD(v54) = v43;
    *((_QWORD *)&v54 + 1) = a2;
    *(_QWORD *)&v55[0] = a3;
    *(_OWORD *)((char *)v55 + 8) = *(_OWORD *)v52;
    if ( v39 )
    {
      if ( v18 )
      {
        v45 = 0;
        v46 = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(v39, 0);
        MainAndRelatedSetOptionalPackagesForMainPackage = GetMainAndRelatedSetOptionalPackagesForMainPackage(
                                                            a2,
                                                            StringRawBuffer,
                                                            &v46,
                                                            &v45);
        TreatAsClassWorker = MainAndRelatedSetOptionalPackagesForMainPackage;
        if ( MainAndRelatedSetOptionalPackagesForMainPackage < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CE4,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (const char *)(unsigned int)MainAndRelatedSetOptionalPackagesForMainPackage,
            v37);
          wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(&v45);
          WindowsDeleteString(newString[1]);
          newString[1] = 0;
          WindowsDeleteString(string);
          string = 0;
          ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v56);
          wil::com_ptr_t<CPackagedComCatalog::CServerRegistration,wil::err_returncode_policy>::~com_ptr_t<CPackagedComCatalog::CServerRegistration,wil::err_returncode_policy>(&v42);
          goto LABEL_15;
        }
        v47[1] = (HSTRING)v45;
        *(_QWORD *)&v48[0] = v46;
        v47[0] = 0;
        *(_OWORD *)((char *)v48 + 8) = 0;
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
          && !*(_QWORD *)&v48[0] )
        {
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xCB,
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            v30);
        }
        v31 = _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(
                (_lambda_384cae988b9b93015a87ed243e331da0_ *)v51,
                (const struct _lambda_384cae988b9b93015a87ed243e331da0_ *)newString);
        WindowsDeleteString(string);
        string = 0;
        v26 = CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(
                (int)v56,
                (int)&string,
                (int)&v40,
                (int)a2,
                a3,
                (__int64)v52,
                v20,
                (PackageFilter *)v47,
                (__int64)v31);
        wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset((char *)v48 + 8);
        wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(&v47[1]);
        WindowsDeleteString(v47[0]);
      }
      else
      {
        PackageFilter::PackageFilter((PackageFilter *)v47, (const struct OpaqueString *)&v39);
        v32 = _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(
                (_lambda_384cae988b9b93015a87ed243e331da0_ *)v51,
                (const struct _lambda_384cae988b9b93015a87ed243e331da0_ *)newString);
        WindowsDeleteString(string);
        string = 0;
        v26 = CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(
                (int)v56,
                (int)&string,
                (int)&v40,
                (int)a2,
                a3,
                (__int64)v52,
                v20,
                (PackageFilter *)v47,
                (__int64)v32);
        PackageFilter::~PackageFilter((PackageFilter *)v47);
      }
    }
    else
    {
      v33 = _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(
              (_lambda_384cae988b9b93015a87ed243e331da0_ *)v51,
              (const struct _lambda_384cae988b9b93015a87ed243e331da0_ *)newString);
      WindowsDeleteString(string);
      string = 0;
      v26 = CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(
              (int)v56,
              (int)&string,
              (int)&v40,
              (int)a2,
              a3,
              (__int64)v52,
              v20,
              0,
              (__int64)v33);
    }
    WindowsDeleteString(newString[1]);
    goto LABEL_23;
  }
  v23 = *(_OWORD *)v52;
  WindowsDeleteString(string);
  LOBYTE(v47[1]) = v18;
  v47[0] = (HSTRING)&v42;
  *(_WORD *)((char *)&v47[1] + 1) = *(_WORD *)((char *)&newString[1] + 1);
  BYTE3(v47[1]) = BYTE3(newString[1]);
  HIDWORD(v47[1]) = v43;
  *(_QWORD *)&v48[0] = a2;
  *((_QWORD *)&v48[0] + 1) = a3;
  string = 0;
  *(_OWORD *)newString = *(_OWORD *)v47;
  v54 = v48[0];
  v55[0] = v23;
  v25 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookupWithCustomRanking<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_2e64a0868ac250278a4b3c43d8193f88_>(
          (unsigned int)v56,
          (unsigned int)&string,
          (unsigned int)&v40,
          v24,
          v37,
          (__int64)a2,
          a3,
          (__int64)v52,
          (__int64)&v39,
          v18,
          v20,
          v41,
          (__int64)newString,
          (__int64)v45,
          a12,
          v50,
          a14,
          (__int64)v44);
  v22 = v39;
  v26 = v25;
LABEL_23:
  v34 = 0;
  v39 = 0;
  if ( v26 >= 0 )
  {
    if ( v42 )
    {
      OpaqueString::OpaqueString(&v44, (const struct OpaqueString *)(v42 + 48));
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                           (Microsoft::WRL::Wrappers::Details *)v44,
                           string,
                           v35) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      WindowsDeleteString(v44);
      if ( !LOBYTE(v56[0]) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( *(_DWORD *)(v42 + 56) != v56[1] )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    ClassRegistrationFromProperties = CPackagedComCatalog::MakeClassRegistrationFromProperties(
                                        a2,
                                        (struct OpaqueString *)&string,
                                        (struct _GUID *)v52,
                                        (struct ComClassRegistrationEntryProperties *)v56,
                                        (__int64)&v42,
                                        (bool)&v39);
    v34 = v39;
    v26 = ClassRegistrationFromProperties;
  }
  if ( v26 == -2147024894 )
  {
    v26 = -2147221164;
  }
  else if ( v26 == -2147024883 )
  {
    v26 = -2147221165;
  }
  else if ( v26 >= 0 )
  {
    if ( v34 )
    {
      v26 = Microsoft::WRL::Details::RuntimeClassBaseT<2>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IComClassInfoImpl,IClassClassicInfoImpl,IClassClassicInfo2Impl,IClassClassicInfo3Impl,IComClassCategoryInfo,IOleClassInfo,IPackagedComClassProperties,ICacheRefresh,IRegistration>>(
              v34,
              a8,
              v49);
    }
    else
    {
      v26 = 0;
      *v49 = 0;
    }
  }
  if ( v34 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IComClassInfoImpl,IClassClassicInfoImpl,IClassClassicInfo2Impl,IClassClassicInfo3Impl,IComClassCategoryInfo,IOleClassInfo,IPackagedComClassProperties,ICacheRefresh,IRegistration>::Release(v34);
  WindowsDeleteString(string);
  string = 0;
  ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v56);
  if ( v42 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IComProcessInfoImpl<IComProcessInfo3>,IComProcessInfo2,IComProcessInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IProcessServerInfoImpl,ICacheRefresh,IApplicationInfo,IRegistration>::Release();
  WindowsDeleteString(v22);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18008d028  mov     rax, rsp
0x18008d02b  mov     [rax+8], rbx
0x18008d02f  push    rbp
0x18008d030  push    rsi
0x18008d031  push    rdi
0x18008d032  push    r12
0x18008d034  push    r13
0x18008d036  push    r14
0x18008d038  push    r15
0x18008d03a  lea     rbp, [rax-328h]
0x18008d041  sub     rsp, 400h
0x18008d048  movaps  xmmword ptr [rax-48h], xmm6
0x18008d04c  mov     rax, cs:__security_cookie
0x18008d053  xor     rax, rsp
0x18008d056  mov     [rbp+320h+var_50], rax
0x18008d05d  mov     rax, [rbp+320h+arg_40]
0x18008d064  xor     ebx, ebx
0x18008d066  mov     rsi, [rbp+320h+arg_50]
0x18008d06d  xorps   xmm0, xmm0
0x18008d070  mov     r12, [rbp+320h+arg_60]
0x18008d077  mov     rdi, r9
0x18008d07a  mov     r13, [rbp+320h+arg_28]
0x18008d081  mov     r15, r8
0x18008d084  mov     [rbp+320h+var_380], ecx
0x18008d087  mov     r14, rdx
0x18008d08a  mov     rcx, [rbp+320h+arg_70]
0x18008d091  mov     [rax], rbx
0x18008d094  mov     [rbp+320h+var_330], rax
0x18008d098  mov     [rbp+320h+var_370], rsi
0x18008d09c  mov     [rbp+320h+var_328], r12
0x18008d0a0  mov     [rbp+320h+var_378], rcx
0x18008d0a4  movups  xmmword ptr [rbp+320h+var_2E8], xmm0
0x18008d0a8  mov     [rbp+320h+var_38C], ebx
0x18008d0ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d0b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d0b7  xor     ecx, ecx; string
0x18008d0b9  test    al, al
0x18008d0bb  jz      loc_18008D162
0x18008d0c1  mov     ebx, [rbp+320h+arg_48]
0x18008d0c7  mov     [rbp+320h+var_38C], ebx
0x18008d0ca  call    cs:__imp_WindowsDeleteString
0x18008d0d0  mov     rcx, [rbp+320h+var_378]
0x18008d0d4  mov     r8, rdi
0x18008d0d7  mov     al, [rbp+320h+arg_30]
0x18008d0dd  mov     rdx, r15
0x18008d0e0  mov     qword ptr [rsp+430h+var_3B8], rcx
0x18008d0e5  mov     ecx, [rbp+320h+arg_68]
0x18008d0eb  mov     dword ptr [rsp+430h+var_3C0], ecx
0x18008d0ef  mov     ecx, [rbp+320h+arg_58]
0x18008d0f5  mov     qword ptr [rsp+430h+var_3C8], r12
0x18008d0fa  mov     dword ptr [rsp+430h+var_3D0], ecx
0x18008d0fe  lea     rcx, [rbp+320h+var_38C]
0x18008d102  mov     [rsp+430h+var_3D8], rsi
0x18008d107  mov     sil, [rbp+320h+arg_20]
0x18008d10e  mov     [rsp+430h+var_3E0], rcx
0x18008d113  mov     r9b, sil
0x18008d116  lea     rcx, [rbp+320h+arg_30]
0x18008d11d  mov     [rbp+320h+var_398], 0
0x18008d125  mov     [rsp+430h+var_3E8], rcx
0x18008d12a  lea     rcx, [rbp+320h+var_398]
0x18008d12e  mov     dword ptr [rsp+430h+var_3F0], ebx
0x18008d132  mov     [rsp+430h+var_3F8], rcx
0x18008d137  lea     rcx, [rbp+320h+var_2E8]
0x18008d13b  mov     qword ptr [rsp+430h+var_400], rcx
0x18008d140  mov     rcx, r14
0x18008d143  mov     byte ptr [rsp+430h+var_408], al
0x18008d147  mov     [rsp+430h+var_410], r13
0x18008d14c  call    ?GetTreatAsClassWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@3PEAU5@PEAPEAUHSTRING__@@W4ComRegistrationVisibility@@PEA_NPEAW47@PEBGIQEBQEAU6@IQEBQEAU6@@Z; CPackagedComCatalog::GetTreatAsClassWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID *,HSTRING__ * *,ComRegistrationVisibility,bool *,ComRegistrationVisibility *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x18008d151  mov     r12b, [rbp+320h+arg_30]
0x18008d158  mov     ebx, eax
0x18008d15a  mov     eax, [rbp+320h+var_38C]
0x18008d15d  mov     [rbp+320h+var_38C], eax
0x18008d160  jmp     short loc_18008D1CE
0x18008d162  call    cs:__imp_WindowsDeleteString
0x18008d168  mov     r12b, [rbp+320h+arg_30]
0x18008d16f  lea     rax, [rbp+320h+var_398]
0x18008d173  mov     sil, [rbp+320h+arg_20]
0x18008d17a  mov     r8, rdi
0x18008d17d  mov     qword ptr [rsp+430h+var_3B8], rbx
0x18008d182  mov     r9b, sil
0x18008d185  mov     dword ptr [rsp+430h+var_3C0], ebx
0x18008d189  mov     rdx, r15
0x18008d18c  mov     qword ptr [rsp+430h+var_3C8], rbx
0x18008d191  mov     rcx, r14
0x18008d194  mov     dword ptr [rsp+430h+var_3D0], ebx
0x18008d198  mov     [rsp+430h+var_3D8], rbx
0x18008d19d  mov     [rsp+430h+var_3E0], rbx
0x18008d1a2  mov     [rsp+430h+var_3E8], rbx
0x18008d1a7  mov     dword ptr [rsp+430h+var_3F0], ebx
0x18008d1ab  mov     [rsp+430h+var_3F8], rax
0x18008d1b0  lea     rax, [rbp+320h+var_2E8]
0x18008d1b4  mov     qword ptr [rsp+430h+var_400], rax
0x18008d1b9  mov     byte ptr [rsp+430h+var_408], r12b
0x18008d1be  mov     [rsp+430h+var_410], r13; int
0x18008d1c3  mov     [rbp+320h+var_398], rbx
0x18008d1c7  call    ?GetTreatAsClassWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@3PEAU5@PEAPEAUHSTRING__@@W4ComRegistrationVisibility@@PEA_NPEAW47@PEBGIQEBQEAU6@IQEBQEAU6@@Z; CPackagedComCatalog::GetTreatAsClassWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID *,HSTRING__ * *,ComRegistrationVisibility,bool *,ComRegistrationVisibility *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x18008d1cc  mov     ebx, eax
0x18008d1ce  test    ebx, ebx
0x18008d1d0  js      short loc_18008D1E3
0x18008d1d2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d1d9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d1de  and     sil, al
0x18008d1e1  jmp     short loc_18008D228
0x18008d1e3  lea     eax, [rbx+7FFBFEADh]
0x18008d1e9  cmp     eax, 1
0x18008d1ec  jbe     short loc_18008D212
0x18008d1ee  mov     rcx, [rbp+328h]; this
0x18008d1f5  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008d1fc  mov     r9d, ebx; char *
0x18008d1ff  mov     edx, 1BF3h; void *
0x18008d204  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d209  mov     rdi, [rbp+320h+var_398]
0x18008d20d  jmp     loc_18008D3F1
0x18008d212  mov     rdx, rdi
0x18008d215  lea     rcx, [rbp+320h+var_398]
0x18008d219  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x18008d21e  movups  xmm0, xmmword ptr [r13+0]
0x18008d223  movdqu  xmmword ptr [rbp+320h+var_2E8], xmm0
0x18008d228  xor     r13d, r13d
0x18008d22b  lea     rcx, [rbp+320h+var_290]; this
0x18008d232  mov     [rbp+320h+var_388], r13
0x18008d236  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x18008d23b  mov     [rbp+320h+string], r13
0x18008d23f  mov     [rbp+320h+var_390], r13d
0x18008d243  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d24a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d24f  test    al, al
0x18008d251  jz      loc_18008D32F
0x18008d257  mov     rcx, [rbp+320h+string]; string
0x18008d25b  movups  xmm6, xmmword ptr [rbp+320h+var_2E8]
0x18008d25f  call    cs:__imp_WindowsDeleteString
0x18008d265  lea     rax, [rbp+320h+var_388]
0x18008d269  mov     byte ptr [rbp+320h+var_360+8], sil
0x18008d26d  mov     [rbp+320h+var_360], rax
0x18008d271  lea     r8, [rbp+320h+var_390]
0x18008d275  movzx   eax, word ptr [rbp+320h+newString+9]
0x18008d279  lea     rdx, [rbp+320h+string]
0x18008d27d  mov     word ptr [rbp+320h+var_360+9], ax
0x18008d281  lea     rcx, [rbp+320h+var_290]
0x18008d288  mov     al, byte ptr [rbp+320h+newString+0Bh]
0x18008d28b  mov     byte ptr [rbp+320h+var_360+0Bh], al
0x18008d28e  mov     eax, [rbp+320h+var_380]
0x18008d291  mov     dword ptr [rbp+320h+var_360+0Ch], eax
0x18008d294  mov     rax, [rbp+320h+var_378]
0x18008d298  movaps  xmm0, xmmword ptr [rbp+320h+var_360]
0x18008d29c  mov     [rsp+430h+var_3A8], rax
0x18008d2a4  mov     eax, [rbp+320h+arg_68]
0x18008d2aa  mov     dword ptr [rsp+430h+var_3B0], eax
0x18008d2b1  mov     rax, [rbp+320h+var_328]
0x18008d2b5  mov     qword ptr [rsp+430h+var_3B8], rax
0x18008d2ba  mov     eax, [rbp+320h+arg_58]
0x18008d2c0  mov     dword ptr [rsp+430h+var_3C0], eax
0x18008d2c4  mov     rax, [rbp+320h+var_370]
0x18008d2c8  mov     qword ptr [rsp+430h+var_3C8], rax
0x18008d2cd  lea     rax, [rbp+320h+newString]
0x18008d2d1  mov     [rsp+430h+var_3D0], rax
0x18008d2d6  mov     eax, [rbp+320h+var_38C]
0x18008d2d9  mov     dword ptr [rsp+430h+var_3D8], eax
0x18008d2dd  lea     rax, [rbp+320h+var_398]
0x18008d2e1  mov     byte ptr [rsp+430h+var_3E0], r12b
0x18008d2e6  mov     byte ptr [rsp+430h+var_3E8], sil
0x18008d2eb  mov     [rsp+430h+var_3F0], rax
0x18008d2f0  lea     rax, [rbp+320h+var_2E8]
0x18008d2f4  mov     [rsp+430h+var_3F8], rax
0x18008d2f9  mov     qword ptr [rbp+320h+var_350], r14
0x18008d2fd  mov     qword ptr [rbp+320h+var_350+8], r15
0x18008d301  movaps  xmm1, xmmword ptr [rbp+320h+var_350]
0x18008d305  mov     qword ptr [rsp+430h+var_400], r15
0x18008d30a  mov     [rsp+430h+var_408], r14
0x18008d30f  mov     [rbp+320h+string], r13
0x18008d313  movaps  xmmword ptr [rbp+320h+newString], xmm0
0x18008d317  movaps  [rbp+320h+var_2C0], xmm1
0x18008d31b  movaps  xmmword ptr [rbp+320h+var_2B0], xmm6
0x18008d31f  call    ??$DoPackageAwareLookupWithCustomRanking@UComClassRegistrationEntryProperties@@VEffectiveClsctxRanking@CPackagedComCatalog@@V_lambda_2e64a0868ac250278a4b3c43d8193f88_@@@EntryLookup@CPackagedComCatalog@@SAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@AEAVEffectiveClsctxRanking@1@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N9W45@V_lambda_2e64a0868ac250278a4b3c43d8193f88_@@PEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookupWithCustomRanking<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_2e64a0868ac250278a4b3c43d8193f88_>(ComClassRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::EffectiveClsctxRanking &,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,_lambda_2e64a0868ac250278a4b3c43d8193f88_,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x18008d324  mov     rdi, [rbp+320h+var_398]
0x18008d328  mov     esi, eax
0x18008d32a  jmp     loc_18008D593
0x18008d32f  lea     rax, [rbp+320h+var_388]
0x18008d333  mov     rdx, rdi; struct OpaqueString *
0x18008d336  lea     rcx, [rbp+320h+newString+8]; newString
0x18008d33a  mov     [rbp+320h+newString], rax
0x18008d33e  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x18008d343  movups  xmm0, xmmword ptr [rbp+320h+var_2E8]
0x18008d347  mov     rdi, [rbp+320h+var_398]
0x18008d34b  mov     eax, [rbp+320h+var_380]
0x18008d34e  mov     dword ptr [rbp+320h+var_2C0], eax
0x18008d351  mov     qword ptr [rbp+320h+var_2C0+8], r14
0x18008d355  mov     qword ptr [rbp+320h+var_2B0], r15
0x18008d359  movdqu  xmmword ptr [rbp+320h+var_2B0+8], xmm0
0x18008d35e  test    rdi, rdi
0x18008d361  jz      loc_18008D535
0x18008d367  test    sil, sil
0x18008d36a  jz      loc_18008D4C5
0x18008d370  xor     edx, edx; length
0x18008d372  mov     [rbp+320h+var_370], r13
0x18008d376  mov     rcx, rdi; string
0x18008d379  mov     [rbp+320h+var_368], r13
0x18008d37d  call    cs:__imp_WindowsGetStringRawBuffer
0x18008d383  lea     r9, [rbp+320h+var_370]; struct PACKAGE_INFO **
0x18008d387  mov     rcx, r14; struct IUserTokenInternal *
0x18008d38a  mov     rdx, rax; unsigned __int16 *
0x18008d38d  lea     r8, [rbp+320h+var_368]; unsigned __int64 *
0x18008d391  call    ?GetMainAndRelatedSetOptionalPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGPEA_KPEAPEAUPACKAGE_INFO@@@Z; GetMainAndRelatedSetOptionalPackagesForMainPackage(IUserTokenInternal *,ushort const *,unsigned __int64 *,PACKAGE_INFO * *)
0x18008d396  mov     ebx, eax
0x18008d398  test    eax, eax
0x18008d39a  jns     short loc_18008D401
0x18008d39c  mov     rcx, [rbp+328h]; this
0x18008d3a3  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008d3aa  mov     r9d, eax; char *
0x18008d3ad  mov     edx, 1CE4h; void *
0x18008d3b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008d3b7  lea     rcx, [rbp+320h+var_370]
0x18008d3bb  call    ?reset@?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x18008d3c0  mov     rcx, [rbp+320h+newString+8]; string
0x18008d3c4  call    cs:__imp_WindowsDeleteString
0x18008d3ca  mov     rcx, [rbp+320h+string]; string
0x18008d3ce  mov     [rbp+320h+newString+8], r13
0x18008d3d2  call    cs:__imp_WindowsDeleteString
0x18008d3d8  lea     rcx, [rbp+320h+var_290]; this
0x18008d3df  mov     [rbp+320h+string], r13
0x18008d3e3  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x18008d3e8  lea     rcx, [rbp+320h+var_388]
0x18008d3ec  call    ??1?$com_ptr_t@VCServerRegistration@CPackagedComCatalog@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CPackagedComCatalog::CServerRegistration,wil::err_returncode_policy>::~com_ptr_t<CPackagedComCatalog::CServerRegistration,wil::err_returncode_policy>(void)
0x18008d3f1  mov     rcx, rdi; string
0x18008d3f4  call    cs:__imp_WindowsDeleteString
0x18008d3fa  mov     eax, ebx
0x18008d3fc  jmp     loc_18008D6BA
0x18008d401  mov     rax, [rbp+320h+var_370]
0x18008d405  xorps   xmm0, xmm0
0x18008d408  mov     [rbp+320h+var_360+8], rax
0x18008d40c  mov     rax, [rbp+320h+var_368]
0x18008d410  mov     qword ptr [rbp+320h+var_350], rax
0x18008d414  mov     [rbp+320h+var_360], r13
0x18008d418  movdqu  xmmword ptr [rbp+320h+var_350+8], xmm0
0x18008d41d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x18008d424  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18008d429  test    al, al
0x18008d42b  jnz     short loc_18008D44C
0x18008d42d  cmp     qword ptr [rbp+320h+var_350], r13
0x18008d431  jnz     short loc_18008D44C
0x18008d433  mov     rcx, [rbp+328h]; this
0x18008d43a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18008d441  mov     edx, 0CBh; void *
0x18008d446  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18008d44c  lea     rdx, [rbp+320h+newString]; struct _lambda_384cae988b9b93015a87ed243e331da0_ *
0x18008d450  lea     rcx, [rbp+320h+var_320]; this
0x18008d454  call    ??0_lambda_384cae988b9b93015a87ed243e331da0_@@QEAA@AEBV0@@Z; _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(_lambda_384cae988b9b93015a87ed243e331da0_ const &)
0x18008d459  mov     rcx, [rbp+320h+string]; string
0x18008d45d  mov     rbx, rax
0x18008d460  call    cs:__imp_WindowsDeleteString
0x18008d466  mov     [rsp+430h+var_3F0], rbx; __int64
0x18008d46b  lea     rax, [rbp+320h+var_360]
0x18008d46f  mov     [rsp+430h+var_3F8], rax; PackageFilter *
0x18008d474  lea     r8, [rbp+320h+var_390]; int
0x18008d478  lea     rax, [rbp+320h+var_2E8]
0x18008d47c  mov     [rsp+430h+var_400], r12b; char
0x18008d481  mov     [rsp+430h+var_408], rax; __int64
0x18008d486  lea     rdx, [rbp+320h+string]; int
0x18008d48a  mov     r9, r14; int
0x18008d48d  mov     [rsp+430h+var_410], r15; __int64
0x18008d492  lea     rcx, [rbp+320h+var_290]; int
0x18008d499  mov     [rbp+320h+string], r13
0x18008d49d  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComClassRegistrationEntryProperties@@VEffectiveClsctxRanking@CPackagedComCatalog@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@CPackagedComCatalog@@CAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAVEffectiveClsctxRanking@0@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(ComClassRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::EffectiveClsctxRanking *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_384cae988b9b93015a87ed243e331da0_)
0x18008d4a2  lea     rcx, [rbp+320h+var_350+8]
0x18008d4a6  mov     esi, eax
0x18008d4a8  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x18008d4ad  lea     rcx, [rbp+320h+var_360+8]
0x18008d4b1  call    ?reset@?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x18008d4b6  mov     rcx, [rbp+320h+var_360]; string
0x18008d4ba  call    cs:__imp_WindowsDeleteString
0x18008d4c0  jmp     loc_18008D589
0x18008d4c5  lea     rdx, [rbp+320h+var_398]; struct OpaqueString *
0x18008d4c9  lea     rcx, [rbp+320h+var_360]; this
0x18008d4cd  call    ??0PackageFilter@@QEAA@AEBVOpaqueString@@@Z; PackageFilter::PackageFilter(OpaqueString const &)
0x18008d4d2  lea     rdx, [rbp+320h+newString]; struct _lambda_384cae988b9b93015a87ed243e331da0_ *
0x18008d4d6  lea     rcx, [rbp+320h+var_320]; this
0x18008d4da  call    ??0_lambda_384cae988b9b93015a87ed243e331da0_@@QEAA@AEBV0@@Z; _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(_lambda_384cae988b9b93015a87ed243e331da0_ const &)
0x18008d4df  mov     rcx, [rbp+320h+string]; string
0x18008d4e3  mov     rbx, rax
0x18008d4e6  call    cs:__imp_WindowsDeleteString
0x18008d4ec  mov     [rsp+430h+var_3F0], rbx; __int64
0x18008d4f1  lea     rax, [rbp+320h+var_360]
0x18008d4f5  mov     [rsp+430h+var_3F8], rax; PackageFilter *
0x18008d4fa  lea     r8, [rbp+320h+var_390]; int
0x18008d4fe  lea     rax, [rbp+320h+var_2E8]
0x18008d502  mov     [rsp+430h+var_400], r12b; char
0x18008d507  mov     [rsp+430h+var_408], rax; __int64
0x18008d50c  lea     rdx, [rbp+320h+string]; int
0x18008d510  mov     r9, r14; int
0x18008d513  mov     [rsp+430h+var_410], r15; __int64
0x18008d518  lea     rcx, [rbp+320h+var_290]; int
0x18008d51f  mov     [rbp+320h+string], r13
0x18008d523  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComClassRegistrationEntryProperties@@VEffectiveClsctxRanking@CPackagedComCatalog@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@CPackagedComCatalog@@CAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAVEffectiveClsctxRanking@0@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(ComClassRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::EffectiveClsctxRanking *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_384cae988b9b93015a87ed243e331da0_)
0x18008d528  lea     rcx, [rbp+320h+var_360]; this
0x18008d52c  mov     esi, eax
0x18008d52e  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x18008d533  jmp     short loc_18008D589
0x18008d535  lea     rdx, [rbp+320h+newString]; struct _lambda_384cae988b9b93015a87ed243e331da0_ *
0x18008d539  lea     rcx, [rbp+320h+var_320]; this
0x18008d53d  call    ??0_lambda_384cae988b9b93015a87ed243e331da0_@@QEAA@AEBV0@@Z; _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(_lambda_384cae988b9b93015a87ed243e331da0_ const &)
  ... truncated ...
```
