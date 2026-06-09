# CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld(IPackagedComCatalogContext *,ushort const *,bool,_GUID const &,void * *)

- ea: `0x1800e3758`
- end: `0x1800e3b16`
- name: `?GetClassInfoFromProgIdWorkerOld@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEBG_NAEBU_GUID@@PEAPEAX@Z`
- size: `958`
- prototype: `__int64 __fastcall(struct IPackagedComCatalogContext *, const unsigned __int16 *, bool, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800e3280`

## callees

- `0x1800065a4`
- `0x18001a374`
- `0x180034260`
- `0x18004b0f0`
- `0x1800581c0`
- `0x1800941bc`
- `0x180095c0c`
- `0x1800a6768`
- `0x1800a9c84`
- `0x1800b7ac0`
- `0x1800dd814`
- `0x1800e3758`
- `0x1800e8dc0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e37d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e37e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e38b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e398a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e399f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e37d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e37e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e38b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e398a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e399f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3a57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3acd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e3ae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e391c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e39dc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e391c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e3931`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e39dc`

## string_xrefs

- `0x1800e394e`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e39f9`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e3a00`: `While resolving ProgId %S, found ProgId %S with CLSID=%ws`
- `0x1800e3942`: `CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld`
- `0x1800e39ed`: `CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld(
        struct IPackagedComCatalogContext *a1,
        const unsigned __int16 *a2,
        char a3,
        const struct _GUID *a4,
        void **a5)
{
  __int64 v8; // rcx
  HSTRING v9; // rbx
  int v10; // edi
  __int64 v12; // rax
  unsigned int (__fastcall *v13)(struct IPackagedComCatalogContext *, HSTRING, HSTRING, _BYTE *, const unsigned __int16 **, __int64 *); // rax
  __int64 v14; // rsi
  __int64 v15; // rdx
  __int64 v16; // rcx
  HSTRING v17; // rbx
  int v18; // r8d
  int v19; // eax
  PCWSTR v20; // rdi
  PCWSTR v21; // rax
  CGuidStr *v22; // rdi
  PCWSTR StringRawBuffer; // rax
  int ClassInfoWorker; // eax
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  HSTRING v26; // [rsp+88h] [rbp-78h] BYREF
  const unsigned __int16 *v27; // [rsp+90h] [rbp-70h] BYREF
  __int64 v28; // [rsp+98h] [rbp-68h] BYREF
  const struct _GUID *v29; // [rsp+A0h] [rbp-60h]
  _BYTE v30[4]; // [rsp+B0h] [rbp-50h] BYREF
  struct _GUID v31; // [rsp+B4h] [rbp-4Ch] BYREF
  char v32; // [rsp+C8h] [rbp-38h]
  HSTRING v33; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v34; // [rsp+D8h] [rbp-28h]
  char v35; // [rsp+DCh] [rbp-24h]
  int v36; // [rsp+E0h] [rbp-20h]
  char v37; // [rsp+E4h] [rbp-1Ch]
  int v38; // [rsp+E8h] [rbp-18h]
  char v39; // [rsp+ECh] [rbp-14h]
  int v40; // [rsp+F0h] [rbp-10h]
  struct _GUID v41; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v42[80]; // [rsp+110h] [rbp+10h] BYREF

  v29 = a4;
  v27 = a2;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
  v9 = 0;
  *a5 = 0;
  v26 = 0;
  string = 0;
  v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string);
  if ( v10 < 0 )
  {
    WindowsDeleteString(string);
    string = 0;
    WindowsDeleteString(0);
    return (unsigned int)v10;
  }
  v41 = 0;
  while ( 1 )
  {
    v30[0] = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v31 = 0;
    if ( !v9 )
      break;
    v12 = *(_QWORD *)a1;
    v27 = 0;
    v13 = *(unsigned int (__fastcall **)(struct IPackagedComCatalogContext *, HSTRING, HSTRING, _BYTE *, const unsigned __int16 **, __int64 *))(v12 + 128);
    v28 = 0;
    v14 = v13(a1, v9, string, v30, &v27, &v28);
    CPackagedComCatalog::LogReadEntryResult(v14, v15, &v26, string);
    if ( (int)v14 < 0 )
      goto LABEL_24;
    if ( !(unsigned __int8)RegistrationIsSupportedSyntaxVersion<ComProgIdRegistrationEntryProperties>(v30) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v16);
LABEL_11:
    if ( v30[0] )
    {
      if ( gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(3) )
      {
        v22 = CGuidStr::CGuidStr((CGuidStr *)v42, &v31);
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (unsigned int)"CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld",
          7592,
          3,
          (__int64)L"While resolving ProgId %S, found ProgId %S with CLSID=%ws",
          a2,
          StringRawBuffer,
          v22);
      }
      v41 = v31;
      WindowsDeleteString(v33);
      goto LABEL_22;
    }
    if ( !v32 )
    {
      WindowsDeleteString(v33);
LABEL_25:
      LODWORD(v14) = -2147221164;
      goto LABEL_28;
    }
    if ( gfEnableTracing )
    {
      if ( (unsigned __int8)IsWppLevelEnabled(3) )
      {
        v20 = WindowsGetStringRawBuffer(v33, 0);
        v21 = WindowsGetStringRawBuffer(string, 0);
        ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(
          (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
          (unsigned int)"CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld",
          7601,
          3,
          (__int64)L"While resolving ProgId %S, found ProgId %S with CurrentVersion=%S",
          a2,
          v21,
          v20);
      }
    }
    OpaqueString::operator=(&string, &v33);
    WindowsDeleteString(v33);
  }
  v17 = string;
  WindowsDeleteString(0);
  v26 = 0;
  v19 = CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(
          (unsigned int)v30,
          (unsigned int)&v26,
          v18,
          (_DWORD)a1,
          (__int64)v17,
          a3);
  v9 = v26;
  LODWORD(v14) = v19;
  if ( v19 >= 0 )
    goto LABEL_11;
