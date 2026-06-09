# CPPCRLRequest::GetPassportHeader(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &)

- ea: `0x18005ddb0`
- end: `0x18005ed53`
- name: `?GetPassportHeader@CPPCRLRequest@@IEAAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@@Z`
- size: `4003`
- prototype: ``
- caller_count: `2`
- callee_count: `64`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800cb9e0`
- `0x180100fd4`

## callees

- `0x1800076b4`
- `0x180007da0`
- `0x18000a354`
- `0x18000ae44`
- `0x18000c050`
- `0x18000d89c`
- `0x18000ed04`
- `0x18000fd04`
- `0x180013fb4`
- `0x1800151c4`
- `0x1800151f8`
- `0x180015fdc`
- `0x1800160a8`
- `0x180016500`
- `0x1800167b8`
- `0x180016f3c`
- `0x1800173a0`
- `0x180017410`
- `0x180017830`
- `0x1800179c0`
- `0x180017af0`
- `0x180018f80`
- `0x1800191c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001f968`
- `0x1800268d0`
- `0x180026bb4`
- `0x180029d54`
- `0x18002a074`
- `0x18002b2bc`
- `0x18002c77c`
- `0x18002f4b0`
- `0x180030e08`
- `0x180030f6c`
- `0x180031800`
- `0x180035b8c`
- `0x180038a80`
- `0x180039c38`
- `0x180042468`
- `0x180043344`
- `0x180046ecc`
- `0x180047b5c`
- `0x180053e64`
- `0x18005ddb0`
- `0x180067188`
- `0x180067218`
- `0x180072508`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e7ed`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18005e7ed`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005e703`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18005e703`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18005e9cc`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18005e9cc`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18005e67d`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18005e67d`
- `ext-ms-win-msa-user-l1-1-1!MsaUser_GetDeviceTelemetryInformation` at `0x18005e3fb`
- `ext-ms-win-msa-user-l1-1-1!MsaUser_GetDeviceTelemetryInformation` at `0x18005e3fb`
- `ext-ms-win-core-game-streaming-l1-1-0!IsGameStreamingServer` at `0x18005e215`
- `ext-ms-win-core-game-streaming-l1-1-0!IsGameStreamingServer` at `0x18005e215`

## string_xrefs

- `0x18005de4d`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18005e843`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\rst.cpp`
- `0x18005eb4c`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\singleidentity.cpp`
- `0x18005de9d`: `<ps:AuthInfo xmlns:ps="http://schemas.microsoft.com/Passport/SoapServices/PPCRL" Id="PPAuthInfo">`
- `0x18005e311`: `Configured InlineUX is invalid: '%hs'`
- `0x18005e58d`: `AppsReadAccess`
- `0x18005e600`: `AppsReadAccess`
- `0x18005e7ff`: `PackageSID`
- `0x18005e806`: `ClientAppURI`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
__int64 __fastcall CPPCRLRequest::GetPassportHeader(__int64 a1, __int64 a2)
{
  char v4; // r15
  int v5; // r9d
  const char *v6; // rax
  unsigned int v7; // r8d
  char v8; // bl
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 *v13; // rcx
  _QWORD *Appid; // rax
  __int64 v15; // rcx
  __int64 BinaryVersion; // rax
  MsaUserExtImpl *v17; // rcx
  char **v18; // r8
  __int64 v19; // rdx
  int v20; // edi
  const WCHAR *v21; // rbx
  int v22; // edi
  __int64 v23; // rbx
  unsigned __int64 i; // rbx
  const char *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rbx
  _QWORD *CurrentUserKey; // rax
  LPCWCH *v30; // rax
  char v31; // bl
  __int64 v32; // rdx
  _QWORD *v33; // rax
  int v34; // ebx
  const char *v35; // rdi
  int v36; // eax
  const char *v37; // rcx
  unsigned int v38; // r8d
  __int64 *v39; // rcx
  __int64 v40; // rax
  unsigned int UserDefaultUILanguage; // ebx
  __int64 v42; // rbx
  int v43; // ebx
  int v44; // eax
  __int64 v45; // rax
  int v46; // eax
  int SystemHardwareID; // eax
  int v48; // ebx
  unsigned int v49; // ebx
  const unsigned __int16 *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea[2]; // [rsp+20h] [rbp-E0h]
  int InlineUxParameterValue; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v54; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v55; // [rsp+40h] [rbp-C0h] BYREF
  int v56[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v57; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v58; // [rsp+58h] [rbp-A8h] BYREF
  char *v59; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+68h] [rbp-98h]
  __int64 v61; // [rsp+70h] [rbp-90h]
  LPCWCH lpString2; // [rsp+78h] [rbp-88h] BYREF
  __int64 v63; // [rsp+80h] [rbp-80h]
  __int64 v64; // [rsp+88h] [rbp-78h]
  int v65; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h] BYREF
  int v68; // [rsp+A8h] [rbp-58h]
  __int64 v69; // [rsp+B0h] [rbp-50h]
  __int64 v70; // [rsp+B8h] [rbp-48h] BYREF
  int v71; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v72; // [rsp+C8h] [rbp-38h]
  int v73; // [rsp+D0h] [rbp-30h]
  _QWORD v74[5]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v75[64]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v76[168]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v77[56]; // [rsp+1E8h] [rbp+E8h] BYREF
  _BYTE v78[140]; // [rsp+220h] [rbp+120h] BYREF
  unsigned int v79; // [rsp+2ACh] [rbp+1ACh]
  void *Block; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v81[136]; // [rsp+428h] [rbp+328h] BYREF
  void *v82; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v83[136]; // [rsp+4B8h] [rbp+3B8h] BYREF

  v4 = 0;
  v56[0] = 0;
  InlineUxParameterValue = 0;
  v72 = 0;
  v71 = 0;
  v73 = 0;
  v70 = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 24) + 24LL))(*(_QWORD *)(a1 + 24), &v66);
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v76);
  v74[0] = "CPPCRLRequest::GetPassportHeader";
  v74[1] = &InlineUxParameterValue;
  v74[2] = 0;
  v74[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
    "CPPCRLRequest::GetPassportHeader",
    (const char *)0x17A,
    0,
    bIgnoreCase);
  if ( !*(_QWORD *)(a1 + 24) )
  {
    v5 = -2147418113;
    v6 = "m_pIdentity != nullptr";
    v7 = 380;
LABEL_3:
    InlineUxParameterValue = v5;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      "CPPCRLRequest::GetPassportHeader",
      v7,
      v5,
      v6);
    goto LABEL_117;
  }
  ATL::CSimpleStringT<char,0>::PrepareWrite(a2, 1000);
  ATL::CSimpleStringT<char,0>::SetString(
    a2,
    "<ps:AuthInfo xmlns:ps=\"http://schemas.microsoft.com/Passport/SoapServices/PPCRL\" Id=\"PPAuthInfo\">");
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaSsoMSACompliance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DmaSsoMSACompliance>::GetImpl'::`2'::impl) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v57,
      &qword_18013DE20);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v54,
      L"ModernTestHook_ApplySsoRestriction");
    v56[0] = 1;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v55,
      L"SOFTWARE\\Microsoft\\IdentityCRL");
    v56[0] = 3;
    if ( (int)Reg_QueryString(HKEY_LOCAL_MACHINE, (__int64)&v57) < 0 || (v8 = 1, !*(_DWORD *)(v57 - 16)) )
      v8 = 0;
    v56[0] = 1;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
    v4 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
    if ( v8 )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64 *)&v54,
        &qword_18013DE20);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        &v54,
        L"<%s>%s</%s>",
        L"ps:SSOFlags",
        v57,
        L"ps:SSOFlags");
      v9 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
             &v58,
             v54);
      ATL::CSimpleStringT<char,0>::Append(a2, v9);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
    }
    else
    {
      v58 = (unsigned __int64)&PolicyEvaluator::`vftable';
      RegionalPolicies::GetSsoPolicyHeader(&v59, &v58);
      if ( *((_DWORD *)v59 - 4) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64 *)&v54,
          &qword_18013DE20);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v54,
          L"<%s>%s</%s>",
          L"ps:SSOFlags",
          v59,
          L"ps:SSOFlags");
        v10 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                &v55,
                v54);
        ATL::CSimpleStringT<char,0>::Append(a2, v10);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
      }
      if ( *(_DWORD *)(v60 - 16) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64 *)&v54,
          &qword_18013DE20);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          &v54,
          L"<%s>%s</%s>",
          L"ps:SSOFlagsSubstatus",
          v60,
          L"ps:SSOFlagsSubstatus");
        v11 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
                &v55,
                v54);
        ATL::CSimpleStringT<char,0>::Append(a2, v11);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
      }
      RegionalPolicies::Headers::~Headers((RegionalPolicies::Headers *)&v59);
    }
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
  }
  ATL::CSimpleStringT<char,0>::Append(a2, "<ps:HostingApp>");
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 48LL))(*(_QWORD *)(a1 + 24)) == 1 )
  {
    (*(void (__fastcall **)(_QWORD, unsigned __int64 *))(**(_QWORD **)(a1 + 24) + 16LL))(*(_QWORD *)(a1 + 24), &v55);
    if ( *(_DWORD *)(v55 - 16) )
      CPPCRLBaseRequest::AppendEscapedXML(a2, v55);
    else
      ATL::CSimpleStringT<char,0>::Append(a2, "{00000000-0000-0000-0000-000000000000}");
    v13 = &v55;
  }
  else
  {
    Appid = (_QWORD *)CPassportClientLibrary::GetAppid(v12, &v58);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(a2, *Appid);
    v13 = &v58;
  }
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v13);
  ATL::CSimpleStringT<char,0>::Append(a2, "</ps:HostingApp>");
  ATL::CSimpleStringT<char,0>::Append(a2, "<ps:BinaryVersion>");
  CClientConfigDataCacheManager::theConfigDataManager();
  BinaryVersion = CClientConfigDataCacheManager::GetBinaryVersion(v15, &v58);
  ATL::CSimpleStringT<char,0>::Append(a2, BinaryVersion);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
  ATL::CSimpleStringT<char,0>::Append(a2, "</ps:BinaryVersion>");
  ATL::CSimpleStringT<char,0>::Append(a2, "<ps:UIVersion>1</ps:UIVersion>");
  if ( *(_BYTE *)(a1 + 176) == 1 )
    ATL::CSimpleStringT<char,0>::Append(a2, "<ps:IsWebFlow>1</ps:IsWebFlow>");
  if ( *(_BYTE *)(a1 + 177) == 1 )
  {
    ATL::CSimpleStringT<char,0>::Append(a2, "<ps:IsFRFS>1</ps:IsFRFS>");
    if ( *(_BYTE *)(a1 + 186) == 1 )
      ATL::CSimpleStringT<char,0>::Append(a2, "<ps:ShowSkipFRFS>1</ps:ShowSkipFRFS>");
  }
  if ( (unsigned __int8)IsIsGameStreamingServerPresent() && (unsigned int)IsGameStreamingServer() )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v55,
      L"RemoteSilent");
    ATL::CSimpleStringT<unsigned short,0>::operator=(a1 + 168, &v55);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      0x1D9u,
      L"InlineUX Override is: '%ls'",
      *(_QWORD *)(a1 + 168));
  }
  v19 = *(_QWORD *)(a1 + 168);
  if ( *(_DWORD *)(v19 - 16) )
  {
    if ( *(int *)(v19 - 16) > 50 )
    {
      v5 = -2147024809;
      v6 = "_inlineUXOverride.GetLength() <= INLINEUX_TYPE_MAXLENGTH";
      v7 = 479;
      goto LABEL_3;
    }
    Block = v81;
    ATL::CW2AEX<128>::Init(&Block, v19, 65001);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(
      a2,
      "<ps:InlineUX>%hs</ps:InlineUX>",
      (const char *)Block);
    if ( Block != v81 )
      free(Block);
  }
  else
  {
    v59 = 0;
    v61 = 0;
    v60 = 0;
    InlineUxParameterValue = MsaUserExtImpl::GetInlineUxParameterValue(v17, (unsigned int)&v59, v18);
    if ( InlineUxParameterValue >= 0 && v59 && *v59 )
    {
      v55 = 0;
      InlineUxParameterValue = StringCchLengthA(v59, 0x32u, &v55);
      if ( InlineUxParameterValue >= 0 && v55 )
      {
        ATL::CSimpleStringT<char,0>::Append(a2, "<ps:InlineUX>");
        ATL::CSimpleStringT<char,0>::Append(a2, v59);
        ATL::CSimpleStringT<char,0>::Append(a2, "</ps:InlineUX>");
      }
      else
      {
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
          0x1F9u,
          L"Configured InlineUX is invalid: '%hs'",
          v59);
      }
    }
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&v59);
  }
  CPPCRLBaseRequest::AppendDeviceType(a2);
  if ( (unsigned __int8)IsMsaUser_GetDeviceTelemetryInformationPresent() )
  {
    lpString2 = 0;
    v64 = 0;
    LODWORD(v63) = 0;
    v67 = 0;
    v69 = 0;
    v68 = 0;
    v55 = 0;
    v57 = 0;
    v54 = 0;
    InlineUxParameterValue = MsaUser_GetDeviceTelemetryInformation(0, &v54, &v55, &v57);
    v20 = v54;
    v21 = (const WCHAR *)v55;
    AutoArray<char * *,LocalAllocArrayFunctor<char *>,DummyContext>::Clear(&lpString2);
    lpString2 = v21;
    LODWORD(v63) = v20;
    v22 = v54;
    v23 = v57;
    AutoArray<char * *,LocalAllocArrayFunctor<char *>,DummyContext>::Clear(&v67);
    v67 = v23;
    v68 = v22;
    if ( InlineUxParameterValue >= 0 && v54 )
    {
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v56);
      for ( i = 0; i < v54; ++i )
      {
        v25 = *(const char **)(v57 + 8 * i);
        if ( v25 )
        {
          v58 = 0;
          InlineUxParameterValue = StringCchLengthA(v25, 0x32u, &v58);
          if ( InlineUxParameterValue >= 0 )
          {
            if ( v58 )
            {
              if ( *(_DWORD *)(*(_QWORD *)v56 - 16LL) )
                ATL::CSimpleStringT<char,0>::Append(v56, "&");
              ATL::CSimpleStringT<char,0>::Append(v56, *(const char **)(v55 + 8 * i));
              LOBYTE(v26) = 61;
              ATL::CSimpleStringT<char,0>::AppendChar(v56, v26);
              v27 = WlidsvcUtil::UrlEscapeStr(&v59, *(_QWORD *)(v57 + 8 * i));
              ATL::CSimpleStringT<char,0>::Append(v56, v27);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
            }
          }
        }
      }
      v28 = *(_QWORD *)v56;
      if ( *(_DWORD *)(*(_QWORD *)v56 - 16LL) )
      {
        ATL::CSimpleStringT<char,0>::Append(a2, "<ps:Telemetry>");
        CPPCRLBaseRequest::AppendEscapedXML(a2, v28);
        ATL::CSimpleStringT<char,0>::Append(a2, "</ps:Telemetry>");
      }
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v56);
    }
    else if ( InlineUxParameterValue == -2147467263 )
    {
      InlineUxParameterValue = 0;
    }
    AutoArray<char * *,LocalAllocArrayFunctor<char *>,DummyContext>::Clear(&v67);
    AutoArray<char * *,LocalAllocArrayFunctor<char *>,DummyContext>::Clear(&lpString2);
  }
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 48LL))(*(_QWORD *)(a1 + 24)) == 1 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v55,
      L"AppsReadAccess");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v58,
      L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture");
    CurrentUserKey = GetCurrentUserKey(&lpString2);
    v56[0] = 0;
    Reg_QueryDWORD(*CurrentUserKey, &v58, &v55, v56);
    ATL::CRegKey::Close((ATL::CRegKey *)&lpString2);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55);
    if ( v56[0] == 1
      || (ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v55,
            L"AppsReadAccess"),
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&v58,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture"),
          v56[0] = 0,
          Reg_QueryDWORD(-2147483646, &v58, &v55, v56),
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58),
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v55),
          v56[0] == 1) )
    {
      ATL::CSimpleStringT<char,0>::Append(a2, "<ps:ConsentFlags>1</ps:ConsentFlags>");
    }
  }
  v65 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v65, 0);
  if ( v65 != 5 && v65 != 12 && v65 != 11 )
  {
    v56[0] = 0;
    ExecutionContextLite::ExecutionContextLite((ExecutionContextLite *)v75);
    lpString2 = 0;
    v64 = 0;
    v63 = 0;
    SystemStoreLite::IsConnected((struct IExecutionContextLite *)v75, v56, (unsigned __int16 **)&lpString2);
    if ( !v56[0]
      || (v30 = (LPCWCH *)(*(__int64 (__fastcall **)(_QWORD, char **))(**(_QWORD **)(a1 + 24) + 32LL))(
                            *(_QWORD *)(a1 + 24),
                            &v59),
          v4 = 4,
          v31 = 1,
          CompareStringOrdinal(*v30, -1, lpString2, -1, 1) != 2) )
    {
      v31 = 0;
    }
    if ( (v4 & 4) != 0 )
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
    if ( v31 )
      ATL::CSimpleStringT<char,0>::Append(a2, "<ps:IsConnected>1</ps:IsConnected>");
    Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&lpString2);
  }
  v56[0] = 0;
  WlidsvcUtil::IsCallerInAdminGroup(v56);
  if ( v56[0] )
    ATL::CSimpleStringT<char,0>::Append(a2, "<ps:IsAdmin>1</ps:IsAdmin>");
  v32 = *(_QWORD *)(a1 + 144);
  if ( *(_DWORD *)(v32 - 16) )
  {
    v82 = v83;
    ATL::CW2AEX<128>::Init(&v82, v32, 65001);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(
      a2,
      "<ps:InlineFT>%s</ps:InlineFT>",
      (const char *)v82);
    if ( v82 != v83 )
      free(v82);
  }
  if ( *(_DWORD *)(v66 - 16) )
  {
    v33 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Left(
                      &v66,
                      &v59,
                      11);
    v34 = _o__wcsicmp(*v33, L"xbox-app://");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v59);
    v35 = "ClientAppURI";
    if ( v34 )
      v35 = "PackageSID";
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(a2, "<ps:%s>", v35);
    CPPCRLBaseRequest::AppendEscapedXML(a2, v66);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(a2, "</ps:%s>", v35);
  }
  if ( *(_BYTE *)(a1 + 96) )
  {
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      0x28Bu,
      L"Sending identity cookies.");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
    v36 = CSingleIdentity::SerializeCookies(*(_QWORD *)(a1 + 24), &v54);
    InlineUxParameterValue = v36;
    if ( v36 < 0 )
    {
      v37 = "hr = m_pIdentity->SerializeCookies(strSerializedCookies)";
      v38 = 655;
LABEL_87:
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::GetPassportHeader",
        v38,
        v36,
        v37);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
      v39 = (__int64 *)&v54;
LABEL_88:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v39);
      goto LABEL_117;
    }
    v40 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
            &v59,
            &v54);
    v36 = PassportEncode::Base64Encode(v40, &v57);
    InlineUxParameterValue = v36;
    if ( v36 < 0 )
    {
      v37 = "hr = PassportEncode::Base64Encode(strSerializedCookies, strEncodedCookies)";
      v38 = 656;
      goto LABEL_87;
    }
    ATL::CSimpleStringT<char,0>::Append(a2, "<ps:Cookies>");
    ATL::CSimpleStringT<char,0>::Append(a2, &v57);
    ATL::CSimpleStringT<char,0>::Append(a2, "</ps:Cookies>");
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
  }
  if ( *(_BYTE *)(a1 + 97) )
  {
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
    UserDefaultUILanguage = 1033;
    if ( g_pPPCRL )
    {
      CONFIGDATA::CONFIGDATA((CONFIGDATA *)v78);
      CSessionAppSettingsMap::GetAppSettings((LPCRITICAL_SECTION)g_pPPCRL + 41, (struct CONFIGDATA *)v78);
      UserDefaultUILanguage = v79;
      if ( !v79 )
      {
        v55 = 0;
        CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v55, 0);
        UserDefaultUILanguage = GetUserDefaultUILanguage();
        CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v55);
      }
      CONFIGDATA::~CONFIGDATA((CONFIGDATA *)v78);
    }
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
      0x2B1u,
      L"Sending request parameters.");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v54,
      L"%-d",
      UserDefaultUILanguage);
    v42 = *(_QWORD *)(a1 + 24);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64 *)&v58,
      L"lc");
    v43 = CSingleIdentity::SetRequestParam(v42, &v58, &v54);
    InlineUxParameterValue = v43;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v58);
    if ( v43 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::GetPassportHeader",
        0x2B7u,
        v43,
        "hr = m_pIdentity->SetRequestParam(L\"lc\",strwLC)");
LABEL_99:
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v56);
      v39 = &v57;
      goto LABEL_88;
    }
    v44 = CSingleIdentity::SerializeRequestParams(*(_QWORD *)(a1 + 24), &v57);
    InlineUxParameterValue = v44;
    if ( v44 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::GetPassportHeader",
        0x2B9u,
        v44,
        "hr = m_pIdentity->SerializeRequestParams(strSerializedParams)");
      goto LABEL_99;
    }
    v45 = ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
            &v59,
            &v57);
    v46 = PassportEncode::Base64Encode(v45, v56);
    InlineUxParameterValue = v46;
    if ( v46 < 0 )
    {
      Telemetry::IfFailExit(
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        "CPPCRLRequest::GetPassportHeader",
        0x2BBu,
        v46,
        "hr = PassportEncode::Base64Encode(strSerializedParams, strEncodedParams)");
      goto LABEL_99;
    }
    ATL::CSimpleStringT<char,0>::Append(a2, "<ps:RequestParams>");
    ATL::CSimpleStringT<char,0>::Append(a2, v56);
    ATL::CSimpleStringT<char,0>::Append(a2, "</ps:RequestParams>");
    ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(*(_QWORD *)(a1 + 24) + 344LL);
    TracePrintW(
      5u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\singleidentity.cpp",
      0x3A8u,
      L"Clearing request params collection.");
    InlineUxParameterValue = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v54);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v56);
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v57);
  }
  lpString2 = 0;
  v64 = 0;
  v63 = 0;
  InlineUxParameterValue = GetWindowsDeviceId((struct ITpmBaseServicesFunctions *)v77, (unsigned __int16 **)&lpString2);
  if ( InlineUxParameterValue >= 0 )
  {
    ATL::CSimpleStringT<char,0>::Append(a2, "<ps:WindowsClientString>");
    CPPCRLBaseRequest::AppendEscapedXML(a2, lpString2);
    ATL::CSimpleStringT<char,0>::Append(a2, "</ps:WindowsClientString>");
  }
  InlineUxParameterValue = 0;
  Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>::~Auto<_TOKEN_USER *,LocalAllocFunctor<_TOKEN_USER *>,DummyContext>((__int64)&lpString2);
  if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 80LL))(*(_QWORD *)(a1 + 24)) == 1
    || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 80LL))(*(_QWORD *)(a1 + 24)) == 2
    || (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 80LL))(*(_QWORD *)(a1 + 24)) == 3 )
  {
    v55 = 0;
    SystemHardwareID = DeviceIdHelpers::GetSystemHardwareID(v76, 16, &v55);
    if ( SystemHardwareID < 0 )
    {
      bIgnoreCasea[0] = SystemHardwareID;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
        0x2EDu,
        L"DeviceIdHelpers::GetSystemHardwareID (0x%x).",
        *(_QWORD *)bIgnoreCasea);
    }
    else
    {
      v58 = 0;
      if ( (*(int (__fastcall **)(unsigned __int64, __int64, unsigned __int64 *))(*(_QWORD *)v55 + 88LL))(v55, 1, &v58) >= 0 )
      {
        v48 = (*(__int64 (__fastcall **)(unsigned __int64))(*(_QWORD *)v58 + 248LL))(v58);
        bIgnoreCasea[0] = v48;
        TracePrintW(
          5u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\rst.cpp",
          0x2E4u,
          L"LicenseSignatureKeyVersion %d",
          *(_QWORD *)bIgnoreCasea);
        if ( v48 )
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::AppendFormat(
            a2,
            "<ps:LicenseSignatureKeyVersion>%d</ps:LicenseSignatureKeyVersion>",
            v48);
      }
    }
    CAutoRefPtr<CSingleIdentity>::Deinit(&v55);
  }
  ATL::CSimpleStringT<char,0>::Append(a2, "<ps:ClientCapabilities>1</ps:ClientCapabilities>");
  ATL::CSimpleStringT<char,0>::Append(a2, "</ps:AuthInfo>");
LABEL_117:
  v49 = InlineUxParameterValue;
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v74);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v76);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v66);
  ATL::CCryptRandomKey::~CCryptRandomKey((ATL::CCryptRandomKey *)&v70);
  CBytePtr::Empty((CBytePtr *)&v71);
  return v49;
}

```

## disassembly

```asm
0x18005ddb0  mov     [rsp-8+arg_10], rbx
0x18005ddb5  push    rbp
0x18005ddb6  push    rsi
0x18005ddb7  push    rdi
0x18005ddb8  push    r12
0x18005ddba  push    r13
0x18005ddbc  push    r14
0x18005ddbe  push    r15
0x18005ddc0  lea     rbp, [rsp-450h]
0x18005ddc8  sub     rsp, 550h
0x18005ddcf  mov     rax, cs:__security_cookie
0x18005ddd6  xor     rax, rsp
0x18005ddd9  mov     [rbp+480h+var_40], rax
0x18005dde0  mov     rsi, rdx
0x18005dde3  mov     r14, rcx
0x18005dde6  xor     r12d, r12d
0x18005dde9  mov     r15d, r12d
0x18005ddec  mov     [rsp+580h+var_538], r12d
0x18005ddf1  mov     [rsp+580h+var_550], r12d
0x18005ddf6  mov     [rbp+480h+var_4B8], r12
0x18005ddfa  mov     [rbp+480h+var_4C0], r12d
0x18005ddfe  mov     [rbp+480h+var_4B0], r12d
0x18005de02  mov     [rbp+480h+var_4C8], r12
0x18005de06  mov     rcx, [rcx+18h]
0x18005de0a  mov     rax, [rcx]
0x18005de0d  lea     rdx, [rbp+480h+var_4E8]
0x18005de11  mov     rax, [rax+18h]
0x18005de15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005de1a  nop
0x18005de1b  lea     rcx, [rbp+480h+var_440]; this
0x18005de1f  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x18005de24  nop
0x18005de25  lea     rbx, aCppcrlrequestG_1; "CPPCRLRequest::GetPassportHeader"
0x18005de2c  mov     [rbp+480h+var_4A8], rbx
0x18005de30  lea     rax, [rsp+580h+var_550]
0x18005de35  mov     [rbp+480h+var_4A0], rax
0x18005de39  mov     [rbp+480h+var_498], r12
0x18005de3d  mov     [rbp+480h+var_490], r12
0x18005de41  xor     r9d, r9d; unsigned int
0x18005de44  mov     r8d, 17Ah; char *
0x18005de4a  mov     rdx, rbx; char *
0x18005de4d  lea     rdi, aOnecoreuapDsEx_94; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18005de54  mov     rcx, rdi; this
0x18005de57  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18005de5c  nop
0x18005de5d  cmp     [r14+18h], r12
0x18005de61  jnz     short loc_18005DE90
0x18005de63  mov     r9d, 8000FFFFh; int
0x18005de69  lea     rax, aMPidentityNull; "m_pIdentity != nullptr"
0x18005de70  mov     r8d, 17Ch; unsigned int
0x18005de76  mov     rdx, rbx; char *
0x18005de79  mov     qword ptr [rsp+580h+bIgnoreCase], rax; char *
0x18005de7e  mov     [rsp+580h+var_550], r9d
0x18005de83  mov     rcx, rdi; char *
0x18005de86  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005de8b  jmp     loc_18005ECF2
0x18005de90  mov     edx, 3E8h
0x18005de95  mov     rcx, rsi
0x18005de98  call    ?PrepareWrite@?$CSimpleStringT@D$0A@@ATL@@AEAAPEADH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite(int)
0x18005de9d  lea     rdx, aPsAuthinfoXmln; "<ps:AuthInfo xmlns:ps=\"http://schemas."...
0x18005dea4  mov     rcx, rsi
0x18005dea7  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x18005deac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DmaSsoMSACompliance@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DmaSsoMSACompliance@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaSsoMSACompliance> `wil::Feature<__WilFeatureTraits_Feature_DmaSsoMSACompliance>::GetImpl(void)'::`2'::impl
0x18005deb3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DmaSsoMSACompliance@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DmaSsoMSACompliance>::__private_IsEnabled(void)
0x18005deb8  mov     r13d, 1
0x18005debe  test    al, al
0x18005dec0  jz      loc_18005E0DE
0x18005dec6  lea     rdx, qword_18013DE20
0x18005decd  lea     rcx, [rsp+580h+var_530]
0x18005ded2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005ded7  nop
0x18005ded8  lea     rdx, aModerntesthook_0; "ModernTestHook_ApplySsoRestriction"
0x18005dedf  lea     rcx, [rsp+580h+var_548]
0x18005dee4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005dee9  nop
0x18005deea  mov     [rsp+580h+var_538], r13d
0x18005deef  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\IdentityCRL"
0x18005def6  lea     rcx, [rsp+580h+var_540]
0x18005defb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005df00  nop
0x18005df01  mov     [rsp+580h+var_538], 3
0x18005df09  lea     rax, [rsp+580h+var_530]
0x18005df0e  mov     qword ptr [rsp+580h+bIgnoreCase], rax; __int64
0x18005df13  mov     r9d, r13d
0x18005df16  lea     r8, [rsp+580h+var_548]
0x18005df1b  lea     rdx, [rsp+580h+var_540]
0x18005df20  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18005df27  call    ?Reg_QueryString@@YAJPEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1KAEAV23@@Z; Reg_QueryString(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18005df2c  test    eax, eax
0x18005df2e  js      short loc_18005DF3E
0x18005df30  mov     rax, [rsp+580h+var_530]
0x18005df35  cmp     [rax-10h], r12d
0x18005df39  mov     bl, r13b
0x18005df3c  jnz     short loc_18005DF41
0x18005df3e  mov     bl, r12b
0x18005df41  mov     [rsp+580h+var_538], r13d
0x18005df46  lea     rcx, [rsp+580h+var_540]
0x18005df4b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005df50  nop
0x18005df51  mov     r15d, r12d
0x18005df54  lea     rcx, [rsp+580h+var_548]
0x18005df59  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005df5e  test    bl, bl
0x18005df60  jz      short loc_18005DFCC
0x18005df62  lea     rdx, qword_18013DE20
0x18005df69  lea     rcx, [rsp+580h+var_548]
0x18005df6e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005df73  nop
0x18005df74  lea     r8, aPsSsoflags; "ps:SSOFlags"
0x18005df7b  mov     qword ptr [rsp+580h+bIgnoreCase], r8
0x18005df80  mov     r9, [rsp+580h+var_530]
0x18005df85  lea     rdx, aSSS; "<%s>%s</%s>"
0x18005df8c  lea     rcx, [rsp+580h+var_548]
0x18005df91  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18005df96  mov     rdx, [rsp+580h+var_548]
0x18005df9b  lea     rcx, [rsp+580h+var_528]
0x18005dfa0  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18005dfa5  nop
0x18005dfa6  mov     rdx, rax
0x18005dfa9  mov     rcx, rsi
0x18005dfac  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x18005dfb1  nop
0x18005dfb2  lea     rcx, [rsp+580h+var_528]
0x18005dfb7  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005dfbc  nop
0x18005dfbd  lea     rcx, [rsp+580h+var_548]
0x18005dfc2  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005dfc7  jmp     loc_18005E0D4
0x18005dfcc  lea     rax, ??_7PolicyEvaluator@@6B@; const PolicyEvaluator::`vftable'
0x18005dfd3  mov     [rsp+580h+var_528], rax
0x18005dfd8  lea     rdx, [rsp+580h+var_528]
0x18005dfdd  lea     rcx, [rsp+580h+var_520]
0x18005dfe2  call    ?GetSsoPolicyHeader@RegionalPolicies@@SA?AUHeaders@1@AEBVIPolicyEvaluator@@@Z; RegionalPolicies::GetSsoPolicyHeader(IPolicyEvaluator const &)
0x18005dfe7  nop
0x18005dfe8  mov     rax, [rsp+580h+var_520]
0x18005dfed  cmp     [rax-10h], r12d
0x18005dff1  jz      short loc_18005E058
0x18005dff3  lea     rdx, qword_18013DE20
0x18005dffa  lea     rcx, [rsp+580h+var_548]
0x18005dfff  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005e004  nop
0x18005e005  lea     r8, aPsSsoflags; "ps:SSOFlags"
0x18005e00c  mov     qword ptr [rsp+580h+bIgnoreCase], r8
0x18005e011  mov     r9, [rsp+580h+var_520]
0x18005e016  lea     rdx, aSSS; "<%s>%s</%s>"
0x18005e01d  lea     rcx, [rsp+580h+var_548]
0x18005e022  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18005e027  mov     rdx, [rsp+580h+var_548]
0x18005e02c  lea     rcx, [rsp+580h+var_540]
0x18005e031  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18005e036  nop
0x18005e037  mov     rdx, rax
0x18005e03a  mov     rcx, rsi
0x18005e03d  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x18005e042  nop
0x18005e043  lea     rcx, [rsp+580h+var_540]
0x18005e048  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e04d  nop
0x18005e04e  lea     rcx, [rsp+580h+var_548]
0x18005e053  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e058  mov     rax, [rsp+580h+var_518]
0x18005e05d  cmp     [rax-10h], r12d
0x18005e061  jz      short loc_18005E0C9
0x18005e063  lea     rdx, qword_18013DE20
0x18005e06a  lea     rcx, [rsp+580h+var_548]
0x18005e06f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005e074  nop
0x18005e075  lea     r8, aPsSsoflagssubs; "ps:SSOFlagsSubstatus"
0x18005e07c  mov     qword ptr [rsp+580h+bIgnoreCase], r8
0x18005e081  mov     r9, [rsp+580h+var_518]
0x18005e086  lea     rdx, aSSS; "<%s>%s</%s>"
0x18005e08d  lea     rcx, [rsp+580h+var_548]
0x18005e092  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18005e097  mov     rdx, [rsp+580h+var_548]
0x18005e09c  lea     rcx, [rsp+580h+var_540]
0x18005e0a1  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(ushort const *)
0x18005e0a6  nop
0x18005e0a7  mov     rdx, rax
0x18005e0aa  mov     rcx, rsi
0x18005e0ad  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x18005e0b2  nop
0x18005e0b3  lea     rcx, [rsp+580h+var_540]
0x18005e0b8  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e0bd  nop
0x18005e0be  lea     rcx, [rsp+580h+var_548]
0x18005e0c3  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e0c8  nop
0x18005e0c9  lea     rcx, [rsp+580h+var_520]; this
0x18005e0ce  call    ??1Headers@RegionalPolicies@@QEAA@XZ; RegionalPolicies::Headers::~Headers(void)
0x18005e0d3  nop
0x18005e0d4  lea     rcx, [rsp+580h+var_530]
0x18005e0d9  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e0de  lea     rdx, aPsHostingapp_0; "<ps:HostingApp>"
0x18005e0e5  mov     rcx, rsi
0x18005e0e8  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e0ed  mov     rcx, [r14+18h]
0x18005e0f1  mov     rax, [rcx]
0x18005e0f4  mov     rax, [rax+30h]
0x18005e0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e0fd  cmp     al, r13b
0x18005e100  jnz     short loc_18005E141
0x18005e102  mov     rcx, [r14+18h]
0x18005e106  mov     rax, [rcx]
0x18005e109  lea     rdx, [rsp+580h+var_540]
0x18005e10e  mov     rax, [rax+10h]
0x18005e112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e117  nop
0x18005e118  mov     rdx, [rsp+580h+var_540]
0x18005e11d  mov     rcx, rsi
0x18005e120  cmp     [rdx-10h], r12d
0x18005e124  jnz     short loc_18005E134
0x18005e126  lea     rdx, a00000000000000_0; "{00000000-0000-0000-0000-000000000000}"
0x18005e12d  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e132  jmp     short loc_18005E13A
0x18005e134  call    ?AppendEscapedXML@CPPCRLBaseRequest@@SAJAEAV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@PEBG@Z; CPPCRLBaseRequest::AppendEscapedXML(ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>> &,ushort const *)
0x18005e139  nop
0x18005e13a  lea     rcx, [rsp+580h+var_540]
0x18005e13f  jmp     short loc_18005E15D
0x18005e141  lea     rdx, [rsp+580h+var_528]
0x18005e146  call    ?GetAppid@CPassportClientLibrary@@QEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CPassportClientLibrary::GetAppid(void)
0x18005e14b  nop
0x18005e14c  mov     rdx, [rax]
0x18005e14f  mov     rcx, rsi
0x18005e152  call    ??Y?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator+=(ushort const *)
0x18005e157  nop
0x18005e158  lea     rcx, [rsp+580h+var_528]
0x18005e15d  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e162  lea     rdx, aPsHostingapp_1; "</ps:HostingApp>"
0x18005e169  mov     rcx, rsi
0x18005e16c  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e171  lea     rdx, aPsBinaryversio; "<ps:BinaryVersion>"
0x18005e178  mov     rcx, rsi
0x18005e17b  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e180  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x18005e185  lea     rdx, [rsp+580h+var_528]
0x18005e18a  call    ?GetBinaryVersion@CClientConfigDataCacheManager@@QEAA?AV?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@XZ; CClientConfigDataCacheManager::GetBinaryVersion(void)
0x18005e18f  nop
0x18005e190  mov     rdx, rax
0x18005e193  mov     rcx, rsi
0x18005e196  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXAEBV12@@Z; ATL::CSimpleStringT<char,0>::Append(ATL::CSimpleStringT<char,0> const &)
0x18005e19b  nop
0x18005e19c  lea     rcx, [rsp+580h+var_528]
0x18005e1a1  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e1a6  lea     rdx, aPsBinaryversio_0; "</ps:BinaryVersion>"
0x18005e1ad  mov     rcx, rsi
0x18005e1b0  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e1b5  lea     rdx, aPsUiversion1Ps; "<ps:UIVersion>1</ps:UIVersion>"
0x18005e1bc  mov     rcx, rsi
0x18005e1bf  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e1c4  cmp     [r14+0B0h], r13b
0x18005e1cb  jnz     short loc_18005E1DC
0x18005e1cd  lea     rdx, aPsIswebflow1Ps; "<ps:IsWebFlow>1</ps:IsWebFlow>"
0x18005e1d4  mov     rcx, rsi
0x18005e1d7  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e1dc  cmp     [r14+0B1h], r13b
0x18005e1e3  jnz     short loc_18005E20C
0x18005e1e5  lea     rdx, aPsIsfrfs1PsIsf; "<ps:IsFRFS>1</ps:IsFRFS>"
0x18005e1ec  mov     rcx, rsi
0x18005e1ef  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e1f4  cmp     [r14+0BAh], r13b
0x18005e1fb  jnz     short loc_18005E20C
0x18005e1fd  lea     rdx, aPsShowskipfrfs; "<ps:ShowSkipFRFS>1</ps:ShowSkipFRFS>"
0x18005e204  mov     rcx, rsi
0x18005e207  call    ?Append@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::Append(char const *)
0x18005e20c  call    IsIsGameStreamingServerPresent
0x18005e211  test    al, al
0x18005e213  jz      short loc_18005E272
0x18005e215  call    cs:__imp_IsGameStreamingServer
0x18005e21b  test    eax, eax
0x18005e21d  jz      short loc_18005E272
0x18005e21f  lea     rdx, aRemotesilent; "RemoteSilent"
0x18005e226  lea     rcx, [rsp+580h+var_540]
0x18005e22b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005e230  nop
0x18005e231  lea     rbx, [r14+0A8h]
0x18005e238  lea     rdx, [rsp+580h+var_540]
0x18005e23d  mov     rcx, rbx
0x18005e240  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18005e245  nop
0x18005e246  lea     rcx, [rsp+580h+var_540]
0x18005e24b  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005e250  mov     rax, [rbx]
0x18005e253  mov     qword ptr [rsp+580h+bIgnoreCase], rax
0x18005e258  lea     r9, aInlineuxOverri; "InlineUX Override is: '%ls'"
0x18005e25f  mov     r8d, 1D9h; unsigned int
0x18005e265  mov     rdx, rdi; char *
0x18005e268  mov     ecx, 5; unsigned __int8
0x18005e26d  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005e272  mov     rdx, [r14+0A8h]
0x18005e279  cmp     [rdx-10h], r12d
0x18005e27d  jnz     loc_18005E338
0x18005e283  mov     [rsp+580h+var_520], r12
0x18005e288  mov     [rsp+580h+var_510], r12
0x18005e28d  mov     [rsp+580h+var_518], r12
0x18005e292  lea     rdx, [rsp+580h+var_520]; unsigned int
0x18005e297  call    ?GetInlineUxParameterValue@MsaUserExtImpl@@YAJKPEAPEAD@Z; MsaUserExtImpl::GetInlineUxParameterValue(ulong,char * *)
0x18005e29c  mov     [rsp+580h+var_550], eax
0x18005e2a0  test    eax, eax
0x18005e2a2  js      loc_18005E32C
0x18005e2a8  mov     rcx, [rsp+580h+var_520]; char *
  ... truncated ...
```
