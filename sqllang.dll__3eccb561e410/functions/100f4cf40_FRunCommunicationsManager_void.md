# FRunCommunicationsManager(void)

- ea: `0x100f4cf40`
- end: `0x100f4dc15`
- name: `?FRunCommunicationsManager@@YAHXZ`
- size: `3285`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x100f4dc20`

## callees

- `0x100401070`
- `0x1004012d0`
- `0x100401340`
- `0x100401433`
- `0x1007a2e50`
- `0x1007dbb50`
- `0x10084a4a0`
- `0x1009cf9c0`
- `0x1009d0310`
- `0x1009d1000`
- `0x1009d10b0`
- `0x1009f1fd0`
- `0x100a00670`
- `0x100a008c0`
- `0x100f4cf40`
- `0x100f4e6d0`
- `0x100fa9310`
- `0x1012e6a50`
- `0x1016d6a00`
- `0x1018b86e0`
- `0x101e88ac0`
- `0x101e88d30`
- `0x101e89210`
- `0x101e899b0`
- `0x101eed770`
- `0x101ef1470`

## import_xrefs

- `KERNEL32!GetLastError` at `0x100f4d4cd`
- `KERNEL32!GetLastError` at `0x100f4d56b`
- `KERNEL32!GetLastError` at `0x100f4d5bf`
- `KERNEL32!GetLastError` at `0x100f4d69b`
- `KERNEL32!GetLastError` at `0x100f4d726`
- `KERNEL32!GetLastError` at `0x100f4d4cd`
- `KERNEL32!GetLastError` at `0x100f4d56b`
- `KERNEL32!GetLastError` at `0x100f4d5bf`
- `KERNEL32!GetLastError` at `0x100f4d69b`
- `KERNEL32!GetLastError` at `0x100f4d726`
- `KERNEL32!GetComputerNameW` at `0x100f4d4c3`
- `KERNEL32!GetComputerNameW` at `0x100f4d4c3`
- `KERNEL32!WaitForSingleObject` at `0x100f4da10`
- `KERNEL32!WaitForSingleObject` at `0x100f4da10`
- `KERNEL32!ResetEvent` at `0x100f4da1d`
- `KERNEL32!ResetEvent` at `0x100f4da1d`
- `ADVAPI32!ConvertStringSidToSidW` at `0x100f4d691`
- `ADVAPI32!ConvertStringSidToSidW` at `0x100f4d691`
- `ADVAPI32!LookupAccountSidW` at `0x100f4d71c`
- `ADVAPI32!LookupAccountSidW` at `0x100f4d71c`
- `ADVAPI32!LookupAccountNameW` at `0x100f4d54c`
- `ADVAPI32!LookupAccountNameW` at `0x100f4d5b5`
- `ADVAPI32!LookupAccountNameW` at `0x100f4d54c`
- `ADVAPI32!LookupAccountNameW` at `0x100f4d5b5`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100f4d386`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100f4d7a9`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100f4d7c9`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100f4d827`
- `sqldk!?s_pServerConf@@3PEAVIServerConfiguration@@EA` at `0x100f4d847`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d2f9`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d327`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d339`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d35b`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d36d`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d3d5`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d3e7`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d625`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d63b`
- `sqldk!?SOS_OS_OsInfo@@3VOsInfo@@A` at `0x100f4d85d`
- `sqldk!?Dequeue@ResQueueBase@@QEAAPEAVSEListElem@@IK_N@Z` at `0x100f4da8f`
- `sqldk!?Dequeue@ResQueueBase@@QEAAPEAVSEListElem@@IK_N@Z` at `0x100f4da8f`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d32e`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d340`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d362`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d374`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d3dc`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d3ee`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d62c`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d642`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d32e`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d340`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d362`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d374`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d3dc`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d3ee`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d62c`
- `sqldk!?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ` at `0x100f4d642`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100f4d95b`
- `sqldk!?HRESULT_FROM_SOS_RESULT_Uncommon@@YAJW4SOS_RESULT@@@Z` at `0x100f4d95b`
- `sqldk!?hdl_backout@@YAHHHHHPEAD@Z` at `0x100f4d9c9`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100f4d864`
- `sqldk!?IsLinux@OsInfo@@QEBA?B_NXZ` at `0x100f4d864`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f4db8d`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x100f4db8d`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100f4d300`
- `sqldk!?IsXPlatInstance@OsInfo@@QEBA?B_NXZ` at `0x100f4d300`
- `sqldk!SystemThread_TlsIndex` at `0x100f4d8d8`
- `sqldk!SystemThread_TlsIndex` at `0x100f4db55`
- `sqldk!SystemThread_TlsOffset` at `0x100f4d8e1`
- `sqldk!SystemThread_TlsOffset` at `0x100f4db5e`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f4d8fa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f4db77`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f4d8fa`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x100f4db77`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x100f4d4f9`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x100f4d513`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x100f4d4f9`
- `api-ms-win-crt-string-l1-1-0!wcscat_s` at `0x100f4d513`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100f4d556`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x100f4d556`
- `sqlmin!?traceCall@@YAXPEBDZZ` at `0x100f4d1dc`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100f4cf85`
- `sqlmin!??0CaptureStartupPhaseTelemetry@@QEAA@H@Z` at `0x100f4cf85`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100f4d9bb`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100f4dbdf`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100f4d9bb`
- `sqlmin!??1CaptureStartupPhaseTelemetry@@QEAA@XZ` at `0x100f4dbdf`
- `sqlmin!?ComputeDacStatus@@YA?AW4EDacStatus@@XZ` at `0x100f4d400`
- `sqlmin!?ComputeDacStatus@@YA?AW4EDacStatus@@XZ` at `0x100f4d400`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100f4dbab`
- `sqlmin!?SetWin32ExitCode@@YAXK@Z` at `0x100f4dbab`
- `sqlmin!?SetSQLExitError@@YAXK@Z` at `0x100f4dbb3`
- `sqlmin!?SetSQLExitError@@YAXK@Z` at `0x100f4dbb3`
- `sqlmin!?InitializeHpcEnvironment@@YAXXZ` at `0x100f4d9a1`
- `sqlmin!?InitializeHpcEnvironment@@YAXXZ` at `0x100f4d9a1`
- `sqlmin!?SetAsCompleted@StartupDependencies@@SAXW4Components@1@@Z` at `0x100f4d9ac`
- `sqlmin!?SetAsCompleted@StartupDependencies@@SAXW4Components@1@@Z` at `0x100f4d9ac`
- `sqlmin!GetXdbServerGlobals` at `0x100f4d2ae`
- `sqlmin!GetXdbServerGlobals` at `0x100f4d2bd`
- `sqlmin!GetXdbServerGlobals` at `0x100f4d409`
- `sqlmin!GetXdbServerGlobals` at `0x100f4d2ae`
- `sqlmin!GetXdbServerGlobals` at `0x100f4d2bd`
- `sqlmin!GetXdbServerGlobals` at `0x100f4d409`
- `instapi160!IsDefaultInstanceName` at `0x100f4d7bf`
- `instapi160!IsDefaultInstanceName` at `0x100f4d83d`
- `instapi160!IsDefaultInstanceName` at `0x100f4d7bf`
- `instapi160!IsDefaultInstanceName` at `0x100f4d83d`
- `hostregdll!HostReg_GetGroupSid` at `0x100f4d667`
- `hostregdll!HostReg_GetGroupSid` at `0x100f4d667`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100f4d42d`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100f4d44c`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100f4d42d`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100f4d44c`

## string_xrefs

- `0x100f4d43e`: `EnableNewReplicationAgentUserForWcow`
- `0x100f4d983`: `Failed to initialize external services.`
- `0x100f4d426`: `SQL.Config`
- `0x100f4d445`: `SQL.Config`
- `0x100f4d5dd`: `Successfully found replAgentUser account.\n`
- `0x100f4d5d6`: `Could not find replAgentUser account.\n`
- `0x100f4d573`: `Sid memory allocation error or account could not be found: %d\n`
- `0x100f4d5c7`: `replAgentuser account (sid) could not be found: %d\n`
- `0x100f4d4d5`: `GetComputerName failed: %d\n`
- `0x100f4d4ff`: `\replAgentUser`
- `0x100f4d6a4`: `Failed to get ConvertStringSidToSid SID with error code %d.`
- `0x100f4d72f`: `Failed to get ReplicationUsersGroup name from SID with error code %d.`
- `0x100f4d671`: `Failed to get ReplicationUsersGroupAccount SID.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 FRunCommunicationsManager(void)
{
  __int64 v0; // rcx
  __int64 v1; // rcx
  __int64 XdbServerGlobals; // rax
  __int64 (__fastcall *v3)(); // rcx
  _DWORD *v4; // rax
  int v5; // edx
  int v6; // ecx
  unsigned int v7; // edi
  unsigned int v8; // r14d
  __int64 v9; // rcx
  char v10; // si
  DWORD v11; // eax
  void *v12; // r15
  DWORD v13; // eax
  DWORD v14; // eax
  const wchar_t *v15; // rcx
  wchar_t *v16; // rax
  DWORD v17; // eax
  DWORD LastError; // eax
  unsigned int v19; // edi
  RESOURCE *v20; // rcx
  const wchar_t *v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rdx
  int v24; // eax
  const wchar_t *v25; // rdi
  __int64 v26; // rax
  int v27; // eax
  int v28; // edi
  __int64 v29; // rdi
  __int64 v30; // rcx
  unsigned int v31; // eax
  RESOURCE *v32; // rcx
  __int64 result; // rax
  int v34; // r14d
  struct SEListElem *v35; // rax
  volatile signed __int32 *v36; // rdi
  int v37; // esi
  signed __int32 v38; // eax
  __int64 v39; // rbx
  struct Worker *v40; // rcx
  RESOURCE *v41; // rcx
  int ReferencedDomainName; // [rsp+20h] [rbp-B18h]
  WCHAR *cchReferencedDomainName; // [rsp+28h] [rbp-B10h]
  _BYTE v44[4]; // [rsp+40h] [rbp-AF8h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-AF4h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-AF0h] BYREF
  DWORD v47; // [rsp+4Ch] [rbp-AECh] BYREF
  DWORD nSize; // [rsp+50h] [rbp-AE8h] BYREF
  DWORD v49; // [rsp+54h] [rbp-AE4h] BYREF
  DWORD cchName[2]; // [rsp+58h] [rbp-AE0h] BYREF
  int v51; // [rsp+60h] [rbp-AD8h]
  int v52; // [rsp+64h] [rbp-AD4h]
  volatile signed __int32 *v53; // [rsp+68h] [rbp-AD0h]
  LPCWSTR StringSid; // [rsp+70h] [rbp-AC8h] BYREF
  PSID Sid; // [rsp+78h] [rbp-AC0h] BYREF
  __int64 v56; // [rsp+80h] [rbp-AB8h] BYREF
  enum _SID_NAME_USE v57[2]; // [rsp+88h] [rbp-AB0h] BYREF
  int v58; // [rsp+90h] [rbp-AA8h]
  signed __int32 v59; // [rsp+94h] [rbp-AA4h]
  int v60; // [rsp+98h] [rbp-AA0h]
  volatile signed __int32 *i; // [rsp+A0h] [rbp-A98h]
  _BYTE v62[40]; // [rsp+A8h] [rbp-A90h] BYREF
  _QWORD v63[43]; // [rsp+D0h] [rbp-A68h] BYREF
  __int128 v64; // [rsp+228h] [rbp-910h]
  __int64 (*v65)(void); // [rsp+238h] [rbp-900h]
  void *v66; // [rsp+240h] [rbp-8F8h]
  void (*v67)(int, int, struct CConnectionOutput *, ...); // [rsp+248h] [rbp-8F0h]
  unsigned int (*v68)(struct CNetConnection *, unsigned __int16, unsigned __int8 *, unsigned int, unsigned int); // [rsp+250h] [rbp-8E8h]
  void *v69; // [rsp+258h] [rbp-8E0h]
  __int64 (__fastcall *v70)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // [rsp+260h] [rbp-8D8h]
  void *v71; // [rsp+268h] [rbp-8D0h]
  __int128 v72; // [rsp+270h] [rbp-8C8h]
  __int128 v73; // [rsp+280h] [rbp-8B8h]
  __int64 v74; // [rsp+290h] [rbp-8A8h]
  __int64 v75; // [rsp+2A0h] [rbp-898h]
  int *v76; // [rsp+2A8h] [rbp-890h]
  struct SEListElem *v77; // [rsp+2B0h] [rbp-888h]
  volatile signed __int32 *v78; // [rsp+2B8h] [rbp-880h]
  _BYTE v79[16]; // [rsp+2C0h] [rbp-878h] BYREF
  _BYTE v80[24]; // [rsp+2D0h] [rbp-868h] BYREF
  _BYTE v81[40]; // [rsp+2E8h] [rbp-850h] BYREF
  WCHAR Buffer[8]; // [rsp+310h] [rbp-828h] BYREF
  __int128 v83; // [rsp+320h] [rbp-818h]
  wchar_t Destination[80]; // [rsp+330h] [rbp-808h] BYREF
  WCHAR Name[136]; // [rsp+3D0h] [rbp-768h] BYREF
  wchar_t v86[200]; // [rsp+4E0h] [rbp-658h] BYREF
  wchar_t v87[200]; // [rsp+670h] [rbp-4C8h] BYREF
  WCHAR v88[264]; // [rsp+800h] [rbp-338h] BYREF
  WCHAR v89[136]; // [rsp+A10h] [rbp-128h] BYREF

  v75 = -2;
  CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v62, 8);
  v44[0] = 0;
  v63[3] = 0;
  v64 = 0;
  v72 = 0;
  v73 = 0;
  v74 = 0;
  CTDSGetResourceGroup::m_pFunc = (struct SOS_ResourceGroup *(*)(struct ILogonSession *))CUEnvTransient::CTDSGetResourceGroup::GetResourceGroup;
  v63[2] = CreateSession;
  v63[0] = CreateByteStream;
  v63[1] = ProcessMessages;
  v63[4] = CreateServerConnection;
  v63[5] = CreateBatch;
  v63[6] = FSetupNewConn;
  v63[7] = FFindEndpointFromConnection;
  v63[8] = FAddConnectionWrapper;
  v63[9] = RemoveConnectionWrapper;
  v63[10] = process_login_finish;
  v63[11] = &process_fedauth_token_message;
  v63[12] = process_request;
  v63[13] = attention_trace;
  v63[14] = FWaitForNewPacket;
  v63[15] = WaitForReadDataDirect;
  v63[16] = FWaitForShutdownResources;
  v63[17] = WaitOnWriteAsyncToFinish;
  v63[18] = CreateBandwidthState;
  v63[19] = XEventDataTransferReadsIfEnabled;
  v63[20] = XEventDataTransferWritesIfEnabled;
  v63[21] = GetLogicalIdentifiers;
  v63[22] = GetNetworkName;
  v63[23] = PbhfBlobHandleFactoryFromContext;
  v63[24] = LTextSizeFromContext;
  v63[25] = DBOptsFromContext;
  v63[26] = SendOneUDTColTI;
  v63[27] = GetUdtSerializationMetadata;
  v63[28] = ConvertXMLForTDS72Plus;
  v63[29] = ConvertXMLToVarWstr;
  v63[30] = ConvertMSJsonForTds;
  v63[31] = GetDatabaseName;
  v63[32] = &ReadTVPParam;
  v63[33] = CSbTask::Free;
  v63[34] = ThrowIfMultiPartNameNoSupport;
  v63[35] = TraceDtcState;
  v63[36] = traceCall;
  v63[37] = ReportLoginFailure;
  v63[38] = ClientLoginFailure;
  v63[39] = LogShimImpersonateError;
  v63[40] = SendDoneWarnings;
  v63[41] = GetFallBackCertContext;
  v63[42] = EclFromContext;
  v65 = GetSqlInstanceActiveLoginsCap;
  v66 = &GetXdbLoginResourceGroup;
  v67 = SendXdbLoginFailureToUser;
  v68 = ProcessXdbConnections;
  v69 = &ProduceTestEvent;
  v70 = ReportProcessCloseConnectionEvent;
  v71 = &GetNumberOfTdsObjects;
  if ( *(_DWORD *)(GetXdbServerGlobals(v0) + 8304) )
  {
    XdbServerGlobals = GetXdbServerGlobals(v1);
    v3 = (__int64 (__fastcall *)())*((_QWORD *)&v73 + 1);
    if ( *(_DWORD *)(XdbServerGlobals + 20692) )
      v3 = ReportSQLCertificateInfo;
    *((_QWORD *)&v73 + 1) = v3;
  }
  v4 = (_DWORD *)qword_102ECFB00;
  if ( *(_DWORD *)(qword_102ECFB00 + 14552) )
    goto LABEL_19;
  if ( OsInfo::IsXPlatInstance(SOS_OS_OsInfo) )
    goto LABEL_18;
  v4 = (_DWORD *)qword_102ECFB00;
  if ( !*(_DWORD *)(qword_102ECFB00 + 14496) )
    goto LABEL_16;
  if ( !*(_DWORD *)(qword_102ECFB00 + 14504) )
  {
LABEL_12:
    if ( v4[3625] )
      goto LABEL_19;
    if ( (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 2
      && (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 3 )
    {
      goto LABEL_15;
    }
LABEL_18:
    v4 = (_DWORD *)qword_102ECFB00;
    goto LABEL_19;
  }
  if ( (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 2
    && (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 3 )
  {
    v4 = (_DWORD *)qword_102ECFB00;
    goto LABEL_12;
  }
LABEL_15:
  v4 = (_DWORD *)qword_102ECFB00;
LABEL_16:
  if ( (unsigned int)(*((_DWORD *)s_pServerConf + 3) - 1) > 1 )
  {
    v5 = 1;
    goto LABEL_20;
  }
LABEL_19:
  v5 = 0;
LABEL_20:
  v6 = v5 | 2;
  if ( !v4[3636] )
    v6 = v5;
  v7 = v6 | 4;
  if ( !v4[3637] )
    v7 = v6;
  if ( v4[3626]
    && ((unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 2
     || (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) == 3) )
  {
    HIBYTE(word_102EF4368) = 1;
  }
  v8 = ComputeDacStatus();
  if ( !*(_DWORD *)(GetXdbServerGlobals(v9) + 11976)
    || !(unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"AllowReplUserConnectNamePipe", 0) )
  {
LABEL_53:
    cchReferencedDomainName = (WCHAR *)&szPassword;
    LOBYTE(ReferencedDomainName) = 0;
    goto LABEL_54;
  }
  if ( !(unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableNewReplicationAgentUserForWcow", 0) )
  {
    if ( !*(_DWORD *)(qword_102ECFB00 + 14504)
      || (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 2
      && (unsigned int)OsInfo::GetContainerType(SOS_OS_OsInfo) != 3 )
    {
      StringSid = 0;
      Sid = 0;
      if ( (unsigned int)HostReg_GetGroupSid(L"ReplicationUsersGroup", &StringSid) )
      {
        scierrlog(0x53B8u, L"Failed to get ReplicationUsersGroupAccount SID.");
      }
      else if ( ConvertStringSidToSidW(StringSid, &Sid) )
      {
        cchName[0] = 129;
        v49 = 129;
        if ( LookupAccountSidW(0, Sid, Name, cchName, v89, &v49, v57) )
        {
          cchReferencedDomainName = Name;
          LOBYTE(ReferencedDomainName) = 1;
          goto LABEL_54;
        }
        LastError = GetLastError();
        swprintf_s(v87, 0xC8u, L"Failed to get ReplicationUsersGroup name from SID with error code %d.", LastError);
        scierrlog(0x53B8u, v87);
      }
      else
      {
        v17 = GetLastError();
        swprintf_s(v86, 0xC8u, L"Failed to get ConvertStringSidToSid SID with error code %d.", v17);
        scierrlog(0x53B8u, v86);
      }
LABEL_117:
      CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v62);
      return 0;
    }
    goto LABEL_53;
  }
  *(_OWORD *)Buffer = 0;
  v83 = 0;
  nSize = 16;
  memset_0(Destination, 0, sizeof(Destination));
  memset_0(v88, 0, 0x208u);
  v47 = 260;
  cbSid = 0;
  peUse = SidTypeUnknown;
  v10 = 1;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    v11 = GetLastError();
    traceprint(L"GetComputerName failed: %d\n", v11);
    v10 = 0;
  }
  wcscat_s(Destination, 0x50u, Buffer);
  wcscat_s(Destination, 0x50u, L"\\replAgentUser");
  LookupAccountNameW(0, Destination, 0, &cbSid, v88, &v47, &peUse);
  v12 = malloc(cbSid);
  if ( !v12 || !cbSid )
  {
    v13 = GetLastError();
    traceprint(L"Sid memory allocation error or account could not be found: %d\n", v13);
    v10 = 0;
  }
  if ( !LookupAccountNameW(0, Destination, v12, &cbSid, v88, &v47, &peUse) )
  {
    v14 = GetLastError();
    traceprint(L"replAgentuser account (sid) could not be found: %d\n", v14);
    v10 = 0;
  }
  v15 = L"Successfully found replAgentUser account.\n";
  if ( !v10 )
    v15 = L"Could not find replAgentUser account.\n";
  traceprint(v15);
  v16 = Destination;
  if ( !v10 )
    v16 = (wchar_t *)&szPassword;
  cchReferencedDomainName = v16;
  LOBYTE(ReferencedDomainName) = v10;
LABEL_54:
  v19 = InitializeTDS(v7, v8, v44, v63, ReferencedDomainName, cchReferencedDomainName);
  if ( !ShouldInitializeExtensibility() )
    goto LABEL_63;
  v21 = 0;
  v22 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
  if ( !(unsigned int)IsDefaultInstanceName(v22) )
    v21 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
  if ( (unsigned __int8)ConstructAuthorizationSIDs() )
  {
    v24 = InitializeExtensibilityComponents(v21);
    if ( v24 >= 0 )
    {
      g_isExtensibilityBootCompleted = 1;
      goto LABEL_63;
    }
    _mm_lfence();
    v23 = (unsigned int)v24;
  }
  else
  {
    v23 = 10;
  }
  scierrlog(0x985Au, v23);
LABEL_63:
  if ( v19 )
  {
    if ( v44[0] )
      RESOURCE::ShutdownListening(v20);
    SetWin32ExitCode(0x42Au);
    SetSQLExitError(v19);
    ErrLog_WrapByNumSev(0x45A2u, 0x12u, (v44[0] != 0) + 3);
    goto LABEL_117;
  }
  if ( IsXdbPkgLauncherEnabled() )
  {
    v25 = 0;
    v26 = (*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
    if ( !(unsigned int)IsDefaultInstanceName(v26) )
      v25 = (const wchar_t *)(*(__int64 (__fastcall **)(struct IServerConfiguration *))(*(_QWORD *)s_pServerConf + 224LL))(s_pServerConf);
    if ( !OsInfo::IsLinux(SOS_OS_OsInfo) || g_isExtensibilityBootCompleted )
    {
      v27 = InitializeXdbPkgLauncherComponents(v25);
      if ( v27 >= 0 )
      {
        g_isXdbPkgLauncherBootCompleted = 1;
        goto LABEL_71;
      }
    }
    else
    {
      v27 = -2147467259;
    }
    _mm_lfence();
    log_unlocalized(L"InitializeXdbPkgLauncher failed. ErrorCode: 0x%08lx.\n", (unsigned int)v27);
  }
LABEL_71:
  if ( IsExternalServicesEnabled() )
  {
    if ( !IsExternalServicesEnabled() )
      goto LABEL_83;
    v28 = ExternalServiceHub::Boot((ExternalServiceHub *)&ExternalServiceHub::sm_hub);
    if ( v28 < 0 )
      goto LABEL_82;
    v56 = 0;
    v29 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v30 = *(_QWORD *)(v29 + 256);
    if ( !v30 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v30 = *(_QWORD *)(v29 + 256);
    }
    v31 = SOS_Node::EnqueueTaskDirect(*(_QWORD *)(v30 + 992), CreateStartupExternalServices, 0, 50, &v56, 0);
    v28 = v31 ? HRESULT_FROM_SOS_RESULT_Uncommon(v31) : 0;
    CAutoRefc<SOS_Task>::~CAutoRefc<SOS_Task>(&v56);
    if ( v28 < 0 )
    {
LABEL_82:
      _mm_lfence();
      scierrlog(0x98E1u, (unsigned int)v28);
      FireTraceEvent(1, (unsigned int)v28, 0, L"Failed to initialize external services.");
    }
    else
    {
LABEL_83:
      g_isExternalServicesInitializationCompleted = 1;
    }
  }
  InitializeHpcEnvironment();
  StartupDependencies::SetAsCompleted(6);
  CaptureStartupPhaseTelemetry::~CaptureStartupPhaseTelemetry((CaptureStartupPhaseTelemetry *)v62);
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v81, 0, 0, 0, (int (*)(int, int, int, int, char *))hdl_backout, 0);
    v37 = 1;
    v76 = &dword_102EF3D80;
    while ( 1 )
    {
      if ( v37 )
      {
        WaitForSingleObject(hEvent, 0xFFFFFFFF);
        ResetEvent(hEvent);
      }
      v52 = 1;
      if ( dword_102EF3D80 == 2 )
        break;
      if ( g_statCOM == 2 )
        LoadDCOM();
      if ( FIsClrStarted() )
      {
        v34 = 0;
        v57[1] = 0;
        v35 = ResQueueBase::Dequeue((ResQueueBase *)&CHostTaskManager::m_ListOfTasksToBeAborted, 0x400061u, 0, 1);
        v77 = v35;
        v36 = 0;
        if ( v35 )
          v36 = (volatile signed __int32 *)((char *)v35 - 8);
        v78 = v36;
        v53 = v36;
        v37 = 1;
        if ( v36 )
        {
          v58 = CHostTask::Abort((CHostTask *)v36);
          if ( v58 < 0 )
          {
            _mm_lfence();
            if ( *((_DWORD *)v36 + 10) != 3 )
            {
              for ( i = v36; ; v36 = i )
              {
                v38 = *((_DWORD *)v36 + 10);
                cchName[1] = v38;
                if ( v38 >= 0 && v38 != 1 )
                  break;
                v51 = 1;
                v59 = _InterlockedCompareExchange(v36 + 10, 0, v38);
                if ( v38 == v59 )
                  goto LABEL_101;
                _mm_pause();
              }
              v51 = 0;
            }
LABEL_101:
            v36 = v53;
          }
          v34 = 1;
          v37 = 0;
        }
        v60 = v34;
        if ( v36 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 16LL))(v36);
      }
      else
      {
        v37 = v52;
      }
    }
    KillAllRunningSpids();
    RESOURCE::ShutdownListening(v32);
    ExcHandler::~ExcHandler((ExcHandler *)v81);
    result = 1;
  }
  catch ( SQLError v80 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)v79, (const struct SQLError *)v80);
      RESOURCE::ShutdownListening(v41);
      ReleaseHpcEnvironment();
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)v79);
    }
    catch ( ShortStackException )
    {
    }
    v39 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
    v40 = *(struct Worker **)(v39 + 256);
    if ( !v40 )
    {
      SystemThread::MakeMiniSOSThread(0);
      v40 = *(struct Worker **)(v39 + 256);
    }
    if ( *((_DWORD *)v40 + 139) )
      ExceptionPostCatchActions(v40);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x100f4cf40  mov     r11, rsp
