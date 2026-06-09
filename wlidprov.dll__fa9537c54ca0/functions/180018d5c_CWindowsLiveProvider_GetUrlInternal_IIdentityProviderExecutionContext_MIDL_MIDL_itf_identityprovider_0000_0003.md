# CWindowsLiveProvider::GetUrlInternal(IIdentityProviderExecutionContext *,__MIDL___MIDL_itf_identityprovider_0000_0003_0001,IBindCtx *,tagVARIANT *,ushort * *)

- ea: `0x180018d5c`
- end: `0x180019664`
- name: `?GetUrlInternal@CWindowsLiveProvider@@AEAAJPEAVIIdentityProviderExecutionContext@@W4__MIDL___MIDL_itf_identityprovider_0000_0003_0001@@PEAUIBindCtx@@PEAUtagVARIANT@@PEAPEAG@Z`
- size: `2312`
- prototype: `int(CWindowsLiveProvider *__hidden this, struct IIdentityProviderExecutionContext *, enum __MIDL___MIDL_itf_identityprovider_0000_0003_0001, struct IBindCtx *, struct tagVARIANT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `34`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024fb0`

## callees

- `0x1800034c0`
- `0x180003990`
- `0x180004b2c`
- `0x1800061a8`
- `0x180006b50`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000a4f0`
- `0x18000bcc4`
- `0x18000f100`
- `0x18000f138`
- `0x180010b80`
- `0x180013434`
- `0x1800160ec`
- `0x180016ea0`
- `0x180017310`
- `0x18001839c`
- `0x180018d5c`
- `0x18001966c`
- `0x1800196fc`
- `0x180019b50`
- `0x18001c5bc`
- `0x18001c628`
- `0x180023300`
- `0x180023320`
- `0x1800233f8`
- `0x18002380c`
- `0x1800259dc`
- `0x18003f9c4`
- `0x18004e6b0`
- `0x18004e944`
- `0x180052754`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019412`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019412`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800195c3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800195c3`
- `OLEAUT32!__imp_VariantClear` at `0x180019149`
- `OLEAUT32!__imp_VariantClear` at `0x180019149`

## string_xrefs

