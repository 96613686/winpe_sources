# HandleGetProofOfPossessionTokens(IServiceExecutionContext *,ushort const *,ushort const *,_GUID const *,ulong *,ProofOfPossessionCookieInfo * *)

- ea: `0x180079684`
- end: `0x180079e4b`
- name: `?HandleGetProofOfPossessionTokens@@YAJPEAVIServiceExecutionContext@@PEBG1PEBU_GUID@@PEAKPEAPEAUProofOfPossessionCookieInfo@@@Z`
- size: `1991`
- prototype: `__int64 __fastcall(struct IServiceExecutionContext *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, unsigned int *, struct ProofOfPossessionCookieInfo **)`
- caller_count: `1`
- callee_count: `35`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180079020`

## callees

- `0x180009f00`
- `0x18000a36c`
- `0x18000c050`
- `0x18000e310`
- `0x18000fd04`
- `0x18000fd48`
- `0x1800151c4`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x180029d54`
- `0x18004cb2c`
- `0x18004ccb0`
- `0x18004d6c8`
- `0x180079684`
- `0x180079e54`
- `0x180079e9c`
- `0x180079f48`
- `0x18007a008`
- `0x18007a070`
- `0x18007a124`
- `0x18007a1fc`
- `0x18007a2e0`
- `0x18007a2f8`
- `0x18008a50c`
- `0x1800a3b60`
- `0x1800a404c`
- `0x1800a4778`
- `0x1800a716c`
- `0x1800adcd0`
- `0x1800af448`
- `0x1800afd50`
- `0x1800b0fcc`
- `0x180128010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180079c92`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180079c92`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180079dda`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180079dda`

## string_xrefs

- `0x180079770`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18007988f`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180079908`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180079a49`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180079c6c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180079d66`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800796cb`: `HandleGetProofOfPossessionTokens`
- `0x180079799`: `HandleGetProofOfPossessionTokens`
- `0x180079901`: `HandleGetProofOfPossessionTokens`
- `0x180079a42`: `HandleGetProofOfPossessionTokens`
- `0x180079c65`: `HandleGetProofOfPossessionTokens`
- `0x180079d5f`: `HandleGetProofOfPossessionTokens`
- `0x180079d92`: `HandleGetProofOfPossessionTokens`
- `0x180079821`: `hr = pServiceWrapper->Impersonate(&client)`
- `0x1800798ec`: `hr = pServiceWrapper->GetLogonId(&client, logonId)`
- `0x180079954`: `hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, hInternal)`
- `0x18007998a`: `hr = pServiceWrapper->GetCookieData(webCookieManager, hInternal, webCookie)`
- `0x180079a96`: `hr = pServiceWrapper->GetCookieData(webCookieManager, hInternal, webCookie)`
- `0x180079a2d`: `hr = pServiceWrapper->GetDeviceIdInternal( g_szStrongAuthAppId, IDCRL_DEVICE_ID_FROMCACHE, IDCRL_DEVICE_ID_NO_ASSOCIATION_UPDATE, nullptr , nullptr , nullptr , &hInternal)`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
__int64 __fastcall HandleGetProofOfPossessionTokens(
        struct IServiceExecutionContext *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        unsigned int *a5,
        struct ProofOfPossessionCookieInfo **a6)
{
  struct ProofOfPossessionCookieInfo *v9; // rsi
  unsigned __int64 v10; // r15
  PPTraceStatus *v11; // rcx
  PPTraceStatus *v12; // rcx
  bool v13; // zf
  char v14; // al
  __int64 v15; // rdi
  int v16; // eax
  int v17; // eax
  int v18; // eax
  const char *v19; // rcx
  unsigned int v20; // r8d
  __int64 (__fastcall *v21)(__int64, const unsigned __int16 *, __int64, __int64, _QWORD, _QWORD, _QWORD, __int64 *); // rbx
  int v22; // eax
  const char *v23; // rcx
  unsigned int v24; // r8d
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // rax
  void *v27; // r14
  unsigned __int64 i; // rsi
  _QWORD *v29; // rbx
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rbx
  __int64 v35; // rax
  const char *v36; // rcx
  unsigned int v37; // r8d
  unsigned __int64 v38; // r8
  WCHAR **v39; // rax
  WCHAR *v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rcx
  WCHAR *v43; // rax
  __int64 v44; // rcx
  WCHAR *v45; // rax
  unsigned int v46; // ebx
  char *v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v51; // [rsp+60h] [rbp-A0h] BYREF
  void *v52; // [rsp+68h] [rbp-98h] BYREF
  __int64 v53; // [rsp+70h] [rbp-90h]
  __int64 v54; // [rsp+78h] [rbp-88h]
  __int64 v55; // [rsp+80h] [rbp-80h] BYREF
  __int64 v56; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v57; // [rsp+90h] [rbp-70h]
  __int64 v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+A0h] [rbp-60h]
  struct ProofOfPossessionCookieInfo *v60; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v61; // [rsp+B0h] [rbp-50h]
  __int64 v62; // [rsp+B8h] [rbp-48h]
  _BYTE v63[48]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v64; // [rsp+F0h] [rbp-10h]
  __int64 v65; // [rsp+F8h] [rbp-8h]
  int *v66; // [rsp+100h] [rbp+0h]
  const char *v67; // [rsp+108h] [rbp+8h]
  _QWORD v68[4]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v69; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v70[264]; // [rsp+138h] [rbp+38h] BYREF
  void **v71; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v72[272]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v73[8]; // [rsp+358h] [rbp+258h] BYREF
  _BYTE v74[48]; // [rsp+360h] [rbp+260h] BYREF

  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(
    (__int64)&v71,
    (__int64)"HandleGetProofOfPossessionTokens");
  v71 = &MSAClientTraceTelemetry::HandleGetProofOfPossessionTokens::`vftable';
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
    &v71,
    a4);
  MSAClientTraceTelemetry::HandleGetProofOfPossessionTokens::StartActivity((MSAClientTraceTelemetry::HandleGetProofOfPossessionTokens *)&v71);
  v49 = 0;
  v55 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64 *)&v51,
    L"Default");
  WebCookieManager::WebCookieManager((WebCookieManager *)&v69);
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v9 = 0;
  v60 = 0;
  v62 = 0;
  v61 = 0;
  v68[0] = "HandleGetProofOfPossessionTokens";
  v68[1] = &v49;
  v68[2] = 0;
  v68[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleGetProofOfPossessionTokens",
    (const char *)0x2BA1,
    0,
    (const unsigned __int16 *)v48);
  v64 = "W";
  v10 = 11;
  v65 = 11;
  v66 = &v49;
  v67 = "HandleGetProofOfPossessionTokens";
  if ( PPTraceStatus::GetAssertFlag(v11) == 1 || (v13 = PPTraceStatus::GetAssertFlag(v12) == 2, v14 = 0, v13) )
    v14 = 1;
  if ( !v14 )
  {
    v10 = -(__int64)((Microsoft_Windows_LiveIdEnableBits & 0x20) != 0) & 0xB;
    v65 = v10;
  }
  if ( !a5 || !a6 )
  {
    v49 = -2147024809;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetProofOfPossessionTokens",
      0x2BABu,
      -2147024809,
      "hr = E_INVALIDARG");
    goto LABEL_53;
  }
  *a5 = 0;
  *a6 = 0;
  v15 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v15 + 32LL))(v15, &v55, 0);
  v49 = v16;
  if ( v16 < 0 )
  {
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetProofOfPossessionTokens",
      0x2BB5u,
      v16,
      "hr = pServiceWrapper->Impersonate(&client)");
    goto LABEL_53;
  }
  v52 = 0;
  v54 = 0;
  v53 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, void **, const wchar_t *))(*(_QWORD *)v15 + 104LL))(
          v15,
          a2,
          0x800000,
          &v52,
          L"{d9ffeb4b-30de-45b4-a72d-0c3fdc12ac7f}");
  v49 = v17;
  if ( v17 >= 0 )
  {
    v51 = 0;
    WebCookieData::WebCookieData((WebCookieData *)v63);
    v50 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD **))(*(_QWORD *)v15 + 40LL))(v15, &v55, &v51);
    v49 = v18;
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, _QWORD **, void *, __int64 *))(*(_QWORD *)v15 + 24LL))(
              v15,
              &v51,
              v52,
              &v50);
      v49 = v18;
      if ( v18 >= 0 )
      {
        v18 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _BYTE *))(*(_QWORD *)v15 + 152LL))(
                v15,
                &v69,
                &v50,
                v63);
        v49 = v18;
        if ( v18 >= 0 )
        {
          ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::Add(&v56, v63);
          CAutoRefPtr<CSingleIdentity>::Deinit(&v50);
          WebCookieData::~WebCookieData((WebCookieData *)v63);
          goto LABEL_22;
        }
        v19 = "hr = pServiceWrapper->GetCookieData(webCookieManager, hInternal, webCookie)";
        v20 = 11280;
      }
      else
      {
        v19 = "hr = pServiceWrapper->GetIdentityHandle(logonId, hUserIdentity, hInternal)";
        v20 = 11279;
      }
    }
    else
    {
      v19 = "hr = pServiceWrapper->GetLogonId(&client, logonId)";
      v20 = 11278;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetProofOfPossessionTokens",
      v20,
      v18,
      v19);
    CAutoRefPtr<CSingleIdentity>::Deinit(&v50);
    WebCookieData::~WebCookieData((WebCookieData *)v63);
LABEL_13:
    Auto<void *,WLIDHandleFunctor,DummyContext>::~Auto<void *,WLIDHandleFunctor,DummyContext>(&v52);
    goto LABEL_53;
  }
  if ( v17 != -2147188724 )
    goto LABEL_13;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0x2BFFu,
    L"Unable to get CAW because caller is not connected.");
  v49 = 0;
LABEL_22:
  Auto<void *,WLIDHandleFunctor,DummyContext>::~Auto<void *,WLIDHandleFunctor,DummyContext>(&v52);
  WebCookieData::WebCookieData((WebCookieData *)v63);
  v50 = 0;
  v21 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64, __int64, _QWORD, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v15 + 128LL);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v50);
  v22 = v21(v15, L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}", 16, 0x4000, 0, 0, 0, &v50);
  v49 = v22;
  if ( v22 < 0 )
  {
    v23 = "hr = pServiceWrapper->GetDeviceIdInternal( g_szStrongAuthAppId, IDCRL_DEVICE_ID_FROMCACHE, IDCRL_DEVICE_ID_NO_"
          "ASSOCIATION_UPDATE, nullptr , nullptr , nullptr , &hInternal)";
    v24 = 11299;
LABEL_24:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleGetProofOfPossessionTokens",
      v24,
      v22,
      v23);
    CAutoRefPtr<CSingleIdentity>::Deinit(&v50);
    WebCookieData::~WebCookieData((WebCookieData *)v63);
    goto LABEL_53;
  }
  v22 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *, _BYTE *))(*(_QWORD *)v15 + 152LL))(
          v15,
          &v69,
          &v50,
          v63);
  v49 = v22;
  if ( v22 < 0 )
  {
    v23 = "hr = pServiceWrapper->GetCookieData(webCookieManager, hInternal, webCookie)";
    v24 = 11301;
    goto LABEL_24;
  }
  ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::Add(&v56, v63);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v50);
  WebCookieData::~WebCookieData((WebCookieData *)v63);
  v25 = v57;
  if ( !v57 )
    goto LABEL_50;
  v52 = 0;
  v54 = 0;
  LODWORD(v53) = 0;
  v26 = 8 * v57;
  if ( !is_mul_ok(v57, 8u) )
    v26 = -1;
  v27 = operator new[](v26, (const struct std::nothrow_t *)std::nothrow);
  AutoArray__HandleGetProofOfPossessionTokens_::_77_::AutoFreeData_____AutoPointerArrayFunctor__HandleGetProofOfPossessionTokens_::_77_::AutoFreeData____DummyContext_::Clear(&v52);
  v52 = v27;
  LODWORD(v53) = v25;
  if ( v27 )
  {
    memset_0(v27, 0, 8 * v25);
    for ( i = 0; i < v25; ++i )
    {
      v29 = operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
      v51 = v29;
      if ( v29 )
      {
        memset_0(v29, 0, 0x50u);
        *v29 = 0;
        v29[2] = 0;
        v29[1] = 0;
        v29[3] = 0;
        v29[5] = 0;
        v29[4] = 0;
        v29[6] = 0;
        v29[8] = 0;
        v29[7] = 0;
      }
      else
      {
        v29 = 0;
      }
      *((_QWORD *)v27 + i) = v29;
      if ( !v29 )
        goto LABEL_51;
      v30 = ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::operator[](&v56, i);
      v31 = DuplicateString(v30 + 8, v29);
      v49 = v31;
      if ( v31 < 0 )
      {
        v36 = "hr = DuplicateString(webCookies[i].CookieName, response[i]->Name)";
        v37 = 11330;
        goto LABEL_44;
      }
      v32 = *((_QWORD *)v27 + i);
      v33 = ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::operator[](&v56, i);
      v31 = DuplicateString(v33 + 16, v32 + 24);
      v49 = v31;
      if ( v31 < 0 )
      {
        v36 = "hr = DuplicateString(webCookies[i].CookieData, response[i]->Data)";
        v37 = 11331;
        goto LABEL_44;
      }
      v34 = *((_QWORD *)v27 + i);
      v35 = ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::operator[](&v56, i);
      v31 = DuplicateString(v35 + 24, v34 + 48);
      v49 = v31;
      if ( v31 < 0 )
      {
        v36 = "hr = DuplicateString(webCookies[i].P3PHeader, response[i]->P3PHeader)";
        v37 = 11332;
LABEL_44:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleGetProofOfPossessionTokens",
          v37,
          v31,
          v36);
        goto LABEL_45;
      }
      *(_DWORD *)(*((_QWORD *)v27 + i) + 72LL) = *(_DWORD *)(ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::operator[](
                                                               &v56,
                                                               i)
                                                           + 40);
    }
    v9 = (struct ProofOfPossessionCookieInfo *)malloc(32 * v25);
    Auto<_WLIDSignedTokens *,LocalMIDLPointerFunctor<_WLIDSignedTokens *>,DummyContext>::Clear(&v60);
    v60 = v9;
    if ( v9 )
    {
      memset_0(v9, 0, 32 * v25);
      v38 = 0;
      do
      {
        v39 = (WCHAR **)*((_QWORD *)v27 + v38);
        v40 = *v39;
        *v39 = 0;
        v39[1] = 0;
        v41 = v38;
        v9[v41].name = v40;
        v42 = *((_QWORD *)v27 + v38);
        v43 = *(WCHAR **)(v42 + 24);
        *(_QWORD *)(v42 + 24) = 0;
        *(_QWORD *)(v42 + 32) = 0;
        v9[v41].data = v43;
        v44 = *((_QWORD *)v27 + v38);
        v45 = *(WCHAR **)(v44 + 48);
        *(_QWORD *)(v44 + 48) = 0;
        *(_QWORD *)(v44 + 56) = 0;
        v9[v41].p3pHeader = v45;
        v9[v41].flags = *(_DWORD *)(*((_QWORD *)v27 + v38++) + 72LL);
      }
      while ( v38 < v25 );
      AutoArray__HandleGetProofOfPossessionTokens_::_77_::AutoFreeData_____AutoPointerArrayFunctor__HandleGetProofOfPossessionTokens_::_77_::AutoFreeData____DummyContext_::Clear(&v52);
LABEL_50:
      *a5 = v25;
      v60 = 0;
      v61 = 0;
      *a6 = v9;
      goto LABEL_53;
    }
  }
LABEL_51:
  v49 = -2147024882;
LABEL_45:
  AutoArray__HandleGetProofOfPossessionTokens_::_77_::AutoFreeData_____AutoPointerArrayFunctor__HandleGetProofOfPossessionTokens_::_77_::AutoFreeData____DummyContext_::Clear(&v52);
LABEL_53:
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v71,
    (unsigned int)v49);
  v46 = v49;
  ErrorVerifier::CheckAgainstList("HandleGetProofOfPossessionTokens", v49, v10, (const int *)"W");
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v68);
  Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>::~Auto<unsigned short *,LocalMIDLPointerFunctor<unsigned short *>,DummyContext>(&v60);
  ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::~CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>(&v56);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v70);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v69);
  if ( (_DWORD)v55 )
    SetThreadToken(0, 0);
  v71 = &MSAClientTraceTelemetry::HandleGetProofOfPossessionTokens::`vftable';
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v71);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v74);
  wil::details::shared_object<wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v73);
  wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<MSAClientTraceTelemetry,_TlgReflectorTag_Param0IsProviderType>((__int64)v72);
  return v46;
}

