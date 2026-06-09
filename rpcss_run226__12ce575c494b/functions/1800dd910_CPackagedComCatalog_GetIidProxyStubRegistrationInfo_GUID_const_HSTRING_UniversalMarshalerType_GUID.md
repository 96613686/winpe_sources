# CPackagedComCatalog::GetIidProxyStubRegistrationInfo(_GUID const &,HSTRING__ * *,UniversalMarshalerType *,_GUID *)

- ea: `0x1800dd910`
- end: `0x1800ddc83`
- name: `?GetIidProxyStubRegistrationInfo@CPackagedComCatalog@@UEAAJAEBU_GUID@@PEAPEAUHSTRING__@@PEAW4UniversalMarshalerType@@PEAU2@@Z`
- size: `883`
- prototype: `int(CPackagedComCatalog *__hidden this, const struct _GUID *, HSTRING *, enum UniversalMarshalerType *, struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005c40`
- `0x18000d4c4`
- `0x18002ba28`
- `0x18004105c`
- `0x1800410d4`
- `0x18005ced0`
- `0x1800a52a8`
- `0x1800b27e0`
- `0x1800d4530`
- `0x1800dd910`
- `0x1800e022c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dda25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dda81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dda8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddadc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddaea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddc37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddc45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dda25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dda81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dda8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddadc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddaea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddc37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ddc45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ddbcd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ddbcd`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800dd979`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800dd979`

## string_xrefs