- `0x1800191af`: `CompleteAccount`
- `0x180019215`: `Invalid combination of urlID and flow Id: 0x%x.`
- `0x18001926d`: `hr = pLiveIdNtService->WLIDCGetConfigDWORDValue(WLID_CONFIG_ENABLE_SERVER_PASSWORD_CHANGE, &enableServerPasswordChange)`
- `0x1800192fa`: `WLIDCGetServiceConfig returned an empty string for '%s', returning ERROR_NOT_FOUND (0x%x).`
- `0x18001950a`: `hr = GetChangePasswordPostData(pLiveIdNtService, isInterrupt, additionalPostData)`
- `0x180019535`: `hr = GetSignedTokenPostData(pLiveIdNtService, additionalPostData)`
- `0x180019562`: `hr = GetSignedTokenPostData(pLiveIdNtService, additionalPostData)`
- `0x180019023`: `CompleteAccountConnect`
- `0x180018f11`: `CompleteAccountSignUp`
- `0x180018e84`: `CompleteAccountSignIn`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWindowsLiveProvider::GetUrlInternal(
        CWindowsLiveProvider *this,
        struct IIdentityProviderExecutionContext *a2,
        enum __MIDL___MIDL_itf_identityprovider_0000_0003_0001 a3,
        struct IBindCtx *a4,
        struct tagVARIANT *pvarg,
        unsigned __int16 **a6)
{
  __int64 v8; // rax
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 v11; // r12
  __int64 v12; // r13
  unsigned __int16 **v13; // r15
  struct tagVARIANT *v14; // r14
  CWindowsLiveProvider *v15; // rcx
  CWindowsLiveProvider *v16; // rcx
  enum __MIDL___MIDL_itf_identityprovider_0000_0003_0001 v17; // edx
  int v18; // ecx
  CWindowsLiveProvider *v19; // rcx
  CWindowsLiveProvider *v20; // rcx
  CWindowsLiveProvider *v21; // rcx
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rdi
  int PlatformQualifier; // eax
  const char *v26; // rcx
  unsigned int v27; // r8d
  const wchar_t *v28; // rax
  unsigned __int16 **v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rbx
  unsigned __int16 *v33; // rax
  unsigned __int8 v34; // dl
  PPTraceStatus *v35; // rcx
  char v36; // cl
  const unsigned __int16 *String; // rax
  __int64 v38; // rcx
  __int64 v39; // rbx
  OLECHAR *v40; // rcx
  BSTR v41; // rax
  unsigned int v42; // ebx
  char *v44; // [rsp+28h] [rbp-C9h]
  char *v45; // [rsp+28h] [rbp-C9h]
  unsigned __int16 *v46; // [rsp+38h] [rbp-B9h] BYREF
  int v47; // [rsp+40h] [rbp-B1h] BYREF
  int v48; // [rsp+44h] [rbp-ADh] BYREF
  OLECHAR *strIn; // [rsp+48h] [rbp-A9h] BYREF
  __int64 v50; // [rsp+50h] [rbp-A1h] BYREF
  __int64 v51; // [rsp+58h] [rbp-99h] BYREF
  __int64 v52; // [rsp+60h] [rbp-91h] BYREF
  __int64 v53; // [rsp+68h] [rbp-89h] BYREF
  unsigned __int64 v54; // [rsp+70h] [rbp-81h] BYREF
  _QWORD v55[3]; // [rsp+78h] [rbp-79h] BYREF
  _QWORD v56[3]; // [rsp+90h] [rbp-61h] BYREF
  char v57; // [rsp+A8h] [rbp-49h]
  _QWORD v58[4]; // [rsp+B0h] [rbp-41h] BYREF
  _BYTE v59[32]; // [rsp+D0h] [rbp-21h] BYREF
  char v60[72]; // [rsp+F0h] [rbp-1h] BYREF
  CWindowsLiveProvider *v61; // [rsp+148h] [rbp+57h] BYREF
  int appended; // [rsp+150h] [rbp+5Fh] BYREF
  enum __MIDL___MIDL_itf_identityprovider_0000_0003_0001 v63; // [rsp+158h] [rbp+67h] BYREF

  v63 = a3;
  v61 = this;
  appended = 0;
  v48 = 0;
  v54 = 0;
  v53 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v46);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v52);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&strIn);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v51);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v50);
  LOBYTE(v61) = 0;
  memset(v55, 0, sizeof(v55));
  if ( dword_18008535C > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18008535C);
    if ( dword_18008535C == -1 )
    {
      qword_180084788 = (__int64)L"CPSignInAuthUp";
      dword_180084790 = 65538;
      qword_180084798 = (__int64)L"CPAddUserSignIn";
      dword_1800847A0 = 65537;
      qword_1800847A8 = (__int64)L"OOBESignInAuthUp";
      dword_1800847B0 = 65539;
      qword_1800847B8 = (__int64)L"OOBEUpgradeSignIn";
      dword_1800847C0 = 65540;
      qword_1800847C8 = (__int64)L"CompleteAccountSignIn";
      dword_1800847D0 = 65541;
      qword_1800847D8 = (__int64)L"NthUserSignIn";
      dword_1800847E0 = 0;
      qword_1800847E8 = (__int64)L"CPSignUpAuthUp";
      dword_1800847F0 = 2;
      qword_1800847F8 = (__int64)L"CPAddUserSignUp";
      dword_180084800 = 1;
      qword_180084808 = (__int64)L"OOBESignUpAuthUp";
      dword_180084810 = 3;
      qword_180084818 = (__int64)L"OOBEUpgradeSignUp";
      dword_180084820 = 4;
      qword_180084828 = (__int64)L"CompleteAccountSignUp";
      dword_180084830 = 5;
      qword_180084838 = (__int64)L"NthUserSignUp";
      dword_180084840 = 196608;
      qword_180084848 = (__int64)L"CPIfExistsAuthUp";
      dword_180084850 = 196610;
      qword_180084858 = (__int64)L"CPAddUserIfExists";
      dword_180084860 = 196609;
      qword_180084868 = (__int64)L"OOBEIfExistsAuthUp";
      dword_180084870 = 0x20000;
      qword_180084878 = (__int64)L"CPChangePwdAuthUp";
      dword_180084880 = 0x40000;
      qword_180084888 = (__int64)L"URL_AccountSettings";
      dword_180084890 = 262146;
      qword_180084898 = (__int64)L"URL_AccountSettings";
      dword_1800848A0 = 262145;
      qword_1800848A8 = (__int64)L"URL_AccountSettings";
      dword_1800848B0 = 393216;
      qword_1800848B8 = (__int64)L"CPConnect";
      dword_1800848C0 = 393217;
      qword_1800848C8 = (__int64)L"OOBEConnect";
      dword_1800848D0 = 393219;
      qword_1800848D8 = (__int64)L"OOBEUpgradeConnect";
      dword_1800848E0 = 393220;
      qword_1800848E8 = (__int64)L"CompleteAccountConnect";
      dword_1800848F0 = 393221;
      qword_1800848F8 = (__int64)L"NthUserConnect";
      Init_thread_footer(&dword_18008535C);
    }
  }
  v58[0] = "CWindowsLiveProvider::GetUrlInternal";
  v58[1] = &appended;
  v58[2] = 0;
  v58[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::GetUrlInternal",
    (const char *)0x8BD,
    0,
    (const unsigned __int16 *)v44);
  v8 = lambda_934676d547081d7307c52d658d925334_::_lambda_934676d547081d7307c52d658d925334_(v60, &appended, &v63, &v48);
  wil::scope_exit__lambda_934676d547081d7307c52d658d925334___(v59, v8);
  v9 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 32LL))(a2);
  v10 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 8LL))(a2);
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 24LL))(v10);
  v12 = (*(__int64 (__fastcall **)(struct IIdentityProviderExecutionContext *))(*(_QWORD *)a2 + 56LL))(a2);
  v13 = a6;
  if ( !a6 )
  {
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      0x8D7u,
      L"Url is null.");
