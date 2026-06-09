# CPassportClientLibrary::Initialize(char const *)

- ea: `0x18005ceb0`
- end: `0x18005d7c4`
- name: `?Initialize@CPassportClientLibrary@@QEAAJPEBD@Z`
- size: `2324`
- prototype: `__int64 __fastcall(CPassportClientLibrary *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ba4f0`

## callees

- `0x18000c050`
- `0x18000ed04`
- `0x1800151c4`
- `0x180015860`
- `0x180015fdc`
- `0x180017af0`
- `0x180019690`
- `0x18001a9c0`
- `0x18001ad00`
- `0x180035400`
- `0x18004b4d4`
- `0x18004f13c`
- `0x18005cd10`
- `0x18005ceb0`
- `0x18005d7cc`
- `0x1800a3fec`
- `0x1800a6e7c`
- `0x1800a6ee8`
- `0x1800c5a90`

## string_xrefs

- `0x18005d792`: `Local\Identity CRL v2 File Access`
- `0x18005cf1e`: `onecoreuap\ds\ext\live\identity\ntservice\lib\svccommon\passportclientlibrary.cpp`
- `0x18005d042`: `Could not get WLID_AUTHURL from config. 0x%x`
- `0x18005d0b1`: `DeviceChangeService`
- `0x18005d085`: `Could not get Enterprise WLID_AUTHURL from config. 0x%x`
- `0x18005d0f4`: `EnterpriseDeviceChangeService`
- `0x18005d0c8`: `Could not get DeviceChangeService from config. 0x%x`
- `0x18005d13d`: `DeviceAddService`
- `0x18005d10b`: `Could not get EnterpriseDeviceChangeService from config. 0x%x`
- `0x18005d189`: `EnterpriseDeviceAddService`
- `0x18005d154`: `Could not get DeviceAddService from config. 0x%x`
- `0x18005d1d5`: `GetUserKeyDataService`
- `0x18005d1a0`: `Could not get EnterpriseDeviceAddService from config. 0x%x`
- `0x18005d1ec`: `Could not get GetUserKeyDataService from config. 0x%x`
- `0x18005d238`: `Could not get ManageLoginKeys from config. 0x%x`
- `0x18005d284`: `Could not get ManageApprover from config. 0x%x`
- `0x18005d2d0`: `Could not get ListSessions from config. 0x%x`
- `0x18005d34e`: `GetAppDataService`
- `0x18005d31c`: `Could not get ApproveSession from config. 0x%x`
- `0x18005d397`: `DeviceAssociateService`
- `0x18005d365`: `Could not get GetAppDataService from config. 0x%x`
- `0x18005d3e0`: `EnterpriseDeviceAssociateService`
- `0x18005d3ae`: `Could not get DeviceAssociateService from config. 0x%x`
- `0x18005d429`: `DeviceDisassociateService`
- `0x18005d3f7`: `Could not get EnterpriseDeviceAssociateService from config. 0x%x`
- `0x18005d472`: `EnterpriseDeviceDisassociateService`
- `0x18005d440`: `Could not get DeviceDisassociateService from config. 0x%x`
- `0x18005d4bb`: `DeviceUpdateService`
- `0x18005d489`: `Could not get EnterpriseDeviceDisassociateService from config. 0x%x`
- `0x18005d504`: `EnterpriseDeviceUpdateService`
- `0x18005d4d2`: `Could not get DeviceUpdateService from config. 0x%x`
- `0x18005d54d`: `DeviceQueryService`
- `0x18005d51b`: `Could not get EnterpriseDeviceUpdateService from config. 0x%x`
- `0x18005d596`: `EnterpriseDeviceQueryService`
- `0x18005d564`: `Could not get DeviceQueryService from config. 0x%x`
- `0x18005d5df`: `DeviceEnumerateService`
- `0x18005d5ad`: `Could not get EnterpriseDeviceQueryService from config. 0x%x`
- `0x18005d628`: `EnterpriseDeviceEnumerateService`
- `0x18005d5f6`: `Could not get DeviceEnumerateService from config. 0x%x`
- `0x18005d671`: `ResolveUserService`
- `0x18005d63f`: `Could not get EnterpriseDeviceEnumerateService from config. 0x%x`
- `0x18005d6ba`: `EnterpriseResolveUserService`
- `0x18005d688`: `Could not get ResolveUserService from config. 0x%x`
- `0x18005d6d1`: `Could not get EnterpriseResolveUserService from config. 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CPassportClientLibrary::Initialize(CPassportClientLibrary *this, const char *a2)
{
  CPassportClientLibrary *v2; // rbx
  int v3; // eax
  int v4; // edi
  CClientConfigDataCacheManager *v5; // rax
  struct IClientConfig *v6; // rdx
  int v7; // ecx
  int ServiceURIFromConfig; // eax
  int v9; // ecx
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int v15; // ecx
  int v16; // eax
  int v17; // ecx
  int v18; // eax
  int v19; // ecx
  int v20; // eax
  int v21; // ecx
  int v22; // eax
  int v23; // ecx
  int v24; // eax
  int v25; // ecx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // ecx
  int v30; // eax
  int v31; // ecx
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  int v35; // ecx
  int v36; // eax
  int v37; // ecx
  int v38; // eax
  int v39; // ecx
  int v40; // eax
  int v41; // ecx
  int v42; // eax
  int v43; // ecx
  int v44; // eax
  int v45; // ecx
  int v46; // eax
  int v47; // ecx
  int v48; // eax
  int v49; // ecx
  int v50; // eax
  int v51; // ecx
  int v52; // eax
  int v53; // ecx
  int v54; // eax
  char *v56; // [rsp+20h] [rbp-48h]
  char *v57; // [rsp+20h] [rbp-48h]
  char *v58; // [rsp+20h] [rbp-48h]
  char *v59; // [rsp+20h] [rbp-48h]
  char *v60; // [rsp+20h] [rbp-48h]
  char *v61; // [rsp+20h] [rbp-48h]
  char *v62; // [rsp+20h] [rbp-48h]
  char *v63; // [rsp+20h] [rbp-48h]
  char *v64; // [rsp+20h] [rbp-48h]
  char *v65; // [rsp+20h] [rbp-48h]
  char *v66; // [rsp+20h] [rbp-48h]
  char *v67; // [rsp+20h] [rbp-48h]
  char *v68; // [rsp+20h] [rbp-48h]
  char *v69; // [rsp+20h] [rbp-48h]
  char *v70; // [rsp+20h] [rbp-48h]
  char *v71; // [rsp+20h] [rbp-48h]
  char *v72; // [rsp+20h] [rbp-48h]
  char *v73; // [rsp+20h] [rbp-48h]
  char *v74; // [rsp+20h] [rbp-48h]
  char *v75; // [rsp+20h] [rbp-48h]
  char *v76; // [rsp+20h] [rbp-48h]
  char *v77; // [rsp+20h] [rbp-48h]
  char *v78; // [rsp+20h] [rbp-48h]
  char *v79; // [rsp+20h] [rbp-48h]
  char *v80; // [rsp+20h] [rbp-48h]
  _BYTE v81[8]; // [rsp+30h] [rbp-38h] BYREF
  _QWORD v82[6]; // [rsp+38h] [rbp-30h] BYREF
  int v83; // [rsp+A0h] [rbp+38h] BYREF
  int v84; // [rsp+A4h] [rbp+3Ch]
  char v85; // [rsp+A8h] [rbp+40h] BYREF
  char v86; // [rsp+B0h] [rbp+48h] BYREF
  char v87; // [rsp+B8h] [rbp+50h] BYREF

  v84 = HIDWORD(this);
  v2 = g_pPPCRL;
  v83 = 0;
  if ( dword_1801C7038 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 8LL) )
  {
    Init_thread_header(&dword_1801C7038);
    if ( dword_1801C7038 == -1 )
    {
      CClientConfigData::CClientConfigData((CClientConfigData *)qword_1801C23E8);
      ATL::CSimpleStringT<unsigned short,0>::SetString(qword_1801C24E8, L"Local\\Identity CRL v2 File Access");
      atexit(CPassportClientLibrary::Initialize_::_2_::_dynamic_atexit_destructor_for__s_CrlConfig__);
      Init_thread_footer(&dword_1801C7038);
    }
  }
  v82[0] = "CPassportClientLibrary::Initialize";
  v82[1] = &v83;
  v82[2] = 0;
  v82[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    "CPassportClientLibrary::Initialize",
    (const char *)0xC0,
    0,
    (const unsigned __int16 *)v56);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v81);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v87);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
  if ( _InterlockedIncrement((volatile signed __int32 *)v2 + 2) > 1 )
  {
    v83 = 294980;
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
      "CPassportClientLibrary::Initialize",
      0xCCu,
      294980,
      "InterlockedIncrement((LONG*)&m_dwInitialized) <= 1");
LABEL_58:
    v4 = v83;
    goto LABEL_59;
  }
  InitializeGlobalBSTRConstants();
  *((_DWORD *)v2 + 324) = 1;
  ATL::CSimpleStringT<char,0>::SetString((char *)v2 + 16, "{DF60E2DF-88AD-4526-AE21-83D130EF0F68}");
  v83 = 0;
  TracePrintW(
    5u,
    "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
    0xD9u,
    L"Initializing cryptographic provider...");
  v3 = CPassportClientLibrary::InitializeCryptProvider(v2);
  v83 = v3;
  if ( v3 >= 0 )
  {
    v5 = CClientConfigDataCacheManager::theConfigDataManager();
    v4 = CClientConfigDataCacheManager::Initialize(v5, v6);
    v83 = v4;
    if ( v4 >= 0 )
    {
      ServiceURIFromConfig = CPassportClientLibrary::GetServiceURIFromConfig(
                               v7,
                               (unsigned int)L"WLIDSTS_WCF",
                               (int)v2 + 24,
                               (int)v2 + 32,
                               (__int64)v2 + 40);
      v83 = ServiceURIFromConfig;
      if ( ServiceURIFromConfig < 0 )
      {
        LODWORD(v58) = ServiceURIFromConfig;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0xEDu,
          L"Could not get WLID_AUTHURL from config. 0x%x",
          v58);
        v83 = 0;
      }
      v10 = CPassportClientLibrary::GetServiceURIFromConfig(
              v9,
              (unsigned int)L"EnterpriseWLIDSTS_WCF",
              (int)v2 + 48,
              (int)v2 + 56,
              (__int64)v2 + 64);
      v83 = v10;
      if ( v10 < 0 )
      {
        LODWORD(v59) = v10;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0xF5u,
          L"Could not get Enterprise WLID_AUTHURL from config. 0x%x",
          v59);
        v83 = 0;
      }
      v12 = CPassportClientLibrary::GetServiceURIFromConfig(
              v11,
              (unsigned int)L"DeviceChangeService",
              (int)v2 + 72,
              (int)v2 + 80,
              (__int64)v2 + 88);
      v83 = v12;
      if ( v12 < 0 )
      {
        LODWORD(v60) = v12;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0xFDu,
          L"Could not get DeviceChangeService from config. 0x%x",
          v60);
        v83 = 0;
      }
      v14 = CPassportClientLibrary::GetServiceURIFromConfig(
              v13,
              (unsigned int)L"EnterpriseDeviceChangeService",
              (int)v2 + 96,
              (int)v2 + 104,
              (__int64)v2 + 112);
      v83 = v14;
      if ( v14 < 0 )
      {
        LODWORD(v61) = v14;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x105u,
          L"Could not get EnterpriseDeviceChangeService from config. 0x%x",
          v61);
        v83 = 0;
      }
      v16 = CPassportClientLibrary::GetServiceURIFromConfig(
              v15,
              (unsigned int)L"DeviceAddService",
              (int)v2 + 120,
              (int)v2 + 128,
              (__int64)v2 + 136);
      v83 = v16;
      if ( v16 < 0 )
      {
        LODWORD(v62) = v16;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x10Du,
          L"Could not get DeviceAddService from config. 0x%x",
          v62);
        v83 = 0;
      }
      v18 = CPassportClientLibrary::GetServiceURIFromConfig(
              v17,
              (unsigned int)L"EnterpriseDeviceAddService",
              (int)v2 + 144,
              (int)v2 + 152,
              (__int64)v2 + 160);
      v83 = v18;
      if ( v18 < 0 )
      {
        LODWORD(v63) = v18;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x115u,
          L"Could not get EnterpriseDeviceAddService from config. 0x%x",
          v63);
        v83 = 0;
      }
      v20 = CPassportClientLibrary::GetServiceURIFromConfig(
              v19,
              (unsigned int)L"GetUserKeyDataService",
              (int)v2 + 168,
              (int)v2 + 176,
              (__int64)v2 + 184);
      v83 = v20;
      if ( v20 < 0 )
      {
        LODWORD(v64) = v20;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x11Du,
          L"Could not get GetUserKeyDataService from config. 0x%x",
          v64);
        v83 = 0;
      }
      v22 = CPassportClientLibrary::GetServiceURIFromConfig(
              v21,
              (unsigned int)L"ManageLoginKeys",
              (int)v2 + 192,
              (int)v2 + 200,
              (__int64)v2 + 208);
      v83 = v22;
      if ( v22 < 0 )
      {
        LODWORD(v65) = v22;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x126u,
          L"Could not get ManageLoginKeys from config. 0x%x",
          v65);
        v83 = 0;
      }
      v24 = CPassportClientLibrary::GetServiceURIFromConfig(
              v23,
              (unsigned int)L"ManageApprover",
              (int)v2 + 216,
              (int)v2 + 224,
              (__int64)v2 + 232);
      v83 = v24;
      if ( v24 < 0 )
      {
        LODWORD(v66) = v24;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x12Fu,
          L"Could not get ManageApprover from config. 0x%x",
          v66);
        v83 = 0;
      }
      v26 = CPassportClientLibrary::GetServiceURIFromConfig(
              v25,
              (unsigned int)L"ListSessions",
              (int)v2 + 240,
              (int)v2 + 248,
              (__int64)v2 + 256);
      v83 = v26;
      if ( v26 < 0 )
      {
        LODWORD(v67) = v26;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x138u,
          L"Could not get ListSessions from config. 0x%x",
          v67);
        v83 = 0;
      }
      v28 = CPassportClientLibrary::GetServiceURIFromConfig(
              v27,
              (unsigned int)L"ApproveSession",
              (int)v2 + 264,
              (int)v2 + 272,
              (__int64)v2 + 280);
      v83 = v28;
      if ( v28 < 0 )
      {
        LODWORD(v68) = v28;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x141u,
          L"Could not get ApproveSession from config. 0x%x",
          v68);
        v83 = 0;
      }
      v30 = CPassportClientLibrary::GetServiceURIFromConfig(
              v29,
              (unsigned int)L"GetAppDataService",
              (int)v2 + 288,
              (int)v2 + 296,
              (__int64)&v85);
      v83 = v30;
      if ( v30 < 0 )
      {
        LODWORD(v69) = v30;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x14Du,
          L"Could not get GetAppDataService from config. 0x%x",
          v69);
        v83 = 0;
      }
      v32 = CPassportClientLibrary::GetServiceURIFromConfig(
              v31,
              (unsigned int)L"DeviceAssociateService",
              (int)v2 + 304,
              (int)v2 + 312,
              (__int64)&v85);
      v83 = v32;
      if ( v32 < 0 )
      {
        LODWORD(v70) = v32;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x155u,
          L"Could not get DeviceAssociateService from config. 0x%x",
          v70);
        v83 = 0;
      }
      v34 = CPassportClientLibrary::GetServiceURIFromConfig(
              v33,
              (unsigned int)L"EnterpriseDeviceAssociateService",
              (int)v2 + 320,
              (int)v2 + 328,
              (__int64)&v85);
      v83 = v34;
      if ( v34 < 0 )
      {
        LODWORD(v71) = v34;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x15Du,
          L"Could not get EnterpriseDeviceAssociateService from config. 0x%x",
          v71);
        v83 = 0;
      }
      v36 = CPassportClientLibrary::GetServiceURIFromConfig(
              v35,
              (unsigned int)L"DeviceDisassociateService",
              (int)v2 + 336,
              (int)v2 + 344,
              (__int64)&v85);
      v83 = v36;
      if ( v36 < 0 )
      {
        LODWORD(v72) = v36;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x165u,
          L"Could not get DeviceDisassociateService from config. 0x%x",
          v72);
        v83 = 0;
      }
      v38 = CPassportClientLibrary::GetServiceURIFromConfig(
              v37,
              (unsigned int)L"EnterpriseDeviceDisassociateService",
              (int)v2 + 352,
              (int)v2 + 360,
              (__int64)&v85);
      v83 = v38;
      if ( v38 < 0 )
      {
        LODWORD(v73) = v38;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x16Du,
          L"Could not get EnterpriseDeviceDisassociateService from config. 0x%x",
          v73);
        v83 = 0;
      }
      v40 = CPassportClientLibrary::GetServiceURIFromConfig(
              v39,
              (unsigned int)L"DeviceUpdateService",
              (int)v2 + 368,
              (int)v2 + 376,
              (__int64)&v85);
      v83 = v40;
      if ( v40 < 0 )
      {
        LODWORD(v74) = v40;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x175u,
          L"Could not get DeviceUpdateService from config. 0x%x",
          v74);
        v83 = 0;
      }
      v42 = CPassportClientLibrary::GetServiceURIFromConfig(
              v41,
              (unsigned int)L"EnterpriseDeviceUpdateService",
              (int)v2 + 384,
              (int)v2 + 392,
              (__int64)&v85);
      v83 = v42;
      if ( v42 < 0 )
      {
        LODWORD(v75) = v42;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x17Du,
          L"Could not get EnterpriseDeviceUpdateService from config. 0x%x",
          v75);
        v83 = 0;
      }
      v44 = CPassportClientLibrary::GetServiceURIFromConfig(
              v43,
              (unsigned int)L"DeviceQueryService",
              (int)v2 + 400,
              (int)v2 + 408,
              (__int64)&v85);
      v83 = v44;
      if ( v44 < 0 )
      {
        LODWORD(v76) = v44;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x185u,
          L"Could not get DeviceQueryService from config. 0x%x",
          v76);
        v83 = 0;
      }
      v46 = CPassportClientLibrary::GetServiceURIFromConfig(
              v45,
              (unsigned int)L"EnterpriseDeviceQueryService",
              (int)v2 + 416,
              (int)v2 + 424,
              (__int64)&v85);
      v83 = v46;
      if ( v46 < 0 )
      {
        LODWORD(v77) = v46;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x18Du,
          L"Could not get EnterpriseDeviceQueryService from config. 0x%x",
          v77);
        v83 = 0;
      }
      v48 = CPassportClientLibrary::GetServiceURIFromConfig(
              v47,
              (unsigned int)L"DeviceEnumerateService",
              (int)v2 + 432,
              (int)v2 + 440,
              (__int64)&v85);
      v83 = v48;
      if ( v48 < 0 )
      {
        LODWORD(v78) = v48;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x195u,
          L"Could not get DeviceEnumerateService from config. 0x%x",
          v78);
        v83 = 0;
      }
      v50 = CPassportClientLibrary::GetServiceURIFromConfig(
              v49,
              (unsigned int)L"EnterpriseDeviceEnumerateService",
              (int)v2 + 448,
              (int)v2 + 456,
              (__int64)&v85);
      v83 = v50;
      if ( v50 < 0 )
      {
        LODWORD(v79) = v50;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x19Du,
          L"Could not get EnterpriseDeviceEnumerateService from config. 0x%x",
          v79);
        v83 = 0;
      }
      v52 = CPassportClientLibrary::GetServiceURIFromConfig(
              v51,
              (unsigned int)L"ResolveUserService",
              (int)v2 + 464,
              (int)v2 + 472,
              (__int64)&v85);
      v83 = v52;
      if ( v52 < 0 )
      {
        LODWORD(v80) = v52;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x1A5u,
          L"Could not get ResolveUserService from config. 0x%x",
          v80);
        v83 = 0;
      }
      v54 = CPassportClientLibrary::GetServiceURIFromConfig(
              v53,
              (unsigned int)L"EnterpriseResolveUserService",
              (int)v2 + 480,
              (int)v2 + 488,
              (__int64)&v85);
      v83 = v54;
      if ( v54 < 0 )
      {
        LODWORD(v57) = v54;
        TracePrintW(
          2u,
          "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
          0x1ADu,
          L"Could not get EnterpriseResolveUserService from config. 0x%x",
          v57);
        v83 = 0;
      }
      TracePrintW(
        5u,
        "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
        0x1B2u,
        L"Initializing TLS...");
      v4 = 0;
      v83 = 0;
    }
  }
  else
  {
    LODWORD(v57) = v3;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
      0xDDu,
      L"Unable to initialize cryptographic provider 0x%x.",
      v57);
    v4 = v83;
  }
  if ( v4 < 0 )
  {
    LODWORD(v57) = v4;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\ntservice\\lib\\svccommon\\passportclientlibrary.cpp",
      0x1BCu,
      L"Failure - unrolling initialization. 0x%x",
      v57);
    CPassportClientLibrary::Uninitialize(v2);
    goto LABEL_58;
  }
LABEL_59:
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v86);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(&v87);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(v81);
  CTraceFuncW<long>::~CTraceFuncW<long>(v82);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18005ceb0  mov     [rsp-30h+arg_0], rcx
0x18005ceb5  push    rbp
0x18005ceb6  push    rbx
0x18005ceb7  push    rsi
0x18005ceb8  push    rdi
0x18005ceb9  push    r14
0x18005cebb  push    r15
0x18005cebd  mov     rbp, rsp
0x18005cec0  sub     rsp, 68h
0x18005cec4  mov     rbx, cs:?g_pPPCRL@@3PEAVCPassportClientLibrary@@EA; CPassportClientLibrary * g_pPPCRL
0x18005cecb  xor     esi, esi
0x18005cecd  mov     dword ptr [rbp+arg_0], esi
0x18005ced0  mov     ecx, cs:_tls_index
0x18005ced6  mov     rax, gs:58h
0x18005cedf  mov     edx, 8
0x18005cee4  mov     rax, [rax+rcx*8]
0x18005cee8  mov     eax, [rdx+rax]
0x18005ceeb  cmp     cs:dword_1801C7038, eax
0x18005cef1  jg      loc_18005D76C
0x18005cef7  lea     rdi, aCpassportclien_2; "CPassportClientLibrary::Initialize"
0x18005cefe  mov     [rbp+var_30], rdi
0x18005cf02  lea     rax, [rbp+arg_0]
0x18005cf06  mov     [rbp+var_28], rax
0x18005cf0a  mov     [rbp+var_20], rsi
0x18005cf0e  mov     [rbp+var_18], rsi
0x18005cf12  xor     r9d, r9d; unsigned int
0x18005cf15  mov     r8d, 0C0h; char *
0x18005cf1b  mov     rdx, rdi; char *
0x18005cf1e  lea     r14, aOnecoreuapDsEx_80; "onecoreuap\\ds\\ext\\live\\identity\\nt"...
0x18005cf25  mov     rcx, r14; this
0x18005cf28  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18005cf2d  nop
0x18005cf2e  lea     rcx, [rbp+var_38]
0x18005cf32  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005cf37  nop
0x18005cf38  lea     rcx, [rbp+arg_18]
0x18005cf3c  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005cf41  nop
0x18005cf42  lea     rcx, [rbp+arg_10]
0x18005cf46  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18005cf4b  nop
0x18005cf4c  mov     r15d, 1
0x18005cf52  mov     eax, r15d
0x18005cf55  lock xadd [rbx+8], eax
0x18005cf5a  add     eax, r15d
0x18005cf5d  cmp     eax, r15d
0x18005cf60  jle     short loc_18005CF8E
0x18005cf62  mov     r9d, 48044h; int
0x18005cf68  mov     dword ptr [rbp+arg_0], r9d
0x18005cf6c  lea     rax, aInterlockedinc; "InterlockedIncrement((LONG*)&m_dwInitia"...
0x18005cf73  mov     [rsp+68h+var_48], rax; char *
0x18005cf78  mov     r8d, 0CCh; unsigned int
0x18005cf7e  mov     rdx, rdi; char *
0x18005cf81  mov     rcx, r14; char *
0x18005cf84  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18005cf89  jmp     loc_18005D733
0x18005cf8e  call    ?InitializeGlobalBSTRConstants@@YAXXZ; InitializeGlobalBSTRConstants(void)
0x18005cf93  mov     [rbx+510h], r15d
0x18005cf9a  lea     rcx, [rbx+10h]
0x18005cf9e  lea     rdx, aDf60e2df88ad45; "{DF60E2DF-88AD-4526-AE21-83D130EF0F68}"
0x18005cfa5  call    ?SetString@?$CSimpleStringT@D$0A@@ATL@@QEAAXPEBD@Z; ATL::CSimpleStringT<char,0>::SetString(char const *)
0x18005cfaa  mov     dword ptr [rbp+arg_0], esi
0x18005cfad  lea     r9, aInitializingCr; "Initializing cryptographic provider..."
0x18005cfb4  mov     r8d, 0D9h; unsigned int
0x18005cfba  mov     rdx, r14; char *
0x18005cfbd  mov     ecx, 5; unsigned __int8
0x18005cfc2  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005cfc7  mov     rcx, rbx; this
0x18005cfca  call    ?InitializeCryptProvider@CPassportClientLibrary@@IEAAJXZ; CPassportClientLibrary::InitializeCryptProvider(void)
0x18005cfcf  mov     dword ptr [rbp+arg_0], eax
0x18005cfd2  mov     r15d, 2
0x18005cfd8  test    eax, eax
0x18005cfda  jns     short loc_18005D000
0x18005cfdc  mov     dword ptr [rsp+68h+var_48], eax
0x18005cfe0  lea     r9, aUnableToInitia; "Unable to initialize cryptographic prov"...
0x18005cfe7  mov     r8d, 0DDh; unsigned int
0x18005cfed  mov     rdx, r14; char *
0x18005cff0  mov     ecx, r15d; unsigned __int8
0x18005cff3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005cff8  mov     edi, dword ptr [rbp+arg_0]
0x18005cffb  jmp     loc_18005D70B
0x18005d000  call    ?theConfigDataManager@CClientConfigDataCacheManager@@SAAEAV1@XZ; CClientConfigDataCacheManager::theConfigDataManager(void)
0x18005d005  mov     rcx, rax; this
0x18005d008  call    ?Initialize@CClientConfigDataCacheManager@@QEAAJPEAVIClientConfig@@@Z; CClientConfigDataCacheManager::Initialize(IClientConfig *)
0x18005d00d  mov     edi, eax
0x18005d00f  mov     dword ptr [rbp+arg_0], eax
0x18005d012  test    eax, eax
0x18005d014  js      loc_18005D70B
0x18005d01a  lea     rax, [rbx+28h]
0x18005d01e  lea     r9, [rbx+20h]
0x18005d022  lea     r8, [rbx+18h]
0x18005d026  mov     [rsp+68h+var_48], rax
0x18005d02b  lea     rdx, aWlidstsWcf; "WLIDSTS_WCF"
0x18005d032  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d037  mov     dword ptr [rbp+arg_0], eax
0x18005d03a  test    eax, eax
0x18005d03c  jns     short loc_18005D05D
0x18005d03e  mov     dword ptr [rsp+68h+var_48], eax
0x18005d042  lea     r9, aCouldNotGetWli; "Could not get WLID_AUTHURL from config."...
0x18005d049  mov     r8d, 0EDh; unsigned int
0x18005d04f  mov     rdx, r14; char *
0x18005d052  mov     ecx, r15d; unsigned __int8
0x18005d055  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d05a  mov     dword ptr [rbp+arg_0], esi
0x18005d05d  lea     rax, [rbx+40h]
0x18005d061  lea     r9, [rbx+38h]
0x18005d065  lea     r8, [rbx+30h]
0x18005d069  mov     [rsp+68h+var_48], rax
0x18005d06e  lea     rdx, aEnterprisewlid; "EnterpriseWLIDSTS_WCF"
0x18005d075  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d07a  mov     dword ptr [rbp+arg_0], eax
0x18005d07d  test    eax, eax
0x18005d07f  jns     short loc_18005D0A0
0x18005d081  mov     dword ptr [rsp+68h+var_48], eax
0x18005d085  lea     r9, aCouldNotGetEnt_4; "Could not get Enterprise WLID_AUTHURL f"...
0x18005d08c  mov     r8d, 0F5h; unsigned int
0x18005d092  mov     rdx, r14; char *
0x18005d095  mov     ecx, r15d; unsigned __int8
0x18005d098  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d09d  mov     dword ptr [rbp+arg_0], esi
0x18005d0a0  lea     rax, [rbx+58h]
0x18005d0a4  lea     r9, [rbx+50h]
0x18005d0a8  lea     r8, [rbx+48h]
0x18005d0ac  mov     [rsp+68h+var_48], rax
0x18005d0b1  lea     rdx, aDevicechangese; "DeviceChangeService"
0x18005d0b8  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d0bd  mov     dword ptr [rbp+arg_0], eax
0x18005d0c0  test    eax, eax
0x18005d0c2  jns     short loc_18005D0E3
0x18005d0c4  mov     dword ptr [rsp+68h+var_48], eax
0x18005d0c8  lea     r9, aCouldNotGetDev_4; "Could not get DeviceChangeService from "...
0x18005d0cf  mov     r8d, 0FDh; unsigned int
0x18005d0d5  mov     rdx, r14; char *
0x18005d0d8  mov     ecx, r15d; unsigned __int8
0x18005d0db  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d0e0  mov     dword ptr [rbp+arg_0], esi
0x18005d0e3  lea     rax, [rbx+70h]
0x18005d0e7  lea     r9, [rbx+68h]
0x18005d0eb  lea     r8, [rbx+60h]
0x18005d0ef  mov     [rsp+68h+var_48], rax
0x18005d0f4  lea     rdx, aEnterprisedevi_1; "EnterpriseDeviceChangeService"
0x18005d0fb  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d100  mov     dword ptr [rbp+arg_0], eax
0x18005d103  test    eax, eax
0x18005d105  jns     short loc_18005D126
0x18005d107  mov     dword ptr [rsp+68h+var_48], eax
0x18005d10b  lea     r9, aCouldNotGetEnt_3; "Could not get EnterpriseDeviceChangeSer"...
0x18005d112  mov     r8d, 105h; unsigned int
0x18005d118  mov     rdx, r14; char *
0x18005d11b  mov     ecx, r15d; unsigned __int8
0x18005d11e  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d123  mov     dword ptr [rbp+arg_0], esi
0x18005d126  lea     rax, [rbx+88h]
0x18005d12d  lea     r9, [rbx+80h]
0x18005d134  lea     r8, [rbx+78h]
0x18005d138  mov     [rsp+68h+var_48], rax
0x18005d13d  lea     rdx, aDeviceaddservi; "DeviceAddService"
0x18005d144  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d149  mov     dword ptr [rbp+arg_0], eax
0x18005d14c  test    eax, eax
0x18005d14e  jns     short loc_18005D16F
0x18005d150  mov     dword ptr [rsp+68h+var_48], eax
0x18005d154  lea     r9, aCouldNotGetDev_3; "Could not get DeviceAddService from con"...
0x18005d15b  mov     r8d, 10Dh; unsigned int
0x18005d161  mov     rdx, r14; char *
0x18005d164  mov     ecx, r15d; unsigned __int8
0x18005d167  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d16c  mov     dword ptr [rbp+arg_0], esi
0x18005d16f  lea     rax, [rbx+0A0h]
0x18005d176  lea     r9, [rbx+98h]
0x18005d17d  lea     r8, [rbx+90h]
0x18005d184  mov     [rsp+68h+var_48], rax
0x18005d189  lea     rdx, aEnterprisedevi_0; "EnterpriseDeviceAddService"
0x18005d190  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d195  mov     dword ptr [rbp+arg_0], eax
0x18005d198  test    eax, eax
0x18005d19a  jns     short loc_18005D1BB
0x18005d19c  mov     dword ptr [rsp+68h+var_48], eax
0x18005d1a0  lea     r9, aCouldNotGetEnt_2; "Could not get EnterpriseDeviceAddServic"...
0x18005d1a7  mov     r8d, 115h; unsigned int
0x18005d1ad  mov     rdx, r14; char *
0x18005d1b0  mov     ecx, r15d; unsigned __int8
0x18005d1b3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d1b8  mov     dword ptr [rbp+arg_0], esi
0x18005d1bb  lea     rax, [rbx+0B8h]
0x18005d1c2  lea     r9, [rbx+0B0h]
0x18005d1c9  lea     r8, [rbx+0A8h]
0x18005d1d0  mov     [rsp+68h+var_48], rax
0x18005d1d5  lea     rdx, aGetuserkeydata; "GetUserKeyDataService"
0x18005d1dc  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d1e1  mov     dword ptr [rbp+arg_0], eax
0x18005d1e4  test    eax, eax
0x18005d1e6  jns     short loc_18005D207
0x18005d1e8  mov     dword ptr [rsp+68h+var_48], eax
0x18005d1ec  lea     r9, aCouldNotGetGet_0; "Could not get GetUserKeyDataService fro"...
0x18005d1f3  mov     r8d, 11Dh; unsigned int
0x18005d1f9  mov     rdx, r14; char *
0x18005d1fc  mov     ecx, r15d; unsigned __int8
0x18005d1ff  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d204  mov     dword ptr [rbp+arg_0], esi
0x18005d207  lea     rax, [rbx+0D0h]
0x18005d20e  lea     r9, [rbx+0C8h]
0x18005d215  lea     r8, [rbx+0C0h]
0x18005d21c  mov     [rsp+68h+var_48], rax
0x18005d221  lea     rdx, aManageloginkey; "ManageLoginKeys"
0x18005d228  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d22d  mov     dword ptr [rbp+arg_0], eax
0x18005d230  test    eax, eax
0x18005d232  jns     short loc_18005D253
0x18005d234  mov     dword ptr [rsp+68h+var_48], eax
0x18005d238  lea     r9, aCouldNotGetMan_0; "Could not get ManageLoginKeys from conf"...
0x18005d23f  mov     r8d, 126h; unsigned int
0x18005d245  mov     rdx, r14; char *
0x18005d248  mov     ecx, r15d; unsigned __int8
0x18005d24b  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d250  mov     dword ptr [rbp+arg_0], esi
0x18005d253  lea     rax, [rbx+0E8h]
0x18005d25a  lea     r9, [rbx+0E0h]
0x18005d261  lea     r8, [rbx+0D8h]
0x18005d268  mov     [rsp+68h+var_48], rax
0x18005d26d  lea     rdx, aManageapprover_4; "ManageApprover"
0x18005d274  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d279  mov     dword ptr [rbp+arg_0], eax
0x18005d27c  test    eax, eax
0x18005d27e  jns     short loc_18005D29F
0x18005d280  mov     dword ptr [rsp+68h+var_48], eax
0x18005d284  lea     r9, aCouldNotGetMan; "Could not get ManageApprover from confi"...
0x18005d28b  mov     r8d, 12Fh; unsigned int
0x18005d291  mov     rdx, r14; char *
0x18005d294  mov     ecx, r15d; unsigned __int8
0x18005d297  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d29c  mov     dword ptr [rbp+arg_0], esi
0x18005d29f  lea     rax, [rbx+100h]
0x18005d2a6  lea     r9, [rbx+0F8h]
0x18005d2ad  lea     r8, [rbx+0F0h]
0x18005d2b4  mov     [rsp+68h+var_48], rax
0x18005d2b9  lea     rdx, aListsessions; "ListSessions"
0x18005d2c0  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d2c5  mov     dword ptr [rbp+arg_0], eax
0x18005d2c8  test    eax, eax
0x18005d2ca  jns     short loc_18005D2EB
0x18005d2cc  mov     dword ptr [rsp+68h+var_48], eax
0x18005d2d0  lea     r9, aCouldNotGetLis; "Could not get ListSessions from config."...
0x18005d2d7  mov     r8d, 138h; unsigned int
0x18005d2dd  mov     rdx, r14; char *
0x18005d2e0  mov     ecx, r15d; unsigned __int8
0x18005d2e3  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d2e8  mov     dword ptr [rbp+arg_0], esi
0x18005d2eb  lea     rax, [rbx+118h]
0x18005d2f2  lea     r9, [rbx+110h]
0x18005d2f9  lea     r8, [rbx+108h]
0x18005d300  mov     [rsp+68h+var_48], rax
0x18005d305  lea     rdx, aApprovesession; "ApproveSession"
0x18005d30c  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d311  mov     dword ptr [rbp+arg_0], eax
0x18005d314  test    eax, eax
0x18005d316  jns     short loc_18005D337
0x18005d318  mov     dword ptr [rsp+68h+var_48], eax
0x18005d31c  lea     r9, aCouldNotGetApp; "Could not get ApproveSession from confi"...
0x18005d323  mov     r8d, 141h; unsigned int
0x18005d329  mov     rdx, r14; char *
0x18005d32c  mov     ecx, r15d; unsigned __int8
0x18005d32f  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d334  mov     dword ptr [rbp+arg_0], esi
0x18005d337  lea     r9, [rbx+128h]
0x18005d33e  lea     r8, [rbx+120h]
0x18005d345  lea     rax, [rbp+arg_8]
0x18005d349  mov     [rsp+68h+var_48], rax
0x18005d34e  lea     rdx, aGetappdataserv; "GetAppDataService"
0x18005d355  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d35a  mov     dword ptr [rbp+arg_0], eax
0x18005d35d  test    eax, eax
0x18005d35f  jns     short loc_18005D380
0x18005d361  mov     dword ptr [rsp+68h+var_48], eax
0x18005d365  lea     r9, aCouldNotGetGet; "Could not get GetAppDataService from co"...
0x18005d36c  mov     r8d, 14Dh; unsigned int
0x18005d372  mov     rdx, r14; char *
0x18005d375  mov     ecx, r15d; unsigned __int8
0x18005d378  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d37d  mov     dword ptr [rbp+arg_0], esi
0x18005d380  lea     r9, [rbx+138h]
0x18005d387  lea     r8, [rbx+130h]
0x18005d38e  lea     rax, [rbp+arg_8]
0x18005d392  mov     [rsp+68h+var_48], rax
0x18005d397  lea     rdx, aDeviceassociat_2; "DeviceAssociateService"
0x18005d39e  call    ?GetServiceURIFromConfig@CPassportClientLibrary@@QEAAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1AEAG@Z; CPassportClientLibrary::GetServiceURIFromConfig(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort &)
0x18005d3a3  mov     dword ptr [rbp+arg_0], eax
0x18005d3a6  test    eax, eax
0x18005d3a8  jns     short loc_18005D3C9
0x18005d3aa  mov     dword ptr [rsp+68h+var_48], eax
0x18005d3ae  lea     r9, aCouldNotGetDev_5; "Could not get DeviceAssociateService fr"...
0x18005d3b5  mov     r8d, 155h; unsigned int
0x18005d3bb  mov     rdx, r14; char *
0x18005d3be  mov     ecx, r15d; unsigned __int8
0x18005d3c1  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18005d3c6  mov     dword ptr [rbp+arg_0], esi
0x18005d3c9  lea     r9, [rbx+148h]
0x18005d3d0  lea     r8, [rbx+140h]
0x18005d3d7  lea     rax, [rbp+arg_8]
0x18005d3db  mov     [rsp+68h+var_48], rax
  ... truncated ...
```
