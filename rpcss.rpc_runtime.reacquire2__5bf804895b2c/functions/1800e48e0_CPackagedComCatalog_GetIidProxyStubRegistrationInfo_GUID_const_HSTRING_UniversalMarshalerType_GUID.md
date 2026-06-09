# CPackagedComCatalog::GetIidProxyStubRegistrationInfo(_GUID const &,HSTRING__ * *,UniversalMarshalerType *,_GUID *)

- ea: `0x1800e48e0`
- end: `0x1800e4ca5`
- name: `?GetIidProxyStubRegistrationInfo@CPackagedComCatalog@@UEAAJAEBU_GUID@@PEAPEAUHSTRING__@@PEAW4UniversalMarshalerType@@PEAU2@@Z`
- size: `965`
- prototype: `int(CPackagedComCatalog *__hidden this, const struct _GUID *, HSTRING *, enum UniversalMarshalerType *, struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800065a4`
- `0x1800210f8`
- `0x18002750c`
- `0x18004ab7c`
- `0x18004ac08`
- `0x180061d74`
- `0x1800aa2ac`
- `0x1800b7ac0`
- `0x1800daf24`
- `0x1800e48e0`
- `0x1800e7404`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e49fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ad8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4c4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4c60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e49fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ac4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4ad8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b25`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4c4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4c60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4bd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4bd9`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800e4949`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800e4949`

## string_xrefs

