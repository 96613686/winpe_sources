# CRemoteTerminal::DoConnect(_TERMINAL_CONNECTMSG *,ITSSession *,unsigned __int64,ulong)

- ea: `0x180050530`
- end: `0x180051146`
- name: `?DoConnect@CRemoteTerminal@@UEAAJPEAU_TERMINAL_CONNECTMSG@@PEAUITSSession@@_KK@Z`
- size: `3094`
- prototype: `__int64 __fastcall(CRemoteTerminal *this, struct _TERMINAL_CONNECTMSG *, struct ITSSession *, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001688`
- `0x180002788`
- `0x180009ee0`
- `0x18000a210`
- `0x18000c2f0`
- `0x180011f80`
- `0x180012480`
- `0x1800127b0`
- `0x1800130d8`
- `0x180013150`
- `0x1800135e0`
- `0x180014814`
- `0x1800148f0`
- `0x1800152a4`
- `0x180015ab0`
- `0x180027d04`
- `0x1800321f0`
- `0x18003d79c`
- `0x18003e644`
- `0x18004fe3c`
- `0x180050298`
- `0x180050530`
- `0x18005347c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050e03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005084f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005084f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180051045`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005108f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005109e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005108f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005109e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800510e9`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180050df5`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x180050df5`

## string_xrefs

- `0x1800505e1`: `Terminal is already terminated`
- `0x1800509fa`: `Terminal is already terminated`
- `0x180050631`: `InitCommonSessionData failed: 0x%x in %s`
- `0x1800509c0`: `GetTerminalChannels completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteTerminal::DoConnect(
        CRemoteTerminal *this,
        struct _TERMINAL_CONNECTMSG *a2,
        struct ITSSession *a3,
        __int64 a4,
        unsigned int a5)
{
  unsigned int *v9; // r15
  _QWORD *v10; // r12
  signed int InstanceOfRemoteConnectionManager; // edi
  int v12; // eax
  int v13; // eax
  unsigned int v14; // r8d
  int SessionList; // eax
  int v16; // eax
  int v17; // ebx
  int InstanceOfSessionManager; // eax
  int v19; // eax
  struct IRemoteConnectionManager *v20; // rdi
  __int64 (__fastcall *v21)(struct IRemoteConnectionManager *, __int64, _QWORD, HANDLE *, DWORD); // rbx
  DWORD CurrentProcessId; // eax
  int v23; // eax
  int v24; // eax
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // r13
  int v29; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  int v33; // r11d
  int v34; // eax
  int v35; // ecx
  int v36; // ecx
  int v37; // r8d
  int v38; // r9d
  struct IRemoteConnectionManager *v39; // rbx
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  signed int LastError; // eax
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  __int64 v54; // [rsp+20h] [rbp-E0h]
  struct IRemoteConnectionManager *v55; // [rsp+50h] [rbp-B0h] BYREF
  struct ISessionManager *v56; // [rsp+58h] [rbp-A8h] BYREF
  const char *v57; // [rsp+60h] [rbp-A0h] BYREF
  const char *v58; // [rsp+68h] [rbp-98h] BYREF
  const char *v59; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v60[2]; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h] BYREF
  HANDLE v62; // [rsp+90h] [rbp-70h] BYREF
  HANDLE v63; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v64; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE v65; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v66; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE v67; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v68; // [rsp+C0h] [rbp-40h] BYREF
  struct ISessionList *v69; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v70; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v71[16]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE Parameter[40]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v73[24]; // [rsp+110h] [rbp+10h] BYREF
  int v74; // [rsp+128h] [rbp+28h]
  int v75; // [rsp+138h] [rbp+38h]
  unsigned int v76; // [rsp+140h] [rbp+40h]

  v70 = 0;
  v69 = 0;
  v68 = 0;
  hObject = 0;
  v62 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  v66 = 0;
  v67 = 0;
  CTSRemoteTerminalTrace::CTSRemoteTerminalTrace((CTSRemoteTerminalTrace *)v73, "CRemoteTerminal::DoConnect", this);
  v9 = (unsigned int *)((char *)this + 1680);
  CTerminalOpsMonitor::CTerminalOpsMonitor(Parameter, *((_DWORD *)this + 420), "CRemoteTerminal::DoConnect");
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v60, (CRemoteTerminal *)((char *)this + 5112));
  v10 = (_QWORD *)((char *)this + 1600);
  if ( !*((_QWORD *)this + 200) )
  {
    _DbgPrintMessage(8, "Terminal is already terminated");
    InstanceOfRemoteConnectionManager = -2147418113;
    CAutoLock::Unlock((CAutoLock *)v60);
    goto LABEL_74;
  }
  SmartPtr<IConnection>::operator=(&v68, (char *)this + 1600);
  v12 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 88LL))(*v10);
  InstanceOfRemoteConnectionManager = v12;
  if ( v12 < 0 )
  {
    _DbgPrintMessage(8, "InitCommonSessionData failed: 0x%x in %s", v12, "CRemoteTerminal::DoConnect");
    CAutoLock::Unlock((CAutoLock *)v60);
    goto LABEL_74;
  }
  v13 = (*(__int64 (__fastcall **)(struct ITSSession *, char *))(*(_QWORD *)a3 + 80LL))(a3, (char *)this + 1680);
  InstanceOfRemoteConnectionManager = v13;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "getId failed: 0x%x in %s", v13, "CRemoteTerminal::DoConnect");
    CAutoLock::Unlock((CAutoLock *)v60);
    goto LABEL_74;
  }
  v14 = *v9;
  v76 = *v9;
  if ( !v75 && (g_DebugTraceComponent & 4) != 0 )
    _DbgPrintMessage(2, "Assign session id %d to terminal Trace ID 0x%x", v14, v74);
  SessionList = CHelper::GetSessionList(&v69);
  InstanceOfRemoteConnectionManager = SessionList;
  if ( SessionList < 0 )
  {
    _DbgPrintMessage(8, "GetSessionList failed: 0x%x in %s", SessionList, "CRemoteTerminal::DoConnect");
    CAutoLock::Unlock((CAutoLock *)v60);
    goto LABEL_74;
  }
  v16 = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, __int64 *))(*(_QWORD *)v69 + 24LL))(v69, *v9, &v70);
  InstanceOfRemoteConnectionManager = v16;
  if ( v16 < 0 )
  {
    _DbgPrintMessage(8, "FindSessionById failed: 0x%x in %s", v16, "CRemoteTerminal::DoConnect");
    CAutoLock::Unlock((CAutoLock *)v60);
    goto LABEL_74;
  }
  v55 = 0;
  GetInstanceOfRemoteConnectionManager(&v55);
  v17 = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v55 + 248LL))(v55);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
  if ( v17 )
  {
    v56 = 0;
    v55 = 0;
    InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v56);
    InstanceOfRemoteConnectionManager = InstanceOfSessionManager;
    if ( InstanceOfSessionManager < 0 )
    {
      _DbgPrintMessage(
        8,
        "GetInstanceOfSessionManager failed: 0x%x in %s",
        InstanceOfSessionManager,
        "CRemoteTerminal::DoConnect");
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v56);
      CAutoLock::Unlock((CAutoLock *)v60);
      goto LABEL_74;
    }
    v19 = (*(__int64 (__fastcall **)(struct ISessionManager *, struct IRemoteConnectionManager **))(*(_QWORD *)v56 + 48LL))(
            v56,
            &v55);
    InstanceOfRemoteConnectionManager = v19;
    if ( v19 < 0 )
    {
      _DbgPrintMessage(8, "GetInstanceOfRestrictedCalls failed: 0x%x in %s", v19, "CRemoteTerminal::DoConnect");
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v56);
      CAutoLock::Unlock((CAutoLock *)v60);
      goto LABEL_74;
    }
    v20 = v55;
    v21 = *(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64, _QWORD, HANDLE *, DWORD))(*(_QWORD *)v55 + 24LL);
    CurrentProcessId = GetCurrentProcessId();
    v23 = v21(v20, a4, a5, &v67, CurrentProcessId);
    InstanceOfRemoteConnectionManager = v23;
    if ( v23 < 0 )
    {
      _DbgPrintMessage(8, "Mgr->DuplicateHandleInPid failed: 0x%x in %s", v23, "CRemoteTerminal::DoConnect");
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
      SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v56);
      CAutoLock::Unlock((CAutoLock *)v60);
      goto LABEL_74;
    }
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v56);
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD, __int64, HANDLE))(*(_QWORD *)*v10 + 56LL))(*v10, v70, v67);
  InstanceOfRemoteConnectionManager = v24;
  if ( v24 < 0 )
  {
    _DbgPrintMessage(8, "AssignSession failed: 0x%x in %s", v24, "CRemoteTerminal::DoConnect");
    CAutoLock::Unlock((CAutoLock *)v60);
    goto LABEL_74;
  }
  CAutoLock::Unlock((CAutoLock *)v60);
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v55 = (struct IRemoteConnectionManager *)"GetTerminalChannels started";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v25,
      (unsigned int)byte_180108AA1,
      v26,
      v27,
      (__int64)&v55);
  }
  v28 = v68;
  v29 = (*(__int64 (__fastcall **)(__int64, HANDLE *, HANDLE *, HANDLE *, HANDLE *, HANDLE *, HANDLE *))(*(_QWORD *)v68 + 112LL))(
          v68,
          &hObject,
          &v62,
          &v63,
          &v64,
          &v65,
          &v66);
  InstanceOfRemoteConnectionManager = v29;
  if ( v29 < 0 )
  {
    _DbgPrintMessage(8, "GetTerminalChannels failed: 0x%x in %s", v29, "CRemoteTerminal::DoConnect");
    goto LABEL_74;
  }
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v55 = (struct IRemoteConnectionManager *)"GetTerminalChannels completed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v30,
      (unsigned int)&dword_180108A7C,
      v31,
      v32,
      (__int64)&v55);
  }
  CAutoExclusiveLock::CAutoExclusiveLock((CAutoExclusiveLock *)v71, (CRemoteTerminal *)((char *)this + 5112));
  if ( !*v10 )
  {
    _DbgPrintMessage(8, "Terminal is already terminated");
    InstanceOfRemoteConnectionManager = -2147418113;
    CAutoLock::Unlock((CAutoLock *)v71);
    goto LABEL_74;
  }
  CRemoteTerminal::GetTerminalName(this, (unsigned __int16 *const)a2 + 38);
  StringCchCopyW((unsigned __int16 *)a2 + 71, 0x20u, (const unsigned __int16 *)this + 920);
  *((_DWORD *)a2 + 71) = 1;
  *((_WORD *)a2 + 144) = *((_WORD *)this + 2037);
  *((_WORD *)a2 + 145) = *((_WORD *)this + 2038);
  switch ( *((_WORD *)this + 2039) )
  {
    case 1:
      LOWORD(v34) = 4;
      break;
    case 2:
      LOWORD(v34) = 8;
      break;
    case 4:
      LOWORD(v34) = 16;
      break;
    case 8:
      LOWORD(v34) = 24;
      break;
    default:
      v34 = v33 - 24;
      v35 = *((unsigned __int16 *)this + 2039) - 8 - (v33 - 24);
      if ( v35 )
      {
        if ( v35 == v34 + 8 )
          LOWORD(v34) = v33;
      }
      else
      {
        LOWORD(v34) = 15;
      }
      break;
  }
  *((_WORD *)a2 + 146) = v34;
  *((_DWORD *)a2 + 74) = *((unsigned __int8 *)this + 1884);
  *((_DWORD *)a2 + 75) = *((unsigned __int8 *)this + 1885);
  *((_DWORD *)a2 + 76) = *((_DWORD *)this + 472);
  *((_DWORD *)a2 + 77) = *((_DWORD *)this + 473);
  *((_DWORD *)a2 + 78) = *((_DWORD *)this + 474);
  *((_DWORD *)a2 + 75) = *((unsigned __int8 *)this + 1885);
  *((_DWORD *)a2 + 1) = *((_DWORD *)this + 479);
  *((_DWORD *)a2 + 2) = *((_DWORD *)this + 480);
  *(_DWORD *)a2 = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 160LL))(*v10);
  *((_DWORD *)a2 + 79) = (*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 168LL))(*v10);
  *((_OWORD *)a2 + 13) = *(_OWORD *)((char *)this + 1822);
  *((_WORD *)a2 + 112) = *((_WORD *)this + 919);
  *(_OWORD *)((char *)a2 + 226) = *(_OWORD *)((char *)this + 1858);
  *((_WORD *)a2 + 121) = *((_WORD *)this + 937);
  *(_OWORD *)((char *)a2 + 244) = *(_OWORD *)((char *)this + 1924);
  *(_OWORD *)((char *)a2 + 260) = *(_OWORD *)((char *)this + 1940);
  *(_QWORD *)((char *)a2 + 276) = *(_QWORD *)((char *)this + 1956);
  v55 = 0;
  InstanceOfRemoteConnectionManager = GetInstanceOfRemoteConnectionManager(&v55);
  if ( InstanceOfRemoteConnectionManager < 0 )
  {
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v57 = "DoConnect";
      LODWORD(v56) = InstanceOfRemoteConnectionManager;
      v58 = "GetInstanceOfRemoteConnectionManager";
      v59 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v36,
        (unsigned int)&word_180108A36,
        v37,
        v38,
        (__int64)&v59,
        (__int64)&v58,
        (__int64)&v56,
        (__int64)&v57);
    }
