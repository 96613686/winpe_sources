# CSessionArbitrationCacheMode::TryToCreateNewSession(void)

- ea: `0x180069848`
- end: `0x180069d89`
- name: `?TryToCreateNewSession@CSessionArbitrationCacheMode@@QEAAJXZ`
- size: `1345`
- prototype: `__int64 __fastcall(CSessionArbitrationCacheMode *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006a318`

## callees

- `0x180001284`
- `0x18000a210`
- `0x18000c2f0`
- `0x1800130d8`
- `0x180013150`
- `0x180013d00`
- `0x1800148f0`
- `0x18005a83c`
- `0x180067068`
- `0x180068a6c`
- `0x180068cdc`
- `0x1800691a8`
- `0x180069848`
- `0x18006a210`
- `0x180077df0`
- `0x1800bb890`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180069c41`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180069c41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069d70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069d70`

## string_xrefs

- `0x1800698f7`: `m_ptrHelperMgr->IsAppServer (TryToCreateNewSession) failed: 0x%x in %s`
- `0x180069865`: `CSessionArbitrationCacheMode::TryToCreateNewSession`
- `0x180069ca3`: `CSessionArbitrationCacheMode::TryToCreateNewSession`
- `0x180069d49`: `CSessionArbitrationCacheMode::TryToCreateNewSession`
- `0x180069d12`: `Marked cache session`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSessionArbitrationCacheMode::TryToCreateNewSession(
        CSessionArbitrationCacheMode *this,
        __int64 a2,
        int a3,
        int a4)
{
  int v5; // esi
  int IsAppServer; // eax
  unsigned int InstanceOfSessionManager; // ebx
  int InstanceOfRemoteConnectionManager; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  int v16; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v20; // eax
  int v21; // r15d
  int SessionsToDisconnect; // eax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  unsigned int v26; // r14d
  unsigned int v27; // r12d
  _DWORD *v28; // r13
  int v29; // ebx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  int v33; // eax
  int v34; // eax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  struct ISessionManager **v38; // rcx
  struct ISessionManager *v40; // [rsp+40h] [rbp-28h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-20h] BYREF
  _QWORD v42[3]; // [rsp+50h] [rbp-18h] BYREF
  const char *v43; // [rsp+B0h] [rbp+48h] BYREF
  struct ISessionManager *v44; // [rsp+B8h] [rbp+50h] BYREF
  int v45; // [rsp+C0h] [rbp+58h] BYREF
  const char *v46; // [rsp+C8h] [rbp+60h] BYREF

  if ( (unsigned int)dword_180128170 > 4 )
  {
    LODWORD(v43) = *((_DWORD *)this + 416);
    v44 = (struct ISessionManager *)"CSessionArbitrationCacheMode::TryToCreateNewSession";
    v46 = "Status";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&dword_180109DAC,
      a3,
      a4,
      (__int64)&v46,
      (__int64)&v44,
      (__int64)&v43);
  }
  v45 = 0;
  v5 = 1;
  LODWORD(v44) = 1;
  pv = 0;
  LODWORD(v43) = 0;
  if ( !*((_DWORD *)this + 404) )
  {
    IsAppServer = CSessionArbitrationHelper::IsAppServer(
                    *(CSessionArbitrationHelper **)(*(_QWORD *)(*((_QWORD *)this + 199) + 1904LL) + 1592LL),
                    (int *)&v44);
    InstanceOfSessionManager = IsAppServer;
    if ( IsAppServer < 0 )
    {
      _DbgPrintMessage(
        8,
        "m_ptrHelperMgr->IsAppServer (TryToCreateNewSession) failed: 0x%x in %s",
        (unsigned int)IsAppServer,
        "CSessionArbitrationCacheMode::TryToCreateNewSession");
      return InstanceOfSessionManager;
    }
    if ( (_DWORD)v44 )
    {
      if ( !*((_QWORD *)this + 200) )
      {
        InstanceOfRemoteConnectionManager = GetInstanceOfRemoteConnectionManager((struct IRemoteConnectionManager **)this + 200);
        InstanceOfSessionManager = InstanceOfRemoteConnectionManager;
        if ( InstanceOfRemoteConnectionManager < 0 )
        {
          _DbgPrintMessage(
            8,
            "GetInstanceOfRemoteConnectionManager failed: 0x%x in %s",
            (unsigned int)InstanceOfRemoteConnectionManager,
            "CSessionArbitrationCacheMode::TryToCreateNewSession");
          return InstanceOfSessionManager;
        }
      }
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 200) + 184LL))(*((_QWORD *)this + 200))
        && !CSessionArbitrationDesktop::IsNewLogonExceptionSpecified(this) )
      {
        if ( (unsigned int)dword_180128170 > 4 )
        {
          v43 = "Machine is in drain mode, new session can not continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v9,
            (unsigned int)&dword_180109D84,
            v10,
            v11,
            (__int64)&v43);
        }
        v44 = (struct ISessionManager *)&qword_1800D7B88;
        CHelper::LogEvent(0xC000042E, 1u, 0, (const unsigned __int16 **)&v44);
        return (unsigned int)-2147017836;
      }
    }
  }
  v12 = (*(__int64 (__fastcall **)(CSessionArbitrationCacheMode *, __int64, __int64, int *))(*(_QWORD *)this + 56LL))(
          this,
          1,
          0xFFFFFFFFLL,
          &v45);
  if ( v12 >= 0 )
  {
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v43 = "License is available, continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v12,
        (unsigned int)&dword_180109D5C,
        v13,
        v14,
        (__int64)&v43);
    }
    v15 = CSessionArbitrationDesktop::PrepareContinueRequest(this);
    if ( v15 < 0 )
      _DbgPrintMessage(
        8,
        "PrepareContinueRequest failed: 0x%x in %s",
        v15,
        "CSessionArbitrationCacheMode::TryToCreateNewSession");
    goto LABEL_52;
  }
  if ( v12 != -2147017842 && v12 != -1073086445 )
  {
    if ( (unsigned int)dword_180128170 > 2 )
    {
      LODWORD(v43) = v12;
      v44 = (struct ISessionManager *)"Unexpected error in enforcement, terminating session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&byte_180109C97,
        v13,
        v14,
        (__int64)&v44,
        (__int64)&v43);
    }
    v16 = CSessionArbitrationDesktop::PrepareTerminateRequest(this);
    InstanceOfSessionManager = v16;
    if ( v16 < 0 )
      _DbgPrintMessage(
        8,
        "PrepareTerminateRequest failed: 0x%x in %s",
        (unsigned int)v16,
        "CSessionArbitrationCacheMode::TryToCreateNewSession");
    return InstanceOfSessionManager;
  }
  v40 = 0;
  LODWORD(v44) = 0;
  CUtils::GetInstanceOfSessionManager(&v40);
  (*(void (__fastcall **)(struct ISessionManager *, struct ISessionManager **))(*(_QWORD *)v40 + 96LL))(v40, &v44);
  if ( !*((_DWORD *)this + 418) || !*((_DWORD *)this + 404) && (_DWORD)v44 != *((_DWORD *)this + 416) )
  {
    v21 = 300;
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v46 = "No license is available, try disconnect request";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v17,
        (unsigned int)&dword_180109D34,
        v18,
        v19,
        (__int64)&v46);
    }
    while ( 1 )
    {
      SessionsToDisconnect = CSessionArbitrationCacheMode::GetSessionsToDisconnect(
                               this,
                               (int **)&pv,
                               (unsigned int *)&v43);
      InstanceOfSessionManager = SessionsToDisconnect;
      if ( SessionsToDisconnect < 0 )
        break;
      v26 = 0;
      v27 = (unsigned int)v43;
      if ( (_DWORD)v43 )
      {
        v28 = pv;
        do
        {
          if ( (unsigned int)dword_180128170 > 5 )
          {
            LODWORD(v46) = v28[v26];
            v42[0] = "Logging off session id";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)word_180109D02,
              v24,
              v25,
              (__int64)v42,
              (__int64)&v46);
          }
          CSessionArbitrationDesktop::TryToLogoffSession(this, v28[v26++]);
        }
        while ( v26 < v27 );
      }
      v29 = (*(__int64 (__fastcall **)(CSessionArbitrationCacheMode *, __int64, __int64, int *))(*(_QWORD *)this + 56LL))(
              this,
              1,
              0xFFFFFFFFLL,
              &v45);
      CSessionArbitrationHelperMgr::GetSessionForArbitration(*((_QWORD *)this + 199), 3, &v43, &pv, 0);
      if ( (unsigned int)v43 <= 2 )
        goto LABEL_49;
      if ( v29 != -2147017842 )
      {
        if ( (unsigned int)dword_180128170 > 5 )
        {
          v43 = "Got a license, we can continue now.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v30,
            (unsigned int)&word_180109CBE,
            v31,
            v32,
            (__int64)&v43);
        }
