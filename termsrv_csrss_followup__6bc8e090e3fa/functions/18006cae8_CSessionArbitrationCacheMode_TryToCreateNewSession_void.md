# CSessionArbitrationCacheMode::TryToCreateNewSession(void)

- ea: `0x18006cae8`
- end: `0x18006d036`
- name: `?TryToCreateNewSession@CSessionArbitrationCacheMode@@QEAAJXZ`
- size: `1358`
- prototype: `__int64 __fastcall(CSessionArbitrationCacheMode *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18006d5cc`

## callees

- `0x180001294`
- `0x180009940`
- `0x18000c2a0`
- `0x180013948`
- `0x1800139c0`
- `0x1800146c8`
- `0x180015310`
- `0x18005d500`
- `0x18006a238`
- `0x18006bcec`
- `0x18006bf68`
- `0x18006c448`
- `0x18006cae8`
- `0x18006d4c0`
- `0x18007b410`
- `0x1800c1ac0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006cee1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006cee1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d016`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006d016`

## string_xrefs

- `0x18006cb97`: `m_ptrHelperMgr->IsAppServer (TryToCreateNewSession) failed: 0x%x in %s`
- `0x18006cb05`: `CSessionArbitrationCacheMode::TryToCreateNewSession`
- `0x18006cf49`: `CSessionArbitrationCacheMode::TryToCreateNewSession`
- `0x18006cfef`: `CSessionArbitrationCacheMode::TryToCreateNewSession`
- `0x18006cfb8`: `Marked cache session`

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

  if ( (unsigned int)dword_18012E170 > 4 )
  {
    LODWORD(v43) = *((_DWORD *)this + 416);
    v44 = (struct ISessionManager *)"CSessionArbitrationCacheMode::TryToCreateNewSession";
    v46 = "Status";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&dword_18010FE2C,
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
        if ( (unsigned int)dword_18012E170 > 4 )
        {
          v43 = "Machine is in drain mode, new session can not continue";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v9,
            (unsigned int)&dword_18010FE04,
            v10,
            v11,
            (__int64)&v43);
        }
        v44 = (struct ISessionManager *)&qword_1800DDBD8;
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
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v43 = "License is available, continue";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v12,
        (unsigned int)&dword_18010FDDC,
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
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      LODWORD(v43) = v12;
      v44 = (struct ISessionManager *)"Unexpected error in enforcement, terminating session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&byte_18010FD17,
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
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v46 = "No license is available, try disconnect request";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v17,
        (unsigned int)&dword_18010FDB4,
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
          if ( (unsigned int)dword_18012E170 > 5 )
          {
            LODWORD(v46) = v28[v26];
            v42[0] = "Logging off session id";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v23,
              (unsigned int)word_18010FD82,
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
        if ( (unsigned int)dword_18012E170 > 5 )
        {
          v43 = "Got a license, we can continue now.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v30,
            (unsigned int)&word_18010FD3E,
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
        if ( (unsigned int)dword_18012E170 > 5 )
        {
          LODWORD(v43) = InstanceOfSessionManager;
          v46 = "Marked cache session";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v35,
            (unsigned int)qword_18010FCF0,
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
      if ( (unsigned int)dword_18012E170 > 5 )
      {
        v42[0] = "We don't have a license yet for the new session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v30,
          (unsigned int)qword_18010FD60,
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
0x18006cae8  push    rbp
0x18006caea  push    rbx
0x18006caeb  push    rsi
0x18006caec  push    rdi
0x18006caed  push    r12
0x18006caef  push    r13
0x18006caf1  push    r14
0x18006caf3  push    r15
0x18006caf5  mov     rbp, rsp
0x18006caf8  sub     rsp, 68h
0x18006cafc  mov     rdi, rcx
0x18006caff  mov     eax, cs:dword_18012E170
0x18006cb05  lea     r12, aCsessionarbitr_45; "CSessionArbitrationCacheMode::TryToCrea"...
0x18006cb0c  cmp     eax, 4
0x18006cb0f  jbe     short loc_18006CB50
0x18006cb11  mov     eax, [rcx+680h]
0x18006cb17  mov     dword ptr [rbp+arg_0], eax
0x18006cb1a  mov     [rbp+arg_8], r12
0x18006cb1e  lea     rax, aStatus; "Status"
0x18006cb25  mov     [rbp+arg_18], rax
0x18006cb29  lea     rax, [rbp+arg_0]
0x18006cb2d  mov     [rsp+68h+var_38], rax
0x18006cb32  lea     rax, [rbp+arg_8]
0x18006cb36  mov     [rsp+68h+var_40], rax
0x18006cb3b  lea     rax, [rbp+arg_18]
0x18006cb3f  mov     [rsp+68h+var_48], rax
0x18006cb44  lea     rdx, dword_18010FE2C
0x18006cb4b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006cb50  xor     r13d, r13d
0x18006cb53  mov     [rbp+arg_10], r13d
0x18006cb57  lea     esi, [r13+1]
0x18006cb5b  mov     dword ptr [rbp+arg_8], esi
0x18006cb5e  mov     [rbp+pv], r13
0x18006cb62  mov     dword ptr [rbp+arg_0], r13d
0x18006cb66  cmp     [rdi+650h], r13d
0x18006cb6d  jnz     loc_18006CC55
0x18006cb73  mov     rax, [rdi+638h]
0x18006cb7a  mov     rcx, [rax+770h]
0x18006cb81  lea     rdx, [rbp+arg_8]; int *
0x18006cb85  mov     rcx, [rcx+638h]; this
0x18006cb8c  call    ?IsAppServer@CSessionArbitrationHelper@@UEAAJPEAH@Z; CSessionArbitrationHelper::IsAppServer(int *)
0x18006cb91  mov     ebx, eax
0x18006cb93  test    eax, eax
0x18006cb95  jns     short loc_18006CBB3
0x18006cb97  lea     rdx, aMPtrhelpermgrI; "m_ptrHelperMgr->IsAppServer (TryToCreat"...
0x18006cb9e  mov     r9, r12
0x18006cba1  mov     r8d, eax
0x18006cba4  mov     ecx, 8; int
0x18006cba9  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006cbae  jmp     loc_18006D022
0x18006cbb3  cmp     dword ptr [rbp+arg_8], r13d
0x18006cbb7  jz      loc_18006CC55
0x18006cbbd  lea     r14, [rdi+640h]
0x18006cbc4  cmp     [r14], r13
0x18006cbc7  jnz     short loc_18006CBE0
0x18006cbc9  mov     rcx, r14; struct IRemoteConnectionManager **
0x18006cbcc  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x18006cbd1  mov     ebx, eax
0x18006cbd3  test    eax, eax
0x18006cbd5  jns     short loc_18006CBE0
0x18006cbd7  lea     rdx, aGetinstanceofr; "GetInstanceOfRemoteConnectionManager fa"...
0x18006cbde  jmp     short loc_18006CB9E
0x18006cbe0  mov     rcx, [r14]
0x18006cbe3  mov     rax, [rcx]
0x18006cbe6  mov     rax, [rax+0B8h]
0x18006cbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cbf2  test    al, al
0x18006cbf4  jz      short loc_18006CC55
0x18006cbf6  mov     rcx, rdi; this
0x18006cbf9  call    ?IsNewLogonExceptionSpecified@CSessionArbitrationDesktop@@IEAAEXZ; CSessionArbitrationDesktop::IsNewLogonExceptionSpecified(void)
0x18006cbfe  test    al, al
0x18006cc00  jnz     short loc_18006CC55
0x18006cc02  mov     eax, cs:dword_18012E170
0x18006cc08  cmp     eax, 4
0x18006cc0b  jbe     short loc_18006CC2D
0x18006cc0d  lea     rax, aMachineIsInDra; "Machine is in drain mode, new session c"...
0x18006cc14  mov     [rbp+arg_0], rax
0x18006cc18  lea     rax, [rbp+arg_0]
0x18006cc1c  mov     [rsp+68h+var_48], rax
0x18006cc21  lea     rdx, dword_18010FE04
0x18006cc28  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006cc2d  lea     rax, qword_1800DDBD8
0x18006cc34  mov     [rbp+arg_8], rax
0x18006cc38  xor     r8d, r8d; unsigned __int16
0x18006cc3b  mov     edx, esi; unsigned __int16
0x18006cc3d  lea     r9, [rbp+arg_8]; unsigned __int16 **
0x18006cc41  mov     ecx, 0C000042Eh; unsigned int
0x18006cc46  call    ?LogEvent@CHelper@@SAJIGGPEAPEBG@Z; CHelper::LogEvent(uint,ushort,ushort,ushort const * *)
0x18006cc4b  mov     ebx, 80071B94h
0x18006cc50  jmp     loc_18006D022
0x18006cc55  mov     rax, [rdi]
0x18006cc58  lea     r9, [rbp+arg_10]
0x18006cc5c  or      r8d, 0FFFFFFFFh
0x18006cc60  mov     edx, esi
0x18006cc62  mov     rcx, rdi
0x18006cc65  mov     rax, [rax+38h]
0x18006cc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cc6e  mov     ecx, eax
0x18006cc70  test    eax, eax
0x18006cc72  js      short loc_18006CCCB
0x18006cc74  mov     eax, cs:dword_18012E170
0x18006cc7a  cmp     eax, 4
0x18006cc7d  jbe     short loc_18006CC9F
0x18006cc7f  lea     rax, aLicenseIsAvail_0; "License is available, continue"
0x18006cc86  mov     [rbp+arg_0], rax
0x18006cc8a  lea     rax, [rbp+arg_0]
0x18006cc8e  mov     [rsp+68h+var_48], rax
0x18006cc93  lea     rdx, dword_18010FDDC
0x18006cc9a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006cc9f  mov     rcx, rdi; this
0x18006cca2  call    ?PrepareContinueRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareContinueRequest(void)
0x18006cca7  test    eax, eax
0x18006cca9  jns     loc_18006CF7A
0x18006ccaf  mov     r9, r12
0x18006ccb2  mov     r8d, eax
0x18006ccb5  lea     rdx, aPreparecontinu; "PrepareContinueRequest failed: 0x%x in "...
0x18006ccbc  mov     ecx, 8; int
0x18006ccc1  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006ccc6  jmp     loc_18006CF7A
0x18006cccb  cmp     ecx, 80071B8Eh
0x18006ccd1  jz      short loc_18006CD30
0x18006ccd3  cmp     ecx, 0C00A0013h
0x18006ccd9  jz      short loc_18006CD30
0x18006ccdb  mov     eax, cs:dword_18012E170
0x18006cce1  cmp     eax, 2
0x18006cce4  jbe     short loc_18006CD12
0x18006cce6  mov     dword ptr [rbp+arg_0], ecx
0x18006cce9  lea     rax, aUnexpectedErro; "Unexpected error in enforcement, termin"...
0x18006ccf0  mov     [rbp+arg_8], rax
0x18006ccf4  lea     rax, [rbp+arg_0]
0x18006ccf8  mov     [rsp+68h+var_40], rax
0x18006ccfd  lea     rax, [rbp+arg_8]
0x18006cd01  mov     [rsp+68h+var_48], rax
0x18006cd06  lea     rdx, byte_18010FD17
0x18006cd0d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006cd12  mov     rcx, rdi; this
0x18006cd15  call    ?PrepareTerminateRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareTerminateRequest(void)
0x18006cd1a  mov     ebx, eax
0x18006cd1c  test    eax, eax
0x18006cd1e  jns     loc_18006D022
0x18006cd24  lea     rdx, aPreparetermina_1; "PrepareTerminateRequest failed: 0x%x in"...
0x18006cd2b  jmp     loc_18006CB9E
0x18006cd30  mov     [rbp+var_28], r13
0x18006cd34  mov     dword ptr [rbp+arg_8], r13d
0x18006cd38  lea     rcx, [rbp+var_28]; struct ISessionManager **
0x18006cd3c  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x18006cd41  mov     rcx, [rbp+var_28]
0x18006cd45  mov     rax, [rcx]
0x18006cd48  lea     rdx, [rbp+arg_8]
0x18006cd4c  mov     rax, [rax+60h]
0x18006cd50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cd55  cmp     [rdi+688h], r13d
0x18006cd5c  jz      short loc_18006CDB4
0x18006cd5e  cmp     [rdi+650h], r13d
0x18006cd65  jnz     short loc_18006CD72
0x18006cd67  mov     eax, [rdi+680h]
0x18006cd6d  cmp     dword ptr [rbp+arg_8], eax
0x18006cd70  jnz     short loc_18006CDB4
0x18006cd72  mov     rcx, rdi; this
0x18006cd75  call    ?PrepareContinueRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareContinueRequest(void)
0x18006cd7a  mov     ebx, eax
0x18006cd7c  test    eax, eax
0x18006cd7e  jns     short loc_18006CDA6
0x18006cd80  mov     r9, r12
0x18006cd83  mov     r8d, eax
0x18006cd86  lea     rdx, aPreparecontinu; "PrepareContinueRequest failed: 0x%x in "...
0x18006cd8d  mov     ecx, 8; int
0x18006cd92  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006cd97  nop
0x18006cd98  lea     rcx, [rbp+var_28]; void *
0x18006cd9c  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18006cda1  jmp     loc_18006D022
0x18006cda6  lea     rcx, [rbp+var_28]; void *
0x18006cdaa  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18006cdaf  jmp     loc_18006CF7A
0x18006cdb4  mov     r15d, 12Ch
0x18006cdba  mov     eax, cs:dword_18012E170
0x18006cdc0  cmp     eax, 4
0x18006cdc3  jbe     short loc_18006CDE5
0x18006cdc5  lea     rax, aNoLicenseIsAva_0; "No license is available, try disconnect"...
0x18006cdcc  mov     [rbp+arg_18], rax
0x18006cdd0  lea     rax, [rbp+arg_18]
0x18006cdd4  mov     [rsp+68h+var_48], rax
0x18006cdd9  lea     rdx, dword_18010FDB4
0x18006cde0  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006cde5  lea     r8, [rbp+arg_0]; unsigned int *
0x18006cde9  lea     rdx, [rbp+pv]; int **
0x18006cded  mov     rcx, rdi; this
0x18006cdf0  call    ?GetSessionsToDisconnect@CSessionArbitrationCacheMode@@QEAAJPEAPEAJPEAK@Z; CSessionArbitrationCacheMode::GetSessionsToDisconnect(long * *,ulong *)
0x18006cdf5  mov     ebx, eax
0x18006cdf7  test    eax, eax
0x18006cdf9  js      loc_18006CFE8
0x18006cdff  mov     r14d, r13d
0x18006ce02  mov     r12d, dword ptr [rbp+arg_0]
0x18006ce06  test    r12d, r12d
0x18006ce09  jz      short loc_18006CE66
0x18006ce0b  mov     r13, [rbp+pv]
0x18006ce0f  mov     eax, cs:dword_18012E170
0x18006ce15  mov     ebx, r14d
0x18006ce18  cmp     eax, 5
0x18006ce1b  jbe     short loc_18006CE4E
0x18006ce1d  mov     eax, [r13+rbx*4+0]
0x18006ce22  mov     dword ptr [rbp+arg_18], eax
0x18006ce25  lea     rax, aLoggingOffSess_0; "Logging off session id"
0x18006ce2c  mov     [rbp+var_18], rax
0x18006ce30  lea     rax, [rbp+arg_18]
0x18006ce34  mov     [rsp+68h+var_40], rax
0x18006ce39  lea     rax, [rbp+var_18]
0x18006ce3d  mov     [rsp+68h+var_48], rax
0x18006ce42  lea     rdx, word_18010FD82
0x18006ce49  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18006ce4e  mov     edx, [r13+rbx*4+0]; int
0x18006ce53  mov     rcx, rdi; this
0x18006ce56  call    ?TryToLogoffSession@CSessionArbitrationDesktop@@IEAAJJ@Z; CSessionArbitrationDesktop::TryToLogoffSession(long)
0x18006ce5b  add     r14d, esi
0x18006ce5e  cmp     r14d, r12d
0x18006ce61  jb      short loc_18006CE0F
0x18006ce63  xor     r13d, r13d
0x18006ce66  mov     rax, [rdi]
0x18006ce69  lea     r9, [rbp+arg_10]
0x18006ce6d  or      r8d, 0FFFFFFFFh
0x18006ce71  mov     edx, esi
0x18006ce73  mov     rcx, rdi
0x18006ce76  mov     rax, [rax+38h]
0x18006ce7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ce7f  mov     ebx, eax
0x18006ce81  mov     [rsp+68h+var_48], r13
0x18006ce86  lea     r9, [rbp+pv]
0x18006ce8a  lea     r8, [rbp+arg_0]
0x18006ce8e  mov     edx, 3
0x18006ce93  mov     rcx, [rdi+638h]
0x18006ce9a  call    ?GetSessionForArbitration@CSessionArbitrationHelperMgr@@UEAAJW4__MIDL___MIDL_itf_sessarbitrationhelper_0000_0000_0001@@PEAKPEAPEAJPEAUISessionEnumFilter@@@Z; CSessionArbitrationHelperMgr::GetSessionForArbitration(__MIDL___MIDL_itf_sessarbitrationhelper_0000_0000_0001,ulong *,long * *,ISessionEnumFilter *)
0x18006ce9f  cmp     dword ptr [rbp+arg_0], 2
0x18006cea3  jbe     loc_18006CF3B
0x18006cea9  mov     eax, cs:dword_18012E170
0x18006ceaf  cmp     ebx, 80071B8Eh
0x18006ceb5  jnz     short loc_18006CF16
0x18006ceb7  cmp     eax, 5
0x18006ceba  jbe     short loc_18006CEDC
0x18006cebc  lea     rax, aWeDonTHaveALic; "We don't have a license yet for the new"...
0x18006cec3  mov     [rbp+var_18], rax
0x18006cec7  lea     rax, [rbp+var_18]
0x18006cecb  mov     [rsp+68h+var_48], rax
0x18006ced0  lea     rdx, qword_18010FD60
0x18006ced7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006cedc  mov     ecx, 3E8h; dwMilliseconds
0x18006cee1  call    cs:__imp_Sleep
0x18006cee8  nop     dword ptr [rax+rax+00h]
0x18006ceed  sub     r15d, esi
0x18006cef0  test    r15d, r15d
0x18006cef3  jg      loc_18006CDE5
0x18006cef9  mov     esi, r13d
0x18006cefc  mov     rcx, rdi; this
0x18006ceff  call    ?PrepareTerminateRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareTerminateRequest(void)
0x18006cf04  mov     ebx, eax
0x18006cf06  test    eax, eax
0x18006cf08  jns     short loc_18006CF69
0x18006cf0a  lea     rdx, aPreparetermina_1; "PrepareTerminateRequest failed: 0x%x in"...
0x18006cf11  jmp     loc_18006CFEF
0x18006cf16  cmp     eax, 5
0x18006cf19  jbe     short loc_18006CF3B
0x18006cf1b  lea     rax, aGotALicenseWeC; "Got a license, we can continue now."
0x18006cf22  mov     [rbp+arg_0], rax
0x18006cf26  lea     rax, [rbp+arg_0]
0x18006cf2a  mov     [rsp+68h+var_48], rax
0x18006cf2f  lea     rdx, word_18010FD3E
0x18006cf36  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18006cf3b  mov     rcx, rdi; this
0x18006cf3e  call    ?PrepareContinueRequest@CSessionArbitrationDesktop@@IEAAJXZ; CSessionArbitrationDesktop::PrepareContinueRequest(void)
0x18006cf43  mov     ebx, eax
0x18006cf45  test    eax, eax
0x18006cf47  jns     short loc_18006CF69
0x18006cf49  lea     r9, aCsessionarbitr_45; "CSessionArbitrationCacheMode::TryToCrea"...
0x18006cf50  mov     r8d, eax
0x18006cf53  lea     rdx, aPreparecontinu; "PrepareContinueRequest failed: 0x%x in "...
0x18006cf5a  mov     ecx, 8; int
0x18006cf5f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18006cf64  jmp     loc_18006CDA6
0x18006cf69  lea     rcx, [rbp+var_28]; void *
0x18006cf6d  call    ??1?$SmartPtr@VCConnectionHandlerItem@@@@QEAA@XZ; SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(void)
0x18006cf72  test    esi, esi
0x18006cf74  jz      loc_18006D00D
0x18006cf7a  mov     [rbp+arg_8], r13
0x18006cf7e  lea     rcx, [rbp+arg_8]; struct ISessionManager **
0x18006cf82  call    ?GetInstanceOfSessionManager@CUtils@@SAJPEAPEAUISessionManager@@@Z; CUtils::GetInstanceOfSessionManager(ISessionManager * *)
0x18006cf87  mov     ebx, eax
0x18006cf89  cmp     [rdi+688h], r13d
0x18006cf90  jz      short loc_18006CFAA
0x18006cf92  mov     rcx, [rbp+arg_8]
0x18006cf96  mov     rax, [rcx]
0x18006cf99  mov     edx, [rdi+680h]
0x18006cf9f  mov     rax, [rax+68h]
0x18006cfa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfa8  mov     ebx, eax
0x18006cfaa  mov     eax, cs:dword_18012E170
0x18006cfb0  cmp     eax, 5
0x18006cfb3  jbe     short loc_18006CFE2
0x18006cfb5  mov     dword ptr [rbp+arg_0], ebx
0x18006cfb8  lea     rax, aMarkedCacheSes; "Marked cache session"
0x18006cfbf  mov     [rbp+arg_18], rax
  ... truncated ...
```
