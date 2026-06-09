# CRemoteConnectionManager::Start(ulong)

- ea: `0x18004aeb0`
- end: `0x18004bcd4`
- name: `?Start@CRemoteConnectionManager@@UEAAJK@Z`
- size: `3620`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *this, int)`
- caller_count: `0`
- callee_count: `54`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001284`
- `0x180002544`
- `0x180007460`
- `0x180009ee0`
- `0x18000a210`
- `0x180011f80`
- `0x180013150`
- `0x1800181e0`
- `0x1800241f0`
- `0x180024d80`
- `0x180026148`
- `0x180026f6c`
- `0x18002739c`
- `0x1800279a8`
- `0x180027b44`
- `0x180027d54`
- `0x18002869c`
- `0x18002dddc`
- `0x1800321f0`
- `0x1800326dc`
- `0x1800330c4`
- `0x18003bdd0`
- `0x18003cb40`
- `0x18003e770`
- `0x18003f898`
- `0x180045758`
- `0x180046018`
- `0x180046ea0`
- `0x180046f64`
- `0x180047040`
- `0x180048b94`
- `0x18004a180`
- `0x18004aeb0`
- `0x18004c2b8`
- `0x18004c46c`
- `0x18004e748`
- `0x18004e8a4`
- `0x1800708cc`
- `0x18007a5bc`
- `0x18008775c`
- `0x180087eec`
- `0x1800881b4`
- `0x18008f758`
- `0x180092f84`
- `0x180093758`
- `0x18009d0c0`
- `0x18009d360`
- `0x18009ebfc`
- `0x1800af2dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b4dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004b4dc`
- `ntdll!RtlAdjustPrivilege` at `0x18004b269`
- `ntdll!RtlAdjustPrivilege` at `0x18004b269`
- `ntdll!EtwEventActivityIdControl` at `0x18004b032`
- `ntdll!EtwEventActivityIdControl` at `0x18004bc88`
- `ntdll!EtwEventActivityIdControl` at `0x18004b032`
- `ntdll!EtwEventActivityIdControl` at `0x18004bc88`
- `REGAPI!RegQueryListenerStart` at `0x18004b51c`
- `REGAPI!RegQueryListenerStart` at `0x18004b51c`

## string_xrefs

