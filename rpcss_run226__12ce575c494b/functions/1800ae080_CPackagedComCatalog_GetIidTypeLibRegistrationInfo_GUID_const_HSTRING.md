# CPackagedComCatalog::GetIidTypeLibRegistrationInfo(_GUID const &,HSTRING__ * *)

- ea: `0x1800ae080`
- end: `0x1800ae2ee`
- name: `?GetIidTypeLibRegistrationInfo@CPackagedComCatalog@@UEAAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z`
- size: `622`
- prototype: `__int64 __fastcall(CPackagedComCatalog *__hidden this, const struct _GUID *, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180005c40`
- `0x18000d4c4`
- `0x18002ba28`
- `0x18005ced0`
- `0x18008e98c`
- `0x1800ae080`
- `0x1800ae2f4`
- `0x1800b27e0`
- `0x1800d4608`
- `0x1800e022c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae1cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae26e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae183`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae1c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae1cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae233`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae260`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae26e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae2a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ae2ae`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800ae0dd`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800ae0dd`

## string_xrefs

- `0x1800ae0ed`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800ae250`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetIidTypeLibRegistrationInfo(
        CPackagedComCatalog *this,
        struct _GUID *a2,
        HSTRING *a3)
{
  int RegistrationStoreContext; // eax
  int v7; // ebx
  char IsUserHiveOk; // r14
  char v9; // dl
  char v10; // bl
  struct IPackagedComCatalogContext *v11; // rdi
  int v12; // r8d
  int v13; // r9d
  CPackagedComCatalog *v14; // rcx
  struct IPackagedComCatalogContext *v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int TypeLibPathForInterface; // eax
  int v22; // [rsp+20h] [rbp-F0h]
  int v23; // [rsp+38h] [rbp-D8h]
  HSTRING string; // [rsp+90h] [rbp-80h] BYREF
  struct IPackagedComCatalogContext *v25; // [rsp+98h] [rbp-78h] BYREF
  int v26[4]; // [rsp+A0h] [rbp-70h] BYREF
  int v27; // [rsp+B0h] [rbp-60h] BYREF
  char v28; // [rsp+B4h] [rbp-5Ch]
  __int128 v29; // [rsp+B8h] [rbp-58h]
  char v30; // [rsp+C8h] [rbp-48h]
  __int128 v31; // [rsp+CCh] [rbp-44h]
  char v32; // [rsp+DCh] [rbp-34h]
  __int128 v33; // [rsp+E0h] [rbp-30h]
  char v34; // [rsp+F0h] [rbp-20h]
  __int128 v35; // [rsp+F4h] [rbp-1Ch]
  char v36; // [rsp+108h] [rbp-8h]
  HSTRING v37; // [rsp+110h] [rbp+0h]
  __int16 v38; // [rsp+118h] [rbp+8h]
  char v39; // [rsp+11Ch] [rbp+Ch]
  int v40; // [rsp+120h] [rbp+10h]
  char v41; // [rsp+124h] [rbp+14h]
  int v42; // [rsp+128h] [rbp+18h]
  char v43; // [rsp+12Ch] [rbp+1Ch]
  int v44; // [rsp+130h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+68h]

  v25 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, 0, 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
  v7 = RegistrationStoreContext;
  if ( RegistrationStoreContext >= 0 )
  {
    LOWORD(v27) = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    v44 = 0;
    string = 0;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    IsUserHiveOk = CPackagedComCatalog::IsUserHiveOk((CPackagedComCatalog *)((char *)this - 16));
    if ( v9 )
    {
      v10 = *((_BYTE *)this + 40);
      v11 = v25;
      WindowsDeleteString(0);
      string = 0;
      *(_QWORD *)v26 = 0;
      v7 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,_lambda_afaa7c6e0ac8d54089b409b311551717_>(
             (unsigned int)&v27,
             (unsigned int)&string,
             v12,
             v13,
             (unsigned int)&v25,
             (__int64)v11,
             (__int64)a2,
             (__int64)v26,
             v10,
             IsUserHiveOk);
      WindowsDeleteString(0);
    }
    else
    {
      v15 = v25;
      WindowsDeleteString(0);
      string = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v16);
      v26[0] = 0;
      v7 = Z::ResolveAndReadEntryWithCustomRankingOld<ComInterfaceRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_>(
             (__int64)&v27,
             &string,
             v26,
             v17,
             (__int64)v15,
             (__int64)a2,
             IsUserHiveOk,
             v23,
             a2);
    }
    if ( v7 == -2147024894 )
    {
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v37);
      v7 = -2147319779;
    }
    else
    {
      if ( v7 >= 0 )
      {
        TypeLibPathForInterface = CPackagedComCatalog::GetTypeLibPathForInterface(
                                    v14,
                                    (const struct ComInterfaceRegistrationEntryProperties *)&v27,
                                    v25,
                                    (const struct OpaqueString *)&string,
                                    a3);
        v7 = TypeLibPathForInterface;
        if ( TypeLibPathForInterface >= 0 )
        {
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v37);
          v7 = 0;
          goto LABEL_16;
        }
        v18 = (unsigned int)TypeLibPathForInterface;
        v19 = 2843;
      }
      else
      {
        v18 = (unsigned int)v7;
        v19 = 2840;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
        (const char *)v18,
        v22);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v37);
    }
