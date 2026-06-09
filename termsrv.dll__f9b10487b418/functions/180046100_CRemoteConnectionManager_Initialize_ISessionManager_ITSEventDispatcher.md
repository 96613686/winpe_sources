# CRemoteConnectionManager::Initialize(ISessionManager *,ITSEventDispatcher *)

- ea: `0x180046100`
- end: `0x1800469da`
- name: `?Initialize@CRemoteConnectionManager@@UEAAJPEAUISessionManager@@PEAUITSEventDispatcher@@@Z`
- size: `2266`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this, struct ISessionManager *, struct ITSEventDispatcher *)`
- caller_count: `0`
- callee_count: `37`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001284`
- `0x180009ee0`
- `0x18000a210`
- `0x180011f80`
- `0x1800126d0`
- `0x180013150`
- `0x1800241f0`
- `0x180024d80`
- `0x180027d54`
- `0x18002869c`
- `0x180030820`
- `0x1800321f0`
- `0x1800326dc`
- `0x18003cae8`
- `0x18003d828`
- `0x18003e770`
- `0x180045020`
- `0x180046100`
- `0x1800469e0`
- `0x180046aa0`
- `0x180046b80`
- `0x18004e274`
- `0x18005a7c0`
- `0x18005c3f0`
- `0x1800603cc`
- `0x18006e040`
- `0x180071844`
- `0x18007b6c8`
- `0x18007d154`
- `0x18008718c`
- `0x18008f8fc`
- `0x180091d30`
- `0x180093e90`
- `0x18009cc40`
- `0x1800b1570`
- `0x1800b7b34`
- `0x1800c8010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800461b2`
- `ntdll!EtwEventActivityIdControl` at `0x180046983`
- `ntdll!EtwEventActivityIdControl` at `0x1800461b2`
- `ntdll!EtwEventActivityIdControl` at `0x180046983`

## string_xrefs

- `0x1800461e7`: `Initialize() call on service stop started failed: 0x%x in %s`
- `0x18004652e`: `this->ptrRCMSink->Initialize failed: 0x%x in %s`
- `0x180046672`: `new CProtocolExMgr() failed: 0x%x in %s`
- `0x180046857`: `error %#x: CAudit initialization failed; error ignored, but TermService will not log events`
- `0x180046868`: `Going to create timer handler manager`
- `0x18004693c`: `RDSHTelemetryLogging telemetry service failed to start`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CRemoteConnectionManager::Initialize(
        CRemoteConnectionManager *this,
        struct ISessionManager *a2,
        struct ITSEventDispatcher *a3)
{
  unsigned __int16 *v6; // rdx
  unsigned __int16 *v7; // rcx
  int v8; // edi
  const char *v9; // rdx
  int v10; // eax
  struct ISessionManager **v11; // r14
  int v12; // eax
  int v13; // eax
  int InstanceOfConnectionDispatchManager; // eax
  int InstanceOfEnforcementCore; // eax
  int InstanceOf; // eax
  int InstanceofTerminalPreferenceManager; // eax
  CDefTSNotifySink *v18; // rax
  CDefTSNotifySink *v19; // rdi
  CRemoteConnectionManager::CRemoteConnectionManagerSink *v20; // rcx
  int v21; // eax
  CWsxMgr *v22; // rax
  CWsxMgr *v23; // rcx
  int v24; // eax
  CProtocolExMgr *v25; // rax
  CProtocolExMgr **v26; // r15
  int InstanceOfObject; // eax
  int v28; // eax
  int v29; // eax
  int InstanceOfRCMPrivateRpc; // eax
  int InstanceOfRCMPublicRpc; // eax
  int InstanceOfRCMLegacyRpc; // eax
  CAudit *v33; // rax
  const unsigned __int16 *v34; // rdx
  int InstanceOfTimerHandlerManager; // eax
  CRemoteConnectionManager *v36; // rcx
  CProtocolExMgr *v37; // rcx
  int v38; // eax
  int v39; // eax
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v43; // [rsp+30h] [rbp-89h] BYREF
  int v44[2]; // [rsp+38h] [rbp-81h] BYREF
  _BYTE v45[16]; // [rsp+40h] [rbp-79h] BYREF
  __int64 v46; // [rsp+50h] [rbp-69h] BYREF
  const char *v47; // [rsp+58h] [rbp-61h] BYREF
  __int64 v48; // [rsp+60h] [rbp-59h] BYREF
  CProtocolExMgr *v49; // [rsp+68h] [rbp-51h]
  _BYTE v50[16]; // [rsp+70h] [rbp-49h] BYREF
  GUID pguid; // [rsp+80h] [rbp-39h] BYREF
  GUID v52; // [rsp+90h] [rbp-29h] BYREF
  const char *v53[7]; // [rsp+A0h] [rbp-19h] BYREF

