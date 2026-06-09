# CPackagedComCatalog::GetCounterpartIid(_GUID const &,bool,_GUID *)

- ea: `0x1800e3f10`
- end: `0x1800e41f5`
- name: `?GetCounterpartIid@CPackagedComCatalog@@UEAAJAEBU_GUID@@_NPEAU2@@Z`
- size: `741`
- prototype: `int(CPackagedComCatalog *__hidden this, const struct _GUID *, bool, struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800065a4`
- `0x18001a374`
- `0x18002750c`
- `0x180034260`
- `0x180061d74`
- `0x180095c0c`
- `0x1800aad5c`
- `0x1800b7ac0`
- `0x1800d1354`
- `0x1800dae3c`
- `0x1800e3f10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e419b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e41af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4013`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4054`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4066`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e419b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e41af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e412f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e412f`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800e3f80`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800e3f80`

## string_xrefs

- `0x1800e4175`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800e4169`: `CPackagedComCatalog::GetCounterpartIid`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetCounterpartIid(
        CPackagedComCatalog *this,
        const struct _GUID *a2,
        char a3,
        struct _GUID *a4)
{
  int RegistrationStoreContext; // eax
  int v9; // ebx
  char IsUserHiveOk; // si
  char v11; // dl
  char v12; // bl
  __int64 v13; // rdi
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // r9
  char v19; // cl
  struct _GUID *v20; // rax
  CGuidStr *v21; // rax
  int v22; // r9d
  __int64 v23; // r11
  const wchar_t *v24; // rcx
  int v26; // [rsp+38h] [rbp-D8h]
  __int64 v27; // [rsp+40h] [rbp-D0h]
  HSTRING string; // [rsp+90h] [rbp-80h] BYREF
  __int64 v29; // [rsp+98h] [rbp-78h] BYREF
  _QWORD v30[2]; // [rsp+A0h] [rbp-70h] BYREF
  _WORD v31[2]; // [rsp+B0h] [rbp-60h] BYREF
  char v32; // [rsp+B4h] [rbp-5Ch]
  __int128 v33; // [rsp+B8h] [rbp-58h]
  char v34; // [rsp+C8h] [rbp-48h]
  __int128 v35; // [rsp+CCh] [rbp-44h] BYREF
  char v36; // [rsp+DCh] [rbp-34h]
  __int128 v37; // [rsp+E0h] [rbp-30h] BYREF
  char v38; // [rsp+F0h] [rbp-20h]
  __int128 v39; // [rsp+F4h] [rbp-1Ch]
  char v40; // [rsp+108h] [rbp-8h]
  HSTRING v41; // [rsp+110h] [rbp+0h]
  __int16 v42; // [rsp+118h] [rbp+8h]
  char v43; // [rsp+11Ch] [rbp+Ch]
  int v44; // [rsp+120h] [rbp+10h]
  char v45; // [rsp+124h] [rbp+14h]
  int v46; // [rsp+128h] [rbp+18h]
  char v47; // [rsp+12Ch] [rbp+1Ch]
  int v48; // [rsp+130h] [rbp+20h]
  _BYTE v49[80]; // [rsp+140h] [rbp+30h] BYREF

