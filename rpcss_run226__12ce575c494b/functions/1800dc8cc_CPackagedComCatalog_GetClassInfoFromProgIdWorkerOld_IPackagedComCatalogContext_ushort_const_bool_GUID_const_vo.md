# CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld(IPackagedComCatalogContext *,ushort const *,bool,_GUID const &,void * *)

- ea: `0x1800dc8cc`
- end: `0x1800dcc41`
- name: `?GetClassInfoFromProgIdWorkerOld@CPackagedComCatalog@@CAJPEAUIPackagedComCatalogContext@@PEBG_NAEBU_GUID@@PEAPEAX@Z`
- size: `885`
- prototype: `__int64 __fastcall(struct IPackagedComCatalogContext *, const unsigned __int16 *, bool, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800dc440`

## callees

- `0x180005c40`
- `0x180016160`
- `0x180034540`
- `0x1800414d0`
- `0x18004c4e0`
- `0x18008d028`
- `0x18008e98c`
- `0x1800a12c4`
- `0x1800a4cc4`
- `0x1800b27e0`
- `0x1800d6bec`
- `0x1800dc8cc`
- `0x1800e1af0`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc94b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcaef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcb7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcc05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcc12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc94b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dc957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dca1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcae0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcaef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcb7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcc05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dcc12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dca7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dca8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dcb26`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dca7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dca8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dcb26`

## string_xrefs