  v47 = (const char *)a2;
  v46 = 0;
  v48 = 0;
  v44[0] = 0;
  CWPPConfig::Refresh((CRemoteConnectionManager *)((char *)this + 264));
  CGenericTrace::CGenericTrace(
    (CGenericTrace *)v53,
    16,
    "CRemoteConnectionManager Initialize ...",
    "CRemoteConnectionManager::Initialize");
  CUtils::DebugBreakIfAskedEx(v7, v6);
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v50, (struct _RTL_RESOURCE *)((char *)this + 1000));
  pguid = 0;
  v8 = GenerateConstrainedGuid(&pguid, 0xF4610000);
  v52 = pguid;
  EtwEventActivityIdControl(4, &v52);
  if ( v8 < 0 )
  {
    _DbgPrintMessage(
      8,
      "GenerateConstrainedGuid failed: 0x%x in %s",
      (unsigned int)v8,
      "CRemoteConnectionManager::Initialize");
    goto LABEL_78;
  }
  if ( *((_BYTE *)this + 2544) )
  {
    v8 = -2147023834;
    v9 = "Initialize() call on service stop started failed: 0x%x in %s";
LABEL_6:
    _DbgPrintMessage(8, v9, (unsigned int)v8, "CRemoteConnectionManager::Initialize");
    goto LABEL_79;
  }
  if ( *((_DWORD *)this + 312) != 1 )
  {
    v8 = -2147418113;
    v9 = "Initialize() call on non-stopped failed: 0x%x in %s";
    goto LABEL_6;
  }
  *((_DWORD *)this + 642) = 0;
  if ( (int)CSLQuery::IsAppServerInstalled(v44) >= 0 && v44[0] == 1 )
  {
    *((_DWORD *)this + 642) = 1;
    *((_DWORD *)this + 643) = 1;
  }
  if ( *((_DWORD *)this + 643) )
  {
    v10 = CRemoteConnectionManager::UALStart(this);
    if ( v10 < 0 && (g_DebugTraceComponent & 0x10) != 0 )
      _DbgPrintMessage(2, "UALStart failed (0x%08x). No UAL logging", v10);
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v45, (struct _RTL_RESOURCE *)((char *)this + 1104));
  v43 = 0;
  v11 = (struct ISessionManager **)((char *)this + 496);
  SmartPtr<ITerminal>::operator=((char *)this + 496, a2);
  v12 = (*(__int64 (__fastcall **)(struct ISessionManager *, char *))(*(_QWORD *)*v11 + 24LL))(*v11, (char *)this + 544);
  v8 = v12;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", v12, "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 68) + 32LL))(
          *((_QWORD *)this + 68),
          (char *)this + 552);
  v8 = v13;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "GetInstanceOfEnum failed: 0x%x in %s", v13, "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  InstanceOfConnectionDispatchManager = IConnectionDispatchManager::GetInstanceOfConnectionDispatchManager((struct IConnectionDispatchManager **)this + 67);
  v8 = InstanceOfConnectionDispatchManager;
  if ( InstanceOfConnectionDispatchManager < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetInstanceOfConnectionDispatchManager failed: 0x%x in %s",
      InstanceOfConnectionDispatchManager,
      "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  InstanceOfEnforcementCore = IEnforcementCore::GetInstanceOfEnforcementCore((struct IEnforcementCore **)this + 63);
  v8 = InstanceOfEnforcementCore;
  if ( InstanceOfEnforcementCore < 0 )
  {
    _DbgPrintMessage(
      8,
      "IEnforcementCore::GetInstanceOfEnforcementCore failed: 0x%x in %s",
      InstanceOfEnforcementCore,
      "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  InstanceOf = IExternalEventDispatcher::GetInstanceOf(a3, (struct IExternalEventDispatcher **)this + 154);
  v8 = InstanceOf;
  if ( InstanceOf < 0 )
  {
    _DbgPrintMessage(
      8,
      "IExternalEventDispatcher::GetInstanceOf failed: 0x%x in %s",
      InstanceOf,
      "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  InstanceofTerminalPreferenceManager = CTerminalSupportManager::GetInstanceofTerminalPreferenceManager((struct CTerminalSupportManager **)this + 155);
  v8 = InstanceofTerminalPreferenceManager;
  if ( InstanceofTerminalPreferenceManager < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetInstanceofTerminalPreferenceManager failed: 0x%x in %s",
      InstanceofTerminalPreferenceManager,
      "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  v18 = (CDefTSNotifySink *)operator new(0x6B0u, (const struct std::nothrow_t *)std::nothrow);
  v19 = v18;
  *(_QWORD *)v44 = v18;
  if ( v18 )
  {
    CDefTSNotifySink::CDefTSNotifySink(v18, "CRemoteConnectionManagerSink");
    *(_QWORD *)v19 = &CRemoteConnectionManager::CRemoteConnectionManagerSink::`vftable';
    *((_QWORD *)v19 + 199) = 0;
    *((_QWORD *)v19 + 200) = 0;
    *((_DWORD *)v19 + 426) = 0;
  }
  else
  {
    v19 = 0;
  }
  SmartPtr<ITerminal>::operator=((char *)this + 480, v19);
  v20 = (CRemoteConnectionManager::CRemoteConnectionManagerSink *)*((_QWORD *)this + 60);
  if ( !v20 )
  {
    v8 = -2147024882;
    _DbgPrintMessage(
      8,
      "new CRemoteConnectionManagerSink() failed: 0x%x in %s",
      -2147024882,
      "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
LABEL_79:
    (*(void (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 48LL))(this);
    goto LABEL_80;
  }
  v21 = CRemoteConnectionManager::CRemoteConnectionManagerSink::Initialize(v20, this);
  v8 = v21;
  if ( v21 < 0 )
  {
    _DbgPrintMessage(8, "this->ptrRCMSink->Initialize failed: 0x%x in %s", v21, "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  v22 = (CWsxMgr *)operator new(0x6C8u, (const struct std::nothrow_t *)std::nothrow);
  *(_QWORD *)v44 = v22;
  if ( v22 )
    v22 = CWsxMgr::CWsxMgr(v22);
  SmartPtr<ITerminal>::operator=((char *)this + 72, v22);
  v23 = (CWsxMgr *)*((_QWORD *)this + 9);
  if ( !v23 )
  {
    v8 = -2147024882;
    _DbgPrintMessage(8, "new CWsxMgr() failed: 0x%x in %s", -2147024882, "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_79;
  }
  v24 = CWsxMgr::Initialize(v23);
  v8 = v24;
  v44[0] = v24;
  if ( v24 < 0 )
  {
    _DbgPrintMessage(8, "this->ptrWsxMgr->Initialize failed: 0x%x in %s", v24, "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  v25 = (CProtocolExMgr *)operator new(0x7A0u, (const struct std::nothrow_t *)std::nothrow);
  v49 = v25;
  if ( v25 )
  {
    v25 = CProtocolExMgr::CProtocolExMgr(v25, *v11, v44);
    v8 = v44[0];
  }
  v26 = (CProtocolExMgr **)((char *)this + 80);
  SmartPtr<ITerminal>::operator=((char *)this + 80, v25);
  if ( !*((_QWORD *)this + 10) )
    v8 = -2147024882;
  if ( v8 < 0 )
  {
    SmartPtr<ITerminal>::operator=((char *)this + 80, 0);
    _DbgPrintMessage(8, "new CProtocolExMgr() failed: 0x%x in %s", v8, "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  InstanceOfObject = ITSRpcClientTrackerMgr::GetInstanceOfObject((struct ITSRpcClientTrackerMgr **)this + 70);
  v8 = InstanceOfObject;
  if ( InstanceOfObject < 0 )
  {
    _DbgPrintMessage(
      8,
      "ITSRpcClientTrackerMgr::GetInstanceOfObject failed: 0x%x in %s",
      InstanceOfObject,
      "CRemoteConnectionManager::Initialize");
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
    CAutoLock::Unlock((CAutoLock *)v45);
    goto LABEL_78;
  }
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v43);
  CAutoLock::Unlock((CAutoLock *)v45);
  v28 = (*(__int64 (__fastcall **)(_QWORD, const char *, _QWORD))(**((_QWORD **)this + 63) + 24LL))(
          *((_QWORD *)this + 63),
          v47,
          *((_QWORD *)this + 154));
  v8 = v28;
  if ( v28 < 0 )
  {
    _DbgPrintMessage(
      8,
      "IEnforcementCore::Initialize failed: 0x%x in %s",
      (unsigned int)v28,
      "CRemoteConnectionManager::Initialize");
    goto LABEL_78;
  }
  while ( 1 )
  {
    v29 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 69) + 80LL))(*((_QWORD *)this + 69), &v46);
    v8 = v29;
    if ( v29 == -2147024637 )
      break;
    if ( v29 < 0 )
    {
      _DbgPrintMessage(
        8,
        "SessionEnum->Enum failed: 0x%x in %s",
        (unsigned int)v29,
        "CRemoteConnectionManager::Initialize");
      goto LABEL_78;
    }
    SmartPtr<ITerminal>::operator=(&v46, 0);
  }
  InstanceOfRCMPrivateRpc = IRCMPrivateRpc::GetInstanceOfRCMPrivateRpc((struct IRCMPrivateRpc **)this + 64);
  v8 = InstanceOfRCMPrivateRpc;
  if ( InstanceOfRCMPrivateRpc < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetInstanceOfRCMPrivateRpc failed: 0x%x in %s",
      (unsigned int)InstanceOfRCMPrivateRpc,
      "CRemoteConnectionManager::Initialize");
    goto LABEL_78;
  }
  InstanceOfRCMPublicRpc = IRCMPublicRpc::GetInstanceOfRCMPublicRpc((struct IRCMPublicRpc **)this + 65);
  v8 = InstanceOfRCMPublicRpc;
  if ( InstanceOfRCMPublicRpc < 0 )
  {
    _DbgPrintMessage(
      8,
      "GetInstanceOfRCMPublicRpc failed: 0x%x in %s",
      (unsigned int)InstanceOfRCMPublicRpc,
      "CRemoteConnectionManager::Initialize");
    goto LABEL_78;
  }
  InstanceOfRCMLegacyRpc = IRCMLegacyRpc::GetInstanceOfRCMLegacyRpc((struct IRCMLegacyRpc **)this + 66);
  v8 = InstanceOfRCMLegacyRpc;
  v44[0] = InstanceOfRCMLegacyRpc;
  if ( InstanceOfRCMLegacyRpc < 0 )
  {
    _DbgPrintMessage(
      8,
      "IRCMLegacyRpc::GetInstanceOfLegacyRpc failed: 0x%x in %s",
      (unsigned int)InstanceOfRCMLegacyRpc,
      "CRemoteConnectionManager::Initialize");
    goto LABEL_78;
  }
  v33 = (CAudit *)operator new(0x640u, (const struct std::nothrow_t *)std::nothrow);
  v49 = v33;
  if ( v33 )
  {
    v33 = CAudit::CAudit(v33, v34, v44);
    v8 = v44[0];
  }
  SmartPtr<ITerminal>::operator=((char *)this + 488, v33);
  if ( !*((_QWORD *)this + 61) )
  {
    v8 = -2147024882;
    _DbgPrintMessage(8, "new CAudit() failed: 0x%x in %s", 2147942414LL, "CRemoteConnectionManager::Initialize");
    goto LABEL_79;
  }
  if ( v8 < 0 )
    _DbgPrintMessage(
      4,
      "error %#x: CAudit initialization failed; error ignored, but TermService will not log events",
      v8);
  _DbgPrintMessage(1, "Going to create timer handler manager");
  if ( *((_QWORD *)this + 152)
    || (InstanceOfTimerHandlerManager = CTSTimerHandlerManager::GetInstanceOfTimerHandlerManager((struct CTSTimerHandlerManager **)this + 152),
        v8 = InstanceOfTimerHandlerManager,
        InstanceOfTimerHandlerManager >= 0) )
  {
    _DbgPrintMessage(1, "Done handling timer handler manager");
    *((_DWORD *)this + 638) = CRemoteConnectionManager::IsAllowNonRDPStack(v36);
    StateTracker<enum CRemoteConnectionManager::TState>::operator=((char *)this + 1248, 0);
    v37 = *v26;
    if ( *v26 )
    {
      v43 = 0x100000000LL;
      CProtocolExMgr::NotifyAllSessions(v37, (struct _TS_STATE_CHANGE *)&v43);
    }
    (*(void (__fastcall **)(CRemoteConnectionManager *))(*(_QWORD *)this + 408LL))(this);
    v38 = CDisplayDevicePnpMonitor::Initialize(*((CDisplayDevicePnpMonitor **)this + 320));
    v8 = v38;
    if ( v38 >= 0 )
    {
      v39 = RDSHTelemetryLogging::Register();
      if ( v39 < 0 && (unsigned int)dword_180128170 > 3 )
      {
        v44[0] = v39;
        v47 = "RDSHTelemetryLogging telemetry service failed to start";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_180128170,
          (unsigned __int8 *)byte_180107169,
          v40,
          v41,
          (const unsigned __int16 **)&v47,
          (__int64)v44);
      }
    }
    else
    {
      _DbgPrintMessage(
        8,
        "m_ptrDisplayDevicePnpMonitor->Initialize failed: 0x%x in %s",
        (unsigned int)v38,
        "CRemoteConnectionManager::Initialize");
    }
  }
  else
  {
    _DbgPrintMessage(
      8,
      "CTSTimerManagerHandler contstructor failed: 0x%x in %s",
      (unsigned int)InstanceOfTimerHandlerManager,
      "CRemoteConnectionManager::Initialize");
  }
LABEL_78:
  if ( v8 < 0 )
    goto LABEL_79;
LABEL_80:
  EtwEventActivityIdControl(2, &v52);
  CAutoLock::Unlock((CAutoLock *)v50);
  CGenericTrace::~CGenericTrace(v53);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v48);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v46);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180046100  mov     [rsp-8+arg_18], rbx
0x180046105  push    rbp
0x180046106  push    rsi
0x180046107  push    rdi
0x180046108  push    r12
0x18004610a  push    r13
0x18004610c  push    r14
0x18004610e  push    r15
0x180046110  lea     rbp, [rsp-27h]
0x180046115  sub     rsp, 0E0h
0x18004611c  mov     rax, cs:__security_cookie
0x180046123  xor     rax, rsp
0x180046126  mov     [rbp+57h+var_38], rax
0x18004612a  mov     r15, r8
0x18004612d  mov     rbx, rdx
0x180046130  mov     [rbp+57h+var_B8], rdx
0x180046134  mov     rsi, rcx
0x180046137  xor     r12d, r12d
0x18004613a  mov     [rbp+57h+var_C0], r12
0x18004613e  mov     [rbp+57h+var_B0], r12
0x180046142  mov     [rsp+110h+var_D8], r12d
0x180046147  add     rcx, 108h; this
0x18004614e  call    ?Refresh@CWPPConfig@@QEAAJXZ; CWPPConfig::Refresh(void)
0x180046153  lea     r13, aCremoteconnect_13; "CRemoteConnectionManager::Initialize"
0x18004615a  mov     r9, r13; char *
0x18004615d  lea     r8, aCremoteconnect_21; "CRemoteConnectionManager Initialize ..."
0x180046164  lea     edx, [r12+10h]; unsigned int
0x180046169  lea     rcx, [rbp+57h+var_70]; this
0x18004616d  call    ??0CGenericTrace@@QEAA@KPEBD0@Z; CGenericTrace::CGenericTrace(ulong,char const *,char const *)
0x180046172  nop
0x180046173  call    ?DebugBreakIfAskedEx@CUtils@@SAXPEAG0@Z; CUtils::DebugBreakIfAskedEx(ushort *,ushort *)
0x180046178  lea     rdx, [rsi+3E8h]; struct CResource *
0x18004617f  lea     rcx, [rbp+57h+var_A0]; this
0x180046183  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180046188  nop
0x180046189  xorps   xmm0, xmm0
0x18004618c  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180046190  mov     edx, 0F4610000h; unsigned int
0x180046195  lea     rcx, [rbp+57h+pguid]; pguid
0x180046199  call    ?GenerateConstrainedGuid@@YAJPEAU_GUID@@K@Z; GenerateConstrainedGuid(_GUID *,ulong)
0x18004619e  mov     edi, eax
0x1800461a0  movaps  xmm0, xmmword ptr [rbp+57h+pguid.Data1]
0x1800461a4  movdqa  [rbp+57h+var_80], xmm0
0x1800461a9  lea     rdx, [rbp+57h+var_80]
0x1800461ad  lea     ecx, [r12+4]
0x1800461b2  call    cs:__imp_EtwEventActivityIdControl
0x1800461b8  nop
0x1800461b9  test    edi, edi
0x1800461bb  jns     short loc_1800461D9
0x1800461bd  mov     r9, r13
0x1800461c0  mov     r8d, edi
0x1800461c3  lea     rdx, aGenerateconstr; "GenerateConstrainedGuid failed: 0x%x in"...
0x1800461ca  mov     ecx, 8; int
0x1800461cf  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800461d4  jmp     loc_180046966
0x1800461d9  cmp     [rsi+9F0h], r12b
0x1800461e0  jz      short loc_180046203
0x1800461e2  mov     edi, 80070426h
0x1800461e7  lea     rdx, aInitializeCall_0; "Initialize() call on service stop start"...
0x1800461ee  mov     r8d, edi
0x1800461f1  mov     r9, r13
0x1800461f4  mov     ecx, 8; int
0x1800461f9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800461fe  jmp     loc_18004696A
0x180046203  mov     edi, 1
0x180046208  cmp     [rsi+4E0h], edi
0x18004620e  jz      short loc_18004621E
0x180046210  mov     edi, 8000FFFFh
0x180046215  lea     rdx, aInitializeCall; "Initialize() call on non-stopped failed"...
0x18004621c  jmp     short loc_1800461EE
0x18004621e  mov     [rsi+0A08h], r12d
0x180046225  lea     rcx, [rsp+110h+var_D8]; int *
0x18004622a  call    ?IsAppServerInstalled@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAppServerInstalled(int *)
0x18004622f  test    eax, eax
0x180046231  js      short loc_180046245
0x180046233  cmp     [rsp+110h+var_D8], edi
0x180046237  jnz     short loc_180046245
0x180046239  mov     [rsi+0A08h], edi
0x18004623f  mov     [rsi+0A0Ch], edi
0x180046245  cmp     [rsi+0A0Ch], r12d
0x18004624c  jz      short loc_180046277
0x18004624e  mov     rcx, rsi; this
0x180046251  call    ?UALStart@CRemoteConnectionManager@@AEAAJXZ; CRemoteConnectionManager::UALStart(void)
0x180046256  test    eax, eax
0x180046258  jns     short loc_180046277
0x18004625a  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 10h; ulong g_DebugTraceComponent
0x180046261  jz      short loc_180046277
0x180046263  mov     r8d, eax
0x180046266  lea     rdx, aUalstartFailed; "UALStart failed (0x%08x). No UAL loggin"...
0x18004626d  mov     ecx, 2; int
0x180046272  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180046277  lea     rdx, [rsi+450h]; struct CResource *
0x18004627e  lea     rcx, [rbp+57h+var_D0]; this
0x180046282  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180046287  nop
0x180046288  mov     [rsp+110h+var_E0], r12
0x18004628d  lea     r14, [rsi+1F0h]
0x180046294  mov     rdx, rbx
0x180046297  mov     rcx, r14
0x18004629a  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x18004629f  mov     rcx, [r14]
0x1800462a2  lea     rbx, [rsi+220h]
0x1800462a9  mov     rax, [rcx]
0x1800462ac  mov     rdx, rbx
0x1800462af  mov     rax, [rax+18h]
0x1800462b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800462b8  mov     edi, eax
0x1800462ba  test    eax, eax
0x1800462bc  jns     short loc_1800462F0
0x1800462be  mov     r9, r13
0x1800462c1  mov     r8d, eax
0x1800462c4  lea     rdx, aGetsessionlist_0; "GetSessionList failed: 0x%x in %s"
0x1800462cb  mov     ecx, 8; int
0x1800462d0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800462d5  nop
0x1800462d6  lea     rcx, [rsp+110h+var_E0]; void *
0x1800462db  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800462e0  nop
0x1800462e1  lea     rcx, [rbp+57h+var_D0]; this
0x1800462e5  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800462ea  nop
0x1800462eb  jmp     loc_180046966
0x1800462f0  mov     rcx, [rbx]
0x1800462f3  lea     rdx, [rsi+228h]
0x1800462fa  mov     rax, [rcx]
0x1800462fd  mov     rax, [rax+20h]
0x180046301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046306  mov     edi, eax
0x180046308  test    eax, eax
0x18004630a  jns     short loc_18004633E
0x18004630c  mov     r9, r13
0x18004630f  mov     r8d, eax
0x180046312  lea     rdx, aGetinstanceofe_2; "GetInstanceOfEnum failed: 0x%x in %s"
0x180046319  mov     ecx, 8; int
0x18004631e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180046323  nop
0x180046324  lea     rcx, [rsp+110h+var_E0]; void *
0x180046329  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18004632e  nop
0x18004632f  lea     rcx, [rbp+57h+var_D0]; this
0x180046333  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180046338  nop
0x180046339  jmp     loc_180046966
0x18004633e  lea     rcx, [rsi+218h]; struct IConnectionDispatchManager **
0x180046345  call    ?GetInstanceOfConnectionDispatchManager@IConnectionDispatchManager@@SAJPEAPEAV1@@Z; IConnectionDispatchManager::GetInstanceOfConnectionDispatchManager(IConnectionDispatchManager * *)
0x18004634a  mov     edi, eax
0x18004634c  test    eax, eax
0x18004634e  jns     short loc_180046382
0x180046350  mov     r9, r13
0x180046353  mov     r8d, eax
0x180046356  lea     rdx, aGetinstanceofc_1; "GetInstanceOfConnectionDispatchManager "...
0x18004635d  mov     ecx, 8; int
0x180046362  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180046367  nop
0x180046368  lea     rcx, [rsp+110h+var_E0]; void *
0x18004636d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180046372  nop
0x180046373  lea     rcx, [rbp+57h+var_D0]; this
0x180046377  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18004637c  nop
0x18004637d  jmp     loc_180046966
0x180046382  lea     r12, [rsi+1F8h]
0x180046389  mov     rcx, r12; struct IEnforcementCore **
0x18004638c  call    ?GetInstanceOfEnforcementCore@IEnforcementCore@@SAJPEAPEAV1@@Z; IEnforcementCore::GetInstanceOfEnforcementCore(IEnforcementCore * *)
0x180046391  mov     edi, eax
0x180046393  test    eax, eax
0x180046395  jns     short loc_1800463C9
0x180046397  mov     r9, r13
0x18004639a  mov     r8d, eax
0x18004639d  lea     rdx, aIenforcementco; "IEnforcementCore::GetInstanceOfEnforcem"...
0x1800463a4  mov     ecx, 8; int
0x1800463a9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800463ae  nop
0x1800463af  lea     rcx, [rsp+110h+var_E0]; void *
0x1800463b4  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800463b9  nop
0x1800463ba  lea     rcx, [rbp+57h+var_D0]; this
0x1800463be  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800463c3  nop
0x1800463c4  jmp     loc_180046966
0x1800463c9  lea     r13, [rsi+4D0h]
0x1800463d0  mov     rdx, r13; struct IExternalEventDispatcher **
0x1800463d3  mov     rcx, r15; struct ITSEventDispatcher *
0x1800463d6  call    ?GetInstanceOf@IExternalEventDispatcher@@SAJPEAUITSEventDispatcher@@PEAPEAV1@@Z; IExternalEventDispatcher::GetInstanceOf(ITSEventDispatcher *,IExternalEventDispatcher * *)
0x1800463db  mov     edi, eax
0x1800463dd  test    eax, eax
0x1800463df  jns     short loc_180046417
0x1800463e1  lea     r9, aCremoteconnect_13; "CRemoteConnectionManager::Initialize"
0x1800463e8  mov     r8d, eax
0x1800463eb  lea     rdx, aIexternalevent; "IExternalEventDispatcher::GetInstanceOf"...
0x1800463f2  mov     ecx, 8; int
0x1800463f7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800463fc  nop
0x1800463fd  lea     rcx, [rsp+110h+var_E0]; void *
0x180046402  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180046407  nop
0x180046408  lea     rcx, [rbp+57h+var_D0]; this
0x18004640c  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180046411  nop
0x180046412  jmp     loc_180046966
0x180046417  lea     rcx, [rsi+4D8h]; struct CTerminalSupportManager **
0x18004641e  call    ?GetInstanceofTerminalPreferenceManager@CTerminalSupportManager@@SAJPEAPEAV1@@Z; CTerminalSupportManager::GetInstanceofTerminalPreferenceManager(CTerminalSupportManager * *)
0x180046423  mov     edi, eax
0x180046425  test    eax, eax
0x180046427  jns     short loc_18004645F
0x180046429  lea     r9, aCremoteconnect_13; "CRemoteConnectionManager::Initialize"
0x180046430  mov     r8d, eax
0x180046433  lea     rdx, aGetinstanceoft_0; "GetInstanceofTerminalPreferenceManager "...
0x18004643a  mov     ecx, 8; int
0x18004643f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180046444  nop
0x180046445  lea     rcx, [rsp+110h+var_E0]; void *
0x18004644a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18004644f  nop
0x180046450  lea     rcx, [rbp+57h+var_D0]; this
0x180046454  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180046459  nop
0x18004645a  jmp     loc_180046966
0x18004645f  lea     r15, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180046466  mov     rdx, r15; struct std::nothrow_t *
0x180046469  mov     ecx, 6B0h; unsigned __int64
0x18004646e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180046473  mov     rdi, rax
0x180046476  mov     qword ptr [rsp+110h+var_D8], rax
0x18004647b  test    rax, rax
0x18004647e  jz      short loc_1800464BB
0x180046480  lea     rdx, aCremoteconnect_16; "CRemoteConnectionManagerSink"
0x180046487  mov     rcx, rax; this
0x18004648a  call    ??0CDefTSNotifySink@@QEAA@PEBD@Z; CDefTSNotifySink::CDefTSNotifySink(char const *)
0x18004648f  lea     rax, ??_7CRemoteConnectionManagerSink@CRemoteConnectionManager@@6B@; const CRemoteConnectionManager::CRemoteConnectionManagerSink::`vftable'
0x180046496  mov     [rdi], rax
0x180046499  mov     qword ptr [rdi+638h], 0
0x1800464a4  mov     qword ptr [rdi+640h], 0
0x1800464af  mov     dword ptr [rdi+6A8h], 0
0x1800464b9  jmp     short loc_1800464BD
0x1800464bb  xor     edi, edi
0x1800464bd  lea     rbx, [rsi+1E0h]
0x1800464c4  mov     rdx, rdi
0x1800464c7  mov     rcx, rbx
0x1800464ca  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x1800464cf  mov     rcx, [rbx]; this
0x1800464d2  test    rcx, rcx
0x1800464d5  jnz     short loc_180046516
0x1800464d7  mov     r14d, 8007000Eh
0x1800464dd  mov     edi, r14d
0x1800464e0  lea     r9, aCremoteconnect_13; "CRemoteConnectionManager::Initialize"
0x1800464e7  mov     r8d, r14d
0x1800464ea  lea     rdx, aNewCremoteconn; "new CRemoteConnectionManagerSink() fail"...
0x1800464f1  mov     ecx, 8; int
0x1800464f6  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800464fb  nop
0x1800464fc  lea     rcx, [rsp+110h+var_E0]; void *
0x180046501  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180046506  nop
0x180046507  lea     rcx, [rbp+57h+var_D0]; this
0x18004650b  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180046510  nop
0x180046511  jmp     loc_18004696A
0x180046516  mov     rdx, rsi; struct CRemoteConnectionManager *
0x180046519  call    ?Initialize@CRemoteConnectionManagerSink@CRemoteConnectionManager@@QEAAJPEAV2@@Z; CRemoteConnectionManager::CRemoteConnectionManagerSink::Initialize(CRemoteConnectionManager *)
0x18004651e  mov     edi, eax
0x180046520  test    eax, eax
0x180046522  jns     short loc_18004655A
0x180046524  lea     r9, aCremoteconnect_13; "CRemoteConnectionManager::Initialize"
0x18004652b  mov     r8d, eax
0x18004652e  lea     rdx, aThisPtrrcmsink; "this->ptrRCMSink->Initialize failed: 0x"...
0x180046535  mov     ecx, 8; int
0x18004653a  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004653f  nop
0x180046540  lea     rcx, [rsp+110h+var_E0]; void *
0x180046545  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18004654a  nop
0x18004654b  lea     rcx, [rbp+57h+var_D0]; this
0x18004654f  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180046554  nop
0x180046555  jmp     loc_180046966
0x18004655a  mov     rdx, r15; struct std::nothrow_t *
0x18004655d  mov     ecx, 6C8h; unsigned __int64
0x180046562  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180046567  mov     qword ptr [rsp+110h+var_D8], rax
0x18004656c  test    rax, rax
0x18004656f  jz      short loc_18004657A
0x180046571  mov     rcx, rax; this
0x180046574  call    ??0CWsxMgr@@QEAA@XZ; CWsxMgr::CWsxMgr(void)
0x180046579  nop
0x18004657a  mov     rdx, rax
0x18004657d  lea     rcx, [rsi+48h]
0x180046581  call    ??4?$SmartPtr@UITerminal@@@@QEAAAEAV0@PEAUITerminal@@@Z; SmartPtr<ITerminal>::operator=(ITerminal *)
0x180046586  mov     rcx, [rsi+48h]; this
0x18004658a  test    rcx, rcx
0x18004658d  jnz     short loc_1800465CE
0x18004658f  mov     r14d, 8007000Eh
0x180046595  mov     edi, r14d
0x180046598  lea     r9, aCremoteconnect_13; "CRemoteConnectionManager::Initialize"
0x18004659f  mov     r8d, r14d
0x1800465a2  lea     rdx, aNewCwsxmgrFail; "new CWsxMgr() failed: 0x%x in %s"
0x1800465a9  mov     ecx, 8; int
0x1800465ae  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800465b3  nop
0x1800465b4  lea     rcx, [rsp+110h+var_E0]; void *
  ... truncated ...
```
