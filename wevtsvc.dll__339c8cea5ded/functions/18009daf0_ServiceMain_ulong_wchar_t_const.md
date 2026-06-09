# ServiceMain(ulong,wchar_t const * *)

- ea: `0x18009daf0`
- end: `0x18009e30c`
- name: `?ServiceMain@@YAXKPEAPEB_W@Z`
- size: `2076`
- prototype: `void __fastcall(__int64, const wchar_t **)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x180001008`
- `0x18000104c`
- `0x180006770`
- `0x180017b98`
- `0x180033ae0`
- `0x18005ff90`
- `0x180064854`
- `0x1800660ac`
- `0x18006c144`
- `0x18007bae4`
- `0x180080d50`
- `0x1800813a4`
- `0x180092008`
- `0x180092ee4`
- `0x18009aee0`
- `0x18009d1bc`
- `0x18009daf0`
- `0x18009e314`
- `0x1800a4d68`
- `0x1800dd010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009de76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009de76`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18009dc85`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18009dc85`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18009e17b`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18009e17b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009dd80`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18009dd80`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009dc21`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18009dc21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ddb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009deff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e1a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009dc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009ddb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009deff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e1a4`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18009dda2`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18009dda2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009def5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009dfb9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e0a8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e169`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009def5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009dfb9`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e0a8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18009e169`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceMain(__int64 a1, const wchar_t **a2)
{
  _DWORD *v2; // r9
  PVOID *v3; // rcx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  _QWORD *v8; // rcx
  struct _TP_CLEANUP_GROUP *ThreadpoolCleanupGroup; // rax
  DWORD v10; // eax
  DWORD v11; // r12d
  DWORD v12; // eax
  DWORD v13; // r12d
  HKEY *phkResult; // rax
  __int64 v15; // r8
  DWORD v16; // eax
  DWORD v17; // r12d
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  DWORD v20; // eax
  DWORD started; // r12d
  DWORD v22; // eax
  unsigned int v23; // eax
  DWORD v24; // [rsp+40h] [rbp-A8h] BYREF
  unsigned int v25; // [rsp+44h] [rbp-A4h] BYREF
  HKEY v26; // [rsp+48h] [rbp-A0h] BYREF
  RTL_SRWLOCK *v27; // [rsp+50h] [rbp-98h] BYREF
  char v28; // [rsp+58h] [rbp-90h]
  _BYTE v29[28]; // [rsp+68h] [rbp-80h] BYREF
  int v30; // [rsp+88h] [rbp-60h] BYREF
  char v31; // [rsp+8Ch] [rbp-5Ch]
  _BYTE v32[16]; // [rsp+90h] [rbp-58h] BYREF
  _DWORD v33[4]; // [rsp+A0h] [rbp-48h] BYREF

  v30 = 0;
  v31 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(&v30);
  if ( (unsigned int)dword_18010F008 > 5 )
  {
    if ( v31 && (v33[0] || v33[1] || v33[2] || v33[3]) )
      v2 = v33;
    else
      v2 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18010F008,
      &dword_1800FBF5C,
      v32,
      v2);
  }
  v3 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
    v3 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !qword_180111728 )
  {
    if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 8) != 0 )
    {
      if ( *((_BYTE *)v3 + 25) )
        WPP_SF_(v3[2], 66, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
    }
    goto LABEL_83;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hEvent, EventW);
  if ( (unsigned __int64)hEvent + 1 <= 1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_83;
    }
    LastError = GetLastError();
    v6 = 67;
    v7 = LastError;
    v8 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  ThreadpoolCleanupGroup = CreateThreadpoolCleanupGroup();
  ptpcg = ThreadpoolCleanupGroup;
  if ( !ThreadpoolCleanupGroup )
  {
    v10 = GetLastError();
    v11 = v10;
    v30 = 2;
    if ( (unsigned int)dword_18010F008 > 5 )
    {
      v24 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18010F008,
        (unsigned int)byte_1800FBFAB,
        (unsigned int)v32,
        0,
        (__int64)&v24);
    }
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_83;
    }
    v6 = 68;
    v7 = v11;
LABEL_31:
    WPP_SF_d(v8[2], v6, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v7);
LABEL_83:
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v30);
    return;
  }
  g_rpcRundownCallbackEnvironment.Version = 3;
  g_rpcRundownCallbackEnvironment.Pool = 0;
  *(_OWORD *)&g_rpcRundownCallbackEnvironment.RaceDll = 0;
  g_rpcRundownCallbackEnvironment.FinalizationCallback = 0;
  g_rpcRundownCallbackEnvironment.u.Flags = 0;
  g_rpcRundownCallbackEnvironment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  g_rpcRundownCallbackEnvironment.Size = 72;
  g_rpcRundownCallbackEnvironment.CleanupGroup = ThreadpoolCleanupGroup;
  g_rpcRundownCallbackEnvironment.CleanupGroupCancelCallback = 0;
  v27 = &stru_1801119A8;
  AcquireSRWLockExclusive(&stru_1801119A8);
  v28 = 1;
  byte_180111704 = 0;
  g_serviceControl = RegisterServiceCtrlHandlerExW(L"eventlog", HandlerProc, 0);
  if ( !g_serviceControl )
  {
    v12 = GetLastError();
    v13 = v12;
    v30 = 2;
    if ( (unsigned int)dword_18010F008 > 5 )
    {
      v24 = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18010F008,
        (unsigned int)qword_1800FBE70,
        (unsigned int)v32,
        0,
        (__int64)&v24);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v13);
    }
    goto LABEL_82;
  }
  v25 = 0;
  v26 = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v26);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Control\\Lsa", 0, 1u, phkResult) )
    RegReadDWORDValueNoThrow(v26, &pszFormat, L"crashonauditfail", &v25);
  memset(v29, 0, sizeof(v29));
  *(_OWORD *)&ServiceStatus.dwWin32ExitCode = 0;
  ServiceStatus.dwCurrentState = 2;
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwControlsAccepted = (v25 != 1) + 4;
  if ( !SetServiceStatus(g_serviceControl, &ServiceStatus) )
  {
    v16 = GetLastError();
    v17 = v16;
    v30 = 2;
    if ( (unsigned int)dword_18010F008 > 5 )
    {
      v24 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18010F008,
        (unsigned int)&dword_1800FBF34,
        (unsigned int)v32,
        0,
        (__int64)&v24);
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_81;
    }
    v19 = 70;
LABEL_55:
    WPP_SF_d(v18[2], v19, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v17);
LABEL_81:
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v26);
LABEL_82:
    utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v27);
    goto LABEL_83;
  }
  LOBYTE(v15) = v25 != 0;
  v20 = EventService::InitializeGlobals(hModule, &v30, v15);
  v17 = v20;
  if ( v20 )
  {
    ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwWin32ExitCode = v20;
    SetServiceStatus(g_serviceControl, &ServiceStatus);
    v30 = 2;
    if ( (unsigned int)dword_18010F008 > 5 )
    {
      v24 = v17;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18010F008,
        (unsigned int)byte_1800FC003,
        (unsigned int)v32,
        0,
        (__int64)&v24);
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      goto LABEL_81;
    }
    v19 = 71;
    goto LABEL_55;
  }
  LegacyEventlogInit1(&v30);
  EventService::Start(g_service);
  LegacyEventlogInit2(&v30);
  started = InitializeAndStartLocalRpcEndpoints(&v30);
  if ( started )
  {
    Shutdown();
    ServiceStatus.dwCurrentState = 1;
    ServiceStatus.dwWin32ExitCode = started;
    SetServiceStatus(g_serviceControl, &ServiceStatus);
    v30 = 2;
    if ( (unsigned int)dword_18010F008 > 5 )
    {
      v24 = started;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18010F008,
        (unsigned int)&dword_1800FBEEC,
        (unsigned int)v32,
        0,
        (__int64)&v24);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, started);
    }
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v26);
    utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v27);
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v30);
  }
  else
  {
    ServiceStatus.dwControlsAccepted |= 0x200u;
    ServiceStatus.dwCurrentState = 4;
    SetServiceStatus(g_serviceControl, &ServiceStatus);
    if ( !TrySubmitThreadpoolCallback(InitializeAndStartTpcIpRpcEndpoint, 0, 0)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v22 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v22);
    }
    v23 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, HANDLE, __int64 (__fastcall *)(), _QWORD, int))(qword_180111728 + 208))(
            &qword_1801116A8,
            L"eventlog",
            hEvent,
            SvchostShutdownCallback,
            0,
            24);
    if ( !v23 )
    {
      v30 = 2;
      if ( (unsigned int)dword_18010F008 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          &dword_18010F008,
          byte_1800FBE21,
          v32,
          0);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids);
      }
      goto LABEL_81;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids, v23);
    }
    Shutdown();
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v26);
    utl::unique_lock<utl::shared_mutex>::~unique_lock<utl::shared_mutex>(&v27);
    TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>::~TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>(&v30);
  }
}

```

