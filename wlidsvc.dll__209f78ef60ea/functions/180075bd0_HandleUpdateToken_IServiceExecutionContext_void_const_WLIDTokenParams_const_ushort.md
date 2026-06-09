# HandleUpdateToken(IServiceExecutionContext *,void * const,_WLIDTokenParams const *,ushort * *)

- ea: `0x180075bd0`
- end: `0x1800765cf`
- name: `?HandleUpdateToken@@YAJPEAVIServiceExecutionContext@@QEAXPEBU_WLIDTokenParams@@PEAPEAG@Z`
- size: `2559`
- prototype: `int(struct IServiceExecutionContext *, void *const, const struct _WLIDTokenParams *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180075a90`

## callees

- `0x18000a354`
- `0x18000c050`
- `0x18000ed04`
- `0x18000fd04`
- `0x180011f38`
- `0x1800124c4`
- `0x180013448`
- `0x1800151c4`
- `0x180015fdc`
- `0x1800179c0`
- `0x180017bf0`
- `0x1800181bc`
- `0x180018f80`
- `0x1800191c0`
- `0x18001925c`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18002994c`
- `0x180037288`
- `0x180043344`
- `0x180046aa4`
- `0x180048fd4`
- `0x18004cb2c`
- `0x180053f04`
- `0x180075bd0`
- `0x18007687c`
- `0x18008390c`
- `0x180084374`
- `0x18008964c`
- `0x180128010`

## import_xrefs

- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180075d86`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180075e7f`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180075d86`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180075e7f`

## string_xrefs

- `0x180075c70`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180075ddc`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180075ea2`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180075f86`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180076030`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18007610e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180076177`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180076205`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800762aa`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800762e7`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x18007643d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800765ae`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180076338`: `login.live.com`
- `0x180075f71`: `hr = pSvcWrapper->Impersonate(&client)`
- `0x1800765a1`: `WebCookieManager::WriteCookieData failed (0x%x).`
- `0x180075c46`: `HandleUpdateToken`
- `0x180075df1`: `HandleUpdateToken`
- `0x180076170`: `HandleUpdateToken`
- `0x1800762a3`: `HandleUpdateToken`
- `0x180076436`: `HandleUpdateToken`
- `0x180075d44`: `hr = ValidateSessionKeyType(pToken->sessionKeyType, sessionKeyType)`
- `0x18007601c`: `pIdentityWrapper->IsIdentityNULL(hIdentity) == false`
- `0x180076084`: `pTokenBagWrapper->IsNULL(hTokenBag) == false`
- `0x1800761f8`: `Session key type in tokenbag (%d) is not EncryptedSymmetric. DA token will not be updated in tokenbag.`
- `0x180076394`: `hr = pNgcFunctions->NgcImportSymmetricPopKey( &accountInfo, nullptr, NGC_DEVICE_KEY_TRANSPORT_KEY, pToken->pSessionKey, pToken->sessionKeyLengthBytes, &decryptedSessionKey, &decryptedSessionKeySizeBytes)`
- `0x180076421`: `hr = WlidsvcUtil::ParseDateTimeString(pCreateTime, createTime)`
- `0x18007652c`: `hr = pTokenBagWrapper->StoreToken( hTokenBag, pToken->pTokenUri, pToken->pToken, L"", CTime(createTime), CTime(expireTime), spSessionKey, pToken->tokenType, sessionKeyType )`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall HandleUpdateToken(
        struct IServiceExecutionContext *a1,
        void *const a2,
        const struct _WLIDTokenParams *a3,
        unsigned __int16 **a4)
{
  char v7; // si
  CClientConfigDataCacheManager *v8; // rcx
  bool IsDeviceKeyBindingEnabled; // r14
  __int64 v10; // r8
  __int64 v11; // rdi
  __int64 v12; // rbx
  int v13; // r8d
  const char *v14; // rax
  unsigned int v15; // r8d
  int v16; // r13d
  _WORD *v17; // rax
  _WORD *v18; // rax
  int v19; // r9d
  unsigned int v20; // ebx
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  const char *v25; // rcx
  unsigned int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // r14
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // rax
  int v32; // r9d
  const char *v33; // rax
  unsigned int v34; // r8d
  int v35; // eax
  const char *v36; // rcx
  unsigned int v37; // r8d
  __int64 v38; // rax
  unsigned __int8 *v39; // rdx
  unsigned int v40; // r8d
  int v41; // eax
  const char *v42; // rcx
  unsigned int v43; // r8d
  __int64 (__fastcall *v44)(__int64, __int64, __int64, __int64 *, __int64 *, __int64 *, __int64 *, int *, int, int); // r15
  int v45; // r14d
  __int64 *v46; // rsi
  __int64 *v47; // rdi
  __int64 v48; // rax
  int v49; // eax
  char *v50; // [rsp+20h] [rbp-E0h]
  char *v51; // [rsp+20h] [rbp-E0h]
  char *v52; // [rsp+20h] [rbp-E0h]
  char *v53; // [rsp+20h] [rbp-E0h]
  __int64 v54; // [rsp+60h] [rbp-A0h] BYREF
  int v55; // [rsp+68h] [rbp-98h] BYREF
  __int64 v56; // [rsp+70h] [rbp-90h]
  int v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h] BYREF
  __int64 v59; // [rsp+88h] [rbp-78h] BYREF
  __time64_t Time; // [rsp+90h] [rbp-70h] BYREF
  __int64 v61; // [rsp+98h] [rbp-68h] BYREF
  __int64 v62; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v63; // [rsp+A8h] [rbp-58h] BYREF
  __time64_t v64; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v65; // [rsp+B8h] [rbp-48h]
  unsigned __int8 *v66[3]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v67[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v68; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v69; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v70; // [rsp+F0h] [rbp-10h]
  _QWORD v71[3]; // [rsp+F8h] [rbp-8h] BYREF
  _QWORD v72[8]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v73[36]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int8 *v74; // [rsp+1E0h] [rbp+E0h]
  _BYTE v75[176]; // [rsp+260h] [rbp+160h] BYREF
  int v76; // [rsp+320h] [rbp+220h] BYREF
  void *v77; // [rsp+328h] [rbp+228h]
  __int64 v78; // [rsp+330h] [rbp+230h] BYREF
  __int64 v79; // [rsp+338h] [rbp+238h] BYREF

  v77 = a2;
  v7 = 0;
  v76 = 0;
  v58 = 0;
  v63 = 0;
  v79 = 0;
  v59 = 0;
  Time = 0;
  v64 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v62,
    *((_WORD **)a3 + 7));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v61,
    *((_WORD **)a3 + 8));
  CClientConfigDataCacheManager::theConfigDataManager();
  IsDeviceKeyBindingEnabled = CClientConfigDataCacheManager::IsDeviceKeyBindingEnabled(v8);
  v72[0] = "HandleUpdateToken";
  v72[1] = &v76;
  v72[2] = 0;
  v72[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleUpdateToken",
    (const char *)0x29B5,
    0,
    (const unsigned __int16 *)v50);
  if ( a4 )
    *a4 = 0;
  SmartPerformanceTelemetryJson::SmartPerformanceTelemetryJson(
    (SmartPerformanceTelemetryJson *)v75,
    a4,
    v10,
    *(_QWORD *)a3,
    L"ut");
  v11 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 56LL))(a1);
  v65 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 104LL))(a1);
  v12 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 80LL))(a1);
  v70 = v12;
  v13 = *((_DWORD *)a3 + 12);
  if ( v13 )
  {
    if ( v13 == 1 )
    {
      v16 = 1;
    }
    else
    {
      if ( v13 != 2 )
      {
        LODWORD(v51) = *((_DWORD *)a3 + 12);
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x1AEu,
          L"Invalid SessionKeyType value specified, dwSessionKeyType = %d",
          v51);
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "ValidateSessionKeyType",
          0x1AFu,
          -2147024809,
          "hr = E_INVALIDARG");
        v14 = "hr = ValidateSessionKeyType(pToken->sessionKeyType, sessionKeyType)";
        v15 = 10702;
LABEL_22:
        v76 = -2147024809;
        v19 = -2147024809;
LABEL_23:
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleUpdateToken",
          v15,
          v19,
          v14);
        goto LABEL_24;
      }
      v16 = 2;
    }
  }
  else
  {
    v16 = 0;
  }
  v76 = 0;
  if ( (!*((_QWORD *)a3 + 5) || !*((_DWORD *)a3 + 8))
    && (v16 & 0xFFFFFFFD) != 0
    && !(unsigned int)MsaDevice_UseXTokenBasedSessionKey()
    && !IsDeviceKeyBindingEnabled
    || (v17 = (_WORD *)*((_QWORD *)a3 + 3)) == 0
    || !*v17
    || (v18 = (_WORD *)*((_QWORD *)a3 + 2)) == 0
    || !*v18 )
  {
LABEL_21:
    v14 = "hr = E_INVALIDARG";
    v15 = 10713;
    goto LABEL_22;
  }
  if ( *((_QWORD *)a3 + 7) )
  {
    if ( !*((_QWORD *)a3 + 8) )
      goto LABEL_21;
  }
  else if ( *((_QWORD *)a3 + 8) )
  {
    goto LABEL_21;
  }
  if ( (!*((_QWORD *)a3 + 5) || !*((_DWORD *)a3 + 8)) && !(unsigned int)MsaDevice_UseXTokenBasedSessionKey() )
  {
    if ( IsDeviceKeyBindingEnabled )
    {
      v16 = 0;
    }
    else
    {
      v7 = 1;
      v16 = 2;
      TracePrintW(
        4u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x29E3u,
        L"Reusing existing encrypted session key.");
    }
  }
  if ( !*((_QWORD *)a3 + 7) && !*((_QWORD *)a3 + 8) )
  {
    Time = *(_QWORD *)ATL::CTime::GetTickCount(&v78);
    v22 = ATL::CTime::FormatGmt(&Time);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v62, v22);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v78);
    v64 = Time + 86400;
    v23 = ATL::CTime::FormatGmt(&v64);
    ATL::CSimpleStringT<unsigned short,0>::operator=(&v61, v23);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v78);
  }
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v12 + 32LL))(v12, &v59, 0);
  v76 = v24;
  if ( v24 < 0 )
  {
    v25 = "hr = pSvcWrapper->Impersonate(&client)";
    v26 = 10748;
LABEL_37:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleUpdateToken",
      v26,
      v24,
      v25);
    goto LABEL_24;
  }
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 *, __int64 *))(*(_QWORD *)v12 + 40LL))(v12, &v59, &v58);
  v76 = v24;
  if ( v24 < 0 )
  {
    v25 = "hr = pSvcWrapper->GetLogonId(&client, logonId)";
    v26 = 10749;
    goto LABEL_37;
  }
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 *, void *, __int64 *))(*(_QWORD *)v12 + 24LL))(v12, &v58, v77, &v79);
  v76 = v24;
  if ( v24 < 0 )
  {
    v25 = "hr = pSvcWrapper->GetIdentityHandle(logonId, handle, hIdentity)";
    v26 = 10754;
    goto LABEL_37;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 48LL))(v11, v79) )
  {
    v19 = -2147467261;
    v14 = "pIdentityWrapper->IsIdentityNULL(hIdentity) == false";
    v15 = 10755;
LABEL_44:
    v76 = v19;
    goto LABEL_23;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 40LL))(v11, v79);
  CAutoRefPtr<CIdentityTokenBag>::operator=(&v63, v27);
  v28 = v65;
  v29 = v63;
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v65 + 24LL))(v65, v63) )
  {
    v19 = -2147188685;
    v14 = "pTokenBagWrapper->IsNULL(hTokenBag) == false";
    v15 = 10761;
    goto LABEL_44;
  }
  v56 = 0;
  v55 = 0;
  v57 = 0;
  if ( v16 != 2 )
  {
    if ( v16 )
    {
      v39 = (unsigned __int8 *)*((_QWORD *)a3 + 5);
      if ( v39 )
      {
        v40 = *((_DWORD *)a3 + 8);
        if ( v40 )
          CBytePtr::Attach((CBytePtr *)&v55, v39, v40, 0);
      }
    }
    goto LABEL_78;
  }
  if ( v7 != 1 )
  {
    if ( (*(_BYTE *)a3 & 1) != 0 )
    {
      CBytePtr::Attach((CBytePtr *)&v55, *((unsigned __int8 **)a3 + 5), *((_DWORD *)a3 + 8), 0);
      goto LABEL_78;
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
    memset(v66, 0, sizeof(v66));
    LODWORD(v78) = 0;
    v35 = (*(__int64 (__fastcall **)(__int64, __int64, const wchar_t *, __int64 *))(*(_QWORD *)v11 + 112LL))(
            v11,
            v79,
            L"CID",
            &v54);
    v76 = v35;
    if ( v35 >= 0 )
    {
      if ( !*(_DWORD *)(v54 - 16) )
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x2A49u,
          L"CID is not set for the current identity.");
        v76 = -2147186543;
        Telemetry::IfFailExit(
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          "HandleUpdateToken",
          0x2A4Au,
          -2147186543,
          "hr = PPCRL_E_CREDPROP_NOTFOUND");
        goto LABEL_68;
      }
      v38 = (*(__int64 (__fastcall **)(struct IServiceExecutionContext *))(*(_QWORD *)a1 + 48LL))(a1);
      v71[1] = 0;
      v71[2] = v54;
      v71[0] = L"login.live.com";
      v35 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, __int64, _QWORD, _DWORD, unsigned __int8 **, __int64 *))(*(_QWORD *)v38 + 152LL))(
              v38,
              v71,
              0,
              2,
              *((_QWORD *)a3 + 5),
              *((_DWORD *)a3 + 8),
              v66,
              &v78);
      v76 = v35;
      if ( v35 >= 0 )
      {
        CBytePtr::Attach((CBytePtr *)&v55, v66[0], v78, 0);
        Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v66);
        CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v54);
        goto LABEL_78;
      }
      v36 = "hr = pNgcFunctions->NgcImportSymmetricPopKey( &accountInfo, nullptr, NGC_DEVICE_KEY_TRANSPORT_KEY, pToken->p"
            "SessionKey, pToken->sessionKeyLengthBytes, &decryptedSessionKey, &decryptedSessionKeySizeBytes)";
      v37 = 10844;
    }
    else
    {
      v36 = "hr = pIdentityWrapper->GetCredProperty(hIdentity, PPCRL_CREDPROPERTY_CID, accountCid)";
      v37 = 10822;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleUpdateToken",
      v37,
      v35,
      v36);
LABEL_68:
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)v66);
    CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v54);
    goto LABEL_55;
  }
  (*(void (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v11 + 136LL))(v11, v79, &v55);
  v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 144LL))(v11, v79);
  if ( !v56 || v30 != 2 )
  {
    LODWORD(v51) = v30;
    TracePrintW(
      4u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      0x2A1Eu,
      L"Session key type on handle (%d).",
      v51);
    CPPCRLToken::CPPCRLToken((CPPCRLToken *)v73);
    v31 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
            &v78,
            "http://Passport.NET/tb");
    if ( !(unsigned int)CIdentityTokenBag::RetrieveToken(v29, v31, v73) )
    {
      v32 = -2147186591;
      v33 = "hr = PPCRL_E_IDENTITY_NOT_AUTHENTICATED";
      v34 = 10787;
LABEL_53:
      v76 = v32;
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        "HandleUpdateToken",
        v34,
        v32,
        v33);
LABEL_54:
      CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v73);
LABEL_55:
      CBytePtr::Empty((CBytePtr *)&v55);
      goto LABEL_24;
    }
    CBytePtr::Attach((CBytePtr *)&v55, v74, v73[34], 0);
    if ( v73[0] )
    {
      if ( !v56 )
      {
        v32 = -2147188722;
        v33 = "hr = PPCRL_NO_SESSION_KEY";
        v34 = 10799;
        goto LABEL_53;
      }
      if ( v73[0] != 2 )
      {
        LODWORD(v52) = v73[0];
        TracePrintW(
          4u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
          0x2A35u,
          L"Session key type in tokenbag (%d) is not EncryptedSymmetric. DA token will not be updated in tokenbag.",
          v52);
        v76 = 0;
        goto LABEL_54;
      }
    }
    else
    {
      v16 = 0;
    }
    CPPCRLToken::~CPPCRLToken((CPPCRLToken *)v73);
  }
LABEL_78:
  v54 = 0;
  v78 = 0;
  v41 = WlidsvcUtil::ParseDateTimeString(&v62, &v54);
  v76 = v41;
  if ( v41 < 0 )
  {
    v42 = "hr = WlidsvcUtil::ParseDateTimeString(pCreateTime, createTime)";
    v43 = 10860;
LABEL_80:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleUpdateToken",
      v43,
      v41,
      v42);
    goto LABEL_55;
  }
  v41 = WlidsvcUtil::ParseDateTimeString(&v61, &v78);
  v76 = v41;
  if ( v41 < 0 )
  {
    v42 = "hr = WlidsvcUtil::ParseDateTimeString(pExpireTime, expireTime)";
    v43 = 10861;
    goto LABEL_80;
  }
  v44 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, __int64 *, __int64 *, __int64 *, int *, int, int))(*(_QWORD *)v28 + 40LL);
  v45 = *((_DWORD *)a3 + 2);
  v68 = v78;
  v69 = v54;
  v72[4] = &v78;
  v46 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v78,
          &qword_18013DE20);
  v72[5] = &v54;
  v47 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v54,
          *((_WORD **)a3 + 3));
  v48 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
          v67,
          *((_QWORD *)a3 + 2));
  v41 = v44(v65, v29, v48, v47, v46, &v69, &v68, &v55, v45, v16);
  v76 = v41;
  if ( v41 < 0 )
  {
    v42 = "hr = pTokenBagWrapper->StoreToken( hTokenBag, pToken->pTokenUri, pToken->pToken, L\"\", CTime(createTime), CTi"
          "me(expireTime), spSessionKey, pToken->tokenType, sessionKeyType )";
    v43 = 10873;
    goto LABEL_80;
  }
  CBytePtr::Empty((CBytePtr *)&v55);
  if ( v58 != 999 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v78,
      L"Default");
    WebCookieManager::WebCookieManager((WebCookieManager *)v73);
    v49 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64 *))(*(_QWORD *)v70 + 192LL))(v70, v73, &v79);
    if ( v49 < 0 )
    {
      LODWORD(v53) = v49;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x2A8Du,
        L"WebCookieManager::WriteCookieData failed (0x%x).",
        v53);
    }
    WebCookieManager::~WebCookieManager((WebCookieManager *)v73);
  }
LABEL_24:
  v20 = v76;
  SmartPerformanceTelemetryJson::~SmartPerformanceTelemetryJson((SmartPerformanceTelemetryJson *)v75);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v72);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v61);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v62);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v59);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v79);
  CAutoRefPtr<IStoredIdentity>::Deinit(&v63);
  return v20;
}

```

