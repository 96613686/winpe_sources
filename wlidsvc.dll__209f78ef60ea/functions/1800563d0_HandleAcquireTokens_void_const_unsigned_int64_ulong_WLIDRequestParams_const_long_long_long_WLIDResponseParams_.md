# HandleAcquireTokens(void * const,unsigned __int64,ulong,_WLIDRequestParams * const,long *,long *,long *,_WLIDResponseParams * *,ushort const *,unsigned __int64,ushort const *,long *,ulong *)

- ea: `0x1800563d0`
- end: `0x180058c29`
- name: `?HandleAcquireTokens@@YAJQEAX_KKQEAU_WLIDRequestParams@@PEAJ33PEAPEAU_WLIDResponseParams@@PEBG_K53PEAK@Z`
- size: `10329`
- prototype: `__int64 __fastcall(void *const, unsigned __int64, unsigned int, struct _WLIDRequestParams *const, int *, int *, int *, struct _WLIDResponseParams **, const unsigned __int16 *, unsigned __int64, const unsigned __int16 *, int *, unsigned int *)`
- caller_count: `15`
- callee_count: `99`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180028f00`
- `0x18002a57c`
- `0x1800592ac`
- `0x18009132c`
- `0x180091e98`
- `0x180094b4c`
- `0x18009f490`
- `0x1800a0f28`
- `0x1800b037c`
- `0x1800b2090`
- `0x1800b7f6c`
- `0x1800b81e8`
- `0x1800b8484`
- `0x1800b9278`
- `0x1800bc9a0`

## callees

- `0x180001100`
- `0x1800057f8`
- `0x1800076b4`
- `0x18000860c`
- `0x18000baac`
- `0x18000bec0`
- `0x18000c050`
- `0x18000cfac`
- `0x18000ed04`
- `0x18000fd04`
- `0x180013448`
- `0x18001426c`
- `0x1800143a4`
- `0x1800151c4`
- `0x180015430`
- `0x180015860`
- `0x180015fdc`
- `0x180017af0`
- `0x180017bf0`
- `0x180018f80`
- `0x1800191c0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x18001cf20`
- `0x18001dfec`
- `0x18001f968`
- `0x180020970`
- `0x180020b10`
- `0x180026308`
- `0x18002795c`
- `0x180028cd4`
- `0x180029088`
- `0x180029d54`
- `0x18002a074`
- `0x18002c77c`
- `0x18002cf58`
- `0x18002d6dc`
- `0x18002d710`
- `0x18002df9c`
- `0x18002ecd0`
- `0x180036640`
- `0x1800367a8`
- `0x180037288`
- `0x18003a8fc`
- `0x18003b1e0`
- `0x18003c814`
- `0x1800419a4`
- `0x180041ee4`
- `0x180043344`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056fe5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057a5e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180057183`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180057183`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057860`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800578b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800578fb`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180057860`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800578b8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800578fb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800572d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800572d9`
- `USERENV!GetProfileType` at `0x180056fdb`
- `USERENV!GetProfileType` at `0x180056fdb`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800571d5`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18005797c`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x1800571d5`
- `api-ms-win-security-lsalookup-l1-1-2!LsaLookupUserAccountType` at `0x18005797c`
- `ext-ms-win-session-winsta-l1-1-1!WinStationGetCurrentSessionCapabilities` at `0x180057a46`
- `ext-ms-win-session-winsta-l1-1-1!WinStationGetCurrentSessionCapabilities` at `0x180057a46`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180057ca3`
- `ext-ms-win-msa-device-l1-1-0!MsaDevice_UseXTokenBasedSessionKey` at `0x180057ca3`

## string_xrefs

- `0x180056510`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x180056e07`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\svcapi.cpp`
- `0x1800567bd`: `hr = client.ImpersonateClient()`
- `0x1800568df`: `DeviceIdHelpers::UpdateDeviceTpmInfo (0x%x).`
- `0x1800564da`: `HandleAcquireTokens`
- `0x180056e00`: `HandleAcquireTokens`
- `0x180056837`: `hr = client.IsImpersonatingSystem(isSystem)`
- `0x180056a6d`: `hr = g_pPPCRL->GetNegativeCacheManager()->CheckNegativeCache( rgRequests[i].wszServiceTarget, rgRequests[i].wszServicePolicy, pIdentity, (pIdentity->GetUserType() == PPCRL_EMAIL))`
- `0x180056a5b`: `hr = IsAuthDisabledByEnterpriseDeviceAuthPolicy(&serviceExecutionContext, pIdentity)`
- `0x180056a9f`: `hr = IsAuthDisabledByPolicy(&serviceExecutionContext, pIdentity)`
- `0x1800574f5`: `hr = IsCallerInTokenRequestAllowedList(pIdentity)`
- `0x18005754a`: `hr = pIdentity->SetFlags(requestFlags & ~ACQUIRE_TOKEN_FLAGS_FILTER)`
- `0x180057aae`: `hr = client.GetTokenUser(userSid)`
- `0x180057b3d`: `No CID found for SID %ls.`
- `0x180057c11`: `hr = ShouldCreateNgcKey(&serviceExecutionContext, userSid, userCid, noUI, createNgcKey)`
- `0x180057d06`: `hr = DeviceIdHelpers::RetrieveDeviceID( g_szStrongAuthAppId, 0, IDCRL_DEVICE_ID_GET_VALID_DA_TOKEN, nullptr, nullptr, nullptr, pDeviceIdentity)`
- `0x1800583c9`: `hr = DeviceIdHelpers::HandleRenewDeviceId( &serviceExecutionContext, g_szStrongAuthAppId, pIdentity->GetUserType(), 0, pDeviceIdentity, pNewDeviceIdentity, nullptr, nullptr)`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
__int64 __fastcall HandleAcquireTokens(
        void *const a1,
        unsigned __int16 *a2,
        unsigned int a3,
        struct _WLIDRequestParams *const a4,
        int *a5,
        int *a6,
        int *a7,
        struct _WLIDResponseParams **a8,
        const unsigned __int16 *a9,
        unsigned __int64 a10,
        unsigned __int16 *a11,
        int *a12,
        unsigned int *a13)
{
  unsigned __int16 *v13; // r13
  __int64 v14; // rbx
  CAuthRequest *v15; // rbx
  unsigned int *v16; // rdi
  struct _WLIDResponseParams **v17; // r9
  struct _WLIDResponseParams **v18; // r12
  int LogonId; // eax
  const char *v20; // rcx
  unsigned int v21; // r8d
  int *v22; // rdi
  int SystemHardwareID; // eax
  int v24; // edi
  int updated; // eax
  void *v26; // rdi
  int SingleIdentity; // eax
  const char *v28; // rcx
  unsigned int v29; // r8d
  int v30; // r9d
  CSingleIdentity *v31; // rdx
  unsigned int v32; // r13d
  CPassportClientLibrary *v33; // rdi
  int v34; // eax
  CSingleIdentity *v35; // rcx
  int v36; // eax
  CSingleIdentity *v37; // rax
  __int64 v38; // r8
  struct _WLIDResponseParams *v39; // rdx
  int v40; // edi
  CSingleIdentity *v41; // rdi
  unsigned int v42; // eax
  __int64 v43; // rdi
  __int64 *v44; // rax
  CSingleIdentity *v45; // rcx
  unsigned int v46; // edi
  __int64 v47; // rdx
  wil *v48; // rcx
  CIdentityCredentialBag *v49; // rax
  const unsigned __int16 **v50; // rax
  int v51; // eax
  unsigned int v52; // r12d
  signed int v53; // eax
  __int64 *v54; // rax
  int v55; // eax
  __int64 v56; // r8
  __int64 v57; // rax
  int v58; // r8d
  __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  _QWORD *p_lpsz; // rcx
  bool v63; // zf
  unsigned __int64 v64; // rax
  int DeviceID; // eax
  const char *v66; // rcx
  CServiceRequest *v67; // rax
  CServiceRequest *v68; // rax
  CDeviceServiceRequest *v69; // rbx
  CSingleIdentity *v70; // rdi
  unsigned int v71; // eax
  int v72; // edi
  LPCWCH *v73; // rax
  LPCWCH *v74; // rax
  LPCWCH *v75; // rax
  int v76; // eax
  char v77; // di
  int v78; // edi
  const wchar_t *v79; // rax
  bool v80; // di
  signed int LastError; // eax
  int TokenUser; // eax
  const char *v83; // rcx
  unsigned int v84; // r8d
  int v85; // r9d
  int v86; // eax
  const char *v87; // rcx
  unsigned int v88; // r8d
  CSingleIdentity *v89; // rcx
  unsigned __int16 v90; // di
  int v91; // edi
  int v92; // edi
  __int64 v93; // rdi
  __int64 *v94; // rax
  __int64 v95; // rdi
  __int64 *v96; // rax
  __int64 RawPUID; // rax
  int v98; // edi
  CSingleIdentity *v99; // rdi
  unsigned int v100; // eax
  int v101; // eax
  unsigned __int64 v102; // rdx
  unsigned __int64 v103; // rcx
  struct CClientConfigDataCacheManager *v104; // rax
  int *v105; // r8
  int *v106; // rdi
  CSingleIdentity *v107; // rcx
  unsigned int *v108; // rdi
  int *v109; // rdi
  __int64 v110; // rcx
  char v111; // di
  char v112; // r12
  const unsigned __int16 **v113; // rax
  __int64 v114; // rcx
  __int64 v115; // r8
  __int64 v116; // r9
  unsigned int v117; // edi
  int TelemetryJson; // eax
  __int64 v119; // rdi
  __int64 *v120; // rax
  __int64 v121; // rdi
  __int64 *v122; // rax
  unsigned __int64 v123; // rax
  __int64 v124; // rdx
  CIdentityCredentialBag *v125; // rax
  const unsigned __int16 *v126; // rdx
  __int64 v127; // rdi
  __int64 v128; // rcx
  int v129; // eax
  unsigned int v130; // edi
  __int64 v131; // rbx
  const unsigned __int16 *bIgnoreCase; // [rsp+20h] [rbp-428h]
  BOOL bIgnoreCasea[2]; // [rsp+20h] [rbp-428h]
  const char *bIgnoreCaseb; // [rsp+20h] [rbp-428h]
  BOOL bIgnoreCasec[2]; // [rsp+20h] [rbp-428h]
  const char *bIgnoreCased; // [rsp+20h] [rbp-428h]
  int MissingCredentialErrorCode; // [rsp+C0h] [rbp-388h] BYREF
  CSingleIdentity *v139; // [rsp+C8h] [rbp-380h] BYREF
  DWORD v140; // [rsp+D0h] [rbp-378h] BYREF
  int v141; // [rsp+D4h] [rbp-374h] BYREF
  struct _WLIDResponseParams **v142; // [rsp+D8h] [rbp-370h]
  LPCOLESTR lpsz; // [rsp+E0h] [rbp-368h] BYREF
  unsigned int *v144; // [rsp+E8h] [rbp-360h]
  unsigned __int16 *v145; // [rsp+F0h] [rbp-358h] BYREF
  int v146; // [rsp+F8h] [rbp-350h] BYREF
  unsigned int v147; // [rsp+FCh] [rbp-34Ch]
  unsigned int v148; // [rsp+100h] [rbp-348h] BYREF
  unsigned __int16 *v149; // [rsp+108h] [rbp-340h] BYREF
  char v150; // [rsp+110h] [rbp-338h] BYREF
  bool v151; // [rsp+111h] [rbp-337h]
  bool v152; // [rsp+112h] [rbp-336h]
  unsigned __int16 *v153; // [rsp+118h] [rbp-330h]
  const unsigned __int16 *v154; // [rsp+120h] [rbp-328h] BYREF
  unsigned int ReportingAccountType; // [rsp+128h] [rbp-320h] BYREF
  int v156; // [rsp+130h] [rbp-318h] BYREF
  int v157; // [rsp+134h] [rbp-314h] BYREF
  int *v158; // [rsp+138h] [rbp-310h] BYREF
  unsigned __int16 **v159; // [rsp+140h] [rbp-308h] BYREF
  unsigned __int16 *v160; // [rsp+148h] [rbp-300h] BYREF
  int *v161; // [rsp+150h] [rbp-2F8h] BYREF
  int v162; // [rsp+158h] [rbp-2F0h] BYREF
  __int64 v163; // [rsp+160h] [rbp-2E8h] BYREF
  int *v164; // [rsp+168h] [rbp-2E0h] BYREF
  const unsigned __int16 *v165; // [rsp+170h] [rbp-2D8h] BYREF
  __int64 v166; // [rsp+178h] [rbp-2D0h]
  int v167; // [rsp+180h] [rbp-2C8h]
  struct _WLIDRequestParams *v168; // [rsp+188h] [rbp-2C0h]
  __int64 v169; // [rsp+190h] [rbp-2B8h] BYREF
  void *v170; // [rsp+198h] [rbp-2B0h] BYREF
  unsigned __int64 v171; // [rsp+1A0h] [rbp-2A8h] BYREF
  DWORD dwFlags; // [rsp+1A8h] [rbp-2A0h] BYREF
  CAuthRequest *v173; // [rsp+1B0h] [rbp-298h]
  struct _WLIDResponseParams *v174; // [rsp+1B8h] [rbp-290h] BYREF
  struct _LUID v175; // [rsp+1C0h] [rbp-288h] BYREF
  int *v176; // [rsp+1C8h] [rbp-280h] BYREF
  struct _WLIDRequestParams *v177; // [rsp+1D0h] [rbp-278h] BYREF
  ULONGLONG TickCount64; // [rsp+1D8h] [rbp-270h] BYREF
  char v179; // [rsp+1E1h] [rbp-267h]
  __int64 v180; // [rsp+1E8h] [rbp-260h] BYREF
  CSingleIdentity **v181; // [rsp+1F0h] [rbp-258h] BYREF
  unsigned __int64 v182; // [rsp+1F8h] [rbp-250h] BYREF
  char v183; // [rsp+204h] [rbp-244h]
  _QWORD v184[4]; // [rsp+208h] [rbp-240h] BYREF
  _BYTE v185[56]; // [rsp+228h] [rbp-220h] BYREF
  _BYTE v186[56]; // [rsp+260h] [rbp-1E8h] BYREF
  _BYTE v187[168]; // [rsp+298h] [rbp-1B0h] BYREF
  _BYTE v188[64]; // [rsp+340h] [rbp-108h] BYREF
  GUID pclsid; // [rsp+380h] [rbp-C8h] BYREF
  __int16 v190; // [rsp+390h] [rbp-B8h] BYREF
  __int64 v191; // [rsp+398h] [rbp-B0h]
  __int64 v192; // [rsp+3A0h] [rbp-A8h]
  __int64 v193; // [rsp+3A8h] [rbp-A0h]
  __int16 v194; // [rsp+3B0h] [rbp-98h]
  __int64 v195; // [rsp+3B8h] [rbp-90h]
  int v196; // [rsp+3C0h] [rbp-88h]
  __int64 v197; // [rsp+3C8h] [rbp-80h]
  int v198; // [rsp+3D0h] [rbp-78h]
  __int128 v199; // [rsp+3D8h] [rbp-70h]
  __int128 v200; // [rsp+3E8h] [rbp-60h]
  __int64 v201; // [rsp+3F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+448h] [rbp+0h]

  v168 = a4;
  v147 = a3;
  v13 = a2;
  v153 = a2;
  v170 = a1;
  v149 = a2;
  ReportingAccountType = a3;
  v177 = a4;
  v164 = a5;
  v158 = a6;
  v161 = a7;
  v142 = a8;
  *(_QWORD *)&pclsid.Data1 = a9;
  v171 = a10;
  v160 = a11;
  v176 = a12;
  v144 = a13;
  v141 = 0;
  v146 = 0;
  MissingCredentialErrorCode = 0;
  v184[0] = "HandleAcquireTokens";
  v184[1] = &MissingCredentialErrorCode;
  v184[2] = 0;
  v184[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    "HandleAcquireTokens",
    (const char *)0x1029,
    0,
    bIgnoreCase);
  v154 = (const unsigned __int16 *)((unsigned __int64)v13 & 0x1000000000LL);
  v165 = (const unsigned __int16 *)((unsigned __int64)v13 & 0x1000000000LL);
  v151 = ((unsigned __int64)v13 & 0x1000000000LL) != 0;
  Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::RequestTelemetryOperation(
    (Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *)v185,
    L"at");
  v182 = (unsigned __int64)v185 & -(__int64)(((unsigned __int64)v13 & 0x1000000000LL) != 0);
  v183 = 0;
  v179 = 1;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v14 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( !*(_BYTE *)(v14 + 12) )
      _dyn_tls_on_demand_init();
    *(_QWORD *)(v14 + 32) = &v182;
  }
  v180 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v181 = (CSingleIdentity **)operator new(0x10u);
    v145 = (unsigned __int16 *)Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation::ScopedRequestTelemetryOperation(
                                 (Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation *)v181,
                                 L"at");
    v141 = 8;
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      &v180,
      (__int64 *)&v145);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v145);
  }
  v175 = 0;
  v139 = 0;
  v156 = 0;
  v15 = 0;
  v173 = 0;
  v174 = 0;
  v190 = 0;
  v191 = 0;
  v192 = 0;
  v193 = 0;
  v194 = 0;
  v195 = 0;
  v196 = 0;
  v197 = 0;
  v198 = 0;
  v199 = 0;
  v200 = 0;
  v201 = 0;
  v181 = &v139;
  ServiceExecutionContext::ServiceExecutionContext((ServiceExecutionContext *)v186);
  v150 = 0;
  v169 = 0;
  bIgnoreCasea[0] = (int)v13;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
    0x104Au,
    L"requestFlags value: 0x%llx");
  if ( !v171 || (BYTE1(v140) = 0, ((unsigned __int16)v13 & 0x8000) != 0) )
    BYTE1(v140) = 1;
  v152 = ((unsigned __int64)v13 & 0x480000000LL) != 0;
  v163 = 0;
  v16 = v144;
  if ( v144 )
    *v144 = 0;
  v17 = v142;
  if ( v142 )
    *v142 = 0;
  if ( !v168 && v147 )
  {
    MissingCredentialErrorCode = -2147024809;
    v18 = v17;
    goto LABEL_273;
  }
  LogonId = CAutoImpersonateClient::ImpersonateClient((CAutoImpersonateClient *)&v163, 0);
  MissingCredentialErrorCode = LogonId;
  if ( LogonId < 0 )
  {
    v20 = "hr = client.ImpersonateClient()";
    v21 = 4205;
LABEL_19:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleAcquireTokens",
      v21,
      LogonId,
      v20);
LABEL_272:
    v18 = v142;
    goto LABEL_273;
  }
  LogonId = CAutoImpersonateClient::GetLogonId((CAutoImpersonateClient *)&v163, &v175);
  MissingCredentialErrorCode = LogonId;
  if ( LogonId < 0 )
  {
    v20 = "hr = client.GetLogonId(logonId)";
    v21 = 4206;
    goto LABEL_19;
  }
  LogonId = CAutoImpersonateClient::IsImpersonatingSystem((CAutoImpersonateClient *)&v163, &v156);
  MissingCredentialErrorCode = LogonId;
  if ( LogonId < 0 )
  {
    v20 = "hr = client.IsImpersonatingSystem(isSystem)";
    v21 = 4207;
    goto LABEL_19;
  }
  v22 = v176;
  if ( v176 )
    *v22 = *((_DWORD *)CClientConfigDataCacheManager::theConfigDataManager() + 68);
  if ( !byte_1801C4558 )
  {
    v145 = 0;
    SystemHardwareID = DeviceIdHelpers::GetSystemHardwareID(v186, 0, &v145);
    v24 = SystemHardwareID;
    if ( SystemHardwareID >= 0 )
    {
      if ( !byte_1801C4559 )
      {
        updated = DeviceIdHelpers::UpdateDeviceTpmInfo((struct IServiceExecutionContext *)v186);
        if ( updated < 0 )
        {
          bIgnoreCasea[0] = updated;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
            0x1089u,
            L"DeviceIdHelpers::UpdateDeviceTpmInfo (0x%x).");
          byte_1801C4559 = 1;
        }
      }
    }
    else
    {
      bIgnoreCasea[0] = SystemHardwareID;
      TracePrintW(
        2u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        0x107Eu,
        L"DeviceIdHelpers::GetSystemHardwareID (0x%x).");
      if ( v24 == -2147207917 )
        byte_1801C4558 = 1;
    }
    CAutoRefPtr<CSingleIdentity>::Deinit(&v145);
  }
  v26 = v170;
  SingleIdentity = CIdentityStore::GetSingleIdentity((__int64)g_pPPCRL + 496, &v175, (__int64)v170, &v139);
  MissingCredentialErrorCode = SingleIdentity;
  if ( SingleIdentity < 0 )
  {
    v28 = "hr = g_pPPCRL->GetIdentityStore()->GetSingleIdentity(logonId, handle, pIdentity)";
    v29 = 4242;
LABEL_36:
    v30 = SingleIdentity;
    bIgnoreCaseb = v28;
LABEL_37:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
      "HandleAcquireTokens",
      v29,
      v30,
      bIgnoreCaseb);
LABEL_271:
    v16 = v144;
    goto LABEL_272;
  }
  v31 = v139;
  if ( !v139 )
  {
    v30 = -2147467261;
    MissingCredentialErrorCode = -2147467261;
    bIgnoreCaseb = "pIdentity != nullptr";
    v29 = 4243;
    goto LABEL_37;
  }
  if ( ((unsigned int)v13 & 0xC0000100) == 0 && v168 )
  {
    v32 = 0;
    if ( v147 )
    {
      while ( 1 )
      {
        v33 = g_pPPCRL;
        v34 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v31 + 80LL))(v31);
        SingleIdentity = NegativeCacheManager::CheckNegativeCache(
                           (CPassportClientLibrary *)((char *)v33 + 2312),
                           *((const unsigned __int16 **)v168 + 5 * v32),
                           *((const unsigned __int16 **)v168 + 5 * v32 + 1),
                           v139,
                           v34 == 0);
        MissingCredentialErrorCode = SingleIdentity;
        if ( SingleIdentity < 0 )
          break;
        ++v32;
        v31 = v139;
        if ( v32 >= v147 )
        {
          v26 = v170;
          goto LABEL_46;
        }
      }
      v28 = "hr = g_pPPCRL->GetNegativeCacheManager()->CheckNegativeCache( rgRequests[i].wszServiceTarget, rgRequests[i]."
            "wszServicePolicy, pIdentity, (pIdentity->GetUserType() == PPCRL_EMAIL))";
      v29 = 4253;
      goto LABEL_36;
    }
LABEL_46:
    v13 = v153;
  }
  SingleIdentity = IsAuthDisabledByEnterpriseDeviceAuthPolicy((struct IServiceExecutionContext *)v186, v31);
  MissingCredentialErrorCode = SingleIdentity;
  if ( SingleIdentity < 0 )
  {
    v28 = "hr = IsAuthDisabledByEnterpriseDeviceAuthPolicy(&serviceExecutionContext, pIdentity)";
    v29 = 4258;
    goto LABEL_36;
  }
  SingleIdentity = IsAuthDisabledByPolicy((struct IServiceExecutionContext *)v186, v139);
  MissingCredentialErrorCode = SingleIdentity;
  if ( SingleIdentity < 0 )
  {
    v28 = "hr = IsAuthDisabledByPolicy(&serviceExecutionContext, pIdentity)";
    v29 = 4259;
    goto LABEL_36;
  }
  CSingleIdentity::SetCancellableRequestTransport(v139, (struct CTransport *)&v190);
  if ( *((_BYTE *)v139 + 624) )
  {
    v30 = -2147186622;
    MissingCredentialErrorCode = -2147186622;
    bIgnoreCaseb = "!pIdentity->IsRequestCancelled()";
    v29 = 4264;
    goto LABEL_37;
  }
  if ( *((_BYTE *)v139 + 627) )
    goto LABEL_70;
  if ( ((unsigned int)v13 & 0xF000000) != 0 )
  {
    if ( !v147 )
      goto LABEL_70;
  }
  else if ( !v147 )
  {
    if ( CSingleIdentity::HasAuthToken(v139) )
    {
      v35 = v139;
      if ( *((_DWORD *)v139 + 46) == -2147186688 )
      {
        CSingleIdentity::SetAuthenticationState(v139, 296963);
        v35 = v139;
      }
      *v158 = *((_DWORD *)v35 + 47);
      v36 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v35 + 56LL))(v35);
      *v161 = v36;
      *v164 = *((_DWORD *)v139 + 46);
      v18 = v142;
      *v142 = 0;
      MissingCredentialErrorCode = 0;
      goto LABEL_61;
    }
LABEL_70:
    if ( ((unsigned __int64)v13 & 0x200000000LL) == 0 )
    {
      if ( ((unsigned int)v13 & 0x2000000) != 0 )
      {
        v40 = 0;
        if ( !CSingleIdentity::HasAuthToken(v139) )
        {
          MissingCredentialErrorCode = -2147186591;
          goto LABEL_271;
        }
LABEL_111:
        if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 1
          && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 2 )
        {
          v63 = (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 3;
          v64 = (unsigned __int64)v153;
          if ( v63
            || ((unsigned int)v153 & 0x80008100) == 0
            && ((unsigned int)v153 & 0x40000080) != 0x40000000
            && (v64 = (unsigned __int64)v153, ((unsigned __int16)v153 & 0x200) == 0) )
          {
LABEL_121:
            DeviceID = CSingleIdentity::SetFlags(v139, v64 & 0xFFFFFFFFF0FFFFFFuLL);
            MissingCredentialErrorCode = DeviceID;
            if ( DeviceID < 0 )
            {
              v66 = "hr = pIdentity->SetFlags(requestFlags & ~ACQUIRE_TOKEN_FLAGS_FILTER)";
              v29 = 4497;
              goto LABEL_119;
            }
            if ( !v40 )
            {
              v159 = (unsigned __int16 **)operator new(0xF0u);
              v15 = CServiceRequest::CServiceRequest((CServiceRequest *)v159);
              v173 = v15;
              goto LABEL_138;
            }
            if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 1
              || (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 2
              || (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 3 )
            {
              v68 = (CServiceRequest *)operator new(0xF0u, (const struct std::nothrow_t *)std::nothrow);
              v69 = v68;
              v159 = (unsigned __int16 **)v68;
              if ( v68 )
              {
                memset_0(v68, 0, 0xF0u);
                v15 = CDeviceServiceRequest::CDeviceServiceRequest(v69);
              }
              else
              {
                v15 = 0;
              }
            }
            else
            {
              if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) )
                goto LABEL_135;
              v67 = (CServiceRequest *)operator new(0xF8u, (const struct std::nothrow_t *)std::nothrow);
              v159 = (unsigned __int16 **)v67;
              if ( v67 )
                v15 = CAuthRequest::CAuthRequest(v67);
              else
                v15 = 0;
            }
            v173 = v15;
LABEL_135:
            v70 = v139;
            v71 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139);
            DeviceID = CSingleIdentity::ValidateCreds(v70, v71);
            MissingCredentialErrorCode = DeviceID;
            if ( DeviceID < 0 )
            {
              v66 = "hr = pIdentity->ValidateCreds(pIdentity->GetUserType())";
              v29 = 4516;
              goto LABEL_119;
            }
LABEL_138:
            if ( !v15 )
            {
              MissingCredentialErrorCode = -2147024882;
              goto LABEL_271;
            }
            if ( v171 )
              *((_QWORD *)v15 + 28) = v171;
            if ( *(_QWORD *)&pclsid.Data1 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64 *)&v145,
                *(_WORD **)&pclsid.Data1);
              ATL::CSimpleStringT<unsigned short,0>::operator=((char *)v15 + 144, &v145);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
            }
            v72 = (int)v153;
            if ( ((unsigned __int16)v153 & 0x100) != 0 )
              *((_BYTE *)v15 + 176) = 1;
            if ( v72 < 0 )
            {
              *((_BYTE *)v15 + 177) = 1;
              if ( (v72 & 0x1000) != 0 )
                *((_BYTE *)v15 + 186) = 1;
            }
            if ( v160 )
            {
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64 *)&v145,
                v160);
              ATL::CSimpleStringT<unsigned short,0>::operator=((char *)v15 + 168, &v145);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
            }
            if ( (v72 & 0x80004000) != 0 )
              goto LABEL_160;
            if ( (*(unsigned __int8 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 48LL))(v139) != 1 )
              goto LABEL_160;
            if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 1 )
              goto LABEL_160;
            if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 2 )
              goto LABEL_160;
            if ( (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 3 )
              goto LABEL_160;
            if ( (*(unsigned int (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 56LL))(v15) != 1 )
              goto LABEL_160;
            v73 = (LPCWCH *)(*(__int64 (__fastcall **)(CSingleIdentity *, unsigned __int16 ***))(*(_QWORD *)v139 + 24LL))(
                              v139,
                              &v159);
            v141 |= 1u;
            v146 = v141;
            if ( CompareStringOrdinal(
                   *v73,
                   -1,
                   L"S-1-15-2-278586202-1783374767-3755652818-1001658646-1865713925-2047498344-1799408599",
                   -1,
                   1) == 2
              || (v74 = (LPCWCH *)(*(__int64 (__fastcall **)(CSingleIdentity *, unsigned __int16 **))(*(_QWORD *)v139 + 16LL))(
                                    v139,
                                    &v160),
                  v141 |= 2u,
                  v146 = v141,
                  CompareStringOrdinal(*v74, -1, L"{7D629E2E-CC4C-4CC4-95B7-25C48B11C53D}", -1, 1) == 2)
              || (v75 = (LPCWCH *)(*(__int64 (__fastcall **)(CSingleIdentity *, GUID *))(*(_QWORD *)v139 + 16LL))(
                                    v139,
                                    &pclsid),
                  v141 |= 4u,
                  v76 = CompareStringOrdinal(*v75, -1, L"{CC553C39-4B1C-43DB-94A0-3B78F751ACEF}", -1, 1),
                  LOBYTE(v140) = 1,
                  v76 == 2) )
            {
LABEL_160:
              LOBYTE(v140) = 0;
            }
            v77 = v141;
            if ( (v141 & 4) != 0 )
            {
              v77 = v141 & 0xFB;
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pclsid);
            }
            if ( (v77 & 2) != 0 )
            {
              v77 &= ~2u;
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v160);
            }
            if ( (v77 & 1) != 0 )
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v159);
            if ( (_BYTE)v140 )
            {
              v148 = 0;
              DeviceID = LsaLookupUserAccountType(0, &v148) | 0x10000000;
              MissingCredentialErrorCode = DeviceID;
              if ( DeviceID < 0 )
              {
                v66 = "hr = HRESULT_FROM_NT(LsaLookupUserAccountType(nullptr, &accountType))";
                v29 = 4565;
                goto LABEL_119;
              }
              v78 = *((_DWORD *)v139 + 184);
              v79 = L"true";
              if ( !v78 )
                v79 = L"false";
              TracePrintW(
                5u,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                0x11D7u,
                L"Identity IsConnected value: %ls ; accountType value: %d",
                v79,
                v148);
              if ( v148 - 1 <= 2 || !v78 )
              {
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpsz);
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v149);
                LOBYTE(v140) = 0;
                v80 = 0;
                v146 = 0;
                if ( (unsigned __int8)IsWinStationGetCurrentSessionCapabilitiesPresent() )
                {
                  if ( (unsigned __int8)WinStationGetCurrentSessionCapabilities(1, &v146) )
                  {
                    v80 = v146 != 0;
                  }
                  else
                  {
                    LastError = GetLastError();
                    if ( LastError > 0 )
                      LastError = (unsigned __int16)LastError | 0x80070000;
                    bIgnoreCasec[0] = LastError;
                    TracePrintW(
                      5u,
                      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                      0x11F4u,
                      L"WinStationGetCurrentSessionCapabilities returns false with 0x%08x.",
                      *(_QWORD *)bIgnoreCasec);
                  }
                }
                TokenUser = CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v163, &lpsz);
                MissingCredentialErrorCode = TokenUser;
                if ( TokenUser < 0 )
                {
                  v83 = "hr = client.GetTokenUser(userSid)";
                  v84 = 4602;
LABEL_182:
                  bIgnoreCased = v83;
                  v85 = TokenUser;
LABEL_183:
                  Telemetry::IfFailExit(
                    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                    "HandleAcquireTokens",
                    v84,
                    v85,
                    bIgnoreCased);
                  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v149);
                  p_lpsz = &lpsz;
LABEL_109:
                  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(p_lpsz);
                  goto LABEL_271;
                }
                TokenUser = (*(__int64 (__fastcall **)(CSingleIdentity *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v139 + 64LL))(
                              v139,
                              L"CID",
                              &v149);
                MissingCredentialErrorCode = TokenUser;
                if ( TokenUser < 0 )
                {
                  v83 = "hr = pIdentity->GetCredProperty(PPCRL_CREDPROPERTY_CID, userCid)";
                  v84 = 4603;
                  goto LABEL_182;
                }
                if ( TokenUser == 1 )
                {
                  TracePrintW(
                    5u,
                    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                    0x1201u,
                    L"No CID found for SID %ls.",
                    lpsz);
                  MissingCredentialErrorCode = 0;
                }
                else if ( v80 )
                {
                  TracePrintW(
                    5u,
                    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                    0x1206u,
                    L"User is in remote session, skip registering NGC for secondary MSA ");
                }
                else
                {
                  TokenUser = ShouldCreateNgcKey(
                                (struct IServiceExecutionContext *)v186,
                                lpsz,
                                v149,
                                SBYTE1(v140),
                                (DWORD)&v140);
                  MissingCredentialErrorCode = TokenUser;
                  if ( TokenUser < 0 )
                  {
                    v83 = "hr = ShouldCreateNgcKey(&serviceExecutionContext, userSid, userCid, noUI, createNgcKey)";
                    v84 = 4618;
                    goto LABEL_182;
                  }
                  if ( (_BYTE)v140 == 1 )
                  {
                    v85 = -2147186509;
                    MissingCredentialErrorCode = -2147186509;
                    bIgnoreCased = "hr = PPCRL_E_NGC_REGISTRATION_REQUIRED";
                    v84 = 4621;
                    goto LABEL_183;
                  }
                }
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v149);
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpsz);
              }
            }
            if ( *((_BYTE *)v139 + 624) )
            {
              v30 = -2147186622;
              MissingCredentialErrorCode = -2147186622;
              bIgnoreCaseb = "!pIdentity->IsRequestCancelled()";
              v29 = 4628;
              goto LABEL_37;
            }
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(
              &pclsid,
              &cchOriginalDestLength);
            DeviceID = CPPCRLRequest::Initialize(v15, v139);
            MissingCredentialErrorCode = DeviceID;
            if ( DeviceID >= 0 )
            {
              if ( !v156 || (unsigned int)MsaDevice_UseXTokenBasedSessionKey() || ((unsigned __int16)v153 & 0x2000) != 0 )
                (*(void (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 240LL))(v15);
              DeviceID = DeviceIdHelpers::RetrieveDeviceID(
                           L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}",
                           0,
                           0,
                           0,
                           (__int64)&v169);
              MissingCredentialErrorCode = DeviceID;
              if ( DeviceID >= 0 )
              {
                if ( !v169 )
                {
                  v30 = -2147188626;
                  MissingCredentialErrorCode = -2147188626;
                  bIgnoreCaseb = "pDeviceIdentity != nullptr";
                  v29 = 4648;
                  goto LABEL_37;
                }
                LOBYTE(v140) = 1;
                v165 = (const unsigned __int16 *)((char *)v139 + 16);
                LOBYTE(v166) = 0;
                v86 = CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v165);
                MissingCredentialErrorCode = v86;
                if ( v86 < 0 )
                {
                  v87 = "hr = lock.Lock()";
                  v88 = 4657;
LABEL_269:
                  Telemetry::IfFailExit(
                    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                    "HandleAcquireTokens",
                    v88,
                    v86,
                    v87);
LABEL_270:
                  CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v165);
                  goto LABEL_271;
                }
                v89 = v139;
                if ( !*((_BYTE *)v139 + 249) )
                {
                  v90 = 0;
                  LOWORD(v141) = 0;
                  BYTE1(v140) = 1;
                  while ( 1 )
                  {
                    LOBYTE(bIgnoreCasea[0]) = v152;
                    v86 = (*(__int64 (__fastcall **)(CAuthRequest *, unsigned __int16 *, _QWORD, struct _WLIDRequestParams *))(*(_QWORD *)v15 + 168LL))(
                            v15,
                            v153,
                            v147,
                            v168);
                    MissingCredentialErrorCode = v86;
                    if ( v86 < 0 && v150 == 1 )
                      break;
                    if ( v86 == -2147187452 )
                    {
                      if ( BYTE1(v140) != 1 )
                        goto LABEL_268;
                      lpsz = 0;
                      v91 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139);
                      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                        (__int64 *)&v145,
                        L"{AFDA72BF-3409-413a-B54E-2AB8D66A7826}");
                      v92 = DeviceIdHelpers::HandleRenewDeviceId(
                              (unsigned int)v186,
                              (unsigned int)&v145,
                              v91,
                              0,
                              (__int64)&v169,
                              (__int64)&lpsz,
                              0,
                              0);
                      MissingCredentialErrorCode = v92;
                      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
                      if ( v92 < 0 )
                      {
                        Telemetry::IfFailExit(
                          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                          "HandleAcquireTokens",
                          0x125Du,
                          v92,
                          "hr = DeviceIdHelpers::HandleRenewDeviceId( &serviceExecutionContext, g_szStrongAuthAppId, pIde"
                          "ntity->GetUserType(), 0, pDeviceIdentity, pNewDeviceIdentity, nullptr, nullptr)");
                        goto LABEL_247;
                      }
                      if ( ((*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 1
                         || (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 2
                         || (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 3)
                        && lpsz )
                      {
                        MissingCredentialErrorCode = -2147187451;
LABEL_247:
                        CAutoRefPtr<CSingleIdentity>::Deinit(&lpsz);
                        goto LABEL_270;
                      }
                      LOWORD(v140) = 1;
                      CAutoRefPtr<CSingleIdentity>::Deinit(&lpsz);
                      v90 = v141;
                    }
                    else
                    {
                      if ( v86 < 0 )
                      {
LABEL_268:
                        v87 = "hr";
                        v88 = 4718;
                        goto LABEL_269;
                      }
                      LOWORD(v141) = ++v90;
                      v86 = (*(__int64 (__fastcall **)(CAuthRequest *, _QWORD, DWORD *))(*(_QWORD *)v15 + 208LL))(
                              v15,
                              v90,
                              &v140);
                      MissingCredentialErrorCode = v86;
                      if ( v86 < 0 )
                      {
                        v87 = "hr = pRequest->ShouldResendRequest(++requestCounter, resendRequest)";
                        v88 = 4721;
                        goto LABEL_269;
                      }
                    }
                    if ( (_BYTE)v140 != 1 || v90 > 3u )
                    {
                      v93 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 8LL))(v139);
                      v159 = &v145;
                      v145 = 0;
                      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
                      v94 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                              (__int64 *)&pclsid,
                              L"ps:ngckn");
                      CIdentityCredentialBag::StoreCredential(v93, v94, &v145);
                      v95 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 8LL))(v139);
                      *(_QWORD *)&pclsid.Data1 = &lpsz;
                      lpsz = 0;
                      ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpsz);
                      v96 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                              (__int64 *)&v160,
                              L"ps:ngcat");
                      CIdentityCredentialBag::StoreCredential(v95, v96, &lpsz);
                      CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v165);
                      if ( *((_BYTE *)v15 + 98) == 1 )
                      {
                        v146 = 0;
                        ExecutionContextLite::ExecutionContextLite((ExecutionContextLite *)v188);
                        SystemStoreLite::IsConnected((struct IExecutionContextLite *)v188, &v146, 0);
                        if ( v146 )
                        {
                          *(_QWORD *)&pclsid.Data1 = v188;
                          RawPUID = CSingleIdentity::GetRawPUID(v139, &v160);
                          IdentityStorage::DeleteTicketsForUser(&pclsid, RawPUID);
                          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v160);
                        }
                      }
                      if ( !(*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139)
                        && ((unsigned int)v153 & 0x10000000) == 0
                        && *((_BYTE *)v15 + 232) == 1 )
                      {
                        ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
                        ATL::CSimpleStringT<char,0>::SetString(&v145, v195);
                        v166 = 0;
                        LODWORD(v165) = 0;
                        v167 = 0;
                        CBytePtr::Attach((CBytePtr *)&v165, *((unsigned __int8 **)v15 + 25), *((_DWORD *)v15 + 48), 0);
                        v98 = *((_DWORD *)v15 + 54);
                        (*(void (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 56LL))(v15);
                        lpsz = (LPCOLESTR)v139;
                        if ( v139 )
                          _InterlockedAdd((volatile signed __int32 *)v139 + 2, 1u);
                        RenameLiveIdIfRequired(v170, (__int64)&v145, (__int64)&v165, v98);
                        CBytePtr::Empty((CBytePtr *)&v165);
                        CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CAutoZeroMemoryStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&v145);
                      }
                      if ( (*(int (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 232LL))(v15) >= 0
                        && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 1
                        && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 2
                        && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 3
                        && !v156 )
                      {
                        v99 = v139;
                        v100 = (*(__int64 (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 232LL))(v15);
                        CSingleIdentity::HandleUserNgcKeyUpdate(
                          v99,
                          (struct IServiceExecutionContext *)v186,
                          v100,
                          v171);
                      }
                      goto LABEL_241;
                    }
                  }
                  TracePrintW(
                    2u,
                    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                    0x1241u,
                    L"CSingleIdentity::AuthIdentity - Failed when sending auth request.",
                    *(_QWORD *)bIgnoreCasea,
                    &v190,
                    &v169,
                    &v150);
                  MapSendError(&MissingCredentialErrorCode);
                  v89 = v139;
                  if ( !*((_BYTE *)v139 + 248) && !*((_BYTE *)v139 + 249) )
                  {
                    *v158 = *((_DWORD *)v139 + 47);
                    *v164 = *((_DWORD *)v89 + 46);
                    v101 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v89 + 56LL))(v89);
                    *v161 = v101;
                    goto LABEL_270;
                  }
                }
                MissingCredentialErrorCode = CSingleIdentity::CheckAndHandleOfflineAuth(
                                               v89,
                                               &MissingCredentialErrorCode);
                CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v165);
LABEL_241:
                if ( *((_BYTE *)v139 + 624) )
                {
                  v30 = -2147186622;
                  MissingCredentialErrorCode = -2147186622;
                  bIgnoreCaseb = "!pIdentity->IsRequestCancelled()";
                  v29 = 4774;
                  goto LABEL_37;
                }
                DeviceID = CPPCRLRequest::GetResponse(v15, &v174);
                MissingCredentialErrorCode = DeviceID;
                if ( DeviceID >= 0 )
                {
                  if ( *((_BYTE *)v139 + 624) )
                  {
                    v30 = -2147186622;
                    MissingCredentialErrorCode = -2147186622;
                    bIgnoreCaseb = "!pIdentity->IsRequestCancelled()";
                    v29 = 4778;
                    goto LABEL_37;
                  }
                  if ( (*(unsigned __int8 (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 224LL))(v15) )
                  {
                    lpsz = 0;
                    (*(void (__fastcall **)(__int64, __int64, LPCOLESTR *))(*(_QWORD *)v169 + 88LL))(v169, 1, &lpsz);
                    if ( lpsz )
                    {
                      ATL::CTime::GetTickCount(&pclsid);
                      v104 = CClientConfigDataCacheManager::theConfigDataManager();
                      (*(void (__fastcall **)(LPCOLESTR, _QWORD))(*(_QWORD *)lpsz + 168LL))(
                        lpsz,
                        *(_QWORD *)&pclsid.Data1 - *((int *)v104 + 68));
                      (*(void (__fastcall **)(LPCOLESTR))(*(_QWORD *)lpsz + 136LL))(lpsz);
                    }
                    if ( ((unsigned __int16)v153 & 0x400) == 0 )
                      DeviceIdHelpers::GetDeviceIDAsync(v103, v102);
                  }
                  if ( v158 && (v105 = v164) != 0 && (v106 = v161) != 0 && (v107 = v139) != 0 )
                  {
                    *v158 = *((_DWORD *)v139 + 47);
                    *v105 = *((_DWORD *)v107 + 46);
                    *v106 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v107 + 56LL))(v107);
                    v18 = v142;
                    *v142 = v174;
                    v108 = v144;
                    if ( v144 )
                      *v108 = (*(__int64 (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 64LL))(v15);
                  }
                  else
                  {
                    v18 = v142;
                  }
                  v109 = v176;
                  if ( v176 )
                    *v109 = *((_DWORD *)CClientConfigDataCacheManager::theConfigDataManager() + 68);
LABEL_61:
                  v16 = v144;
                  goto LABEL_273;
                }
                v66 = "hr = pRequest->GetResponse(&rgResponses)";
                v29 = 4776;
              }
              else
              {
                v66 = "hr = DeviceIdHelpers::RetrieveDeviceID( g_szStrongAuthAppId, 0, IDCRL_DEVICE_ID_GET_VALID_DA_TOKEN"
                      ", nullptr, nullptr, nullptr, pDeviceIdentity)";
                v29 = 4646;
              }
            }
            else
            {
              v66 = "hr = pRequest->Initialize(pIdentity, \"\")";
              v29 = 4630;
            }
LABEL_119:
            bIgnoreCaseb = v66;
            v30 = DeviceID;
            goto LABEL_37;
          }
          DeviceID = IsCallerInTokenRequestAllowedList(&v139);
          MissingCredentialErrorCode = DeviceID;
          if ( DeviceID < 0 )
          {
            v66 = "hr = IsCallerInTokenRequestAllowedList(pIdentity)";
            v29 = 4493;
            goto LABEL_119;
          }
        }
        v64 = (unsigned __int64)v153;
        goto LABEL_121;
      }
      v41 = v139;
      v42 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139);
      if ( (unsigned int)CSingleIdentity::ValidateCreds(v41, v42)
        && !CSingleIdentity::HasSuppliedCredential(v139, (unsigned __int64)v13 & 0xFFFFFFFFF0FFFFFFuLL) )
      {
        if ( CSingleIdentity::HasAuthToken(v139) )
        {
          v40 = 0;
          goto LABEL_111;
        }
        v43 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 8LL))(v139);
        v44 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64 *)&v145,
                L"ps:password");
        if ( !(unsigned __int8)CIdentityCredentialBag::HasPersistedCredential(v43, v44) )
        {
          v162 = 0;
          v45 = v139;
          if ( *((_BYTE *)v139 + 740) )
          {
            v148 = 3;
            MissingCredentialErrorCode = -2147186500;
            v46 = v147;
          }
          else
          {
            MissingCredentialErrorCode = CSingleIdentity::GetMissingCredentialErrorCode(v139);
            try
            {
              LOBYTE(v47) = 1;
              v148 = CSingleIdentity::WriteCredManLogInternal(v139, v47);
            }
            catch ( ... )
            {
              v146 = 2;
              v157 = wil::ResultFromCaughtException(v48);
              TracePrintW(
                2u,
                "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                0x1112u,
                L"TestAndSetIsMissingCredValue failed: hr = 0x%x.",
                v157);
              v15 = v173;
              v148 = v146;
              v162 = v157;
              v153 = v149;
              v46 = ReportingAccountType;
              v147 = ReportingAccountType;
              v168 = v177;
              v154 = v165;
              goto LABEL_83;
            }
            v46 = v147;
LABEL_83:
            v45 = v139;
          }
          v146 = 0;
          if ( !*((_BYTE *)v45 + 740) && *((_DWORD *)v45 + 184) )
          {
            v49 = (CIdentityCredentialBag *)(*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v45 + 8LL))(v45);
            v146 = CIdentityCredentialBag::ResetDefaultCredSavedProperty(
                     v49,
                     (struct IServiceExecutionContext *)v186,
                     L"DefaultCredsMissing");
            v45 = v139;
          }
          v157 = 0;
          ReportingAccountType = 0;
          if ( !(*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v45 + 80LL))(v45) )
          {
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v149);
            if ( (int)CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v163, &v149) >= 0 )
            {
              v50 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(CSingleIdentity *, const unsigned __int16 **))(*(_QWORD *)v139 + 32LL))(
                                                 v139,
                                                 &v165);
              ReportingAccountType = SystemStoreLite::GetReportingAccountType(
                                       (struct IExecutionContextLite *)v187,
                                       v149,
                                       *v50,
                                       (enum ReportingAccountType *)&v157);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v165);
            }
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v149);
          }
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
          v51 = (*(__int64 (__fastcall **)(CSingleIdentity *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v139 + 64LL))(
                  v139,
                  L"CID",
                  &v145);
          if ( v51 < 0 )
            Telemetry::IfFailExit(
              "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
              "HandleAcquireTokens",
              0x1133u,
              v51,
              "pIdentity->GetCredProperty(PPCRL_CREDPROPERTY_CID, accountCid)");
          dwFlags = 0;
          v52 = 0;
          if ( !GetProfileType(&dwFlags) )
          {
            v53 = GetLastError();
            v52 = v53;
            if ( v53 > 0 )
              v52 = (unsigned __int16)v53 | 0x80070000;
          }
          ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
            (__int64 *)&lpsz,
            L"none");
          if ( v46 && v168 )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&v149,
              *(_WORD **)v168);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              &v158,
              "=");
            v54 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                    (__int64 *)&v165,
                    L"uaid");
            ATL::operator+(&v164, v54, &v158);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v165);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v158);
            v141 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                     &v149,
                     v164);
            if ( v141 != -1 )
            {
              ATL::CSimpleStringT<unsigned short,0>::SetString(&lpsz, L"{");
              v55 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
                      &v149,
                      38,
                      (unsigned int)(v141 + 5));
              v56 = (unsigned int)(v141 + 5);
              v57 = v55 == -1
                  ? ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                      &v149,
                      &v161,
                      v56)
                  : ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                      &v149,
                      &v161,
                      v56,
                      (unsigned int)(v55 - v56));
              ATL::CSimpleStringT<unsigned short,0>::Append(&lpsz, v57);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v161);
              ATL::CSimpleStringT<unsigned short,0>::Append(&lpsz, L"}");
              pclsid = 0;
              if ( CLSIDFromString(lpsz, &pclsid) < 0 )
                ATL::CSimpleStringT<unsigned short,0>::SetString(&lpsz, L"NonGuidParsed");
            }
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v164);
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v149);
            v46 = v147;
          }
          v156 = 0;
          LsaLookupUserAccountType(0, &v156);
          if ( (unsigned int)dword_1801C2080 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
          {
            v141 = v58 | 0x10000000;
            LODWORD(v177) = v156;
            v165 = lpsz;
            LODWORD(v176) = v52;
            LODWORD(v171) = dwFlags & 1;
            LODWORD(v170) = MissingCredentialErrorCode;
            LODWORD(v161) = *((_DWORD *)v139 + 184);
            LODWORD(v164) = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) == 0;
            LODWORD(v158) = v46;
            TickCount64 = GetTickCount64();
            v159 = (unsigned __int16 **)v153;
            LODWORD(v149) = 0;
            v160 = v145;
            *(_QWORD *)&pclsid.Data1 = 50331648;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
              v59,
              (__int64)word_18019832A,
              v60,
              v61,
              (__int64)&pclsid,
              (const unsigned __int16 **)&v160,
              (__int64)&v149,
              (__int64)&v159,
              (__int64)&TickCount64,
              (__int64)&v158,
              (__int64)&v164,
              (__int64)&v161,
              (__int64)&v170,
              (__int64)&v146,
              (__int64)&v171,
              (__int64)&v176,
              (__int64)&v157,
              (__int64)&ReportingAccountType,
              (__int64)&v148,
              (__int64)&v162,
              &v165,
              (__int64)&v177,
              (__int64)&v141);
          }
          ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpsz);
          p_lpsz = &v145;
          goto LABEL_109;
        }
      }
    }
    v40 = 1;
    goto LABEL_111;
  }
  if ( ((unsigned __int16)v13 & 0x200) != 0 )
    goto LABEL_70;
  v148 = 0;
  MissingCredentialErrorCode = HandleGetCachedTokens((__int64)v26, v147, (const unsigned __int16 **)v168, &v148, &v174);
  if ( MissingCredentialErrorCode )
  {
    MissingCredentialErrorCode = 0;
    goto LABEL_70;
  }
  v37 = v139;
  if ( *((_DWORD *)v139 + 46) == -2147186688 )
  {
    CSingleIdentity::SetAuthenticationState(v139, 296963);
    v37 = v139;
  }
  v38 = 136LL * (v147 - 1);
  v39 = v174;
  *v158 = *(_DWORD *)((char *)v174 + v38);
  *v161 = *(_DWORD *)((char *)v39 + v38 + 4);
  *v164 = *((_DWORD *)v37 + 46);
  v18 = v142;
  *v142 = v39;
  v16 = v144;
  if ( v144 )
    *v144 = v148;
LABEL_273:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
    CreateTelemetryOnlyResponseIfRequested(v151, v18, v16);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpsz);
  if ( v139 )
  {
    if ( MissingCredentialErrorCode >= 0 || v154 )
    {
      if ( v15 )
      {
        v110 = *((_QWORD *)v15 + 3);
        if ( v110 )
        {
          if ( MissingCredentialErrorCode < 0
            || (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v110 + 80LL))(v110)
            || (v111 = 1, (*(unsigned int (__fastcall **)(CAuthRequest *))(*(_QWORD *)v15 + 56LL))(v15) != 1) )
          {
            v111 = 0;
          }
          if ( !v18 || !*v18 || (v112 = 1, !v154) )
            v112 = 0;
          if ( v111 || v112 )
          {
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
            if ( (int)CAutoImpersonateClient::GetTokenUser((CAutoImpersonateClient *)&v163, &v145) >= 0 )
            {
              v141 = 0;
              v113 = (const unsigned __int16 **)(*(__int64 (__fastcall **)(_QWORD, GUID *))(**((_QWORD **)v15 + 3) + 32LL))(
                                                  *((_QWORD *)v15 + 3),
                                                  &pclsid);
              LODWORD(v149) = SystemStoreLite::GetReportingAccountType(
                                (struct IExecutionContextLite *)v187,
                                v145,
                                *v113,
                                (enum ReportingAccountType *)&v141);
              ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&pclsid);
              if ( v111 )
              {
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v154);
                (*(void (__fastcall **)(_QWORD, const wchar_t *, const unsigned __int16 **))(**((_QWORD **)v15 + 3)
                                                                                           + 64LL))(
                  *((_QWORD *)v15 + 3),
                  L"CID",
                  &v154);
                if ( (unsigned int)dword_1801C2080 > 5
                  && (unsigned __int8)tlgKeywordOn(&dword_1801C2080, 0x400000000000LL) )
                {
                  *(_QWORD *)&pclsid.Data1 = v154;
                  v117 = v141;
                  LODWORD(v158) = v141;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
                    v114,
                    (unsigned __int8 *)&byte_1801982F7,
                    v115,
                    v116,
                    (__int64)&v149,
                    (__int64)&v158,
                    (const unsigned __int16 **)&pclsid);
                }
                else
                {
                  v117 = v141;
                }
                ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v154);
              }
              else
              {
                v117 = v141;
              }
              if ( v112 )
              {
                if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
                {
                  MatsHelpers::LogAccountType(v117);
                }
                else
                {
                  TelemetryJson = MatsHelpers::GetTelemetryJson(v117, &lpsz);
                  if ( TelemetryJson < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x1304,
                      (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
                      (const char *)(unsigned int)TelemetryJson,
                      bIgnoreCasea[0]);
                }
              }
            }
            ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
          }
        }
      }
    }
    v165 = (const unsigned __int16 *)((char *)v139 + 16);
    LOBYTE(v166) = 0;
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::Lock(&v165);
    v119 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 8LL))(v139);
    v159 = (unsigned __int16 **)&v154;
    v154 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v154);
    v120 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
             (__int64 *)&pclsid,
             L"ps:ngckn");
    CIdentityCredentialBag::StoreCredential(v119, v120, &v154);
    v121 = (*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 8LL))(v139);
    *(_QWORD *)&pclsid.Data1 = &v145;
    v145 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v145);
    v122 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
             (__int64 *)&v160,
             L"ps:ngcat");
    CIdentityCredentialBag::StoreCredential(v121, v122, &v145);
    CComCritSecLockWTry<CComAutoCriticalSectionWTry>::~CComCritSecLockWTry<CComAutoCriticalSectionWTry>((__int64)&v165);
    if ( MissingCredentialErrorCode >= 0 && v15
      || (v123 = (unsigned int)(MissingCredentialErrorCode + 2147186655), (unsigned int)v123 <= 0x2B)
      && (v124 = 0x80000002001LL, _bittest64(&v124, v123))
      || MissingCredentialErrorCode == -2147186500
      || MissingCredentialErrorCode == -2147186552 )
    {
      if ( ((unsigned __int64)v153 & 0xFF0000) == 0 )
        DoActionCenterNotification(
          MissingCredentialErrorCode,
          v139,
          &v175,
          (struct CAutoImpersonateClient *)&v163,
          v147,
          1,
          v168,
          v15);
    }
  }
  if ( v15
    && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 1
    && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 2
    && (*(unsigned int (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 80LL))(v139) != 3
    && *((_BYTE *)v15 + 232) == 1 )
  {
    v125 = (CIdentityCredentialBag *)(*(__int64 (__fastcall **)(CSingleIdentity *))(*(_QWORD *)v139 + 8LL))(v139);
    CIdentityCredentialBag::RemoveCredential(v125, v126);
    *((_BYTE *)v139 + 628) = 0;
    v127 = *((_QWORD *)v139 + 11);
    v154 = 0;
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v154);
    CIdentityTokenBag::CacheAndEncryptPersistedPassword(v127, &v154);
    CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CAutoZeroMemoryStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v154);
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    LOBYTE(v128) = v151;
    v129 = MatsHelpers::FinalizeAndOutputTelemetryJson(v128, &lpsz, v185, v142);
    if ( v129 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1333,
        (unsigned int)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\svcapi.cpp",
        (const char *)(unsigned int)v129,
        bIgnoreCasea[0]);
  }
  v130 = MissingCredentialErrorCode;
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&lpsz);
  CAutoImpersonateClient::~CAutoImpersonateClient((CAutoImpersonateClient *)&v163);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v169);
  ServiceExecutionContext::~ServiceExecutionContext((ServiceExecutionContext *)v186);
  CSmartCancelRequest::~CSmartCancelRequest((__int64 **)&v181);
  CTransport::~CTransport((CTransport *)&v190);
  if ( v15 )
    (**(void (__fastcall ***)(CAuthRequest *, __int64))v15)(v15, 1);
  CAutoRefPtr<CSingleIdentity>::Deinit(&v139);
  std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v180);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v131 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    if ( !*(_BYTE *)(v131 + 12) )
      _dyn_tls_on_demand_init();
    *(_QWORD *)(v131 + 32) = 0;
  }
  Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::~RequestTelemetryOperation((Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *)v185);
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v184);
  return v130;
}

```