- `0x1800dd98c`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ddb05`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ddb82`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ddbda`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetIidProxyStubRegistrationInfo(
        CPackagedComCatalog *this,
        const struct _GUID *a2,
        HSTRING *a3,
        enum UniversalMarshalerType *a4,
        struct _GUID *a5)
{
  int RegistrationStoreContext; // eax
  int Entry; // ebx
  char *v11; // r14
  char IsUserHiveOk; // r15
  char v13; // dl
  char v14; // bl
  struct IPackagedComCatalogContext *v15; // rdi
  int v16; // r8d
  int v17; // r9d
  int v18; // ebx
  int v19; // r8d
  CPackagedComCatalog *v20; // rcx
  int TypeLibPathForInterface; // eax
  __int64 v22; // rdx
  HSTRING v23; // rax
  bool v24; // zf
  GUID *v25; // rax
  int v27; // [rsp+20h] [rbp-F0h]
  int v28; // [rsp+20h] [rbp-F0h]
  HSTRING string; // [rsp+90h] [rbp-80h] BYREF
  struct IPackagedComCatalogContext *v30; // [rsp+98h] [rbp-78h] BYREF
  HSTRING v31; // [rsp+A0h] [rbp-70h] BYREF
  struct _GUID *v32; // [rsp+A8h] [rbp-68h] BYREF
  HANDLE Token[2]; // [rsp+B0h] [rbp-60h] BYREF
  const struct _GUID *v34; // [rsp+C0h] [rbp-50h]
  char *v35; // [rsp+C8h] [rbp-48h]
  struct IPackagedComCatalogContext **v36; // [rsp+D0h] [rbp-40h]
  _WORD v37[2]; // [rsp+E0h] [rbp-30h] BYREF
  char v38; // [rsp+E4h] [rbp-2Ch]
  __int128 v39; // [rsp+E8h] [rbp-28h] BYREF
  char v40; // [rsp+F8h] [rbp-18h]
  __int128 v41; // [rsp+FCh] [rbp-14h]
  char v42; // [rsp+10Ch] [rbp-4h]
  __int128 v43; // [rsp+110h] [rbp+0h]
  char v44; // [rsp+120h] [rbp+10h]
  __int128 v45; // [rsp+124h] [rbp+14h]
  char v46; // [rsp+138h] [rbp+28h]
  HSTRING v47; // [rsp+140h] [rbp+30h]
  __int16 v48; // [rsp+148h] [rbp+38h]
  char v49; // [rsp+14Ch] [rbp+3Ch]
  int v50; // [rsp+150h] [rbp+40h]
  char v51; // [rsp+154h] [rbp+44h]
  int v52; // [rsp+158h] [rbp+48h]
  char v53; // [rsp+15Ch] [rbp+4Ch]
  int v54; // [rsp+160h] [rbp+50h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+A8h]

  v32 = a5;
  v30 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, 0, 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
  Entry = RegistrationStoreContext;
  if ( RegistrationStoreContext >= 0 )
  {
    v37[0] = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v53 = 0;
    v54 = 0;
    string = 0;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    v11 = (char *)this - 16;
    IsUserHiveOk = CPackagedComCatalog::IsUserHiveOk((CPackagedComCatalog *)((char *)this - 16));
    if ( v13 )
    {
      v14 = *((_BYTE *)this + 40);
      v15 = v30;
      WindowsDeleteString(0);
      string = 0;
      v36 = &v30;
      Token[0] = 0;
      v34 = a2;
      v35 = v11;
      Entry = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,_lambda_853bd4202750da7ac9a2e6d1063c32c0_>(
                (unsigned int)v37,
                (unsigned int)&string,
                v16,
                v17,
                (unsigned int)&v30,
                (__int64)v15,
                (__int64)a2,
                (__int64)Token,
                v14,
                IsUserHiveOk);
      WindowsDeleteString(0);
    }
    else
    {
      v18 = (int)v30;
      WindowsDeleteString(0);
      v34 = a2;
      v36 = &v30;
      v35 = (char *)this - 16;
      string = 0;
      Entry = CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_027c0d8e07d338be82b33330958a4219_>(
                (unsigned int)v37,
                (unsigned int)&string,
                v19,
                v18,
                (__int64)a2,
                IsUserHiveOk);
    }
    if ( Entry == -2147024894 )
    {
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v47);
      Entry = -2147221163;
LABEL_23:
      v47 = 0;
      goto LABEL_24;
    }
    if ( Entry < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA71,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)(unsigned int)Entry,
        v27);
LABEL_10:
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v47);
      goto LABEL_23;
    }
    if ( !LOBYTE(v37[0]) || !HIBYTE(v37[0]) )
    {
      v23 = string;
      v24 = v38 == 0;
      *(_DWORD *)a4 = 0;
      *a3 = v23;
      v25 = (GUID *)&v39;
      if ( v24 )
        v25 = &GUID_NULL;
      string = 0;
      *v32 = *v25;
      WindowsDeleteString(0);
      string = 0;
      WindowsDeleteString(v47);
      Entry = 0;
      goto LABEL_23;
    }
    WindowsDeleteString(0);
    v31 = 0;
    TypeLibPathForInterface = CPackagedComCatalog::GetTypeLibPathForInterface(
                                v20,
                                (const struct ComInterfaceRegistrationEntryProperties *)v37,
                                v30,
                                (const struct OpaqueString *)&string,
                                &v31);
    Entry = TypeLibPathForInterface;
    if ( TypeLibPathForInterface >= 0 )
    {
      Token[0] = 0;
      TypeLibPathForInterface = SuspendImpersonate(Token);
      Entry = TypeLibPathForInterface;
      if ( TypeLibPathForInterface >= 0 )
      {
        v32 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        WindowsGetStringRawBuffer(v31, 0);
        Entry = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA81,
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (const char *)0x8000FFFFLL,
          v28);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
        ResumeImpersonate(Token[0]);
        goto LABEL_16;
      }
      v22 = 2685;
    }
    else
    {
      v22 = 2682;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
      (const char *)(unsigned int)TypeLibPathForInterface,
      v28);
LABEL_16:
    WindowsDeleteString(v31);
    goto LABEL_10;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA2A,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)RegistrationStoreContext,
    (int)&v30);
LABEL_24:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x1800dd910  mov     [rsp-8+arg_0], rbx
0x1800dd915  push    rbp
0x1800dd916  push    rsi
0x1800dd917  push    rdi
0x1800dd918  push    r12
0x1800dd91a  push    r13
0x1800dd91c  push    r14
0x1800dd91e  push    r15
0x1800dd920  lea     rbp, [rsp-70h]
0x1800dd925  sub     rsp, 180h
0x1800dd92c  mov     rax, cs:__security_cookie
0x1800dd933  xor     rax, rsp
0x1800dd936  mov     [rbp+0A0h+var_40], rax
0x1800dd93a  mov     rax, [rbp+0A0h+arg_20]
0x1800dd941  mov     rdi, rcx
0x1800dd944  xor     r14d, r14d
0x1800dd947  mov     [rbp+0A0h+var_108], rax
0x1800dd94b  lea     rcx, [rbp+0A0h+var_118]
0x1800dd94f  mov     [rbp+0A0h+var_118], r14
0x1800dd953  mov     r13, r9
0x1800dd956  mov     r12, r8
0x1800dd959  mov     rsi, rdx
0x1800dd95c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dd961  xor     edx, edx
0x1800dd963  lea     rax, [rbp+0A0h+var_118]
0x1800dd967  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800dd96e  mov     [rsp+1B0h+var_190], rax; int
0x1800dd973  xor     r8d, r8d
0x1800dd976  lea     ecx, [rdx+1]
0x1800dd979  call    cs:__imp_RoGetRegistrationStoreContext
0x1800dd97f  mov     ebx, eax
0x1800dd981  test    eax, eax
0x1800dd983  jns     short loc_1800DD9A5
0x1800dd985  mov     rcx, [rbp+0A8h]; this
0x1800dd98c  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dd993  mov     r9d, eax; char *
0x1800dd996  mov     edx, 0A2Ah; void *
0x1800dd99b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dd9a0  jmp     loc_1800DDC51
0x1800dd9a5  xorps   xmm0, xmm0
0x1800dd9a8  mov     [rbp+0A0h+var_D0], r14w
0x1800dd9ad  xorps   xmm1, xmm1
0x1800dd9b0  mov     [rbp+0A0h+var_CC], r14b
0x1800dd9b4  movups  [rbp+0A0h+var_C8], xmm0
0x1800dd9b8  mov     [rbp+0A0h+var_B8], r14b
0x1800dd9bc  movups  [rbp+0A0h+var_B4], xmm1
0x1800dd9c0  mov     [rbp+0A0h+var_A4], r14b
0x1800dd9c4  movups  [rbp+0A0h+var_A0], xmm0
0x1800dd9c8  mov     [rbp+0A0h+var_90], r14b
0x1800dd9cc  movups  [rbp+0A0h+var_8C], xmm1
0x1800dd9d0  mov     [rbp+0A0h+var_78], r14b
0x1800dd9d4  mov     [rbp+0A0h+var_70], r14
0x1800dd9d8  mov     [rbp+0A0h+var_68], r14w
0x1800dd9dd  mov     [rbp+0A0h+var_64], r14b
0x1800dd9e1  mov     [rbp+0A0h+var_60], r14d
0x1800dd9e5  mov     [rbp+0A0h+var_5C], r14b
0x1800dd9e9  mov     [rbp+0A0h+var_58], r14d
0x1800dd9ed  mov     [rbp+0A0h+var_54], r14b
0x1800dd9f1  mov     [rbp+0A0h+var_50], r14d
0x1800dd9f5  mov     [rbp+0A0h+string], r14
0x1800dd9f9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800dda00  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800dda05  lea     r14, [rdi-10h]
0x1800dda09  mov     dl, al
0x1800dda0b  mov     rcx, r14; this
0x1800dda0e  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800dda13  mov     rcx, [rbp+0A0h+string]; string
0x1800dda17  mov     r15b, al
0x1800dda1a  test    dl, dl
0x1800dda1c  jz      short loc_1800DDA8B
0x1800dda1e  mov     bl, [rdi+28h]
0x1800dda21  mov     rdi, [rbp+0A0h+var_118]
0x1800dda25  call    cs:__imp_WindowsDeleteString
0x1800dda2b  lea     rax, [rbp+0A0h+var_118]
0x1800dda2f  mov     [rbp+0A0h+string], 0
0x1800dda37  mov     [rbp+0A0h+var_E0], rax
0x1800dda3b  lea     rdx, [rbp+0A0h+string]
0x1800dda3f  lea     rax, [rbp+0A0h+var_F0]
0x1800dda43  mov     [rbp+0A0h+Token], 0
0x1800dda4b  mov     [rsp+1B0h+var_158], rax
0x1800dda50  lea     rcx, [rbp+0A0h+var_D0]
0x1800dda54  mov     [rsp+1B0h+var_168], r15b
0x1800dda59  lea     rax, [rbp+0A0h+Token]
0x1800dda5d  mov     [rsp+1B0h+var_170], bl
0x1800dda61  mov     [rsp+1B0h+var_178], rax
0x1800dda66  mov     [rsp+1B0h+var_180], rsi
0x1800dda6b  mov     [rsp+1B0h+var_188], rdi
0x1800dda70  mov     [rbp+0A0h+var_F0], rsi
0x1800dda74  mov     [rbp+0A0h+var_E8], r14
0x1800dda78  call    ??$DoPackageAwareLookup@UComInterfaceRegistrationEntryProperties@@V_lambda_853bd4202750da7ac9a2e6d1063c32c0_@@@EntryLookup@CPackagedComCatalog@@SAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@V_lambda_853bd4202750da7ac9a2e6d1063c32c0_@@PEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,_lambda_853bd4202750da7ac9a2e6d1063c32c0_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,_lambda_853bd4202750da7ac9a2e6d1063c32c0_,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800dda7d  xor     ecx, ecx; string
0x1800dda7f  mov     ebx, eax
0x1800dda81  call    cs:__imp_WindowsDeleteString
0x1800dda87  xor     edi, edi
0x1800dda89  jmp     short loc_1800DDAD0
0x1800dda8b  mov     rbx, [rbp+0A0h+var_118]
0x1800dda8f  call    cs:__imp_WindowsDeleteString
0x1800dda95  lea     rax, [rbp+0A0h+var_118]
0x1800dda99  mov     [rbp+0A0h+var_F0], rsi
0x1800dda9d  mov     [rbp+0A0h+var_E0], rax
0x1800ddaa1  lea     rdx, [rbp+0A0h+string]
0x1800ddaa5  lea     rax, [rbp+0A0h+var_F0]
0x1800ddaa9  mov     [rbp+0A0h+var_E8], r14
0x1800ddaad  mov     [rsp+1B0h+var_178], rax
0x1800ddab2  lea     rcx, [rbp+0A0h+var_D0]
0x1800ddab6  xor     edi, edi
0x1800ddab8  mov     byte ptr [rsp+1B0h+var_188], r15b
0x1800ddabd  mov     r9, rbx
0x1800ddac0  mov     [rsp+1B0h+var_190], rsi; int
0x1800ddac5  mov     [rbp+0A0h+string], rdi
0x1800ddac9  call    ??$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@V_lambda_027c0d8e07d338be82b33330958a4219_@@@CPackagedComCatalog@@CAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_027c0d8e07d338be82b33330958a4219_@@@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_027c0d8e07d338be82b33330958a4219_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_027c0d8e07d338be82b33330958a4219_)
0x1800ddace  mov     ebx, eax
0x1800ddad0  cmp     ebx, 80070002h
0x1800ddad6  jnz     short loc_1800DDAFA
0x1800ddad8  mov     rcx, [rbp+0A0h+string]; string
0x1800ddadc  call    cs:__imp_WindowsDeleteString
0x1800ddae2  mov     rcx, [rbp+0A0h+var_70]; string
0x1800ddae6  mov     [rbp+0A0h+string], rdi
0x1800ddaea  call    cs:__imp_WindowsDeleteString
0x1800ddaf0  mov     ebx, 80040155h
0x1800ddaf5  jmp     loc_1800DDC4D
0x1800ddafa  test    ebx, ebx
0x1800ddafc  jns     short loc_1800DDB36
0x1800ddafe  mov     rcx, [rbp+0A8h]; this
0x1800ddb05  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ddb0c  mov     r9d, ebx; char *
0x1800ddb0f  mov     edx, 0A71h; void *
0x1800ddb14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddb19  mov     rcx, [rbp+0A0h+string]; string
0x1800ddb1d  call    cs:__imp_WindowsDeleteString
0x1800ddb23  mov     rcx, [rbp+0A0h+var_70]; string
0x1800ddb27  mov     [rbp+0A0h+string], rdi
0x1800ddb2b  call    cs:__imp_WindowsDeleteString
0x1800ddb31  jmp     loc_1800DDC4D
0x1800ddb36  cmp     byte ptr [rbp+0A0h+var_D0], dil
0x1800ddb3a  jz      loc_1800DDC07
0x1800ddb40  cmp     byte ptr [rbp+0A0h+var_D0+1], dil
0x1800ddb44  jz      loc_1800DDC07
0x1800ddb4a  xor     ecx, ecx; string
0x1800ddb4c  call    cs:__imp_WindowsDeleteString
0x1800ddb52  mov     r8, [rbp+0A0h+var_118]; struct IPackagedComCatalogContext *
0x1800ddb56  lea     rax, [rbp+0A0h+var_110]
0x1800ddb5a  lea     r9, [rbp+0A0h+string]; struct OpaqueString *
0x1800ddb5e  mov     [rsp+1B0h+var_190], rax; int
0x1800ddb63  lea     rdx, [rbp+0A0h+var_D0]; struct ComInterfaceRegistrationEntryProperties *
0x1800ddb67  mov     [rbp+0A0h+var_110], rdi
0x1800ddb6b  call    ?GetTypeLibPathForInterface@CPackagedComCatalog@@QEAAJAEBUComInterfaceRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@PEAPEAUHSTRING__@@@Z; CPackagedComCatalog::GetTypeLibPathForInterface(ComInterfaceRegistrationEntryProperties const &,IPackagedComCatalogContext *,OpaqueString const &,HSTRING__ * *)
0x1800ddb70  mov     ebx, eax
0x1800ddb72  test    eax, eax
0x1800ddb74  jns     short loc_1800DDBA0
0x1800ddb76  mov     edx, 0A7Ah; void *
0x1800ddb7b  mov     rcx, [rbp+0A8h]; this
0x1800ddb82  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ddb89  mov     r9d, eax; char *
0x1800ddb8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddb91  mov     rcx, [rbp+0A0h+var_110]; string
0x1800ddb95  call    cs:__imp_WindowsDeleteString
0x1800ddb9b  jmp     loc_1800DDB19
0x1800ddba0  lea     rcx, [rbp+0A0h+Token]; TokenHandle
0x1800ddba4  mov     [rbp+0A0h+Token], rdi
0x1800ddba8  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1800ddbad  mov     ebx, eax
0x1800ddbaf  test    eax, eax
0x1800ddbb1  jns     short loc_1800DDBBA
0x1800ddbb3  mov     edx, 0A7Dh
0x1800ddbb8  jmp     short loc_1800DDB7B
0x1800ddbba  lea     rcx, [rbp+0A0h+var_108]
0x1800ddbbe  mov     [rbp+0A0h+var_108], rdi
0x1800ddbc2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ddbc7  mov     rcx, [rbp+0A0h+var_110]; string
0x1800ddbcb  xor     edx, edx; length
0x1800ddbcd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ddbd3  mov     rcx, [rbp+0A8h]; this
0x1800ddbda  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ddbe1  mov     ebx, 8000FFFFh
0x1800ddbe6  mov     edx, 0A81h; void *
0x1800ddbeb  mov     r9d, ebx; char *
0x1800ddbee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ddbf3  lea     rcx, [rbp+0A0h+var_108]
0x1800ddbf7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ddbfc  mov     rcx, [rbp+0A0h+Token]; Token
0x1800ddc00  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800ddc05  jmp     short loc_1800DDB91
0x1800ddc07  mov     rax, [rbp+0A0h+string]
0x1800ddc0b  lea     rcx, GUID_NULL
0x1800ddc12  cmp     [rbp+0A0h+var_CC], dil
0x1800ddc16  mov     [r13+0], edi
0x1800ddc1a  mov     [r12], rax
0x1800ddc1e  lea     rax, [rbp+0A0h+var_C8]
0x1800ddc22  cmovz   rax, rcx
0x1800ddc26  mov     [rbp+0A0h+string], rdi
0x1800ddc2a  xor     ecx, ecx; string
0x1800ddc2c  movups  xmm0, xmmword ptr [rax]
0x1800ddc2f  mov     rax, [rbp+0A0h+var_108]
0x1800ddc33  movdqu  xmmword ptr [rax], xmm0
0x1800ddc37  call    cs:__imp_WindowsDeleteString
0x1800ddc3d  mov     rcx, [rbp+0A0h+var_70]; string
0x1800ddc41  mov     [rbp+0A0h+string], rdi
0x1800ddc45  call    cs:__imp_WindowsDeleteString
0x1800ddc4b  mov     ebx, edi
0x1800ddc4d  mov     [rbp+0A0h+var_70], rdi
0x1800ddc51  lea     rcx, [rbp+0A0h+var_118]
0x1800ddc55  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ddc5a  mov     eax, ebx
0x1800ddc5c  mov     rcx, [rbp+0A0h+var_40]
0x1800ddc60  xor     rcx, rsp; StackCookie
0x1800ddc63  call    __security_check_cookie
0x1800ddc68  mov     rbx, [rsp+1B0h+arg_0]
0x1800ddc70  add     rsp, 180h
0x1800ddc77  pop     r15
0x1800ddc79  pop     r14
0x1800ddc7b  pop     r13
0x1800ddc7d  pop     r12
0x1800ddc7f  pop     rdi
0x1800ddc80  pop     rsi
0x1800ddc81  pop     rbp
0x1800ddc82  retn
```
