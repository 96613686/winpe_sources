# CPackagedComCatalog::GetClassInfoWorker(tagCLSCTX,IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID const &,void * *,ComRegistrationVisibility,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)

- ea: `0x1800941bc`
- end: `0x1800948d8`
- name: `?GetClassInfoWorker@CPackagedComCatalog@@CAJW4tagCLSCTX@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@45PEAPEAXW4ComRegistrationVisibility@@PEBGIQEBQEAUHSTRING__@@I9@Z`
- size: `1820`
- prototype: `static int __high(enum tagCLSCTX, struct IUserTokenInternal *, struct IPackagedComCatalogContext *, const struct OpaqueString *, bool, const struct _GUID *, bool, const struct _GUID *, void **, enum ComRegistrationVisibility, const unsigned __int16 *, unsigned int, HSTRING *const, unsigned int, HSTRING *const)`
- caller_count: `5`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180061950`
- `0x1800e2ff0`
- `0x1800e33e0`
- `0x1800e3758`
- `0x1800e3b20`

## callees

- `0x1800065a4`
- `0x180011ff8`
- `0x180012e10`
- `0x1800210f8`
- `0x18002610c`
- `0x1800263c8`
- `0x1800263f0`
- `0x180026450`
- `0x18004b0f0`
- `0x180057bc0`
- `0x1800632fc`
- `0x180081400`
- `0x180085b3c`
- `0x1800941bc`
- `0x1800948e0`
- `0x180094f7c`
- `0x18009515c`
- `0x180095934`
- `0x180095c0c`
- `0x1800968fc`
- `0x1800989a0`
- `0x180098b34`
- `0x1800a74d0`
- `0x1800b7ac0`
- `0x1800db1c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009425e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800942fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800943ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800945ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009461e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009467e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800946b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009486d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009489a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009425e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800942fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800943ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094570`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800945ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009461e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009467e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800946b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800947ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009486d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009489a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094523`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094523`

## string_xrefs

- `0x180094395`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x18009454f`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800945f8`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
          ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((HSTRING *)v56);
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
  ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties((HSTRING *)v56);
  if ( v42 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Microsoft::WRL::ChainInterfaces<IComProcessInfoImpl<IComProcessInfo3>,IComProcessInfo2,IComProcessInfo,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IProcessServerInfoImpl,ICacheRefresh,IApplicationInfo,IRegistration>::Release();
  WindowsDeleteString(v22);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x1800941bc  mov     rax, rsp
0x1800941bf  mov     [rax+8], rbx
0x1800941c3  push    rbp
0x1800941c4  push    rsi
0x1800941c5  push    rdi
0x1800941c6  push    r12
0x1800941c8  push    r13
0x1800941ca  push    r14
0x1800941cc  push    r15
0x1800941ce  lea     rbp, [rax-328h]
0x1800941d5  sub     rsp, 400h
0x1800941dc  movaps  xmmword ptr [rax-48h], xmm6
0x1800941e0  mov     rax, cs:__security_cookie
0x1800941e7  xor     rax, rsp
0x1800941ea  mov     [rbp+320h+var_50], rax
0x1800941f1  mov     rax, [rbp+320h+arg_40]
0x1800941f8  xor     ebx, ebx
0x1800941fa  mov     rsi, [rbp+320h+arg_50]
0x180094201  xorps   xmm0, xmm0
0x180094204  mov     r12, [rbp+320h+arg_60]
0x18009420b  mov     rdi, r9
0x18009420e  mov     r13, [rbp+320h+arg_28]
0x180094215  mov     r15, r8
0x180094218  mov     [rbp+320h+var_380], ecx
0x18009421b  mov     r14, rdx
0x18009421e  mov     rcx, [rbp+320h+arg_70]
0x180094225  mov     [rax], rbx
0x180094228  mov     [rbp+320h+var_330], rax
0x18009422c  mov     [rbp+320h+var_370], rsi
0x180094230  mov     [rbp+320h+var_328], r12
0x180094234  mov     [rbp+320h+var_378], rcx
0x180094238  movups  xmmword ptr [rbp+320h+var_2E8], xmm0
0x18009423c  mov     [rbp+320h+var_38C], ebx
0x18009423f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180094246  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18009424b  xor     ecx, ecx; string
0x18009424d  test    al, al
0x18009424f  jz      loc_1800942FC
0x180094255  mov     ebx, [rbp+320h+arg_48]
0x18009425b  mov     [rbp+320h+var_38C], ebx
0x18009425e  call    cs:__imp_WindowsDeleteString
0x180094265  nop     dword ptr [rax+rax+00h]
0x18009426a  mov     rcx, [rbp+320h+var_378]
0x18009426e  mov     r8, rdi
0x180094271  mov     al, [rbp+320h+arg_30]
0x180094277  mov     rdx, r15
0x18009427a  mov     qword ptr [rsp+430h+var_3B8], rcx
0x18009427f  mov     ecx, [rbp+320h+arg_68]
0x180094285  mov     dword ptr [rsp+430h+var_3C0], ecx
0x180094289  mov     ecx, [rbp+320h+arg_58]
0x18009428f  mov     qword ptr [rsp+430h+var_3C8], r12
0x180094294  mov     dword ptr [rsp+430h+var_3D0], ecx
0x180094298  lea     rcx, [rbp+320h+var_38C]
0x18009429c  mov     [rsp+430h+var_3D8], rsi
0x1800942a1  mov     sil, [rbp+320h+arg_20]
0x1800942a8  mov     [rsp+430h+var_3E0], rcx
0x1800942ad  mov     r9b, sil
0x1800942b0  lea     rcx, [rbp+320h+arg_30]
0x1800942b7  mov     [rbp+320h+var_398], 0
0x1800942bf  mov     [rsp+430h+var_3E8], rcx
0x1800942c4  lea     rcx, [rbp+320h+var_398]
0x1800942c8  mov     dword ptr [rsp+430h+var_3F0], ebx
0x1800942cc  mov     [rsp+430h+var_3F8], rcx
0x1800942d1  lea     rcx, [rbp+320h+var_2E8]
0x1800942d5  mov     qword ptr [rsp+430h+var_400], rcx
0x1800942da  mov     rcx, r14
0x1800942dd  mov     byte ptr [rsp+430h+var_408], al
0x1800942e1  mov     [rsp+430h+var_410], r13
0x1800942e6  call    ?GetTreatAsClassWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@3PEAU5@PEAPEAUHSTRING__@@W4ComRegistrationVisibility@@PEA_NPEAW47@PEBGIQEBQEAU6@IQEBQEAU6@@Z; CPackagedComCatalog::GetTreatAsClassWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID *,HSTRING__ * *,ComRegistrationVisibility,bool *,ComRegistrationVisibility *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800942eb  mov     r12b, [rbp+320h+arg_30]
0x1800942f2  mov     ebx, eax
0x1800942f4  mov     eax, [rbp+320h+var_38C]
0x1800942f7  mov     [rbp+320h+var_38C], eax
0x1800942fa  jmp     short loc_18009436E
0x1800942fc  call    cs:__imp_WindowsDeleteString
0x180094303  nop     dword ptr [rax+rax+00h]
0x180094308  mov     r12b, [rbp+320h+arg_30]
0x18009430f  lea     rax, [rbp+320h+var_398]
0x180094313  mov     sil, [rbp+320h+arg_20]
0x18009431a  mov     r8, rdi
0x18009431d  mov     qword ptr [rsp+430h+var_3B8], rbx
0x180094322  mov     r9b, sil
0x180094325  mov     dword ptr [rsp+430h+var_3C0], ebx
0x180094329  mov     rdx, r15
0x18009432c  mov     qword ptr [rsp+430h+var_3C8], rbx
0x180094331  mov     rcx, r14
0x180094334  mov     dword ptr [rsp+430h+var_3D0], ebx
0x180094338  mov     [rsp+430h+var_3D8], rbx
0x18009433d  mov     [rsp+430h+var_3E0], rbx
0x180094342  mov     [rsp+430h+var_3E8], rbx
0x180094347  mov     dword ptr [rsp+430h+var_3F0], ebx
0x18009434b  mov     [rsp+430h+var_3F8], rax
0x180094350  lea     rax, [rbp+320h+var_2E8]
0x180094354  mov     qword ptr [rsp+430h+var_400], rax
0x180094359  mov     byte ptr [rsp+430h+var_408], r12b
0x18009435e  mov     [rsp+430h+var_410], r13; int
0x180094363  mov     [rbp+320h+var_398], rbx
0x180094367  call    ?GetTreatAsClassWorker@CPackagedComCatalog@@CAJPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@3PEAU5@PEAPEAUHSTRING__@@W4ComRegistrationVisibility@@PEA_NPEAW47@PEBGIQEBQEAU6@IQEBQEAU6@@Z; CPackagedComCatalog::GetTreatAsClassWorker(IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID *,HSTRING__ * *,ComRegistrationVisibility,bool *,ComRegistrationVisibility *,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x18009436c  mov     ebx, eax
0x18009436e  test    ebx, ebx
0x180094370  js      short loc_180094383
0x180094372  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180094379  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18009437e  and     sil, al
0x180094381  jmp     short loc_1800943C8
0x180094383  lea     eax, [rbx+7FFBFEADh]
0x180094389  cmp     eax, 1
0x18009438c  jbe     short loc_1800943B2
0x18009438e  mov     rcx, [rbp+328h]; this
0x180094395  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x18009439c  mov     r9d, ebx; char *
0x18009439f  mov     edx, 1BF3h; void *
0x1800943a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800943a9  mov     rdi, [rbp+320h+var_398]
0x1800943ad  jmp     loc_1800945A9
0x1800943b2  mov     rdx, rdi
0x1800943b5  lea     rcx, [rbp+320h+var_398]
0x1800943b9  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800943be  movups  xmm0, xmmword ptr [r13+0]
0x1800943c3  movdqu  xmmword ptr [rbp+320h+var_2E8], xmm0
0x1800943c8  xor     r13d, r13d
0x1800943cb  lea     rcx, [rbp+320h+var_290]; this
0x1800943d2  mov     [rbp+320h+var_388], r13
0x1800943d6  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x1800943db  mov     [rbp+320h+string], r13
0x1800943df  mov     [rbp+320h+var_390], r13d
0x1800943e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800943ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800943ef  test    al, al
0x1800943f1  jz      loc_1800944D5
0x1800943f7  mov     rcx, [rbp+320h+string]; string
0x1800943fb  movups  xmm6, xmmword ptr [rbp+320h+var_2E8]
0x1800943ff  call    cs:__imp_WindowsDeleteString
0x180094406  nop     dword ptr [rax+rax+00h]
0x18009440b  lea     rax, [rbp+320h+var_388]
0x18009440f  mov     byte ptr [rbp+320h+var_360+8], sil
0x180094413  mov     [rbp+320h+var_360], rax
0x180094417  lea     r8, [rbp+320h+var_390]
0x18009441b  movzx   eax, word ptr [rbp+320h+newString+9]
0x18009441f  lea     rdx, [rbp+320h+string]
0x180094423  mov     word ptr [rbp+320h+var_360+9], ax
0x180094427  lea     rcx, [rbp+320h+var_290]
0x18009442e  mov     al, byte ptr [rbp+320h+newString+0Bh]
0x180094431  mov     byte ptr [rbp+320h+var_360+0Bh], al
0x180094434  mov     eax, [rbp+320h+var_380]
0x180094437  mov     dword ptr [rbp+320h+var_360+0Ch], eax
0x18009443a  mov     rax, [rbp+320h+var_378]
0x18009443e  movaps  xmm0, xmmword ptr [rbp+320h+var_360]
0x180094442  mov     [rsp+430h+var_3A8], rax
0x18009444a  mov     eax, [rbp+320h+arg_68]
0x180094450  mov     dword ptr [rsp+430h+var_3B0], eax
0x180094457  mov     rax, [rbp+320h+var_328]
0x18009445b  mov     qword ptr [rsp+430h+var_3B8], rax
0x180094460  mov     eax, [rbp+320h+arg_58]
0x180094466  mov     dword ptr [rsp+430h+var_3C0], eax
0x18009446a  mov     rax, [rbp+320h+var_370]
0x18009446e  mov     qword ptr [rsp+430h+var_3C8], rax
0x180094473  lea     rax, [rbp+320h+newString]
0x180094477  mov     [rsp+430h+var_3D0], rax
0x18009447c  mov     eax, [rbp+320h+var_38C]
0x18009447f  mov     dword ptr [rsp+430h+var_3D8], eax
0x180094483  lea     rax, [rbp+320h+var_398]
0x180094487  mov     byte ptr [rsp+430h+var_3E0], r12b
0x18009448c  mov     byte ptr [rsp+430h+var_3E8], sil
0x180094491  mov     [rsp+430h+var_3F0], rax
0x180094496  lea     rax, [rbp+320h+var_2E8]
0x18009449a  mov     [rsp+430h+var_3F8], rax
0x18009449f  mov     qword ptr [rbp+320h+var_350], r14
0x1800944a3  mov     qword ptr [rbp+320h+var_350+8], r15
0x1800944a7  movaps  xmm1, xmmword ptr [rbp+320h+var_350]
0x1800944ab  mov     qword ptr [rsp+430h+var_400], r15
0x1800944b0  mov     [rsp+430h+var_408], r14
0x1800944b5  mov     [rbp+320h+string], r13
0x1800944b9  movaps  xmmword ptr [rbp+320h+newString], xmm0
0x1800944bd  movaps  [rbp+320h+var_2C0], xmm1
0x1800944c1  movaps  xmmword ptr [rbp+320h+var_2B0], xmm6
0x1800944c5  call    ??$DoPackageAwareLookupWithCustomRanking@UComClassRegistrationEntryProperties@@VEffectiveClsctxRanking@CPackagedComCatalog@@V_lambda_2e64a0868ac250278a4b3c43d8193f88_@@@EntryLookup@CPackagedComCatalog@@SAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@AEAVEffectiveClsctxRanking@1@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N9W45@V_lambda_2e64a0868ac250278a4b3c43d8193f88_@@PEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookupWithCustomRanking<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_2e64a0868ac250278a4b3c43d8193f88_>(ComClassRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::EffectiveClsctxRanking &,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,_lambda_2e64a0868ac250278a4b3c43d8193f88_,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800944ca  mov     rdi, [rbp+320h+var_398]
0x1800944ce  mov     esi, eax
0x1800944d0  jmp     loc_18009476F
0x1800944d5  lea     rax, [rbp+320h+var_388]
0x1800944d9  mov     rdx, rdi; struct OpaqueString *
0x1800944dc  lea     rcx, [rbp+320h+newString+8]; newString
0x1800944e0  mov     [rbp+320h+newString], rax
0x1800944e4  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x1800944e9  movups  xmm0, xmmword ptr [rbp+320h+var_2E8]
0x1800944ed  mov     rdi, [rbp+320h+var_398]
0x1800944f1  mov     eax, [rbp+320h+var_380]
0x1800944f4  mov     dword ptr [rbp+320h+var_2C0], eax
0x1800944f7  mov     qword ptr [rbp+320h+var_2C0+8], r14
0x1800944fb  mov     qword ptr [rbp+320h+var_2B0], r15
0x1800944ff  movdqu  xmmword ptr [rbp+320h+var_2B0+8], xmm0
0x180094504  test    rdi, rdi
0x180094507  jz      loc_180094705
0x18009450d  test    sil, sil
0x180094510  jz      loc_18009468F
0x180094516  xor     edx, edx; length
0x180094518  mov     [rbp+320h+var_370], r13
0x18009451c  mov     rcx, rdi; string
0x18009451f  mov     [rbp+320h+var_368], r13
0x180094523  call    cs:__imp_WindowsGetStringRawBuffer
0x18009452a  nop     dword ptr [rax+rax+00h]
0x18009452f  lea     r9, [rbp+320h+var_370]; struct PACKAGE_INFO **
0x180094533  mov     rcx, r14; struct IUserTokenInternal *
0x180094536  mov     rdx, rax; unsigned __int16 *
0x180094539  lea     r8, [rbp+320h+var_368]; unsigned __int64 *
0x18009453d  call    ?GetMainAndRelatedSetOptionalPackagesForMainPackage@@YAJPEAUIUserTokenInternal@@PEBGPEA_KPEAPEAUPACKAGE_INFO@@@Z; GetMainAndRelatedSetOptionalPackagesForMainPackage(IUserTokenInternal *,ushort const *,unsigned __int64 *,PACKAGE_INFO * *)
0x180094542  mov     ebx, eax
0x180094544  test    eax, eax
0x180094546  jns     short loc_1800945BF
0x180094548  mov     rcx, [rbp+328h]; this
0x18009454f  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x180094556  mov     r9d, eax; char *
0x180094559  mov     edx, 1CE4h; void *
0x18009455e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094563  lea     rcx, [rbp+320h+var_370]
0x180094567  call    ?reset@?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x18009456c  mov     rcx, [rbp+320h+newString+8]; string
0x180094570  call    cs:__imp_WindowsDeleteString
0x180094577  nop     dword ptr [rax+rax+00h]
0x18009457c  mov     rcx, [rbp+320h+string]; string
0x180094580  mov     [rbp+320h+newString+8], r13
0x180094584  call    cs:__imp_WindowsDeleteString
0x18009458b  nop     dword ptr [rax+rax+00h]
0x180094590  lea     rcx, [rbp+320h+var_290]; this
0x180094597  mov     [rbp+320h+string], r13
0x18009459b  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800945a0  lea     rcx, [rbp+320h+var_388]
0x1800945a4  call    ??1?$com_ptr_t@VCServerRegistration@CPackagedComCatalog@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<CPackagedComCatalog::CServerRegistration,wil::err_returncode_policy>::~com_ptr_t<CPackagedComCatalog::CServerRegistration,wil::err_returncode_policy>(void)
0x1800945a9  mov     rcx, rdi; string
0x1800945ac  call    cs:__imp_WindowsDeleteString
0x1800945b3  nop     dword ptr [rax+rax+00h]
0x1800945b8  mov     eax, ebx
0x1800945ba  jmp     loc_1800948A8
0x1800945bf  mov     rax, [rbp+320h+var_370]
0x1800945c3  xorps   xmm0, xmm0
0x1800945c6  mov     [rbp+320h+var_360+8], rax
0x1800945ca  mov     rax, [rbp+320h+var_368]
0x1800945ce  mov     qword ptr [rbp+320h+var_350], rax
0x1800945d2  mov     [rbp+320h+var_360], r13
0x1800945d6  movdqu  xmmword ptr [rbp+320h+var_350+8], xmm0
0x1800945db  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800945e2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800945e7  test    al, al
0x1800945e9  jnz     short loc_18009460A
0x1800945eb  cmp     qword ptr [rbp+320h+var_350], r13
0x1800945ef  jnz     short loc_18009460A
0x1800945f1  mov     rcx, [rbp+328h]; this
0x1800945f8  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800945ff  mov     edx, 0CBh; void *
0x180094604  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18009460a  lea     rdx, [rbp+320h+newString]; struct _lambda_384cae988b9b93015a87ed243e331da0_ *
0x18009460e  lea     rcx, [rbp+320h+var_320]; this
0x180094612  call    ??0_lambda_384cae988b9b93015a87ed243e331da0_@@QEAA@AEBV0@@Z; _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(_lambda_384cae988b9b93015a87ed243e331da0_ const &)
0x180094617  mov     rcx, [rbp+320h+string]; string
0x18009461b  mov     rbx, rax
0x18009461e  call    cs:__imp_WindowsDeleteString
0x180094625  nop     dword ptr [rax+rax+00h]
0x18009462a  mov     [rsp+430h+var_3F0], rbx; __int64
0x18009462f  lea     rax, [rbp+320h+var_360]
0x180094633  mov     [rsp+430h+var_3F8], rax; PackageFilter *
0x180094638  lea     r8, [rbp+320h+var_390]; int
0x18009463c  lea     rax, [rbp+320h+var_2E8]
0x180094640  mov     [rsp+430h+var_400], r12b; char
0x180094645  mov     [rsp+430h+var_408], rax; __int64
0x18009464a  lea     rdx, [rbp+320h+string]; int
0x18009464e  mov     r9, r14; int
0x180094651  mov     [rsp+430h+var_410], r15; __int64
0x180094656  lea     rcx, [rbp+320h+var_290]; int
0x18009465d  mov     [rbp+320h+string], r13
0x180094661  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComClassRegistrationEntryProperties@@VEffectiveClsctxRanking@CPackagedComCatalog@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@CPackagedComCatalog@@CAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAVEffectiveClsctxRanking@0@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_384cae988b9b93015a87ed243e331da0_@@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,CPackagedComCatalog::EffectiveClsctxRanking,_lambda_384cae988b9b93015a87ed243e331da0_>(ComClassRegistrationEntryProperties &,HSTRING__ * *,CPackagedComCatalog::EffectiveClsctxRanking *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_384cae988b9b93015a87ed243e331da0_)
0x180094666  lea     rcx, [rbp+320h+var_350+8]
0x18009466a  mov     esi, eax
0x18009466c  call    ?reset@?$unique_any_array_ptr@PEAUHSTRING__@@Uprocess_heap_deleter@wil@@U?$function_deleter@P6AJPEAUHSTRING__@@@Z$1?WindowsDeleteString@@YAJ0@Z@3@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<HSTRING__ *,wil::process_heap_deleter,wil::function_deleter<long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *)>,unsigned __int64>::reset(void)
0x180094671  lea     rcx, [rbp+320h+var_360+8]
0x180094675  call    ?reset@?$unique_any_array_ptr@UPACKAGE_INFO@@UPrivMemDeleter@@Uempty_deleter@wil@@_K@wil@@QEAAXXZ; wil::unique_any_array_ptr<PACKAGE_INFO,PrivMemDeleter,wil::empty_deleter,unsigned __int64>::reset(void)
0x18009467a  mov     rcx, [rbp+320h+var_360]; string
0x18009467e  call    cs:__imp_WindowsDeleteString
0x180094685  nop     dword ptr [rax+rax+00h]
0x18009468a  jmp     loc_18009475F
0x18009468f  lea     rdx, [rbp+320h+var_398]; struct OpaqueString *
0x180094693  lea     rcx, [rbp+320h+var_360]; this
0x180094697  call    ??0PackageFilter@@QEAA@AEBVOpaqueString@@@Z; PackageFilter::PackageFilter(OpaqueString const &)
0x18009469c  lea     rdx, [rbp+320h+newString]; struct _lambda_384cae988b9b93015a87ed243e331da0_ *
0x1800946a0  lea     rcx, [rbp+320h+var_320]; this
0x1800946a4  call    ??0_lambda_384cae988b9b93015a87ed243e331da0_@@QEAA@AEBV0@@Z; _lambda_384cae988b9b93015a87ed243e331da0_::_lambda_384cae988b9b93015a87ed243e331da0_(_lambda_384cae988b9b93015a87ed243e331da0_ const &)
0x1800946a9  mov     rcx, [rbp+320h+string]; string
0x1800946ad  mov     rbx, rax
0x1800946b0  call    cs:__imp_WindowsDeleteString
0x1800946b7  nop     dword ptr [rax+rax+00h]
0x1800946bc  mov     [rsp+430h+var_3F0], rbx; __int64
0x1800946c1  lea     rax, [rbp+320h+var_360]
0x1800946c5  mov     [rsp+430h+var_3F8], rax; PackageFilter *
0x1800946ca  lea     r8, [rbp+320h+var_390]; int
0x1800946ce  lea     rax, [rbp+320h+var_2E8]
0x1800946d2  mov     [rsp+430h+var_400], r12b; char
0x1800946d7  mov     [rsp+430h+var_408], rax; __int64
0x1800946dc  lea     rdx, [rbp+320h+string]; int
0x1800946e0  mov     r9, r14; int
0x1800946e3  mov     [rsp+430h+var_410], r15; __int64
  ... truncated ...
```
