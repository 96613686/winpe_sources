# CRemoteConnectionManager::Start(ulong)

- ea: `0x18004d4d0`
- end: `0x18004e2ff`
- name: `?Start@CRemoteConnectionManager@@UEAAJK@Z`
- size: `3631`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `55`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001294`
- `0x18000256c`
- `0x1800074d0`
- `0x1800095a0`
- `0x180009940`
- `0x180012750`
- `0x1800139c0`
- `0x180015d48`
- `0x180018e2c`
- `0x18002558c`
- `0x1800260ec`
- `0x180027534`
- `0x180028384`
- `0x1800287bc`
- `0x180028dd8`
- `0x180028f88`
- `0x180029420`
- `0x180029bc4`
- `0x18002f83c`
- `0x180033f60`
- `0x18003444c`
- `0x180034e64`
- `0x18003df50`
- `0x18003ed90`
- `0x1800409ac`
- `0x180041b08`
- `0x180047b48`
- `0x180048420`
- `0x1800492d0`
- `0x1800493a8`
- `0x180049490`
- `0x18004b064`
- `0x18004c740`
- `0x18004d4d0`
- `0x18004e8e8`
- `0x18004ea9c`
- `0x180050dd4`
- `0x180050f30`
- `0x180073dec`
- `0x18007dc70`
- `0x18008b1bc`
- `0x18008b988`
- `0x18008bc58`
- `0x1800934cc`
- `0x180096e14`
- `0x180097730`
- `0x1800a14c8`
- `0x1800a21dc`
- `0x1800a4044`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004daf4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004daf4`
- `ntdll!RtlAdjustPrivilege` at `0x18004d87b`
- `ntdll!RtlAdjustPrivilege` at `0x18004d87b`
- `ntdll!EtwEventActivityIdControl` at `0x18004e2ac`
- `ntdll!EtwEventActivityIdControl` at `0x18004e2ac`
- `REGAPI!RegQueryListenerStart` at `0x18004db3a`
- `REGAPI!RegQueryListenerStart` at `0x18004db3a`

## string_xrefs