- `0x1800e4962`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e4af9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e4b88`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e4bec`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
0x1800e48e0  mov     [rsp-8+arg_0], rbx
0x1800e48e5  push    rbp
0x1800e48e6  push    rsi
0x1800e48e7  push    rdi
0x1800e48e8  push    r12
0x1800e48ea  push    r13
0x1800e48ec  push    r14
0x1800e48ee  push    r15
0x1800e48f0  lea     rbp, [rsp-70h]
0x1800e48f5  sub     rsp, 180h
0x1800e48fc  mov     rax, cs:__security_cookie
0x1800e4903  xor     rax, rsp
0x1800e4906  mov     [rbp+0A0h+var_40], rax
0x1800e490a  mov     rax, [rbp+0A0h+arg_20]
0x1800e4911  mov     rdi, rcx
0x1800e4914  xor     r14d, r14d
0x1800e4917  mov     [rbp+0A0h+var_108], rax
0x1800e491b  lea     rcx, [rbp+0A0h+var_118]
0x1800e491f  mov     [rbp+0A0h+var_118], r14
0x1800e4923  mov     r13, r9
0x1800e4926  mov     r12, r8
0x1800e4929  mov     rsi, rdx
0x1800e492c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e4931  xor     edx, edx
0x1800e4933  lea     rax, [rbp+0A0h+var_118]
0x1800e4937  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800e493e  mov     [rsp+1B0h+var_190], rax; int
0x1800e4943  xor     r8d, r8d
0x1800e4946  lea     ecx, [rdx+1]
0x1800e4949  call    cs:__imp_RoGetRegistrationStoreContext
0x1800e4950  nop     dword ptr [rax+rax+00h]
0x1800e4955  mov     ebx, eax
0x1800e4957  test    eax, eax
0x1800e4959  jns     short loc_1800E497B
0x1800e495b  mov     rcx, [rbp+0A8h]; this
0x1800e4962  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e4969  mov     r9d, eax; char *
0x1800e496c  mov     edx, 0A2Ah; void *
0x1800e4971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4976  jmp     loc_1800E4C72
0x1800e497b  xorps   xmm0, xmm0
0x1800e497e  mov     [rbp+0A0h+var_D0], r14w
0x1800e4983  xorps   xmm1, xmm1
0x1800e4986  mov     [rbp+0A0h+var_CC], r14b
0x1800e498a  movups  [rbp+0A0h+var_C8], xmm0
0x1800e498e  mov     [rbp+0A0h+var_B8], r14b
0x1800e4992  movups  [rbp+0A0h+var_B4], xmm1
0x1800e4996  mov     [rbp+0A0h+var_A4], r14b
0x1800e499a  movups  [rbp+0A0h+var_A0], xmm0
0x1800e499e  mov     [rbp+0A0h+var_90], r14b
0x1800e49a2  movups  [rbp+0A0h+var_8C], xmm1
0x1800e49a6  mov     [rbp+0A0h+var_78], r14b
0x1800e49aa  mov     [rbp+0A0h+var_70], r14
0x1800e49ae  mov     [rbp+0A0h+var_68], r14w
0x1800e49b3  mov     [rbp+0A0h+var_64], r14b
0x1800e49b7  mov     [rbp+0A0h+var_60], r14d
0x1800e49bb  mov     [rbp+0A0h+var_5C], r14b
0x1800e49bf  mov     [rbp+0A0h+var_58], r14d
0x1800e49c3  mov     [rbp+0A0h+var_54], r14b
0x1800e49c7  mov     [rbp+0A0h+var_50], r14d
0x1800e49cb  mov     [rbp+0A0h+string], r14
0x1800e49cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800e49d6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800e49db  lea     r14, [rdi-10h]
0x1800e49df  mov     dl, al
0x1800e49e1  mov     rcx, r14; this
0x1800e49e4  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800e49e9  mov     rcx, [rbp+0A0h+string]; string
0x1800e49ed  mov     r15b, al
0x1800e49f0  test    dl, dl
0x1800e49f2  jz      short loc_1800E4A6D
0x1800e49f4  mov     bl, [rdi+28h]
0x1800e49f7  mov     rdi, [rbp+0A0h+var_118]
0x1800e49fb  call    cs:__imp_WindowsDeleteString
0x1800e4a02  nop     dword ptr [rax+rax+00h]
0x1800e4a07  lea     rax, [rbp+0A0h+var_118]
0x1800e4a0b  mov     [rbp+0A0h+string], 0
0x1800e4a13  mov     [rbp+0A0h+var_E0], rax
0x1800e4a17  lea     rdx, [rbp+0A0h+string]
0x1800e4a1b  lea     rax, [rbp+0A0h+var_F0]
0x1800e4a1f  mov     [rbp+0A0h+Token], 0
0x1800e4a27  mov     [rsp+1B0h+var_158], rax
0x1800e4a2c  lea     rcx, [rbp+0A0h+var_D0]
0x1800e4a30  mov     [rsp+1B0h+var_168], r15b
0x1800e4a35  lea     rax, [rbp+0A0h+Token]
0x1800e4a39  mov     [rsp+1B0h+var_170], bl
0x1800e4a3d  mov     [rsp+1B0h+var_178], rax
0x1800e4a42  mov     [rsp+1B0h+var_180], rsi
0x1800e4a47  mov     [rsp+1B0h+var_188], rdi
0x1800e4a4c  mov     [rbp+0A0h+var_F0], rsi
0x1800e4a50  mov     [rbp+0A0h+var_E8], r14
0x1800e4a54  call    ??$DoPackageAwareLookup@UComInterfaceRegistrationEntryProperties@@V_lambda_853bd4202750da7ac9a2e6d1063c32c0_@@@EntryLookup@CPackagedComCatalog@@SAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@V_lambda_853bd4202750da7ac9a2e6d1063c32c0_@@PEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,_lambda_853bd4202750da7ac9a2e6d1063c32c0_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,_lambda_853bd4202750da7ac9a2e6d1063c32c0_,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800e4a59  xor     ecx, ecx; string
0x1800e4a5b  mov     ebx, eax
0x1800e4a5d  call    cs:__imp_WindowsDeleteString
0x1800e4a64  nop     dword ptr [rax+rax+00h]
0x1800e4a69  xor     edi, edi
0x1800e4a6b  jmp     short loc_1800E4AB8
0x1800e4a6d  mov     rbx, [rbp+0A0h+var_118]
0x1800e4a71  call    cs:__imp_WindowsDeleteString
0x1800e4a78  nop     dword ptr [rax+rax+00h]
0x1800e4a7d  lea     rax, [rbp+0A0h+var_118]
0x1800e4a81  mov     [rbp+0A0h+var_F0], rsi
0x1800e4a85  mov     [rbp+0A0h+var_E0], rax
0x1800e4a89  lea     rdx, [rbp+0A0h+string]
0x1800e4a8d  lea     rax, [rbp+0A0h+var_F0]
0x1800e4a91  mov     [rbp+0A0h+var_E8], r14
0x1800e4a95  mov     [rsp+1B0h+var_178], rax
0x1800e4a9a  lea     rcx, [rbp+0A0h+var_D0]
0x1800e4a9e  xor     edi, edi
0x1800e4aa0  mov     byte ptr [rsp+1B0h+var_188], r15b
0x1800e4aa5  mov     r9, rbx
0x1800e4aa8  mov     [rsp+1B0h+var_190], rsi; int
0x1800e4aad  mov     [rbp+0A0h+string], rdi
0x1800e4ab1  call    ??$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@V_lambda_027c0d8e07d338be82b33330958a4219_@@@CPackagedComCatalog@@CAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_027c0d8e07d338be82b33330958a4219_@@@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_027c0d8e07d338be82b33330958a4219_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_027c0d8e07d338be82b33330958a4219_)
0x1800e4ab6  mov     ebx, eax
0x1800e4ab8  cmp     ebx, 80070002h
0x1800e4abe  jnz     short loc_1800E4AEE
0x1800e4ac0  mov     rcx, [rbp+0A0h+string]; string
0x1800e4ac4  call    cs:__imp_WindowsDeleteString
0x1800e4acb  nop     dword ptr [rax+rax+00h]
0x1800e4ad0  mov     rcx, [rbp+0A0h+var_70]; string
0x1800e4ad4  mov     [rbp+0A0h+string], rdi
0x1800e4ad8  call    cs:__imp_WindowsDeleteString
0x1800e4adf  nop     dword ptr [rax+rax+00h]
0x1800e4ae4  mov     ebx, 80040155h
0x1800e4ae9  jmp     loc_1800E4C6E
0x1800e4aee  test    ebx, ebx
0x1800e4af0  jns     short loc_1800E4B36
0x1800e4af2  mov     rcx, [rbp+0A8h]; this
0x1800e4af9  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e4b00  mov     r9d, ebx; char *
0x1800e4b03  mov     edx, 0A71h; void *
0x1800e4b08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4b0d  mov     rcx, [rbp+0A0h+string]; string
0x1800e4b11  call    cs:__imp_WindowsDeleteString
0x1800e4b18  nop     dword ptr [rax+rax+00h]
0x1800e4b1d  mov     rcx, [rbp+0A0h+var_70]; string
0x1800e4b21  mov     [rbp+0A0h+string], rdi
0x1800e4b25  call    cs:__imp_WindowsDeleteString
0x1800e4b2c  nop     dword ptr [rax+rax+00h]
0x1800e4b31  jmp     loc_1800E4C6E
0x1800e4b36  cmp     byte ptr [rbp+0A0h+var_D0], dil
0x1800e4b3a  jz      loc_1800E4C1C
0x1800e4b40  cmp     byte ptr [rbp+0A0h+var_D0+1], dil
0x1800e4b44  jz      loc_1800E4C1C
0x1800e4b4a  xor     ecx, ecx; string
0x1800e4b4c  call    cs:__imp_WindowsDeleteString
0x1800e4b53  nop     dword ptr [rax+rax+00h]
0x1800e4b58  mov     r8, [rbp+0A0h+var_118]; struct IPackagedComCatalogContext *
0x1800e4b5c  lea     rax, [rbp+0A0h+var_110]
0x1800e4b60  lea     r9, [rbp+0A0h+string]; struct OpaqueString *
0x1800e4b64  mov     [rsp+1B0h+var_190], rax; int
0x1800e4b69  lea     rdx, [rbp+0A0h+var_D0]; struct ComInterfaceRegistrationEntryProperties *
0x1800e4b6d  mov     [rbp+0A0h+var_110], rdi
0x1800e4b71  call    ?GetTypeLibPathForInterface@CPackagedComCatalog@@QEAAJAEBUComInterfaceRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@PEAPEAUHSTRING__@@@Z; CPackagedComCatalog::GetTypeLibPathForInterface(ComInterfaceRegistrationEntryProperties const &,IPackagedComCatalogContext *,OpaqueString const &,HSTRING__ * *)
0x1800e4b76  mov     ebx, eax
0x1800e4b78  test    eax, eax
0x1800e4b7a  jns     short loc_1800E4BAC
0x1800e4b7c  mov     edx, 0A7Ah; void *
0x1800e4b81  mov     rcx, [rbp+0A8h]; this
0x1800e4b88  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e4b8f  mov     r9d, eax; char *
0x1800e4b92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4b97  mov     rcx, [rbp+0A0h+var_110]; string
0x1800e4b9b  call    cs:__imp_WindowsDeleteString
0x1800e4ba2  nop     dword ptr [rax+rax+00h]
0x1800e4ba7  jmp     loc_1800E4B0D
0x1800e4bac  lea     rcx, [rbp+0A0h+Token]; TokenHandle
0x1800e4bb0  mov     [rbp+0A0h+Token], rdi
0x1800e4bb4  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x1800e4bb9  mov     ebx, eax
0x1800e4bbb  test    eax, eax
0x1800e4bbd  jns     short loc_1800E4BC6
0x1800e4bbf  mov     edx, 0A7Dh
0x1800e4bc4  jmp     short loc_1800E4B81
0x1800e4bc6  lea     rcx, [rbp+0A0h+var_108]
0x1800e4bca  mov     [rbp+0A0h+var_108], rdi
0x1800e4bce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e4bd3  mov     rcx, [rbp+0A0h+var_110]; string
0x1800e4bd7  xor     edx, edx; length
0x1800e4bd9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4be0  nop     dword ptr [rax+rax+00h]
0x1800e4be5  mov     rcx, [rbp+0A8h]; this
0x1800e4bec  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e4bf3  mov     ebx, 8000FFFFh
0x1800e4bf8  mov     edx, 0A81h; void *
0x1800e4bfd  mov     r9d, ebx; char *
0x1800e4c00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e4c05  lea     rcx, [rbp+0A0h+var_108]
0x1800e4c09  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e4c0e  mov     rcx, [rbp+0A0h+Token]; Token
0x1800e4c12  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x1800e4c17  jmp     loc_1800E4B97
0x1800e4c1c  mov     rax, [rbp+0A0h+string]
0x1800e4c20  lea     rcx, GUID_NULL
0x1800e4c27  cmp     [rbp+0A0h+var_CC], dil
0x1800e4c2b  mov     [r13+0], edi
0x1800e4c2f  mov     [r12], rax
0x1800e4c33  lea     rax, [rbp+0A0h+var_C8]
0x1800e4c37  cmovz   rax, rcx
0x1800e4c3b  mov     [rbp+0A0h+string], rdi
0x1800e4c3f  xor     ecx, ecx; string
0x1800e4c41  movups  xmm0, xmmword ptr [rax]
0x1800e4c44  mov     rax, [rbp+0A0h+var_108]
0x1800e4c48  movdqu  xmmword ptr [rax], xmm0
0x1800e4c4c  call    cs:__imp_WindowsDeleteString
0x1800e4c53  nop     dword ptr [rax+rax+00h]
0x1800e4c58  mov     rcx, [rbp+0A0h+var_70]; string
0x1800e4c5c  mov     [rbp+0A0h+string], rdi
0x1800e4c60  call    cs:__imp_WindowsDeleteString
0x1800e4c67  nop     dword ptr [rax+rax+00h]
0x1800e4c6c  mov     ebx, edi
0x1800e4c6e  mov     [rbp+0A0h+var_70], rdi
0x1800e4c72  lea     rcx, [rbp+0A0h+var_118]
0x1800e4c76  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e4c7b  mov     eax, ebx
0x1800e4c7d  mov     rcx, [rbp+0A0h+var_40]
0x1800e4c81  xor     rcx, rsp; StackCookie
0x1800e4c84  call    __security_check_cookie
0x1800e4c89  mov     rbx, [rsp+1B0h+arg_0]
0x1800e4c91  add     rsp, 180h
0x1800e4c98  pop     r15
0x1800e4c9a  pop     r14
0x1800e4c9c  pop     r13
0x1800e4c9e  pop     r12
0x1800e4ca0  pop     rdi
0x1800e4ca1  pop     rsi
0x1800e4ca2  pop     rbp
0x1800e4ca3  retn
```