LABEL_6:
    appended = -2147024809;
    goto LABEL_72;
  }
  v14 = pvarg;
  if ( !pvarg )
  {
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      0x8DEu,
      L"PostData is null.");
    goto LABEL_6;
  }
  *a6 = 0;
  VariantClear(v14);
  if ( (unsigned int)CWindowsLiveProvider::BindCtxContainsObject(v15, a4, L"OutOfBoxExperience") )
  {
    v17 = v63;
    v18 = (v63 << 16) | 1;
  }
  else if ( (unsigned int)CWindowsLiveProvider::BindCtxContainsObject(v16, a4, L"ModernSettingsAddUser") )
  {
    v17 = v63;
    v18 = (v63 << 16) | 2;
  }
  else if ( (unsigned int)CWindowsLiveProvider::BindCtxContainsObject(v19, a4, L"OutOfBoxUpgradeExperience") )
  {
    v17 = v63;
    v18 = (v63 << 16) | 3;
  }
  else if ( (unsigned int)CWindowsLiveProvider::BindCtxContainsObject(v20, a4, L"CompleteAccount") )
  {
    v17 = v63;
    v18 = (v63 << 16) | 4;
  }
  else
  {
    v22 = CWindowsLiveProvider::BindCtxContainsObject(v21, a4, L"NthUserFirstAuth");
    v17 = v63;
    v18 = v63 << 16;
    if ( v22 )
      v18 |= 5u;
  }
  v48 = v18;
  v23 = 0;
  while ( LODWORD(qword_180084780[2 * v23]) != v18 )
  {
    if ( (unsigned __int64)++v23 >= 0x18 )
    {
      if ( v23 == 24 )
      {
        LODWORD(v45) = v18;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
          0x90Fu,
          L"Invalid combination of urlID and flow Id: 0x%x.",
          v45);
        goto LABEL_6;
      }
      break;
    }
  }
  v24 = qword_180084780[2 * v23 + 1];
  v47 = 0;
  if ( v17 == IDENTITY_URL_CHANGE_PASSWORD_WIZARD )
  {
    PlatformQualifier = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v9 + 96LL))(v9, 20, &v47);
    appended = PlatformQualifier;
    if ( PlatformQualifier < 0 )
    {
      v26 = "hr = pLiveIdNtService->WLIDCGetConfigDWORDValue(WLID_CONFIG_ENABLE_SERVER_PASSWORD_CHANGE, &enableServerPasswordChange)";
      v27 = 2328;
LABEL_27:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        "CWindowsLiveProvider::GetUrlInternal",
        v27,
        PlatformQualifier,
        v26);
      goto LABEL_72;
    }
    v28 = L"CPChangePwdOnline";
    if ( !v47 )
      v28 = (const wchar_t *)v24;
    v24 = (__int64)v28;
  }
  appended = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v9 + 112LL))(v9, v24, &v53);
  if ( appended < 0 )
    goto LABEL_72;
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v46, v53);
  if ( !*((_DWORD *)v46 - 4) )
  {
    appended = -2147023728;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      0x933u,
      L"WLIDCGetServiceConfig returned an empty string for '%s', returning ERROR_NOT_FOUND (0x%x).",
      v24,
      -2147023728);
    goto LABEL_72;
  }
  PlatformQualifier = MsaUserExtImpl::GetPlatformQualifier((MsaUserExtImpl *)v55, v29);
  appended = PlatformQualifier;
  if ( PlatformQualifier < 0 )
  {
    v26 = "hr = MsaUserExtImpl::GetPlatformQualifier(&spPlatformType)";
    v27 = 2359;
    goto LABEL_27;
  }
  PlatformQualifier = UrlAppendQueryString(&v46, L"Platform", v55[0]);
  appended = PlatformQualifier;
  if ( PlatformQualifier < 0 )
  {
    v26 = "hr = UrlAppendQueryString(wstrFullUrl, L\"Platform\", spPlatformType)";
    v27 = 2360;
    goto LABEL_27;
  }
  LODWORD(a6) = 4;
  v30 = 0;
  v31 = (unsigned int)v63;
  while ( !v30 )
  {
    if ( v63 == (_DWORD)a6 )
      goto LABEL_44;
    v30 = 1;
  }
  PlatformQualifier = UrlUtilities::AppendMarket(v11, &v46);
  appended = PlatformQualifier;
  if ( PlatformQualifier < 0 )
  {
    v26 = "hr = UrlUtilities::AppendMarket(pWinApiLite, wstrFullUrl)";
    v27 = 2366;
    goto LABEL_27;
  }
