# CDefaultConnectionHandler::AttempFastReconnectToExistingSession(IConnection *,IRemoteTerminal *)

- ea: `0x18007690c`
- end: `0x18007717f`
- name: `?AttempFastReconnectToExistingSession@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAVIRemoteTerminal@@@Z`
- size: `2163`
- prototype: `int(CDefaultConnectionHandler *__hidden this, struct IConnection *, struct IRemoteTerminal *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800799f0`

## callees

- `0x180001294`
- `0x1800016a8`
- `0x1800026a0`
- `0x180002ca4`
- `0x180003208`
- `0x180003540`
- `0x180009940`
- `0x18000c2a0`
- `0x180012c90`
- `0x1800139c0`
- `0x1800143e4`
- `0x1800146c8`
- `0x180015310`
- `0x180033f60`
- `0x18003440c`
- `0x180052b58`
- `0x180069450`
- `0x1800764a8`
- `0x18007690c`
- `0x180078674`
- `0x180079154`
- `0x180079f7c`
- `0x18007da94`
- `0x1800a2d54`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180076d86`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180076faf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180076d86`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180076faf`

## string_xrefs

- `0x18007709b`: `Task completed successfully`
- `0x18007699d`: `Attempt fast reconnect to existing session`
- `0x18007698a`: `CDefaultConnectionHandler::AttempFastReconnectToExistingSession`
- `0x180076e0f`: `CDefaultConnectionHandler::AttempFastReconnectToExistingSession`
- `0x18007708f`: `CDefaultConnectionHandler::AttempFastReconnectToExistingSession`
- `0x180076b78`: `AttempFastReconnectToExistingSession`
- `0x180076c17`: `AttempFastReconnectToExistingSession`
- `0x180076c53`: `AttempFastReconnectToExistingSession`
- `0x180076c9a`: `AttempFastReconnectToExistingSession`
- `0x180076d2f`: `AttempFastReconnectToExistingSession`
- `0x180076db3`: `AttempFastReconnectToExistingSession`
- `0x180076f1f`: `AttempFastReconnectToExistingSession`
- `0x180076f70`: `AttempFastReconnectToExistingSession`
- `0x180077109`: `AttempFastReconnectToExistingSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDefaultConnectionHandler::AttempFastReconnectToExistingSession(
        CDefaultConnectionHandler *this,
        struct IConnection *a2,
        struct IRemoteTerminal *a3,
        int a4)
{
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  unsigned int v10; // edx
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int UserSessionToReconnect; // ebx
  int IsSingleSessionPerUser; // eax
  int v16; // ebx
  const char *v17; // rax
  __int16 *v18; // rdx
  ULONGLONG TickCount64; // r15
  const char *v20; // rax
  __int16 *v21; // rdx
  const char *v23; // rsi
  ULONGLONG v24; // rax
  const char *v25; // rdi
  int v26; // edx
  CDefaultConnectionHandler *v27; // rcx
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int v31; // [rsp+50h] [rbp-B0h] BYREF
  const char *v32; // [rsp+58h] [rbp-A8h] BYREF
  const char *v33; // [rsp+60h] [rbp-A0h] BYREF
  const char *v34; // [rsp+68h] [rbp-98h] BYREF
  int v35[2]; // [rsp+70h] [rbp-90h] BYREF
  const char *v36; // [rsp+78h] [rbp-88h] BYREF
  struct IRemoteConnectionManager *v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  struct ISessionList *v39; // [rsp+90h] [rbp-70h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  void **v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h]
  void *Block; // [rsp+B0h] [rbp-50h]
  struct _GUID v44; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v45[40]; // [rsp+D0h] [rbp-30h] BYREF

  v40 = 0;
  v39 = 0;
  v44 = 0;
  v41 = &DynArray<long,unsigned long>::`vftable';
  v42 = 0;
  Block = 0;
  v31 = 0;
  v38 = 0;
  v37 = 0;
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v33 = "Attempt fast reconnect to existing session";
    *(_QWORD *)v35 = "CDefaultConnectionHandler::AttempFastReconnectToExistingSession";
    v32 = "Fast Reconnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)&byte_180111AE7,
      (_DWORD)a3,
      a4,
      (__int64)&v32,
      (__int64)v35,
      (__int64)&v33);
  }
  if ( !(unsigned int)CDefaultConnectionHandler::IsFastReconnectAllow(this)
    || !(*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 752LL))(a2) )
  {
    UserSessionToReconnect = -2147024846;
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v31 = (*(__int64 (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 752LL))(a2);
      v35[0] = CDefaultConnectionHandler::IsFastReconnectAllow(v27);
      v34 = "AttempFastReconnectToExistingSession";
      LODWORD(v33) = -2147024846;
      v32 = "Fast reconnect is not supported";
      v36 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v28,
        (unsigned int)&unk_180111A50,
        v29,
        v30,
        (__int64)&v36,
        (__int64)&v32,
        (__int64)&v33,
        (__int64)&v34,
        (__int64)v35,
        (__int64)&v31);
    }
    goto LABEL_42;
  }
  if ( (*(int (__fastcall **)(struct IConnection *, struct _GUID *))(*(_QWORD *)a2 + 368LL))(a2, &v44) < 0 )
    v44 = 0;
  CUtils::ConvertUuidToString(&v44, v10, v45);
  if ( !(unsigned int)CHelper::IsReconnectAllowed(a2, a3) )
  {
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v32 = "The connection limit will be exceeded if we fast reconnect, do not fast reconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_180111A2D,
        v12,
        v13,
        (__int64)&v32);
    }
    UserSessionToReconnect = -2147017842;
    _DbgPrintMessage(
      8,
      "Exceed listener max instance count failed: 0x%x in %s",
      -2147017842,
      "CDefaultConnectionHandler::AttempFastReconnectToExistingSession");
    goto LABEL_42;
  }
  if ( (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 752LL))(a2) == 1 )
  {
    v35[0] = 1;
    IsSingleSessionPerUser = CUtils::IsSingleSessionPerUser(v35);
    v16 = v35[0];
    if ( IsSingleSessionPerUser < 0 )
      v16 = 1;
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      v35[0] = v16;
      v32 = "SingleSessionPerUser";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)byte_1801119F3,
        v8,
        v9,
        (__int64)&v32,
        (__int64)v35);
    }
    if ( !v16 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        v31 = 0;
        v32 = "Basic Fast Reconnect is not supported";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)byte_1801119B9,
          v8,
          v9,
          (__int64)&v32,
          (__int64)&v31);
      }
      UserSessionToReconnect = -2147024846;
      goto LABEL_42;
    }
    UserSessionToReconnect = CDefaultConnectionHandler::FindUserSessionToReconnect(this, a3, a2, &v41);
    if ( UserSessionToReconnect < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
      {
LABEL_42:
        if ( (unsigned int)dword_18012E170 > 4 )
        {
          LODWORD(v33) = UserSessionToReconnect;
          v36 = "CDefaultConnectionHandler::AttempFastReconnectToExistingSession";
          v34 = "Fast Reconnect";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v7,
            (unsigned int)byte_180111703,
            v8,
            v9,
            (__int64)&v34,
            (__int64)&v36,
            (__int64)&v33);
        }
        if ( (unsigned int)dword_18012E170 > 4 )
        {
          v36 = "Fast Reconnect failed, using default action";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v7,
            (unsigned int)word_1801116AA,
            v8,
            v9,
            (__int64)&v36);
        }
        goto LABEL_46;
      }
      v32 = "AttempFastReconnectToExistingSession";
      v17 = "FindUserSessionToReconnect";
      v18 = (__int16 *)&dword_18011197C;
      goto LABEL_23;
    }
  }
  else if ( (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 752LL))(a2) == 2 )
  {
    UserSessionToReconnect = CDefaultConnectionHandler::FindUserSessionForEnhancedReconnect(
                               (__int64)this,
                               (__int64)a3,
                               (__int64)a2,
                               (__int64)&v41);
    if ( UserSessionToReconnect < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_42;
      v32 = "AttempFastReconnectToExistingSession";
      v17 = "FindUserSessionForEnhancedReconnect";
      v18 = (__int16 *)&byte_18011193F;
LABEL_23:
      v31 = UserSessionToReconnect;
LABEL_24:
      v33 = v17;
      *(_QWORD *)v35 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (_DWORD)v18,
        v8,
        v9,
        (__int64)v35,
        (__int64)&v33,
        (__int64)&v31,
        (__int64)&v32);
      goto LABEL_42;
    }
  }
  if ( !HIDWORD(v42) )
  {
    v7 = -2147024894;
    UserSessionToReconnect = -2147024894;
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_42;
    v32 = "AttempFastReconnectToExistingSession";
    v31 = -2147024894;
    v17 = "No session to fast reconnect";
    v18 = word_180111902;
    goto LABEL_24;
  }
  if ( HIDWORD(v42) > 1 )
  {
    UserSessionToReconnect = -2147024846;
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v31 = HIDWORD(v42);
      v32 = "AttempFastReconnectToExistingSession";
      v35[0] = -2147024846;
      v33 = "Too many sesssion to fast reconnect";
      v34 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)word_1801118AA,
        v8,
        v9,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)v35,
        (__int64)&v32,
        (__int64)&v31);
    }
    goto LABEL_42;
  }
  if ( !(unsigned int)DynArray<long,unsigned long>::GetAt(&v41, 0, &v31) )
  {
    v7 = -2147024894;
    UserSessionToReconnect = -2147024894;
    if ( (unsigned int)dword_18012E170 > 3 )
    {
      v34 = "AttempFastReconnectToExistingSession";
      v31 = -2147024894;
      v32 = "No session to reconnect";
      v33 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147024894,
        (unsigned int)byte_18011186D,
        v8,
        v9,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v34);
    }
    goto LABEL_42;
  }
  TickCount64 = GetTickCount64();
  UserSessionToReconnect = CHelper::GetSessionList(&v39);
  if ( UserSessionToReconnect < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_42;
    v34 = "AttempFastReconnectToExistingSession";
    v20 = "GetSessionList";
    v21 = (__int16 *)qword_180111830;
LABEL_41:
    v32 = v20;
    v33 = "Warning HResult failed";
    v31 = UserSessionToReconnect;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v7,
      (_DWORD)v21,
      v8,
      v9,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v34);
    goto LABEL_42;
  }
  v23 = (const char *)v31;
  UserSessionToReconnect = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, __int64 *))(*(_QWORD *)v39 + 24LL))(
                             v39,
                             (unsigned int)v31,
                             &v40);
  if ( UserSessionToReconnect < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_42;
    v34 = "AttempFastReconnectToExistingSession";
    v20 = "FindSessionById";
    v21 = (__int16 *)byte_1801117F3;
    goto LABEL_41;
  }
  GetInstanceOfRemoteConnectionManager(&v37);
  UserSessionToReconnect = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64 *))(*(_QWORD *)v37 + 72LL))(
                             v37,
                             &v38);
  if ( UserSessionToReconnect < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_42;
    v34 = "AttempFastReconnectToExistingSession";
    v20 = "GetInstanceOfEnforcementCore";
    v21 = &word_1801117B6;
    goto LABEL_41;
  }
  UserSessionToReconnect = (*(__int64 (__fastcall **)(__int64, __int64, struct IRemoteTerminal *, __int64))(*(_QWORD *)v38 + 96LL))(
                             v38,
                             v40,
                             a3,
                             1);
  if ( UserSessionToReconnect < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      v34 = v23;
      v31 = UserSessionToReconnect;
      v32 = "Fast reconnect failed to reconnect to session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)byte_180111741,
        v8,
        v9,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v34);
    }
  }
  else
  {
    v24 = GetTickCount64();
    v25 = (const char *)(v24 - TickCount64);
    CrimsonHelper::RaiseEvent<unsigned short *,long,unsigned __int64>(
      (unsigned int)&CrimsonHelper::s_instance,
      v26,
      (unsigned int)v45,
      (_DWORD)v23,
      v24 - TickCount64);
    v7 = dword_18012E170;
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v34 = v23;
      v32 = v25;
      v33 = "Fast reconnect time to connect to session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        dword_18012E170,
        (unsigned int)&dword_180111774,
        v8,
        v9,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v34);
    }
  }
  if ( UserSessionToReconnect < 0 )
    goto LABEL_42;
  if ( (unsigned int)dword_18012E170 > 5 )
  {
    v31 = UserSessionToReconnect;
    v34 = "CDefaultConnectionHandler::AttempFastReconnectToExistingSession";
    v32 = "Task completed successfully";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)byte_1801116CD,
      v8,
      v9,
      (__int64)&v32,
      (__int64)&v34,
      (__int64)&v31);
  }
LABEL_46:
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v37);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v38);
  v41 = &DynArray<long,unsigned long>::`vftable';
  operator delete(Block);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v39);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v40);
  return (unsigned int)UserSessionToReconnect;
}

