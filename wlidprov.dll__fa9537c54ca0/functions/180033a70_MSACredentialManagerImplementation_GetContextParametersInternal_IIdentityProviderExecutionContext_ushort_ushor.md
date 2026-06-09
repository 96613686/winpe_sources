# MSACredentialManagerImplementation::GetContextParametersInternal(IIdentityProviderExecutionContext *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x180033a70`
- end: `0x180034075`
- name: `?GetContextParametersInternal@MSACredentialManagerImplementation@@EEAAJPEAVIIdentityProviderExecutionContext@@PEAPEAG11111@Z`
- size: `1541`
- prototype: `int(MSACredentialManagerImplementation *__hidden this, struct IIdentityProviderExecutionContext *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800034c0`
- `0x180003990`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x180010b80`
- `0x180018164`
- `0x1800205d8`
- `0x180020784`
- `0x180028630`
- `0x18002ac24`
- `0x18002faf4`
- `0x18003056c`
- `0x180030b40`
- `0x180030bac`
- `0x180032c58`
- `0x180033a70`
- `0x180034878`
- `0x180040f4c`
- `0x18004eb64`
- `0x180058010`

## import_xrefs

- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x180033cee`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x180033d1a`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x180033cee`
- `ext-ms-win-security-cfl-l1-1-0!CflFreeBuffer` at `0x180033d1a`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioDataNew` at `0x180033d41`
- `ext-ms-win-security-cfl-l1-1-0!CflGetScenarioDataNew` at `0x180033d41`

## string_xrefs

- `0x180033d83`: `Deserialized username is %ls`
- `0x180033e36`: `hr = CopyToAutoString(platform, spPlatform)`
- `0x180033e83`: `hr = CopyToAutoString(uiflavor, spUiflavor)`
- `0x180033eb2`: `hr = CopyToAutoString(market, spMarket)`
- `0x180033ee1`: `hr = CopyToAutoString(scenarioId, spScenarioId)`
- `0x180033f14`: `hr = CopyToAutoString(hasNgc, spHasNgc)`
- `0x180033f48`: `hr = CopyToAutoString(userName, spUserName)`

## pseudocode

```c
__int64 __fastcall MSACredentialManagerImplementation::GetContextParametersInternal(
        MSACredentialManagerImplementation *this,
        struct IIdentityProviderExecutionContext *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8)
{
  unsigned __int16 *v8; // r12
  const char *v12; // rax
  unsigned int v13; // r8d
  __int64 v14; // rbx
  __int64 *v15; // rax
  int Market; // eax
  int PlatformIdentifiers; // eax
  int InlineUxScenarioId; // eax
  bool HasNgc; // al
  const wchar_t *v20; // rdx
  __int64 v21; // rdx
  unsigned __int8 *v22; // rbx
  __int64 v23; // rbx
  unsigned __int16 *v24; // rbx
  unsigned __int16 *v25; // rdi
  unsigned __int16 *v26; // rsi
  unsigned __int16 *v27; // r14
  unsigned __int16 *v28; // r15
  unsigned __int16 *v29; // rbx
  int v30; // eax
  const char *v31; // rcx
  unsigned int v32; // r8d
  unsigned int v33; // ebx
  const unsigned __int16 *v35; // [rsp+28h] [rbp-E0h]
  __int64 v36; // [rsp+38h] [rbp-D0h] BYREF
  unsigned __int16 *v37; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v38[2]; // [rsp+48h] [rbp-C0h] BYREF
  unsigned __int8 *v39; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int16 *v41; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v42; // [rsp+68h] [rbp-A0h]
  __int64 v43; // [rsp+70h] [rbp-98h]
  unsigned __int16 *v44; // [rsp+78h] [rbp-90h] BYREF
  __int64 v45; // [rsp+80h] [rbp-88h]
  __int64 v46; // [rsp+88h] [rbp-80h]
  unsigned __int16 *v47; // [rsp+90h] [rbp-78h] BYREF
  __int64 v48; // [rsp+98h] [rbp-70h]
  __int64 v49; // [rsp+A0h] [rbp-68h]
  unsigned __int16 *v50; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-58h]
  __int64 v52; // [rsp+B8h] [rbp-50h]
  unsigned __int16 *v53; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-40h]
  __int64 v55; // [rsp+D0h] [rbp-38h]
  unsigned __int16 *v56; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-28h]
  __int64 v58; // [rsp+E8h] [rbp-20h]
  unsigned __int16 *v59; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int16 *v60; // [rsp+F8h] [rbp-10h] BYREF
  unsigned __int16 *v61; // [rsp+100h] [rbp-8h] BYREF
  unsigned __int16 *v62; // [rsp+108h] [rbp+0h] BYREF
  unsigned __int16 *v63; // [rsp+110h] [rbp+8h] BYREF
  unsigned __int16 *v64; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v65[11]; // [rsp+120h] [rbp+18h] BYREF

  v8 = 0;
  LODWORD(v36) = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v64);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v63);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v62);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v61);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v60);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v59);
  v40 = 0;
  v65[1] = &v36;
  v39 = 0;
  v65[3] = qword_18006B4B0;
  v38[0] = 0;
  v65[0] = "MSACredentialManagerImplementation::GetContextParametersInternal";
  v65[2] = 11;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
    "MSACredentialManagerImplementation::GetContextParametersInternal",
    (const char *)0x24A,
    0,
    v35);
  if ( !a3 )
  {
    v12 = "ppPlatform != nullptr";
    v13 = 588;
LABEL_3:
    LODWORD(v36) = -2147467261;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
      "MSACredentialManagerImplementation::GetContextParametersInternal",
      v13,
      -2147467261,
      v12);
    goto LABEL_59;
  }
  if ( !a4 )
  {
    v12 = "ppUiflavor != nullptr";
    v13 = 589;
    goto LABEL_3;
  }
  if ( !a5 )
  {
    v12 = "ppMarket != nullptr";
    v13 = 590;
    goto LABEL_3;
  }
  if ( !a6 )
  {
    v12 = "ppScenarioId != nullptr";
    v13 = 591;
    goto LABEL_3;
  }
  if ( !a7 )
  {
    v12 = "ppHasNgc != nullptr";
    v13 = 592;
    goto LABEL_3;
  }
  if ( !a8 )
  {
    v12 = "ppUserName != nullptr";
    v13 = 593;
    goto LABEL_3;
  }
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  v14 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
  v15 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
  Market = UrlUtilities::GetMarket(v15, &v62);
  LODWORD(v36) = Market;
  if ( Market >= 0 )
  {
    PlatformIdentifiers = UrlContextInfo::GetPlatformIdentifiers(&v64, &v63);
    LODWORD(v36) = PlatformIdentifiers;
    if ( PlatformIdentifiers < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        "MSACredentialManagerImplementation::GetContextParametersInternal",
        0x261u,
        PlatformIdentifiers,
        "hr = UrlContextInfo::GetPlatformIdentifiers(platform, uiflavor)");
      goto LABEL_59;
    }
    InlineUxScenarioId = UrlContextInfo::GetInlineUxScenarioId(v14, &v61);
    LODWORD(v36) = InlineUxScenarioId;
    if ( InlineUxScenarioId < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
        "MSACredentialManagerImplementation::GetContextParametersInternal",
        0x264u,
        InlineUxScenarioId,
        "hr = UrlContextInfo::GetInlineUxScenarioId(pExecutionContextLite, scenarioId)");
      goto LABEL_59;
    }
    HasNgc = UserIdKeyManagerImplementation::HasNgc(a2);
    v20 = L"1";
    if ( !HasNgc )
      v20 = L"0";
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v60, v20);
    LOBYTE(v21) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl'::`2'::impl,
      v21);
    v22 = v39;
    if ( v39 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v37);
      CflFreeBuffer(v22);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v37);
    }
    v23 = v40;
    v39 = 0;
    if ( v40 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v37);
      CflFreeBuffer(v23);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v37);
    }
    v40 = 0;
    LODWORD(v36) = CflGetScenarioDataNew(&v40, &v39, v38, 0);
    if ( (int)v36 >= 0 && v38[0] )
    {
      v37 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v37,
        0);
      if ( (int)DeserializeScenarioContext(v39, v38[0], &v37) >= 0 )
      {
        v24 = v37;
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
          0x279u,
          L"Deserialized username is %ls",
          v37);
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v59, v24);
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
    }
    LODWORD(v36) = 0;
    v25 = 0;
    v56 = 0;
    v26 = 0;
    v58 = 0;
    v27 = 0;
    v28 = 0;
    v57 = 0;
    v29 = 0;
    v53 = 0;
    v55 = 0;
    v54 = 0;
    v50 = 0;
    v52 = 0;
    v51 = 0;
    v47 = 0;
    v49 = 0;
    v48 = 0;
    v44 = 0;
    v46 = 0;
    v45 = 0;
    v41 = 0;
    v43 = 0;
    v42 = 0;
    if ( *((_DWORD *)v64 - 4) )
    {
      v30 = CopyToAutoString<CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(v64);
      LODWORD(v36) = v30;
      if ( v30 < 0 )
      {
        v31 = "hr = CopyToAutoString(platform, spPlatform)";
        v32 = 651;
LABEL_35:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
          "MSACredentialManagerImplementation::GetContextParametersInternal",
          v32,
          v30,
          v31);
LABEL_58:
        Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(&v41);
        Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(&v44);
        Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(&v47);
        Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(&v50);
        Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(&v53);
        Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(&v56);
        goto LABEL_59;
      }
      v25 = v56;
    }
    if ( *((_DWORD *)v63 - 4) )
    {
      v30 = CopyToAutoString<CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(v63);
      LODWORD(v36) = v30;
      if ( v30 < 0 )
      {
        v31 = "hr = CopyToAutoString(uiflavor, spUiflavor)";
        v32 = 656;
        goto LABEL_35;
      }
      v26 = v53;
    }
    if ( *((_DWORD *)v62 - 4) )
    {
      v30 = CopyToAutoString<CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(v62);
      LODWORD(v36) = v30;
      if ( v30 < 0 )
      {
        v31 = "hr = CopyToAutoString(market, spMarket)";
        v32 = 661;
        goto LABEL_35;
      }
      v27 = v50;
    }
    if ( *((_DWORD *)v61 - 4) )
    {
      v30 = CopyToAutoString<CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(v61);
      LODWORD(v36) = v30;
      if ( v30 < 0 )
      {
        v31 = "hr = CopyToAutoString(scenarioId, spScenarioId)";
        v32 = 666;
        goto LABEL_35;
      }
      v28 = v47;
    }
    if ( *((_DWORD *)v60 - 4) )
    {
      v30 = CopyToAutoString<CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(v60);
      LODWORD(v36) = v30;
      if ( v30 < 0 )
      {
        v31 = "hr = CopyToAutoString(hasNgc, spHasNgc)";
        v32 = 671;
        goto LABEL_35;
      }
      v8 = v44;
    }
    if ( *((_DWORD *)v59 - 4) )
    {
      v30 = CopyToAutoString<CoTaskMemAllocFunctor<unsigned short *>,DummyContext>(v59);
      LODWORD(v36) = v30;
      if ( v30 < 0 )
      {
        v31 = "hr = CopyToAutoString(userName, spUserName)";
        v32 = 676;
        goto LABEL_35;
      }
      v29 = v41;
    }
    v56 = 0;
    v57 = 0;
    v53 = 0;
    *a3 = v25;
    v54 = 0;
    v50 = 0;
    v51 = 0;
    *a4 = v26;
    *a5 = v27;
    v47 = 0;
    v48 = 0;
    *a6 = v28;
    v44 = 0;
    v45 = 0;
    v41 = 0;
    *a7 = v8;
    v42 = 0;
    *a8 = v29;
    goto LABEL_58;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\msacredentialmanagerimplementation.cpp",
    "MSACredentialManagerImplementation::GetContextParametersInternal",
    0x25Eu,
    Market,
    "hr = UrlUtilities::GetMarket(pExecutionContextLite->GetWinApiFunctions(), market)");
