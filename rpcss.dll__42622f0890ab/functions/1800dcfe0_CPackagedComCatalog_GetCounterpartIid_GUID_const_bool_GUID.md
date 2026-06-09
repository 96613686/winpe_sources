# CPackagedComCatalog::GetCounterpartIid(_GUID const &,bool,_GUID *)

- ea: `0x1800dcfe0`
- end: `0x1800dd29a`
- name: `?GetCounterpartIid@CPackagedComCatalog@@UEAAJAEBU_GUID@@_NPEAU2@@Z`
- size: `698`
- prototype: `int(CPackagedComCatalog *__hidden this, const struct _GUID *, bool, struct _GUID *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180005c40`
- `0x18000d4c4`
- `0x180016160`
- `0x180034540`
- `0x18005ced0`
- `0x18008e98c`
- `0x1800a5cfc`
- `0x1800b27e0`
- `0x1800cb210`
- `0x1800d4448`
- `0x1800dcfe0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd24d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd25b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd124`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd24d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800dd25b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd1e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800dd1e7`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800dd050`
- `combase!__imp_RoGetRegistrationStoreContext` at `0x1800dd050`

## string_xrefs

- `0x1800dd227`: `onecore\com\combase\catalog\packagedcomcatalog.cpp`
- `0x1800dd21b`: `CPackagedComCatalog::GetCounterpartIid`

## pseudocode

