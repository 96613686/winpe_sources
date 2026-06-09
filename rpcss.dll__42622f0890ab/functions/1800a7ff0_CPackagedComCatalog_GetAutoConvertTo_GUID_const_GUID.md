# CPackagedComCatalog::GetAutoConvertTo(_GUID const &,_GUID *)

- ea: `0x1800a7ff0`
- end: `0x1800a83a3`
- name: `?GetAutoConvertTo@CPackagedComCatalog@@UEAAJAEBU_GUID@@PEAU2@@Z`
- size: `947`
- prototype: `int(CPackagedComCatalog *__hidden this, const struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005c40`
- `0x18000d4c4`
- `0x18000e148`
- `0x18002ba28`
- `0x18005ced0`
- `0x180081894`
- `0x18008dd38`
- `0x18008e98c`
- `0x18008eff4`
- `0x180092d8c`
- `0x1800a7ff0`
- `0x1800a83ac`
- `0x1800b27e0`
- `0x1800d4360`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a80e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a814f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a815b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a81b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a81c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a820d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a824a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a82e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a82f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8364`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a80e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a814f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a815b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a81b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a81c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a820d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a824a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a82e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a82f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8356`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800a8364`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800a8050`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800a8050`

## string_xrefs

- `0x1800a8063`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800a833a`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetAutoConvertTo(CPackagedComCatalog *this, struct _GUID *a2, struct _GUID *a3)
{
  int RegistrationStoreContext; // eax
  int v7; // ebx
  char IsUserHiveOk; // r15
  char v9; // dl
  char v10; // bl
  __int64 v11; // rdi
  __int64 v12; // rbx
  char v13; // r15
  char v14; // dl
  char v15; // bl
  __int64 v16; // rdi
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 *v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-F0h]
  int v24; // [rsp+38h] [rbp-D8h]
  int v25; // [rsp+50h] [rbp-C0h]
  void **v26; // [rsp+58h] [rbp-B8h]
  HSTRING string; // [rsp+90h] [rbp-80h] BYREF
  int v28[2]; // [rsp+98h] [rbp-78h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-70h] BYREF
  _OWORD v30[2]; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v31; // [rsp+C8h] [rbp-48h]
  _BYTE v32[24]; // [rsp+D0h] [rbp-40h] BYREF
  HSTRING v33; // [rsp+E8h] [rbp-28h]
  char v34; // [rsp+F0h] [rbp-20h]
  struct _GUID v35; // [rsp+F4h] [rbp-1Ch]
  __int16 v36; // [rsp+104h] [rbp-Ch]
  char v37; // [rsp+108h] [rbp-8h]
  int v38; // [rsp+10Ch] [rbp-4h]
  char v39; // [rsp+110h] [rbp+0h]
  int v40; // [rsp+114h] [rbp+4h]
  char v41; // [rsp+118h] [rbp+8h]
  int v42; // [rsp+11Ch] [rbp+Ch]
  HSTRING v43[11]; // [rsp+120h] [rbp+10h] BYREF
  char v44; // [rsp+178h] [rbp+68h]
  struct _GUID v45; // [rsp+17Ch] [rbp+6Ch]
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+298h]

  *(_QWORD *)v28 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, 0, 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
  v7 = RegistrationStoreContext;
  if ( RegistrationStoreContext >= 0 )
  {
    v32[16] = 0;
    v33 = 0;
    v35 = 0;
    v34 = 0;
    memset(v30, 0, sizeof(v30));
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    string = 0;
    v31 = 0;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    IsUserHiveOk = CPackagedComCatalog::IsUserHiveOk((CPackagedComCatalog *)((char *)this - 24));
    if ( v9 )
    {
      v10 = *((_BYTE *)this + 32);
      v11 = *(_QWORD *)v28;
      WindowsDeleteString(0);
      string = 0;
      v29 = 0;
      v7 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComTreatAsClassRegistrationEntryProperties const &,bool &)>(
             (__int64)v32,
             (__int64)&string,
             0,
             0,
             0,
             v11,
             (__int64)a2,
             (__int64)&v29,
             v10,
             IsUserHiveOk,
             0,
             v26,
             0,
             0,
             0,
             0,
             0);
      WindowsDeleteString(0);
    }
    else
    {
      v12 = *(_QWORD *)v28;
      WindowsDeleteString(0);
      string = 0;
      v7 = CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
             (int)v32,
             (int)&string,
             0,
             v12,
             (__int64)a2,
             IsUserHiveOk,
             0,
             v24);
    }
    if ( v7 >= 0 )
    {
      if ( v34 )
      {
        *a3 = v35;
LABEL_9:
        PackageFilter::~PackageFilter((PackageFilter *)v30);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v33);
        v7 = 0;
LABEL_27:
        v33 = 0;
        goto LABEL_28;
      }
      goto LABEL_20;
    }
    if ( v7 != -2147024894 )
      goto LABEL_23;
    ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v43);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v13 = CPackagedComCatalog::IsUserHiveOk((CPackagedComCatalog *)((char *)this - 24));
    if ( v14 )
    {
      v15 = *((_BYTE *)this + 32);
      v16 = *(_QWORD *)v28;
      WindowsDeleteString(string);
      string = 0;
      v29 = 0;
      v7 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComClassRegistrationEntryProperties const &,bool &)>(
             (__int64)v43,
             (__int64)&string,
             v17,
             v18,
             v23,
             v16,
             (__int64)a2,
             (__int64)&v29,
             v15,
             v13,
             v25);
      WindowsDeleteString(0);
    }
    else
    {
      v19 = *(__int64 **)v28;
      WindowsDeleteString(string);
      string = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v20);
      LODWORD(v29) = 0;
      v7 = Z::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>(
             (__int64)v43,
             &string,
             &v29,
             0,
             v19,
             a2,
             v13,
             0,
             (__int64 (__fastcall *)(_QWORD *, _QWORD, _BYTE *, char *))CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>);
    }
    if ( v7 >= 0 )
    {
      if ( v44 )
      {
        *a3 = v45;
        ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v43);
        goto LABEL_9;
      }
      ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v43);
