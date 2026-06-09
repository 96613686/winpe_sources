# CRemoteTerminal::DoConnect(_TERMINAL_CONNECTMSG *,ITSSession *,unsigned __int64,ulong)

- ea: `0x180052bf0`
- end: `0x180053849`
- name: `?DoConnect@CRemoteTerminal@@UEAAJPEAU_TERMINAL_CONNECTMSG@@PEAUITSSession@@_KK@Z`
- size: `3161`
- prototype: `__int64 __usercall@<rax>(CRemoteTerminal *__hidden this@<rcx>, struct _TERMINAL_CONNECTMSG *@<rdx>, struct ITSSession *@<r8>, unsigned __int64@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800016a8`
- `0x1800027b4`
- `0x1800095a0`
- `0x180009940`
- `0x18000c2a0`
- `0x180012750`
- `0x180012c90`
- `0x180012d10`
- `0x180013948`
- `0x1800139c0`
- `0x180013f10`
- `0x180015238`
- `0x180015310`
- `0x180015c44`
- `0x180016558`
- `0x1800291e8`
- `0x180033f60`
- `0x18003f9a8`
- `0x180040878`
- `0x1800524e8`
- `0x180052958`
- `0x180052bf0`
- `0x180055bdc`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800534cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800534cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052f0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180053717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052f0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180053717`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005377c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053767`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005377c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053791`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800537e5`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x1800534bb`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x1800534bb`

## string_xrefs

