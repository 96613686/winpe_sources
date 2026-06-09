# Smb2RefreshRegistryValue

- ea: `0x140077c0c`
- end: `0x140078dda`
- name: `Smb2RefreshRegistryValue`
- size: `4558`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140061f44`
- `0x14007667c`

## callees

- `0x140001008`
- `0x14001a554`
- `0x14001c768`
- `0x1400224b8`
- `0x140023338`
- `0x140024f9c`
- `0x14002533c`
- `0x1400253b4`
- `0x140025414`
- `0x140025fc4`
- `0x140038490`
- `0x140077c0c`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140078ab4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140078ab4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140078b71`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140078b71`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140077cb7`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140077cb7`
- `srvnet!SrvLibGetDWord` at `0x140077c56`
- `srvnet!SrvLibGetDWord` at `0x140077c9d`
- `srvnet!SrvLibGetDWord` at `0x140077cd9`
- `srvnet!SrvLibGetDWord` at `0x140077d07`
- `srvnet!SrvLibGetDWord` at `0x140077d32`
- `srvnet!SrvLibGetDWord` at `0x140077d87`
- `srvnet!SrvLibGetDWord` at `0x140077dd7`
- `srvnet!SrvLibGetDWord` at `0x140077e05`
- `srvnet!SrvLibGetDWord` at `0x140077e37`
- `srvnet!SrvLibGetDWord` at `0x140077e75`
- `srvnet!SrvLibGetDWord` at `0x140077ec5`
- `srvnet!SrvLibGetDWord` at `0x140077ef3`
- `srvnet!SrvLibGetDWord` at `0x140077f22`
- `srvnet!SrvLibGetDWord` at `0x140077f50`
- `srvnet!SrvLibGetDWord` at `0x140077f88`
- `srvnet!SrvLibGetDWord` at `0x140077fbd`
- `srvnet!SrvLibGetDWord` at `0x140077ff7`
- `srvnet!SrvLibGetDWord` at `0x14007802c`
- `srvnet!SrvLibGetDWord` at `0x140078064`
- `srvnet!SrvLibGetDWord` at `0x14007809a`
- `srvnet!SrvLibGetDWord` at `0x1400780ca`
- `srvnet!SrvLibGetDWord` at `0x1400780f9`
- `srvnet!SrvLibGetDWord` at `0x140078141`
- `srvnet!SrvLibGetDWord` at `0x140078171`
- `srvnet!SrvLibGetDWord` at `0x1400781a1`
- `srvnet!SrvLibGetDWord` at `0x1400781cb`
- `srvnet!SrvLibGetDWord` at `0x1400781ff`
- `srvnet!SrvLibGetDWord` at `0x140078241`
- `srvnet!SrvLibGetDWord` at `0x14007826b`
- `srvnet!SrvLibGetDWord` at `0x140078299`
- `srvnet!SrvLibGetDWord` at `0x1400782f4`
- `srvnet!SrvLibGetDWord` at `0x140078312`
- `srvnet!SrvLibGetDWord` at `0x14007833a`
- `srvnet!SrvLibGetDWord` at `0x140078358`
- `srvnet!SrvLibGetDWord` at `0x140078380`
- `srvnet!SrvLibGetDWord` at `0x1400783b8`
- `srvnet!SrvLibGetDWord` at `0x1400783f8`
- `srvnet!SrvLibGetDWord` at `0x14007845d`
- `srvnet!SrvLibGetDWord` at `0x14007848a`
- `srvnet!SrvLibGetDWord` at `0x1400784b1`
- `srvnet!SrvLibGetDWord` at `0x140078543`
- `srvnet!SrvLibGetDWord` at `0x140078579`
- `srvnet!SrvLibGetDWord` at `0x1400785b1`
- `srvnet!SrvLibGetDWord` at `0x1400785e8`
- `srvnet!SrvLibGetDWord` at `0x14007863c`
- `srvnet!SrvLibGetDWord` at `0x140078682`
- `srvnet!SrvLibGetDWord` at `0x1400786bc`
- `srvnet!SrvLibGetDWord` at `0x1400786e7`
- `srvnet!SrvLibGetDWord` at `0x140078716`
- `srvnet!SrvLibGetDWord` at `0x140078745`
- `srvnet!SrvLibGetDWord` at `0x140078778`
- `srvnet!SrvLibGetDWord` at `0x1400787c8`
- `srvnet!SrvLibGetDWord` at `0x1400787fa`
- `srvnet!SrvLibGetDWord` at `0x140078825`
- `srvnet!SrvLibGetDWord` at `0x140078854`
- `srvnet!SrvLibGetDWord` at `0x1400788db`
- `srvnet!SrvLibGetDWord` at `0x140078914`
- `srvnet!SrvLibGetDWord` at `0x14007894d`
- `srvnet!SrvLibGetDWord` at `0x14007896a`
- `srvnet!SrvLibGetDWord` at `0x1400789c9`
- `srvnet!SrvLibGetDWord` at `0x1400789e3`
- `srvnet!SrvLibGetDWord` at `0x140078a44`
- `srvnet!SrvLibGetDWord` at `0x140078a73`
- `srvnet!SrvLibGetDWord` at `0x140078a91`
- `srvnet!SrvLibGetDWord` at `0x140078b8b`
- `srvnet!SrvLibGetDWord` at `0x140078ba9`
- `srvnet!SrvLibGetDWord` at `0x140078bd8`
- `srvnet!SrvLibGetDWord` at `0x140078bf6`
- `srvnet!SrvLibGetDWord` at `0x140078c1e`
- `srvnet!SrvLibGetDWord` at `0x140078c3c`
- `srvnet!SrvLibGetDWord` at `0x140078cef`
- `srvnet!SrvLibGetDWord` at `0x140078d86`
- `srvnet!SrvLibGetDWord` at `0x140077c56`
- `srvnet!SrvLibGetDWord` at `0x140077c9d`
- `srvnet!SrvLibGetDWord` at `0x140077cd9`
- `srvnet!SrvLibGetDWord` at `0x140077d07`
- `srvnet!SrvLibGetDWord` at `0x140077d32`
- `srvnet!SrvLibGetDWord` at `0x140077d87`
- `srvnet!SrvLibGetDWord` at `0x140077dd7`
- `srvnet!SrvLibGetDWord` at `0x140077e05`
- `srvnet!SrvLibGetDWord` at `0x140077e37`
- `srvnet!SrvLibGetDWord` at `0x140077e75`
- `srvnet!SrvLibGetDWord` at `0x140077ec5`
- `srvnet!SrvLibGetDWord` at `0x140077ef3`
- `srvnet!SrvLibGetDWord` at `0x140077f22`
- `srvnet!SrvLibGetDWord` at `0x140077f50`
- `srvnet!SrvLibGetDWord` at `0x140077f88`
- `srvnet!SrvLibGetDWord` at `0x140077fbd`
- `srvnet!SrvLibGetDWord` at `0x140077ff7`
- `srvnet!SrvLibGetDWord` at `0x14007802c`
- `srvnet!SrvLibGetDWord` at `0x140078064`
- `srvnet!SrvLibGetDWord` at `0x14007809a`
- `srvnet!SrvLibGetDWord` at `0x1400780ca`
- `srvnet!SrvLibGetDWord` at `0x1400780f9`
- `srvnet!SrvLibGetDWord` at `0x140078141`
- `srvnet!SrvLibGetDWord` at `0x140078171`
- `srvnet!SrvLibGetDWord` at `0x1400781a1`
- `srvnet!SrvLibGetDWord` at `0x1400781cb`
- `srvnet!SrvLibGetDWord` at `0x1400781ff`
- `srvnet!SrvLibGetDWord` at `0x140078241`
- `srvnet!SrvLibGetDWord` at `0x14007826b`
- `srvnet!SrvLibGetDWord` at `0x140078299`
- `srvnet!SrvLibGetDWord` at `0x1400782f4`
- `srvnet!SrvLibGetDWord` at `0x140078312`
- `srvnet!SrvLibGetDWord` at `0x14007833a`
- `srvnet!SrvLibGetDWord` at `0x140078358`
- `srvnet!SrvLibGetDWord` at `0x140078380`
- `srvnet!SrvLibGetDWord` at `0x1400783b8`
- `srvnet!SrvLibGetDWord` at `0x1400783f8`
- `srvnet!SrvLibGetDWord` at `0x14007845d`
- `srvnet!SrvLibGetDWord` at `0x14007848a`
- `srvnet!SrvLibGetDWord` at `0x1400784b1`
- `srvnet!SrvLibGetDWord` at `0x140078543`
- `srvnet!SrvLibGetDWord` at `0x140078579`
- `srvnet!SrvLibGetDWord` at `0x1400785b1`
- `srvnet!SrvLibGetDWord` at `0x1400785e8`
- `srvnet!SrvLibGetDWord` at `0x14007863c`
- `srvnet!SrvLibGetDWord` at `0x140078682`
- `srvnet!SrvLibGetDWord` at `0x1400786bc`
- `srvnet!SrvLibGetDWord` at `0x1400786e7`
- `srvnet!SrvLibGetDWord` at `0x140078716`
- `srvnet!SrvLibGetDWord` at `0x140078745`
- `srvnet!SrvLibGetDWord` at `0x140078778`
- `srvnet!SrvLibGetDWord` at `0x1400787c8`
- `srvnet!SrvLibGetDWord` at `0x1400787fa`
- `srvnet!SrvLibGetDWord` at `0x140078825`
- `srvnet!SrvLibGetDWord` at `0x140078854`
- `srvnet!SrvLibGetDWord` at `0x1400788db`
- `srvnet!SrvLibGetDWord` at `0x140078914`
- `srvnet!SrvLibGetDWord` at `0x14007894d`
- `srvnet!SrvLibGetDWord` at `0x14007896a`
- `srvnet!SrvLibGetDWord` at `0x1400789c9`
- `srvnet!SrvLibGetDWord` at `0x1400789e3`
- `srvnet!SrvLibGetDWord` at `0x140078a44`
- `srvnet!SrvLibGetDWord` at `0x140078a73`
- `srvnet!SrvLibGetDWord` at `0x140078a91`
- `srvnet!SrvLibGetDWord` at `0x140078b8b`
- `srvnet!SrvLibGetDWord` at `0x140078ba9`
- `srvnet!SrvLibGetDWord` at `0x140078bd8`
- `srvnet!SrvLibGetDWord` at `0x140078bf6`
- `srvnet!SrvLibGetDWord` at `0x140078c1e`
- `srvnet!SrvLibGetDWord` at `0x140078c3c`
- `srvnet!SrvLibGetDWord` at `0x140078cef`
- `srvnet!SrvLibGetDWord` at `0x140078d86`
- `srvnet!SmbCryptoReadCipherSuiteOrderPolicySetting` at `0x140078aeb`
- `srvnet!SmbCryptoReadCipherSuiteOrderPolicySetting` at `0x140078aeb`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140077d5e`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140077da2`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140077e93`
- `srvnet!SrvLibQueryLicensingDWord` at `0x14007842a`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140078d3b`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140077d5e`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140077da2`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140077e93`
- `srvnet!SrvLibQueryLicensingDWord` at `0x14007842a`
- `srvnet!SrvLibQueryLicensingDWord` at `0x140078d3b`
- `srvnet!SrvAdminRefreshAllowedServerNameList` at `0x140078874`
- `srvnet!SrvAdminRefreshAllowedServerNameList` at `0x140078874`
- `srvnet!SrvAdminRefreshFsctlPropertyList` at `0x140078880`
- `srvnet!SrvAdminRefreshFsctlPropertyList` at `0x140078880`
- `srvnet!SrvAdminRefreshPipeList` at `0x1400788fa`
- `srvnet!SrvAdminRefreshPipeList` at `0x1400788fa`
- `srvnet!SmbCryptoIsCipherSuiteOrderPresentPolicySetting` at `0x140078ac3`
- `srvnet!SmbCryptoIsCipherSuiteOrderPresentPolicySetting` at `0x140078ac3`
- `srvnet!SrvLibIsDomainJoined` at `0x140078d08`
- `srvnet!SrvLibIsDomainJoined` at `0x140078d08`