LABEL_20:
      PackageFilter::~PackageFilter((PackageFilter *)v30);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v33);
      v7 = -2147221166;
      goto LABEL_27;
    }
    ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v43);
    if ( v7 == -2147024894 )
    {
      v7 = -2147221164;
      v21 = 2996;
    }
    else
    {
LABEL_23:
      if ( v7 == -2147024883 )
      {
        v7 = -2147221165;
        v21 = 2997;
      }
      else
      {
        v21 = 2998;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)v7,
      v23);
    PackageFilter::~PackageFilter((PackageFilter *)v30);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v33);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB73,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)RegistrationStoreContext,
    (int)v28);
LABEL_28:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v28);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800a7ff0  mov     [rsp-8+arg_18], rbx
0x1800a7ff5  push    rbp
0x1800a7ff6  push    rsi
0x1800a7ff7  push    rdi
0x1800a7ff8  push    r12
0x1800a7ffa  push    r13
0x1800a7ffc  push    r14
0x1800a7ffe  push    r15
0x1800a8000  lea     rbp, [rsp-260h]
0x1800a8008  sub     rsp, 370h
0x1800a800f  mov     rax, cs:__security_cookie
0x1800a8016  xor     rax, rsp
0x1800a8019  mov     [rbp+290h+var_40], rax
0x1800a8020  mov     r13, rcx
0x1800a8023  xor     edi, edi
0x1800a8025  lea     rcx, [rbp+290h+var_308]
0x1800a8029  mov     qword ptr [rbp+290h+var_308], rdi
0x1800a802d  mov     rsi, r8
0x1800a8030  mov     r14, rdx
0x1800a8033  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a8038  lea     rax, [rbp+290h+var_308]
0x1800a803c  xor     r8d, r8d
0x1800a803f  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800a8046  mov     qword ptr [rsp+3A0h+var_380], rax; int
0x1800a804b  xor     edx, edx
0x1800a804d  lea     ecx, [rdi+1]
0x1800a8050  call    cs:__imp_RoGetRegistrationStoreContext
0x1800a8056  mov     ebx, eax
0x1800a8058  test    eax, eax
0x1800a805a  jns     short loc_1800A807C
0x1800a805c  mov     rcx, [rbp+298h]; this
0x1800a8063  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a806a  mov     r9d, eax; char *
0x1800a806d  mov     edx, 0B73h; void *
0x1800a8072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8077  jmp     loc_1800A836E
0x1800a807c  xorps   xmm0, xmm0
0x1800a807f  mov     [rbp+290h+var_2C0], dil
0x1800a8083  xorps   xmm1, xmm1
0x1800a8086  mov     [rbp+290h+var_2B8], rdi
0x1800a808a  movups  [rbp+290h+var_2AC], xmm0
0x1800a808e  mov     [rbp+290h+var_2B0], dil
0x1800a8092  movdqu  [rbp+290h+var_2F8], xmm0
0x1800a8097  mov     [rbp+290h+var_29C], di
0x1800a809b  movdqu  [rbp+290h+var_2E8], xmm1
0x1800a80a0  mov     [rbp+290h+var_298], dil
0x1800a80a4  mov     [rbp+290h+var_294], edi
0x1800a80a7  mov     [rbp+290h+var_290], dil
0x1800a80ab  mov     [rbp+290h+var_28C], edi
0x1800a80ae  mov     [rbp+290h+var_288], dil
0x1800a80b2  mov     [rbp+290h+var_284], edi
0x1800a80b5  mov     [rbp+290h+string], rdi
0x1800a80b9  mov     [rbp+290h+var_2D8], rdi
0x1800a80bd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800a80c4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800a80c9  lea     rcx, [r13-18h]; this
0x1800a80cd  mov     dl, al
0x1800a80cf  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800a80d4  mov     rcx, [rbp+290h+string]; string
0x1800a80d8  mov     r15b, al
0x1800a80db  test    dl, dl
0x1800a80dd  jz      short loc_1800A8157
0x1800a80df  mov     bl, [r13+20h]
0x1800a80e3  mov     rdi, qword ptr [rbp+290h+var_308]
0x1800a80e7  call    cs:__imp_WindowsDeleteString
0x1800a80ed  xor     eax, eax
0x1800a80ef  lea     rdx, [rbp+290h+string]
0x1800a80f3  mov     [rsp+3A0h+var_320], rax
0x1800a80fb  lea     rcx, [rbp+290h+var_2D0]
0x1800a80ff  mov     [rsp+3A0h+var_328], eax
0x1800a8103  xor     r9d, r9d
0x1800a8106  mov     [rsp+3A0h+var_330], rax
0x1800a810b  xor     r8d, r8d
0x1800a810e  mov     [rsp+3A0h+var_338], eax
0x1800a8112  mov     [rsp+3A0h+var_340], rax
0x1800a8117  mov     [rsp+3A0h+var_350], eax
0x1800a811b  mov     [rsp+3A0h+var_358], r15b
0x1800a8120  mov     byte ptr [rsp+3A0h+var_360], bl
0x1800a8124  mov     [rbp+290h+string], rax
0x1800a8128  mov     [rbp+290h+var_300], rax
0x1800a812c  lea     rax, [rbp+290h+var_300]
0x1800a8130  mov     [rsp+3A0h+var_368], rax
0x1800a8135  mov     [rsp+3A0h+var_370], r14
0x1800a813a  mov     [rsp+3A0h+var_378], rdi
0x1800a813f  xor     edi, edi
0x1800a8141  mov     qword ptr [rsp+3A0h+var_380], rdi
0x1800a8146  call    ??$DoPackageAwareLookup@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComTreatAsClassRegistrationEntryProperties const &,bool &)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComTreatAsClassRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800a814b  xor     ecx, ecx; string
0x1800a814d  mov     ebx, eax
0x1800a814f  call    cs:__imp_WindowsDeleteString
0x1800a8155  jmp     short loc_1800A8189
0x1800a8157  mov     rbx, qword ptr [rbp+290h+var_308]
0x1800a815b  call    cs:__imp_WindowsDeleteString
0x1800a8161  mov     [rsp+3A0h+var_370], rdi
0x1800a8166  lea     rdx, [rbp+290h+string]
0x1800a816a  mov     byte ptr [rsp+3A0h+var_378], r15b
0x1800a816f  lea     rcx, [rbp+290h+var_2D0]
0x1800a8173  mov     r9, rbx
0x1800a8176  mov     qword ptr [rsp+3A0h+var_380], r14; int
0x1800a817b  xor     r8d, r8d
0x1800a817e  mov     [rbp+290h+string], rdi
0x1800a8182  call    ??$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))
0x1800a8187  mov     ebx, eax
0x1800a8189  test    ebx, ebx
0x1800a818b  js      short loc_1800A81CE
0x1800a818d  lea     rcx, [rbp+290h+var_2F8]; this
0x1800a8191  cmp     [rbp+290h+var_2B0], dil
0x1800a8195  jz      loc_1800A82DD
0x1800a819b  mov     rax, qword ptr [rbp+290h+var_2AC]
0x1800a819f  mov     [rsi], rax
0x1800a81a2  mov     rax, qword ptr [rbp+290h+var_2AC+8]
0x1800a81a6  mov     [rsi+8], rax
0x1800a81aa  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x1800a81af  mov     rcx, [rbp+290h+string]; string
0x1800a81b3  call    cs:__imp_WindowsDeleteString
0x1800a81b9  mov     rcx, [rbp+290h+var_2B8]; string
0x1800a81bd  mov     [rbp+290h+string], rdi
0x1800a81c1  call    cs:__imp_WindowsDeleteString
0x1800a81c7  mov     ebx, edi
0x1800a81c9  jmp     loc_1800A836A
0x1800a81ce  cmp     ebx, 80070002h
0x1800a81d4  jnz     loc_1800A831A
0x1800a81da  lea     rcx, [rbp+290h+var_280]; this
0x1800a81de  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x1800a81e3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800a81ea  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800a81ef  lea     rcx, [r13-18h]; this
0x1800a81f3  mov     dl, al
0x1800a81f5  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800a81fa  mov     rcx, [rbp+290h+string]; string
0x1800a81fe  mov     r15b, al
0x1800a8201  test    dl, dl
0x1800a8203  jz      short loc_1800A8254
0x1800a8205  mov     bl, [r13+20h]
0x1800a8209  mov     rdi, qword ptr [rbp+290h+var_308]
0x1800a820d  call    cs:__imp_WindowsDeleteString
0x1800a8213  xor     eax, eax
0x1800a8215  mov     [rsp+3A0h+var_358], r15b
0x1800a821a  mov     byte ptr [rsp+3A0h+var_360], bl
0x1800a821e  lea     rdx, [rbp+290h+string]
0x1800a8222  mov     [rbp+290h+string], rax
0x1800a8226  lea     rcx, [rbp+290h+var_280]
0x1800a822a  mov     [rbp+290h+var_300], rax
0x1800a822e  lea     rax, [rbp+290h+var_300]
0x1800a8232  mov     [rsp+3A0h+var_368], rax
0x1800a8237  mov     [rsp+3A0h+var_370], r14
0x1800a823c  mov     [rsp+3A0h+var_378], rdi
0x1800a8241  call    ??$DoPackageAwareLookup@UComClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComClassRegistrationEntryProperties const &,bool &)>(ComClassRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComClassRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800a8246  xor     ecx, ecx; string
0x1800a8248  mov     ebx, eax
0x1800a824a  call    cs:__imp_WindowsDeleteString
0x1800a8250  xor     edi, edi
0x1800a8252  jmp     short loc_1800A82B0
0x1800a8254  mov     rbx, qword ptr [rbp+290h+var_308]
0x1800a8258  call    cs:__imp_WindowsDeleteString
0x1800a825e  mov     [rbp+290h+string], rdi
0x1800a8262  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800a8269  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800a826e  test    al, al
0x1800a8270  jz      short loc_1800A8277
0x1800a8272  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a8277  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x1800a827e  mov     dword ptr [rbp+290h+var_300], edi
0x1800a8281  mov     [rsp+3A0h+var_360], rax
0x1800a8286  lea     r8, [rbp+290h+var_300]
0x1800a828a  mov     [rsp+3A0h+var_368], rdi
0x1800a828f  lea     rdx, [rbp+290h+string]
0x1800a8293  mov     byte ptr [rsp+3A0h+var_370], r15b
0x1800a8298  lea     rcx, [rbp+290h+var_280]
0x1800a829c  mov     [rsp+3A0h+var_378], r14
0x1800a82a1  xor     r9d, r9d
0x1800a82a4  mov     qword ptr [rsp+3A0h+var_380], rbx
0x1800a82a9  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>(ComClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>(ComClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x1800a82ae  mov     ebx, eax
0x1800a82b0  lea     rcx, [rbp+290h+var_280]; this
0x1800a82b4  test    ebx, ebx
0x1800a82b6  js      short loc_1800A8301
0x1800a82b8  cmp     [rbp+290h+var_228], dil
0x1800a82bc  jz      short loc_1800A82D4
0x1800a82be  movups  xmm0, [rbp+290h+var_224]
0x1800a82c2  movdqu  xmmword ptr [rsi], xmm0
0x1800a82c6  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800a82cb  lea     rcx, [rbp+290h+var_2F8]
0x1800a82cf  jmp     loc_1800A81AA
0x1800a82d4  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800a82d9  lea     rcx, [rbp+290h+var_2F8]; this
0x1800a82dd  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x1800a82e2  mov     rcx, [rbp+290h+string]; string
0x1800a82e6  call    cs:__imp_WindowsDeleteString
0x1800a82ec  mov     rcx, [rbp+290h+var_2B8]; string
0x1800a82f0  mov     [rbp+290h+string], rdi
0x1800a82f4  call    cs:__imp_WindowsDeleteString
0x1800a82fa  mov     ebx, 80040152h
0x1800a82ff  jmp     short loc_1800A836A
0x1800a8301  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800a8306  cmp     ebx, 80070002h
0x1800a830c  jnz     short loc_1800A831A
0x1800a830e  mov     ebx, 80040154h
0x1800a8313  mov     edx, 0BB4h
0x1800a8318  jmp     short loc_1800A8333
0x1800a831a  cmp     ebx, 8007000Dh
0x1800a8320  jnz     short loc_1800A832E
0x1800a8322  mov     ebx, 80040153h
0x1800a8327  mov     edx, 0BB5h
0x1800a832c  jmp     short loc_1800A8333
0x1800a832e  mov     edx, 0BB6h; void *
0x1800a8333  mov     rcx, [rbp+298h]; this
0x1800a833a  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800a8341  mov     r9d, ebx; char *
0x1800a8344  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8349  lea     rcx, [rbp+290h+var_2F8]; this
0x1800a834d  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x1800a8352  mov     rcx, [rbp+290h+string]; string
0x1800a8356  call    cs:__imp_WindowsDeleteString
0x1800a835c  mov     rcx, [rbp+290h+var_2B8]; string
0x1800a8360  mov     [rbp+290h+string], rdi
0x1800a8364  call    cs:__imp_WindowsDeleteString
0x1800a836a  mov     [rbp+290h+var_2B8], rdi
0x1800a836e  lea     rcx, [rbp+290h+var_308]
0x1800a8372  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a8377  mov     eax, ebx
0x1800a8379  mov     rcx, [rbp+290h+var_40]
0x1800a8380  xor     rcx, rsp; StackCookie
0x1800a8383  call    __security_check_cookie
0x1800a8388  mov     rbx, [rsp+3A0h+arg_18]
0x1800a8390  add     rsp, 370h
0x1800a8397  pop     r15
0x1800a8399  pop     r14
0x1800a839b  pop     r13
0x1800a839d  pop     r12
0x1800a839f  pop     rdi
0x1800a83a0  pop     rsi
0x1800a83a1  pop     rbp
0x1800a83a2  retn
```