- `0x180052ca1`: `Terminal is already terminated`
- `0x1800530c0`: `Terminal is already terminated`
- `0x180052cf1`: `InitCommonSessionData failed: 0x%x in %s`
- `0x180053086`: `GetTerminalChannels completed`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v55 = (struct IRemoteConnectionManager *)"GetTerminalChannels started";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v25,
      (unsigned int)byte_18010EB21,
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
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v55 = (struct IRemoteConnectionManager *)"GetTerminalChannels completed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v30,
      (unsigned int)&dword_18010EAFC,
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
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v57 = "DoConnect";
      LODWORD(v56) = InstanceOfRemoteConnectionManager;
      v58 = "GetInstanceOfRemoteConnectionManager";
      v59 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v36,
        (unsigned int)&word_18010EAB6,
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
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v59 = "DoConnect";
        LODWORD(v56) = InstanceOfRemoteConnectionManager;
        v58 = "GetIndirectDisplayHardwareId";
        v57 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)&unk_18010EA70,
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
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v59 = "DoConnect";
        LODWORD(v56) = InstanceOfRemoteConnectionManager;
        v58 = "Failed to construct InstanceId for ID driver";
        v57 = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v43,
          (unsigned int)word_18010EA2A,
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
        if ( (unsigned int)dword_18012E170 > 3 )
        {
          v59 = "DoConnect";
          LODWORD(v56) = InstanceOfRemoteConnectionManager;
          v58 = "Failed to generate TerminalLuid";
          v57 = "Warning HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v47,
            (unsigned int)&dword_18010E9E4,
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
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v59 = (char *)a2 + 732;
        v58 = "DoConnect";
        LODWORD(v56) = InstanceOfRemoteConnectionManager;
        v57 = "Failed to start Remote Display Device";
        v60[0] = "Warning HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v50,
          (unsigned int)&dword_18010E98C,
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
0x180052bf0  push    rbp
0x180052bf2  push    rbx
0x180052bf3  push    rsi
0x180052bf4  push    rdi
0x180052bf5  push    r12
0x180052bf7  push    r13
0x180052bf9  push    r14
0x180052bfb  push    r15
0x180052bfd  lea     rbp, [rsp-0C8h]
0x180052c05  sub     rsp, 1C8h
0x180052c0c  mov     rax, cs:__security_cookie
0x180052c13  xor     rax, rsp
0x180052c16  mov     [rbp+100h+var_50], rax
0x180052c1d  mov     r13, r9
0x180052c20  mov     rbx, r8
0x180052c23  mov     r14, rdx
0x180052c26  mov     rsi, rcx
0x180052c29  xor     edi, edi
0x180052c2b  mov     [rbp+100h+var_130], rdi
0x180052c2f  mov     [rbp+100h+var_138], rdi
0x180052c33  mov     [rbp+100h+var_140], rdi
0x180052c37  mov     [rbp+100h+hObject], rdi
0x180052c3b  mov     [rbp+100h+var_170], rdi
0x180052c3f  mov     [rbp+100h+var_168], rdi
0x180052c43  mov     [rbp+100h+var_160], rdi
0x180052c47  mov     [rbp+100h+var_158], rdi
0x180052c4b  mov     [rbp+100h+var_150], rdi
0x180052c4f  mov     [rbp+100h+var_148], rdi
0x180052c53  mov     r8, rcx; struct CRemoteTerminal *
0x180052c56  lea     rdx, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052c5d  lea     rcx, [rbp+100h+var_F0]; this
0x180052c61  call    ??0CTSRemoteTerminalTrace@@QEAA@PEBDPEAVCRemoteTerminal@@@Z; CTSRemoteTerminalTrace::CTSRemoteTerminalTrace(char const *,CRemoteTerminal *)
0x180052c66  nop
0x180052c67  lea     r15, [rsi+690h]
0x180052c6e  lea     r8, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052c75  mov     edx, [r15]; int
0x180052c78  lea     rcx, [rbp+100h+Parameter]; Parameter
0x180052c7c  call    ??0CTerminalOpsMonitor@@QEAA@JPEBD@Z; CTerminalOpsMonitor::CTerminalOpsMonitor(long,char const *)
0x180052c81  nop
0x180052c82  lea     rdx, [rsi+13F8h]; struct CResource *
0x180052c89  lea     rcx, [rsp+200h+var_188]; this
0x180052c8e  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x180052c93  nop
0x180052c94  lea     r12, [rsi+640h]
0x180052c9b  cmp     [r12], rdi
0x180052c9f  jnz     short loc_180052CC5
0x180052ca1  lea     rdx, aTerminalIsAlre; "Terminal is already terminated"
0x180052ca8  lea     ecx, [rdi+8]; int
0x180052cab  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052cb0  mov     edi, 8000FFFFh
0x180052cb5  lea     rcx, [rsp+200h+var_188]; this
0x180052cba  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052cbf  nop
0x180052cc0  jmp     loc_18005375E
0x180052cc5  mov     rdx, r12
0x180052cc8  lea     rcx, [rbp+100h+var_140]
0x180052ccc  call    ??4?$SmartPtr@VIConnection@@@@QEAAAEAV0@AEAV0@@Z; SmartPtr<IConnection>::operator=(SmartPtr<IConnection> &)
0x180052cd1  mov     rcx, [r12]
0x180052cd5  mov     rax, [rcx]
0x180052cd8  mov     rax, [rax+58h]
0x180052cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ce1  mov     edi, eax
0x180052ce3  test    eax, eax
0x180052ce5  jns     short loc_180052D13
0x180052ce7  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052cee  mov     r8d, eax
0x180052cf1  lea     rdx, aInitcommonsess; "InitCommonSessionData failed: 0x%x in %"...
0x180052cf8  mov     ecx, 8; int
0x180052cfd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052d02  nop
0x180052d03  lea     rcx, [rsp+200h+var_188]; this
0x180052d08  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052d0d  nop
0x180052d0e  jmp     loc_18005375E
0x180052d13  mov     rax, [rbx]
0x180052d16  mov     rdx, r15
0x180052d19  mov     rcx, rbx
0x180052d1c  mov     rax, [rax+50h]
0x180052d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d25  mov     edi, eax
0x180052d27  test    eax, eax
0x180052d29  jns     short loc_180052D57
0x180052d2b  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052d32  mov     r8d, eax
0x180052d35  lea     rdx, aGetidFailed0xX; "getId failed: 0x%x in %s"
0x180052d3c  mov     ecx, 8; int
0x180052d41  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052d46  nop
0x180052d47  lea     rcx, [rsp+200h+var_188]; this
0x180052d4c  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052d51  nop
0x180052d52  jmp     loc_18005375E
0x180052d57  mov     r8d, [r15]
0x180052d5a  mov     [rbp+100h+var_C0], r8d
0x180052d5e  cmp     [rbp+100h+var_C8], 0
0x180052d62  jnz     short loc_180052D82
0x180052d64  test    byte ptr cs:?g_DebugTraceComponent@@3KA, 4; ulong g_DebugTraceComponent
0x180052d6b  jz      short loc_180052D82
0x180052d6d  mov     r9d, [rbp+100h+var_D8]
0x180052d71  lea     rdx, aAssignSessionI; "Assign session id %d to terminal Trace "...
0x180052d78  mov     ecx, 2; int
0x180052d7d  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052d82  lea     rcx, [rbp+100h+var_138]; struct ISessionList **
0x180052d86  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180052d8b  mov     edi, eax
0x180052d8d  test    eax, eax
0x180052d8f  jns     short loc_180052DBD
0x180052d91  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052d98  mov     r8d, eax
0x180052d9b  lea     rdx, aGetsessionlist_0; "GetSessionList failed: 0x%x in %s"
0x180052da2  mov     ecx, 8; int
0x180052da7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052dac  nop
0x180052dad  lea     rcx, [rsp+200h+var_188]; this
0x180052db2  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052db7  nop
0x180052db8  jmp     loc_18005375E
0x180052dbd  mov     rcx, [rbp+100h+var_138]
0x180052dc1  mov     rax, [rcx]
0x180052dc4  lea     r8, [rbp+100h+var_130]
0x180052dc8  mov     edx, [r15]
0x180052dcb  mov     rax, [rax+18h]
0x180052dcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052dd4  mov     edi, eax
0x180052dd6  test    eax, eax
0x180052dd8  jns     short loc_180052E06
0x180052dda  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052de1  mov     r8d, eax
0x180052de4  lea     rdx, aFindsessionbyi_0; "FindSessionById failed: 0x%x in %s"
0x180052deb  mov     ecx, 8; int
0x180052df0  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052df5  nop
0x180052df6  lea     rcx, [rsp+200h+var_188]; this
0x180052dfb  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052e00  nop
0x180052e01  jmp     loc_18005375E
0x180052e06  mov     [rsp+200h+var_1B0], 0
0x180052e0f  lea     rcx, [rsp+200h+var_1B0]; struct IRemoteConnectionManager **
0x180052e14  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180052e19  mov     rcx, [rsp+200h+var_1B0]
0x180052e1e  mov     rax, [rcx]
0x180052e21  mov     rax, [rax+0F8h]
0x180052e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e2d  mov     ebx, eax
0x180052e2f  lea     rcx, [rsp+200h+var_1B0]; void *
0x180052e34  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052e39  test    ebx, ebx
0x180052e3b  jz      loc_180052F95
0x180052e41  mov     [rsp+200h+var_1A8], 0
0x180052e4a  mov     [rsp+200h+var_1B0], 0
0x180052e53  lea     rcx, [rsp+200h+var_1A8]; struct ISessionManager **
0x180052e58  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x180052e5d  mov     edi, eax
0x180052e5f  test    eax, eax
0x180052e61  jns     short loc_180052EA5
0x180052e63  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052e6a  mov     r8d, eax
0x180052e6d  lea     rdx, aGetinstanceofs; "GetInstanceOfSessionManager failed: 0x%"...
0x180052e74  mov     ecx, 8; int
0x180052e79  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052e7e  nop
0x180052e7f  lea     rcx, [rsp+200h+var_1B0]; void *
0x180052e84  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052e89  nop
0x180052e8a  lea     rcx, [rsp+200h+var_1A8]; void *
0x180052e8f  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052e94  nop
0x180052e95  lea     rcx, [rsp+200h+var_188]; this
0x180052e9a  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052e9f  nop
0x180052ea0  jmp     loc_18005375E
0x180052ea5  mov     rcx, [rsp+200h+var_1A8]
0x180052eaa  mov     rax, [rcx]
0x180052ead  lea     rdx, [rsp+200h+var_1B0]
0x180052eb2  mov     rax, [rax+30h]
0x180052eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052ebb  mov     edi, eax
0x180052ebd  test    eax, eax
0x180052ebf  jns     short loc_180052F03
0x180052ec1  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052ec8  mov     r8d, eax
0x180052ecb  lea     rdx, aGetinstanceofr_4; "GetInstanceOfRestrictedCalls failed: 0x"...
0x180052ed2  mov     ecx, 8; int
0x180052ed7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052edc  nop
0x180052edd  lea     rcx, [rsp+200h+var_1B0]; void *
0x180052ee2  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052ee7  nop
0x180052ee8  lea     rcx, [rsp+200h+var_1A8]; void *
0x180052eed  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052ef2  nop
0x180052ef3  lea     rcx, [rsp+200h+var_188]; this
0x180052ef8  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052efd  nop
0x180052efe  jmp     loc_18005375E
0x180052f03  mov     rdi, [rsp+200h+var_1B0]
0x180052f08  mov     rax, [rdi]
0x180052f0b  mov     rbx, [rax+18h]
0x180052f0f  call    cs:__imp_GetCurrentProcessId
0x180052f16  nop     dword ptr [rax+rax+00h]
0x180052f1b  mov     dword ptr [rsp+200h+var_1E0], eax
0x180052f1f  lea     r9, [rbp+100h+var_148]
0x180052f23  mov     r8d, [rbp+100h+arg_20]
0x180052f2a  mov     rdx, r13
0x180052f2d  mov     rcx, rdi
0x180052f30  mov     rax, rbx
0x180052f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f38  mov     edi, eax
0x180052f3a  test    eax, eax
0x180052f3c  jns     short loc_180052F80
0x180052f3e  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052f45  mov     r8d, eax
0x180052f48  lea     rdx, aMgrDuplicateha; "Mgr->DuplicateHandleInPid failed: 0x%x "...
0x180052f4f  mov     ecx, 8; int
0x180052f54  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052f59  nop
0x180052f5a  lea     rcx, [rsp+200h+var_1B0]; void *
0x180052f5f  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052f64  nop
0x180052f65  lea     rcx, [rsp+200h+var_1A8]; void *
0x180052f6a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052f6f  nop
0x180052f70  lea     rcx, [rsp+200h+var_188]; this
0x180052f75  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052f7a  nop
0x180052f7b  jmp     loc_18005375E
0x180052f80  lea     rcx, [rsp+200h+var_1B0]; void *
0x180052f85  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052f8a  nop
0x180052f8b  lea     rcx, [rsp+200h+var_1A8]; void *
0x180052f90  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180052f95  mov     rcx, [r12]
0x180052f99  mov     rax, [rcx]
0x180052f9c  mov     r8, [rbp+100h+var_148]
0x180052fa0  mov     rdx, [rbp+100h+var_130]
0x180052fa4  mov     rax, [rax+38h]
0x180052fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052fad  mov     edi, eax
0x180052faf  test    eax, eax
0x180052fb1  jns     short loc_180052FDF
0x180052fb3  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180052fba  mov     r8d, eax
0x180052fbd  lea     rdx, aAssignsessionF; "AssignSession failed: 0x%x in %s"
0x180052fc4  mov     ecx, 8; int
0x180052fc9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180052fce  nop
0x180052fcf  lea     rcx, [rsp+200h+var_188]; this
0x180052fd4  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052fd9  nop
0x180052fda  jmp     loc_18005375E
0x180052fdf  lea     rcx, [rsp+200h+var_188]; this
0x180052fe4  call    ?Unlock@CAutoLock@@QEAAXXZ; CAutoLock::Unlock(void)
0x180052fe9  nop
0x180052fea  mov     eax, cs:dword_18012E170
0x180052ff0  mov     ebx, 4
0x180052ff5  cmp     eax, ebx
0x180052ff7  jbe     short loc_18005301B
0x180052ff9  lea     rax, aGetterminalcha_0; "GetTerminalChannels started"
0x180053000  mov     [rsp+200h+var_1B0], rax
0x180053005  lea     rax, [rsp+200h+var_1B0]
0x18005300a  mov     [rsp+200h+var_1E0], rax
0x18005300f  lea     rdx, byte_18010EB21
0x180053016  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18005301b  mov     r13, [rbp+100h+var_140]
0x18005301f  mov     rax, [r13+0]
0x180053023  lea     rcx, [rbp+100h+var_150]
0x180053027  mov     [rsp+200h+var_1D0], rcx
0x18005302c  lea     rcx, [rbp+100h+var_158]
0x180053030  mov     [rsp+200h+var_1D8], rcx
0x180053035  lea     rcx, [rbp+100h+var_160]
0x180053039  mov     [rsp+200h+var_1E0], rcx
0x18005303e  lea     r9, [rbp+100h+var_168]
0x180053042  lea     r8, [rbp+100h+var_170]
0x180053046  lea     rdx, [rbp+100h+hObject]
0x18005304a  mov     rcx, r13
0x18005304d  mov     rax, [rax+70h]
0x180053051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053056  mov     edi, eax
0x180053058  test    eax, eax
0x18005305a  jns     short loc_18005307C
0x18005305c  lea     r9, aCremotetermina_3; "CRemoteTerminal::DoConnect"
0x180053063  mov     r8d, eax
0x180053066  lea     rdx, aGetterminalcha; "GetTerminalChannels failed: 0x%x in %s"
0x18005306d  mov     ecx, 8; int
0x180053072  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180053077  jmp     loc_18005375E
0x18005307c  mov     eax, cs:dword_18012E170
0x180053082  cmp     eax, ebx
0x180053084  jbe     short loc_1800530A8
0x180053086  lea     rax, aGetterminalcha_1; "GetTerminalChannels completed"
0x18005308d  mov     [rsp+200h+var_1B0], rax
0x180053092  lea     rax, [rsp+200h+var_1B0]
0x180053097  mov     [rsp+200h+var_1E0], rax
0x18005309c  lea     rdx, dword_18010EAFC
0x1800530a3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800530a8  lea     rdx, [rsi+13F8h]; struct CResource *
0x1800530af  lea     rcx, [rbp+100h+var_128]; this
0x1800530b3  call    ??0CAutoExclusiveLock@@QEAA@AEAVCResource@@@Z; CAutoExclusiveLock::CAutoExclusiveLock(CResource &)
0x1800530b8  nop
0x1800530b9  cmp     qword ptr [r12], 0
  ... truncated ...
```