- `0x18004d675`: `RCM Start(): call on termsrv service stop failed: 0x%x in %s`
- `0x18004d6c7`: `this->ReadMachineGroupPolicy failed: 0x%x in %s`
- `0x18004d897`: `RtlAdjustPrivilege on SE_AUDIT_PRIVILEGE failed: 0x%x in %s`
- `0x18004d926`: `UpdateWddmModeSettings failed: 0x%x in %s`
- `0x18004d9c7`: `this->RemoveStaleListener failed 0x%x`
- `0x18004da12`: `Failed to open TS reg key failed: 0x%x in %s`
- `0x18004da56`: `Failed to read TS reg key failed: 0x%x in %s`
- `0x18004dab5`: `CGraphicsFactory__StartGraphicsServices failed: 0x%x in %s`
- `0x18004dba9`: `GetProtocolExtension for listener %ws failed, error 0x%08x`
- `0x18004dcdc`: `Protocol failed to create listener %ws, error 0x%08x`
- `0x18004dd91`: `Ignoring listener %ws, missing protocol GUID`
- `0x18004dd23`: `Listener %ws created`
- `0x18004de65`: `Failed to remove listener: %ws, 0x%x`
- `0x18004e0a2`: `FAILED to create CExecSessionApps failed: 0x%x in %s`
- `0x18004e23f`: `this->ChangeRCMReadyEventState for SetEvent failed : 0x%08x`
- `0x18004d569`: `wwwwwwwwwwwwwwwwTermService`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CRemoteConnectionManager::Start(CRemoteConnectionManager *this, int a2, __int64 a3)
{
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  _DWORD *v9; // r15
  int MachineGroupPolicy; // eax
  CProtocolExMgr *v11; // rsi
  __int64 v12; // rcx
  _DWORD *v13; // rdx
  const char *v14; // rdx
  NTSTATUS v15; // eax
  int v16; // eax
  int v17; // r14d
  int updated; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int NextSubKey; // eax
  int v25; // esi
  int started; // eax
  unsigned __int16 *v27; // rsi
  int ListenerStart; // ebx
  int ListenerByName; // eax
  CRemoteConnectionManager *v30; // rcx
  int ProtocolExtension; // eax
  unsigned int v32; // ebx
  __int64 v33; // rdx
  GUID v34; // xmm0
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // r8d
  int v39; // r9d
  unsigned int v40; // ebx
  int v41; // eax
  struct IListener *v42; // rbx
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  int v49; // eax
  CTSTimerHandlerManager *v50; // rcx
  int v51; // eax
  CExecSessionApps **v52; // rbx
  CExecSessionApps *v53; // rax
  CExecSessionApps *v54; // rax
  int v55; // eax
  int DrainMode; // eax
  int AllowFastReconnect; // eax
  int v58; // ecx
  int v59; // r8d
  int v60; // r9d
  char v61; // si
  int v62; // r14d
  CProtocolExMgr *v63; // rcx
  int v64; // eax
  int v65; // eax
  CRemoteConnectionManager *v66; // rcx
  struct _GUID *v68; // [rsp+20h] [rbp-E0h]
  _BYTE v69[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v70; // [rsp+54h] [rbp-ACh] BYREF
  int v71; // [rsp+58h] [rbp-A8h] BYREF
  struct IListener *v72; // [rsp+60h] [rbp-A0h] BYREF
  struct IListenerItem *v73; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v74; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v76[2]; // [rsp+80h] [rbp-80h] BYREF
  int v77; // [rsp+90h] [rbp-70h]
  __int64 v78; // [rsp+98h] [rbp-68h]
  int v79; // [rsp+A0h] [rbp-60h]
  int v80; // [rsp+A4h] [rbp-5Ch]
  struct _GUID Buf1; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v82[16]; // [rsp+C0h] [rbp-40h] BYREF
  GUID pclsid; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v84; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v85; // [rsp+F0h] [rbp-10h] BYREF
  _WRDS_SETTINGS v86; // [rsp+100h] [rbp+0h] BYREF
  GUID pguid; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v88[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v89[56]; // [rsp+1B0h] [rbp+B0h] BYREF

  v70 = 0;
  v74 = 0;
  v76[0] = &CRegistry::`vftable';
  v76[1] = 0;
  v77 = 0;
  v78 = 0;
  v79 = -1;
  v80 = -1;
  v71 = 0;
  *(_DWORD *)Data = 0;
  v84 = 0;
  if ( (unsigned int)dword_18012E170 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18012E170, 0x470000000000LL, a3) )
  {
    v73 = (struct IListenerItem *)"wwwwwwwwwwwwwwwwT\x00e\x00r\x00m\x00S\x00e\x00r\x00v\x00i\x00c\x00e";
    v72 = (struct IListener *)"desc";
    *(_QWORD *)&Buf1.Data1 = "Termsrv";
    *(_QWORD *)&v85.Data1 = 0x1000000;
    *(_QWORD *)&pclsid.Data1 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      v5,
      (unsigned int)byte_18010D17B,
      v6,
      v7,
      (__int64)&pclsid,
      (__int64)&v85,
      (__int64)&Buf1,
      (__int64)&v72,
      (__int64)&v73);
  }
  CWPPConfig::Refresh((CRemoteConnectionManager *)((char *)this + 264));
  CGenericTrace::CGenericTrace(
    (CGenericTrace *)v89,
    0x10u,
    "CRemoteConnectionManager Starts...",
    "CRemoteConnectionManager::Start");
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v82, (CRemoteConnectionManager *)((char *)this + 1000));
  pguid = 0;
  v8 = GenerateConstrainedGuid(&pguid, 0xF4620000);
  CAutoSetThreadActivityId::CAutoSetThreadActivityId((CAutoSetThreadActivityId *)v88, &pguid);
  if ( v8 < 0 )
  {
    _DbgPrintMessage(
      8,
      "GenerateConstrainedGuid failed: 0x%x in %s",
      (unsigned int)v8,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  if ( *((_BYTE *)this + 2544) )
  {
    v8 = -2147023834;
    _DbgPrintMessage(
      8,
      "RCM Start(): call on termsrv service stop failed: 0x%x in %s",
      2147943462LL,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v9 = (_DWORD *)((char *)this + 1248);
  if ( *((_DWORD *)this + 312) == 1 )
  {
    v8 = -2147418113;
    _DbgPrintMessage(
      8,
      "RCM Start(): Invalid starting state, Start from stopped state failed: 0x%x in %s",
      2147549183LL,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  if ( a2 == 1 )
  {
    MachineGroupPolicy = CRemoteConnectionManager::ReadMachineGroupPolicy(this);
    v8 = MachineGroupPolicy;
    if ( MachineGroupPolicy < 0 )
    {
      _DbgPrintMessage(
        8,
        "this->ReadMachineGroupPolicy failed: 0x%x in %s",
        (unsigned int)MachineGroupPolicy,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v11 = (CProtocolExMgr *)*((_QWORD *)this + 10);
    if ( !v11 )
      goto LABEL_192;
    memset_0(&v86.WRdsSetting, 0, sizeof(v86.WRdsSetting));
    v86.WRdsSettingType = WRDS_SETTING_TYPE_MACHINE;
    v86.WRdsSettingLevel = WRDS_SETTING_LEVEL_1;
    v12 = *((_QWORD *)this + 11);
    if ( v12 )
    {
      v13 = (_DWORD *)(v12 + 4);
      if ( (*(_BYTE *)v12 & 1) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisableClipStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisableClipValue = (*v13 >> 13) & 1;
      }
      if ( (*(_BYTE *)v12 & 8) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisableLPTStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisableLPTValue = *(_WORD *)(v12 + 6) & 1;
      }
      if ( (*(_BYTE *)v12 & 4) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisableCcmStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisableCcmValue = (*v13 >> 15) & 1;
      }
      if ( (*(_DWORD *)v12 & 0x2000000) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisableCdmStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisableCdmValue = (*v13 >> 26) & 1;
      }
      if ( (*(_BYTE *)v12 & 0x10) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisableCpmStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisableCpmValue = (*v13 >> 17) & 1;
      }
      if ( (*(_BYTE *)(v12 + 24) & 8) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisablePnpStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisablePnpValue = (*(_DWORD *)(v12 + 24) >> 4) & 1;
      }
      if ( *(char *)v12 < 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsEncryptionLevelStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsEncryptionValue = *(unsigned __int8 *)(v12 + 36);
      }
      if ( (*(_DWORD *)v12 & 0x10000) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsColorDepthStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsColorDepthValue = (*v13 >> 19) & 7;
      }
      if ( (*(_DWORD *)v12 & 0x200) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisableAutoReconnecetStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisableAutoReconnecetValue = (*(_DWORD *)(v12 + 8) >> 4) & 1;
      }
      if ( (*(_BYTE *)(v12 + 8) & 0x40) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsDisableEncryptionStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsDisableEncryptionValue = (*(_DWORD *)(v12 + 8) >> 7) & 1;
      }
      if ( (*(_DWORD *)v12 & 0x10000000) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsResetBrokenStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsResetBrokenValue = (*v13 >> 28) & 1;
      }
      if ( (*(_BYTE *)v13 & 1) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsMaxIdleTimeStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsMaxIdleTimeValue = *(_DWORD *)(v12 + 2644);
      }
      if ( *(int *)v12 < 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsMaxDisconnectTimeStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsMaxDisconnectTimeValue = *(_DWORD *)(v12 + 2640);
      }
      if ( (*(_DWORD *)v12 & 0x40000000) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsMaxConnectTimeStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsMaxConnectTimeValue = *(_DWORD *)(v12 + 2636);
      }
      if ( (*(_BYTE *)v13 & 0x10) != 0 )
      {
        v86.WRdsSetting.WRdsSettings1.WRdsKeepAliveStatus = WRDS_SETTING_STATUS_ENABLED;
        v86.WRdsSetting.WRdsSettings1.WRdsKeepAliveStartValue = *(_BYTE *)(v12 + 8) & 1;
        v86.WRdsSetting.WRdsSettings1.WRdsKeepAliveIntervalValue = *(_DWORD *)(v12 + 2628);
      }
      v8 = 0;
      CProtocolExMgr::NotifySettingsChange(v11, &v86);
      goto LABEL_192;
    }
    v14 = "CHelper::ConvertPolicySettingsToWRdsSetting failed: 0x%x in %s";
    goto LABEL_190;
  }
  v15 = RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)this + 1208);
  v8 = v15 | 0x10000000;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(
      8,
      "RtlAdjustPrivilege on SE_AUDIT_PRIVILEGE failed: 0x%x in %s",
      (unsigned int)v8,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v16 = CSLQuery::AreRemoteConnectionsAllowed(&v71);
  v8 = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(
      8,
      "CSLQuery::AreRemoteConnectionsAllowed failed: 0x%x in %s",
      (unsigned int)v16,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v17 = v71;
  if ( !v71 && (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(v71 + 2, "Remote Connection is not allow on this edition");
  if ( (unsigned int)CContainerHelper::IsProcessRunningInContainer() )
  {
    v17 = 0;
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "TS in container and so Remote Connection is not allow");
  }
  updated = CRemoteConnectionManager::UpdateWddmModeSettings(this);
  v8 = updated;
  if ( updated < 0 )
  {
    _DbgPrintMessage(
      8,
      "UpdateWddmModeSettings failed: 0x%x in %s",
      (unsigned int)updated,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 63) + 32LL))(*((_QWORD *)this + 63));
  v8 = v19;
  if ( v19 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Enforcement core start failed: 0x%x in %s",
      (unsigned int)v19,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v20 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 67) + 24LL))(*((_QWORD *)this + 67));
  v8 = v20;
  if ( v20 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Connection Dispatcher start failed: 0x%x in %s",
      (unsigned int)v20,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v21 = CTerminalSupportManager::Start(*((CTerminalSupportManager **)this + 155));
  v8 = v21;
  if ( v21 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Terminal Support Mgr start failed: 0x%x in %s",
      (unsigned int)v21,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v22 = CRemoteConnectionManager::RemoveStaleListener(this);
  if ( v22 < 0 )
    _DbgPrintMessage(4, "this->RemoveStaleListener failed 0x%x", v22);
  v23 = CRegistry::OpenKey(
          (CRegistry *)v76,
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0x20019u,
          (const unsigned __int16 *)v68);
  v8 = v23;
  if ( v23 > 0 )
    v8 = (unsigned __int16)v23 | 0x80070000;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Failed to open TS reg key failed: 0x%x in %s",
      (unsigned int)v8,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v79 = 0;
  NextSubKey = CRegistry::GetNextSubKey((CRegistry *)v76, &v74, &v70);
  v25 = NextSubKey;
  if ( NextSubKey > 0 )
    v8 = (unsigned __int16)NextSubKey | 0x80070000;
  else
    v8 = NextSubKey;
  if ( v8 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Failed to read TS reg key failed: 0x%x in %s",
      (unsigned int)v8,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  if ( (int)CSLQuery::IsAppServerInstalled(&v71) < 0 && (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(2, "Checking AppServer failed, assuming non-app-server");
  if ( !(*(unsigned int (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 400LL))(this) )
  {
    started = CGraphicsFactory__StartGraphicsServices();
    v8 = started;
    if ( started < 0 )
    {
      _DbgPrintMessage(
        8,
        "CGraphicsFactory__StartGraphicsServices failed: 0x%x in %s",
        (unsigned int)started,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
  }
  if ( !*((_QWORD *)this + 11) )
    CRemoteConnectionManager::ReadMachineGroupPolicy(this);
  if ( !v17 || v25 )
  {
LABEL_143:
    v45 = CRemoteConnectionManager::StartStopHardcodedListeners(this);
    v8 = v45;
    if ( v45 < 0 )
    {
      _DbgPrintMessage(
        8,
        "this->StartHardcodedListeners failed: 0x%x in %s",
        (unsigned int)v45,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v46 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 64) + 24LL))(*((_QWORD *)this + 64));
    v8 = v46;
    if ( v46 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RCMPrivateRpc->Start failed: 0x%x in %s",
        (unsigned int)v46,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v47 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 65) + 24LL))(*((_QWORD *)this + 65));
    v8 = v47;
    if ( v47 < 0 )
    {
      _DbgPrintMessage(8, "PublicRpc->Start failed: 0x%x in %s", (unsigned int)v47, "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v48 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 65) + 40LL))(*((_QWORD *)this + 65));
    v8 = v48;
    if ( v48 < 0 )
    {
      _DbgPrintMessage(
        8,
        "PublicRpc->StartRemote failed: 0x%x in %s",
        (unsigned int)v48,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v49 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 66) + 24LL))(*((_QWORD *)this + 66));
    v8 = v49;
    if ( v49 < 0 )
    {
      _DbgPrintMessage(8, "LegacyRpc->Start failed: 0x%x in %s", (unsigned int)v49, "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    _DbgPrintMessage(1, "Starting Timer Handler Manager");
    v50 = (CTSTimerHandlerManager *)*((_QWORD *)this + 152);
    if ( v50 )
    {
      v51 = CTSTimerHandlerManager::Start(v50);
      v8 = v51;
      if ( v51 < 0 )
      {
        _DbgPrintMessage(
          8,
          "ptrTimerHandlerManager->Start failed: 0x%x in %s",
          (unsigned int)v51,
          "CRemoteConnectionManager::Start");
        goto LABEL_191;
      }
      _DbgPrintMessage(1, "Done starting Timer Handler Manager");
      v52 = (CExecSessionApps **)((char *)this + 1224);
      if ( !*((_QWORD *)this + 153) )
      {
        v53 = (CExecSessionApps *)operator new(0xC80u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&pclsid.Data1 = v53;
        if ( v53 )
          v54 = CExecSessionApps::CExecSessionApps(v53);
        else
          v54 = 0;
        SmartPtr<ITerminal>::operator=((char *)this + 1224, v54);
        if ( !*v52 )
        {
          v8 = -2147024882;
          _DbgPrintMessage(
            8,
            "FAILED to create CExecSessionApps failed: 0x%x in %s",
            2147942414LL,
            "CRemoteConnectionManager::Start");
          goto LABEL_191;
        }
        v55 = CExecSessionApps::Initialize(*v52);
        v8 = v55;
        if ( v55 < 0 )
        {
          _DbgPrintMessage(
            8,
            "ExecApps.Initialize failed: 0x%x in %s",
            (unsigned int)v55,
            "CRemoteConnectionManager::Start");
          goto LABEL_191;
        }
      }
      CRemoteConnectionManager::UpdateResetLastTimeoutOnAutoReconnect(this);
      DrainMode = CUtils::GetDrainMode(Data);
      v8 = DrainMode;
      if ( DrainMode < 0 )
      {
        _DbgPrintMessage(
          8,
          "CUtils::GetDrainMode failed: 0x%x in %s",
          (unsigned int)DrainMode,
          "CRemoteConnectionManager::Start");
        goto LABEL_191;
      }
      AllowFastReconnect = CUtils::GetAllowFastReconnect((int *)this + 637);
      v8 = AllowFastReconnect;
      if ( AllowFastReconnect < 0 )
      {
        _DbgPrintMessage(
          8,
          "CUtils::GetAllowFastReconnect failed: 0x%x in %s",
          (unsigned int)AllowFastReconnect,
          "CRemoteConnectionManager::Start");
        goto LABEL_191;
      }
      if ( (unsigned int)dword_18012E170 > 5 )
      {
        v71 = *((_DWORD *)this + 637);
        *(_QWORD *)&pclsid.Data1 = "Enabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v58,
          (unsigned int)byte_18010D143,
          v59,
          v60,
          (__int64)&pclsid,
          (__int64)&v71);
      }
      v61 = *((_BYTE *)this + 2536);
      *((_BYTE *)this + 2536) = *(_DWORD *)Data != 0;
      v62 = *((_DWORD *)this + 635);
      if ( (int)CSLQuery::GetUserSessionLimit((int *)this + 635) < 0 )
        *((_DWORD *)this + 635) = 0;
      v84 = 0u;
      if ( !*v9
        || v61 != *((_BYTE *)this + 2536)
        || v62 != (*(unsigned int (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 192LL))(this) )
      {
        LODWORD(v84) = *v9 == 0;
        if ( *((_BYTE *)this + 2536) == 1 )
        {
          DWORD1(v84) = 1;
        }
        else
        {
          v64 = 0;
          if ( v61 == 1 )
            v64 = 2;
          DWORD1(v84) = v64;
        }
        DWORD2(v84) = (*(__int64 (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 192LL))(this) != 0;
        HIDWORD(v84) = (*(__int64 (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 192LL))(this);
        v63 = (CProtocolExMgr *)*((_QWORD *)this + 10);
        if ( v63 )
          CProtocolExMgr::NotifyServiceStateChange(v63, (struct __SERVICESTATECHANGE *)&v84);
      }
      v65 = CRemoteConnectionManager::ChangeRCMReadyEventState(v63, 1);
      v8 = v65;
      if ( v65 < 0 )
      {
        _DbgPrintMessage(4, "this->ChangeRCMReadyEventState for SetEvent failed : 0x%08x", v65);
        v8 = 0;
      }
      CRemoteConnectionManager::StartStopDependentServices(v66, 1);
      RDSHTelemetryLogging::OnRegUpdate();
      StateTracker<enum CRemoteConnectionManager::TState>::operator=((char *)this + 1248, 2);
      goto LABEL_192;
    }
    v14 = "NULL timer manager, cannot start timers. failed: 0x%x in %s";
LABEL_190:
    v8 = -2147024809;
    _DbgPrintMessage(8, v14, 2147942487LL, "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  while ( 1 )
  {
    v72 = 0;
    v27 = v74;
    if ( !(unsigned int)_o__wcsicmp(v74, L"Console") )
      goto LABEL_141;
    if ( (unsigned int)CHardcodedListenerConfig::ListenerTypeFromProtoName(v27) )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Hardcoded listeners %s are stopped and started in a different function", v27);
      goto LABEL_141;
    }
    v69[0] = 0;
    ListenerStart = RegQueryListenerStart(v27, v69);
    ListenerByName = CRemoteConnectionManager::CListenersList::GetListenerByName(
                       (CRemoteConnectionManager *)((char *)this + 280),
                       v27,
                       &v72);
    if ( ListenerStart )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Skipping Listener %ws Start, failed to query listener enablement status", v27);
      goto LABEL_141;
    }
    if ( !v69[0] )
    {
      if ( ListenerByName < 0 )
      {
        if ( (g_DebugTraceComponent & 0x10) != 0 )
          _DbgPrintMessage(2, "Skipping Listener %ws Start, Remote Desktop or listener is disabled", v27);
      }
      else
      {
        if ( (g_DebugTraceComponent & 0x10) != 0 )
          _DbgPrintMessage(2, "Stopping Listener %ws, Remote Desktop or listener is disabled", v27);
        v42 = v72;
        v43 = (*(__int64 (__fastcall **)(struct IListener *))(*(_QWORD *)v72 + 32LL))(v72);
        if ( v43 >= 0 )
        {
          v44 = CRemoteConnectionManager::CListenersList::RemoveListener(
                  (CRemoteConnectionManager *)((char *)this + 280),
                  v42);
          if ( v44 < 0 && (g_DebugTraceComponent & 0x10) != 0 )
            _DbgPrintMessage(2, "Failed to remove listener: %ws, 0x%x", v27, (unsigned int)v44);
        }
        else if ( (g_DebugTraceComponent & 0x10) != 0 )
        {
          _DbgPrintMessage(2, "Failed to stop listener: %ws, 0x%x", v27, (unsigned int)v43);
        }
      }
      goto LABEL_141;
    }
    if ( ListenerByName >= 0 )
      goto LABEL_117;
    v73 = 0;
    v85 = 0;
    v71 = 0;
    ProtocolExtension = CRemoteConnectionManager::GetProtocolExtension(v30, v27, &v71, &v85);
    if ( ProtocolExtension >= 0 )
      break;
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(
        2,
        "GetProtocolExtension for listener %ws failed, error 0x%08x",
        v27,
        (unsigned int)ProtocolExtension);
LABEL_96:
    v32 = CRegistry::GetNextSubKey((CRegistry *)v76, &v74, &v70);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v73);
LABEL_142:
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v72);
    if ( v32 )
      goto LABEL_143;
  }
  if ( v71 != 1 )
  {
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "Ignoring listener %ws, missing protocol GUID", v27);
    goto LABEL_96;
  }
  pclsid = 0;
  if ( !*((_DWORD *)this + 638) )
  {
    Buf1 = v85;
    if ( !(unsigned int)IsRDPProtocol(&Buf1) && !(unsigned int)DoesVMNeedLicensing() )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Listener %ws is not alowed", v27);
      goto LABEL_96;
    }
  }
  if ( (int)CUtils::GetProtocolTerminalClass(v27, &pclsid) >= 0 )
  {
    v34 = pclsid;
  }
  else
  {
    v34 = v85;
    pclsid = v85;
  }
  Buf1 = v34;
  CrimsonHelper::RaiseEvent<unsigned short const *,_GUID>(&CrimsonHelper::s_instance, v33, v27, &Buf1);
  if ( (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(2, "Creating listener %ws", v27);
  v35 = CProtocolExMgr::CreateListener(
          *((CProtocolExMgr **)this + 10),
          this,
          (struct IWRdsProtocolSettings *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          v27,
          &v85,
          &pclsid,
          &v73);
  if ( v35 < 0 )
  {
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "Protocol failed to create listener %ws, error 0x%08x", v27, (unsigned int)v35);
    goto LABEL_96;
  }
  if ( v73 )
  {
    v36 = CRemoteConnectionManager::CListenersList::AddListener((CRemoteConnectionManager *)((char *)this + 280), v73);
    v8 = v36;
    if ( v36 < 0 )
    {
      _DbgPrintMessage(8, "Adding Listeners to list failed: 0x%x in %s", v36, "CRemoteConnectionManager::Start");
      goto LABEL_148;
    }
    SmartPtr<ITerminal>::operator=(&v72, v73);
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "Listener %ws created", v27);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v73);
LABEL_117:
    v37 = (*(__int64 (__fastcall **)(struct IListener *))(*(_QWORD *)v72 + 24LL))(v72);
    v40 = v37;
    if ( v37 >= 0 )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Listener %ws started", v27);
    }
    else
    {
      CHelper::LogErrorEvent(0xC000040B, v37);
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Failed to start listener: %ws, 0x%x", v27, v40);
    }
    v41 = CHelper::LogListenerStartErrorToReg(v27, v40, v38, v39);
    if ( v41 < 0 && (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "LogListenerStartErrorToReg failed", (unsigned int)v41);
LABEL_141:
    v32 = CRegistry::GetNextSubKey((CRegistry *)v76, &v74, &v70);
    goto LABEL_142;
  }
  v8 = -2147024882;
  if ( (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(2, "Can't start listener %ws due to out of resources", v27);
LABEL_148:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v73);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v72);
LABEL_191:
  (*(void (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 48LL))(this);
LABEL_192:
  EtwEventActivityIdControl(2, v88);
  CAutoLock::Unlock((CAutoLock *)v82);
  CGenericTrace::~CGenericTrace((CGenericTrace *)v89);
  CRegistry::~CRegistry((CRegistry *)v76);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18004d4d0  push    rbp
0x18004d4d2  push    rbx
0x18004d4d3  push    rsi
0x18004d4d4  push    rdi
0x18004d4d5  push    r12
0x18004d4d7  push    r13
0x18004d4d9  push    r14
0x18004d4db  push    r15
0x18004d4dd  lea     rbp, [rsp-0F8h]
0x18004d4e5  sub     rsp, 1F8h
0x18004d4ec  mov     rax, cs:__security_cookie
0x18004d4f3  xor     rax, rsp
0x18004d4f6  mov     [rbp+130h+var_48], rax
0x18004d4fd  mov     esi, edx
0x18004d4ff  mov     rdi, rcx
0x18004d502  xor     r12d, r12d
0x18004d505  mov     [rsp+230h+var_1DC], r12d
0x18004d50a  mov     [rsp+230h+var_1C0], r12
0x18004d50f  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18004d516  mov     [rbp+130h+var_1B0], rax
0x18004d51a  mov     [rbp+130h+var_1A8], r12
0x18004d51e  mov     [rbp+130h+var_1A0], r12d
0x18004d522  mov     [rbp+130h+var_198], r12
0x18004d526  or      eax, 0FFFFFFFFh
0x18004d529  mov     [rbp+130h+var_190], eax
0x18004d52c  mov     [rbp+130h+var_18C], eax
0x18004d52f  mov     [rsp+230h+var_1D8], r12d
0x18004d534  mov     dword ptr [rsp+230h+Data], r12d
0x18004d539  xorps   xmm0, xmm0
0x18004d53c  movups  [rbp+130h+var_150], xmm0
0x18004d540  mov     eax, cs:dword_18012E170
0x18004d546  cmp     eax, 4
0x18004d549  jbe     loc_18004D5DA
0x18004d54f  mov     rdx, 470000000000h
0x18004d559  lea     rcx, dword_18012E170
0x18004d560  call    _tlgKeywordOn
0x18004d565  test    al, al
0x18004d567  jz      short loc_18004D5DA
0x18004d569  lea     rax, aWwwwwwwwwwwwww; "wwwwwwwwwwwwwwwwT\x00e\x00r\x00m\x00S"...
0x18004d570  mov     [rsp+230h+var_1C8], rax
0x18004d575  lea     rax, aDesc; "desc"
0x18004d57c  mov     [rsp+230h+var_1D0], rax
0x18004d581  lea     rax, aTermsrv_1; "Termsrv"
0x18004d588  mov     qword ptr [rbp+130h+Buf1.Data1], rax
0x18004d58c  mov     qword ptr [rbp+130h+var_140.Data1], 1000000h
0x18004d594  lea     rax, aCheckpoint; "Checkpoint"
0x18004d59b  mov     qword ptr [rbp+130h+pclsid.Data1], rax
0x18004d59f  lea     rax, [rsp+230h+var_1C8]
0x18004d5a4  mov     [rsp+230h+var_1F0], rax
0x18004d5a9  lea     rax, [rsp+230h+var_1D0]
0x18004d5ae  mov     [rsp+230h+var_1F8], rax
0x18004d5b3  lea     rax, [rbp+130h+Buf1]
0x18004d5b7  mov     [rsp+230h+var_200], rax
0x18004d5bc  lea     rax, [rbp+130h+var_140]
0x18004d5c0  mov     [rsp+230h+var_208], rax
0x18004d5c5  lea     rax, [rbp+130h+pclsid]
0x18004d5c9  mov     [rsp+230h+var_210], rax; unsigned __int16 *
0x18004d5ce  lea     rdx, byte_18010D17B
0x18004d5d5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x18004d5da  lea     rcx, [rdi+108h]; this
0x18004d5e1  call    ?Refresh@CWPPConfig@@QEAAJXZ; CWPPConfig::Refresh(void)
0x18004d5e6  lea     r14, aCremoteconnect; "CRemoteConnectionManager::Start"
0x18004d5ed  mov     r9, r14; char *
0x18004d5f0  lea     r8, aCremoteconnect_18; "CRemoteConnectionManager Starts..."
0x18004d5f7  mov     edx, 10h; unsigned int
0x18004d5fc  lea     rcx, [rbp+130h+var_80]; this
0x18004d603  call    ??0CGenericTrace@@QEAA@KPEBD0@Z; CGenericTrace::CGenericTrace(ulong,char const *,char const *)
0x18004d608  nop
0x18004d609  lea     rdx, [rdi+3E8h]; struct CResource *
0x18004d610  lea     rcx, [rbp+130h+var_170]; this
0x18004d614  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18004d619  nop
0x18004d61a  xorps   xmm0, xmm0
0x18004d61d  movups  xmmword ptr [rbp+130h+pguid.Data1], xmm0
0x18004d624  mov     edx, 0F4620000h; unsigned int
0x18004d629  lea     rcx, [rbp+130h+pguid]; pguid
0x18004d630  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x18004d635  mov     ebx, eax
0x18004d637  lea     rdx, [rbp+130h+pguid]; struct _GUID *
0x18004d63e  lea     rcx, [rbp+130h+var_90]; this
0x18004d645  call    ??0CAutoSetThreadActivityId@@QEAA@PEBU_GUID@@@Z; CAutoSetThreadActivityId::CAutoSetThreadActivityId(_GUID const *)
0x18004d64a  nop
0x18004d64b  test    ebx, ebx
0x18004d64d  jns     short loc_18004D661
0x18004d64f  mov     r9, r14
0x18004d652  mov     r8d, ebx
0x18004d655  lea     rdx, aGenerateconstr; "GenerateConstrainedGuid failed: 0x%x in"...
0x18004d65c  jmp     loc_18004E286
0x18004d661  cmp     [rdi+9F0h], r12b
0x18004d668  jz      short loc_18004D681
0x18004d66a  mov     ebx, 80070426h
0x18004d66f  mov     r9, r14
0x18004d672  mov     r8d, ebx
0x18004d675  lea     rdx, aRcmStartCallOn; "RCM Start(): call on termsrv service st"...
0x18004d67c  jmp     loc_18004E286
0x18004d681  lea     r15, [rdi+4E0h]
0x18004d688  mov     r13d, 1
0x18004d68e  cmp     [r15], r13d
0x18004d691  jnz     short loc_18004D6AA
0x18004d693  mov     ebx, 8000FFFFh
0x18004d698  mov     r9, r14
0x18004d69b  mov     r8d, ebx
0x18004d69e  lea     rdx, aRcmStartInvali; "RCM Start(): Invalid starting state, St"...
0x18004d6a5  jmp     loc_18004E286
0x18004d6aa  cmp     esi, r13d
0x18004d6ad  jnz     loc_18004D86A
0x18004d6b3  mov     rcx, rdi; this
0x18004d6b6  call    ?ReadMachineGroupPolicy@CRemoteConnectionManager@@AEAAJXZ; CRemoteConnectionManager::ReadMachineGroupPolicy(void)
0x18004d6bb  mov     ebx, eax
0x18004d6bd  test    eax, eax
0x18004d6bf  jns     short loc_18004D6D3
0x18004d6c1  mov     r9, r14
0x18004d6c4  mov     r8d, eax
0x18004d6c7  lea     rdx, aThisReadmachin; "this->ReadMachineGroupPolicy failed: 0x"...
0x18004d6ce  jmp     loc_18004E286
0x18004d6d3  mov     rsi, [rdi+50h]
0x18004d6d7  test    rsi, rsi
0x18004d6da  jz      loc_18004E2A0
0x18004d6e0  xor     edx, edx; Val
0x18004d6e2  lea     r8d, [rdx+7Ch]; Size
0x18004d6e6  lea     rcx, [rbp+130h+var_130.WRdsSetting]; void *
0x18004d6ea  call    memset_0
0x18004d6ef  mov     [rbp+130h+var_130.WRdsSettingType], r13d
0x18004d6f3  mov     [rbp+130h+var_130.WRdsSettingLevel], r13d
0x18004d6f7  mov     rcx, [rdi+58h]
0x18004d6fb  test    rcx, rcx
0x18004d6fe  jz      loc_18004D85B
0x18004d704  lea     rdx, [rcx+4]
0x18004d708  test    [rcx], r13b
0x18004d70b  jz      short loc_18004D71C
0x18004d70d  mov     dword ptr [rbp+130h+var_130.WRdsSetting], r13d
0x18004d711  mov     eax, [rdx]
0x18004d713  shr     eax, 0Dh
0x18004d716  and     eax, r13d
0x18004d719  mov     dword ptr [rbp+130h+var_130.WRdsSetting+4], eax
0x18004d71c  test    byte ptr [rcx], 8
0x18004d71f  jz      short loc_18004D72F
0x18004d721  mov     dword ptr [rbp+130h+var_130.WRdsSetting+8], r13d
0x18004d725  movzx   eax, word ptr [rdx+2]
0x18004d729  and     eax, r13d
0x18004d72c  mov     dword ptr [rbp+130h+var_130.WRdsSetting+0Ch], eax
0x18004d72f  test    byte ptr [rcx], 4
0x18004d732  jz      short loc_18004D743
0x18004d734  mov     dword ptr [rbp+130h+var_130.WRdsSetting+10h], r13d
0x18004d738  mov     eax, [rdx]
0x18004d73a  shr     eax, 0Fh
0x18004d73d  and     eax, r13d
0x18004d740  mov     dword ptr [rbp+130h+var_130.WRdsSetting+14h], eax
0x18004d743  test    dword ptr [rcx], 2000000h
0x18004d749  jz      short loc_18004D75A
0x18004d74b  mov     dword ptr [rbp+130h+var_130.WRdsSetting+18h], r13d
0x18004d74f  mov     eax, [rdx]
0x18004d751  shr     eax, 1Ah
0x18004d754  and     eax, r13d
0x18004d757  mov     dword ptr [rbp+130h+var_130.WRdsSetting+1Ch], eax
0x18004d75a  test    byte ptr [rcx], 10h
0x18004d75d  jz      short loc_18004D76E
0x18004d75f  mov     dword ptr [rbp+130h+var_130.WRdsSetting+20h], r13d
0x18004d763  mov     eax, [rdx]
0x18004d765  shr     eax, 11h
0x18004d768  and     eax, r13d
0x18004d76b  mov     dword ptr [rbp+130h+var_130.WRdsSetting+24h], eax
0x18004d76e  test    byte ptr [rcx+18h], 8
0x18004d772  jz      short loc_18004D784
0x18004d774  mov     dword ptr [rbp+130h+var_130.WRdsSetting+28h], r13d
0x18004d778  mov     eax, [rcx+18h]
0x18004d77b  shr     eax, 4
0x18004d77e  and     eax, r13d
0x18004d781  mov     dword ptr [rbp+130h+var_130.WRdsSetting+2Ch], eax
0x18004d784  test    byte ptr [rcx], 80h
0x18004d787  jz      short loc_18004D794
0x18004d789  mov     dword ptr [rbp+130h+var_130.WRdsSetting+30h], r13d
0x18004d78d  movzx   eax, byte ptr [rcx+24h]
0x18004d791  mov     dword ptr [rbp+130h+var_130.WRdsSetting+34h], eax
0x18004d794  test    dword ptr [rcx], 10000h
0x18004d79a  jz      short loc_18004D7AB
0x18004d79c  mov     dword ptr [rbp+130h+var_130.WRdsSetting+38h], r13d
0x18004d7a0  mov     eax, [rdx]
0x18004d7a2  shr     eax, 13h
0x18004d7a5  and     eax, 7
0x18004d7a8  mov     dword ptr [rbp+130h+var_130.WRdsSetting+3Ch], eax
0x18004d7ab  test    dword ptr [rcx], 200h
0x18004d7b1  jz      short loc_18004D7C3
0x18004d7b3  mov     dword ptr [rbp+130h+var_130.WRdsSetting+40h], r13d
0x18004d7b7  mov     eax, [rcx+8]
0x18004d7ba  shr     eax, 4
0x18004d7bd  and     eax, r13d
0x18004d7c0  mov     dword ptr [rbp+130h+var_130.WRdsSetting+44h], eax
0x18004d7c3  test    byte ptr [rcx+8], 40h
0x18004d7c7  jz      short loc_18004D7D9
0x18004d7c9  mov     dword ptr [rbp+130h+var_130.WRdsSetting+48h], r13d
0x18004d7cd  mov     eax, [rcx+8]
0x18004d7d0  shr     eax, 7
0x18004d7d3  and     eax, r13d
0x18004d7d6  mov     dword ptr [rbp+130h+var_130.WRdsSetting+4Ch], eax
0x18004d7d9  test    dword ptr [rcx], 10000000h
0x18004d7df  jz      short loc_18004D7F0
0x18004d7e1  mov     dword ptr [rbp+130h+var_130.WRdsSetting+50h], r13d
0x18004d7e5  mov     eax, [rdx]
0x18004d7e7  shr     eax, 1Ch
0x18004d7ea  and     eax, r13d
0x18004d7ed  mov     dword ptr [rbp+130h+var_130.WRdsSetting+54h], eax
0x18004d7f0  test    [rdx], r13b
0x18004d7f3  jz      short loc_18004D802
0x18004d7f5  mov     dword ptr [rbp+130h+var_130.WRdsSetting+58h], r13d
0x18004d7f9  mov     eax, [rcx+0A54h]
0x18004d7ff  mov     dword ptr [rbp+130h+var_130.WRdsSetting+5Ch], eax
0x18004d802  cmp     [rcx], r12d
0x18004d805  jge     short loc_18004D814
0x18004d807  mov     dword ptr [rbp+130h+var_130.WRdsSetting+60h], r13d
0x18004d80b  mov     eax, [rcx+0A50h]
0x18004d811  mov     dword ptr [rbp+130h+var_130.WRdsSetting+64h], eax
0x18004d814  test    dword ptr [rcx], 40000000h
0x18004d81a  jz      short loc_18004D829
0x18004d81c  mov     dword ptr [rbp+130h+var_130.WRdsSetting+68h], r13d
0x18004d820  mov     eax, [rcx+0A4Ch]
0x18004d826  mov     dword ptr [rbp+130h+var_130.WRdsSetting+6Ch], eax
0x18004d829  test    byte ptr [rdx], 10h
0x18004d82c  jz      short loc_18004D847
0x18004d82e  mov     dword ptr [rbp+130h+var_130.WRdsSetting+70h], r13d
0x18004d832  mov     al, [rcx+8]
0x18004d835  and     al, r13b
0x18004d838  mov     byte ptr [rbp+130h+var_130.WRdsSetting+74h], al
0x18004d83b  mov     eax, [rcx+0A44h]
0x18004d841  mov     dword ptr [rbp+130h+var_130.WRdsSetting+78h], eax
0x18004d847  mov     ebx, r12d
0x18004d84a  lea     rdx, [rbp+130h+var_130]; struct _WRDS_SETTINGS *
0x18004d84e  mov     rcx, rsi; this
0x18004d851  call    ?NotifySettingsChange@CProtocolExMgr@@QEAAJPEAU_WRDS_SETTINGS@@@Z; CProtocolExMgr::NotifySettingsChange(_WRDS_SETTINGS *)
0x18004d856  jmp     loc_18004E2A0
0x18004d85b  mov     r9, r14
0x18004d85e  lea     rdx, aChelperConvert; "CHelper::ConvertPolicySettingsToWRdsSet"...
0x18004d865  jmp     loc_18004E27D
0x18004d86a  lea     r9, [rdi+4B8h]; OldValue
0x18004d871  xor     r8d, r8d; ForThread
0x18004d874  mov     dl, r13b; NewValue
0x18004d877  lea     ecx, [r8+15h]; Privilege
0x18004d87b  call    cs:__imp_RtlAdjustPrivilege
0x18004d882  nop     dword ptr [rax+rax+00h]
0x18004d887  mov     ebx, eax
0x18004d889  or      ebx, 10000000h
0x18004d88f  jge     short loc_18004D8A3
0x18004d891  mov     r9, r14
0x18004d894  mov     r8d, ebx
0x18004d897  lea     rdx, aRtladjustprivi; "RtlAdjustPrivilege on SE_AUDIT_PRIVILEG"...
0x18004d89e  jmp     loc_18004E286
0x18004d8a3  lea     rcx, [rsp+230h+var_1D8]; int *
0x18004d8a8  call    ?AreRemoteConnectionsAllowed@CSLQuery@@SAJPEAH@Z; CSLQuery::AreRemoteConnectionsAllowed(int *)
0x18004d8ad  mov     ebx, eax
0x18004d8af  test    eax, eax
0x18004d8b1  jns     short loc_18004D8C5
0x18004d8b3  mov     r9, r14
0x18004d8b6  mov     r8d, eax
0x18004d8b9  lea     rdx, aCslqueryArerem_0; "CSLQuery::AreRemoteConnectionsAllowed f"...
0x18004d8c0  jmp     loc_18004E286
0x18004d8c5  mov     r14d, [rsp+230h+var_1D8]
0x18004d8ca  test    r14d, r14d
0x18004d8cd  jnz     short loc_18004D8E8
0x18004d8cf  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 10h; ulong g_DebugTraceComponent
0x18004d8d6  jz      short loc_18004D8E8
0x18004d8d8  lea     rdx, aRemoteConnecti_0; "Remote Connection is not allow on this "...
0x18004d8df  lea     ecx, [r14+2]; int
0x18004d8e3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d8e8  call    ?IsProcessRunningInContainer@CContainerHelper@@SAHXZ; CContainerHelper::IsProcessRunningInContainer(void)
0x18004d8ed  test    eax, eax
0x18004d8ef  jz      short loc_18004D90E
0x18004d8f1  mov     r14d, r12d
0x18004d8f4  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 10h; ulong g_DebugTraceComponent
0x18004d8fb  jz      short loc_18004D90E
0x18004d8fd  lea     rdx, aTsInContainerA; "TS in container and so Remote Connectio"...
0x18004d904  mov     ecx, 2; int
0x18004d909  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004d90e  mov     rcx, rdi; this
0x18004d911  call    ?UpdateWddmModeSettings@CRemoteConnectionManager@@AEAAJXZ; CRemoteConnectionManager::UpdateWddmModeSettings(void)
0x18004d916  mov     ebx, eax
0x18004d918  test    eax, eax
0x18004d91a  jns     short loc_18004D932
0x18004d91c  lea     r9, aCremoteconnect; "CRemoteConnectionManager::Start"
0x18004d923  mov     r8d, eax
0x18004d926  lea     rdx, aUpdatewddmmode; "UpdateWddmModeSettings failed: 0x%x in "...
0x18004d92d  jmp     loc_18004E286
0x18004d932  mov     rcx, [rdi+1F8h]
0x18004d939  mov     rax, [rcx]
0x18004d93c  mov     rax, [rax+20h]
0x18004d940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d945  mov     ebx, eax
0x18004d947  test    eax, eax
0x18004d949  jns     short loc_18004D961
0x18004d94b  lea     r9, aCremoteconnect; "CRemoteConnectionManager::Start"
0x18004d952  mov     r8d, eax
0x18004d955  lea     rdx, aEnforcementCor; "Enforcement core start failed: 0x%x in "...
0x18004d95c  jmp     loc_18004E286
0x18004d961  mov     rcx, [rdi+218h]
0x18004d968  mov     rax, [rcx]
0x18004d96b  mov     rax, [rax+18h]
0x18004d96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d974  mov     ebx, eax
0x18004d976  test    eax, eax
0x18004d978  jns     short loc_18004D990
0x18004d97a  lea     r9, aCremoteconnect; "CRemoteConnectionManager::Start"
  ... truncated ...
```