LABEL_44:
  if ( (unsigned int)CWindowsLiveProvider::BindCtxContainsUserName(v31, a4, &v52) != 1
    || (appended = UrlAppendQueryString(&v46, L"username", v52), appended >= 0) )
  {
    appended = StringCchLengthW(v46, 0x823u, &v54);
    if ( appended >= 0 )
    {
      v32 = v54;
      v33 = (unsigned __int16 *)CoTaskMemAlloc(2 * v54 + 2);
      *v13 = v33;
      if ( !v33 )
      {
        appended = -2147024882;
        goto LABEL_72;
      }
      appended = StringCchCopyW(v33, v32 + 1, v46);
      if ( appended < 0 )
        goto LABEL_72;
      if ( !TraceSession::IsRedactionEnabled((TraceSession *)&TraceSession::_instance)
        || (LOBYTE(v35) = 1, !PPTraceStatus::TraceOnFlag(v35, v34)) )
      {
        v36 = 0;
      }
      v56[0] = &PPRedactedStringW::`vftable';
      v56[1] = *v13;
      v56[2] = 0;
      v57 = v36;
      String = PPRedactedStringW::GetString((PPRedactedStringW *)v56);
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        0x963u,
        L"Output url: '%ls'",
        String);
      PPRedactedStringW::~PPRedactedStringW((PPRedactedStringW *)v56);
      if ( (int)UrlUtilities::GetColorSet(v12, &v51) >= 0 )
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &strIn,
          L"%ls=%ls",
          L"Win8Colors",
          v51);
      if ( v63 == IDENTITY_URL_CHANGE_PASSWORD_WIZARD )
      {
        if ( v47 )
        {
          PlatformQualifier = CWindowsLiveProvider::GetSignedTokenPostData(v38, v9, &v50);
          appended = PlatformQualifier;
          if ( PlatformQualifier < 0 )
          {
            v26 = "hr = GetSignedTokenPostData(pLiveIdNtService, additionalPostData)";
            v27 = 2424;
            goto LABEL_27;
          }
        }
        else
        {
          PlatformQualifier = CWindowsLiveProvider::GetChangePasswordPostData(v38, v9, &v61, &v50);
          appended = PlatformQualifier;
          if ( PlatformQualifier < 0 )
          {
            v26 = "hr = GetChangePasswordPostData(pLiveIdNtService, isInterrupt, additionalPostData)";
            v27 = 2420;
            goto LABEL_27;
          }
        }
      }
      else if ( v48 == 393221 )
      {
        PlatformQualifier = CWindowsLiveProvider::GetSignedTokenPostData(v38, v9, &v50);
        appended = PlatformQualifier;
        if ( PlatformQualifier < 0 )
        {
          v26 = "hr = GetSignedTokenPostData(pLiveIdNtService, additionalPostData)";
          v27 = 2429;
          goto LABEL_27;
        }
      }
      v39 = v50;
      if ( *(_DWORD *)(v50 - 16) )
      {
        if ( *((_DWORD *)strIn - 4) )
          ATL::CSimpleStringT<unsigned short,0>::Append(&strIn, L"&", 1);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          &strIn,
          L"%ls",
          v39);
      }
      v40 = strIn;
      if ( *((_DWORD *)strIn - 4) )
      {
        v14->vt = 8;
        v41 = SysAllocStringLen(v40, *((_DWORD *)v40 - 4));
        if ( !v41 )
          ATL::CSimpleStringT<char,0>::ThrowMemoryException();
        v14->llVal = (LONGLONG)v41;
      }
    }
  }
LABEL_72:
  v42 = ErrorHandlingUtilities::MapInternalErrorToExternal(appended, (bool)v61, 0);
  wil::details::lambda_call__lambda_934676d547081d7307c52d658d925334___::_lambda_call__lambda_934676d547081d7307c52d658d925334___(v59);
  CTraceFuncW<long>::~CTraceFuncW<long>(v58);
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>(v55);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v50);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v51);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&strIn);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v52);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v46);
  CMIDLPtr<unsigned short *>::Clear(&v53);
  return v42;
}

```

## disassembly

```asm
0x180018d5c  mov     rax, rsp
0x180018d5f  mov     [rax+20h], rbx
0x180018d63  mov     [rax+18h], r8d
0x180018d67  mov     [rax+8], rcx
0x180018d6b  push    rbp
0x180018d6c  push    rsi
0x180018d6d  push    rdi
0x180018d6e  push    r12
0x180018d70  push    r13
0x180018d72  push    r14
0x180018d74  push    r15
0x180018d76  lea     rbp, [rax-4Fh]
0x180018d7a  sub     rsp, 100h
0x180018d81  mov     rbx, r9
0x180018d84  mov     rdi, rdx
0x180018d87  xor     r14d, r14d
0x180018d8a  mov     [rbp+47h+arg_8], r14d
0x180018d8e  mov     dword ptr [rsp+130h+var_F8+4], r14d
0x180018d93  mov     [rsp+130h+var_C8], r14
0x180018d98  mov     [rsp+130h+var_D0], r14
0x180018d9d  lea     rcx, [rsp+130h+var_100]; void *
0x180018da2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018da7  nop
0x180018da8  lea     rcx, [rsp+130h+var_D8]; void *
0x180018dad  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018db2  nop
0x180018db3  lea     rcx, [rsp+130h+strIn]; void *
0x180018db8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018dbd  nop
0x180018dbe  lea     rcx, [rsp+130h+var_E0]; void *
0x180018dc3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018dc8  nop
0x180018dc9  lea     rcx, [rsp+130h+var_E8]; void *
0x180018dce  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180018dd3  nop
0x180018dd4  mov     byte ptr [rbp+47h+arg_0], r14b
0x180018dd8  mov     [rbp+47h+var_C0], r14
0x180018ddc  mov     [rbp+47h+var_B0], r14
0x180018de0  mov     [rbp+47h+var_B8], r14
0x180018de4  mov     ecx, cs:_tls_index
0x180018dea  mov     rax, gs:58h
0x180018df3  mov     edx, 4
0x180018df8  mov     rax, [rax+rcx*8]
0x180018dfc  mov     eax, [rdx+rax]
0x180018dff  cmp     cs:dword_18008535C, eax
0x180018e05  jle     loc_180019055
0x180018e0b  lea     rcx, dword_18008535C
0x180018e12  call    _Init_thread_header
0x180018e17  cmp     cs:dword_18008535C, 0FFFFFFFFh
0x180018e1e  jnz     loc_180019055
0x180018e24  lea     rax, aCpsigninauthup; "CPSignInAuthUp"
0x180018e2b  mov     cs:qword_180084788, rax
0x180018e32  mov     cs:dword_180084790, 10002h
0x180018e3c  lea     rax, aCpaddusersigni; "CPAddUserSignIn"
0x180018e43  mov     cs:qword_180084798, rax
0x180018e4a  mov     cs:dword_1800847A0, 10001h
0x180018e54  lea     rax, aOobesigninauth; "OOBESignInAuthUp"
0x180018e5b  mov     cs:qword_1800847A8, rax
0x180018e62  mov     cs:dword_1800847B0, 10003h
0x180018e6c  lea     rax, aOobeupgradesig; "OOBEUpgradeSignIn"
0x180018e73  mov     cs:qword_1800847B8, rax
0x180018e7a  mov     cs:dword_1800847C0, 10004h
0x180018e84  lea     rax, aCompleteaccoun_0; "CompleteAccountSignIn"
0x180018e8b  mov     cs:qword_1800847C8, rax
0x180018e92  mov     cs:dword_1800847D0, 10005h
0x180018e9c  lea     rax, aNthusersignin; "NthUserSignIn"
0x180018ea3  mov     cs:qword_1800847D8, rax
0x180018eaa  mov     cs:dword_1800847E0, r14d
0x180018eb1  lea     rax, aCpsignupauthup; "CPSignUpAuthUp"
0x180018eb8  mov     cs:qword_1800847E8, rax
0x180018ebf  mov     cs:dword_1800847F0, 2
0x180018ec9  lea     rax, aCpaddusersignu; "CPAddUserSignUp"
0x180018ed0  mov     cs:qword_1800847F8, rax
0x180018ed7  mov     cs:dword_180084800, 1
0x180018ee1  lea     rax, aOobesignupauth; "OOBESignUpAuthUp"
0x180018ee8  mov     cs:qword_180084808, rax
0x180018eef  mov     cs:dword_180084810, 3
0x180018ef9  lea     rax, aOobeupgradesig_0; "OOBEUpgradeSignUp"
0x180018f00  mov     cs:qword_180084818, rax
0x180018f07  mov     cs:dword_180084820, 4
0x180018f11  lea     rax, aCompleteaccoun_2; "CompleteAccountSignUp"
0x180018f18  mov     cs:qword_180084828, rax
0x180018f1f  mov     cs:dword_180084830, 5
0x180018f29  lea     rax, aNthusersignup; "NthUserSignUp"
0x180018f30  mov     cs:qword_180084838, rax
0x180018f37  mov     cs:dword_180084840, 30000h
0x180018f41  lea     rax, aCpifexistsauth; "CPIfExistsAuthUp"
0x180018f48  mov     cs:qword_180084848, rax
0x180018f4f  mov     cs:dword_180084850, 30002h
0x180018f59  lea     rax, aCpadduserifexi; "CPAddUserIfExists"
0x180018f60  mov     cs:qword_180084858, rax
0x180018f67  mov     cs:dword_180084860, 30001h
0x180018f71  lea     rax, aOobeifexistsau; "OOBEIfExistsAuthUp"
0x180018f78  mov     cs:qword_180084868, rax
0x180018f7f  mov     cs:dword_180084870, 20000h
0x180018f89  lea     rax, aCpchangepwdaut; "CPChangePwdAuthUp"
0x180018f90  mov     cs:qword_180084878, rax
0x180018f97  mov     cs:dword_180084880, 40000h
0x180018fa1  lea     rax, aUrlAccountsett; "URL_AccountSettings"
0x180018fa8  mov     cs:qword_180084888, rax
0x180018faf  mov     cs:dword_180084890, 40002h
0x180018fb9  mov     cs:qword_180084898, rax
0x180018fc0  mov     cs:dword_1800848A0, 40001h
0x180018fca  mov     cs:qword_1800848A8, rax
0x180018fd1  mov     cs:dword_1800848B0, 60000h
0x180018fdb  lea     rax, aCpconnect; "CPConnect"
0x180018fe2  mov     cs:qword_1800848B8, rax
0x180018fe9  mov     cs:dword_1800848C0, 60001h
0x180018ff3  lea     rax, aOobeconnect; "OOBEConnect"
0x180018ffa  mov     cs:qword_1800848C8, rax
0x180019001  mov     cs:dword_1800848D0, 60003h
0x18001900b  lea     rax, aOobeupgradecon; "OOBEUpgradeConnect"
0x180019012  mov     cs:qword_1800848D8, rax
0x180019019  mov     cs:dword_1800848E0, 60004h
0x180019023  lea     rax, aCompleteaccoun_1; "CompleteAccountConnect"
0x18001902a  mov     cs:qword_1800848E8, rax
0x180019031  mov     cs:dword_1800848F0, 60005h
0x18001903b  lea     rax, aNthuserconnect; "NthUserConnect"
0x180019042  mov     cs:qword_1800848F8, rax
0x180019049  lea     rcx, dword_18008535C
0x180019050  call    _Init_thread_footer
0x180019055  lea     rcx, aCwindowslivepr_20; "CWindowsLiveProvider::GetUrlInternal"
0x18001905c  mov     [rbp+47h+var_88], rcx
0x180019060  lea     rax, [rbp+47h+arg_8]
0x180019064  mov     [rbp+47h+var_80], rax
0x180019068  mov     [rbp+47h+var_78], r14
0x18001906c  mov     [rbp+47h+var_70], r14
0x180019070  xor     r9d, r9d; unsigned int
0x180019073  mov     r8d, 8BDh; char *
0x180019079  mov     rdx, rcx; char *
0x18001907c  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180019083  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x180019088  nop
0x180019089  lea     r9, [rsp+130h+var_F8+4]
0x18001908e  lea     r8, [rbp+47h+arg_10]
0x180019092  lea     rdx, [rbp+47h+arg_8]
0x180019096  lea     rcx, [rbp+47h+var_48]
0x18001909a  call    _lambda_934676d547081d7307c52d658d925334____lambda_934676d547081d7307c52d658d925334_
0x18001909f  mov     rdx, rax
0x1800190a2  lea     rcx, [rbp+47h+var_68]
0x1800190a6  call    wil__scope_exit__lambda_934676d547081d7307c52d658d925334___
0x1800190ab  nop
0x1800190ac  mov     rax, [rdi]
0x1800190af  mov     rcx, rdi
0x1800190b2  mov     rax, [rax+20h]
0x1800190b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190bb  mov     rsi, rax
0x1800190be  mov     rax, [rdi]
0x1800190c1  mov     rcx, rdi
0x1800190c4  mov     rax, [rax+8]
0x1800190c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190cd  mov     rdx, rax
0x1800190d0  mov     rcx, [rax]
0x1800190d3  mov     rax, [rcx+18h]
0x1800190d7  mov     rcx, rdx
0x1800190da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190df  mov     r12, rax
0x1800190e2  mov     r8, [rdi]
0x1800190e5  mov     rcx, rdi
0x1800190e8  mov     rax, [r8+38h]
0x1800190ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190f1  mov     r13, rax
0x1800190f4  mov     r15, [rbp+47h+arg_28]
0x1800190f8  test    r15, r15
0x1800190fb  jnz     short loc_180019127
0x1800190fd  lea     r9, aUrlIsNull; "Url is null."
0x180019104  mov     r8d, 8D7h; unsigned int
0x18001910a  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180019111  mov     ecx, 2; unsigned __int8
0x180019116  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18001911b  mov     [rbp+47h+arg_8], 80070057h
0x180019122  jmp     loc_1800195D8
0x180019127  mov     r14, [rbp+47h+pvarg]
0x18001912b  test    r14, r14
0x18001912e  jnz     short loc_18001913F
0x180019130  lea     r9, aPostdataIsNull; "PostData is null."
0x180019137  mov     r8d, 8DEh
0x18001913d  jmp     short loc_18001910A
0x18001913f  mov     qword ptr [r15], 0
0x180019146  mov     rcx, r14; pvarg
0x180019149  call    cs:__imp_VariantClear
0x18001914f  lea     r8, aOutofboxexperi; "OutOfBoxExperience"
0x180019156  mov     rdx, rbx; struct IBindCtx *
0x180019159  call    ?BindCtxContainsObject@CWindowsLiveProvider@@AEAAHPEAUIBindCtx@@PEBG@Z; CWindowsLiveProvider::BindCtxContainsObject(IBindCtx *,ushort const *)
0x18001915e  test    eax, eax
0x180019160  jz      short loc_18001916F
0x180019162  mov     edx, [rbp+47h+arg_10]
0x180019165  mov     ecx, edx
0x180019167  shl     ecx, 10h
0x18001916a  or      ecx, 1
0x18001916d  jmp     short loc_1800191ED
0x18001916f  lea     r8, aModernsettings; "ModernSettingsAddUser"
0x180019176  mov     rdx, rbx; struct IBindCtx *
0x180019179  call    ?BindCtxContainsObject@CWindowsLiveProvider@@AEAAHPEAUIBindCtx@@PEBG@Z; CWindowsLiveProvider::BindCtxContainsObject(IBindCtx *,ushort const *)
0x18001917e  test    eax, eax
0x180019180  jz      short loc_18001918F
0x180019182  mov     edx, [rbp+47h+arg_10]
0x180019185  mov     ecx, edx
0x180019187  shl     ecx, 10h
0x18001918a  or      ecx, 2
0x18001918d  jmp     short loc_1800191ED
0x18001918f  lea     r8, aOutofboxupgrad; "OutOfBoxUpgradeExperience"
0x180019196  mov     rdx, rbx; struct IBindCtx *
0x180019199  call    ?BindCtxContainsObject@CWindowsLiveProvider@@AEAAHPEAUIBindCtx@@PEBG@Z; CWindowsLiveProvider::BindCtxContainsObject(IBindCtx *,ushort const *)
0x18001919e  test    eax, eax
0x1800191a0  jz      short loc_1800191AF
0x1800191a2  mov     edx, [rbp+47h+arg_10]
0x1800191a5  mov     ecx, edx
0x1800191a7  shl     ecx, 10h
0x1800191aa  or      ecx, 3
0x1800191ad  jmp     short loc_1800191ED
0x1800191af  lea     r8, aCompleteaccoun; "CompleteAccount"
0x1800191b6  mov     rdx, rbx; struct IBindCtx *
0x1800191b9  call    ?BindCtxContainsObject@CWindowsLiveProvider@@AEAAHPEAUIBindCtx@@PEBG@Z; CWindowsLiveProvider::BindCtxContainsObject(IBindCtx *,ushort const *)
0x1800191be  test    eax, eax
0x1800191c0  jz      short loc_1800191CF
0x1800191c2  mov     edx, [rbp+47h+arg_10]
0x1800191c5  mov     ecx, edx
0x1800191c7  shl     ecx, 10h
0x1800191ca  or      ecx, 4
0x1800191cd  jmp     short loc_1800191ED
0x1800191cf  lea     r8, aNthuserfirstau; "NthUserFirstAuth"
0x1800191d6  mov     rdx, rbx; struct IBindCtx *
0x1800191d9  call    ?BindCtxContainsObject@CWindowsLiveProvider@@AEAAHPEAUIBindCtx@@PEBG@Z; CWindowsLiveProvider::BindCtxContainsObject(IBindCtx *,ushort const *)
0x1800191de  mov     edx, [rbp+47h+arg_10]
0x1800191e1  mov     ecx, edx
0x1800191e3  shl     ecx, 10h
0x1800191e6  test    eax, eax
0x1800191e8  jz      short loc_1800191ED
0x1800191ea  or      ecx, 5
0x1800191ed  mov     dword ptr [rsp+130h+var_F8+4], ecx
0x1800191f1  xor     r8d, r8d
0x1800191f4  lea     rdi, qword_180084780
0x1800191fb  mov     rax, r8
0x1800191fe  add     rax, rax
0x180019201  cmp     [rdi+rax*8], ecx
0x180019204  jz      short loc_180019238
0x180019206  inc     r8
0x180019209  cmp     r8, 18h
0x18001920d  jb      short loc_1800191FB
0x18001920f  jnz     short loc_180019238
0x180019211  mov     dword ptr [rsp+130h+var_110], ecx
0x180019215  lea     r9, aInvalidCombina; "Invalid combination of urlID and flow I"...
0x18001921c  mov     r8d, 90Fh; unsigned int
0x180019222  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180019229  mov     ecx, 2; unsigned __int8
0x18001922e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180019233  jmp     loc_18001911B
0x180019238  add     r8, r8
0x18001923b  mov     rdi, [rdi+r8*8+8]
0x180019240  mov     dword ptr [rsp+130h+var_F8], 0
0x180019248  cmp     edx, 2
0x18001924b  jnz     short loc_1800192AD
0x18001924d  mov     rax, [rsi]
0x180019250  lea     r8, [rsp+130h+var_F8]
0x180019255  mov     edx, 14h
0x18001925a  mov     rcx, rsi
0x18001925d  mov     rax, [rax+60h]
0x180019261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019266  mov     [rbp+47h+arg_8], eax
0x180019269  test    eax, eax
0x18001926b  jns     short loc_18001929A
0x18001926d  lea     rcx, aHrPliveidntser; "hr = pLiveIdNtService->WLIDCGetConfigDW"...
0x180019274  mov     r8d, 918h; unsigned int
0x18001927a  mov     [rsp+130h+var_110], rcx; char *
0x18001927f  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180019286  mov     r9d, eax; int
0x180019289  lea     rdx, aCwindowslivepr_20; "CWindowsLiveProvider::GetUrlInternal"
0x180019290  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180019295  jmp     loc_1800195D8
0x18001929a  lea     rax, aCpchangepwdonl; "CPChangePwdOnline"
0x1800192a1  cmp     dword ptr [rsp+130h+var_F8], 0
0x1800192a6  cmovz   rax, rdi
0x1800192aa  mov     rdi, rax
0x1800192ad  mov     rax, [rsi]
0x1800192b0  lea     r8, [rsp+130h+var_D0]
0x1800192b5  mov     rdx, rdi
0x1800192b8  mov     rcx, rsi
0x1800192bb  mov     rax, [rax+70h]
0x1800192bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800192c4  mov     [rbp+47h+arg_8], eax
0x1800192c7  test    eax, eax
0x1800192c9  js      loc_1800195D8
0x1800192cf  mov     rdx, [rsp+130h+var_D0]
0x1800192d4  lea     rcx, [rsp+130h+var_100]
0x1800192d9  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x1800192de  mov     rax, [rsp+130h+var_100]
0x1800192e3  cmp     dword ptr [rax-10h], 0
0x1800192e7  jnz     short loc_18001931D
0x1800192e9  mov     eax, 80070490h
0x1800192ee  mov     [rbp+47h+arg_8], eax
0x1800192f1  mov     dword ptr [rsp+130h+var_108], eax
0x1800192f5  mov     [rsp+130h+var_110], rdi
0x1800192fa  lea     r9, aWlidcgetservic_0; "WLIDCGetServiceConfig returned an empty"...
0x180019301  mov     r8d, 933h; unsigned int
0x180019307  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18001930e  mov     ecx, 2; unsigned __int8
0x180019313  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180019318  jmp     loc_1800195D8
0x18001931d  lea     rcx, [rbp+47h+var_C0]; this
  ... truncated ...
```