LABEL_59:
  v33 = v36;
  CTraceFuncW<long>::~CTraceFuncW<long>(v65);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CflFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v60);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v63);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v64);
  return v33;
}

```

## disassembly

```asm
0x180033a70  mov     rax, rsp
0x180033a73  mov     [rax+8], rbx
0x180033a77  mov     [rax+20h], r9
0x180033a7b  mov     [rax+18h], r8
0x180033a7f  push    rbp
0x180033a80  push    rsi
0x180033a81  push    rdi
0x180033a82  push    r12
0x180033a84  push    r13
0x180033a86  push    r14
0x180033a88  push    r15
0x180033a8a  lea     rbp, [rax-78h]
0x180033a8e  sub     rsp, 140h
0x180033a95  xor     r12d, r12d
0x180033a98  lea     rcx, [rbp+70h+var_60]; void *
0x180033a9c  mov     dword ptr [rsp+170h+var_140], r12d
0x180033aa1  mov     rbx, r9
0x180033aa4  mov     rsi, r8
0x180033aa7  mov     rdi, rdx
0x180033aaa  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180033aaf  lea     rcx, [rbp+70h+var_68]; void *
0x180033ab3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180033ab8  lea     rcx, [rbp+70h+var_70]; void *
0x180033abc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180033ac1  lea     rcx, [rbp+70h+var_78]; void *
0x180033ac5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180033aca  lea     rcx, [rbp+70h+var_80]; void *
0x180033ace  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180033ad3  lea     rcx, [rbp+70h+var_88]; void *
0x180033ad7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180033adc  lea     rax, [rsp+170h+var_140]
0x180033ae1  mov     [rsp+170h+var_120], r12
0x180033ae6  mov     [rbp+70h+var_50], rax
0x180033aea  lea     r15, aMsacredentialm_3; "MSACredentialManagerImplementation::Get"...
0x180033af1  lea     rax, qword_18006B4B0
0x180033af8  mov     [rsp+170h+var_128], r12
0x180033afd  lea     r14, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180033b04  mov     [rbp+70h+var_40], rax
0x180033b08  xor     r9d, r9d; unsigned int
0x180033b0b  mov     [rsp+170h+var_130], r12d
0x180033b10  mov     r8d, 24Ah; char *
0x180033b16  mov     [rbp+70h+var_58], r15
0x180033b1a  mov     rdx, r15; char *
0x180033b1d  mov     [rbp+70h+var_48], 0Bh
0x180033b25  mov     rcx, r14; this
0x180033b28  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180033b2d  test    rsi, rsi
0x180033b30  jnz     short loc_180033B5F
0x180033b32  lea     rax, aPpplatformNull; "ppPlatform != nullptr"
0x180033b39  mov     r8d, 24Ch; unsigned int
0x180033b3f  mov     r9d, 80004003h; int
0x180033b45  mov     [rsp+20h], rax; char *
0x180033b4a  mov     dword ptr [rsp+170h+var_140], r9d
0x180033b4f  mov     rdx, r15; char *
0x180033b52  mov     rcx, r14; char *
0x180033b55  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180033b5a  jmp     loc_180034001
0x180033b5f  test    rbx, rbx
0x180033b62  jnz     short loc_180033B73
0x180033b64  lea     rax, aPpuiflavorNull; "ppUiflavor != nullptr"
0x180033b6b  mov     r8d, 24Dh
0x180033b71  jmp     short loc_180033B3F
0x180033b73  mov     r13, [rbp+70h+arg_20]
0x180033b7a  test    r13, r13
0x180033b7d  jnz     short loc_180033B8E
0x180033b7f  lea     rax, aPpmarketNullpt; "ppMarket != nullptr"
0x180033b86  mov     r8d, 24Eh
0x180033b8c  jmp     short loc_180033B3F
0x180033b8e  mov     rax, [rbp+70h+arg_28]
0x180033b95  test    rax, rax
0x180033b98  jnz     short loc_180033BA9
0x180033b9a  lea     rax, aPpscenarioidNu; "ppScenarioId != nullptr"
0x180033ba1  mov     r8d, 24Fh
0x180033ba7  jmp     short loc_180033B3F
0x180033ba9  mov     rcx, [rbp+70h+arg_30]
0x180033bb0  test    rcx, rcx
0x180033bb3  jnz     short loc_180033BC7
0x180033bb5  lea     rax, aPphasngcNullpt; "ppHasNgc != nullptr"
0x180033bbc  mov     r8d, 250h
0x180033bc2  jmp     loc_180033B3F
0x180033bc7  mov     rdx, [rbp+70h+arg_38]
0x180033bce  test    rdx, rdx
0x180033bd1  jnz     short loc_180033BE5
0x180033bd3  lea     rax, aPpusernameNull; "ppUserName != nullptr"
0x180033bda  mov     r8d, 251h
0x180033be0  jmp     loc_180033B3F
0x180033be5  mov     [rsi], r12
0x180033be8  mov     [rbx], r12
0x180033beb  mov     [r13+0], r12
0x180033bef  mov     [rax], r12
0x180033bf2  mov     [rcx], r12
0x180033bf5  mov     rcx, rdi
0x180033bf8  mov     [rdx], r12
0x180033bfb  mov     rax, [rdi]
0x180033bfe  mov     rax, [rax+8]
0x180033c02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c07  mov     rbx, rax
0x180033c0a  mov     rcx, [rax]
0x180033c0d  mov     rax, [rcx+18h]
0x180033c11  mov     rcx, rbx
0x180033c14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033c19  mov     rcx, rax
0x180033c1c  lea     rdx, [rbp+70h+var_70]
0x180033c20  call    ?GetMarket@UrlUtilities@@SAJPEAVIWinApiLite@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UrlUtilities::GetMarket(IWinApiLite *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180033c25  mov     dword ptr [rsp+170h+var_140], eax
0x180033c29  test    eax, eax
0x180033c2b  jns     short loc_180033C47
0x180033c2d  lea     rcx, aHrUrlutilities; "hr = UrlUtilities::GetMarket(pExecution"...
0x180033c34  mov     r9d, eax
0x180033c37  mov     [rsp+20h], rcx
0x180033c3c  mov     r8d, 25Eh
0x180033c42  jmp     loc_180033B4F
0x180033c47  lea     rdx, [rbp+70h+var_68]
0x180033c4b  lea     rcx, [rbp+70h+var_60]
0x180033c4f  call    ?GetPlatformIdentifiers@UrlContextInfo@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; UrlContextInfo::GetPlatformIdentifiers(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180033c54  mov     dword ptr [rsp+170h+var_140], eax
0x180033c58  test    eax, eax
0x180033c5a  jns     short loc_180033C76
0x180033c5c  lea     rcx, aHrUrlcontextin_0; "hr = UrlContextInfo::GetPlatformIdentif"...
0x180033c63  mov     r9d, eax
0x180033c66  mov     [rsp+20h], rcx
0x180033c6b  mov     r8d, 261h
0x180033c71  jmp     loc_180033B4F
0x180033c76  lea     rdx, [rbp+70h+var_78]
0x180033c7a  mov     rcx, rbx
0x180033c7d  call    ?GetInlineUxScenarioId@UrlContextInfo@@SAJPEAVIExecutionContextLite@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; UrlContextInfo::GetInlineUxScenarioId(IExecutionContextLite *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180033c82  mov     dword ptr [rsp+170h+var_140], eax
0x180033c86  test    eax, eax
0x180033c88  jns     short loc_180033CA4
0x180033c8a  lea     rcx, aHrUrlcontextin; "hr = UrlContextInfo::GetInlineUxScenari"...
0x180033c91  mov     r9d, eax
0x180033c94  mov     [rsp+20h], rcx
0x180033c99  mov     r8d, 264h
0x180033c9f  jmp     loc_180033B4F
0x180033ca4  mov     rcx, rdi; struct IIdentityProviderExecutionContext *
0x180033ca7  call    ?HasNgc@UserIdKeyManagerImplementation@@SA_NPEAVIIdentityProviderExecutionContext@@@Z; UserIdKeyManagerImplementation::HasNgc(IIdentityProviderExecutionContext *)
0x180033cac  test    al, al
0x180033cae  lea     rcx, a0; "0"
0x180033cb5  lea     rdx, a1; "1"
0x180033cbc  cmovz   rdx, rcx
0x180033cc0  lea     rcx, [rbp+70h+var_80]
0x180033cc4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180033cc9  mov     dl, 1
0x180033ccb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADPinResetV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2> `wil::Feature<__WilFeatureTraits_Feature_AADPinResetV2>::GetImpl(void)'::`2'::impl
0x180033cd2  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AADPinResetV2@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADPinResetV2>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180033cd7  mov     rbx, [rsp+170h+var_128]
0x180033cdc  test    rbx, rbx
0x180033cdf  jz      short loc_180033CFE
0x180033ce1  lea     rcx, [rsp+170h+var_138]; this
0x180033ce6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180033ceb  mov     rcx, rbx
0x180033cee  call    cs:__imp_CflFreeBuffer
0x180033cf4  lea     rcx, [rsp+170h+var_138]; this
0x180033cf9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033cfe  mov     rbx, [rsp+170h+var_120]
0x180033d03  mov     [rsp+170h+var_128], r12
0x180033d08  test    rbx, rbx
0x180033d0b  jz      short loc_180033D2A
0x180033d0d  lea     rcx, [rsp+170h+var_138]; this
0x180033d12  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180033d17  mov     rcx, rbx
0x180033d1a  call    cs:__imp_CflFreeBuffer
0x180033d20  lea     rcx, [rsp+170h+var_138]; this
0x180033d25  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180033d2a  xor     r9d, r9d
0x180033d2d  mov     [rsp+170h+var_120], r12
0x180033d32  lea     r8, [rsp+170h+var_130]
0x180033d37  lea     rdx, [rsp+170h+var_128]
0x180033d3c  lea     rcx, [rsp+170h+var_120]
0x180033d41  call    cs:__imp_CflGetScenarioDataNew
0x180033d47  mov     dword ptr [rsp+170h+var_140], eax
0x180033d4b  test    eax, eax
0x180033d4d  js      short loc_180033DB8
0x180033d4f  cmp     [rsp+170h+var_130], r12d
0x180033d54  jbe     short loc_180033DB8
0x180033d56  xor     edx, edx
0x180033d58  mov     [rsp+170h+var_138], r12
0x180033d5d  lea     rcx, [rsp+170h+var_138]
0x180033d62  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180033d67  mov     edx, [rsp+170h+var_130]; unsigned int
0x180033d6b  lea     r8, [rsp+170h+var_138]; unsigned __int16 **
0x180033d70  mov     rcx, [rsp+170h+var_128]; unsigned __int8 *
0x180033d75  call    ?DeserializeScenarioContext@@YAJPEBEKPEAPEAG@Z; DeserializeScenarioContext(uchar const *,ulong,ushort * *)
0x180033d7a  test    eax, eax
0x180033d7c  js      short loc_180033DAE
0x180033d7e  mov     rbx, [rsp+170h+var_138]
0x180033d83  lea     r9, aDeserializedUs; "Deserialized username is %ls"
0x180033d8a  mov     r8d, 279h; unsigned int
0x180033d90  mov     [rsp+20h], rbx
0x180033d95  mov     rdx, r14; char *
0x180033d98  mov     ecx, 5; unsigned __int8
0x180033d9d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180033da2  mov     rdx, rbx
0x180033da5  lea     rcx, [rbp+70h+var_88]
0x180033da9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x180033dae  lea     rcx, [rsp+170h+var_138]
0x180033db3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180033db8  mov     rcx, [rbp+70h+var_60]; unsigned __int16 *
0x180033dbc  xor     edx, edx
0x180033dbe  mov     dword ptr [rsp+170h+var_140], r12d
0x180033dc3  mov     rdi, r12
0x180033dc6  mov     [rbp+70h+var_A0], r12
0x180033dca  mov     rsi, r12
0x180033dcd  mov     [rbp+70h+var_90], r12
0x180033dd1  mov     r14, r12
0x180033dd4  mov     r15, r12
0x180033dd7  mov     [rbp+70h+var_98], r12
0x180033ddb  mov     ebx, edx
0x180033ddd  mov     [rbp+70h+var_B8], r12
0x180033de1  mov     [rbp+70h+var_A8], r12
0x180033de5  mov     [rbp+70h+var_B0], r12
0x180033de9  mov     [rbp+70h+var_D0], r12
0x180033ded  mov     [rbp+70h+var_C0], r12
0x180033df1  mov     [rbp+70h+var_C8], r12
0x180033df5  mov     [rbp+70h+var_E8], r12
0x180033df9  mov     [rbp+70h+var_D8], r12
0x180033dfd  mov     [rbp+70h+var_E0], r12
0x180033e01  mov     [rsp+170h+var_100], r12
0x180033e06  mov     [rbp+70h+var_F0], rdx
0x180033e0a  mov     [rsp+170h+var_F8], rdx
0x180033e0f  mov     [rsp+170h+var_118], rdx
0x180033e14  mov     [rsp+170h+var_108], rdx
0x180033e19  mov     [rsp+170h+var_110], rdx
0x180033e1e  cmp     [rcx-10h], edx
0x180033e21  jz      short loc_180033E67
0x180033e23  lea     rdx, [rbp+70h+var_A0]
0x180033e27  call    ??$CopyToAutoString@V?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@YAJPEBGAEAV?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@PEA_K@Z; CopyToAutoString<CoTaskMemAllocFunctor<ushort *>,DummyContext>(ushort const *,Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext> &,unsigned __int64 *)
0x180033e2c  xor     edx, edx
0x180033e2e  mov     dword ptr [rsp+170h+var_140], eax
0x180033e32  test    eax, eax
0x180033e34  jns     short loc_180033E63
0x180033e36  lea     rcx, aHrCopytoautost_4; "hr = CopyToAutoString(platform, spPlatf"...
0x180033e3d  mov     r8d, 28Bh; unsigned int
0x180033e43  mov     [rsp+20h], rcx; char *
0x180033e48  lea     rdx, aMsacredentialm_3; "MSACredentialManagerImplementation::Get"...
0x180033e4f  lea     rcx, aOnecoreuapDsEx_6; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180033e56  mov     r9d, eax; int
0x180033e59  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180033e5e  jmp     loc_180033FC9
0x180033e63  mov     rdi, [rbp+70h+var_A0]
0x180033e67  mov     rcx, [rbp+70h+var_68]; unsigned __int16 *
0x180033e6b  cmp     [rcx-10h], edx
0x180033e6e  jz      short loc_180033E96
0x180033e70  lea     rdx, [rbp+70h+var_B8]
0x180033e74  call    ??$CopyToAutoString@V?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@YAJPEBGAEAV?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@PEA_K@Z; CopyToAutoString<CoTaskMemAllocFunctor<ushort *>,DummyContext>(ushort const *,Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext> &,unsigned __int64 *)
0x180033e79  xor     edx, edx
0x180033e7b  mov     dword ptr [rsp+170h+var_140], eax
0x180033e7f  test    eax, eax
0x180033e81  jns     short loc_180033E92
0x180033e83  lea     rcx, aHrCopytoautost_0; "hr = CopyToAutoString(uiflavor, spUifla"...
0x180033e8a  mov     r8d, 290h
0x180033e90  jmp     short loc_180033E43
0x180033e92  mov     rsi, [rbp+70h+var_B8]
0x180033e96  mov     rcx, [rbp+70h+var_70]; unsigned __int16 *
0x180033e9a  cmp     [rcx-10h], edx
0x180033e9d  jz      short loc_180033EC5
0x180033e9f  lea     rdx, [rbp+70h+var_D0]
0x180033ea3  call    ??$CopyToAutoString@V?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@YAJPEBGAEAV?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@PEA_K@Z; CopyToAutoString<CoTaskMemAllocFunctor<ushort *>,DummyContext>(ushort const *,Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext> &,unsigned __int64 *)
0x180033ea8  xor     edx, edx
0x180033eaa  mov     dword ptr [rsp+170h+var_140], eax
0x180033eae  test    eax, eax
0x180033eb0  jns     short loc_180033EC1
0x180033eb2  lea     rcx, aHrCopytoautost_3; "hr = CopyToAutoString(market, spMarket)"
0x180033eb9  mov     r8d, 295h
0x180033ebf  jmp     short loc_180033E43
0x180033ec1  mov     r14, [rbp+70h+var_D0]
0x180033ec5  mov     rcx, [rbp+70h+var_78]; unsigned __int16 *
0x180033ec9  cmp     [rcx-10h], edx
0x180033ecc  jz      short loc_180033EF7
0x180033ece  lea     rdx, [rbp+70h+var_E8]
0x180033ed2  call    ??$CopyToAutoString@V?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@YAJPEBGAEAV?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@PEA_K@Z; CopyToAutoString<CoTaskMemAllocFunctor<ushort *>,DummyContext>(ushort const *,Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext> &,unsigned __int64 *)
0x180033ed7  xor     edx, edx
0x180033ed9  mov     dword ptr [rsp+170h+var_140], eax
0x180033edd  test    eax, eax
0x180033edf  jns     short loc_180033EF3
0x180033ee1  lea     rcx, aHrCopytoautost_6; "hr = CopyToAutoString(scenarioId, spSce"...
0x180033ee8  mov     r8d, 29Ah
0x180033eee  jmp     loc_180033E43
0x180033ef3  mov     r15, [rbp+70h+var_E8]
0x180033ef7  mov     rcx, [rbp+70h+var_80]; unsigned __int16 *
0x180033efb  cmp     [rcx-10h], edx
0x180033efe  jz      short loc_180033F2B
0x180033f00  lea     rdx, [rsp+170h+var_100]
0x180033f05  call    ??$CopyToAutoString@V?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@YAJPEBGAEAV?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@PEA_K@Z; CopyToAutoString<CoTaskMemAllocFunctor<ushort *>,DummyContext>(ushort const *,Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext> &,unsigned __int64 *)
0x180033f0a  xor     edx, edx
0x180033f0c  mov     dword ptr [rsp+170h+var_140], eax
0x180033f10  test    eax, eax
0x180033f12  jns     short loc_180033F26
0x180033f14  lea     rcx, aHrCopytoautost_5; "hr = CopyToAutoString(hasNgc, spHasNgc)"
0x180033f1b  mov     r8d, 29Fh
0x180033f21  jmp     loc_180033E43
0x180033f26  mov     r12, [rsp+170h+var_100]
0x180033f2b  mov     rcx, [rbp+70h+var_88]; unsigned __int16 *
0x180033f2f  cmp     [rcx-10h], edx
0x180033f32  jz      short loc_180033F5F
0x180033f34  lea     rdx, [rsp+170h+var_118]
0x180033f39  call    ??$CopyToAutoString@V?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@YAJPEBGAEAV?$Auto@PEAGV?$CoTaskMemAllocFunctor@PEAG@@VDummyContext@@@@PEA_K@Z; CopyToAutoString<CoTaskMemAllocFunctor<ushort *>,DummyContext>(ushort const *,Auto<ushort *,CoTaskMemAllocFunctor<ushort *>,DummyContext> &,unsigned __int64 *)
0x180033f3e  xor     edx, edx
0x180033f40  mov     dword ptr [rsp+170h+var_140], eax
0x180033f44  test    eax, eax
  ... truncated ...
```