LABEL_49:
        v34 = CSessionArbitrationDesktop::PrepareContinueRequest(this);
        InstanceOfSessionManager = v34;
        if ( v34 < 0 )
        {
          _DbgPrintMessage(
            8,
            "PrepareContinueRequest failed: 0x%x in %s",
            v34,
            "CSessionArbitrationCacheMode::TryToCreateNewSession");
          goto LABEL_31;
        }
LABEL_51:
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v40);
        if ( !v5 )
          goto LABEL_60;
LABEL_52:
        v44 = 0;
        InstanceOfSessionManager = CUtils::GetInstanceOfSessionManager(&v44);
        if ( *((_DWORD *)this + 418) )
          InstanceOfSessionManager = (*(__int64 (__fastcall **)(struct ISessionManager *, _QWORD))(*(_QWORD *)v44 + 104LL))(
                                       v44,
                                       *((unsigned int *)this + 416));
        if ( (unsigned int)dword_180128170 > 5 )
        {
          LODWORD(v43) = InstanceOfSessionManager;
          v46 = "Marked cache session";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v35,
            (unsigned int)qword_180109C70,
            v36,
            v37,
            (__int64)&v46,
            (__int64)&v43);
        }
        v38 = &v44;
LABEL_59:
        SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(v38);
LABEL_60:
        if ( pv )
          CoTaskMemFree(pv);
        return InstanceOfSessionManager;
      }
      if ( (unsigned int)dword_180128170 > 5 )
      {
        v42[0] = "We don't have a license yet for the new session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v30,
          (unsigned int)qword_180109CE0,
          v31,
          v32,
          (__int64)v42);
      }
      Sleep(0x3E8u);
      if ( --v21 <= 0 )
      {
        v5 = 0;
        v33 = CSessionArbitrationDesktop::PrepareTerminateRequest(this);
        InstanceOfSessionManager = v33;
        if ( v33 >= 0 )
          goto LABEL_51;
        _DbgPrintMessage(
          8,
          "PrepareTerminateRequest failed: 0x%x in %s",
          (unsigned int)v33,
          "CSessionArbitrationCacheMode::TryToCreateNewSession");
LABEL_58:
        v38 = &v40;
        goto LABEL_59;
      }
    }
    _DbgPrintMessage(
      8,
      "GetSessionsToDisconnect failed: 0x%x in %s",
      (unsigned int)SessionsToDisconnect,
      "CSessionArbitrationCacheMode::TryToCreateNewSession");
    goto LABEL_58;
  }
  v20 = CSessionArbitrationDesktop::PrepareContinueRequest(this);
  InstanceOfSessionManager = v20;
  if ( v20 >= 0 )
  {
LABEL_31:
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v40);
    goto LABEL_52;
  }
  _DbgPrintMessage(
    8,
    "PrepareContinueRequest failed: 0x%x in %s",
    v20,
    "CSessionArbitrationCacheMode::TryToCreateNewSession");
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v40);
  return InstanceOfSessionManager;
}