## disassembly

```asm
0x18009daf0  mov     r11, rsp
0x18009daf3  push    rbx
0x18009daf4  push    r12
0x18009daf6  push    r13
0x18009daf8  push    r14
0x18009dafa  push    r15
0x18009dafc  sub     rsp, 0C0h
0x18009db03  mov     rax, cs:__security_cookie
0x18009db0a  xor     rax, rsp
0x18009db0d  mov     [rsp+0E8h+var_38], rax
0x18009db15  xor     r13d, r13d
0x18009db18  mov     [r11-60h], r13d
0x18009db1c  mov     [r11-5Ch], r13b
0x18009db20  lea     rcx, [r11-60h]
0x18009db24  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0A@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider>,0,5>::zInternalStart(void)
0x18009db29  mov     eax, cs:dword_18010F008
0x18009db2f  cmp     eax, 5
0x18009db32  jbe     short loc_18009DB93
0x18009db34  cmp     [rsp+0E8h+var_5C], r13b
0x18009db3c  jz      short loc_18009DB70
0x18009db3e  cmp     [rsp+0E8h+var_48], r13d
0x18009db46  jnz     short loc_18009DB66
0x18009db48  cmp     [rsp+0E8h+var_44], r13d
0x18009db50  jnz     short loc_18009DB66
0x18009db52  cmp     [rsp+0E8h+var_40], r13d
0x18009db5a  jnz     short loc_18009DB66
0x18009db5c  cmp     [rsp+0E8h+var_3C], r13d
0x18009db64  jz      short loc_18009DB70
0x18009db66  lea     r9, [rsp+0E8h+var_48]
0x18009db6e  jmp     short loc_18009DB73
0x18009db70  mov     r9, r13
0x18009db73  lea     r8, [rsp+0E8h+var_58]
0x18009db7b  lea     rdx, dword_1800FBF5C
0x18009db82  lea     r15, dword_18010F008
0x18009db89  mov     rcx, r15
0x18009db8c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18009db91  jmp     short loc_18009DB9A
0x18009db93  lea     r15, dword_18010F008
0x18009db9a  lea     r14, WPP_GLOBAL_Control
0x18009dba1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dba8  cmp     rcx, r14
0x18009dbab  jz      short loc_18009DBD5
0x18009dbad  test    byte ptr [rcx+1Ch], 8
0x18009dbb1  jz      short loc_18009DBD5
0x18009dbb3  cmp     byte ptr [rcx+19h], 4
0x18009dbb7  jb      short loc_18009DBD5
0x18009dbb9  mov     edx, 41h ; 'A'
0x18009dbbe  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009dbc5  mov     rcx, [rcx+10h]
0x18009dbc9  call    WPP_SF_
0x18009dbce  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dbd5  cmp     cs:qword_180111728, r13
0x18009dbdc  jnz     short loc_18009DC17
0x18009dbde  cmp     rcx, r14
0x18009dbe1  jz      loc_18009E2DE
0x18009dbe7  test    byte ptr [rcx+1Ch], 8
0x18009dbeb  jz      loc_18009E2DE
0x18009dbf1  mov     ebx, 1
0x18009dbf6  cmp     [rcx+19h], bl
0x18009dbf9  jb      loc_18009E2DE
0x18009dbff  lea     edx, [rbx+41h]
0x18009dc02  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009dc09  mov     rcx, [rcx+10h]
0x18009dc0d  call    WPP_SF_
0x18009dc12  jmp     loc_18009E2DE
0x18009dc17  xor     r9d, r9d; lpName
0x18009dc1a  xor     r8d, r8d; bInitialState
0x18009dc1d  xor     edx, edx; bManualReset
0x18009dc1f  xor     ecx, ecx; lpEventAttributes
0x18009dc21  call    cs:__imp_CreateEventW
0x18009dc27  mov     rdx, rax
0x18009dc2a  lea     rcx, hEvent
0x18009dc31  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18009dc36  mov     rax, cs:hEvent
0x18009dc3d  inc     rax
0x18009dc40  mov     ebx, 1
0x18009dc45  cmp     rax, rbx
0x18009dc48  ja      short loc_18009DC85
0x18009dc4a  mov     rax, cs:WPP_GLOBAL_Control
0x18009dc51  cmp     rax, r14
0x18009dc54  jz      loc_18009E2DE
0x18009dc5a  test    byte ptr [rax+1Ch], 8
0x18009dc5e  jz      loc_18009E2DE
0x18009dc64  cmp     [rax+19h], bl
0x18009dc67  jb      loc_18009E2DE
0x18009dc6d  call    cs:__imp_GetLastError
0x18009dc73  lea     edx, [rbx+42h]
0x18009dc76  mov     r9d, eax
0x18009dc79  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dc80  jmp     loc_18009DD17
0x18009dc85  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18009dc8b  mov     cs:ptpcg, rax
0x18009dc92  test    rax, rax
0x18009dc95  jnz     loc_18009DD2C
0x18009dc9b  call    cs:__imp_GetLastError
0x18009dca1  mov     r12d, eax
0x18009dca4  mov     r14d, 2
0x18009dcaa  mov     [rsp+0E8h+var_60], r14d
0x18009dcb2  mov     edx, cs:dword_18010F008
0x18009dcb8  cmp     edx, 5
0x18009dcbb  jbe     short loc_18009DCE5
0x18009dcbd  mov     [rsp+0E8h+var_A8], eax
0x18009dcc1  lea     rax, [rsp+0E8h+var_A8]
0x18009dcc6  mov     [rsp+0E8h+phkResult], rax
0x18009dccb  xor     r9d, r9d
0x18009dcce  lea     r8, [rsp+0E8h+var_58]
0x18009dcd6  lea     rdx, byte_1800FBFAB
0x18009dcdd  mov     rcx, r15
0x18009dce0  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009dce5  mov     rcx, cs:WPP_GLOBAL_Control
0x18009dcec  lea     rax, WPP_GLOBAL_Control
0x18009dcf3  cmp     rcx, rax
0x18009dcf6  jz      loc_18009E2DE
0x18009dcfc  test    byte ptr [rcx+1Ch], 8
0x18009dd00  jz      loc_18009E2DE
0x18009dd06  cmp     [rcx+19h], bl
0x18009dd09  jb      loc_18009E2DE
0x18009dd0f  mov     edx, 44h ; 'D'
0x18009dd14  mov     r9d, r12d
0x18009dd17  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009dd1e  mov     rcx, [rcx+10h]
0x18009dd22  call    WPP_SF_d
0x18009dd27  jmp     loc_18009E2DE
0x18009dd2c  mov     cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd36  mov     cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, r13; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd3d  xorps   xmm0, xmm0
0x18009dd40  movdqa  xmmword ptr cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd48  mov     cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, r13; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd4f  mov     dword ptr cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, r13d; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd56  mov     cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, ebx; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd5c  mov     cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd66  mov     cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rax; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd6d  mov     cs:?g_rpcRundownCallbackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, r13; _TP_CALLBACK_ENVIRON_V3 g_rpcRundownCallbackEnvironment ...
0x18009dd74  lea     rcx, stru_1801119A8; SRWLock
0x18009dd7b  mov     [rsp+0E8h+var_98], rcx
0x18009dd80  call    cs:__imp_AcquireSRWLockExclusive
0x18009dd86  mov     [rsp+0E8h+var_90], bl
0x18009dd8a  mov     cs:byte_180111704, r13b
0x18009dd91  xor     r8d, r8d; lpContext
0x18009dd94  lea     rdx, HandlerProc; lpHandlerProc
0x18009dd9b  lea     rcx, ServiceName; "eventlog"
0x18009dda2  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18009dda8  mov     cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_serviceControl
0x18009ddaf  test    rax, rax
0x18009ddb2  jnz     loc_18009DE49
0x18009ddb8  call    cs:__imp_GetLastError
0x18009ddbe  mov     r12d, eax
0x18009ddc1  mov     r14d, 2
0x18009ddc7  mov     [rsp+0E8h+var_60], r14d
0x18009ddcf  mov     ecx, cs:dword_18010F008
0x18009ddd5  cmp     ecx, 5
0x18009ddd8  jbe     short loc_18009DE02
0x18009ddda  mov     [rsp+0E8h+var_A8], eax
0x18009ddde  lea     rax, [rsp+0E8h+var_A8]
0x18009dde3  mov     [rsp+0E8h+phkResult], rax
0x18009dde8  xor     r9d, r9d
0x18009ddeb  lea     r8, [rsp+0E8h+var_58]
0x18009ddf3  lea     rdx, qword_1800FBE70
0x18009ddfa  mov     rcx, r15
0x18009ddfd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009de02  mov     rcx, cs:WPP_GLOBAL_Control
0x18009de09  lea     rax, WPP_GLOBAL_Control
0x18009de10  cmp     rcx, rax
0x18009de13  jz      loc_18009E2D3
0x18009de19  test    byte ptr [rcx+1Ch], 8
0x18009de1d  jz      loc_18009E2D3
0x18009de23  cmp     [rcx+19h], bl
0x18009de26  jb      loc_18009E2D3
0x18009de2c  mov     edx, 45h ; 'E'
0x18009de31  mov     r9d, r12d
0x18009de34  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009de3b  mov     rcx, [rcx+10h]
0x18009de3f  call    WPP_SF_d
0x18009de44  jmp     loc_18009E2D3
0x18009de49  mov     [rsp+0E8h+var_A4], r13d
0x18009de4e  mov     [rsp+0E8h+var_A0], r13
0x18009de53  lea     rcx, [rsp+0E8h+var_A0]
0x18009de58  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18009de5d  mov     [rsp+0E8h+phkResult], rax; phkResult
0x18009de62  mov     r9d, ebx; samDesired
0x18009de65  xor     r8d, r8d; ulOptions
0x18009de68  lea     rdx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Control\\Lsa"
0x18009de6f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009de76  call    cs:__imp_RegOpenKeyExW
0x18009de7c  test    eax, eax
0x18009de7e  jnz     short loc_18009DE9D
0x18009de80  lea     r9, [rsp+0E8h+var_A4]; unsigned int *
0x18009de85  lea     r8, aCrashonauditfa; "crashonauditfail"
0x18009de8c  lea     rdx, pszFormat; wchar_t *
0x18009de93  mov     rcx, [rsp+0E8h+var_A0]; HKEY
0x18009de98  call    ?RegReadDWORDValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAK@Z; RegReadDWORDValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,ulong &)
0x18009de9d  xorps   xmm1, xmm1
0x18009dea0  movups  xmmword ptr [rsp+0E8h+var_80], xmm1
0x18009dea5  movups  xmmword ptr [rsp+0E8h+var_80+0Ch], xmm1
0x18009deaa  movups  xmm0, xmmword ptr [rsp+0E8h+var_80]
0x18009deaf  movups  xmmword ptr cs:ServiceStatus.dwServiceType, xmm0
0x18009deb6  movups  xmmword ptr cs:ServiceStatus.dwWin32ExitCode, xmm1
0x18009debd  mov     r14d, 2
0x18009dec3  mov     cs:ServiceStatus.dwCurrentState, r14d
0x18009deca  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x18009ded4  mov     eax, r13d
0x18009ded7  cmp     [rsp+0E8h+var_A4], ebx
0x18009dedb  setnz   al
0x18009dede  add     eax, 4
0x18009dee1  mov     cs:ServiceStatus.dwControlsAccepted, eax
0x18009dee7  lea     rdx, ServiceStatus; lpServiceStatus
0x18009deee  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18009def5  call    cs:__imp_SetServiceStatus
0x18009defb  test    eax, eax
0x18009defd  jnz     short loc_18009DF77
0x18009deff  call    cs:__imp_GetLastError
0x18009df05  mov     r12d, eax
0x18009df08  mov     [rsp+0E8h+var_60], r14d
0x18009df10  mov     ecx, cs:dword_18010F008
0x18009df16  cmp     ecx, 5
0x18009df19  jbe     short loc_18009DF43
0x18009df1b  mov     [rsp+0E8h+var_A8], eax
0x18009df1f  lea     rax, [rsp+0E8h+var_A8]
0x18009df24  mov     [rsp+0E8h+phkResult], rax
0x18009df29  xor     r9d, r9d
0x18009df2c  lea     r8, [rsp+0E8h+var_58]
0x18009df34  lea     rdx, dword_1800FBF34
0x18009df3b  mov     rcx, r15
0x18009df3e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009df43  mov     rcx, cs:WPP_GLOBAL_Control
0x18009df4a  lea     rax, WPP_GLOBAL_Control
0x18009df51  cmp     rcx, rax
0x18009df54  jz      loc_18009E2C8
0x18009df5a  test    byte ptr [rcx+1Ch], 8
0x18009df5e  jz      loc_18009E2C8
0x18009df64  cmp     [rcx+19h], bl
0x18009df67  jb      loc_18009E2C8
0x18009df6d  mov     edx, 46h ; 'F'
0x18009df72  jmp     loc_18009E02A
0x18009df77  cmp     [rsp+0E8h+var_A4], r13d
0x18009df7c  setnz   r8b
0x18009df80  lea     rdx, [rsp+0E8h+var_60]
0x18009df88  mov     rcx, cs:hModule
0x18009df8f  call    ?InitializeGlobals@EventService@@SAKPEAUHINSTANCE__@@AEAV?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@_N@Z; EventService::InitializeGlobals(HINSTANCE__ *,TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider> &,bool)
0x18009df94  mov     r12d, eax
0x18009df97  test    eax, eax
0x18009df99  jz      loc_18009E042
0x18009df9f  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18009dfa5  mov     cs:ServiceStatus.dwWin32ExitCode, eax
0x18009dfab  lea     rdx, ServiceStatus; lpServiceStatus
0x18009dfb2  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18009dfb9  call    cs:__imp_SetServiceStatus
0x18009dfbf  mov     [rsp+0E8h+var_60], r14d
0x18009dfc7  mov     ecx, cs:dword_18010F008
0x18009dfcd  cmp     ecx, 5
0x18009dfd0  jbe     short loc_18009DFFB
0x18009dfd2  mov     [rsp+0E8h+var_A8], r12d
0x18009dfd7  lea     rax, [rsp+0E8h+var_A8]
0x18009dfdc  mov     [rsp+0E8h+phkResult], rax
0x18009dfe1  xor     r9d, r9d
0x18009dfe4  lea     r8, [rsp+0E8h+var_58]
0x18009dfec  lea     rdx, byte_1800FC003
0x18009dff3  mov     rcx, r15
0x18009dff6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18009dffb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009e002  lea     rax, WPP_GLOBAL_Control
0x18009e009  cmp     rcx, rax
0x18009e00c  jz      loc_18009E2C8
0x18009e012  test    byte ptr [rcx+1Ch], 8
0x18009e016  jz      loc_18009E2C8
0x18009e01c  cmp     [rcx+19h], bl
0x18009e01f  jb      loc_18009E2C8
0x18009e025  mov     edx, 47h ; 'G'
0x18009e02a  mov     r9d, r12d
0x18009e02d  lea     r8, WPP_c81622dadc0b34ee49a8cc9df4a5609a_Traceguids
0x18009e034  mov     rcx, [rcx+10h]
0x18009e038  call    WPP_SF_d
0x18009e03d  jmp     loc_18009E2C8
0x18009e042  lea     rcx, [rsp+0E8h+var_60]
0x18009e04a  call    ?LegacyEventlogInit1@@YAXAEAV?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z; LegacyEventlogInit1(TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider> &)
0x18009e04f  lea     rdx, [rsp+0E8h+var_60]
0x18009e057  mov     rcx, cs:?g_service@@3PEAVEventService@@EA; SRWLock
0x18009e05e  call    ?Start@EventService@@QEAAXAEAV?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z; EventService::Start(TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider> &)
0x18009e063  lea     rcx, [rsp+0E8h+var_60]
0x18009e06b  call    ?LegacyEventlogInit2@@YAXAEAV?$TraceLoggingActivity@$1?g_hEventLogRpcActivityProvider@@3QEBU_tlgProvider_t@@EB$0A@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z; LegacyEventlogInit2(TraceLoggingActivity<&_tlgProvider_t const * const g_hEventLogRpcActivityProvider,0,5,_TlgReflectorTag_Param0IsHProvider> &)
0x18009e070  lea     rcx, [rsp+0E8h+var_60]
0x18009e078  call    InitializeAndStartLocalRpcEndpoints
0x18009e07d  mov     r12d, eax
0x18009e080  test    eax, eax
0x18009e082  jz      loc_18009E149
0x18009e088  call    ?Shutdown@@YAXAEAV?$unique_lock@Vmutex@utl@@@utl@@@Z; Shutdown(utl::unique_lock<utl::mutex> &)
0x18009e08d  mov     cs:ServiceStatus.dwCurrentState, ebx
0x18009e093  mov     cs:ServiceStatus.dwWin32ExitCode, r12d
0x18009e09a  lea     rdx, ServiceStatus; lpServiceStatus
0x18009e0a1  mov     rcx, cs:?g_serviceControl@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18009e0a8  call    cs:__imp_SetServiceStatus
0x18009e0ae  mov     [rsp+0E8h+var_60], r14d
0x18009e0b6  mov     ecx, cs:dword_18010F008
0x18009e0bc  cmp     ecx, 5
0x18009e0bf  jbe     short loc_18009E0EA
0x18009e0c1  mov     [rsp+0E8h+var_A8], r12d
0x18009e0c6  lea     rax, [rsp+0E8h+var_A8]
0x18009e0cb  mov     [rsp+0E8h+phkResult], rax
0x18009e0d0  xor     r9d, r9d
0x18009e0d3  lea     r8, [rsp+0E8h+var_58]
  ... truncated ...
```
