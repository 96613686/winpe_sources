# CDefaultConnectionHandler::AttempFastReconnectToExistingSession(IConnection *,IRemoteTerminal *)

- ea: `0x18007339c`
- end: `0x180073c02`
- name: `?AttempFastReconnectToExistingSession@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAVIRemoteTerminal@@@Z`
- size: `2150`
- prototype: `__int64 __fastcall(CDefaultConnectionHandler *this, struct IConnection *, struct IRemoteTerminal *, int)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180076420`

## callees

- `0x180001284`
- `0x180001688`
- `0x180002674`
- `0x180002c74`
- `0x1800031d4`
- `0x18000350c`
- `0x18000a210`
- `0x18000c2f0`
- `0x180012480`
- `0x180013150`
- `0x180013a18`
- `0x180013d00`
- `0x1800148f0`
- `0x1800321f0`
- `0x18003269c`
- `0x180050490`
- `0x180066280`
- `0x180072ee8`
- `0x18007339c`
- `0x1800750e8`
- `0x180075b84`
- `0x1800769ac`
- `0x18007a3e0`
- `0x18009dd9c`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180073816`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180073a38`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180073816`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180073a38`

## string_xrefs

- `0x180073b1e`: `Task completed successfully`
- `0x18007342d`: `Attempt fast reconnect to existing session`
- `0x18007341a`: `CDefaultConnectionHandler::AttempFastReconnectToExistingSession`
- `0x180073899`: `CDefaultConnectionHandler::AttempFastReconnectToExistingSession`
- `0x180073b12`: `CDefaultConnectionHandler::AttempFastReconnectToExistingSession`
- `0x180073608`: `AttempFastReconnectToExistingSession`
- `0x1800736a7`: `AttempFastReconnectToExistingSession`
- `0x1800736e3`: `AttempFastReconnectToExistingSession`
- `0x18007372a`: `AttempFastReconnectToExistingSession`
- `0x1800737bf`: `AttempFastReconnectToExistingSession`
- `0x18007383d`: `AttempFastReconnectToExistingSession`
- `0x1800739a8`: `AttempFastReconnectToExistingSession`
- `0x1800739f9`: `AttempFastReconnectToExistingSession`
- `0x180073b8c`: `AttempFastReconnectToExistingSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v33 = "Attempt fast reconnect to existing session";
    *(_QWORD *)v35 = "CDefaultConnectionHandler::AttempFastReconnectToExistingSession";
    v32 = "Fast Reconnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (_DWORD)this,
      (unsigned int)&byte_18010BA67,
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
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v31 = (*(__int64 (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 752LL))(a2);
      v35[0] = CDefaultConnectionHandler::IsFastReconnectAllow(v27);
      v34 = "AttempFastReconnectToExistingSession";
      LODWORD(v33) = -2147024846;
      v32 = "Fast reconnect is not supported";
      v36 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v28,
        (unsigned int)&unk_18010B9D0,
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
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v32 = "The connection limit will be exceeded if we fast reconnect, do not fast reconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v11,
        (unsigned int)byte_18010B9AD,
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
    if ( (unsigned int)dword_180128170 > 5 )
    {
      v35[0] = v16;
      v32 = "SingleSessionPerUser";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)byte_18010B973,
        v8,
        v9,
        (__int64)&v32,
        (__int64)v35);
    }
    if ( !v16 )
    {
      if ( (unsigned int)dword_180128170 > 3 )
      {
        v31 = 0;
        v32 = "Basic Fast Reconnect is not supported";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)byte_18010B939,
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
      if ( (unsigned int)dword_180128170 <= 3 )
      {
LABEL_42:
        if ( (unsigned int)dword_180128170 > 4 )
        {
          LODWORD(v33) = UserSessionToReconnect;
          v36 = "CDefaultConnectionHandler::AttempFastReconnectToExistingSession";
          v34 = "Fast Reconnect";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v7,
            (unsigned int)byte_18010B683,
            v8,
            v9,
            (__int64)&v34,
            (__int64)&v36,
            (__int64)&v33);
        }
        if ( (unsigned int)dword_180128170 > 4 )
        {
          v36 = "Fast Reconnect failed, using default action";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v7,
            (unsigned int)word_18010B62A,
            v8,
            v9,
            (__int64)&v36);
        }
        goto LABEL_46;
      }
      v32 = "AttempFastReconnectToExistingSession";
      v17 = "FindUserSessionToReconnect";
      v18 = (__int16 *)&dword_18010B8FC;
      goto LABEL_23;
    }
  }
  else if ( (*(unsigned int (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 752LL))(a2) == 2 )
  {
    UserSessionToReconnect = CDefaultConnectionHandler::FindUserSessionForEnhancedReconnect(this, a3, a2, &v41);
    if ( UserSessionToReconnect < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_42;
      v32 = "AttempFastReconnectToExistingSession";
      v17 = "FindUserSessionForEnhancedReconnect";
      v18 = (__int16 *)&byte_18010B8BF;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_42;
    v32 = "AttempFastReconnectToExistingSession";
    v31 = -2147024894;
    v17 = "No session to fast reconnect";
    v18 = word_18010B882;
    goto LABEL_24;
  }
  if ( HIDWORD(v42) > 1 )
  {
    UserSessionToReconnect = -2147024846;
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v31 = HIDWORD(v42);
      v32 = "AttempFastReconnectToExistingSession";
      v35[0] = -2147024846;
      v33 = "Too many sesssion to fast reconnect";
      v34 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)word_18010B82A,
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
    if ( (unsigned int)dword_180128170 > 3 )
    {
      v34 = "AttempFastReconnectToExistingSession";
      v31 = -2147024894;
      v32 = "No session to reconnect";
      v33 = "Warning HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        -2147024894,
        (unsigned int)byte_18010B7ED,
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_42;
    v34 = "AttempFastReconnectToExistingSession";
    v20 = "GetSessionList";
    v21 = (__int16 *)qword_18010B7B0;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_42;
    v34 = "AttempFastReconnectToExistingSession";
    v20 = "FindSessionById";
    v21 = (__int16 *)byte_18010B773;
    goto LABEL_41;
  }
  GetInstanceOfRemoteConnectionManager(&v37);
  UserSessionToReconnect = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64 *))(*(_QWORD *)v37 + 72LL))(
                             v37,
                             &v38);
  if ( UserSessionToReconnect < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_42;
    v34 = "AttempFastReconnectToExistingSession";
    v20 = "GetInstanceOfEnforcementCore";
    v21 = &word_18010B736;
    goto LABEL_41;
  }
  UserSessionToReconnect = (*(__int64 (__fastcall **)(__int64, __int64, struct IRemoteTerminal *, __int64))(*(_QWORD *)v38 + 96LL))(
                             v38,
                             v40,
                             a3,
                             1);
  if ( UserSessionToReconnect < 0 )
  {
    if ( (unsigned int)dword_180128170 > 2 )
    {
      v34 = v23;
      v31 = UserSessionToReconnect;
      v32 = "Fast reconnect failed to reconnect to session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)byte_18010B6C1,
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
    v7 = dword_180128170;
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v34 = v23;
      v32 = v25;
      v33 = "Fast reconnect time to connect to session";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        dword_180128170,
        (unsigned int)&dword_18010B6F4,
        v8,
        v9,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v34);
    }
  }
  if ( UserSessionToReconnect < 0 )
    goto LABEL_42;
  if ( (unsigned int)dword_180128170 > 5 )
  {
    v31 = UserSessionToReconnect;
    v34 = "CDefaultConnectionHandler::AttempFastReconnectToExistingSession";
    v32 = "Task completed successfully";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)byte_18010B64D,
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
0x18007339c  push    rbp
0x18007339e  push    rbx
0x18007339f  push    rsi
0x1800733a0  push    rdi
0x1800733a1  push    r13
0x1800733a3  push    r14
0x1800733a5  push    r15
0x1800733a7  lea     rbp, [rsp-30h]
0x1800733ac  sub     rsp, 130h
0x1800733b3  mov     rax, cs:__security_cookie
0x1800733ba  xor     rax, rsp
0x1800733bd  mov     [rbp+60h+var_40], rax
0x1800733c1  mov     r14, r8
0x1800733c4  mov     rdi, rdx
0x1800733c7  mov     rsi, rcx
0x1800733ca  mov     [rbp+60h+var_C8], 0
0x1800733d2  mov     [rbp+60h+var_D0], 0
0x1800733da  xorps   xmm0, xmm0
0x1800733dd  movups  xmmword ptr [rbp+60h+var_A8.Data1], xmm0
0x1800733e1  lea     rax, ??_7?$DynArray@JK@@6B@; const DynArray<long,ulong>::`vftable'
0x1800733e8  mov     [rbp+60h+var_C0], rax
0x1800733ec  mov     [rbp+60h+var_B8], 0
0x1800733f4  mov     [rbp+60h+Block], 0
0x1800733fc  mov     [rsp+160h+var_110], 0
0x180073404  mov     [rbp+60h+var_D8], 0
0x18007340c  mov     [rbp+60h+var_E0], 0
0x180073414  mov     eax, cs:dword_180128170
0x18007341a  lea     r15, aCdefaultconnec_0; "CDefaultConnectionHandler::AttempFastRe"...
0x180073421  lea     r13, aFastReconnect; "Fast Reconnect"
0x180073428  cmp     eax, 4
0x18007342b  jbe     short loc_18007346D
0x18007342d  lea     rax, aAttemptFastRec; "Attempt fast reconnect to existing sess"...
0x180073434  mov     [rsp+160h+var_100], rax
0x180073439  mov     qword ptr [rsp+160h+var_F0], r15
0x18007343e  mov     [rsp+160h+var_108], r13
0x180073443  lea     rax, [rsp+160h+var_100]
0x180073448  mov     [rsp+160h+var_130], rax
0x18007344d  lea     rax, [rsp+160h+var_F0]
0x180073452  mov     [rsp+160h+var_138], rax
0x180073457  lea     rax, [rsp+160h+var_108]
0x18007345c  mov     [rsp+160h+var_140], rax
0x180073461  lea     rdx, byte_18010BA67
0x180073468  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18007346d  call    ?IsFastReconnectAllow@CDefaultConnectionHandler@@AEAAHXZ; CDefaultConnectionHandler::IsFastReconnectAllow(void)
0x180073472  test    eax, eax
0x180073474  jz      loc_180073B59
0x18007347a  mov     rax, [rdi]
0x18007347d  mov     rcx, rdi
0x180073480  mov     rax, [rax+2F0h]
0x180073487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007348c  test    eax, eax
0x18007348e  jz      loc_180073B59
0x180073494  mov     rax, [rdi]
0x180073497  lea     rdx, [rbp+60h+var_A8]
0x18007349b  mov     rcx, rdi
0x18007349e  mov     rax, [rax+170h]
0x1800734a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800734aa  lea     r8, [rbp+60h+var_90]; unsigned __int16 *
0x1800734ae  lea     rcx, [rbp+60h+var_A8]; struct _GUID *
0x1800734b2  test    eax, eax
0x1800734b4  jns     short loc_1800734BD
0x1800734b6  xorps   xmm0, xmm0
0x1800734b9  movups  xmmword ptr [rbp+60h+var_A8.Data1], xmm0
0x1800734bd  call    ?ConvertUuidToString@CUtils@@SAJPEAU_GUID@@KPEAG@Z; CUtils::ConvertUuidToString(_GUID *,ulong,ushort *)
0x1800734c2  mov     rdx, r14; struct IRemoteTerminal *
0x1800734c5  mov     rcx, rdi; struct IConnection *
0x1800734c8  call    ?IsReconnectAllowed@CHelper@@SAHPEAVIConnection@@PEAVIRemoteTerminal@@@Z; CHelper::IsReconnectAllowed(IConnection *,IRemoteTerminal *)
0x1800734cd  test    eax, eax
0x1800734cf  jnz     short loc_18007351F
0x1800734d1  mov     eax, cs:dword_180128170
0x1800734d7  cmp     eax, 5
0x1800734da  jbe     short loc_1800734FE
0x1800734dc  lea     rax, aTheConnectionL_1; "The connection limit will be exceeded i"...
0x1800734e3  mov     [rsp+160h+var_108], rax
0x1800734e8  lea     rax, [rsp+160h+var_108]
0x1800734ed  mov     [rsp+160h+var_140], rax
0x1800734f2  lea     rdx, byte_18010B9AD
0x1800734f9  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800734fe  mov     ebx, 80071B8Eh
0x180073503  mov     r9, r15
0x180073506  mov     r8d, ebx
0x180073509  lea     rdx, aExceedListener_1; "Exceed listener max instance count fail"...
0x180073510  mov     ecx, 8; int
0x180073515  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007351a  jmp     loc_1800738A7
0x18007351f  mov     rax, [rdi]
0x180073522  mov     rcx, rdi
0x180073525  mov     rax, [rax+2F0h]
0x18007352c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073531  mov     r13d, 1
0x180073537  cmp     eax, r13d
0x18007353a  jnz     loc_180073669
0x180073540  mov     [rsp+160h+var_F0], r13d
0x180073545  lea     rcx, [rsp+160h+var_F0]; int *
0x18007354a  call    ?IsSingleSessionPerUser@CUtils@@SAJPEAH@Z; CUtils::IsSingleSessionPerUser(int *)
0x18007354f  mov     ebx, [rsp+160h+var_F0]
0x180073553  test    eax, eax
0x180073555  cmovs   ebx, r13d
0x180073559  mov     eax, cs:dword_180128170
0x18007355f  cmp     eax, 5
0x180073562  jbe     short loc_180073594
0x180073564  mov     [rsp+160h+var_F0], ebx
0x180073568  lea     rax, aSinglesessionp; "SingleSessionPerUser"
0x18007356f  mov     [rsp+160h+var_108], rax
0x180073574  lea     rax, [rsp+160h+var_F0]
0x180073579  mov     [rsp+160h+var_138], rax
0x18007357e  lea     rax, [rsp+160h+var_108]
0x180073583  mov     [rsp+160h+var_140], rax
0x180073588  lea     rdx, byte_18010B973
0x18007358f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180073594  test    ebx, ebx
0x180073596  jnz     short loc_1800735DD
0x180073598  mov     eax, cs:dword_180128170
0x18007359e  cmp     eax, 3
0x1800735a1  jbe     short loc_1800735D3
0x1800735a3  mov     [rsp+160h+var_110], ebx
0x1800735a7  lea     rax, aBasicFastRecon; "Basic Fast Reconnect is not supported"
0x1800735ae  mov     [rsp+160h+var_108], rax
0x1800735b3  lea     rax, [rsp+160h+var_110]
0x1800735b8  mov     [rsp+160h+var_138], rax
0x1800735bd  lea     rax, [rsp+160h+var_108]
0x1800735c2  mov     [rsp+160h+var_140], rax
0x1800735c7  lea     rdx, byte_18010B939
0x1800735ce  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800735d3  mov     ebx, 80070032h
0x1800735d8  jmp     loc_1800738A0
0x1800735dd  lea     r9, [rbp+60h+var_C0]
0x1800735e1  mov     r8, rdi
0x1800735e4  mov     rdx, r14
0x1800735e7  mov     rcx, rsi
0x1800735ea  call    ?FindUserSessionToReconnect@CDefaultConnectionHandler@@AEAAJPEAVIRemoteTerminal@@PEAVIConnection@@AEAV?$DynArray@JK@@@Z; CDefaultConnectionHandler::FindUserSessionToReconnect(IRemoteTerminal *,IConnection *,DynArray<long,ulong> &)
0x1800735ef  mov     ebx, eax
0x1800735f1  test    eax, eax
0x1800735f3  jns     loc_1800736C6
0x1800735f9  mov     eax, cs:dword_180128170
0x1800735ff  cmp     eax, 3
0x180073602  jbe     loc_1800738A0
0x180073608  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x18007360f  mov     [rsp+160h+var_108], rax
0x180073614  lea     rax, aFindusersessio; "FindUserSessionToReconnect"
0x18007361b  lea     rdx, dword_18010B8FC
0x180073622  mov     [rsp+160h+var_110], ebx
0x180073626  mov     [rsp+160h+var_100], rax
0x18007362b  lea     rax, aWarningHresult; "Warning HResult failed"
0x180073632  mov     qword ptr [rsp+160h+var_F0], rax
0x180073637  lea     rax, [rsp+160h+var_108]
0x18007363c  mov     [rsp+160h+var_128], rax
0x180073641  lea     rax, [rsp+160h+var_110]
0x180073646  mov     [rsp+160h+var_130], rax
0x18007364b  lea     rax, [rsp+160h+var_100]
0x180073650  mov     [rsp+160h+var_138], rax
0x180073655  lea     rax, [rsp+160h+var_F0]
0x18007365a  mov     [rsp+160h+var_140], rax
0x18007365f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180073664  jmp     loc_1800738A0
0x180073669  mov     rax, [rdi]
0x18007366c  mov     rcx, rdi
0x18007366f  mov     rax, [rax+2F0h]
0x180073676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007367b  cmp     eax, 2
0x18007367e  jnz     short loc_1800736C6
0x180073680  lea     r9, [rbp+60h+var_C0]
0x180073684  mov     r8, rdi
0x180073687  mov     rdx, r14
0x18007368a  mov     rcx, rsi
0x18007368d  call    ?FindUserSessionForEnhancedReconnect@CDefaultConnectionHandler@@AEAAJPEAVIRemoteTerminal@@PEAVIConnection@@AEAV?$DynArray@JK@@@Z; CDefaultConnectionHandler::FindUserSessionForEnhancedReconnect(IRemoteTerminal *,IConnection *,DynArray<long,ulong> &)
0x180073692  mov     ebx, eax
0x180073694  test    eax, eax
0x180073696  jns     short loc_1800736C6
0x180073698  mov     eax, cs:dword_180128170
0x18007369e  cmp     eax, 3
0x1800736a1  jbe     loc_1800738A0
0x1800736a7  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x1800736ae  mov     [rsp+160h+var_108], rax
0x1800736b3  lea     rax, aFindusersessio_0; "FindUserSessionForEnhancedReconnect"
0x1800736ba  lea     rdx, byte_18010B8BF
0x1800736c1  jmp     loc_180073622
0x1800736c6  mov     eax, dword ptr [rbp+60h+var_B8+4]
0x1800736c9  test    eax, eax
0x1800736cb  jnz     short loc_180073706
0x1800736cd  mov     ecx, 80070002h
0x1800736d2  mov     ebx, ecx
0x1800736d4  mov     eax, cs:dword_180128170
0x1800736da  cmp     eax, 3
0x1800736dd  jbe     loc_1800738A0
0x1800736e3  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x1800736ea  mov     [rsp+160h+var_108], rax
0x1800736ef  mov     [rsp+160h+var_110], ecx
0x1800736f3  lea     rax, aNoSessionToFas; "No session to fast reconnect"
0x1800736fa  lea     rdx, word_18010B882
0x180073701  jmp     loc_180073626
0x180073706  cmp     eax, r13d
0x180073709  jbe     loc_180073795
0x18007370f  mov     ebx, 80070032h
0x180073714  mov     eax, cs:dword_180128170
0x18007371a  cmp     eax, 3
0x18007371d  jbe     loc_1800738A0
0x180073723  mov     eax, dword ptr [rbp+60h+var_B8+4]
0x180073726  mov     [rsp+160h+var_110], eax
0x18007372a  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180073731  mov     [rsp+160h+var_108], rax
0x180073736  mov     [rsp+160h+var_F0], ebx
0x18007373a  lea     rax, aTooManySesssio; "Too many sesssion to fast reconnect"
0x180073741  mov     [rsp+160h+var_100], rax
0x180073746  lea     rax, aWarningHresult; "Warning HResult failed"
0x18007374d  mov     [rsp+160h+var_F8], rax
0x180073752  lea     rax, [rsp+160h+var_110]
0x180073757  mov     [rsp+160h+var_120], rax
0x18007375c  lea     rax, [rsp+160h+var_108]
0x180073761  mov     [rsp+160h+var_128], rax
0x180073766  lea     rax, [rsp+160h+var_F0]
0x18007376b  mov     [rsp+160h+var_130], rax
0x180073770  lea     rax, [rsp+160h+var_100]
0x180073775  mov     [rsp+160h+var_138], rax
0x18007377a  lea     rax, [rsp+160h+var_F8]
0x18007377f  mov     [rsp+160h+var_140], rax
0x180073784  lea     rdx, word_18010B82A
0x18007378b  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180073790  jmp     loc_1800738A0
0x180073795  lea     r8, [rsp+160h+var_110]
0x18007379a  xor     edx, edx
0x18007379c  lea     rcx, [rbp+60h+var_C0]
0x1800737a0  call    ?GetAt@?$DynArray@JK@@UEAAHKPEAJ@Z; DynArray<long,ulong>::GetAt(ulong,long *)
0x1800737a5  test    eax, eax
0x1800737a7  jnz     short loc_180073816
0x1800737a9  mov     ecx, 80070002h
0x1800737ae  mov     ebx, ecx
0x1800737b0  mov     eax, cs:dword_180128170
0x1800737b6  cmp     eax, 3
0x1800737b9  jbe     loc_1800738A0
0x1800737bf  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x1800737c6  mov     [rsp+160h+var_F8], rax
0x1800737cb  mov     [rsp+160h+var_110], ecx
0x1800737cf  lea     rax, aNoSessionToRec_0; "No session to reconnect"
0x1800737d6  mov     [rsp+160h+var_108], rax
0x1800737db  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800737e2  mov     [rsp+160h+var_100], rax
0x1800737e7  lea     rax, [rsp+160h+var_F8]
0x1800737ec  mov     [rsp+160h+var_128], rax
0x1800737f1  lea     rax, [rsp+160h+var_110]
0x1800737f6  mov     [rsp+160h+var_130], rax
0x1800737fb  lea     rax, [rsp+160h+var_108]
0x180073800  mov     [rsp+160h+var_138], rax
0x180073805  lea     rax, [rsp+160h+var_100]
0x18007380a  lea     rdx, byte_18010B7ED
0x180073811  jmp     loc_18007365A
0x180073816  call    cs:__imp_GetTickCount64
0x18007381c  mov     r15, rax
0x18007381f  lea     rcx, [rbp+60h+var_D0]; struct ISessionList **
0x180073823  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180073828  mov     ebx, eax
0x18007382a  test    eax, eax
0x18007382c  jns     loc_180073978
0x180073832  mov     eax, cs:dword_180128170
0x180073838  cmp     eax, 3
0x18007383b  jbe     short loc_180073899
0x18007383d  lea     rax, aAttempfastreco; "AttempFastReconnectToExistingSession"
0x180073844  mov     [rsp+160h+var_F8], rax
0x180073849  lea     rax, aGetsessionlist_1; "GetSessionList"
0x180073850  lea     rdx, qword_18010B7B0
0x180073857  mov     [rsp+160h+var_108], rax
0x18007385c  lea     rax, aWarningHresult; "Warning HResult failed"
0x180073863  mov     [rsp+160h+var_100], rax
0x180073868  lea     rax, [rsp+160h+var_F8]
0x18007386d  mov     [rsp+160h+var_128], rax
0x180073872  lea     rax, [rsp+160h+var_110]
0x180073877  mov     [rsp+160h+var_130], rax
0x18007387c  lea     rax, [rsp+160h+var_108]
0x180073881  mov     [rsp+160h+var_138], rax
0x180073886  lea     rax, [rsp+160h+var_100]
0x18007388b  mov     [rsp+160h+var_110], ebx
0x18007388f  mov     [rsp+160h+var_140], rax
0x180073894  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180073899  lea     r15, aCdefaultconnec_0; "CDefaultConnectionHandler::AttempFastRe"...
0x1800738a0  lea     r13, aFastReconnect; "Fast Reconnect"
0x1800738a7  mov     eax, cs:dword_180128170
0x1800738ad  cmp     eax, 4
0x1800738b0  jbe     short loc_1800738EA
0x1800738b2  mov     dword ptr [rsp+160h+var_100], ebx
0x1800738b6  mov     [rsp+160h+var_E8], r15
0x1800738bb  mov     [rsp+160h+var_F8], r13
0x1800738c0  lea     rax, [rsp+160h+var_100]
0x1800738c5  mov     [rsp+160h+var_130], rax
0x1800738ca  lea     rax, [rsp+160h+var_E8]
0x1800738cf  mov     [rsp+160h+var_138], rax
0x1800738d4  lea     rax, [rsp+160h+var_F8]
0x1800738d9  mov     [rsp+160h+var_140], rax
0x1800738de  lea     rdx, byte_18010B683
0x1800738e5  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800738ea  test    ebx, ebx
0x1800738ec  jns     short loc_18007391C
0x1800738ee  mov     eax, cs:dword_180128170
0x1800738f4  cmp     eax, 4
0x1800738f7  jbe     short loc_18007391C
0x1800738f9  lea     rax, aFastReconnectF_0; "Fast Reconnect failed, using default ac"...
0x180073900  mov     [rsp+160h+var_E8], rax
0x180073905  lea     rax, [rsp+160h+var_E8]
0x18007390a  mov     [rsp+160h+var_140], rax
0x18007390f  lea     rdx, word_18010B62A
0x180073916  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
  ... truncated ...
```