```

## disassembly

```asm
0x180079684  mov     [rsp-8+arg_10], rbx
0x180079689  push    rbp
0x18007968a  push    rsi
0x18007968b  push    rdi
0x18007968c  push    r12
0x18007968e  push    r13
0x180079690  push    r14
0x180079692  push    r15
0x180079694  lea     rbp, [rsp-2A0h]
0x18007969c  sub     rsp, 3A0h
0x1800796a3  mov     rax, cs:__security_cookie
0x1800796aa  xor     rax, rsp
0x1800796ad  mov     [rbp+2D0h+var_40], rax
0x1800796b4  mov     rbx, r9
0x1800796b7  mov     r14, rdx
0x1800796ba  mov     rdi, rcx
0x1800796bd  mov     r12, [rbp+2D0h+arg_20]
0x1800796c4  mov     r13, [rbp+2D0h+arg_28]
0x1800796cb  lea     r15, aHandlegetproof; "HandleGetProofOfPossessionTokens"
0x1800796d2  mov     rdx, r15
0x1800796d5  lea     rcx, [rbp+2D0h+var_190]
0x1800796dc  call    ??0?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800796e1  lea     rax, ??_7HandleGetProofOfPossessionTokens@MSAClientTraceTelemetry@@6B@; const MSAClientTraceTelemetry::HandleGetProofOfPossessionTokens::`vftable'
0x1800796e8  mov     [rbp+2D0h+var_190], rax
0x1800796ef  mov     rdx, rbx
0x1800796f2  lea     rcx, [rbp+2D0h+var_190]
0x1800796f9  call    ?SetRelatedActivityId@?$ActivityBase@VMSAClientTraceTelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXPEBU_GUID@@@Z; wil::ActivityBase<MSAClientTraceTelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const *)
0x1800796fe  lea     rcx, [rbp+2D0h+var_190]; this
0x180079705  call    ?StartActivity@HandleGetProofOfPossessionTokens@MSAClientTraceTelemetry@@QEAAXXZ; MSAClientTraceTelemetry::HandleGetProofOfPossessionTokens::StartActivity(void)
0x18007970a  xor     ebx, ebx
0x18007970c  mov     [rsp+3D0h+var_380], ebx
0x180079710  mov     [rbp+2D0h+var_350], rbx
0x180079714  lea     rdx, aDefault; "Default"
0x18007971b  lea     rcx, [rsp+3D0h+var_370]
0x180079720  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180079725  mov     rdx, rax
0x180079728  lea     rcx, [rbp+2D0h+var_2A0]; this
0x18007972c  call    ??0WebCookieManager@@QEAA@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebCookieManager::WebCookieManager(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180079731  nop
0x180079732  mov     [rbp+2D0h+var_348], rbx
0x180079736  mov     [rbp+2D0h+var_340], rbx
0x18007973a  mov     [rbp+2D0h+var_338], rbx
0x18007973e  mov     [rbp+2D0h+var_330], ebx
0x180079741  mov     esi, ebx
0x180079743  mov     [rbp+2D0h+var_328], rbx
0x180079747  mov     [rbp+2D0h+var_318], rbx
0x18007974b  mov     [rbp+2D0h+var_320], rbx
0x18007974f  mov     [rbp+2D0h+var_2C0], r15
0x180079753  lea     rax, [rsp+3D0h+var_380]
0x180079758  mov     [rbp+2D0h+var_2B8], rax
0x18007975c  mov     [rbp+2D0h+var_2B0], rbx
0x180079760  mov     [rbp+2D0h+var_2A8], rbx
0x180079764  xor     r9d, r9d; unsigned int
0x180079767  mov     r8d, 2BA1h; char *
0x18007976d  mov     rdx, r15; char *
0x180079770  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180079777  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18007977c  nop
0x18007977d  lea     rax, aW_1; "W"
0x180079784  mov     [rbp+2D0h+var_2E0], rax
0x180079788  lea     r15d, [rbx+0Bh]
0x18007978c  mov     [rbp+2D0h+var_2D8], r15
0x180079790  lea     rax, [rsp+3D0h+var_380]
0x180079795  mov     [rbp+2D0h+var_2D0], rax
0x180079799  lea     rax, aHandlegetproof; "HandleGetProofOfPossessionTokens"
0x1800797a0  mov     [rbp+2D0h+var_2C8], rax
0x1800797a4  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x1800797a9  cmp     eax, 1
0x1800797ac  jz      short loc_1800797BA
0x1800797ae  call    ?GetAssertFlag@PPTraceStatus@@YAKXZ; PPTraceStatus::GetAssertFlag(void)
0x1800797b3  cmp     eax, 2
0x1800797b6  mov     al, bl
0x1800797b8  jnz     short loc_1800797BC
0x1800797ba  mov     al, 1
0x1800797bc  test    al, al
0x1800797be  jnz     short loc_1800797D7
0x1800797c0  mov     al, cs:Microsoft_Windows_LiveIdEnableBits
0x1800797c6  and     al, 20h
0x1800797c8  neg     al
0x1800797ca  sbb     rax, rax
0x1800797cd  and     rax, r15
0x1800797d0  mov     r15, rax
0x1800797d3  mov     [rbp+2D0h+var_2D8], rax
0x1800797d7  test    r12, r12
0x1800797da  jz      loc_180079D42
0x1800797e0  test    r13, r13
0x1800797e3  jz      loc_180079D42
0x1800797e9  mov     [r12], ebx
0x1800797ed  mov     [r13+0], rbx
0x1800797f1  mov     rax, [rdi]
0x1800797f4  mov     rcx, rdi
0x1800797f7  mov     rax, [rax+50h]
0x1800797fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079800  mov     rdi, rax
0x180079803  mov     rcx, [rax]
0x180079806  mov     rax, [rcx+20h]
0x18007980a  xor     r8d, r8d
0x18007980d  lea     rdx, [rbp+2D0h+var_350]
0x180079811  mov     rcx, rdi
0x180079814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079819  mov     [rsp+3D0h+var_380], eax
0x18007981d  test    eax, eax
0x18007981f  jns     short loc_18007983B
0x180079821  lea     rdx, aHrPservicewrap_25; "hr = pServiceWrapper->Impersonate(&clie"...
0x180079828  mov     [rsp+3D0h+var_3B0], rdx
0x18007982d  mov     r9d, eax
0x180079830  mov     r8d, 2BB5h
0x180079836  jmp     loc_180079D5F
0x18007983b  mov     [rsp+3D0h+var_368], rbx
0x180079840  mov     [rsp+3D0h+var_358], rbx
0x180079845  mov     [rsp+3D0h+var_360], rbx
0x18007984a  mov     rax, [rdi]
0x18007984d  lea     rcx, aD9ffeb4b30de45; "{d9ffeb4b-30de-45b4-a72d-0c3fdc12ac7f}"
0x180079854  mov     [rsp+3D0h+var_3B0], rcx
0x180079859  lea     r9, [rsp+3D0h+var_368]
0x18007985e  mov     r8d, 800000h
0x180079864  mov     rdx, r14
0x180079867  mov     rcx, rdi
0x18007986a  mov     rax, [rax+68h]
0x18007986e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079873  mov     [rsp+3D0h+var_380], eax
0x180079877  test    eax, eax
0x180079879  jns     short loc_1800798B8
0x18007987b  cmp     eax, 8004800Ch
0x180079880  jnz     short loc_1800798A9
0x180079882  lea     r9, aUnableToGetCaw; "Unable to get CAW because caller is not"...
0x180079889  mov     r8d, 2BFFh; unsigned int
0x18007988f  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180079896  mov     ecx, 5; unsigned __int8
0x18007989b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800798a0  mov     [rsp+3D0h+var_380], ebx
0x1800798a4  jmp     loc_1800799BF
0x1800798a9  lea     rcx, [rsp+3D0h+var_368]
0x1800798ae  call    ??1?$Auto@PEAXVWLIDHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,WLIDHandleFunctor,DummyContext>::~Auto<void *,WLIDHandleFunctor,DummyContext>(void)
0x1800798b3  jmp     loc_180079D72
0x1800798b8  mov     [rsp+3D0h+var_370], rbx
0x1800798bd  lea     rcx, [rbp+2D0h+var_310]; this
0x1800798c1  call    ??0WebCookieData@@QEAA@XZ; WebCookieData::WebCookieData(void)
0x1800798c6  nop
0x1800798c7  mov     [rsp+3D0h+var_378], rbx
0x1800798cc  mov     rax, [rdi]
0x1800798cf  lea     r8, [rsp+3D0h+var_370]
0x1800798d4  lea     rdx, [rbp+2D0h+var_350]
0x1800798d8  mov     rcx, rdi
0x1800798db  mov     rax, [rax+28h]
0x1800798df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800798e4  mov     [rsp+3D0h+var_380], eax
0x1800798e8  test    eax, eax
0x1800798ea  jns     short loc_18007992E
0x1800798ec  lea     rcx, aHrPservicewrap_16; "hr = pServiceWrapper->GetLogonId(&clien"...
0x1800798f3  mov     r8d, 2C0Eh; unsigned int
0x1800798f9  mov     [rsp+3D0h+var_3B0], rcx; char *
0x1800798fe  mov     r9d, eax; int
0x180079901  lea     rdx, aHandlegetproof; "HandleGetProofOfPossessionTokens"
0x180079908  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18007990f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180079914  nop
0x180079915  lea     rcx, [rsp+3D0h+var_378]
0x18007991a  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x18007991f  nop
0x180079920  lea     rcx, [rbp+2D0h+var_310]; this
0x180079924  call    ??1WebCookieData@@QEAA@XZ; WebCookieData::~WebCookieData(void)
0x180079929  jmp     loc_1800798A9
0x18007992e  mov     rax, [rdi]
0x180079931  lea     r9, [rsp+3D0h+var_378]
0x180079936  mov     r8, [rsp+3D0h+var_368]
0x18007993b  lea     rdx, [rsp+3D0h+var_370]
0x180079940  mov     rcx, rdi
0x180079943  mov     rax, [rax+18h]
0x180079947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007994c  mov     [rsp+3D0h+var_380], eax
0x180079950  test    eax, eax
0x180079952  jns     short loc_180079963
0x180079954  lea     rcx, aHrPservicewrap_9; "hr = pServiceWrapper->GetIdentityHandle"...
0x18007995b  mov     r8d, 2C0Fh
0x180079961  jmp     short loc_1800798F9
0x180079963  mov     rax, [rdi]
0x180079966  lea     r9, [rbp+2D0h+var_310]
0x18007996a  lea     r8, [rsp+3D0h+var_378]
0x18007996f  lea     rdx, [rbp+2D0h+var_2A0]
0x180079973  mov     rcx, rdi
0x180079976  mov     rax, [rax+98h]
0x18007997d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079982  mov     [rsp+3D0h+var_380], eax
0x180079986  test    eax, eax
0x180079988  jns     short loc_18007999C
0x18007998a  lea     rcx, aHrPservicewrap_29; "hr = pServiceWrapper->GetCookieData(web"...
0x180079991  mov     r8d, 2C10h
0x180079997  jmp     loc_1800798F9
0x18007999c  lea     rdx, [rbp+2D0h+var_310]
0x1800799a0  lea     rcx, [rbp+2D0h+var_348]
0x1800799a4  call    ?Add@?$CAtlArray@VWebCookieData@@V?$CElementTraits@VWebCookieData@@@ATL@@@ATL@@QEAA_KAEBVWebCookieData@@@Z; ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::Add(WebCookieData const &)
0x1800799a9  nop
0x1800799aa  lea     rcx, [rsp+3D0h+var_378]
0x1800799af  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x1800799b4  nop
0x1800799b5  lea     rcx, [rbp+2D0h+var_310]; this
0x1800799b9  call    ??1WebCookieData@@QEAA@XZ; WebCookieData::~WebCookieData(void)
0x1800799be  nop
0x1800799bf  lea     rcx, [rsp+3D0h+var_368]
0x1800799c4  call    ??1?$Auto@PEAXVWLIDHandleFunctor@@VDummyContext@@@@QEAA@XZ; Auto<void *,WLIDHandleFunctor,DummyContext>::~Auto<void *,WLIDHandleFunctor,DummyContext>(void)
0x1800799c9  lea     rcx, [rbp+2D0h+var_310]; this
0x1800799cd  call    ??0WebCookieData@@QEAA@XZ; WebCookieData::WebCookieData(void)
0x1800799d2  nop
0x1800799d3  mov     [rsp+3D0h+var_378], rbx
0x1800799d8  mov     rax, [rdi]
0x1800799db  mov     rbx, [rax+80h]
0x1800799e2  lea     rcx, [rsp+3D0h+var_378]
0x1800799e7  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x1800799ec  lea     rax, [rsp+3D0h+var_378]
0x1800799f1  mov     [rsp+3D0h+var_398], rax
0x1800799f6  xor     eax, eax
0x1800799f8  mov     [rsp+3D0h+var_3A0], rax
0x1800799fd  mov     [rsp+3D0h+var_3A8], rax
0x180079a02  mov     [rsp+3D0h+var_3B0], rax
0x180079a07  mov     r9d, 4000h
0x180079a0d  lea     r8d, [rax+10h]
0x180079a11  lea     rdx, aAfda72bf340941; "{AFDA72BF-3409-413a-B54E-2AB8D66A7826}"
0x180079a18  mov     rcx, rdi
0x180079a1b  mov     rax, rbx
0x180079a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a23  mov     [rsp+3D0h+var_380], eax
0x180079a27  xor     ebx, ebx
0x180079a29  test    eax, eax
0x180079a2b  jns     short loc_180079A6F
0x180079a2d  lea     rcx, aHrPservicewrap_21; "hr = pServiceWrapper->GetDeviceIdIntern"...
0x180079a34  mov     r8d, 2C23h; unsigned int
0x180079a3a  mov     r9d, eax; int
0x180079a3d  mov     [rsp+3D0h+var_3B0], rcx; char *
0x180079a42  lea     rdx, aHandlegetproof; "HandleGetProofOfPossessionTokens"
0x180079a49  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180079a50  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180079a55  nop
0x180079a56  lea     rcx, [rsp+3D0h+var_378]
0x180079a5b  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x180079a60  nop
0x180079a61  lea     rcx, [rbp+2D0h+var_310]; this
0x180079a65  call    ??1WebCookieData@@QEAA@XZ; WebCookieData::~WebCookieData(void)
0x180079a6a  jmp     loc_180079D72
0x180079a6f  mov     rax, [rdi]
0x180079a72  lea     r9, [rbp+2D0h+var_310]
0x180079a76  lea     r8, [rsp+3D0h+var_378]
0x180079a7b  lea     rdx, [rbp+2D0h+var_2A0]
0x180079a7f  mov     rcx, rdi
0x180079a82  mov     rax, [rax+98h]
0x180079a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079a8e  mov     [rsp+3D0h+var_380], eax
0x180079a92  test    eax, eax
0x180079a94  jns     short loc_180079AA5
0x180079a96  lea     rcx, aHrPservicewrap_29; "hr = pServiceWrapper->GetCookieData(web"...
0x180079a9d  mov     r8d, 2C25h
0x180079aa3  jmp     short loc_180079A3A
0x180079aa5  lea     rdx, [rbp+2D0h+var_310]
0x180079aa9  lea     rcx, [rbp+2D0h+var_348]
0x180079aad  call    ?Add@?$CAtlArray@VWebCookieData@@V?$CElementTraits@VWebCookieData@@@ATL@@@ATL@@QEAA_KAEBVWebCookieData@@@Z; ATL::CAtlArray<WebCookieData,ATL::CElementTraits<WebCookieData>>::Add(WebCookieData const &)
0x180079ab2  nop
0x180079ab3  lea     rcx, [rsp+3D0h+var_378]
0x180079ab8  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x180079abd  nop
0x180079abe  lea     rcx, [rbp+2D0h+var_310]; this
0x180079ac2  call    ??1WebCookieData@@QEAA@XZ; WebCookieData::~WebCookieData(void)
0x180079ac7  mov     rdi, [rbp+2D0h+var_340]
0x180079acb  test    rdi, rdi
0x180079ace  jz      loc_180079D23
0x180079ad4  mov     [rsp+3D0h+var_368], rbx
0x180079ad9  mov     [rsp+3D0h+var_358], rbx
0x180079ade  mov     dword ptr [rsp+3D0h+var_360], ebx
0x180079ae2  mov     eax, 8
0x180079ae7  mul     rdi
0x180079aea  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180079af1  cmovb   rax, rcx
0x180079af5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180079afc  mov     rcx, rax; unsigned __int64
0x180079aff  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180079b04  mov     r14, rax
0x180079b07  lea     rcx, [rsp+3D0h+var_368]
0x180079b0c  call    AutoArray__HandleGetProofOfPossessionTokens____77___AutoFreeData_____AutoPointerArrayFunctor__HandleGetProofOfPossessionTokens____77___AutoFreeData____DummyContext___Clear
0x180079b11  mov     [rsp+3D0h+var_368], r14
0x180079b16  mov     dword ptr [rsp+3D0h+var_360], edi
0x180079b1a  test    r14, r14
0x180079b1d  jz      loc_180079D35
0x180079b23  lea     r8, ds:0[rdi*8]; Size
0x180079b2b  xor     edx, edx; Val
0x180079b2d  mov     rcx, r14; void *
0x180079b30  call    memset_0
0x180079b35  mov     rsi, rbx
0x180079b38  cmp     rsi, rdi
0x180079b3b  jnb     loc_180079C88
0x180079b41  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180079b48  mov     ecx, 50h ; 'P'; unsigned __int64
0x180079b4d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180079b52  mov     rbx, rax
0x180079b55  mov     [rsp+3D0h+var_370], rax
0x180079b5a  xor     eax, eax
0x180079b5c  test    rbx, rbx
0x180079b5f  jz      short loc_180079B96
0x180079b61  xor     edx, edx; Val
0x180079b63  lea     r8d, [rax+50h]; Size
0x180079b67  mov     rcx, rbx; void *
0x180079b6a  call    memset_0
  ... truncated ...
```
