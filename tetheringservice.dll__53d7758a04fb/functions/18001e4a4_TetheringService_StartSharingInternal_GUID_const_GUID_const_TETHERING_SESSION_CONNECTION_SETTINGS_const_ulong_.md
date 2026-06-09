# TetheringService::StartSharingInternal(_GUID const *,_GUID const *,_TETHERING_SESSION_CONNECTION_SETTINGS * const,ulong,ushort const *)

- ea: `0x18001e4a4`
- end: `0x18001f668`
- name: `?StartSharingInternal@TetheringService@@AEAAJPEBU_GUID@@0QEAU_TETHERING_SESSION_CONNECTION_SETTINGS@@KPEBG@Z`
- size: `4548`
- prototype: `__int64 __usercall@<rax>(TetheringService *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct _GUID *@<r8>, struct _TETHERING_SESSION_CONNECTION_SETTINGS *const@<r9>, unsigned int, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `42`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014c8c`
- `0x180019b4c`
- `0x18001c75c`
- `0x18001dc08`
- `0x18001f670`

## callees

- `0x180001008`
- `0x1800010a8`
- `0x180002590`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000d584`
- `0x18000d9dc`
- `0x18000ee14`
- `0x18000ee3c`
- `0x18000f348`
- `0x18000f76c`
- `0x18000f828`
- `0x18000f9dc`
- `0x180010c6c`
- `0x180012738`
- `0x180013bbc`
- `0x180013be0`
- `0x180013ca0`
- `0x180018a60`
- `0x180019ec0`
- `0x18001a21c`
- `0x18001b714`
- `0x18001c184`
- `0x18001d344`
- `0x18001e4a4`
- `0x18001f740`
- `0x18002072c`
- `0x180021580`
- `0x180021980`
- `0x180025c88`
- `0x180026558`
- `0x180026774`
- `0x180027130`
- `0x1800272c0`
- `0x180027394`
- `0x180029c10`
- `0x18002b1f0`
- `0x18002bad8`
- `0x1800315ec`
- `0x1800315f8`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001effe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f00d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f258`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001effe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f00d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001f258`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e9ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001eaa1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f443`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e9ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001eaa1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001f443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e942`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ea6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f46c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e942`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ea6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f46c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e8a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e92e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ea4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e8a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e92e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ea4f`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18001f2c9`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x18001f2c9`
- `IPHLPAPI!FreeMibTable` at `0x18001e6b6`
- `IPHLPAPI!FreeMibTable` at `0x18001f613`
- `IPHLPAPI!FreeMibTable` at `0x18001e6b6`
- `IPHLPAPI!FreeMibTable` at `0x18001f613`
- `IPHLPAPI!GetIfTable2` at `0x18001e67c`
- `IPHLPAPI!GetIfTable2` at `0x18001e67c`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18001f29d`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x18001f29d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001efe4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001f028`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001f04f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001efe4`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001f028`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x18001f04f`
- `WMICLNT!WmiNotificationRegistrationW` at `0x18001ee2b`
- `WMICLNT!WmiNotificationRegistrationW` at `0x18001ee2b`

## string_xrefs