- `0x1800dcaa4`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dcb3d`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dca98`: `CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld`
- `0x1800dcb31`: `CPackagedComCatalog::GetClassInfoFromProgIdWorkerOld`
- `0x1800dcb44`: `While resolving ProgId %S, found ProgId %S with CLSID=%ws`

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
0x1800dc8cc  mov     [rsp-8+arg_10], rbx
0x1800dc8d1  push    rbp
0x1800dc8d2  push    rsi
0x1800dc8d3  push    rdi
0x1800dc8d4  push    r12
0x1800dc8d6  push    r13
0x1800dc8d8  push    r14
0x1800dc8da  push    r15
0x1800dc8dc  lea     rbp, [rsp-70h]
0x1800dc8e1  sub     rsp, 170h
0x1800dc8e8  mov     rax, cs:__security_cookie
0x1800dc8ef  xor     rax, rsp
0x1800dc8f2  mov     [rbp+0A0h+var_40], rax
0x1800dc8f6  mov     r12, [rbp+0A0h+arg_20]
0x1800dc8fd  mov     r13b, r8b
0x1800dc900  mov     [rbp+0A0h+var_100], r9
0x1800dc904  mov     r15, rdx
0x1800dc907  mov     r14, rcx
0x1800dc90a  mov     [rbp+0A0h+var_110], rdx
0x1800dc90e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800dc915  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800dc91a  xor     esi, esi
0x1800dc91c  test    al, al
0x1800dc91e  jz      short loc_1800DC925
0x1800dc920  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800dc925  mov     rbx, rsi
0x1800dc928  mov     [r12], rsi
0x1800dc92c  lea     rdx, [rbp+0A0h+var_110]
0x1800dc930  mov     [rbp+0A0h+var_118], rbx
0x1800dc934  lea     rcx, [rbp+0A0h+string]; string
0x1800dc938  mov     [rbp+0A0h+string], rsi
0x1800dc93c  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800dc941  mov     edi, eax
0x1800dc943  test    eax, eax
0x1800dc945  jns     short loc_1800DC964
0x1800dc947  mov     rcx, [rbp+0A0h+string]; string
0x1800dc94b  call    cs:__imp_WindowsDeleteString
0x1800dc951  xor     ecx, ecx; string
0x1800dc953  mov     [rbp+0A0h+string], rsi
0x1800dc957  call    cs:__imp_WindowsDeleteString
0x1800dc95d  mov     eax, edi
0x1800dc95f  jmp     loc_1800DCC1A
0x1800dc964  xorps   xmm0, xmm0
0x1800dc967  xor     edi, edi
0x1800dc969  movups  [rbp+0A0h+var_A0], xmm0
0x1800dc96d  xor     eax, eax
0x1800dc96f  mov     [rbp+0A0h+var_F0], dil
0x1800dc973  mov     [rbp+0A0h+var_D8], dil
0x1800dc977  xorps   xmm0, xmm0
0x1800dc97a  mov     [rbp+0A0h+var_D0], rdi
0x1800dc97e  mov     [rbp+0A0h+var_C8], ax
0x1800dc982  mov     [rbp+0A0h+var_C4], dil
0x1800dc986  mov     [rbp+0A0h+var_C0], edi
0x1800dc989  mov     [rbp+0A0h+var_BC], dil
0x1800dc98d  mov     [rbp+0A0h+var_B8], edi
0x1800dc990  mov     [rbp+0A0h+var_B4], dil
0x1800dc994  mov     [rbp+0A0h+var_B0], edi
0x1800dc997  movups  xmmword ptr [rbp+0A0h+var_EC.Data1], xmm0
0x1800dc99b  test    rbx, rbx
0x1800dc99e  jz      short loc_1800DCA16
0x1800dc9a0  mov     rax, [r14]
0x1800dc9a3  lea     rcx, [rbp+0A0h+var_108]
0x1800dc9a7  mov     r8, [rbp+0A0h+string]
0x1800dc9ab  lea     r9, [rbp+0A0h+var_F0]
0x1800dc9af  mov     [rsp+1A0h+var_178], rcx
0x1800dc9b4  mov     rdx, rbx
0x1800dc9b7  lea     rcx, [rbp+0A0h+var_110]
0x1800dc9bb  mov     [rbp+0A0h+var_110], rdi
0x1800dc9bf  mov     rax, [rax+80h]
0x1800dc9c6  mov     [rsp+1A0h+var_180], rcx
0x1800dc9cb  mov     rcx, r14
0x1800dc9ce  mov     [rbp+0A0h+var_108], rdi
0x1800dc9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc9d7  mov     r9, [rbp+0A0h+string]
0x1800dc9db  lea     r8, [rbp+0A0h+var_118]
0x1800dc9df  mov     esi, eax
0x1800dc9e1  mov     rax, [rbp+0A0h+var_108]
0x1800dc9e5  mov     [rsp+1A0h+var_178], rax
0x1800dc9ea  mov     ecx, esi
0x1800dc9ec  mov     rax, [rbp+0A0h+var_110]
0x1800dc9f0  mov     [rsp+1A0h+var_180], rax
0x1800dc9f5  call    ?LogReadEntryResult@CPackagedComCatalog@@CAXJAEBUComProgIdRegistrationEntryProperties@@AEBVOpaqueString@@PEAUHSTRING__@@W4ComProgIdRegistrationEntryPropertyFlags@@3@Z; CPackagedComCatalog::LogReadEntryResult(long,ComProgIdRegistrationEntryProperties const &,OpaqueString const &,HSTRING__ *,ComProgIdRegistrationEntryPropertyFlags,ComProgIdRegistrationEntryPropertyFlags)
0x1800dc9fa  test    esi, esi
0x1800dc9fc  js      loc_1800DCB91
0x1800dca02  lea     rcx, [rbp+0A0h+var_F0]
0x1800dca06  call    ??$RegistrationIsSupportedSyntaxVersion@UComProgIdRegistrationEntryProperties@@@@YA_NAEBUComProgIdRegistrationEntryProperties@@@Z; RegistrationIsSupportedSyntaxVersion<ComProgIdRegistrationEntryProperties>(ComProgIdRegistrationEntryProperties const &)
0x1800dca0b  test    al, al
0x1800dca0d  jnz     short loc_1800DCA4E
0x1800dca0f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800dca14  jmp     short loc_1800DCA4E
0x1800dca16  mov     rbx, [rbp+0A0h+string]
0x1800dca1a  xor     ecx, ecx; string
0x1800dca1c  call    cs:__imp_WindowsDeleteString
0x1800dca22  mov     r9, r14
0x1800dca25  mov     byte ptr [rsp+1A0h+var_178], r13b
0x1800dca2a  lea     rdx, [rbp+0A0h+var_118]
0x1800dca2e  mov     [rbp+0A0h+var_118], rdi
0x1800dca32  lea     rcx, [rbp+0A0h+var_F0]
0x1800dca36  mov     [rsp+1A0h+var_180], rbx
0x1800dca3b  call    ??$ResolveAndReadEntryOld@UComProgIdRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAUComProgIdRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@PEAU2@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z; CPackagedComCatalog::ResolveAndReadEntryOld<ComProgIdRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)>(ComProgIdRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,HSTRING__ *,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *))
0x1800dca40  mov     rbx, [rbp+0A0h+var_118]
0x1800dca44  mov     esi, eax
0x1800dca46  test    eax, eax
0x1800dca48  js      loc_1800DCB91
0x1800dca4e  cmp     [rbp+0A0h+var_F0], dil
0x1800dca52  jnz     loc_1800DCAFA
0x1800dca58  cmp     [rbp+0A0h+var_D8], dil
0x1800dca5c  jz      loc_1800DCAEB
0x1800dca62  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800dca68  jz      short loc_1800DCACF
0x1800dca6a  mov     ecx, 3
0x1800dca6f  call    IsWppLevelEnabled
0x1800dca74  test    al, al
0x1800dca76  jz      short loc_1800DCACF
0x1800dca78  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dca7c  xor     edx, edx; length
0x1800dca7e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dca84  mov     rcx, [rbp+0A0h+string]; string
0x1800dca88  xor     edx, edx; length
0x1800dca8a  mov     rdi, rax
0x1800dca8d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dca93  mov     [rsp+1A0h+var_168], rdi
0x1800dca98  lea     rdx, aCpackagedcomca_1; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800dca9f  mov     [rsp+1A0h+var_170], rax
0x1800dcaa4  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dcaab  lea     rax, aWhileResolving; "While resolving ProgId %S, found ProgId"...
0x1800dcab2  mov     [rsp+1A0h+var_178], r15
0x1800dcab7  mov     r9d, 3
0x1800dcabd  mov     [rsp+1A0h+var_180], rax
0x1800dcac2  mov     r8d, 1DB1h
0x1800dcac8  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800dcacd  xor     edi, edi
0x1800dcacf  lea     rdx, [rbp+0A0h+var_D0]
0x1800dcad3  lea     rcx, [rbp+0A0h+string]
0x1800dcad7  call    ??4OpaqueString@@QEAAAEAV0@AEBV0@@Z; OpaqueString::operator=(OpaqueString const &)
0x1800dcadc  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dcae0  call    cs:__imp_WindowsDeleteString
0x1800dcae6  jmp     loc_1800DC96D
0x1800dcaeb  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dcaef  call    cs:__imp_WindowsDeleteString
0x1800dcaf5  jmp     loc_1800DCBA3
0x1800dcafa  cmp     cs:?gfEnableTracing@@3HA, edi; int gfEnableTracing
0x1800dcb00  jz      short loc_1800DCB68
0x1800dcb02  mov     ecx, 3
0x1800dcb07  call    IsWppLevelEnabled
0x1800dcb0c  test    al, al
0x1800dcb0e  jz      short loc_1800DCB68
0x1800dcb10  lea     rdx, [rbp+0A0h+var_EC]; struct _GUID *
0x1800dcb14  lea     rcx, [rbp+0A0h+var_90]; this
0x1800dcb18  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800dcb1d  mov     rcx, [rbp+0A0h+string]; string
0x1800dcb21  xor     edx, edx; length
0x1800dcb23  mov     rdi, rax
0x1800dcb26  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dcb2c  mov     [rsp+1A0h+var_168], rdi
0x1800dcb31  lea     rdx, aCpackagedcomca_1; "CPackagedComCatalog::GetClassInfoFromPr"...
0x1800dcb38  mov     [rsp+1A0h+var_170], rax
0x1800dcb3d  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dcb44  lea     rax, aWhileResolving_0; "While resolving ProgId %S, found ProgId"...
0x1800dcb4b  mov     [rsp+1A0h+var_178], r15
0x1800dcb50  mov     r9d, 3
0x1800dcb56  mov     [rsp+1A0h+var_180], rax
0x1800dcb5b  mov     r8d, 1DA8h
0x1800dcb61  call    ??$ComTraceMessageT@PEAVCClientSet@@_K_K@@YAXPEBD0HW4TraceLevel@@PEBGPEAVCClientSet@@_K4@Z; ComTraceMessageT<CClientSet *,unsigned __int64,unsigned __int64>(char const *,char const *,int,TraceLevel,ushort const *,CClientSet *,unsigned __int64,unsigned __int64)
0x1800dcb66  xor     edi, edi
0x1800dcb68  mov     rax, qword ptr [rbp+0A0h+var_EC.Data1]
0x1800dcb6c  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dcb70  mov     qword ptr [rbp+0A0h+var_A0], rax
0x1800dcb74  mov     rax, qword ptr [rbp+0A0h+var_EC.Data4]
0x1800dcb78  mov     qword ptr [rbp+0A0h+var_A0+8], rax
0x1800dcb7c  call    cs:__imp_WindowsDeleteString
0x1800dcb82  cmp     esi, 8007000Dh
0x1800dcb88  jnz     short loc_1800DCBAA
0x1800dcb8a  mov     esi, 80040153h
0x1800dcb8f  jmp     short loc_1800DCC01
0x1800dcb91  mov     rcx, [rbp+0A0h+var_D0]; string
0x1800dcb95  call    cs:__imp_WindowsDeleteString
0x1800dcb9b  cmp     esi, 80070002h
0x1800dcba1  jnz     short loc_1800DCB82
0x1800dcba3  mov     esi, 80040154h
0x1800dcba8  jmp     short loc_1800DCC01
0x1800dcbaa  test    esi, esi
0x1800dcbac  js      short loc_1800DCC01
0x1800dcbae  mov     rax, [rbp+0A0h+var_100]
0x1800dcbb2  lea     r9, [rbp+0A0h+var_118]
0x1800dcbb6  mov     [rsp+1A0h+var_130], rdi
0x1800dcbbb  xor     edx, edx
0x1800dcbbd  mov     [rsp+1A0h+var_138], edi
0x1800dcbc1  mov     r8, r14
0x1800dcbc4  mov     [rsp+1A0h+var_140], rdi
0x1800dcbc9  mov     [rsp+1A0h+var_148], edi
0x1800dcbcd  mov     [rsp+1A0h+var_150], rdi
0x1800dcbd2  lea     ecx, [rdx+6]
0x1800dcbd5  mov     [rsp+1A0h+var_158], edi
0x1800dcbd9  mov     [rsp+1A0h+var_160], r12
0x1800dcbde  mov     [rsp+1A0h+var_168], rax
0x1800dcbe3  lea     rax, [rbp+0A0h+var_A0]
0x1800dcbe7  mov     byte ptr [rsp+1A0h+var_170], r13b
0x1800dcbec  mov     [rsp+1A0h+var_178], rax
0x1800dcbf1  mov     byte ptr [rsp+1A0h+var_180], dil
0x1800dcbf6  call    ?GetClassInfoWorker@CPackagedComCatalog@@CAJW4tagCLSCTX@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBVOpaqueString@@_NAEBU_GUID@@45PEAPEAXW4ComRegistrationVisibility@@PEBGIQEBQEAUHSTRING__@@I9@Z; CPackagedComCatalog::GetClassInfoWorker(tagCLSCTX,IUserTokenInternal *,IPackagedComCatalogContext *,OpaqueString const &,bool,_GUID const &,bool,_GUID const &,void * *,ComRegistrationVisibility,ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800dcbfb  mov     rbx, [rbp+0A0h+var_118]
0x1800dcbff  mov     esi, eax
0x1800dcc01  mov     rcx, [rbp+0A0h+string]; string
0x1800dcc05  call    cs:__imp_WindowsDeleteString
0x1800dcc0b  mov     rcx, rbx; string
0x1800dcc0e  mov     [rbp+0A0h+string], rdi
0x1800dcc12  call    cs:__imp_WindowsDeleteString
0x1800dcc18  mov     eax, esi
0x1800dcc1a  mov     rcx, [rbp+0A0h+var_40]
0x1800dcc1e  xor     rcx, rsp; StackCookie
0x1800dcc21  call    __security_check_cookie
0x1800dcc26  mov     rbx, [rsp+1A0h+arg_10]
0x1800dcc2e  add     rsp, 170h
0x1800dcc35  pop     r15
0x1800dcc37  pop     r14
0x1800dcc39  pop     r13
0x1800dcc3b  pop     r12
0x1800dcc3d  pop     rdi
0x1800dcc3e  pop     rsi
0x1800dcc3f  pop     rbp
0x1800dcc40  retn
```