```c
__int64 __fastcall CPackagedComCatalog::GetCounterpartIid(
        CPackagedComCatalog *this,
        struct _GUID *a2,
        char a3,
        struct _GUID *a4)
{
  int RegistrationStoreContext; // eax
  int v9; // ebx
  char IsUserHiveOk; // si
  char v11; // dl
  char v12; // bl
  __int64 v13; // rdi
  __int64 v14; // r8
  __int64 v15; // r9
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
  int v27; // [rsp+50h] [rbp-C0h]
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
             (__int64)v31,
             (__int64)&string,
             v14,
             v15,
             (int)&v29,
             v13,
             (__int64)a2,
             (__int64)v30,
             v12,
             IsUserHiveOk,
             v27);
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
             a2,
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
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          WindowsGetStringRawBuffer(string, 0);
          v21 = CGuidStr::CGuidStr((CGuidStr *)v49, a2);
          v24 = L"True";
          if ( !a3 )
            v24 = L"False";
          ComTraceMessageT<unsigned short *,unsigned short const *,unsigned short const *,long>(
            (__int64)"onecore\\com\\combase\\catalog\\packagedcomcatalog.cpp",
            (__int64)"CPackagedComCatalog::GetCounterpartIid",
            0xB54u,
            v22,
            (__int64)L"Failed to convert between sync and async IIDs for packaged interface. IID=%ws PackageName=%S SyncTo"
                      "Async=%S hr=%!HRESULT!",
            (__int64)v21,
            v23,
            (__int64)v24,
            0x80040150);
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
0x1800dcfe0  mov     [rsp-8+arg_0], rbx
0x1800dcfe5  push    rbp
0x1800dcfe6  push    rsi
0x1800dcfe7  push    rdi
0x1800dcfe8  push    r12
0x1800dcfea  push    r13
0x1800dcfec  push    r14
0x1800dcfee  push    r15
0x1800dcff0  lea     rbp, [rsp-90h]
0x1800dcff8  sub     rsp, 1A0h
0x1800dcfff  mov     rax, cs:__security_cookie
0x1800dd006  xor     rax, rsp
0x1800dd009  mov     [rbp+0C0h+var_40], rax
0x1800dd010  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800dd017  mov     rdi, rcx
0x1800dd01a  xor     r13d, r13d
0x1800dd01d  lea     rcx, [rbp+0C0h+var_138]
0x1800dd021  mov     [rbp+0C0h+var_138], r13
0x1800dd025  movdqu  xmmword ptr [r9], xmm0
0x1800dd02a  mov     r12, r9
0x1800dd02d  mov     r14b, r8b
0x1800dd030  mov     r15, rdx
0x1800dd033  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dd038  xor     edx, edx
0x1800dd03a  lea     rax, [rbp+0C0h+var_138]
0x1800dd03e  lea     r9, _GUID_3d36d086_c789_44cc_9d8c_cb3b5f8eeada
0x1800dd045  mov     [rsp+1D0h+var_1B0], rax
0x1800dd04a  xor     r8d, r8d
0x1800dd04d  lea     ecx, [rdx+1]
0x1800dd050  call    cs:__imp_RoGetRegistrationStoreContext
0x1800dd056  xorps   xmm0, xmm0
0x1800dd059  mov     [rbp+0C0h+var_120], r13w
0x1800dd05e  mov     [rbp+0C0h+var_11C], r13b
0x1800dd062  xorps   xmm1, xmm1
0x1800dd065  mov     [rbp+0C0h+var_108], r13b
0x1800dd069  mov     ebx, eax
0x1800dd06b  mov     [rbp+0C0h+var_F4], r13b
0x1800dd06f  mov     [rbp+0C0h+var_E0], r13b
0x1800dd073  mov     [rbp+0C0h+var_C8], r13b
0x1800dd077  mov     [rbp+0C0h+var_C0], r13
0x1800dd07b  mov     [rbp+0C0h+var_B8], r13w
0x1800dd080  mov     [rbp+0C0h+var_B4], r13b
0x1800dd084  mov     [rbp+0C0h+var_B0], r13d
0x1800dd088  mov     [rbp+0C0h+var_AC], r13b
0x1800dd08c  mov     [rbp+0C0h+var_A8], r13d
0x1800dd090  mov     [rbp+0C0h+var_A4], r13b
0x1800dd094  mov     [rbp+0C0h+var_A0], r13d
0x1800dd098  mov     [rbp+0C0h+string], r13
0x1800dd09c  movups  [rbp+0C0h+var_118], xmm0
0x1800dd0a0  movups  [rbp+0C0h+var_104], xmm1
0x1800dd0a4  movups  [rbp+0C0h+var_F0], xmm0
0x1800dd0a8  movups  [rbp+0C0h+var_DC], xmm1
0x1800dd0ac  test    eax, eax
0x1800dd0ae  js      loc_1800DD249
0x1800dd0b4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800dd0bb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800dd0c0  lea     rcx, [rdi-10h]; this
0x1800dd0c4  mov     dl, al
0x1800dd0c6  call    ?IsUserHiveOk@CPackagedComCatalog@@AEBA_NXZ; CPackagedComCatalog::IsUserHiveOk(void)
0x1800dd0cb  mov     rcx, [rbp+0C0h+string]; string
0x1800dd0cf  mov     sil, al
0x1800dd0d2  test    dl, dl
0x1800dd0d4  jz      short loc_1800DD120
0x1800dd0d6  mov     bl, [rdi+28h]
0x1800dd0d9  mov     rdi, [rbp+0C0h+var_138]
0x1800dd0dd  call    cs:__imp_WindowsDeleteString
0x1800dd0e3  mov     [rsp+1D0h+var_188], sil
0x1800dd0e8  lea     rax, [rbp+0C0h+var_130]
0x1800dd0ec  mov     byte ptr [rsp+1D0h+var_190], bl
0x1800dd0f0  lea     rdx, [rbp+0C0h+string]
0x1800dd0f4  mov     [rsp+1D0h+var_198], rax
0x1800dd0f9  lea     rcx, [rbp+0C0h+var_120]
0x1800dd0fd  mov     [rsp+1D0h+var_1A0], r15
0x1800dd102  mov     [rsp+1D0h+var_1A8], rdi
0x1800dd107  mov     [rbp+0C0h+string], r13
0x1800dd10b  mov     [rbp+0C0h+var_130], r13
0x1800dd10f  call    ??$DoPackageAwareLookup@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU1@AEA_N@Z@EntryLookup@CPackagedComCatalog@@SAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEA_NPEAW4ComRegistrationVisibility@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@AEBVOpaqueString@@_N8W44@P6AJ7V?$optional@W4InstallScope@RegistrationStoreContext@@@std@@AEBU2@AEA_N@ZPEBGIQEBQEAU3@IQEBQEAU3@@Z; CPackagedComCatalog::EntryLookup::DoPackageAwareLookup<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &)>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,bool *,ComRegistrationVisibility *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,OpaqueString const &,bool,bool,ComRegistrationVisibility,long (*)(OpaqueString const &,std::optional<RegistrationStoreContext::InstallScope>,ComInterfaceRegistrationEntryProperties const &,bool &),ushort const *,uint,HSTRING__ * const * const,uint,HSTRING__ * const * const)
0x1800dd114  xor     ecx, ecx; string
0x1800dd116  mov     ebx, eax
0x1800dd118  call    cs:__imp_WindowsDeleteString
0x1800dd11e  jmp     short loc_1800DD175
0x1800dd120  mov     rbx, [rbp+0C0h+var_138]
0x1800dd124  call    cs:__imp_WindowsDeleteString
0x1800dd12a  mov     [rbp+0C0h+string], r13
0x1800dd12e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800dd135  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800dd13a  test    al, al
0x1800dd13c  jz      short loc_1800DD143
0x1800dd13e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800dd143  lea     rax, ??$AlwaysApplicableOld@UComProgIdRegistrationEntryProperties@@@CPackagedComCatalog@@CAJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBUComProgIdRegistrationEntryProperties@@PEA_N@Z; CPackagedComCatalog::AlwaysApplicableOld<ComProgIdRegistrationEntryProperties>(OpaqueString const &,RegistrationStoreContext::InstallScope,ComProgIdRegistrationEntryProperties const &,bool *)
0x1800dd14a  mov     dword ptr [rbp+0C0h+var_130], r13d
0x1800dd14e  mov     [rsp+1D0h+var_190], rax
0x1800dd153  lea     r8, [rbp+0C0h+var_130]
0x1800dd157  mov     byte ptr [rsp+1D0h+var_1A0], sil
0x1800dd15c  lea     rdx, [rbp+0C0h+string]
0x1800dd160  mov     [rsp+1D0h+var_1A8], r15
0x1800dd165  lea     rcx, [rbp+0C0h+var_120]
0x1800dd169  mov     [rsp+1D0h+var_1B0], rbx
0x1800dd16e  call    ??$ResolveAndReadEntryWithCustomRankingOld@UComInterfaceRegistrationEntryProperties@@HVCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@CPackagedComCatalog@@CAJAEAU1@PEAPEAUHSTRING__@@PEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@CPackagedComCatalog@@CAJAEAUComInterfaceRegistrationEntryProperties@@PEAPEAUHSTRING__@@PEAHPEAUIUserTokenInternal@@PEAUIPackagedComCatalogContext@@AEBU_GUID@@_NPEBVPackageFilter@@VCheckApplicability@?1???$ResolveAndReadEntryOld@UComInterfaceRegistrationEntryProperties@@P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@0@CAJ0134567P6AJAEBVOpaqueString@@W4InstallScope@RegistrationStoreContext@@AEBU1@PEA_N@Z@Z@@Z; CPackagedComCatalog::ResolveAndReadEntryWithCustomRankingOld<ComInterfaceRegistrationEntryProperties,int,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *)>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,int *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,`CPackagedComCatalog::ResolveAndReadEntryOld<ComInterfaceRegistrationEntryProperties,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *)>(ComInterfaceRegistrationEntryProperties &,HSTRING__ * *,IUserTokenInternal *,IPackagedComCatalogContext *,_GUID const &,bool,PackageFilter const *,long (*)(OpaqueString const &,RegistrationStoreContext::InstallScope,ComInterfaceRegistrationEntryProperties const &,bool *))'::`2'::CheckApplicability)
0x1800dd173  mov     ebx, eax
0x1800dd175  cmp     ebx, 80070002h
0x1800dd17b  jnz     short loc_1800DD187
0x1800dd17d  mov     ebx, 80040155h
0x1800dd182  jmp     loc_1800DD249
0x1800dd187  test    ebx, ebx
0x1800dd189  js      loc_1800DD249
0x1800dd18f  movzx   ecx, [rbp+0C0h+var_108]
0x1800dd193  test    r14b, r14b
0x1800dd196  movzx   eax, [rbp+0C0h+var_F4]
0x1800dd19a  cmovnz  ecx, eax
0x1800dd19d  test    cl, cl
0x1800dd19f  jz      short loc_1800DD1BE
0x1800dd1a1  test    r14b, r14b
0x1800dd1a4  lea     rax, [rbp+0C0h+var_104]
0x1800dd1a8  lea     rcx, [rbp+0C0h+var_F0]
0x1800dd1ac  cmovnz  rax, rcx
0x1800dd1b0  movups  xmm0, xmmword ptr [rax]
0x1800dd1b3  movdqu  xmmword ptr [r12], xmm0
0x1800dd1b9  jmp     loc_1800DD249
0x1800dd1be  mov     eax, cs:dword_18014E4B8
0x1800dd1c4  mov     ebx, 80040150h
0x1800dd1c9  test    eax, eax
0x1800dd1cb  jnz     short loc_1800DD1E1
0x1800dd1cd  cmp     cs:?gfEnableTracing@@3HA, r13d; int gfEnableTracing
0x1800dd1d4  jz      short loc_1800DD249
0x1800dd1d6  xor     ecx, ecx
0x1800dd1d8  call    IsWppLevelEnabled
0x1800dd1dd  test    al, al
0x1800dd1df  jz      short loc_1800DD249
0x1800dd1e1  mov     rcx, [rbp+0C0h+string]; string
0x1800dd1e5  xor     edx, edx; length
0x1800dd1e7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800dd1ed  mov     rdx, r15; struct _GUID *
0x1800dd1f0  lea     rcx, [rbp+0C0h+var_90]; this
0x1800dd1f4  mov     r11, rax
0x1800dd1f7  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800dd1fc  mov     dword ptr [rsp+1D0h+var_190], ebx
0x1800dd200  lea     rdx, aFalse_0; "False"
0x1800dd207  test    r14b, r14b
0x1800dd20a  lea     rcx, aTrue_0; "True"
0x1800dd211  mov     r8d, 0B54h
0x1800dd217  cmovz   rcx, rdx
0x1800dd21b  lea     rdx, aCpackagedcomca_4; "CPackagedComCatalog::GetCounterpartIid"
0x1800dd222  mov     [rsp+1D0h+var_198], rcx
0x1800dd227  lea     rcx, aOnecoreComComb_81; "onecore\\com\\combase\\catalog\\package"...
0x1800dd22e  mov     [rsp+1D0h+var_1A0], r11
0x1800dd233  mov     [rsp+1D0h+var_1A8], rax
0x1800dd238  lea     rax, aFailedToConver; "Failed to convert between sync and asyn"...
0x1800dd23f  mov     [rsp+1D0h+var_1B0], rax
0x1800dd244  call    ??$ComTraceMessageT@PEAGPEBGPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG22J@Z; ComTraceMessageT<ushort *,ushort const *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ushort const *,long)
0x1800dd249  mov     rcx, [rbp+0C0h+string]; string
0x1800dd24d  call    cs:__imp_WindowsDeleteString
0x1800dd253  mov     rcx, [rbp+0C0h+var_C0]; string
0x1800dd257  mov     [rbp+0C0h+string], r13
0x1800dd25b  call    cs:__imp_WindowsDeleteString
0x1800dd261  lea     rcx, [rbp+0C0h+var_138]
0x1800dd265  mov     [rbp+0C0h+var_C0], r13
0x1800dd269  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800dd26e  mov     eax, ebx
0x1800dd270  mov     rcx, [rbp+0C0h+var_40]
0x1800dd277  xor     rcx, rsp; StackCookie
0x1800dd27a  call    __security_check_cookie
0x1800dd27f  mov     rbx, [rsp+1D0h+arg_0]
0x1800dd287  add     rsp, 1A0h
0x1800dd28e  pop     r15
0x1800dd290  pop     r14
0x1800dd292  pop     r13
0x1800dd294  pop     r12
0x1800dd296  pop     rdi
0x1800dd297  pop     rsi
0x1800dd298  pop     rbp
0x1800dd299  retn
```