  v29 = 0;
  *a4 = GUID_NULL;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  RegistrationStoreContext = RoGetRegistrationStoreContext(1, 0, 0, &GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada);
  v31[0] = 0;
  v32 = 0;
  v34 = 0;
  v9 = RegistrationStoreContext;
  v36 = 0;
  v38 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  string = 0;
  v33 = 0;
  v35 = 0;
  v37 = 0;
  v39 = 0;
  if ( RegistrationStoreContext >= 0 )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl);
    IsUserHiveOk = CPackagedComCatalog::IsUserHiveOk((CPackagedComCatalog *)((char *)this - 16));
    if ( v11 )
    {
      v12 = *((_BYTE *)this + 40);
      v13 = v29;
      WindowsDeleteString(string);
      string = 0;
      v30[0] = 0;
      v9 = CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<enum RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &)>(
             (unsigned int)v31,
             (unsigned int)&string,
             v14,
             v15,
             (unsigned int)&v29,
             v13,
             (__int64)a2,
             (__int64)v30,
             v12,
             IsUserHiveOk);
      WindowsDeleteString(0);
    }
    else
    {
      v16 = v29;
      WindowsDeleteString(string);
      string = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v17);
      LODWORD(v30[0]) = 0;
      v9 = Z::ResolveAndReadEntryWithCustomRankingOld<ComInterfaceRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *)>'::`2'::CheckApplicability,signed char,PEAPEAUHSTRING__::AEAU1 const huge &,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,enum RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *)>(
             (__int64)v31,
             &string,
             v30,
             v18,
             v16,
             (__int64)a2,
             IsUserHiveOk,
             v26,
             (__int64 (__fastcall *)(__int64 *, _QWORD, int *, char *))CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>);
    }
    if ( v9 == -2147024894 )
    {
      v9 = -2147221163;
    }
    else if ( v9 >= 0 )
    {
      v19 = v34;
      if ( a3 )
        v19 = v36;
      if ( v19 )
      {
        v20 = (struct _GUID *)&v35;
        if ( a3 )
          v20 = (struct _GUID *)&v37;
        *a4 = *v20;
      }
      else
      {
        v9 = -2147221168;
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          WindowsGetStringRawBuffer(string, 0);
          v21 = CGuidStr::CGuidStr((CGuidStr *)v49, a2);
          LODWORD(v27) = -2147221168;
          v24 = L"True";
          if ( !a3 )
            v24 = L"False";
          ComTraceMessageT<unsigned short *,unsigned short const *,unsigned short const *,long>(
            (unsigned int)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (unsigned int)"CPackagedComCatalog::GetCounterpartIid",
            2900,
            v22,
            (__int64)L"Failed to convert between sync and async IIDs for packaged interface. IID=%ws PackageName=%S SyncTo"
                      "Async=%S hr=%!HRESULT!",
            v21,
            v23,
            v24,
            v27);
        }
      }
    }
  }
  WindowsDeleteString(string);
  string = 0;
  WindowsDeleteString(v41);
  v41 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800e3f10  mov     [rsp-8+arg_0], rbx