## disassembly

```asm
0x1800563d0  mov     r11, rsp
0x1800563d3  push    rbx
0x1800563d4  push    rsi
0x1800563d5  push    rdi
0x1800563d6  push    r12
0x1800563d8  push    r13
0x1800563da  push    r14
0x1800563dc  push    r15
0x1800563de  sub     rsp, 410h
0x1800563e5  mov     rax, cs:__security_cookie
0x1800563ec  xor     rax, rsp
0x1800563ef  mov     [rsp+448h+var_48], rax
0x1800563f7  mov     [rsp+448h+var_2C0], r9
0x1800563ff  mov     eax, r8d
0x180056402  mov     [rsp+448h+var_34C], eax
0x180056409  mov     r13, rdx
0x18005640c  mov     [rsp+448h+var_330], rdx
0x180056414  mov     [rsp+448h+var_2B0], rcx
0x18005641c  mov     [rsp+448h+var_340], rdx
0x180056424  mov     [rsp+448h+var_320], eax
0x18005642b  mov     [rsp+448h+var_278], r9
0x180056433  mov     rax, [rsp+448h+arg_20]
0x18005643b  mov     [rsp+448h+var_2E0], rax
0x180056443  mov     rax, [rsp+448h+arg_28]
0x18005644b  mov     [rsp+448h+var_310], rax
0x180056453  mov     rax, [rsp+448h+arg_30]
0x18005645b  mov     [rsp+448h+var_2F8], rax
0x180056463  mov     rax, [rsp+448h+arg_38]
0x18005646b  mov     [rsp+448h+var_370], rax
0x180056473  mov     rax, [rsp+448h+arg_40]
0x18005647b  mov     qword ptr [rsp+448h+pclsid.Data1], rax
0x180056483  mov     rax, [rsp+448h+arg_48]
0x18005648b  mov     [rsp+448h+var_2A8], rax
0x180056493  mov     rax, [rsp+448h+arg_50]
0x18005649b  mov     [rsp+448h+var_300], rax
0x1800564a3  mov     rax, [rsp+448h+arg_58]
0x1800564ab  mov     [rsp+448h+var_280], rax
0x1800564b3  mov     rax, [rsp+448h+arg_60]
0x1800564bb  mov     [rsp+448h+var_360], rax
0x1800564c3  xor     esi, esi
0x1800564c5  mov     [rsp+448h+var_374], esi
0x1800564cc  mov     [rsp+448h+var_350], esi
0x1800564d3  mov     [rsp+448h+var_388], esi
0x1800564da  lea     r12, aHandleacquiret_0; "HandleAcquireTokens"
0x1800564e1  mov     [r11-240h], r12
0x1800564e8  lea     rax, [r11-388h]
0x1800564ef  mov     [r11-238h], rax
0x1800564f6  mov     [r11-230h], rsi
0x1800564fd  mov     [r11-228h], rsi
0x180056504  xor     r9d, r9d; unsigned int
0x180056507  mov     r8d, 1029h; char *
0x18005650d  mov     rdx, r12; char *
0x180056510  lea     r15, aOnecoreuapDsEx_11; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x180056517  mov     rcx, r15; this
0x18005651a  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18005651f  nop
0x180056520  mov     rax, 1000000000h
0x18005652a  mov     rbx, r13
0x18005652d  and     rbx, rax
0x180056530  mov     [rsp+448h+var_328], rbx
0x180056538  mov     [rsp+448h+var_2D8], rbx
0x180056540  setnz   [rsp+448h+var_337]
0x180056548  lea     rdx, aAt; "at"
0x18005654f  lea     rcx, [rsp+448h+var_220]; this
0x180056557  call    ??0RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@QEAA@PEBG@Z; Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::RequestTelemetryOperation(ushort const *)
0x18005655c  nop
0x18005655d  mov     rax, rbx
0x180056560  neg     rax
0x180056563  sbb     rcx, rcx
0x180056566  lea     rax, [rsp+448h+var_220]
0x18005656e  and     rcx, rax
0x180056571  mov     [rsp+448h+var_250], rcx
0x180056579  mov     [rsp+448h+var_244], sil
0x180056581  lea     r14d, [rsi+1]
0x180056585  mov     [rsp+448h+var_267], r14b
0x18005658d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x180056594  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x180056599  test    al, al
0x18005659b  jnz     short loc_1800565D1
0x18005659d  mov     ecx, cs:_tls_index
0x1800565a3  mov     rax, gs:58h
0x1800565ac  mov     rbx, [rax+rcx*8]
0x1800565b0  mov     eax, 0Ch
0x1800565b5  cmp     [rax+rbx], sil
0x1800565b9  jnz     short loc_1800565C0
0x1800565bb  call    __dyn_tls_on_demand_init
0x1800565c0  mov     edi, 20h ; ' '
0x1800565c5  lea     rcx, [rsp+448h+var_250]
0x1800565cd  mov     [rdi+rbx], rcx
0x1800565d1  mov     [rsp+448h+var_260], rsi
0x1800565d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x1800565e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x1800565e5  test    al, al
0x1800565e7  jz      short loc_180056640
0x1800565e9  mov     ecx, 10h; Size
0x1800565ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800565f3  mov     [rsp+448h+var_258], rax
0x1800565fb  lea     rdx, aAt; "at"
0x180056602  mov     rcx, rax; this
0x180056605  call    ??0ScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@QEAA@PEBG@Z; Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation::ScopedRequestTelemetryOperation(ushort const *)
0x18005660a  nop
0x18005660b  mov     [rsp+448h+var_358], rax
0x180056613  mov     [rsp+448h+var_374], 8
0x18005661e  lea     rdx, [rsp+448h+var_358]
0x180056626  lea     rcx, [rsp+448h+var_260]
0x18005662e  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x180056633  lea     rcx, [rsp+448h+var_358]
0x18005663b  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180056640  mov     qword ptr [rsp+448h+var_288.LowPart], rsi
0x180056648  mov     [rsp+448h+var_380], rsi
0x180056650  mov     [rsp+448h+var_318], esi
0x180056657  mov     rbx, rsi
0x18005665a  mov     [rsp+448h+var_298], rbx
0x180056662  mov     [rsp+448h+var_290], rsi
0x18005666a  mov     [rsp+448h+var_B8], si
0x180056672  mov     [rsp+448h+var_B0], rsi
0x18005667a  mov     [rsp+448h+var_A8], rsi
0x180056682  mov     [rsp+448h+var_A0], rsi
0x18005668a  mov     [rsp+448h+var_98], si
0x180056692  mov     [rsp+448h+var_90], rsi
0x18005669a  mov     [rsp+448h+var_88], esi
0x1800566a1  mov     [rsp+448h+var_80], rsi
0x1800566a9  mov     [rsp+448h+var_78], esi
0x1800566b0  xorps   xmm0, xmm0
0x1800566b3  xor     eax, eax
0x1800566b5  movups  [rsp+448h+var_70], xmm0
0x1800566bd  movups  [rsp+448h+var_60], xmm0
0x1800566c5  mov     [rsp+448h+var_50], rax
0x1800566cd  lea     rax, [rsp+448h+var_380]
0x1800566d5  mov     [rsp+448h+var_258], rax
0x1800566dd  lea     rcx, [rsp+448h+var_1E8]; this
0x1800566e5  call    ??0ServiceExecutionContext@@QEAA@XZ; ServiceExecutionContext::ServiceExecutionContext(void)
0x1800566ea  nop
0x1800566eb  mov     [rsp+448h+var_338], sil
0x1800566f3  mov     [rsp+448h+var_2B8], rsi
0x1800566fb  mov     qword ptr [rsp+448h+bIgnoreCase], r13
0x180056700  lea     r9, aRequestflagsVa; "requestFlags value: 0x%llx"
0x180056707  mov     r8d, 104Ah; unsigned int
0x18005670d  mov     rdx, r15; char *
0x180056710  mov     ecx, 5; unsigned __int8
0x180056715  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005671a  cmp     [rsp+448h+var_2A8], rsi
0x180056722  jz      short loc_180056733
0x180056724  bt      r13, 0Fh
0x180056729  mov     byte ptr [rsp+448h+var_378+1], sil
0x180056731  jnb     short loc_18005673B
0x180056733  mov     byte ptr [rsp+448h+var_378+1], r14b
0x18005673b  mov     rax, 480000000h
0x180056745  test    rax, r13
0x180056748  setnz   [rsp+448h+var_336]
0x180056750  mov     [rsp+448h+var_2E8], rsi
0x180056758  mov     rdi, [rsp+448h+var_360]
0x180056760  test    rdi, rdi
0x180056763  jz      short loc_180056767
0x180056765  mov     [rdi], esi
0x180056767  mov     r9, [rsp+448h+var_370]
0x18005676f  test    r9, r9
0x180056772  jz      short loc_180056777
0x180056774  mov     [r9], rsi
0x180056777  cmp     [rsp+448h+var_2C0], rsi
0x18005677f  jnz     short loc_1800567A3
0x180056781  cmp     [rsp+448h+var_34C], esi
0x180056788  jbe     short loc_1800567A3
0x18005678a  mov     [rsp+448h+var_388], 80070057h
0x180056795  mov     r13d, 3
0x18005679b  mov     r12, r9
0x18005679e  jmp     loc_1800585FE
0x1800567a3  xor     edx, edx; struct ATL::CAccessToken *
0x1800567a5  lea     rcx, [rsp+448h+var_2E8]; this
0x1800567ad  call    ?ImpersonateClient@CAutoImpersonateClient@@QEAAJPEAVCAccessToken@ATL@@@Z; CAutoImpersonateClient::ImpersonateClient(ATL::CAccessToken *)
0x1800567b2  mov     [rsp+448h+var_388], eax
0x1800567b9  test    eax, eax
0x1800567bb  jns     short loc_1800567E8
0x1800567bd  lea     rcx, aHrClientImpers_1; "hr = client.ImpersonateClient()"
0x1800567c4  mov     r8d, 106Dh; unsigned int
0x1800567ca  mov     qword ptr [rsp+448h+bIgnoreCase], rcx; char *
0x1800567cf  mov     r9d, eax; int
0x1800567d2  mov     rdx, r12; char *
0x1800567d5  mov     rcx, r15; char *
0x1800567d8  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x1800567dd  mov     r13d, 3
0x1800567e3  jmp     loc_1800585F6
0x1800567e8  lea     rdx, [rsp+448h+var_288]; struct _LUID *
0x1800567f0  lea     rcx, [rsp+448h+var_2E8]; this
0x1800567f8  call    ?GetLogonId@CAutoImpersonateClient@@QEAAJAEAU_LUID@@@Z; CAutoImpersonateClient::GetLogonId(_LUID &)
0x1800567fd  mov     [rsp+448h+var_388], eax
0x180056804  test    eax, eax
0x180056806  jns     short loc_180056817
0x180056808  lea     rcx, aHrClientGetlog; "hr = client.GetLogonId(logonId)"
0x18005680f  mov     r8d, 106Eh
0x180056815  jmp     short loc_1800567CA
0x180056817  lea     rdx, [rsp+448h+var_318]; int *
0x18005681f  lea     rcx, [rsp+448h+var_2E8]; this
0x180056827  call    ?IsImpersonatingSystem@CAutoImpersonateClient@@QEAAJAEAH@Z; CAutoImpersonateClient::IsImpersonatingSystem(int &)
0x18005682c  mov     [rsp+448h+var_388], eax
0x180056833  test    eax, eax
0x180056835  jns     short loc_180056846
0x180056837  lea     rcx, aHrClientIsimpe; "hr = client.IsImpersonatingSystem(isSys"...
0x18005683e  mov     r8d, 106Fh
0x180056844  jmp     short loc_1800567CA
0x180056846  mov     rdi, [rsp+448h+var_280]
0x18005684e  test    rdi, rdi
0x180056851  jz      short loc_180056860
0x180056853  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x180056858  mov     ecx, [rax+110h]
0x18005685e  mov     [rdi], ecx
0x180056860  cmp     cs:byte_1801C4558, sil
0x180056867  jnz     loc_18005690D
0x18005686d  mov     [rsp+448h+var_358], rsi
0x180056875  lea     r8, [rsp+448h+var_358]
0x18005687d  xor     edx, edx
0x18005687f  lea     rcx, [rsp+448h+var_1E8]
0x180056887  call    ?GetSystemHardwareID@DeviceIdHelpers@@SAJPEAVIServiceExecutionContext@@_KAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; DeviceIdHelpers::GetSystemHardwareID(IServiceExecutionContext *,unsigned __int64,CAutoRefPtr<CSingleIdentity> &)
0x18005688c  mov     edi, eax
0x18005688e  test    eax, eax
0x180056890  jns     short loc_1800568C1
0x180056892  mov     [rsp+448h+bIgnoreCase], eax
0x180056896  lea     r9, aDeviceidhelper_5; "DeviceIdHelpers::GetSystemHardwareID (0"...
0x18005689d  mov     r8d, 107Eh; unsigned int
0x1800568a3  mov     rdx, r15; char *
0x1800568a6  mov     ecx, 2; unsigned __int8
0x1800568ab  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800568b0  cmp     edi, 80043513h
0x1800568b6  jnz     short loc_180056900
0x1800568b8  mov     cs:byte_1801C4558, r14b
0x1800568bf  jmp     short loc_180056900
0x1800568c1  cmp     cs:byte_1801C4559, sil
0x1800568c8  jnz     short loc_180056900
0x1800568ca  lea     rcx, [rsp+448h+var_1E8]; struct IServiceExecutionContext *
0x1800568d2  call    ?UpdateDeviceTpmInfo@DeviceIdHelpers@@SAJPEAVIServiceExecutionContext@@@Z; DeviceIdHelpers::UpdateDeviceTpmInfo(IServiceExecutionContext *)
0x1800568d7  test    eax, eax
0x1800568d9  jns     short loc_180056900
0x1800568db  mov     [rsp+448h+bIgnoreCase], eax
0x1800568df  lea     r9, aDeviceidhelper_3; "DeviceIdHelpers::UpdateDeviceTpmInfo (0"...
0x1800568e6  mov     r8d, 1089h; unsigned int
0x1800568ec  mov     rdx, r15; char *
0x1800568ef  mov     ecx, 2; unsigned __int8
0x1800568f4  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800568f9  mov     cs:byte_1801C4559, r14b
0x180056900  lea     rcx, [rsp+448h+var_358]
0x180056908  call    ?Deinit@?$CAutoRefPtr@VCSingleIdentity@@@@IEAAXXZ; CAutoRefPtr<CSingleIdentity>::Deinit(void)
0x18005690d  mov     rcx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x180056914  add     rcx, 1F0h
0x18005691b  lea     r9, [rsp+448h+var_380]
0x180056923  mov     rdi, [rsp+448h+var_2B0]
0x18005692b  mov     r8, rdi
0x18005692e  lea     rdx, [rsp+448h+var_288]
0x180056936  call    ?GetSingleIdentity@CIdentityStore@@QEAAJAEAU_LUID@@PEAXAEAV?$CAutoRefPtr@VCSingleIdentity@@@@@Z; CIdentityStore::GetSingleIdentity(_LUID &,void *,CAutoRefPtr<CSingleIdentity> &)
0x18005693b  mov     [rsp+448h+var_388], eax
0x180056942  test    eax, eax
0x180056944  jns     short loc_180056971
0x180056946  lea     rcx, aHrGPppcrlGetid_29; "hr = g_pPPCRL->GetIdentityStore()->GetS"...
0x18005694d  mov     r8d, 1092h; unsigned int
0x180056953  mov     r9d, eax; int
0x180056956  mov     qword ptr [rsp+448h+bIgnoreCase], rcx; char *
0x18005695b  mov     rdx, r12; char *
0x18005695e  mov     rcx, r15; char *
0x180056961  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x180056966  mov     r13d, 3
0x18005696c  jmp     loc_1800585EE
0x180056971  mov     rdx, [rsp+448h+var_380]
0x180056979  test    rdx, rdx
0x18005697c  jnz     short loc_1800569A0
0x18005697e  mov     r9d, 80004003h
0x180056984  mov     [rsp+448h+var_388], r9d
0x18005698c  lea     rax, aPidentityNullp; "pIdentity != nullptr"
0x180056993  mov     qword ptr [rsp+448h+bIgnoreCase], rax
0x180056998  mov     r8d, 1093h
0x18005699e  jmp     short loc_18005695B
0x1800569a0  mov     eax, 0C0000100h
0x1800569a5  test    rax, r13
0x1800569a8  jnz     loc_180056A43
0x1800569ae  cmp     [rsp+448h+var_2C0], rsi
0x1800569b6  jz      loc_180056A43
0x1800569bc  mov     r13d, esi
0x1800569bf  cmp     [rsp+448h+var_34C], esi
0x1800569c6  jbe     short loc_180056A3B
0x1800569c8  mov     rdi, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x1800569cf  mov     rax, [rdx]
0x1800569d2  mov     rcx, rdx
0x1800569d5  mov     rax, [rax+50h]
0x1800569d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569de  test    eax, eax
0x1800569e0  setz    cl
0x1800569e3  mov     eax, r13d
0x1800569e6  lea     rdx, [rax+rax*4]
0x1800569ea  mov     byte ptr [rsp+448h+bIgnoreCase], cl; bool
0x1800569ee  mov     r9, [rsp+448h+var_380]; struct ISingleIdentity *
0x1800569f6  mov     rax, [rsp+448h+var_2C0]
0x1800569fe  mov     r8, [rax+rdx*8+8]; unsigned __int16 *
0x180056a03  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x180056a07  lea     rcx, [rdi+908h]; this
0x180056a0e  call    ?CheckNegativeCache@NegativeCacheManager@@QEAAJPEBG0PEAVISingleIdentity@@_N@Z; NegativeCacheManager::CheckNegativeCache(ushort const *,ushort const *,ISingleIdentity *,bool)
0x180056a13  mov     [rsp+448h+var_388], eax
0x180056a1a  test    eax, eax
0x180056a1c  js      short loc_180056A6D
0x180056a1e  add     r13d, r14d
0x180056a21  mov     rdx, [rsp+448h+var_380]; struct ISingleIdentity *
0x180056a29  cmp     r13d, [rsp+448h+var_34C]
0x180056a31  jb      short loc_1800569C8
  ... truncated ...
```