LABEL_24:
  WindowsDeleteString(v33);
  if ( (_DWORD)v14 == -2147024894 )
    goto LABEL_25;
LABEL_22:
  if ( (_DWORD)v14 == -2147024883 )
  {
    LODWORD(v14) = -2147221165;
  }
  else if ( (int)v14 >= 0 )
  {
    ClassInfoWorker = CPackagedComCatalog::GetClassInfoWorker(
                        6,
                        0,
                        (__int64)a1,
                        (const struct OpaqueString *)&v26,
                        0,
                        &v41,
                        a3,
                        (__int64)v29,
                        a5,
                        0,
                        0,
                        0,
                        0,
                        0,
                        0);
    v9 = v26;
    LODWORD(v14) = ClassInfoWorker;
  }
LABEL_28:
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v9);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800e3758  mov     [rsp-8+arg_10], rbx
0x1800e375d  push    rbp
0x1800e375e  push    rsi
0x1800e375f  push    rdi
0x1800e3760  push    r12
0x1800e3762  push    r13
0x1800e3764  push    r14
0x1800e3766  push    r15
0x1800e3768  lea     rbp, [rsp-70h]
0x1800e376d  sub     rsp, 170h
0x1800e3774  mov     rax, cs:__security_cookie
0x1800e377b  xor     rax, rsp
0x1800e377e  mov     [rbp+0A0h+var_40], rax
0x1800e3782  mov     r12, [rbp+0A0h+arg_20]
0x1800e3789  mov     r13b, r8b
0x1800e378c  mov     [rbp+0A0h+var_100], r9
0x1800e3790  mov     r15, rdx
0x1800e3793  mov     r14, rcx
0x1800e3796  mov     [rbp+0A0h+var_110], rdx
0x1800e379a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800e37a1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800e37a6  xor     esi, esi
0x1800e37a8  test    al, al
0x1800e37aa  jz      short loc_1800E37B1
0x1800e37ac  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e37b1  mov     rbx, rsi
0x1800e37b4  mov     [r12], rsi
0x1800e37b8  lea     rdx, [rbp+0A0h+var_110]
0x1800e37bc  mov     [rbp+0A0h+var_118], rbx
0x1800e37c0  lea     rcx, [rbp+0A0h+string]; string
0x1800e37c4  mov     [rbp+0A0h+string], rsi
0x1800e37c8  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800e37cd  mov     edi, eax
0x1800e37cf  test    eax, eax
0x1800e37d1  jns     short loc_1800E37FC
0x1800e37d3  mov     rcx, [rbp+0A0h+string]; string
0x1800e37d7  call    cs:__imp_WindowsDeleteString
0x1800e37de  nop     dword ptr [rax+rax+00h]
0x1800e37e3  xor     ecx, ecx; string
0x1800e37e5  mov     [rbp+0A0h+string], rsi
0x1800e37e9  call    cs:__imp_WindowsDeleteString
0x1800e37f0  nop     dword ptr [rax+rax+00h]
0x1800e37f5  mov     eax, edi
0x1800e37f7  jmp     loc_1800E3AEE
0x1800e37fc  xorps   xmm0, xmm0
0x1800e37ff  xor     edi, edi
0x1800e3801  movups  [rbp+0A0h+var_A0], xmm0
0x1800e3805  xor     eax, eax
0x1800e3807  mov     [rbp+0A0h+var_F0], dil
0x1800e380b  mov     [rbp+0A0h+var_D8], dil
0x1800e380f  xorps   xmm0, xmm0
0x1800e3812  mov     [rbp+0A0h+var_D0], rdi
0x1800e3816  mov     [rbp+0A0h+var_C8], ax
0x1800e381a  mov     [rbp+0A0h+var_C4], dil
0x1800e381e  mov     [rbp+0A0h+var_C0], edi
0x1800e3821  mov     [rbp+0A0h+var_BC], dil
0x1800e3825  mov     [rbp+0A0h+var_B8], edi
0x1800e3828  mov     [rbp+0A0h+var_B4], dil
0x1800e382c  mov     [rbp+0A0h+var_B0], edi
0x1800e382f  movups  xmmword ptr [rbp+0A0h+var_EC.Data1], xmm0
0x1800e3833  test    rbx, rbx
0x1800e3836  jz      short loc_1800E38AE
0x1800e3838  mov     rax, [r14]
0x1800e383b  lea     rcx, [rbp+0A0h+var_108]
0x1800e383f  mov     r8, [rbp+0A0h+string]
0x1800e3843  lea     r9, [rbp+0A0h+var_F0]
0x1800e3847  mov     [rsp+1A0h+var_178], rcx
0x1800e384c  mov     rdx, rbx
0x1800e384f  lea     rcx, [rbp+0A0h+var_110]
0x1800e3853  mov     [rbp+0A0h+var_110], rdi
0x1800e3857  mov     rax, [rax+80h]
0x1800e385e  mov     [rsp+1A0h+var_180], rcx
0x1800e3863  mov     rcx, r14
0x1800e3866  mov     [rbp+0A0h+var_108], rdi
0x1800e386a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e386f  mov     r9, [rbp+0A0h+string]
0x1800e3873  lea     r8, [rbp+0A0h+var_118]
0x1800e3877  mov     esi, eax
0x1800e3879  mov     rax, [rbp+0A0h+var_108]
0x1800e387d  mov     [rsp+1A0h+var_178], rax
0x1800e3882  mov     ecx, esi
0x1800e3884  mov     rax, [rbp+0A0h+var_110]
0x1800e3888  mov     [rsp+1A0h+var_180], rax
0x1800e388d  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComProgIdRegistrationEntryProperties@@AEBVOpaqueString@@PEAUHSTRING__@@W4ComProgIdRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComProgIdRegistrationEntryProperties const &,OpaqueString const &,HSTRING__ *,ComProgIdRegistrationEntryPropertyFlags,ComProgIdRegistrationEntryPropertyFlags)
0x1800e3892  test    esi, esi
0x1800e3894  js      loc_1800E3A53
0x1800e389a  lea     rcx, [rbp+0A0h+var_F0]
0x1800e389e  call    ??$RegistrationIsSupportedSyntaxVersion@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationIsSupportedSyntaxVersion<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800e38a3  test    al, al
0x1800e38a5  jnz     short loc_1800E38EC
0x1800e38a7  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e38ac  jmp     short loc_1800E38EC
0x1800e38ae  mov     rbx, [rbp+0A0h+string]
0x1800e38b2  xor     ecx, ecx; string
0x1800e38b4  call    cs:__imp_WindowsDeleteString
0x1800e38bb  nop     dword ptr [rax+rax+00h]
0x1800e38c0  mov     r9, r14
0x1800e38c3  mov     byte ptr [rsp+1A0h+var_178], r13b
0x1800e38c8  lea     rdx, [rbp+0A0h+var_118]
0x1800e38cc  mov     [rbp+0A0h+var_118], rdi
0x1800e38d0  lea     rcx, [rbp+0A0h+var_F0]
0x1800e38d4  mov     [rsp+1A0h+var_180], rbx
0x1800e38d9  call    ??$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU2@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))
0x1800e38de  mov     rbx, [rbp+0A0h+var_118]
0x1800e38e2  mov     esi, eax
0x1800e38e4  test    eax, eax
0x1800e38e6  js      loc_1800E3A53
0x1800e38ec  cmp     [rbp+0A0h+var_F0], dil
0x1800e38f0  jnz     loc_1800E39B0
0x1800e38f6  cmp     [rbp+0A0h+var_D8], dil
0x1800e38fa  jz      loc_1800E399B
0x1800e3900  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800e3906  jz      short loc_1800E3979
0x1800e3908  mov     ecx, 3
0x1800e390d  call    IsWppLevelEnabled
0x1800e3912  test    al, al
0x1800e3914  jz      short loc_1800E3979
0x1800e3916  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e391a  xor     edx, edx; length
0x1800e391c  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e3923  nop     dword ptr [rax+rax+00h]
0x1800e3928  mov     rcx, [rbp+0A0h+string]; string
0x1800e392c  xor     edx, edx; length
0x1800e392e  mov     rdi, rax
0x1800e3931  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e3938  nop     dword ptr [rax+rax+00h]
0x1800e393d  mov     [rsp+1A0h+var_168], rdi
0x1800e3942  lea     rdx, aCpackagedcomca_1; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800e3949  mov     [rsp+1A0h+var_170], rax
0x1800e394e  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e3955  lea     rax, aWhileResolving; "While resolving ProgId %S, found ProgId"...
0x1800e395c  mov     [rsp+1A0h+var_178], r15
0x1800e3961  mov     r9d, 3
0x1800e3967  mov     [rsp+1A0h+var_180], rax
0x1800e396c  mov     r8d, 1DB1h
0x1800e3972  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800e3977  xor     edi, edi
0x1800e3979  lea     rdx, [rbp+0A0h+var_D0]
0x1800e397d  lea     rcx, [rbp+0A0h+string]
0x1800e3981  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800e3986  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e398a  call    cs:__imp_WindowsDeleteString
0x1800e3991  nop     dword ptr [rax+rax+00h]
0x1800e3996  jmp     loc_1800E3805
0x1800e399b  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e399f  call    cs:__imp_WindowsDeleteString
0x1800e39a6  nop     dword ptr [rax+rax+00h]
0x1800e39ab  jmp     loc_1800E3A6B
0x1800e39b0  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800e39b6  jz      short loc_1800E3A24
0x1800e39b8  mov     ecx, 3
0x1800e39bd  call    IsWppLevelEnabled
0x1800e39c2  test    al, al
0x1800e39c4  jz      short loc_1800E3A24
0x1800e39c6  lea     rdx, [rbp+0A0h+var_EC]; struct _GUID *
0x1800e39ca  lea     rcx, [rbp+0A0h+var_90]; this
0x1800e39ce  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e39d3  mov     rcx, [rbp+0A0h+string]; string
0x1800e39d7  xor     edx, edx; length
0x1800e39d9  mov     rdi, rax
0x1800e39dc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e39e3  nop     dword ptr [rax+rax+00h]
0x1800e39e8  mov     [rsp+1A0h+var_168], rdi
0x1800e39ed  lea     rdx, aCpackagedcomca_1; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800e39f4  mov     [rsp+1A0h+var_170], rax
0x1800e39f9  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e3a00  lea     rax, aWhileResolving_0; "While resolving ProgId %S, found ProgId"...
0x1800e3a07  mov     [rsp+1A0h+var_178], r15
0x1800e3a0c  mov     r9d, 3
0x1800e3a12  mov     [rsp+1A0h+var_180], rax
0x1800e3a17  mov     r8d, 1DA8h
0x1800e3a1d  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800e3a22  xor     edi, edi
0x1800e3a24  mov     rax, qword ptr [rbp+0A0h+var_EC.Data1]
0x1800e3a28  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e3a2c  mov     qword ptr [rbp+0A0h+var_A0], rax
0x1800e3a30  mov     rax, qword ptr [rbp+0A0h+var_EC.Data4]
0x1800e3a34  mov     qword ptr [rbp+0A0h+var_A0+8], rax
0x1800e3a38  call    cs:__imp_WindowsDeleteString
0x1800e3a3f  nop     dword ptr [rax+rax+00h]
0x1800e3a44  cmp     esi, 8007000Dh
0x1800e3a4a  jnz     short loc_1800E3A72
0x1800e3a4c  mov     esi, 80040153h
0x1800e3a51  jmp     short loc_1800E3AC9
0x1800e3a53  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800e3a57  call    cs:__imp_WindowsDeleteString
0x1800e3a5e  nop     dword ptr [rax+rax+00h]
0x1800e3a63  cmp     esi, 80070002h
0x1800e3a69  jnz     short loc_1800E3A44
0x1800e3a6b  mov     esi, 80040154h
0x1800e3a70  jmp     short loc_1800E3AC9
0x1800e3a72  test    esi, esi
0x1800e3a74  js      short loc_1800E3AC9
0x1800e3a76  mov     rax, [rbp+0A0h+var_100]
0x1800e3a7a  lea     r9, [rbp+0A0h+var_118]
0x1800e3a7e  mov     [rsp+1A0h+var_130], rdi
0x1800e3a83  xor     edx, edx
0x1800e3a85  mov     [rsp+1A0h+var_138], edi
0x1800e3a89  mov     r8, r14
0x1800e3a8c  mov     [rsp+1A0h+var_140], rdi
0x1800e3a91  mov     [rsp+1A0h+var_148], edi
0x1800e3a95  mov     [rsp+1A0h+var_150], rdi
0x1800e3a9a  lea     ecx, [rdx+6]
0x1800e3a9d  mov     [rsp+1A0h+var_158], edi
0x1800e3aa1  mov     [rsp+1A0h+var_160], r12
0x1800e3aa6  mov     [rsp+1A0h+var_168], rax
0x1800e3aab  lea     rax, [rbp+0A0h+var_A0]
0x1800e3aaf  mov     byte ptr [rsp+1A0h+var_170], r13b
0x1800e3ab4  mov     [rsp+1A0h+var_178], rax
0x1800e3ab9  mov     byte ptr [rsp+1A0h+var_180], dil
0x1800e3abe  call    ?GetClassInfoWorker@CPackagedComCatalog@@CAJW4tagCLSCTX@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@45PEAPEAXW4ComRegistrationVisibility@@PEBGIQEBQEAUHSTRING__@@I9@Z; CPackagedComCatalog::GetClassInfoWorker(tagCLSCTX,IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID const &,void * *,ComRegistrationVisibility,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800e3ac3  mov     rbx, [rbp+0A0h+var_118]
0x1800e3ac7  mov     esi, eax
0x1800e3ac9  mov     rcx, [rbp+0A0h+string]; string
0x1800e3acd  call    cs:__imp_WindowsDeleteString
0x1800e3ad4  nop     dword ptr [rax+rax+00h]
0x1800e3ad9  mov     rcx, rbx; string
0x1800e3adc  mov     [rbp+0A0h+string], rdi
0x1800e3ae0  call    cs:__imp_WindowsDeleteString
0x1800e3ae7  nop     dword ptr [rax+rax+00h]
0x1800e3aec  mov     eax, esi
0x1800e3aee  mov     rcx, [rbp+0A0h+var_40]
0x1800e3af2  xor     rcx, rsp; StackCookie
0x1800e3af5  call    __security_check_cookie
0x1800e3afa  mov     rbx, [rsp+1A0h+arg_10]
0x1800e3b02  add     rsp, 170h
0x1800e3b09  pop     r15
0x1800e3b0b  pop     r14
0x1800e3b0d  pop     r13
0x1800e3b0f  pop     r12
0x1800e3b11  pop     rdi
0x1800e3b12  pop     rsi
0x1800e3b13  pop     rbp
0x1800e3b14  retn
```