LABEL_67:
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
    CAutoLock::Unlock((CAutoLock *)v71);
    goto LABEL_74;
  }
  v39 = v55;
  if ( (*(unsigned int (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v55 + 400LL))(v55) )
  {
    InstanceOfRemoteConnectionManager = (*(__int64 (__fastcall **)(__int64, char *, __int64))(*(_QWORD *)v28 + 768LL))(
                                          v28,
                                          (char *)a2 + 332,
                                          200);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v59 = "DoConnect";
        LODWORD(v56) = InstanceOfRemoteConnectionManager;
        v58 = "GetIndirectDisplayHardwareId";
        v57 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)&unk_1801089F0,
          v41,
          v42,
          (__int64)&v57,
          (__int64)&v58,
          (__int64)&v56,
          (__int64)&v59);
      }
      goto LABEL_67;
    }
    LODWORD(v54) = *v9;
    InstanceOfRemoteConnectionManager = StringCchPrintfW(
                                          (unsigned __int16 *)a2 + 366,
                                          0xC8u,
                                          L"%s&SessionId_%04d",
                                          (char *)a2 + 332,
                                          v54);
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v59 = "DoConnect";
        LODWORD(v56) = InstanceOfRemoteConnectionManager;
        v58 = "Failed to construct InstanceId for ID driver";
        v57 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v43,
          (unsigned int)word_1801089AA,
          v44,
          v45,
          (__int64)&v57,
          (__int64)&v58,
          (__int64)&v56,
          (__int64)&v59);
      }
      goto LABEL_67;
    }
    if ( !AllocateLocallyUniqueId((PLUID)((char *)a2 + 1132)) )
    {
      LastError = GetLastError();
      InstanceOfRemoteConnectionManager = LastError;
      if ( LastError > 0 )
        InstanceOfRemoteConnectionManager = (unsigned __int16)LastError | 0x80070000;
      if ( InstanceOfRemoteConnectionManager < 0 )
      {
        if ( (unsigned int)dword_180128170 > 3 )
        {
          v59 = "DoConnect";
          LODWORD(v56) = InstanceOfRemoteConnectionManager;
          v58 = "Failed to generate TerminalLuid";
          v57 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v47,
            (unsigned int)&dword_180108964,
            v48,
            v49,
            (__int64)&v57,
            (__int64)&v58,
            (__int64)&v56,
            (__int64)&v59);
        }
        goto LABEL_67;
      }
    }
    InstanceOfRemoteConnectionManager = CRemoteTerminal::StartRemoteDisplayDevice(
                                          this,
                                          (const unsigned __int16 *)a2 + 366,
                                          *v9,
                                          (const struct _LUID *)((char *)a2 + 1132));
    if ( InstanceOfRemoteConnectionManager < 0 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v59 = (char *)a2 + 732;
        v58 = "DoConnect";
        LODWORD(v56) = InstanceOfRemoteConnectionManager;
        v57 = "Failed to start Remote Display Device";
        v60[0] = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v50,
          (unsigned int)&dword_18010890C,
          v51,
          v52,
          (__int64)v60,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&v58,
          (__int64)&v59);
      }
      goto LABEL_67;
    }
    *((_DWORD *)a2 + 285) = 1;
  }
  if ( !*((_QWORD *)this + 666) )
  {
    SmartHANDLE::operator=((char *)this + 5328, v62);
    SmartHANDLE::operator=((char *)this + 5336, v63);
    SmartHANDLE::operator=((char *)this + 5344, v64);
    SmartHANDLE::operator=((char *)this + 5352, v65);
    if ( !(*(unsigned int (__fastcall **)(struct IRemoteConnectionManager *))(*(_QWORD *)v39 + 400LL))(v39) )
    {
      *((_QWORD *)this + 665) = hObject;
      SmartHANDLE::operator=((char *)this + 5360, v66);
      hObject = 0;
      v66 = 0;
    }
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
  }
  *((_QWORD *)a2 + 2) = *((_QWORD *)this + 665);
  *((_QWORD *)a2 + 4) = *((_QWORD *)this + 666);
  *((_QWORD *)a2 + 3) = *((_QWORD *)this + 667);
  *((_QWORD *)a2 + 6) = *((_QWORD *)this + 668);
  *((_QWORD *)a2 + 5) = *((_QWORD *)this + 669);
  *((_QWORD *)a2 + 7) = *((_QWORD *)this + 670);
  *((_DWORD *)a2 + 18) = GetCurrentProcessId();
  (*(void (__fastcall **)(_QWORD, struct _TERMINAL_CONNECTMSG *))(**((_QWORD **)this + 200) + 448LL))(
    *((_QWORD *)this + 200),
    a2);
  CRemoteTerminal::CacheTerminalInfo(this);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v55);
  CAutoLock::Unlock((CAutoLock *)v71);