## string_xrefs

- `0x140077c35`: `\Registry\Machine\System\CurrentControlSet\Services\LanmanServer\Parameters`
- `0x140077e22`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x14007893c`: `\Registry\Machine\Software\Policies\Microsoft\Windows\LanmanServer`
- `0x140077c96`: `MaxAsyncDecryptionThreads`
- `0x140077d57`: `SMBServer-AllowRemoteShadowCopyAccess`
- `0x140077d80`: `RequireSecuritySignature`
- `0x140077dc7`: `RequireSecuritySignatureForLoopback`
- `0x140077ebe`: `EnableInlineSendIOCompletion`
- `0x140077ee9`: `ForceMdlWrite`
- `0x1400780c0`: `EnableSequentialRead`
- `0x14007828f`: `SmbDirectDataPlacementSecurity`
- `0x1400782ed`: `EnableCompressedTraffic`
- `0x14007830b`: `EnableCompressedTraffic`
- `0x140078333`: `DisableCompression`
- `0x140078351`: `DisableCompression`
- `0x140078379`: `RejectUnencryptedAccess`
- `0x1400787b3`: `AllowOpeningDosNames`

## pseudocode

```c
__int64 Smb2RefreshRegistryValue()
{
  char v0; // bl
  __int64 v1; // rcx
  ULONG v2; // eax
  bool v3; // al
  int DWord; // eax
  ULONG v5; // ecx
  int v6; // eax
  ULONG v7; // ecx
  bool v8; // al
  __int64 v9; // rax
  ULONG v10; // ecx
  bool v11; // al
  bool v12; // al
  bool v13; // al
  ULONG v14; // eax
  int v15; // eax
  ULONG v16; // ecx
  __int64 v17; // rcx
  char v18; // al
  char v19; // al
  ULONG v20; // ecx
  char v21; // al
  ULONG v22; // ecx
  int v23; // eax
  bool v24; // al
  bool v25; // al
  int refreshed; // eax
  bool v27; // al
  int v28; // r8d
  __int16 v29; // cx
  int v30; // r8d
  __int16 v31; // cx
  bool v32; // al
  int CipherSuiteOrderPolicySetting; // eax
  unsigned int v34; // edi
  char v35; // di
  __int64 v36; // r8
  __int64 result; // rax
  __int64 v38; // rcx
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // r8
  ULONG pulResult; // [rsp+30h] [rbp-49h] BYREF
  char v43; // [rsp+34h] [rbp-45h] BYREF
  __int64 v44; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v45[32]; // [rsp+40h] [rbp-39h] BYREF
  __int64 *v46; // [rsp+60h] [rbp-19h]
  __int64 v47; // [rsp+68h] [rbp-11h]
  char *v48; // [rsp+70h] [rbp-9h]
  __int64 v49; // [rsp+78h] [rbp-1h]

  pulResult = 0;
  v0 = 1;
  Smb2Enabled = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"SMB2",
              &pulResult) >= 0 )
  {
    if ( pulResult )
    {
      Smb2Enabled = 1;
    }
    else
    {
      Smb2Enabled = 0;
      if ( byte_14004C339 < 0 )
        McTemplateK0_EtwWriteTransfer(v1, SMB2_EVENT_SMB2_DISABLED);
    }
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MaxAsyncDecryptionThreads",
              &pulResult) < 0 )
    v2 = 2 * KeQueryActiveProcessorCountEx(0xFFFFu);
  else
    v2 = pulResult;
  Smb2MaxAsyncDecryptionThreads = v2;
  v3 = (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DisableLiveDumps",
              &pulResult) < 0
    || pulResult == 0;
  Smb2LiveKernelDumpsEnabled = v3;
  DWord = SrvLibGetDWord(
            L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
            L"StalledIoLiveDumpThresholdInSec",
            &pulResult);
  v5 = 600;
  if ( DWord >= 0 )
    v5 = pulResult;
  Smb2StalledIoLiveDumpThresholdInSeconds = v5;
  v6 = SrvLibGetDWord(
         L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
         L"LiveDumpFlags",
         &pulResult);
  v7 = 0;
  Smb2TimewarpEnabled = 0;
  if ( v6 >= 0 )
    v7 = pulResult;
  Smb2LiveDumpFlags = v7;
  if ( (int)SrvLibQueryLicensingDWord(L"SMBServer-AllowRemoteShadowCopyAccess", &pulResult) >= 0 && pulResult )
    Smb2TimewarpEnabled = 1;
  v8 = ((int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"RequireSecuritySignature",
               &pulResult) >= 0
     || (int)SrvLibQueryLicensingDWord(L"SMBServer-RequireSigningByDefault", &pulResult) >= 0)
    && pulResult != 0;
  Smb2SigningRequired = v8;
  Smb2SigningRequiredForLoopback = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"RequireSecuritySignatureForLoopback",
              &pulResult) >= 0 )
    Smb2SigningRequiredForLoopback = pulResult != 0;
  Smb2ReauthTimeoutInSec = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"ReAuthenticationTimeout",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2ReauthTimeoutInSec = pulResult;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"InvalidAuthenticationDelayTimeInMs",
              &pulResult) >= 0
    || (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"InvalidAuthenticationDelayTimeInMs",
              &pulResult) >= 0 )
  {
    v9 = 10000;
    v10 = 100 * ((pulResult + 50) / 0x64);
    if ( v10 < 0x2710 )
      v9 = v10;
  }
  else
  {
    LODWORD(v44) = 0;
    if ( (int)SrvLibQueryLicensingDWord(L"SMBServer-InvalidAuthenticationDelayTimeInMs", &v44) < 0 )
      goto LABEL_36;
    v9 = 10000;
    if ( (unsigned int)v44 < 0x2710 )
      v9 = (unsigned int)v44;
  }
  Smb2InvalidAuthenticationDelayMs = v9;