0x1800e3f15  push    rbp
0x1800e3f16  push    rsi
0x1800e3f17  push    rdi
0x1800e3f18  push    r12
0x1800e3f1a  push    r13
0x1800e3f1c  push    r14
0x1800e3f1e  push    r15
0x1800e3f20  lea     rbp, [rsp-90h]
0x1800e3f28  sub     rsp, 1A0h
0x1800e3f2f  mov     rax, cs:__security_cookie
0x1800e3f36  xor     rax, rsp
0x1800e3f39  mov     [rbp+0C0h+var_40], rax
0x1800e3f40  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800e3f47  mov     rdi, rcx
0x1800e3f4a  xor     r13d, r13d
0x1800e3f4d  lea     rcx, [rbp+0C0h+var_138]
0x1800e3f51  mov     [rbp+0C0h+var_138], r13
0x1800e3f55  movdqu  xmmword ptr [r9], xmm0
0x1800e3f5a  mov     r12, r9
0x1800e3f5d  mov     r14b, r8b
0x1800e3f60  mov     r15, rdx
0x1800e3f63  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e3f68  xor     edx, edx
0x1800e3f6a  lea     rax, [rbp+0C0h+var_138]
0x1800e3f6e  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800e3f75  mov     [rsp+1D0h+var_1B0], rax
0x1800e3f7a  xor     r8d, r8d
0x1800e3f7d  lea     ecx, [rdx+1]
0x1800e3f80  call    cs:__imp_RoGetRegistrationStoreContext
0x1800e3f87  nop     dword ptr [rax+rax+00h]
0x1800e3f8c  xorps   xmm0, xmm0
0x1800e3f8f  mov     [rbp+0C0h+var_120], r13w
0x1800e3f94  mov     [rbp+0C0h+var_11C], r13b
0x1800e3f98  xorps   xmm1, xmm1
0x1800e3f9b  mov     [rbp+0C0h+var_108], r13b
0x1800e3f9f  mov     ebx, eax
0x1800e3fa1  mov     [rbp+0C0h+var_F4], r13b
0x1800e3fa5  mov     [rbp+0C0h+var_E0], r13b
0x1800e3fa9  mov     [rbp+0C0h+var_C8], r13b
0x1800e3fad  mov     [rbp+0C0h+var_C0], r13
0x1800e3fb1  mov     [rbp+0C0h+var_B8], r13w
0x1800e3fb6  mov     [rbp+0C0h+var_B4], r13b
0x1800e3fba  mov     [rbp+0C0h+var_B0], r13d
0x1800e3fbe  mov     [rbp+0C0h+var_AC], r13b
0x1800e3fc2  mov     [rbp+0C0h+var_A8], r13d
0x1800e3fc6  mov     [rbp+0C0h+var_A4], r13b
0x1800e3fca  mov     [rbp+0C0h+var_A0], r13d
0x1800e3fce  mov     [rbp+0C0h+string], r13
0x1800e3fd2  movups  [rbp+0C0h+var_118], xmm0
0x1800e3fd6  movups  [rbp+0C0h+var_104], xmm1
0x1800e3fda  movups  [rbp+0C0h+var_F0], xmm0
0x1800e3fde  movups  [rbp+0C0h+var_DC], xmm1
0x1800e3fe2  test    eax, eax
0x1800e3fe4  js      loc_1800E4197
0x1800e3fea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800e3ff1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800e3ff6  lea     rcx, [rdi-10h]; this
0x1800e3ffa  mov     dl, al
0x1800e3ffc  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800e4001  mov     rcx, [rbp+0C0h+string]; string
0x1800e4005  mov     sil, al
0x1800e4008  test    dl, dl
0x1800e400a  jz      short loc_1800E4062
0x1800e400c  mov     bl, [rdi+28h]
0x1800e400f  mov     rdi, [rbp+0C0h+var_138]
0x1800e4013  call    cs:__imp_WindowsDeleteString
0x1800e401a  nop     dword ptr [rax+rax+00h]
0x1800e401f  mov     [rsp+1D0h+var_188], sil
0x1800e4024  lea     rax, [rbp+0C0h+var_130]
0x1800e4028  mov     byte ptr [rsp+1D0h+var_190], bl
0x1800e402c  lea     rdx, [rbp+0C0h+string]
0x1800e4030  mov     [rsp+1D0h+var_198], rax
0x1800e4035  lea     rcx, [rbp+0C0h+var_120]
0x1800e4039  mov     [rsp+1D0h+var_1A0], r15
0x1800e403e  mov     [rsp+1D0h+var_1A8], rdi
0x1800e4043  mov     [rbp+0C0h+string], r13
0x1800e4047  mov     [rbp+0C0h+var_130], r13
0x1800e404b  call    ??$DoPackageAwareLookup@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &)>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800e4050  xor     ecx, ecx; string
0x1800e4052  mov     ebx, eax
0x1800e4054  call    cs:__imp_WindowsDeleteString
0x1800e405b  nop     dword ptr [rax+rax+00h]
0x1800e4060  jmp     short loc_1800E40BD
0x1800e4062  mov     rbx, [rbp+0C0h+var_138]
0x1800e4066  call    cs:__imp_WindowsDeleteString
0x1800e406d  nop     dword ptr [rax+rax+00h]
0x1800e4072  mov     [rbp+0C0h+string], r13
0x1800e4076  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800e407d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800e4082  test    al, al
0x1800e4084  jz      short loc_1800E408B
0x1800e4086  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e408b  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x1800e4092  mov     dword ptr [rbp+0C0h+var_130], r13d
0x1800e4096  mov     [rsp+1D0h+var_190], rax
0x1800e409b  lea     r8, [rbp+0C0h+var_130]
0x1800e409f  mov     byte ptr [rsp+1D0h+var_1A0], sil
0x1800e40a4  lea     rdx, [rbp+0C0h+string]
0x1800e40a8  mov     [rsp+1D0h+var_1A8], r15
0x1800e40ad  lea     rcx, [rbp+0C0h+var_120]
0x1800e40b1  mov     [rsp+1D0h+var_1B0], rbx
0x1800e40b6  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComInterfaceRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComInterfaceRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *)>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *)>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x1800e40bb  mov     ebx, eax
0x1800e40bd  cmp     ebx, 80070002h
0x1800e40c3  jnz     short loc_1800E40CF
0x1800e40c5  mov     ebx, 80040155h
0x1800e40ca  jmp     loc_1800E4197
0x1800e40cf  test    ebx, ebx
0x1800e40d1  js      loc_1800E4197
0x1800e40d7  movzx   ecx, [rbp+0C0h+var_108]
0x1800e40db  test    r14b, r14b
0x1800e40de  movzx   eax, [rbp+0C0h+var_F4]
0x1800e40e2  cmovnz  ecx, eax
0x1800e40e5  test    cl, cl
0x1800e40e7  jz      short loc_1800E4106
0x1800e40e9  test    r14b, r14b
0x1800e40ec  lea     rax, [rbp+0C0h+var_104]
0x1800e40f0  lea     rcx, [rbp+0C0h+var_F0]
0x1800e40f4  cmovnz  rax, rcx
0x1800e40f8  movups  xmm0, xmmword ptr [rax]
0x1800e40fb  movdqu  xmmword ptr [r12], xmm0
0x1800e4101  jmp     loc_1800E4197
0x1800e4106  mov     eax, cs:dword_1801574B8
0x1800e410c  mov     ebx, 80040150h
0x1800e4111  test    eax, eax
0x1800e4113  jnz     short loc_1800E4129
0x1800e4115  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800e411c  jz      short loc_1800E4197
0x1800e411e  xor     ecx, ecx
0x1800e4120  call    IsWppLevelEnabled
0x1800e4125  test    al, al
0x1800e4127  jz      short loc_1800E4197
0x1800e4129  mov     rcx, [rbp+0C0h+string]; string
0x1800e412d  xor     edx, edx; length
0x1800e412f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4136  nop     dword ptr [rax+rax+00h]
0x1800e413b  mov     rdx, r15; struct _GUID *
0x1800e413e  lea     rcx, [rbp+0C0h+var_90]; this
0x1800e4142  mov     r11, rax
0x1800e4145  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800e414a  mov     dword ptr [rsp+1D0h+var_190], ebx
0x1800e414e  lea     rdx, aFalse_0; "False"
0x1800e4155  test    r14b, r14b
0x1800e4158  lea     rcx, aTrue_0; "True"
0x1800e415f  mov     r8d, 0B54h
0x1800e4165  cmovz   rcx, rdx
0x1800e4169  lea     rdx, aCpackagedcomca_4; "CPackagedComCatalog::GetCounterpartIid"
0x1800e4170  mov     [rsp+1D0h+var_198], rcx
0x1800e4175  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800e417c  mov     [rsp+1D0h+var_1A0], r11
0x1800e4181  mov     [rsp+1D0h+var_1A8], rax
0x1800e4186  lea     rax, aFailedToConver; "Failed to convert between sync and asyn"...
0x1800e418d  mov     [rsp+1D0h+var_1B0], rax
0x1800e4192  call    ??$ComTraceMessageT@PEAGPEBGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG22J@Z; ComTraceMessageT<ushort *,ushort const *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ushort const *,long)
0x1800e4197  mov     rcx, [rbp+0C0h+string]; string
0x1800e419b  call    cs:__imp_WindowsDeleteString
0x1800e41a2  nop     dword ptr [rax+rax+00h]
0x1800e41a7  mov     rcx, [rbp+0C0h+var_C0]; string
0x1800e41ab  mov     [rbp+0C0h+string], r13
0x1800e41af  call    cs:__imp_WindowsDeleteString
0x1800e41b6  nop     dword ptr [rax+rax+00h]
0x1800e41bb  lea     rcx, [rbp+0C0h+var_138]
0x1800e41bf  mov     [rbp+0C0h+var_C0], r13
0x1800e41c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e41c8  mov     eax, ebx
0x1800e41ca  mov     rcx, [rbp+0C0h+var_40]
0x1800e41d1  xor     rcx, rsp; StackCookie
0x1800e41d4  call    __security_check_cookie
0x1800e41d9  mov     rbx, [rsp+1D0h+arg_0]
0x1800e41e1  add     rsp, 1A0h
0x1800e41e8  pop     r15
0x1800e41ea  pop     r14
0x1800e41ec  pop     r13
0x1800e41ee  pop     r12
0x1800e41f0  pop     rdi
0x1800e41f1  pop     rsi
0x1800e41f2  pop     rbp
0x1800e41f3  retn
```
