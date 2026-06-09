# CPackagedComCatalog::GetAutoConvertTo(_GUID const &,_GUID *)

- ea: `0x1800ad060`
- end: `0x1800ad466`
- name: `?GetAutoConvertTo@CPackagedComCatalog@@UEAAJAEBU_GUID@@PEAU2@@Z`
- size: `1030`
- prototype: `int(CPackagedComCatalog *__hidden this, const struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800065a4`
- `0x1800210f8`
- `0x18002610c`
- `0x18002750c`
- `0x180061d74`
- `0x180085b3c`
- `0x180094f7c`
- `0x180095c0c`
- `0x1800962a8`
- `0x18009836c`
- `0x1800ad060`
- `0x1800ad46c`
- `0x1800b7ac0`
- `0x1800dad54`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad1cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad1e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad23f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad3a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad40c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad420`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad161`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad1cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad1e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad23f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad2fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad390`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad3a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad40c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ad420`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800ad0c0`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800ad0c0`

## string_xrefs

- `0x1800ad0d9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ad3f0`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetAutoConvertTo(
        CPackagedComCatalog *this,
        const struct _GUID *a2,
        struct _GUID *a3)
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
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdx
  int v23; // [rsp+20h] [rbp-F0h]
  int v24; // [rsp+50h] [rbp-C0h]
  HSTRING string; // [rsp+90h] [rbp-80h] BYREF
  int v26[2]; // [rsp+98h] [rbp-78h] BYREF
  __int64 v27; // [rsp+A0h] [rbp-70h] BYREF
  _OWORD v28[2]; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-48h]
  _BYTE v30[24]; // [rsp+D0h] [rbp-40h] BYREF
  HSTRING v31; // [rsp+E8h] [rbp-28h]
  char v32; // [rsp+F0h] [rbp-20h]
  struct _GUID v33; // [rsp+F4h] [rbp-1Ch]
  __int16 v34; // [rsp+104h] [rbp-Ch]
  char v35; // [rsp+108h] [rbp-8h]
  int v36; // [rsp+10Ch] [rbp-4h]
  char v37; // [rsp+110h] [rbp+0h]
  int v38; // [rsp+114h] [rbp+4h]
  char v39; // [rsp+118h] [rbp+8h]
  int v40; // [rsp+11Ch] [rbp+Ch]
  HSTRING v41[11]; // [rsp+120h] [rbp+10h] BYREF
  char v42; // [rsp+178h] [rbp+68h]
  struct _GUID v43; // [rsp+17Ch] [rbp+6Ch]
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+298h]

  *(_QWORD *)v26 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26);
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, 0, 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
  v7 = RegistrationStoreContext;
  if ( RegistrationStoreContext >= 0 )
  {
    v30[16] = 0;
    v31 = 0;
    v33 = 0;
    v32 = 0;
    memset(v28, 0, sizeof(v28));
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    string = 0;
    v29 = 0;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    IsUserHiveOk = CPackagedComCatalog::IsUserHiveOk((CPackagedComCatalog *)((char *)this - 24));
    if ( v9 )
    {
      v10 = *((_BYTE *)this + 32);
      v11 = *(_QWORD *)v26;
      WindowsDeleteString(0);
      string = 0;
      v27 = 0;
      v7 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComTreatAsClassRegistrationEntryProperties const &,bool &)>(
             (unsigned int)v30,
             (unsigned int)&string,
             0,
             0,
             0,
             v11,
             (__int64)a2,
             (__int64)&v27,
             v10,
             IsUserHiveOk,
             0);
      WindowsDeleteString(0);
    }
    else
    {
      v12 = *(_QWORD *)v26;
      WindowsDeleteString(0);
      string = 0;
      v7 = CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(
             (unsigned int)v30,
             (unsigned int)&string,
             0,
             v12,
             (__int64)a2,
             IsUserHiveOk,
             0);
    }
    if ( v7 >= 0 )
    {
      if ( v32 )
      {
        *a3 = v33;
LABEL_9:
        PackageFilter::~PackageFilter((PackageFilter *)v28);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v31);
        v7 = 0;
LABEL_27:
        v31 = 0;
        goto LABEL_28;
      }
      goto LABEL_20;
    }
    if ( v7 != -2147024894 )
      goto LABEL_23;
    ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties((ComClassRegistrationEntryProperties *)v41);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v13 = CPackagedComCatalog::IsUserHiveOk((CPackagedComCatalog *)((char *)this - 24));
    if ( v14 )
    {
      v15 = *((_BYTE *)this + 32);
      v16 = *(_QWORD *)v26;
      WindowsDeleteString(string);
      string = 0;
      v27 = 0;
      v7 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComClassRegistrationEntryProperties const &,bool &)>(
             (unsigned int)v41,
             (unsigned int)&string,
             v17,
             v18,
             v23,
             v16,
             (__int64)a2,
             (__int64)&v27,
             v15,
             v13,
             v24);
      WindowsDeleteString(0);
    }
    else
    {
      v19 = *(_QWORD *)v26;
      WindowsDeleteString(string);
      string = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v20);
      LODWORD(v27) = 0;
      v7 = Z::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>(
             (unsigned int)v41,
             (unsigned int)&string,
             (unsigned int)&v27,
             0,
             v19,
             (__int64)a2,
             v13,
             0,
             (__int64)CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>);
    }
    if ( v7 >= 0 )
    {
      if ( v42 )
      {
        *a3 = v43;
        ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v41);
        goto LABEL_9;
      }
      ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v41);