LABEL_36:
  v11 = (int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"EnableInlineSendIOCompletion",
               &pulResult) < 0
     || pulResult != 0;
  Smb2EnableInlineSendIOCompletion = v11;
  v12 = (int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"ForceMdlWrite",
               &pulResult) >= 0
     && pulResult != 0;
  Smb2ForceMdlWrite = v12;
  v13 = (int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"EnableNetworkInterfacesCapabilities",
               &pulResult) < 0
     || pulResult != 0;
  Smb2EnableNetworkInterfacesCapabilities = v13;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"AutoDisconnectTimeoutV2",
              &pulResult) < 0 )
  {
    Smb2AutoDisconnectTimeoutInSeconds = 0;
  }
  else
  {
    v14 = 900;
    if ( pulResult < 0x384 )
      v14 = pulResult;
    Smb2AutoDisconnectTimeoutInSeconds = v14;
  }
  v15 = SrvLibGetDWord(
          L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
          L"EnableExtendedTraces",
          &pulResult);
  v16 = 0;
  if ( v15 >= 0 )
    v16 = pulResult;
  Smb2ProviderEnableExtendedTraces = v16;
  Smb2KeepAliveTimeInMin = 2;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"KeepAliveTime",
              &pulResult) >= 0
    && pulResult < 0x1179E )
  {
    Smb2KeepAliveTimeInMin = pulResult;
  }
  Smb2ResilientKeepAliveTimeInSec = 10;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"ResilientKeepAliveTime",
              &pulResult) >= 0
    && pulResult < 0x1179E )
  {
    Smb2ResilientKeepAliveTimeInSec = pulResult;
  }
  Smb2MaxRtInSec = 20;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"SmbMaxRT",
              &pulResult) >= 0 )
    Smb2MaxRtInSec = pulResult;
  Smb2RefreshSnapShotsSchedule = 9000000000LL;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"RefreshSnapShotsSchedule",
              &pulResult) >= 0 )
    Smb2RefreshSnapShotsSchedule = 10000000LL * pulResult;
  Smb2TreatHostAsStableStorage = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"treathostasstablestorage",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2TreatHostAsStableStorage = 1;
  }
  Smb2AllowSequentialRead = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableSequentialRead",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2AllowSequentialRead = 1;
  }
  Smb2LeasingEnabled = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DisableLeasing",
              &pulResult) >= 0 )
  {
    if ( pulResult )
    {
      Smb2LeasingEnabled = 0;
      if ( (byte_14004C339 & 0x40) != 0 )
        McTemplateK0_EtwWriteTransfer(v17, SMB2_EVENT_LEASING_DISABLED);
    }
  }
  Smb2DirLeasingEnabled = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DisableDirLeasing",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2DirLeasingEnabled = 0;
  }
  Smb2DirHandleLeasingEnabled = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableDirHandleLeasing",
              &pulResult) >= 0
    && !pulResult )
  {
    Smb2DirHandleLeasingEnabled = 0;
  }
  Smb2MultiChannelEnabled = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DisableMultiChannel",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2MultiChannelEnabled = 0;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EncryptData",
              &pulResult) < 0
    || (v18 = 1, !pulResult) )
  {
    v18 = 0;
  }
  Smb2EncryptData = v18;
  Smb2EncryptionEnabled = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DisableEncryption",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2EncryptionEnabled = 0;
  }
  Smb2DisableSmbEncryptDataOnSecureConnection = 1;
  if ( Smb2EncryptionEnabled
    && Smb2EncryptData
    && (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DisableSmbEncryptionOnSecureConnection",
              &pulResult) >= 0
    && !pulResult )
  {
    Smb2DisableSmbEncryptDataOnSecureConnection = 0;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableNotifications",
              &pulResult) < 0
    || (v19 = 0, pulResult) )
  {
    v19 = 1;
  }
  Smb2NotificationsEnabled = v19;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"SmbDirectDataPlacementSecurity",
              &pulResult) < 0 )
    goto LABEL_101;
  v20 = pulResult;
  if ( pulResult && pulResult - 1 >= 2 )
  {
    if ( Smb2DirectDataPlacementSecurity != 1 )
    {
      if ( (byte_14004C339 & 0x40) != 0 )
        McTemplateK0qq_EtwWriteTransfer(pulResult);
LABEL_101:
      Smb2DirectDataPlacementSecurity = 1;
    }
  }
  else if ( Smb2DirectDataPlacementSecurity != pulResult )
  {
    if ( (byte_14004C339 & 0x40) != 0 )
    {
      McTemplateK0qq_EtwWriteTransfer(pulResult);
      v20 = pulResult;
    }
    Smb2DirectDataPlacementSecurity = v20;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"EnableCompressedTraffic",
              &pulResult) >= 0
    || (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableCompressedTraffic",
              &pulResult) >= 0 )
  {
    Smb2EnableCompressedTraffic = pulResult != 0;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"DisableCompression",
              &pulResult) >= 0
    || (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DisableCompression",
              &pulResult) >= 0 )
  {
    Smb2CompressionDisabled = pulResult != 0;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"RejectUnencryptedAccess",
              &pulResult) < 0
    || (v21 = 1, pulResult) )
  {
    v21 = 0;
  }
  Smb2AllowUnencryptedAccess = v21;
  Smb2MaxChannelPerSession = 32;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MaxChannelPerSession",
              &pulResult) >= 0
    && pulResult - 1 <= 0x7FFFFFFD )
  {
    Smb2MaxChannelPerSession = pulResult;
  }
  Smb2MaxSessionPerConnection = 0x4000;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MaxSessionPerConnection",
              &pulResult) >= 0
    && pulResult - 1 <= 0x7FFFFFFD )
  {
    Smb2MaxSessionPerConnection = pulResult;
  }
  Smb2HashPublicationEnabled = 0;
  if ( (int)SrvLibQueryLicensingDWord(L"SMBServer-AllowHashPublication", &pulResult) >= 0 && pulResult )
    Smb2HashPublicationEnabled = 1;
  Smb2ResilientMaxTimeoutInSec = 300;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"ResilientTimeout",
              &pulResult) >= 0 )
    Smb2ResilientMaxTimeoutInSec = pulResult;
  Smb2StartIdleTimeoutInSec = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"StartIdleTimeoutInSecond",
              &pulResult) >= 0 )
    Smb2StartIdleTimeoutInSec = pulResult;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"DurableHandleV2TimeoutInSecond",
              &pulResult) < 0 )
  {
    Smb2DurableHandleV2TimeoutInMs = 180000;
  }
  else
  {
    if ( RtlULongLongToULong(1000LL * pulResult, &pulResult) >= 0 )
    {
      v22 = pulResult;
    }
    else
    {
      v22 = -1;
      pulResult = -1;
    }
    v23 = 300000;
    if ( v22 < 0x493E0 )
      v23 = v22;
    Smb2DurableHandleV2TimeoutInMs = v23;
  }
  Smb2PendingClientTimeoutInSec = 120;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"PendingClientTimeoutInSecond",
              &pulResult) >= 0 )
    Smb2PendingClientTimeoutInSec = pulResult;
  if ( Smb2HashPublicationEnabled )
  {
    Smb2HashCacheLevel = 0;
    if ( (int)SrvLibGetDWord(
                L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
                L"HashPublicationForPeerCaching",
                &pulResult) >= 0
      && pulResult - 1 <= 1 )
    {
      Smb2HashCacheLevel = pulResult;
    }
    Smb2HashSupportVersion = 3;
    if ( (int)SrvLibGetDWord(
                L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
                L"HashSupportVersion",
                &pulResult) >= 0
      && pulResult - 1 <= 2 )
    {
      Smb2HashSupportVersion = pulResult;
    }
  }
  else
  {
    Smb2HashCacheLevel = 1;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"SmbServerNameHardeningLevel",
              &pulResult) >= 0
    && pulResult )
  {
    switch ( pulResult )
    {
      case 1u:
        Smb2SpnValidationPolicy = 2;
        goto LABEL_155;
      case 2u:
        Smb2SpnValidationPolicy = 4;
        goto LABEL_155;
      case 3u:
        Smb2SpnValidationPolicy = 1;
        goto LABEL_155;
    }
  }
  Smb2SpnValidationPolicy = 0;
