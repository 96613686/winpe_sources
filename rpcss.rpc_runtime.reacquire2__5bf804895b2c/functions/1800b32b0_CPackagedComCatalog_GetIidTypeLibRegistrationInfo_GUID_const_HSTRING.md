# CPackagedComCatalog::GetIidTypeLibRegistrationInfo(_GUID const &,HSTRING__ * *)

- ea: `0x1800b32b0`
- end: `0x1800b355e`
- name: `?GetIidTypeLibRegistrationInfo@CPackagedComCatalog@@UEAAJAEBU_GUID@@PEAPEAUHSTRING__@@@Z`
- size: `686`
- prototype: `__int64 __fastcall(CPackagedComCatalog *__hidden this, const struct _GUID *, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x1800065a4`
- `0x1800210f8`
- `0x18002750c`
- `0x180061d74`
- `0x180095c0c`
- `0x1800b32b0`
- `0x1800b3564`
- `0x1800b7ac0`
- `0x1800db000`
- `0x1800e7404`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b33b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b33ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b346d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b34b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b34cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3517`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b33b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b33ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3411`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b346d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3481`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b34b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b34cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3503`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b3517`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800b330d`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800b330d`

## string_xrefs

- `0x1800b3323`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800b34a7`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`

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
0x1800b32b0  mov     [rsp-8+arg_0], rbx
0x1800b32b5  mov     [rsp-8+arg_18], rsi
0x1800b32ba  push    rbp
0x1800b32bb  push    rdi
0x1800b32bc  push    r12
0x1800b32be  push    r14
0x1800b32c0  push    r15
0x1800b32c2  lea     rbp, [rsp-40h]
0x1800b32c7  sub     rsp, 150h
0x1800b32ce  mov     rax, cs:__security_cookie
0x1800b32d5  xor     rax, rsp
0x1800b32d8  mov     [rbp+60h+var_30], rax
0x1800b32dc  mov     rdi, rcx
0x1800b32df  xor     r12d, r12d
0x1800b32e2  lea     rcx, [rbp+60h+var_D8]
0x1800b32e6  mov     [rbp+60h+var_D8], r12
0x1800b32ea  mov     r15, r8
0x1800b32ed  mov     rsi, rdx
0x1800b32f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b32f5  xor     edx, edx
0x1800b32f7  lea     rax, [rbp+60h+var_D8]
0x1800b32fb  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800b3302  mov     [rsp+170h+var_150], rax; int
0x1800b3307  xor     r8d, r8d
0x1800b330a  lea     ecx, [rdx+1]
0x1800b330d  call    cs:__imp_RoGetRegistrationStoreContext
0x1800b3314  nop     dword ptr [rax+rax+00h]
0x1800b3319  mov     ebx, eax
0x1800b331b  test    eax, eax
0x1800b331d  jns     short loc_1800B333C
0x1800b331f  mov     rcx, [rbp+68h]; this
0x1800b3323  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800b332a  mov     r9d, eax; char *
0x1800b332d  mov     edx, 0AEBh; void *
0x1800b3332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b3337  jmp     loc_1800B352A
0x1800b333c  xorps   xmm0, xmm0
0x1800b333f  mov     word ptr [rbp+60h+var_C0], r12w
0x1800b3344  xorps   xmm1, xmm1
0x1800b3347  mov     [rbp+60h+var_BC], r12b
0x1800b334b  movups  [rbp+60h+var_B8], xmm0
0x1800b334f  mov     [rbp+60h+var_A8], r12b
0x1800b3353  movups  [rbp+60h+var_A4], xmm1
0x1800b3357  mov     [rbp+60h+var_94], r12b
0x1800b335b  movups  [rbp+60h+var_90], xmm0
0x1800b335f  mov     [rbp+60h+var_80], r12b
0x1800b3363  movups  [rbp+60h+var_7C], xmm1
0x1800b3367  mov     [rbp+60h+var_68], r12b
0x1800b336b  mov     [rbp+60h+var_60], r12
0x1800b336f  mov     [rbp+60h+var_58], r12w
0x1800b3374  mov     [rbp+60h+var_54], r12b
0x1800b3378  mov     [rbp+60h+var_50], r12d
0x1800b337c  mov     [rbp+60h+var_4C], r12b
0x1800b3380  mov     [rbp+60h+var_48], r12d
0x1800b3384  mov     [rbp+60h+var_44], r12b
0x1800b3388  mov     [rbp+60h+var_40], r12d
0x1800b338c  mov     [rbp+60h+string], r12
0x1800b3390  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800b3397  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800b339c  lea     rcx, [rdi-10h]; this
0x1800b33a0  mov     dl, al
0x1800b33a2  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800b33a7  mov     rcx, [rbp+60h+string]; string
0x1800b33ab  mov     r14b, al
0x1800b33ae  test    dl, dl
0x1800b33b0  jz      short loc_1800B340D
0x1800b33b2  mov     bl, [rdi+28h]
0x1800b33b5  mov     rdi, [rbp+60h+var_D8]
0x1800b33b9  call    cs:__imp_WindowsDeleteString
0x1800b33c0  nop     dword ptr [rax+rax+00h]
0x1800b33c5  mov     [rsp+170h+var_118], rsi
0x1800b33ca  lea     rax, [rbp+60h+var_D0]
0x1800b33ce  mov     [rsp+170h+var_128], r14b
0x1800b33d3  lea     rdx, [rbp+60h+string]
0x1800b33d7  mov     byte ptr [rsp+170h+var_130], bl
0x1800b33db  lea     rcx, [rbp+60h+var_C0]
0x1800b33df  mov     [rsp+170h+var_138], rax
0x1800b33e4  mov     qword ptr [rsp+170h+var_140], rsi
0x1800b33e9  mov     [rsp+170h+var_148], rdi
0x1800b33ee  mov     [rbp+60h+string], r12
0x1800b33f2  mov     qword ptr [rbp+60h+var_D0], r12
0x1800b33f6  call    ??$DoPackageAwareLookup@UComInterfaceRegistrationEntryProperties@@V_lambda_afaa7c6e0ac8d54089b409b311551717_@@@EntryLookup@CPackagedComCatalog@@SAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@V_lambda_afaa7c6e0ac8d54089b409b311551717_@@PEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,_lambda_afaa7c6e0ac8d54089b409b311551717_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,_lambda_afaa7c6e0ac8d54089b409b311551717_,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800b33fb  xor     ecx, ecx; string
0x1800b33fd  mov     ebx, eax
0x1800b33ff  call    cs:__imp_WindowsDeleteString
0x1800b3406  nop     dword ptr [rax+rax+00h]
0x1800b340b  jmp     short loc_1800B3461
0x1800b340d  mov     rbx, [rbp+60h+var_D8]
0x1800b3411  call    cs:__imp_WindowsDeleteString
0x1800b3418  nop     dword ptr [rax+rax+00h]
0x1800b341d  mov     [rbp+60h+string], r12
0x1800b3421  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800b3428  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800b342d  test    al, al
0x1800b342f  jz      short loc_1800B3436
0x1800b3431  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b3436  mov     [rsp+170h+var_130], rsi; struct _GUID *
0x1800b343b  lea     r8, [rbp+60h+var_D0]; int
0x1800b343f  mov     byte ptr [rsp+170h+var_140], r14b; int
0x1800b3444  lea     rdx, [rbp+60h+string]; int
0x1800b3448  mov     [rsp+170h+var_148], rsi; __int64
0x1800b344d  lea     rcx, [rbp+60h+var_C0]; int
0x1800b3451  mov     [rsp+170h+var_150], rbx; int
0x1800b3456  mov     [rbp+60h+var_D0], r12d
0x1800b345a  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComInterfaceRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@Z@@CPackagedComCatalog@@CAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@0@CAJ0134567V_lambda_06e8315f1c9f28f4d598ffb1e99cd492_@@@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComInterfaceRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_)'::`2'::CheckApplicability>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,_lambda_06e8315f1c9f28f4d598ffb1e99cd492_)'::`2'::CheckApplicability)
0x1800b345f  mov     ebx, eax
0x1800b3461  cmp     ebx, 80070002h
0x1800b3467  jnz     short loc_1800B3497
0x1800b3469  mov     rcx, [rbp+60h+string]; string
0x1800b346d  call    cs:__imp_WindowsDeleteString
0x1800b3474  nop     dword ptr [rax+rax+00h]
0x1800b3479  mov     rcx, [rbp+60h+var_60]; string
0x1800b347d  mov     [rbp+60h+string], r12
0x1800b3481  call    cs:__imp_WindowsDeleteString
0x1800b3488  nop     dword ptr [rax+rax+00h]
0x1800b348d  mov     ebx, 8002801Dh
0x1800b3492  jmp     loc_1800B3526
0x1800b3497  test    ebx, ebx
0x1800b3499  jns     short loc_1800B34D9
0x1800b349b  mov     r9d, ebx; char *
0x1800b349e  mov     edx, 0B18h; void *
0x1800b34a3  mov     rcx, [rbp+68h]; this
0x1800b34a7  lea     r8, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800b34ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b34b3  mov     rcx, [rbp+60h+string]; string
0x1800b34b7  call    cs:__imp_WindowsDeleteString
0x1800b34be  nop     dword ptr [rax+rax+00h]
0x1800b34c3  mov     rcx, [rbp+60h+var_60]; string
0x1800b34c7  mov     [rbp+60h+string], r12
0x1800b34cb  call    cs:__imp_WindowsDeleteString
0x1800b34d2  nop     dword ptr [rax+rax+00h]
0x1800b34d7  jmp     short loc_1800B3526
0x1800b34d9  mov     r8, [rbp+60h+var_D8]; struct IPackagedComCatalogContext *
0x1800b34dd  lea     r9, [rbp+60h+string]; struct OpaqueString *
0x1800b34e1  lea     rdx, [rbp+60h+var_C0]; struct ComInterfaceRegistrationEntryProperties *
0x1800b34e5  mov     [rsp+170h+var_150], r15; HSTRING *
0x1800b34ea  call    ?GetTypeLibPathForInterface@CPackagedComCatalog@@QEAAJAEBUComInterfaceRegistrationEntryProperties@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@PEAPEAUHSTRING__@@@Z; CPackagedComCatalog::GetTypeLibPathForInterface(ComInterfaceRegistrationEntryProperties const &,IPackagedComCatalogContext *,OpaqueString const &,HSTRING__ * *)
0x1800b34ef  mov     ebx, eax
0x1800b34f1  test    eax, eax
0x1800b34f3  jns     short loc_1800B34FF
0x1800b34f5  mov     r9d, eax
0x1800b34f8  mov     edx, 0B1Bh
0x1800b34fd  jmp     short loc_1800B34A3
0x1800b34ff  mov     rcx, [rbp+60h+string]; string
0x1800b3503  call    cs:__imp_WindowsDeleteString
0x1800b350a  nop     dword ptr [rax+rax+00h]
0x1800b350f  mov     rcx, [rbp+60h+var_60]; string
0x1800b3513  mov     [rbp+60h+string], r12
0x1800b3517  call    cs:__imp_WindowsDeleteString
0x1800b351e  nop     dword ptr [rax+rax+00h]
0x1800b3523  mov     ebx, r12d
0x1800b3526  mov     [rbp+60h+var_60], r12
0x1800b352a  lea     rcx, [rbp+60h+var_D8]
0x1800b352e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b3533  mov     eax, ebx
0x1800b3535  mov     rcx, [rbp+60h+var_30]
0x1800b3539  xor     rcx, rsp; StackCookie
0x1800b353c  call    __security_check_cookie
0x1800b3541  lea     r11, [rsp+170h+var_20]
0x1800b3549  mov     rbx, [r11+30h]
0x1800b354d  mov     rsi, [r11+48h]
0x1800b3551  mov     rsp, r11
0x1800b3554  pop     r15
0x1800b3556  pop     r14
0x1800b3558  pop     r12
0x1800b355a  pop     rdi
0x1800b355b  pop     rbp
0x1800b355c  retn
```