LABEL_20:
      PackageFilter::~PackageFilter((PackageFilter *)v28);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v31);
      v7 = -2147221166;
      goto LABEL_27;
    }
    ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(v41);
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
    PackageFilter::~PackageFilter((PackageFilter *)v28);
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(v31);
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB73,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)RegistrationStoreContext,
    (int)v26);
LABEL_28:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v26);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ad060  mov     [rsp-8+arg_18], rbx
0x1800ad065  push    rbp
0x1800ad066  push    rsi
0x1800ad067  push    rdi
0x1800ad068  push    r12
0x1800ad06a  push    r13
0x1800ad06c  push    r14
0x1800ad06e  push    r15
0x1800ad070  lea     rbp, [rsp-260h]
0x1800ad078  sub     rsp, 370h
0x1800ad07f  mov     rax, cs:__security_cookie
0x1800ad086  xor     rax, rsp
0x1800ad089  mov     [rbp+290h+var_40], rax
0x1800ad090  mov     r13, rcx
0x1800ad093  xor     edi, edi
0x1800ad095  lea     rcx, [rbp+290h+var_308]
0x1800ad099  mov     qword ptr [rbp+290h+var_308], rdi
0x1800ad09d  mov     rsi, r8
0x1800ad0a0  mov     r14, rdx
0x1800ad0a3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ad0a8  lea     rax, [rbp+290h+var_308]
0x1800ad0ac  xor     r8d, r8d
0x1800ad0af  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800ad0b6  mov     qword ptr [rsp+3A0h+var_380], rax; int
0x1800ad0bb  xor     edx, edx
0x1800ad0bd  lea     ecx, [rdi+1]
0x1800ad0c0  call    cs:__imp_RoGetRegistrationStoreContext
0x1800ad0c7  nop     dword ptr [rax+rax+00h]
0x1800ad0cc  mov     ebx, eax
0x1800ad0ce  test    eax, eax
0x1800ad0d0  jns     short loc_1800AD0F2
0x1800ad0d2  mov     rcx, [rbp+298h]; this
0x1800ad0d9  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ad0e0  mov     r9d, eax; char *
0x1800ad0e3  mov     edx, 0B73h; void *
0x1800ad0e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad0ed  jmp     loc_1800AD430
0x1800ad0f2  xorps   xmm0, xmm0
0x1800ad0f5  mov     [rbp+290h+var_2C0], dil
0x1800ad0f9  xorps   xmm1, xmm1
0x1800ad0fc  mov     [rbp+290h+var_2B8], rdi
0x1800ad100  movups  [rbp+290h+var_2AC], xmm0
0x1800ad104  mov     [rbp+290h+var_2B0], dil
0x1800ad108  movdqu  [rbp+290h+var_2F8], xmm0
0x1800ad10d  mov     [rbp+290h+var_29C], di
0x1800ad111  movdqu  [rbp+290h+var_2E8], xmm1
0x1800ad116  mov     [rbp+290h+var_298], dil
0x1800ad11a  mov     [rbp+290h+var_294], edi
0x1800ad11d  mov     [rbp+290h+var_290], dil
0x1800ad121  mov     [rbp+290h+var_28C], edi
0x1800ad124  mov     [rbp+290h+var_288], dil
0x1800ad128  mov     [rbp+290h+var_284], edi
0x1800ad12b  mov     [rbp+290h+string], rdi
0x1800ad12f  mov     [rbp+290h+var_2D8], rdi
0x1800ad133  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800ad13a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800ad13f  lea     rcx, [r13-18h]; this
0x1800ad143  mov     dl, al
0x1800ad145  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800ad14a  mov     rcx, [rbp+290h+string]; string
0x1800ad14e  mov     r15b, al
0x1800ad151  test    dl, dl
0x1800ad153  jz      loc_1800AD1DD
0x1800ad159  mov     bl, [r13+20h]
0x1800ad15d  mov     rdi, qword ptr [rbp+290h+var_308]
0x1800ad161  call    cs:__imp_WindowsDeleteString
0x1800ad168  nop     dword ptr [rax+rax+00h]
0x1800ad16d  xor     eax, eax
0x1800ad16f  lea     rdx, [rbp+290h+string]
0x1800ad173  mov     [rsp+3A0h+var_320], rax
0x1800ad17b  lea     rcx, [rbp+290h+var_2D0]
0x1800ad17f  mov     [rsp+3A0h+var_328], eax
0x1800ad183  xor     r9d, r9d
0x1800ad186  mov     [rsp+3A0h+var_330], rax
0x1800ad18b  xor     r8d, r8d
0x1800ad18e  mov     [rsp+3A0h+var_338], eax
0x1800ad192  mov     [rsp+3A0h+var_340], rax
0x1800ad197  mov     [rsp+3A0h+var_350], eax
0x1800ad19b  mov     [rsp+3A0h+var_358], r15b
0x1800ad1a0  mov     byte ptr [rsp+3A0h+var_360], bl
0x1800ad1a4  mov     [rbp+290h+string], rax
0x1800ad1a8  mov     [rbp+290h+var_300], rax
0x1800ad1ac  lea     rax, [rbp+290h+var_300]
0x1800ad1b0  mov     [rsp+3A0h+var_368], rax
0x1800ad1b5  mov     [rsp+3A0h+var_370], r14
0x1800ad1ba  mov     [rsp+3A0h+var_378], rdi
0x1800ad1bf  xor     edi, edi
0x1800ad1c1  mov     qword ptr [rsp+3A0h+var_380], rdi
0x1800ad1c6  call    ??$DoPackageAwareLookup@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComTreatAsClassRegistrationEntryProperties const &,bool &)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComTreatAsClassRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800ad1cb  xor     ecx, ecx; string
0x1800ad1cd  mov     ebx, eax
0x1800ad1cf  call    cs:__imp_WindowsDeleteString
0x1800ad1d6  nop     dword ptr [rax+rax+00h]
0x1800ad1db  jmp     short loc_1800AD215
0x1800ad1dd  mov     rbx, qword ptr [rbp+290h+var_308]
0x1800ad1e1  call    cs:__imp_WindowsDeleteString
0x1800ad1e8  nop     dword ptr [rax+rax+00h]
0x1800ad1ed  mov     [rsp+3A0h+var_370], rdi
0x1800ad1f2  lea     rdx, [rbp+290h+string]
0x1800ad1f6  mov     byte ptr [rsp+3A0h+var_378], r15b
0x1800ad1fb  lea     rcx, [rbp+290h+var_2D0]
0x1800ad1ff  mov     r9, rbx
0x1800ad202  mov     qword ptr [rsp+3A0h+var_380], r14; int
0x1800ad207  xor     r8d, r8d
0x1800ad20a  mov     [rbp+290h+string], rdi
0x1800ad20e  call    ??$ResolveAndReadEntryOld@UComTreatAsClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComTreatAsClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComTreatAsClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *)>(ComTreatAsClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComTreatAsClassRegistrationEntryProperties const &,bool *))
0x1800ad213  mov     ebx, eax
0x1800ad215  test    ebx, ebx
0x1800ad217  js      short loc_1800AD266
0x1800ad219  lea     rcx, [rbp+290h+var_2F8]; this
0x1800ad21d  cmp     [rbp+290h+var_2B0], dil
0x1800ad221  jz      loc_1800AD387
0x1800ad227  mov     rax, qword ptr [rbp+290h+var_2AC]
0x1800ad22b  mov     [rsi], rax
0x1800ad22e  mov     rax, qword ptr [rbp+290h+var_2AC+8]
0x1800ad232  mov     [rsi+8], rax
0x1800ad236  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x1800ad23b  mov     rcx, [rbp+290h+string]; string
0x1800ad23f  call    cs:__imp_WindowsDeleteString
0x1800ad246  nop     dword ptr [rax+rax+00h]
0x1800ad24b  mov     rcx, [rbp+290h+var_2B8]; string
0x1800ad24f  mov     [rbp+290h+string], rdi
0x1800ad253  call    cs:__imp_WindowsDeleteString
0x1800ad25a  nop     dword ptr [rax+rax+00h]
0x1800ad25f  mov     ebx, edi
0x1800ad261  jmp     loc_1800AD42C
0x1800ad266  cmp     ebx, 80070002h
0x1800ad26c  jnz     loc_1800AD3D0
0x1800ad272  lea     rcx, [rbp+290h+var_280]; this
0x1800ad276  call    ??0ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::ComClassRegistrationEntryProperties(void)
0x1800ad27b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800ad282  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800ad287  lea     rcx, [r13-18h]; this
0x1800ad28b  mov     dl, al
0x1800ad28d  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800ad292  mov     rcx, [rbp+290h+string]; string
0x1800ad296  mov     r15b, al
0x1800ad299  test    dl, dl
0x1800ad29b  jz      short loc_1800AD2F8
0x1800ad29d  mov     bl, [r13+20h]
0x1800ad2a1  mov     rdi, qword ptr [rbp+290h+var_308]
0x1800ad2a5  call    cs:__imp_WindowsDeleteString
0x1800ad2ac  nop     dword ptr [rax+rax+00h]
0x1800ad2b1  xor     eax, eax
0x1800ad2b3  mov     [rsp+3A0h+var_358], r15b
0x1800ad2b8  mov     byte ptr [rsp+3A0h+var_360], bl
0x1800ad2bc  lea     rdx, [rbp+290h+string]
0x1800ad2c0  mov     [rbp+290h+string], rax
0x1800ad2c4  lea     rcx, [rbp+290h+var_280]
0x1800ad2c8  mov     [rbp+290h+var_300], rax
0x1800ad2cc  lea     rax, [rbp+290h+var_300]
0x1800ad2d0  mov     [rsp+3A0h+var_368], rax
0x1800ad2d5  mov     [rsp+3A0h+var_370], r14
0x1800ad2da  mov     [rsp+3A0h+var_378], rdi
0x1800ad2df  call    ??$DoPackageAwareLookup@UComClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComClassRegistrationEntryProperties const &,bool &)>(ComClassRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComClassRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800ad2e4  xor     ecx, ecx; string
0x1800ad2e6  mov     ebx, eax
0x1800ad2e8  call    cs:__imp_WindowsDeleteString
0x1800ad2ef  nop     dword ptr [rax+rax+00h]
0x1800ad2f4  xor     edi, edi
0x1800ad2f6  jmp     short loc_1800AD35A
0x1800ad2f8  mov     rbx, qword ptr [rbp+290h+var_308]
0x1800ad2fc  call    cs:__imp_WindowsDeleteString
0x1800ad303  nop     dword ptr [rax+rax+00h]
0x1800ad308  mov     [rbp+290h+string], rdi
0x1800ad30c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800ad313  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800ad318  test    al, al
0x1800ad31a  jz      short loc_1800AD321
0x1800ad31c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ad321  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x1800ad328  mov     dword ptr [rbp+290h+var_300], edi
0x1800ad32b  mov     [rsp+3A0h+var_360], rax
0x1800ad330  lea     r8, [rbp+290h+var_300]
0x1800ad334  mov     [rsp+3A0h+var_368], rdi
0x1800ad339  lea     rdx, [rbp+290h+string]
0x1800ad33d  mov     byte ptr [rsp+3A0h+var_370], r15b
0x1800ad342  lea     rcx, [rbp+290h+var_280]
0x1800ad346  mov     [rsp+3A0h+var_378], r14
0x1800ad34b  xor     r9d, r9d
0x1800ad34e  mov     qword ptr [rsp+3A0h+var_380], rbx
0x1800ad353  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComClassRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComClassRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComClassRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComClassRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>(ComClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComClassRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComClassRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *)>(ComClassRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComClassRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x1800ad358  mov     ebx, eax
0x1800ad35a  lea     rcx, [rbp+290h+var_280]; this
0x1800ad35e  test    ebx, ebx
0x1800ad360  js      short loc_1800AD3B7
0x1800ad362  cmp     [rbp+290h+var_228], dil
0x1800ad366  jz      short loc_1800AD37E
0x1800ad368  movups  xmm0, [rbp+290h+var_224]
0x1800ad36c  movdqu  xmmword ptr [rsi], xmm0
0x1800ad370  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800ad375  lea     rcx, [rbp+290h+var_2F8]
0x1800ad379  jmp     loc_1800AD236
0x1800ad37e  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800ad383  lea     rcx, [rbp+290h+var_2F8]; this
0x1800ad387  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x1800ad38c  mov     rcx, [rbp+290h+string]; string
0x1800ad390  call    cs:__imp_WindowsDeleteString
0x1800ad397  nop     dword ptr [rax+rax+00h]
0x1800ad39c  mov     rcx, [rbp+290h+var_2B8]; string
0x1800ad3a0  mov     [rbp+290h+string], rdi
0x1800ad3a4  call    cs:__imp_WindowsDeleteString
0x1800ad3ab  nop     dword ptr [rax+rax+00h]
0x1800ad3b0  mov     ebx, 80040152h
0x1800ad3b5  jmp     short loc_1800AD42C
0x1800ad3b7  call    ??1ComClassRegistrationEntryProperties@@QEAA@XZ; ComClassRegistrationEntryProperties::~ComClassRegistrationEntryProperties(void)
0x1800ad3bc  cmp     ebx, 80070002h
0x1800ad3c2  jnz     short loc_1800AD3D0
0x1800ad3c4  mov     ebx, 80040154h
0x1800ad3c9  mov     edx, 0BB4h
0x1800ad3ce  jmp     short loc_1800AD3E9
0x1800ad3d0  cmp     ebx, 8007000Dh
0x1800ad3d6  jnz     short loc_1800AD3E4
0x1800ad3d8  mov     ebx, 80040153h
0x1800ad3dd  mov     edx, 0BB5h
0x1800ad3e2  jmp     short loc_1800AD3E9
0x1800ad3e4  mov     edx, 0BB6h; void *
0x1800ad3e9  mov     rcx, [rbp+298h]; this
0x1800ad3f0  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ad3f7  mov     r9d, ebx; char *
0x1800ad3fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ad3ff  lea     rcx, [rbp+290h+var_2F8]; this
0x1800ad403  call    ??1PackageFilter@@QEAA@XZ; PackageFilter::~PackageFilter(void)
0x1800ad408  mov     rcx, [rbp+290h+string]; string
0x1800ad40c  call    cs:__imp_WindowsDeleteString
0x1800ad413  nop     dword ptr [rax+rax+00h]
0x1800ad418  mov     rcx, [rbp+290h+var_2B8]; string
0x1800ad41c  mov     [rbp+290h+string], rdi
0x1800ad420  call    cs:__imp_WindowsDeleteString
0x1800ad427  nop     dword ptr [rax+rax+00h]
0x1800ad42c  mov     [rbp+290h+var_2B8], rdi
0x1800ad430  lea     rcx, [rbp+290h+var_308]
0x1800ad434  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ad439  mov     eax, ebx
0x1800ad43b  mov     rcx, [rbp+290h+var_40]
0x1800ad442  xor     rcx, rsp; StackCookie
0x1800ad445  call    __security_check_cookie
0x1800ad44a  mov     rbx, [rsp+3A0h+arg_18]
0x1800ad452  add     rsp, 370h
0x1800ad459  pop     r15
0x1800ad45b  pop     r14
0x1800ad45d  pop     r13
0x1800ad45f  pop     r12
0x1800ad461  pop     rdi
0x1800ad462  pop     rsi
0x1800ad463  pop     rbp
0x1800ad464  retn
```