LABEL_155:
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"AsymmetryMode",
              &pulResult) < 0 )
    goto LABEL_159;
  if ( pulResult )
  {
    Smb2SofsAsymmetryMode = 2;
    if ( pulResult == 2 )
      goto LABEL_160;
LABEL_159:
    Smb2SofsAsymmetryMode = 1;
    goto LABEL_160;
  }
  Smb2SofsAsymmetryMode = 0;
LABEL_160:
  Smb2EnableS4U2SelfForClaims = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableS4U2SelfForClaims",
              &pulResult) >= 0 )
  {
    Smb2EnableS4U2SelfForClaims = pulResult;
    if ( pulResult > 2 )
      Smb2EnableS4U2SelfForClaims = 2;
  }
  Smb2CAPRequiresS4U2SelfForClaims = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"CAPRequiresS4U2SelfForClaims",
              &pulResult) >= 0 )
    Smb2CAPRequiresS4U2SelfForClaims = pulResult != 0;
  pulResult = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableSessionPerfCounters",
              &pulResult) >= 0 )
    Smb2SessionPerfCountersEnabled = pulResult != 0;
  Smb2ForceBackchannelInvalidation = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"ForceBackchannel",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2ForceBackchannelInvalidation = 1;
  }
  Smb2SyncRedirectEnabled = 1;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableSyncRedirect",
              &pulResult) >= 0 )
    Smb2SyncRedirectEnabled = pulResult != 0;
  Smb2ShareLockTimeout = 100000000;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"ShareLockTimeout",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2ShareLockTimeout = 10000000LL * pulResult;
  }
  Smb2AllowOpeningDosNames = 0;
  Smb2Livedumps = (unsigned __int8)(byte_1400583AA - 2) <= 1u;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"AllowOpeningDosNames",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2AllowOpeningDosNames = 1;
  }
  if ( Smb2LiveKernelDumpsEnabled
    && (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"LiveDumpsSetting",
              &pulResult) >= 0
    && pulResult )
  {
    Smb2Livedumps = pulResult;
  }
  v24 = (int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"ParseFailureTelemetryEnabled",
               &pulResult) >= 0
     && pulResult != 0;
  ParseFailureTelemetryEnabled = v24;
  v25 = (int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"ParseFailureTelemetryThrottlingEnabled",
               &pulResult) < 0
     || pulResult != 0;
  ParseFailureTelemetryThrottlingEnabled = v25;
  SrvAdminRefreshAllowedServerNameList();
  refreshed = SrvAdminRefreshFsctlPropertyList();
  if ( refreshed < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      35,
      WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids,
      (unsigned int)refreshed);
  }
  Smb2MinSessionKeyCbLength = 0;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MinimumSessionKeyLength",
              &pulResult) >= 0 )
    Smb2MinSessionKeyCbLength = (pulResult + 7) >> 3;
  SrvAdminRefreshPipeList();
  v27 = (int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"ForceSyncRedirectOnAsymmetricShare",
               &pulResult) >= 0
     && pulResult != 0;
  Smb2ForceSyncRedirectOnAsymmetricShare = v27;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"MinSmb2Dialect",
              &pulResult) < 0
    && (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MinSmb2Dialect",
              &pulResult) < 0 )
  {
    MinSmb2DialectConstant = 0;
  }
  else
  {
    v29 = pulResult;
    if ( MinSmb2DialectConstant != (_WORD)pulResult )
    {
      if ( (byte_14004C339 & 0x10) != 0 )
      {
        McTemplateK0zdd_EtwWriteTransfer(
          pulResult,
          (unsigned __int16)MinSmb2DialectConstant,
          v28,
          (unsigned int)L"MinSmb2Dialect",
          MinSmb2DialectConstant,
          pulResult);
        v29 = pulResult;
      }
      MinSmb2DialectConstant = v29;
    }
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"MaxSmb2Dialect",
              &pulResult) < 0
    && (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"MaxSmb2Dialect",
              &pulResult) < 0 )
  {
    MaxSmb2DialectConstant = -1;
  }
  else
  {
    v31 = pulResult;
    if ( MaxSmb2DialectConstant != (_WORD)pulResult )
    {
      if ( (byte_14004C339 & 0x10) != 0 )
      {
        McTemplateK0zdd_EtwWriteTransfer(
          pulResult,
          (unsigned __int16)MaxSmb2DialectConstant,
          v30,
          (unsigned int)L"MaxSmb2Dialect",
          MaxSmb2DialectConstant,
          pulResult);
        v31 = pulResult;
      }
      MaxSmb2DialectConstant = v31;
    }
  }
  v32 = (int)SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"SingleCreditChargePerSpecifiedRequest",
               &pulResult) >= 0
     && pulResult != 0;
  Smb2SingleCreditChargePerSpecifiedRequest = v32;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"EnableAuthRateLimiter",
              &pulResult) >= 0
    || (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"EnableAuthRateLimiter",
              &pulResult) >= 0 )
  {
    Smb2EnableAuthRateLimiter = pulResult != 0;
  }
  ExAcquirePushLockExclusiveEx(&Smb2CipherSuiteOrderLock, 0);
  if ( (unsigned int)SmbCryptoIsCipherSuiteOrderPresentPolicySetting(L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer") == -1073741772 )
  {
    CipherSuiteOrderPolicySetting = SmbCryptoReadCipherSuiteOrderPolicySetting(
                                      L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
                                      &Smb2CipherOrder,
                                      &Smb2CipherOrderCeLength);
    v34 = CipherSuiteOrderPolicySetting;
    if ( CipherSuiteOrderPolicySetting < 0 )
    {
      if ( CipherSuiteOrderPolicySetting == -1073739509 && byte_14004C339 < 0 )
        McTemplateK0z_EtwWriteTransfer();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_11e8a595f18e319c03a7761a299fdc44_Traceguids, v34);
      }
      Smb2CipherOrderCeLength = 4;
      Smb2CipherOrder = (__int128)_mm_load_si128((const __m128i *)&_xmm);
    }
  }
  ExReleasePushLockExclusiveEx(&Smb2CipherSuiteOrderLock, 0);
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"AuditClientDoesNotSupportEncryption",
              &pulResult) >= 0
    || (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"AuditClientDoesNotSupportEncryption",
              &pulResult) >= 0 )
  {
    AuditClientDoesNotSupportEncryption = pulResult != 0;
  }
  v35 = AuditClientDoesNotSupportSigning;
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"AuditClientDoesNotSupportSigning",
              &pulResult) >= 0
    || (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"AuditClientDoesNotSupportSigning",
              &pulResult) >= 0 )
  {
    AuditClientDoesNotSupportSigning = pulResult != 0;
  }
  if ( (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
              L"AuditInsecureGuestLogon",
              &pulResult) >= 0
    || (int)SrvLibGetDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
              L"AuditInsecureGuestLogon",
              &pulResult) >= 0 )
  {
    AuditInsecureGuestLogon = pulResult != 0;
  }
  if ( !v35
    && AuditClientDoesNotSupportSigning
    && (unsigned int)dword_1400583B0 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_1400583B0, 0x400000000000LL, v36) )
  {
    v44 = 0x1000000;
    v46 = &v44;
    v43 = AuditClientDoesNotSupportSigning;
    v47 = 8;
    v48 = &v43;
    v49 = 1;
    tlgWriteTransfer_EtwWriteTransfer(&dword_1400583B0, &unk_140042F68, 0, 0, 4, v45);
  }
  result = SrvLibGetDWord(
             L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\LanmanServer",
             L"RequireWindowsHelloForBusiness",
             &pulResult);
  if ( (int)result < 0 )
  {
    result = SrvLibGetDWord(
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\LanmanServer\\Parameters",
               L"RequireWindowsHelloForBusiness",
               &pulResult);
    if ( (int)result < 0 )
      goto LABEL_254;
  }
  if ( !pulResult )
  {
LABEL_257:
    v0 = 0;
    goto LABEL_258;
  }
  if ( !(unsigned __int8)SrvLibIsDomainJoined() && Microsoft_Windows_SMBServerEnableBits < 0 )
    McTemplateK0q_EtwWriteTransfer(v38, SMB2_EVENT_WHFB_ENFORCEMENT_FAILED, v39, 0);
  if ( (int)SrvLibQueryLicensingDWord(L"SMBServer-RequireWindowsHelloForBusinessNotSupported", &pulResult) < 0 )
  {
LABEL_254:
    result = pulResult;
    goto LABEL_255;
  }
  result = pulResult;
  if ( pulResult )
  {
    if ( Microsoft_Windows_SMBServerEnableBits < 0 )
    {
      McTemplateK0q_EtwWriteTransfer(v40, SMB2_EVENT_WHFB_ENFORCEMENT_FAILED, v41, 1);
      result = pulResult;
    }
    if ( (_DWORD)result )
    {
      pulResult = 0;
      goto LABEL_257;
    }
  }
  result = 1;
  pulResult = 1;