```

## disassembly

```asm
0x180069848  push    rbp
0x18006984a  push    rbx
0x18006984b  push    rsi
0x18006984c  push    rdi
0x18006984d  push    r12
0x18006984f  push    r13
0x180069851  push    r14
0x180069853  push    r15
0x180069855  mov     rbp, rsp
0x180069858  sub     rsp, 68h
0x18006985c  mov     rdi, rcx
0x18006985f  mov     eax, cs:dword_180128170
0x180069865  lea     r12, aCsessionarbitr_45; "CSessionArbitrationCacheMode::TryToCrea"...
0x18006986c  cmp     eax, 4
0x18006986f  jbe     short loc_1800698B0
0x180069871  mov     eax, [rcx+680h]
0x180069877  mov     dword ptr [rbp+arg_0], eax
0x18006987a  mov     [rbp+arg_8], r12
0x18006987e  lea     rax, aStatus; "Status"
0x180069885  mov     [rbp+arg_18], rax
0x180069889  lea     rax, [rbp+arg_0]
0x18006988d  mov     [rsp+68h+var_38], rax
0x180069892  lea     rax, [rbp+arg_8]
0x180069896  mov     [rsp+68h+var_40], rax
0x18006989b  lea     rax, [rbp+arg_18]
0x18006989f  mov     [rsp+68h+var_48], rax
0x1800698a4  lea     rdx, dword_180109DAC
0x1800698ab  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800698b0  xor     r13d, r13d
0x1800698b3  mov     [rbp+arg_10], r13d
0x1800698b7  lea     esi, [r13+1]
0x1800698bb  mov     dword ptr [rbp+arg_8], esi
0x1800698be  mov     [rbp+pv], r13
0x1800698c2  mov     dword ptr [rbp+arg_0], r13d
0x1800698c6  cmp     [rdi+650h], r13d
0x1800698cd  jnz     loc_1800699B5
0x1800698d3  mov     rax, [rdi+638h]
0x1800698da  mov     rcx, [rax+770h]
0x1800698e1  lea     rdx, [rbp+arg_8]; int *
0x1800698e5  mov     rcx, [rcx+638h]; this
0x1800698ec  call    ?IsAppServer@CSessionArbitrationHelper@@UEAAJPEAH@Z; CSessionArbitrationHelper::IsAppServer(int *)
0x1800698f1  mov     ebx, eax
0x1800698f3  test    eax, eax
0x1800698f5  jns     short loc_180069913
0x1800698f7  lea     rdx, aMPtrhelpermgrI; "m_ptrHelperMgr->IsAppServer (TryToCreat"...
0x1800698fe  mov     r9, r12
0x180069901  mov     r8d, eax
0x180069904  mov     ecx, 8; int
0x180069909  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006990e  jmp     loc_180069D76
0x180069913  cmp     dword ptr [rbp+arg_8], r13d
0x180069917  jz      loc_1800699B5
0x18006991d  lea     r14, [rdi+640h]
0x180069924  cmp     [r14], r13
0x180069927  jnz     short loc_180069940
0x180069929  mov     rcx, r14; struct IRemoteConnectionManager **
0x18006992c  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180069931  mov     ebx, eax
0x180069933  test    eax, eax
0x180069935  jns     short loc_180069940
0x180069937  lea     rdx, aGetinstanceofr; "GetInstanceOfRemoteConnectionManager fa"...
0x18006993e  jmp     short loc_1800698FE
0x180069940  mov     rcx, [r14]
0x180069943  mov     rax, [rcx]
0x180069946  mov     rax, [rax+0B8h]
0x18006994d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069952  test    al, al
0x180069954  jz      short loc_1800699B5
0x180069956  mov     rcx, rdi; this
0x180069959  call    ?IsNewLogonExceptionSpecified@CSessionArbitrationDesktop@@IEAAEXZ; CSessionArbitrationDesktop::IsNewLogonExceptionSpecified(void)
0x18006995e  test    al, al
0x180069960  jnz     short loc_1800699B5
0x180069962  mov     eax, cs:dword_180128170
0x180069968  cmp     eax, 4
0x18006996b  jbe     short loc_18006998D
0x18006996d  lea     rax, aMachineIsInDra; "Machine is in drain mode, new session c"...
0x180069974  mov     [rbp+arg_0], rax
0x180069978  lea     rax, [rbp+arg_0]
0x18006997c  mov     [rsp+68h+var_48], rax
0x180069981  lea     rdx, dword_180109D84
0x180069988  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006998d  lea     rax, qword_1800D7B88
0x180069994  mov     [rbp+arg_8], rax
0x180069998  xor     r8d, r8d; unsigned __int16
0x18006999b  mov     edx, esi; unsigned __int16
0x18006999d  lea     r9, [rbp+arg_8]; unsigned __int16 **
0x1800699a1  mov     ecx, 0C000042Eh; unsigned int
0x1800699a6  call    ?LogEvent@CHelper@@SAJIGGPEAPEBG@Z; CHelper::LogEvent(uint,ushort,ushort,ushort const * *)
0x1800699ab  mov     ebx, 80071B94h
0x1800699b0  jmp     loc_180069D76
0x1800699b5  mov     rax, [rdi]
0x1800699b8  lea     r9, [rbp+arg_10]
0x1800699bc  or      r8d, 0FFFFFFFFh
0x1800699c0  mov     edx, esi
0x1800699c2  mov     rcx, rdi
0x1800699c5  mov     rax, [rax+38h]
0x1800699c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699ce  mov     ecx, eax
0x1800699d0  test    eax, eax
0x1800699d2  js      short loc_180069A2B
0x1800699d4  mov     eax, cs:dword_180128170
0x1800699da  cmp     eax, 4
0x1800699dd  jbe     short loc_1800699FF
0x1800699df  lea     rax, aLicenseIsAvail_0; "License is available, continue"
0x1800699e6  mov     [rbp+arg_0], rax
0x1800699ea  lea     rax, [rbp+arg_0]
0x1800699ee  mov     [rsp+68h+var_48], rax
0x1800699f3  lea     rdx, dword_180109D5C
0x1800699fa  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800699ff  mov     rcx, rdi; this
0x180069a02  call    ?PrepareContinueRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareContinueRequest(void)
0x180069a07  test    eax, eax
0x180069a09  jns     loc_180069CD4
0x180069a0f  mov     r9, r12
0x180069a12  mov     r8d, eax
0x180069a15  lea     rdx, aPreparecontinu; "PrepareContinueRequest failed: 0x%x in "...
0x180069a1c  mov     ecx, 8; int
0x180069a21  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180069a26  jmp     loc_180069CD4
0x180069a2b  cmp     ecx, 80071B8Eh
0x180069a31  jz      short loc_180069A90
0x180069a33  cmp     ecx, 0C00A0013h
0x180069a39  jz      short loc_180069A90
0x180069a3b  mov     eax, cs:dword_180128170
0x180069a41  cmp     eax, 2
0x180069a44  jbe     short loc_180069A72
0x180069a46  mov     dword ptr [rbp+arg_0], ecx
0x180069a49  lea     rax, aUnexpectedErro; "Unexpected error in enforcement, termin"...
0x180069a50  mov     [rbp+arg_8], rax
0x180069a54  lea     rax, [rbp+arg_0]
0x180069a58  mov     [rsp+68h+var_40], rax
0x180069a5d  lea     rax, [rbp+arg_8]
0x180069a61  mov     [rsp+68h+var_48], rax
0x180069a66  lea     rdx, byte_180109C97
0x180069a6d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180069a72  mov     rcx, rdi; this
0x180069a75  call    ?PrepareTerminateRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareTerminateRequest(void)
0x180069a7a  mov     ebx, eax
0x180069a7c  test    eax, eax
0x180069a7e  jns     loc_180069D76
0x180069a84  lea     rdx, aPreparetermina_1; "PrepareTerminateRequest failed: 0x%x in"...
0x180069a8b  jmp     loc_1800698FE
0x180069a90  mov     [rbp+var_28], r13
0x180069a94  mov     dword ptr [rbp+arg_8], r13d
0x180069a98  lea     rcx, [rbp+var_28]; struct ISessionManager **
0x180069a9c  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x180069aa1  mov     rcx, [rbp+var_28]
0x180069aa5  mov     rax, [rcx]
0x180069aa8  lea     rdx, [rbp+arg_8]
0x180069aac  mov     rax, [rax+60h]
0x180069ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069ab5  cmp     [rdi+688h], r13d
0x180069abc  jz      short loc_180069B14
0x180069abe  cmp     [rdi+650h], r13d
0x180069ac5  jnz     short loc_180069AD2
0x180069ac7  mov     eax, [rdi+680h]
0x180069acd  cmp     dword ptr [rbp+arg_8], eax
0x180069ad0  jnz     short loc_180069B14
0x180069ad2  mov     rcx, rdi; this
0x180069ad5  call    ?PrepareContinueRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareContinueRequest(void)
0x180069ada  mov     ebx, eax
0x180069adc  test    eax, eax
0x180069ade  jns     short loc_180069B06
0x180069ae0  mov     r9, r12
0x180069ae3  mov     r8d, eax
0x180069ae6  lea     rdx, aPreparecontinu; "PrepareContinueRequest failed: 0x%x in "...
0x180069aed  mov     ecx, 8; int
0x180069af2  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180069af7  nop
0x180069af8  lea     rcx, [rbp+var_28]; void *
0x180069afc  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180069b01  jmp     loc_180069D76
0x180069b06  lea     rcx, [rbp+var_28]; void *
0x180069b0a  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180069b0f  jmp     loc_180069CD4
0x180069b14  mov     r15d, 12Ch
0x180069b1a  mov     eax, cs:dword_180128170
0x180069b20  cmp     eax, 4
0x180069b23  jbe     short loc_180069B45
0x180069b25  lea     rax, aNoLicenseIsAva_0; "No license is available, try disconnect"...
0x180069b2c  mov     [rbp+arg_18], rax
0x180069b30  lea     rax, [rbp+arg_18]
0x180069b34  mov     [rsp+68h+var_48], rax
0x180069b39  lea     rdx, dword_180109D34
0x180069b40  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180069b45  lea     r8, [rbp+arg_0]; unsigned int *
0x180069b49  lea     rdx, [rbp+pv]; int **
0x180069b4d  mov     rcx, rdi; this
0x180069b50  call    ?GetSessionsToDisconnect@CSessionArbitrationCacheMode@@QEAAJPEAPEAJPEAK@Z; CSessionArbitrationCacheMode::GetSessionsToDisconnect(long * *,ulong *)
0x180069b55  mov     ebx, eax
0x180069b57  test    eax, eax
0x180069b59  js      loc_180069D42
0x180069b5f  mov     r14d, r13d
0x180069b62  mov     r12d, dword ptr [rbp+arg_0]
0x180069b66  test    r12d, r12d
0x180069b69  jz      short loc_180069BC6
0x180069b6b  mov     r13, [rbp+pv]
0x180069b6f  mov     eax, cs:dword_180128170
0x180069b75  mov     ebx, r14d
0x180069b78  cmp     eax, 5
0x180069b7b  jbe     short loc_180069BAE
0x180069b7d  mov     eax, [r13+rbx*4+0]
0x180069b82  mov     dword ptr [rbp+arg_18], eax
0x180069b85  lea     rax, aLoggingOffSess_0; "Logging off session id"
0x180069b8c  mov     [rbp+var_18], rax
0x180069b90  lea     rax, [rbp+arg_18]
0x180069b94  mov     [rsp+68h+var_40], rax
0x180069b99  lea     rax, [rbp+var_18]
0x180069b9d  mov     [rsp+68h+var_48], rax
0x180069ba2  lea     rdx, word_180109D02
0x180069ba9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180069bae  mov     edx, [r13+rbx*4+0]; int
0x180069bb3  mov     rcx, rdi; this
0x180069bb6  call    ?TryToLogoffSession@CSessionArbitrationDesktop@@IEAAJJ@Z; CSessionArbitrationDesktop::TryToLogoffSession(long)
0x180069bbb  add     r14d, esi
0x180069bbe  cmp     r14d, r12d
0x180069bc1  jb      short loc_180069B6F
0x180069bc3  xor     r13d, r13d
0x180069bc6  mov     rax, [rdi]
0x180069bc9  lea     r9, [rbp+arg_10]
0x180069bcd  or      r8d, 0FFFFFFFFh
0x180069bd1  mov     edx, esi
0x180069bd3  mov     rcx, rdi
0x180069bd6  mov     rax, [rax+38h]
0x180069bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069bdf  mov     ebx, eax
0x180069be1  mov     [rsp+68h+var_48], r13
0x180069be6  lea     r9, [rbp+pv]
0x180069bea  lea     r8, [rbp+arg_0]
0x180069bee  mov     edx, 3
0x180069bf3  mov     rcx, [rdi+638h]
0x180069bfa  call    ?GetSessionForArbitration@CSessionArbitrationHelperMgr@@UEAAJW4__MIDL___MIDL_itf_sessarbitrationhelper_0000_0000_0001@@PEAKPEAPEAJPEAUISessionEnumFilter@@@Z; CSessionArbitrationHelperMgr::GetSessionForArbitration(__MIDL___MIDL_itf_sessarbitrationhelper_0000_0000_0001,ulong *,long * *,ISessionEnumFilter *)
0x180069bff  cmp     dword ptr [rbp+arg_0], 2
0x180069c03  jbe     loc_180069C95
0x180069c09  mov     eax, cs:dword_180128170
0x180069c0f  cmp     ebx, 80071B8Eh
0x180069c15  jnz     short loc_180069C70
0x180069c17  cmp     eax, 5
0x180069c1a  jbe     short loc_180069C3C
0x180069c1c  lea     rax, aWeDonTHaveALic; "We don't have a license yet for the new"...
0x180069c23  mov     [rbp+var_18], rax
0x180069c27  lea     rax, [rbp+var_18]
0x180069c2b  mov     [rsp+68h+var_48], rax
0x180069c30  lea     rdx, qword_180109CE0
0x180069c37  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180069c3c  mov     ecx, 3E8h; dwMilliseconds
0x180069c41  call    cs:__imp_Sleep
0x180069c47  sub     r15d, esi
0x180069c4a  test    r15d, r15d
0x180069c4d  jg      loc_180069B45
0x180069c53  mov     esi, r13d
0x180069c56  mov     rcx, rdi; this
0x180069c59  call    ?PrepareTerminateRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareTerminateRequest(void)
0x180069c5e  mov     ebx, eax
0x180069c60  test    eax, eax
0x180069c62  jns     short loc_180069CC3
0x180069c64  lea     rdx, aPreparetermina_1; "PrepareTerminateRequest failed: 0x%x in"...
0x180069c6b  jmp     loc_180069D49
0x180069c70  cmp     eax, 5
0x180069c73  jbe     short loc_180069C95
0x180069c75  lea     rax, aGotALicenseWeC; "Got a license, we can continue now."
0x180069c7c  mov     [rbp+arg_0], rax
0x180069c80  lea     rax, [rbp+arg_0]
0x180069c84  mov     [rsp+68h+var_48], rax
0x180069c89  lea     rdx, word_180109CBE
0x180069c90  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180069c95  mov     rcx, rdi; this
0x180069c98  call    ?PrepareContinueRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareContinueRequest(void)
0x180069c9d  mov     ebx, eax
0x180069c9f  test    eax, eax
0x180069ca1  jns     short loc_180069CC3
0x180069ca3  lea     r9, aCsessionarbitr_45; "CSessionArbitrationCacheMode::TryToCrea"...
0x180069caa  mov     r8d, eax
0x180069cad  lea     rdx, aPreparecontinu; "PrepareContinueRequest failed: 0x%x in "...
0x180069cb4  mov     ecx, 8; int
0x180069cb9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180069cbe  jmp     loc_180069B06
0x180069cc3  lea     rcx, [rbp+var_28]; void *
0x180069cc7  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x180069ccc  test    esi, esi
0x180069cce  jz      loc_180069D67
0x180069cd4  mov     [rbp+arg_8], r13
0x180069cd8  lea     rcx, [rbp+arg_8]; struct ISessionManager **
0x180069cdc  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x180069ce1  mov     ebx, eax
0x180069ce3  cmp     [rdi+688h], r13d
0x180069cea  jz      short loc_180069D04
0x180069cec  mov     rcx, [rbp+arg_8]
0x180069cf0  mov     rax, [rcx]
0x180069cf3  mov     edx, [rdi+680h]
0x180069cf9  mov     rax, [rax+68h]
0x180069cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069d02  mov     ebx, eax
0x180069d04  mov     eax, cs:dword_180128170
0x180069d0a  cmp     eax, 5
0x180069d0d  jbe     short loc_180069D3C
0x180069d0f  mov     dword ptr [rbp+arg_0], ebx
0x180069d12  lea     rax, aMarkedCacheSes; "Marked cache session"
0x180069d19  mov     [rbp+arg_18], rax
0x180069d1d  lea     rax, [rbp+arg_0]
  ... truncated ...
```