LABEL_74:
  if ( hObject )
    CloseHandle(hObject);
  if ( v62 )
    CloseHandle(v62);
  if ( v63 )
    CloseHandle(v63);
  if ( v64 )
    CloseHandle(v64);
  if ( v65 )
    CloseHandle(v65);
  if ( v66 )
    CloseHandle(v66);
  if ( v67 )
    CloseHandle(v67);
  CTerminalOpsMonitor::~CTerminalOpsMonitor((CTerminalOpsMonitor *)Parameter);
  CTSRemoteTerminalTrace::~CTSRemoteTerminalTrace((CTSRemoteTerminalTrace *)v73);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v68);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v69);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v70);
  return (unsigned int)InstanceOfRemoteConnectionManager;
}

```

## disassembly

```asm
0x180050530  push    rbp
0x180050532  push    rbx
0x180050533  push    rsi
0x180050534  push    rdi
0x180050535  push    r12
0x180050537  push    r13
0x180050539  push    r14
0x18005053b  push    r15
0x18005053d  lea     rbp, [rsp-0C8h]
0x180050545  sub     rsp, 1C8h
0x18005054c  mov     rax, cs:__security_cookie
0x180050553  xor     rax, rsp
0x180050556  mov     [rbp+100h+var_50], rax
0x18005055d  mov     r13, r9
0x180050560  mov     rbx, r8
0x180050563  mov     r14, rdx
0x180050566  mov     rsi, rcx
0x180050569  xor     edi, edi
0x18005056b  mov     [rbp+100h+var_130], rdi
0x18005056f  mov     [rbp+100h+var_138], rdi
0x180050573  mov     [rbp+100h+var_140], rdi
0x180050577  mov     [rbp+100h+hObject], rdi
0x18005057b  mov     [rbp+100h+var_170], rdi
0x18005057f  mov     [rbp+100h+var_168], rdi
0x180050583  mov     [rbp+100h+var_160], rdi
0x180050587  mov     [rbp+100h+var_158], rdi
0x18005058b  mov     [rbp+100h+var_150], rdi
0x18005058f  mov     [rbp+100h+var_148], rdi
0x180050593  mov     r8, rcx; struct CRemoteTerminal *
0x180050596  lea     rdx, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x18005059d  lea     rcx, [rbp+100h+var_F0]; this
0x1800505a1  call    ??0CTSRemoteTerminalTrace@@QEAA@PEBDPEAVCRemoteTerminal@@@Z; CTSRemoteTerminalTrace::CTSRemoteTerminalTrace(char const *,CRemoteTerminal *)
0x1800505a6  nop
0x1800505a7  lea     r15, [rsi+690h]
0x1800505ae  lea     r8, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x1800505b5  mov     edx, [r15]; int
0x1800505b8  lea     rcx, [rbp+100h+Parameter]; Parameter
0x1800505bc  call    ??0CTerminalOpsMonitor@@QEAA@JPEBD@Z; CTerminalOpsMonitor::CTerminalOpsMonitor(long,char const *)
0x1800505c1  nop
0x1800505c2  lea     rdx, [rsi+13F8h]; struct CResource *
0x1800505c9  lea     rcx, [rsp+200h+var_188]; this
0x1800505ce  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800505d3  nop
0x1800505d4  lea     r12, [rsi+640h]
0x1800505db  cmp     [r12], rdi
0x1800505df  jnz     short loc_180050605
0x1800505e1  lea     rdx, aTerminalIsAlre; "Terminal is already terminated"
0x1800505e8  lea     ecx, [rdi+8]; int
0x1800505eb  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800505f0  mov     edi, 8000FFFFh
0x1800505f5  lea     rcx, [rsp+200h+var_188]; this
0x1800505fa  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800505ff  nop
0x180050600  jmp     loc_180051086
0x180050605  mov     rdx, r12
0x180050608  lea     rcx, [rbp+100h+var_140]
0x18005060c  call    ??4?$SmartPtr@VIConnection@@@@QEAAAEAV0@AEAV0@@Z; SmartPtr<IConnection>::operator=(SmartPtr<IConnection> &)
0x180050611  mov     rcx, [r12]
0x180050615  mov     rax, [rcx]
0x180050618  mov     rax, [rax+58h]
0x18005061c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050621  mov     edi, eax
0x180050623  test    eax, eax
0x180050625  jns     short loc_180050653
0x180050627  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x18005062e  mov     r8d, eax
0x180050631  lea     rdx, aInitcommonsess; "InitCommonSessionData failed: 0x%x in %"...
0x180050638  mov     ecx, 8; int
0x18005063d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180050642  nop
0x180050643  lea     rcx, [rsp+200h+var_188]; this
0x180050648  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18005064d  nop
0x18005064e  jmp     loc_180051086
0x180050653  mov     rax, [rbx]
0x180050656  mov     rdx, r15
0x180050659  mov     rcx, rbx
0x18005065c  mov     rax, [rax+50h]
0x180050660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050665  mov     edi, eax
0x180050667  test    eax, eax
0x180050669  jns     short loc_180050697
0x18005066b  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180050672  mov     r8d, eax
0x180050675  lea     rdx, aGetidFailed0xX; "getId failed: 0x%x in %s"
0x18005067c  mov     ecx, 8; int
0x180050681  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180050686  nop
0x180050687  lea     rcx, [rsp+200h+var_188]; this
0x18005068c  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180050691  nop
0x180050692  jmp     loc_180051086
0x180050697  mov     r8d, [r15]
0x18005069a  mov     [rbp+100h+var_C0], r8d
0x18005069e  cmp     [rbp+100h+var_C8], 0
0x1800506a2  jnz     short loc_1800506C2
0x1800506a4  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x1800506ab  jz      short loc_1800506C2
0x1800506ad  mov     r9d, [rbp+100h+var_D8]
0x1800506b1  lea     rdx, aAssignSessionI; "Assign session id %d to terminal Trace "...
0x1800506b8  mov     ecx, 2; int
0x1800506bd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800506c2  lea     rcx, [rbp+100h+var_138]; struct ISessionList **
0x1800506c6  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x1800506cb  mov     edi, eax
0x1800506cd  test    eax, eax
0x1800506cf  jns     short loc_1800506FD
0x1800506d1  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x1800506d8  mov     r8d, eax
0x1800506db  lea     rdx, aGetsessionlist_0; "GetSessionList failed: 0x%x in %s"
0x1800506e2  mov     ecx, 8; int
0x1800506e7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800506ec  nop
0x1800506ed  lea     rcx, [rsp+200h+var_188]; this
0x1800506f2  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800506f7  nop
0x1800506f8  jmp     loc_180051086
0x1800506fd  mov     rcx, [rbp+100h+var_138]
0x180050701  mov     rax, [rcx]
0x180050704  lea     r8, [rbp+100h+var_130]
0x180050708  mov     edx, [r15]
0x18005070b  mov     rax, [rax+18h]
0x18005070f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050714  mov     edi, eax
0x180050716  test    eax, eax
0x180050718  jns     short loc_180050746
0x18005071a  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180050721  mov     r8d, eax
0x180050724  lea     rdx, aFindsessionbyi_0; "FindSessionById failed: 0x%x in %s"
0x18005072b  mov     ecx, 8; int
0x180050730  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180050735  nop
0x180050736  lea     rcx, [rsp+200h+var_188]; this
0x18005073b  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180050740  nop
0x180050741  jmp     loc_180051086
0x180050746  mov     [rsp+200h+var_1B0], 0
0x18005074f  lea     rcx, [rsp+200h+var_1B0]; struct IRemoteConnectionManager **
0x180050754  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180050759  mov     rcx, [rsp+200h+var_1B0]
0x18005075e  mov     rax, [rcx]
0x180050761  mov     rax, [rax+0F8h]
0x180050768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005076d  mov     ebx, eax
0x18005076f  lea     rcx, [rsp+200h+var_1B0]; void *
0x180050774  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180050779  test    ebx, ebx
0x18005077b  jz      loc_1800508CF
0x180050781  mov     [rsp+200h+var_1A8], 0
0x18005078a  mov     [rsp+200h+var_1B0], 0
0x180050793  lea     rcx, [rsp+200h+var_1A8]; struct ISessionManager **
0x180050798  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x18005079d  mov     edi, eax
0x18005079f  test    eax, eax
0x1800507a1  jns     short loc_1800507E5
0x1800507a3  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x1800507aa  mov     r8d, eax
0x1800507ad  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x1800507b4  mov     ecx, 8; int
0x1800507b9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800507be  nop
0x1800507bf  lea     rcx, [rsp+200h+var_1B0]; void *
0x1800507c4  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800507c9  nop
0x1800507ca  lea     rcx, [rsp+200h+var_1A8]; void *
0x1800507cf  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800507d4  nop
0x1800507d5  lea     rcx, [rsp+200h+var_188]; this
0x1800507da  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800507df  nop
0x1800507e0  jmp     loc_180051086
0x1800507e5  mov     rcx, [rsp+200h+var_1A8]
0x1800507ea  mov     rax, [rcx]
0x1800507ed  lea     rdx, [rsp+200h+var_1B0]
0x1800507f2  mov     rax, [rax+30h]
0x1800507f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507fb  mov     edi, eax
0x1800507fd  test    eax, eax
0x1800507ff  jns     short loc_180050843
0x180050801  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180050808  mov     r8d, eax
0x18005080b  lea     rdx, aGetinstanceofr_4; "GetInstanceOfRestrictedCalls failed: 0x"...
0x180050812  mov     ecx, 8; int
0x180050817  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18005081c  nop
0x18005081d  lea     rcx, [rsp+200h+var_1B0]; void *
0x180050822  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180050827  nop
0x180050828  lea     rcx, [rsp+200h+var_1A8]; void *
0x18005082d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180050832  nop
0x180050833  lea     rcx, [rsp+200h+var_188]; this
0x180050838  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x18005083d  nop
0x18005083e  jmp     loc_180051086
0x180050843  mov     rdi, [rsp+200h+var_1B0]
0x180050848  mov     rax, [rdi]
0x18005084b  mov     rbx, [rax+18h]
0x18005084f  call    cs:__imp_GetCurrentProcessId
0x180050855  mov     dword ptr [rsp+200h+var_1E0], eax
0x180050859  lea     r9, [rbp+100h+var_148]
0x18005085d  mov     r8d, [rbp+100h+arg_20]
0x180050864  mov     rdx, r13
0x180050867  mov     rcx, rdi
0x18005086a  mov     rax, rbx
0x18005086d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050872  mov     edi, eax
0x180050874  test    eax, eax
0x180050876  jns     short loc_1800508BA
0x180050878  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x18005087f  mov     r8d, eax
0x180050882  lea     rdx, aMgrDuplicateha; "Mgr->DuplicateHandleInPid failed: 0x%x "...
0x180050889  mov     ecx, 8; int
0x18005088e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180050893  nop
0x180050894  lea     rcx, [rsp+200h+var_1B0]; void *
0x180050899  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18005089e  nop
0x18005089f  lea     rcx, [rsp+200h+var_1A8]; void *
0x1800508a4  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800508a9  nop
0x1800508aa  lea     rcx, [rsp+200h+var_188]; this
0x1800508af  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x1800508b4  nop
0x1800508b5  jmp     loc_180051086
0x1800508ba  lea     rcx, [rsp+200h+var_1B0]; void *
0x1800508bf  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800508c4  nop
0x1800508c5  lea     rcx, [rsp+200h+var_1A8]; void *
0x1800508ca  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x1800508cf  mov     rcx, [r12]
0x1800508d3  mov     rax, [rcx]
0x1800508d6  mov     r8, [rbp+100h+var_148]
0x1800508da  mov     rdx, [rbp+100h+var_130]
0x1800508de  mov     rax, [rax+38h]
0x1800508e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800508e7  mov     edi, eax
0x1800508e9  test    eax, eax
0x1800508eb  jns     short loc_180050919
0x1800508ed  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x1800508f4  mov     r8d, eax
0x1800508f7  lea     rdx, aAssignsessionF; "AssignSession failed: 0x%x in %s"
0x1800508fe  mov     ecx, 8; int
0x180050903  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180050908  nop
0x180050909  lea     rcx, [rsp+200h+var_188]; this
0x18005090e  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180050913  nop
0x180050914  jmp     loc_180051086
0x180050919  lea     rcx, [rsp+200h+var_188]; this
0x18005091e  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180050923  nop
0x180050924  mov     eax, cs:dword_180128170
0x18005092a  mov     ebx, 4
0x18005092f  cmp     eax, ebx
0x180050931  jbe     short loc_180050955
0x180050933  lea     rax, aGetterminalcha_0; "GetTerminalChannels started"
0x18005093a  mov     [rsp+200h+var_1B0], rax
0x18005093f  lea     rax, [rsp+200h+var_1B0]
0x180050944  mov     [rsp+200h+var_1E0], rax
0x180050949  lea     rdx, byte_180108AA1
0x180050950  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180050955  mov     r13, [rbp+100h+var_140]
0x180050959  mov     rax, [r13+0]
0x18005095d  lea     rcx, [rbp+100h+var_150]
0x180050961  mov     [rsp+200h+var_1D0], rcx
0x180050966  lea     rcx, [rbp+100h+var_158]
0x18005096a  mov     [rsp+200h+var_1D8], rcx
0x18005096f  lea     rcx, [rbp+100h+var_160]
0x180050973  mov     [rsp+200h+var_1E0], rcx
0x180050978  lea     r9, [rbp+100h+var_168]
0x18005097c  lea     r8, [rbp+100h+var_170]
0x180050980  lea     rdx, [rbp+100h+hObject]
0x180050984  mov     rcx, r13
0x180050987  mov     rax, [rax+70h]
0x18005098b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050990  mov     edi, eax
0x180050992  test    eax, eax
0x180050994  jns     short loc_1800509B6
0x180050996  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x18005099d  mov     r8d, eax
0x1800509a0  lea     rdx, aGetterminalcha; "GetTerminalChannels failed: 0x%x in %s"
0x1800509a7  mov     ecx, 8; int
0x1800509ac  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800509b1  jmp     loc_180051086
0x1800509b6  mov     eax, cs:dword_180128170
0x1800509bc  cmp     eax, ebx
0x1800509be  jbe     short loc_1800509E2
0x1800509c0  lea     rax, aGetterminalcha_1; "GetTerminalChannels completed"
0x1800509c7  mov     [rsp+200h+var_1B0], rax
0x1800509cc  lea     rax, [rsp+200h+var_1B0]
0x1800509d1  mov     [rsp+200h+var_1E0], rax
0x1800509d6  lea     rdx, dword_180108A7C
0x1800509dd  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800509e2  lea     rdx, [rsi+13F8h]; struct CResource *
0x1800509e9  lea     rcx, [rbp+100h+var_128]; this
0x1800509ed  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800509f2  nop
0x1800509f3  cmp     qword ptr [r12], 0
0x1800509f8  jnz     short loc_180050A1F
  ... truncated ...
```