LABEL_16:
    v37 = 0;
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xAEB,
    (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
    (const char *)(unsigned int)RegistrationStoreContext,
    (int)&v25);
LABEL_17:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800ae080  mov     [rsp-8+arg_0], rbx
0x1800ae085  mov     [rsp-8+arg_18], rsi
0x1800ae08a  push    rbp
0x1800ae08b  push    rdi
0x1800ae08c  push    r12
0x1800ae08e  push    r14
0x1800ae090  push    r15
0x1800ae092  lea     rbp, [rsp-40h]
0x1800ae097  sub     rsp, 150h
0x1800ae09e  mov     rax, cs:__security_cookie
0x1800ae0a5  xor     rax, rsp
0x1800ae0a8  mov     [rbp+60h+var_30], rax
0x1800ae0ac  mov     rdi, rcx
0x1800ae0af  xor     r12d, r12d
0x1800ae0b2  lea     rcx, [rbp+60h+var_D8]
0x1800ae0b6  mov     [rbp+60h+var_D8], r12
0x1800ae0ba  mov     r15, r8
0x1800ae0bd  mov     rsi, rdx
0x1800ae0c0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ae0c5  xor     edx, edx
0x1800ae0c7  lea     rax, [rbp+60h+var_D8]
0x1800ae0cb  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800ae0d2  mov     [rsp+170h+var_150], rax; int
0x1800ae0d7  xor     r8d, r8d
0x1800ae0da  lea     ecx, [rdx+1]
0x1800ae0dd  call    cs:__imp_RoGetRegistrationStoreContext
0x1800ae0e3  mov     ebx, eax
0x1800ae0e5  test    eax, eax
0x1800ae0e7  jns     short loc_1800AE106
0x1800ae0e9  mov     rcx, [rbp+68h]; this
0x1800ae0ed  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ae0f4  mov     r9d, eax; char *
0x1800ae0f7  mov     edx, 0AEBh; void *
0x1800ae0fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae101  jmp     loc_1800AE2BB
0x1800ae106  xorps   xmm0, xmm0
0x1800ae109  mov     word ptr [rbp+60h+var_C0], r12w
0x1800ae10e  xorps   xmm1, xmm1
0x1800ae111  mov     [rbp+60h+var_BC], r12b
0x1800ae115  movups  [rbp+60h+var_B8], xmm0
0x1800ae119  mov     [rbp+60h+var_A8], r12b
0x1800ae11d  movups  [rbp+60h+var_A4], xmm1
0x1800ae121  mov     [rbp+60h+var_94], r12b
0x1800ae125  movups  [rbp+60h+var_90], xmm0
0x1800ae129  mov     [rbp+60h+var_80], r12b
0x1800ae12d  movups  [rbp+60h+var_7C], xmm1
0x1800ae131  mov     [rbp+60h+var_68], r12b
0x1800ae135  mov     [rbp+60h+var_60], r12
0x1800ae139  mov     [rbp+60h+var_58], r12w
0x1800ae13e  mov     [rbp+60h+var_54], r12b
0x1800ae142  mov     [rbp+60h+var_50], r12d
0x1800ae146  mov     [rbp+60h+var_4C], r12b
0x1800ae14a  mov     [rbp+60h+var_48], r12d
0x1800ae14e  mov     [rbp+60h+var_44], r12b
0x1800ae152  mov     [rbp+60h+var_40], r12d
0x1800ae156  mov     [rbp+60h+string], r12
0x1800ae15a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800ae161  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800ae166  lea     rcx, [rdi-10h]; this
0x1800ae16a  mov     dl, al
0x1800ae16c  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800ae171  mov     rcx, [rbp+60h+string]; string
0x1800ae175  mov     r14b, al
0x1800ae178  test    dl, dl
0x1800ae17a  jz      short loc_1800AE1CB
0x1800ae17c  mov     bl, [rdi+28h]
0x1800ae17f  mov     rdi, [rbp+60h+var_D8]
0x1800ae183  call    cs:__imp_WindowsDeleteString
0x1800ae189  mov     [rsp+170h+var_118], rsi
0x1800ae18e  lea     rax, [rbp+60h+var_D0]
0x1800ae192  mov     [rsp+170h+var_128], r14b
0x1800ae197  lea     rdx, [rbp+60h+string]
0x1800ae19b  mov     byte ptr [rsp+170h+var_130], bl
0x1800ae19f  lea     rcx, [rbp+60h+var_C0]
0x1800ae1a3  mov     [rsp+170h+var_138], rax
0x1800ae1a8  mov     qword ptr [rsp+170h+var_140], rsi
0x1800ae1ad  mov     [rsp+170h+var_148], rdi
0x1800ae1b2  mov     [rbp+60h+string], r12
0x1800ae1b6  mov     qword ptr [rbp+60h+var_D0], r12
0x1800ae1ba  call    ??$DoPackageAwareLookup@UComInterfaceRegistrationEntryProperties@@V_lambda_afaa7c6e0ac8d54089b409b311551717_@@@EntryLookup@CPackagedComCatalog@@SAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@V_lambda_afaa7c6e0ac8d54089b409b311551717_@@PEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,_lambda_afaa7c6e0ac8d54089b409b311551717_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,_lambda_afaa7c6e0ac8d54089b409b311551717_,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800ae1bf  xor     ecx, ecx; string
0x1800ae1c1  mov     ebx, eax
0x1800ae1c3  call    cs:__imp_WindowsDeleteString
0x1800ae1c9  jmp     short loc_1800AE219
0x1800ae1cb  mov     rbx, [rbp+60h+var_D8]
0x1800ae1cf  call    cs:__imp_WindowsDeleteString
0x1800ae1d5  mov     [rbp+60h+string], r12
0x1800ae1d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800ae1e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800ae1e5  test    al, al
0x1800ae1e7  jz      short loc_1800AE1EE
0x1800ae1e9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ae1ee  mov     [rsp+170h+var_130], rsi; struct _GUID *
0x1800ae1f3  lea     r8, [rbp+60h+var_D0]; int
0x1800ae1f7  mov     byte ptr [rsp+170h+var_140], r14b; int
0x1800ae1fc  lea     rdx, [rbp+60h+string]; int
0x1800ae200  mov     [rsp+170h+var_148], rsi; __int64
0x1800ae205  lea     rcx, [rbp+60h+var_C0]; int
0x1800ae209  mov     [rsp+170h+var_150], rbx; int
0x1800ae20e  mov     [rbp+60h+var_D0], r12d
0x1800ae212  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComInterfaceRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@Z@@CPackagedComCatalog@@CAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@0@CAJ0134567V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComInterfaceRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_)'::`2'::CheckApplicability>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_)'::`2'::CheckApplicability)
0x1800ae217  mov     ebx, eax
0x1800ae219  cmp     ebx, 80070002h
0x1800ae21f  jnz     short loc_1800AE240
0x1800ae221  mov     rcx, [rbp+60h+string]; string
0x1800ae225  call    cs:__imp_WindowsDeleteString
0x1800ae22b  mov     rcx, [rbp+60h+var_60]; string
0x1800ae22f  mov     [rbp+60h+string], r12
0x1800ae233  call    cs:__imp_WindowsDeleteString
0x1800ae239  mov     ebx, 8002801Dh
0x1800ae23e  jmp     short loc_1800AE2B7
0x1800ae240  test    ebx, ebx
0x1800ae242  jns     short loc_1800AE276
0x1800ae244  mov     r9d, ebx; char *
0x1800ae247  mov     edx, 0B18h; void *
0x1800ae24c  mov     rcx, [rbp+68h]; this
0x1800ae250  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800ae257  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae25c  mov     rcx, [rbp+60h+string]; string
0x1800ae260  call    cs:__imp_WindowsDeleteString
0x1800ae266  mov     rcx, [rbp+60h+var_60]; string
0x1800ae26a  mov     [rbp+60h+string], r12
0x1800ae26e  call    cs:__imp_WindowsDeleteString
0x1800ae274  jmp     short loc_1800AE2B7
0x1800ae276  mov     r8, [rbp+60h+var_D8]; struct IPackagedComCatalogContext *
0x1800ae27a  lea     r9, [rbp+60h+string]; struct OpaqueString *
0x1800ae27e  lea     rdx, [rbp+60h+var_C0]; struct ComInterfaceRegistrationEntryProperties *
0x1800ae282  mov     [rsp+170h+var_150], r15; HSTRING *
0x1800ae287  call    ?GetTypeLibPathForInterface@CPackagedComCatalog@@QEAAJAEBUComInterfaceRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@PEAPEAUHSTRING__@@@Z; CPackagedComCatalog::GetTypeLibPathForInterface(ComInterfaceRegistrationEntryProperties const &,IPackagedComCatalogContext *,OpaqueString const &,HSTRING__ * *)
0x1800ae28c  mov     ebx, eax
0x1800ae28e  test    eax, eax
0x1800ae290  jns     short loc_1800AE29C
0x1800ae292  mov     r9d, eax
0x1800ae295  mov     edx, 0B1Bh
0x1800ae29a  jmp     short loc_1800AE24C
0x1800ae29c  mov     rcx, [rbp+60h+string]; string
0x1800ae2a0  call    cs:__imp_WindowsDeleteString
0x1800ae2a6  mov     rcx, [rbp+60h+var_60]; string
0x1800ae2aa  mov     [rbp+60h+string], r12
0x1800ae2ae  call    cs:__imp_WindowsDeleteString
0x1800ae2b4  mov     ebx, r12d
0x1800ae2b7  mov     [rbp+60h+var_60], r12
0x1800ae2bb  lea     rcx, [rbp+60h+var_D8]
0x1800ae2bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ae2c4  mov     eax, ebx
0x1800ae2c6  mov     rcx, [rbp+60h+var_30]
0x1800ae2ca  xor     rcx, rsp; StackCookie
0x1800ae2cd  call    __security_check_cookie
0x1800ae2d2  lea     r11, [rsp+170h+var_20]
0x1800ae2da  mov     rbx, [r11+30h]
0x1800ae2de  mov     rsi, [r11+48h]
0x1800ae2e2  mov     rsp, r11
0x1800ae2e5  pop     r15
0x1800ae2e7  pop     r14
0x1800ae2e9  pop     r12
0x1800ae2eb  pop     rdi
0x1800ae2ec  pop     rbp
0x1800ae2ed  retn
```