- `0x18004b063`: `RCM Start(): call on termsrv service stop failed: 0x%x in %s`
- `0x18004b0b5`: `this->ReadMachineGroupPolicy failed: 0x%x in %s`
- `0x18004b27f`: `RtlAdjustPrivilege on SE_AUDIT_PRIVILEGE failed: 0x%x in %s`
- `0x18004b30e`: `UpdateWddmModeSettings failed: 0x%x in %s`
- `0x18004b3af`: `this->RemoveStaleListener failed 0x%x`
- `0x18004b3fa`: `Failed to open TS reg key failed: 0x%x in %s`
- `0x18004b43e`: `Failed to read TS reg key failed: 0x%x in %s`
- `0x18004b49d`: `CGraphicsFactory__StartGraphicsServices failed: 0x%x in %s`
- `0x18004b585`: `GetProtocolExtension for listener %ws failed, error 0x%08x`
- `0x18004b6b8`: `Protocol failed to create listener %ws, error 0x%08x`
- `0x18004b76d`: `Ignoring listener %ws, missing protocol GUID`
- `0x18004b6ff`: `Listener %ws created`
- `0x18004b841`: `Failed to remove listener: %ws, 0x%x`
- `0x18004ba7e`: `FAILED to create CExecSessionApps failed: 0x%x in %s`
- `0x18004bc1b`: `this->ChangeRCMReadyEventState for SetEvent failed : 0x%08x`
- `0x18004af49`: `wwwwwwwwwwwwwwwwTermService`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteConnectionManager::Start(CRemoteConnectionManager *this, int a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int v7; // ebx
  _DWORD *v8; // r15
  int MachineGroupPolicy; // eax
  CProtocolExMgr *v10; // rsi
  __int64 v11; // rcx
  _DWORD *v12; // rdx
  const char *v13; // rdx
  NTSTATUS v14; // eax
  int v15; // eax
  int v16; // r14d
  int updated; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int NextSubKey; // eax
  int v24; // esi
  int started; // eax
  unsigned __int16 *v26; // rsi
  int ListenerStart; // ebx
  int ListenerByName; // eax
  CRemoteConnectionManager *v29; // rcx
  int ProtocolExtension; // eax
  unsigned int v31; // ebx
  __int64 v32; // rdx
  GUID v33; // xmm0
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // r8d
  int v38; // r9d
  unsigned int v39; // ebx
  int v40; // eax
  struct IListener *v41; // rbx
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  int v48; // eax
  CTSTimerHandlerManager *v49; // rcx
  int v50; // eax
  CExecSessionApps **v51; // rbx
  CExecSessionApps *v52; // rax
  CExecSessionApps *v53; // rax
  int v54; // eax
  int DrainMode; // eax
  int AllowFastReconnect; // eax
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  char v60; // si
  int v61; // r14d
  CProtocolExMgr *v62; // rcx
  int v63; // eax
  int v64; // eax
  CRemoteConnectionManager *v65; // rcx
  struct _GUID *v67; // [rsp+20h] [rbp-E0h]
  _BYTE v68[4]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v69; // [rsp+54h] [rbp-ACh] BYREF
  int v70; // [rsp+58h] [rbp-A8h] BYREF
  struct IListener *v71; // [rsp+60h] [rbp-A0h] BYREF
  struct IListenerItem *v72; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v73; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v75[2]; // [rsp+80h] [rbp-80h] BYREF
  int v76; // [rsp+90h] [rbp-70h]
  __int64 v77; // [rsp+98h] [rbp-68h]
  int v78; // [rsp+A0h] [rbp-60h]
  int v79; // [rsp+A4h] [rbp-5Ch]
  struct _GUID Buf1; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v81[16]; // [rsp+C0h] [rbp-40h] BYREF
  GUID pclsid; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v83; // [rsp+E0h] [rbp-20h] BYREF
  struct _GUID v84; // [rsp+F0h] [rbp-10h] BYREF
  _WRDS_SETTINGS v85; // [rsp+100h] [rbp+0h] BYREF
  GUID pguid; // [rsp+190h] [rbp+90h] BYREF
  GUID v87; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v88[56]; // [rsp+1B0h] [rbp+B0h] BYREF

  v69 = 0;
  v73 = 0;
  v75[0] = &CRegistry::`vftable';
  v75[1] = 0;
  v76 = 0;
  v77 = 0;
  v78 = -1;
  v79 = -1;
  v70 = 0;
  *(_DWORD *)Data = 0;
  v83 = 0;
  if ( (unsigned int)dword_180128170 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180128170, 0x470000000000LL) )
  {
    v72 = (struct IListenerItem *)"wwwwwwwwwwwwwwwwT\x00e\x00r\x00m\x00S\x00e\x00r\x00v\x00i\x00c\x00e";
    v71 = (struct IListener *)"desc";
    *(_QWORD *)&Buf1.Data1 = "Termsrv";
    *(_QWORD *)&v84.Data1 = 0x1000000;
    *(_QWORD *)&pclsid.Data1 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(
      v4,
      (unsigned int)byte_1801070FB,
      v5,
      v6,
      (__int64)&pclsid,
      (__int64)&v84,
      (__int64)&Buf1,
      (__int64)&v71,
      (__int64)&v72);
  }
  CWPPConfig::Refresh((CRemoteConnectionManager *)((char *)this + 264));
  CGenericTrace::CGenericTrace(
    (CGenericTrace *)v88,
    0x10u,
    "CRemoteConnectionManager Starts...",
    "CRemoteConnectionManager::Start");
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v81, (CRemoteConnectionManager *)((char *)this + 1000));
  pguid = 0;
  v7 = GenerateConstrainedGuid(&pguid, 0xF4620000);
  v87 = pguid;
  EtwEventActivityIdControl(4, &v87);
  if ( v7 < 0 )
  {
    _DbgPrintMessage(
      8,
      "GenerateConstrainedGuid failed: 0x%x in %s",
      (unsigned int)v7,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  if ( *((_BYTE *)this + 2544) )
  {
    v7 = -2147023834;
    _DbgPrintMessage(
      8,
      "RCM Start(): call on termsrv service stop failed: 0x%x in %s",
      2147943462LL,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v8 = (_DWORD *)((char *)this + 1248);
  if ( *((_DWORD *)this + 312) == 1 )
  {
    v7 = -2147418113;
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
    v7 = MachineGroupPolicy;
    if ( MachineGroupPolicy < 0 )
    {
      _DbgPrintMessage(
        8,
        "this->ReadMachineGroupPolicy failed: 0x%x in %s",
        (unsigned int)MachineGroupPolicy,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v10 = (CProtocolExMgr *)*((_QWORD *)this + 10);
    if ( !v10 )
      goto LABEL_192;
    memset_0(&v85.WRdsSetting, 0, sizeof(v85.WRdsSetting));
    v85.WRdsSettingType = WRDS_SETTING_TYPE_MACHINE;
    v85.WRdsSettingLevel = WRDS_SETTING_LEVEL_1;
    v11 = *((_QWORD *)this + 11);
    if ( v11 )
    {
      v12 = (_DWORD *)(v11 + 4);
      if ( (*(_BYTE *)v11 & 1) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisableClipStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisableClipValue = (*v12 >> 13) & 1;
      }
      if ( (*(_BYTE *)v11 & 8) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisableLPTStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisableLPTValue = *(_WORD *)(v11 + 6) & 1;
      }
      if ( (*(_BYTE *)v11 & 4) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisableCcmStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisableCcmValue = (*v12 >> 15) & 1;
      }
      if ( (*(_DWORD *)v11 & 0x2000000) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisableCdmStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisableCdmValue = (*v12 >> 26) & 1;
      }
      if ( (*(_BYTE *)v11 & 0x10) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisableCpmStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisableCpmValue = (*v12 >> 17) & 1;
      }
      if ( (*(_BYTE *)(v11 + 24) & 8) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisablePnpStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisablePnpValue = (*(_DWORD *)(v11 + 24) >> 4) & 1;
      }
      if ( *(char *)v11 < 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsEncryptionLevelStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsEncryptionValue = *(unsigned __int8 *)(v11 + 36);
      }
      if ( (*(_DWORD *)v11 & 0x10000) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsColorDepthStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsColorDepthValue = (*v12 >> 19) & 7;
      }
      if ( (*(_DWORD *)v11 & 0x200) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisableAutoReconnecetStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisableAutoReconnecetValue = (*(_DWORD *)(v11 + 8) >> 4) & 1;
      }
      if ( (*(_BYTE *)(v11 + 8) & 0x40) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsDisableEncryptionStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsDisableEncryptionValue = (*(_DWORD *)(v11 + 8) >> 7) & 1;
      }
      if ( (*(_DWORD *)v11 & 0x10000000) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsResetBrokenStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsResetBrokenValue = (*v12 >> 28) & 1;
      }
      if ( (*(_BYTE *)v12 & 1) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsMaxIdleTimeStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsMaxIdleTimeValue = *(_DWORD *)(v11 + 2644);
      }
      if ( *(int *)v11 < 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsMaxDisconnectTimeStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsMaxDisconnectTimeValue = *(_DWORD *)(v11 + 2640);
      }
      if ( (*(_DWORD *)v11 & 0x40000000) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsMaxConnectTimeStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsMaxConnectTimeValue = *(_DWORD *)(v11 + 2636);
      }
      if ( (*(_BYTE *)v12 & 0x10) != 0 )
      {
        v85.WRdsSetting.WRdsSettings1.WRdsKeepAliveStatus = WRDS_SETTING_STATUS_ENABLED;
        v85.WRdsSetting.WRdsSettings1.WRdsKeepAliveStartValue = *(_BYTE *)(v11 + 8) & 1;
        v85.WRdsSetting.WRdsSettings1.WRdsKeepAliveIntervalValue = *(_DWORD *)(v11 + 2628);
      }
      v7 = 0;
      CProtocolExMgr::NotifySettingsChange(v10, &v85);
      goto LABEL_192;
    }
    v13 = "CHelper::ConvertPolicySettingsToWRdsSetting failed: 0x%x in %s";
    goto LABEL_190;
  }
  v14 = RtlAdjustPrivilege(0x15u, 1u, 0, (PBOOLEAN)this + 1208);
  v7 = v14 | 0x10000000;
  if ( v14 < 0 )
  {
    _DbgPrintMessage(
      8,
      "RtlAdjustPrivilege on SE_AUDIT_PRIVILEGE failed: 0x%x in %s",
      (unsigned int)v7,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v15 = CSLQuery::AreRemoteConnectionsAllowed(&v70);
  v7 = v15;
  if ( v15 < 0 )
  {
    _DbgPrintMessage(
      8,
      "CSLQuery::AreRemoteConnectionsAllowed failed: 0x%x in %s",
      (unsigned int)v15,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v16 = v70;
  if ( !v70 && (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(v70 + 2, "Remote Connection is not allow on this edition");
  if ( (unsigned int)CContainerHelper::IsProcessRunningInContainer() )
  {
    v16 = 0;
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "TS in container and so Remote Connection is not allow");
  }
  updated = CRemoteConnectionManager::UpdateWddmModeSettings(this);
  v7 = updated;
  if ( updated < 0 )
  {
    _DbgPrintMessage(
      8,
      "UpdateWddmModeSettings failed: 0x%x in %s",
      (unsigned int)updated,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 63) + 32LL))(*((_QWORD *)this + 63));
  v7 = v18;
  if ( v18 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Enforcement core start failed: 0x%x in %s",
      (unsigned int)v18,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 67) + 24LL))(*((_QWORD *)this + 67));
  v7 = v19;
  if ( v19 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Connection Dispatcher start failed: 0x%x in %s",
      (unsigned int)v19,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v20 = CTerminalSupportManager::Start(*((CTerminalSupportManager **)this + 155));
  v7 = v20;
  if ( v20 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Terminal Support Mgr start failed: 0x%x in %s",
      (unsigned int)v20,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v21 = CRemoteConnectionManager::RemoveStaleListener(this);
  if ( v21 < 0 )
    _DbgPrintMessage(4, "this->RemoveStaleListener failed 0x%x", v21);
  v22 = CRegistry::OpenKey(
          (CRegistry *)v75,
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0x20019u,
          (const unsigned __int16 *)v67);
  v7 = v22;
  if ( v22 > 0 )
    v7 = (unsigned __int16)v22 | 0x80070000;
  if ( v7 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Failed to open TS reg key failed: 0x%x in %s",
      (unsigned int)v7,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  v78 = 0;
  NextSubKey = CRegistry::GetNextSubKey((CRegistry *)v75, &v73, &v69);
  v24 = NextSubKey;
  if ( NextSubKey > 0 )
    v7 = (unsigned __int16)NextSubKey | 0x80070000;
  else
    v7 = NextSubKey;
  if ( v7 < 0 )
  {
    _DbgPrintMessage(
      8,
      "Failed to read TS reg key failed: 0x%x in %s",
      (unsigned int)v7,
      "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  if ( (int)CSLQuery::IsAppServerInstalled(&v70) < 0 && (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(2, "Checking AppServer failed, assuming non-app-server");
  if ( !(*(unsigned int (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 400LL))(this) )
  {
    started = CGraphicsFactory__StartGraphicsServices();
    v7 = started;
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
  if ( !v16 || v24 )
  {
LABEL_143:
    v44 = CRemoteConnectionManager::StartStopHardcodedListeners(this);
    v7 = v44;
    if ( v44 < 0 )
    {
      _DbgPrintMessage(
        8,
        "this->StartHardcodedListeners failed: 0x%x in %s",
        (unsigned int)v44,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v45 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 64) + 24LL))(*((_QWORD *)this + 64));
    v7 = v45;
    if ( v45 < 0 )
    {
      _DbgPrintMessage(
        8,
        "RCMPrivateRpc->Start failed: 0x%x in %s",
        (unsigned int)v45,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v46 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 65) + 24LL))(*((_QWORD *)this + 65));
    v7 = v46;
    if ( v46 < 0 )
    {
      _DbgPrintMessage(8, "PublicRpc->Start failed: 0x%x in %s", (unsigned int)v46, "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v47 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 65) + 40LL))(*((_QWORD *)this + 65));
    v7 = v47;
    if ( v47 < 0 )
    {
      _DbgPrintMessage(
        8,
        "PublicRpc->StartRemote failed: 0x%x in %s",
        (unsigned int)v47,
        "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    v48 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 66) + 24LL))(*((_QWORD *)this + 66));
    v7 = v48;
    if ( v48 < 0 )
    {
      _DbgPrintMessage(8, "LegacyRpc->Start failed: 0x%x in %s", (unsigned int)v48, "CRemoteConnectionManager::Start");
      goto LABEL_191;
    }
    _DbgPrintMessage(1, "Starting Timer Handler Manager");
    v49 = (CTSTimerHandlerManager *)*((_QWORD *)this + 152);
    if ( v49 )
    {
      v50 = CTSTimerHandlerManager::Start(v49);
      v7 = v50;
      if ( v50 < 0 )
      {
        _DbgPrintMessage(
          8,
          "ptrTimerHandlerManager->Start failed: 0x%x in %s",
          (unsigned int)v50,
          "CRemoteConnectionManager::Start");
        goto LABEL_191;
      }
      _DbgPrintMessage(1, "Done starting Timer Handler Manager");
      v51 = (CExecSessionApps **)((char *)this + 1224);
      if ( !*((_QWORD *)this + 153) )
      {
        v52 = (CExecSessionApps *)operator new(0xC80u, (const struct std::nothrow_t *)std::nothrow);
        *(_QWORD *)&pclsid.Data1 = v52;
        if ( v52 )
          v53 = CExecSessionApps::CExecSessionApps(v52);
        else
          v53 = 0;
        SmartPtr<ITerminal>::operator=((char *)this + 1224, v53);
        if ( !*v51 )
        {
          v7 = -2147024882;
          _DbgPrintMessage(
            8,
            "FAILED to create CExecSessionApps failed: 0x%x in %s",
            2147942414LL,
            "CRemoteConnectionManager::Start");
          goto LABEL_191;
        }
        v54 = CExecSessionApps::Initialize(*v51);
        v7 = v54;
        if ( v54 < 0 )
        {
          _DbgPrintMessage(
            8,
            "ExecApps.Initialize failed: 0x%x in %s",
            (unsigned int)v54,
            "CRemoteConnectionManager::Start");
          goto LABEL_191;
        }
      }
      CRemoteConnectionManager::UpdateResetLastTimeoutOnAutoReconnect(this);
      DrainMode = CUtils::GetDrainMode(Data);
      v7 = DrainMode;
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
      v7 = AllowFastReconnect;
      if ( AllowFastReconnect < 0 )
      {
        _DbgPrintMessage(
          8,
          "CUtils::GetAllowFastReconnect failed: 0x%x in %s",
          (unsigned int)AllowFastReconnect,
          "CRemoteConnectionManager::Start");
        goto LABEL_191;
      }
      if ( (unsigned int)dword_180128170 > 5 )
      {
        v70 = *((_DWORD *)this + 637);
        *(_QWORD *)&pclsid.Data1 = "Enabled";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v57,
          (unsigned int)byte_1801070C3,
          v58,
          v59,
          (__int64)&pclsid,
          (__int64)&v70);
      }
      v60 = *((_BYTE *)this + 2536);
      *((_BYTE *)this + 2536) = *(_DWORD *)Data != 0;
      v61 = *((_DWORD *)this + 635);
      if ( (int)CSLQuery::GetUserSessionLimit((int *)this + 635) < 0 )
        *((_DWORD *)this + 635) = 0;
      v83 = 0u;
      if ( !*v8
        || v60 != *((_BYTE *)this + 2536)
        || v61 != (*(unsigned int (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 192LL))(this) )
      {
        LODWORD(v83) = *v8 == 0;
        if ( *((_BYTE *)this + 2536) == 1 )
        {
          DWORD1(v83) = 1;
        }
        else
        {
          v63 = 0;
          if ( v60 == 1 )
            v63 = 2;
          DWORD1(v83) = v63;
        }
        DWORD2(v83) = (*(__int64 (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 192LL))(this) != 0;
        HIDWORD(v83) = (*(__int64 (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 192LL))(this);
        v62 = (CProtocolExMgr *)*((_QWORD *)this + 10);
        if ( v62 )
          CProtocolExMgr::NotifyServiceStateChange(v62, (struct __SERVICESTATECHANGE *)&v83);
      }
      v64 = CRemoteConnectionManager::ChangeRCMReadyEventState(v62, 1);
      v7 = v64;
      if ( v64 < 0 )
      {
        _DbgPrintMessage(4, "this->ChangeRCMReadyEventState for SetEvent failed : 0x%08x", v64);
        v7 = 0;
      }
      CRemoteConnectionManager::StartStopDependentServices(v65, 1);
      RDSHTelemetryLogging::OnRegUpdate();
      StateTracker<enum CRemoteConnectionManager::TState>::operator=((char *)this + 1248, 2);
      goto LABEL_192;
    }
    v13 = "NULL timer manager, cannot start timers. failed: 0x%x in %s";
LABEL_190:
    v7 = -2147024809;
    _DbgPrintMessage(8, v13, 2147942487LL, "CRemoteConnectionManager::Start");
    goto LABEL_191;
  }
  while ( 1 )
  {
    v71 = 0;
    v26 = v73;
    if ( !(unsigned int)_o__wcsicmp(v73, L"Console") )
      goto LABEL_141;
    if ( (unsigned int)CHardcodedListenerConfig::ListenerTypeFromProtoName(v26) )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Hardcoded listeners %s are stopped and started in a different function", v26);
      goto LABEL_141;
    }
    v68[0] = 0;
    ListenerStart = RegQueryListenerStart(v26, v68);
    ListenerByName = CRemoteConnectionManager::CListenersList::GetListenerByName(
                       (CRemoteConnectionManager *)((char *)this + 280),
                       v26,
                       &v71);
    if ( ListenerStart )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Skipping Listener %ws Start, failed to query listener enablement status", v26);
      goto LABEL_141;
    }
    if ( !v68[0] )
    {
      if ( ListenerByName < 0 )
      {
        if ( (g_DebugTraceComponent & 0x10) != 0 )
          _DbgPrintMessage(2, "Skipping Listener %ws Start, Remote Desktop or listener is disabled", v26);
      }
      else
      {
        if ( (g_DebugTraceComponent & 0x10) != 0 )
          _DbgPrintMessage(2, "Stopping Listener %ws, Remote Desktop or listener is disabled", v26);
        v41 = v71;
        v42 = (*(__int64 (__fastcall **)(struct IListener *))(*(_QWORD *)v71 + 32LL))(v71);
        if ( v42 >= 0 )
        {
          v43 = CRemoteConnectionManager::CListenersList::RemoveListener(
                  (CRemoteConnectionManager *)((char *)this + 280),
                  v41);
          if ( v43 < 0 && (g_DebugTraceComponent & 0x10) != 0 )
            _DbgPrintMessage(2, "Failed to remove listener: %ws, 0x%x", v26, (unsigned int)v43);
        }
        else if ( (g_DebugTraceComponent & 0x10) != 0 )
        {
          _DbgPrintMessage(2, "Failed to stop listener: %ws, 0x%x", v26, (unsigned int)v42);
        }
      }
      goto LABEL_141;
    }
    if ( ListenerByName >= 0 )
      goto LABEL_117;
    v72 = 0;
    v84 = 0;
    v70 = 0;
    ProtocolExtension = CRemoteConnectionManager::GetProtocolExtension(v29, v26, &v70, &v84);
    if ( ProtocolExtension >= 0 )
      break;
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(
        2,
        "GetProtocolExtension for listener %ws failed, error 0x%08x",
        v26,
        (unsigned int)ProtocolExtension);
LABEL_96:
    v31 = CRegistry::GetNextSubKey((CRegistry *)v75, &v73, &v69);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v72);
LABEL_142:
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v71);
    if ( v31 )
      goto LABEL_143;
  }
  if ( v70 != 1 )
  {
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "Ignoring listener %ws, missing protocol GUID", v26);
    goto LABEL_96;
  }
  pclsid = 0;
  if ( !*((_DWORD *)this + 638) )
  {
    Buf1 = v84;
    if ( !(unsigned int)IsRDPProtocol(&Buf1) && !(unsigned int)DoesVMNeedLicensing() )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Listener %ws is not alowed", v26);
      goto LABEL_96;
    }
  }
  if ( (int)CUtils::GetProtocolTerminalClass(v26, &pclsid) >= 0 )
  {
    v33 = pclsid;
  }
  else
  {
    v33 = v84;
    pclsid = v84;
  }
  Buf1 = v33;
  CrimsonHelper::RaiseEvent<unsigned short const *,_GUID>(&CrimsonHelper::s_instance, v32, v26, &Buf1);
  if ( (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(2, "Creating listener %ws", v26);
  v34 = CProtocolExMgr::CreateListener(
          *((CProtocolExMgr **)this + 10),
          this,
          (struct IWRdsProtocolSettings *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          v26,
          &v84,
          &pclsid,
          &v72);
  if ( v34 < 0 )
  {
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "Protocol failed to create listener %ws, error 0x%08x", v26, (unsigned int)v34);
    goto LABEL_96;
  }
  if ( v72 )
  {
    v35 = CRemoteConnectionManager::CListenersList::AddListener((CRemoteConnectionManager *)((char *)this + 280), v72);
    v7 = v35;
    if ( v35 < 0 )
    {
      _DbgPrintMessage(8, "Adding Listeners to list failed: 0x%x in %s", v35, "CRemoteConnectionManager::Start");
      goto LABEL_148;
    }
    SmartPtr<ITerminal>::operator=(&v71, v72);
    if ( (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "Listener %ws created", v26);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v72);
LABEL_117:
    v36 = (*(__int64 (__fastcall **)(struct IListener *))(*(_QWORD *)v71 + 24LL))(v71);
    v39 = v36;
    if ( v36 >= 0 )
    {
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Listener %ws started", v26);
    }
    else
    {
      CHelper::LogErrorEvent(0xC000040B, v36);
      if ( (g_DebugTraceComponent & 0x10) != 0 )
        _DbgPrintMessage(2, "Failed to start listener: %ws, 0x%x", v26, v39);
    }
    v40 = CHelper::LogListenerStartErrorToReg(v26, v39, v37, v38);
    if ( v40 < 0 && (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "LogListenerStartErrorToReg failed", (unsigned int)v40);
LABEL_141:
    v31 = CRegistry::GetNextSubKey((CRegistry *)v75, &v73, &v69);
    goto LABEL_142;
  }
  v7 = -2147024882;
  if ( (g_DebugTraceComponent & 0x10) != 0 )
    _DbgPrintMessage(2, "Can't start listener %ws due to out of resources", v26);
LABEL_148:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v72);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v71);
LABEL_191:
  (*(void (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 48LL))(this);
LABEL_192:
  EtwEventActivityIdControl(2, &v87);
  CAutoLock::Unlock((CAutoLock *)v81);
  CGenericTrace::~CGenericTrace((CGenericTrace *)v88);
  CRegistry::~CRegistry((CRegistry *)v75);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004aeb0  push    rbp
0x18004aeb2  push    rbx
0x18004aeb3  push    rsi
0x18004aeb4  push    rdi
0x18004aeb5  push    r12
0x18004aeb7  push    r13
0x18004aeb9  push    r14
0x18004aebb  push    r15
0x18004aebd  lea     rbp, [rsp-0F8h]
0x18004aec5  sub     rsp, 1F8h
0x18004aecc  mov     rax, cs:__security_cookie
0x18004aed3  xor     rax, rsp
0x18004aed6  mov     [rbp+130h+var_48], rax
0x18004aedd  mov     esi, edx
0x18004aedf  mov     rdi, rcx
0x18004aee2  xor     r12d, r12d
0x18004aee5  mov     [rsp+230h+var_1DC], r12d
0x18004aeea  mov     [rsp+230h+var_1C0], r12
0x18004aeef  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x18004aef6  mov     [rbp+130h+var_1B0], rax
0x18004aefa  mov     [rbp+130h+var_1A8], r12
0x18004aefe  mov     [rbp+130h+var_1A0], r12d
0x18004af02  mov     [rbp+130h+var_198], r12
0x18004af06  or      eax, 0FFFFFFFFh
0x18004af09  mov     [rbp+130h+var_190], eax
0x18004af0c  mov     [rbp+130h+var_18C], eax
0x18004af0f  mov     [rsp+230h+var_1D8], r12d
0x18004af14  mov     dword ptr [rsp+230h+Data], r12d
0x18004af19  xorps   xmm0, xmm0
0x18004af1c  movups  [rbp+130h+var_150], xmm0
0x18004af20  mov     eax, cs:dword_180128170
0x18004af26  cmp     eax, 4
0x18004af29  jbe     loc_18004AFBA
0x18004af2f  mov     rdx, 470000000000h
0x18004af39  lea     rcx, dword_180128170
0x18004af40  call    _tlgKeywordOn
0x18004af45  test    al, al
0x18004af47  jz      short loc_18004AFBA
0x18004af49  lea     rax, aWwwwwwwwwwwwww; "wwwwwwwwwwwwwwwwT\x00e\x00r\x00m\x00S"...
0x18004af50  mov     [rsp+230h+var_1C8], rax
0x18004af55  lea     rax, aDesc; "desc"
0x18004af5c  mov     [rsp+230h+var_1D0], rax
0x18004af61  lea     rax, aTermsrv_1; "Termsrv"
0x18004af68  mov     qword ptr [rbp+130h+Buf1.Data1], rax
0x18004af6c  mov     qword ptr [rbp+130h+var_140.Data1], 1000000h
0x18004af74  lea     rax, aCheckpoint; "Checkpoint"
0x18004af7b  mov     qword ptr [rbp+130h+pclsid.Data1], rax
0x18004af7f  lea     rax, [rsp+230h+var_1C8]
0x18004af84  mov     [rsp+230h+var_1F0], rax
0x18004af89  lea     rax, [rsp+230h+var_1D0]
0x18004af8e  mov     [rsp+230h+var_1F8], rax
0x18004af93  lea     rax, [rbp+130h+Buf1]
0x18004af97  mov     [rsp+230h+var_200], rax
0x18004af9c  lea     rax, [rbp+130h+var_140]
0x18004afa0  mov     [rsp+230h+var_208], rax
0x18004afa5  lea     rax, [rbp+130h+pclsid]
0x18004afa9  mov     [rsp+230h+var_210], rax; unsigned __int16 *
0x18004afae  lea     rdx, byte_1801070FB
0x18004afb5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &)
0x18004afba  lea     rcx, [rdi+108h]; this
0x18004afc1  call    ?Refresh@CWPPConfig@@QEAAJXZ; CWPPConfig::Refresh(void)
0x18004afc6  lea     r14, aCremoteconnect; "CRemoteConnectionManager::Start"
0x18004afcd  mov     r9, r14; char *
0x18004afd0  lea     r8, aCremoteconnect_18; "CRemoteConnectionManager Starts..."
0x18004afd7  mov     edx, 10h; unsigned int
0x18004afdc  lea     rcx, [rbp+130h+var_80]; this
0x18004afe3  call    ??0CGenericTrace@@QEAA@KPEBD0@Z; CGenericTrace::CGenericTrace(ulong,char const *,char const *)
0x18004afe8  nop
0x18004afe9  lea     rdx, [rdi+3E8h]; struct CResource *
0x18004aff0  lea     rcx, [rbp+130h+var_170]; this
0x18004aff4  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x18004aff9  nop
0x18004affa  xorps   xmm0, xmm0
0x18004affd  movups  xmmword ptr [rbp+130h+pguid.Data1], xmm0
0x18004b004  mov     edx, 0F4620000h; unsigned int
0x18004b009  lea     rcx, [rbp+130h+pguid]; pguid
0x18004b010  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x18004b015  mov     ebx, eax
0x18004b017  movaps  xmm0, xmmword ptr [rbp+130h+pguid.Data1]
0x18004b01e  movdqa  [rbp+130h+var_90], xmm0
0x18004b026  lea     rdx, [rbp+130h+var_90]
0x18004b02d  mov     ecx, 4
0x18004b032  call    cs:__imp_EtwEventActivityIdControl
0x18004b038  nop
0x18004b039  test    ebx, ebx
0x18004b03b  jns     short loc_18004B04F
0x18004b03d  mov     r9, r14
0x18004b040  mov     r8d, ebx
0x18004b043  lea     rdx, aGenerateconstr; "GenerateConstrainedGuid failed: 0x%x in"...
0x18004b04a  jmp     loc_18004BC62
0x18004b04f  cmp     [rdi+9F0h], r12b
0x18004b056  jz      short loc_18004B06F
0x18004b058  mov     ebx, 80070426h
0x18004b05d  mov     r9, r14
0x18004b060  mov     r8d, ebx
0x18004b063  lea     rdx, aRcmStartCallOn; "RCM Start(): call on termsrv service st"...
0x18004b06a  jmp     loc_18004BC62
0x18004b06f  lea     r15, [rdi+4E0h]
0x18004b076  mov     r13d, 1
0x18004b07c  cmp     [r15], r13d
0x18004b07f  jnz     short loc_18004B098
0x18004b081  mov     ebx, 8000FFFFh
0x18004b086  mov     r9, r14
0x18004b089  mov     r8d, ebx
0x18004b08c  lea     rdx, aRcmStartInvali; "RCM Start(): Invalid starting state, St"...
0x18004b093  jmp     loc_18004BC62
0x18004b098  cmp     esi, r13d
0x18004b09b  jnz     loc_18004B258
0x18004b0a1  mov     rcx, rdi; this
0x18004b0a4  call    ?ReadMachineGroupPolicy@CRemoteConnectionManager@@AEAAJXZ; CRemoteConnectionManager::ReadMachineGroupPolicy(void)
0x18004b0a9  mov     ebx, eax
0x18004b0ab  test    eax, eax
0x18004b0ad  jns     short loc_18004B0C1
0x18004b0af  mov     r9, r14
0x18004b0b2  mov     r8d, eax
0x18004b0b5  lea     rdx, aThisReadmachin; "this->ReadMachineGroupPolicy failed: 0x"...
0x18004b0bc  jmp     loc_18004BC62
0x18004b0c1  mov     rsi, [rdi+50h]
0x18004b0c5  test    rsi, rsi
0x18004b0c8  jz      loc_18004BC7C
0x18004b0ce  xor     edx, edx; Val
0x18004b0d0  lea     r8d, [rdx+7Ch]; Size
0x18004b0d4  lea     rcx, [rbp+130h+var_130.WRdsSetting]; void *
0x18004b0d8  call    memset_0
0x18004b0dd  mov     [rbp+130h+var_130.WRdsSettingType], r13d
0x18004b0e1  mov     [rbp+130h+var_130.WRdsSettingLevel], r13d
0x18004b0e5  mov     rcx, [rdi+58h]
0x18004b0e9  test    rcx, rcx
0x18004b0ec  jz      loc_18004B249
0x18004b0f2  lea     rdx, [rcx+4]
0x18004b0f6  test    [rcx], r13b
0x18004b0f9  jz      short loc_18004B10A
0x18004b0fb  mov     dword ptr [rbp+130h+var_130.WRdsSetting], r13d
0x18004b0ff  mov     eax, [rdx]
0x18004b101  shr     eax, 0Dh
0x18004b104  and     eax, r13d
0x18004b107  mov     dword ptr [rbp+130h+var_130.WRdsSetting+4], eax
0x18004b10a  test    byte ptr [rcx], 8
0x18004b10d  jz      short loc_18004B11D
0x18004b10f  mov     dword ptr [rbp+130h+var_130.WRdsSetting+8], r13d
0x18004b113  movzx   eax, word ptr [rdx+2]
0x18004b117  and     eax, r13d
0x18004b11a  mov     dword ptr [rbp+130h+var_130.WRdsSetting+0Ch], eax
0x18004b11d  test    byte ptr [rcx], 4
0x18004b120  jz      short loc_18004B131
0x18004b122  mov     dword ptr [rbp+130h+var_130.WRdsSetting+10h], r13d
0x18004b126  mov     eax, [rdx]
0x18004b128  shr     eax, 0Fh
0x18004b12b  and     eax, r13d
0x18004b12e  mov     dword ptr [rbp+130h+var_130.WRdsSetting+14h], eax
0x18004b131  test    dword ptr [rcx], 2000000h
0x18004b137  jz      short loc_18004B148
0x18004b139  mov     dword ptr [rbp+130h+var_130.WRdsSetting+18h], r13d
0x18004b13d  mov     eax, [rdx]
0x18004b13f  shr     eax, 1Ah
0x18004b142  and     eax, r13d
0x18004b145  mov     dword ptr [rbp+130h+var_130.WRdsSetting+1Ch], eax
0x18004b148  test    byte ptr [rcx], 10h
0x18004b14b  jz      short loc_18004B15C
0x18004b14d  mov     dword ptr [rbp+130h+var_130.WRdsSetting+20h], r13d
0x18004b151  mov     eax, [rdx]
0x18004b153  shr     eax, 11h
0x18004b156  and     eax, r13d
0x18004b159  mov     dword ptr [rbp+130h+var_130.WRdsSetting+24h], eax
0x18004b15c  test    byte ptr [rcx+18h], 8
0x18004b160  jz      short loc_18004B172
0x18004b162  mov     dword ptr [rbp+130h+var_130.WRdsSetting+28h], r13d
0x18004b166  mov     eax, [rcx+18h]
0x18004b169  shr     eax, 4
0x18004b16c  and     eax, r13d
0x18004b16f  mov     dword ptr [rbp+130h+var_130.WRdsSetting+2Ch], eax
0x18004b172  test    byte ptr [rcx], 80h
0x18004b175  jz      short loc_18004B182
0x18004b177  mov     dword ptr [rbp+130h+var_130.WRdsSetting+30h], r13d
0x18004b17b  movzx   eax, byte ptr [rcx+24h]
0x18004b17f  mov     dword ptr [rbp+130h+var_130.WRdsSetting+34h], eax
0x18004b182  test    dword ptr [rcx], 10000h
0x18004b188  jz      short loc_18004B199
0x18004b18a  mov     dword ptr [rbp+130h+var_130.WRdsSetting+38h], r13d
0x18004b18e  mov     eax, [rdx]
0x18004b190  shr     eax, 13h
0x18004b193  and     eax, 7
0x18004b196  mov     dword ptr [rbp+130h+var_130.WRdsSetting+3Ch], eax
0x18004b199  test    dword ptr [rcx], 200h
0x18004b19f  jz      short loc_18004B1B1
0x18004b1a1  mov     dword ptr [rbp+130h+var_130.WRdsSetting+40h], r13d
0x18004b1a5  mov     eax, [rcx+8]
0x18004b1a8  shr     eax, 4
0x18004b1ab  and     eax, r13d
0x18004b1ae  mov     dword ptr [rbp+130h+var_130.WRdsSetting+44h], eax
0x18004b1b1  test    byte ptr [rcx+8], 40h
0x18004b1b5  jz      short loc_18004B1C7
0x18004b1b7  mov     dword ptr [rbp+130h+var_130.WRdsSetting+48h], r13d
0x18004b1bb  mov     eax, [rcx+8]
0x18004b1be  shr     eax, 7
0x18004b1c1  and     eax, r13d
0x18004b1c4  mov     dword ptr [rbp+130h+var_130.WRdsSetting+4Ch], eax
0x18004b1c7  test    dword ptr [rcx], 10000000h
0x18004b1cd  jz      short loc_18004B1DE
0x18004b1cf  mov     dword ptr [rbp+130h+var_130.WRdsSetting+50h], r13d
0x18004b1d3  mov     eax, [rdx]
0x18004b1d5  shr     eax, 1Ch
0x18004b1d8  and     eax, r13d
0x18004b1db  mov     dword ptr [rbp+130h+var_130.WRdsSetting+54h], eax
0x18004b1de  test    [rdx], r13b
0x18004b1e1  jz      short loc_18004B1F0
0x18004b1e3  mov     dword ptr [rbp+130h+var_130.WRdsSetting+58h], r13d
0x18004b1e7  mov     eax, [rcx+0A54h]
0x18004b1ed  mov     dword ptr [rbp+130h+var_130.WRdsSetting+5Ch], eax
0x18004b1f0  cmp     [rcx], r12d
0x18004b1f3  jge     short loc_18004B202
0x18004b1f5  mov     dword ptr [rbp+130h+var_130.WRdsSetting+60h], r13d
0x18004b1f9  mov     eax, [rcx+0A50h]
0x18004b1ff  mov     dword ptr [rbp+130h+var_130.WRdsSetting+64h], eax
0x18004b202  test    dword ptr [rcx], 40000000h
0x18004b208  jz      short loc_18004B217
0x18004b20a  mov     dword ptr [rbp+130h+var_130.WRdsSetting+68h], r13d
0x18004b20e  mov     eax, [rcx+0A4Ch]
0x18004b214  mov     dword ptr [rbp+130h+var_130.WRdsSetting+6Ch], eax
0x18004b217  test    byte ptr [rdx], 10h
0x18004b21a  jz      short loc_18004B235
0x18004b21c  mov     dword ptr [rbp+130h+var_130.WRdsSetting+70h], r13d
0x18004b220  mov     al, [rcx+8]
0x18004b223  and     al, r13b
0x18004b226  mov     byte ptr [rbp+130h+var_130.WRdsSetting+74h], al
0x18004b229  mov     eax, [rcx+0A44h]
0x18004b22f  mov     dword ptr [rbp+130h+var_130.WRdsSetting+78h], eax
0x18004b235  mov     ebx, r12d
0x18004b238  lea     rdx, [rbp+130h+var_130]; struct _WRDS_SETTINGS *
0x18004b23c  mov     rcx, rsi; this
0x18004b23f  call    ?NotifySettingsChange@CProtocolExMgr@@QEAAJPEAU_WRDS_SETTINGS@@@Z; CProtocolExMgr::NotifySettingsChange(_WRDS_SETTINGS *)
0x18004b244  jmp     loc_18004BC7C
0x18004b249  mov     r9, r14
0x18004b24c  lea     rdx, aChelperConvert; "CHelper::ConvertPolicySettingsToWRdsSet"...
0x18004b253  jmp     loc_18004BC59
0x18004b258  lea     r9, [rdi+4B8h]; OldValue
0x18004b25f  xor     r8d, r8d; ForThread
0x18004b262  mov     dl, r13b; NewValue
0x18004b265  lea     ecx, [r8+15h]; Privilege
0x18004b269  call    cs:__imp_RtlAdjustPrivilege
0x18004b26f  mov     ebx, eax
0x18004b271  or      ebx, 10000000h
0x18004b277  jge     short loc_18004B28B
0x18004b279  mov     r9, r14
0x18004b27c  mov     r8d, ebx
0x18004b27f  lea     rdx, aRtladjustprivi; "RtlAdjustPrivilege on SE_AUDIT_PRIVILEG"...
0x18004b286  jmp     loc_18004BC62
0x18004b28b  lea     rcx, [rsp+230h+var_1D8]; int *
0x18004b290  call    ?AreRemoteConnectionsAllowed@CSLQuery@@SAJPEAH@Z; CSLQuery::AreRemoteConnectionsAllowed(int *)
0x18004b295  mov     ebx, eax
0x18004b297  test    eax, eax
0x18004b299  jns     short loc_18004B2AD
0x18004b29b  mov     r9, r14
0x18004b29e  mov     r8d, eax
0x18004b2a1  lea     rdx, aCslqueryArerem_0; "CSLQuery::AreRemoteConnectionsAllowed f"...
0x18004b2a8  jmp     loc_18004BC62
0x18004b2ad  mov     r14d, [rsp+230h+var_1D8]
0x18004b2b2  test    r14d, r14d
0x18004b2b5  jnz     short loc_18004B2D0
0x18004b2b7  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 10h; ulong g_DebugTraceComponent
0x18004b2be  jz      short loc_18004B2D0
0x18004b2c0  lea     rdx, aRemoteConnecti_0; "Remote Connection is not allow on this "...
0x18004b2c7  lea     ecx, [r14+2]; int
0x18004b2cb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004b2d0  call    ?IsProcessRunningInContainer@CContainerHelper@@SAHXZ; CContainerHelper::IsProcessRunningInContainer(void)
0x18004b2d5  test    eax, eax
0x18004b2d7  jz      short loc_18004B2F6
0x18004b2d9  mov     r14d, r12d
0x18004b2dc  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 10h; ulong g_DebugTraceComponent
0x18004b2e3  jz      short loc_18004B2F6
0x18004b2e5  lea     rdx, aTsInContainerA; "TS in container and so Remote Connectio"...
0x18004b2ec  mov     ecx, 2; int
0x18004b2f1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004b2f6  mov     rcx, rdi; this
0x18004b2f9  call    ?UpdateWddmModeSettings@CRemoteConnectionManager@@AEAAJXZ; CRemoteConnectionManager::UpdateWddmModeSettings(void)
0x18004b2fe  mov     ebx, eax
0x18004b300  test    eax, eax
0x18004b302  jns     short loc_18004B31A
0x18004b304  lea     r9, aCremoteconnect; "CRemoteConnectionManager::Start"
0x18004b30b  mov     r8d, eax
0x18004b30e  lea     rdx, aUpdatewddmmode; "UpdateWddmModeSettings failed: 0x%x in "...
0x18004b315  jmp     loc_18004BC62
0x18004b31a  mov     rcx, [rdi+1F8h]
0x18004b321  mov     rax, [rcx]
0x18004b324  mov     rax, [rax+20h]
0x18004b328  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b32d  mov     ebx, eax
0x18004b32f  test    eax, eax
0x18004b331  jns     short loc_18004B349
0x18004b333  lea     r9, aCremoteconnect; "CRemoteConnectionManager::Start"
0x18004b33a  mov     r8d, eax
0x18004b33d  lea     rdx, aEnforcementCor; "Enforcement core start failed: 0x%x in "...
0x18004b344  jmp     loc_18004BC62
0x18004b349  mov     rcx, [rdi+218h]
0x18004b350  mov     rax, [rcx]
0x18004b353  mov     rax, [rax+18h]
0x18004b357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b35c  mov     ebx, eax
0x18004b35e  test    eax, eax
0x18004b360  jns     short loc_18004B378
  ... truncated ...
```