## disassembly

```asm
0x180075bd0  mov     [rsp-8+arg_8], rdx
0x180075bd5  push    rbp
0x180075bd6  push    rbx
0x180075bd7  push    rsi
0x180075bd8  push    rdi
0x180075bd9  push    r12
0x180075bdb  push    r13
0x180075bdd  push    r14
0x180075bdf  push    r15
0x180075be1  lea     rbp, [rsp-1D8h]
0x180075be9  sub     rsp, 2D8h
0x180075bf0  mov     rbx, r9
0x180075bf3  mov     r12, r8
0x180075bf6  mov     r15, rcx
0x180075bf9  xor     esi, esi
0x180075bfb  mov     [rbp+210h+arg_0], esi
0x180075c01  mov     [rbp+210h+var_290], rsi
0x180075c05  mov     [rbp+210h+var_268], rsi
0x180075c09  mov     [rbp+210h+arg_18], rsi
0x180075c10  mov     [rbp+210h+var_288], rsi
0x180075c14  mov     [rbp+210h+Time], rsi
0x180075c18  mov     [rbp+210h+var_260], rsi
0x180075c1c  mov     rdx, [r8+38h]
0x180075c20  lea     rcx, [rbp+210h+var_270]
0x180075c24  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180075c29  nop
0x180075c2a  mov     rdx, [r12+40h]
0x180075c2f  lea     rcx, [rbp+210h+var_278]
0x180075c33  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180075c38  nop
0x180075c39  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x180075c3e  call    ?IsDeviceKeyBindingEnabled@CClientConfigDataCacheManager@@QEAA_NXZ; CClientConfigDataCacheManager::IsDeviceKeyBindingEnabled(void)
0x180075c43  mov     r14b, al
0x180075c46  lea     rcx, aHandleupdateto; "HandleUpdateToken"
0x180075c4d  mov     [rbp+210h+var_200], rcx
0x180075c51  lea     rax, [rbp+210h+arg_0]
0x180075c58  mov     [rbp+210h+var_1F8], rax
0x180075c5c  mov     [rbp+210h+var_1F0], rsi
0x180075c60  mov     [rbp+210h+var_1E8], rsi
0x180075c64  xor     r9d, r9d; unsigned int
0x180075c67  mov     r8d, 29B5h; char *
0x180075c6d  mov     rdx, rcx; char *
0x180075c70  lea     r13, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180075c77  mov     rcx, r13; this
0x180075c7a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180075c7f  nop
0x180075c80  test    rbx, rbx
0x180075c83  jz      short loc_180075C88
0x180075c85  mov     [rbx], rsi
0x180075c88  lea     rax, aUt; "ut"
0x180075c8f  mov     [rsp+310h+var_2F0], rax; unsigned __int16 *
0x180075c94  mov     r9, [r12]; unsigned __int64
0x180075c98  mov     rdx, rbx; unsigned __int16 **
0x180075c9b  lea     rcx, [rbp+210h+var_B0]; this
0x180075ca2  call    ??0SmartPerformanceTelemetryJson@@QEAA@PEAPEAG_K1PEBG@Z; SmartPerformanceTelemetryJson::SmartPerformanceTelemetryJson(ushort * *,unsigned __int64,unsigned __int64,ushort const *)
0x180075ca7  nop
0x180075ca8  mov     rax, [r15]
0x180075cab  mov     rcx, r15
0x180075cae  mov     rax, [rax+38h]
0x180075cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cb7  mov     rdi, rax
0x180075cba  mov     rcx, [r15]
0x180075cbd  mov     rax, [rcx+68h]
0x180075cc1  mov     rcx, r15
0x180075cc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cc9  mov     [rbp+210h+var_258], rax
0x180075ccd  mov     rcx, [r15]
0x180075cd0  mov     rax, [rcx+50h]
0x180075cd4  mov     rcx, r15
0x180075cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075cdc  mov     rbx, rax
0x180075cdf  mov     [rbp+210h+var_220], rax
0x180075ce3  mov     r8d, [r12+30h]
0x180075ce8  mov     edx, r8d
0x180075ceb  mov     eax, 2
0x180075cf0  test    r8d, r8d
0x180075cf3  jz      short loc_180075D66
0x180075cf5  sub     edx, 1
0x180075cf8  jz      short loc_180075D5E
0x180075cfa  cmp     edx, 1
0x180075cfd  jz      short loc_180075D59
0x180075cff  mov     dword ptr [rsp+310h+var_2F0], r8d
0x180075d04  lea     r9, aInvalidSession; "Invalid SessionKeyType value specified,"...
0x180075d0b  mov     r8d, 1AEh; unsigned int
0x180075d11  mov     rdx, r13; char *
0x180075d14  mov     ecx, eax; unsigned __int8
0x180075d16  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180075d1b  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x180075d22  mov     [rsp+310h+var_2F0], rax; char *
0x180075d27  mov     ebx, 80070057h
0x180075d2c  mov     r9d, ebx; int
0x180075d2f  mov     r8d, 1AFh; unsigned int
0x180075d35  lea     rdx, aValidatesessio; "ValidateSessionKeyType"
0x180075d3c  mov     rcx, r13; char *
0x180075d3f  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180075d44  lea     rax, aHrValidatesess; "hr = ValidateSessionKeyType(pToken->ses"...
0x180075d4b  mov     r8d, 29CEh
0x180075d51  mov     rcx, r13
0x180075d54  jmp     loc_180075DE3
0x180075d59  mov     r13d, eax
0x180075d5c  jmp     short loc_180075D69
0x180075d5e  mov     r13d, 1
0x180075d64  jmp     short loc_180075D69
0x180075d66  mov     r13d, esi
0x180075d69  mov     [rbp+210h+arg_0], esi
0x180075d6f  cmp     [r12+28h], rsi
0x180075d74  jz      short loc_180075D7D
0x180075d76  cmp     [r12+20h], esi
0x180075d7b  jnz     short loc_180075D96
0x180075d7d  test    r13d, 0FFFFFFFDh
0x180075d84  jz      short loc_180075D96
0x180075d86  call    cs:__imp_MsaDevice_UseXTokenBasedSessionKey
0x180075d8c  test    eax, eax
0x180075d8e  jnz     short loc_180075D96
0x180075d90  cmp     r14b, 1
0x180075d94  jnz     short loc_180075DCA
0x180075d96  mov     rax, [r12+18h]
0x180075d9b  test    rax, rax
0x180075d9e  jz      short loc_180075DCA
0x180075da0  cmp     [rax], si
0x180075da3  jz      short loc_180075DCA
0x180075da5  mov     rax, [r12+10h]
0x180075daa  test    rax, rax
0x180075dad  jz      short loc_180075DCA
0x180075daf  cmp     [rax], si
0x180075db2  jz      short loc_180075DCA
0x180075db4  cmp     [r12+38h], rsi
0x180075db9  jnz     loc_180075E64
0x180075dbf  cmp     [r12+40h], rsi
0x180075dc4  jz      loc_180075E6F
0x180075dca  mov     ebx, 80070057h
0x180075dcf  lea     rax, aHrEInvalidarg; "hr = E_INVALIDARG"
0x180075dd6  mov     r8d, 29D9h; unsigned int
0x180075ddc  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180075de3  mov     [rbp+210h+arg_0], ebx
0x180075de9  mov     r9d, ebx; int
0x180075dec  mov     [rsp+310h+var_2F0], rax; char *
0x180075df1  lea     rdx, aHandleupdateto; "HandleUpdateToken"
0x180075df8  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180075dfd  mov     ebx, [rbp+210h+arg_0]
0x180075e03  lea     rcx, [rbp+210h+var_B0]; this
0x180075e0a  call    ??1SmartPerformanceTelemetryJson@@UEAA@XZ; SmartPerformanceTelemetryJson::~SmartPerformanceTelemetryJson(void)
0x180075e0f  nop
0x180075e10  lea     rcx, [rbp+210h+var_200]
0x180075e14  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180075e19  nop
0x180075e1a  lea     rcx, [rbp+210h+var_278]
0x180075e1e  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180075e23  nop
0x180075e24  lea     rcx, [rbp+210h+var_270]
0x180075e28  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180075e2d  nop
0x180075e2e  lea     rcx, [rbp+210h+var_288]; this
0x180075e32  call    ??1CAutoImpersonateClient@@QEAA@XZ; CAutoImpersonateClient::~CAutoImpersonateClient(void)
0x180075e37  nop
0x180075e38  lea     rcx, [rbp+210h+arg_18]
0x180075e3f  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x180075e44  nop
0x180075e45  lea     rcx, [rbp+210h+var_268]
0x180075e49  call    ?Deinit@?$CAutoRefPtr@VIStoredIdentity@@@@IEAAXXZ; CAutoRefPtr<IStoredIdentity>::Deinit(void)
0x180075e4e  mov     eax, ebx
0x180075e50  add     rsp, 2D8h
0x180075e57  pop     r15
0x180075e59  pop     r14
0x180075e5b  pop     r13
0x180075e5d  pop     r12
0x180075e5f  pop     rdi
0x180075e60  pop     rsi
0x180075e61  pop     rbx
0x180075e62  pop     rbp
0x180075e63  retn
0x180075e64  cmp     [r12+40h], rsi
0x180075e69  jz      loc_180075DCA
0x180075e6f  cmp     qword ptr [r12+28h], 0
0x180075e75  jz      short loc_180075E7F
0x180075e77  cmp     dword ptr [r12+20h], 0
0x180075e7d  jnz     short loc_180075EB6
0x180075e7f  call    cs:__imp_MsaDevice_UseXTokenBasedSessionKey
0x180075e85  test    eax, eax
0x180075e87  jnz     short loc_180075EB6
0x180075e89  test    r14b, r14b
0x180075e8c  jnz     short loc_180075EB3
0x180075e8e  mov     sil, 1
0x180075e91  lea     r13d, [rax+2]
0x180075e95  lea     r9, aReusingExistin; "Reusing existing encrypted session key."
0x180075e9c  mov     r8d, 29E3h; unsigned int
0x180075ea2  lea     rdx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180075ea9  lea     ecx, [rax+4]; unsigned __int8
0x180075eac  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180075eb1  jmp     short loc_180075EB6
0x180075eb3  xor     r13d, r13d
0x180075eb6  cmp     qword ptr [r12+38h], 0
0x180075ebc  jnz     loc_180075F51
0x180075ec2  cmp     qword ptr [r12+40h], 0
0x180075ec8  jnz     loc_180075F51
0x180075ece  lea     rcx, [rbp+210h+arg_10]
0x180075ed5  call    ?GetTickCount@CTime@ATL@@SA?AV12@XZ; ATL::CTime::GetTickCount(void)
0x180075eda  mov     rcx, [rax]
0x180075edd  mov     [rbp+210h+Time], rcx
0x180075ee1  lea     r8, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x180075ee8  lea     rdx, [rbp+210h+arg_10]
0x180075eef  lea     rcx, [rbp+210h+Time]; Time
0x180075ef3  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x180075ef8  nop
0x180075ef9  mov     rdx, rax
0x180075efc  lea     rcx, [rbp+210h+var_270]
0x180075f00  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180075f05  nop
0x180075f06  lea     rcx, [rbp+210h+arg_10]
0x180075f0d  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180075f12  mov     rax, [rbp+210h+Time]
0x180075f16  add     rax, 15180h
0x180075f1c  mov     [rbp+210h+var_260], rax
0x180075f20  lea     r8, aYMDtHMSz; "%Y-%m-%dT%H:%M:%SZ"
0x180075f27  lea     rdx, [rbp+210h+arg_10]
0x180075f2e  lea     rcx, [rbp+210h+var_260]; Time
0x180075f32  call    ?FormatGmt@CTime@ATL@@QEBA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@PEBG@Z; ATL::CTime::FormatGmt(ushort const *)
0x180075f37  nop
0x180075f38  mov     rdx, rax
0x180075f3b  lea     rcx, [rbp+210h+var_278]
0x180075f3f  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x180075f44  nop
0x180075f45  lea     rcx, [rbp+210h+arg_10]
0x180075f4c  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x180075f51  mov     rax, [rbx]
0x180075f54  xor     r8d, r8d
0x180075f57  lea     rdx, [rbp+210h+var_288]
0x180075f5b  mov     rcx, rbx
0x180075f5e  mov     rax, [rax+20h]
0x180075f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075f67  mov     [rbp+210h+arg_0], eax
0x180075f6d  test    eax, eax
0x180075f6f  jns     short loc_180075F92
0x180075f71  lea     rcx, aHrPsvcwrapperI; "hr = pSvcWrapper->Impersonate(&client)"
0x180075f78  mov     r8d, 29FCh
0x180075f7e  mov     [rsp+310h+var_2F0], rcx
0x180075f83  mov     r9d, eax
0x180075f86  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180075f8d  jmp     loc_180075DF1
0x180075f92  mov     rax, [rbx]
0x180075f95  lea     r8, [rbp+210h+var_290]
0x180075f99  lea     rdx, [rbp+210h+var_288]
0x180075f9d  mov     rcx, rbx
0x180075fa0  mov     rax, [rax+28h]
0x180075fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075fa9  mov     [rbp+210h+arg_0], eax
0x180075faf  test    eax, eax
0x180075fb1  jns     short loc_180075FC2
0x180075fb3  lea     rcx, aHrPsvcwrapperG_2; "hr = pSvcWrapper->GetLogonId(&client, l"...
0x180075fba  mov     r8d, 29FDh
0x180075fc0  jmp     short loc_180075F7E
0x180075fc2  mov     rax, [rbx]
0x180075fc5  lea     r9, [rbp+210h+arg_18]
0x180075fcc  mov     r8, [rbp+210h+arg_8]
0x180075fd3  lea     rdx, [rbp+210h+var_290]
0x180075fd7  mov     rcx, rbx
0x180075fda  mov     rax, [rax+18h]
0x180075fde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075fe3  mov     [rbp+210h+arg_0], eax
0x180075fe9  test    eax, eax
0x180075feb  jns     short loc_180075FFC
0x180075fed  lea     rcx, aHrPsvcwrapperG_3; "hr = pSvcWrapper->GetIdentityHandle(log"...
0x180075ff4  mov     r8d, 2A02h
0x180075ffa  jmp     short loc_180075F7E
0x180075ffc  mov     rax, [rdi]
0x180075fff  mov     rdx, [rbp+210h+arg_18]
0x180076006  mov     rcx, rdi
0x180076009  mov     rax, [rax+30h]
0x18007600d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076012  test    al, al
0x180076014  jz      short loc_18007603C
0x180076016  mov     r9d, 80004003h
0x18007601c  lea     rax, aPidentitywrapp; "pIdentityWrapper->IsIdentityNULL(hIdent"...
0x180076023  mov     r8d, 2A03h
0x180076029  mov     [rbp+210h+arg_0], r9d
0x180076030  lea     rcx, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180076037  jmp     loc_180075DEC
0x18007603c  mov     rax, [rdi]
0x18007603f  mov     rdx, [rbp+210h+arg_18]
0x180076046  mov     rcx, rdi
0x180076049  mov     rax, [rax+28h]
0x18007604d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076052  mov     rdx, rax
0x180076055  lea     rcx, [rbp+210h+var_268]
0x180076059  call    ??4?$CAutoRefPtr@VCIdentityTokenBag@@@@QEAAAEAV0@PEAVCIdentityTokenBag@@@Z; CAutoRefPtr<CIdentityTokenBag>::operator=(CIdentityTokenBag *)
0x18007605e  mov     r14, [rbp+210h+var_258]
0x180076062  mov     rax, [r14]
0x180076065  mov     rbx, [rbp+210h+var_268]
0x180076069  mov     rdx, rbx
0x18007606c  mov     rcx, r14
0x18007606f  mov     rax, [rax+18h]
0x180076073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076078  xor     ecx, ecx
0x18007607a  test    al, al
0x18007607c  jz      short loc_180076093
0x18007607e  mov     r9d, 80048033h
0x180076084  lea     rax, aPtokenbagwrapp; "pTokenBagWrapper->IsNULL(hTokenBag) == "...
0x18007608b  mov     r8d, 2A09h
0x180076091  jmp     short loc_180076029
0x180076093  mov     [rsp+310h+var_2A0], rcx
  ... truncated ...
```