- `0x18001f2f9`: `onecoreuap\net\tethering\service\tetheringservice.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TetheringService::StartSharingInternal(
        TetheringService *this,
        const struct _GUID *a2,
        struct _GUID *a3,
        struct _TETHERING_SESSION_CONNECTION_SETTINGS *const a4,
        unsigned int a5,
        const unsigned __int16 *a6)
{
  struct _GUID *v6; // rbx
  const struct _GUID *v7; // r13
  int v9; // r12d
  TetheringServiceTelemetry *v10; // rcx
  __int64 v11; // r9
  RTL_SRWLOCK *v12; // rsi
  int Session; // ebx
  NTSTATUS IfTable2; // eax
  signed int v15; // r14d
  void *v16; // rcx
  TetheringServiceTelemetry *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  int InterfaceGuidInMibTable; // eax
  __int64 v21; // r13
  struct _MIB_IF_TABLE2 *v22; // rbx
  int v23; // r14d
  __int64 v24; // r12
  __int64 v25; // rdi
  int SharedInterfaceIndices; // eax
  __int64 v27; // rdx
  __int64 v28; // r9
  int v29; // edx
  int v30; // r8d
  TetheringServiceTelemetry *v31; // rcx
  BOOL v32; // ebx
  int v33; // r14d
  TetheringServiceTelemetry *v34; // rcx
  __int64 v35; // r8
  __int64 v36; // r9
  TetheringServiceTelemetry *v37; // rcx
  TetheringService *v38; // rcx
  char v39; // di
  int updated; // eax
  __int64 v41; // rdx
  int v42; // eax
  int started; // eax
  __int64 v44; // rdx
  int v45; // eax
  __int64 v46; // r13
  ULONG v47; // r14d
  _DWORD *SettingValueWithGuidInternal; // rax
  void *v49; // rbx
  _DWORD *SettingValueGlobalInternal; // rax
  void *v51; // rdi
  unsigned int Value; // ebx
  _OWORD *v53; // rcx
  unsigned int v54; // edi
  unsigned int v55; // r12d
  _DWORD *v56; // rax
  __int128 v57; // xmm6
  int v58; // r13d
  unsigned int v59; // eax
  unsigned int v60; // r8d
  __int64 v61; // rdx
  int v62; // eax
  unsigned int v63; // ecx
  int v64; // ebx
  _DWORD *v65; // rcx
  TetheringServiceTelemetry *v66; // rcx
  int v68; // [rsp+28h] [rbp-E0h]
  __int64 v69; // [rsp+58h] [rbp-B0h] BYREF
  const struct _GUID *v70; // [rsp+60h] [rbp-A8h]
  bool v71[8]; // [rsp+68h] [rbp-A0h]
  NET_LUID InterfaceLuid; // [rsp+70h] [rbp-98h] BYREF
  unsigned int v73; // [rsp+78h] [rbp-90h] BYREF
  int v74; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v75; // [rsp+80h] [rbp-88h] BYREF
  unsigned int v76; // [rsp+84h] [rbp-84h] BYREF
  PVOID Memory; // [rsp+88h] [rbp-80h] BYREF
  struct _GUID *v78; // [rsp+90h] [rbp-78h]
  TetheringSessionTelemetry *v79; // [rsp+98h] [rbp-70h] BYREF
  struct _GUID *v80; // [rsp+A0h] [rbp-68h] BYREF
  const struct _GUID *v81; // [rsp+A8h] [rbp-60h] BYREF
  const WCHAR *v82; // [rsp+B0h] [rbp-58h] BYREF
  int v83; // [rsp+B8h] [rbp-50h] BYREF
  signed int v84; // [rsp+BCh] [rbp-4Ch] BYREF
  _BYTE v85[216]; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v86[12]; // [rsp+198h] [rbp+90h] BYREF
  GUID Buf1; // [rsp+1A4h] [rbp+9Ch] BYREF
  int v88; // [rsp+600h] [rbp+4F8h]
  int v89; // [rsp+60Ch] [rbp+504h]
  _BYTE Table[20]; // [rsp+6E8h] [rbp+5E0h] BYREF
  int v91; // [rsp+6FCh] [rbp+5F4h]
  struct _GUID v92; // [rsp+708h] [rbp+600h] BYREF
  GUID InterfaceGuid; // [rsp+718h] [rbp+610h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v94[2]; // [rsp+728h] [rbp+620h] BYREF
  const WCHAR *v95; // [rsp+748h] [rbp+640h]
  __int64 v96; // [rsp+750h] [rbp+648h]
  const struct _GUID *v97; // [rsp+758h] [rbp+650h]
  __int64 v98; // [rsp+760h] [rbp+658h]
  struct _GUID *v99; // [rsp+768h] [rbp+660h]
  __int64 v100; // [rsp+770h] [rbp+668h]
  int *v101; // [rsp+778h] [rbp+670h]
  __int64 v102; // [rsp+780h] [rbp+678h]
  __int64 *v103; // [rsp+788h] [rbp+680h]
  __int64 v104; // [rsp+790h] [rbp+688h]
  unsigned int *v105; // [rsp+798h] [rbp+690h]
  __int64 v106; // [rsp+7A0h] [rbp+698h]
  NET_LUID *p_InterfaceLuid; // [rsp+7A8h] [rbp+6A0h]
  __int64 v108; // [rsp+7B0h] [rbp+6A8h]
  wil::details::in1diag3 *retaddr; // [rsp+820h] [rbp+718h]

  *(_QWORD *)&InterfaceGuid.Data1 = a4;
  v6 = a3;
  v78 = a3;
  v7 = a2;
  v70 = a2;
  *(_QWORD *)&v92.Data1 = a6;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF__guid__guid_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)&WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (_DWORD)a2,
      (__int64)a3);
  }
  v76 = 0;
  v75 = 0;
  v74 = 0;
  v9 = 0;
  LODWORD(v69) = 0;
  memset_0(v94, 0, 0x50u);
  v12 = 0;
  v79 = 0;
  v71[0] = 0;
  if ( *(_QWORD *)&g_pTetheringSessionId.Data1 )
  {
    Session = TetheringServiceTelemetry::GetSession(v10, *(struct _GUID **)&g_pTetheringSessionId.Data1, &v79);
    v73 = Session;
    v12 = (RTL_SRWLOCK *)v79;
    if ( Session >= 0 )
    {
      if ( v79 )
      {
        if ( !TetheringSessionTelemetry::Initialized((RTL_SRWLOCK *)v79) )
          Session = -2147467259;
        v73 = Session;
      }
      else
      {
        v73 = -2147467261;
      }
    }
    v6 = v78;
  }
  else
  {
    v73 = -2147418113;
  }
  if ( g_lTraceLoggingRegistered >= 0
    && (unsigned int)dword_180041008 > 5
    && (qword_180041018 & 0x400000000000LL) != 0
    && (qword_180041020 & 0x400000000000LL) == qword_180041020 )
  {
    LODWORD(InterfaceLuid.Value) = a5;
    v80 = v6;
    v81 = v7;
    v82 = &sourceString;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      qword_180041020,
      (__int64)&word_180039976,
      (__int64)&sourceString,
      v11,
      &v82,
      (__int64 *)&v81,
      (__int64 *)&v80,
      (__int64)&InterfaceLuid);
  }
  Memory = 0;
  *(_QWORD *)Table = &Memory;
  *(_QWORD *)&Table[8] = 0;
  Table[16] = 1;
  IfTable2 = GetIfTable2((PMIB_IF_TABLE2 *)&Table[8]);
  v15 = IfTable2;
  if ( IfTable2 > 0 )
    v15 = (unsigned __int16)IfTable2 | 0x80070000;
  if ( Table[16] )
  {
    v16 = **(void ***)Table;
    **(_QWORD **)Table = *(_QWORD *)&Table[8];
    if ( v16 )
      FreeMibTable(v16);
  }
  if ( v15 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v18 = 58;
      v19 = (unsigned int)v15;
LABEL_27:
      WPP_SF_d(*((_QWORD *)v17 + 2), v18, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v19);
      v17 = WPP_GLOBAL_Control;
      goto LABEL_201;
    }
    goto LABEL_201;
  }
  LODWORD(InterfaceLuid.Value) = 0;
  InterfaceGuidInMibTable = InterfaceMgr::FindInterfaceGuidInMibTable(
                              (struct _MIB_IF_TABLE2 *)Memory,
                              v7,
                              (unsigned int *)&InterfaceLuid);
  v15 = InterfaceGuidInMibTable;
  if ( InterfaceGuidInMibTable >= 0 )
  {
    v21 = 1352LL * LODWORD(InterfaceLuid.Value);
    v22 = (struct _MIB_IF_TABLE2 *)Memory;
    v23 = *(_DWORD *)((char *)Memory + v21 + 1148);
    v74 = v23;
    memset_0(v86, 0, 0x548u);
    v24 = *(_QWORD *)&GUID_NULL.Data1;
    if ( *(_QWORD *)&v78->Data1 == *(_QWORD *)&GUID_NULL.Data1
      && (v25 = *(_QWORD *)GUID_NULL.Data4, *(_QWORD *)v78->Data4 == *(_QWORD *)GUID_NULL.Data4) )
    {
      LODWORD(v69) = 10;
      v89 = 10;
      Buf1 = GUID_NULL;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
    }
    else
    {
      LODWORD(InterfaceLuid.Value) = 0;
      SharedInterfaceIndices = InterfaceMgr::FindInterfaceGuidInMibTable(v22, v78, (unsigned int *)&InterfaceLuid);
      v15 = SharedInterfaceIndices;
      if ( SharedInterfaceIndices < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_199;
        }
        v27 = 61;
        goto LABEL_41;
      }
      memcpy_0(v86, (char *)Memory + 1352 * LODWORD(InterfaceLuid.Value) + 8, 0x548u);
      LODWORD(v69) = v89;
      v25 = *(_QWORD *)Buf1.Data4;
      v24 = *(_QWORD *)&Buf1.Data1;
      v23 = v74;
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
    if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_L_guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, v30, *((_DWORD *)this + 56), (__int64)this + 1288);
    }
    if ( *((_DWORD *)this + 56) == 2 )
    {
      v15 = 0;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_199;
      }
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, 2);
LABEL_198:
      v17 = WPP_GLOBAL_Control;
LABEL_199:
      v9 = v69;
      goto LABEL_200;
    }
    if ( v23 == 8 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
      v15 = TetheringService::InitializeCellularWnfSubscriptions(this);
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1488));
      if ( v15 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_199;
        }
        v27 = 64;
        goto LABEL_56;
      }
      v23 = v74;
    }
    *((_DWORD *)this + 56) = 4;
    if ( (a5 & 1) != 0 )
    {
      memset_0(&v84, 0, 0xD0u);
      v83 = 8;
      TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v83);
    }
    v32 = IsMobile();
    if ( !v73 )
    {
      if ( !v12 )
        goto LABEL_231;
      TetheringServiceTelemetry::AcquireSessionData(v31, v12, (struct TetheringServiceTelemetry::SESSION_DATA *)v94);
      *(_DWORD *)(v100 + 4) = v32;
      ReleaseSRWLockExclusive(v12 + 2);
    }
    if ( v32 || v23 != 8 )
    {
      v71[0] = 0;
    }
    else
    {
      v71[0] = 1;
      if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
      }
      CSebHelper::PublishWnfEvent(v70, 11);
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1752));
    v33 = CPowerHandler::PreventSleepInternal((const struct _WNF_STATE_NAME *)this + 219, 1u);
    if ( v33 >= 0 )
      *((_BYTE *)this + 1792) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1752));
    if ( !v73 )
    {
      if ( !v12 )
        goto LABEL_231;
      TetheringServiceTelemetry::AcquireSessionData(v34, v12, (struct TetheringServiceTelemetry::SESSION_DATA *)v94);
      *(_DWORD *)(v100 + 48) = v33;
      ReleaseSRWLockExclusive(v12 + 2);
    }
    if ( v33 < 0 )
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
        goto LABEL_83;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_80:
        if ( v37 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)v37 + 2), 111, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids);
LABEL_83:
        *((_QWORD *)this + 54) = v24;
        *((_QWORD *)this + 55) = v25;
        v9 = v69;
        *((_DWORD *)this + 119) = v69;
        *((_DWORD *)this + 112) = v88;
        v38 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, &WPP_c92c1a9e691a3125ab7df275584a9ff2_Traceguids, 0);
        }
        v39 = 0;
        v71[1] = 0;
        if ( ((v9 - 1) & 0xFFFFFFF7) == 0 )
        {
          if ( (a5 & 2) == 0 )
          {
            updated = TetheringService::SetWiFiPowerState(this, 1u, v35, v36);
            v15 = updated;
            if ( updated < 0 )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_200;
              }
              v41 = 68;
              goto LABEL_92;
            }
          }
          if ( (unsigned int)TetheringService::IsBluetoothAutoConnectionEnabled(v38) )
            BtPanHandler::Start((TetheringService *)((char *)this + 1184), 0);
          goto LABEL_95;
        }
        if ( v9 == 10 )
        {
          updated = BtPanHandler::Start((TetheringService *)((char *)this + 1184), 1);
          v15 = updated;
          if ( updated < 0 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            {
              goto LABEL_200;
            }
            v41 = 69;
            goto LABEL_92;
          }
          v39 = 1;
          v71[1] = 1;
          if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
          {
            updated = InterfaceMgr::UpdatePrivateBluetoothInterface((TetheringService *)((char *)this + 352));
            v15 = updated;
            if ( updated < 0 )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_200;
              }
              v41 = 70;
LABEL_92:
              WPP_SF_d(
                *((_QWORD *)v17 + 2),
                v41,
                &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
                (unsigned int)updated);
              v17 = WPP_GLOBAL_Control;
LABEL_200:
              v7 = v70;
              goto LABEL_201;
            }
          }
        }
LABEL_95:
        SharedInterfaceIndices = EntitlementMgr::SetPublicInterface(
                                   (TetheringService *)((char *)this + 568),
                                   (struct _MIB_IF_ROW2 *)((char *)Memory + v21 + 8));
        v15 = SharedInterfaceIndices;
        if ( SharedInterfaceIndices < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 71;
          goto LABEL_41;
        }
        if ( !*((_BYTE *)this + 662) )
        {
          v15 = -2147024875;
LABEL_111:
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 73;
          goto LABEL_56;
        }
        v42 = EntitlementMgr::CheckEntitlement(
                (TetheringService *)((char *)this + 568),
                *(const unsigned __int16 **)&v92.Data1);
        v15 = v42;
        if ( v42 < 0 )
        {
          v28 = 2198994956LL;
          if ( v42 == -2095972340 )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
            {
              goto LABEL_199;
            }
            v27 = 72;
            goto LABEL_42;
          }
          goto LABEL_111;
        }
        SharedInterfaceIndices = InterfaceMgr::SetPublicInterface(
                                   (TetheringService *)((char *)this + 352),
                                   (struct _MIB_IF_ROW2 *)((char *)Memory + v21 + 8));
        v15 = SharedInterfaceIndices;
        if ( SharedInterfaceIndices < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 74;
          goto LABEL_41;
        }
        *((_BYTE *)this + 1744) = 0;
        started = CNsiInterfaceMonitor::StartMonitor((TetheringService *)((char *)this + 1712));
        v15 = started;
        if ( started > 0 )
          v15 = (unsigned __int16)started | 0x80070000;
        if ( v15 < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 75;
          goto LABEL_56;
        }
        v68 = 4;
        LOBYTE(v44) = 1;
        v45 = WmiNotificationRegistrationW(
                &GUID_NDIS_NOTIFY_ADAPTER_REMOVAL,
                v44,
                TetheringService::NdisWmiEventNotificationHandler,
                this);
        v15 = v45;
        if ( v45 > 0 )
          v15 = (unsigned __int16)v45 | 0x80070000;
        if ( v15 < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 76;
LABEL_56:
          v28 = (unsigned int)v15;
          goto LABEL_42;
        }
        v46 = *(_QWORD *)&InterfaceGuid.Data1;
        SharedInterfaceIndices = InterfaceMgr::EnableSharedInterfaces(
                                   (TetheringService *)((char *)this + 352),
                                   *(struct _TETHERING_SESSION_CONNECTION_SETTINGS *const *)&InterfaceGuid.Data1);
        v15 = SharedInterfaceIndices;
        if ( SharedInterfaceIndices < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 77;
          goto LABEL_41;
        }
        SharedInterfaceIndices = TetheringService::GetSharedInterfaceIndices(this, &v76, &v75);
        v15 = SharedInterfaceIndices;
        if ( SharedInterfaceIndices < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 78;
          goto LABEL_41;
        }
        SharedInterfaceIndices = SharedAccessSvcMgr::Start((TetheringService *)((char *)this + 312), v76, v75, v39);
        v15 = SharedInterfaceIndices;
        if ( SharedInterfaceIndices < 0 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_199;
          }
          v27 = 79;
          goto LABEL_41;
        }
        if ( (((_DWORD)v69 - 1) & 0xFFFFFFF6) == 0 && (_DWORD)v69 != 2 )
        {
          v47 = 5;
          InterfaceLuid.Value = 0;
          if ( v74 == 8 )
            SettingValueWithGuidInternal = (_DWORD *)TetheringSettingsGetSettingValueWithGuidInternal(1, v70);
          else
            SettingValueWithGuidInternal = (_DWORD *)TetheringSettingsGetSettingValueGlobalInternal(1);
          InterfaceLuid.Value = (ULONG64)SettingValueWithGuidInternal;
          v49 = SettingValueWithGuidInternal;
          if ( SettingValueWithGuidInternal )
            v47 = 60000 * *SettingValueWithGuidInternal;
          SettingValueGlobalInternal = (_DWORD *)TetheringSettingsGetSettingValueGlobalInternal(16);
          v51 = SettingValueGlobalInternal;
          if ( SettingValueGlobalInternal )
            *((_BYTE *)this + 1568) = *SettingValueGlobalInternal == 1;
          *((_DWORD *)this + 398) = v47;
          if ( *((_BYTE *)this + 1568)
            && ChangeTimerQueueTimer(*((HANDLE *)this + 198), *((HANDLE *)this + 197), v47, 0xFFFFFFFF) )
          {
            *((_BYTE *)this + 1596) = 1;
          }
          if ( v51 )
            free(v51);
          if ( v49 )
            free(v49);
        }
        if ( ChangeTimerQueueTimer(*((HANDLE *)this + 204), *((HANDLE *)this + 203), 0xFFFFFFFF, 0xFFFFFFFF) )
          *((_BYTE *)this + 1644) = 0;
        if ( ChangeTimerQueueTimer(*((HANDLE *)this + 201), *((HANDLE *)this + 200), 0xFFFFFFFF, 0xFFFFFFFF) )
          *((_BYTE *)this + 1620) = 0;
        if ( *((_DWORD *)this + 154) != 8 )
        {
          Value = 0;
          v15 = 0;
          goto LABEL_182;
        }
        LODWORD(InterfaceLuid.Value) = 0;
        SharedInterfaceIndices = EntitlementMgr::GetProvisionedEntitlementStatus(
                                   (TetheringService *)((char *)this + 568),
                                   (enum TetheringEntitlementStatus *)&InterfaceLuid);
        v15 = SharedInterfaceIndices;
        if ( SharedInterfaceIndices >= 0 )
        {
          Value = InterfaceLuid.Value;
          if ( LODWORD(InterfaceLuid.Value) )
          {
            SharedInterfaceIndices = TetheringService::RegisterEntitlementFailedCallback((void **)this);
            v15 = SharedInterfaceIndices;
            if ( SharedInterfaceIndices < 0 )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_199;
              }
              v27 = 81;
              goto LABEL_41;
            }
            SharedInterfaceIndices = EntitlementMgr::StartPeriodicChecking((void **)this + 71);
            v15 = SharedInterfaceIndices;
            if ( SharedInterfaceIndices < 0 )
            {
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_199;
              }
              v27 = 82;
              goto LABEL_41;
            }
          }
LABEL_182:
          *((_DWORD *)this + 56) = 2;
          *(struct _GUID *)((char *)this + 1288) = *v70;
          *((_DWORD *)this + 412) = v15;
          v53 = (_OWORD *)((char *)this + 8);
          if ( v46 )
          {
            *v53 = *(_OWORD *)v46;
            *(_OWORD *)((char *)this + 24) = *(_OWORD *)(v46 + 16);
            *(_OWORD *)((char *)this + 40) = *(_OWORD *)(v46 + 32);
            *(_OWORD *)((char *)this + 56) = *(_OWORD *)(v46 + 48);
            *(_OWORD *)((char *)this + 72) = *(_OWORD *)(v46 + 64);
            *(_OWORD *)((char *)this + 88) = *(_OWORD *)(v46 + 80);
            *(_OWORD *)((char *)this + 104) = *(_OWORD *)(v46 + 96);
            *(_OWORD *)((char *)this + 120) = *(_OWORD *)(v46 + 112);
            *(_OWORD *)((char *)this + 136) = *(_OWORD *)(v46 + 128);
            *(_OWORD *)((char *)this + 152) = *(_OWORD *)(v46 + 144);
            *(_OWORD *)((char *)this + 168) = *(_OWORD *)(v46 + 160);
            *(_OWORD *)((char *)this + 184) = *(_OWORD *)(v46 + 176);
            *(_OWORD *)((char *)this + 200) = *(_OWORD *)(v46 + 192);
            *((_DWORD *)this + 54) = *(_DWORD *)(v46 + 208);
            *((_BYTE *)this + 220) = 1;
            v54 = *(_DWORD *)(v46 + 200);
            v55 = *(_DWORD *)(v46 + 204);
          }
          else
          {
            memset_0(v53, 0, 0xD4u);
            *((_BYTE *)this + 220) = 0;
            v56 = (_DWORD *)TetheringSettingsGetSettingValueGlobalInternal(7);
            if ( v56 )
            {
              v54 = v56[50];
              v55 = v56[51];
              free(v56);
            }
            else
            {
              v54 = 0;
              v55 = 0;
            }
          }
          v92 = GUID_NULL;
          v57 = *((_OWORD *)this + 27);
          v58 = *((_DWORD *)this + 112);
          InterfaceLuid.Value = 0;
          InterfaceGuid = GUID_NULL;
          v59 = ConvertInterfaceIndexToLuid(v75, &InterfaceLuid);
          if ( v59 )
          {
            v61 = 1409;
          }
          else
          {
            v59 = ConvertInterfaceLuidToGuid(&InterfaceLuid, &InterfaceGuid);
            if ( !v59 )
            {
              v92 = InterfaceGuid;
              v62 = 0;
              goto LABEL_193;
            }
            v61 = 1411;
          }
          v62 = wil::details::in1diag3::Return_Win32(retaddr, (void *)v61, v60, (const char *)v59, 4u);
LABEL_193:
          if ( v62 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x3D2,
              (unsigned int)"onecoreuap\\net\\tethering\\service\\tetheringservice.cpp",
              (const char *)(unsigned int)v62,
              v68);
          v63 = *((_DWORD *)this + 412);
          if ( (v63 & 0x1FFF0000) == 0x70000 )
            v63 = (unsigned __int16)v63;
          *(_DWORD *)Table = 25;
          *(_OWORD *)&Table[4] = v57;
          v91 = v58;
          NetworkingTriageScenario::MobileHotspot::TetheringStarted(
            (const struct NetworkingTriageScenario::MobileHotspot::RequiredFields *)Table,
            &v92,
            v75,
            v76,
            v71[1],
            v54,
            v55,
            Value,
            v63);
          goto LABEL_198;
        }
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_199;
        }
        v27 = 80;
LABEL_41:
        v28 = (unsigned int)SharedInterfaceIndices;
LABEL_42:
        WPP_SF_d(*((_QWORD *)v17 + 2), v27, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v28);
        goto LABEL_198;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
        (unsigned int)v33);
    }
    v37 = WPP_GLOBAL_Control;
    goto LABEL_80;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v18 = 59;
    v19 = (unsigned int)InterfaceGuidInMibTable;
    goto LABEL_27;
  }
LABEL_201:
  if ( (a5 & 1) != 0 )
  {
    memset_0(v85, 0, 0xCCu);
    v83 = 1;
    v84 = v15;
    TetheringService::SendNotification(this, (struct _TETHERING_WNF_NOTIFICATION_MSG *)&v83);
    v17 = WPP_GLOBAL_Control;
  }
  if ( v71[0] )
  {
    if ( v17 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)v17 + 2), 83, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    CSebHelper::PublishWnfEvent(v7, 11);
  }
  v64 = v73;
  if ( !v73 )
  {
    if ( v12 )
    {
      TetheringServiceTelemetry::AcquireSessionData(v17, v12, (struct TetheringServiceTelemetry::SESSION_DATA *)v94);
      v65 = (_DWORD *)v100;
      *(_DWORD *)(v100 + 8) = a5;
      v65[10] = v76;
      v65[11] = v75;
      v65[23] = v74;
      v65[24] = v9;
      v65[7] = v15;
      ReleaseSRWLockExclusive(v12 + 2);
      goto LABEL_211;
    }
LABEL_231:
    ATL::AtlThrowImpl(-2147467259);
  }
LABEL_211:
  if ( v15 < 0 )
  {
    *((_DWORD *)this + 412) = v15;
    TetheringService::StopSharing((__int64)this, a5, 10);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 232));
  if ( g_lTraceLoggingRegistered < 0 )
    goto LABEL_222;
  if ( (unsigned int)dword_180041008 > 5
    && (qword_180041018 & 0x400000000000LL) != 0
    && (qword_180041020 & 0x400000000000LL) == qword_180041020 )
  {
    LODWORD(InterfaceLuid.Value) = v15;
    v73 = a5;
    LODWORD(v69) = v9;
    p_InterfaceLuid = &InterfaceLuid;
    v108 = 4;
    v105 = &v73;
    v106 = 4;
    v103 = &v69;
    v104 = 4;
    v101 = &v74;
    v102 = 4;
    v99 = v78;
    v100 = 16;
    v97 = v7;
    v98 = 16;
    v95 = &sourceString;
    v96 = 2;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180041008, (unsigned __int8 *)byte_180039C9B, 0, 0, 9u, v94);
  }
  if ( v64 >= 0 )
    goto LABEL_222;
  v66 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
    goto LABEL_226;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      84,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)v64);
LABEL_222:
    v66 = WPP_GLOBAL_Control;
  }
  if ( v66 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v66 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v66 + 2), 85, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)v15);
LABEL_226:
  if ( Memory )
    FreeMibTable(Memory);
  if ( v12 )
    (*((void (__fastcall **)(RTL_SRWLOCK *))v12->Ptr + 2))(v12);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001e4a4  mov     rax, rsp
0x18001e4a7  push    rbp
0x18001e4a8  push    rbx
0x18001e4a9  push    rsi
0x18001e4aa  push    rdi
0x18001e4ab  push    r12
0x18001e4ad  push    r13
0x18001e4af  push    r14
0x18001e4b1  push    r15
0x18001e4b3  lea     rbp, [rax-718h]
0x18001e4ba  sub     rsp, 7D8h
0x18001e4c1  movaps  xmmword ptr [rax-58h], xmm6
0x18001e4c5  mov     rax, cs:__security_cookie
0x18001e4cc  xor     rax, rsp
0x18001e4cf  mov     [rbp+710h+var_60], rax
0x18001e4d6  mov     qword ptr [rbp+710h+InterfaceGuid.Data1], r9
0x18001e4dd  mov     rbx, r8
0x18001e4e0  mov     [rbp+710h+var_788], rbx
0x18001e4e4  mov     r13, rdx
0x18001e4e7  mov     qword ptr [rsp+810h+var_7B8], rdx
0x18001e4ec  mov     r15, rcx
0x18001e4ef  mov     rax, [rbp+710h+arg_28]
0x18001e4f6  mov     qword ptr [rbp+710h+var_110.Data1], rax
0x18001e4fd  lea     rax, WPP_GLOBAL_Control
0x18001e504  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e50b  mov     edi, [rbp+710h+arg_20]
0x18001e511  cmp     rcx, rax
0x18001e514  jz      short loc_18001E53D
0x18001e516  test    byte ptr [rcx+1Ch], 8
0x18001e51a  jz      short loc_18001E53D
0x18001e51c  mov     edx, 39h ; '9'
0x18001e521  mov     [rsp+810h+var_7E8], edi
0x18001e525  mov     qword ptr [rsp+810h+var_7F0], rbx
0x18001e52a  mov     r9, r13
0x18001e52d  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001e534  mov     rcx, [rcx+10h]
0x18001e538  call    WPP_SF__guid__guid_d
0x18001e53d  xor     r14d, r14d
0x18001e540  mov     [rsp+810h+var_794], r14d
0x18001e545  mov     [rsp+810h+var_798], r14d
0x18001e54a  mov     [rsp+810h+var_79C], r14d
0x18001e54f  mov     r12d, r14d
0x18001e552  mov     dword ptr [rsp+810h+var_7C0], r14d
0x18001e557  xor     edx, edx; Val
0x18001e559  lea     r8d, [r14+50h]; Size
0x18001e55d  lea     rcx, [rbp+710h+var_F0]; void *
0x18001e564  call    memset_0
0x18001e569  nop
0x18001e56a  mov     esi, r14d
0x18001e56d  mov     [rbp+710h+var_780], r14
0x18001e571  mov     [rsp+810h+var_7B0], r14b
0x18001e576  mov     rdx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data1; struct _GUID *
0x18001e57d  test    rdx, rdx
0x18001e580  jnz     short loc_18001E58C
0x18001e582  mov     [rsp+810h+var_7A0], 8000FFFFh
0x18001e58a  jmp     short loc_18001E5CC
0x18001e58c  lea     r8, [rbp+710h+var_780]; struct TetheringSessionTelemetry **
0x18001e590  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x18001e595  mov     ebx, eax
0x18001e597  mov     [rsp+810h+var_7A0], eax
0x18001e59b  mov     rsi, [rbp+710h+var_780]
0x18001e59f  test    eax, eax
0x18001e5a1  js      short loc_18001E5C8
0x18001e5a3  test    rsi, rsi
0x18001e5a6  jnz     short loc_18001E5B2
0x18001e5a8  mov     [rsp+810h+var_7A0], 80004003h
0x18001e5b0  jmp     short loc_18001E5C8
0x18001e5b2  mov     rcx, rsi; this
0x18001e5b5  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x18001e5ba  test    eax, eax
0x18001e5bc  mov     eax, 80004005h
0x18001e5c1  cmovz   ebx, eax
0x18001e5c4  mov     [rsp+810h+var_7A0], ebx
0x18001e5c8  mov     rbx, [rbp+710h+var_788]
0x18001e5cc  mov     rdx, 400000000000h
0x18001e5d6  lea     r8, sourceString
0x18001e5dd  cmp     cs:?g_lTraceLoggingRegistered@@3JA, r14d; long g_lTraceLoggingRegistered
0x18001e5e4  jl      short loc_18001E650
0x18001e5e6  mov     eax, cs:dword_180041008
0x18001e5ec  cmp     eax, 5
0x18001e5ef  jbe     short loc_18001E650
0x18001e5f1  mov     rcx, cs:qword_180041020
0x18001e5f8  mov     rax, cs:qword_180041018
0x18001e5ff  test    rdx, rax
0x18001e602  jz      short loc_18001E650
0x18001e604  mov     rax, rcx
0x18001e607  and     rax, rdx
0x18001e60a  cmp     rax, rcx
0x18001e60d  jnz     short loc_18001E650
0x18001e60f  mov     dword ptr [rsp+810h+InterfaceLuid], edi
0x18001e613  mov     [rbp+710h+var_778], rbx
0x18001e617  mov     [rbp+710h+var_770], r13
0x18001e61b  mov     [rbp+710h+var_768], r8
0x18001e61f  lea     rax, [rsp+810h+InterfaceLuid]
0x18001e624  mov     qword ptr [rsp+810h+var_7D8], rax
0x18001e629  lea     rax, [rbp+710h+var_778]
0x18001e62d  mov     qword ptr [rsp+810h+var_7E0], rax
0x18001e632  lea     rax, [rbp+710h+var_770]
0x18001e636  mov     qword ptr [rsp+810h+var_7E8], rax
0x18001e63b  lea     rax, [rbp+710h+var_768]
0x18001e63f  mov     qword ptr [rsp+810h+var_7F0], rax
0x18001e644  lea     rdx, word_180039976
0x18001e64b  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18001e650  mov     [rbp+710h+Memory], 0
0x18001e658  lea     rax, [rbp+710h+Memory]
0x18001e65c  mov     [rbp+710h+Table], rax
0x18001e663  mov     [rbp+710h+Table+8], 0
0x18001e66e  mov     [rbp+710h+var_120], 1
0x18001e675  lea     rcx, [rbp+710h+Table+8]; Table
0x18001e67c  call    cs:__imp_GetIfTable2
0x18001e682  mov     r14d, eax
0x18001e685  test    eax, eax
0x18001e687  jle     short loc_18001E694
0x18001e689  movzx   r14d, ax
0x18001e68d  or      r14d, 80070000h
0x18001e694  cmp     [rbp+710h+var_120], 0
0x18001e69b  jz      short loc_18001E6BC
0x18001e69d  mov     rdx, [rbp+710h+Table]
0x18001e6a4  mov     rcx, [rdx]; Memory
0x18001e6a7  mov     rax, [rbp+710h+Table+8]
0x18001e6ae  mov     [rdx], rax
0x18001e6b1  test    rcx, rcx
0x18001e6b4  jz      short loc_18001E6BC
0x18001e6b6  call    cs:__imp_FreeMibTable
0x18001e6bc  test    r14d, r14d
0x18001e6bf  jns     short loc_18001E706
0x18001e6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e6c8  lea     rbx, WPP_GLOBAL_Control
0x18001e6cf  cmp     rcx, rbx
0x18001e6d2  jz      loc_18001F389
0x18001e6d8  test    byte ptr [rcx+1Ch], 1
0x18001e6dc  jz      loc_18001F389
0x18001e6e2  mov     edx, 3Ah ; ':'
0x18001e6e7  mov     r9d, r14d
0x18001e6ea  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001e6f1  mov     rcx, [rcx+10h]
0x18001e6f5  call    WPP_SF_d
0x18001e6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e701  jmp     loc_18001F389
0x18001e706  mov     dword ptr [rsp+810h+InterfaceLuid], 0
0x18001e70e  lea     r8, [rsp+810h+InterfaceLuid]; unsigned int *
0x18001e713  mov     rdx, r13; struct _GUID *
0x18001e716  mov     rcx, [rbp+710h+Memory]; struct _MIB_IF_TABLE2 *
0x18001e71a  call    ?FindInterfaceGuidInMibTable@InterfaceMgr@@SAJPEAU_MIB_IF_TABLE2@@PEBU_GUID@@PEAK@Z; InterfaceMgr::FindInterfaceGuidInMibTable(_MIB_IF_TABLE2 *,_GUID const *,ulong *)
0x18001e71f  mov     r14d, eax
0x18001e722  test    eax, eax
0x18001e724  jns     short loc_18001E751
0x18001e726  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e72d  lea     rbx, WPP_GLOBAL_Control
0x18001e734  cmp     rcx, rbx
0x18001e737  jz      loc_18001F389
0x18001e73d  test    byte ptr [rcx+1Ch], 1
0x18001e741  jz      loc_18001F389
0x18001e747  mov     edx, 3Bh ; ';'
0x18001e74c  mov     r9d, eax
0x18001e74f  jmp     short loc_18001E6EA
0x18001e751  mov     eax, dword ptr [rsp+810h+InterfaceLuid]
0x18001e755  imul    r13, rax, 548h
0x18001e75c  mov     rbx, [rbp+710h+Memory]
0x18001e760  mov     r14d, [rbx+r13+47Ch]
0x18001e768  mov     [rsp+810h+var_79C], r14d
0x18001e76d  xor     edx, edx; Val
0x18001e76f  mov     r8d, 548h; Size
0x18001e775  lea     rcx, [rbp+710h+var_680]; void *
0x18001e77c  call    memset_0
0x18001e781  mov     r12, qword ptr cs:GUID_NULL.Data1
0x18001e788  mov     rax, [rbp+710h+var_788]
0x18001e78c  cmp     [rax], r12
0x18001e78f  jnz     short loc_18001E7F6
0x18001e791  mov     rdi, qword ptr cs:GUID_NULL.Data4
0x18001e798  cmp     [rax+8], rdi
0x18001e79c  jnz     short loc_18001E7F6
0x18001e79e  mov     ecx, 0Ah
0x18001e7a3  mov     dword ptr [rsp+810h+var_7C0], ecx
0x18001e7a7  mov     [rbp+710h+var_20C], ecx
0x18001e7ad  mov     [rbp+710h+Buf1], r12
0x18001e7b4  mov     [rbp+710h+var_66C], rdi
0x18001e7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e7c2  lea     rbx, WPP_GLOBAL_Control
0x18001e7c9  cmp     rcx, rbx
0x18001e7cc  jz      loc_18001E89F
0x18001e7d2  test    byte ptr [rcx+1Ch], 8
0x18001e7d6  jz      loc_18001E89F
0x18001e7dc  mov     edx, 3Ch ; '<'
0x18001e7e1  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001e7e8  mov     rcx, [rcx+10h]
0x18001e7ec  call    WPP_SF_
0x18001e7f1  jmp     loc_18001E89F
0x18001e7f6  mov     dword ptr [rsp+810h+InterfaceLuid], 0
0x18001e7fe  lea     r8, [rsp+810h+InterfaceLuid]; unsigned int *
0x18001e803  mov     rdx, rax; struct _GUID *
0x18001e806  mov     rcx, rbx; struct _MIB_IF_TABLE2 *
0x18001e809  call    ?FindInterfaceGuidInMibTable@InterfaceMgr@@SAJPEAU_MIB_IF_TABLE2@@PEBU_GUID@@PEAK@Z; InterfaceMgr::FindInterfaceGuidInMibTable(_MIB_IF_TABLE2 *,_GUID const *,ulong *)
0x18001e80e  mov     r14d, eax
0x18001e811  test    eax, eax
0x18001e813  jns     short loc_18001E853
0x18001e815  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e81c  lea     rbx, WPP_GLOBAL_Control
0x18001e823  cmp     rcx, rbx
0x18001e826  jz      loc_18001F37F
0x18001e82c  test    byte ptr [rcx+1Ch], 1
0x18001e830  jz      loc_18001F37F
0x18001e836  mov     edx, 3Dh ; '='
0x18001e83b  mov     r9d, eax
0x18001e83e  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001e845  mov     rcx, [rcx+10h]
0x18001e849  call    WPP_SF_d
0x18001e84e  jmp     loc_18001F378
0x18001e853  mov     eax, dword ptr [rsp+810h+InterfaceLuid]
0x18001e857  imul    rdx, rax, 548h
0x18001e85e  lea     rcx, [rbp+710h+var_680]; void *
0x18001e865  mov     rax, [rbp+710h+Memory]
0x18001e869  add     rax, 8
0x18001e86d  add     rdx, rax; Src
0x18001e870  mov     r8d, 548h; Size
0x18001e876  call    memcpy_0
0x18001e87b  mov     ecx, [rbp+710h+var_20C]
0x18001e881  mov     dword ptr [rsp+810h+var_7C0], ecx
0x18001e885  mov     rdi, [rbp+710h+var_66C]
0x18001e88c  mov     r12, [rbp+710h+Buf1]
0x18001e893  mov     r14d, [rsp+810h+var_79C]
0x18001e898  lea     rbx, WPP_GLOBAL_Control
0x18001e89f  lea     rcx, [r15+0E8h]; lpCriticalSection
0x18001e8a6  call    cs:__imp_EnterCriticalSection
0x18001e8ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8b3  cmp     rcx, rbx
0x18001e8b6  jz      short loc_18001E8DA
0x18001e8b8  test    byte ptr [rcx+1Ch], 8
0x18001e8bc  jz      short loc_18001E8DA
0x18001e8be  mov     rcx, [rcx+10h]
0x18001e8c2  lea     rax, [r15+508h]
0x18001e8c9  mov     qword ptr [rsp+810h+var_7F0], rax
0x18001e8ce  mov     r9d, [r15+0E0h]
0x18001e8d5  call    WPP_SF_L_guid_
0x18001e8da  mov     eax, [r15+0E0h]
0x18001e8e1  cmp     eax, 2
0x18001e8e4  jnz     short loc_18001E91E
0x18001e8e6  xor     r14d, r14d
0x18001e8e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e8f0  cmp     rcx, rbx
0x18001e8f3  jz      loc_18001F37F
0x18001e8f9  test    byte ptr [rcx+1Ch], 4
0x18001e8fd  jz      loc_18001F37F
0x18001e903  lea     edx, [rax+3Dh]
0x18001e906  mov     r9d, eax
0x18001e909  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001e910  mov     rcx, [rcx+10h]
0x18001e914  call    WPP_SF_d
0x18001e919  jmp     loc_18001F378
0x18001e91e  cmp     r14d, 8
0x18001e922  jnz     short loc_18001E980
0x18001e924  lea     rbx, [r15+5D0h]
0x18001e92b  mov     rcx, rbx; lpCriticalSection
0x18001e92e  call    cs:__imp_EnterCriticalSection
0x18001e934  mov     rcx, r15; this
0x18001e937  call    ?InitializeCellularWnfSubscriptions@TetheringService@@AEAAJXZ; TetheringService::InitializeCellularWnfSubscriptions(void)
0x18001e93c  mov     r14d, eax
0x18001e93f  mov     rcx, rbx; lpCriticalSection
0x18001e942  call    cs:__imp_LeaveCriticalSection
0x18001e948  test    r14d, r14d
0x18001e94b  jns     short loc_18001E97B
0x18001e94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e954  lea     rbx, WPP_GLOBAL_Control
0x18001e95b  cmp     rcx, rbx
0x18001e95e  jz      loc_18001F37F
0x18001e964  test    byte ptr [rcx+1Ch], 1
0x18001e968  jz      loc_18001F37F
0x18001e96e  mov     edx, 40h ; '@'
0x18001e973  mov     r9d, r14d
0x18001e976  jmp     loc_18001E83E
0x18001e97b  mov     r14d, [rsp+810h+var_79C]
0x18001e980  mov     dword ptr [r15+0E0h], 4
0x18001e98b  test    byte ptr [rbp+710h+arg_20], 1
0x18001e992  jz      short loc_18001E9B8
0x18001e994  xor     edx, edx; Val
0x18001e996  mov     r8d, 0D0h; Size
0x18001e99c  lea     rcx, [rbp+710h+var_75C]; void *
0x18001e9a0  call    memset_0
0x18001e9a5  mov     [rbp+710h+var_760], 8
0x18001e9ac  lea     rdx, [rbp+710h+var_760]; struct _TETHERING_WNF_NOTIFICATION_MSG *
0x18001e9b0  mov     rcx, r15; this
0x18001e9b3  call    ?SendNotification@TetheringService@@AEAAXPEAU_TETHERING_WNF_NOTIFICATION_MSG@@@Z; TetheringService::SendNotification(_TETHERING_WNF_NOTIFICATION_MSG *)
0x18001e9b8  call    ?IsMobile@@YA_NXZ; IsMobile(void)
0x18001e9bd  movzx   ebx, al
0x18001e9c0  cmp     [rsp+810h+var_7A0], 0
0x18001e9c5  jnz     short loc_18001E9F3
0x18001e9c7  test    rsi, rsi
0x18001e9ca  jz      loc_18001F65D
0x18001e9d0  lea     r8, [rbp+710h+var_F0]; struct TetheringServiceTelemetry::SESSION_DATA *
0x18001e9d7  mov     rdx, rsi; struct TetheringSessionTelemetry *
0x18001e9da  call    ?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z; TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)
0x18001e9df  mov     rcx, [rbp+710h+var_A8]
0x18001e9e6  mov     [rcx+4], ebx
0x18001e9e9  lea     rcx, [rsi+10h]; SRWLock
0x18001e9ed  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e9f3  test    bl, bl
0x18001e9f5  jnz     short loc_18001EA40
0x18001e9f7  cmp     r14d, 8
0x18001e9fb  jnz     short loc_18001EA40
0x18001e9fd  mov     [rsp+810h+var_7B0], 1
  ... truncated ...
```