```

## disassembly

```asm
0x18007690c  push    rbp
0x18007690e  push    rbx
0x18007690f  push    rsi
0x180076910  push    rdi
0x180076911  push    r13
0x180076913  push    r14
0x180076915  push    r15
0x180076917  lea     rbp, [rsp-30h]
0x18007691c  sub     rsp, 130h
0x180076923  mov     rax, cs:__security_cookie
0x18007692a  xor     rax, rsp
0x18007692d  mov     [rbp+60h+var_40], rax
0x180076931  mov     r14, r8
0x180076934  mov     rdi, rdx
0x180076937  mov     rsi, rcx
0x18007693a  mov     [rbp+60h+var_C8], 0
0x180076942  mov     [rbp+60h+var_D0], 0
0x18007694a  xorps   xmm0, xmm0
0x18007694d  movups  xmmword ptr [rbp+60h+var_A8.Data1], xmm0
0x180076951  lea     rax, ??_7?$DynArray@JK@@6B@; const DynArray<long,ulong>::`vftable'
0x180076958  mov     [rbp+60h+var_C0], rax
0x18007695c  mov     [rbp+60h+var_B8], 0
0x180076964  mov     [rbp+60h+Block], 0
0x18007696c  mov     [rsp+160h+var_110], 0
0x180076974  mov     [rbp+60h+var_D8], 0
0x18007697c  mov     [rbp+60h+var_E0], 0
0x180076984  mov     eax, cs:dword_18012E170
0x18007698a  lea     r15, aCdefaultconnec_0; "CDefaultConnectionHandler::AttempFastRe"...
0x180076991  lea     r13, aFastReconnect; "Fast Reconnect"
0x180076998  cmp     eax, 4
0x18007699b  jbe     short loc_1800769DD
0x18007699d  lea     rax, aAttemptFastRec; "Attempt fast reconnect to existing sess"...
0x1800769a4  mov     [rsp+160h+var_100], rax
0x1800769a9  mov     qword ptr [rsp+160h+var_F0], r15
0x1800769ae  mov     [rsp+160h+var_108], r13
0x1800769b3  lea     rax, [rsp+160h+var_100]
0x1800769b8  mov     [rsp+160h+var_130], rax
0x1800769bd  lea     rax, [rsp+160h+var_F0]
0x1800769c2  mov     [rsp+160h+var_138], rax
0x1800769c7  lea     rax, [rsp+160h+var_108]
0x1800769cc  mov     [rsp+160h+var_140], rax
0x1800769d1  lea     rdx, byte_180111AE7
0x1800769d8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800769dd  call    ?IsFastReconnectAllow@CDefaultConnectionHandler@@AEAAHXZ; CDefaultConnectionHandler::IsFastReconnectAllow(void)
0x1800769e2  test    eax, eax
0x1800769e4  jz      loc_1800770D6
0x1800769ea  mov     rax, [rdi]
0x1800769ed  mov     rcx, rdi
0x1800769f0  mov     rax, [rax+2F0h]
0x1800769f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800769fc  test    eax, eax
0x1800769fe  jz      loc_1800770D6
0x180076a04  mov     rax, [rdi]
0x180076a07  lea     rdx, [rbp+60h+var_A8]
0x180076a0b  mov     rcx, rdi
0x180076a0e  mov     rax, [rax+170h]
0x180076a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076a1a  lea     r8, [rbp+60h+var_90]; unsigned __int16 *
0x180076a1e  lea     rcx, [rbp+60h+var_A8]; struct _GUID *
0x180076a22  test    eax, eax
0x180076a24  jns     short loc_180076A2D
0x180076a26  xorps   xmm0, xmm0
0x180076a29  movups  xmmword ptr [rbp+60h+var_A8.Data1], xmm0
0x180076a2d  call    ?ConvertUuidToString@CUtils@@SAJPEAU_GUID@@KPEAG@Z; CUtils::ConvertUuidToString(_GUID *,ulong,ushort *)
0x180076a32  mov     rdx, r14; struct IRemoteTerminal *
0x180076a35  mov     rcx, rdi; struct IConnection *
0x180076a38  call    ?IsReconnectAllowed@CHelper@@SAHPEAVIConnection@@PEAVIRemoteTerminal@@@Z; CHelper::IsReconnectAllowed(IConnection *,IRemoteTerminal *)
0x180076a3d  test    eax, eax
0x180076a3f  jnz     short loc_180076A8F
0x180076a41  mov     eax, cs:dword_18012E170
0x180076a47  cmp     eax, 5
0x180076a4a  jbe     short loc_180076A6E
0x180076a4c  lea     rax, aTheConnectionL_1; "The connection limit will be exceeded i"...
0x180076a53  mov     [rsp+160h+var_108], rax
0x180076a58  lea     rax, [rsp+160h+var_108]
0x180076a5d  mov     [rsp+160h+var_140], rax
0x180076a62  lea     rdx, byte_180111A2D
0x180076a69  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180076a6e  mov     ebx, 80071B8Eh
0x180076a73  mov     r9, r15
0x180076a76  mov     r8d, ebx
0x180076a79  lea     rdx, aExceedListener_1; "Exceed listener max instance count fail"...
0x180076a80  mov     ecx, 8; int
0x180076a85  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180076a8a  jmp     loc_180076E1D
0x180076a8f  mov     rax, [rdi]
0x180076a92  mov     rcx, rdi
0x180076a95  mov     rax, [rax+2F0h]
0x180076a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076aa1  mov     r13d, 1
0x180076aa7  cmp     eax, r13d
0x180076aaa  jnz     loc_180076BD9
0x180076ab0  mov     [rsp+160h+var_F0], r13d
0x180076ab5  lea     rcx, [rsp+160h+var_F0]; int *
0x180076aba  call    ?IsSingleSessionPerUser@CUtils@@SAJPEAH@Z; CUtils::IsSingleSessionPerUser(int *)
0x180076abf  mov     ebx, [rsp+160h+var_F0]
0x180076ac3  test    eax, eax
0x180076ac5  cmovs   ebx, r13d
0x180076ac9  mov     eax, cs:dword_18012E170
0x180076acf  cmp     eax, 5
0x180076ad2  jbe     short loc_180076B04
0x180076ad4  mov     [rsp+160h+var_F0], ebx
0x180076ad8  lea     rax, aSinglesessionp; "SingleSessionPerUser"
0x180076adf  mov     [rsp+160h+var_108], rax
0x180076ae4  lea     rax, [rsp+160h+var_F0]
0x180076ae9  mov     [rsp+160h+var_138], rax
0x180076aee  lea     rax, [rsp+160h+var_108]
0x180076af3  mov     [rsp+160h+var_140], rax
0x180076af8  lea     rdx, byte_1801119F3
0x180076aff  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180076b04  test    ebx, ebx
0x180076b06  jnz     short loc_180076B4D
0x180076b08  mov     eax, cs:dword_18012E170
0x180076b0e  cmp     eax, 3
0x180076b11  jbe     short loc_180076B43
0x180076b13  mov     [rsp+160h+var_110], ebx
0x180076b17  lea     rax, aBasicFastRecon; "Basic Fast Reconnect is not supported"
0x180076b1e  mov     [rsp+160h+var_108], rax
0x180076b23  lea     rax, [rsp+160h+var_110]
0x180076b28  mov     [rsp+160h+var_138], rax
0x180076b2d  lea     rax, [rsp+160h+var_108]
0x180076b32  mov     [rsp+160h+var_140], rax
0x180076b37  lea     rdx, byte_1801119B9
0x180076b3e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180076b43  mov     ebx, 80070032h
0x180076b48  jmp     loc_180076E16
0x180076b4d  lea     r9, [rbp+60h+var_C0]
0x180076b51  mov     r8, rdi
0x180076b54  mov     rdx, r14
0x180076b57  mov     rcx, rsi
0x180076b5a  call    ?FindUserSessionToReconnect@CDefaultConnectionHandler@@AEAAJPEAVIRemoteTerminal@@PEAVIConnection@@AEAV?$DynArray@JK@@@Z; CDefaultConnectionHandler::FindUserSessionToReconnect(IRemoteTerminal *,IConnection *,DynArray<long,ulong> &)
0x180076b5f  mov     ebx, eax
0x180076b61  test    eax, eax
0x180076b63  jns     loc_180076C36
0x180076b69  mov     eax, cs:dword_18012E170
0x180076b6f  cmp     eax, 3
0x180076b72  jbe     loc_180076E16
0x180076b78  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180076b7f  mov     [rsp+160h+var_108], rax
0x180076b84  lea     rax, aFindusersessio; "FindUserSessionToReconnect"
0x180076b8b  lea     rdx, dword_18011197C
0x180076b92  mov     [rsp+160h+var_110], ebx
0x180076b96  mov     [rsp+160h+var_100], rax
0x180076b9b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180076ba2  mov     qword ptr [rsp+160h+var_F0], rax
0x180076ba7  lea     rax, [rsp+160h+var_108]
0x180076bac  mov     [rsp+160h+var_128], rax
0x180076bb1  lea     rax, [rsp+160h+var_110]
0x180076bb6  mov     [rsp+160h+var_130], rax
0x180076bbb  lea     rax, [rsp+160h+var_100]
0x180076bc0  mov     [rsp+160h+var_138], rax
0x180076bc5  lea     rax, [rsp+160h+var_F0]
0x180076bca  mov     [rsp+160h+var_140], rax
0x180076bcf  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180076bd4  jmp     loc_180076E16
0x180076bd9  mov     rax, [rdi]
0x180076bdc  mov     rcx, rdi
0x180076bdf  mov     rax, [rax+2F0h]
0x180076be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076beb  cmp     eax, 2
0x180076bee  jnz     short loc_180076C36
0x180076bf0  lea     r9, [rbp+60h+var_C0]
0x180076bf4  mov     r8, rdi
0x180076bf7  mov     rdx, r14
0x180076bfa  mov     rcx, rsi
0x180076bfd  call    ?FindUserSessionForEnhancedReconnect@CDefaultConnectionHandler@@AEAAJPEAVIRemoteTerminal@@PEAVIConnection@@AEAV?$DynArray@JK@@@Z; CDefaultConnectionHandler::FindUserSessionForEnhancedReconnect(IRemoteTerminal *,IConnection *,DynArray<long,ulong> &)
0x180076c02  mov     ebx, eax
0x180076c04  test    eax, eax
0x180076c06  jns     short loc_180076C36
0x180076c08  mov     eax, cs:dword_18012E170
0x180076c0e  cmp     eax, 3
0x180076c11  jbe     loc_180076E16
0x180076c17  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180076c1e  mov     [rsp+160h+var_108], rax
0x180076c23  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x180076c2a  lea     rdx, byte_18011193F
0x180076c31  jmp     loc_180076B92
0x180076c36  mov     eax, dword ptr [rbp+60h+var_B8+4]
0x180076c39  test    eax, eax
0x180076c3b  jnz     short loc_180076C76
0x180076c3d  mov     ecx, 80070002h
0x180076c42  mov     ebx, ecx
0x180076c44  mov     eax, cs:dword_18012E170
0x180076c4a  cmp     eax, 3
0x180076c4d  jbe     loc_180076E16
0x180076c53  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180076c5a  mov     [rsp+160h+var_108], rax
0x180076c5f  mov     [rsp+160h+var_110], ecx
0x180076c63  lea     rax, aNoSessionToFas; "No session to fast reconnect"
0x180076c6a  lea     rdx, word_180111902
0x180076c71  jmp     loc_180076B96
0x180076c76  cmp     eax, r13d
0x180076c79  jbe     loc_180076D05
0x180076c7f  mov     ebx, 80070032h
0x180076c84  mov     eax, cs:dword_18012E170
0x180076c8a  cmp     eax, 3
0x180076c8d  jbe     loc_180076E16
0x180076c93  mov     eax, dword ptr [rbp+60h+var_B8+4]
0x180076c96  mov     [rsp+160h+var_110], eax
0x180076c9a  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180076ca1  mov     [rsp+160h+var_108], rax
0x180076ca6  mov     [rsp+160h+var_F0], ebx
0x180076caa  lea     rax, aTooManySesssio; "Too many sesssion to fast reconnect"
0x180076cb1  mov     [rsp+160h+var_100], rax
0x180076cb6  lea     rax, aWarningHresult; "Warning HResult failed"
0x180076cbd  mov     [rsp+160h+var_F8], rax
0x180076cc2  lea     rax, [rsp+160h+var_110]
0x180076cc7  mov     [rsp+160h+var_120], rax
0x180076ccc  lea     rax, [rsp+160h+var_108]
0x180076cd1  mov     [rsp+160h+var_128], rax
0x180076cd6  lea     rax, [rsp+160h+var_F0]
0x180076cdb  mov     [rsp+160h+var_130], rax
0x180076ce0  lea     rax, [rsp+160h+var_100]
0x180076ce5  mov     [rsp+160h+var_138], rax
0x180076cea  lea     rax, [rsp+160h+var_F8]
0x180076cef  mov     [rsp+160h+var_140], rax
0x180076cf4  lea     rdx, word_1801118AA
0x180076cfb  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180076d00  jmp     loc_180076E16
0x180076d05  lea     r8, [rsp+160h+var_110]
0x180076d0a  xor     edx, edx
0x180076d0c  lea     rcx, [rbp+60h+var_C0]
0x180076d10  call    ?GetAt@?$DynArray@JK@@UEAAHKPEAJ@Z; DynArray<long,ulong>::GetAt(ulong,long *)
0x180076d15  test    eax, eax
0x180076d17  jnz     short loc_180076D86
0x180076d19  mov     ecx, 80070002h
0x180076d1e  mov     ebx, ecx
0x180076d20  mov     eax, cs:dword_18012E170
0x180076d26  cmp     eax, 3
0x180076d29  jbe     loc_180076E16
0x180076d2f  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180076d36  mov     [rsp+160h+var_F8], rax
0x180076d3b  mov     [rsp+160h+var_110], ecx
0x180076d3f  lea     rax, aNoSessionToRec_0; "No session to reconnect"
0x180076d46  mov     [rsp+160h+var_108], rax
0x180076d4b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180076d52  mov     [rsp+160h+var_100], rax
0x180076d57  lea     rax, [rsp+160h+var_F8]
0x180076d5c  mov     [rsp+160h+var_128], rax
0x180076d61  lea     rax, [rsp+160h+var_110]
0x180076d66  mov     [rsp+160h+var_130], rax
0x180076d6b  lea     rax, [rsp+160h+var_108]
0x180076d70  mov     [rsp+160h+var_138], rax
0x180076d75  lea     rax, [rsp+160h+var_100]
0x180076d7a  lea     rdx, byte_18011186D
0x180076d81  jmp     loc_180076BCA
0x180076d86  call    cs:__imp_GetTickCount64
0x180076d8d  nop     dword ptr [rax+rax+00h]
0x180076d92  mov     r15, rax
0x180076d95  lea     rcx, [rbp+60h+var_D0]; struct ISessionList **
0x180076d99  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180076d9e  mov     ebx, eax
0x180076da0  test    eax, eax
0x180076da2  jns     loc_180076EEF
0x180076da8  mov     eax, cs:dword_18012E170
0x180076dae  cmp     eax, 3
0x180076db1  jbe     short loc_180076E0F
0x180076db3  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180076dba  mov     [rsp+160h+var_F8], rax
0x180076dbf  lea     rax, aGetsessionlist_1; "GetSessionList"
0x180076dc6  lea     rdx, qword_180111830
0x180076dcd  mov     [rsp+160h+var_108], rax
0x180076dd2  lea     rax, aWarningHresult; "Warning HResult failed"
0x180076dd9  mov     [rsp+160h+var_100], rax
0x180076dde  lea     rax, [rsp+160h+var_F8]
0x180076de3  mov     [rsp+160h+var_128], rax
0x180076de8  lea     rax, [rsp+160h+var_110]
0x180076ded  mov     [rsp+160h+var_130], rax
0x180076df2  lea     rax, [rsp+160h+var_108]
0x180076df7  mov     [rsp+160h+var_138], rax
0x180076dfc  lea     rax, [rsp+160h+var_100]
0x180076e01  mov     [rsp+160h+var_110], ebx
0x180076e05  mov     [rsp+160h+var_140], rax
0x180076e0a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180076e0f  lea     r15, aCdefaultconnec_0; "CDefaultConnectionHandler::AttempFastRe"...
0x180076e16  lea     r13, aFastReconnect; "Fast Reconnect"
0x180076e1d  mov     eax, cs:dword_18012E170
0x180076e23  cmp     eax, 4
0x180076e26  jbe     short loc_180076E60
0x180076e28  mov     dword ptr [rsp+160h+var_100], ebx
0x180076e2c  mov     [rsp+160h+var_E8], r15
0x180076e31  mov     [rsp+160h+var_F8], r13
0x180076e36  lea     rax, [rsp+160h+var_100]
0x180076e3b  mov     [rsp+160h+var_130], rax
0x180076e40  lea     rax, [rsp+160h+var_E8]
0x180076e45  mov     [rsp+160h+var_138], rax
0x180076e4a  lea     rax, [rsp+160h+var_F8]
0x180076e4f  mov     [rsp+160h+var_140], rax
0x180076e54  lea     rdx, byte_180111703
0x180076e5b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180076e60  test    ebx, ebx
0x180076e62  jns     short loc_180076E92
0x180076e64  mov     eax, cs:dword_18012E170
0x180076e6a  cmp     eax, 4
0x180076e6d  jbe     short loc_180076E92
0x180076e6f  lea     rax, aFastReconnectF_0; "Fast Reconnect failed, using default ac"...
0x180076e76  mov     [rsp+160h+var_E8], rax
0x180076e7b  lea     rax, [rsp+160h+var_E8]
0x180076e80  mov     [rsp+160h+var_140], rax
0x180076e85  lea     rdx, word_1801116AA
  ... truncated ...
```