0x100f4cf43  push    r15
0x100f4cf45  sub     rsp, 0B30h
0x100f4cf4c  mov     qword ptr [r11-898h], 0FFFFFFFFFFFFFFFEh
0x100f4cf57  mov     [r11+8], rbx
0x100f4cf5b  mov     [r11+10h], rsi
0x100f4cf5f  mov     [r11+18h], rdi
0x100f4cf63  mov     [r11+20h], r14
0x100f4cf67  mov     rax, cs:__security_cookie
0x100f4cf6e  xor     rax, rsp
0x100f4cf71  mov     [rsp+0B38h+var_18], rax
0x100f4cf79  mov     edx, 8
0x100f4cf7e  lea     rcx, [r11-0A90h]
0x100f4cf85  call    cs:__imp_??0CaptureStartupPhaseTelemetry@@QEAA@H@Z; CaptureStartupPhaseTelemetry::CaptureStartupPhaseTelemetry(int)
0x100f4cf8b  nop
0x100f4cf8c  mov     [rsp+0B38h+var_AF8], 0
0x100f4cf91  xor     eax, eax
0x100f4cf93  mov     [rsp+0B38h+var_A50], rax
0x100f4cf9b  xorps   xmm0, xmm0
0x100f4cf9e  movups  [rsp+0B38h+var_910], xmm0
0x100f4cfa6  xorps   xmm1, xmm1
0x100f4cfa9  movups  [rsp+0B38h+var_8C8], xmm1
0x100f4cfb1  movaps  [rsp+0B38h+var_8B8], xmm0
0x100f4cfb9  mov     [rsp+0B38h+var_8A8], rax
0x100f4cfc1  lea     rax, ?GetResourceGroup@CTDSGetResourceGroup@CUEnvTransient@@CAPEAVSOS_ResourceGroup@@PEAVILogonSession@@@Z; CUEnvTransient::CTDSGetResourceGroup::GetResourceGroup(ILogonSession *)
0x100f4cfc8  mov     cs:?m_pFunc@CTDSGetResourceGroup@@0P6APEAVSOS_ResourceGroup@@PEAVILogonSession@@@ZEA, rax; SOS_ResourceGroup * (*CTDSGetResourceGroup::m_pFunc)(ILogonSession *)
0x100f4cfcf  lea     rax, ?CreateSession@@YAPEAVILogonSession@@PEAVIMemObj@@PEAVCPhysicalConnection@@@Z; CreateSession(IMemObj *,CPhysicalConnection *)
0x100f4cfd6  mov     [rsp+0B38h+var_A58], rax
0x100f4cfde  lea     rax, ?CreateByteStream@@YAPEAVCNetByteStream@@PEAVIMemObj@@PEAVCNetConnection@@@Z; CreateByteStream(IMemObj *,CNetConnection *)
0x100f4cfe5  mov     [rsp+0B38h+var_A68], rax
0x100f4cfed  lea     rax, ?ProcessMessages@@YAPEAXPEAX@Z; ProcessMessages(void *)
0x100f4cff4  mov     [rsp+0B38h+var_A60], rax
0x100f4cffc  lea     rax, ?CreateServerConnection@@YAPEAVCServerNetConnection@@PEAVIMemObj@@@Z; CreateServerConnection(IMemObj *)
0x100f4d003  mov     [rsp+0B38h+var_A48], rax
0x100f4d00b  lea     rax, ?CreateBatch@@YAPEAVIBatch@@PEAVIMemObj@@PEAVILogonSession@@PEAVCNetConnection@@@Z; CreateBatch(IMemObj *,ILogonSession *,CNetConnection *)
0x100f4d012  mov     [rsp+0B38h+var_A40], rax
0x100f4d01a  lea     rax, ?FSetupNewConn@@YAHPEAVIBatch@@JU_GUID@@PEAVSNI_Conn@@_N@Z; FSetupNewConn(IBatch *,long,_GUID,SNI_Conn *,bool)
0x100f4d021  mov     [rsp+0B38h+var_A38], rax
0x100f4d029  lea     rax, ?FFindEndpointFromConnection@@YA_NPEAVSNI_Conn@@HPEAKPEAW4ProtocolType@@PEAH@Z; FFindEndpointFromConnection(SNI_Conn *,int,ulong *,ProtocolType *,int *)
0x100f4d030  mov     [rsp+0B38h+var_A30], rax
0x100f4d038  lea     rax, ?FAddConnectionWrapper@@YAHPEAVSNI_Conn@@PEAVCNetConnection@@@Z; FAddConnectionWrapper(SNI_Conn *,CNetConnection *)
0x100f4d03f  mov     [rsp+0B38h+var_A28], rax
0x100f4d047  lea     rax, ?RemoveConnectionWrapper@@YAXPEAVSNI_Conn@@PEAVCNetConnection@@@Z; RemoveConnectionWrapper(SNI_Conn *,CNetConnection *)
0x100f4d04e  mov     [rsp+0B38h+var_A20], rax
0x100f4d056  lea     rax, ?process_login_finish@@YA?AW4ECommandResult@@PEAVCNetConnection@@@Z; process_login_finish(CNetConnection *)
0x100f4d05d  mov     [rsp+0B38h+var_A18], rax
0x100f4d065  lea     rax, ?process_fedauth_token_message@@YA?AW4ECommandResult@@PEAVCNetConnection@@@Z; process_fedauth_token_message(CNetConnection *)
0x100f4d06c  mov     [rsp+0B38h+var_A10], rax
0x100f4d074  lea     rax, ?process_request@@YA?AW4ECommandResult@@PEAVIBatch@@PEAVSNI_Conn@@W4RequestType@@@Z; process_request(IBatch *,SNI_Conn *,RequestType)
0x100f4d07b  mov     [rsp+0B38h+var_A08], rax
0x100f4d083  lea     rax, ?attention_trace@@YAXPEAVIBatch@@PEAVCNetConnection@@@Z; attention_trace(IBatch *,CNetConnection *)
0x100f4d08a  mov     [rsp+0B38h+var_A00], rax
0x100f4d092  lea     rax, ?FWaitForNewPacket@@YAHPEAVCNetConnection@@PEAVIBatch@@@Z; FWaitForNewPacket(CNetConnection *,IBatch *)
0x100f4d099  mov     [rsp+0B38h+var_9F8], rax
0x100f4d0a1  lea     rax, ?WaitForReadDataDirect@@YAXPEAVILogonSession@@PEAVCNetConnection@@I@Z; WaitForReadDataDirect(ILogonSession *,CNetConnection *,uint)
0x100f4d0a8  mov     [rsp+0B38h+var_9F0], rax
0x100f4d0b0  lea     rax, ?FWaitForShutdownResources@@YAHPEAK@Z; FWaitForShutdownResources(ulong *)
0x100f4d0b7  mov     [rsp+0B38h+var_9E8], rax
0x100f4d0bf  lea     rax, ?WaitOnWriteAsyncToFinish@@YA_NPEAVCNetConnection@@@Z; WaitOnWriteAsyncToFinish(CNetConnection *)
0x100f4d0c6  mov     [rsp+0B38h+var_9E0], rax
0x100f4d0ce  lea     rax, ?CreateBandwidthState@@YAHPEAVIMemObj@@PEAVCNetConnection@@PEAPEAVIBandwidthState@@@Z; CreateBandwidthState(IMemObj *,CNetConnection *,IBandwidthState * *)
0x100f4d0d5  mov     [rsp+0B38h+var_9D8], rax
0x100f4d0dd  lea     rax, ?XEventDataTransferReadsIfEnabled@@YAXPEAVIBandwidthState@@@Z; XEventDataTransferReadsIfEnabled(IBandwidthState *)
0x100f4d0e4  mov     [rsp+0B38h+var_9D0], rax
0x100f4d0ec  lea     rax, ?XEventDataTransferWritesIfEnabled@@YAXPEAVIBandwidthState@@@Z; XEventDataTransferWritesIfEnabled(IBandwidthState *)
0x100f4d0f3  mov     [rsp+0B38h+var_9C8], rax
0x100f4d0fb  lea     rax, ?GetLogicalIdentifiers@@YAXPEBVCNetConnection@@PEA_WI1IAEAU_GUID@@@Z; GetLogicalIdentifiers(CNetConnection const *,wchar_t *,uint,wchar_t *,uint,_GUID &)
0x100f4d102  mov     [rsp+0B38h+var_9C0], rax
0x100f4d10a  lea     rax, ?GetNetworkName@@YAXPEB_WPEA_WI@Z; GetNetworkName(wchar_t const *,wchar_t *,uint)
0x100f4d111  mov     [rsp+0B38h+var_9B8], rax
0x100f4d119  lea     rax, ?PbhfBlobHandleFactoryFromContext@@YAPEAUIBlobHandleFactory@@PEAURpcParamParseHandle@@@Z; PbhfBlobHandleFactoryFromContext(RpcParamParseHandle *)
0x100f4d120  mov     [rsp+0B38h+var_9B0], rax
0x100f4d128  lea     rax, ?LTextSizeFromContext@@YAJPEAVCNetConnection@@@Z; LTextSizeFromContext(CNetConnection *)
0x100f4d12f  mov     [rsp+0B38h+var_9A8], rax
0x100f4d137  lea     rax, ?DBOptsFromContext@@YAXPEAVCDefaultCollation@@PEAEPEA_N@Z; DBOptsFromContext(CDefaultCollation *,uchar *,bool *)
0x100f4d13e  mov     [rsp+0B38h+var_9A0], rax
0x100f4d146  lea     rax, ?SendOneUDTColTI@@YAXGPEBVCTypeInfo@@PEAGPEAPEAE@Z; SendOneUDTColTI(ushort,CTypeInfo const *,ushort *,uchar * *)
0x100f4d14d  mov     [rsp+0B38h+var_998], rax
0x100f4d155  lea     rax, ?GetUdtSerializationMetadata@@YAXPEAVIMemObj@@PEBVCTypeInfo@@AEAGPEFAPEFAUSerializationMetadata@@@Z; GetUdtSerializationMetadata(IMemObj *,CTypeInfo const *,ushort &,SerializationMetadata * *)
0x100f4d15c  mov     [rsp+0B38h+var_990], rax
0x100f4d164  lea     rax, ?ConvertXMLForTDS72Plus@@YAXPEBVCXVariant@@PEBVCTypeInfo@@PEAVCBufferedStream@@H@Z; ConvertXMLForTDS72Plus(CXVariant const *,CTypeInfo const *,CBufferedStream *,int)
0x100f4d16b  mov     [rsp+0B38h+var_988], rax
0x100f4d173  lea     rax, ?ConvertXMLToVarWstr@@YAXPEBVCXVariant@@PEBVCTypeInfo@@PEAVCBufferedStream@@@Z; ConvertXMLToVarWstr(CXVariant const *,CTypeInfo const *,CBufferedStream *)
0x100f4d17a  mov     [rsp+0B38h+var_980], rax
0x100f4d182  lea     rax, ?ConvertMSJsonForTds@@YAXPEBVCXVariant@@PEBVCTypeInfo@@PEAVCBufferedStream@@@Z; ConvertMSJsonForTds(CXVariant const *,CTypeInfo const *,CBufferedStream *)
0x100f4d189  mov     [rsp+0B38h+var_978], rax
0x100f4d191  lea     rax, ?GetDatabaseName@@YAPEA_WPEAVIMemObj@@KPEAG@Z; GetDatabaseName(IMemObj *,ulong,ushort *)
0x100f4d198  mov     [rsp+0B38h+var_970], rax
0x100f4d1a0  lea     rax, ?ReadTVPParam@@YAXPEAURpcParamParseHandle@@W4TdsRpcParamReaderFlags@@@Z; ReadTVPParam(RpcParamParseHandle *,TdsRpcParamReaderFlags)
0x100f4d1a7  mov     [rsp+0B38h+var_968], rax
0x100f4d1af  lea     rax, ?Free@CSbTask@@UEAAXXZ; CSbTask::Free(void)
0x100f4d1b6  mov     [rsp+0B38h+var_960], rax
0x100f4d1be  lea     rax, ?ThrowIfMultiPartNameNoSupport@@YAXPEAVWParseName@@@Z; ThrowIfMultiPartNameNoSupport(WParseName *)
0x100f4d1c5  mov     [rsp+0B38h+var_958], rax
0x100f4d1cd  lea     rax, ?TraceDtcState@@YAXEPEBU_GUID@@@Z; TraceDtcState(uchar,_GUID const *)
0x100f4d1d4  mov     [rsp+0B38h+var_950], rax
0x100f4d1dc  mov     rax, cs:__imp_?traceCall@@YAXPEBDZZ; traceCall(char const *,...)
0x100f4d1e3  mov     [rsp+0B38h+var_948], rax
0x100f4d1eb  lea     rax, ?ReportLoginFailure@@YAXPEAVIBatch@@HPEA_WH_NPEAVSNI_Conn@@HPEAXZZ; ReportLoginFailure(IBatch *,int,wchar_t *,int,bool,SNI_Conn *,int,void *,...)
0x100f4d1f2  mov     [rsp+0B38h+var_940], rax
0x100f4d1fa  lea     rax, ?ClientLoginFailure@@YAXPEAVIBatch@@HPEA_WH_NPEAVSNI_Conn@@HPEAXZZ; ClientLoginFailure(IBatch *,int,wchar_t *,int,bool,SNI_Conn *,int,void *,...)
0x100f4d201  mov     [rsp+0B38h+var_938], rax
0x100f4d209  lea     rax, ?LogShimImpersonateError@@YAXK@Z; LogShimImpersonateError(ulong)
0x100f4d210  mov     [rsp+0B38h+var_930], rax
0x100f4d218  lea     rax, ?SendDoneWarnings@@YAXPEAVSOS_LsAccessCache@@@Z; SendDoneWarnings(SOS_LsAccessCache *)
0x100f4d21f  mov     [rsp+0B38h+var_928], rax
0x100f4d227  lea     rax, ?GetFallBackCertContext@@YAPEBU_CERT_CONTEXT@@XZ; GetFallBackCertContext(void)
0x100f4d22e  mov     [rsp+0B38h+var_920], rax
0x100f4d236  lea     rax, ?EclFromContext@@YAGXZ; EclFromContext(void)
0x100f4d23d  mov     [rsp+0B38h+var_918], rax
0x100f4d245  lea     rax, ?GetSqlInstanceActiveLoginsCap@@YAHXZ; GetSqlInstanceActiveLoginsCap(void)
0x100f4d24c  mov     [rsp+0B38h+var_900], rax
0x100f4d254  lea     rax, ?GetXdbLoginResourceGroup@@YA?AW4SOS_RESULT@@PEAPEAVSOS_ResourceGroup@@PEA_N@Z; GetXdbLoginResourceGroup(SOS_ResourceGroup * *,bool *)
0x100f4d25b  mov     [rsp+0B38h+var_8F8], rax
0x100f4d263  lea     rax, ?SendXdbLoginFailureToUser@@YAXHHPEAVCConnectionOutput@@ZZ; SendXdbLoginFailureToUser(int,int,CConnectionOutput *,...)
0x100f4d26a  mov     [rsp+0B38h+var_8F0], rax
0x100f4d272  lea     rax, ?ProcessXdbConnections@@YAKPEAVCNetConnection@@GPEAEKK@Z; ProcessXdbConnections(CNetConnection *,ushort,uchar *,ulong,ulong)
0x100f4d279  mov     [rsp+0B38h+var_8E8], rax
0x100f4d281  lea     rax, ?ProduceTestEvent@@YAXW4ETestEvent@@@Z; ProduceTestEvent(ETestEvent)
0x100f4d288  mov     [rsp+0B38h+var_8E0], rax
0x100f4d290  lea     rax, ?ReportProcessCloseConnectionEvent@@YAXPEAVIBatch@@HHKW4ESessionKillReason@@PEAVSQLError@@@Z; ReportProcessCloseConnectionEvent(IBatch *,int,int,ulong,ESessionKillReason,SQLError *)
0x100f4d297  mov     [rsp+0B38h+var_8D8], rax
0x100f4d29f  lea     rax, ?GetNumberOfTdsObjects@@YA_NW4XdbConnectionType@@PEAG@Z; GetNumberOfTdsObjects(XdbConnectionType,ushort *)
0x100f4d2a6  mov     [rsp+0B38h+var_8D0], rax
0x100f4d2ae  call    cs:__imp_GetXdbServerGlobals
0x100f4d2b4  cmp     dword ptr [rax+2070h], 0
0x100f4d2bb  jz      short loc_100F4D2E5
0x100f4d2bd  call    cs:__imp_GetXdbServerGlobals
0x100f4d2c3  mov     rcx, qword ptr [rsp+0B38h+var_8B8+8]
0x100f4d2cb  lea     rdx, ReportSQLCertificateInfo
0x100f4d2d2  cmp     dword ptr [rax+50D4h], 0
0x100f4d2d9  cmovnz  rcx, rdx
0x100f4d2dd  mov     qword ptr [rsp+0B38h+var_8B8+8], rcx
0x100f4d2e5  mov     rax, cs:qword_102ECFB00
0x100f4d2ec  cmp     dword ptr [rax+38D8h], 0
0x100f4d2f3  jnz     loc_100F4D3AA
0x100f4d2f9  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100f4d300  call    cs:__imp_?IsXPlatInstance@OsInfo@@QEBA?B_NXZ; OsInfo::IsXPlatInstance(void)
0x100f4d306  test    al, al
0x100f4d308  jnz     loc_100F4D3A3
0x100f4d30e  mov     rax, cs:qword_102ECFB00
0x100f4d315  cmp     dword ptr [rax+38A0h], 0
0x100f4d31c  jz      short loc_100F4D386
0x100f4d31e  cmp     dword ptr [rax+38A8h], 0
0x100f4d325  jz      short loc_100F4D352
0x100f4d327  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100f4d32e  call    cs:__imp_?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ; OsInfo::GetContainerType(void)
0x100f4d334  cmp     eax, 2
0x100f4d337  jz      short loc_100F4D37F
0x100f4d339  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100f4d340  call    cs:__imp_?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ; OsInfo::GetContainerType(void)
0x100f4d346  cmp     eax, 3
0x100f4d349  jz      short loc_100F4D37F
0x100f4d34b  mov     rax, cs:qword_102ECFB00
0x100f4d352  cmp     dword ptr [rax+38A4h], 0
0x100f4d359  jnz     short loc_100F4D3AA
0x100f4d35b  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100f4d362  call    cs:__imp_?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ; OsInfo::GetContainerType(void)
0x100f4d368  cmp     eax, 2
0x100f4d36b  jz      short loc_100F4D3A3
0x100f4d36d  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100f4d374  call    cs:__imp_?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ; OsInfo::GetContainerType(void)
0x100f4d37a  cmp     eax, 3
0x100f4d37d  jz      short loc_100F4D3A3
0x100f4d37f  mov     rax, cs:qword_102ECFB00
0x100f4d386  mov     rcx, cs:__imp_?s_pServerConf@@3PEAVIServerConfiguration@@EA; IServerConfiguration * s_pServerConf
0x100f4d38d  mov     rdx, [rcx]
0x100f4d390  mov     ecx, [rdx+0Ch]
0x100f4d393  dec     ecx
0x100f4d395  cmp     ecx, 1
0x100f4d398  jbe     short loc_100F4D3AA
0x100f4d39a  mov     edx, 1
0x100f4d39f  xor     ebx, ebx
0x100f4d3a1  jmp     short loc_100F4D3AE
0x100f4d3a3  mov     rax, cs:qword_102ECFB00
0x100f4d3aa  xor     ebx, ebx
0x100f4d3ac  mov     edx, ebx
0x100f4d3ae  mov     ecx, edx
0x100f4d3b0  or      ecx, 2
0x100f4d3b3  cmp     dword ptr [rax+38D0h], 0
0x100f4d3ba  cmovz   ecx, edx
0x100f4d3bd  mov     edi, ecx
0x100f4d3bf  or      edi, 4
0x100f4d3c2  cmp     dword ptr [rax+38D4h], 0
0x100f4d3c9  cmovz   edi, ecx
0x100f4d3cc  cmp     dword ptr [rax+38A8h], 0
0x100f4d3d3  jz      short loc_100F4D400
0x100f4d3d5  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100f4d3dc  call    cs:__imp_?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ; OsInfo::GetContainerType(void)
0x100f4d3e2  cmp     eax, 2
0x100f4d3e5  jz      short loc_100F4D3F9
0x100f4d3e7  mov     rcx, cs:__imp_?SOS_OS_OsInfo@@3VOsInfo@@A; OsInfo SOS_OS_OsInfo
0x100f4d3ee  call    cs:__imp_?GetContainerType@OsInfo@@QEBA?BW4ContainerType@@XZ; OsInfo::GetContainerType(void)
0x100f4d3f4  cmp     eax, 3
0x100f4d3f7  jnz     short loc_100F4D400
0x100f4d3f9  mov     byte ptr cs:word_102EF4368+1, 1
0x100f4d400  call    cs:__imp_?ComputeDacStatus@@YA?AW4EDacStatus@@XZ; ComputeDacStatus(void)
0x100f4d406  mov     r14d, eax
0x100f4d409  call    cs:__imp_GetXdbServerGlobals
0x100f4d40f  cmp     dword ptr [rax+2EC8h], 0
0x100f4d416  jz      loc_100F4D773
0x100f4d41c  xor     r8d, r8d
0x100f4d41f  lea     rdx, aAllowrepluserc; "AllowReplUserConnectNamePipe"
0x100f4d426  lea     rcx, aSqlConfig; "SQL.Config"
0x100f4d42d  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100f4d433  test    al, al
0x100f4d435  jz      loc_100F4D773
0x100f4d43b  xor     r8d, r8d
0x100f4d43e  lea     rdx, aEnablenewrepli; "EnableNewReplicationAgentUserForWcow"
0x100f4d445  lea     rcx, aSqlConfig; "SQL.Config"
0x100f4d44c  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100f4d452  test    al, al
0x100f4d454  jz      loc_100F4D615
0x100f4d45a  xorps   xmm0, xmm0
0x100f4d45d  movups  xmmword ptr [rsp+0B38h+Buffer], xmm0
0x100f4d465  movups  [rsp+0B38h+var_818], xmm0
0x100f4d46d  mov     [rsp+0B38h+nSize], 10h
0x100f4d475  xor     edx, edx; Val
0x100f4d477  mov     r8d, 0A0h; Size
0x100f4d47d  lea     rcx, [rsp+0B38h+Destination]; void *
0x100f4d485  call    memset_0
0x100f4d48a  xor     edx, edx; Val
0x100f4d48c  mov     r8d, 208h; Size
0x100f4d492  lea     rcx, [rsp+0B38h+var_338]; void *
0x100f4d49a  call    memset_0
0x100f4d49f  mov     [rsp+0B38h+var_AEC], 104h
0x100f4d4a7  mov     [rsp+0B38h+cbSid], ebx
0x100f4d4ab  mov     [rsp+0B38h+var_AF0], 8
0x100f4d4b3  mov     sil, 1
0x100f4d4b6  lea     rdx, [rsp+0B38h+nSize]; nSize
0x100f4d4bb  lea     rcx, [rsp+0B38h+Buffer]; lpBuffer
0x100f4d4c3  call    cs:__imp_GetComputerNameW
0x100f4d4c9  test    eax, eax
0x100f4d4cb  jnz     short loc_100F4D4E4
0x100f4d4cd  call    cs:__imp_GetLastError
0x100f4d4d3  mov     edx, eax
0x100f4d4d5  lea     rcx, aGetcomputernam; "GetComputerName failed: %d\n"
0x100f4d4dc  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x100f4d4e1  xor     sil, sil
0x100f4d4e4  lea     r8, [rsp+0B38h+Buffer]; Source
0x100f4d4ec  mov     edx, 50h ; 'P'; SizeInWords
0x100f4d4f1  lea     rcx, [rsp+0B38h+Destination]; Destination
0x100f4d4f9  call    cs:__imp_wcscat_s
0x100f4d4ff  lea     r8, aReplagentuser; "\\replAgentUser"
0x100f4d506  mov     edx, 50h ; 'P'; SizeInWords
0x100f4d50b  lea     rcx, [rsp+0B38h+Destination]; Destination
0x100f4d513  call    cs:__imp_wcscat_s
0x100f4d519  lea     rax, [rsp+0B38h+var_AF0]
0x100f4d51e  mov     [rsp+0B38h+peUse], rax; peUse
0x100f4d523  lea     rax, [rsp+0B38h+var_AEC]
0x100f4d528  mov     [rsp+0B38h+cchReferencedDomainName], rax; cchReferencedDomainName
0x100f4d52d  lea     rax, [rsp+0B38h+var_338]
0x100f4d535  mov     [rsp+0B38h+ReferencedDomainName], rax; ReferencedDomainName
0x100f4d53a  lea     r9, [rsp+0B38h+cbSid]; cbSid
0x100f4d53f  xor     r8d, r8d; Sid
0x100f4d542  lea     rdx, [rsp+0B38h+Destination]; lpAccountName
0x100f4d54a  xor     ecx, ecx; lpSystemName
0x100f4d54c  call    cs:__imp_LookupAccountNameW
0x100f4d552  mov     ecx, [rsp+0B38h+cbSid]; Size
0x100f4d556  call    cs:__imp_malloc
0x100f4d55c  mov     r15, rax
0x100f4d55f  test    rax, rax
0x100f4d562  jz      short loc_100F4D56B
0x100f4d564  cmp     [rsp+0B38h+cbSid], 0
0x100f4d569  jnz     short loc_100F4D582
0x100f4d56b  call    cs:__imp_GetLastError
0x100f4d571  mov     edx, eax
0x100f4d573  lea     rcx, aSidMemoryAlloc; "Sid memory allocation error or account "...
0x100f4d57a  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x100f4d57f  xor     sil, sil
0x100f4d582  lea     rax, [rsp+0B38h+var_AF0]
0x100f4d587  mov     [rsp+0B38h+peUse], rax; peUse
0x100f4d58c  lea     rax, [rsp+0B38h+var_AEC]
0x100f4d591  mov     [rsp+0B38h+cchReferencedDomainName], rax; cchReferencedDomainName
0x100f4d596  lea     rax, [rsp+0B38h+var_338]
0x100f4d59e  mov     [rsp+0B38h+ReferencedDomainName], rax; ReferencedDomainName
0x100f4d5a3  lea     r9, [rsp+0B38h+cbSid]; cbSid
0x100f4d5a8  mov     r8, r15; Sid
0x100f4d5ab  lea     rdx, [rsp+0B38h+Destination]; lpAccountName
0x100f4d5b3  xor     ecx, ecx; lpSystemName
0x100f4d5b5  call    cs:__imp_LookupAccountNameW
0x100f4d5bb  test    eax, eax
0x100f4d5bd  jnz     short loc_100F4D5D6
0x100f4d5bf  call    cs:__imp_GetLastError
0x100f4d5c5  mov     edx, eax
0x100f4d5c7  lea     rcx, aReplagentuserA; "replAgentuser account (sid) could not b"...
0x100f4d5ce  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x100f4d5d3  xor     sil, sil
0x100f4d5d6  lea     rax, aCouldNotFindRe; "Could not find replAgentUser account.\n"
0x100f4d5dd  lea     rcx, aSuccessfullyFo; "Successfully found replAgentUser accoun"...
0x100f4d5e4  test    sil, sil
0x100f4d5e7  cmovz   rcx, rax; wchar_t *
0x100f4d5eb  call    ?traceprint@@YAXPEB_WZZ; traceprint(wchar_t const *,...)
0x100f4d5f0  lea     rdx, szPassword
0x100f4d5f7  lea     rax, [rsp+0B38h+Destination]
0x100f4d5ff  test    sil, sil
0x100f4d602  cmovz   rax, rdx
0x100f4d606  mov     [rsp+0B38h+cchReferencedDomainName], rax
0x100f4d60b  mov     byte ptr [rsp+0B38h+ReferencedDomainName], sil
0x100f4d610  jmp     loc_100F4D784
  ... truncated ...
```