LABEL_255:
  if ( !(_DWORD)result )
    goto LABEL_257;
  result = UpdateMultiSZListSynchronized();
  if ( !pulResult )
    goto LABEL_257;
LABEL_258:
  Smb2RequireWindowsHelloForBusiness = v0;
  return result;
}

```

## disassembly

```asm
0x140077c0c  push    rbp
0x140077c0e  push    rbx
0x140077c0f  push    rsi
0x140077c10  push    rdi
0x140077c11  push    r12
0x140077c13  push    r13
0x140077c15  push    r14
0x140077c17  push    r15
0x140077c19  lea     rbp, [rsp-1Fh]
0x140077c1e  sub     rsp, 98h
0x140077c25  mov     rax, cs:__security_cookie
0x140077c2c  xor     rax, rsp
0x140077c2f  mov     [rbp+57h+var_50], rax
0x140077c33  xor     esi, esi
0x140077c35  lea     r14, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x140077c3c  lea     r8, [rbp+57h+pulResult]
0x140077c40  mov     [rbp+57h+pulResult], esi
0x140077c43  lea     rdx, aSmb2_0; "SMB2"
0x140077c4a  mov     rcx, r14
0x140077c4d  lea     ebx, [rsi+1]
0x140077c50  mov     cs:Smb2Enabled, bl
0x140077c56  call    cs:__imp_SrvLibGetDWord
0x140077c5d  nop     dword ptr [rax+rax+00h]
0x140077c62  test    eax, eax
0x140077c64  js      short loc_140077C8F
0x140077c66  cmp     [rbp+57h+pulResult], esi
0x140077c69  jz      short loc_140077C73
0x140077c6b  mov     cs:Smb2Enabled, bl
0x140077c71  jmp     short loc_140077C8F
0x140077c73  cmp     cs:byte_14004C339, sil
0x140077c7a  mov     cs:Smb2Enabled, sil
0x140077c81  jge     short loc_140077C8F
0x140077c83  lea     rdx, SMB2_EVENT_SMB2_DISABLED
0x140077c8a  call    McTemplateK0_EtwWriteTransfer
0x140077c8f  lea     r8, [rbp+57h+pulResult]
0x140077c93  mov     rcx, r14
0x140077c96  lea     rdx, aMaxasyncdecryp; "MaxAsyncDecryptionThreads"
0x140077c9d  call    cs:__imp_SrvLibGetDWord
0x140077ca4  nop     dword ptr [rax+rax+00h]
0x140077ca9  test    eax, eax
0x140077cab  js      short loc_140077CB2
0x140077cad  mov     eax, [rbp+57h+pulResult]
0x140077cb0  jmp     short loc_140077CC5
0x140077cb2  mov     ecx, 0FFFFh; GroupNumber
0x140077cb7  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140077cbe  nop     dword ptr [rax+rax+00h]
0x140077cc3  add     eax, eax
0x140077cc5  lea     r8, [rbp+57h+pulResult]
0x140077cc9  mov     cs:Smb2MaxAsyncDecryptionThreads, eax
0x140077ccf  lea     rdx, aDisablelivedum; "DisableLiveDumps"
0x140077cd6  mov     rcx, r14
0x140077cd9  call    cs:__imp_SrvLibGetDWord
0x140077ce0  nop     dword ptr [rax+rax+00h]
0x140077ce5  test    eax, eax
0x140077ce7  js      short loc_140077CF1
0x140077ce9  cmp     [rbp+57h+pulResult], esi
0x140077cec  setz    al
0x140077cef  jmp     short loc_140077CF3
0x140077cf1  mov     al, bl
0x140077cf3  lea     r8, [rbp+57h+pulResult]
0x140077cf7  mov     cs:Smb2LiveKernelDumpsEnabled, al
0x140077cfd  lea     rdx, aStallediolived; "StalledIoLiveDumpThresholdInSec"
0x140077d04  mov     rcx, r14
0x140077d07  call    cs:__imp_SrvLibGetDWord
0x140077d0e  nop     dword ptr [rax+rax+00h]
0x140077d13  mov     ecx, 258h
0x140077d18  lea     r8, [rbp+57h+pulResult]
0x140077d1c  test    eax, eax
0x140077d1e  lea     rdx, aLivedumpflags; "LiveDumpFlags"
0x140077d25  cmovns  ecx, [rbp+57h+pulResult]
0x140077d29  mov     cs:Smb2StalledIoLiveDumpThresholdInSeconds, ecx
0x140077d2f  mov     rcx, r14
0x140077d32  call    cs:__imp_SrvLibGetDWord
0x140077d39  nop     dword ptr [rax+rax+00h]
0x140077d3e  mov     ecx, esi
0x140077d40  mov     cs:Smb2TimewarpEnabled, sil
0x140077d47  test    eax, eax
0x140077d49  lea     rdx, [rbp+57h+pulResult]
0x140077d4d  cmovns  ecx, [rbp+57h+pulResult]
0x140077d51  mov     cs:Smb2LiveDumpFlags, ecx
0x140077d57  lea     rcx, aSmbserverAllow; "SMBServer-AllowRemoteShadowCopyAccess"
0x140077d5e  call    cs:__imp_SrvLibQueryLicensingDWord
0x140077d65  nop     dword ptr [rax+rax+00h]
0x140077d6a  test    eax, eax
0x140077d6c  js      short loc_140077D79
0x140077d6e  cmp     [rbp+57h+pulResult], esi
0x140077d71  jz      short loc_140077D79
0x140077d73  mov     cs:Smb2TimewarpEnabled, bl
0x140077d79  lea     r8, [rbp+57h+pulResult]
0x140077d7d  mov     rcx, r14
0x140077d80  lea     rdx, aRequiresecurit_0; "RequireSecuritySignature"
0x140077d87  call    cs:__imp_SrvLibGetDWord
0x140077d8e  nop     dword ptr [rax+rax+00h]
0x140077d93  test    eax, eax
0x140077d95  jns     short loc_140077DB2
0x140077d97  lea     rdx, [rbp+57h+pulResult]
0x140077d9b  lea     rcx, aSmbserverRequi_0; "SMBServer-RequireSigningByDefault"
0x140077da2  call    cs:__imp_SrvLibQueryLicensingDWord
0x140077da9  nop     dword ptr [rax+rax+00h]
0x140077dae  test    eax, eax
0x140077db0  js      short loc_140077DBA
0x140077db2  cmp     [rbp+57h+pulResult], esi
0x140077db5  setnz   al
0x140077db8  jmp     short loc_140077DBD
0x140077dba  mov     al, sil
0x140077dbd  lea     r8, [rbp+57h+pulResult]
0x140077dc1  mov     cs:Smb2SigningRequired, al
0x140077dc7  lea     rdx, aRequiresecurit; "RequireSecuritySignatureForLoopback"
0x140077dce  mov     cs:Smb2SigningRequiredForLoopback, bl
0x140077dd4  mov     rcx, r14
0x140077dd7  call    cs:__imp_SrvLibGetDWord
0x140077dde  nop     dword ptr [rax+rax+00h]
0x140077de3  test    eax, eax
0x140077de5  js      short loc_140077DF1
0x140077de7  cmp     [rbp+57h+pulResult], esi
0x140077dea  setnz   cs:Smb2SigningRequiredForLoopback
0x140077df1  lea     r8, [rbp+57h+pulResult]
0x140077df5  mov     cs:Smb2ReauthTimeoutInSec, esi
0x140077dfb  lea     rdx, aReauthenticati; "ReAuthenticationTimeout"
0x140077e02  mov     rcx, r14
0x140077e05  call    cs:__imp_SrvLibGetDWord
0x140077e0c  nop     dword ptr [rax+rax+00h]
0x140077e11  test    eax, eax
0x140077e13  js      short loc_140077E22
0x140077e15  mov     eax, [rbp+57h+pulResult]
0x140077e18  test    eax, eax
0x140077e1a  jz      short loc_140077E22
0x140077e1c  mov     cs:Smb2ReauthTimeoutInSec, eax
0x140077e22  lea     r12, aRegistryMachin_1; "\\Registry\\Machine\\Software\\Policies"...
0x140077e29  mov     rcx, r12
0x140077e2c  lea     r8, [rbp+57h+pulResult]
0x140077e30  lea     rdx, aInvalidauthent; "InvalidAuthenticationDelayTimeInMs"
0x140077e37  call    cs:__imp_SrvLibGetDWord
0x140077e3e  nop     dword ptr [rax+rax+00h]
0x140077e43  test    eax, eax
0x140077e45  js      short loc_140077E67
0x140077e47  mov     ecx, [rbp+57h+pulResult]
0x140077e4a  mov     eax, 51EB851Fh
0x140077e4f  add     ecx, 32h ; '2'
0x140077e52  mul     ecx
0x140077e54  mov     eax, 2710h
0x140077e59  shr     edx, 5
0x140077e5c  imul    ecx, edx, 64h ; 'd'
0x140077e5f  cmp     ecx, eax
0x140077e61  jnb     short loc_140077EB0
0x140077e63  mov     eax, ecx
0x140077e65  jmp     short loc_140077EB0
0x140077e67  lea     r8, [rbp+57h+pulResult]
0x140077e6b  mov     rcx, r14
0x140077e6e  lea     rdx, aInvalidauthent; "InvalidAuthenticationDelayTimeInMs"
0x140077e75  call    cs:__imp_SrvLibGetDWord
0x140077e7c  nop     dword ptr [rax+rax+00h]
0x140077e81  test    eax, eax
0x140077e83  jns     short loc_140077E47
0x140077e85  lea     rdx, [rbp+57h+var_98]
0x140077e89  mov     dword ptr [rbp+57h+var_98], esi
0x140077e8c  lea     rcx, aSmbserverInval; "SMBServer-InvalidAuthenticationDelayTim"...
0x140077e93  call    cs:__imp_SrvLibQueryLicensingDWord
0x140077e9a  nop     dword ptr [rax+rax+00h]
0x140077e9f  test    eax, eax
0x140077ea1  js      short loc_140077EB7
0x140077ea3  mov     eax, 2710h
0x140077ea8  cmp     dword ptr [rbp+57h+var_98], eax
0x140077eab  jnb     short loc_140077EB0
0x140077ead  mov     eax, dword ptr [rbp+57h+var_98]
0x140077eb0  mov     cs:Smb2InvalidAuthenticationDelayMs, rax
0x140077eb7  lea     r8, [rbp+57h+pulResult]
0x140077ebb  mov     rcx, r14
0x140077ebe  lea     rdx, aEnableinlinese; "EnableInlineSendIOCompletion"
0x140077ec5  call    cs:__imp_SrvLibGetDWord
0x140077ecc  nop     dword ptr [rax+rax+00h]
0x140077ed1  test    eax, eax
0x140077ed3  js      short loc_140077EDD
0x140077ed5  cmp     [rbp+57h+pulResult], esi
0x140077ed8  setnz   al
0x140077edb  jmp     short loc_140077EDF
0x140077edd  mov     al, bl
0x140077edf  lea     r8, [rbp+57h+pulResult]
0x140077ee3  mov     cs:Smb2EnableInlineSendIOCompletion, al
0x140077ee9  lea     rdx, aForcemdlwrite; "ForceMdlWrite"
0x140077ef0  mov     rcx, r14
0x140077ef3  call    cs:__imp_SrvLibGetDWord
0x140077efa  nop     dword ptr [rax+rax+00h]
0x140077eff  test    eax, eax
0x140077f01  js      short loc_140077F0B
0x140077f03  cmp     [rbp+57h+pulResult], esi
0x140077f06  setnz   al
0x140077f09  jmp     short loc_140077F0E
0x140077f0b  mov     al, sil
0x140077f0e  lea     r8, [rbp+57h+pulResult]
0x140077f12  mov     cs:Smb2ForceMdlWrite, al
0x140077f18  lea     rdx, aEnablenetworki; "EnableNetworkInterfacesCapabilities"
0x140077f1f  mov     rcx, r14
0x140077f22  call    cs:__imp_SrvLibGetDWord
0x140077f29  nop     dword ptr [rax+rax+00h]
0x140077f2e  test    eax, eax
0x140077f30  js      short loc_140077F3A
0x140077f32  cmp     [rbp+57h+pulResult], esi
0x140077f35  setnz   al
0x140077f38  jmp     short loc_140077F3C
0x140077f3a  mov     al, bl
0x140077f3c  lea     r8, [rbp+57h+pulResult]
0x140077f40  mov     cs:Smb2EnableNetworkInterfacesCapabilities, al
0x140077f46  lea     rdx, aAutodisconnect; "AutoDisconnectTimeoutV2"
0x140077f4d  mov     rcx, r14
0x140077f50  call    cs:__imp_SrvLibGetDWord
0x140077f57  nop     dword ptr [rax+rax+00h]
0x140077f5c  test    eax, eax
0x140077f5e  js      short loc_140077F74
0x140077f60  mov     eax, 384h
0x140077f65  cmp     [rbp+57h+pulResult], eax
0x140077f68  cmovb   eax, [rbp+57h+pulResult]
0x140077f6c  mov     cs:Smb2AutoDisconnectTimeoutInSeconds, eax
0x140077f72  jmp     short loc_140077F7A
0x140077f74  mov     cs:Smb2AutoDisconnectTimeoutInSeconds, esi
0x140077f7a  lea     r8, [rbp+57h+pulResult]
0x140077f7e  mov     rcx, r14
0x140077f81  lea     rdx, aEnableextended; "EnableExtendedTraces"
0x140077f88  call    cs:__imp_SrvLibGetDWord
0x140077f8f  nop     dword ptr [rax+rax+00h]
0x140077f94  mov     ecx, esi
0x140077f96  lea     r8, [rbp+57h+pulResult]
0x140077f9a  test    eax, eax
0x140077f9c  lea     rdx, aKeepalivetime; "KeepAliveTime"
0x140077fa3  mov     r15d, 2
0x140077fa9  cmovns  ecx, [rbp+57h+pulResult]
0x140077fad  mov     cs:Smb2ProviderEnableExtendedTraces, ecx
0x140077fb3  mov     rcx, r14
0x140077fb6  mov     cs:Smb2KeepAliveTimeInMin, r15d
0x140077fbd  call    cs:__imp_SrvLibGetDWord
0x140077fc4  nop     dword ptr [rax+rax+00h]
0x140077fc9  mov     edi, 1179Eh
0x140077fce  test    eax, eax
0x140077fd0  js      short loc_140077FDF
0x140077fd2  mov     eax, [rbp+57h+pulResult]
0x140077fd5  cmp     eax, edi
0x140077fd7  jnb     short loc_140077FDF
0x140077fd9  mov     cs:Smb2KeepAliveTimeInMin, eax
0x140077fdf  lea     r8, [rbp+57h+pulResult]
0x140077fe3  mov     cs:Smb2ResilientKeepAliveTimeInSec, 0Ah
0x140077fed  lea     rdx, aResilientkeepa; "ResilientKeepAliveTime"
0x140077ff4  mov     rcx, r14
0x140077ff7  call    cs:__imp_SrvLibGetDWord
0x140077ffe  nop     dword ptr [rax+rax+00h]
0x140078003  test    eax, eax
0x140078005  js      short loc_140078014
0x140078007  mov     eax, [rbp+57h+pulResult]
0x14007800a  cmp     eax, edi
0x14007800c  jnb     short loc_140078014
0x14007800e  mov     cs:Smb2ResilientKeepAliveTimeInSec, eax
0x140078014  lea     r8, [rbp+57h+pulResult]
0x140078018  mov     cs:Smb2MaxRtInSec, 14h
0x140078022  lea     rdx, aSmbmaxrt; "SmbMaxRT"
0x140078029  mov     rcx, r14
0x14007802c  call    cs:__imp_SrvLibGetDWord
0x140078033  nop     dword ptr [rax+rax+00h]
0x140078038  test    eax, eax
0x14007803a  js      short loc_140078045
0x14007803c  mov     eax, [rbp+57h+pulResult]
0x14007803f  mov     cs:Smb2MaxRtInSec, eax
0x140078045  mov     rax, 218711A00h
0x14007804f  lea     r8, [rbp+57h+pulResult]
0x140078053  lea     rdx, aRefreshsnapsho; "RefreshSnapShotsSchedule"
0x14007805a  mov     cs:Smb2RefreshSnapShotsSchedule, rax
0x140078061  mov     rcx, r14
0x140078064  call    cs:__imp_SrvLibGetDWord
0x14007806b  nop     dword ptr [rax+rax+00h]
0x140078070  test    eax, eax
0x140078072  js      short loc_140078085
0x140078074  mov     eax, [rbp+57h+pulResult]
0x140078077  imul    rcx, rax, 989680h
0x14007807e  mov     cs:Smb2RefreshSnapShotsSchedule, rcx
0x140078085  lea     r8, [rbp+57h+pulResult]
0x140078089  mov     cs:Smb2TreatHostAsStableStorage, sil
0x140078090  lea     rdx, aTreathostassta; "treathostasstablestorage"
0x140078097  mov     rcx, r14
0x14007809a  call    cs:__imp_SrvLibGetDWord
0x1400780a1  nop     dword ptr [rax+rax+00h]
0x1400780a6  test    eax, eax
0x1400780a8  js      short loc_1400780B5
0x1400780aa  cmp     [rbp+57h+pulResult], esi
0x1400780ad  jz      short loc_1400780B5
0x1400780af  mov     cs:Smb2TreatHostAsStableStorage, bl
0x1400780b5  lea     r8, [rbp+57h+pulResult]
0x1400780b9  mov     cs:Smb2AllowSequentialRead, sil
0x1400780c0  lea     rdx, aEnablesequenti; "EnableSequentialRead"
0x1400780c7  mov     rcx, r14
0x1400780ca  call    cs:__imp_SrvLibGetDWord
0x1400780d1  nop     dword ptr [rax+rax+00h]
0x1400780d6  test    eax, eax
0x1400780d8  js      short loc_1400780E5
0x1400780da  cmp     [rbp+57h+pulResult], esi
0x1400780dd  jz      short loc_1400780E5
0x1400780df  mov     cs:Smb2AllowSequentialRead, bl
0x1400780e5  lea     r8, [rbp+57h+pulResult]
0x1400780e9  mov     cs:Smb2LeasingEnabled, bl
0x1400780ef  lea     rdx, aDisableleasing; "DisableLeasing"
0x1400780f6  mov     rcx, r14
0x1400780f9  call    cs:__imp_SrvLibGetDWord
0x140078100  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
